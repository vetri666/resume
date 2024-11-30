<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Vetri Velan Anandan's Resume</title>
    <link rel="stylesheet" href="styles.css">
</head>

<body>
    <div class="container">
        <!-- Header Section -->
        <header>
            <h1>Vetri Velan Anandan</h1>
            <p>
                <a href="mailto:vetri.ary@gmail.com">vetri.ary@gmail.com</a> |
                <a href="tel:+15483844050">+1-548-384-4050</a> | Second Avenue, Kitchener, Ontario
            </p>
        </header>

        <!-- Objective Section -->
        <section id="objective">
            <h2>Objective</h2>
            <p>Seeking a challenging position in database development and reporting systems.</p>
        </section>

        <!-- Education Section -->
        <section id="education">
            <h2>Education</h2>
            <ul>
                <li><strong>PGDM in Reporting Systems and Database Development</strong>, Conestoga College, Canada (Expected Graduation: 2025)</li>
            </ul>
        </section>

        <!-- Work Experience Section -->
        <section id="work-experience">
            <h2>Work Experience</h2>
            <ul>
                <li>
                    <strong>Catalog Analyst</strong> at Walmart, India (14 months)
                    <ul>
                        <li>Analyzed and managed product catalogs.</li>
                        <li>Improved catalog accuracy by 15%.</li>
                    </ul>
                </li>
                <li>
                    <strong>System Administrator</strong> at Wipro, India (8 months)
                    <ul>
                        <li>Maintained and configured server environments.</li>
                        <li>Troubleshot system-level issues.</li>
                    </ul>
                </li>
                <li>
                    <strong>Technical Support Engineer</strong> at Zoho Corp, India (28 months)
                    <ul>
                        <li>Debugged email terminal and network issues.</li>
                        <li>Worked on anti-spam and abuse prevention with email firewalls.</li>
                    </ul>
                </li>
            </ul>
        </section>

        <!-- Skills Section -->
        <section id="skills">
            <h2>Skills</h2>
            <ul>
                <li>Java</li>
                <li>HTML</li>
                <li>MongoDB</li>
                <li>Data Analysis</li>
                <li>DNS/IP</li>
                <li>MySQL/PLSQL</li>
            </ul>
        </section>

        <!-- Certifications Section -->
        <section id="certifications">
            <h2>Certifications</h2>
            <ul>
                <li>Cloud Certification</li>
            </ul>
        </section>

        <!-- Projects Section -->
        <section id="projects">
            <h2>Projects</h2>
            <ul>
                <li>
                    <h3>Big Data Storehouse Model using Large Language Models</h3>
                    <p>Developing a scalable data model for efficient storage, retrieval, and analysis of large, diverse datasets using MongoDB and Studio 3T.</p>
                    <ul>
                        <li>Technologies used: Java, NoSQL, JSON</li>
                    </ul>
                </li>
            </ul>
        </section>
    </div>
</body>

</html>

-----------// script.js
document.addEventListener("DOMContentLoaded", function() {
            // Fetch the JSON data
            fetch('resume.json')
                .then(response => response.json())
                .then(data => {
                        // Render personal information
                        document.getElementById('name').textContent = data.personal_info.name;
                        document.getElementById('contact').innerHTML = `
                <p>Email: ${data.personal_info.email}</p>
                <p>Phone: ${data.personal_info.phone}</p>
                <p>Address: ${data.personal_info.address}</p>
            `;

                        // Render introduction
                        document.getElementById('intro-text').textContent = data.introduction;

                        // Render education
                        const educationList = document.getElementById('education-list');
                        data.education.forEach(edu => {
                            const li = document.createElement('li');
                            li.textContent = `${edu.degree} in ${edu.field} from ${edu.college}, ${edu.location} (${edu.graduation_year})`;
                            educationList.appendChild(li);
                        });

                        // Render skills
                        const skillsList = document.getElementById('skills-list');
                        data.skills.forEach(skill => {
                            const li = document.createElement('li');
                            li.textContent = skill;
                            skillsList.appendChild(li);
                        });

                        // Render work experience
                        const workList = document.getElementById('work-experience-list');
                        data.work_experience.forEach(job => {
                                    const li = document.createElement('li');
                                    li.innerHTML = `
                    <strong>${job.job_title}</strong> at ${job.company}, ${job.location} (${job.duration})<br>
                    Responsibilities: <ul>
                        ${job.responsibilities.map(res => `<li>${res}</li>`).join('')}
                    </ul>
                `;
                workList.appendChild(li);
            });
        })
        .catch(error => console.error('Error loading the JSON file:', error));
});


-----------

