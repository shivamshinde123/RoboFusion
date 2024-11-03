# RoboFusion: Machine Learning-Driven Sensor Integration for Motion Control

Team Members: Ankit Gole, Harsh Chhajed,  Shivam Shinde, Shreya Boyane, Simran Chauhan

**1) What is exactly the function of your tool (or a method)? That is, what will it do?**
The proposed system allows users to control a robotic arm through hand gestures, interpreted using computer vision, machine learning algorithms, and sensor data. Built on the Robot Operating System (ROS2), this setup delivers a real-time, human-robot interface that enables precise and responsive manipulation of the robotic arm.

**2) Why would we need such a tool (or a method) and who would you expect to use and benefit from it?**
This tool is essential for achieving highly accurate robotic arm movements by combining the strengths of sensor data and machine learning predictions. Sensor data on its own can be prone to noise and inconsistency, leading to potential inaccuracies in crucial tasks. By combining sensor inputs with machine learning predictions, this approach creates a more precise and reliable control system, ensuring safer and smoother operation.

**3) Who Benefits and Why:**
**- Remote Operations in Hazardous Environments:** Workers operating robotic arms remotely in hazardous environments, such as nuclear facilities or disaster zones, can rely on precise movements, minimizing the risk of errors.
**- Manufacturing and Industrial Machinery:** Precise robotic control is vital for tasks like assembly, welding, and material handling, making this tool invaluable for reducing operational downtime and improving quality.
**- Medical Robotics:** In surgeries and remote medical procedures, even minor inaccuracies can have major consequences. This tool’s enhanced precision can be crucial for safe, effective robotic-assisted medical interventions.

**4) Do these kinds of tools/methods already exist? If similar tools/methods exist, how is your tool/method different from them?** 
- Our approach integrates ROS with machine learning to enable gesture recognition and precise angle adjustments, setting it apart from traditional methods that rely only on sensor data or preset gestures. The model interprets hand gestures, like finger twists and folds, with corresponding angles for more responsive control.
- By combining ROS with adaptive ML-based gesture recognition, our system enhances real-time control and facilitates intuitive, user-friendly human-robot interactions, especially in applications needing fine motor skills and precision.

**5) Would people care about the difference? How hard is it to build such a tool/algorithm? What is the challenge?**
- Yes, the difference would be significant for users in fields requiring precise robotic control, as even small improvements in gesture recognition and movement accuracy can greatly impact performance and safety. - The ability to interpret nuanced hand gestures with precision offers a smoother, more intuitive control experience, something that’s especially valuable in delicate applications, like remote surgeries or complex manufacturing tasks.

_Challenges in Building the Tool:_
- One of the primary challenges is generating high-quality training data. Accurate gesture recognition requires extensive, well-labeled data to teach the model to interpret complex hand movements accurately.
- Collecting and labeling this data, especially for subtle gestures, can be time-consuming and resource-intensive. Additionally, ensuring that the ML model integrates seamlessly with ROS and can operate in real time adds another layer of complexity to development.

**6) How do you plan to build it? You should mention the data you will use and the core algorithm that you will implement (either an existing algorithm for tools or a new algorithm for methods).**
_Our approach to building this system involves several key steps:_
Data Collection: We'll gather a dataset of hand gestures using a webcam feed. This data will capture various hand movements and angles (e.g., twists, and folds), which will serve as training data for the machine-learning model.

_Robotic Arm Simulation:_ We’ll simulate a robotic arm in Gazebo using ROS2, creating a realistic test environment where the robotic arm can respond to input in real-time.
_Machine Learning Model:_ Using the collected gesture dataset, we’ll train a machine learning model to predict specific hand movements and angles, allowing real-time robotic arms to mimic these gestures accurately.
_Sensor Integration with MPU6050:_ We’ll use the MPU6050 sensor to capture estimated hand movement angles directly. This sensor data provides a real-time angle estimation that complements our machine-learning predictions.
_Data Fusion:_ To achieve precise control, we’ll fuse the sensor data with ML predictions, combining the strengths of both to correct for any discrepancies and reduce noise.
_Final Robotic Arm Simulation:_ Once integrated, the ML model and sensor data fusion will be tested in the Gazebo simulation to refine accuracy, responsiveness, and robustness in robotic arm control.

