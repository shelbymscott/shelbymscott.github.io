---
permalink: /BatesTalk/
title: "Bates DCS Departmental Seminar"
excerpt: "Further Information"
type: NDSEGConference
author_profile: true
---
If you have further questions about the details regarding my work, hopefully some of them are answered here. Feel free to explore and, as always, [e-mail](mailto:sscott41@vols.utk.edu) me if you have further questions, or find me around the conference this week! Figures and tables from the preliminary results are available [here](https://shelbymscott.github.io/files/PreliminaryResults.pdf) and more figures for motivation and methods are available [here](https://shelbymscott.github.io/files/MotivationMethods.pdf).

<details>
<summary>Motivation</summary>
<br>
<p>
Gun violence leads to more than 31,000 deaths and 78,000 nonfatal injuries each year in the United States. Homicide is the leading cause of death among African American males aged 10 - 24, and 2/3 of these deaths involve firearm use. The homicide rate for African Americans in 2010 was 16.3 per 100,000, whereas the overall homicide rate was 4.4 per 100,000. Therefore, apparent disparity exists in rates of homicide for different demographic groups. Gun violence does not only affect the direct victims and perpetrators involved in events, studies have shown that adults exposed to gun violence as children showed an increased likelihood for chronic health conditions compared with those who did not experience such exposures. These chronic health conditions include heart disease, cancer, chronic obstructive lung disease, hepatitis, diabetes, and stroke. Exposure to gun violence also leads to an increase in risky behaviors, especially in youth.
</p>

<p>
Despite the severity of gun violence, there has been little research published on the topic and also limited amounts of funding provided. Gun violence has a similar mortality rate to that of sepsis, but only receives 0.7% of the funding. It is also the second least researched cause of death, with accidental falls as the cause of death with fewer published papers, relative to mortality rate. This is due in part to the Dickey Amendment, passed in 1996. Three years earlier, Arthur Kellermann and colleagues published a paper that found having a gun in the home is significantly associated with increased risk of homicide occurring in the home. Congress then passed the amendment in concert with funding appropriations for the Centers for Disease Control (CDC), which stated no federal funds could be used to promote or advocate for gun control. Similar language has since been added to the funding appropriations for the National Institutes of Health (NIH). Removing funding from these two groups effectively reduced large-scale research on gun violence in the United States, contributing to the lack of relevant publications.
</p>

<p>
The purpose of this model is to observe and predict the spread of gun crime in Chicago, Illinois. I use approaches from epidemic models in order to explore the ways in which gun crime spreads throughout the 77 community areas of Chicago and how heterogeneity in the socioeconomic conditions can bolster and hinder the spread of these events. Provided the model can appropriately replicate past gun crime events, it can also be used to predict and then control future gun crimes in both space and time. Further, these methods can be applied to gun crime in other cities to predict future crime. Because I include socioeconomic conditions as environmental heterogeneity, I can also determine how socioeconomic conditions affect the spread of gun crime, which could inform policy decisions.
</p>

</details>

<details>
<summary>Mathematical and Statistical Modeling</summary>
<br>
<p>
There are multiple statistical models in this project that come together in order to contribute to a mathematical model of the system. The mainstream media often presents gun violence as an "epidemic" in the United States, and a variety of researchers have addressed the validity of this claim. If it is acceptable that gun violence is analogous to an epidemic, a suite of methods from epidemiology are then available to be used for this sociological "disease." Siettos and Russo present a summary of the mathematical and statistical methods used for observing infectious disease dynamics. Robert Smith? similarly outlines the types of mathematical models that can be used to assess problems in epidemiology and to arrive at the desired conclusions, without having to perform rigorous (or often impossible) field experiments. Generally, the purpose of mathematical models is to elucidate key features of the system and ignore what is not relevant to the specific question to be answered. Whereas mathematical models explore how a change in one aspect of the system can relate to changes in other parts of the system, statistical models imply that variations in the dependent variables depend on variations in the independent variables. Statistical models help to unearth what is happening, while mathematical models help to unearth why the event is occurring. Statistical models are often seen as a subset of mathematical models. Therefore, mathematical and statistical models should be used in concert with one another to make conclusions about questions of interest in the field.
</p>

<p>
There are a variety of different types of models that are used in order to understand the dynamics of epidemics. They can be broken down into categories of stochastic vs. deterministic, static vs. dynamic, and discrete vs. continuous. Stochastic models allow the inclusion of random events in the system, while deterministic models assume that the factors included in the model fully represent the outcomes. Static models observe the events at one point in time and/or space, while dynamic models observe the events over a span of time and/or space. Finally, discrete models observe the state of a system at specific increments in space and/or time, while continuous models observe the state of a system over a span of space and/or time.
</p>

</details>

<details>
<summary>Cellular Automata Models</summary>
<br>
<p>
Cellular automata (CA) are a class of spatio-temporal models that have often been used for epidemic modeling. Basic CA models are composed of a regular lattice in which each cell exists in a specific state. At each time step, the cell states update based on a set of local rules, usually depending on interactions within neighborhoods. They are discrete in space and time and often attempt to gain new insight into the behavior and dynamics of a system or predict future outcomes under certain conditions. Previous CA models of epidemics have included rabies, Chagas disease, foot-and-mouth, as well as many others. Many epidemic models ignore the spatial component and solely track the temporal spread of an epidemic through a population. When the environment is generally homogeneous, there may be no need to add the complexity of a spatial component. In numerous cases, though, environmental heterogeneity increases the need to add a spatial component to models. Liu et al. compared a reaction-diffusion model of epidemic spread with one formulated on a CA. They included interactions between epidemic states and environmental heterogeneity in the form of population structure and demography, and found that the CA model with environmental heterogeneity embedded and dispersed more stably in space than the non-spatial counterpart. A more stable model is easier to interpret, thus it is appropriate to use the spatial model when environmental heterogeneity is present in the system. Some of these spatial components are simple additions to the lattice, but many more recent CA models have incorporated the use of geographic information systems (GIS) data to improve the biological realism of the spatial component.
</p>

<p>
The cellular automata model we create consists of a $7 \times 11$ lattice of the 77 community areas of Chicago with each cell's state representing the category of crime (low, medium, or high) present in that community area. The cells also contain parameters for the unemployment rate, poverty level, and percentage of the population that is considered dependent, as well as a parameter for the level of crime present (1 - 15). The states of the cells update based on the crime levels of the surrounding cells. At each time step (representing a week), the cell will average the crime levels of the cells in its von Neumann neighborhood. If the average is higher than its current crime level, then it will increase its crime level by 1. Conversely, if the average is lower than its current crime level, then it will decrease its crime level by 1. If it is the same crime level as the average, then it will remain at the same crime level. It will then update its crime category and the global observation parameters for overall crime categories will be updated. The model measures the average crime level across all cells, the number of cells within each crime category, and the number of cells within each crime level. These dynamics are tracked over 520 time steps, or 10 years.
</p>

</details>

<details>
<summary>Covariates</summary>
<br>
<p>
While there are endless factors that can contribute to increased rates of crime, we focus on socio-economic indicators, as they are often blamed for crime and also can be addressed with changes to public policy, community action, or other interventions. In order to determine which indicators best-predicted the number of gun crimes in each community area, we run a subset procedure with a negative binomial regression, using information criteria to score the fit of each subset.
</p>

<p>
The subset procedure is used to determine which predictor variables are most useful for forecasting the response variable, and also often used to interpret a large number of regression coefficients, thus reducing some of the issues often faced with a large parameter space.  Overall, subset selection requires both an algorithm for the efficient searching of the solution space and a criterion or measure for the comparison of competing models to help guide the search. The algorithm takes combinations of predictors, runs a negative binomial regression over the data, and then diagnoses how well the regression fits the data. For our subset selection procedure, we use Akaike's Information Criteria with the equation:
$$
AIC(k) = 2k - 2 log L(\hat{\theta}_k),
$$
where $k$ represents the number of predictors in the subset and $log L(\hat{\theta}_k)$ is the log likelihood of the observations evaluated at $\theta$, which is the vector of predictors. The log likelihood function is:
$$
LogL(\hat{\theta}) = \sum_{i = 1}^{n} \ln(\Gamma(k_i + r)) - \sum_{i=1}^{n} \ln(k_i!) - n \ln(\Gamma(r)) + \sum_{i = 1}^{n} k_i \ln(p) + nr \ln(1 - p),
$$
where $n$ is the number of observations, $k_i$ is a predictor from the subset, $r$ is the number of failures before the experiment is stopped, and $p$ is the probability of success in the model.
</p>

<p>
Whereas count data is often fit using a Poisson distribution, the characteristics of this data point to a negative binomial distribution being most appropriate. In the Poisson distribution, it is expected that mean and variance are equal and therefore that there is equidispersion in the data. Our data do not meet this criteria, as the variance is far larger than the mean ($\mu = 128.88, \sigma^2 = 2.29 x 10^4$). The negative binomial distribution relaxes this restriction, and is therefore a better choice for this model.
</p>

<p>
We use multiple diagnostic statistics to determine whether one subset is a better fit of the data than others. While the algorithm gives the option of using AIC, ICOMP, CAIC, SBC, ICOMP(IFIM), and ICOMP(CovB), AIC produced better results than the other diagnostics and is therefore used for this model.
</p>
</details>

<details>
<summary>Determining Disease States</summary>
<br>

<p>
In order to determine how many different levels of crime should be included in the model, we used the $k$-selection procedure from Pham et al. Whereas most categorization algorithms require the user to define the number of classes before the data are divided into classes, the $k$-selection algorithm uses statistical diagnostics to determine the optimal number of categories in which to divide the data. The evaluation function $f(k)$ is defined using the equations:
$$
f(k) =
\begin{cases}
 1 & \text{if}~ k = 1 \\
 \frac{S_k}{\alpha_k S_{k-1}} & \text{if}~ S_{k-1} \neq 0, ~\forall k > 1 \\
   1 & \text{if}~ S_{k-1} = 0, ~\forall k > 1\\
\end{cases}\\
$$
$$
\alpha_k =
\begin{cases}
 1 - \frac{3}{4N_d} & \text{if}~ k = 2 ~\text{and}~ N_d > 1\\
 \alpha_{k-1} + \frac{1 - \alpha_{k-1}}{6} & \text{if}~ k > 2 ~\text{and}~ N_d > 1\\
\end{cases}
$$
where $S_k$ is the sum of the cluster distortions when the number of clusters is $k$, $N_d$ is the number of data set attributes (or dimensions), and $\alpha_k$ is a weight factor. Overall, the value of $f(k)$ is the ratio of the real distortion to the estimated distortion and is close to $1$ when the data distribution is uniform. Therefore, values of $k$ that yield small $f(k)$ can be regarded as giving well-defined clusters.
</p>

<p>
For the gun crime data in Chicago, Illinois, we wanted to inform the number of classes to be used in the cellular automata with data. Since our model is concerned with the spatial density of crime, we took the number of crimes in each community area from $2012 - 2017$, found the average over the time period, then divided this average by the community area to give the number of crimes per km$^2$ for each community area. We then ran twenty iterations of the $k$-selection algorithm (since stochasticity is integral to the process), and averaged the results.
</p>

</details>

<details>
<summary>Infectiousness of Gun Crime</summary>
<br>

<p>
Gun violence is often termed an epidemic in popular science and news articles. This is due to the fact that it seemingly can be passed between individuals and that there is spillover between geographically close areas. Slutkin describes in detail the aspects of gun violence that make it an epidemic and proposes some of the ways epidemiology could be used in order to understand more about gun crime and gun violence. If we can claim that gun violence is an epidemic, it may be useful to determine how far in space, time, and space/time that gun crime spreads throughout Chicago.
</p>

<p>
Loeffler and Flaxman use a Bayesian spatio-temporal point process model in order to differentiate between gun crimes that are clustered but non-diffusing and clustered gun crime resulting from diffusion. Their paper works exclusively with gun violence data collected from an Acoustic Gunshot Locator System (AGLS), while our dataset contains all of the spatio-temporally logged gun crimes that occurred in 2008 in Chicago, Illinois. The process used calculates the conditional intensity, $\lambda(x,y,t)$, of gun crime. This conditional intensity is composed of two parts: a background rate and a self-excitatory rate, which can be distinguished from one another. The equation used is:
$$
\lambda(x,y,t) = m_0 \mu(x,y,t)
$$
$$
+ \theta \sum_{i:t_i < t}^{}\omega \exp(-\omega(t-t_i))\frac{1}{2\pi \sigma^2} \exp(-((x-x_i)^2) + (y-y_i)^2/(2\sigma^2)),
$$
where the first term, $\mu(x,y,t)$, is the background intensity, estimated with an Epanechnikov kernel and weighted by $m_0$. The second term is the self-excitatory kernel, which is Gaussian distributed. The parameters of this equation include $\theta$, which gives the number of shootings triggered by any particular shooting. Other important parameters include $\omega$ and $\sigma$, which are the temporal and spatial length scales, respectively. The algorithm implements Hamiltonian Monte Carlo sampling to explore the parameter space. We run four chains for 1000 iterations, with 500 draws used as burn-in, giving a total of 2000 draws.
</p>

</details>

<details>
<summary>Preliminary Results</summary>
<br>

<b>Covariates</b>
<p>
The subset selection algorithm presents a constant, poverty, unemployment, and dependents as the best predictors of gun crime in Chicago. The table in the results (linked at the top of this page) shows the results from the algorithm. This allows us to see which subsets of predictors fit the model reasonably well and therefore may need to be further considered. We also show some diagnostics from the algorithm. The objective change at convergence ($\delta$) represents how well the algorithm performs and should be close to zero. Therefore, our procedure has done reasonably well at finding the appropriate subset. The log likelihood ($LogL$) does not have an interpretation on its own, but is used to calculate the AIC values and therefore part of the comparison with other models. The dispersion parameter ($\alpha$) represents how scattered the data are around the mean. A dispersion parameter of one would suggest a Poisson distribution. The resulting value of $\alpha = 0.7095$ confirms the decision to model this data using a negative binomial distribution.
</p>

<b>Determining Disease States</b>
<p>
After running 20 iterations of the $k$-selection algorithm, we found that the optimal number of classes for this data set is $15$ ($\mu = 14.95, \sigma = 1.61$). Figure 1 shows the results from one iteration of the model. The $f(k)$ function evaluates distortion in the data and is optimal when approaching zero. In the figure we observe that $6$ or $13$ clusters would also be appropriate ($f(k) < 0.85$), but that $15$ is the optimal number. These 15 disease levels can then be broken into equal interval subsets ranging from 0 - 92.70 gun crimes/km$^2$. These 15 crime levels can then be broken into three categories: low, medium, and high. Low crime areas have densities from 0.0 - 30.9 gun crimes/km$^2$, medium crime areas have densities from 31.0 - 61.8 gun crimes/km$^2$, and high crime areas have densities from 61.9 - 92.7 gun crimes/km$^2$.
</p>

<b>Infectiousness of Gun Crime</b>
<p>
Due to computational power, we have not yet run the algorithm over the entire dataset. The 2008 gun crimes have been subset by geographic area, time, and crime type. In all cases, gun crime shows contagious behavior. For a subset of the community areas (community areas 20-25), we find a $\theta$ value of $0.93$. Interpreted, this means that if $100$ crimes were observed at a given location, the next $93$ crimes observed within a $1.6$km radius and $12$ hours would have been triggered by the original $100$. We have also run this algorithm over other subsets and obtained different results, but in all cases there is spatio-temporal triggering of gun crimes.
</p>

</details>

<details>
<summary>Conclusions</summary>
<br>
<p>
The cellular automata model is still in development, but we have come to some conclusions in this preliminary work. From the analysis of covariates using negative binomial subset selection, we are able to determine that poverty, unemployment, and dependents are all significantly associated with the number of gun crimes that occur in a given community area. When assessing the natural breaks within the dataset using $k$-selection, we determine that we can break the crime down into $15$ different crime levels, which can then be further broken down into three categories of crime: low, medium, and high. Finally, when assessing a geographic subset of the data, we find that gun crimes are triggered by past gun crimes at that therefore we can term gun crime as an epidemic.
</p>

<p>
Preliminary cellular automata models have been created, which find that crime persists in the system, no matter where the initial outbreak occurs. Further testing is required to determine how the initial geographic distribution of crime affects the dynamics and how changes in parameters (crime levels, covariates, infectiousness) affect these dynamics as well.
</p>

</details>

<details>
<summary>Future Work</summary>
<br>
<p>
The next step in this model is to complete the Bayesian point process in order to determine the infectiousness of gun crime over a larger subset of the data or the entire dataset, if possible. There is also a need to confirm the model is not misspecified before the parameters are used within a cellular automata model. Once the model is appropriately parameterized, the full model, including GIS data, will be built and analyzed. This analysis will observe 1) how changes in the initial conditions affect the dynamics of crime spread and 2) how changes in the parameters affect the dynamics of crime spread.
</p>

