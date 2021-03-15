AutoApiSecret-encrypted version
AutoApi series: AutoApi, AutoApiSecret, AutoApiSR, AutoApiS

Top
This project is based on the assumption that the original tutorial can call the api correctly , and the core is the py script of paran/shadow.
This project only provides an automatic, free, and no additional device script operation mode, in other words, it is a machine . (Because the original tutorial requires a server/extremely long-running equipment, most people do not have it, this project came into being)
Please be sure to read and understand the principle description and design concept of the original tutorial first .
The original tutorial said: There is no guarantee that it will be renewed! There is no guarantee that it will be renewed! There is no guarantee that it will be renewed ! In other words, it just increases the possibility of renewal .
If you understand and accept the above instructions, please proceed; if not, please click the X in the upper right corner of the browser.
project instruction
Use github action to automatically call api regularly and keep E5 development active.
It's free, no additional equipment/server is needed, and you don't need to worry about it after deployment.
Encrypted version, hide application id+confidential, protect account security.
Special instructions/Thanks
The original tutorial blogger-shady (kuan id-Paran): https://blog.432100.xyz/index.php/archives/50/
Normal version address: https://github.com/wangziyingwen/AutoApi
Encrypted version address: https://github.com/wangziyingwen/AutoApiSecret
Imitate the human application development version (including upgrade steps): https://github.com/wangziyingwen/AutoApiSR
Super version address (test): https://github.com/wangziyingwen/AutoApiS
Update log: https://github.com/wangziyingwen/Autoapi-test
Get the refresh_token widget from the web page (not recommended): https://github.com/wangziyingwen/GetAutoApiToken
Video tutorial: (My operation is very slow, I double speed/fast forward by myself)
Online/download address: https://kino-onemanager.herokuapp.com/Video/AutoApi%E6%95%99%E7%A8%8B.mp4?preview
Station B: https://www.bilibili.com/video/av95688306/
the difference
The project uses a public repository (open code), and everyone can see the content of your code.

So your application id, secret, and token will be displayed, which is not secure.

In the encrypted version, I hide the application id and secrets. The token needs to be updated in real time and cannot be hidden (I won't!). The security will be much higher!

Imitate the human application development version, as the name suggests.

step
The first step is to browse the original tutorial to learn how to get the application id, secret, and refresh_token to facilitate the next operation.

The second step is to log in/create a new github account, go back to the project page, click on the fork of the project code to your own account in the upper right corner, and then an identical project will appear under your account, and the next operations are in yours Under the project.

image

Obtain the application id, secret, and refresh_token according to the original tutorial (copy and save by yourself, pay attention to distinguish the id secret, don’t confuse it)

Then edit the 1.txt in your project online, and paste the entire refresh_token into it (there is my data, delete or overwrite it first). (Do not change 1.py)

The location of refresh_token is as shown below. Copy the content in the double quotation marks immediately following refresh_token (framed by the red vertical line), do not copy the double quotation marks into it. After copying into 1.txt, be careful not to leave spaces or blank lines at the end

image

The third step is to click the upper column Setting> Secrets> Add a new secret, and create two new secrets as shown in the figure: CONFIG_ID and CONFIG_KEY.

The contents are as follows: (change your application id to your application id, and your application secret to your secret, do not move the single quotes)

CONFIG_ID

= R & lt ID ' your application ID '
CONFIG_KEY

r = Secret ' your application confidential '
image

The final format should be similar to this:

image

The fourth step, enter your personal settings page (the upper right corner of the picture Settings, not the settings in the warehouse), select Developer settings> Personal access tokens> Generate new token,

image image

Set the name to GITHUB_TOKEN, then check the repo, admin:repo_hook, workflow and other options, and finally click Generate token.

image image image

The fifth step, click the star/star in the upper right corner to call immediately, and then click the above Action to see each running log and check the running status

(You must click in Test Api to see if the api is called in place and if there is any error. The Auto Api outside can only indicate that the operation is normal. We also need to confirm that the 10 api calls are successful, just like the picture. .If a few apis are missing, either the api permissions are not properly assigned when registering the application; or the onedrive is not logged in to activate, log in to activate)

image

The sixth step, if there is no error, it is done! ! Let's see if you want to modify the following timing times. Don't worry if you don't plan to modify it.

I set it to run automatically once an hour, and call it 3 rounds each time (click on the star/star in the upper right corner to call it immediately), you can modify it at your own discretion (I don't know how many calls and how long to keep active):

Timing and automatic start to modify the place: (in the .github/workflow/AutoApiSecret.yml file, Baidu cron timing task format, at least once every 5 minutes)
image

Modify the number of each round: (at the end of 1.py)
image

Digression
Api call You can go to the graph browser to take a look, learn to modify what api you want to call (the most important thing is to call outlook, onedrive) https://developer.microsoft.com/zh-CN/graph/graph-explorer/ preview

Introduction to GithubAction
Provided virtual environment:

· 2-core CPU · 7 GB RAM memory · 14 GB SSD hard disk space

Use restrictions:

Each warehouse can only support 20 parallel workflows at the same time.
GitHub API can be called 1000 times per hour.
Each job can be executed for up to 6 hours.
Users of the free version support a maximum of 20 jobs concurrently, and macOS only supports a maximum of 5.
The monthly accumulative usage time of the private warehouse is 2000 minutes, after exceeding it is $0.008/min, and the public warehouse is unlimited.
(The public warehouse we use here, logically, you can set up an infinite loop call, and then start it once every 6 hours to ensure 24 hours a day call)

At last
The tutorial is very straightforward, I should be able to do it!

Code noob, forgive me! If you have any questions/recommendations, you can click on the issues above to post it, or PY to me: wz.lxh@outlook.com

Created a Q group: 657581700, but no one

Finally, thank you again for shady/paran boss

———— wangziyingwen/kuan id-curly hair fungus
