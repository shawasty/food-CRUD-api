# food_ordering_app
An e-commerce CRUD API for  African food
DESCRIPTION

This is an API demonstrating CRUD but will be used for building a food ordering app

TECHNOLOGIES

Express, Mongoose , Node.JS, MongoDB

DEPENDENCIES

crypto-js
dotenv   
jsonwebtoken

HOW TO RUN APPLICATION:

Default heroku URL for API : http://shawsfoodapp.herokuapp.com/ 
Use the following endpoints to access data in web-browser and postman.

Note that the authentication and encription of passwords implemented limits
access to information one can get from heroku, unless access is given to a super User with tokens.

Below are some endpoints to be used with postman or heroku with admin or super user access:

POSTMAN:
/api/meals,
/api/users,
/api/orders,
/api/carts,
/api/users/stats  - This gives statistics of all users within one year range

HEROKU
/api/meals

SCHEMAS

USER SCHEMA

const userSchema = new Schema(
    {
        username: {type: String, required: true },
        email: {type: String, required: true },
        password: {type: String, required: true },
        isAdmin: {type: Boolean, default: false},    
    },
    {timestamps: true}
)

MEAL SCHEMA
const mealSchema = new Schema(
  {
    name: { type: String, required: true },
    category: { type: String, required: true },
    image: { type: String, required: true },
    calories: { type: String, required: true },
    price: { type: String, required: true },
  },
  { timestamps: true }
)


ORDERS SCHEMA
const ordersSchema = new Schema(
  {
    userId: { type: String, required: true },
    meals: [{mealId: { String },quantity: {type: Number, default: 1}]
    amount: { type: Number, required: true },
    address: { type: Object, required: true },
  },
  { timestamps: true }
)

CART
const cartSchema = new Schema(
  {
    userId: { type: String, required: true },
    meals: [{mealId: { type: String },quantity: {type: Number,default: 1}]
  { timestamps: true }
)




