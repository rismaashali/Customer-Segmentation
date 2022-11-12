# Customer Segmentation
# Workflow Customer Segmentation
1. Use Case
2. Business Understanding
3. Data Understanding
4. Data Preparation
5. Data Profiling
6. Data Cleansing
7. Exploratory Data Analysis
8. Preprocessing Modeling - RFM
9. Modelling - RFM
10. Labeling
11. Result
12. Recommendation

# Use Case Summary
- Objective Statement:
  - To gain insight into sales fluctuations per year.
  - To gain insight into the revenue earned per year and month.
  - To find out how long it's been since a customer ordering.
  - To gain insight about how often a customer orders.
  - To find out how much money customers spend on ordering goods.
  - To get insight about customer segmentation analysis.

- Challenges:
  - Large size of data, cannot maintain by excel spreadsheet.
  - There are inappropriate data types.

- Methodology / Analytic Technique:
  - Descriptive Analysis.
  - Graph Analysis.
  - Segment Analysis using Recency Frequency Monetary (RFM) Modelling

- Business Benefit:
  - Knowing sales performance every year so, it can be a reference for future decision making.
  - Helping Business Development Team to create product differentiation based on the characteristic for each customer.
  - Knowing how to treat customer with specific criteria.

- Expected Outcome:
  - Find out how sales fluctuate per year.
  - Find out how much revenue per year and per month.
  - Find out how long it's been since the customer ordered.
  - Find out how often customers orders.
  - Find out how much the customer spends when orders.
  - Know customer segmentation analysis.
  
# Business Understanding
- Retail is the sale of goods from a business to a consumer for their own use. A retail transaction handles small quantities of goods whereas wholesale deals with the purchasing of goods on a large scale.
- This case has some business question using the data:
  - How sales fluctuate per year?
  - How much revenue per year and per month?
  - How long it's been since the customer ordered?
  - How often customers orders?
  - How much the customer spends when orders?
  - How about customer segmentation analysis?
  
# Data Understanding
- Data of Customer order with 4 columns and 5009 rows
- This data from 04/01/2011 to 31/12/2014
- Source Code : https://www.kaggle.com/datasets/siddinho/sample-orders-dataset-retail
- Data Dictionary :
  - order_date : Customer order date 
  - order_id : Customer order unique Id
  - customer : Customer name
  - grand_total : Total cost from customers order

# Data Preparation
Code Used:
- Python Version: 3.7.15
- Packages: Pandas, Numpy, Matplotlib, Seaborn, Datetime, Plotly and Warnings

# Data Profiling
Data profiling is the process of reviewing source data, understanding structure, content and interrelationships, and identifying potential for data projects.

# Data Cleansing
- Data cleansing is the process of identifying and resolving corrupt, inaccurate, or irrelevant data.
- Common inaccuracies in data include missing values, misplaced entries, and typographical errors. In some cases, data cleansing requires certain values to be filled in or corrected, while in other instances, the values will need to be removed altogether.

