
 
1. INTRODUCTION 
 
1.1 Introduction of the Application 
 
With the growing demand for cloud-based storage solutions, managing and sharing 
images has become an essential feature for both personal and professional use. This 
application aims to create a scalable and secure image gallery web-page hosted on 
AWS (Amazon Web Services). Users can log in, upload, store, and retrieve images 
efficiently. The application utilizes AWS S3 for storing images, AWS RDS for 
managing user and image metadata, and AWS EC2 for hosting the web interface, 
all within the AWS Free Tier to minimize costs. 
The application will support: 
• User Authentication: Ensures that only authorized users can upload and 
access their images. 
• Image Storage: Images are stored securely in AWS S3 buckets. 
• Database Management: AWS RDS will manage user data and image 
metadata. 
• Front-end Interface: A simple, user-friendly interface hosted on AWS 
EC2. 
 
1.2 Drawbacks of the Existing System 
 
Many existing systems face significant limitations when it comes to image hosting 
and management, particularly: 
• Limited Free Storage: Most cloud services, even popular ones like Google 
Photos or Dropbox, offer limited free storage, forcing users to either delete 
old images or pay for additional storage. 
• Privacy and Security Concerns: Users often have to rely on third-party 
image hosting services, which could lead to privacy issues or data theft due 
to poor security measures. 
• High Hosting Costs: Self-hosting solutions are expensive, especially when 
handling large volumes of data and needing high availability. 
2 
 
• Slow Image Retrieval: In many cases, images hosted on third-party 
services suffer from slow loading times due to inefficient retrieval 
mechanisms, especially if the server is located far from the user. 
 
1.3 Proposed System 
 
The proposed system leverages the AWS Free Tier to provide a scalable, secure, 
and cost-efficient platform for users to store and manage images. Key features of 
the proposed system include: 
 
• AWS S3 for Image Storage: Secure and scalable object storage for images, 
which can be accessed efficiently via HTTP/HTTPS. 
• AWS EC2 for Hosting: A scalable web hosting solution that supports a 
seamless user experience for uploading and viewing images. 
• AWS IAM for Access Control: Provides secure user authentication and 
ensures only authorized users can access their images. 
• AWS RDS for Database Management: A reliable database management 
system to store user and image metadata, ensuring fast queries and secure 
data storage. 
By using AWS services, the application ensures that images are stored securely, can 
be accessed at high speed, and provides a seamless experience for users while 
minimizing costs with AWS’s Free Tier. 
1.4 Advantages of the Developed System 
By adopting the AWS-based solution, the developed system offers 
several key advantages over traditional hosting methods: 
The developed system offers several advantages over existing solutions: 
 
• Scalability: The use of AWS services ensures that the system can easily 
scale to handle more users and images without major changes in the 
architecture. 
• Cost Efficiency: The system utilizes AWS's Free Tier, making it suitable 
for users with moderate storage needs without incurring high costs. 
• Security: Using AWS IAM roles for user authentication and ensuring secure 
image storage in S3 minimizes the risk of unauthorized access and data 
breaches. 
3 
 
• High Availability: With EC2 and S3, the application ensures high uptime 
and availability, reducing the chances of downtime. 
• Efficient Image Retrieval: AWS S3's integration with Amazon Cloud 
Front can be used to cache and deliver images quickly to users, minimizing 
latency. 
• Privacy: As the images are stored within the AWS ecosystem, privacy is 
better controlled compared to third-party hosting services. 
 
1.5 Description of Modules (Specially in Case of a Structured Approach) 
A structured approach divides the project into distinct modules, each 
responsible for specific tasks within the overall system. Below is a 
detailed breakdown of the primary modules: 
1. User Authentication Module 
o Function: This module handles user registration, login, and 
authentication. Users must create an account to upload or view 
images. It integrates with AWS IAM for secure authentication. 
o Technologies: Python (Flask/Django) or Node.js for back-end API, 
integrating AWS Cognito for secure user authentication. 
2. Image Upload & Storage Module 
o Function: This module allows users to upload images to AWS S3. 
The uploaded images are securely stored with access control lists 
(ACLs) to ensure that only the user who uploaded the image can 
access it. 
o Technologies: AWS SDK (Boto3 for Python or AWS SDK for 
Node.js), Flask/Django API for back-end logic. 
3. Image Retrieval & Display Module 
o Function: After uploading images, users can retrieve and view their 
images in a gallery. This module ensures that images are retrieved 
efficiently from AWS S3, and are displayed in a user-friendly 
interface. 
o Technologies: AWS S3, AWS CloudFront for optimized delivery, 
Front-end (HTML, CSS, JavaScript). 
 
4 
 
4. Database Management Module 
o Function: This module manages user data and image metadata, such 
as the image name, description, upload date, etc., using AWS RDS 
(MySQL or PostgreSQL). 
o Technologies: AWS RDS for database management, SQL queries 
to manage image metadata. 
5. Frontend & Hosting Module 
o Function: This module provides the user interface (UI) for users to 
interact with the system, including uploading images, viewing 
images in a gallery, and managing their profile. 
o Technologies: HTML, CSS, JavaScript (React or simple Vanilla 
JS), and hosted on AWS EC2. 
5 
 
2. LITERATURE SURVEY 
 
The literature survey for this project examines key software engineering concepts, 
the analysis and design methodologies applied, the tools that have been employed, 
and the overall methodology adopted. This comprehensive review provides 
context for the design decisions and technical choices made throughout the 
development of the WordPress deployment on AWS. 
 
