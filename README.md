# 🚀 Ansible Infrastructure Automation

This repository contains Ansible playbooks and inventory configuration for provisioning and managing cloud infrastructure such as Kafka, NiFi, Spark, and HDFS.

> 🛡️ **Security First**: No IP addresses, usernames, or private key files are stored or exposed in this repository. All sensitive information is passed securely during execution.


## 🔐 Sensitive Data Handling

This project uses placeholders in the inventory file:

[new] my_vm ansible_host={{ HOST_IP }} ansible_user={{ HOST_USER }} ansible_ssh_private_key_file={{ SSH_KEY }}



You must pass values at runtime using one of the methods below.

---

## 🚀 Usage

### Option 1: Using Inline Variables

ansible-playbook -i inventory.ini playbook.yml
-e "HOST_IP=xxx.xxx.xxx.xxx HOST_USER=username SSH_KEY=./keys/my-key.pem"



### Option 2: Using a Local vars.yml File

`vars/host_vars.yml` (this file is not committed to Git):

HOST_IP: xxx.xxx.xxx.xxx HOST_USER: username SSH_KEY: ./keys/my-key.pem


Run the playbook with:

ansible-playbook -i inventory.ini playbook.yml -e "@vars/host_vars.yml"

---

## 📦 Features

- 🔄 Infrastructure provisioning for:
  - Apache Kafka
  - Apache NiFi
  - Apache Spark
  - Hadoop HDFS
- 🛡️ Secure handling of credentials
- 📁 Clean project structure for scaling and reuse

---

## 🧾 .gitignore

Key files and variables
.pem keys/ vars/.yml



---

## 🙌 Contributing

Feel free to fork, raise issues, or submit PRs to improve the automation.

---

## 🛡 License

MIT License. Feel free to use and modify.
