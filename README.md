# Exno:1
Data Cleaning Process

# AIM
To read the given data and perform data cleaning and save the cleaned data to a file.

# Explanation
Data cleaning is the process of preparing data for analysis by removing or modifying data that is incorrect ,incompleted , irrelevant , duplicated or improperly formatted. Data cleaning is not simply about erasing data ,but rather finding a way to maximize datasets accuracy without necessarily deleting the information.

# Algorithm
STEP 1: Read the given Data

STEP 2: Get the information about the data

STEP 3: Remove the null values from the data

STEP 4: Save the Clean data to the file

STEP 5: Remove outliers using IQR

STEP 6: Use zscore of to remove outliers

# Coding and Output
import pandas as pd

data=pd.read_csv(r"C:\Users\MIRDULA\Downloads\Data_set (1).csv")

print(data)

image
df.describe()

image
df=pd.DataFrame(data)

print(df.isnull())

image
df=pd.DataFrame(data)

print(df.isnull().sum())

image
df.info()

image
import pandas as pd

data=pd.read_csv(r"C:\Users\MIRDULA\Downloads\Data_set (1).csv")

df=pd.DataFrame(data)

dfd=df.dropna()

print("AFTER DROPNA")

print(dfd)

image
dfd=df.dropna(axis=1)

print("AFTER DROPNA")

print(dfd)

image
dfd=df.dropna(axis=1,inplace=True)

print("AFTER DROPNA")

print(dfd)

image
df=pd.DataFrame(data)

df1=df.iloc[[1,3,5],[1,3]]

print(df1)

image
dfd=df.dropna(axis=0)

print("AFTER DROPNA")

print(dfd)

image
df=pd.DataFrame(data)

print(df.isnull().any())

image
dfd=df.fillna(0)

print("AFTER FILLNA")

print(dfd)

image
dfd=df.fillna(method="ffill")

print("AFTER FILLNA")

print(dfd)

image
dfd=df.fillna(method="bfill")

print("AFTER FILLNA")

print(dfd)

image
dfd=df.fillna({'show_name':'nandy','aired_on':'wednesday','original_network':'Jio','rating':7.5})

print("AFTER FILLNA")

print(dfd)

image
import pandas as pd

import matplotlib.pyplot as plt

import numpy as np

data=pd.read_csv("iris.csv")

df=pd.DataFrame(data)

print(df)

x=df["petal_length"]

y=df["sepal_length"]

plt.bar(x,y)

plt.show()

image
import pandas as pd

import matplotlib.pyplot as plt

import numpy as np

data=pd.read_csv("iris.csv")

df=pd.DataFrame(data)

print(df)

x=df["petal_length"]

y=df["sepal_length"]

plt.xlabel('X-axis')

plt.ylabel('Y-axis')

plt.plot(x,y)

plt.show()

image
plt.scatter(x,y)

plt.show()

image
import pandas as pd

import matplotlib.pyplot as plt

import numpy as np

data=pd.read_csv("iris.csv")

df=pd.DataFrame(data)

print(df)

dff=plt.boxplot(x="petal_width",data=df)

print(dff)

image
import pandas as pd

import numpy as np

from scipy import stats

data=pd.read_csv("iris.csv")

df=pd.DataFrame(data)

z_scores = np.abs(stats.zscore(df.select_dtypes(include=[np.number])))

df_cleaned = df[(z_scores < 3).all(axis=1)]

df_cleaned

image
import pandas as pd

import numpy as np

data_set = pd.read_csv("iris.csv")

df = pd.DataFrame(data_set)

Q1 = df["sepal_width"].quantile(0.25)

Q3 = df["sepal_width"].quantile(0.75)

IQR = Q3 - Q1

lower_bound = Q1 - 1.5 * IQR

upper_bound = Q3 + 1.5 * IQR

print("The Orginal DataSet")

print(df)

outliers = df[(df['sepal_width'] < lower_bound) | (df['sepal_width'] > upper_bound)]

print("The Outliers")

print(outliers)

df_clean = df[(df['sepal_width'] >= lower_bound) & (df['sepal_width'] <= upper_bound)]

print("The Dataset after removing the outliers")

print(df_clean)

image
Result
THUS DATA CLEANING IS PERFORMED


Result
THUS DATA CLEANING IS PERFORMED
