# CS815_trading

In this repo, we attempt to create a trading bot that automates the decision-making process based on next-day prediction. So there are 2 main tasks:

(1) Produce a reliable next day time-series prediction - this is solved using a bidirectional Long Short Term Memory (LSTM) neural network with a mix of financial indicators to incorporate long-term trends while maintaining a small data time window

(2) Using the time prediction, we then need to develop a trading strategy to generate buy/hole/sell tickers for our automated trading operation. To determine the trading strategy, we use evolutionary programming to iteratively test for an optimal solution.

The stocks we picked are from the S&P100 to ascertain liquidity and transparency. From this, we picked the top 20 stocks based on market cap and data availability during the period of 2016 to 2019 (Only stocks that was listed throughout this whole period will be chosen). From the next day's price prediction, we utilize an evolutionary algorithm to determine an optimal trading strategy to work with 

We perform next-day closing price prediction, using a time window of 5 prior trading days (equivalent to 1 week) and use MSE to measure the prediction for comparison - the use of momentum technical indicators helps improve the prediction as it incorporates information from a much longer time window (up to 50 days), this help reduce training time as each stock will require us to train a separate model. 
![test_stock_predict](https://github.com/trduc97/CS815_trading/assets/52210863/983a9940-849a-4157-89b7-7cd91666bd4d)

After having an optimal price prediction, we used evolutionary programming to iteratively test out an optimal trading strategy that can utilize the prediction, along with the available financial indicators 

![Trading_strategy](https://github.com/trduc97/CS815_trading/assets/52210863/246c12e0-e6c7-40f5-913e-4b764adf2e0d)

Overall, we can determine a trading strategy that can mirror the performance of the stocks, but with minimal holding time.

![trading_result](https://github.com/trduc97/CS815_trading/assets/52210863/4563cb8e-6c02-4753-b53d-77482e319007)

