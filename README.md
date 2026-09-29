# Excel Data Cleaning and Transformation – Data Analytics Project

## 📊 Project Overview

This project demonstrates a complete **data cleaning and transformation workflow using Microsoft Excel**.

The objective was to take a raw product dataset containing missing values, inconsistent text, duplicate records, incorrectly categorized data, and unstructured Product ID information, and transform it into a cleaner and more analysis-ready dataset.

This project helped me develop practical skills in:

- Data Cleaning
- Data Quality Management
- Data Standardization
- Missing Value Handling
- Duplicate Detection and Removal
- Data Transformation
- Text Manipulation
- Column Splitting and Merging
- Number and Date Formatting
- Conditional Formatting
- Excel Data Preparation

The dataset contains product-related information such as **Product ID, Product Name, Brand Name, Price, Quantity, and Category**.

---

# 🎯 Project Objective

The main objective was to prepare the raw product dataset for further analysis by identifying and correcting data-quality problems.

The workflow followed these major stages:

1. Inspecting the raw dataset
2. Identifying missing values
3. Handling missing categories
4. Identifying inconsistent text formats
5. Correcting category errors
6. Removing duplicate records
7. Splitting the Product ID into meaningful fields
8. Merging Product Name and Brand Name
9. Applying appropriate number and date formats
10. Applying conditional formatting
11. Validating the final cleaned dataset

The assignment itself defines the goal as improving data usability, consistency, and quality before analysis.

---

# 📁 Dataset Description

The original dataset contains the following main attributes:

| Column | Description |
|---|---|
| Product ID | Identifier containing date/month and country information |
| Product Name | Name of the product |
| Brand Name | Brand associated with the product |
| Price ($) | Product price |
| Quantity | Available/product quantity |
| Category | Product category |

The assignment identifies the dataset as a **Product Dataset** with these core attributes.

---

# 🔍 Step 1 – Initial Data Inspection

I first inspected the raw dataset to understand its structure and identify potential data-quality problems.

The raw dataset contained **34 records and 6 columns**.

During the initial inspection, I identified:

- Missing values in the `Price ($)` column
- Missing values in the `Category` column
- Inconsistent capitalization in `Product Name`
- A misspelled category value
- Duplicate records
- Product IDs containing multiple pieces of information that could be separated into different columns

This initial profiling step was important because data should be understood before applying transformations.

---

# 🧹 Step 2 – Handling Missing Values

## Price Column

The raw dataset contained missing values in the `Price ($)` column.

Instead of inserting arbitrary values, the missing prices were retained as blank/null values in the cleaned dataset because there was insufficient information in the provided dataset to determine the actual prices.

The affected products include:

- Camping Tent
- Headphones
- Sunglasses

This demonstrates an important data-analysis principle: **missing data should not automatically be replaced with guessed values**.

Possible approaches in a real-world project could include:

- Checking the original source system
- Looking up the value from a trusted reference dataset
- Using an appropriate statistical imputation method when justified
- Keeping the value missing if no reliable information exists

The assignment specifically requires checking missing prices and proposing an appropriate strategy for missing price information.

## Category Column

Several records had missing categories in the original dataset.

The cleaned dataset contains populated categories for these records based on the product information.

Examples include:

- Backpack → Accessories
- Coffee Maker → Electronics
- Fitness Tracker → Electronics
- Sneakers → Fashion

The purpose of this step was to ensure that the categorical field could be used consistently for grouping and analysis.

---

# ✏️ Step 3 – Correcting Inconsistent Text

The raw dataset contained inconsistent capitalization in the `Product Name` column.

Examples included:

- `laptop`
- `smartphone`
- `headphones`

These were standardized where appropriate so that product names followed a more consistent naming convention.

For example:

**Before:**
`laptop`

**After:**
`Laptop`

Text standardization is important because inconsistent capitalization can cause the same product to appear as different values during analysis.

For example:

`Laptop`, `laptop`, and `LAPTOP`

could incorrectly be interpreted as three separate categories by some analytical processes.

The assignment specifically requires identifying inconsistent Product Name formatting and standardizing it using Excel's Find and Replace functionality.

---

# 🏷️ Step 4 – Correcting Category Errors

A typo was identified in the `Category` column:

**Before:**
`Electroni`

