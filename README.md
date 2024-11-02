# REST Countries API with Dark Mode Theme Switcher

This is a solution to the [REST Countries API with color theme switcher challenge](https://www.frontendmentor.io/challenges/rest-countries-api-with-color-theme-switcher-UXlZ9weE) on Frontend Mentor. This project displays country data fetched from the REST Countries API with the ability to filter, search, and toggle between light and dark mode.

## Table of Contents

- [Overview](#overview)
  - [Features](#features)
  - [Screenshots](#screenshots)
  - [Links](#links)
- [My Process](#my-process)
  - [Built With](#built-with)
  - [What I Learned](#what-i-learned)
- [Continued Development](#continued-development)
- [Useful Resources](#useful-resources)
- [Author](#author)
- [Acknowledgments](#acknowledgments)

## Overview

### Features

Users can:
- View all countries from the REST Countries API on the homepage.
- Search for a country using the input field.
- Filter countries by region using the dropdown.
- View detailed information about a selected country on a separate page.
- View and click on neighboring countries (border countries).
- Toggle between light and dark mode.

### Screenshots

**Light Mode**
![Light Mode Screenshot](path_to_light_mode_screenshot)

**Dark Mode**
![Dark Mode Screenshot](path_to_dark_mode_screenshot)

### Links

- **Solution URL:** [Solution Link](https://www.frontendmentor.io/solutions/your-solution-link)
- **Live Site URL:** [Live Demo](https://your-live-site-link)

## My Process

### Built With

- Semantic HTML5 markup
- CSS custom properties
- Flexbox
- CSS Grid
- Mobile-first workflow
- JavaScript
- Fetch API

### What I Learned

This project helped me solidify the following concepts:
- Fetching and handling API data dynamically.
- Implementing light/dark mode using CSS custom properties.
- Managing search and filter functionality in JavaScript.
  
Here’s a code snippet showcasing how I fetched and displayed countries:

```js
fetch('https://restcountries.com/v3.1/all')
  .then(res => res.json())
  .then(data => {
    renderCountries(data);
  });

function renderCountries(data) {
  countriesContainer.innerHTML = '';
  data.forEach(country => {
    const countryCard = document.createElement('a');
    countryCard.classList.add('country-card');
    countryCard.href = `/country.html?name=${country.name.common}`;
    countryCard.innerHTML = `
      <img src="${country.flags.svg}" alt="${country.name.common} flag" />
      <div class="card-text">
          <h3 class="card-title">${country.name.common}</h3>
          <p><b>Population: </b>${country.population.toLocaleString()}</p>
          <p><b>Region: </b>${country.region}</p>
          <p><b>Capital: </b>${country.capital?.[0]}</p>
      </div>
    `;
    countriesContainer.appendChild(countryCard);
  });
}
Link of Project:
https://670d0cd8853a21cbf9a1ee9e--cozy-crepe-a85da0.netlify.app/
