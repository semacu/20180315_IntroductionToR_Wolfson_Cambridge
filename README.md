
## Introduction to R

<img align="right" src=images/R_logo.png width="150">

- Date: 15th March 2018, 6 - 7pm
- Series: Wolfson College [Skills for Academic Success](https://www.wolfson.cam.ac.uk/study-skills)
- Location: [Roger Needham Room](http://www.wolfson.cam.ac.uk/tour/chancellorscentre), [Wolfson college](https://goo.gl/maps/aR6a5FWrLoR2), University of Cambridge, UK
- Trainer: Sergio Martínez Cuesta
- Register [here](https://www.eventbrite.co.uk/e/skills-for-academic-success-introduction-to-r-tickets-41949950431)


### Overview

This course provides a short beginners introduction to the R programming language and software environment for statistical computing and graphics. Sergio will demonstrate basic examples on how to input, explore, plot and output data in R. Everybody is welcome, if you would like to follow along with your laptop, please bring R and RStudio [downloaded and installed](https://www.rstudio.com/products/rstudio/download/) before the session.



### Outline

- Motivation
- Installing R and RStudio
- How can I find help?
- Getting started
- Variables and functions
    - Exercise 1
- Vectors
- Import and explore data
    - Subsetting
    - Exercise 2
- Sort tables and export results
- Basic plotting
    - Export graphics
    - Exercise 3

This short course is based on the [R crash course](https://github.com/bioinformatics-core-shared-training/r-crash-course) developed by [Mark Dunning](https://github.com/markdunning) and [Laurent Gatto](https://github.com/lgatto).



### Motivation

- R is one of the most widely-used programming languages for data analysis, statistics and visualisation in academia and industry.
- It is open-source and available in all platforms (Mac, Linux and Windows)
- Supported by a broad community of software developers and researchers who contribute R packages and libraries to many fields of research 
- It facilitates reproducibility in research and integration of all your analyses in individual scripts
- Easy to write documentation and code together using a free environment like [RStudio](https://www.rstudio.com/)

E.g. The New Zealand [Tourism Dashboard](https://mbienz.shinyapps.io/tourism_dashboard_prod/) uses R extensively to report statistics.



### Installing R and RStudio

- [Latest version of R](https://cran.r-project.org/)
    - To check if you have R installed in Mac, go to `Finder` -> `Applications` -> `Utilities` -> `Terminal`, type `R` and press Enter. If you see information about the R version and other details appearing followed by a ">" prompt, then you have R installed.
- [RStudio Desktop Open Source License](https://www.rstudio.com/products/rstudio/download/)
    - To check if you have RStudio installed in Mac, try opening it, go to `Finder` -> `Applications` and click on `Rstudio` 



### How can I find help?

- [Stack Overflow](https://stackoverflow.com/)
- The Comprehensive R Archive Network ([CRAN](https://cran.r-project.org/))
- [CRAN Task Views](https://cran.r-project.org/web/views/)
- [R-bloggers](https://www.r-bloggers.com/)
- [Quick-R](https://www.statmethods.net/)
- Local R groups, e.g. [R-ladies Cambridge](https://www.meetup.com/rladies-cambridge/)
- Type `?` followed my the name of the function that you'd like to use, e.g. `?mean`

If you are interested in bioinformatics and computational biology, the following links might also be of interest:

- [Bioconductor](https://www.bioconductor.org/)
- [Biostars](https://www.biostars.org/)



### Getting started

- Open RStudio - see above. Explore the different panels

To download today's workshop:

- Go to your web browser and type: https://tinyurl.com/2018-IntroR-Wolfson
- Click on `IntroR.zip`, then press `Download` and save the file in your preferred folder, e.g. your Desktop
- Go to the folder where you saved `IntroR.zip` and uncompress it, e.g. in Mac just double-click on `IntroR.zip`. Only then, the folder `IntroR` will appear.
- The folder `IntroR` contains two files:
    - `IntroR.Rmd` - the code for today's session
    - `patient-data-cleaned.csv` - the dataset that we will be exploring

Now, go back to RStudio:

- Click on `File` -> `Open File` and select `IntroR.Rmd`
- You are all set to go now :)

Also:

- We will be using RStudio console (bottom-left panel) to interact with R during the workshop
- The blocks of code shown in `IntroR.Rmd` - see below - are written using the format **R markdown**, which allows mixed plain text and R code together within the same [document](https://rmarkdown.rstudio.com/)
- Each line of R code inside a block can be executed by clicking on the line and pressing CMD + ENTER (Mac) or CTRL + ENTER (Windows and Linux), e.g.:

```{r eval=FALSE}
print("R is fun!")
```

Alternatively, to execute the entire block, click on the green arrow tip on the right-hand side of the block.

```{r eval=FALSE}
3 + 1
```

- You can add a new block of code by selecting `R` in the `Insert` menu or by typing the following syntax directly:

```{r}
# R code goes in here
```



### Variables and functions

You can use R as a calculator using the symbols `+`, `-`, `*` and `/`, or more advanced features such as statistical operations, logarithms, trigonometry ...

```{r eval=FALSE}
2 + 1
7 - 1
3 * 2
10 / 5

mean(1:5)
log(1)
pi
sin(pi/2)
```

To store your results for later, use **variables**. To create them, use the assignment operator `<-`:

```{r eval=FALSE}
x <- 25
x
y <- 16
y
```

You can perform multiple operations using variables:

```{r eval=FALSE}
sqrt(x)
x + y
x <- 36
x <- y
x <- x + 8
```

**Functions** in R take one or more *arguments* as input, which are captured using parentheses. Arguments can be named explicitly, otherwise they are meant to be used in the same order as described in the function definition. E.g. `seq` is a function for generating a numeric sequence *from* and *to* particular numbers. Type `?seq` to get the help page for this function.

```{r eval=FALSE}
?seq
seq(from = 1, to = 10, by = 2)
seq(1, 10, 2)
```

Some functions have *default* values in some arguments:

```{r eval=FALSE}
seq(1, 10, 1)
seq(1, 10)
```

The default value for the `by` argument in the `seq()` function is 1.

An alternative method to obtain sequences of numbers spaced by one value is the `:` symbol:

```{r eval=FALSE}
z <- 1:5
z
```



#### Exercise 1

Work in pairs, meet the person sitting next to you and try the following together (3 min):

- Create a sequence of numbers from 10 to 30 spaced by three values
- How about decreasing sequences? Now try from 30 to 10 spaced by three values  (hint: check `?seq`)
- Round the number `pi` down to 1 decimal place (hint: check `?round`)

```{r}


```



### Vectors

- The output we get using R functions such as `seq()` are called vectors, which are collections of numbers or characters
- To create vectors use the function `c()` (a.k.a. *combine*)
- Use square brackets `[ ]` to indicate the position within the vector (the ***index***) and extract elements

```{r eval=FALSE}
x <- c(5,6,7,8,9,10)
x
x[3]
x[1]
x[3:5]
```

Arithmetic operations in vectors occur element by element:

```{r eval=FALSE}
x <- c(2, 4, 5, 6, 7)
y <- x*2
y
x + y
```

A vector can also contain text, however unlike values, these need to be captured using quotation marks `" "`:

```{r eval=FALSE}
x <- c("a", "b", "b", "c", "c", "d")
x

x <- c(a, b, b, c, c, d) # otherwise R thinks they are objects
```

To create subsets of our vectors, we can use *comparison* operators:

- `==` equal
- `>` greater than
- `<` less than
- `!=` not equal

```{r eval=FALSE}
x <- c("a", "b", "b", "c", "c", "d")
x == "b" # this is known as a logical or boolean vector, composed of TRUE or FALSE values only
x != "b"
x[x != "b"]

x <- c(2, 4, 5, 6, 7)
x > 4
x[x > 4]
```



### Import and explore data

We will use a small made-up dataset which is often used for [training purposes](https://www.rpubs.com/Shoaib29/323077). It contains information about 100 lung cancer patients aged 42-44 from different states in the US. We have saved these data as a `.csv` file to demonstrate how to import and explore data using R.

You will first need to find the **path** to the file `patient-data-cleaned.csv`, which was downloaded together with the course materials - see folder `IntroR`. Use the function `file.choose()` to open a dialogue box and browse through the directories to reach the file. The path will then be displayed in R:

```{r eval=FALSE}
file.choose()
```

e.g. for me the path is `/Users/martin03/Desktop/IntroR/patient-data-cleaned.csv`. The file `patient-data-cleaned.csv` is a comma-separated values (CSV) file, which can easily be opened using software like Excel. In R, use the `read.csv()` function and the path obtained above to create a data frame object:

```{r eval=FALSE}
patient_data <- read.csv("/Users/martin03/Desktop/IntroR/patient-data-cleaned.csv") # copy here the path obtained when running file.choose()
```

Exploring rows and columns in the `patient_data` data frame:

```{r eval=FALSE}
# Dimensions
dim(patient_data)
ncol(patient_data)
nrow(patient_data)

# Viewing contents
head(patient_data)
View(patient_data)

# Names of columns
colnames(patient_data)

# Accessing data using column names
patient_data$Smokes
patient_data$Height
patient_data$State

# Summary of all data frame contents
summary(patient_data)
```

R works such that the values in each column have all to be of the same type (i.e. all numbers or all characters/text).

You can apply functions to the columns of the data frame to ask various questions:

```{r eval=FALSE}
# What is the maximum height?
max(patient_data$Height)
# What is the minimum weight?
min(patient_data$Weight)
# What is the mean body mass index (BMI)? Rounded to one decimal place?
round(min(patient_data$BMI), 1)
```


#### Subsetting

Just like when subsetting vectors, a selection of a data frame can be made using square brackes `[ , ]`, however data frames are two-dimensional objects so you'll need both *row* and *column* indexes:

```{r eval=FALSE}
patient_data[1 , 2]
patient_data[2 , 1]
patient_data[c(1,2,3) , 1]
patient_data[c(1,2,3) , c(1,2)]
```

If you'd like to see all the rows, or all the columns, you can neglect either the row or column index respectively. But ... remember to keep the comma ;)

```{r eval=FALSE}
patient_data[2, ]
patient_data[, 2]
patient_data[, 1:4]
```

Rather than selecting rows based on indexes, you can also use **comparison** operators to give either a `TRUE` or `FALSE` result. When applied to subsetting, only rows with a `TRUE` result get returned.

```{r eval=FALSE}
# The vector of TRUE or FALSE results applied to subsetting data
patient_data$Height > 183

# Which patients are taller than 183cm?
patient_data[patient_data$Height > 183,]

# Which patients are smokers?
patient_data[patient_data$Smokes == "Smoker",]

# Which patients are taller than 183cm AND are smokers too?
patient_data$Height > 183 & patient_data$Smokes == "Smoker"
patient_data[patient_data$Height > 183 & patient_data$Smokes == "Smoker",]

# You can also select only specific columns using the column name, e.g. give me only the ID, Name, State and Disease Grade
patient_data[patient_data$Height > 183 & patient_data$Smokes == "Smoker", c("ID", "Name", "State", "Grade")]
```

The useful subsetting operators to bear in mind here are **and** `&`, **or** `|` and **in** `%in%`.


#### Exercise 2

Work in pairs if possible (3 min):

- Select patients that have a BMI greater than 30 or their weight is greater than 90kg. Calculate their average height.

- Select female patients from California who are not overweighted

```{r}


```



### Sort tables and export results

The function `order()` gives sorted indices, which can then be used to sort your data set:

```{r eval=FALSE}
# Sort patients by Disease Grade
order(patient_data$Grade)
patient_data[order(patient_data$Grade),] # from benign (1) to harmful (3)
patient_data[order(patient_data$Grade, decreasing = TRUE),] # from harmful (3) to benign (1)

# Sort patients by more than one condition: first Disease Grade, second Weight
patient_data[order(patient_data$Grade, patient_data$Weight, decreasing = TRUE),]
```

Once data processing is completed, you can export results out of R as follows:

```{r eval=FALSE}
# Which patients from California are non-smokers?
patient_data_california <- patient_data[patient_data$State == "California" & patient_data$Smokes == "Non-Smoker",]

# Export
write.csv(patient_data_california, file = "/Users/martin03/Desktop/IntroR/patient-data-cleaned-california.csv")
```



### Basic plotting

Simple plotting functions are available in the base R distribution (histograms, barplots, boxplots, scatterplots ...). All that is required as input are vectors of data, e.g. columns in your data frame.

**Histograms** are often used to have an overview of the distribution of continuous data:

```{r eval=FALSE}
hist(patient_data$BMI)
hist(patient_data$Weight)
```

**Barplots** are useful when you have counts of categorical data:

```{r eval=FALSE}
barplot(table(patient_data$Race))
barplot(table(patient_data$Sex))
barplot(table(patient_data$Smokes))
barplot(table(patient_data$State), las=2, cex.names=0.7) # 'las=2' changes the x-axis labels to horizonal and 'cex.names=0.7' changes the size
barplot(table(patient_data$Grade))
barplot(table(patient_data$Overweight))
```

**Boxplots** are good when comparing distributions Here the `~` symbol sets up a formula, the effect of which is to put the categorical variable on the x-axis and continuous variable on the y-axis -> `boxplot(y ~ x)`

```{r eval=FALSE}
boxplot(patient_data$BMI ~ patient_data$Grade)

boxplot(patient_data$BMI ~ patient_data$Overweight)
boxplot(patient_data$Weight ~ patient_data$Overweight)
```

**Scatter plots** are useful when representing two continuous variables. Here -> `plot(x, y)`:

```{r eval=FALSE}
plot(patient_data$Weight, patient_data$BMI)
```

To enhance the appearance of your plots, many different ways of customisation are possible:

- **Colours**: `col` argument. To get a full list of possible colours type `colours()`, or check this [online reference](http://www.stat.columbia.edu/~tzheng/files/Rcolor.pdf).
- **Point type**: `pch`
- **Axis labels**: `xlab` and `ylab`
- **Plot title**: `main`
- ... and many others: see `?plot` and `?par` for more options

```{r eval=FALSE}
plot(patient_data$Weight, patient_data$BMI, col="red", pch=16, xlab="Weight (kg)", ylab="BMI", main="US patient data")
abline(lm(patient_data$BMI ~ patient_data$Weight), col="blue")
```

Related arguments can be used for other plotting functions:

```{r eval=FALSE}
boxplot(patient_data$BMI ~ patient_data$Overweight, col=c("red", "green"), xlab="Overweight patient?", ylab="BMI", main="US patient data")
```

To explore other types of plots, have a look [here](https://www.statmethods.net/graphs/index.html). There are dedicated R libraries e.g. [ggplot2](http://ggplot2.tidyverse.org/index.html) to do more sophisticated plotting. We will be exploring these in future workshops.


#### Export graphics

When running commands directly in the interactive console (bottom-left panel), plots can be exported using the **Plots** tab in RStudio (bottom-right panel). Click on `Export` -> `Save as PDF ...`.

You can also save plots to a file calling the `pdf()` or `png()` functions before executing the code to create the plot:
 
```{r eval=FALSE}
pdf("/Users/martin03/Desktop/IntroR/BMIvsWeight.pdf")
plot(patient_data$Weight, patient_data$BMI, col="red", pch=16, xlab="Weight (kg)", ylab="BMI", main="US patient data")
abline(lm(patient_data$BMI ~ patient_data$Weight), col="blue")
dev.off()
```

The `dev.off()` line is important; without it you will not be able to view the plot you have created.


#### Exercise 3

The final one:

- Any differences of Weight or BMI between Smokers and Non-Smokers? (hint: try `boxplot`)
- Visualise the relationship between the Height and Weight of the patients

That's it! Enjoy R!



### Questions?

Feedback / questions about the course, please email Sergio (sermarcue@gmail.com).



### References and additional materials

Blogs:

- [End-to-end visualization using ggplot2](https://rviews.rstudio.com/2017/08/14/end-to-end-visualization-using-ggplot2/)
- [ggplot2 - Easy way to mix multiple graphs on the same page](http://www.sthda.com/english/wiki/ggplot2-easy-way-to-mix-multiple-graphs-on-the-same-page)
- [Getting started with data visualization in R using ggplot2](http://www.storybench.org/getting-started-data-visualization-r-using-ggplot2/)
- [Rookie mistakes and how to fix them when making plots of data](http://stuartlee.org/2018/04/14/content/post/2018-04-14-rookie-mistakes/)

Books:

- [R for Data Science](http://r4ds.had.co.nz/)
- [Data Visualization for Social Science. A practical introduction with R and ggplot2](http://socviz.co/)
- [https://www.huber.embl.de/msmb/index.html](https://www.huber.embl.de/msmb/index.html)

Courses:

- [CRUK-CI R crash course](https://bioinformatics-core-shared-training.github.io/r-crash-course/)
- [R for Reproducible Scientific Analysis](http://swcarpentry.github.io/r-novice-gapminder/)
- [Karl Broman's mini tutorials](http://kbroman.org/pages/tutorials.html)
- [Basic statistics and data handling with R](https://github.com/cambiotraining/stats-intro)
- [Scripting for data analysis (with R)](https://github.com/mrtnj/scripting_for_data_analysis)
- [An Introduction to Solving Biological Problems with R](http://cambiotraining.github.io/r-intro/)
- [Data Analysis and Visualisation using R](http://bioinformatics-core-shared-training.github.io/r-intermediate/): including dplyr and ggplot2
- Babraham institute basic/advanced R and ggplot2 [courses](http://www.bioinformatics.babraham.ac.uk/training/)
- R object-oriented programming and package development, [link1](http://lgatto.github.io/TeachingMaterial/) and [link2](http://logic.sysbiol.cam.ac.uk/teaching/advancedR/)
- [R course content for the CODATA-RDA Research Data Science Summer School](https://github.com/marioa/trieste)
- [Data carpentry course for biologists](https://jabberwocky.weecology.org/2016/11/14/fork-our-course-a-semester-long-data-carpentry-course-for-biologists/) by Ethan White
- [Cambridge's Data carpentry using R](https://tavareshugo.github.io/2017-09-11-cambridge/)
- [The Bioconductor 2018 Workshop Compilation](https://bioconductor.github.io/BiocWorkshops/)

Perspectives:

- [Bioconductor: A test drive of a DNA-analysis toolkit in the cloud](https://www.nature.com/articles/d41586-017-07833-1)
- [Scientific computing: code alert](https://www.nature.com/nature/journal/v541/n7638/full/nj7638-563a.html)



### Acknowledgements

Sergio is a University of Cambridge Data Champion funded by a Jisc research data [fellowship](https://www.jisc.ac.uk/) to develop research data training activities for researchers. He does research in bioinformatics and computational biology within the [Balasubramanian laboratories](http://www.balasubramanian.co.uk/) funded by the Wellcome Trust at the University of Cambridge.



### License

This work is distributed under a Creative Commons [CC0 license](https://en.wikipedia.org/wiki/Creative_Commons_license#CC0). No rights reserved.

Our sponsors:

<p align="center">
<img src=../../../20171024_GitHub_Chemistry_Cambridge/blob/master/images/UniversityCambridge_logo.png height="50"> <img src=../../../20171024_GitHub_Chemistry_Cambridge/blob/master/images/CRUKCI_logo.jpg height="50"> <img src=../../../20171024_GitHub_Chemistry_Cambridge/blob/master/images/Jisc_logo.png height="50"> <img src=../../../20171024_GitHub_Chemistry_Cambridge/blob/master/images/WellcomeTrust_logo.jpg height="50">
</p>
