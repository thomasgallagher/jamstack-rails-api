# Rails API for the Jamstack

A starter app for a Rails API to power Jamstack apps using Devise and Doorkeeper (oAuth) with sensible defaults.

[![Deploy](https://www.herokucdn.com/deploy/button.svg)](https://heroku.com/deploy)

## History

### Gemfile
gem 'devise'

### Terminal
rails generate devise:install

### config/environments/development.rb
config.action_mailer.default_url_options = { host: 'localhost', port: 3000 }

### Terminal
rails generate devise User

### db/migrate/20211103054517_devise_create_users.rb
Uncomment all properties

### app/models/user.rb
devise :database_authenticatable, :registerable, :recoverable, :rememberable,
       :validatable, :confirmable, :lockable, :timeoutable, :trackable

### config/initializers/devise.rb
config.password_length = 8..128

### Add example app/controllers/pages_controller.rb, pages routes, and pages views

### Make Gemfile compatible with Heroku
bundle lock --add-platform x86_64-darwin
bundle lock --add-platform x86_64-linux
