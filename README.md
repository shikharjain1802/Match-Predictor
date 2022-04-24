# Match Predictor 

## About 

- Project repository for SC1015 (Introduction to Data Science and Artificial Intelligence)
- Uses IPL Complete Dataset 2008-2020 (https://www.kaggle.com/datasets/patrickb1912/ipl-complete-dataset-20082020), obtained from Kaggle.
- Dataset contains CSV files which provide essential data about 816 matches played in the Indian Premier League between 2008 and 2020.

## Contributors

- @shikharjain1802
- @chinmay-002
- @emmanuelmthomas

## Problem Definition

- Can the outcome of a cricket match be predicted using the initial 75% of the data from both innings?
- Which ML algorithm (classification or regression) would be better for this prediction?

## Models Used

1. Multivariate Linear Regression
2. Random Forest Classification

## Process

1. Preparing the Data: 
- Cleaned the dataset by removing abandonded or incomplete match data, and other outliers.
- Created 5 predictor variables by manipulating provided dataset: current score, wickets left, weighted economy, average strike rate, average runs of current batsmen
- Response variable: outcome of the match
2. Multivariate Linear Regression:
- Used 75:25 train test data split in order to train data.
- Obtained multivariate regression equation with coefficients for each of the predictor variables.
- Plotted resultant regression line that predicted final score of an innings.
- Compared final scores to calculate outcome of the match.
- Accuracy: 73.45%
3. Random Forest Classification:
- Used 75:25 train test data split in order to train data.
- Refined dataframe to combine both innings of the match into one record.
- Model creates numerous indivudal decision trees which return class prediction. At the end, majority vote is taken to determine final class.
- Model predicted outcome of each match based on data from both innings.
- Accuracy: 80.80%

## Conclusion

- Random Forest classification had greater accuracy than multivariate linear regression. Probable explanation:
(i) Random Forest predicts a class, while regression model predicts numeric value which is then compared. Therefore, regression has greater susceptibility to error.
(ii) Multivariate regression used is suited to linear data, while Random Forest is better at capturing non-linearity.
- It is possible to predict the match outcome from 75% of the data from both innings, with accuracy of the models ranging from 73-81%.
- Models used data from only 816 matches. Accuracy can be improved significantly with greater sample size.
- Potential predictor variables could be: historical performance of teams and players in the match, home team advantage, effect of pitch conditions.
- IPL uses projected score metric to predict final score, which is based solely on current score. With increased accuracy, our project can potentially replace this metric.

## What did we learn from this project?

- Manipulating Pandas DataFrame to extract required variables.
- Resetting indices, sorting values, and removing redundant values.
- Pandas.DataFrame.groupby()
- Concatentation to recombine data
- Calculating cumulative sum
- Regression with multiple predictor variables
- Random Forest as an improved version of single classification tree

## References

- <https://www.kaggle.com/datasets/patrickb1912/ipl-complete-dataset-20082020>
- <https://pandas.pydata.org/docs/reference/frame.html>
- <https://medium.com/analytics-vidhya/evaluating-a-random-forest-model-9d165595ad56>
- <https://towardsdatascience.com/five-regression-python-modules-that-every-data-scientist-must-know-a4e03a886853>
- <https://www.w3schools.com/python/python_ml_multiple_regression.asp>
- <https://towardsdatascience.com/all-pandas-groupby-you-should-know-for-grouping-data-and-performing-operations-2a8ec1327b5>
