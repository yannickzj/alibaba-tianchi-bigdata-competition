# Alibaba Tianchi Big Data competition

## Introduction

This project is based on the Alibaba Tianchi Big Data competition [Customer Flow Forecasts on Koubei.com](https://tianchi.aliyun.com/competition/information.htm?spm=5176.100067.5678.2.67fd4943OMYU6P&raceId=231591&_lang=en_US). The main goal is to predict the customer flow per day during the period of 14 days (11.01.2016-11.14.2016) for 2000 shops. It is a typical regression problem with time series data.

In the competition, customer flow is defined as “number of customers making payment via Alipay in a shop during a particular period of time”. With all the payment and browsing history in the given period from 07.01.2015 to 10.31.2016, we select three popular methods, including XGBoost, Neural Network, and SVM, to predict the customer flow of the 2000 shops for the following 14 days.


## Prerequisites

Here's the software you need to run the program:

+ Python 3.6

+ Jupyter Notebook 4.4.0

+ Python packages: os, numpy, pandas, datetime, scipy, sklearn, multiprocessing, numpy, pandas, xgboost, sklearn, datetime

## How to run the program

In order to generate the solution, we first run the code in the *featureExtraction* directory to generate the preprocessed data. The order of execution for feature engineering is described as follows:

+ *timeHistoryData.ipynb*: transfer the original transaction data to time history data of custom flow;

+ *featureExtraction_*.ipynb* (including basicInfo, currentTrend, recentData, recentDataView, temporalInfo, and weather): generate feature data;

+ *featureEnsemble.ipynb*: ensemble all preprocessed features into ensemble data files for final training, validation and testing.

After generating feature data, the scripts in the models folder can be executed to select best parameters for each single model and train the ensemble model for final prediction submission. The general program execution structure is shown as follows.

<p align="center"><img src="/README/program_structure.png" width="500"></p>

## Official evaluation

By ensembling the best performing single model (XGBoost) using the bagging method, the loss value based on the official evaluation metrics in the competition can be improved to 0.0928. Our final ranking in the competition is top 10% among more than 4000 teams.

## Build and test environment

+ Build and test: 
```
ubuntu 16.04
```

## Project report
Please review the *report.pdf* for details.