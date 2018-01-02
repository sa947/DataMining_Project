# DataMining_Project
Credit Card Fraud Detection Using Random Forest Classifier With k fold cross validaiton

Worked on the following dataset
https://www.kaggle.com/dalpozz/creditcardfraud/data

Code Description 

1.	Load all required packages and libraries
2.	Read the dataset in csv file into raw.dt
3.	Using the correlation function corr(), plot the correlation matrix between attributes against each other (using Pearson correlation coefficient)
4.	Wrote a function to calculate the TPR and FPR for various threshold in order to plot the ROC curve later in evaluating the models
5.	k fold cross validation with Random Forest
•	Set k as 10
•	Assign id’s (1-10) to each tuple in order to group the entire dataset into 10 folds
•	Create 2 data frames to hold Predicted and Actual classes for each tuple after training and testing the model
•	Iterate from 1 through 10 (10 times):
¬	At every ith iteration, form trainset combining all folds except ith fold. Reserve the ith fold for test
¬	Train the random forest model with 10 tress
¬	Test on the set to get predicted class for each test set. Combine them during each iteration and capture it in the first data frame created to hold Predicted class. While capturing the actual class of test tuples into the second data frame.
¬	Provided a progress bar to show the status
•	After all 10 iterations, combine the two data frames mentioned above into a single result dataset. Label the two columns as predicted and class(actual) respectively.
•	Pass the result as parameter to the function we defined earlier to make the table (output the table as csv file) 
•	Plot the ROC curve for a reference threshold (here it is 0.3)
•	To produce the confusion matrix
¬	Calculate the TP,FN,FP,TN counts from the above result dataset 
¬	Make a table with the 4 values 

6.	k fold cross validation with Random Forest (After Over Sampling)
•	Using ovun.sample() function oversample the minority (fraud) class to form a balanced class sample. 
•	Consider the above dataset for 10 fold cross validation with RF (Followed step 5)
•	Since the results show an overfitting problem, we tried doing oversampling and training RF by data partitioning
•	Divide the raw dataset in the ratio 7:3
•	Using ovun.sample() function over sample the training set
•	Test the model on test set and find predicted values
•	Combine the predicted and actual into a single result set
•	Using roc.curve() function, plot the ROC curve

ϖ	k fold cross validation with Random Forest (After Under Sampling)
•	Using ovun.sample() function under sample the majority (non fraud) class from the raw dataset
•	Consider the above balanced dataset for 10 fold cross validation with RF (Followed step 5)


