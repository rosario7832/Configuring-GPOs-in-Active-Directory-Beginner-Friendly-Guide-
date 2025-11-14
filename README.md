# 🖥️ Configuring GPOs in Active Directory (Beginner-Friendly Guide)

When a company has many computers, it’s not practical to configure each one manually.  
To solve this, Active Directory uses **GPOs (Group Policy Objects)** — rules created on the server that automatically apply to all computers or users in the domain.

This saves time and ensures that everyone follows the same security settings.

---

# 🛠️ How to Create and Link a GPO (Step-by-Step)

1. On your server, open **Server Manager**.
2. In the top-right corner, click **Tools**.
3. Select **Group Policy Management**.
4. In the left panel, find your domain (e.g., *mydomain.com*).
5. Right-click the domain name and select:  
   **Create a GPO in this domain, and Link it here**.
6. Give the GPO a clear and simple name, such as:  
   **“GPO – Security”**.

<img src="https://i.imgur.com/wHesJws.png" height="55%" width="60%"/> 

> 💡 **Tip:** Using descriptive names helps you quickly identify the purpose of each GPO when you have many of them.

---

# 🔐 Configuring Security Policies

These settings help protect user accounts by requiring strong passwords and preventing unauthorized access attempts.

1. Right-click the GPO you created (**GPO – Security**) and select **Edit**.
2. Navigate to:
Computer Configuration → Policies → Windows Settings → Security Settings → Account Policies

<img src="https://i.imgur.com/TJNiPvH.png" height="55%" width="60%"/> 

Here you will configure three important policies:

# Password Policies
### 1️⃣ Minimum password length  
Defines the minimum number of characters a password must have.  
✔ Recommended: **8 characters**.

<img src="https://i.imgur.com/aCj2nbU.png" height="55%" width="60%"/> 

### 2️⃣ Password must meet complexity requirements  
Requires passwords to include a combination of:
- Uppercase letters  
- Lowercase letters  
- Numbers  
- Symbols

<img src="https://i.imgur.com/aoYWDF7.png" height="55%" width="60%"/> 

# Account Lockup Policy
### 3️⃣ Account lockout threshold  
Locks the user account temporarily after several incorrect login attempts.  
✔ Set it to lock the account after **5 failed attempts**.

After configuring **Account lockout threshold**, you will also need to configure the following settings:

### 🔹 Account lockout duration  
This defines how long (in minutes) an account remains locked before it automatically unlocks.

### 🔹 Allow administrator account lockout  
This option determines whether the built-in Administrator account can be locked out.  
> Recommended: **Disable**, to avoid locking out critical admin accounts.

### 🔹 Reset account lockout counter after  
This defines how long the system waits (in minutes) before the failed login attempt counter resets back to zero.

<img src="https://i.imgur.com/IZU45rR.png" height="55%" width="60%"/> 

---
