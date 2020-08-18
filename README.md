# Retail-Banking-EDA
Exploratory Data Analysis Mini Projects about CRM Call Logs and Loan Portfolio

# CRM Call Logs
![alt text](https://github.com/theis19/Retail-Banking-EDA/blob/master/images/logs_info.png "Columns Info")
![alt text](https://github.com/theis19/Retail-Banking-EDA/blob/master/images/events_info.png "Columns Info")

## Joining the 2 Datasets with Left Join (Left being "Call Logs Dataset")
```python
df = cc_logs.join(events.set_index('Complaint ID'), on='Complaint ID', how='left', lsuffix='_cclogs', rsuffix='_events')
```
## Problem
Get insight and know more about the effect of Serve Time used on other features

## Product
- Most of the complaints are for **Bank account or service** with most of the Sub-product problem being **Checking account**
- Almost half of the product values data are missing
- Average Serve Time for product are around the same, but the missing Product values has less Average Serve Time

![alt text](https://github.com/theis19/Retail-Banking-EDA/blob/master/images/product_count.png "Product Count")
![alt text](https://github.com/theis19/Retail-Banking-EDA/blob/master/images/sub_product_pie.png "Sub-Product Proportion")
![alt text](https://github.com/theis19/Retail-Banking-EDA/blob/master/images/product_avg_minute.png "Product Average Serve Time (Minutes)")

## Issue
- Most of the complaints has issue with **Account opening, closing, or management**, followed by **Deposits and withdrawals**.
- Highest Average Serve Time is for **Privacy** issue, while the **Account opening, closing, or management** and **Deposits and withdrawals** which is the top 2 most complaint issue has Average Serve Time of 11 minutes.

## Complain Hour
- There's no real intake here since complains came at the same rate throughout the working hour, with 4 PM being the lowest since most working hour is done by that time.

![alt text](https://github.com/theis19/Retail-Banking-EDA/blob/master/images/comp_hour.png "Complain Hour")

## Tags
- 14% of the consumer are made of Older American, 5.1% Servicemember, and 3.1% Older American & Servicemember
- Maybe because they're older, they have trouble understanding our Server, Average Serve Time-wise they need 2 more minutes than usual.
- If we care about reducing our serve time, we could start making the banking system more friendly for older people or explain it better to them.

![alt text](https://github.com/theis19/Retail-Banking-EDA/blob/master/images/tags.png "Tags")
![alt text](https://github.com/theis19/Retail-Banking-EDA/blob/master/images/tags_avg_minute.png "Tags Average Serve Time (Minutes)")

# Loan Portfolio
![alt text](https://github.com/theis19/Retail-Banking-EDA/blob/master/images/loan_info.png "Columns Info")

## Quick Overview
- The higher the funded amount, the higher the consumer need to do payment for each month, this of course affects the loan balance left needed to be paid by the consumer. Also the higher the property amount, consumer will ask for more funded amount
- The lesser the duration, the more payment the consumer need to do each month
- The higher the 10 yr treasury index date funded the higher interest rate is
- Interest rate increases if fund amount is higher and duration is longer

![alt text](https://github.com/theis19/Retail-Banking-EDA/blob/master/images/loan_corr.png "Correlation Heatmap")

## Month
- There are more loan taker in latter half of the year, looking at this data i think the marketing team can do more promos or campaign during the latter half of the year.
- Average-wise we could see in the linechart below, almost every year, interest rate increase near October and November (besides 2019 since there's Covid-19 Outbreak), with higher interest we will profit more if we give out more loan near October and November

![alt text](https://github.com/theis19/Retail-Banking-EDA/blob/master/images/loan_month_count.png "Funded Month Count ")
![alt text](https://github.com/theis19/Retail-Banking-EDA/blob/master/images/loan_month_interest.png "Funded Month vs Interest Rate")
![alt text](https://github.com/theis19/Retail-Banking-EDA/blob/master/images/loan_month_amount.png "Funded Month vs Funded Amount")

## Duration
- The more duration the higher the interest rate
- Most loan-takers took 30 years duration loan
- The more duration the higher the funded amount given, but it seems average-wise the duration for 15 years has slightly higher funded amount than duration for 20 years. With the given information i have currently, then we might increase loan given with duration 15 years, since funded amount is slightly higher and the bank (lender) will get the money back faster (less riskier in case loan-taker suddenly cannot pay the loan)

![alt text](https://github.com/theis19/Retail-Banking-EDA/blob/master/images/duration_amount.png "Duration Years vs Funded Amount")

## Purpose
- Around the same overall, it seems the highest average interest rate is for the "home" purpose loan-takers though, so i would probably increase the aim to people with "home" purpose to generate more profit.

![alt text](https://github.com/theis19/Retail-Banking-EDA/blob/master/images/purpose.png "Purpose vs Interest Rate")
