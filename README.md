<h1>ExpNo 1 :Developing AI Agent with PEAS Description</h1>
<h3>Name: YOGARAJ.S</h3>
<h3>Register Number:212223040248</h3>


<h3>AIM:</h3>
<br>
<p>To find the PEAS description for the given AI problem and develop an AI agent.</p>
<br>
<h3>Theory</h3>
<h3>Medicine prescribing agent:</h3>
<p>Such this agent prescribes medicine for fever (greater than 98.5 degrees) which we consider here as unhealthy, by the user temperature input, and another environment is rooms in the hospital (two rooms). This agent has to consider two factors one is room location and an unhealthy patient in a random room, the agent has to move from one room to another to check and treat the unhealthy person. The performance of the agent is calculated by incrementing performance and each time after treating in one room again it has to check another room so that the movement causes the agent to reduce its performance. Hence, agents prescribe medicine to unhealthy.</p>
<hr>
<h3>PEAS DESCRIPTION:</h3>
<table>
  <tr>
    <td><strong>Agent Type</strong></td>
    <td><strong>Performance</strong></td>
     <td><strong>Environment</strong></td>
    <td><strong>Actuators</strong></td>
    <td><strong>Sensors</strong></td>
  </tr>
    <tr>
    <td><strong>Medicine prescribing agent</strong></td>
    <td><strong>Treating unhealthy, agent movement</strong></td>
     <td><strong>Rooms, Patient</strong></td>
    <td><strong>Medicine, Treatment</strong></td>
    <td><strong>Location, Temperature of patient</strong></td>
  </tr>
</table>
<hr>
<H3>DESIGN STEPS</H3>
<h3>STEP 1:Identifying the input:</h3>
<p>Temperature from patients, Location.</p>
<h3>STEP 2:Identifying the output:</h3>
<p>Prescribe medicine if the patient in a random has a fever.</p>
<h3>STEP 3:Developing the PEAS description:</h3>
<p>PEAS description is developed by the performance, environment, actuators, and sensors in an agent.</p>
<h3>STEP 4:Implementing the AI agent:</h3>
<p>Treat unhealthy patients in each room. And check for the unhealthy patients in random room</p>
<h3>STEP 5:</h3>
<p>Measure the performance parameters: For each treatment performance incremented, for each movement performance decremented</p>

# Program:
```
class MedicinePrescribingAgent:
    def __init__(self):
        self.performance = 0
        self.current_room = 1

    def sense_temperature(self, temp):
        return temp

    def prescribe_medicine(self, temp):
        if temp > 98.5:
            print(f"Patient in Room {self.current_room} has fever ({temp}°F). Prescribing medicine.")
            self.performance += 10
        else:
            print(f"Patient in Room {self.current_room} is healthy ({temp}°F). No treatment needed.")

    def move_to_next_room(self):
        self.current_room = 2 if self.current_room == 1 else 1
        self.performance -= 1
        print(f"Moving to Room {self.current_room}... (Performance -1)")

    def run(self, room_temperatures):
        for i in range(2):
            temp = self.sense_temperature(room_temperatures[self.current_room - 1])
            self.prescribe_medicine(temp)
            if i == 0:  # Move once between the two rooms
                self.move_to_next_room()
        print("\nFinal Performance Score:", self.performance)


# Example simulation
room_temperatures = [99.0, 97.5]  # Room1: Fever, Room2: Normal
agent = MedicinePrescribingAgent()
agent.run(room_temperatures)

```
# OUTPUT:
<img width="802" height="139" alt="Screenshot 2025-10-22 093433" src="https://github.com/user-attachments/assets/1f562f53-0bd7-4c79-9955-f5b0a241a227" />

# Reesult:

Thus the Developing AI Agent with PEAS Description was implemented using python programming.
