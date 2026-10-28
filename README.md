# StaffSync - Modern Human Resource Management Solution

A Full Stack MERN (MongoDB, Express.js, React.js, Node.js) Web Application developed for the College Project Curriculum (SkillWallet LMS).

---

## Project Overview
**StaffSync** is a comprehensive internal company portal that allows organizations to:
1. Manage user access with secure, Role-Based Access Control (**Employee**, **HR**, and **Manager** tiers).
2. Log, track, and review daily employee attendance and working hours.
3. Submit leave applications (Sick, Casual, Paid) with a full approval/rejection workflow for managers.
4. Broadcast company-wide announcements and internal updates.
5. Manage employee training programs and schedule departmental development.
6. Maintain a centralized Employee database with full CRUD capabilities for HR.

---

## Architecture & MVC Structure

```text
StaffSync-HRM/
├── Frontend/                             # Client (React + Vite + Tailwind CSS)
│   ├── src/
│   │   ├── api/
│   │   │   └── api.js                    # Axios instance & backend endpoints
│   │   ├── components/
│   │   │   ├── auth/                     # Login & Register forms
│   │   │   ├── employee/                 # Employee views (Attendance, LeaveApply, etc.)
│   │   │   ├── hr/                       # HR management tables (EmployeeCRUD, etc.)
│   │   │   ├── manager/                  # Manager approvals (LeaveApplications, Training)
│   │   │   └── ui/                       # Reusable UI components (buttons, cards, tabs)
│   │   ├── pages/
│   │   │   ├── EmployeeDashboard.jsx     # Main portal for standard staff
│   │   │   ├── HrDashboard.jsx           # Portal for Human Resources
│   │   │   └── ManagerDashboard.jsx      # Portal for Department Managers
│   │   ├── routes/
│   │   │   └── ProtectedRoute.jsx        # JWT Route protection & Role authorization
│   │   ├── utils/
│   │   │   └── formatDate.js             # Date parsing utilities
│   │   ├── App.jsx                       # Master Routes
│   │   └── main.jsx                      # React DOM rendering
│   ├── package.json
│   └── vite.config.js                    # Vite configuration
│
└── Backend/                              # Server (Node.js + Express.js + Mongoose)
    ├── config/
    │   └── db.js                         # Mongoose MongoDB Connection
    ├── controllers/
    │   ├── announcementController.js     # Logic for broadcasting updates
    │   ├── attendanceController.js       # Logic for clock-in/clock-out tracking
    │   ├── authController.js             # Logic for Login/Register & JWT generation
    │   ├── employeeController.js         # Logic for HR user management
    │   ├── leaveController.js            # Logic for leave requests & approvals
    │   └── trainingController.js         # Logic for training module assignments
    ├── middleware/
    │   └── authMiddleware.js             # JWT verification & Role checking
    ├── models/
    │   ├── Announcement.js               # Announcement Mongoose Schema
    │   ├── Attendance.js                 # Attendance Mongoose Schema
    │   ├── Employee.js                   # Employee Profile Schema
    │   ├── Leave.js                      # Leave Request Schema
    │   ├── Training.js                   # Training Program Schema
    │   └── User.js                       # Master User Authentication Schema
    ├── routes/
    │   ├── announcementRoutes.js         # /api/announcements
    │   ├── attendanceRoutes.js           # /api/attendance
    │   ├── authRoutes.js                 # /api/auth (Login, Register)
    │   ├── employeeRoutes.js             # /api/employees
    │   ├── leaveRoutes.js                # /api/leaves
    │   └── trainingRoutes.js             # /api/training
    ├── .env                              # Environment configuration (Hidden)
    ├── package.json
    └── server.js                         # Master Express API Server