**7) What existing resources can you use?**
To develop this system effectively, we’ll utilize a combination of existing software, hardware, and datasets:
**_Software and Tools:_**
_- ROS2 (Robot Operating System):_ Essential for creating, simulating, and controlling the robotic arm in a structured and modular environment.
_- OpenCV:_ For real-time image processing, which will aid in capturing and interpreting hand gestures from the webcam feed.
_- TensorFlow or PyTorch:_ For building and training machine learning models that can recognize and predict hand gestures and angles.
_- Simulation Tools:_ Use simulation environments (e.g., Gazebo ) to test and validate the control system in various scenarios before real-world implementation.
_- MediaPipe Library:_ To capture 3D hand tracking data from the webcam feed, allowing us to create a custom dataset with specific gestures and angles tailored to the project requirements.
**_Hardware:_**
_- Webcam:_ To capture hand gestures in real-time, providing the data necessary for training and live control of the robotic arm.
_- MPU6050 Sensor:_ For measuring hand movement angles, which will be integrated with ML predictions to improve accuracy.

**8) How will you demonstrate the usefulness of your tool/method?**
- Performance Metrics: We will establish key performance indicators (KPIs) such as gesture recognition accuracy, response time, and movement precision. By conducting quantitative tests, we can showcase improvements over existing methods.
- Real-World Scenarios: We will simulate various real-world applications, such as robotic-assisted surgeries or remote operations in hazardous environments. Demonstrating the tool in these contexts will highlight its practical benefits and versatility.
- Comparative Analysis: We will compare our tool's performance against traditional robotic control methods, highlighting advantages such as enhanced precision, flexibility, and adaptability through machine learning integration.

## Branching Strategy

![Image](https://github.com/user-attachments/assets/7df4e810-02ff-4304-9905-8a6b1745bf5a)


### 1. Main Branches
- **main branch:** This is the stable branch with production-ready code. Only thoroughly reviewed and tested code is merged here.
- **integration branch:** This branch is for integrating features before they’re finalized. All new features and bug fixes are merged into this branch first. Regularly updated from team members' contributions, it serves as the main staging area.

### 2. Development Branches
- **Feature branches (feature/branch-name):** Each team member should create a feature branch off `integration`for a specific task or feature. These branches focus on specific parts of the project (e.g., `feature/data-preprocessing`, `feature/model-selection`, etc.). Each `feature branch` is merged back into `integration`once complete.
- Naming Convention:  ` feature/short-description`  (e.g., `feature/data-collection`, `feature/model-training`)

- **Bugfix branches (bugfix/branch-name):** If issues arise during development, team members can create branches off `integration`for bug fixes. These branches are named descriptively (e.g., `bugfix/data-cleaning-issue`) and merged back into `integration`after testing.
- Naming Convention:  `bugfix/short-description` (e.g., `bugfix/missing-values`, `bugfix/model-overfitting`)

### 3. Pull Requests:
When ready, team members open Pull Requests (PRs) from feature branches into integration, moving the linked task in GitHub Projects to Review.
Other team members review the PR and suggest improvements if needed. Once approved, merge it into `integration`.

## Workflow
Planning and Assignment: Break down the project into distinct tasks (e.g., data preprocessing, feature engineering, model training, evaluation). Ensure that everyone has a clear feature branch in which to work.

**Daily Development:**
- Each team member pulls the latest integration branch and works on their respective feature branches.
- Team members commit frequently and push updates to their feature branches.

**Regular Integration:**
- Designate short integration sessions (e.g., every 2-3 days) for all members to merge their feature branches into integration.
- Review each feature branch with code reviews to check for any conflicts or issues.

 **Testing and Finalizing:**
- Toward the end of the project, focus on integrating and thoroughly testing the code in integration.
- Conduct final testing and review on the `integration` branch, and then merge it into `main `once the project reaches a stable, production-ready state.


## 7. Final Wrap-Up
When the project is complete and ready to submit, ensure all code from `integration` is thoroughly tested and merged into `main` for the final version. Tag this final commit as **v1.0.**
