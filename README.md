# NYC Screened High School Admissions—School Year 2020
This repository contains code and data to reproduce the findings featured in our story "[NYC’s School Algorithms Cement Segregation. This Data Shows How](https://themarkup.org/investigation/2021/05/26/nycs-school-algorithms-cement-segregation-this-data-shows-how)."

Our methodology is described in "[How We Investigated NYC High School Admissions](https://themarkup.org/show-your-work/2021/05/26/how-we-investigated-nyc-high-school-admissions)."

Data we used to perform our analysis is in the `data` folder. Our final analysis is in the `output` folder.

Jupyter notebooks used for data collection, preprocessing, and analysis are in the `notebooks` folder.

## Installation
### Python
Make sure you have Python 3.6+ installed. We used [virtualenv](https://docs.python-guide.org/dev/virtualenvs/) to create a Python 3.8 virtual environment.

Then install the Python packages:<br>
`pip install -r requirements.txt`

## Notebooks
These notebooks have already been run and do not need to run sequentially.

### 0-rankings-collection.ipynb

This notebook pulls schools' percentile rankings within the city during 2019 from the NYC School Performance website. This notebook uses Selenium. For additional installation instructions see its [documentation](https://selenium-python.readthedocs.io/installation.html). Note that this notebook may not run due to potential changes to the site.

### 1-data-cleaning.ipynb

This notebook splits FOIL data into separate files for applicant counts, offer counts, and information about the school's name and screening method. The files generated from this notebook are found in the `data/cleaned` folder.

### 2-calculations.ipynb

This notebook calculates admissions rates by demographic, and the share of applicants and offers for each demographic. It also breaks out "top-ranked" schools and calculates the offer rate.

### 3-dia-statistics.ipynb

This notebook looks at Diversity in Admissions participants in 2020 and 2021 NYC DOE High School Directories.

### 4-data-summary.ipynb

This notebook calculates summary statistics about the original FOIL response data.

## Data

### Input Data

Data used in our analysis can be found in the `data` folder.

| File | Description |
|------|-------------|
| **`foil/data.csv`** | Applicant and offer data broken down by demographics for the fall 2020 admissions cycle for fully screened high schools in NYC. This data is from a FOIL response from the NYC Department of Education. |
| **`foil/notes.csv`** | Notes included in the FOIL response. |
| **`2020_DOE_High_School_Directory.csv`** | Detailed information about NYC high schools, including admissions methods and priority information, found on [NYC OpenData](https://data.cityofnewyork.us/Education/2020-DOE-High-School-Directory/23z9-6uk9). |
| **`metrics_2019.csv`** | Each school's percentile rank within the city for six different metrics, taken from the "Multi-Year Data Tables" featured in the [2019-20 School Performance Dashboard](https://tools.nycenet.edu/dashboard/#dbn=02M418&report_type=HS&view=City). |

### Output

#### Individual Schools' Applicant and Offer Demographics

| Column | Description |
|--------|-------------|
|`dbn`| The school's ID. |
|`School Name`| The name of the school.|
|`# Applicants`| The number of applicants who applied to the school. Note that according to the NYCDOE, the data is school level, meaning that "applicants to schools with multiple programs are only counted once even if they applied to 2+ programs at the school."
|`% Asian Applicants`| The estimated percentage of applicants who are Asian.
|`% Asian Applicants - Estimate Off By (+/-)`| The amount that estimated percentage of applicants who are Asian could be off by. For estimates, we calculate the minimum and maximum possible amount of students and use the midpoint. Most instances involve 0-5 students. For more information, read our methodology.
|`% Black Applicants`| The estimated percentage of applicants who are Black.
|`% Black Applicants - Estimate Off By (+/-)`| The amount that estimated percentage of applicants who are Black could be off by. For estimates, we calculate the minimum and maximum possible amount of students and use the midpoint. Most instances involve 0-5 students. For more information, read our methodology.
|`% Latino Applicants`| The estimated percentage of applicants who are Latino.
|`% Latino Applicants - Estimate Off By (+/-)`| The amount that estimated percentage of applicants who are Latino could be off by. For estimates, we calculate the minimum and maximum possible amount of students and use the midpoint. Most instances involve 0-5 students. For more information, read our methodology.
|`% White Applicants`| The estimated percentage of applicants who are White.
|`% White Applicants - Estimate Off By (+/-)`| The amount that estimated percentage of applicants who are White could be off by. For estimates, we calculate the minimum and maximum possible amount of students and use the midpoint. Most instances involve 0-5 students. For more information, read our methodology.
|`# Offers`| The number of students who recieved offers to the school.
|`% Asian Offers`| The estimated percentage of offers that went to students of Asian descent.
|`% Asian Offers - Estimate Off By (+/-)`| The amount that estimated percentage of offers that went to students of Asian descent could be off by. For estimates, we calculate the minimum and maximum possible amount of students and use the midpoint. Most instances involve 0-5 students. For more information, read our methodology.
|`% Black Offers`| The estimated percentage of offers that went to Black students.
|`% Black Offers - Estimate Off By (+/-)`| The amount that estimated percentage of offers that went to students who are Black could be off by. For estimates, we calculate the minimum and maximum possible amount of students and use the midpoint. Most instances involve 0-5 students. For more information, read our methodology.
|`% Latino Offers`| The estimated percentage of offers that went to Latino students.
|`% Latino Offers - Estimate Off By (+/-)`| The amount that estimated percentage of offers that went to students who are Latino could be off by. For estimates, we calculate the minimum and maximum possible amount of students and use the midpoint. Most instances involve 0-5 students. For more information, read our methodology.
|`% White Offers`| The estimated percentage of offers that went to White students.
|`% White Offers - Estimate Off By (+/-)`| The amount that estimated percentage of offers that went to students who are White could be off by. For estimates, we calculate the minimum and maximum possible amount of students and use the midpoint. Most instances involve 0-5 students. For more information, read our methodology. 
