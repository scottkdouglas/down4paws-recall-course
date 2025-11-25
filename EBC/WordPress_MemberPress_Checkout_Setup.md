# WordPress + MemberPress Landing Page to Checkout Setup Guide
## "Come When Called: 30-Day Recall Course"

---

## OVERVIEW

You'll create two pages in WordPress:
1. **Landing Page** (built with Avada) - The sales page
2. **Checkout Page** (MemberPress registration form) - The payment page

Then link all CTA buttons from landing page → checkout page.

---

## STEP 1: CREATE THE MEMBERSHIP LEVEL IN MEMBERPRESS

### 1.1 - Create Membership

1. In WordPress admin, go to **MemberPress → Memberships**
2. Click **Add New**

### 1.2 - Configure Basic Settings

**Title:** `30-Day Recall Course`

**Content:**
```
Get instant access to all 19 email lessons delivered over 30 days.
```

**Pricing:**

**For Early Bird (First 50 Members):**
- Price: `$97.00`
- Billing Type: `One Time`
- Price Box: ✅ Checked

**Plan to change after 50 sales:**
- You'll manually edit this to `$147.00` after 50th sale

### 1.3 - Registration Settings

**Registration Button Text:** `Complete Purchase`

**Thank You Message:**
```
Welcome to the 30-Day Recall Transformation!

Check your email - your first lesson will arrive in the next 5 minutes.

IMPORTANT: Add our email to your contacts to ensure all lessons reach your inbox.

Questions? Email us at [your-support-email]
```

### 1.4 - Advanced Settings

**Registration Template:** Choose a clean template (or use default)

**Thank You Page:**
- **Option A:** Use built-in thank you message (above)
- **Option B:** Create custom thank you page (recommended)

If Option B:
- Create new WordPress page: "Welcome - You're In!"
- Add content (see Section 3 below)
- Select this page in dropdown

### 1.5 - Save Membership

Click **Publish**

**Note the Membership ID** - you'll see it in the URL:
`post.php?post=123&action=edit`
The number (123) is your membership ID.

---

## STEP 2: CREATE THE CHECKOUT PAGE

### 2.1 - Create New Page

1. **Pages → Add New**
2. **Title:** `Checkout - Recall Course` (or just "Checkout")
3. **Permalink:** Make it clean - `/checkout` or `/recall-course-checkout`

### 2.2 - Page Settings

**Template:** Full Width (no sidebar)

**In Avada:**
- Use Avada Live Builder
- Or use classic editor with shortcode (simpler for checkout)

### 2.3 - Add MemberPress Registration Form

**In the page content area, add:**

```
[mepr-membership-registration-form id="123"]
```

Replace `123` with your actual membership ID from Step 1.5.

**What this does:**
- Displays registration form
- Shows pricing
- Shows payment options (Square + PayPal buttons)
- Handles purchase processing
- Redirects to thank you page

### 2.4 - Add Trust Elements ABOVE the Form

Before the shortcode, add this content:

```html
<div style="max-width: 700px; margin: 0 auto; text-align: center; padding: 40px 20px;">

<h1>Complete Your Enrollment</h1>

<div style="margin: 20px 0;">
⭐⭐⭐⭐⭐ 69 Five-Star Google Reviews<br>
<em>Join 50+ dog owners transforming their recall</em>
</div>

<div style="background: #f9fafb; padding: 30px; border-radius: 8px; margin: 30px 0; text-align: left;">
<h3 style="margin-top: 0;">What You're Getting:</h3>
✅ 19 Email Lessons Over 30 Days<br>
✅ The 5 Rules of Reliable Recall<br>
✅ Step-by-Step Practice Exercises<br>
✅ Distraction Management Protocol<br>
✅ Your Dog's Personal Motivation Guide<br>
✅ Lifetime Access to All Lessons<br>
✅ Based on 5 Years of Proven Training Methods
</div>

<p style="font-size: 18px; margin: 20px 0;">
<strong>Early Bird Pricing: $97</strong> (First 50 Members - Save $50)<br>
<span style="color: #6b7280; font-size: 14px;">Regular price: $147</span>
</p>

<!-- MemberPress form appears below -->

</div>
```

Then add the MemberPress shortcode:
```
[mepr-membership-registration-form id="123"]
```

### 2.5 - Add Trust Elements BELOW the Form

After the shortcode, add:

