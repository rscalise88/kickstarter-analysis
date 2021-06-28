# Kickstarting with Excel
## Overview of Project
An analysis of the available data for all Kickstarter projects from 2009-2017.

### Purpose
This analysis specifically reviews the success rate of theater projects proposed on the kickstarter platform to determine if success is directly correlated to the launch date or the funding goals of these projects.

## Analysis and Challenges
Using Excel, we review the raw data for all theater projects using data filtering, functions, pivto tables, and graphs.

### Analysis of Outcomes Based on Launch Date
From the full data set, we filter out only projects in the theater category, combining this data for all years.  The outcome of each project is reviewed then on a month-by-month basis to determine, for each month, if there is a direct relationship between successful, failed, and canceled projects.  The data contain a small number of projects that were live at the time of data retrieval - this data has been exlucded from the analysis.
[https://github.com/rscalise88/kickstarter-analysis/resources/theater_outcomes_vs_launch.png]

### Analysis of Outcomes Based on Goals
For all theater projects, the goals of the project were first divided into tiers. Starting at any projects requested less than $1,000 in funding, next any that requested up to $4,999, then increasing each category by $5,000 until the final tier, which contains all projects seeking more than $50,000 in funding.  Within each tier, the number of successful, failed, and canceled projects were calculated from the raw data using a COUNTIFS function within Excel.

For example:
=COUNTIFS(Kickstarter!$D:$D, "<1000", Kickstarter!$F:$F, "successful", Kickstarter!$R:$R, "plays")

The total of all project outcomes are summed for each tier level, then divided by each the number of successes, failures, and cancellations in order to determine the percentage of total projects that each outcome represents for that goal tier.  This data is then plotted linearly, comparing each goal tier to its eventual outcome.
[https://github.com/rscalise88/kickstarter-analysis/resources/outcomes_vs_goals.png]

### Challenges and Difficulties Encountered
Due to the narrow scope of the data available, it's difficult to draw a concrete conclusion on all of the factors that might lead to a project's success or failure.  This is discussed in greater detail below.

## Results
The data suggest that projects find greater success in the month of May, decreasing linearly as the year progresses.  In addition to this, more projects appear to be created in May year over year, again decreasing as the months progress.  With this in mind, the number of failed projects stays relatively constant throughout the year.

Generally speaking, as the goal set by the campaign increases, the chance of success drops.  More projects found success in the $35000-$45000 goal range, however the overall trend suggests that success is linearly related to the financial ambitions of the project.

Though the data appear to imply a correlation between the success of a campaign and its start date and goals, the data available for this analysis in limited.  We do not know individual factors that may have contributed to the eventual outcome of each project.  A large driver of success could be attributed to the reach of each project, how aggressively they were advertised, as well as how professionally the campaign pages presented their pitch to potential donors.  Also absent is data on individual donation levels.  Interested parties with a significant amount of money could theoretically make or break a campaign.  

With these points in mind, using the data available it would also be worthwhile to investigate how the average donation compares to the success of projects. Alternatively, given that we know whether or not Kickstarter themselves promoted the project on their front page, there is merit in determining if there is a correlation between the added publicity and rate of success for these projects.
