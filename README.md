# newser
Search for articles of a given topic and send them to various places: db, slack

# Requirements
 * Take queries or search strings for news stories
 * Accept a list of sources to limit specific publications
 * Integrate with a news api to retrieve top headlines for each query
 * Integrate with Slack to send articles
 * Integrate with Slack to suck articles that people post
 * Each slack post should include article, publication, description, and link to the article.

# Design
 * News Worker Interface
  * Connect to API
  * Query the top headlines based on config
 * Slack API Interface
  * Connect to api
  * Structure data in desired message format
  * send messages to specified channel (recent_news)
 * Query object
  * Encapsulate all query logic and perform data checks if needed
  * Map a query to a channel
  * Map query to the name of our result set
 * Config
  * House all constants/settings
  * Contain an iterable of query objects
 * Worker
  * Use the objects to implement the behavior we want and execute the program
 * Database object
  * Store the query results to a db

# Exe
 1. Use config file to get a set of queries we want to use for our article search
 2. Iterate over query objects and call news api for each to get top headlines
 3. Format Slack messages according to preferred style/layout
 4. Send Slack messages to the specified channel
 5. Store each item to DB
 6. Exit