```html
<div style="max-width: 700px; margin: 0 auto; text-align: center; padding: 20px;">

<p style="color: #6b7280; font-size: 14px;">
🔒 Secure checkout powered by Square and PayPal<br>
Your first lesson arrives in the next 5 minutes
</p>

<hr style="margin: 30px 0; border: none; border-top: 1px solid #e5e7eb;">

<h3>Quick Questions?</h3>

<details style="text-align: left; margin: 10px 0;">
<summary style="cursor: pointer; font-weight: bold;">What happens after I purchase?</summary>
<p>You'll receive a confirmation email immediately, followed by your first lesson within 5 minutes. Then, you'll receive new lessons every 1-2 days for 30 days.</p>
</details>

<details style="text-align: left; margin: 10px 0;">
<summary style="cursor: pointer; font-weight: bold;">Do I need any special equipment?</summary>
<p>No! Just your dog, treats (we'll show you how to find what motivates YOUR dog), and a leash. That's it.</p>
</details>

<details style="text-align: left; margin: 10px 0;">
<summary style="cursor: pointer; font-weight: bold;">Is this a subscription?</summary>
<p>No. This is a one-time payment of $97. You get lifetime access to all 19 email lessons.</p>
</details>

</div>
```

### 2.6 - Publish Page

Click **Publish**

**Your checkout page is now live at:**
`yourdomain.com/checkout` (or whatever permalink you chose)

---

## STEP 3: CREATE THANK YOU PAGE (OPTIONAL BUT RECOMMENDED)

### 3.1 - Why a Custom Thank You Page?

**Better than just the message because:**
- Can add more detailed onboarding instructions
- Can show what to expect over 30 days
- Can add support info
- Can track conversion with thank you page view

### 3.2 - Create Thank You Page

**Pages → Add New**

**Title:** `Welcome - You're In!`
**Permalink:** `/welcome` or `/thank-you`

**Template:** Full Width

### 3.3 - Thank You Page Content

```html
<div style="max-width: 700px; margin: 0 auto; text-align: center; padding: 40px 20px;">

<h1>🎉 Welcome to the 30-Day Recall Transformation!</h1>

<div style="background: #d1fae5; padding: 30px; border-radius: 8px; margin: 30px 0;">
<h2 style="color: #065f46; margin-top: 0;">✅ Your Purchase is Complete</h2>
<p style="color: #065f46; font-size: 18px;">Check your email in the next 5 minutes for your first lesson.</p>
</div>

<hr style="margin: 40px 0;">

<h2>What Happens Next?</h2>

<div style="text-align: left; margin: 30px 0;">

<div style="margin: 20px 0;">
<strong>📧 In the next 5 minutes:</strong><br>
You'll receive your welcome email with your first lesson. It explains why your smart dog suddenly stopped listening (hint: it's not stubbornness).
</div>

<div style="margin: 20px 0;">
<strong>📅 Over the next 30 days:</strong><br>
You'll receive 19 email lessons every 1-2 days. Each one builds on the last, giving you specific exercises to practice. No overwhelm—just steady progress.
</div>

<div style="margin: 20px 0;">
<strong>🐕 By Day 30:</strong><br>
You'll have a dog who comes when called—even with squirrels, other dogs, and real-world distractions. No more backyard standoffs.
</div>

</div>

<hr style="margin: 40px 0;">

<h2>⚠️ Important: Make Sure You Get All Emails</h2>

<div style="background: #fef3c7; padding: 20px; border-radius: 8px; margin: 20px 0; text-align: left;">
<p><strong>To ensure all lessons reach your inbox:</strong></p>
<ol>
<li>Check your email right now for the welcome message</li>
<li>If it's in Spam/Promotions, drag it to your Primary inbox</li>
<li>Add <strong>[your-email@domain.com]</strong> to your contacts</li>
<li>Mark the email as "Not Spam" if needed</li>
</ol>
<p><em>This ensures you get all 19 lessons on schedule.</em></p>
</div>

<hr style="margin: 40px 0;">

<h2>Need Help?</h2>

<p>Questions about the course or not seeing your welcome email?<br>
Email us: <strong>[support-email@domain.com]</strong><br>
We typically respond within 24 hours.</p>

<hr style="margin: 40px 0;">

<p style="color: #6b7280; font-size: 14px;">
© 2025 Down 4 Paws Dog Training. All rights reserved.
</p>

</div>
```

**Publish page**

Then go back to MemberPress membership settings and select this page as the Thank You Page.

---

## STEP 4: LINK LANDING PAGE CTAs TO CHECKOUT

### 4.1 - Landing Page CTA Buttons

In your Avada landing page, you have multiple CTA buttons:
- Hero button (above fold)
- Post-curriculum button
- Pricing section button
- Final CTA button
- Sticky header button

**All of these should link to:** `/checkout`

