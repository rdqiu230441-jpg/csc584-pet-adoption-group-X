**# Pet Adoption \& Animal Rescue Awareness Portal**



**## Project Overview**

**A comprehensive web-based platform designed to connect loving homes with pets in need of adoption. This system facilitates the entire adoption process from browsing available pets to managing shelters, processing adoption applications, and organizing awareness events.**



**Team Members**

**- \Bawan Amanj**

**- \Mohammed Yaseen**

**- \Rand Dilman**

**- \Rahand Farhad**


**## Project Structure**

**```**

**pet-adoption-portal/**

**├── index.html              # Main storyboard/wireframe file**

**├── erd\_diagram.png         # ERD (alternate format)**

**├── schema.sql              # Database schema (optional)**

**└── README.md               # This file**

**```**



**## How to Navigate the Storyboard**



**### Getting Started**

**1. \*\*Open `index.html`\*\* in your web browser (Chrome, Firefox, or Edge recommended)**

**2. You will land on the \*\*Home Page\*\* showing overview statistics**



**### User Flow**

**1. \*\*Home Page\*\* → Click "Login" or "Register" to access the system**

**2. \*\*Login/Register\*\* → Use the forms to simulate authentication**

**3. \*\*Dashboard\*\* → After login, you'll see:**

   **- 4 KPI cards (Total Pets, Pending Adoptions, Active Shelters, Monthly Adoptions)**

   **- 2 Chart placeholders (Monthly Adoptions Trend, Pets by Species)**

   **- Quick action buttons**



**### Main Modules**



**#### 1. \*\*Pets Management\*\* 🐾**

**- \*\*Browse Pets\*\* → View all available pets in card layout**

**- \*\*Add New Pet\*\* → Register a new pet for adoption**

**- \*\*View Details\*\* → See complete pet information**

**- \*\*Edit Pet\*\* → Update pet details**

**- Navigate: Dashboard → Browse Pets**



**#### 2. \*\*Shelters Management\*\* 🏠**

**- \*\*View Shelters\*\* → List all registered shelters in table format**

**- \*\*Add Shelter\*\* → Register a new animal shelter**

**- \*\*Shelter Details\*\* → View complete shelter information and statistics**

**- \*\*Edit Shelter\*\* → Update shelter information**

**- Navigate: Dashboard → Shelters**



**#### 3. \*\*Adoptions Management\*\* 📋**

**- \*\*View Applications\*\* → See all adoption applications with status**

**- \*\*New Application\*\* → Submit adoption request for a pet**

**- \*\*Application Details\*\* → Review complete application information**

**- \*\*Edit Application\*\* → Update application status and notes**

**- Navigate: Dashboard → Adoptions**



**#### 4. \*\*Events Management\*\* 📅**

**- \*\*Browse Events\*\* → View upcoming adoption events and activities**

**- \*\*Create Event\*\* → Organize new adoption fairs, workshops, etc.**

**- \*\*Event Details\*\* → See complete event information**

**- \*\*Edit Event\*\* → Update event details**

**- Navigate: Dashboard → Events**



**### Navigation Features**

**- \*\*Breadcrumb Navigation\*\* → Shows your current location in the site hierarchy**

**- \*\*Back Buttons\*\* → Return to previous pages easily**

**- \*\*Main Navigation Menu\*\* → Quick access to all main modules (visible after login)**

**- \*\*Logout\*\* → Return to home page**



**## Database Design**



**### ERD Location**

**The Entity Relationship Diagram can be found in:**

**- \*\*Primary:\*\* `erd\_diagram.pdf`**

**- \*\*Alternate:\*\* `erd\_diagram.png`**



**### Database Tables (6 Tables)**



**1. \*\*users\*\* - System user management**

   **- Primary Key: `user\_id`**

   **- User types: Adopter, Shelter Manager, Volunteer**

   **- Unique constraint on email**



**2. \*\*shelters\*\* - Animal shelter information**

   **- Primary Key: `shelter\_id`**

   **- Foreign Key: `created\_by` → users.user\_id**

   **- Tracks capacity and current pet count**



**3. \*\*pets\*\* - Pet information and availability**

   **- Primary Key: `pet\_id`**

   **- Foreign Key: `shelter\_id` → shelters.shelter\_id**

   **- Status tracking: Available, Pending, Adopted, Not Available**



**4. \*\*adoptions\*\* - Adoption applications and tracking**

   **- Primary Key: `adoption\_id`**

   **- Foreign Keys:** 

     **- `pet\_id` → pets.pet\_id**

     **- `adopter\_id` → users.user\_id**

   **- Status workflow: Pending → Under Review → Approved → Completed**



