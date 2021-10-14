Milestone 1
================
Elizabeth Zambrano
08/10/2021

# Welcome to your (maybe) first-ever data analysis project!

And hopefully the first of many. Let’s get started:

1.  Install the [`datateachr`](https://github.com/UBC-MDS/datateachr)
    package by typing the following into your **R terminal**:

<!-- -->


    ```r
    library(devtools)

    ## Loading required package: usethis

``` r
devtools::install_github("UBC-MDS/datateachr",force=T)
```

    ## Downloading GitHub repo UBC-MDS/datateachr@HEAD

    ## tibble (3.1.4 -> 3.1.5) [CRAN]

    ## Installing 1 packages: tibble

    ## Installing package into 'C:/Users/Hoppmann Lab/Documents/R/win-library/4.1'
    ## (as 'lib' is unspecified)

    ## package 'tibble' successfully unpacked and MD5 sums checked

    ## Warning: cannot remove prior installation of package 'tibble'

    ## Warning in file.copy(savedcopy, lib, recursive = TRUE):
    ## problem copying C:\Users\Hoppmann Lab\Documents\R\win-
    ## library\4.1\00LOCK\tibble\libs\x64\tibble.dll to C:\Users\Hoppmann
    ## Lab\Documents\R\win-library\4.1\tibble\libs\x64\tibble.dll: Permission denied

    ## Warning: restored 'tibble'

    ## 
    ## The downloaded binary packages are in
    ##  C:\Users\Hoppmann Lab\AppData\Local\Temp\RtmpKKf2mv\downloaded_packages
    ##          checking for file 'C:\Users\Hoppmann Lab\AppData\Local\Temp\RtmpKKf2mv\remotes31e0427078c\UBC-MDS-datateachr-78d391f/DESCRIPTION' ...  v  checking for file 'C:\Users\Hoppmann Lab\AppData\Local\Temp\RtmpKKf2mv\remotes31e0427078c\UBC-MDS-datateachr-78d391f/DESCRIPTION' (1.1s)
    ##       -  preparing 'datateachr': (2.2s)
    ##    checking DESCRIPTION meta-information ...     checking DESCRIPTION meta-information ...   v  checking DESCRIPTION meta-information
    ##       -  checking for LF line-endings in source and make files and shell scripts (380ms)
    ##       -  checking for empty or unneeded directories
    ##       -  building 'datateachr_0.2.1.tar.gz'
    ##      
    ## 

    ## Installing package into 'C:/Users/Hoppmann Lab/Documents/R/win-library/4.1'
    ## (as 'lib' is unspecified)

``` r
devtools::install_github("UBC-MDS/datateachr")
```

    ## Skipping install of 'datateachr' from a github remote, the SHA1 (78d391f4) has not changed since last install.
    ##   Use `force = TRUE` to force installation

2.  Load the packages below.

``` r
library(datateachr)
library(tidyverse)
```

    ## -- Attaching packages --------------------------------------- tidyverse 1.3.1 --

    ## v ggplot2 3.3.5     v purrr   0.3.4
    ## v tibble  3.1.4     v dplyr   1.0.7
    ## v tidyr   1.1.3     v stringr 1.4.0
    ## v readr   2.0.2     v forcats 0.5.1

    ## -- Conflicts ------------------------------------------ tidyverse_conflicts() --
    ## x dplyr::filter() masks stats::filter()
    ## x dplyr::lag()    masks stats::lag()

``` r
library(dplyr)
library(ggplot2)
library(ggridges)
```

3.  Make a repository in the <https://github.com/stat545ubc-2021>
    Organization. You will be working with this repository for the
    entire data analysis project. You can either make it public, or make
    it private and add the TA’s and Vincenzo as collaborators.

4.  When you go to submit, submit a URL to your repository to canvas.

# Instructions

More details regarding the instructions and points allocated to each
task can be found below. Briefly,

-   Each milestone is worth 30 points. The number of points allocated to
    each task will be annotated within each deliverable. Tasks that are
    more challenging will often be allocated more points.

-   10 points will be allocated to the reproducibility, cleanliness, and
    coherence of the analysis. While the three milestones will be
    submitted as independent deliverables, the analysis itself is a
    continuum - think of it as 3 chapters to a story. Each chapter, or
    in this case, portion of your analysis, should be easily followed
    through by someone unfamiliar with the content.
    [Here](https://swcarpentry.github.io/r-novice-inflammation/06-best-practices-R/)
    is a good resource for what constitutes “good code”. Learning good
    coding practices early in your career will save you hassle later on!

# Learning Objectives

By the end of this milestone, you should:

-   Become familiar with your dataset of choosing
-   Think of 4 questions that you would like to answer with your data
-   Generate a reproducible and clear report using R Markdown

# Task 1: Choose your favorite dataset (10 points)

The `datateachr` package by Hayley Boyce and Jordan Bourak currently
composed of 7 semi-tidy datasets for educational purposes. Here is a
brief description of each dataset:

-   *apt\_buildings*: Acquired courtesy of The City of Toronto’s Open
    Data Portal. It currently has 3455 rows and 37 columns.

-   *building\_permits*: Acquired courtesy of The City of Vancouver’s
    Open Data Portal. It currently has 20680 rows and 14 columns.

-   *cancer\_sample*: Acquired courtesy of UCI Machine Learning
    Repository. It currently has 569 rows and 32 columns.

-   *flow\_sample*: Acquired courtesy of The Government of Canada’s
    Historical Hydrometric Database. It currently has 218 rows and 7
    columns.

-   *parking\_meters*: Acquired courtesy of The City of Vancouver’s Open
    Data Portal. It currently has 10032 rows and 22 columns.

-   *steam\_games*: Acquired courtesy of Kaggle. It currently has 40833
    rows and 21 columns.

-   *vancouver\_trees*: Acquired courtesy of The City of Vancouver’s
    Open Data Portal. It currently has 146611 rows and 20 columns.

**Things to keep in mind**

-   We hope that this project will serve as practice for carrying our
    your own *independent* data analysis. Remember to comment your code,
    be explicit about what you are doing, and write notes in this
    markdown document when you feel that context is required. As you
    advance in the project, prompts and hints to do this will be
    diminished - it’ll be up to you!

-   Before choosing a dataset, you should always keep in mind **your
    goal**, or in other ways, *what you wish to achieve with this data*.
    This mini data-analysis project focuses on *data wrangling*,
    *tidying*, and *visualization*. In short, it’s a way for you to get
    your feet wet with exploring data on your own.

And that is exactly the first thing that you will do!

1.1 Out of the 7 datasets available in the `datateachr` package, choose
**4** that appeal to you based on their description. Write your choices
below:

**Note**: We encourage you to use the ones in the `datateachr` package,
but if you have a dataset that you’d really like to use, you can include
it here. But, please check with a member of the teaching team to see
whether the dataset is of appropriate complexity. Also, include a
**brief** description of the dataset here to help the teaching team
understand your data.

1: apt\_buildings  
2: building\_permits  
3: parking\_meters  
4: vaouncer\_trees

1.2 One way to narrowing down your selection is to *explore* the
datasets. Use your knowledge of dplyr to find out at least *3*
attributes about each of these datasets (an attribute is something such
as number of rows, variables, class type…). The goal here is to have an
idea of *what the data looks like*.

*Hint:* This is one of those times when you should think about the
cleanliness of your analysis. I added a single code chunk for you, but
do you want to use more than one? Would you like to write more comments
outside of the code chunk?

``` r
### EXPLORE HERE ###
#Data set 1: apt_buildings  
head(apt_buildings) #to look at the data
```

    ## # A tibble: 6 x 37
    ##      id air_conditioning amenities   balconies barrier_free_acc~ bike_parking   
    ##   <dbl> <chr>            <chr>       <chr>     <chr>             <chr>          
    ## 1 10359 NONE             Outdoor re~ YES       YES               0 indoor parki~
    ## 2 10360 NONE             Outdoor po~ YES       NO                0 indoor parki~
    ## 3 10361 NONE             <NA>        YES       NO                Not Available  
    ## 4 10362 NONE             <NA>        YES       YES               Not Available  
    ## 5 10363 NONE             <NA>        NO        NO                12 indoor park~
    ## 6 10364 NONE             <NA>        NO        NO                Not Available  
    ## # ... with 31 more variables: exterior_fire_escape <chr>, fire_alarm <chr>,
    ## #   garbage_chutes <chr>, heating_type <chr>, intercom <chr>,
    ## #   laundry_room <chr>, locker_or_storage_room <chr>, no_of_elevators <dbl>,
    ## #   parking_type <chr>, pets_allowed <chr>, prop_management_company_name <chr>,
    ## #   property_type <chr>, rsn <dbl>, separate_gas_meters <chr>,
    ## #   separate_hydro_meters <chr>, separate_water_meters <chr>,
    ## #   site_address <chr>, sprinkler_system <chr>, visitor_parking <chr>, ...

``` r
class(apt_buildings$amenities) #it's a character, would not be easy to analyze
```

    ## [1] "character"

``` r
colnames(apt_buildings) #to look at the names and number of columns: 37
```

    ##  [1] "id"                               "air_conditioning"                
    ##  [3] "amenities"                        "balconies"                       
    ##  [5] "barrier_free_accessibilty_entr"   "bike_parking"                    
    ##  [7] "exterior_fire_escape"             "fire_alarm"                      
    ##  [9] "garbage_chutes"                   "heating_type"                    
    ## [11] "intercom"                         "laundry_room"                    
    ## [13] "locker_or_storage_room"           "no_of_elevators"                 
    ## [15] "parking_type"                     "pets_allowed"                    
    ## [17] "prop_management_company_name"     "property_type"                   
    ## [19] "rsn"                              "separate_gas_meters"             
    ## [21] "separate_hydro_meters"            "separate_water_meters"           
    ## [23] "site_address"                     "sprinkler_system"                
    ## [25] "visitor_parking"                  "ward"                            
    ## [27] "window_type"                      "year_built"                      
    ## [29] "year_registered"                  "no_of_storeys"                   
    ## [31] "emergency_power"                  "non-smoking_building"            
    ## [33] "no_of_units"                      "no_of_accessible_parking_spaces" 
    ## [35] "facilities_available"             "cooling_room"                    
    ## [37] "no_barrier_free_accessible_units"

``` r
mean(apt_buildings$pets_allowed) #returns NA
```

    ## Warning in mean.default(apt_buildings$pets_allowed): argument is not numeric or
    ## logical: returning NA

    ## [1] NA

``` r
class(apt_buildings$pets_allowed) #so it's characters as well, again not easy to analyze but there are a lot of other variables in this dataset!
```

    ## [1] "character"

``` r
table(apt_buildings$no_of_storeys)
```

    ## 
    ##   0   3   4   5   6   7   8   9  10  11  12  13  14  15  16  17  18  19  20  21 
    ##   3 869 820 166 255 214 101  88  91  84 102  81  76  76  63  56  48  43  36  24 
    ##  22  23  24  25  26  27  28  29  30  31  32  33  34  36  37  41  43  51 
    ##  22  27  26  14   5  11  12  13   9   2   5   3   1   2   2   1   3   1

``` r
table(apt_buildings$year_built)
```

    ## 
    ## 1805 1809 1838 1880 1885 1888 1890 1891 1895 1896 1897 1898 1900 1901 1902 1903 
    ##    1    1    1    1    2    1    1    1    1    1    1    1   13    1    1    1 
    ## 1904 1905 1907 1909 1910 1911 1912 1913 1914 1915 1916 1917 1918 1919 1920 1921 
    ##    1    3    2    1   15    5    3    3    3    6    2    8    8    2   38    2 
    ## 1922 1923 1924 1925 1926 1927 1928 1929 1930 1931 1932 1933 1934 1935 1936 1937 
    ##    3    9    2   13   11   18   19   20   47    9    8    1    7    6    1    9 
    ## 1938 1939 1940 1941 1943 1944 1945 1947 1948 1949 1950 1951 1952 1953 1954 1955 
    ##    8    5   37    8    4    3   13    5    8   16  127   27   63   53   96  149 
    ## 1956 1957 1958 1959 1960 1961 1962 1963 1964 1965 1966 1967 1968 1969 1970 1971 
    ##   73  101  112  103  329   60   99   77   82  170   56  107  114  100  153   75 
    ## 1972 1973 1974 1975 1976 1977 1978 1979 1980 1981 1982 1983 1984 1985 1986 1987 
    ##   61   35   57   37   19   22   19   25   27    7   20   15   13   14   16   13 
    ## 1988 1989 1990 1991 1992 1993 1994 1995 1996 1997 1999 2000 2001 2002 2003 2004 
    ##   11   22   13   14   44   31   21   11   12    4    1    1    2    3    6    2 
    ## 2005 2006 2007 2008 2009 2010 2011 2012 2013 2014 2015 2016 2017 2018 2019 
    ##   10    6    6    9    8    9    5    7    6    4    4    8    6    4    5

``` r
#Data set 2: building_permits 
head(building_permits)
```

    ## # A tibble: 6 x 14
    ##   permit_number issue_date project_value type_of_work  address  project_descrip~
    ##   <chr>         <date>             <dbl> <chr>         <chr>    <chr>           
    ## 1 BP-2016-02248 2017-02-01             0 Salvage and ~ 4378 W ~ <NA>            
    ## 2 BU468090      2017-02-01             0 New Building  1111 RI~ <NA>            
    ## 3 DB-2016-04450 2017-02-01         35000 Addition / A~ 3732 W ~ <NA>            
    ## 4 DB-2017-00131 2017-02-01         15000 Addition / A~ 88 W PE~ <NA>            
    ## 5 DB452250      2017-02-01        181178 New Building  492 E 6~ <NA>            
    ## 6 BP-2016-01458 2017-02-02             0 Salvage and ~ 3332 W ~ <NA>            
    ## # ... with 8 more variables: building_contractor <chr>,
    ## #   building_contractor_address <chr>, applicant <chr>,
    ## #   applicant_address <chr>, property_use <chr>, specific_use_category <chr>,
    ## #   year <dbl>, bi_id <dbl>

``` r
range(building_permits$project_value) #to look at the range of the values, has NAs
```

    ## [1] NA NA

``` r
range(building_permits$project_value, na.rm=T) #look at the ranges without NA
```

    ## [1]         0 807185500

``` r
colnames(building_permits) #there are 14 columns- smaller
```

    ##  [1] "permit_number"               "issue_date"                 
    ##  [3] "project_value"               "type_of_work"               
    ##  [5] "address"                     "project_description"        
    ##  [7] "building_contractor"         "building_contractor_address"
    ##  [9] "applicant"                   "applicant_address"          
    ## [11] "property_use"                "specific_use_category"      
    ## [13] "year"                        "bi_id"

``` r
nrow(building_permits) #look at the number of rows
```

    ## [1] 20680

``` r
#Data set 3: parking_meters    
head(parking_meters) #look at the data, noticed it has $ which might make it harder to analyze
```

    ## # A tibble: 6 x 22
    ##   meter_head  r_mf_9a_6p r_mf_6p_10 r_sa_9a_6p r_sa_6p_10 r_su_9a_6p r_su_6p_10
    ##   <chr>       <chr>      <chr>      <chr>      <chr>      <chr>      <chr>     
    ## 1 Twin        $2.00      $4.00      $2.00      $4.00      $2.00      $4.00     
    ## 2 Pay Station $1.00      $1.00      $1.00      $1.00      $1.00      $1.00     
    ## 3 Twin        $1.00      $1.00      $1.00      $1.00      $1.00      $1.00     
    ## 4 Single      $1.00      $1.00      $1.00      $1.00      $1.00      $1.00     
    ## 5 Twin        $2.00      $1.00      $2.00      $1.00      $2.00      $1.00     
    ## 6 Twin        $2.00      $1.00      $2.00      $1.00      $2.00      $1.00     
    ## # ... with 15 more variables: rate_misc <chr>, time_in_effect <chr>,
    ## #   t_mf_9a_6p <chr>, t_mf_6p_10 <chr>, t_sa_9a_6p <chr>, t_sa_6p_10 <chr>,
    ## #   t_su_9a_6p <chr>, t_su_6p_10 <chr>, time_misc <chr>, credit_card <chr>,
    ## #   pay_phone <chr>, longitude <dbl>, latitude <dbl>, geo_local_area <chr>,
    ## #   meter_id <chr>

``` r
colnames(parking_meters) #22 columns
```

    ##  [1] "meter_head"     "r_mf_9a_6p"     "r_mf_6p_10"     "r_sa_9a_6p"    
    ##  [5] "r_sa_6p_10"     "r_su_9a_6p"     "r_su_6p_10"     "rate_misc"     
    ##  [9] "time_in_effect" "t_mf_9a_6p"     "t_mf_6p_10"     "t_sa_9a_6p"    
    ## [13] "t_sa_6p_10"     "t_su_9a_6p"     "t_su_6p_10"     "time_misc"     
    ## [17] "credit_card"    "pay_phone"      "longitude"      "latitude"      
    ## [21] "geo_local_area" "meter_id"

``` r
nrow(parking_meters) #10032 rows
```

    ## [1] 10032

``` r
parking_meters %>% select(credit_card, pay_phone, longitude, latitude) #to see these values, since I oculdn't see them before
```

    ## # A tibble: 10,032 x 4
    ##    credit_card pay_phone longitude latitude
    ##    <chr>       <chr>         <dbl>    <dbl>
    ##  1 No          66890         -123.     49.3
    ##  2 Yes         59916         -123.     49.3
    ##  3 No          57042         -123.     49.3
    ##  4 No          57159         -123.     49.3
    ##  5 No          51104         -123.     49.3
    ##  6 No          60868         -123.     49.3
    ##  7 No          60810         -123.     49.3
    ##  8 No          60577         -123.     49.3
    ##  9 No          52884         -123.     49.3
    ## 10 No          66822         -123.     49.3
    ## # ... with 10,022 more rows

``` r
class(parking_meters$pay_phone) #to see if it is numeric
```

    ## [1] "character"

``` r
#Data set 4: vancouver_trees  
head(vancouver_trees)
```

    ## # A tibble: 6 x 20
    ##   tree_id civic_number std_street genus_name species_name cultivar_name  
    ##     <dbl>        <dbl> <chr>      <chr>      <chr>        <chr>          
    ## 1  149556          494 W 58TH AV  ULMUS      AMERICANA    BRANDON        
    ## 2  149563          450 W 58TH AV  ZELKOVA    SERRATA      <NA>           
    ## 3  149579         4994 WINDSOR ST STYRAX     JAPONICA     <NA>           
    ## 4  149590          858 E 39TH AV  FRAXINUS   AMERICANA    AUTUMN APPLAUSE
    ## 5  149604         5032 WINDSOR ST ACER       CAMPESTRE    <NA>           
    ## 6  149616          585 W 61ST AV  PYRUS      CALLERYANA   CHANTICLEER    
    ## # ... with 14 more variables: common_name <chr>, assigned <chr>,
    ## #   root_barrier <chr>, plant_area <chr>, on_street_block <dbl>,
    ## #   on_street <chr>, neighbourhood_name <chr>, street_side_name <chr>,
    ## #   height_range_id <dbl>, diameter <dbl>, curb <chr>, date_planted <date>,
    ## #   longitude <dbl>, latitude <dbl>

``` r
colnames(vancouver_trees) #20
```

    ##  [1] "tree_id"            "civic_number"       "std_street"        
    ##  [4] "genus_name"         "species_name"       "cultivar_name"     
    ##  [7] "common_name"        "assigned"           "root_barrier"      
    ## [10] "plant_area"         "on_street_block"    "on_street"         
    ## [13] "neighbourhood_name" "street_side_name"   "height_range_id"   
    ## [16] "diameter"           "curb"               "date_planted"      
    ## [19] "longitude"          "latitude"

``` r
nrow(vancouver_trees) #146611
```

    ## [1] 146611

``` r
vancouver_trees %>% group_by(species_name) %>% summarise(n=n()) #to look at the number of trees per species
```

    ## # A tibble: 283 x 2
    ##    species_name       n
    ##    <chr>          <int>
    ##  1 ABIES            139
    ##  2 ACERIFOLIA   X  1724
    ##  3 ACUMINATA          7
    ##  4 ACUTISSIMA       526
    ##  5 AILANTHIFOLIA      5
    ##  6 ALBA              26
    ##  7 ALBA-SINENSIS      3
    ##  8 ALNIFOLIA        274
    ##  9 ALPINUM            1
    ## 10 ALTISSIMA          4
    ## # ... with 273 more rows

``` r
table(vancouver_trees$neighbourhood_name)
```

    ## 
    ##            ARBUTUS-RIDGE                 DOWNTOWN        DUNBAR-SOUTHLANDS 
    ##                     5169                     5159                     9415 
    ##                 FAIRVIEW       GRANDVIEW-WOODLAND         HASTINGS-SUNRISE 
    ##                     4002                     6703                    10547 
    ## KENSINGTON-CEDAR COTTAGE               KERRISDALE                KILLARNEY 
    ##                    11042                     6936                     6148 
    ##                KITSILANO                  MARPOLE           MOUNT PLEASANT 
    ##                     8115                     6353                     6292 
    ##                 OAKRIDGE      RENFREW-COLLINGWOOD               RILEY PARK 
    ##                     4796                    11386                     6870 
    ##              SHAUGHNESSY             SOUTH CAMBIE               STRATHCONA 
    ##                     7009                     3343                     2724 
    ##                   SUNSET      VICTORIA-FRASERVIEW                 WEST END 
    ##                     8367                     7789                     3507 
    ##          WEST POINT GREY 
    ##                     4939

1.3 Now that you’ve explored the 4 datasets that you were initially most
interested in, let’s narrow it down to 2. What lead you to choose these
2? Briefly explain your choices below, and feel free to include any code
in your explanation.

``` r
#I chose vancouver_trees because think it will be fun to differentiate between the species, genus, and so on. I chose apt_buildings because, even though it lacks many numeric variables, it has a lot of variables to explore. I thought parking_meters had a lot of dollar signs that could make it harder and building_permits has few variables.
```

1.4 Time for the final decision! Going back to the beginning, it’s
important to have an *end goal* in mind. For example, if I had chosen
the `titanic` dataset for my project, I might’ve wanted to explore the
relationship between survival and other variables. Try to think of 1
research question that you would want to answer with each dataset. Note
them down below, and make your final choice based on what seems more
interesting to you!

``` r
#For vancouver_trees: I would like to investigate how many different species a neighborhood has

#For apt_buildings: I would like to explore year built is associated with number of stories. Maybe also look at some of the amenities (laundry room, AC, etc.)
```

# Important note

Read Tasks 2 and 3 *fully* before starting to complete either of them.
Probably also a good point to grab a coffee to get ready for the fun
part!

This project is semi-guided, but meant to be *independent*. For this
reason, you will complete tasks 2 and 3 below (under the **START HERE**
mark) as if you were writing your own exploratory data analysis report,
and this guidance never existed! Feel free to add a brief introduction
section to your project, format the document with markdown syntax as you
deem appropriate, and structure the analysis as you deem appropriate.
Remember, marks will be awarded for completion of the 4 tasks, but 10
points of the whole project are allocated to a reproducible and clean
analysis. If you feel lost, you can find a sample data analysis
[here](https://www.kaggle.com/headsortails/tidy-titarnic) to have a
better idea. However, bear in mind that it is **just an example** and
you will not be required to have that level of complexity in your
project.

# Task 2: Exploring your dataset (15 points)

If we rewind and go back to the learning objectives, you’ll see that by
the end of this deliverable, you should have formulated *4* research
questions about your data that you may want to answer during your
project. However, it may be handy to do some more exploration on your
dataset of choice before creating these questions - by looking at the
data, you may get more ideas. **Before you start this task, read all
instructions carefully until you reach START HERE**.

2.1 Complete *4 out of the following 8 exercises* to dive deeper into
your data. All datasets are different and therefore, not all of these
tasks may make sense for your data - which is why you should only answer
*4*. Use *dplyr* and *ggplot*.

1.  Plot the distribution of a numeric variable.

``` r
dist <- ggplot(apt_buildings, aes(no_of_storeys)) + geom_histogram()
#It makes sense to plot the distribution of the number of storeys just to get an idea of how tall buildings are.
#For the questions after, it makes sense to look at the years they were built:
yb <- ggplot(apt_buildings, aes(year_built)) + geom_histogram()
#Most of them are built after 1950
```

2.  Create a new variable based on other variables in your data (only if
    it makes sense)

``` r
#creating a variable to know the number of years since it has been built, I use the mutate function, creating a variable called "years" which is made up of substracting the year it was built from 2021 (the present year)
apt_buildings <- apt_buildings %>% mutate(years = 2021 - year_built)
#Doing this creates a value for number of years the building has, i.e. it's "age"
```

3.  Investigate how many missing values there are per variable. Can you
    find a way to plot this?
4.  Explore the relationship between 2 variables in a plot.

``` r
#looking at the relationship between buildings' storeys and the year it was built
rel <- ggplot(apt_buildings, aes(year_built, no_of_storeys)) + geom_point()
#they get taller as the years go by :) interesting
```

5.  Filter observations in your data according to your own criteria.
    Think of what you’d like to explore - again, if this was the
    `titanic` dataset, I may want to narrow my search down to passengers
    born in a particular year…

``` r
#Will explore how many buildings are 50 years or more
filt <- filter(apt_buildings, years > 50)
nrow(filt)
```

    ## [1] 2672

``` r
#2672 buildings are 50 years old or more
```

6.  Use a boxplot to look at the frequency of different observations
    within a single variable. You can do this for more than one variable
    if you wish!
7.  Make a new tibble with a subset of your data, with variables and
    observations that you are interested in exploring.
8.  Use a density plot to explore any of your variables (that are
    suitable for this type of plot).

2.2 For each of the 4 exercises that you complete, provide a *brief
explanation* of why you chose that exercise in relation to your data (in
other words, why does it make sense to do that?), and sufficient
comments for a reader to understand your reasoning and code.

``` r
#Added above! Below the lines of code
```

# Task 3: Write your research questions (5 points)

So far, you have chosen a dataset and gotten familiar with it through
exploring the data. Now it’s time to figure out 4 research questions
that you would like to answer with your data! Write the 4 questions and
any additional comments at the end of this deliverable. These questions
are not necessarily set in stone - TAs will review them and give you
feedback; therefore, you may choose to pursue them as they are for the
rest of the project, or make modifications!

\#4 Research questions

``` r
#1.Do newer buildings have more amenities?
#2. What is the average number of years to get registered after the building is built?
#3. Is there a positive relationship between non-smoking buildings and year it was built (i.e. newer buildings do not allow smoking in the building but older ones do?)
#4.Analyze the relationship between number of units and number of storeys
```

### Attribution

Thanks to Icíar Fernández Boyano for mostly putting this together, and
Vincenzo Coia for launching.
