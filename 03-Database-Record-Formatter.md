# Database Record Formatter – 

## Prompt Description
Develop a **comprehensive data cleaning and formatting workflow** for large, multi-column customer datasets. The workflow should ensure **accuracy, consistency, and readiness** for analytics, reporting, or CRM integration. The dataset now includes **additional columns** such as **Date of Birth, Gender, Signup Date, Membership Level, and Purchase History**, increasing the complexity of cleaning and validation.

The workflow must cover:

- **Duplicate detection and resolution across multiple identifiers** (Name, Email, Phone)  
- **Missing value handling across mandatory and optional fields**  
- **Normalization of text, capitalization, date formats, and numeric fields**  
- **Validation of emails, phone numbers, DOB, membership levels, and purchase history**  
- **Standardization for database, CSV, or Excel ingestion**  
- **Documentation of cleaning steps and edge case handling**  

Include **detailed reasoning for each cleaning step**, potential issues, and **practical implementation tips**. The final dataset must be **professional, reliable, and fully ready for analysis**.



## Prompt Text
You are given a raw customer dataset with the following columns:

- **Name**  
- **Email**  
- **Phone**  
- **City**  
- **Date of Birth**  
- **Gender**  
- **Signup Date**  
- **Membership Level** (Free, Standard, Premium)  
- **Last Purchase Amount**  

The dataset may include:

- Duplicate entries across Name, Email, or Phone  
- Missing values in any column  
- Inconsistent capitalization or formatting  
- Invalid emails, phone numbers, or dates  
- Incorrect or inconsistent membership levels  
- Outliers in Last Purchase Amount  

Perform a **complete data cleaning and formatting procedure** including:

1. **Duplicate Detection**  
   - Identify duplicates based on **Name + Email** or **Phone**.  
   - Keep the most complete record.  
   - Flag conflicts for manual review.  

2. **Missing Value Handling**  
   - Flag missing **Email, Phone, DOB, or Membership Level**.  
   - Fill missing **City** using inferred or default values.  
   - Impute or flag missing **Last Purchase Amount** for follow-up.  

3. **Normalization & Standardization**  
   - Convert **Name** and **City** to title case.  
   - Standardize **Email** to lowercase.  
   - Format **Phone numbers** uniformly (XXX-XXX-XXXX).  
   - Standardize **DOB and Signup Date** to YYYY-MM-DD format.  
   - Correct **Membership Level** typos (e.g., “premum” → “Premium”).  

4. **Validation**  
   - Validate **Emails** using regex.  
   - Validate **Phone numbers** for correct length and numeric characters.  
   - Check **DOB** and **Signup Date** for realistic ranges.  
   - Ensure **Membership Level** matches allowed categories.  
   - Flag outliers in **Last Purchase Amount** for review.  

5. **Structured Output**  
   - Cleaned dataset must be **CSV or Excel-ready**.  
   - Ensure consistent column order: **Name, Email, Phone, City, Date of Birth, Gender, Signup Date, Membership Level, Last Purchase Amount**.  
   - Include **5+ example rows** demonstrating cleaned data.



## Example Output – 

| Name          | Email                 | Phone       | City       | Date of Birth | Gender | Signup Date |Membership Level|Last Purchase Amount|
|---------------|-----------------------|-------------|------------|---------------|--------|-------------|----------------|-------------------|
| John Doe      | johndoe@email.com     | 555-123-4567| New York   | 1985-04-12    | Male   | 2022-01-15  | Premium        | 299.99            |
| Jane Smith    | jane.smith@email.com  | 555-987-6543| Boston     | 1992-08-30    | Female | 2021-11-05  | Standard       | 89.50             |
| Mark Johnson  | markj@email.com       | 555-555-7890| San Diego  | 1988-02-20    | Male   | 2022-03-10  | Free           | 0                 |
| Emily Davis   | emilyd@email.com      | 555-654-3210| Chicago    | 1995-12-01    | Female | 2021-09-12  | Premium        | 149.00            |
| Michael Brown | mbrown@email.com      | 555-111-2222| Los Angeles| 1983-06-18    | Male   | 2022-02-22  | Standard       | 75.00             |


## Paragraph Insight
“The extended dataset has been cleaned, normalized, and validated across all nine columns. **Duplicates** were removed to ensure accuracy, **missing values** were flagged or imputed where possible, and **field formatting** was standardized for text, dates, and numeric values. Email, phone, and membership level validation ensures operational reliability, while date checks guarantee realistic customer profiles. The dataset is now **ready for CRM integration, reporting dashboards, and analytical modeling**, providing a complete and trustworthy basis for business decisions.”



## Data Cleaning Steps Explanation
- **Duplicates:** Avoid overcounting and biased reporting.  
- **Missing Values:** Prevents gaps that distort metrics and ensures operational follow-up.  
- **Normalization:** Ensures consistency across multiple columns for smooth integration.  
- **Validation:** Reduces communication errors, maintains customer data integrity, and avoids analytics mistakes.  
- **Structured Output:** Enables seamless use in BI tools, SQL databases, Excel dashboards, or Python analytics workflows.



## Notes for Analysts
- Maintain **raw dataset backups** for audit purposes.  
- Track **all transformations, removed duplicates, and corrected fields** in a change log.  
- Use **automation scripts** (Python pandas, SQL, or Excel formulas) for large datasets.  
- Include **manual review for flagged anomalies** like outlier purchases or inconsistent DOB.  
- Ensure **final dataset compatibility** with downstream visualization and analytics tools.



## Data Visualization Suggestions
- **Bar charts:** Show counts of missing values per column and duplicates removed.  
- **Pie charts:** Illustrate distribution of membership levels or gender.  
- **Line charts:** Track monthly signups over time.  
- **Histograms:** Display distribution of Last Purchase Amount to identify high-value customers.  
- **Dashboard Table:** Highlight flagged records for quality control and validation review.  



## Insight – Business Impact
“Cleaning an extended dataset with multiple columns ensures reliable insights across **customer demographics, purchasing behavior, and membership patterns**. Standardizing and validating all fields enables **accurate reporting, segmentation, and marketing targeting**, reducing operational errors and increasing stakeholder confidence. Visualizations help executives quickly understand the dataset’s integrity and identify opportunities or risks.”


## Implementation Recommendations
- Use **bulk cleaning automation** for large datasets, but retain manual oversight for anomalies.  
- Standardize **date and numeric formats** across all systems to avoid downstream errors.  
- Document **all regex patterns and validation rules** applied to emails, phone numbers, and membership levels.  
- Perform **final quality checks** before releasing datasets to teams or systems.  
