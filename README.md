# Ansible Molecule 

### Step 1:

Make sure you have the following installed:

    !!! Note
        -  Make sure you have python & pip 
        -  Make sure that your on the right   directory.

### Installing [pip / pip3](https://github.com/pypa/pip)
```
python get-pip.py
```
### Installing all requirments using pip (make sure you stand inside the directory that contains the requirements file).
```
pip3 install -r requirment.txt
```
### Installing [Ansible](https://github.com/ansible/ansible.git), [Ansible-lint](https://github.com/ansible-community/ansible-lint.git) & [Molecule](https://github.com/ansible-community/molecule.git):
```
brew install ansible
brew install ansible-lint
brew install molecule
```
### Installing [Molecule Vagrant](https://github.com/ansible-community/molecule-vagrant.git)
```
pip3 install molecule-vagrant
```
### Installing [Test Infra](https://github.com/pytest-dev/pytest-testinfra.git)
```
pip3 install pytest-testinfra
or
pip install 'git+https://github.com/pytest-dev/pytest-testinfra@master#egg=pytest-testinfra'
```
### Installing [Ansible-Elasticsearch](https://github.com/elastic/ansible-elasticsearch.git)
```
ansible-galaxy install elastic.elasticsearch,v7.17.0
```
### Step 2:

Install the requirements.txt file _(make sure you stand inside the directory that contains the requirements file)_

```bash
cd molecule/default

pip install -r requirements.txt
```

### Step 3:

Create the docker containers _(make sure you are one step back from the molecule directory )_

```bash
cd ../../
molecule create
```

### Step 4:

Run the converge playbook file on both containers:

```bash
molecule converge
```

### Step 5:

When you are done and would like to remove the containers:

```bash
molecule destroy
```

### Get inside the containers:

Use the following command to see the created machine names:

```bash
molecule login
```

Use the following command to get inside the container:

```bash
molecule login -h <machine-name>
```

### For Testing:

You can run this to test creating > running converge > and destroy all at once:

```bash
molecule test
```
