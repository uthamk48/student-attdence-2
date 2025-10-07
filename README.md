<!DOCTYPE html>
<html>
<head>
  <title>NG College Login</title>
  <style>
    body{
      background-color: #ffff;
      padding:20px;
      display:flex;
      justify-content: center;
    }
    a {
      color:black;
      padding:20px;
      border-radius:20px;
    }
    h1{
      padding :20px;
      border-radius:10px;
      background-color:blue;
      text-align: center;
      color:white;
      border:solid black;
    }
    form{
      color:black;
      background-color : white;
      border:solid black;
      text-align:center;
      padding: 300px;
    }
    h2{
      color:black;
      padding:20px;
    }
    button{
      padding:20px;
      width:50%;
      background-color:blue;
      border-radius: 20px;
      color:white;
    }
    input{
      justify-content:space-around;
    }
  </style>
</head>
<body>

  <form>
    <h1>NG College</h1>
    <h2>LOGIN</h2>
    
    <h3>Name</h3>
    <input type="text" id="username" required>
    
    <h3>Hallticket</h3>
    <input type="text" id="hallticket" required>
    
    <br><br>
    <button>Login</button>
  </form>

  <script>
    // list of valid students (name + hallticket)
    var students = [
      { name: "yelander", hallticket: "240440284681002" },
      { name: "Utham", hallticket: "240440284681086" },
      { name: "ch saibalaji", hallticket: "240440284681031" },
      { name: "Priya", hallticket: "11223" },
      { name: "Kiran", hallticket: "44556" },
      { name: "Suma", hallticket: "77889" },
      { name: "Rohit", hallticket: "99100" },
      { name: "Manoj", hallticket: "13579" },
      { name: "Anjali", hallticket: "24680" },
      { name: "Sneha", hallticket: "90807" }
      // 👉 You can add up to 100 here same format
    ];

    var loginBtn = document.querySelector("button");
    var errorMessage = document.createElement("div");
    errorMessage.style.color = "red";
    errorMessage.style.marginTop = "10px";
    errorMessage.style.fontWeight = "bold";
    loginBtn.parentElement.appendChild(errorMessage);

    // when user clicks login
    loginBtn.addEventListener("click", function(event){
      event.preventDefault();

      var nameInput = document.getElementById("username").value.trim();
      var hallticketInput = document.getElementById("hallticket").value.trim();

      // check if any student matches
      var found = false;
      for(var i = 0; i < students.length; i++){
        if(students[i].name.toLowerCase() === nameInput.toLowerCase() && students[i].hallticket === hallticketInput){
          found = true;
          break;
        }
      }

      if(found){
        window.location.href = "dashboard.html";
      } else {
        errorMessage.innerText = "Name or Hallticket is incorrect!";
      }
    });
  </script>

</body>
</html>