**5. \*\*events\*\* - Adoption events and activities**

   **- Primary Key: `event\_id`**

   **- Foreign Keys:**

     **- `shelter\_id` → shelters.shelter\_id**

     **- `created\_by` → users.user\_id**

   **- Event types: Adoption Fair, Vaccination Drive, Training Workshop, etc.**



**6. \*\*event\_registrations\*\* - Event participation tracking (Junction table)**

   **- Primary Key: `registration\_id`**

   **- Foreign Keys:**

     **- `event\_id` → events.event\_id**

     **- `user\_id` → users.user\_id**

   **- Many-to-Many relationship between users and events**



**### Key Relationships**

**- \*\*One-to-Many:\*\***

  **- One user can create multiple shelters**

  **- One shelter can have many pets**

  **- One user can submit many adoption applications**

  **- One pet can have multiple adoption applications (history)**

  **- One shelter can organize many events**



**- \*\*Many-to-Many:\*\***

  **- Users can register for multiple events**

  **- Events can have multiple user registrations**

  **- Implemented through `event\_registrations` junction table**



**## Features Implemented in Storyboard**



**### ✅ Authentication Module**

**- User login page with email/password**

**- Registration page with user type selection**

**- Logout functionality**



**### ✅ Dashboard**

**- 4 KPI metrics with real-time statistics**

**- Chart placeholders for data visualization**

**- Quick action buttons for common tasks**



**### ✅ CRUD Operations (Create, Read, Update, Delete)**

**All four main entities support full CRUD:**

**- \*\*Pets:\*\* List, Create, View Details, Edit**

**- \*\*Shelters:\*\* List, Create, View Details, Edit**

**- \*\*Adoptions:\*\* List, Create, View Details, Edit**

**- \*\*Events:\*\* List, Create, View Details, Edit**



**### ✅ User Interface Features**

**- Responsive design with modern gradient colors**

**- Card layouts for visual browsing (Pets, Events)**

**- Table layouts for data management (Shelters, Adoptions)**

**- Form validation placeholders**

**- Status indicators with color coding**

**- Breadcrumb navigation**

**- Active state highlighting in navigation**



**## Technical Details**



**### Technologies Used (Storyboard)**

**- \*\*HTML5\*\* - Semantic markup**

**- \*\*CSS3\*\* - Styling with gradients and flexbox/grid**

**- \*\*JavaScript\*\* - Page navigation and interactivity**



**### Design Principles**

**- Clean, modern interface**

**- Intuitive navigation**

**- Consistent layout across pages**

**- Clear visual hierarchy**

**- Accessibility considerations**



**## Important Notes**



**### Storyboard Limitations**

**⚠️ \*\*This is a static storyboard/wireframe only:\*\***

**- No backend functionality implemented yet**

**- No database connections**

**- No actual form submissions**

**- No user authentication/authorization**

**- All data shown is placeholder/sample data**

**- Forms do not validate or save data**



**### Purpose**

**This deliverable focuses on:**

**- Application structure and flow**

**- User interface layout**

**- Navigation patterns**

**- Database design (ERD)**

**- Visual presentation of features**



**## Next Steps (Future Deliverables)**



**### Deliverable 2 - Backend Implementation**

**- Implement JSP/Servlet backend**

**- Connect to MySQL database**

**- Add form validation and processing**

**- Implement authentication/authorization**

**- Add CRUD operations with database**



**### Deliverable 3 - Final Application**

**- Complete all features**

**- Add data visualization (charts)**

**- Implement search and filtering**

**- Add file upload for pet images**

**- Deploy application**



**## How to View**

**1. Extract the ZIP file to a folder**

**2. Open `index.html` in a modern web browser**

**3. Click around to explore all pages and features**

**4. All navigation links are functional**



**## Browser Compatibility**

**- ✅ Google Chrome (Recommended)**

**- ✅ Mozilla Firefox**

**- ✅ Microsoft Edge**

**- ✅ Safari**



**## Contact**


**## Acknowledgments**

**- Course: CSC584 - Web Development**

**- Institution: \Qaiwani International University**

**- Semester: \Stage 3 - Semester 1**

**- Due Date: Week 8**



**---**



**\*\*Last Updated:\*\* November 23, 2025**  

**\*\*Version:\*\* 1.0 - Deliverable 1 (Storyboard + ERD)**