2.1 Description of the Software Engineering Concepts Used 
This project leverages several foundational software engineering 
concepts that ensure the system is robust, scalable, and maintainable: 
• Cloud-Based Architecture: The system uses AWS cloud services for scalable 
storage and efficient resource management. Cloud computing allows for flexible, 
cost-effective solutions with high availability and on-demand resources. 
• Model-View-Controller (MVC) Design Pattern: The application follows the 
MVC design pattern, where:  
o Model: Represents the data (user and image metadata stored in AWS 
RDS). 
o View: The user interface for interaction (frontend developed using HTML, 
CSS, and JavaScript). 
o Controller: Manages the user inputs and interacts with the backend 
(Flask/Django/Node.js API). 
• RESTful API Design: The backend is designed using RESTful APIs to enable 
communication between the frontend and backend efficiently. This ensures 
scalability and maintainability, especially when adding new features. 
• Authentication and Authorization: The system implements secure 
user authentication using AWS IAM and possibly AWS Cognito to 
ensure only authorized users can upload or view images. 
2.2 Description of the Analysis and Design Concepts Used 
The design and analysis phases for this project were guided by several 
established methodologies: 
• Structured System Analysis and Design (SSAD): This methodology helps in 
visualizing the system’s overall structure. Data Flow Diagrams (DFDs) are used 
to represent the flow of data between the user, the backend, and the AWS services 
(EC2, S3, RDS). 
6 
 
• Entity-Relationship (E-R) Diagram: The database design is represented using 
E-R diagrams to model the relationship between users, images, and metadata in 
AWS RDS. 
• Object-Oriented Analysis and Design (OOAD): The system’s components are 
designed using object-oriented principles, where the system is broken down into 
classes representing entities like User, Image, and Gallery. Use Case diagrams 
and Activity diagrams are used to model user interactions with the system. 
• Security Analysis: Security models and risk assessments were 
performed to identify vulnerabilities. Techniques such as 
threat modeling and penetration testing (using OWASP 
guidelines) were integral to ensuring the system met high 
security standards. 
2.3 Description of the Tools Used 
• A Frontend: HTML, CSS, and JavaScript for creating the web pages. Optionally, 
frameworks like React or Vue.js can be used for dynamic interfaces. 
• Backend: Flask or Django (Python) or Node.js to build RESTful APIs that manage 
user authentication and handle image uploads and retrieval. 
• Database: AWS RDS (MySQL or PostgreSQL) is used for storing user and image 
metadata, ensuring data integrity and fast query performance. 
• Cloud Services:  
o AWS S3 for scalable image storage. 
o AWS EC2 for hosting the application. 
o AWS IAM for user authentication and authorization. 
o AWS CloudFront for fast content delivery and image retrieval. 
• Version Control: Git for code versioning and collaboration, with repositories 
hosted on GitHub or GitLab. 
2.4 Description of the Methodology Used 
 
A systematic methodology was adopted to guide the project from conception to 
deployment, ensuring that all aspects of design, implementation, and testing were 
thoroughly addressed: 
• Agile Development Approach: The project followed an iterative agile 
development methodology. This allowed for continuous feedback, 
adaptive planning, and the flexibility to incorporate changes as new 
requirements emerged. 
 
7 
 
• Requirement Gathering and Analysis: Detailed requirements were 
collected from stakeholders, which included performance expectations, 
security needs, and scalability targets. This phase set the foundation for 
the system design. 
 
• Design and Prototyping: The initial system design was developed using 
both SSAD and OOAD techniques. Prototypes of key system components 
(such as the EC2 setup and Image gallery configuration) were created to 
validate design assumptions. 
 
• Implementation and Coding: With the design in place, the coding phase 
commenced. Infrastructure was set up using Terraform scripts, while the 
application was developed using a combination of PHP, MySQL, and 
Apache configurations. Emphasis was placed on writing clean, 
maintainable code and following best practices in coding standards. 
 
• Testing and Validation: A comprehensive testing strategy was 
implemented, including: 
 
• Unit Testing: Testing individual modules to ensure they work as 
expected. 
 
• Integration Testing: Verifying those different modules (e.g., EC2, RDS, 
Image gallery) integrate smoothly. 
 
• Performance Testing: Conducting load and stress tests to determine how 
the system performs under various conditions. 
 
• Security Testing: Performing penetration tests and vulnerability 
assessments to ensure robust security. 
 
• Deployment:The deployment process was automated as much as possible 
using CI/CD pipelines. This ensured a smooth transition from 
development to production while minimizing downtime.  
 
• Maintenance and Continuous Improvement: Post-deployment, the 
system is subject to continuous monitoring. Feedback loops and regular 
updates ensure that the system remains secure, efficient, and responsive 
to evolving requirements. 
8 
 
3. FEASIBILITY STUDY 
 
3.1 Feasibility Study Definition 
 
Feasibility Study is a process of assessing a project’s viability before its 
implementation. It involves evaluating the project from various angles to ensure 
that the proposed system is practical, cost-effective, and can be implemented with 
the available resources. The study includes three key aspects: Economic, 
Technical, and Operational feasibility. 
 
3.2 Economical Feasibility 
 Description: 
Economic Feasibility refers to evaluating whether the proposed system is 
financially viable. It involves analyzing the costs of development, maintenance, and 
operation against the expected benefits to determine if the project is worth the 
investment. 
Description: 
The project utilizes AWS Free Tier services, which significantly reduce initial 
costs. AWS services such as EC2, S3, IAM, and RDS can scale as needed, meaning 
that the system can handle growth without incurring high upfront infrastructure 
costs. The cost-effective nature of the project makes it ideal for small to medium
sized applications. Since the system is hosted on AWS, additional costs are minimal 
and can be managed within the Free Tier limits. 
Conclusion: 
Given that AWS provides a scalable solution with minimal costs during 
development, this project is economically feasible for small-scale usage and can be 
scaled with low incremental costs. 
3.3 Technical Feasibility Description: 
Technical feasibility examines whether the existing technology and resources can 
support the development and implementation of the project. 
Description: 
The project relies on AWS services, which are widely used and supported, ensuring 
reliable, well-documented, and efficient operations. The back-end can be built using 
widely-known frameworks such as Flask or Django for Python, or Node.js for the 
server-side processing. Front-end development using HTML, CSS, and JavaScript 
ensures compatibility with all major web browsers and devices. Additionally, AWS 
provides robust services like IAM for secure user authentication and Cloud Front 
for optimized image delivery. 
9 
 
 
Conclusion: 
From a technical standpoint, the project is feasible, as all the required technologies 
(AWS services, web development frameworks, and database systems) are mature, 
widely adopted, and well-supported by communities and documentation. 
3.4 Operational Feasibility Description: 
Operational Feasibility is concerned with whether the proposed system can operate 
within the existing organizational and operational constraints. It examines the 
practical aspects of implementation, including ease of use, user adoption, and 
system management. 
. 
Description: 
The application is designed to be user-friendly, with a simple web interface that 
allows users to log in, upload, and manage images without technical expertise. The 
backend services hosted on AWS EC2 will ensure high uptime and availability. The 
system is also scalable, making it possible to handle increasing numbers of users 
and images as the user base grows. The operational process is straightforward and 
can be managed without significant additional overhead, as AWS handles much of 
the infrastructure management. 
Conclusion: 
Operationally, the system is feasible as it provides a simple and intuitive user 
experience, easy-to-manage back-end services, and scalability to handle increased 
user demand without extensive operational complexity. 
10 
 
