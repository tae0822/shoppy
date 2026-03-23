# Shoppy 
**Shoppy** is a robust E-commerce solution built with React and Firebase, focusing on **Role-Based Access Control (RBAC)** and persistent global state synchronization.

[![Tech Stack](https://img.shields.io/badge/React-Ready-blue)](https://reactjs.org/)
[![Firebase](https://img.shields.io/badge/Backend-Firebase-orange)](https://firebase.google.com/)
[![React Query](https://img.shields.io/badge/State-React_Query-red)](https://tanstack.com/query/latest)

---

## 💡 Why I Built This
E-commerce applications are the ultimate test for **State Management** and **Data Integrity**. I built **Shoppy** to master the complexities of a real-world digital storefront:
- **Role-Based Logic**: Differentiating the user experience between a regular Customer and an authorized Admin.
- **Data Persistence**: Ensuring that a user's shopping journey (cart, preferences) remains consistent across sessions.
- **Server-State Sync**: Minimizing the gap between the cloud database (Firebase) and the UI to prevent stale data.

## 🛠 Strategic Engineering Choices

### 1. Persistent Global State (Firebase + React Query)
Instead of relying on fragile local state, I implemented a robust synchronization strategy.
- **Result**: By leveraging **React Query**'s caching mechanisms combined with **Firebase Realtime Database**, I achieved a "Single Source of Truth." 
- **Impact**: Shopping cart data persists even if the user refreshes the page or switches devices, significantly improving the conversion UX.

### 2. Role-Based Access Control (RBAC) Architecture
Security isn't just about hiding buttons; it's about structural protection.
- **Admin Dashboard**: Developed a secure administrative interface accessible only via specific UID verification.
- **Route Guarding**: Implemented **Protected Routes** that intercept unauthorized access attempts at the component level, ensuring administrative functions are technically inaccessible to regular users.

### 3. Optimized Image & Data Pipeline
- **Categorization**: Engineered a dynamic filtering system that allows users to browse products by specific metadata (Category, Gender).
- **Efficiency**: Reduced unnecessary re-renders by centralizing cart logic within a custom **Context Provider**, ensuring smooth UI transitions during updates.

## 🔥 Critical Problem Solving

### Case Study: Solving the Stale Data Conflict
**Context**: During early development, the "Add to Cart" action often resulted in a lag where the UI didn't reflect the new item count immediately, or showed outdated prices.

**Analysis**: Manual `useEffect` fetching was creating race conditions between the client-side state and the Firebase backend.

**Resolution**: 
- Migrated the entire data flow to **TanStack Query (React Query)**.
- Implemented **Query Invalidation** strategies: whenever a cart action occurs, the `cart` query is immediately marked as stale and refetched.
- **Outcome**: Achieved a 100% data synchronization rate between the cloud database and the user interface without manual page reloads.

## 🎬 Project Showcase

#### ✅ Admin Product Management
*Authorized admin interface for uploading and managing the product catalog.*
<img src="https://github.com/user-attachments/assets/972b071b-678c-42aa-9d72-9da3cc0be794" width="100%" />

---

#### ✅ Seamless Shopping Experience
*Dynamic product filtering, detailed views, and persistent shopping cart.*
<img src="https://github.com/user-attachments/assets/805d07dc-7d34-43b2-9ff6-0f10c8973977" width="100%" />

---

## 📊 Technical Specs & Growth
- **Backend**: Firebase Realtime Database & Authentication.
- **State Management**: React Query for server state, Context API for UI state.
- **Future Scale**: Planning to integrate **Stripe API** for secure payment processing and **Firebase Cloud Functions** for server-side inventory validation.

---
[Live Demo](https://shoppy-peach.vercel.app) | [GitHub Repo](https://github.com/tae0822/shoppy)