### 4.2 - Configure Button Links in Avada

**For each button element:**

1. Select the button in Avada Live Builder
2. Click **Link** settings
3. **URL:** Enter your checkout page URL
   - If using relative URL: `/checkout`
   - If using full URL: `https://yourdomain.com/checkout`
4. **Target:** Same window (not new tab)
5. **Button Text Examples:**
   - "Join First 50 at $97"
   - "Yes! Fix My Dog's Recall - $97"
   - "Complete Purchase - $97"
   - "Claim Early Bird Pricing"

### 4.3 - Add Tracking (Optional but Recommended)

**To track which buttons get clicked:**

Add onclick tracking to buttons:

```javascript
onclick="gtag('event', 'click', {
  'event_category': 'CTA',
  'event_label': 'Hero Button - Checkout'
});"
```

Different label for each button:
- Hero Button - Checkout
- Curriculum Button - Checkout
- Pricing Button - Checkout
- Final Button - Checkout

This lets you see in Google Analytics which button drives most conversions.

---

## STEP 5: CONFIGURE MEMBERPRESS PAYMENT OPTIONS

### 5.1 - Enable Square

1. **MemberPress → Settings → Payments**
2. Click **+** to add payment method
3. Select **Square**
4. If not installed, install Square addon first
5. Click **Connect to Square**
6. Log into Square account
7. Authorize MemberPress
8. Select business location
9. **Gateway Name:** "Credit or Debit Card"
10. **Icon:** Card icon (displays on checkout)
11. **Test Mode:** Enable for testing, disable for live
12. **Save**

### 5.2 - Enable PayPal

1. **MemberPress → Settings → Payments**
2. Click **+** to add payment method
3. Select **PayPal Commerce Platform** (NOT PayPal Standard)
   - This is critical - Commerce Platform has Apple Pay, Google Pay, Venmo
4. Click **Connect to PayPal**
5. Log into PayPal business account
6. Authorize MemberPress
7. **Gateway Name:** "PayPal, Venmo, Apple Pay, Google Pay"
8. **Payment Options:** Enable all:
   - ✅ Credit/Debit Cards
   - ✅ PayPal
   - ✅ PayPal Pay Later
   - ✅ Venmo
   - ✅ Apple Pay
   - ✅ Google Pay
9. **Test Mode:** Enable for testing (PayPal Sandbox)
10. **Save**

### 5.3 - Set Payment Method Order

**In MemberPress → Settings → Payments:**

