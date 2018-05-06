# Predicting Fraud Mobile Money Transactions

## Team member: 

Yunhe Zhang(1701213157)

## Motivation:

Mobile payment has become a convenient way of payment in our life. Transaction size has risen rapidly in recent years. But fraud transactions happen more frequently at the same time.Thus it is useful to identify the relationship between transaction’s characters and the probability of the transaction being a fraud. In this way, mobile payment platforms can detect timely and remind consumers of payment risk.

## Goal:

The research is aimed at finding out the most satisfying model to predict whether a transaction is a fraud or not according to characters of the transaction.

## Dataset：

https://www.kaggle.com/ntnu-testimon/paysim1/data

## Data description:

Dataset used is called "Synthetic Financial Datasets For Fraud Detection", chosen from Kaggle website. The dataset contains 6,362,619 transactions. There are 11 variables in total. Variable "isFraud" is the target variable that we want to predict. Dependent variables include transaction type, amount, transaction starter's and receiver's balance account before and after transaction. The dataset is imbalanced because 99.87% of transactions are not fraud vesus 0.13% of transactions are.
* Independent Variable: isFraud
* Dependent Variable:
  * step:a unit of time in the real world(1 step is 1 hour of time)
  * type:transaction type, including CASH-IN, CASH-OUT, DEBIT, PAYMENT and TRANSFER
  * amount:amount of the transaction in local currency
  * oldbalanceOrg:initial balance of starter before the transaction
  * newbalanceOrig:balance of starter after the transaction
  * oldbalanceDest:initial balance of receiver before the transaction
  * newbalanceDest:balance of receiver after the transaction

## Methodology:

### Data preprocessing

Before classification analysis, I preprocess data at first. 
* Testing whether the dataset has any missing value
* String variables being encoded as class labels
* Data being separated into two parts--train set and test set
* Data being standardized

### Classification
* Methods:Logistics regression, random forest and KNN
* Model tuning: Stratified K-fold cross validation  
* Evaluation metrics:Accuracy and FPR 
* Technique:Assigning a larger penalty to wrong predictions on the minority class to deal with class imbalance problem

## Conclusion:

Comparing results of 3 models, we can see that test accuracy of logistics regression is the lowest,but it has the highest ratio of 1-False Positive rate.Considering its test accuracy is not so much lower and its 1-FPR is much higher than others, logistics regression has the most predictive power in this case.

See [.ipynb](https://github.com/zhang-yunhe/PHBS_TQFML-Project/Predicting Fraud Mobile Money Transactions.ipynb) for more details.
