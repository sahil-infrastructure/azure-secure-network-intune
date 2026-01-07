# Azure Network & Security Infrastructure using Terraform

## Project Status

✅ **Completed** – Infrastructure design and security layer implemented using Terraform.

This project intentionally focuses on **Azure networking and security infrastructure**.
The compute layer (virtual machines) was evaluated but excluded due to **Azure Free Trial
quota and regional capacity restrictions**, which were investigated and documented as part
of real-world cloud constraints.

---

## Project Overview

This project demonstrates how **Azure network infrastructure and security controls**
can be designed, provisioned, and managed using **Infrastructure as Code (IaC) with Terraform**.

Rather than focusing on application deployment, the goal of this project is to build a
**strong, production-aligned foundation** consisting of virtual networking, subnet
segmentation, and network security rules — components that are commonly designed and
validated independently in real infrastructure projects.

---

## What This Project Demonstrates

- Infrastructure as Code (IaC) using Terraform
- Azure Resource Group design
- Azure Virtual Network (VNet) creation
- Subnet segmentation
- Network Security Group (NSG) implementation
- Inbound security rule configuration
- Subnet-level security association
- Terraform state handling and recovery
- Handling real-world cloud limitations (quota & capacity)

---

## Architecture Components

### Resource Group
Logical container for all Azure resources in this project.

### Virtual Network (VNet)
Provides isolated private networking within Azure.

### Subnet
Defines a segmented address space inside the VNet for workload isolation.

### Network Security Group (NSG)
Acts as a Layer-4 firewall to control inbound and outbound traffic.

### Network Security Rule
An example inbound rule allowing SSH traffic (port 22) to demonstrate
controlled access design.

---

## Infrastructure Flow (Conceptual)

1. Terraform initializes Azure provider
2. Resource Group is created
3. Virtual Network is provisioned
4. Subnet is defined within the VNet
5. Network Security Group is created
6. Security rules are applied
7. NSG is associated with the subnet

This layered approach reflects how infrastructure is commonly built and secured in
real production environments.

---

## Compute Consideration

Virtual machine deployment was explored as part of this project.
However, Azure Free Trial compute quotas and regional SKU capacity restrictions prevented
reliable VM provisioning across multiple regions and sizes.

Rather than forcing an unstable or incomplete design, the project was finalized at the
**network and security layer**, which is frequently designed and validated independently
before compute is introduced in real-world infrastructure workflows.

---

## Repository Structure
```
terraform/
├── main.tf # Core infrastructure resources
├── providers.tf # Azure provider configuration
├── variables.tf # Reusable variables
├── outputs.tf # Outputs (if applicable)
├── .terraform.lock.hcl
README.md
```


---

## Design Decisions

- Terraform used for repeatable and auditable infrastructure provisioning
- Network and security layers prioritized over compute
- Variables used to centralize configuration
- Infrastructure scoped intentionally to avoid unnecessary cloud costs
- Limitations documented instead of hidden

---

## Limitations

- No virtual machines deployed due to Azure Free Trial restrictions
- No application runtime included
- No CI/CD pipelines in this repository

These aspects are intentionally handled in **separate, dedicated projects**.

---

## Out of Scope / Next Steps

- Compute layer (VMs or containers)
- Application deployment
- Container orchestration
- CI/CD automation

These are addressed in follow-up projects focusing on Docker and runtime orchestration.

---

## Key Learnings

- Terraform state management is critical during iterative development
- Cloud provider quotas can directly influence architectural decisions
- Network and security design can be completed independently of compute
- Real-world infrastructure often requires redesign rather than retries

---

## Summary

This project represents a **completed and intentional infrastructure design**
focused on Azure networking and security using Terraform. It reflects real-world
engineering decisions, including the evaluation and documentation of cloud limitations,
rather than forcing incomplete or unstable deployments.

