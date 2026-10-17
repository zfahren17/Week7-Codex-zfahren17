# AI Workflow Log

## 1. AmesHousing.csv cleanup

- **Recorded:** 2026-10-14 07:13:45 PM CDT 
- **Prompt:** “can you clean up AmesHousing.csv especially in regards to WoodDeckSF and SalePrice”
- **What I produced:** Audited the data, found trailing spaces in 2,536 `Sale Type` values, and later removed those spaces. Confirmed the two requested numeric fields contained no blanks or nonnumeric entries and retained their values.
- **What I accepted:** Accepted cleaned data set.
- **What I modified:** NA
- **What I rejected:** NA.
- **Rationale for my decisions:** Cleaning data step addressed all visible issues from what I saw in the data.

## 2. Initial deck and sale price summary

- **Recorded:** 2026-10-14 7:18:22 PM CDT 
- **Prompt:** “I want to analyze the impact having a wood deck has on SalePrice. Can you produce a summary table of both variables.”
- **What I produced:** Compared homes with and without decks: 1,526 had no deck and 1,404 had a deck; mean sale prices were $156,565 and $207,132, respectively. Noted that the unadjusted difference was associative, not causal.
- **What I accepted:** Table format and measures
- **What I modified:** Wanted to control for basic variables
- **What I rejected:** Rejected this as my final table
- **Rationale for my decisions:** Gaps in SalePrice were quite large so I wanted to control for some variables.

## 3. Control for neighborhood and home size

- **Recorded:** 2026-10-14 7:21:29 PM CDT 
- **Prompt:** “can you control this analysis on the similar sized homes in particular neighborhoods”
- **What I produced:** A one-to-one matched comparison within neighborhoods, using homes within 10% in above-ground living area. Reported 918 pairs across 23 neighborhoods and a mean paired price difference of +$6,817.
- **What I accepted:** Accepted pairing method.
- **What I modified:** Expanded the analysis to control for neighborhood and similar home size.
- **What I rejected:** Rejected this as the final table, still had more variables to consider.
- **Rationale for my decisions:** This controlling of variables allows for a little more insight to be extracted from my analysis

## 4. Add year built to the comparison

- **Recorded:** 2026-10-14 7:24:52 PM CDT
- **Prompt:** “can you incorporate year built into the comparison as well”
- **What I produced:** Re-matched homes within neighborhood, within 10% in living area and 5 years in year built. Reported 776 pairs and a mean paired price difference of +$4,867.
- **What I accepted:** Accepted this as a valid comparison tool
- **What I modified:** Added year built as a matching criterion.
- **What I rejected:** NA
- **Rationale for my decisions:** Felt like my logic was still missing an important variable to control for in regards to the build year.

## 5. Create output table and explain matching logic

- **Recorded:** 2026-10-14 7:26:50 PM CDT (recorded retrospectively; original prompt time unavailable)
- **Prompt:** “can you create an output table with this latest controlled version with a brief explanation of the logic in the analysis”
- **What I produced:** Created a matched summary CSV with overall and neighborhood rows, including pair counts and price differences; explained the matching criteria.
- **What I accepted:** Accepted partial elements for final table output.
- **What I modified:** I wanted to set a limit for neighborhoods with very few pairs and add an additional calculated field.
- **What I rejected:** Rejected this as final output.
- **Rationale for my decisions:** This table seemed with its neighborhood breakdown and summary statistics seemed sufficient for my investigation.

## 6. Filter and revise the output table

- **Recorded:** 2026-10-14 8:32:14 PM CDT
- **Prompt:** “Can you cut off the table to only include neighborhoods with 25 or more pairs. Also remove mean area difference and mean year difference and add a column that calculates the percentage of homes where the deck home was sold at a higher price. Please place the corresponding output in the \\analysis folder”
- **What I produced:** Created a CSV in `analysis` with the 12 neighborhoods having at least 25 matched pairs, omitted the overall row and area/year diagnostics, and added the percentage of matched deck homes sold for more.
- **What I accepted:** Accepted this table as final output
- **What I modified:** I requested the pair-count filter, removal of two columns, addition of the higher-price percentage, and placement in `analysis`.
- **What I rejected:** NA
- **Rationale for my decisions:** Some of the neighborhoods had very few pairs to make a fair comparison in so I filtered those out.  I also want to add the measured field on % of homes sold at a higher price in the pairs. The math was there already, just want it to be explicitly shown.


## 7. Boxplot for the neighborhood with the highest difference

- **Recorded:** 2026-10-17 12:07:03 PM CDT (recorded retrospectively; original prompt time unavailable)
- **Prompt:** “can you create a boxplot for neighborhood with the highest difference in sales price”
- **What I produced:** Created a boxplot comparing matched deck and no-deck sale prices in Somerst, the neighborhood with the largest positive mean paired difference among those with at least 25 pairs.
- **What I accepted:** Accepted boxplot style and general format.
- **What I modified:** NA
- **What I rejected:** Rejected this as final visual.
- **Rationale for my decisions:** Boxplot was helpful but I wanted a bit more information on how the top 3 neighborhoods (in mean SalePrice difference) stack up with each other.

## 8. Expand boxplot to the top three neighborhoods

- **Recorded:** 2026-10-17 12:13:37 PM CDT (recorded retrospectively; original prompt time unavailable)
- **Prompt:** “Can you modify the boxplot to include the top 3 neighborhoods where it appears having a deck alters the sell price and then have them grouped by neighborhood. I am envision 6 boxplots and whiskers with this.”
- **What I produced:** Updated the chart with six boxplots grouped by neighborhood for Somerst, SawyerW, and Sawyer, selected by absolute mean paired price difference among neighborhoods with at least 25 pairs.
- **What I accepted:** Accepted this as final visual.
- **What I modified:** Requested expanding the chart to three neighborhoods and grouping deck/no-deck boxplots by neighborhood.
- **What I rejected:** NA
- **Rationale for my decisions:** Kept the same general format as my first attempt, just added in SawyerW and Sawyer as the #2 and #3 neighborhoods respectively to give a better picture.



