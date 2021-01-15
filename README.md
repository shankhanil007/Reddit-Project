# Reddit-Project

Reddit is a popular social media site. On this site, users post threads in various subreddits. Users can comment on threads or other comments. They can also give upvotes or downvotes to other threads and comments. Our goal is to predict the number of upvotes that comments will receive.


## Data Set
The data, a pickle file containing 1,205,039 rows (comments) that occurred in May of 2015, is hosted on google drive and can be downloaded using this link.
[http://files.pushshift.io/reddit/comments/RC_2015-01.bz2](http://files.pushshift.io/reddit/comments/RC_2015-01.bz2)

## Target variable
  * score: number of upvotes on the comment
  
## Comment level features
  * gilded: the number of gilded tags (premium likes) on the comment
  * distinguished: the type of user on the page. Either ‘moderator’, ‘admin’, or ‘user’
  * controversiality: a Boolean indicating whether (1) or not (0) comment is controversial (popular comments that are getting close to the same amount of upvotes as downvotes)
  * over_18: Whether or not the thread has been marked as NSFW
  * time_lapse: the time in seconds between comment and the first comment on the thread
  * hour_of_comment: the hour of day comment was posted
  * weekday: the day of week comment was posted
  * is_flair: whether or not there is flair text for the comment (https://www.reddit.com/r/help/comments/3tbuml/whats_a_flair/)
  * is_flair_css: whether or not there is a CSS class for the comment flair
  * depth: depth of comment in thread (number of parent comments that comment has)
  * no_of_linked_sr: number of subreddits mentioned in the comment
  * no_of_linked_urls: number of urls linked in the comment
  * subjectivity: number of instances of “I”
  * is_edited: whether or not the comment has been edited
  * is_quoted: whether or not comment quotes another
  * no_quoted: number of quotes in the comment
  * senti_neg: negative sentiment score
  * senti_neu: neutral sentiment score
  * senti_pos: positive sentiment score
  * senti_comp: compound sentiment score
  * word_count: number of words in the comment
  
## Parent level features
  * time_since_parent: the time in seconds between comment and the parent comment
  * parent_score: score of parent comment (NaN if the comment doesn’t have a parent)
  * parent_cos_angle: cosine similarity between comment and its parent comment’s embeddings (https://nlp.stanford.edu/projects/glove/)
  
## Comment tree root features
  * is_root: whether or the comment is a root
  * time_since_comment_tree_root: the time in seconds between comment and the comment tree root
  * comment_tree_root_score: score of comment tree root
  
## Thread level features
  * link_score: upvotes of on thread comment is on
  * upvote_ratio: the percentage of upvotes from all votes on thread comment is on
  * link_ups: number of upvotes on thread
  * time_since_link: time in seconds since the thread was created
  * no_past_comments: number of comments on thread before comment was posted
  * score_till_now: score of thread at the time this comment was posted
  * title_cos_angle: cosine similarity between comment and its thread’s title’s embeddings
  * is_selftext: whether or not thread had selftext
  
## Predicting Comment Scores

After selecting data features, we used four supervised learning techniques in order to attempt to learn the relationship between these features and the ultimate score of a comment.
  * Decision Trees
  * Random Forest
  * k-Nearest Neighbors

## Results
![](MAE_Comparision.JPG)
![](RMSE_Comparision.JPG)
