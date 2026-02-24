# EmailJS Setup Instructions

Your portfolio now uses EmailJS to send emails directly from the contact form. Follow these steps to complete the setup:

## 1. Create EmailJS Account
1. Go to [https://www.emailjs.com/](https://www.emailjs.com/)
2. Sign up for a free account

## 2. Create Email Service
1. In your EmailJS dashboard, go to "Email Services"
2. Click "Add New Service"
3. Choose your email provider (Gmail, Outlook, etc.)
4. Connect your email account (use: shainnavilla2@gmail.com)
5. Note the **Service ID** (it will look like: `service_xxxxxx`)

## 3. Create Email Template
1. Go to "Email Templates" in your EmailJS dashboard
2. Click "Create New Template"
3. Use this template:

**Subject:** `New Message from Portfolio Contact Form`

**Content:**
```
Hello Shainna,

You have received a new message from your portfolio contact form:

Name: {{from_name}}
Email: {{from_email}}
Message: {{message}}

Best regards,
EmailJS
```

4. Save the template and note the **Template ID** (it will look like: `template_xxxxxx`)

## 4. Get Your Public Key
1. Go to "Account" → "API Keys"
2. Copy your **Public Key**

## 5. Update Your JavaScript
Replace the placeholder values in `assets/js/main.js`:

```javascript
// Line 83 - Replace with your actual public key
emailjs.init("YOUR_PUBLIC_KEY");

// Line 104 - Replace with your actual service and template IDs
emailjs.send('YOUR_SERVICE_ID', 'YOUR_TEMPLATE_ID', {
```

## 6. Test Your Form
1. Open your portfolio in the browser
2. Fill out the contact form
3. Submit to test if emails are sending correctly

## Benefits of EmailJS
- ✅ No backend server required
- ✅ Direct email sending from frontend
- ✅ Free tier available (200 emails/month)
- ✅ Professional appearance
- ✅ Better user experience than mailto links

## Troubleshooting
- If emails don't send, check your EmailJS dashboard for error logs
- Ensure your email service is properly connected
- Verify the template variables match the JavaScript code
- Check browser console for any JavaScript errors