4. SOFTWARE REQUIREMENTS SPECIFICATION (SRS) 
The Software Requirements Specification (SRS) document defines the functional 
and non-functional requirements, system architecture, and design approach for the 
AWS-Based Image Gallery Webpage. It serves as a blueprint for developers and 
stakeholders to understand the project’s scope and functionality. 
4.1 Overview 
 
The SRS is organized into several key sections: 
Introduction: Describes the purpose, scope, definitions, and overall organization 
of the document. 
Overall Description: Provides a high-level view of the product, its functions, and 
its operational environment. 
Specific Requirements: Details the functional requirements, non- functional 
requirements, and external interface specifications. 
Annexures: Includes supplementary diagrams and documents, such as Data Flow 
Diagrams, Process Descriptions, and Data Dictionaries. 
4.2 Introduction 
4.2.1 Purpose 
 
The purpose of this SRS is to document all the requirements for the project 
"Deploying Image Gallery on AWS EC2 and RDS." It provides a clear, 
unambiguous description of the system functionalities and constraints that the 
development team will implement. 
4.2.2 Scope 
This SRS covers the following: 
• Deployment of Image Gallery on an AWS EC2 instance. 
• Integration with a MySQL database hosted on AWS RDS. 
• Implementation of security, scalability, and performance requirements. 
• Definition of user roles, access control, and system interfaces. 
4.2.3 Definitions, Acronyms, and Abbreviations 
• AWS: Amazon Web Services. 
11 
 
• EC2: Elastic Compute Cloud. 
• RDS: Relational Database Service. 
• DFD: Data Flow Diagram. 
• SRS: Software Requirements Specification. 
• IEEE: Institute of Electrical and Electronics Engineers. 
4.2.4 References 
List all relevant documents, standards, and resources used in preparing this SRS 
(e.g., IEEE 830-1993 Standard, AWS documentation). 
4.2.5 Overview of Document Structure 
This document is organized into the main sections described above, followed by 
annexures that provide detailed visual and textual representations of system 
processes and data. 
4.3    Overall Description 
4.3.1 Product Perspective 
The system is a cloud-based Image Gallery deployment designed to leverage 
AWS services for hosting, database management, and security. It is intended to be 
modular, scalable, and easily maintainable. 
4.3.2 Product Functions 
• Host and serve a Image Gallery website using AWS EC2. 
• Manage data using AWS RDS (MySQL). 
 Provide administrative functions through a user-friendly interface. 
• Enable monitoring and logging through AWS Cloud-watch. 
4.3.3 User Characteristics 
• Administrators: Manage the overall system, configure 
settings, and perform backups. 
• Content Managers: Use the Image Gallery interface 
to upload images. 
• End-Users: Access the website to view images. 
 
12 
 
4.3.4 Operating Environment 
• Hosted on AWS EC2 (Linux-based instances). 
• AWS RDS for database services. 
• Internet browsers for user access. 
• Network and security configurations defined by AWS Security 
Groups and IAM policies. 
4.3.5 Design and Implementation Constraints 
• Compliance with AWS best practices. 
• Adherence to the IEEE 830-1993 standard. 
• Compatibility with existing Image Gallery plugins and themes. 
• Scalability requirements to handle variable web traffic. 
4.3.6 Assumptions and Dependencies 
• Availability of reliable internet connectivity. 
• Continued support for AWS services. 
• Availability of technical expertise in AWS, PHP, and MySQL. 
4.4 Specific Requirements 
4.4.1 Functional Requirements 
• User Authentication Users must be able to register for an account using an 
email and password. 
• Image Upload & Storage: Users should be able to upload images to the 
platform in supported formats (e.g., JPEG, PNG). 
• Image Retrieval & Viewing: Users can view their uploaded images from a 
gallery interface. 
• User Access Control: The system must enforce role-based access control 
using AWS IAM. 
13 
 
4.4.2 Non-functional Requirements 
• Security: User data and images should be protected using AWS IAM for 
authentication and secure storage practices within AWS S3. 
• Performance: The system should ensure efficient image upload and 
retrieval, aiming for minimal delay, using AWS CloudFront for faster 
image delivery. 
• Scalability: AWS S3 ensures virtually unlimited storage, while AWS EC2 
and RDS can scale as required. 
• Availability: The application hosted on AWS EC2 should have high uptime 
with minimal downtime for maintenance. 
4.4.3 External Interface Requirements 
• User Interfaces: Web-based Image gallery admin panel and 
public-facing website. 
• Hardware Interfaces: AWS EC2 instances and associated 
networking hardware. 
• Software Interfaces: Integration with third-party plugins, 
AWS APIs, and security tools. 
• Communication Interfaces: Use of HTTPS and secure API endpoints. 
4.5 Annexures 
  Annexure A: Data Flow Diagram (DFD) 
