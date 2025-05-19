# TP3 - Création de VM avec Ansible - Groupe APT

## Objectif du TP

Automatiser la création de machines virtuelles sur un serveur Proxmox à l’aide d’Ansible.  
L’objectif est de pouvoir déployer facilement des VMs en fonction de l’environnement (production ou développement) via un système de playbooks.

## Structure du tp

Le projet est organisé comme suit :

- `create-vm.yml` : Playbook principal pour créer une VM
- `inventories/` : Contient les environnements :
- `prd/hosts` : inventaire pour la production
- `dev/hosts` : inventaire pour le développement
- `group_vars/` : fichiers de variables pour chaque environnement (`prd.yml`, `dev.yml`)
- `vars/` : autres fichiers de configuration (si besoin)

### Prérequis

- Python 3 et pip installés
- Ansible installé
- Accès à un serveur Proxmox fonctionnel
- Accès SSH ou clé API valide
- Le serveur Proxmox doit être accessible depuis la machine de contrôle Ansible
- IP par défaut du serveur Proxmox : `192.168.30.140 (node0 du tp précédent)` (modifiable dans `group_vars/prd.yml` ou `group_vars/dev.yml`)

### Installation

```bash utilisé :
sudo apt install python3-venv -y
python3 -m venv ansible-env
source ansible-env/bin/activate
pip install --upgrade pip
pip install ansible
ansible-galaxy collection install community.general
