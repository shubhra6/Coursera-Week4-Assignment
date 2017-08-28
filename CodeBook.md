Description of run_analysis.R

The Script aims at implementing the task mentioned in the course description.Below are the task to be performed.

1. Merges the training and the test sets to create one data set.
2. Extracts only the measurements on the mean and standard deviation for each measurement.
3. Uses descriptive activity names to name the activities in the data set
4. Appropriately labels the data set with descriptive variable names.
5. From the data set in step 4, creates a second, independent tidy data set with the average of each     variable for each activity and each subject.

Workflow

1. First, all the similar data is merged using the rbind() function. By similar, we address those    files having the same number of columns and referring to the same    entities.
2. Then, only those columns with the mean and standard deviation measures are taken from the whole    dataset. After extracting these columns, they are given the    correct names, taken from    features.txt.
3. As activity data is addressed with values 1:6, we take the activity names and IDs from    activity_labels.txt and they are substituted in the dataset.
4. On the whole dataset, those columns with vague column names are corrected.
5. Finally, we generate a new dataset with all the average measures for each subject and activity    type (30 subjects * 6 activities = 180 rows). The output file is    called averages_data.txt, and    uploaded to this repository.

Variables

1. x_train, y_train, x_test, y_test, subject_train and subject_test contain the data from the    downloaded files.
2. x_data, y_data and subject_data merge the previous datasets to further analysis.
3. features contains the correct names for the x_data dataset, which are applied to the column names    stored in mean_and_std_features, a numeric vector used to    extract the desired data.
4. A similar approach is taken with activity names through the activities variable.
5. all_data merges x_data, y_data and subject_data in a big dataset.
6. Finally, averages_data contains the relevant averages which will be later stored in a .txt file.    ddply() from the plyr package is used to apply colMeans() and    ease the development.

Functions

1. Rbind() : It combines vector, matrix or data frame by rows.
2. Read.table{utils} : Reads a file in table format and creates a data frame from it, with cases    corresponding to lines and variables to fields in the file.
3. Cbind() : Take a sequence of vector, matrix or data-frame arguments and combine by columns or    rows, respectively. These are generic functions with methods for    other R classes.
4. names() : Functions to get or set the names of an object.

