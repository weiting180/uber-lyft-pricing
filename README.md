# Uber and Lyft Pricing Analysis
## Data Description

This data is accessed from [Kaggle](https://www.kaggle.com/brllrb/uber-and-lyft-dataset-boston-ma), I implemented several regression models to analyze the pattern between the features. There are original 57 features and 637976 instances, I reduced the number of rows to 10000 and kept 24 features on this project pupose. Let's check the definition for each feature below:
- id - Unique identifier for each column
- Timestamp - Unix Timestamp
- hour - Hour of the day
- day - Day of the week
- month - Month in a year
- datetime - Date value
- timezone - Timezone
- source - Initial source of the ride
- destination - Destination of the ride
- cab_type - The type of cab
- price - Price of the ride
- distance - Total distance of the requested ride
- surge_multiplier - Times of the normal price
- temperature - Temperature of the ride
- apparentTemperature - Apparent temperature of the ride
- summary - weather report summary of the day
- humidity - Humidity of the ride
- windSpeed - Wind speed of the ride
- windGust - Wind gust of the ride
- uvIndex - UV index of the ride

## Procedure
1. Generate random NA

   Artificially replaced around 6% of the original records with NA across the data
   
2. Data imputation

   There're 5.8% missing values after we artificial replacement. I simply fill the NA with builtin method, fill forward and fill backward.
   
3. Exploratory data analysis

   It's always a mandatory step for all the analysis, as it can help you know your data better! Otherwise, garbage in garbage out.
   
4. Modeling

   This project included Simple Linear Regression, KNN Regressor, Ridge and Lasso Regression, Polynomial Regression, Linear SVR, and SVR with kernel. I aopted GridsearchCV method to find the best hyperparameters for each models if applicable. Also, I provided the visualizations for their training and validation score to see if there existed overfittng issue.
   
## Conclusion
The best regression model is SVR with polynomial kernel (SVR-poly) as it performs highest average cross-validation score and r-squared in this task, 0.8189 and 0.8305 respectively. The test score and mean squared error for prediction is 0.8258 and 14.2253 respectively. In other words, the SVR-poly is able to explain 82.58% of the data.
