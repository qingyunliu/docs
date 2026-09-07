# SaaS Platform Security Overview

## Overview

This document describes the security controls implemented in the HyperBDR and HyperMotion SaaS platform, including data protection, identity authentication, access control, infrastructure security, and security operations\.

For simplicity, this document uses "the Platform" to refer to the HyperBDR and HyperMotion SaaS services\.

The Platform is operated by OnePro and provides enterprise users with backup, disaster recovery, and data migration services\.

The Platform follows a Security by Design approach, integrating security considerations into its architecture, data processing workflows, and daily operations\.

For enterprise data protection scenarios, the Platform focuses on the following security objectives:

- Protect customer business data during transmission and storage;

- Prevent unauthorized access and operations;

- Reduce direct exposure of customer production data within the Platform;

- Maintain service availability and business continuity\.

The Platform adopts a Control Flow and Data Flow separated architecture:

- The Control Flow is responsible for user management, permission control, task orchestration, resource management, status monitoring, and operational management;

- The Data Flow is responsible for transferring customer business data between source environments and target environments;

- The SaaS platform does not act as a storage or relay point for customer business data\.

This architecture reduces the Platform's direct exposure to customer production data and improves overall data security\.

---

# Data Security

The Platform follows data security and data minimization principles to protect customer data through secure data transmission, storage protection, and lifecycle management\.

## 2\.1 Data Transmission Security

The Platform protects data transmission channels during backup, recovery, and migration operations\.

Key security measures include:

- Customer data is protected through encryption during transmission;

- AES\-256 encryption is used for data protection;

- Sensitive information exchanged through APIs is encrypted to prevent unauthorized access\.

The Platform uses a Control Flow and Data Flow separated architecture:

- The Control Flow manages tasks, resources, and operational status;

- The Data Flow is responsible for actual data transfer between customer source environments and target environments;

- Customer production data is not stored or relayed by the SaaS platform\.

This architecture reduces exposure of customer business data and improves transmission security\.

---

## 2\.2 Data Storage Security

The Platform follows the principle of data minimization and stores only the information required for service operation\.

The Platform mainly stores:

- Task configuration data;

- Resource information;

- Service status information;

- Operation records;

- Other required service metadata\.

Customer business data is stored in customer\-owned environments or customer\-designated target storage resources according to different business scenarios\.

The Platform applies appropriate protection measures for different storage scenarios:

- For object storage scenarios, data is stored in encrypted format;

- For block storage scenarios, data is decrypted and restored directly to the target environment storage resources;

- Sensitive information stored in Platform databases is encrypted\.

The underlying storage security capabilities are provided through enterprise\-grade public cloud infrastructure, including storage protection, access control, and infrastructure security capabilities\.

---

## 2\.3 Data Lifecycle Management

The Platform manages the data lifecycle, including data retention, maintenance, and deletion\.

Key measures include:

- Defining data retention policies based on operational requirements;

- Managing Platform metadata through controlled processes;

- Performing data deletion according to established procedures;

- Preventing unauthorized access, modification, or deletion of data\.

---

# Identity Authentication and Access Control

The Platform uses role\-based access control \(RBAC\) to ensure users can only access and perform operations within their authorized scope\.

## 3\.1 User Roles and Permission Management

The Platform supports three user roles:

### Tenant Administrator

The Tenant Administrator has the highest level of management permissions, including:

- Tenant management;

- User management;

- Platform configuration management;

- Administrative operations\.

### Operator User

The Operator User has business operation permissions, including:

- Business configuration;

- Task management;

- Related operational activities\.

The Operator User does not have full administrative privileges\.

### Read\-only User

The Read\-only User can only view relevant information, including:

- Task status;

- Resource information;

- Operation results\.

The Read\-only User cannot perform modification or administrative operations\.

Through role separation, the Platform applies the principle of least privilege and reduces the risk of misuse or unauthorized operations\.

---

## 3\.2 Identity Authentication Security

The Platform uses identity authentication mechanisms to protect user accounts\.

Security measures include:

- User identity authentication;

- Role\-based access control;

- Administrative access protection;

- Login and operation auditing\.

