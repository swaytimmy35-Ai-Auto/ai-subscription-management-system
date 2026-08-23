# AI Subscription Management System
An automated subscription management system designed for membership-based businesses.
The system manages the subscription lifecycle from customer registration through renewal, reminders, and expiration. It integrates a website form with n8n, Airtable, JavaScript, and email automation to reduce manual administration and maintain accurate subscription records.
**Tech Stack:** `n8n` · `Airtable` · `JavaScript` · `Webhooks` · `Gmail` · `Vibecoding`
---
## 📌 Problem
Managing subscriptions manually can lead to:
- Duplicate customer registrations
- Missed renewals
- Incorrect or inconsistent subscription records
- Delayed customer notifications
- Manual calculation of renewal and expiry dates
- Difficulty monitoring active and expired subscriptions
- Limited visibility into subscription activity
Businesses need a system that keeps subscription information accurate while reducing repetitive administrative work.
---
## 🎯 Objectives
The system was designed to:
- Automate customer registration
- Prevent duplicate registrations
- Track subscription status
- Automatically calculate subscription and renewal dates
- Send professional customer email notifications
- Automate subscription renewals
- Maintain a centralized admin dashboard
- Handle workflow errors and failures
- Reduce manual subscription-management work
---
## 💡 Solution
Customers submit their information through a website form connected to an **n8n webhook**.
The workflow validates the submission and searches Airtable for an existing customer record.
If the customer is new, a subscription record is created and the appropriate subscription dates and status are calculated.
If the customer already exists, the system follows the renewal flow instead of creating another registration.
JavaScript is used for dynamic date calculations, while Airtable serves as the central subscription database.
Automated email workflows handle registration confirmations, renewal confirmations, expiry reminders, and expiration notifications.
A dedicated error workflow captures failed executions and sends notifications for troubleshooting.
An admin dashboard provides visibility into customer and subscription status.
---
## 🏗️ Workflow Architecture
### Customer Registration
```
Customer
   ↓
Website Registration Form
   ↓
n8n Webhook
   ↓
Validate Submission
   ↓
Search Airtable by Email
   ↓
Existing Customer?
   ↙              ↘
 No                Yes
 ↓                  ↓
Create Customer    Renewal Flow
Record              ↓
 ↓             Calculate New
Calculate Dates   Expiry Date
 ↓                  ↓
Set Status       Update Record
 ↓                  ↓
Registration      Renewal
Confirmation      Confirmation
```
### Subscription Renewal
```
Existing Customer
       ↓
Renewal Trigger
       ↓
Find Subscription
       ↓
JavaScript Date Calculation
       ↓
Calculate New Expiry Date
       ↓
Update Subscription Status
       ↓
Update Airtable Record
       ↓
Send Renewal Confirmation

Subscription Notifications

Subscription Lifecycle
        ↓
┌───────┼────────┬─────────────┐
↓       ↓        ↓             ↓
Registration   Renewal    Expiry Reminder
Confirmation   Confirmation      ↓
                              Expiration
                               Notice
```
### Error Handling
```
Any Workflow
     ↓
Execution Failure
     ↓
Error Workflow
     ↓
Capture Error Details
     ↓
Send Troubleshooting
Notification
```
⸻

🛠️ Technologies Used

Technology	Purpose
n8n	Workflow automation and orchestration
Airtable	Customer database and subscription management
JavaScript	Dynamic subscription and renewal date calculations
Webhooks	Communication between the website and automation workflows
Gmail	Automated customer and administrative email notifications
Vibecoding	Website and testing interface development

⸻

🧠 Core Features

Automated Registration

Customers can register through a website form, triggering the subscription workflow automatically.

Duplicate Registration Detection

The system checks Airtable for an existing customer before creating a new record.

Automatic Subscription Renewal

Existing customers can enter the renewal flow without creating duplicate subscription records.

Dynamic Date Calculation

JavaScript calculates subscription and renewal dates based on the customer’s subscription period.

Subscription Status Automation

Customer records are automatically updated based on their subscription lifecycle.

Automated Email Notifications

The system sends professional emails for:

- Registration confirmation
- Renewal confirmation
- Upcoming expiry
- Subscription expiration

Admin Dashboard

Airtable provides a centralized view of customer and subscription information for administrators.

Testing Payment Page

A simulated payment page was created to test the subscription and renewal workflow without requiring a live payment gateway.

Centralized Error Handling

A dedicated error workflow captures automation failures and sends notifications for troubleshooting.

⸻

🧩 Challenges Encountered

- Handling duplicate registrations without creating multiple customer records
- Correctly calculating renewal periods across different subscription plans
- Updating existing subscription records during renewals
- Managing workflow failures without interrupting the customer experience
- Keeping subscription status and dates synchronized across the automation
- Designing reliable notification logic throughout the subscription lifecycle

⸻

🔧 Improvements Made

- Added an admin dashboard
- Improved professional email templates
- Implemented duplicate registration handling
- Added automatic subscription renewal
- Added dynamic subscription date calculations
- Added centralized error handling
- Created a testing payment page
- Added automated expiry reminders
- Added automated expiration notifications
- Produced workflow documentation and a demonstration video

⸻

📊 Results

The completed system can automatically:

- Register new customers
- Detect existing registrations
- Create and update subscription records
- Calculate subscription and renewal dates
- Manage subscription status
- Process renewal flows
- Send registration and renewal confirmations
- Send expiry reminders
- Send expiration notifications
- Provide administrators with centralized subscription visibility
- Capture and report workflow errors

The result is an automated subscription-management system that reduces repetitive administrative work, improves record accuracy, and gives administrators better visibility into the customer subscription lifecycle.

⸻

📸 Screenshots

Screenshots demonstrating the registration interface, automation workflows, Airtable dashboard, payment testing flow, and email notifications will be added here.

⸻

🎥 Demo

A full walkthrough demonstrating customer registration, duplicate detection, subscription management, renewal automation, notifications, dashboard monitoring, and error handling will be linked here.

Demo: Coming soon

⸻

🔮 Future Improvements

- Stripe integration
- Paystack integration
- Flutterwave integration
- Customer self-service portal
- WhatsApp subscription reminders
- Advanced subscription analytics dashboard

⸻

📚 Key Learnings

- Webhook integrations
- Airtable database management
- JavaScript-based automation
- Subscription lifecycle design
- Workflow architecture
- Error handling
- Automated notification systems
- Building production-ready automation workflows

⸻

👤 Author

Okanlawon Abdulhammed

AI & Automation Builder

[LinkedIn](https://www.linkedin.com/in/okanlawon-a-o/)⁠￼
