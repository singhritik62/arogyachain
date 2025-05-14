**🏥 ArogyaChain — Blockchain-Based Healthcare Records System**

👨‍💻 Team Members
	•	Ritik Singh
	•	Roque Martins
	•	Krishna Sonar

📘 Introduction

ArogyaChain is a secure, decentralized healthcare records management system built on Hyperledger Fabric. It empowers patients to store, manage, and selectively share their health data with authorized providers including doctors, pharmacies, labs, and insurance companies — while ensuring data privacy and transparency.

⸻

🚀 Technologies Used
	•	Hyperledger Fabric
	•	Hyperledger Explorer
	•	CouchDB
	•	Docker & Docker Compose
	•	Node.js & Express.js
	•	MongoDB
	•	React.js & TailwindCSS

⸻

⚙️ Features

👤 Patient
	•	Open registration
	•	Login & dashboard access
	•	Fine-grained access control to healthcare providers
	•	View medical history
	•	Submit insurance claims

🩺 Doctor
	•	Admin registration
	•	Login
	•	Access patient history
	•	Write prescriptions

💊 Pharmacy
	•	Admin registration
	•	Login
	•	View prescriptions
	•	Update medicine dispensed with billing
	•	Comments on unavailability

🔬 Lab
	•	Admin registration
	•	Login
	•	View lab test requests
	•	Update lab results with billing

🛡 Insurance
	•	Admin registration
	•	Login
	•	Review and approve/reject claim requests

⸻

🛠 Installation Guide

✅ Prerequisites

Ensure the following tools are installed:

$ node -v                # v16.20.0
$ npm -v                 # v8.19.4
$ docker -v              # Docker version 23.0.1
$ docker-compose -v      # Docker Compose version v2.15.1
$ git --version          # git version 2.39.2

📦 Steps

📦 Steps to Run the Project

1. **Clone the Repository**

	```bash
	git clone https://github.com/singhritik62/arogyachain
	cd arogyachain
	```

2. **Add `.env` File**

	Place the required `.env` file in the `backend` directory as specified in the documentation.

3. **Start Hyperledger Fabric Network**

	```bash
	./fablo up fablo-config.json
	cd backend/config
	./generate-ccp
	```

4. **Start the Backend**

	```bash
	cd backend
	npm install
	node app.js
	```

5. **Start the Frontend**

	```bash
	cd client
	npm install
	npm start
	```

6. **Access the Application**

	Open your browser and navigate to:

	```
	http://localhost:3000
	```




⸻

🌐 Access Application

Open your browser:

http://localhost:3000

To create admin users manually in MongoDB (for Doctor, Lab, Pharmacy, Insurance):

{
  userName: "admin_name",
  orgName: "Admin",
  userId: "admin_id",
  password: "admin_password"
}


⸻

📐 System Architecture

Network Structure
	•	Organizations (5): Patient, Doctor, Pharmacy, Lab, Insurance
	•	Peers: One per organization
	•	Channel: main-channel1
	•	Chaincode: chaincode1
	•	Database: CouchDB per peer

⸻

🧪 API Testing

📩 Postman Collection

⸻

🧯 Troubleshooting

Common issues and fixes:

# Stop Fabric Network
./fablo down

# Restart Fabric Network
./fablo up fablo-config.json

# Stop and remove all containers
docker stop $(docker ps -a -q)
docker rm $(docker ps -a -q)

# Prune Docker volumes
docker volume prune

# Remove wallet data
rm -rf backend/*-wallet

# Regenerate connection profiles
cd backend/config
./generate-ccp

Affiliation Error (Code 20 Fix):

Add these lines to all fabric-ca-server-config.yaml files:

affiliations:
  patient:
    - department1
  doctor:
    - department1
  pharmacy:
    - department1
  lab:
    - department1
  insurance:
    - department1

File path:
/fablo-target/fabric-config/fabric-ca-server-config/*.healthcare.com/fabric-ca-server-config.yaml

⸻

📚 Contribution Info
	•	📘 Project Title: ArogyaChain - Blockchain Healthcare Record System
	•	👥 Team Members:
	•	Ritik Singh
	•	Roque Martins
	•	Krishna Sonar

