jquery.mycart
===============
jQuery plugin for cart feature
## myCart
It is a simple jQuery plugin with cart feature. Items are added into cart with single unit quantity every time **add to cart** button pressed. There are also feature for showing built in modal for **checkout** from cart. Quantity can be changed from the modal and item can be removed from it also. There has a facility to show your custom checkout page.
## Demo
[click here](http://asraf-uddin-ahmed.github.io/jquery.mycart/demo.html)
## How to Use It
Include CSS library on the web page
```css
<link rel="stylesheet" href="css/bootstrap.min.css">
```
Add this CSS
```css
<style>
  .badge-notify{
    background:red;
    position:relative;
    top: -20px;
    right: 10px;
  }
  .my-cart-icon-affix {
    position: fixed;
    z-index: 999;
  }
</style>
```
Include JS library on the web page
```javascript
<script src="js/jquery-2.2.3.min.js"></script>
<script type='text/javascript' src="js/bootstrap.min.js"></script>
<script type='text/javascript' src="js/jquery.mycart.js"></script>
```
Add this JS
```javascript
<script type="text/javascript">
     $(function () {
         // selector may be an ID, class, tag name or etc
         $("selector").myCart(options);
     });
</script>
```
## Options
You can change the effect by modifying **options**.
```javascript
var options = {
      currencySymbol: '$',
      classCartIcon: 'my-cart-icon',
      classCartBadge: 'my-cart-badge',
      classProductQuantity: 'my-product-quantity',
      classProductRemove: 'my-product-remove',
      classCheckoutCart: 'my-cart-checkout',
      affixCartIcon: true,
      showCheckoutModal: true,
      cartItems: [
        {id: 1, name: 'product 1', summary: 'summary 1', price: 10, quantity: 1, image: 'images/img_1.png'},
        {id: 2, name: 'product 2', summary: 'summary 2', price: 20, quantity: 2, image: 'images/img_2.png'},
        {id: 3, name: 'product 3', summary: 'summary 3', price: 30, quantity: 1, image: 'images/img_3.png'}
      ],
      clickOnAddToCart: function($addTocart){
        goToCartIcon($addTocart);
      },
      clickOnCartIcon: function($cartIcon, products, totalPrice, totalQuantity) {
        console.log("cart icon clicked", $cartIcon, products, totalPrice, totalQuantity);
      },
      checkoutCart: function(products, totalPrice, totalQuantity) {
        var checkoutString = "Total Price: " + totalPrice + "\nTotal Quantity: " + totalQuantity;
        checkoutString += "\n\n id \t name \t summary \t price \t quantity \t image path";
        $.each(products, function(){
          checkoutString += ("\n " + this.id + " \t " + this.name + " \t " + this.summary + " \t " + this.price + " \t " + this.quantity + " \t " + this.image);
        });
        alert(checkoutString)
        console.log("checking out", products, totalPrice, totalQuantity);
      },
      getDiscountPrice: function(products, totalPrice, totalQuantity) {
        console.log("calculating discount", products, totalPrice, totalQuantity);
        return totalPrice * 0.5;
      }
};
```
## End
Thanks for checking this out. If you have any questions, please contact with this email: 13ratul@gmail.com
