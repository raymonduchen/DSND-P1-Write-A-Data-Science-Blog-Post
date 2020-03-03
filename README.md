# Trends or illusions ? Stack Overflow Survey Discovery

As a developer, you may feel some trends are happening based on your intuition or experience. But, is it a real trend or just an illusion? To answer this question, we need data to tell its story.

Since 2011, Stack Overflow conducted [developer survey](https://insights.stackoverflow.com/survey) examining all aspects of the developer experiences around the world. It covers career satisfaction, education and opinions on open source software, etc.

Here, I list three questions I’m interested in. In this article, I’ll share my findings below. Detailed works are implemented in my [Github repo](https://github.com/raymonduchen/DSND-P1-Write-A-Data-Science-Blog-Post). Here are my questions :

1. What are the top 5 popular languages from 2018 to 2019 ?
2. What is the most popular version control tool in 2018 ? What percentage does it take ?

3. What are the top 5 popular IDEs from 2017 to 2019 ?

You may guess the results before reading. Let's go !



## Getting Started

1. Clone this repository
2. Install and configure Python 3 environment 
3. Install the following dependency
   1. Pandas
   2. Numpy
   3. Matplotlib
   4. seaborn
   5. IPython
4. Clone this repository to a local folder.
5. Download 2017, 2018 and 2019 full data set from [Stack Overflow Survey](https://insights.stackoverflow.com/survey):
6. Unzip and place the folders in the local repository which cloned from step 1, say in the `DSND-P1-Write-A-Data-Science-Blog-Post/` folder. The file hierarchy is similar as follows :

```
DSND-P1-Write-A-Data-Science-Blog-Post/
|- developer_survey_2017
|  |- survey_results_public.csv
|  |- survey_results_schema.csv
|              ...
|- developer_survey_2018
|  |- survey_results_public.csv
|  |- survey_results_schema.csv
|              ...
|- developer_survey_2019
   |- survey_results_public.csv
   |- survey_results_schema.csv
               ...
```



## Instructions

1.  Open jupyter notebook `write_a_data_science_blog_post.ipynb`
2.  Execute all code cells



## Blog Post

I posted a [Medium blog](https://medium.com/@raymonduchen/trends-or-illusions-stack-overflow-survey-discovery-e2add81da3ff) to communicate my findings with stakeholders.



## Results

### Q : What are the top 5 popular languages from 2018 to 2019 ?

#### 1. Business Understanding

- What are the top 5 popular languages from 2018 to 2019 ?

#### 2. Data Understanding

- Read in Stack Overflow survey schema file and data file
- Found relavent column **LanguageWorkedWith** and checked its meaning using **get_description()** function

#### 3. Prepare Data

- Separate and count language item for each cell using **item_count()**
- Sort value according to **Count** column
- Correct and rename inconsistent language item in 2018 and 2019
  - **HTML** and **CSS** are seperatedly counted in 2018 but counted together as **HTML/CSS** in 2019
  - **Bash/Shell** in 2018 is the same category as **Bash/Shell/PowerShell** in 2019
- After all data preparation, I set index using **LanguageWorkedWith** column and plot bar charts for comparison.

#### 4. Evaluate the Results

- By examing the bar charts, the top 5 popular languages in 2018 and 2019 are :

|      | 2018       | 2019       |
| ---- | ---------- | ---------- |
| 1    | JavaScript | JavaScript |
| 2    | HTML/CSS   | HTML/CSS   |
| 3    | SQL        | SQL        |
| 4    | Java       | Python     |
| 5    | Shell      | Java       |

- The top 3 popular languages remain the same. Also, it can be noted that **Python** replace **Shell** in the top 5 list in 2019.



### Q : What is the most popular version control tool in 2018 ? What percentage does it take ?

#### 1. Business Understanding

- What is the most popular version control tool in 2018 ? What percentage does it take ?

#### 2. Data Understanding

- Read in Stack Overflow survey schema file and data file
- Found one relavent column **VersionControl** and confirmed its meaning using **get_description()** function

#### 3. Prepare Data

- Separate and count version control tool item for each cell using **item_count()**
- Sort value according to **Count** column
- Plot the pie chart for **VesionControl**.

#### 4. Evaluate the Results

- According to the pie chart, **Git** is the most popular version control tool and It takes about **63%** in 2018.



### Q : What are the top 5 popular IDEs from 2017 to 2019 ?

#### 1. Business Understanding

- What are the top 5 popular IDEs from 2017 to 2019 ?

#### 2. Data Understanding

- Read in Stack Overflow survey schema file and data file
- Found relavent column **IDE** in 2017 and 2018 data, and **DevEnviron** in 2019 data and confirmed their meaning using **get_description()** function

#### 3. Prepare Data

- Separate and count IDE item for each cell using **item_count()**
- Sort value according to **Count** column
- Rename inconsistent column name in 2017, 2018 and 2019
  - Rename **DevEnviron** in 2019 data as **IDE**, the same column name as in 2017 and 2018

#### 4. Evaluate the Results

- By examing the bar charts, the top 5 popular IDEs in 2017, 2018 and 2019 are :

|      | 2017          | 2018               | 2019               |
| ---- | ------------- | ------------------ | ------------------ |
| 1    | Visual Studio | Visual Studio Code | Visual Studio Code |
| 2    | Notepad++     | Visual Studio      | Visual Studio      |
| 3    | Sublime Text  | Notepad++          | Notepad++          |
| 4    | Vim           | Sublime Text       | Intellij           |
| 5    | Eclipse       | Vim                | Vim                |