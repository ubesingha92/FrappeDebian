# **Frappe Framework Installation (Version 15) on Debian 12**

A complete step-by-step guide to install **Frappe Framework** on Debian 12.

---

## **STEP 1: Install Git, Python, and Redis**

```bash
sudo apt install git python-is-python3 python3-dev python3-pip redis-server libmariadb-dev mariadb-server mariadb-client pkg-config
```

---

## **STEP 2: Install Virtual Environment**

```bash
sudo apt install -y python3-venv
```

---

## **STEP 3: Install MariaDB**

```bash
sudo apt-get install software-properties-common
sudo apt install mariadb-server
sudo systemctl status mariadb
sudo mysql_secure_installation
```

### **MariaDB Secure Installation Prompts**

* Press **Enter** for the current root password (if fresh install)
* Switch to unix\_socket authentication: **Y**
* Change root password: **Y** (set a strong password)
* Remove anonymous users: **Y**
* Disallow root login remotely: **Y**
* Remove test database: **Y**
* Reload privilege tables: **Y**

---

## **STEP 9: Install Node.js 18.x**

```bash
sudo apt install curl 
curl https://raw.githubusercontent.com/creationix/nvm/master/install.sh | bash
source ~/.profile
nvm install 18
```

---

## **STEP 10: Install Yarn**

```bash
sudo apt-get install npm
sudo npm install -g yarn
```

---

## **STEP 11: Install wkhtmltopdf**

```bash
sudo apt-get install xvfb libfontconfig wkhtmltopdf
```

---

## **STEP 12: Install Frappe Bench**

```bash
pip install frappe-bench --break-system-packages
```

### **Add Frappe Bench to PATH (Temporary)**

```bash
export PATH=$PATH:/home/chanaka/.local/bin
```

Check installation:

```bash
bench --version
```

---

## **STEP 13: Initialize Frappe Bench**

```bash
bench init frappe-bench
cd frappe-bench/
bench start
```

---

## **STEP 14: Create a Site in Frappe Bench**

> **Note:** MariaDB version `10.11.7` is newer than `10.8` and not officially tested with Frappe Framework.

```bash
bench new-site llink.wyb.ac.lk
bench --site llink.wyb.ac.lk add-to-hosts
```

### **Host Configuration**

* **Debian:**

  ```bash
  sudo nano /etc/hosts
  ```
* **Windows:**
  Navigate to:

  ```
  C:\Windows\System32\drivers\etc\
  ```

  Edit the `hosts` file.

Open in browser:

```
http://llink.wyb.ac.lk:8000
```

---

## **STEP 15: Install Your App**

```bash
bench new-app [app name]
```

---

## **STEP 16:Install your app on the site**

```bash
bench --site llink.wyb.ac.lk install-app llink
```


---

### ✅ You now have Frappe Framework (v15) installed and ready to use on Debian 12!

---
