After completing my data engineering online course, I worked with Azure to finish an end-to-end big data engineering project.



Project Architecture

The project utilizes an end-to-end data pipeline architecture built on **Azure Data Factory** and **Azure Data Lake Storage Gen2**, integrating multiple components for seamless data processing and storage. Here's a high-level breakdown of the architecture:

 1. Data Ingestion
   - **Source**: Data is sourced from multiple CSV files hosted on a GitHub repository using HTTP links.
   - Data Ingestion Pipeline: The pipeline uses **Azure Data Factory** to fetch data from GitHub, with each file having a relative URL that points to the dataset in the repository.
   - ForEach Activity: A `ForEach` loop iterates over the list of files, processing each file individually by using their relative URLs and file names stored in a JSON configuration.

2. Data Storage
   - Azure Data Lake Storage Gen2: Processed data is stored in Azure Data Lake Storage Gen2 (ADLS Gen2), organized within containers for easy access and management.
   - Sink: The data is written into containers under the "bronze" layer, enabling a clear and organized data storage structure.

 3. Copy Activity
   - CopyInsideForEach: This activity copies the files fetched from GitHub into the designated containers in ADLS Gen2.
   - Linked Services: The project is set up with linked services for both GitHub (HTTP) and Azure Data Lake Storage Gen2, ensuring secure and efficient data transfers.
   - Sequential Execution: The data is processed sequentially for each file inside the ForEach loop, ensuring smooth processing for each dataset.

4. Error Handling
   - The architecture accounts for potential errors such as 404 (File Not Found) and ensures that data is transferred correctly after proper verification of paths.


This architecture efficiently facilitates the ingestion, processing, and storage of data from various sources into a secure and scalable cloud environment, leveraging Azure's capabilities for optimal performance.
