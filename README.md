# Quora-Question-Pairs

## Problem Statement
The goal of this project is to predict which of the provided pairs of questions contain two questions with the same meaning

## Data Wrangling
- The questions were first all converted to lower case and then the all the stop words were removed to make it easier to compare the pairs
- Then, using a dictionary of all the words from Google News, the words in the questions were converted to vectors (word2vec)

## Feature Engineering
To make comparison of similarity easier, the following features were engineered:
• Word Mover's Distance
• Difference in length
• Common Words
• Fuzz Ratio
• Fuzz Partial Ratio
• Fuzz Partial Token Set Ratio
• Fuzz Token Set Ratio
• Fuzz Token Sort Ratio

Next, I wrote a function to convert each question into a vector itself (sent2vec)
Using these sentence vectors, the following features were engineered:
• Cosine Distance
• Cityblock Distance
• Jaccard Distance
• Canberra Distance
• Euclidean Distance
• Minkowski Distance
• Braycurtis Distance
• Skew Vectors
• Kurtosis Vectors

## The Model
Finally, after imputing the null values, I trained am XGBoost Classifier on the training data and then predicted the probability of each question pair being similar based on the features engineered.
Achieved an accuracy of 78%
