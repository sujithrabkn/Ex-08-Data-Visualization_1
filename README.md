# Ex-09-Data-Visualization-

## AIM
To Perform Data Visualization on a complex dataset and save the data to a file. 

# Explanation
Data visualization is the graphical representation of information and data. By using visual elements like charts, graphs, and maps, data visualization tools provide an accessible way to see and understand trends, outliers, and patterns in data.

# ALGORITHM
### STEP 1
Read the given Data
### STEP 2
Clean the Data Set using Data Cleaning Process
### STEP 3
Apply Feature generation and selection techniques to all the features of the data set
### STEP 4
Apply data visualization techniques to identify the patterns of the data.

# CODE
```
Data Preprocessing

import seaborn as sns
import pandas as pd
import matplotlib.pyplot as plt
df = sns.load_dataset("tips")
print(df)

df.isnull().sum()

Handling Outliers
plt.figure(figsize=(8,8))
plt.title("Data with Outliers")
df.boxplot()
plt.show()

Removing Outliers
plt.figure(figsize=(8,8))
cols = ['size','tip','total_bill']
Q1 = df[cols].quantile(0.25)
Q3 = df[cols].quantile(0.75)
IQR = Q3 - Q1
df = df[~((df[cols] < (Q1 - 1.5 * IQR)) |(df[cols] > (Q3 + 1.5 * IQR))).any(axis=1)]
plt.title("Dataset after removing outliers")
df.boxplot()
plt.show()

1) Which day of the week has the highest total bill amount?
sns.barplot(x=df['day'], y=df['total_bill'], hue=df['day'])
plt.legend(loc="center")
plt.title("Highest Total Bill Amount by day of the week")
plt.show()

2) What is the average tip amount given by smokers and non-smokers?
sns.boxplot(x=df['smoker'], y=df['tip'], hue=df['smoker'])
plt.title("Average Tip Amount given by smokers and non-smokers")

3) How does the tip percentage vary based on the size of the dining party?
df["tip_percent"] = df["tip"] / df["total_bill"]
sns.scatterplot(x=df['size'],y=df['tip_percent'],data=df)
plt.title("Tip Percentage by Dining Party Size")

4) Which gender tends to leave higher tips?
sns.boxplot(x=df['sex'], y=df['tip'],hue=df['sex'])
plt.title("Tips based on gender")

5) Is there any relationship between the total bill amount and the day of the week?
sns.scatterplot(x=df['day'],y=df['total_bill'],hue=df['day'])
plt.legend(loc="best")
plt.title("Total bill amount by day of the week")

6) How does the distribution of total bill amounts vary across different time periods (lunch vs. dinner)?
sns.histplot(data=df, x="total_bill", hue="time", element="step", stat="density")
plt.title("Distribution of Total Bill Amounts by Time of Day")
plt.show()

7) Which dining party size group tends to have the highest average total bill amount?
sns.barplot(x=df['size'],y=df['total_bill'],hue=df['size'])
plt.title("Average Total Bill Amount by Dining Party Size")
plt.show()

8) What is the distribution of tip amounts for each day of the week?
sns.boxplot(x="day", y="tip", data=df)
plt.title("Tip Amount by Day of Week")
plt.show()

9) How does the tip amount vary based on the type of service (lunch vs. dinner)?
sns.violinplot(x="time", y="tip", data=df)
plt.title("Tip Amount by Time of Day")
plt.show()

10) Is there any correlation between the total bill amount and the tip amount?
sns.scatterplot(x="total_bill", y="tip", data=df)
plt.title("Correlation between Tip Amount and Total Bill Amount")
plt.show()
```

# OUPUT
![Screenshot 2023-05-27 231327](https://github.com/sujithrabkn/Ex-08-Data-Visualization_1/assets/119477857/27df6d24-1af0-4c62-a385-dde9dd0b155e)

![Screenshot 2023-05-27 231343](https://github.com/sujithrabkn/Ex-08-Data-Visualization_1/assets/119477857/ac83b166-2e08-46a8-b894-58fdd4006255)

![Screenshot 2023-05-27 231403](https://github.com/sujithrabkn/Ex-08-Data-Visualization_1/assets/119477857/c6705f11-1cf5-490c-9115-311e700f2846)

![Screenshot 2023-05-27 231424](https://github.com/sujithrabkn/Ex-08-Data-Visualization_1/assets/119477857/5ccdb206-10dc-4a85-9645-f6bdd1f555ff)

![Screenshot 2023-05-27 231441](https://github.com/sujithrabkn/Ex-08-Data-Visualization_1/assets/119477857/ab33a4e0-c210-48a3-8901-ba1fc5336a9f)

![Screenshot 2023-05-27 231451](https://github.com/sujithrabkn/Ex-08-Data-Visualization_1/assets/119477857/c42591f5-f57c-4869-9b2a-3fd76211445f)

![Screenshot 2023-05-27 231459](https://github.com/sujithrabkn/Ex-08-Data-Visualization_1/assets/119477857/4fe2c0dd-c79c-431d-84dc-cc025e317790)

![Screenshot 2023-05-27 231507](https://github.com/sujithrabkn/Ex-08-Data-Visualization_1/assets/119477857/4b70fb78-384e-4d68-b091-80d68369a8d3)

![Screenshot 2023-05-27 231516](https://github.com/sujithrabkn/Ex-08-Data-Visualization_1/assets/119477857/1c186455-a424-4299-8718-8a812932611d)

![Screenshot 2023-05-27 231525](https://github.com/sujithrabkn/Ex-08-Data-Visualization_1/assets/119477857/97d1d1d2-bb86-4069-a7cd-0172266cfd1b)

![Screenshot 2023-05-27 231534](https://github.com/sujithrabkn/Ex-08-Data-Visualization_1/assets/119477857/eb291a5b-93d2-4704-a9db-46e585201041)

![Screenshot 2023-05-27 231544](https://github.com/sujithrabkn/Ex-08-Data-Visualization_1/assets/119477857/ba3029e9-035b-419a-80ab-817c7582f6ed)

![Screenshot 2023-05-27 231553](https://github.com/sujithrabkn/Ex-08-Data-Visualization_1/assets/119477857/d7753670-8fdc-4947-bd8c-6ba4419a2890)

![Screenshot 2023-05-27 231602](https://github.com/sujithrabkn/Ex-08-Data-Visualization_1/assets/119477857/c966462f-801b-487d-87ee-5eb282f1a1d1)

# RESULT

Thus the Data Visualization method is performed to the given data and to predict the outcome for the given questions.
