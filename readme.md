# Alternative best practices for jupyter
A tentative attempt at jupyter best practices

# Motivation
Many of the guides on "best practice" in jupyter seem amount to telling you to write code like like a software engineer and then use jupyter as an interface.
I've been a software engineer - I like software engineering... and yet, I don't really think software engineering practices are always the best fit for
data analysis.

The key point here is that jupyter notebooks serve a few different roles from software:

## Reproducibility

You did some analysis can other people understand what assumptions were baked in how it was wrong. This can get broken be the refactoring that can be necessary for reproducibility.
But even if nothing changes you can still miss out on the chain of reasoning that lead one to an approach.

## Discoverability
How quickly can a user add material to sheet or discover what is going on.

## Narrativity
Can a user tell what was going on when the analysis happened and what motivated. This feature is often missing from code
(although a skilled programmer is often quite good at infering it from the code structure)

## Data display
One of the points of notebooks is to present data 

# Forces at play
* Discoverability
* Reproducibility
* Understandability

# The problems
* Slow analysis
* Large sheets that you can get lost in 
* Building up "out of order" execution that make things
* "Execution" looks a jupyter tab.

# Some third party tools
* [papermill](https://papermill.io/)
* [ipyflow](https://github.com/ipyflow/ipyflow) - still a little young at time or writing - Allows partial recalculation of a sheet in the style of a spreadsheet

# Some structuring tools
A complete "best practice" will tell you what to do then. But before best practices exist (and maybe in any complex domain) rather than best practices you have something 
resembling a "toolkit" of possible interventions and the forces that could cause you to use them. These ideas have been fleshed out (then somewhat ignored) in design patterns. 

## Regular full recalc
Advantages: Early issue detectin
Disadvantages: Slow

## Single big conditions
Advantages: +Discoverability, +Efficiency
Breaking conditions: Slow execution
As the sheet becomes bit it can bexome slow

## Splitting sheets
Forces: Large sheets and getting lost
Costs: Data need to be manually shared between sheets (-efficiency)
Advantages: Quite easily understood (+discoverability)

## Table of contents

Forces: Difficult finding parts of code while editing things at the same time
Best practice: Tables of contents can crash if you are displaying cell results

## Use papermill to "execute" a sheet written for narrative

## Use papermill for all "slow" runs 
Effects: Pushing you into a "multisheet environment" because when you wa

Paper mill provides a tool to "reuse sheets". You don't seem to be able get at the context after execution. However - you can have your papermill file 
write output that should be reused to a file. 

## Use makefiles or similar to orchestrate execution
This could be done through papermill, and could potentially be done from a top notebook.

## Organizaiing subfoldrs
* Using markdown to link to child folders from a parent
* Using a folder structure to make things more discoverable

## Nuclear option: Switching to make files
Switch to make files and command line execution. Though you should be aware that there is some measure of "impedance mismatch" in doing this. `papermill` and `import_ipynb` might help this.



