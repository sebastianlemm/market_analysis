Modeling the SPY? -An Analysis of Historical SPY Data Using Time Series Data with Facebook's Prophet Model

Introduction: In recent years, the intersection of quantitative finance and machine learning has 
spurred an increased focus on leveraging advanced algorithms to predict and model financial 
markets. This paper investigates the application of Facebook's Prophet model, a robust time 
series forecasting tool, to model the behavior of the S&P 500 Index ETF (SPY) using 
historical closing prices from 1993 to 2023 obtained from Yahoo Finance. As part of the broader 
landscape of market modeling, this study aims to offer insights into the potential of modern 
forecasting techniques to capture the complexities and nuances of financial markets effectively.

The Data: The historical data for the S&P 500 Index ETF (SPY) can be accessed via the URL 
'https://finance.yahoo.com/quote/SPY/history/'. The data consists of several key variables, 
including Date, Open, High, Low, Close, Adjusted Close, and Volume, which provide a 
comprehensive overview of the ETF's performance since its inception in 1993. In addition, 
historical interest rate data from the Federal Reserve (Fed) was incorporated into the dataset, 
and was sourced from FRED. 

The dataset's chronological arrangement, with consistent daily records (excluding weekends and 
holidays), makes it a good dataset for time series analysis using the Prophet model. The 
Prophet model is specifically designed for handling time series data, as it can effectively capture 
trends, seasonality, and holidays, to create a model that accurately follows the data. In this
context, the SPY historical data, including the Fed interest rates, serve as good input for the 
model.

By focusing on the Close price, which represents the final price at which the ETF was traded on 
a given day, the analysis can incorporate a direct and straightforward representation of the ETF's 
value over time, while trying to take into account the impact of changes in the Fed interest rates 
on the stock market. Consequently, this dataset provides a solid foundation for exploring the 
potential of the Prophet model in forecasting and understanding the behavior of financial 
markets.

Literature Review: Recent literature on financial market forecasting has explored various 
machine learning and statistical techniques to predict stock prices and other financial 
instruments. Examples include the use of recurrent neural networks (RNNs), long short-term 
memory (LSTM) networks, autoregressive integrated moving average (ARIMA) models, and 
various forms of regression analysis. The Prophet model, developed by Facebook, has gained 
popularity in recent years due to its flexibility, scalability, and capability to handle missing data, 
outliers, and changes in seasonality patterns.

Methodology: My methodology will involve cleaning the SPY historical data to 
accommodate the requirements of the Prophet model. This process includes transforming the 
dataset into a date column labeled ‘ds’ and the value column labeled as ‘y’. To add Holidays and 
the Fed Interest Rate as a regressor additional coding had to be implemented to the model. The 
research explored various model configurations, such as the incorporation of external regressors 
like the Fed interest rates, to assess their impact on the model's accuracy.

The model's performance was evaluated using standard metrics such as the coefficient of 
determination (R^2) and mean squared error (MSE). Comparisons were made between the 
different model configurations to determine the accuracy of the Prophet model in capturing the 
behavior of the SPY.

The Research Question: This research seeks to answer the question: Can we model the price of 
stocks well enough to make accurate predictions using advanced machine learning techniques? 
The primary objective of this study is to assess the feasibility of modeling the price of the SPY 
(S&P 500 ETF), which serves as a proxy for other stocks, in order to generate precise forecasts 
for future performance. The SPY is an exchange-traded fund that closely mirrors the 
performance of the S&P 500 index, making it a suitable representative for the broader stock 
market. By determining the effectiveness of predictive models for the SPY, we can gain insights 
into the potential of using similar approaches for individual stocks and other financial 
instruments, ultimately contributing to a deeper understanding of the dynamics and predictability 
of financial markets.

Model Evaluation and Comparison: To determine the efficacy of various models in predicting 
the SPY's performance, the coefficient of determination (R^2) and mean squared error (MSE) 
were calculated for each model. Different variations of the 'Prophet' model were employed in an 
attempt to identify the one with the highest R^2 and the lowest MSE among all models.
The variations considered in this study included analyzing SPY data dating back to 1993, 2017, 
and 2019. Additionally, both the linear growth model and the logistic growth model of the 
Prophet model were tested. By exploring these variations, the study aimed to identify the optimal 
combination of parameters that would yield the most accurate predictions.

Furthermore, I sought to enhance the models by incorporating the federal funds rate as an 
additional regressor. This step was taken to examine whether the inclusion of this economic 
indicator could improve the fit of the model. Upon integrating the federal funds rate, noticeable 
shifts in the predicted values were observed, as evidenced by the graphical representations of the 
forecasts.
 
(Model looking at data going back to 2018, looking at actual Close price)
 
(Model after adding the interest rate as a regressor)
 
(Model with best fit actuals, although this was a model for the log values of the close price)

Overall, of all the models tested, the one with the highest R^2 score and lowest MSE statistic 
utilized data going back to 2020 and accounted for US Holidays. This model employed a linear 
growth model focusing on the natural logarithm of the close price of the SPY in order to reduce 
noise and better capture the underlying trends. The results suggest that this particular model 
configuration, which did not incorporate the federal funds rate as a regressor, is more effective in 
predicting the SPY's performance. These findings indicate that accounting for US Holidays in 
the model increases the accuracy of the model much more than adding the federal interest rate as 
a regressor. Additionally, there appears to be an optimal history of data going back about 3 years. 

Implications and Future Work: The study's results provide valuable insights into the potential of 
machine learning algorithms, specifically the Prophet model, to predict financial market trends. 
The findings highlight the importance of considering seasonality and holidays in financial time 
series analysis, which may contribute to a more accurate understanding of market dynamics. 
Additionally, the results indicate that while the incorporation of macroeconomic indicators, such 
as the federal funds rate, may lead to noticeable shifts in predicted values, their impact on the 
model's overall accuracy may be limited.

Future work could include an exploration of other machine learning techniques, such as deep 
learning models like LSTMs and RNNs, to determine their effectiveness in financial market 
forecasting compared to the Prophet model. Moreover, the integration of alternative economic 
indicators, such as inflation rates or GDP growth, may provide further insights into the factors 
influencing the accuracy of financial market predictions. By investigating these avenues, 
researchers can continue to enhance the understanding of financial market dynamics and develop 
more sophisticated models for forecasting purposes.




















Sources Cited 

Yahoo Finance. "SPDR S&P 500 ETF Trust (SPY) Stock Historical Prices & Data." Yahoo Finance, 2023, https://finance.yahoo.com/quote/SPY/history?period1=1642377600&period2=1679011200&interval=1d&filter=history&frequency=1d&includeAdjustedClose=true.
Federal Reserve Economic Data. "Effective Federal Funds Rate (FEDFUNDS)." Federal Reserve Bank of St. Louis, 2023, https://fred.stlouisfed.org/series/FEDFUNDS.
Taylor, Sean J., and Benjamin Letham. "Prophet: Automatic Forecasting Procedure." Facebook Research, 2017, https://research.fb.com/prophet-forecasting-at-scale/.
