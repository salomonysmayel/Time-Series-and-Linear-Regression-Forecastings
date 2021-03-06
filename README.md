# Time Series Forecasting and Linear Regression Modeling

In this project, different time-series tools were tested in order to predict future movements in the value of the Japanese yen versus the U.S. dollar.

### Time-Series Forecasting

First, historical Dollar-Yen exchange rate futures data is loaded to apply time series analysis and modeling to determine whether there is any predictable behavior.

Following these steps:

Decomposition using a Hodrick-Prescott Filter (Decomposing the Settle price into trend and noise).
Forecasting Returns using an ARMA Model.
Forecasting the Settle Price using an ARIMA Model.
Forecasting Volatility with GARCH.

The results of the time series analysis and modeling was used to answer the followwing questions:

Based on the time series analysis, would it be wise to but yen now?
Is the risk of the yen expected to increase or decrease?
Based on the model evaluation, would it be wise to use these models for trading?


### Linear Regression Forecasting

In this section a Scikit-Learn linear regression model was built to predict Yen futures ("settle") returns with lagged Yen futures returns and categorical calendar seasonal effects (e.g., day-of-week or week-of-year seasonal effects).

Following these steps:

Data Preparation (Creating Returns and Lagged Returns and splitting the data into training and testing data)


![supply_chain](/images/data.png)


![supply_chain](/images/lagged_returns.png)

Fitting a Linear Regression Model.

![supply_chain](/images/lmodel.png)

Making predictions using the testing data.

![supply_chain](/images/pred.png)

![supply_chain](/images/pred_plots.png)

Out-of-sample performance.
In-sample performance.

![supply_chain](/images/in_out.png)

The results of the linear regression analysis and modeling were used to answer the following question:

Does this model perform better or worse on out-of-sample data compared to in-sample data?

## Results

### Time series analysis

Based on the time series analysis, would it be wise to but yen now?

Based on the time series analysis, for the ARIMA model, I would buy the yen, for a 5 day forecasting the price of the yen is predicted to grow. Based on the the ARMA model I wouldn't buy, since the projection shows that the price will drop, for  a 5 day forecasting.

Is the risk of the yen expected to increase or decrease?

According to the GARCH volatility forecasting the risk of the yen is expected to increase when we see values calculated for our forecast horizon. The forecastig shows that for 5 days time horizon the volatility will be incremental from day to day.

Based on the model evaluation, would it be wise to use these models for trading?

Since for both ARMA and ARIMA models the P>|z| values are way bigger than 0.05, the predictions could have been generated by a random process, in wich case I wouldn't recommend making a decision of whether to buy or not yens based on the forecasting of this models.

### Reggresion Analysis

Does this model perform better or worse on out-of-sample data compared to in-sample data?

The out of sample performance was better than the in sample, because the Root Mean Squared Error of the out of sample data is lower. 0.4152 < 0.5658. Meaning that the difference between values observed and predicted is lower. 