{
    "personal_info": {
        "name": "Vetri Velan Anandan",
        "email": "xxxx",
        "phone": "xxxxx",
        "address": "Second Avenue, Kitchener, Ontario"
    },
    "objective": "Seeking a challenging position in database development and reporting systems.",
    "education": [{
        "degree": "Post  Graduate Certificate",
        "field": "Reporting Systems and Database Development",
        "college": "Conestoga College",
        "location": "Canada",
        "graduation_year": 2025
    }],
    "work_experience": [{
            "job_title": "Catalog Analyst",
            "company": "Walmart",
            "location": "India",
            "duration": "14 months",
            "responsibilities": [
                "Analyzed and managed product catalogs.",
                "Improved catalog accuracy by 15%."
            ]
        },
        {
            "job_title": "System Administrator",
            "company": "Wipro",
            "location": "India",
            "duration": "8 months",
            "responsibilities": [
                "Maintained and configured server environments.",
                "Troubleshot system-level issues."
            ]
        },
        {
            "job_title": "Technical Support Engineer",
            "company": "Zoho Corp",
            "location": "India",
            "duration": "28 months",
            "responsibilities": [
                "Debugged email terminal and network issues.",
                "Worked on anti-spam and abuse prevention with email firewalls."
            ]
        }
    ],
    "skills": [
        "Java",
        "HTML",
        "MongoDB",
        "Data Analysis",
        "DNS/IP",
        "MySQL/PLSQL"
    ],
    "certifications": [
        "Cloud Certification"
    ],
    "projects": [{
        "title": "Big Data Storehouse Model using Large Language Models",
        "description": "Developing a scalable data model for efficient storage, retrieval, and analysis of large, diverse datasets using MongoDB and Studio 3T.",
        "technologies": [
            "Java",
            "NoSQL",
            "JSON"
        ]
    }]
}


-------------------


/* Global Styles */

* {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
}

body {
    font-family: 'Roboto', Arial, sans-serif;
    background-color: #494848;
    color: #aca8a8;
    padding: 40px;
    line-height: 1.6;
    font-size: 16px;
}


/* Container */

.container {
    max-width: 1000px;
    margin: 0 auto;
    background-color: #fff;
    padding: 40px;
    box-shadow: 0 4px 10px rgba(0, 0, 0, 0.05);
    border-radius: 8px;
}


/* Header Section */

header {
    text-align: center;
    margin-bottom: 30px;
    padding-bottom: 20px;
    border-bottom: 2px solid #007ACC;
}

header h1 {
    font-size: 2.5em;
    font-weight: 700;
    color: #084d7b;
    margin-bottom: 10px;
}

header p {
    font-size: 1em;
    color: #555;
}

header p a {
    color: #0565a4;
    text-decoration: none;
}

header p a:hover {
    text-decoration: underline;
}


/* Objective Section */

#objective {
    background-color: #f9f9f9;
    padding: 20px;
    border-radius: 8px;
    margin-bottom: 30px;
}

#objective h2 {
    font-size: 1.5em;
    font-weight: 600;
    color: #2b9de9;
    margin-bottom: 10px;
}

#objective p {
    font-size: 1.2em;
    color: #666666;
    margin-bottom: 20px;
}


/* Education Section */

#education {
    margin-bottom: 30px;
}

#education h2 {
    font-size: 1.8em;
    font-weight: 600;
    color: #007ACC;
    margin-bottom: 10px;
}

#education ul {
    list-style-type: none;
    margin-bottom: 20px;
}

#education li {
    font-size: 1.1em;
    color: #555;
    padding: 5px 0;
}

#education li strong {
    color: #007ACC;
}


/* Work Experience Section */

#work-experience {
    margin-bottom: 30px;
}

#work-experience h2 {
    font-size: 1.8em;
    font-weight: 600;
    color: #007ACC;
    margin-bottom: 10px;
}

#work-experience ul {
    list-style-type: none;
    margin-bottom: 20px;
}

#work-experience li {
    margin-bottom: 20px;
}

#work-experience li strong {
    font-size: 1.2em;
    color: #007ACC;
}

#work-experience ul li ul {
    margin-left: 20px;
}

#work-experience ul li ul li {
    font-size: 1.1em;
    color: #555;
}


/* Skills Section */

#skills {
    margin-bottom: 30px;
}

#skills h2 {
    font-size: 1.8em;
    font-weight: 600;
    color: #007ACC;
    margin-bottom: 10px;
}

#skills ul {
    list-style-type: none;
    padding-left: 0;
}

#skills li {
    display: inline-block;
    background-color: #007ACC;
    color: white;
    padding: 8px 15px;
    border-radius: 20px;
    margin: 5px;
    font-size: 1.1em;
}


/* Certifications Section */

#certifications {
    margin-bottom: 30px;
}

#certifications h2 {
    font-size: 1.8em;
    font-weight: 600;
    color: #007ACC;
    margin-bottom: 10px;
}

#certifications ul {
    list-style-type: none;
    padding-left: 0;
}

#certifications li {
    font-size: 1.1em;
    color: #555;
}


/* Projects Section */

#projects {
    margin-bottom: 30px;
}

#projects h2 {
    font-size: 1.8em;
    font-weight: 600;
    color: #007ACC;
    margin-bottom: 10px;
}

#projects ul {
    list-style-type: none;
    padding-left: 0;
}

#projects li {
    font-size: 1.1em;
    margin-bottom: 15px;
}

#projects li h3 {
    font-size: 1.3em;
    color: #007ACC;
    margin-bottom: 5px;
}

#projects li p {
    font-size: 1.1em;
    color: #555;
}

#projects li ul {
    padding-left: 20px;
}

#projects li ul li {
    font-size: 1.1em;
    color: #555;
}


/* Responsive Design */

@media (max-width: 768px) {
    body {
        padding: 20px;
    }
    .container {
        padding: 20px;
    }
    header h1 {
        font-size: 2em;
    }
    #objective,
    #education,
    #work-experience,
    #skills,
    #certifications,
    #projects {
        padding: 15px;
    }
    h2 {
        font-size: 1.5em;
    }
}