# Exploratory Data Analysis
- How many product sold every month in 2011?

  ![2011](https://user-images.githubusercontent.com/113870005/201459678-b3792766-c4e9-49bd-8eda-e5d63e932ab8.png)

  The number of items purchased tends to **increase every year**. **In October sales declined sharply** but increased again in the following month, even exceeding sales in September. As for sales in **December experienced decline again**.

- How many product sold every month in 2012?

  ![2012](https://user-images.githubusercontent.com/113870005/201459681-2664527e-6c20-4efa-acd0-f8b3af3b366e.png)

  The number of items purchased tends to **increase every month**, in February to March there is a **sharp increase about 2 times**. In September there was a sharp increase. However, in the following month, October, there was a sharp decline. However, in November there was a high increase even higher than in September and  **increased again in December**.

- How many product sold every month in 2013?

  ![2013](https://user-images.githubusercontent.com/113870005/201459688-23b70b3e-a845-4fd7-91d5-5532bfaf40e7.png)

  The number of items purchased tends to **increase every month**, in February to March there is a **sharp increase to almost 2 times**. In September there was a sharp increase. However, in the following month, October, there was a sharp decline. However, in November there was a high increase in the number of goods purchased and returned **decreased slightly sales in December**.

- How many product sold every month in 2014?

  ![2014](https://user-images.githubusercontent.com/113870005/201459692-e5c62253-d787-4a5f-8840-07830a03f361.png)

  The number of items purchased tends to **increase every month**, in February to March there is a sharp increase to almost 2 times. In September there was a sharp increase. However, in the following month, October, there was a sharp decline. However, in November, there was a high increase in the number of goods purchased even higher than in September and again **decreased slightly sales in December**.

- How much monthly order in 2011-2014?

  ![newplot](https://user-images.githubusercontent.com/113869968/201459847-837c7813-a4aa-47cd-8244-5bb3a16c9b6c.png)

  Based on the chart above, **product sales always increased in September and November in 2011-2014**. Meanwhile, there was **always a fairly sharp decreased in October in 2011-2014**.

- How much annual revenue in 2011-2014?

  ![newplot (2)](https://user-images.githubusercontent.com/113869968/201459844-cd183e32-406f-47be-b1c4-0f83a5912bdf.png)

  Based on the chart above, **revenue in 2011 amounted to 484.26K dollars** and **in 2012 it was 470,539K dollars**. This means that **there was a decrease in revenue from 2011 to 2012 by 2.83%**. Meanwhile, **from 2013 to 2014, revenue continued to increase**. When viewed quantitatively, the increase in revenue from 2012 to 2013 was 29.3%. **From 2013 to 2014, revenue increased by 20.6%**.

- How much monthly revenue in 2011-2014?

  ![newplot (1)](https://user-images.githubusercontent.com/113869968/201445272-099f359c-3646-43b3-8503-14581c286291.png)
  
  Based on the chart above, monthly revenue from 2011-2014 is **seasonal** because in certain months there is an increase and decrease. In September and November in 2011-2014 there was **always a fairly high increase** in income, this may be due to the high demand for products for the Halloween and Christmas celebration preparation.
  
# Modeling Using RFM
### Recency Frequency Monetary (RFM)

RFM is a model used in marketing analysis that segments a company's consumer base by their purchasing patterns or habits. 

- Recency : how long it's been since a customer bought something from us.
- Frequency : how often a customer buys from us
- Monetary value : the total value of purchases a customer has made.

# Preprocessing Modeling

- Create new data frame containing customer name column and recency column. This is done by calculating how long since customers make purchases.
- Create new data frame containing customer name column, frequency column, and monetary column. The results of frequency can be determined by calculating how often customers make a purchase. While the monetary is produced from the calculation of how much money the customer spent making purchases.
- Combine the recency table with the frequency and monetary table.

# Modeling
- Split the metrics into segments using quantiles.
- Assign a score from 1 to 4 to each Recency, Frequency and Monetary respectively.
- 1 is the highest value, and 4 is the lowest value.
- A final RFM score (Overall Value) is calculated simply by combining individual RFM score numbers.

# Labelling
![image](https://user-images.githubusercontent.com/113869964/201459364-429f82bd-2619-493f-a90e-1d954f6d0906.png)


Based on the graph above, there are 6 segmentations of customers using RFM modeling. The Loyal Customers segmentation has the highest percentage of 16.27% of total customers. Followed by Big Spenders with a percentage amount of 15.76%, Lost Cheap Customers with a percentage amount of 8.45%, Lost Customers with a percentage amount of 3.91%, Best Customers with a percentage amount of 3.78%, Then Almost Customers with a percentage amount of 0.25%.

# Result
- In 2011, The number of items purchased tends to increase every year. In October sales declined sharply but increased again in the following month, even exceeding sales in September. As for sales in December experienced decline again.
- In 2012,The number of items purchased tends to increase every month, in February to March there is a sharp increase about 2 times. In September there was a sharp increase. However, in the following month, October, there was a sharp decline. However, in November there was a high increase even higher than in September and again increased sales in December.
- In 2013, The number of items purchased tends to increase every month, in February to March there is a sharp increase to almost 2 times. In September there was a sharp increase. However, in the following month, October, there was a sharp decline. However, in November there was a high increase in the number of goods purchased and returned decreased slightly sales in December.
- In 2014, The number of items purchased tends to increase every month, in February to March there is a sharp increase to almost 2 times. In September there was a sharp increase. However, in the following month, October, there was a sharp decline. However, in November, there was a high increase in the number of goods purchased even higher than in September and again decreased slightly sales in December.
- Product sales always increased in September and November in 2011-2014. Meanwhile, there was always a fairly sharp decreased in October in 2011-2014.
- Based on the chart Annual Revenue, revenue in 2011 amounted to 484.26K dollars and in 2012 it was 470,539K dollars. This means that there was a decrease in revenue from 2011 to 2012 by 2.83%. Meanwhile, from 2013 to 2014, revenue continued to increase. When viewed quantitatively, the increase in revenue from 2012 to 2013 was 29.3%. From 2013 to 2014, revenue increased by 20.6%.
- Based on the chart Monthly Revenue, monthly revenue from 2011-2014 is seasonal because in certain months there is an increase and decrease. In September in 2011-2014 there was always a fairly high increase in income, this may be due to the high demand for products for the feast day.
- Based on the graph Labelling, there are 6 segmentations of customers using RFM modeling. The Loyal Customers segmentation has the highest percentage of 16.27% of total customers. Followed by Big Spenders with a percentage amount of 15.76%, Lost Cheap Customers with a percentage amount of 8.45%, Lost Customers with a percentage amount of 3.91%, Best Customers with a percentage amount of 3.78%, Then Almost Customers with a percentage amount of 0.25%.

# Recommendation
- Recommendations for increased orders in a given month such as September and November: focus on increasing the amount of production of goods because in certain months such as September and November will receive high demand.
- Recommendations for a decrease orders in a given month such as October: focus on improving marketing strategy so that customers will orders in that month. It can also be by optimizing sales such as multiplying products in October with Halloween celebrations or give points to increase customer purchasing power by giving vouchers or other gifts. The company also can hold an event or sale that smells of Valentine's Day in February to increase sales for that month.
- Recommendations for Loyal Customers segment: The company must optimize the campaign for this customer segment in order to maintain their loyalty. It can also give additional points for customer loyalty.
- Recommendations for Big Spenders segment: focus on offering other products, especially products that match customer interests or products that are often sought after. Can also offer products with a high price range.
- Recommendations for Lost Cheap Customers segment: focus on activating customers and making repurchases by forming a Reactivation Strategy. One of them is by offering products that have been purchased.
- Recommendations for Lost Customers segment: focus on activating customers and making repurchases by forming a Reactivation Strategy. One of them is by offering products that have been purchased.
- Recommendations for Best Customers segment: focus on increasing customer purchases therefore it is necessary to form a Cross Selling or Up Selling Strategy by offering other products that can be complementary to frequently purchased products.
- Recommendations for Almost Lost segment: focus on activating customers and making repurchases by forming a Reactivation Strategy. One of them is by offering products that have been purchased.
