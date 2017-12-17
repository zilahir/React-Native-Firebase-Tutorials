# Tutorial-React-Native-Firebase-#3-Facebook-Login Complete Project Files.

- Learn how to add Facebook Login to Your React Native + Firebase App.

### Install Dependencies

```sh 
npm install 
```

### Configure App.js
```sh
// Initialize Firebase
const firebaseConfig = {
  // ADD YOUR FIREBASE CREDENTIALS
  apiKey: "",
  authDomain: "",
  databaseURL: "",
  projectId: "",
  storageBucket: "",
};
```

## Add your Facebook App Id
```sh
  async loginWithFacebook() {

    //ENTER YOUR APP ID 
    const { type, token } = await Expo.Facebook.logInWithReadPermissionsAsync('<APP ID>', { permissions: ['public_profile'] })

    if (type == 'success') {

      const credential = firebase.auth.FacebookAuthProvider.credential(token)

      firebase.auth().signInWithCredential(credential).catch((error) => {
        console.log(error)
      })
    }
  }
```


### That's all you need!  