# Automate-Task-Column-in-Asana-based-off-GitHub-pull-request-status

Description

Do you want your tasks to automatically move to a PR column in Asana whenever a GitHub pull request is opened? How about Asana task that automtically move to a Done or Complete column when a pull request is closed? Then just complete the steps below and you'll have your asana task moving to what ever column you want based off your GitHub Pull Request Status!

Steps

Step 1 : Create Asana Person Access Token (PAT)
https://developers.asana.com/docs/personal-access-token
![image](https://github.com/vanvsue001/Automate-Task-Column-in-Asana-based-off-GitHub-pull-request-status/assets/57229630/3be12a3e-6e4a-48eb-a0ae-e053b4121866)

Make sure to save this token in a safe place we'll use it again in the next steps.

Step 2: Load Asana PAT into GitHub Secrets
https://docs.github.com/en/actions/security-guides/using-secrets-in-github-actions
![image](https://github.com/vanvsue001/Automate-Task-Column-in-Asana-based-off-GitHub-pull-request-status/assets/57229630/26683010-97d9-4c8f-971f-a917cff1faef)

Name your secret ASANA_API_SECRET
![image](https://github.com/vanvsue001/Automate-Task-Column-in-Asana-based-off-GitHub-pull-request-status/assets/57229630/1bf98840-ed87-4acf-a0d2-af7748c14fa6)

Then in the textbox labled token copy and paste the token from step 1.

Step 3: Find Project ID and set ASANA_PROJECT_ID variable
The easiest way to find this is to open your Asana Project and the Project ID can be found in the URL
![image](https://github.com/vanvsue001/Automate-Task-Column-in-Asana-based-off-GitHub-pull-request-status/assets/57229630/d169f8d4-495e-4d40-b084-4581fae6875b)

Or you can use the Asana API Docs to find it
https://developers.asana.com/reference/getprojects
On the right side of the Docs you should see this pannel
![image](https://github.com/vanvsue001/Automate-Task-Column-in-Asana-based-off-GitHub-pull-request-status/assets/57229630/2867c3fa-2ad9-4b96-8cb1-7c332e6ec003)
Enter your Asana PAT from step 1 for the Bearer textbox then press "Try It!" 
It will return a list of all your projects and their Gids.
![image](https://github.com/vanvsue001/Automate-Task-Column-in-Asana-based-off-GitHub-pull-request-status/assets/57229630/8be0c62c-d715-427b-a4f2-a223b1d933cf)

Using the Gid of the project you want to automate set the ASANA_PROJECT_ID variable.
Example:
![image](https://github.com/vanvsue001/Automate-Task-Column-in-Asana-based-off-GitHub-pull-request-status/assets/57229630/5077482a-d01d-4c5d-adb7-f59c84a291fb)

Step 4: Find Section ID and set ASANA_SECTION_ID variable
You can find your sections Gid by using the Asana API Docs.
https://developers.asana.com/reference/getsectionsforproject
Now that we know our Project ID we can enter it into the textfield and then press "Try It!" to find our Section ID.
Example:
![image](https://github.com/vanvsue001/Automate-Task-Column-in-Asana-based-off-GitHub-pull-request-status/assets/57229630/20d33214-37cc-4f4e-96e6-e5ac61c832e6)
![image](https://github.com/vanvsue001/Automate-Task-Column-in-Asana-based-off-GitHub-pull-request-status/assets/57229630/a9f2497e-e60a-4fc6-8f20-23501bafaed9)

Now we can set the ASANA_SECTION_ID.
Example:
![image](https://github.com/vanvsue001/Automate-Task-Column-in-Asana-based-off-GitHub-pull-request-status/assets/57229630/87259750-f512-4365-94be-3ec0004561e4)
In this example we our moving our tasks to the Asana Column named "Completed".

Step 5: Linking your GitHub PRs to Asana
All you need to do is add a link to your Asana Task in your GitHub pull request description. 

Example:








