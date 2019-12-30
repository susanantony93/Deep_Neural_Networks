# DeepNeuralNetworks

1. The function read_xml_files() is used to extract all  filename, headline, text, biptopics, date published and itemid from every news article in all the given directories.

2. The function text_processing() is written for the text pre-processing and cleaning purposes. PorterStemmer() object is used for word stemming and word_tokenize() is used for tokenizing different words. This function returns a list of cleaned text.

3. The function extract_features() is written for vectorizing the cleaned text using TfidfVectorizer().

4. A MultiLabelBinarizer() object is used as we were dealing with multiple labels and multiple classes. It will convert the list of labels into a matrix of multiple labels represented by 1 and 0 which can be used to cluster multi-label documents.

5. Elbow method is used to estimate the optimal number of clusters that can effectively cluster the given dataset. It will display a an elbow graph for clusters in the range of 3 to 12. We got an elbow at 6 and 8 clusters.

6. Silhouette method is also used to estimate the best value of 'k'. The graph plotted displays the silhouette scores for cluster values k=5,6,7,8,9. According to the silhouette graph the best value for k was selected as 7.

7. The function create_cluster() clusters all the TF-IDF features into different clusters using k-means clustering algorithm. The function returns a data frame with the document id and assigned cluster number.

8. The function evaluate_cluster() is used to evaluate the quality of the different clusters based on their average Silhouette Score.

9. The function classifier_for_cluster() is written to classify every cluster using 5 different classifiers: Multinomial NaiveBayes, SVC classifier, Random Forest, Decision Tree and Neural Networks.

10. The function get_accuracy_score() is used to get the accuracy score for every classifier model created from the clusters.

11. The function get_autoencoder_features() implements a deep autoencoder that takes the features of every cluster and returns the encoded features which is exactly half the size of the passed feature size. The auto encoder has 3 encoding layers, 3 decoding layers,l1 & l2 regulizers to prevent overfitting, relu and sigmoid activation and loss ='binary_crossentropy'.

12. The function deep_neural_network() implements a simple deep neural network which has three layers for multi-class and multi-label classification. It takes the encoded features from the auto encoder.
It uses relu and sigmoid activation and loss ='binary_crossentropy'.

14. Finally, the accuracy score for every cluster is calculated to compare with the accuracies before and after using Deep Neural Networks.

15. According to our observation, Deep Neural Networks works best for text classification.