<p>
The longer term plan for this project is to develop a theory for control in cellular automata models. There is currently a limited literature on how to use methods of optimization, control, and optimal control in cellular automata models. This work will be done on a simple cellular automata model, with methods tested against one another to determine which optimizes our parameter of choice and which one requires the least amount of computational power. The results from this will then be applied to the cellular automata model of gun crime to determine when and where intervention methods should be applied in order to reduce gun crime in Chicago. This "best" method can then be applied to cellular automata models of epidemics, fire spread, and other systems to optimize a desired outcome.
</p>
</details>

<details>
<summary>References</summary>
<br>
Sarsenbay Abdrakhmanov, Kanatzhan Beisembayev, Fedor I. Korennoy, Gulzhan Yessembekova, Dosym B. Kushubaev, and Ablaikhan S. Kadyrov. Revealing spatio-temporal patterns of rabies spread among various categories of animals in the republic of Kazakhstan, 2010-2013. Geospatial Health, 11(2), 2016. <br> <br>
American Psychological Association. Gun violence: Prediction, prevention, and policy. Technical report, American Psychological Association, 2013. <br> <br>
J.P. Aurambout, A.G. Endress, and B.M. Deal. A spatial model to estimate habitat fragmentation and its consequences on long-term persistence of animal populations. Environmental Monitoring and
Assessment, 109:199 – 225, 2005. <br> <br>
Braga, A. A., Zimmerman, G., Barao, L., Farrell, C., Brunson, R. K., & Papachristos, A. V. Street Gangs, Gun Violence, and Focused Deterrence: Comparing Place-based and Group-based Evaluation Methods to Estimate Direct and Spillover Deterrent Effects. Journal of Research in Crime and Delinquency, 56(4), 524–562, 2019. <br> <br>
Hamparsum Bozdogan. Intelligent Statistical Data Mining with Information Complexity and Genetic Algorithms. 1 edition, 2003. <br> <br>
Hamparsum Bozdogan. Modern statistical theory and inference: An informational modeling process with matlab. In preparation, 2019. <br> <br>
T. Rashad Byrdsong, Angela Devan, and Hide Yamatani. A ground-up model for gun violence reduction: A community-based public health approach. Journal of Evidence-Informed Social Work, 13(1):76–86, 2016. <br> <br>
Andreas Deutsch and Sabine Dormann. Cellular Automaton Modeling of Biological Pattern Formation. Modeling and Simulation in Science, Engineering, and Technology. Birkhauser Basel, 1 edition, 2005. <br> <br>
Ben Green, Thibaut Horel, and Andrew B Papachristos. Modeling contagion through social networks to explain and predict gunshot violence in chicago, 2006 to 2014. JAMA Internal Medicine, 2017. <br> <br>
William Greene. Functional forms for the negative binomial model for count data. Economics Letters, 99(3):585-590, 2008. <br> <br>
James W. Hardin. Generalized linear models and extensions, 2007. <br> <br>
Arthur L. Kellermann, Frederick P. Rivara, Norman B. Rushforth, Joyce G. Banton, Donald T. Reay, Jerry T. Francisco, Ana B. Locci, Janice Prodzinski, Bela B. Hackman, and Grant Somes. Gun ownership as a risk factor for homicide in the home. New England Journal of Medicine, 329(15):1084-1091, 1993. <br> <br>
Quan-Xing Liu, Zhen Jin, and Mao-Xing Liu. Spatial organization and evolution period of the epidemic model using cellular automata. Physical Review, 74, 2006. <br> <br>
C Loeffler and S Flaxman. Is gun violence contagious? a spatiotemporal test. Journal of Quantitative Criminology, August 2018. <br> <br>
Armin R. Mikler, Sangeeta Venkatachalam, and Kaja Abbas. Modeling infectious diseases using global stochastic cellular automata. Journal of Biological Systems, 13(04):421-439, 2005. <br> <br>
D Pham, Stefan Dimov, and Cuong Nguyen. Selection of k in k -means clustering. Proceedings of The Institution of Mechanical Engineers Part C-journal of Mechanical Engineering Science - PROC INST MECH ENG C-J MECH E, 219:103-119, 01 2005. <br> <br>
Joel L. Schiff. Cellular Automata: A Discrete View of the World. John Wiley & Sons, Inc, 2008. <br> <br>
Constantinos Siettos and Lucia Russo. Mathematical modeling of infectious disease dynamics. Virulence, 4, 04 2013. <br> <br>
R. Slimi, S. El Yacoubi, E. Dumonteil, and S. Gourbire. A cellular automata model for chagas disease. Applied Mathematical Modelling, 33(2):1072-1085, 2009. <br> <br>
Gary Slutkin. Violence is a contagious disease: Contagion of violence: Workshop summary, 2013. <br> <br>
Robert Smith? Modelling Disease Ecology with Mathematics, volume 2 of AIMS Series on Differential Equations & Dynamical Systems. American Institute of Mathematical Sciences, 1 edition, 2008. <br> <br>
Stark DE and Shah NH. Funding and publication of research on gun violence and other leading causes of death. JAMA, 317(1):84–86, Jan 2017. <br> <br>
Michael J. Tildesley and Matt J. Keeling. Is r0 a good predictor of final epidemic size: Foot-and-mouth disease in the uk. Journal of Theoretical Biology, 258(4):623 – 629, 2009. <br> <br>
S Towers. The difference between mathematical and statistical modelling (plus some more basics of r), 08 2013. Online. <br> <br>
S Towers, A Gomez-Lievano, M Khan, A Mubayi, and C Castillo-Chavez. Contagion in mass killings and school shootings. PLoS ONE, 10(7):e117 - 259, 2015. <br> <br>
Dexter R. Voisin, Sadiq Patel, Jun Sung Hong, Lois Takahashi, and Noni Gaylord-Harden. Behavioral health correlates of exposure to community violence among african-american adolescents in chicago. Children and Youth Services Review, 69(Supplement C):97 – 105, 2016. <br> <br>
Shari A. Wiley, Michael Z. Levy, and Charles C. Branas. The Impact of Violence Interruption on the Diffusion of Violence: A Mathematical Modeling Approach, pages 225{249. Springer International Publishing, Cham, 2016. <br> <br>
Margaret A Winker, Kamran Abbasi, and Frederick P Rivara. Unsafe and understudied: the us gun problem. BMJ, 352, 2016. <br> <br>
Jiaquan Xu, Sheery L. Murphy, Kenneth D. Kochanek, and Brigham A. Bastian. Deaths: Final data for 2013. Technical Report 64(2), National Vital Statistics System, Hyattsville, MD, February 2016. <br> <br>
Jie Xu and Elizabeth Griffiths. Shooting on the street: Measuring the spatial influence of physical features on gun violence in a bounded street network. Journal of Quantitative Criminology, 33(2):237 - 253, Jun 2017.

</details>