• Represents the flow of data within the Image Gallery Webpage system. 
• Level 0 - Context Diagram 
• Shows interaction between User, Web Application, and AWS 
Services (S3, RDS, IAM). 
• Level 1 - DFD Breakdown 
o User Authentication 
• User credentials are sent for verification via AWS 
Cognito or RDS. 
o Image Upload 
• User uploads an image → Stored in AWS S3, metadata 
saved in RDS. 
14 
 
o Image Retrieval 
• Web app fetches image metadata from RDS and image 
file from S3. 
Image Deletion 
• User deletes an image → Entry removed from RDS, image deleted 
from S3 
 
Annexure B: Process Description 
• User Registration & Login 
• Users sign up and log in securely using AWS Cognito or RDS. 
• Image Upload 
• Users select an image → The system validates and uploads it to 
AWS S3. 
• Metadata (image URL, user ID, timestamp) is stored in RDS. 
• Image Retrieval 
• User requests images → Web app retrieves image URLs from 
RDS and loads images from S3. 
• Image Deletion 
• User deletes an image → Metadata removed from RDS, file 
deleted from S3. 
Annexure C: Data Dictionary 
• Image ID 
o Data Type: Integer 
o Description: Unique identifier for each image in the gallery. 
• Image URL 
o Data Type: String 
o Description: The URL path to access an image stored in Amazon 
S3. 
• Image Title 
o Data Type: String 
o Description: The title or name given to the image. 
• Image Description 
o Data Type: String 
o Description: A brief description of the image. 
• Upload Date 
15 
 
o Data Type: DateTime 
o Description: The date and time when the image was uploaded to 
the gallery. 
• UploaderID 
o Data Type: Integer 
o Description: ID of the user who uploaded the image. 
• Category 
o Data Type: String 
o Description: The category under which the image is categorized 
(e.g., Nature, Urban). 
• Image Format 
o Data Type: String 
o Description: The format of the image (e.g., JPEG, PNG). 
• Image  Size 
o Data Type: Integer 
o Description: The file size of the image in bytes. 
• Thumbnail URL 
o Data Type: String 
o Description: The URL of the thumbnail image. 
• Views Count 
o Data Type: Integer 
o Description: The number of views the image has received. 
• Tags 
o Data Type: String 
 Description: Tags or keywords associated with the image. 
 Example Entry: 
• User Table 
o User id → Unique identifier for each user. 
o User name → User’s unique name. 
o Password hash  → Encrypted password for security. 
• Image Table 
o Image id → Unique ID for each uploaded image. 
o Image URl→ S3 storage link for the image. 
o Upload time stamp  → Time of upload, defaults to the current 
timestamp. 
16 
 
5. SSAD (Structured System Analysis and Design) 
 
This section provides a detailed analysis of the system using SSAD methodologies. 
It includes visual and descriptive representations of the system’s structure and data 
flows, which help in understanding the design, relationships, and processes 
involved in deploying WordPress on AWS. 
5.1 Decomposition Diagram 
Purpose: 
The Decomposition Diagram breaks the system into its major subsystems and 
modules, illustrating how the project is divided into manageable components. 
Description: 
For the Image Gallery Webpage on AWS, the decomposition structure can be 
conceptualized as follows: 
Image Gallery Webpage (Overall System) 
• Frontend (User Interface) 
o User authentication & registration 
o Image upload & preview 
o Image display & gallery management 
• Backend (Server Logic) 
o User request handling 
o Image metadata processing 
• Storage & Database 
o AWS S3: Stores uploaded images securely 
o AWS RDS: Stores user details, image metadata 
• Security & Authentication 
o IAM Roles & Policies: Secure access to AWS resources 
o User Authentication: Managed via credentials or AWS Cognito 
o Monitoring & LoggingAWS CloudWatch: Logs user activity 
and system performance 
17 
 
 
 
 
5.2 Data Flow Diagram (DFD) 
Purpose: 
The DFD illustrates the flow of data within the system, showing how user inputs 
are processed, stored, and retrieved. 
Description: 
For the Image Gallery Webpage on AWS, the DFD consists of: 
• External Entities: Users (uploading, viewing images) 
• Processes: 
o User authentication & login 
o Image upload processing 
o Image retrieval & display 
• Data Stores: 
o AWS S3 (Object Storage) - Stores images 
o AWS RDS (Database) - Stores user info & image metadata 
• Data Flows: 
18 
 
o Users interact with the frontend 
o Requests are processed by the backend 
o Image data is stored in S3 
o Image metadata is saved in RDS 
o Images are retrieved and displayed in the gallery 
 
 
 
 
5.3 Structure Chart Purpose: 
Purpose: 
The Structure Chart shows the hierarchical relationships between different 
system modules and functions. 
Description: 
For the Image Gallery Webpage, the structure chart can be represented as: 
• User Interface (Frontend) 
• Login & Authentication 
• Image Upload 
• Image Display 
• Backend Server (EC2) 
• Handles User Requests 
• Validates & Processes Uploads 
• Communicates with AWS Services 
• AWS Services 
• S3: Image Storage 
• RDS: Metadata Storage 
19 
 
• IAM: Security Roles 
CloudWatch: Logging Sample Textual Representation: 
 
 
5.4 E-R Diagrams (Entity-Relationship Diagrams) Purpose: 
Purpose: 
The E-R Diagram illustrates the database structure, defining entities, their 
attributes, and relationships. 
Description: 
For the Image Gallery Webpage, key entities include: 
• Users Table 
• User id (Primary Key) 
• username 
• email 
• password hash 
• Images Table 
• Image id (Primary Key) 
• User id (Foreign Key) → Links to Users Table 
• Image url 
• Upload date 
• description 
• Metadata Table 
• Metadata id (Primary Key) 
• Image id (Foreign Key) → Links to Images Table 
• size 
• format 
• resolution 
 
20 
 
21 
 
5.5 Data Dictionary 
 
