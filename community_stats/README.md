# Community stats

Here is some of the data we aggregated for use on the site. Keep in mind that this doesn't have all of the players, just the ones that we were keeping track of (biased towards higher ranked / skilled players) and it won't match the data that Ubisoft releases.

## community_ranks.csv

This is a dump of the table on which the graph on top of the leaderboards was based with the following columns.

-   platform
-   region
-   rank - rank 0 - 20, 0 being unranked, 1 is copper IV, ..., 20 - diamond
-   amount - amount of people in this rank
-   relevant_at - the day at which this row was aggregated

## community_skill.csv

This is similar to **community_ranks.csv** but instead of rank, it's the skill of players (MMR / 100 in season 2 and onwards) rounded downwards (floored), so if a person's MMR is 4751, then the skill_range column will be 47

-   platform
-   region
-   skill_range - Math.floor(MMR / 100)
-   amount - amount of people with this skill_range
-   relevant_at - the day at which this row was aggregated

## communityoperators2018.json

Part of a planned feature to display operator KD / WL / Pickrate / Time played. This is grouped by platform and isn't sampled. We haven't validated how useful this information is.

In each entry of the JSON array there's a property called stats, keys of which are one of

-   [operator name]\_kd - average KD of this operator ((todays total kills - yesterdays total kills) / (todays total deaths - yesterdays total deaths))
-   [operator name]\_wl - average WL of this operator ((todays total wins - yesterdays total wins) / (todays total losses - yesterdays total losses))
-   [operator name]\_total_time_played - sum of time played with these operators for all players compared to yesterday
-   [operator name]\_total_rounds_played - sum of rounds played with these operators for all players compared to yesterday (useful to find pickrates I guess)

## communityoperators2017.json

Previous effort to add community operator stats to the site. The aggregation was too costly for the hardware at the time so we dropped it.

This data was also sampled, samples were full and diamond (diamond meaning data was only aggregated for players who were in diamond rank at in at least one of the regions at the time of the aggregation, full had the whole playerbase in the DB).

The data that was aggregated wasn't very thought through and does seem odd now. If I remember correctly I only took data for each operator from people who had played it the previous 24 hours. Take this data with near-lethal doses of salt.

-   [operator_name]\_deaths - sum of total number of deaths with this operator
-   [operator_name]\_deaths_delta - average change of deaths compared to the previous day
-   [operator_name]\_kills - sum of total number of kills with this operator
-   [operator_name]\_kills_delta - average change of kills compared to the previous day
-   [operator_name]\_lost - sum of total number of rounds lost with this operator
-   [operator_name]\_lost_delta - average change of losses compared to the previous day
-   [operator_name]\_time_played - sum of time played with this operator (seconds)
-   [operator_name]\_time_played_delta - average change of time played (seconds) compared to the previous day
-   [operator_name]\_won - sum of total won rounds with this operator
-   [operator_name]\_won_delta - average change of rounds won compared to the previous day
