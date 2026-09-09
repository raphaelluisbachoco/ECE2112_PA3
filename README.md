#ECE-2112-PA-3

Created by: Raphael Luis L. Bachoco | 2ECE-D

This repository contains content that pertains to Programming Assignment 3 of ECE 2112: Advanced Computer Programming and Algorithms, SY: 2026-2027


## A. POSITIONAL AND LABEL-BASED SLICING
> After loading cars, complete the following operations.
a. Display the shape and complete list of column names of cars.
b. Using positional slicing, create cars 6 to 10 containing rows 6 through 10 of the dataset, where
the first data row is row 1.
c. From cars 6 to 10, display only the columns Model, mpg, cyl, hp, and gear, in that order.
Requirement: The row selection in part (b) must use iloc; the column selection in part (c) must
use column labels.

```
import pandas as pd
```
To solve all current given problem we first must import the pandas library in which we can shorten the name to pd so when we call future pandas function we can shorten it to `pd`.

```
cars = pd.read_csv('cars.csv')
```
We also need to call the `.csv` file that contains the data we need for Problems A, B and C of which we assign to a variable named `cars`.

```
cars.shape
```
This calls for the shape of the variable cars in (rows, columns).

```
cars_6_to_10 = cars.iloc[6:11]
```
To locate cars 6 to 10 in the `.csv` file. Note that we use 6 to 11 in `iloc` since the index count starts at 6 and ends with 10. 11 is not counted.

```
columns = ['Model', 'mpg', 'cyl', 'hp', 'gear']
cars_6_to_10_columns = cars_6_to_10[columns]
```
To use the display the needed columns in the data set we can use the following to set up a new variable in which we call the cars 6 to 10 but only including the need columns.



Problem A : Positional And Label-Based Slicing Fuction
``` 
import pandas as pd
cars = pd.read_csv('cars.csv')
cars.shape
cars_6_to_10 = cars.iloc[6:11]
columns = ['Model', 'mpg', 'cyl', 'hp', 'gear']
cars_6_to_10_columns = cars_6_to_10[columns]
```

## B. MODEL LOOKUP
>Use Boolean indexing on the Model column to answer both requests.
a. Display the complete row for Toyota Corolla.
b. For Pontiac Firebird, display only Model, mpg, hp, and wt.
Store the two results in toyota and pontiac, respectively. Do not use a hard-coded row number to
locate either model.

```
cars
```
First we call the data set `cars` again

```
toyota = cars.loc[cars['Model'] == 'Toyota Corolla']
```
To search  the car `Toyota Corolla` we can use the funcion `.loc` to display the entire row and its other statistics. We also assign the output to the variable `toyota`.

```
pontiac = cars.loc[cars['Model'] == 'Pontiac Firebird',[ 'Model','mpg', 'hp', 'wt']]
```
For the `Pontiac Firebird` we can also use `.loc` to locate the car however since we are only searching for some of its statistic we must put the restrictions `'Model','mpg', 'hp', 'wt'` to only display certain parts. We assign the output to the variable name `pontiac`.

Problem B : Model Lookup Function
```
cars
toyota = cars.loc[cars['Model'] == 'Toyota Corolla']
pontiac = cars.loc[cars['Model'] == 'Pontiac Firebird',[ 'Model','mpg', 'hp', 'wt']]

```
## C. MULTI-MODEL SUBSETTING
>Create a DataFrame named selected cars containing only the records for three models: Datsun 710,
Lotus Europa, and Ferrari Dino.
For these records, retain only Model, mpg, cyl, hp, and gear. Select the rows by their model values
rather than by row numbers. Display selected cars and its shape.
Required check: The final DataFrame must contain exactly three rows and five columns.

```
cars
```
We again call the original data set `cars` in this problem.

```
before_selected_cars = pd.DataFrame(cars, columns = ['Model', 'mpg', 'cy', 'hp', 'gear'],)
```
For our output to display the only needed statistics records we must first restrict our dataset by creating a data frame with the variable name `before_selected_cars` of which we must use `columns = ['Model', 'mpg', 'cy', 'hp', 'gear']` as our restriction.

```
selected_cars = before_selected_cars.loc[(before_selected_cars['Model'] == 'Datsun 710') | (before_selected_cars['Model'] == 'Lotus Europa') | (before_selected_cars['Model'] == 'Ferrari Dino')]
```
We must first note that we are unable to search the cars via their index values since that is restricted by the original problem. hence we must use a `.loc` function to search the model name of each car in which the given model name must equal that of the given selected car.


Problem C : Multi-Model Subsetting Fuction
```
cars
before_selected_cars = pd.DataFrame(cars, columns = ['Model', 'mpg', 'cy', 'hp', 'gear'],)
selected_cars = before_selected_cars.loc[(before_selected_cars['Model'] == 'Datsun 710') | (before_selected_cars['Model'] == 'Lotus Europa') | (before_selected_cars['Model'] == 'Ferrari Dino')]
```

## History
- September 8, 2026 - Created README.md
- September 9, 2026 - Updated README.md, Uploaded Solutions For PA3 