Purpose: 
The Data Dictionary provides detailed definitions for each data element used in the 
system. It ensures consistency and clarity in how data is stored, processed, and 
validated across the project. 
User id 
Data Type: Integer 
Description: Unique user identifier 
Format/Structure: Auto-increment 
Constraints: Primary Key, Not Null 
 
Username 
Data Type: String 
Description: User's name 
Format/Structure: Max 50 chars 
Constraints: Unique, Not Null 
 
Email 
Data Type: String 
Description: User’s email 
Format/Structure: Max 100 chars 
Constraints: Unique, Not Null 
 
Password hash 
Data Type: String 
Description: Encrypted password 
Format/Structure: Hashed string 
Constraints: Not Null 
 
Image id 
Data Type: Integer 
Description: Unique image identifier 
Format/Structure: Auto-increment 
Constraints: Primary Key 
 
 
 
 
 
 
22 
 
User id (in images table) 
Data Type: Integer 
Description: Owner of the image 
Format/Structure: Foreign Key → Users Table 
Constraints: Not Null 
 
Image url 
Data Type: String 
Description: URL of uploaded image 
Format/Structure: S3 URL format 
Constraints: Not Null 
 
Upload date 
Data Type: Date Time 
Description: Timestamp of upload 
Format/Structure: YYYY-MM-DD HH:MM:SS 
Constraints: Not Null 
 
23 
 
6.OOAD (Object-Oriented Analysis and Design) 
 
In Object-Oriented Analysis and Design (OOAD), the system is designed using 
object-oriented concepts, focusing on identifying objects, their responsibilities, 
interactions, and the relationships between them. The OOAD approach utilizes 
various diagrams to visually represent the system’s structure and behavior. Below 
is the detailed breakdown for your AWS-based Image Gallery Webpage project. 
6.1 Use Case Model 
 
A Use Case Model describes the system's functionality in terms of actors and use 
cases, which define how users interact with the system. 
 
Actors: 
 
User: Regular users who can log in, upload images, view images, and manage 
their personal gallery. 
 
Admin: Admins who can manage user accounts and images. 
 
System: Represents the image storage and management backend (AWS services). 
 
Use Cases: 
 
User Registration: A new user can sign up with their details. 
 
User Login: Users log in to access their galleries. 
 
Image Upload: Users upload images to their personal gallery. 
 
Image Viewing: Users can view images they’ve uploaded. 
 
Admin Management: Admins can manage users, their data, and images. 
 
 
 
 
24 
 
 
 
 
 
 
 
6.2 Use Case Specification-Format Purpose: 
 
The Use Case Specification provides detailed descriptions for each 
use case, including preconditions, main flow, alternative flows, and 
postconditions. 
Each use case specifies the details of the interaction between the actor and the 
system. 
 
Use Case Example: User Login 
• Name: User Login 
• Actor: User 
• Description: A user enters their credentials to log in to the system. 
• Preconditions: User must be registered. 
• Basic Flow:  
o User enters their username and password. 
o System authenticates the credentials. 
o System grants access to the user’s gallery upon successful login. 
• Postconditions: User is logged in and redirected to their gallery. 
• Alternative Flow: Invalid credentials result in an error 
message and prompt for re-entry. 
25 
 
6.3 Activity Diagram Purpose: 
 
An Activity Diagram represents the workflow of a specific process, illustrating 
the flow of control from one activity to the next. 
Example: User Login Activity Diagram 
 
 
 
26 
 
6.4   Identification of Scenarios Purpose: 
 
Identification of scenarios involves describing specific, real-world interactions with 
the system. These scenarios help in validating requirements and guiding design. 
In OOAD, scenarios describe how a user will interact with the system. For 
example: 
 
Scenario 1: User Uploads an Image 
 
The user logs into the system, accesses the image upload interface, selects an 
image, and submits it. The system stores the image in AWS S3 and updates the 
image metadata in AWS RDS. 
 
Scenario 2: Admin Deletes an Image 
 
The admin logs in, accesses the admin dashboard, selects an image to delete, and 
confirms the deletion. The system removes the image from AWS S3 and updates 
the database. 
 
6.5  Sequence and Collaboration Diagrams Purpose: 
 
Sequence Diagram: This diagram represents the sequence of messages between 
objects over time, showing the interactions in a specific use case. 
Example: Image Upload Sequence Diagram 
 
 
27 
 
 
6.6 Class Diagrams Purpose: 
 
A Class Diagram represents the static structure of the system, showing the 
classes, their attributes, methods, and the relationships between them. 
Example: Class Diagram 
 
 
 
 
28 
 
6.7 State Chart Purpose: 
 
A State Chart (also known as a State Machine Diagram) describes the states that 
an object can be in and how it transitions between those states. 
Example: Image State Chart 
 
 
 
29 
 
  6.8 Component Diagrams 
  
Component Diagrams show the organization and dependencies among 
software components. 
Example: 
A component diagram for the Image Gallery on AWS system might include: 
• Web Server Component: 
• Handles HTTP requests, serves the WordPress application. 
• Database Component: 
• Manages data storage via AWS RDS (MySQL). 
• Security Component: 
• Implements access control using AWS IAM and Security Groups. 
• Monitoring Component: 
• Collects performance data using AWS CloudWatch. 
• Load Balancer Component: 
• Distributes incoming traffic across multiple EC2 instances. 
 
 
 
30 
 
6.9 Deployment Diagrams 
 
A Deployment Diagram shows the physical deployment of the system's software 
components on hardware nodes. It is used to visualize how the system will be 
deployed on the server infrastructure. 
Example: Deployment Diagram 
 
 
 
31  
7.FORM DESIGNING 
This section outlines all the forms used in the system, presented in sequence, with example 
photos to help visualize the layout, design elements, and user interactions of the deployed 
WordPress system on AWS. 
 
FORM DESIGNING 
Form designing is an essential part of web application development, as it defines the user 
interface and provides an interaction platform for the users. Below are the forms required for 
the AWS-Based Image Gallery Webpage, organized in the sequence they will appear for the 
user journey. 
 
