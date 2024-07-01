# Bing News Data Analytics Project
Project to showcase the expertise on MS Fabric platform in addition to acing Microsoft Fabric Analytics Engineer Associate(DP-600) exam.

## Note: Project Version 1.0
  - *Project is currently in BETA but with full working functionality. Future features will be added later in upcoming versions.*

## Overview

This project implements a comprehensive Bing News Data Analytics Platform using Microsoft Fabric. The platform ingests the latest **Stock Market** news data from Bing Search, processes it, and creates a dynamic report. This report serves as a ***Stock Market Sentiment Prediction dashboard*** showcasing the latest news and relevant analytics.

## Dashboard Link
Access the report from the [Here.](https://app.fabric.microsoft.com/reportEmbed?reportId=98551fd5-bc71-4983-a1fe-baee78329e09&autoAuth=true&ctid=13ed772a-0b84-4582-aee1-530b55129b33)

## Tools and Technologies Used

- **Microsoft Fabric**: The core platform used for implementing the project.
  - **Data Factory**: Used for data ingestion.
  - **OneLake**: The storage solution within Fabric, storing both raw and processed data.
  - **Synapse Data Engineering**: Utilized for transforming raw JSON data into structured Delta tables.
  - **Synapse Data Science**: Used for performing sentiment analysis on the news data.
  - **Power BI**: For creating and visualizing the news dashboard.
  - **Data Activator**: For setting up alerts based on the data in the Power BI dashboard.

## Project Architecture

1. **Data Ingestion**
   - **Bing API**: The data source for ingesting the latest news.
   - **Data Factory**: Connects to the Bing API and ingests news data into the Fabric workspace as JSON files.

2. **Storage**
   - **OneLake**: 
     - Stores raw JSON files in a Lake Database.
     - Utilizes Lake Database, Data Warehouse, and Kusto Database within OneLake.

3. **Data Transformation**
   - **Synapse Data Engineering**: 
     - Transforms raw JSON files into structured Delta tables using Spark notebooks.
     - Implements incremental load functionality for efficient data processing.

4. **Sentiment Analysis**
   - **Synapse Data Science**:
     - Uses a pre-trained text analytics model to predict the sentiment of news articles.
     - Stores the sentiment-analyzed data as Delta tables in the Lake Database.

5. **Data Visualization**
   - **Power BI**:
     - Creates a news dashboard to monitor the latest news.
     - Utilizes data from the final Delta tables for visualization.

6. **Scheduling**
   - **Data Pipeline**
     - Set a scheduling system to automatically extract the data at specific time of the day, everyday until my trial expires.
     - Extracted data automatically appened to the respective delta tables in the Lakehouse.

6. **Alerts and Notifications**
   - **Data Activator**:
     - Configures alerts based on visual data from Power BI.
     - Sends alerts via email or Microsoft Teams when specific conditions are met, such as detecting negative sentiment in news articles.

## Project Workflow

1. **Configure Bing API** in Azure to use it as a data source.
2. **Ingest Data**:
   - Use Data Factory to ingest news data from Bing API into the Fabric workspace as JSON files.
3. **Store Data**:
   - Save the JSON files in OneLake's Lake Database.
4. **Transform Data**:
   - Use Synapse Data Engineering to convert JSON files into structured Delta tables.
   - Implement incremental load for efficient data handling.
5. **Perform Sentiment Analysis**:
   - Utilize Synapse Data Science to analyze the sentiment of news articles.
   - Store the sentiment-analyzed data as Delta tables.
6. **Create Dashboard**:
   - Use Power BI to create a news dashboard for visualizing the data.
7. **Set Up Alerts**:
   - Configure Data Activator to send alerts based on specific conditions in the Power BI dashboard.

## Conclusion

This project demonstrates the integration of various tools within Microsoft Fabric to create a comprehensive news data analytics platform. The platform facilitates data ingestion, storage, transformation, analysis, visualization, and alerting, providing a robust solution for monitoring the latest Stock Market news.
