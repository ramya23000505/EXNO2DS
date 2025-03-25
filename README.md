# EXNO2DS-Exploratory Data Analysis
## AIM:
  To perform Exploratory Data Analysis on the given data set.
      
## EXPLANATION:
 The primary aim with exploratory analysis is to examine the data for distribution, outliers and anomalies to direct specific testing of your hypothesis.
  
## ALGORITHM:
STEP 1: Import the required packages to perform Data Cleansing,Removing Outliers and Exploratory Data Analysis.

STEP 2: Replace the null value using any one of the method from mode,median and mean based on the dataset available.

STEP 3: Use boxplot method to analyze the outliers of the given dataset.

STEP 4: Remove the outliers using Inter Quantile Range method.

STEP 5: Use Countplot method to analyze in a graphical method for categorical data.

STEP 6: Use displot method to represent the univariate distribution of data.

STEP 7: Use cross tabulation method to quantitatively analyze the relationship between multiple variables.

STEP 8: Use heatmap method of representation to show relationships between two variables, one plotted on each axis.

## CODING AND OUTPUT
### Developed by: RAMYA R
### Register no: 212223230169
```py
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns  
df=pd.read_csv("titanic_dataset.csv")
df
```
![image](https://github.com/user-attachments/assets/5f48e7a7-3c7d-4292-a068-61ec4b05b379)


```py
df.info()
```
![image](https://github.com/user-attachments/assets/d8793510-cb63-4c4d-861d-2422abd93837)
)

```py
df.shape
```
![image](https://github.com/user-attachments/assets/22f564c2-e7c1-476d-9c8b-e9659515e2ed)


```py
df.set_index("PassengerId",inplace=True)
df.describe()
```
![image](https://github.com/user-attachments/assets/fda6af28-192b-4d1d-ae9d-6850f7003641)


```py
df.shape
```
![image](https://github.com/user-attachments/assets/418d2d0f-2ee7-41d6-9a68-e4a38e781f3e)


### Categorical data analysis
```py
df.nunique()
```
![image](https://github.com/user-attachments/assets/2a946ed4-c7ef-49f2-bf36-452db3398a89)


```py
df["Survived"].value_counts()
```
![image](https://github.com/user-attachments/assets/830796f2-a95c-4d70-8e8a-07f3770c46dc)


```py
per=(df["Survived"].value_counts()/df.shape[0]*100).round(2)
per
```
![image](https://github.com/user-attachments/assets/575e9251-bba6-485d-a336-8d47aeb932f4)


```py
sns.countplot(data=df,x="Survived")
```
![image](https://github.com/user-attachments/assets/3976b641-f048-49ef-a648-6f82e835d12c)


```py
df
```
![image](https://github.com/user-attachments/assets/78840a81-a9cb-43f9-9792-fb6dcdcce2f4)


```py
df.Pclass.unique()
```
![image](https://github.com/user-attachments/assets/fe954b35-c123-41c1-b5b5-ab62eb37856b)


```py
df.rename(columns={'Sex':'Gender'},inplace=True)
df
```
![image](https://github.com/user-attachments/assets/7e1da582-da7b-46e4-b543-57bfa95db7fa)


### Bivariate Analysis
```py
sns.catplot(x="Gender",col="Survived",kind="count",data=df,height=5,aspect=.7)
```
![image](https://github.com/user-attachments/assets/005fbe8b-2589-4425-9c61-f1c80ac6a226)


```py
sns.catplot(x="Survived",hue="Gender",data=df,kind="count")
```
![image](https://github.com/user-attachments/assets/ffc12016-e944-45b6-9e03-a5b923320b38)


```py
df.boxplot(column="Age",by="Survived")
```
![image](https://github.com/user-attachments/assets/2e67538c-9531-443a-bcdc-1e5daa12723d)


```py
sns.scatterplot(x=df["Age"],y=df["Fare"])
```
![image](https://github.com/user-attachments/assets/302e4780-4bde-4493-92cd-5f86395971ce)


```py
sns.jointplot(x="Age",y="Fare",data=df)
```
![image](https://github.com/user-attachments/assets/6788938d-1988-402d-9ea6-1eff77ca327c)


### Multivariate Analysis
```py
fig, ax1 = plt.subplots(figsize=(8,5))
plt = sns.boxplot(ax=ax1,x='Pclass',y='Age',hue='Gender',data=df)
```
![image](https://github.com/user-attachments/assets/d67fbdad-0f12-46ba-b502-2c2585a5580a)


```py
sns.catplot(data=df,col="Survived",x="Gender",hue="Pclass",kind="count")
```
![image](https://github.com/user-attachments/assets/d84076f0-ff22-4927-b657-89ed477bb0e8)


# Co-relation
```py
corr=df.corr()
sns.heatmap(corr,annot=True)
```
![image](https://github.com/user-attachments/assets/192135a7-520e-4e1f-b80f-1ec7bfd6d8c6)


```py
sns.pairplot(df)
```
![image](https://github.com/user-attachments/assets/30b82f06-b0c7-422d-bc31-f795fd0e8c8c)


## RESULT
We have performed Exploratory Data Analysis on the given data set successfully.
