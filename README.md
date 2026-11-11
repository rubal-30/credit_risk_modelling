# Loan Portfolio Risk Analysis | Sirius Finserv

An exploratory data analysis (EDA) and loan-risk assessment project using **Python, Pandas, NumPy, Matplotlib, and Seaborn**. The project studies loan quality, customer characteristics, lending channels, and application trends using an anonymized loan-book dataset provided for an analytics assignment.

## Project overview

The goal is to identify which kinds of loans are more likely to become bad loans, examine possible drivers of risk, and translate the findings into practical lending-policy recommendations.

A **bad loan** is defined in this project as a loan with status **Default**, **Charged Off**, or **Auctioned**. For risk comparisons, the analysis uses loans disbursed **before 1 April 2024** to allow more time for repayment problems to emerge. Loan status is observed as of **30 September 2025**.

## Dataset and preparation

- **48,355 rows and 40 columns** in the original file.
- **355 repeated loan IDs** removed, retaining the first record for each loan ID.
- **60 records** with disbursal dates earlier than application dates excluded.
- **47,940 loans** remained after those exclusions.
- Dates and numeric fields were converted to appropriate types; inconsistent product, gender, employment, and city labels were standardized.
- Missing values and implausible ages, loan tenures, incomes, and CIBIL scores were investigated and documented.
- EMI amounts were independently recalculated; **940 EMI loans (2.14%)** differed from their recorded EMI by more than **₹10**.

The dataset was supplied for the assignment. **It is not included in this repository unless redistribution is permitted.**

## Analysis covered

1. Data inspection, duplicates, missing values, and quality checks.
2. Loan amount, income, interest-rate, and credit-score distributions.
3. Loan count and lending amount by product, channel, city tier, and employment type.
4. Bad-loan rates by customer profile, credit score, product, channel, and EMI burden.
5. Fintech Partner versus other channels, including comparisons within CIBIL bands.
6. Monthly application volumes, product trends, weekday patterns, and quarterly loan performance.

## Key findings

| Finding | Result |
| --- | --- |
| Overall bad-loan rate among older loans | **7.42%** (1,985 of 26,743) |
| CIBIL 600–649 vs. CIBIL 800–900 | **21.83%** vs. **1.65%** bad-loan rate |
| Business Loans vs. Home Loans | **13.72%** vs. **1.01%** |
| Fintech Partner vs. Branch | **16.02%** vs. **5.34%** |
| EMI burden above 75% vs. below 30% | **16.32%** vs. **5.93%** |
| No credit history vs. established credit history | **10.20%** vs. **7.16%** |

Loans issued in **2023 Q3 (9.42%)** and **2024 Q1 (9.34%)** had particularly high observed bad-loan rates. Application volumes also showed notable spikes, especially around October, with Personal Loans and Consumer Durable Loans contributing strongly.

These are **observed associations**, not proof that any single factor causes a loan to go bad or that a factor is the best standalone predictor.

## Recommendations

- Strengthen income and repayment-capacity checks for applicants with weaker credit scores.
- Review customers whose monthly repayment burden exceeds **45% of income**; this is a proposal to test, **not** a validated approval cutoff.
- Monitor higher-risk products and sourcing channels—particularly Business Loans and Fintech Partner—with more detailed customer-level reviews.

## Tools

- Python
- Pandas and NumPy
- Matplotlib and Seaborn
- Google Colab / Jupyter Notebook

## How to run

1. Download the notebook from this repository and open it in **Google Colab**.
2. Obtain the authorized `loan_book.csv` dataset.
3. Run the cells from top to bottom and upload the CSV when prompted.
4. Review the generated tables, charts, and written conclusions.

> **Data note:** The notebook uses `files.upload()` to load the CSV interactively. Do not commit customer-level loan records or confidential information to a public repository without permission.

## Limitations

- Loan outcomes are based on a single snapshot dated **30 September 2025**; newer loans have had less time to develop repayment problems.
- Some fields contain missing or inconsistent information, and a subset of recorded EMIs does not match the standard calculation.
- Group comparisons may also reflect differences in customer and product mix. Additional validation is required before changing lending policy.

## Project context

Completed as part of a **Python for Data Analysis: Loan Book** assignment. The project focuses on data cleaning, exploratory analysis, and communicating results in plain business language—not building a deployed credit-scoring model.