**After:**
`Electronics`

This correction is important because categorical values must use consistent labels.

Without correction, an analysis such as:

> Total sales by category

could incorrectly treat `Electroni` and `Electronics` as two different categories.

This step improved the consistency and analytical usability of the dataset.

---

# 🗑️ Step 5 – Removing Duplicate Records

Duplicate records were identified by comparing the complete row.

The original dataset contained **3 duplicate records**, representing repeated rows.

Examples included duplicate records for:

- Laptop Bag – Samsonite
- Laptop – HP
- Headphones – Bose

These duplicate records were removed from the cleaned dataset.

The cleaned workbook therefore contains **31 records** compared with the original 34 records.

Removing duplicates prevents problems such as:

- Inflated record counts
- Incorrect quantity calculations
- Incorrect averages
- Double-counting products
- Misleading analytical results

The assignment specifically requires checking the entire row for duplicates and removing duplicate rows where they exist.

---

# 🔀 Step 6 – Splitting the Product ID

The `Product ID` contained multiple pieces of information in a single field.

Example:

`22-MAY-US`

This identifier contains:

- `22` → Day
- `MAY` → Manufacturing month
- `US` → Country code

I transformed the Product ID into separate fields to make the information easier to analyze.

The cleaned dataset contains:

### Manufacturing Date

A separate `MANUFACTURING DATE` field was created.

### Country Code

A separate `country code` field was created.

### Month

A `MONTH` field was also derived from the Product ID.

Excel text functions were used for this transformation.

For example, the cleaned workbook uses functions based on:

`MID()`

to extract the month information, and:

`RIGHT()`

to extract the country code.

This transformation converts an encoded identifier into separate analytical attributes.

The assignment explicitly asks for the Product ID to be split into Manufacturing Date and Country Code and for unnecessary characters to be removed.

---

# 🔗 Step 7 – Merging Product Name and Brand Name

The `Product Name` and `Brand Name` columns were combined to create a new field called:

`PRODUCT BRAND`

Examples:

- Backpack + North Face → `BackpackNorth Face`
- Blender + Vitamix → `BlenderVitamix`
- Camera + Nikon → `CameraNikon`
- Laptop + Dell → `LaptopDell`

This transformation demonstrates how multiple columns can be combined to create a new descriptive field.

The cleaned workbook uses a concatenation formula to combine the two fields.

The assignment specifically requires merging Brand Name and Product Name into a `Product Brand` column.

---

# 💰 Step 8 – Price Formatting

The `Price ($)` column was formatted as a currency/price field.

This makes the dataset easier to read and ensures that monetary values are visually distinguishable from other numeric fields.

For example:

`1000`

can be displayed as a currency value rather than as an unformatted number.

Correct number formatting is particularly important when preparing datasets for presentation and reporting.

The assignment requires the Price column to use currency formatting.

---

# 📅 Step 9 – Manufacturing Date Formatting

The extracted manufacturing date was formatted to follow the required:

**DD-MM-YYYY**

format.

This creates a standardized date representation and makes the date field easier to interpret.

Standard date formatting is useful when performing:

- Date-based filtering
- Sorting
- Time-based analysis
- Monthly/yearly comparisons
- Reporting

The assignment specifically requires the Manufacturing Date to be displayed in DD-MM-YYYY format.

---

# 🎨 Step 10 – Conditional Formatting

Conditional formatting was applied to make important information easier to identify visually.

## Price Column

A data bar/color-scale style of conditional formatting was applied to the Price field.

This makes it easier to visually compare products based on their prices.

For example:

- Lower values → smaller visual representation
- Higher values → larger visual representation

This allows patterns in the price distribution to be recognized quickly without manually comparing every number.

## Category Column

A custom conditional-formatting rule was also applied to identify:

`Electronics`

products.

This makes records belonging to the Electronics category easier to locate.

The assignment specifically requires conditional formatting for Price and a custom rule for highlighting Electronics in the Category column.

---

# ✅ Step 11 – Final Data Validation

After completing the transformations, I reviewed the cleaned dataset to confirm that the major data-quality issues had been addressed.

The final dataset contains:

- **31 records**
- **12 main working columns**
- Standardized product information
- Corrected category spelling
- Removed duplicate rows
- Separated Product ID information
- Combined Product and Brand information
- Currency/number formatting
- Date formatting
- Conditional formatting

