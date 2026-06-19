
# 📝 Notes Management API

> A RESTful API for managing notes — built with Node.js, Express.js, and MongoDB.  
> Developed as part of **Mission 1** from WeCodeFuture Workspace.

![Node.js](https://img.shields.io/badge/Node.js-339933?style=for-the-badge&logo=nodedotjs&logoColor=white)
![Express](https://img.shields.io/badge/Express.js-000000?style=for-the-badge&logo=express&logoColor=white)
![MongoDB](https://img.shields.io/badge/MongoDB-47A248?style=for-the-badge&logo=mongodb&logoColor=white)

---

## 📌 Project Overview

This project implements a full **CRUD Notes API** where users can:
- ✅ Create a new note
- ✅ Read all notes or a single note
- ✅ Update an existing note
- ✅ Delete a note

---

## 📂 Project Structure

```
notes-api/
│
├── src/
│   ├── config/
│   │   └── db.js              # MongoDB connection
│   ├── controllers/
│   │   └── noteController.js  # CRUD logic
│   ├── middleware/
│   │   └── errorHandler.js    # Global error handling
│   ├── models/
│   │   └── Note.js            # Mongoose schema
│   └── routes/
│       └── notes.js           # API route definitions
│
├── .env.example               # Environment variable template
├── .gitignore
├── package.json
├── server.js                  # App entry point
└── README.md
```

---

## ⚙️ Tech Stack

| Technology | Purpose |
|-----------|---------|
| Node.js | JavaScript runtime |
| Express.js | Web framework / routing |
| MongoDB | NoSQL database |
| Mongoose | MongoDB object modeling |
| dotenv | Environment variable management |
| Nodemon | Auto-restart during development |

---

## 🚀 Getting Started

### 1. Clone the Repository
```bash
git clone https://github.com/YOUR_USERNAME/notes-api.git
cd notes-api
```

### 2. Install Dependencies
```bash
npm install
```

### 3. Set Up Environment Variables
```bash
cp .env.example .env
```
Open `.env` and fill in your values:
```
PORT=5000
MONGO_URI=mongodb+srv://username:password@cluster0.xxxxx.mongodb.net/notesdb
NODE_ENV=development
```
> Get a free MongoDB URI at [mongodb.com/cloud/atlas](https://www.mongodb.com/cloud/atlas)

### 4. Run the Server
```bash
# Development (auto-restart)
npm run dev

# Production
npm start
```

The server will start at: **http://localhost:5000**

---

## 🔗 API Endpoints

### Base URL: `http://localhost:5000/api/notes`

| Method | Endpoint | Description |
|--------|----------|-------------|
| GET | `/api/notes` | Get all notes |
| GET | `/api/notes/:id` | Get a note by ID |
| POST | `/api/notes` | Create a new note |
| PUT | `/api/notes/:id` | Update a note |
| DELETE | `/api/notes/:id` | Delete a note |

---

## 📬 API Usage (Postman Examples)

### ➕ Create a Note
**POST** `/api/notes`
```json
{
  "title": "My First Note",
  "content": "This is the content of my note.",
  "category": "Study",
  "isPinned": false
}
```

**Response:**
```json
{
  "success": true,
  "message": "Note created successfully",
  "data": {
    "_id": "665abc123def456",
    "title": "My First Note",
    "content": "This is the content of my note.",
    "category": "Study",
    "isPinned": false,
    "createdAt": "2026-06-18T10:00:00.000Z",
    "updatedAt": "2026-06-18T10:00:00.000Z"
  }
}
```

---

### 📋 Get All Notes
**GET** `/api/notes`

**Response:**
```json
{
  "success": true,
  "count": 2,
  "data": [ ... ]
}
```

---

### 🔍 Get Note by ID
**GET** `/api/notes/665abc123def456`

---

### ✏️ Update a Note
**PUT** `/api/notes/665abc123def456`
```json
{
  "title": "Updated Title",
  "isPinned": true
}
```

---

### 🗑️ Delete a Note
**DELETE** `/api/notes/665abc123def456`

**Response:**
```json
{
  "success": true,
  "message": "Note deleted successfully",
  "data": {}
}
```

---

## 🧪 Testing with Postman

1. Download and open [Postman](https://www.postman.com)
2. Create a new Collection: `Notes API`
3. Add requests for each endpoint listed above
4. Set the base URL to `http://localhost:5000`
5. For POST and PUT requests, set Body → raw → JSON

---

## ✅ Success Criteria (Mission Checklist)

- [x] Notes API Completed
- [x] CRUD Operations Implemented (Create, Read, Update, Delete)
- [x] Database Connected Successfully (MongoDB via Mongoose)
- [x] API Tested Using Postman
- [x] Clean Code Structure Maintained
- [x] Project Submitted on GitHub

---

## 📚 References

- [Node.js Documentation](https://nodejs.org/en/docs)
- [Express.js Documentation](https://expressjs.com)
- [MongoDB Documentation](https://www.mongodb.com/docs)
- [Mongoose Documentation](https://mongoosejs.com/docs)
- [Postman Documentation](https://www.postman.com)

---

## 👨‍💻 Author

Submitted for **Mission 1 — WeCodeFuture Workspace**

> *"Great backend engineers are not built by memorizing code. They are built by solving problems, debugging failures, and learning through implementation."*
