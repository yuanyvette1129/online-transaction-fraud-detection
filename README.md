# online-transaction-fraud-detection

# Background
- E-commerce fraud detection
- E-commerce websites often transact huge amounts of money. And whenever a huge amount of money is moved, there is a high risk of users performing fraudulent activities, eg. using stolen credit cards, doing money laundray, etc.

- Machine Learning really excels at identifying fraudulent activities. Any website where you put your credict card information has a risk team in charge of avoiding frauds via machine learning.

# Goal

The goal of this challenge is to build a machine learning model that predicts the probability that the first transaction of a new user is fraudulent.

# Data
- Company XYZ is an e-commerce site that sells eletronic products
- You have to build a model that predicts whether a user has a high probability of using the site to perform some illegal activity or not. This is a commom task for data scientists. You only have information about most of the user first transaction on the site and based on that you have to make your classification of fraud or no fraud.
- "Fraud_Data" information about each user first transaction
- "IpAddress_to_Country" mapping each numeric ip address to its country. For each country, it gives a range. If the numeric ip address falls within the range, then the ip address belongs to the correpsonding country

# Tasks
1. For each user, determine his/her country based on the numeric IP address
2. Build a model to predict whether an activity is fraudulent or not. Explain how different assumptions about the cost of false positives vs. false negatives would impact the model
3. Your boss is a bit worried about using a model she doesn't understand for something as important as fraud detection. How would you explain to her how the model is making the predictions? Not from a methematical perspective, but from a user perspective. What kind of users are more likely to be classified as at risk? What are their characteristics?
4. Let's say you now have this model which can be used to predict in real time if an activity is fraudulent or not. From a product perspective, how would you use it? That is, what kind of differnet user experiences would you build based on the model output? i.e. based on your prediction, are you going to approve/decline this transaction?


# Summary of findings
- Data is highly imbalanced
- I trained a random forest model, and after parameter tuning, it reached an F1 score 0.687. Since data is high imbalanced, I tried SMOTE technique but it did not improve f1 score. instead, it increases false positives a lot. 
- Characteristics of fraud: half of fraudulent purchase trasactions occur 1 second after account sign up. The more device_id/ip_address that is shared, the higher rate of fraud. 

- Made actionable operation recommendations/proposal for business: in real-time prediction, if a transaction has a predcited probability of fraud lower than 0.3, then we can safely pass. If prob between 0.4-0.7, we need manual investigation. If above 0.8, decline this transaction. 
