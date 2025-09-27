# Trivia

This project is part of **CS50’s Introduction to Computer Science (Week 8)** problem set.  
It implements a simple **web-based trivia quiz** using **HTML, CSS, and JavaScript**.

---

## 📚 Description
The trivia game contains:
- **Multiple-choice questions** – user clicks a button to select the answer  
- **Free-response questions** – user types an answer and submits it  

JavaScript is used to make the quiz interactive by providing **instant feedback** when the user submits an answer.

---

## 🛠 Technologies Used
- **HTML** → Page content and quiz structure  
- **CSS** → Styling for layout, colors, and design  
- **JavaScript** → Logic for answer validation and interactivity  

---

## ⚙️ Implementation Details
- In `index.html`:
  - **Part 1**: A multiple-choice trivia question (with at least 3 options)  
    - One `<h3>` heading for the question  
    - One button for each answer choice  
    - Exactly one correct answer  
  - **Part 2**: A text-based free-response question  
    - One `<h3>` heading for the question  
    - An input field for the user’s response  
    - A button to confirm the answer  

- In `script.js`:
  - For **Part 1** (multiple-choice):
    - When the user clicks a button:  
      - ✅ Correct choice → button turns **green** and displays “Correct!”  
      - ❌ Incorrect choice → button turns **red** and displays “Incorrect”  
  - For **Part 2** (free-response):
    - When the user confirms their answer:  
      - ✅ Correct → input field turns **green** and displays “Correct!”  
      - ❌ Incorrect → input field turns **red** and displays “Incorrect”  

---

## 📂 File Structure

📁 trivia
├── index.html # Main trivia page
├── styles.css # Styling for the quiz
└── script.js # Logic for interactivity


---

## 📝 Example Code Snippet

### HTML (Part 1 – Multiple Choice)
```html
<h3>What is the capital of France?</h3>
<button>Berlin</button>
<button>Paris</button>
<button>Madrid</button>
<p id="mcq-result"></p>

<h3>Who is known as the father of computers?</h3>
<input type="text" id="answer">
<button id="check">Check Answer</button>
<p id="fr-result"></p>

// Part 1: Multiple Choice
let buttons = document.querySelectorAll("button");
let result = document.querySelector("#mcq-result");

buttons[0].addEventListener("click", function() {
    this.style.backgroundColor = "red";
    result.innerText = "Incorrect";
});
buttons[1].addEventListener("click", function() {
    this.style.backgroundColor = "green";
    result.innerText = "Correct!";
});
buttons[2].addEventListener("click", function() {
    this.style.backgroundColor = "red";
    result.innerText = "Incorrect";
});

// Part 2: Free Response
document.querySelector("#check").addEventListener("click", function() {
    let input = document.querySelector("#answer");
    let frResult = document.querySelector("#fr-result");

    if (input.value.toLowerCase() === "charles babbage") {
        input.style.backgroundColor = "lightgreen";
        frResult.innerText = "Correct!";
    } else {
        input.style.backgroundColor = "lightcoral";
        frResult.innerText = "Incorrect";
    }
});






