 Project Overview
This project involves using SQL subqueries and aggregation functions to analyze and extract insights from a dataset. The goal is to perform various operations such as identifying top students, calculating averages, and finding the second-highest math score.

example:
Project Steps
Step 1: Database Setup
Create the Students Table:

sql
CREATE TABLE Students (
    student_id INT PRIMARY KEY,
    name VARCHAR(50),
    math_score INT,
    science_score INT,
    english_score INT
);
The table includes:

student_id: Unique identifier (Primary Key)

name: Student's name

math_score, science_score, english_score: Scores in respective subjects

Insert Sample Data:

sql
Copy
Edit
INSERT INTO Students (student_id, name, math_score, science_score, english_score)
VALUES
    (1, 'Alice', 85, 90, 88),
    (2, 'Bob', 92, 76, 80),
    (3, 'Charlie', 78, 85, 82),
    (4, 'David', 95, 88, 91),
    (5, 'Eva', 70, 75, 72);
You can add more sample data as needed.

🚀 Task 2: SQL Operations
1. Identify Top Students by Total Scores
Calculate and rank students by their total score:

sql 1:
SELECT name, 
       (math_score + science_score + english_score) AS total_score
FROM Students
ORDER BY total_score DESC
LIMIT 5;
2. Calculate Averages Based on Specific Conditions
Average Score of Students Who Scored Above 70 in Math:

sql 2:
SELECT AVG(math_score) AS average_math_score
FROM Students
WHERE math_score > 70;
Average Total Score of Students in a Specific Range (200–250):

sql 2:
SELECT AVG(math_score + science_score + english_score) AS average_total_score
FROM Students
WHERE (math_score + science_score + english_score) BETWEEN 200 AND 250;
3. Find the Second-Highest Math Score
Identify the second-highest math score using a subquery:

sql 3:
SELECT MAX(math_score) AS second_highest_math_score
FROM Students
WHERE math_score < (SELECT MAX(math_score) FROM Students);
