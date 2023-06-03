# Implementation-of-K-Means-Clustering-for-Customer-Segmentation

## AIM:
To write a program to implement the K Means Clustering for Customer Segmentation.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
1. Import pandas as pd and matplotlib.pyplot as plt
2. Get the info and also obtain the sum of any null values
3. Importing KMeans from sklearn.cluster we group the similar datas
4. Grouping similar datas gives us a elbow shaped graph which is called the Elbow method. 5.Print the number of clusters obtained
5. Giving the clustered data differnet colors and presenting as a scatter plot
6. Print the obtained graph.

## Program:
```
/*
Program to implement the K Means Clustering for Customer Segmentation.
Developed by: YOHESH KUMAR R.M
RegisterNumber:  212222240118
*/
```
```
import pandas as pd
import matplotlib.pyplot as plt
data =pd.read_csv("/content/Mall_Customers (1).csv")
data.head()
data.info()
data.isnull().sum()
from sklearn.cluster import KMeans
wcss=[]
for i in range(1,11):
  kmeans = KMeans(n_clusters = i,init = "k-means++")
  kmeans.fit(data.iloc[:,3:])
  wcss.append(kmeans.inertia_)

plt.plot(range(1,11),wcss)
plt.xlabel("No. of Clusters")
plt.ylabel("wcss")
plt.title("Elbow Method")
km = KMeans(n_clusters = 5)
print("K-Means")
km.fit(data.iloc[:,3:])
y_pred = km.predict(data.iloc[:,3:])
print("Array:")
y_pred
data["cluster"] = y_pred
df0 = data[data["cluster"]==0]
df1 = data[data["cluster"]==1]
df2 = data[data["cluster"]==2]
df3 = data[data["cluster"]==3]
df4 = data[data["cluster"]==4]
plt.scatter(df0["Annual Income (k$)"],df0["Spending Score (1-100)"],c="red",label="cluster0")
plt.scatter(df1["Annual Income (k$)"],df1["Spending Score (1-100)"],c="yellow",label="cluster1")
plt.scatter(df2["Annual Income (k$)"],df2["Spending Score (1-100)"],c="pink",label="cluster2")
plt.scatter(df3["Annual Income (k$)"],df3["Spending Score (1-100)"],c="green",label="cluster3")
plt.scatter(df4["Annual Income (k$)"],df4["Spending Score (1-100)"],c="purple",label="cluster4")
print("Customer Segments")
print("Customer Segement")
plt.legend()
plt.title("Customer Segments")
```

## Output:
### data.head():
![dhead](https://github.com/yoheshkumar/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/119393568/e4801807-c8a8-426e-a559-b1ce94c1bbda)
### data.info():
![dinfo](https://github.com/yoheshkumar/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/119393568/a2efbccc-8ae0-458d-94d0-25e3400901a5)
### data.isnull().sum():
![in is](https://github.com/yoheshkumar/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/119393568/7ae8d25d-13b7-4455-b01c-36c721352895)
### Elbow method Graph:
![grph](https://github.com/yoheshkumar/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/119393568/bdbf07b3-a7e2-429f-8bea-fe80e3b7d15a)
### K-means Cluster:
![k clus](https://github.com/yoheshkumar/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/119393568/a20d2ee9-3a4e-47fd-9705-86e5677623c2)
### y_pred:
![ypred](https://github.com/yoheshkumar/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/119393568/3d2edf38-aa14-4e4b-ad65-87f6ceb03f64)
### Customer segments Graph:
![csg](https://github.com/yoheshkumar/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/119393568/82cff8f4-325b-4b0e-afe4-5f7353bd8a62)


## Result:
Thus the program to implement the K Means Clustering for Customer Segmentation is written and verified using python programming.
