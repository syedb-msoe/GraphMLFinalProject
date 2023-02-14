# Universities Recommendation System
##### CS 4981 - 031: Graph Machine Learning Final Project
##### Authors: Bilal Syed, Thy Le

## Abstract
Our goal for this final project is to make a recommendation system that recommends a set of universities for the user based on their GPA. This problem interests us because we understand the difficulties of researching and choosing options for universitites and colleges. Finding schools with certain grades can be hard and consuming as there are not many sites containing all information about schools, and/or allow students to filter grades as constraints. Our hypothesis is that GPA is the critical constraint for a student to be accepted to specific universities. While in reality, other factors might effect (athlete, scholarships, ...), we eliminate those factors here and only consider GPA. Another hypothesis that we have is that when a student applied and got accepted to a school, they are recommended to apply and may have good chance to be accepted to similar universities. Our contribution is to make an efficient recommendation system by applying the learning of node embedding to turn data into vectors, and from here to train the model, analyze and filter the data based on GPA constraint. We measure the results by analyzing the sets of universities that accept certain GPA. Each set are recommended universities that one may apply to as they apply to one in the same set. 
## Introduction
We are making a university recommendation system by applying our knowledge of graph machine learning. In more detail, we found a dataset of students along with their GPAs, schools that they applied to and the results of getting accepted or rejected to those schools. As the dataset is a tabular representation, we want to turn these into learnable data to train the model so it'd give precise and accurate recommendation, by using node embedding process of turning data into vectors of features (GPAs, schools' ids that the student applied, status of accepted/rejected). As we are able to train the model from these data, we want to use algorithms to return results based on these node features. Our results would be returned by the k means clustering algorithm, as sets of universities that has certain similarities.
## Methods
#### Methods
Common recommendation system uses K nearest neighbor, feature weighted algorithm. In our project, we are using the feature weighted algorithm, so called "k-means clustering". By using this, we are able to weight the GPA, figure out the similarities between the students applied and get accepted to specific schools. K means clustering helps us to recommend a set of universities where there're certain similarities.
#### Dataset
The dataset of students information along with their GPAs, and schools applied to can be found here: https://github.com/tramatejaswini/University_Recommendation_System/blob/master/WebScraped_data/csv/Final.zip
We use the data in this zip file to filter out the node features (GPAs, schools applied)
#### Data reprocessing
Since the dataset is huge, and there are only certain information that we needed. There were quite some effort spend on data processing, in order to only take what we need. In more detail, we eliminated NULL and unknown columns. Other than that, as we want to train our model, we filtered the accepted status students so our model can recommend universities that student can get accepted to. Lastly, as PyTorch doesn't allow Tensor of String, we have to create dictionary/table of the mapping of universities names and numeric ids. The processed data can be found here:
https://github.com/syedb-msoe/GraphMLFinalProject/blob/master/data/overall_data.csv

## Results
Results are sets of universities that accept certain GPA/students that applied to one university in the set, may apply to others in the same set (i.e. each set are recommended universities that one may apply to as they apply to one in the same set). As a result, the clusters/sets in the result reflect this, where a cluster is a set of universities that accept somewhat similar GPAs. However, it's a little off due to the diversity in GPAs that get accepted to one school. This might be because only the decision of accepted/rejected were provided, while other factors (athlete, scholarships, fellowship, ...) were not, and hence affect the results (where a school for 4.0 GPA also accepts students with 2.8 GPA). Below is a sample result from 3 clusters (the actual results are bigger and shown in the ipynb file). From the clusters, we notices that students applied and got accepted to university A in cluster x, are recommended to apply to university B in cluster x.
| Cluster 1|Cluster 2| Cluster 3|
|-------|-----|----|
|University of Florida|Stanford University|University of Washington|
|Brown University|Boston University|Arizona State University|
|Ohio State University|Cornell University|New York University|
## Conclusions
Our hypothesis is somewhat precise to the results. It's precise in a way that we weight GPA and hence students with certain GPA applied and got accepted to a school are recommended to apply and have a high chance to get accepted to other schools in the same clusters. However, it's a little off due to the diversity in GPAs that get accepted to one school. This might be because only the decision of accepted/rejected were provided, while other factors (athlete, scholarships, fellowship, ...) were not, and hence affect the results (where a school for 4.0 GPA also accepts students with 2.8 GPA). By working on this project, us as Software Engineering majors without Machine Learning experience have greatly extended our knowledge on the topics of not only graph based machine learning, but also general topics in machine learning such as node embedding, matrix factorization, training model, ...
## References
https://github.com/tramatejaswini/University_Recommendation_System
https://www.youtube.com/watch?v=_hf_y-_sj5Y&list=PLZoTAELRMXVN7QGpcuN-Vg35Hgjp3htvi
https://github.com/SpencerPao/Data_Science/tree/main/Recommendation%20Systems
