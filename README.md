<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Redirecting to Stripe...</title>
    <script>
        window.onload = function() {
            // Extract the discord ID from the URL parameter
            const urlParams = new URLSearchParams(window.location.search);
            const discordId = urlParams.get('discordid');
            
            if (discordId) {
                // Redirect to the Stripe Checkout page with the custom field prefilled
                const stripeCheckoutUrl = 'https://buy.stripe.com/eVa8xQ9wZ0du1Mc6oo';

                // Create a form to submit the discordId to Stripe
                const form = document.createElement('form');
                form.setAttribute('action', stripeCheckoutUrl);
                form.setAttribute('method', 'POST');

                // Create the hidden input field for the Discord ID
                const input = document.createElement('input');
                input.setAttribute('type', 'hidden');
                input.setAttribute('name', 'discorduserid'); // Must match the input name in the Stripe form
                input.setAttribute('value', discordId);

                form.appendChild(input);
                document.body.appendChild(form);

                form.submit(); // Submit the form automatically
            } else {
                alert('Discord ID not found.');
            }
        };
    </script>
</head>
<body>
    <h1>Redirecting to Stripe Checkout...</h1>
</body>
</html>
