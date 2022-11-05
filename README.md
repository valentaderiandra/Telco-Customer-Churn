# Telco-Customer-Churn
Telco Company is a company engaged in the information technology services, communications and telecommunications networks.

[![forthebadge made-with-python](http://ForTheBadge.com/images/badges/made-with-python.svg)](https://www.python.org/)

[![Made withJupyter](https://img.shields.io/badge/Made%20with-Jupyter-orange?style=for-the-badge&logo=Jupyter)](https://jupyter.org/try)

[![Ask Me Anything !](https://img.shields.io/badge/Ask%20me-anything-1abc9c.svg)](https://GitHub.com/Naereen/ama)


# Use Case
* *Use Case Summary*


* *Objective Statement* :

    * Get business insight about how many customer who churn or not churn
    * Get business insight about how many female and male in churn or not churn customer
    * Get business insight about how many customer who has a partner, has dependent or not, and old age or not
    * Get business insight about how many customer used additional service like : PhoneService, MultipleLines, InternetService, OnlineSecurity, OnlineBackup, DeviceProtection, TechSupport, StreamingTV, StreamingMovies, and Papperless Billing
    * Get business insight about how long customer used service who has churn(Contract)
    * Get business insight about how payment method from customer
    * Get insight about 5 feature or facility that influenced customer to churn most. That is, tenure, monthly charge, contract, gender male, fiber optic
    * Build models using machine learning to predict customer churn
    
    
* *Challanges* :
    * Large size of data, can not maintain by excel spreadsheet
    * Fill in the missing value in the dataset
    * Change the data type of column which doesn't match
    * Hard to know the meaning of each column



* *Methodology / Analytic Technique* :
    * Descriptive analysis
        * Describe the information such as, min/max value of each column, average, and the total count of data contained in each column. We also describe the distribution of the numerical data.
    * Graph analysis
        * Elaborate the relation of each plot/graphic including the data percentage and assumption/hypothesis of its implication.
    * Using Machine Learning Classification
        * Logistic regression


* *Business Benefit*:

    * Gain insight to keep customers from churn through modification of benefits/features provided to these customers
    * Gain insight to improve the quality of company services so that customers remain loyal and gain more profit for the company
    * Build models using machine learning to predict customer churn


* *Expected Outcome*:

    * Know how many customer who churn or not churn
    * Know how many female and male in churn or not churn customer
    * Know how many customer who has a partner, has dependent or not, and old age or not
    * Know how many customer used additional service like : PhoneService, MultipleLines, InternetService, OnlineSecurity, OnlineBackup, DeviceProtection, TechSupport, StreamingTV, StreamingMovies, and Papperless Billing
    * Know how long customer used service who has churn(Contract)
    * Know about how payment method from customer
    * Know about 4 feature variable that influenced customer to churn most.
    * Know how to build models using machine learning to predict customer churn
    
# Business Understanding
* Data telco is a company engaged in telecommunication and internet services. 
- This case has some business question using the data:
    * How many customer who churn or not churn?
    * How many female and male in churn or not churn customer?
    * How how many customer who has a partner, has dependent or not, and old age or not?
    * How how many customer used additional service like : PhoneService, MultipleLines, InternetService, OnlineSecurity, OnlineBackup, DeviceProtection, TechSupport, StreamingTV, StreamingMovies, and Papperless Billing
    * How how long customer used service who has churn ? (Contract)
    * How about how payment method from customer?
    * How about 4 feature or facility that influenced customer to churn most. That is, tenure, monthly charge, contract, gender male, fiber optic?
    * How how to build models using machine learning to predict customer churn?
# Data Understanding


* *Source Data*:
    * The dataset used is data from https://www.kaggle.com/datasets/yeanzc/telco-customer-churn-ibm-dataset
    * The raw data contains 7043 rows (customers) and 21 columns (features).

* *Data Dictionary* :
    * customerID : Customer ID
    * gender : Whether the customer is a male or a female (Male, Female)
    * SeniorCitizen : Whether the customer is a senior citizen or not (1, 0)
    * Partner : Whether the customer has a partner or not (Yes, No)
    * Dependents : Whether the customer has dependents or not (Yes, No)
    * Tenure : Number of months the customer has stayed with the company
    * PhoneService : Whether the customer has a phone service or not (Yes, No)
    * MultipleLines : Whether the customer has multiple lines or not (Yes, No, No phone service)
    * InternetService : Customer’s internet service provider (DSL, Fiber optic, No)
    * OnlineSecurity : Whether the customer has online security or not (Yes, No, No internet service)
    * OnlineBackup : Whether the customer has online backup or not (Yes, No, No internet service)
    * DeviceProtection : Whether the customer has device protection or not (Yes, No, No internet service)
    * TechSupport : Whether the customer has tech support or not (Yes, No, No internet service)
    * StreamingTV : Whether the customer has streaming TV or not (Yes, No, No internet service)
    * Contract : Indicates the customer’s current contract type: (Month-to-Month, One Year, Two Year)
    * Paperless Billing: Indicates if the customer has chosen paperless billing: (Yes, No)
    * Payment Method: Indicates how the customer pays their bill: (Bank Withdrawal, Credit Card, Mailed Check)
    * Monthly Charge: Indicates the customer’s current total monthly charge for all their services from the company.
    * Total Charges: Indicates the customer’s total charges, calculated to the end of the quarter specified above.
    * Churn Label: 
        * Yes = the customer left the company
        * No = the customer remained with the company

# Data Preparation

* *Code use*:
    * Python 3.9.7
    * Package: Pandas, Numpy, Matplotlib, Seaborn, Sklearn, Warning and Feature Engine


# Data Cleansing
  * There are 1009 missing value data in the column gender, SeniorCitizen, Partner, Dependents, MultipleLines, InternetService, OnlineSecurity, OnlineBackup, DeviceProtection, TechSupport, StreamingTV, and StreamingMovies
  * Change the Total Charge column data type to float
  * Column monthlyCharge, TotalCharge and tenure multicollinearity, so one column must be deleted, here we delete the TotalCharge column

# Exploratory Data Analysis
  * How many customer who churn or not churn?
  
  ![1 churn vs non churn](https://user-images.githubusercontent.com/101789879/200106887-a93f13a8-b8c7-4437-8046-f3721692120d.jpg)
  
  The bar chart above shows the number of customers who did not leave/stop telco services (No churn) more than customers who left/stopped telco services (Yes churn).     Likewise, in the pie chart above, it can be seen that customers who do not Churn are 73.46% and customers who Churn are 26.54%.
  
  * How many female and male in churn or not churn customer?
  
  ![2 churn vs gender](https://user-images.githubusercontent.com/101789879/200106956-78acc42e-e495-4dca-9c69-744c68619427.jpg)
  
  Of the total 5174, those who did not churn were female as much as 42%, male as much as 43%, unknown 14%

  Of the total 1869, the churn were 43% female, 42% male, Unknown 13%
  
  * How many customer has partners?
  
  ![3 churn vs partner](https://user-images.githubusercontent.com/101789879/200107029-c18b1bee-c2e0-4a22-bb3c-22952c492665.jpg)
  
  5174 customer who not churn, customer who no partner 40%, have a partner 45% and unknown 14%
  1869 customer who churn, no partner 55%, have a partner 30%, unknown 13%

  Why does not Churn have more partners, here we suspect that the customer is married and has a family so that the economy is quite stable.

  In the churn section, we think that we are still young people who are still in the stage of managing their finances and still leaving the house more often, so they prefer to use cellular internet services.

  * How many customer has dependent?
  
  ![4 churn vs dependent](https://user-images.githubusercontent.com/101789879/200107091-394d4364-ad14-4010-9530-1983da6aa683.jpg)
  
  5174 customers not churn, customers has no dependents 56%, have dependents 29%,unknown 14%

  1869 customer churn, customer has no dependents 70%, have a dependent 15%, unknown 13%

  Whether churn or not, have no dependents. because maybe many customers are not from the rich who have a lot of insurance
  
  * How many customers was old?
  
  ![5 churn vs seniorcitizen](https://user-images.githubusercontent.com/101789879/200107135-80884a05-f8cf-4455-8be0-e3d73cf6dd00.jpg)
  
  From a total of 5174 not churn, customers who not old age 74%, elderly 10%, and unknown 14%

  From a total of 1869 churn, not old age 64%, elderly 21%, and Unknown 13%

  From the data, both Churn and not, the elderly users are few. because also at this age we think many are 'technical' and can't keep up with the times, so if we give a discount for the elderly it will be in vain

  * How many customers churn and don't churn from  Phone Service
  
  ![6 churn vs phoneservice](https://user-images.githubusercontent.com/101789879/200107199-a43dd4c3-be6c-482e-8654-30e646c54134.jpg)
  
  Of the total 1869, those who churn telco service and churn of Phone Service as 91 %,churn telco service and not churn of Phone Service as much as 9 %

  Of the total 5174, those who did not churn telco service and churn of Phone Service as 90%, did not churn telco service and not churn of Phone Service as much as 10%

  In our opinion, the Phone Service service is quite good, as evidenced by approximately 90% of customers who have Churn No or yes. In the future, in our opinion, it is better for customers who have churn yes and phone service yes so that discounts are given so that they can subscribe again (Churn == No)

  * How many customers churn and don't churn from  Multiple Lines
  
  ![7 churn vs multiple lines](https://user-images.githubusercontent.com/101789879/200107237-e0325fa6-e137-4f0e-b1e0-1739c7ea0ca4.jpg)
  
  From Column Churn vs Multiple Lines

  Churn no = from a total of 5174, subscribe to Multiple Lines 35% | not subscribed to Multiple Lines 42% | do not have phone service by 9% | customers whose data is unknown 14%

  Churn yes = from a total of 1869, subscribed to Multiple Lines 39% | not subscribed to Multiple Lines 39% | do not have phone service by 8% | customers whose data is unknown 14%

  In our opinion, multiple lines services are less affordable to customers because this is indicated by the multiple lines data for churn no (still subscribed) with a comparison of those who are still subscribed and unsubscribed +-8 : +-10. The comparison of churn yes (leaving the service) for multiple lines service with a ratio of those who are still subscribed and unsubscribed 1:1. So we can assume, the service is good (not bad) but in my opinion the service is expensive (only for certain circles)
  
  * How many customers churn and don't churn from  Internet service
  
  ![8 churn vs internet service](https://user-images.githubusercontent.com/101789879/200107352-c54ef039-c8be-4b6f-9d82-4bfc1a91e44d.jpg)

  From Column Churn vs Internet Service

  Churn no = out of a total of 5174, 33% DSL subscription | Fiber Optic subscription 29 % | do not subscribe to internet service by 24% | Unknown data 14%

  Churn yes = out of 1869 total, 22% DSL subscription | 59% Fiber Optic subscription | don't subscribe to internet service by 5% | Unknown data 14%

  In our opinion, DSL service is a superior service, as seen from the data churn No with the largest percentage, namely DSL at 33%.
  In our opinion, Fiber Optic service is a service that is not good, this can be seen from the churn value of yes (leaving our service) of 59%. So, every customer who leaves our service (Churn == Yes) has used Fiber Optic and Fiber Optic is worth the biggest

  * *How many customers churn and don't churn from Online Backup*
  
  ![9 churn vs online backup](https://user-images.githubusercontent.com/101789879/200107442-322fa267-d92d-43e0-9074-8b43951e1c8d.jpg)
  
  Of the 5174 customers whose Churn is No, as many as 30.45% of customers do not subscribe to Online Backup. Maybe they don't know about the Online Backup feature. as many as 23.6% do not have an internet connection. As many as 31.4% subscribed and 14.4% unknown status.

  Of the 1869 customers whose Churn is Yes, as many as 57% of customers do not subscribe to Online Backup. Maybe they don't know the Online Backup feature. as much as 5.2% do not have an internet connection. A total of 23.7% subscribed and 13.4% unknown status.

  Based on the data, more users use Online Backup for customers whose churn is Yes, maybe customers whose churn is Yes, most likely he has never tried the online backup feature. Because as many as 57% of 1869 customers of those whose Churn is Yes have not subscribed to Online Backup
  
  * How many customers churn and don't churn from Device Protection
  
  ![10 churn vs device protection](https://user-images.githubusercontent.com/101789879/200107491-b0d19aff-7eee-4aec-8d9a-4dd2f25a5850.jpg)
  
  From Column Churn vs Device Protection

  Churn no = from a total of 5174, subscribe to Device Protection 31% | not subscribed to Device Protection 31% | do not have internet service 24% | customers whose data is unknown 14%

  Churn yes = from a total of 1869, subscribed to Device Protection 25% | not subscribed to Device Protection 56% | do not have internet service 5% | customers whose data is unknown 14%

  In our opinion, device protection services are less attractive to customers. This is indicated by data on customers who churn and have never used device protection services as many as 1043 of 1869 customers (56%). customers who use and do not use device protection are 1:1. So, we assume that maybe the Device Protection service is less attractive to customers. In the future, this service can continue to be educated to customers so that customers know the advantages of this service.

  * How many customer churn compared with their subscription in additional Tech Support?
  
  ![11 churn vs Techsupport](https://user-images.githubusercontent.com/101789879/200107533-d893efbb-c805-4571-859a-892996766d7b.jpg)
  
  66% of Churn customers did'nt subscribe Tech Support.
  
  Of the 1869 customers whose Churn is Yes.
  Probably those customers found several technical issues and was not able to resolve by them self. 
  Therefore, the marketing could rebranding their strategy for tech support plan to the customer
  
  * How many customer churn compared with their usage of internet service for streaming tv programs?
  
  ![12 churn vs StreamingTv](https://user-images.githubusercontent.com/101789879/200107627-2fb4300f-bc13-4dd2-b5e9-df304aa321d8.jpg)
  
  43% of Churn customers did'nt use their internet service to stream tv program.
  
  * How many customer churn compared with their usage of internet service for streaming movies?
  
  ![13 churn vs StreamingMovies](https://user-images.githubusercontent.com/101789879/200107678-d81dbb63-d39e-4420-8213-40850e023739.jpg)

  43.4% of Churn customer  did'nt use their internet service to stream movies.
  
  * How many customer churn compared with use paperless billing and not use paperless billing? 
  
  ![14 churn vs Paperless Billing](https://user-images.githubusercontent.com/101789879/200107869-5b7402ba-a0be-4525-b83c-b99422e562bc.jpg)
  
  74.9% of Churn customers did'nt Chose paperless billing.
  
  * How long customer churn used service who has churn
  
  ![15 churn vs Contract](https://user-images.githubusercontent.com/101789879/200107963-584cdd6a-21d9-4e2d-8d76-bf90bb646ee5.jpg)
  
  From a total of 1869 customer whose chure, month to month 88%, one year 8%, two years 2%

  The barchart above shows the Churn amount by Contract category. Judging from the barchart, the number of churn customers is dominated by customers with month-to-month contracts. We think the customer is Churn because he just wants to try it, if the service is bad, the customer doesn't have to worry about extending it because it also costs less, not as much as one year and two years.

  Suggestions, improve service to new customers
  
  * Feature or variable that influenced customer to churn most
  
  The barchart height on feature importance shows the score or how much the feature has an effect on Churn. The higher the score, the more significant it is. Based on the results besides, the 5 features that affect someone Churn or not are:
    * Tenure
    * Monthly Charges
    * Contract
    * Gender
    * Fiber Optic
# Logistic Regression Modeling Results

  * Evaluate Model
  
  ![1 Logistic Regression Modeling Results](https://user-images.githubusercontent.com/101789879/200108175-1e06fdd0-ec7c-4a80-94b8-9470f5cf2e0b.jpg)
  
    * From the confusion matrix on the side, value:
    * True Positive of 943 (meaning as many as 943 people who did not Churn, correctly predicted No Churn)
    * True Negative of 218 (meaning as many as 218 people who Churn, correctly predicted Churn)
    * False Positive of 155 (meaning as many as 155 people who Churn, incorrectly predicted No Churn)
    * False Negative of 93 (meaning as many as 93 people who did not Churn, wrongly predicted Churn)

  * Accuracy, Precision, Recall
  
  ![2 Accuracy, Precision, Recall](https://user-images.githubusercontent.com/101789879/200108246-8fbde414-6d19-4d4b-a4d0-98a02bff2bcb.jpg)
  
  Accuracy = 0,82

  The correct customer predicted No Churn and Churn from the overall customer by 82%

  Precision = 0,86

  The correct customers did not Churn out of the total predicted customers No Churn by 86%

  Recall = 0,91

  Predicted customers No Churn compared to total customers who actually No Churn by 91%

  * Is Model Overfit or Underfit?
  
  ![3 underfit or overfit](https://user-images.githubusercontent.com/101789879/200108420-f15c7b26-b65f-4ead-b4d5-39492a97b55f.jpg)

  In the results of the logistic regression model from telco data, the accuracy of testing data with training data is not too far away. This shows that there is no overfitting or underfitting of the model.
  
  * ROC AUC
  
  ![4 roc auc](https://user-images.githubusercontent.com/101789879/200108461-4cf482d6-79fe-4711-87cc-f6394b3e9d18.jpg)
  
  ![5 plot roc auc](https://user-images.githubusercontent.com/101789879/200108502-e9635fd0-701f-4046-8a4e-eb66273d6e65.jpg)

  The AUC value of the training data is 83.86% and the AUC value of the testing data is 86.06%.

# Regression Logistic Model With Cross Validation and Hyperparameter Tuning Results

  * Evaluate Model
  
  ![6 Regression Logistic ModelWith Cross Validation and Hyperparameter Tuning Results](https://user-images.githubusercontent.com/101789879/200108709-555b457e-526d-442b-a49f-7cd1dec89efc.jpg)
  
  From the confusion matrix on the side, value:
  
  * True Positive of 941 (meaning as many as 941 people who did not Churn, correctly predicted No Churn)
  * True Negative of 220 (meaning as many as 220 people who Churn, correctly predicted Churn)
  * False Positive of 153 (meaning as many as 153 people who Churn, incorrectly predicted No Churn)
  * False Negative of 95 (meaning as many as 95 people who did not Churn, wrongly predicted Churn)

  
  * *Accuracy, Precision, Recall*
  
  ![7 Accuracy, Precision, Recall](https://user-images.githubusercontent.com/101789879/200109144-7dfbfa21-5056-46f7-9624-80faf2cfbc86.jpg)
  
  * Accuracy = 0,82
  
  The correct customer predicted No Churn and Churn from the overall customer by 82%
  * Precission = 0,86
  
  The correct customers did not Churn out of the total predicted customers No Churn by 86%
  
  * Recall = 0,91
  
  Predicted customers No Churn compared to total customers who actually No Churn by 91%

  * Is Model Overfit or Underfit?
  ![8 underfit or overfit](https://user-images.githubusercontent.com/101789879/200109268-670b54f7-5ac6-47dc-94a4-12c9142f418f.jpg)
  
  In the results of the logistic regression model from telco data, the accuracy of testing data with training data is not too far away. This shows that there is no overfitting or underfitting of the model.
  
# Oversampling SMOTE for Logistic Regression Model Result

  * Evaluate Model 
  
  ![9 Regression Logistic Model With Cross Validation and Hyperparameter Tuning Results](https://user-images.githubusercontent.com/101789879/200109350-6f063029-969b-4063-a0b2-9aa2e4bd811e.jpg)

  From the confusion matrix on the side, value:
  * True Positive of 941 (meaning as many as 941 people who did not Churn, correctly predicted No Churn)
  * True Negative of 220 (meaning as many as 220 people who Churn, correctly predicted Churn)
  * False Positive of 153 (meaning as many as 153 people who Churn, incorrectly predicted No Churn)
  * False Negative of 95 (meaning as many as 95 people who did not Churn, wrongly predicted Churn)
  
  * Accuracy, Precision, Recall
  
  ![10 Accuracy, Precision, Recall](https://user-images.githubusercontent.com/101789879/200109471-4b10ba5f-8bef-4dbe-b74b-9c321260005a.jpg)
  
  Accuracy = 0,75

The correct customer predicted No Churn and Churn from the overall customer by 75%

Precision = 0,91

The correct customers did not Churn out of the total predicted customers No Churn by 91%

Recall = 0,74

Predicted customers No Churn compared to total customers who actually No Churn by 74%

  * Is Model Overfit or Underfit?

![11 underfit or overfit](https://user-images.githubusercontent.com/101789879/200109497-bae741c5-d06f-4867-9a23-ffe29adb15d3.jpg)

# Comparing the data accuracy of the three models (without CV and hyperparameter tuning, with CV and hyperparameter tuning, and using SMOTE oversampling)

![12 comparing](https://user-images.githubusercontent.com/101789879/200109523-2ed33d7e-16cf-4cd3-8431-070efcb11c86.jpg)

From the results of good accuracy, the model chosen is logistic regression using Cross Validation and Hyperparameter tuning.

# Result

*How many customer Churn, who has a partner, has dependent or not, and old age or not*?
* *Partners*:

Out of a total of 1869 customer churn :

customer has no partner as much as 55%, customer who has a partner 30%, unknown 13%

* *Dependent*:

Out of a total of 1869 customers churn :

customer has no dependents as much as 70%, customer have a dependent 15%, unknown 13%

* *Senior Citizens* :

Out of the total 1869 customer churn :

non-elderly customers as much as 64%, elderly customers as much as 21%, Unknown 13%

*How many Churn customers used additional service*

* *Telephone Service*:

Out of a total of 1869 customer churn :

91% of customers used Telephone Service, 9% not used Telephone Service

* *Multiple Lines*:

of a total of 1869, subscribed to Multiple Lines 39% | unsubscribed Multiple Lines 39% | do not have telephone service by 8% | customers whose data is unknown 14%

* *Internet services*:

of 1869 total, 22% DSL subscription | 59% Fiber Optic subscription | don't subscribe to internet service by 5% | unknown data 14%


* *Online Backup*

Of the 1869 customers whose Churn is Yes, as many as 57% of customers do not subscribe to Online Backup. Maybe they don't know the Online Backup feature. as much as 5.2% do not have an internet connection. A total of 23.7% subscribed and 13.4% unknown status.

* *Device Protection*

Of the 1869 customers whose Churn is Yes, as many as 55% of customers do not subscribe to Device Protection. Maybe you don't know the device protection feature. as much as 5.2% do not have an internet connection. A total of 24.9% subscribed and 13% unknown status.

* *TechSupport*

Of the 1869 customers whose Churn is Yes, as many as 66% of customers have not done Tech Support. Probably those customers found several technical issues and was not able to resolve by them self.

* *StreamingTV*

not using their internet service for streaming tv 43%, do not have internet service by 5.2%, subscribe to tech support 37.2, unknowns of 13.9%

* *StreamingMovies*

not using their internet service for streaming movies 43.4%, do not have internet service by 5.2%, subscribe to tech support 37.2%, unknowns of 13.96%

* *Papperless Billing*

of a total of 1869, billing without receipts 25%, with 74% receipt

*How long customer churn used service who has churn*

from a total of 1869 costumer who churn, use month to month 88% | one year 8% | two years 2%

*5 feature or facility that influenced customer to churn most*. 

based on feature or variable importance, we obtaine the following ordered by the most likely influencing customer to churn, that is :  
        
        1. tenure, 
        
        2. monthly charge
        
        3. contract
        
        4. gender male, and
        
        5. fiber optic

* *Machine Learning*

From the third model that has been tried/done, the best model with the highest accuracy is the With CV and Hyperparameter Tuning model with training data accuracy of 79.9%, and testing data of 82.3%

## Action / Recommendation

*Suggestions for facilities* :

* recommendations for FiberOptic,

the cost is reduced, many customers we find it difficult to continue the payment service rental fee

* recommendations for Online Security,

promote again about the importance of security when surfing the internet

* recommendations for OnlineBackup,

more promotion about OnlineBackup, because it is important if data is lost

* recommendations for Contracts,

Don't underestimate month-to-month customers. maybe the costs incurred by month-to-month customers are not as big as one year and two years, but from the demand side, month-to-month company users are the most. keep the quality so that customers stay