The Platform continuously improves identity security capabilities and provides enhanced authentication mechanisms based on enterprise customer security requirements\.

---

## 3\.3 Operation Audit

The Platform provides audit logging capabilities to record important operational activities\.

Audit records include:

- User login activities;

- User operation activities;

- Permission changes;

- Important configuration changes\.

Audit logs support security review, analysis, and issue investigation\.

---

# Platform Infrastructure Security

The Platform is deployed on enterprise\-grade public cloud infrastructure and uses native cloud security capabilities to protect the operating environment\.

## 4\.1 Cloud Infrastructure Security

The Platform environment includes:

- Cloud computing resources;

- Cloud database services;

- Cloud storage services;

- Network security components\.

The underlying cloud infrastructure provides:

- Physical data center security;

- Network isolation capabilities;

- Identity and access control;

- Infrastructure monitoring;

- Security protection capabilities\.

---

## 4\.2 Environment Isolation

The Platform maintains isolation between different environments, including:

- Production environment;

- Development environment;

- Testing environment\.

Environment isolation prevents development and testing activities from affecting production services and improves platform stability\.

---

## 4\.3 Network Security

The Platform uses a secure network architecture:

- Core services such as databases and middleware are not directly exposed to the public internet;

- Internal services communicate through internal networks;

- External access interfaces are controlled through authentication mechanisms;

- Network access follows the principle of least privilege\.

These controls reduce the risk of unauthorized access\.

---

## 4\.4 Vulnerability and Patch Management

The Platform continuously performs security maintenance activities, including:

- Operating system security updates;

- Software component security maintenance;

- Known vulnerability fixes;

- Platform version upgrades\.

These activities help reduce known security risks\.

---

# Security Operations and Monitoring

The Platform maintains continuous security operations to monitor system status and security events\.

## 5\.1 System Monitoring

The Platform monitors:

- Service availability;

- System logs;

- Application logs;

- Abnormal events\.

Monitoring helps identify potential issues and maintain stable service operation\.

---

## 5\.2 Security Log Management

The Platform records security\-related logs, including:

- User access logs;

- Login logs;

- Administrative operation logs;

- System security events\.

Logs support security analysis, anomaly detection, and issue investigation\.

---

## 5\.3 Data Backup and Disaster Recovery

The Platform maintains backup mechanisms for critical system data, including:

- Platform configuration data;

- Service metadata;

- System operation data\.

In the event of system failure or disaster, backup data can be used to restore services and maintain SaaS service continuity\.

At the same time, because the Platform uses a Control Flow and Data Flow separated architecture, customer business data is mainly stored in customer\-owned environments or customer\-designated target storage environments\.

A Platform service failure does not directly affect the integrity of customer original data:

- Customer production data is not stored as internal SaaS platform data;

- Customer business data is protected by the customer's own storage environment according to their data protection policies;

- The Platform mainly provides business management, task orchestration, and operational status management\.

This architecture reduces the impact of a single SaaS platform failure on customer data security\.

---

# Security Assurance

The Platform is built on enterprise\-grade public cloud infrastructure and follows commonly adopted information security practices\.

The Platform provides security controls to protect customer data and business operations, including:

- Data encryption protection;

- Identity authentication and access control;

- Network isolation;

- Operation auditing;

- Security monitoring;

- Data backup and recovery\.

The underlying infrastructure platform provides enterprise\-level security capabilities, including:

- Infrastructure protection;

- Data security capabilities;

- Network security capabilities;

- Access control capabilities\.

The Platform continuously improves security controls based on customer requirements and industry security practices\.

---

# Data Flow Security Architecture

The Platform adopts a Control Flow and Data Flow separated architecture\.

## Control Flow

The Control Flow is responsible for:

- User management;

- Permission control;

- Task orchestration;

- Resource management;

- Status monitoring;

- Operation auditing\.

## Data Flow

The Data Flow is responsible for:

- Customer business data transfer;

- Data backup;

- Data recovery\.

During service execution:

- Data transfer channels are established between customer source environments and target environments;

- Data is encrypted during transmission according to security policies;

- The SaaS platform provides control and management functions and does not store customer production data\.

This architecture provides SaaS management capabilities while reducing exposure of customer core business data\.

