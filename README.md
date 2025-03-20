Pancake customization app (STEP 1)
This is the first step of your application, where you'll build a simple interactive webpage that allows users to customize their pancakes and see the total price update dynamically. You will submit this project later, so follow the steps carefully and keep your code clean and organized.

This application lets users customize their pancakes by selecting different types, toppings, and extras. As they make choices, the total price updates instantly, just like a pizza or burger configurator on a food-ordering site.

Steps to Build the Project
Set up event listeners
Use addEventListener to detect when the user changes the pancake type in the dropdown menu.
Use addEventListener to track when the user selects or deselects toppings and extras.
Retrive user selections
Get the selected pancake type from the dropdown.
Get all checked toppings from the list.
Get all checked extras and their prices.
Calculate the total price
Start with the base price of the selected pancake type.
Add 1€ per topping if selected.
Add the specific extra price for additional add-ons.
Update the Price Display
Dynamically update the #totalPrice and #totalPriceDisplay with the correct total price.
Improve the design and styling to make it more appealing Inspiration for this app is Kotipizza's "Make your Own Pizza" page. See example for inspiration.
Integrate a font from Google Fonts to apply to all elements on the page. Select a font that aligns with the modern and appealing aesthetic of the project.
Change the image and the colors, to make this app in your style.
Implement a captivating animation for the price display to draw attention to price changes.

# Pancake customization app (Step 2: Customer information and delivery options)

This is the second step of your application, where you will enhance the pancake customization app by adding customer details and delivery options.

You will submit this project later, so follow the steps carefully and keep your code clean and structured.

This step will also refactor event handling by listening to form changes instead of attaching multiple event listeners. The focus of this step is arrays, so you will store toppings and extras in arrays and display them correctly in the order summary.

## What has changed

- The HTML has already been refactored, so you do not need to modify it.
- All inputs are inside a `<form>` to allow for a single event listener.
- Prices are stored using `data-price` instead of `value` attributes.
- Selections should be retrieved using `.textContent` for display and `data-price` for calculations.
- An order summary section was added to display the final order details.

You now need to update the JavaScript based on these changes.

## Steps to update the JavaScript

### Refactor event listeners

- Instead of having multiple `addEventListener()` calls, attach a single `change` event listener to the `<form>` element.
- Inside the event handler, check which input was changed and update the order accordingly.

### Store toppings and extras in arrays

- Use arrays to store selected toppings and extras.
- When a topping or extra is selected, add it to the array.
- When it is deselected, remove it from the array.

### Update total price calculation

- Start with the base price of the selected pancake using `data-price`.
- Add 1€ per topping by iterating through the toppings array.
- Add the specific price for each extra by iterating through the extras array.
- If "Delivery" is selected, add an extra 5€ using `data-price`.
- Ensure the price updates instantly when any selection changes.

### Display the order summary

- Retrieve the customer name.
- Retrieve the selected pancake type.
- Retrieve checked toppings and extras from arrays and display them.
- Retrieve the chosen delivery method.
- Display the complete order details when the user clicks "See order".

# Pancake Customization App (Step 3: Order Management)

In this step, you will improve your application by handling **orders as objects** and storing them in an **array**. Additionally, you will create an **"All Orders"** page where a "chef" can manage the status of each order.

## What’s New?

1. **Store orders in an array**

   - Each order is stored as an object containing:
     - A unique `id`
     - The `customerName`
     - The `selectedPancake`
     - An array of `toppings`
     - An array of `extras`
     - The `deliveryMethod`
     - The `totalPrice`
     - The `status` (default: `"waiting"`)

2. **New "All Orders" page**
   - Displays all stored orders.
   - The "chef" can **update the status** of each order.
   - Different statuses will have **different styles**:
     - **"waiting"** - default style (e.g., yellow)
     - **"ready"** - updated style (e.g., blue)
     - **"delivered"** - final style (e.g., green)

## Steps to implement

### Store orders in an array

- Create an `orders` array to store order objects.
- When a user **confirms** an order:
  - Generate a **unique ID** (e.g., using `Date.now()`).
  - Create an **object** containing order details.
  - Add the object to the `orders` array.
  - Store `orders` in **localStorage** so data is not lost when the page refreshes.

### Display orders on the "All Orders" page

- Retrieve all orders from `localStorage` and display them.
- Each order should show:
  - **Order ID**
  - **Customer Name**
  - **Pancake Type**
  - **Toppings & Extras**
  - **Delivery Method**
  - **Total Price**
  - **Status** (Dropdown or Buttons to change status)

### Update order status

- Add a **dropdown** or **buttons** to allow the chef to update the status.
- When the status changes, update the corresponding order object and save it in `localStorage`.
- Apply different styles based on status:
  - `"waiting"` → 🟡 Yellow
  - `"ready"` → 🔵 Blue
  - `"delivered"` → 🟢 Green

### Persist data using `localStorage`

- Save orders in `localStorage` to keep data after refreshing.
- Load and display orders from `localStorage` when the "All Orders" page opens.

## Example order object:

```javascript
{
  id: 1700000001234,
  customerName: "Alice",
  selectedPancake: "Chocolate",
  toppings: ["Nuts", "Syrup"],
  extras: ["Whipped Cream"],
  deliveryMethod: "Delivery",
  totalPrice: 15,
  status: "waiting"
}
```

### Bonus fatures:

- Add **search** to find orders by name or ID.
- Add **sorting** (e.g., show "waiting" orders first).
- Allow the **removal of orders** when delivered.
