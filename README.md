# PorterDeliveryCase
**Context:**
Porter is India's Largest Marketplace for Intra-City Logistics. Leader in the country's $40 billion intra-city logistics market, Porter strives to improve the lives of 1,50,000+ driver-partners by providing them with consistent earning & independence. Currently, the company has serviced 5+ million customers
Porter works with a wide range of restaurants for delivering their items directly to the people.
Porter has a number of delivery partners available for delivering the food, from various restaurants and wants to get an estimated delivery time that it can provide the customers on the basis of what they are ordering, from where and also the delivery partners.
This dataset has the required data to train a regression model that will do the delivery time estimation, based on all those features.

#### Implementation Steps
1. **Import the data and understand the structure of the data.**
2. **Data Preprocessing:**
   - Cleaning the data
   - Feature engineering:
     - Creating the target column `time_taken` = actual_delivery_time - created_at
     - Extracting hour of day and day of week from order time
     - Using pandas datetime functions
     - Getting delivery time in minutes
3. **Handling null values**
    - Handle missing data for feature 'actual_delivery_time' -**Strategy :** Check how much avegare delivery time is required to delivered each food items (store_primary_category) w.r.t day of the week and time.
    -  Handle missing data for 'market_id' feature _ **Strategy:** If store_id uniquely determines market_id, then we can impute missing market_id values by looking up the market_id associated with the same store_id from non-missing rows.
    -  Find missing data for features total_onshift_partners, total_busy_partners and total_outstanding_orders _ **Stratergy** --> Find relation with specific market and store.
    -  Handle missing data for column 'store_primary_category' and 'order_protocol'
      **Strategy :** Find the relationship with other columns
       - Impute store_primary_category using store_id, since a store typically has a fixed category.
       - Impute order_protocol using store_id or store_primary_category : Imputing order_protocol using the most frequent value (mode) per store_id or per store_primary_category
     
4. **Data visualization and cleaning**
5. **Check if the data contains outliers**
   - Removing outliers by interquartile method
6. **Split the data into train and test**
7. **Scaling the data for neural networks.**
   - MinMaxScalling
   - StandardScaling
8. **Creating a simple neural network**
   - Understanding different activation functions, optimizers and other hyperparameters.
9. **Training the neural network for required amount of epochs**
10. **Plotting the losses and checking the accuracy of the model**
11. **Checking its various metrics like MSE, RMSE, MAE**
12. **Tune the model**
    - EarlyStopping, Dropout






           
