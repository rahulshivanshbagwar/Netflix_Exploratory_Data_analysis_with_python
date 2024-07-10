# Netflix Exploratory Data Analysis


## Problem Statement

 What started in 1997 as a DVD rental service has since exploded into one of the largest entertainment and media companies.

Given the large number of movies and series available on the platform, it is essential to know about the trends of the movies over the years to understand how the industy has grown.

The motive of the project is to do some research on movies released in the 1990's. We'll delve into Netflix data and perform exploratory data analysis to better understand this awesome movie decade!

We have the dataset netflix_data.csv, along with the following table detailing the column names and descriptions.

We have the dataset `netflix_data.csv`, along with the following table detailing the column names and descriptions. 
## The data
### **netflix_data.csv**
| Column | Description |
|--------|-------------|
| `show_id` | The ID of the show |
| `type` | Type of show |
| `title` | Title of the show |
| `director` | Director of the show |
| `cast` | Cast of the show |
| `country` | Country of origin |
| `date_added` | Date added to Netflix |
| `release_year` | Year of Netflix release |
| `duration` | Duration of the show in minutes |
| `description` | Description of the show |
| `genre` | Show genre |

### Steps followed 
#### First part of the Project is to determine the most frequent duration of movies during the 1990's period using visualization.
- Step 1 : Import pandas and matplotlib

          import pandas as pd
          import matplotlib.pyplot as plt
- Step 2 : Read in the Netflix CSV as a DataFrame.

        netflix_df = pd.read_csv("netflix_data.csv")
- Step 3 : Subset Data in the time period between 1990 and 1999.

        time_period_movies = netflix_df[(netflix_df['release_year'] >= 1990) & (netflix_df['release_year'] <= 1999)]
        time_period_movies
- Step 4 : Visualizing the most frequent movie durationusing histogram and using the correct xlabels and ylabels for better understanding and the appropriate title for the histogram .

        duration_values= time_period_movies['duration']
        plt.hist(duration_values,bins=10)
        plt.xlabel('duration')
        plt.ylabel('No of movies')
        plt.title('Duration of Movies between 1990 and 1999')
        plt.show()
![download](https://github.com/rahulshivanshbagwar/Netflix_Exploratory_Data_analysis_with_python/assets/173008519/b8b470d8-cf34-4663-af4e-84d27789ec7e))
- Step 5 : Store the Most frequent movie duration in the 1990s as the variable 'duration'. 

        duration=110
#### Second part of the project is to find the number of short action movies which are shorter than 90 minutes.
- Step 6 :Subset the the movies of action genre.

        action_movies=time_period_movies[time_period_movies['genre']== 'Action']
        action_movies
- Step 7 : Create a variable called 'short movie count' .

        short_movie_count=0
- Step 8 :Create a loop for counting the short movies and print the result.

        action_genre=action_movies['duration']
        for short in action_genre:
        if short<=90:
        short_movie_count=short_movie_count+1

        print(short_movie_count)

