# MongoDB-create-collection

Database Creation Using MongoDB
DATABASE NAME : zen_protal

1)Find all the topics and tasks which are thought in the month of October
db.tasks.find({month:”october”}).projection({task:1})
db.topics.find({month:”october”}).projection({topic:1})

2)Find all the company drives which appeared between 15 oct-2020 and 31-oct-2020
db.company_drives.find({appeared_date:{$gt:”15 OCT-2020”,$lt:”31 OCT-2020”}}).projection({company:1})

3)Find all the company drives and students who are appeared for the placement.
db.company_drives.find().projection.({company:1,user_appeared:1})

4)Find the number of problems solved by the user in codekata
db.codekata.find().projection.({user:1,problems_solved:1})

5)Find all the mentors with who has the mentee's count more than 15
db.mentors.find({total_students:{$gt:15}})

6) Find the number of users who are absent and task is not submitted  between 15 oct-2020 and 31-oct-2020
db.attendance.find({Attendance{oct:”false”}})
db.users.find().projection({task_submission:”No”})

List of Collections for above task :

Users :                                                                  
[{
  "id": 1,
  "name": "John Doe",
  "email": "john.doe@example.com",
  “Task_submissions”: “Yes”
},
{
  "id": 2,
  "name": "Jane Smith",
  "email": "jane.smith@example.com",
  “Task_submissions”: “Yes”
},
{
  "id": 3,
  "name": "Bob Johnson",
  "email": "bob.johnson@example.com",
  “Task_submissions”: “Yes”
},
{
  "id": 4,
  "name": "Alice Lee",
  "email": "alice.lee@example.com",
  “Task_submissions”: “No”
},
{
  "id": 5,
  "name": "Eva Brown",
  "email": "eva.brown@example.com",
  “Task_submissions”: “No”
}]

CodeKata :
[{
  "user": "John Doe",
  "problems_solved": 5
},
{ 
  "user": "Jane Smith",
  "problems_solved": 10
},

{
  "user": "Bob Johnson",
  "problems_solved": 20
},
{
  "user": "Alice Lee",
  "problems_solved": 30
},
{
   "user": "Eva Brown",
  "problems_solved": 40
}]

Attendance :
[{
  "name": "John Doe",
  "Attendance": [
    {
      "oct": "true"
    }
  ]
},
{
  "name": "Jane Smith",
  "Attendance": [
    {
      "oct": "true"
    }
  ]
},
{
  "name": "Bob Johnson",
  "Attendance": [
    {
      "oct": "true"
    }
  ]
},
{
   "name": "Alice Lee",
  "Attendance": [
    {
      "oct": "true"
    }
  ]
},
{
  "name": "Eva Brown",
  "Attendance": [
    {
      "oct": "true"
    }
  ]
}]

Company_drive:
[{ 
  "company": "facebook",
  "user_appeared": "john Doe",
  "appeared_date": "10 OCT-2020"
},
{
  "company": "zoho",
  "user_appeared": "Jane Smith",
  "appeared_date": "12 OCT-2020"
},
{
  "company": "HCL",
  "user_appeared": "Bob Johnson",
  "appeared_date": "15 OCT-2020"
},
{
  "company": "google",
  "user_appeared": "Alice Lee",
  "appeared_date": "18 OCT-2020"
},
{
  "company": "Amazon",
  "user_appeared": "Eva Brown",
  "appeared_date": "20 OCT-2020"
}]

Topics:
[{
   "month": "June",
  "topic": "HTML"
},
{
  "month": "July",
  "topic": "CSS"
},
{
  "month": "August",
  "topic": "Javascript"
},
{
   "month": "September",
  "topic": "React"
},
{
  "month": "October",
  "topic": "Node"
}]

Tasks :
[{
  "month":"June",
  "task":"Structure-Webpage"
},
{
  "month":"July",
  "task":"Webpage-Styling"
},
{
  "month":"August",
  "task":"Webpage-Functionalities"
},
{
  "month":"September",
  "task":"Webpage-UI"
},
{
  "month":"October",
  "task":"Webpage-Database deployment"
}]

Mentors :
[{
    "name":"imran",
    "total_students":10
  },
{
    "name":"alura",
    "total_students":11
  },
{
    "name":"vishnu",
    "total_students":19
  },
{
    "name":"jobs",
    "total_students":50
  },
{
    "name":"vijay”,
    "total_students":13
  }]
