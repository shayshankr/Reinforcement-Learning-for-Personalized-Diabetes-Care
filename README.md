# Reinforcement-Learning-for-Personalized-Diabetes-Care

Reinforcement Learning for Personalized Diabetes Care
This project explores the application of Reinforcement Learning (RL) to develop personalized treatment strategies for individuals with Type 1 diabetes. The goal is to create an intelligent agent that can recommend optimal insulin dosages based on a patient's glucose levels and historical data, aiming to maintain blood glucose within a healthy range while minimizing the costs and side effects of treatment.
This repository contains the Jupyter Notebook with the complete code for data preprocessing, environment setup, agent training (using PPO and DQN algorithms), and evaluation against a rule-based agent. A meta-learning approach is also demonstrated to show how a pre-trained general model can be quickly adapted to a new patient.
Getting Started
To run this project, you can use Google Colab, which provides a free, cloud-based environment with all the necessary libraries pre-installed.
Prerequisites
A Google Account to access Google Colab.
The diabetes-data.zip dataset file.
Opening the Notebook in Google Colab
Navigate to Google Colab.
Click on File -> Open notebook.
In the pop-up window, select the GitHub tab.
Enter the URL of this repository: https://github.com/shayshankr/Reinforcement-Learning-for-Personalized-Diabetes-Care
Select the code_sr .ipynb notebook to open it.
Inserting the Dataset
The notebook requires the diabetes-data.zip file to be present in the Colab environment.
In the open Colab notebook, locate the file browser on the left-hand side.
Click on the "Upload to session storage" icon (a file icon with an upward arrow).
Select the diabetes-data.zip file from your local machine to upload it.
Important: The notebook expects the file to be at the path /content/diabetes-data.zip. Ensure the file is uploaded to the root /content/ directory.
How to Run the Code
Once the notebook is open and the dataset is uploaded, you can run the code cells sequentially.
Data Prepration: This section reads the raw patient data from the zip file, cleans and preprocesses it, and creates a unified pivot_df DataFrame. This DataFrame contains time-series data for each patient's glucose and insulin levels, along with normalized values.
Environment Creation: Here, a custom OpenAI Gym (now Gymnasium) environment named DiabetesEnv is defined. This environment simulates the patient's response to insulin actions and provides observations, rewards, and state transitions to the RL agent.
Agent Training - PPO Model: This section installs the stable-baselines3 library and trains a Proximal Policy Optimization (PPO) agent on the prepared data. The trained model is saved as ppo_diabetes_model.zip.
Loading PPO Agent: The saved PPO model is loaded, and a single evaluation episode is run to demonstrate its performance. The results, including total reward and its components (health improvement, side effect penalty, and cost penalty), are printed and visualized.
Rule Based Agent: A simple rule-based agent is defined as a baseline for comparison. This agent's logic is based on predefined glucose thresholds.
Agent Training DQN Model: This section trains a Deep Q-Network (DQN) agent on the data and saves the model as dqn_diabetes_model.zip.
Evaluation: A robust evaluation is performed by running 100 episodes for the PPO, DQN, and rule-based agents. The average total rewards are then compared in a bar chart to assess their relative performance.
META-LEARNING / FINE-TUNING DEMONSTRATION: This final section demonstrates a meta-learning approach. A base PPO model is trained on a general population of patients. This model is then fine-tuned on new, held-out patients to show how it can be quickly personalized. The performance of the fine-tuned model is compared to the base model's zero-shot performance on the new patients.
Models
Proximal Policy Optimization (PPO): A state-of-the-art policy gradient method that is known for its stability and performance.
Deep Q-Network (DQN): A value-based RL algorithm that uses a neural network to approximate the optimal action-value function.
Rule-Based Agent: A baseline agent that follows a simple set of predefined rules based on glucose levels.
