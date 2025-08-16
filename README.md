## INR to USD Exchange Rate Forecasting with SARIMA

This repository contains a Google Colab notebook that demonstrates the process of forecasting the INR to USD exchange rate using a Seasonal Autoregressive Integrated Moving Average (SARIMA) model.

## Project Overview

The project aims to analyze historical INR to USD exchange rate data, identify patterns and seasonality, and build a time series forecasting model to predict future exchange rates. The SARIMA model is chosen due to the apparent seasonality in the data.

## Data

The data used in this notebook is the historical INR to USD exchange rate, sourced from a CSV file (`INR-USD.csv`). The data includes the following columns:

- `Date`: The date of the exchange rate observation.
- `Open`: The opening exchange rate for the period.
- `High`: The highest exchange rate during the period.
- `Low`: The lowest exchange rate during the period.
- `Close`: The closing exchange rate for the period.
- `Adj Close`: The adjusted closing exchange rate for the period.
- `Volume`: The trading volume.

## Methodology

The notebook follows these steps:

1.  **Data Loading and Preparation:** Loading the exchange rate data and handling missing values.
2.  **Exploratory Data Analysis (EDA):** Visualizing the closing exchange rate over time and analyzing yearly and monthly growth patterns.
3.  **Seasonal Decomposition:** Decomposing the time series to identify trend, seasonality, and residuals.
4.  **SARIMA Model Selection:** Using `auto_arima` to automatically determine the optimal SARIMA model orders (p, d, q) and seasonal orders (P, D, Q, m).
5.  **SARIMA Model Fitting:** Fitting the SARIMA model to the historical data.
6.  **Forecasting:** Generating future exchange rate predictions using the fitted model.
7.  **Model Interpretability:** Explaining the SARIMA model results, including coefficients, p-values, information criteria, and the impact of the chosen orders on predictions. Discussing the assumptions and limitations of the SARIMA model.

## Key Findings

- The INR to USD exchange rate exhibits a clear upward trend and significant yearly seasonality.
- The `auto_arima` process identified a SARIMA(2, 1, 0)x(2, 1, 0, 52) model as suitable for this data, capturing both non-seasonal and seasonal dependencies.
- The seasonal components at lags 52 and 104 were found to be statistically significant, highlighting the importance of the yearly pattern in forecasting.
- While the model captures trend and seasonality, residual analysis indicated potential areas for improvement, such as non-normally distributed and heteroskedastic residuals.

## How to Use

To run this notebook:

1.  Clone this repository.
2.  Open the `inr_usd_forecasting.ipynb` notebook in Google Colab.
3.  Run the cells sequentially to execute the data analysis, modeling, and forecasting steps.

## Dependencies

The main libraries used in this notebook include:

- pandas
- numpy
- matplotlib
- seaborn
- plotly
- pmdarima
- statsmodels

These dependencies are installed within the notebook environment.
