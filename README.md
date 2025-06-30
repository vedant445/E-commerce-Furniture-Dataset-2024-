E-commerce Furniture Dataset 2024 

Objective-
The aim is to build a logistic regression model that helps us predict whether a furniture product will be a high-selling item (sold > 50 units) on the bases of its price and shipping option.
This model enables e-commerce businesses to identify high-selling products for targeted marketing, better inventory decisions, and competitive pricing strategies.

Dataset Description-
This dataset is named 'E-commerce Furniture Dataset 2024’ and it contains historical record of furniture products sold. This dataset contains 2000 entries and multiple columns such as  ‘productTitle’, ‘originalPrice’,  ‘price’, ‘sold’, 	‘tagText’.

Exploratory Data Analysis (EDA)-
 ![image](https://github.com/user-attachments/assets/b2f77dd9-856a-4bb0-9366-055bf1f3b139)
![image](https://github.com/user-attachments/assets/aab675b1-ba3a-4c86-ad2a-bbb3ad2de015)

 
Using this I remove the ‘originalPrice’ column as more than 1000 values are null and removed the missing values in ‘tagText’ column.
 ![image](https://github.com/user-attachments/assets/1b66a479-3db1-4e9e-8afa-ca8609f3a030)

After doing this I got
 ![image](https://github.com/user-attachments/assets/b9b5e279-f623-4785-b97e-9aca9faf8e9d)

This shows that there are no null values in this dataset.





Feature Engineering-
 ![image](https://github.com/user-attachments/assets/8a3cbb57-1237-4d79-ac7f-557756c45db7)

•	This creates a new column ‘Sales’ where the value in binary form such that (1 if Quantity > 50) or else 0.
•	The same goes for ‘Shipping’ where ‘Free Shipping’ is 1 and the other is 0.
 ![image](https://github.com/user-attachments/assets/ab496ec2-6ef0-4eae-a1f7-d7437ad939ca)

•	This normalizes the ‘price’ and ‘Shipping’ using Standard Scalar
 ![image](https://github.com/user-attachments/assets/1b8e4e54-af10-42e2-ad6a-85254ecef758)

•	This uses VIF analysis to remove the multi-colinear features.

Model Building-
We used Logistic Regression to classify products are high-selling or not. The dataset is split in 80-20 training and testing sets. Here classweight is balanced because it automatically adjusts for class imbalance by assigning higher weights to minor class.
 ![image](https://github.com/user-attachments/assets/92db5c6d-1b0b-47c3-ab26-417dd7f2f45c)

Model Evaluation includes:
•	Accuracy Score
•	Confusion Matrix
•	Classification Matrix


Results-
 ![image](https://github.com/user-attachments/assets/a9306dc3-9e0e-4aaf-8b1d-6c42cba8dfd9)

The Logistic Regression shows an accuracy score of approximately 73%

Confusion Matrix and Classification Reports showed:
•	Very high recall rate for ‘High Sales’ which is ‘0.95’. This model identified 21 out of 22 high-selling products.
•	Low precision for ‘High Sales’ of ‘0.16’. This tells us that the model flagged many products as high-selling which was wrong, indicating there is room for improving precision by reducing false positives.

Plot-
This plot show the classification report for both not high-selling and high-selling.
 ![image](https://github.com/user-attachments/assets/49c97db6-c87e-4ec0-afd3-0bdf1add8c51)


Summary-
The model effectively supports decision-making by ensuring high-selling products are correctly flagged, even if it occasional has some false positives. Future improvements can be made by including additional features such as product category, customer review rate, etc.

Reference-
•	Libraries - pandas, matplotlib, scikit-learn, statsmodels.
•	Tools – Visual Studio Code
