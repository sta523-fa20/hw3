# STA 523 :: Homework 3

## Introduction

>**Restaurant Scores**
<br/><br/>
The Health Department has developed an inspection report and scoring system.
After conducting an inspection of the facility, the Health Inspector calculates
a score based on the violations observed. Violations can fall into - high risk
category: records specific violations that directly relate to the transmission
of food borne illnesses, the adulteration of food products and the contamination
of food-contact surfaces; moderate risk category: records specific violations
that are of a moderate risk to the public health and safety; low risk category:
records violations that are low risk or have no immediate risk to the public
health and safety. The score card that will be issued by the inspector is
maintained at the food establishment and is available to the public in this
dataset.
<br/><br/>
*Source*: [DataSF](https://data.sfgov.org/Health-and-Social-Services/Restaurant-Scores-LIVES-Standard/pyih-qa8i)

## Tasks


### Part I

The following questions/tasks will require you to manipulate and summarize the
data provided by the health department of San Francisco. Most of the variables
are self-explanatory; however, if you need more
information, visit [DataSF - Restaurant Scores](https://data.sfgov.org/Health-and-Social-Services/Restaurant-Scores-LIVES-Standard/pyih-qa8i).

Your code to manipulate and summarize the data frame should consist of
`dplyr`, `purrr`, and `janitor` functions. Code output should only contain
the necessary rows and variables from the data frame to answer the question or
complete the task.

To get started, load the CSV file of restaurant scores.

```r
res_scores <- read_csv("data/restaurant_scores.csv")
```

#### Task 1

Fix the variable names so they have a uniform syntax format. Save this output
as `res_scores`. Output the result of `glimpse(res_scores)` to show the
new variable names.

#### Task 2

How many `NA` values exist for each variable?

#### Task 3

Drop the variable `business_location` and the variables `neighborhoods_old`
through `analysis_neighborhoods`. Save this output as `res_scores`. Output the
result of `glimpse(res_scores)` to show the reduced variable set.

#### Task 4

What was the most common known reason for a violation? Your output should only
consist of the violation and its count in a tibble.

#### Task 5

Among those violations deemed "High Risk", what were the top seven known
violations in terms of frequency? Your output should only consist of the
violations and their counts in a tibble.

#### Task 6

What proportion of violations deemed "Moderate Risk" were due to
"Noncompliance with Gulf Coast oyster regulation"? Your output should be an
atomic double vector.

#### Task 7

Summarize the data to show which type of inspection receives an
inspection score.

#### Task 8

What is the median star rating of Peet's Coffee & Tea by postal code based on
each store's most recent inspection score? Your output should only consist of
the postal codes and median inspection scores in a tibble.

#### Task 9

What is the average score for all restaurants at all times within a radius of
[0, 0.25] miles, (0.25, 0.50] miles, and (0.50, 1.0] miles from 21 Taste House
on 1109 Ocean Ave. Your output should be an atomic double vector.

### Part II

Going forward you will work with a subset of the restaurant score data but
starting in JSON format.

To get started, load the `jsonlite` package and read in
`restaurant_scores.json`.

```r
library(jsonlite)
dine <- read_json("data/restaurant_scores.json")
```

Your code to manipulate and summarize the resulting list object should
consist of `dplyr`, `purrr`, and `tidyr` functions.

#### Task 10

How many unique business id values exist in `dine`?

#### Task 11

Create a data frame for the restaurants with variables that consist of the
`business features` - `name`, `address`, `postal_code`, `latitude`, `longitude`.
Be sure to not have duplicate rows.

#### Task 12

Convert `dine` to a tidy tibble. Tidy in this case means in the same format as
`res_scores` from Part I. As a reminder, `dine` is a subset of `res_scores` in
both observations and variables.

## Essential details

### Deadline and submission

**The deadline to submit Homework 3 is Wednesday, September 16 at 11:59pm EST.**
Only your final commit and code in the master branch will be graded.
To submit, push your work to your assigned team repository on GitHub before
the deadline.

### Help

- Post your questions in the #hw3 channel on Slack. Explain your error / problem
  in as much detail as possible or give a reproducible example that generates
  the same error. Make use of the code snippet option available in Slack. You
  may also send a direct message to the instructor or TAs.

- Visit the instructor or TAs in Zoom office hours.

- The instructor and TAs will not answer any questions about this assignment
 	within six hours of the deadline.

### Academic integrity

This is a team assignment. You may **not** communicate with other teams in the
course. As a reminder, any code you use directly or as inspiration must be
cited.

To uphold the Duke Community Standard:

- I will not lie, cheat, or steal in my academic endeavors;
- I will conduct myself honorably in all my endeavors; and
- I will act if the Standard is compromised.

Duke University is a community dedicated to scholarship, leadership, and
service and to the principles of honesty, fairness, respect, and accountability.
Citizens of this community commit to reflect upon and uphold these principles in
all academic and non-academic endeavors, and to protect and promote a culture of
integrity. Cheating on exams and quizzes, plagiarism on homework assignments and
projects, lying about an illness or absence and other forms of academic
dishonesty are a breach of trust with classmates and faculty, violate the Duke
Community Standard, and will not be tolerated. Such incidences will result in a
0 grade for all parties involved as well as being reported to the University
Judicial Board. Additionally, there may be penalties to your final class grade.
Please review Duke’s Standards of Conduct.

### Grading

| **Topic**                                        | **Points** |
|--------------------------------------------------|-----------:|
| Task 1                                           |        0.5 |
| Task 2                                           |          1 |
| Task 3                                           |        0.5 |
| Task 4                                           |          1 |
| Task 5                                           |          2 |
| Task 6                                           |          2 |
| Task 7                                           |          2 |
| Task 8                                           |          4 |
| Task 9                                           |          4 |
| Task 10                                          |          1 |
| Task 11                                          |          4 |
| Task 12                                          |          4 |
| Code style and format                            |          3 |
| Named R code chunks                              |          1 |
| **Total**                                        |     **30** |

*Documents that fail to knit after minimal intervention will receive a 0*.

## References

1. DataSF (2020). https://data.sfgov.org/Health-and-Social-Services/Restaurant-Scores-LIVES-Standard/pyih-qa8i
