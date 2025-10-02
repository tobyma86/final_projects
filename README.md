# Data 101 Final Project: A Comparison Study between PostgreSQL and MongoDB Using Yelp Dataset

## Overview
This final project, "A Comparison Study between PostgreSQL and MongoDB Using Yelp Dataset," examines the distinct capabilities and performance characteristics of a relational database (PostgreSQL) and a non-relational, document-based database (MongoDB). The study uses the Yelp dataset, which includes five JSON files containing information on businesses, reviews, and users, to simulate and analyze various database tasks.

Per [UC Berkeley](https://www.berkeley.edu) course agreements, only the final report may be shown on GitHub, and source codes and notebooks are omitted. Please read the full spec on the [Data 101 Website](https://data101.org/fa24/assignments/final-project/) and the dateset on the [Yelp](https://business.yelp.com/data/resources/open-dataset/) website.

## Project Setup and Data Preparation
The team used JupyterLab with Python libraries like ```psycopg3``` and ```pymongo4``` to work with local instances of PostgreSQL and MongoDB. Due to the large size of the dataset, particularly the 5 GB ```review.json``` and 2.7 GB ```user.json``` files, the team sampled a portion of the data to manage hardware limitations and performance issues. For PostgreSQL, the semi-structured JSON files were converted into a tabular CSV format to align with its relational structure.

## Key Tasks and Findings
The project performed several tasks in both databases to compare their functionality and efficiency:
* **PostgreSQL**:
  * **Task 1 & 2**: Analyzed relational data to find users who reviewed in multiple cities and to generate a ranked summary of users based on their reviews. PostgreSQL's efficient query planner and join operations were well-suited for these relational tasks.
  * **Task 3 & 4**: "Unwound" the JSON-like ```hours``` column to show daily hours for ```businesses```. The team found that using PostgreSQL's native JSON functions (Task 4) was significantly faster (600.89 ms) and more maintainable than a text-parsing approach using string manipulation functions (3857.42 ms).
* **MongoDB**:
  * **Task 1**: Identified all 5-star reviews and calculated their total count and average usefulness rating, completing the task in 398 ms.
  * **Task 2**: "Unwound" the nested ```hours``` field using MongoDB's aggregation framework, specifically the ```\$objectToArray``` and ```\$unwind``` keywords. This approach was noted for its code cleanliness and efficiency in handling semi-structured data.

## Conclusion
The project concluded that both PostgreSQL and MongoDB are powerful tools with distinct strengths:

* **PostgreSQL** excels at handling **structured** data and complex relational queries, making it a robust choice when data consistency and schema enforcement are critical.
* **MongoDB** is better suited for **flexible, semi-structured** data, with its native JSON handling and powerful aggregation pipeline simplifying complex data transformations.

The team's reflections highlighted the initial challenges of data preparation for a relational database and the learning curve associated with MongoDB's non-relational paradigm. Ultimately, the choice between the two databases depends on balancing the specific characteristics of the data with the practical needs of the project.

---

## Repository Structure

The final project contains this starter setup. You may adapt it as needed, but please make sure you don't commit large files which can be complicated to undo.

```
.
├── README.md                  # Project documentation
├── data101_final_report.pdf   # Final report


```

**Warning:** It can be tricky to work with large files and git / GitHub. We've set up a `.gitignore` to exclude many common large files, and **everything** inside `data/`.

---