I also checked that the transformed columns corresponded correctly to the original Product ID values.

Validation is an important final step because cleaning a dataset is not complete until the transformations have been checked for accuracy.

The assignment's evaluation guidelines also emphasize validating missing values, standardized categories, duplicate removal, column transformations, and formatting rules.

---

# 🛠️ Tools & Excel Functions Used

### Software

- Microsoft Excel

### Excel Features

- Find & Replace
- Remove Duplicates
- Conditional Formatting
- Number Formatting
- Date Formatting
- Text Manipulation
- Column Splitting
- Column Merging
- Data Validation

### Excel Functions

Some of the transformations used functions such as:

```text
MID()
RIGHT()
CONCAT()
```

These functions were used to extract information from Product IDs and combine product-related fields.

---

# 📈 Before vs After

| Data Quality Issue | Raw Dataset | Cleaned Dataset |
|---|---|---|
| Missing Prices | Present | Retained where value could not be reliably determined |
| Missing Categories | Present | Categories populated where identifiable |
| Product Name inconsistencies | Present | Standardized |
| Category typo | `Electroni` | `Electronics` |
| Duplicate records | 3 duplicates | Removed |
| Product ID | Combined information | Separated into useful fields |
| Product + Brand | Separate columns | `PRODUCT BRAND` created |
| Price formatting | Numeric | Currency/price format |
| Manufacturing Date | Encoded in Product ID | Separate date field |
| Conditional Formatting | Not prepared | Applied |

---

# 💡 Key Learning Outcomes

Through this project, I gained practical experience in the data-preparation stage of the data analytics workflow.

### 1. Data Cleaning

I learned how to identify and address common problems such as missing values, inconsistent text, incorrect category labels, and duplicate records.

### 2. Data Transformation

I learned how to convert an encoded Product ID into separate analytical fields and how to create new fields by combining existing columns.

### 3. Data Quality

I understood how seemingly small problems, such as spelling differences or duplicate records, can affect analysis and reporting.

### 4. Excel Data Analysis

I developed hands-on experience with Excel functions, formatting tools, Find & Replace, Remove Duplicates, and Conditional Formatting.

### 5. Analytical Thinking

Rather than simply changing values, I learned to consider whether a correction was supported by the available data and whether a transformation would make the dataset more useful for future analysis.

---

# 📂 Project Files

The project contains:

```text
Excel-Data-Cleaning-Transformation/
│
├── Raw Dataset/
│   └── AssigN 2 - Data Clean and TransforM.xlsx
│
├── Cleaned Dataset/
│   └── Assignment 2 - Data Cleaning and Transformation.xlsx
│
├── Documentation/
│   └── Excel Assignment-2.pdf
│
└── README.md
```

---

# 🚀 Skills Demonstrated

**Data Analytics**

- Data Cleaning
- Data Preparation
- Data Transformation
- Data Quality Management
- Data Validation

**Microsoft Excel**

- Text Functions
- Find & Replace
- Remove Duplicates
- Conditional Formatting
- Date Formatting
- Currency Formatting
- Column Transformation

**Analytical Skills**

- Identifying Data Quality Issues
- Standardizing Data
- Structuring Raw Data
- Preparing Data for Analysis
- Documenting Data-Cleaning Processes

---

# 🎓 Project Summary

This project represents one of my practical steps toward becoming a **Data Analyst**.

The project demonstrates how a raw dataset can be systematically inspected, cleaned, transformed, formatted, and validated using Microsoft Excel before being used for analysis.

The overall workflow can be summarized as:

**Raw Data → Data Inspection → Cleaning → Standardization → Transformation → Formatting → Validation → Analysis-Ready Dataset**

This project strengthened my understanding of the importance of data quality and gave me practical experience in preparing datasets for reliable analysis.

---

## 👤 About Me

I am an aspiring **Data Analyst** developing practical skills in data cleaning, data transformation, visualization, and analytical problem-solving.

I am currently building hands-on projects using tools such as **Microsoft Excel, SQL, Python, and Power BI** to strengthen my data analytics portfolio.

I am interested in transforming raw data into meaningful insights and continuously improving my analytical and technical skills.
