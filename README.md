Project Overview

This project focuses on analyzing operating system resource usage data using Python. The dataset contains multiple CSV files representing system-level task execution metrics such as CPU usage, memory usage, queue length, and lock contention.

The project performs:

Data extraction and preprocessing
Cleaning and stratified sampling
Feature engineering
Load classification
Resource usage visualization
Dashboard generation for performance analysis

The objective is to study system workload behavior and classify load conditions based on calculated resource intensity.

Technologies Used
Python
Pandas
NumPy
Matplotlib
Seaborn
Google Colab
Dataset Information

The dataset contains multiple CSV files with operating system task metrics.

Sample Features
Timestamp [ms]
CPU usage [%]
Memory usage [KB]
Queue-related information
Lock contention metrics

The project combines all CSV files and performs sampling to create a balanced dataset for analysis.

Project Workflow
1. ZIP Upload and Extraction

The project accepts a ZIP file containing multiple CSV files.

Process
Upload ZIP dataset
Extract all CSV files
Store extracted files in a working directory
2. Data Cleaning and Stratified Sampling

The extracted CSV files are cleaned and sampled.

Cleaning Operations
Remove missing values
Handle invalid entries
Standardize column names
Merge datasets
Sampling

Approximately equal rows are sampled from each file to maintain balanced representation.

3. Feature Engineering

Additional features are generated to improve workload analysis.

Added Features
Queue Length

Randomized queue length values are generated:

queue_length = np.random.randint(1, 21)
Lock Contention

Random lock contention values are generated:

lock_contention = np.random.uniform(0, 1)
Composite Index (CI)

A custom workload metric called Composite Index is calculated:

CI = (
    0.4 * CPU_usage +
    0.3 * (queue_length / 20) +
    0.2 * Memory_usage +
    0.1 * lock_contention
)
Load Classification

The system load is classified based on the Composite Index.

CI Range	Load Level
Low CI	Light Load
Medium CI	Moderate Load
High CI	Heavy Load
Data Visualization

The project generates a structured dashboard using Seaborn and Matplotlib.

Dashboard Includes
CPU usage trends
Memory usage trends
Load distribution
Composite Index analysis
Resource utilization comparison
Output Summary

The notebook displays:

Total sampled rows
Average CPU usage
Average memory usage
Composite Index statistics
Load group analysis
Folder Structure
project-folder/
│
├── dataset/
│   ├── 15.csv
│   ├── 22.csv
│   ├── ...
│
├── notebook.ipynb
├── README.md
└── requirements.txt
Installation

Clone the repository:

git clone https://github.com/your-username/your-repository-name.git

Move into the project directory:

cd your-repository-name

Install required libraries:

pip install pandas numpy matplotlib seaborn
Running the Project

Open the notebook in:

Jupyter Notebook
Google Colab

Run all cells sequentially.

Upload the ZIP dataset when prompted.
