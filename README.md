
# Project: Home Sales Data Analysis with SparkSQL

In this project, we harnessed the power of Big Data and SparkSQL to meticulously analyze and query home sales data. The data analysis process was executed through the following steps:

**1. Importing Essential Packages:** We initiated the project by importing essential packages, such as findspark for Spark initialization and pyspark.sql for SparkSQL functionality.

**2. Establishing a SparkSession:** To establish a seamless connection with Spark, we created a SparkSession using `SparkSession.builder.appName("SparkSQL").getOrCreate()`.

**3. Data Ingestion:** The home sales data was fetched from an AWS S3 bucket and transformed into a DataFrame using the provided URL.

**4. Creating a Temporary View:** We established a temporary view named "my_table" for the DataFrame, which allowed us to execute SQL queries seamlessly.

**5. Data Exploration:** Various SQL queries were employed to gain insights from the home sales data. This included calculating the average price of four-bedroom houses sold each year and dissecting average prices based on attributes like bedrooms, bathrooms, and square footage.

**6. Data Caching:** To optimize query performance, we cached the "home_sales_df" DataFrame in memory using `spark.catalog.cacheTable()`.

**7. Query Performance Comparison:** A performance comparison was conducted between a specific query executed on the cached DataFrame and another on the Parquet data. Query start times were recorded using `time.time()` before execution, and the time difference was calculated for runtime assessment.

**8. Storing Data in Parquet Format:** The formatted home sales data was efficiently written to Parquet format, partitioned by the "date_built" field, employing the `partitionBy().parquet()` method.

**9. Retrieving Parquet Data:** The Parquet data was read back into a DataFrame for further analysis.

**10. Temporary Table for Parquet Data:** We established a temporary table named "parquet_table" for the Parquet DataFrame using `createOrReplaceTempView()`.

**11. Querying Parquet Data:** SQL queries were executed on the Parquet DataFrame to filter view ratings with an average price greater than or equal to $350,000. The runtime was measured and compared to the cached version.

**12. Uncaching Data:** To release memory resources, we uncached the temporary table "home_sales" using `spark.catalog.uncacheTable()`.

**13. Caching Status Verification:** Finally, we confirmed the caching status of the "home_sales" table using `spark.catalog.isCached()`.

In essence, this project showcased the powerful capabilities of SparkSQL in reading, querying, caching, and analyzing home sales data, ultimately providing valuable insights into average prices based on diverse criteria.
