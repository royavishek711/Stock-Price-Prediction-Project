# Stock-Price-Prediction-Project


This is a Python web application built using the Streamlit library for stock price forecasting. Here's a step-by-step explanation of the project:

Import Required Libraries: The first step is to import the necessary libraries, including Streamlit for creating the web app, datetime for handling date-related operations, yfinance for fetching stock data, Prophet for time series forecasting, and Plotly for data visualization.

Define Constants: Two constants are defined: START, representing the start date for fetching historical stock data, and TODAY, representing the current date.

Create a Streamlit Web App: The st.title function sets the title of the web app to "Stocks Forecasting Web Application."

Stocks Selection: Users can select a stock for prediction from a list of predefined stock symbols using the st.selectbox function. The selected stock symbol is stored in the selected_stock variable.

Prediction Duration Slider: Users can adjust the number of years for which they want to make stock price predictions using a slider. The selected value is stored in the n_years variable, which is then used to calculate the prediction period in days.

Load Historical Stock Data: The load_data function, decorated with @st.cache_data, is responsible for downloading historical stock data using the yfinance library. The data is fetched based on the selected stock symbol and date range, and it is displayed in the web app.

Display Raw Data: The raw historical stock data is displayed in a table format using st.subheader and st.write.

Plot Raw Data: The plot_raw_data function is used to create an interactive Plotly chart that displays the opening and closing prices of the selected stock over time. This chart is displayed using st.plotly_chart.

Time Series Forecasting with Prophet:

Historical data for the selected stock's closing prices is prepared in the format required by the Prophet library (with columns 'ds' for dates and 'y' for values).
A Prophet model is created and trained on this historical data.
A future dataframe is created to represent the period for which predictions are to be made.
Predictions for the future period are generated using the trained Prophet model.
Display Forecast Data: The forecasted data, including dates, predicted values, and uncertainty intervals, is displayed in a table format in the web app.

Display Forecast Plot: A Plotly chart is generated to visualize the stock price forecast for the specified number of years. This chart includes the historical data and forecasted values.

Display Forecast Components: The forecast components (trend, seasonality, and holidays) are displayed using another Plotly chart to provide insights into the decomposition of the time series data.

In summary, this web application allows users to select a stock symbol, choose a prediction duration, and then view historical stock data, a forecasted stock price plot, and the decomposition of the time series data. It uses the Prophet library for time series forecasting and Streamlit for creating the user interface. Users can interact with the app to explore and analyze stock price predictions for different stocks and timeframes.
