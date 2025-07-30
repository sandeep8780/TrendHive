# TrendHive 🛍️

A full-stack e-commerce application built with Java and Spring Boot, offering a secure and seamless shopping experience for customers and administrators.

## 🚀 Tech Stack

| Layer        | Technology                  |
|-------------|------------------------------|
| Backend     | Java, Spring Boot            |
| Security    | Spring Security, JWT         |
| Server      | Apache Tomcat (embedded)     |
| API Testing | Postman                      |
| Database    | MySQL                        |

## 📁 Database Tables

| Table Name       | Description                                    |
|------------------|------------------------------------------------|
| `users`          | Stores customer and admin user info            |
| `roles`          | Role-based access control (e.g., ADMIN, USER)  |
| `products`       | Stores product catalog                         |
| `orders`         | Stores customer orders                         |
| `order_items`    | Details of each product in an order            |
| `cart`           | Temporary cart items before checkout           |
| `payments`       | Stores payment transaction info                |

---

## 🛒 How to Purchase a Product

### 1. **User Registration & Login**
- Use `/api/auth/register` to register a new user.
- Login using `/api/auth/login` with email/password.
- Receive a JWT token for authenticated access.

### 2. **Browse Products**
- GET `/api/products` — View all available products.
- GET `/api/products/{id}` — View specific product details.

### 3. **Add to Cart**
- POST `/api/cart/add` — Add product(s) to user's cart.
```json
{
  "productId": 101,
  "quantity": 2
}

4. Place Order
POST /api/orders/place — Create order from cart.

 How Payment is Processed
1. Initiate Payment
After placing an order, payment is initiated via POST /api/payments/initiate

json
{
  "orderId": 501,
  "paymentMethod": "UPI/CARD"
}
2. Payment Confirmation
Simulated or integrated with third-party gateway (Razorpay).

On successful transaction:

Status updated in payments table.

Order marked as "Paid".

Inventory updated.

🔐 Role-Based Access
Role	Access
USER	Browse, add to cart, place orders, make payments
ADMIN	Manage products, view orders, update statuses, access all user data

🧪 API Testing with Postman
Collection available in /postman/TrendHive.postman_collection.json


