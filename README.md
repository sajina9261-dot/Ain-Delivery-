# Ain-Delivery-
Delivery website
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Ain Delivery App</title>
    <link rel="icon" href="icon.png" type="image/png">
    <style>
        body {
            font-family: Arial, sans-serif;
            margin: 0;
            padding: 0;
            background: #f8f8f8;
        }
        header {
            background: #28a745;
            color: white;
            padding: 20px;
            text-align: center;
        }
        header h1 { margin: 0; }
        .caption { font-size: 16px; margin-top: 5px; }
        nav { background: #333; display: flex; justify-content: center; flex-wrap: wrap; }
        nav a { color: white; padding: 15px 20px; text-decoration: none; display: block; }
        nav a:hover { background: #444; }
        .container { padding: 20px; }
        .page { display: none; }
        .active { display: block; }
        .card { background: white; padding: 20px; border-radius: 10px; margin-bottom: 20px; box-shadow: 0 2px 5px rgba(0,0,0,0.1); }
        .card h2 { margin-top: 0; }
        .card ul { list-style: none; padding: 0; }
        .card ul li { padding: 5px 0; }
        form input, form textarea, form select { width: 100%; padding: 10px; margin: 10px 0; border-radius: 5px; border: 1px solid #ccc; }
        form button { background: #28a745; color: white; border: none; padding: 15px; border-radius: 5px; width: 100%; cursor: pointer; font-size: 16px; }
        form button:hover { background: #218838; }
        .quantity-container { display: flex; gap: 10px; }
        .quantity-container input, .quantity-container select { flex: 1; }
        label { font-weight: bold; }
        .shops ul { list-style: none; padding: 0; }
        .shops li { padding: 5px 0; }
    </style>
</head>
<body>

<header>
    <h1>Ain Delivery</h1>
    <p class="caption">Your Home Delivery App – Everything You Need at Your Doorstep</p>
</header>

<nav>
    <a href="#" onclick="showPage('home')">Home</a>
    <a href="#" onclick="showPage('shops')">Nearby Shops</a>
    <a href="#" onclick="showPage('groceries')">Groceries Only</a>
    <a href="#" onclick="showPage('payment')">Payment</a>
</nav>

<div class="container">

    <!-- Home Page -->
    <div id="home" class="page active">
        <div class="card">
            <h2>Our Services</h2>
            <ul>
                <li>Fresh Meat & Fish</li>
                <li>Groceries & Vegetables</li>
                <li>Home Delivery to Your Doorstep</li>
                <li>Quick and Easy Ordering</li>
            </ul>
        </div>

        <div class="card">
            <h2>Place Your Order</h2>
            <form id="orderForm">
                <label for="name">Your Name</label>
                <input type="text" id="name" name="name" placeholder="Enter your name" required>

                <label for="phone">Phone Number</label>
                <input type="tel" id="phone" name="phone" placeholder="Enter phone number" required>

                <label for="address">Delivery Address / Location</label>
                <input type="text" id="address" name="address" placeholder="Enter your address or location" required>

                <label for="category">Select Category</label>
                <select id="category" name="category" required>
                    <option value="">Select Category</option>
                    <option value="meat">Meat</option>
                    <option value="fish">Fish</option>
                    <option value="grocery">Groceries</option>
                    <option value="other">Other Goods</option>
                </select>

                <label>Quantity & Unit</label>
                <div class="quantity-container">
                    <input type="number" name="quantity" placeholder="Quantity" min="0" step="0.01" required>
                    <select name="unit" required>
                        <option value="">Unit</option>
                        <option value="kg">kg</option>
                        <option value="ltr">ltr</option>
                        <option value="pack">pack</option>
                    </select>
                </div>

                <label for="details">Order Details</label>
                <textarea id="details" name="details" placeholder="Additional details about your order" rows="4" required></textarea>

                <button type="submit">Submit Order</button>
            </form>
            <p id="orderMessage" style="color:green; text-align:center;"></p>
        </div>
    </div>

    <!-- Nearby Shops Page -->
    <div id="shops" class="page">
        <div class="card shops">
            <h2>Nearby Shops</h2>
            <ul id="shopsList">
                <li>1. Kaliyathmukk, Kerala Chicken</li>
                <li>2. Kunamvallikavu Fish</li>
                <li>3. TP Bazar</li>
                <li>4. PK Store</li>
                <li>5. Alankar</li>
                <li>6. Salam Mart</li>
            </ul>
        </div>
    </div>

    <!-- Groceries Only Page -->
    <div id="groceries" class="page">
        <div class="card groceries">
            <h2>Groceries Only</h2>
            <form id="groceryForm">
                <label for="gname">Your Name</label>
                <input type="text" id="gname" name="gname" placeholder="Enter your name" required>

                <label for="gphone">Phone Number</label>
                <input type="tel" id="gphone" name="gphone" placeholder="Enter phone number" required>

                <label for="glocation">Delivery Address / Location</label>
                <input type="text" id="glocation" name="glocation" placeholder="Enter your address or location" required>

                <label for="gdetails">Groceries Details</label>
                <textarea id="gdetails" name="gdetails" placeholder="List your groceries here" rows="4" required></textarea>

                <label for="gphoto">Upload Photos (optional)</label>
                <input type="file" id="gphoto" name="gphoto" accept="image/*" multiple>

                <button type="submit">Submit Groceries Order</button>
            </form>
            <p id="groceryMessage" style="color:green; text-align:center;"></p>
        </div>
    </div>

    <!-- Payment Page -->
    <div id="payment" class="page">
        <div class="card">
            <h2>Delivery Charges & Payment</h2>
            <p>Minimum charge: <strong>₹50</strong> for up to <strong>1.5 km</strong></p>
            <p>Above 1.5 km: <strong>₹30 per km</strong></p>

            <form id="paymentForm">
                <label for="pname">Your Name</label>
                <input type="text" id="pname" name="pname" placeholder="Enter your name" required>

                <label for="pphone">Phone Number</label>
                <input type="tel" id="pphone" name="pphone" placeholder="Enter phone number" required>

                <label for="pdistance">Distance (in km)</label>
                <input type="number" id="pdistance" name="pdistance" placeholder="Enter delivery distance" step="0.1" required>

                <button type="submit">Calculate Payment</button>
            </form>

            <p id="paymentMessage" style="color:green; text-align:center; margin-top: 15px;"></p>
        </div>
    </div>

</div>

<script>
    const whatsappNumber = "+919539119261"; // Your mobile number

    function showPage(pageId) {
        const pages = document.querySelectorAll('.page');
        pages.forEach(page => page.classList.remove('active'));
        document.getElementById(pageId).classList.add('active');
    }

    // Home Order Form - WhatsApp
    const orderForm = document.getElementById('orderForm');
    const orderMessage = document.getElementById('orderMessage');
    orderForm.addEventListener('submit', function(e) {
        e.preventDefault();
        const name = orderForm.name.value;
        const phone = orderForm.phone.value;
        const address = orderForm.address.value;
        const category = orderForm.category.value;
        const quantity = orderForm.quantity.value;
        const unit = orderForm.unit.value;
        const details = orderForm.details.value;

        const msg = `New Order from ${name} (%2B${phone}):%0ACategory: ${category}%0AQuantity: ${quantity} ${unit}%0ADetails: ${details}%0ALocation: ${address}`;
        const url = `https://wa.me/${whatsappNumber}?text=${msg}`;
        window.open(url, "_blank");

        orderMessage.textContent = `Thank you, ${name}! Your order has been sent to WhatsApp.`;
        orderForm.reset();
    });

    // Groceries Form - WhatsApp
    const groceryForm = document.getElementById('groceryForm');
    const groceryMessage = document.getElementById('groceryMessage');
    groceryForm.addEventListener('submit', function(e) {
        e.preventDefault();
        const gname = groceryForm.gname.value;
        const gphone = groceryForm.gphone.value;
        const glocation = groceryForm.glocation.value;
        const gdetails = groceryForm.gdetails.value;

        const msg = `New Groceries Order from ${gname} (%2B${gphone}):%0ADetails: ${gdetails}%0ALocation: ${glocation}`;
        const url = `https://wa.me/${whatsappNumber}?text=${msg}`;
        window.open(url, "_blank");

        groceryMessage.textContent = `Thank you, ${gname}! Your groceries order has been sent to WhatsApp.`;
        groceryForm.reset();
    });

    // Payment Form Calculation
    const paymentForm = document.getElementById('paymentForm');
    const paymentMessage = document.getElementById('paymentMessage');
    paymentForm.addEventListener('submit', function(e) {
        e.preventDefault();
        const name = paymentForm.pname.value;
        const distance = parseFloat(paymentForm.pdistance.value);

        let amount = 50; // minimum charge
        if(distance > 1.5){
            amount += (distance - 1.5) * 30;
        }

        paymentMessage.textContent = `${name}, your delivery charge is ₹${amount.toFixed(0)}.`;
        paymentForm.reset();
    });
</script>

</body>
</html>
