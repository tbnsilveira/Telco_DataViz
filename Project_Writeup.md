
# Udacity Data Analyst Nanodegree 
## Project 8 - Create a Tableau Story

Since I work with Telecommunications, and also considering this is a working field that generates large amounts of data, I decided to explore the open data available from Brazilian Telecommunications Agency (Anatel) in order to see how the mobile communication in Brazil has evolved from 2009 to 2018.  
In the following lines I will report how it was to prepare the data; to start the data visualization via Tableau and what I could learn regarding both the data and the new tools. 


## 1. First Design
I was warned that choosing a specific dataset could increase the project execution time due to data wrangling tasks. On the other hand, I was in the same way encouraged to explore some data from my own, which I must say it was very exciting. Considering both arguments, time versus application, I established a time limit to the wrangling process: I should deal with it in two days, otherwise I would come back to a simpler and already cleaned dataset.  

The chosen data concerns about the numbers of mobile accesses in Brazil, provided by [Anatel](https://cloud.anatel.gov.br/index.php/s/TpaFAwSw7RPfBa8?path=%2FMovel_Pessoal) -- the Brazilian Telecommunications Agency. Also, Anatel has provided an analysis over this data ([available in Portuguese](http://www.anatel.gov.br/dados/destaque-1/283-brasil-tem-236-2-milhoes-de-linhas-moveis-em-janeiro-de-2018)) which I have used as a reference to my exploration: I should be able to find at least the same results.  

Once my dataset was chosen, my first attempt to read it directly on Tableau has failed, and I realized I wouldn't escape from the wrangling process. To do this task, I wrote an R script ([available at GitHub](https://github.com/tbnsilveira/Telco_DataViz/blob/master/dataWrangling.ipynb)) to transform the original data into a tidy format. At this stage I discovered the data before 2009 have been collected in a different way, the reason why I limited my analysis from 2009 to 2018.  

After loading my tidy data for the first time in Tableau, I started making some questions and trying to answer them through some simple visualizations. Since I had georeferenced data as well as a time series, my initial idea was to build a map evolving year after year. However, the resolution of the data was not enough for what I wanted: geo-referrals were limited to states, not cities, with little distinction between operators. In addition, the acronyms of the Brazilian states were confused with some of the United States. To solve this, I had to include and group in the "country" attribute so that the map was positioned correctly. This process led me to build [this dashboard](https://github.com/tbnsilveira/Telco_DataViz/blob/master/Tableau_FinalProject_TBNSilveira.twb), in which I tried to show the mobile access distribution along the years, as well as for the respective technologies. It was not the final result I wanted, but I started asking for feedback in order to improve it and to check if I was in the right way.  


## 2. Feedback
Working in a telecommunications company made it easy for me to find colleagues who were interested in the subject of my analysis.  They kindly replied to my questions, shared their understanding of my charts, and gave me important suggestions for improving them, as follow. 

### 2.1. What do you notice in the visualization?
[Colleague 01]  
> I am somewhat surprised to note how much mobile access has begun to decline in recent years.  

### 2.2. What questions do you have about the data?
[Colleague 01]
> What is the total access by year? 

### 2.3. What relationships do you notice?
[Colleague 02]  
> It's interesting to infer from the technology chart that some operators are predominant in some states against others. It would be nice to have the "Access by Telco" chart also changing by UF. 

[Colleague 03]
> Nice to see the technology evolving from GSM to LTE, but there's still so much to be done.


### 2.4. What do you think is the main takeaway from this visualization?
[Colleague 03]  
> This visualization could give me a whole view of the mobile telecommunication scene in Brazil. Really interesting!

### 2.5. Is there something you don’t understand in the graphic?
[Colleague 01]  
> Is there need to select the year on the map? I don't think it's useful since the charts below are already designed by year.  

[Colleague 03]  
> Do I really need to click on each state to change the technology chart? It would be so much easier if I just have to select it.  


## 3. Final Design  
Receiving some feedback from my peers helped me both to confirm that the message I wanted to pass through the charts was appropriately delivered, as well as to implement the improvements and fixes to make them more effective.  

Regarding the suggestion on item 2.2, I included the total number of access in the main chart. Doing it I could also remove the *year filter*, as suggested in item 2.5. I also improved the dashboard actions, make it able to change the charts appropriately when selecting some UF. 

Once the final version was ready, [I published it on Tableau Public](https://public.tableau.com/views/Tableau_FinalProject_TBNSilveira_v2/Dashboard?:embed=y&:display_count=yes). For the sake of comparison, [the previous version is also available on GitHub]([this dashboard](https://github.com/tbnsilveira/Telco_DataViz/blob/master/Tableau_FinalProject_TBNSilveira.twb))


## 4. Resources
All the resources used in this analysis was referred to along the text and code. 


