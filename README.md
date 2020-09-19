# Git setup steps

## Pre-requirements
* If you are using latest version of eclipse, ignore this step. Install egit plugin in eclipse : http://www.eclipse.org/egit/download/
* Install git in your system and make sure that it is accessible from command promt : https://git-scm.com/book/en/v2/Getting-Started-Installing-Git

## Setup Environment Steps
**`NOTE : Every occurrence of << >> indicate the place holder, not actual value.`**
#### 1. Fork repository (You might be using some other clients like Gitlab, that does not matter here)
* Please note, everytime you might not need forking, it depends on your project guidelines, refer https://www.atlassian.com/git/tutorials/comparing-workflows/forking-workflow 
* Go to the repository (on htpps://github.com) where you are going to push your final code. It will be something like this : https://github.com/somecompany/somerepo
* Click the `Fork` button on above repository page.
* If you don't get above step, please refer : https://help.github.com/articles/fork-a-repo/#fork-an-example-repository

#### 2. Clone Repository
* Go to your repository home page. This URL will be something like this : **`https://github.com/<<username>>/somerepo`**.
* Copy the repository URL from above repository page on github. This url will be something like this : **`https://github.com/<<username>>/somerepo.git`**
* Open command prompt at your desired directory where you want to clone the repository.
* Type command : **`git clone <<copied url from above step>>`**
* It will ask for your username and password, please provide it.

### 3. Add Upstream (needed only if forked)
* Type command : **`git remote add upstream https://github.com/somecompany/somerepo.git`** (Cross verify this URL from your repository page from Github)

**`NOTE : Above 3 steps are required only once when you do new repository setup.`**

### 4. Fetch from Upstream OR Origin
* Type command : **`git fetch upstream`** (useful only in case of forking)
* Type command : **`git fetch origin`** (do it always)

### 5. Create New Local Branch from Upstream OR Origin
* Type command : **`git checkout -b <<branch_name_based_on_new_feature>> upstream(OR origin)/master`** (Cross verify the branch name which is being used for developing purpose from your repository owner, here we have assumed the **`master`** branch)

### 6. Do Code
* Import existing project in eclipse (or any of your favorite IDE)  and do changes.

### 7. Add to Index
* Once you are done with code changes which you need to add to index all of changed files, I have mentioned below two ways of doing this. 
* Command way : `git add <<relative_path_of_your_file>>`
* Eclipse way : Once you are done with code changes which you need to commit, right click on those files from **`Eclipse`** and click on **`Add to Index`**. (I prefer you set yuor own shortcut for this as it's most needed one)

### 8. Commit Changes
* Command way : Type `git status` to check which files are going in next commit. The indexed files will be visible in green color. Once you are happy with those files, please type command `git commit -m <<your_commit_msg>>`. 
* Eclipse way : Open **`Git Staging`** view in **`Eclipse`** and make sure above indexed files are listed there. Click on **`Commit`** button (visible on **`Git Staging`** view ).

### 9. Pull changes done by others
* We need to pull changes so that we can resolve conflicts before push.
* Type command : **`git pull upstream(OR origin) master`** (Make sure you are using the same branch name here which we have used in Step 5 : **`upstream/master`**)

## 10. Resolve Conflicts, if any
* If you get conflicts for any files as output of **`Step 9`**, then follow below steps (10.a and 10.b), else go to next **`Step 11`**.
* 10.a : Resolve those conflicts manually
* 10.b : Repeat from **`Step 7`**.

### 11. Push code
* Type command : **`git push origin <<current_branch_name>>`**
* You can cross verify the current branch name with **`git branch`** command.

### 12. Create PR (pull request)
* Refer : https://help.github.com/articles/creating-a-pull-request/

### 13. Repeat from step 4.
