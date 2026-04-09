#EXP13## Project Overview
The primary objective of this experiment is to perform preprocessing on a dataset, specifically focusing on identifying, analyzing, and resolving missing values using various imputation and cleaning strategies.

### Technologies Used

Python 3

Pandas: Used for tabular data manipulation and handling missing data (NaN).

NumPy: Used for scientific computing and representing missing values as np.nan.

## Core Concepts & Operations
### Identifying Missing Values

The notebook demonstrates how to locate and quantify missing data within a DataFrame:

df.isna(): Returns a boolean mask identifying where data is missing.

df.isna().sum(): Provides a count of null values per column (axis=0) or per row (axis=1).

df.notna(): The inverse of isna(), showing True for valid data points.

### Data Cleaning Strategies

Two main approaches are explored for handling missing values:

Deletion:

df.dropna(): Drops rows containing at least one missing value.

df.dropna(axis=1): Drops entire columns that contain missing values.

Imputation (Filling):

df.fillna(value='DEFAULT'): Replaces all NaN values with a specific string.

df.fillna(0): Replaces missing values with a numeric zero.

Mean Imputation: Replacing missing values with the column average (df.fillna(df.mean())).

## Detailed Student Preprocessing Case Study
The notebook includes a practical example involving a student dataset with inconsistent formatting and placeholders (e.g., '-').

### Preprocessing Steps:

Placeholder Replacement: Replacing generic characters like '-' with np.nan to enable mathematical operations.

Type Conversion: Using pd.to_numeric with errors='coerce' to convert object-type columns (Age, Marks) into numeric formats.

Targeted Imputation:

Age: Filled with the Mean (since age typically has low variation among students).

Marks: Filled with the Median (to reduce the influence of outliers).

Categorical Normalization: Converting "Department" strings to uppercase (e.g., 'cse' to 'CSE') to ensure consistency.

Date Standardization: Using pd.to_datetime with format="mixed" to resolve varying date formats (e.g., 01-06-2023 and 10/06/23) into a single standard format.
