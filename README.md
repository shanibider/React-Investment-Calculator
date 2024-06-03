# React Investment Calculator 📈💻
[![React](https://img.shields.io/badge/React-★★★★★-blue)](https://react.dev/)
[![Vite](https://img.shields.io/badge/Vite-★★★★★-yellow)](https://vitejs.dev/)
[![Javascript](https://img.shields.io/badge/JavaScript-★★★★★-orange)](https://developer.mozilla.org/en-US/docs/Web/JavaScript)

This project is a simple and efficient investment calculator built using **React** and **Vite**. <img height=25px src="https://skillicons.dev/icons?i=react"> <img height=25px src="https://skillicons.dev/icons?i=vite">
<br> It demonstrates the power of modern web development tools to create fast and interactive web applications.

## Tech Stack 💻
This project use the following technologies:

[![My Skills](https://skillicons.dev/icons?i=js,react,vite)](https://skillicons.dev)

- [x] **React**: A JavaScript library for building user interfaces.
- [x] **Vite**: A next-generation front-end tooling that focuses on speed and performance.

The application consists of three main components:
- [ ] `Header`
- [ ] `UserInput`
- [ ] `Results`



## Components 🧩

The application is structured using the following main components:

### 1. Header Component
Located in `src/components/Header.jsx`, this component renders the title and a brief introduction to the application.

```jsx
import logo from '../assets/investment-calculator-logo.png';

export default function Header() {
    return (
    <header id="header">
    <img src={logo} alt="logo" />
    <h1>Investment Calculator</h1>
    </header>
);}
```

### 2. UserInput Component
Located in `src/components/UserInput.jsx`, this component includes input fields for the user to enter their investment details.

```jsx
import React, { useState } from 'react';
// User Input Component - work process:
// Create a form with input fields for initial investment, annual investment, expected return, and duration.
// Manage the state for each input field.
// Handle form submission and pass the input values back to the parent component.

export default function UserInput( {onChange, userInput } ) {
 // Return JSX to render the form with styled input fields.
  return (
    <section id="user-input">
    {/* first input group */}
        <div className="input-group">
        <p>
            <label>Initial Investment:</label>
            <input
            type="number" required
            value={userInput.initialInvestment}
            onChange={(event) => onChange('initialInvestment', event.target.value)}
            />
        </p>

        <p>
            <label>Annual Investment:</label>
            <input
            type="number" required
            value={userInput.annualInvestment}
            onChange={(event) => onChange('annualInvestment', event.target.value)}
           />
        </p>
        </div>

    {/* second input group */}
       <div className="input-group">
        <p>
            <label>Expected Return:</label>
            <input
            type="number" required
            value={userInput.expectedReturn}
            onChange={(event) => onChange('expectedReturn', event.target.value)}
            />
        </p>

        <p>
            <label>Duration (years):</label>
            <input
            type="number" required
            value={userInput.duration}
            onChange={(event) => onChange('duration', event.target.value)}
            />
            </p>
        </div>

        <button type="submit">Calculate</button>
    </section>
  );}
```


### 3. Results Component
Located in `src/components/Results.jsx`, this component displays the calculated investment returns based on the user input.

```jsx
export default function Results({ input }) {
    console.log(input);
    return <p>Results...</p>
}
```



### 4. App.jsx
```jsx
import React, { useState } from 'react';
import Header from './components/Header.jsx'; 
import UserInput from './components/UserInput';
//import ResultTable from './components/ResultTable';
//import { calculateInvestmentResults } from './util/investment';
import './index.css';
import Results from './components/Results.jsx';

// Handle User Input and Display Results
function App() {
// State variable to store user inputs (from investment.js)
const [userInput, setUserInput]= useState({
  initialInvestment: 1000,
  annualInvestment: 1200,
  expectedReturn: 6,
  duration: 10,
});

// Handle Form Submission: Create a function to handle form submission.
// Pass the input values to the parent component via props.
 function handleChange (inputIdentifier, newValue) {
  setUserInput(prevUserInput => {
      return {
          ...prevUserInput,
          [inputIdentifier]: newValue
      };
});
};

  return (
    <>
    <Header />
    <UserInput userInput={userInput} onChange={handleChange}/>
    {/* results go here */}
    <Results input={userInput}/>
    </>
  )
}
export default App
```

---

## Installation + Development 🛠️⚙️

To set up the project locally, follow these steps:

1. **Clone the repository:**
   ```sh
   git clone https://github.com/your-username/React-Investment-Calculator.git
   ```

2. **Install dependencies:**
   ```sh
   npm install
   ```
   
3. **Start the Development Server**

To start the development server, use the following command:

```sh
npm run dev
```

This will start the Vite development server, which is optimized for fast reloads and a smooth development experience. You can access the application at `http://localhost:3000`.

4. **Build for Production**

To build the application for production, use:

```sh
npm run build
```

This command will bundle the application using Vite, optimizing the output for production deployment.


## Screenshot 🖼️

![investments clculator](https://github.com/shanibider/React-Investment-Calculator/assets/72359805/b5691df4-2389-4be3-a731-78dd05cf49d7)

---


##### Happy Coding! 🥳

## 📫 Connect with me 😊
[![linkedin](https://img.shields.io/badge/linkedin-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/shani-bider/)
[![portfolio](https://img.shields.io/badge/my_portfolio-000?style=for-the-badge&logo=ko-fi&logoColor=white)](https://shanibider.onrender.com/)
[![gmail](https://img.shields.io/badge/Gmail-D14836?style=for-the-badge&logo=gmail&logoColor=white)](mailto:shanibider@gmail.com)

<footer>
<p style="float:left; width: 20%;">
Copyright © Shani Bider, 2024
</p>
</footer>