Drag to reorder (what customers see first):
1. PayPal (most popular, appears first)
2. Square (backup for those who don't use PayPal)

**Why this order:**
- PayPal One Touch converts at 88.7%
- Most people prefer PayPal for online purchases
- Square available as fallback

---

## STEP 6: CUSTOMIZE CHECKOUT PAGE APPEARANCE

### 6.1 - MemberPress Form Styling

**MemberPress → Settings → General → Styling**

Choose styling options:
- Form field style
- Button colors
- Layout (vertical recommended for mobile)

**Or use custom CSS:**

```css
/* Checkout page custom styles */
.mepr-signup-form {
    max-width: 600px;
    margin: 0 auto;
    padding: 20px;
}

.mepr-payment-methods-wrapper {
    margin: 30px 0;
}

.mepr-payment-method {
    border: 2px solid #e5e7eb;
    border-radius: 8px;
    padding: 20px;
    margin: 10px 0;
    cursor: pointer;
    transition: border-color 0.2s;
}

.mepr-payment-method:hover {
    border-color: #2563eb;
}

.mepr-payment-method.mepr-selected-payment-method {
    border-color: #2563eb;
    background: #eff6ff;
}

.mepr-submit {
    background: #2563eb;
    color: white;
    padding: 16px 32px;
    border: none;
    border-radius: 8px;
    font-size: 18px;
    font-weight: bold;
    cursor: pointer;
    width: 100%;
    margin-top: 20px;
}

.mepr-submit:hover {
    background: #1d4ed8;
}
```

**Add this CSS:**
- **Appearance → Customize → Additional CSS**
- Or in your theme's custom CSS area

### 6.2 - Minimize Required Fields

**MemberPress → Settings → Registration**

**Required Fields:**
- ✅ Email (always required)
- ❌ Username (remove if possible)
- ❌ Password (MemberPress generates one automatically)
- ❌ First Name (optional)
- ❌ Last Name (optional)

**Goal:** Email + payment only

**The fewer fields, the higher conversion.**

### 6.3 - Mobile Optimization

Test checkout on mobile:
- Buttons thumb-sized (min 44px height)
- Form fields full-width
- Payment options stack vertically
- No horizontal scrolling
- PayPal button renders properly
- Square form is mobile-friendly

---

## STEP 7: TEST THE COMPLETE FLOW

### 7.1 - Enable Test Modes

**Square Test Mode:**
- MemberPress → Settings → Payments → Square
- Enable "Sandbox Mode"
- Use Square test card: 4111 1111 1111 1111

**PayPal Test Mode:**
- MemberPress → Settings → Payments → PayPal
- Enable "Sandbox Mode"
- Use PayPal sandbox account

### 7.2 - Test Purchase Flow

**Test #1: Square Payment**
1. Go to landing page
2. Click CTA button
3. Should redirect to /checkout
4. Fill out form (test email)
5. Select Square payment method
6. Enter test card: 4111 1111 1111 1111
   - Expiry: Any future date
   - CVV: Any 3 digits
7. Click "Complete Purchase"
8. Should redirect to thank you page
9. Check test email for:
   - MemberPress confirmation
   - Kit welcome email
   - Kit first lesson

**Test #2: PayPal Payment**
1. Go to landing page
2. Click different CTA button
3. Should redirect to /checkout
4. Fill out form (different test email)
5. Select PayPal payment method
6. Click PayPal button
7. Log into PayPal sandbox account
8. Complete payment
9. Should return to thank you page
10. Check test email for confirmations

**Test #3: Mobile**
- Repeat Test #1 on iPhone
- Repeat Test #2 on Android
- Check Apple Pay shows (via PayPal)
- Check Google Pay shows (via PayPal)

### 7.3 - Verify Kit Integration

**After test purchase:**
1. Go to Kit dashboard
2. Check Subscribers list
3. Test subscriber should be there
4. Should have tag: (whatever you configured)
5. Should be in sequence: "30-Day Recall Course"
6. Check Automations to verify it triggered

**If not working:**
- Check MemberPress → Settings → Integrations → Kit
- Verify connection is active
- Re-authorize if needed
- Check mapping: Membership → Kit Tag

---

## STEP 8: GO LIVE

### 8.1 - Disable Test Modes

**Square:**
- MemberPress → Settings → Payments → Square
- Disable "Sandbox Mode"
- Save

**PayPal:**
- MemberPress → Settings → Payments → PayPal
- Disable "Sandbox Mode"
- Save

### 8.2 - Final Test with Real Payment

**Important:** Do one final test with real payment, then refund it.

1. Make real purchase with your credit card ($97)
2. Verify entire flow works with live payment processors
3. Check real email receives all messages
4. Then refund the test purchase:
   - Square: Refund from Square dashboard
   - PayPal: Refund from PayPal dashboard

### 8.3 - Launch Checklist

- [ ] Landing page published and live
- [ ] Checkout page published and live
- [ ] Thank you page published and live
- [ ] All CTA buttons link to checkout
- [ ] Square live mode enabled
- [ ] PayPal live mode enabled
- [ ] Kit integration verified working
- [ ] Mobile checkout tested
- [ ] One real transaction tested and refunded
- [ ] Google Analytics tracking set up
- [ ] Support email mentioned in thank you page

---

## STEP 9: EARLY BIRD PRICING MANAGEMENT

### 9.1 - Track Sales Manually

**Create simple spreadsheet:**

| Sale # | Date | Name | Email | Amount | Payment Method |
|--------|------|------|-------|--------|----------------|
| 1 | 1/15 | John | john@... | $97 | PayPal |
| 2 | 1/15 | Sarah | sarah@... | $97 | Square |

**Or use MemberPress reports:**
- MemberPress → Transactions
- Filter by membership
- Count total sales

### 9.2 - When You Hit 50 Sales

**Update the price:**

1. **MemberPress → Memberships**
2. Edit "30-Day Recall Course"
3. Change price: $97 → $147
4. Save

**Update all landing page copy:**
5. Change notice bar: "Early bird sold out! Now $147"
6. Update all CTA buttons: "Join at $147" (remove "Save $50")
7. Update pricing section to remove early bird language
8. Update checkout page price callout

### 9.3 - Announce Price Change

**Email your list:**
```
Subject: Early bird pricing sold out 🎉

We just enrolled our 50th student in the 30-Day Recall Transformation!

Early bird pricing ($97) has officially ended.

The course is now $147 - still a fraction of the cost of private training, and you get the complete system that's helped 50+ dog owners transform their recall.

Ready to join? [Link to checkout]
```

**Post on social media:**
"50 dog owners are transforming their recall! Early bird pricing has ended. Course now $147."

---

## STEP 10: MONITOR & OPTIMIZE

### 10.1 - Key Metrics to Watch

**In Google Analytics (or similar):**
- Landing page views
- Checkout page views
- Thank you page views (= conversions)
- Conversion rate: Thank you views ÷ Landing page views

**In MemberPress:**
- Total sales
- Revenue
- Failed transactions (troubleshoot these)

**In Kit:**
- Course enrollment (should match MemberPress sales)
- Email open rates
- Click-through rates

### 10.2 - Common Issues & Fixes

**Problem: High checkout abandonment**
- Check mobile experience
- Reduce form fields
- Test both payment methods work
- Speed up page load time

**Problem: Customers don't receive course emails**
- Check Kit automation is active
- Verify MemberPress → Kit integration
- Check customer's email in Kit subscribers
- Look for bounced emails

**Problem: Payment fails**
- Check Square/PayPal live modes enabled
- Verify payment accounts active
- Check for declined cards
- Ensure no minimums/maximums set wrong

### 10.3 - Optimization Ideas (After 30+ Sales)

**A/B test:**
- Different CTA button text
- Payment method order (PayPal first vs Square first)
- Checkout page headline
- Number of trust elements on checkout

**Survey abandoners:**
- Add exit-intent popup: "What stopped you from purchasing?"
- Email people who viewed checkout but didn't buy
- Ask: "What questions do you have?"

---

## TROUBLESHOOTING GUIDE

### Landing Page → Checkout Issues

**Problem:** CTA button doesn't go to checkout
- **Fix:** Check button link URL is correct (`/checkout`)
- **Fix:** Clear cache (Avada, WordPress, browser)
- **Fix:** Check checkout page is published (not draft)

**Problem:** Checkout page shows 404
- **Fix:** Go to Settings → Permalinks, click Save (refreshes URLs)
- **Fix:** Check page wasn't accidentally trashed

### Payment Processing Issues

**Problem:** Square doesn't show on checkout
- **Fix:** MemberPress → Settings → Payments, verify Square enabled
- **Fix:** Check Square connection still active
- **Fix:** Reconnect Square if needed

**Problem:** PayPal doesn't show on checkout
- **Fix:** Verify using PayPal Commerce Platform (not Standard)
- **Fix:** Check PayPal connection active
- **Fix:** Reconnect PayPal if needed

**Problem:** Payment fails at checkout
- **Fix:** Check test mode is disabled (if live)
- **Fix:** Verify payment account has no issues
- **Fix:** Test with different card

### MemberPress → Kit Integration Issues

**Problem:** Customer purchases but doesn't receive course
- **Fix:** Check Kit automation is active
- **Fix:** Verify webhook in MemberPress → Settings → Integrations
- **Fix:** Manually trigger: Add customer to Kit sequence
- **Fix:** Check customer email isn't bouncing

**Problem:** Duplicate emails send
- **Fix:** Check only one automation triggers on purchase
- **Fix:** Verify customer isn't manually added to sequence also

---

## ADDITIONAL RESOURCES

### MemberPress Documentation
- [MemberPress Square Setup](https://memberpress.com/docs/square/)
- [MemberPress PayPal Setup](https://memberpress.com/docs/paypal-commerce-platform/)
- [Kit Integration](https://memberpress.com/docs/convertkit-automations-with-memberpress/)

### Support Contacts
- MemberPress Support: support@memberpress.com
- Kit Support: help.kit.com
- Square Support: squareup.com/help
- PayPal Support: paypal.com/help

---

## SUMMARY CHECKLIST

**Setup Complete When:**
- [ ] MemberPress membership created ($97, one-time)
- [ ] Checkout page created with MemberPress shortcode
- [ ] Thank you page created with onboarding instructions
- [ ] Square connected and enabled
- [ ] PayPal Commerce Platform connected (with Apple/Google Pay)
- [ ] Kit integration verified working
- [ ] Landing page CTAs all link to /checkout
- [ ] Mobile checkout tested
- [ ] Test purchases completed (Square + PayPal)
- [ ] Kit automation verified triggering
- [ ] All test transactions refunded
- [ ] Test modes disabled
- [ ] One final real purchase tested and refunded
- [ ] Landing page published
- [ ] Ready to launch!

---

**Estimated Total Setup Time: 3-4 hours**

This includes:
- MemberPress configuration: 1 hour
- Page creation (checkout + thank you): 1 hour
- Payment processor setup: 1 hour
- Testing: 1 hour

Since your Kit integration is already working, you're just adding the WordPress pages and payment processors.

Good luck with launch! 🚀
