# Natural Disaster
#### *Objective:* Leverage supervised machine learning to estimate natural disaster casulties and damage cost. 

**Datasets Used**
* *EM-DAT: Natural Disasters Database.* Historical earthquake, storm and flood data for years 2000-2019
* *Socialeconomic Data and Applications Center (SEDAC) Population fo the World* Global population estimates by longitude and latitude For years 2000, 2005, 2010, 2015 and 2020(estimate)
* *USGS Earthquake Database.* Historical earthquake catalog with details such as earthquake magnitude, intensity and depth

**References**
* EM-DAT: The Emergency Events Database - Universite catholique de Louvain (UCL) - CRED, D. Guha-Sapir - www.emdat.be, Brussels, Belgium
* Center for International Earth Science Information Network - CIESIN - Columbia University. 2018. Gridded Population of the World, Version 4 (GPWv4): Administrative Unit Center Points with Population Estimates, Revision 11. Palisades, NY: NASA Socioeconomic Data and Applications Center (SEDAC). https://doi.org/10.7927/H4BC3WMT. Accessed June 9, 2019

## Natural Disaster: Preparing Earthquake Data

**Objective:** Analyze and merge earthquake datasets to gain a complete understanding of the factors affecting the severity and impact of earthquakes. 

**Steps + Conclusion**
1. **Importing Datasets**
    * EM-DAT: Natural Disasters Database. Historical earthquake, storm and flood data for years 2000-2019
    * USGS Earthquake Database. Historical earthquake catalog with details such as earthquake magnitude, intensity and depth


2. **Exploratory Analysis**
    * There is no directly linear correlation between magnitude value and total death. 
    * A magnitude value of 9.0+ does not correlate to higher death rate. Earthquake damage depends moreso on what area is hit. If an unpopulated region is struck, there will be low loss of life or property. But if the earthquake is struck in a highly densed area, there will be more casualities.
    * Magnitude alone cannot be used to predict death rate. Another important factor is location and location population/density. I'll need to somehow incorporate **World Population by Longitude and Latitude** data into my model.
    * To understand the strength and severity of earthquakes, I need to not only look at the **magnitutde** of an earthquake but also its **intensity** and **depth**. The EM-DAT data sets stores information about the magnitude of the earthquake, but I will need to join it with the USGS earthquake datasets to pull the depth and intensity. 


3. **Merging Datasets**
    * The EM-DAT and USGS datasets are pulled from two independent government agencies, so there are many inconsistency between the two data sources. As a result, merging the two datasets is not so straightforward as there are many null values and inconsistent data points for the same 'earthquake event'. I will attempt different merges by matching varying combinations of columns to try to narrow down the amount of manual merge. 
    

4. **Finding Outliers**
    * While I was able to merge 95% of the EM-DAT data based on methods described above, I need to make sure that the two data sources are aligned. 
    

#### Features Selection:
* Magnitude
* Depth
* Location (latitude and longitude)

