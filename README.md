
## Usage

Sample HTML pages are provided to showcase how to use this framework with a JavaScript application:

- signup.html - to create a new user, the email address will be validated sending a custom link to the verify.html page
- login.html - to login in, assuming an authenitcated role with Cognito
- verify.html - to validate the email address of a new user
- changePassword.html - to change password, knowing the old one
- lostPAssword.html - to ask for a passwrod reser, via email
- reset.html - to reset the password, linked by the email sent for a lost password

The same use cases can be implemented on a Mobile device using the [AWS Mobile SDK](http://aws.amazon.com/mobile/sdk/).

## APIs

The APIs are exposed as AWS Lambda Functions:

| Function              | Input                         | Output                                 |
|-----------------------|-------------------------------|----------------------------------------|
|LambdAuthCreateUser    |email, password                | created: true / false                  |
|LambdAuthVerifyUser    |email, verify                  | verified: true / false                 |
|LambdAuthLogin         |email, password                | login: true / false,	identityId, token|
|LambdAuthChangePassword|email, oldPassword, newPassword | changed: true / false                 |
|LambdAuthLostPassword  |email                          | sent: true / false                     |
|LambdAuthResetPassword |email, lost, password          | changed: true / false                  |
