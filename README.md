## Movie database API

This project provides an API for managing a movie database and their TV broadcast schedules.

## Setup Instructions

**Clone the repository**:

    git clone https://github.com/ritvarscaupenoks/Laravel-Movies.git

**Switch to the repo folder**:
   
    cd Laravel-Movies

**Install all the dependencies using composer**:
    
    composer install

**Copy the example env file and make the required configuration changes in the `.env` file**:

    cp .env.example .env

**Update the `.env` file with your database configuration**:

    DB_CONNECTION=mysql
    DB_HOST=127.0.0.1
    DB_PORT=3306
    DB_DATABASE=your_database
    DB_USERNAME=your_db_username
    DB_PASSWORD=your_db_password

**Run migrations**:

    php artisan migrate

**Start the development server**:

    php artisan serve

## Usage Instructions

**Access the API**:

    The API will be accessible at http://localhost:8000/

## API Endpoints

### Get All Movies

- **Endpoint**: `/movies`
- **Method**: `GET`
- **Description**: Retrieves a paginated list of movies sorted by the newest addition date.
- **Parametrs**: `title` (optional): Filter movies by title.

### Get Movie Details and Broadcasts

- **Endpoint**: `/movies/{id}`
- **Method**: `GET`
- **Description**: Retrieves details of a specific movie by ID, including current and future TV broadcast dates and channels, sorted by the nearest broadcast date.
- **Parametrs**: none.

### Add a New Movie

- **Endpoint**: `/movies`
- **Method**: `POST`
- **Description**: Adds a new movie to the database.
- **Parametrs**: 
   - `title` (string, required): The title of the movie.
   - `rating` (float, required): The rating of the movie.
   - `age_restriction` (string, optional): The age restriction of the movie.
   - `description`: (string, required): The description of the movie.
   - `premieres_at`: (datetime, required): The premiere date and time of the movie.

### Add a TV Broadcast to a Movie

- **Endpoint**: `/movies/{movie}/broadcasts`
- **Method**: `POST`
- **Description**:  Add a new TV broadcast date, time, and channel to a movie.
- **Parameters**:
   - `movie_id` (integer, required): The ID of the movie.
   - `channel_nr` (integer, required): The channel number.
   - `broadcasts_at` (datetime, required): The broadcast date and time.

### Delete a Movie

- **Endpoint**: `/movies/{id}`
- **Method**: `DELETE`
- **Description**:  Delete a movie by ID.
- **Parametrs**: none.






