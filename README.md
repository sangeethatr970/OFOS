# 🍔 Online Food Ordering System — JSP + Hibernate

A classic full‑stack Java web app where customers browse restaurants and menus, add items to cart, place orders, and track delivery. Admins manage restaurants, menu items, users, and orders. Built with **JSP + Servlets**, **Hibernate (JPA)**, and **MySQL**.

---

## ✨ Features

* **Authentication & Roles**: Customer, Admin, Delivery.
* **Restaurant & Menu Management** (Admin).
* **Search & Filters**: by cuisine, price, rating, veg/non‑veg.
* **Cart & Checkout**: address + payment mode (COD/Mock UPI).
* **Order Tracking**: Pending → Accepted → Preparing → Out for Delivery → Delivered/Cancelled.
* **Reviews & Ratings** (customers post‑delivery).
* **Responsive UI** (JSP + CSS/Bootstrap).
* **Hibernate ORM**: clean DAO/service layers.
* **Validation & Security**: session-based auth, server‑side validation.

---

## 🧱 Tech Stack

* **Frontend**: JSP, HTML5, CSS3, JavaScript (with Bootstrap for responsiveness)
* **Backend**: Java (Servlets, Hibernate ORM)
* **Database**: MySQL 8+
* **Server**: Apache Tomcat 9/10
* **Build Tool**: Maven

---

## 🗂️ Project Structure

```
food-ordering/
├─ src/
│  ├─ main/
│  │  ├─ java/
│  │  │  └─ com/example/foodapp/
│  │  │     ├─ config/ (HibernateUtil)
│  │  │     ├─ entity/ (JPA entities)
│  │  │     ├─ dao/ (DAO interfaces + impl)
│  │  │     ├─ service/ (business services)
│  │  │     ├─ web/ (servlets, filters, listeners)
│  │  │     └─ util/ (helpers, validators)
│  │  ├─ resources/
│  │  │  └─ hibernate.cfg.xml
│  │  └─ webapp/
│  │     ├─ WEB-INF/
│  │     │  ├─ web.xml
│  │     │  └─ views/ (JSP pages)
│  │     ├─ assets/ (css, js, images)
│  │     └─ index.jsp
│  └─ test/ (unit tests)
├─ pom.xml
└─ README.md
```

---

## 🧩 ER Diagram (Simplified)

```
User( id PK, name, email, passwordHash, role{ADMIN,CUSTOMER,DELIVERY}, phone )
Address( id PK, user_id FK→User.id, line1, line2, city, pincode, landmark )
Restaurant( id PK, name, cuisine, open, rating )
MenuItem( id PK, restaurant_id FK→Restaurant.id, name, description, price, veg, available )
Cart( id PK, user_id FK→User.id, updatedAt )
CartItem( id PK, cart_id FK→Cart.id, menu_item_id FK→MenuItem.id, qty )
Order( id PK, user_id FK→User.id, address_id FK→Address.id, status, total, paymentMode, createdAt )
OrderItem( id PK, order_id FK→Order.id, menu_item_id FK→MenuItem.id, price, qty )
Review( id PK, user_id FK→User.id, restaurant_id FK→Restaurant.id, rating, comment, createdAt )
```
**still ongoing project ------------**
```