7.1 User Interface Entry Points 
 
7.1.1 Login Form 
 
The Login Form is the entry point for registered users to access their image gallery. 
Components: 
Username Field: A text field to enter the registered username. 
Password Field: A password field to securely input the password. 
Login Button: A button to submit the login credentials. 
Forgot Password Link: A link to reset the password if the user forgets it. 
Register Button: A link/button to redirect new users to the registration form. 
Form Layout: 
 
 
32  
 
7.1.2 Registration Form 
 
The Registration Form is for new users to create an account and gain access to the system. 
Components: 
Name Field: A text field to enter the full name. 
Email Field: A text field to enter the email address (used for login). 
Password Field: A password field to set the user’s password. 
Confirm Password Field: A field to confirm the entered password. 
Submit Button: A button to submit the registration form. 
Login Link: A link to navigate back to the login page if the user already has an account. 
Form Layout: 
 
 
 
 
 
 
 
 
 
 
33  
 
 
7.2 Authentication Forms 
 
7.2.1 Forgot Password Form 
 
The Forgot Password Form helps users reset their password in case they forget it. 
Components: 
Email Field: A text field where users can enter the email address linked to their account. 
Submit Button: A button to send the reset password email to the user. 
Back to Login Link: A link to go back to the login page. 
Form Layout: 
 
 
 
 
 
 
 
34  
 
 
 
7.3 Content Management Forms  
 
7.3.1 Admin Dashboard Form 
 
The Admin Dashboard Form allows administrators to manage user accounts and uploaded 
images. 
Components: 
User Management Section: Displays a list of registered users with the option to delete or 
modify their accounts. 
Image Management Section: Displays a list of all images uploaded by users, with options to 
delete or approve images. 
Search Field: Allows admins to search for specific users or images. 
Form Layout: 
 
 
 
 
7.4 Additional Forms: 
 
7.4.1 Image Upload Form 
 
Once the user has logged in, they can upload images to their personal gallery. This form 
enables image selection and submission. 
Components: 
File Upload Field: A field to select the image to upload (with file validation for formats like 
PNG, JPG, JPEG, etc.). 
Title Field: A text field to provide an optional title for the image. 
35  
Submit Button: A button to submit the image for upload. 
Progress Bar (optional): Displays the upload progress. 
 
 
 
Form Layout: 
 
 
 
7.4.2 Image Gallery View Form 
The Image Gallery View Form displays all uploaded images in a user’s gallery. Users can 
view, delete, or download their images. 
Components: 
Gallery Grid: A grid displaying thumbnails of all images the user has uploaded. 
Delete Button: A button to remove an image from the gallery. 
Download Button: A button to download the image to the user's device. 
View Button: A button to view the image in a larger format. 
Form Layout: 
 
36  
 
 
7.4.3 Image Deletion Confirmation Form 
 
Before an image is permanently deleted, the Image Deletion Confirmation Form asks for 
confirmation to prevent accidental deletion. 
Components: 
Confirmation Message: A message asking if the user is sure they want to delete the image. 
Confirm Button: A button to confirm the deletion. 
Cancel Button: A button to cancel the deletion and return to the gallery. 
Form Layout: 
 
 
 
 
37  
8.DATA DICTIONARY 
A Data Dictionary is a centralized repository of information about data such as 
meaning, relationships to other data, origin, usage, and format. It plays a critical role 
in ensuring consistency, clarity, and proper management of data elements throughout 
the system. 
The following entries provide sample definitions for key data elements found in the 
WordPress database schema. These definitions serve as examples and can be 
expanded as needed for a comprehensive implementation. 
 
8.1 Sample Data Dictionary Entries 
Below is the Data Dictionary for the entities involved in the AWS-Based Image Gallery 
Webpage, listed with the attributes in points format. 
 8.1.1 User 
• Description: Represents the user of the Image Gallery Webpage. A user has personal 
details and a gallery to manage their images. 
o User id 
▪ Type: Integer 
▪ Description: Unique identifier for each user. 
▪ Constraints: Primary Key, Auto-increment 
o Username 
▪ Type: String 
▪ Description: Username used for logging in. 
▪ Constraints: Unique, Not Null 
o Password 
▪ Type: String 
▪ Description: Encrypted password for user authentication. 
▪ Constraints: Not Null 
o Email 
▪ Type: String 
▪ Description: Email address for user communication. 
▪ Constraints: Unique, Not Null 
o Full name 
▪ Type: String 
▪ Description: Full name of the user. 
▪ Constraints: Not Null 
o Registration date 
▪ Type: Date 
▪ Description: Date when the user registered. 
38  
 8.1.2 Image 
• Description: Represents an image uploaded by a user to the image gallery. Each image 
is associated with a user and can have metadata. 
o Image id 
▪ Type: Integer 
▪ Description: Unique identifier for each image. 
▪ Constraints: Primary Key, Auto-increment 
o Title 
▪ Type: String 
▪ Description: Optional title of the image. 
▪ Constraints: Nullable 
o File name 
▪ Type: String 
▪ Description: Name of the file as stored in AWS S3. 
▪ Constraints: Not Null 
o Upload date 
▪ Type: Date 
▪ Description: Date when the image was uploaded. 
▪ Constraints: Default: Current Date 
o User id 
▪ Type: Integer 
▪ Description: ID of the user who uploaded the image. 
▪ Constraints: Foreign Key (references User) 
o Image url 
▪ Type: String 
▪ Description: URL of the image stored in AWS S3. 
▪ Constraints: Not Null 
o Image size 
▪ Type: Integer 
▪ Description: Size of the image in bytes. 
▪ Constraints: Not Null 
8.1.3 Gallery 
• Description: Represents a user’s gallery that contains a collection of images uploaded 
by that user. 
o Gallery id 
▪ Type: Integer 
▪ Description: Unique identifier for the gallery. 
▪ Constraints: Primary Key, Auto-increment 
 
 
39  
o User id 
▪ Type: Integer 
▪ Description: ID of the user who owns the gallery. 
▪ Constraints: Foreign Key (references User) 
o Gallery name 
▪ Type: String 
▪ Description: Name or title of the gallery (optional). 
▪ Constraints: Nullable 
8.1.4 Admin 
• Description: Represents the administrator responsible for managing users and images 
in the system. 
o Admin id 
▪ Type: Integer 
▪ Description: Unique identifier for each admin. 
▪ Constraints: Primary Key, Auto-increment 
o Username 
▪ Type: String 
▪ Description: Username for admin login. 
▪ Constraints: Unique, Not Null 
o Password 
▪ Type: String 
▪ Description: Encrypted password for admin authentication. 
▪ Constraints: Not Null 
o Email 
▪ Type: String 
▪ Description: Admin’s email address for communication. 
▪ Constraints: Unique, Not Null 
 
 8.1.5  Image Metadata 
