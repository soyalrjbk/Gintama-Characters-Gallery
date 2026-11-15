# Gintama Characters Gallery

A full-stack photo feed for Gintama fans. Users can sign up, upload pictures of their favorite characters with a title and caption, browse everyone's posts in a gallery grid, and like or delete posts.

**Link to project:** https://gintama-characters-gallery.onrender.com

<img width="1438" height="856" alt="Screenshot 2026-11-14 at 10 18 30 PM" src="https://github.com/user-attachments/assets/e21c1460-3c2d-4b86-b957-267e9716ab49" />

<img width="1444" height="839" alt="Screenshot 2026-11-14 at 10 35 37 PM" src="https://github.com/user-attachments/assets/ea2e6eb2-c9a2-4d3e-973f-0b30e12594fe" />



## How It's Made:

**Tech used:**

![HTML5](https://img.shields.io/badge/HTML5-E34F26?style=for-the-badge&logo=html5&logoColor=white)
![CSS3](https://img.shields.io/badge/CSS3-1572B6?style=for-the-badge&logo=css3&logoColor=white)
![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?style=for-the-badge&logo=javascript&logoColor=black)
![Bootstrap](https://img.shields.io/badge/Bootstrap-7952B3?style=for-the-badge&logo=bootstrap&logoColor=white)
![EJS](https://img.shields.io/badge/EJS-B4CA65?style=for-the-badge&logo=ejs&logoColor=black)
![Node.js](https://img.shields.io/badge/Node.js-339933?style=for-the-badge&logo=nodedotjs&logoColor=white)
![Express](https://img.shields.io/badge/Express-000000?style=for-the-badge&logo=express&logoColor=white)
![MongoDB](https://img.shields.io/badge/MongoDB-47A248?style=for-the-badge&logo=mongodb&logoColor=white)
![Mongoose](https://img.shields.io/badge/Mongoose-880000?style=for-the-badge&logo=mongoose&logoColor=white)
![Cloudinary](https://img.shields.io/badge/Cloudinary-3448C5?style=for-the-badge&logo=cloudinary&logoColor=white)
![Passport](https://img.shields.io/badge/Passport-34E27A?style=for-the-badge&logo=passport&logoColor=white)

I built this app on top of the 100Devs `binary-upload-boom` starter and turned it into a themed gallery for Gintama characters. It follows the MVC pattern:

- **Models:** Mongoose schemas for users and posts, stored in MongoDB.
- **Views:** EJS templates for the login, profile, feed, and single-post pages.
- **Controllers:** handle creating, liking, and deleting posts and rendering each page.
- **Routes:** map URLs like `/profile`, `/feed`, and `/post/:id` to their controllers.

Authentication uses Passport.js with a local strategy, and sessions are stored in MongoDB so users stay logged in. Images are uploaded with Multer and stored on Cloudinary, and only the image URL and Cloudinary ID are saved in the database. The feed is a responsive CSS Grid that uses `aspect-ratio` and `object-fit: cover` so every character card is the same size, whatever the original image's dimensions.

## Optimizations

- Moved image storage to Cloudinary so the database only stores URLs instead of large binary files.
- Replaced the default stacked image layout with a responsive CSS Grid, so the feed looks even on any screen size.
- Next steps: comments on posts, filtering by character or arc, and user avatars.

## Lessons Learned:

Working in an existing codebase taught me how an MVC app connects end to end: a request goes through a route, then a controller, then the model, and a view renders the result. I also learned how file uploads work with Multer and Cloudinary, how Passport manages login sessions, and how to use CSS Grid and `object-fit` to make user-uploaded images of any size look consistent.

## Installation

1. Clone the repo and install dependencies:

```bash
npm install
```

2. Create a `.env` file in the `config` folder with:

```
PORT=2121
DB_STRING=<your MongoDB connection string>
CLOUD_NAME=<your Cloudinary cloud name>
API_KEY=<your Cloudinary API key>
API_SECRET=<your Cloudinary API secret>
```

3. Start the server:

```bash
npm start
```

4. Open `http://localhost:2121` in your browser.

## Acknowledgments

Built from the [100Devs binary-upload-boom](https://github.com/100devs/binary-upload-boom) starter. Gintama and its characters belong to Hideaki Sorachi and Shueisha. This is a non-commercial fan project.
