# WT-Analyzer
This is a suite of scripts to analyze data from WahreTabelle.de obtained by [WT-Scrapper](https://github.com/wolkensichel/wt-scrapper).

# Examples
<div style="display: grid;">
<div>![stats_analyzer.py example](pro_contra_stats/KT/WT-Community_pro_contra_stats_(S0910-S1920).png)</div>
<div>![team_histograms.py example](hist/SC%20Freiburg.png)</div>
<div>![team_statistics.py example](pro_contra_stats/Teams/all_1BL_seasons/Entscheidungen%20im%20Teamvergleich.png)</div>
<div>![team_statistics.py example](pro_contra_stats/Teams/1BL_seasons_per_team/Mainz%2005.png)</div>
</div>

## stats_analyzer.py
Adds up all decisions for and against each team, a WT-User voted on, for the chosen time frame (in seasons) and visualizes those results in a horizontal bar graph on a percentage scale with absolute values noted at the tip of each bar. Next to the team name a percentile value provdides information on the likelihood of the result.

Dark colored reference bar graphs, which show the mean voting decision of all users, or a set of users like a neutral Kompetenz-Team, i.e., excluding votes of fans in the Kompetenz-Team, are put behind those user statistics to assess how far off a user voting is compared to the mean result. The mean voting decision can also be computed with fans of a team excluded, as those votes may be biased. For a user results more extreme than 3\varsigma off, indicators show the 3\varsigma mark.

Draw decisions are ignored. For small sample sizes, which do not satisfy the laplace condition, percentiles are approximated using a bionomial distribution. For larger sample sizes a normal distribution is assumed.


## team_histograms.py
The voting results of all users are normalized by the standard deviation of a distribution comprising all user results, given the chosen time frame (in seasons). The histogram depicts the percentage of results in each standard deviation bin, where positive bin numbers are read as a more positive vote on a team and vice versa.

An expected normal distribution with correct magnitude given the mean and the standard deviation are set on top of the histogram as a means to interpret the statistical significance of the voting behavior. The sample size is heading each histogram.


## team_statistics.py
Plot bar graph diagram of overall voting decisions on teams for the chosen time frame (in seasons). Pro, contra and draw results are depicted for each team. Exclusion of non-neutral voters or the Community vote is possible.

The script either plots a diagram comparing teams over the chosen time frame or plots a diagram showing the decisions on one team split by seasons.