# Quiz and Exam System

A Python and Tkinter desktop prototype for running a local multiple-choice quiz. It includes a student flow for registration and attempts, plus an administrator view for reviewing results and editing existing questions.

## Run the application

Use Python 3 with Tkinter on a machine with a graphical desktop. From the repository folder, run:

```bash
python Code
```

On first launch, the application creates `data.json` in the working directory with sample accounts and questions. Use a writable working directory and test data. To preserve the current results and questions, keep a backup of the JSON file before starting with a fresh copy.

## User flows

| Role | Workflow |
| --- | --- |
| Student | Create a local account or sign in, select an answer for each question, and see the final score. |
| Administrator | Sign in, view the latest score for each student, and edit an existing question, its four choices, and the expected answer. |

## How it works

```text
Tkinter main menu
  -> Student registration or sign-in -> Question screens -> Score -> data.json
  -> Administrator sign-in -> Results or question editing -> data.json
```

The quiz shows one question at a time. When a student selects **Next**, the app compares the selected option with the stored answer and adds one point for a match. At completion it shows the score and stores that student's latest result. The administrator results screen shows **Not Attempted** for students without a saved result.

| Local record | Contents |
| --- | --- |
| Student | Name, local sign-in data, and latest score |
| Administrator | Local sign-in record |
| Question | Prompt, four answer choices, and expected answer |

The repository contains the [application source](Code). The application stores its data in a single local JSON file, including demo credentials. It is suited to a classroom demonstration with test data.

## Manual verification

1. Launch the app from a new writable working directory and check that the main menu and `data.json` appear.
2. Register a test student, sign in, and complete a quiz with known answers.
3. Restart the program and verify the saved account and score.
4. In the administrator view, edit a sample question and check that the next student attempt displays the updated prompt and choices.