• Description: Represents metadata for each image that may include tags, categories, or 
other image-related information. 
o Metadata id 
▪ Type: Integer 
▪ Description: Unique identifier for the metadata entry. 
▪ Constraints: Primary Key, Auto-increment 
o Image id 
▪ Type: Integer 
▪ Description: ID of the image associated with the metadata. 
▪ Constraints: Foreign Key (references Image) 
40  
o tags 
▪ Type: String 
▪ Description: Tags related to the image for categorization. 
▪ Constraints: Nullable 
o category 
▪ Type: String 
▪ Description: Category to which the image belongs. 
▪ Constraints: Nullable 
8.1.6 Session/Authentication 
• Description: Stores temporary session data for user authentication. 
o Session id 
▪ Type: String 
▪ Description: Unique session identifier for the user. 
▪ Constraints: Primary Key 
o User id 
▪ Type: Integer 
▪ Description: ID of the user associated with the session. 
▪ Constraints: Foreign Key (references User) 
o Login time 
▪ Type: Timestamp 
▪ Description: Timestamp when the user logged in. 
▪ Constraints: Default: Current Timestamp 
o Expiry time 
▪ Type: Timestamp 
▪ Description: Timestamp when the session will expire. 
▪ Constraints: Default: 1 hour after login time 
8.1.7  Image Deletion Logs 
• Description: Represents logs related to deleted images. Keeps track of deleted image 
data for auditing purposes. 
o Log id 
▪ Type: Integer 
▪ Description: Unique identifier for each deletion log. 
▪ Constraints: Primary Key, Auto-increment 
o Image id 
▪ Type: Integer 
▪ Description: ID of the deleted image. 
▪ Constraints: Foreign Key (references Image) 
 
o Deleted by 
41  
▪ Type: Integer 
▪ Description: ID of the user/admin who deleted the image. 
▪ Constraints: Foreign Key (references User or Admin) 
o Delete date 
▪ Type: Date 
▪ Description: Date when the image was deleted. 
▪ Constraints: Default: Current Date 
8.2 Guidelines for Creating Additional Data Dictionary Entries 
To create additional entries for the data dictionary based on the existing entities, consider the 
following guidelines: 
8.2.1   Entity Identification: 
o Define the entity first (e.g., User, Image, Admin). 
o Describe the purpose of the entity and its role within the system. 
 8.2.2     Attribute Definition: 
o Attribute Name: Use clear, descriptive names for attributes. 
o Type: Identify the data type (e.g., Integer, String, Date, Timestamp). 
o Description: Provide a short, concise description of what the attribute represents 
and how it is used. 
o Constraints: List the constraints (e.g., Not Null, Primary Key, Foreign Key, 
Unique). These ensure the integrity of the data. 
8.3.3      Relationships: 
o Foreign Keys: If the attribute references another entity, describe the 
relationship. For example, if an image id in the Image Metadata entity refers to 
an Image, state that the image id is a foreign key referencing the Image table. 
8.3.4   Default Values: 
 If the attribute has a default value (e.g., Current Date for registration date), specify  it 
in the constraints. 
42  
9.TEST CASES 
 
Test cases are derived from the Analysis and Design process, and they ensure that the 
application functions as expected. Below are the Test Cases for the AWS-Based Image 
Gallery Webpage. These test cases cover different modules, including user login, image 
upload, gallery viewing, and user authentication. 
 
9.1 Functional Test Cases 
 
 9.1.1 Test Case: User Login 
 
Test Case ID: TC001 
Module: User Authentication 
Objective: To verify that a registered user can successfully log in to the system. 
Test Steps: 
Open the login page. 
Enter a valid username in the "Username" field. 
Enter the correct password in the "Password" field. 
Click on the "Login" button. 
Expected Result: 
The user should be redirected to the dashboard/gallery page. 
A session is created, and the user's credentials are authenticated successfully. 
Pass Criteria: 
User is able to log in successfully and access their gallery. 
Fail Criteria: 
User is unable to log in, or incorrect credentials lead to error messages. 
 
 9.1.2 Test Case: User Registration 
 
Test Case ID: TC002 
Module: User Authentication 
Objective: To verify that a new user can successfully register. 
Test Steps: 
Open the registration page. 
Fill in the "Full Name", "Email", "Password", and "Confirm Password" fields. 
Click on the "Submit" button. 
Expected Result: 
A new user is successfully registered, and a confirmation message is displayed. 
The user can log in using the newly created credentials. 
Pass Criteria: 
User is registered, and details are stored in the database. 
Fail Criteria: 
43  
User registration fails if any required field is empty or passwords do not match. 
 
 9.1.3 Test Case: Image Upload 
 
Test Case ID: TC003 
Module: Image Upload & Storage 
Objective: To verify that a user can upload an image to the gallery. 
Test Steps: 
Log in to the system. 
Go to the image upload page. 
Choose an image from the local system using the "Choose File" option. 
Provide a title for the image (optional). 
Click on the "Upload Image" button. 
Expected Result: 
The image is uploaded to AWS S3. 
A success message is shown, and the image is displayed in the gallery. 
Pass Criteria: 
Image is successfully uploaded to the gallery and stored in S3. 
Fail Criteria: 
Image upload fails due to invalid file format or size. 
 
 9.1.4 Test Case: Image Deletion 
 
