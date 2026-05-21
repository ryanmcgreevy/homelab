# Homelab Configuration, Infrastructure as Code (IaC) and Documentation

[![Pangolin Deployment](https://github.com/ryanmcgreevy/homelab/actions/workflows/pangolin.yml/badge.svg)](https://github.com/ryanmcgreevy/homelab/actions/workflows/pangolin.yml)
[![FreshRSS Deployment](https://github.com/ryanmcgreevy/homelab/actions/workflows/freshrss.yml/badge.svg)](https://github.com/ryanmcgreevy/homelab/actions/workflows/freshrss.yml)
[![Traefik Deployment](https://github.com/ryanmcgreevy/homelab/actions/workflows/traefik.yml/badge.svg)](https://github.com/ryanmcgreevy/homelab/actions/workflows/traefik.yml)

## Background
This repository contains the configuration files, infrastructure as code (IaC) and documentation for my homelab setup. The goal of this project is to automate the deployment and management of my homelab services using GitHub Actions, Docker Compose, Kubernetes,
and other GitOps, CI/CD, and IaC principles. This repository is mostly for hands-on learning of all these techniques and technologies, so don't expect production-level code!

## Overview
My homelab currently runs:
- 3 node Proxmox HA cluster of hp mini pcs for compute 
- Raspberry Pi for dedicated services 
- Minisforum N100 mini pc for Proxmox Backup Server
- Unifi UNAS-4 for network attached storage and backups

Pangolin running on AWS EC2 acts as the proxy to the entire homelab, and everything is backed up to Backblaze B2 (primary backups are onsite in the NAS).

The HA Proxmox Cluster uses Proxmox managed Ceph shared storage for VMs and LXC containers. Cluster communication runs over a dedicated 1 Gbe connection, while VM and LXC communication and migration is over a 2.5 Gbe connection. All of the networking is done through Unifi switches and router.

The configuration for all of this is not currently entirely found in this repository; this project is a constant work in progress!

## Architecture Diagram

![Homelab Diagram](images/homelab_diagram.drawio.svg)

