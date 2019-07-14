# Kaggle_Santander

This is a machine learning practice project with Kaggle's Santander Customer Satisfaction Dataset. The link to the competition is https://www.kaggle.com/c/santander-customer-satisfaction

### Goal: 
Indentify dissatisfied customers by hundreds of anonymized features; Predict if a customer is satisfied or dissatisfied with their banking experience.

### Dataset: 
76020 observations and 371 features, including the target.

### Observations: 

1. Sparsity: In this dataset, most of the entries (96%) are zeros, and more than 90% of customers has more than 350/370 features as zeros. 

2. Highly-skewed dataset: The target is binary, and only 4.5% of customers are labeled as unsatisfied. 

### Feature engineering and data cleaning:

1. As the dataset is highly sparse, the duplicated features, including zero columns, are deleted, such that the number of features is reduced by 20%. 

2. During the feature engineering, we found the numbers are records of various assets/financial products owned by customers and therefore we engineered a new feature which counts the total quantitity/value of the assets. 
  
3. TruncatedSVD is more appropriate than PCA since the data is sparse, and t-SVD does not require feature centralization as opposed to PCA, which destroies the sparsity.

### Model training:

In this project, tree models are chosen as the most appropriate model, and XGBoost classifier was implemented as the main base estimator. The main reason is that it takes special care for sparsity-aware split finding, as shown in [1]. Other models are still worthwhile to be trained. For instance, random forest classifier, SVM classifier, logistic classifier or neural network. However, special care need to be taken for downsampling with the skewed data and overfitting. 
  
  
[1] Chen, Tianqi, and Carlos Guestrin. "Xgboost: A scalable tree boosting system." Proceedings of the 22nd acm sigkdd international conference on knowledge discovery and data mining. ACM, 2016.  



  


  