Test Case ID: TC004 
Module: Image Gallery Management 
Objective: To verify that a user can delete an image from the gallery. 
Test Steps: 
Log in to the system. 
Go to the image gallery page. 
Click on the "Delete" button next to an image. 
Confirm the deletion in the pop-up window. 
Expected Result: 
The image is removed from the gallery and deleted from AWS S3. 
A confirmation message is displayed. 
Pass Criteria: 
Image is deleted successfully from both the gallery and storage. 
Fail Criteria: 
Image is not deleted or system throws an error. 
 
 
 
 
44  
 9.1.5 Test Case: Image Viewing 
 
Test Case ID: TC005 
Module: Image Gallery Management 
Objective: To verify that a user can view an image in full size. 
Test Steps: 
Log in to the system. 
Go to the image gallery page. 
Click on any image thumbnail to view it in full size. 
Expected Result: 
The selected image is displayed in full size. 
The user can close the full-size view and return to the gallery. 
Pass Criteria: 
Image opens in full view without errors. 
Fail Criteria: 
Image does not open or there is an issue displaying the image. 
 
 9.1.6 Test Case: Forgot Password 
 
Test Case ID: TC006 
Module: User Authentication 
Objective: To verify the forgot password functionality. 
Test Steps: 
Open the login page. 
Click on the "Forgot Password?" link. 
Enter the registered email address. 
Click the "Submit" button. 
Expected Result: 
A password reset email is sent to the user’s registered email address. 
The user can reset their password using the link. 
Pass Criteria: 
Password reset email is received successfully. 
Fail Criteria: 
Email is not sent or an error occurs during the password reset process. 
 
 9.1.7 Test Case: Admin Login 
 
Test Case ID: TC007 
Module: Admin Authentication 
Objective: To verify that an admin can log in to the system. 
Test Steps: 
Open the admin login page. 
45  
Enter the admin credentials (username and password). 
Click on the "Login" button. 
Expected Result: 
Admin is able to log in and access the admin dashboard. 
Pass Criteria: 
Admin successfully logs in and is directed to the dashboard. 
Fail Criteria: 
Admin is unable to log in, and an error message is displayed. 
 
9.2 Non-Functional Test Cases 
  
These test cases focus on system performance, security, and reliability.   
 
 9.2.1 Performance Testing - Verify login response time under different loads.   - Check image upload time with various file sizes.   - Ensure quick image retrieval from AWS S3.   
 
9.2.2 Scalability Testing   - Test with multiple concurrent users logging in/uploading images.   - Check system behavior under heavy loads.   
 
 9.2.3 Security Testing  - Ensure password encryption using hashing algorithms.   - Check for SQL injection vulnerabilities in login and registration.   - Test access control to prevent unauthorized gallery access. 
 
9.2.4 Storage Testing  - Ensure images are stored securely in AWS S3.   - Test backup and recovery in case of system failures.   
 
 
 
 
46  
10.CONCLUSION 
 
The AWS-Based Image Gallery Webpage project successfully demonstrates how cloud 
services can be leveraged to create a scalable, secure, and cost-effective platform for users to 
upload, manage, and view images. By utilizing AWS's Free Tier services, such as S3 for 
storage, EC2 for hosting, RDS for database management, and IAM for user access control, the 
project offers a robust solution to handle image management for multiple users. The 
implemented system ensures that user data and images are handled securely while providing an 
efficient and seamless experience. 
 
This project report has detailed the deployment of an Image Gallery website on 
AWS using EC2 for hosting and RDS for database management. Throughout the 
report, we examined the project from multiple perspectives, including feasibility 
studies (economic, technical, and operational), detailed requirements (as per IEEE 
830- 1993 standards), system design using SSAD and OOAD methodologies, and 
comprehensive form designing with visual mockups. We also provided a clear data 
dictionary and a set of test cases to ensure that all functional and non-functional 
requirements are met. 
 
This project not only addresses the existing limitations of image storage systems by offering a 
scalable and secure cloud-based solution but also enhances accessibility by allowing users to 
easily upload and view images on a simple web interface. Furthermore, the use of AWS ensures 
that the solution can scale efficiently to meet future demands while maintaining minimal 
operational costs. 
 
In conclusion, the project meets the primary objectives of providing a secure, user
friendly, and scalable image gallery system. Future improvements may include 
advanced features such as image tagging with AI, enhanced search functionalities, 
and cloud CDN optimization to further improve image delivery and speed. 
 
47  
11.BIBLIOGRAPHY 
 
1. Pankaj Jalote, An Integrated Approach to Software Engineering. 
o This book provided foundational knowledge on software engineering concepts, 
which were critical in structuring the design and implementation of the Image 
Gallery Webpage. 
2. AWS Documentation: Amazon S3, IAM, RDS, EC2 Services. 
o Official AWS documentation was used extensively for understanding the 
configuration and best practices related to AWS services like S3 (storage), IAM 
(access control), RDS (database), and EC2 (hosting). 
3. IEEE 830.1993 Standard for Software Requirements Specification (SRS). 
o This standard was followed for defining the software requirements specification 
to ensure comprehensive and structured documentation. 
4. W3Schools Documentation on Web Technologies: HTML, CSS, JavaScript. 
o W3Schools provided practical resources for frontend development, which 
helped in building the user interface for the webpage. 
5. Flask Documentation (or Django/Node.js depending on backend choice). 
o Flask documentation (or Django/Node.js) was used for backend development to 
understand how to set up the API, handle requests, and interact with the AWS 
services. 
6. AWS IAM User Guide: 
o The IAM user guide provided detailed information on how to manage user 
access securely within the AWS ecosystem, crucial for implementing proper 
authentication and authorization mechanisms. 
 
