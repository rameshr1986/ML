# Techniques in the project
In this project we got the uk house pricing dataset to predict the price of the property in UK. We used the dataset but due to my limitations on my laptop i have used 20% of the complete dataset which still contains around 180000 records taken randomly

We would like to add some extra features to the table which bank of england interest rates based on year and its impact is crucial in deterining the price of the property. For example after covid the interest rate was too low which spiked the property. With increase in interest rate the rate of property price increase every year has been reduced.

## Steps done in the project
  1. The data is taken from kaggle with property prices from 1995 to 2023.
  2. We take the data as chunks as a large data set and from each chunk we select a random sample so that all types of data is represented in each chunk
  3. There are some alternatives such as  dask, datatable which we can use to do parallel or distributed loading. But due to machine contraints we did the random sampling of each chunk from whole dataset.
  4. Since Price is the target feature it does not need to be scaled.
  5. Non null values are droped from price with median value of price.
  6. Date of Teansfer is split in to Date, Day and month
  7. Other categorical parameters are scaled in to numerical variables and new table has been created
  8. Price, Date of Transfer are dropped from the original table as they are used in other ways or a target variable
  9. Different models including, Logistic regression, XGBoost, RandomForestRegressor are applied and XGBoost is selected based on Mean average error. Since the house prices are varied from 10K gbp to 8 million gbp mean average error is on the range of 30 to 60 gbp for xgboost.
  10. Xgboost is tried with max depth from 5 to 12 and we got a better value at max_depth=7 so that we do not underfit or overfit
  
