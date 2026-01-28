# Critical-thinking-project-SCM

## Critical Thinking Project


### Source Code Management for a Distributed Development Team


Introduction


As software development teams grow and spread across different locations, managing source code becomes more complex. In this project, I assume the role of a senior DevOps engineer in a mid-sized software company that is transitioning from a centralized development system to a distributed team structure.

Previously, the team used Subversion (SVN), a centralized version control system, but now plans to adopt a Distributed Version Control System (DVCS), with Git being the main option.

This project evaluates SCM tools, designs Git workflows, automates quality checks using CI/CD, enforces security best practices, and handles real-world Git challenges.

Task 1: Evaluate Different SCM Tools


Centralized vs Distributed Version Control Systems


A centralized version control system (CVCS) like SVN uses a single central server where all code is stored. Developers must connect to this server to commit or retrieve changes.

A distributed version control system (DVCS) like Git allows each developer to have a full copy of the repository, including its entire history.



Key Differences Between SVN and Git
Feature            SVN                Git

Repository model  Centralized        Distributed

Offline work       Limited           Fully supported

Speed              Slower            Faster

Branching          Heavy and slow    Lightweight and fast

Collaboration      Server-dependent  Highly flexible

Advantages of Git for Distributed Teams
1. Developers can work offline and commit changes locally.

2. Branching and merging are faster and safer.

3. Better support for parallel development.

4. Improved collaboration across different locations.

5. Strong integration with CI/CD tools.



Challenges of Git
1. Steeper learning curve for beginners.

2. Requires clear workflows to avoid confusion.

3. Poor practices can lead to messy commit histories.



Conclusion


Git is the best choice for a distributed development team because it offers flexibility, speed, and better collaboration compared to SVN. Although Git requires proper training and discipline, its advantages greatly outweigh its challenges in a distributed environment.

Task 2: Implement Git Workflows for a Team Project


Scenario


The team is developing a new web application. Multiple developers work on different features at the same time, but the main branch must always remain stable.



Chosen Workflow: Feature Branch Workflow (Git Flow Inspired)


Branching Strategy
1. main: Stable production-ready code

2. develop: Integration branch for tested features

3. feature/*: Used for new features

4. hotfix/*: Used for urgent bug fixes



Workflow Steps
1. Developer creates a feature branch:

git checkout -b feature/login-system

2. Code is written and committed locally.

3. Developer pushes branch to remote repository.

4. A Pull Request (PR) is created.

5. Team members review the code.

6. Automated tests run before merging.

7. After approval, the branch is merged into develop.



Best Practices
1. Keep feature branches small.

2. Write clear commit messages.

3. Use pull requests for all merges.

4. Rebase feature branches regularly to avoid conflicts.



Why This Works for Distributed Teams
1. Encourages collaboration and transparency.

2. Prevents unstable code from entering the main branch.

3. Supports simultaneous development without conflicts.

Task 3: Automate Code Quality and Deployment


CI/CD Integration Using GitHub Actions


To ensure high code quality, a CI/CD pipeline is integrated with GitHub.



Pipeline Overview
1. Triggered when code is pushed to a feature branch or PR is opened.

2. Automatically runs:

a. Unit tests

b. Code quality checks

c. Deployment to staging environment (if tests pass)



Pipeline Process
1. Developer pushes code to GitHub.

2. GitHub Actions workflow starts.

3. Tests and linting are executed.

4. If successful, code is deployed to staging.

5. If failed, merge is blocked.



Benefits
1. Early detection of bugs.

2. Faster development cycles.

3. Reduced human error.

4. Consistent deployment process.



Conclusion


Automating testing and deployment improves reliability and helps maintain consistent code quality across distributed teams.

Task 4: Enforce Security Best Practices


Security Measures Implemented
1. User Access Control

a. Role-based permissions (Admin, Write, Read).

2. SSH Key Authentication

a. Password login disabled.

b. Each developer uses a unique SSH key.

3. Branch Protection Rules

a. Prevent direct pushes to main.

b. Require pull request approvals.

c. Require passing CI checks.

4. Signed Commits

a. Enforced for critical branches.

5. Audit Logs

a. All changes tracked and logged in GitHub.



Why This Is Important
1. Prevents unauthorized access.

2. Protects sensitive data.

3. Ensures accountability.

4. Maintains repository integrity.

Task 5: Handle a Real-World Git Challenge


Scenario


Two developers accidentally introduced conflicting changes into the main branch after a failed merge.



Steps to Resolve the Conflict
1. Pull latest changes:

git pull origin main
2. Git identifies conflicting files.

3. Open files and manually resolve conflicts.

4. Mark conflicts as resolved:

git add .
git commit
5. Push resolved changes to remote repository.



Preventing Future Conflicts
1. Smaller and more frequent pull requests.

2. Better team communication.

3. Regular rebasing of feature branches.

4. Mandatory code reviews.

5. CI checks before merging.



Conclusion


Merge conflicts are common in collaborative development, but proper workflows and communication can significantly reduce their occurrence.

Overall Conclusion


This project demonstrates the importance of effective Source Code Management in a distributed development environment. By transitioning from SVN to Git, implementing structured workflows, automating testing and deployment, enforcing security measures, and learning how to resolve conflicts, the team can work more efficiently and securely.

Overall, Git provides a scalable and reliable solution for modern distributed software development.

