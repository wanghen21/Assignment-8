# Assignment-8
Movies-ETL
Extract, Transform & Load

Using ETL to clean data files, parse the data that we extracted to make it look how we want. Merge parsed data sets and load the merged sets into pgadmin for further use.

Step 1:
-- Using the ETL_function_test file by step:

Created a function to read in three seperate files
Read in the Kaggle metadata and MovieLens ratings CSV files as Pandas DataFrames.
Opened the Wikipedia JSON file and use the json.load() function to convert the JSON data to raw data.
read in the raw Wikipedia movie data as a Pandas DataFrame.
use the code provided to return the three DataFrames.
use the variables provided to create a path to the Wikipedia data, the Kaggle metadata, and the MovieLens rating data files.
set the three variables in Step 6 equal to the function created in Step 1.
set the DataFrames from the return statement equal to the file names in Step 6. In this step, you are reassigning the variables created in Step 6 to the variables in the return statement.
Now to view that all our dataframes are correct use the .head() method to make sure your dataframes look correct(example below):

![Kaggle metadata capture](https://user-images.githubusercontent.com/80020446/128205968-71d50ccc-778f-4a77-8125-9858fe56aedf.PNG)


Step 2:
-- Extract and Transform the Wikipedia Data with the ETL_clean_wiki_movies.ipynb:

Create the code for the clean movie function that takes in the argument "movie".
Add the function you created in step 1 that reads in the three data files.
Inside the function you created in step 1's python file, remove the code that creates the wiki_movies_df DataFrame from the wiki_movies_raw file, then write a list comprehension that filters out TV shows from the wiki_movies_raw file.
Write a list comprehension to iterate through the cleaned wiki movies list that you created in Step 3.
Read in the cleaned movies list from Step 4 as a DataFrame.
Write a try-except block that will catch errors while extracting the IMDb IDs with a regular expression string and dropping any imdb_id duplicates. If there is an error, capture and print the exception.
Write a list comprehension to keep the columns that have non-null values from the DataFrame created in Step 5, then create a wiki_movies_df DataFrame from the list.
Create a variable that will hold all the non-null values from the "Box office" column.
Convert the box office data created in Step 8 to string values using the lambda and join functions.
Write a regular expression to match the six elements of form_one of the box office data.
Write a regular expression to match the three elements of form_two of the box office data.
Add the parse_dollars() function.
Add the code that cleans the box office column in the wiki_movies_df DataFrame using the form_one and form_two lists created in Steps 10 and 11, respectively.
Add code that cleans the budget column in the wiki_movies_df DataFrame.
Add code that cleans the release date column in the wiki_movies_df DataFrame.
Add code that cleans the running time column in the wiki_movies_df DataFrame.
Use the variables provided to create a path to the Wikipedia data, the Kaggle metadata, and the MovieLens rating data files.
Set the three variables in Step 17 equal to the function created in Deliverable 1.
Set the wiki_movies_df equal to the wiki_file variable.
Add the columns from wiki_movies_df DataFrame to a list, and confirm that they are the same as this image:
![Wiki movies capture](https://user-images.githubusercontent.com/80020446/128206006-18edb694-3061-42d5-990b-2ea8e752217a.PNG)


Step 3:
-- Extract and Transform the Kaggle Data using the ETL_clean_kaggle_data.ipynb

Add the function was created in our very first python file that reads in the three data files and creates the kaggle_metadata and ratings DataFrames. Also, make sure you add in all of the code from the ETL_clean_wiki_movies.ipynb file
below the code that cleans the running time column in the wiki_movies_df DataFrame from ETL_clean_wiki_movies.ipynb, add the code that cleans the Kaggle metadata.
Merge the wiki_movies_df DataFrame and the kaggle_metadata DataFrames, then name the new DataFrame, movies_df.
Drop unnecessary columns from the movies_df DataFrame.
Add the fill_missing_kaggle_data() function that fills in the missing Kaggle data on the movies_df DataFrame.
Call the fill_missing_kaggle_data() function with the movies_df DataFrame and the Kaggle and Wikipedia columns to be cleaned as the arguments.
Filter the movies_df DataFrame to keep the necessary columns.
Rename the columns in the movies_df DataFrame.
Transform and merge the ratings DataFrame with the movies_df DataFrame, name the new DataFrame movies_with_ratings_df, then clean the movies_with_ratings_df DataFrame.
Use the variables provided to create a path to the Wikipedia data, the Kaggle metadata, and the MovieLens rating data files.
Set the three variables from Step 17 of ETL_clean_wiki_movies.ipynb equal to the function created in the first python file we created.
Set the DataFrames from the return statement after Step 9 equal to the file names in Step 11.
Check that your wiki_movies_df DataFrame is the same as in ETL_clean_wiki_movies.ipynb.
Confirm that your DataFrames look correct using the .head() method
Finally, make sure you have a config file setup to connect with your postgres database. Confirm that the movies table has 6,052 rows and the ratings table has 26,024,289 rows![Kaggle metadata capture](https://user-images.githubusercontent.com/80020446/128205909-fbc381c8-a0b5-409e-a4f2-e4deaf186947.PNG)
