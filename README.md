<form id="loginForm">
  <label for="username">Username</label>
  <input type="text" id="username" name="username" required />

  <label for="password">Password</label>
  <input type="password" id="password" name="password" required />

  <button type="submit">Login</button>
</form>

<script>
  document.getElementById("loginForm").addEventListener("submit", function(e) {
    e.preventDefault();

    const username = document.getElementById("username").value;
    const password = document.getElementById("password").value;

    // Example: Send data to your backend API securely
    fetch("/api/login", {
      method: "POST",
      headers: { "Content-Type": "application/json" },
      body: JSON.stringify({ username, password })
    })
    .then(res => res.json())
    .then(data => {
      console.log("Server response:", data);
    })
    .catch(err => console.error(err));
  });
</script>
