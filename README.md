# Apple Revenue Time Series Forecasting

This repository contains a Jupyter Notebook that demonstrates time series forecasting of Apple Inc.'s quarterly revenue using Python. The notebook walks through the complete process of preparing data, visualizing trends, building regression models with time components, and incorporating dummy variables to capture seasonal patterns.

## Overview

The notebook uses quarterly sales data from Compustat to build and evaluate time series forecasting models for Apple's revenue. Key steps include:

- **Data Preparation**: Loading and filtering quarterly sales data for Apple Inc.
- **Exploratory Data Analysis**: Visualizing revenue trends over time
- **Time Series Regression**: Creating a baseline model using time as a predictor
- **Dummy Variable Integration**: Adding seasonal indicators and interaction terms to improve model accuracy
- **Forecasting**: Generating predictions with confidence intervals

## Dataset

The dataset (`qSales_2024.csv`) contains quarterly financial data from Compustat for multiple companies, including:

- Apple Inc. (AAPL)
- Other companies with quarterly sales data

The data spans from 2001 to 2023, with 92 quarterly observations for Apple.

### Key Features Used:
- `datadate`: Quarter end date
- `saleq`: Quarterly sales/revenue in USD
- `fqtr`: Fiscal quarter (1-4)
- `tic`: Ticker symbol

## Models Implemented

### 1. Baseline Time Series Model
**Formula**: `Revenue = -13,536.82 + 1077.61 × Time`

A simple linear regression using time as the only predictor. This captures the overall upward trend in Apple's revenue.

### 2. Enhanced Model with Seasonal Dummies
**Formula**: `Revenue = -11,044.75 + 933.21 × Time - 10,422.13 × iPhone_DV + 578.33 × (Time × iPhone_DV)`

This model includes:
- **Time**: Linear time trend
- **iPhone_DV**: Dummy variable for fiscal quarter 1 (representing seasonal effects)
- **Interaction Term**: Allows the seasonal effect to change over time

## Key Findings

- Apple's quarterly revenue shows a strong upward trend over time
- There is a significant seasonal component, particularly in Q1 (the quarter ending in December)
- The seasonal effect has become more pronounced over the years

## Dependencies

The notebook requires the following Python packages:

- `pandas` - Data manipulation and analysis
- `numpy` - Numerical computing
- `matplotlib` - Data visualization
- `statsmodels` - Statistical modeling and regression

## Usage

1. Clone this repository
2. Ensure you have the required dependencies installed
3. Run the Jupyter Notebook in order:
   - Load and inspect the data
   - Prepare time variables
   - Split data into training (75%) and testing (25%) sets
   - Build and evaluate models
   - Generate forecasts with confidence intervals

## Results Visualization

The notebook includes visualizations showing:
- Historical revenue trends with clear upward trajectory
- Seasonal patterns in quarterly revenue
- Model predictions with confidence intervals

## Limitations and Future Work

- The model uses a simple linear approach; more sophisticated methods (ARIMA, SARIMA) could capture additional patterns
- External factors (economic conditions, product launches, market competition) are not included
- The data is quarterly, limiting the ability to capture within-quarter variations

## Contributing

Feel free to fork this repository and submit pull requests with improvements or additional models.

## License

This project is open source and available for educational purposes.

---

*Note: This is an educational exercise in time series forecasting and should not be used as the sole basis for financial decisions.*
