# copilot-phishing-agent-analysis

# Evaluation of the Microsoft Security Copilot Phishing Triage Agent

<img width="734" height="479" alt="Screenshot from 2026-01-08 12-53-00" src="https://github.com/user-attachments/assets/79bed7fc-7bce-4d9d-b73a-a64117e0d6fa" />


## 1. Introduction

Phishing remains one of the most common and effective entry points for ransomware, placing a significant operational burden on security operations center (SOC) teams. Analysts must manually review a constant stream of user‑reported suspicious emails, a process that is time‑consuming, repetitive, and prone to human error. At scale, this workload slows response times and increases the likelihood of missing genuine threats.

To address this challenge, Microsoft Defender includes the **Security Copilot Phishing Triage Agent**, an AI‑driven capability designed to automate the triage and classification of user‑submitted phishing emails. This report summarizes a 23‑day evaluation of the agent, focusing on performance, accuracy, operational impact, and efficiency gains.

---

## 2. Agent Overview

The Phishing Triage Agent uses large language model (LLM)–based reasoning to analyze reported emails, determine intent, and classify each submission as malicious or non‑malicious. Unlike static rule‑based systems, the agent applies contextual analysis, correlates signals across Microsoft Defender XDR, and uses threat intelligence to make informed decisions.

<table>
  <tr>
    <td><img src="https://github.com/user-attachments/assets/c564b1d1-41a8-47af-a7a9-9d9b749babb4" width="100%"></td>
    <td><img src="https://github.com/user-attachments/assets/2d9d21fa-ada8-49f5-9e1f-c2e24c89e4b3" width="100%"></td>
  </tr>
</table>


### Key Capabilities

- **Autonomous triage:** Automatically evaluates user‑reported phishing emails without requiring manual steps or custom code.
- **Transparent rationale:** Provides natural‑language explanations describing why an email was classified as malicious or benign.
- **Continuous learning:** Incorporates analyst feedback to refine future classifications and reduce false positives.
- **Deep investigation tools:** Uses email content analysis, URL and file detonation, screenshot inspection, threat intelligence, and cross‑platform signal correlation.

---

## 3. Purpose of the Evaluation

This 23‑day evaluation aimed to determine:

- How effectively the agent reduces manual triage workload  
- Whether classification accuracy improves operational efficiency  
- How quickly the agent processes user‑reported phishing submissions  
- The overall impact on incident resolution and SOC performance  
- SCU (Security Compute Unit) consumption per run  

---

## 4. Triggering Mechanism

The agent runs **automatically** whenever a user reports a suspicious email. This ensures immediate triage without requiring analyst intervention and provides consistent, repeatable classification across all submissions.

---

## 5. Integrated Data Sources and Plugins

During the evaluation, the agent leveraged:

- **Microsoft Defender XDR**
- **Microsoft Threat Intelligence**
- **Phishing Triage Agent core logic**

These integrations enabled enriched investigations, signal correlation, and accurate verdicts.

---

## 6. Access and Permissions

- Security administrators can fully manage the agent after deployment.
- Any user with permissions equal to or greater than the agent can view its output.

This ensures transparency and supports collaborative investigation workflows.

---

## 7. Workflow Example

### Assign Agent to Alert

- **Run by:** Phishing Triage Agent  
- **Duration:** 1.9 seconds  
- **Start:** Dec 27, 2025, 9:50 AM  
- **End:** Dec 27, 2025, 9:51 AM  
- **Trigger:** User‑reported phishing submission  

### Investigation Example

The agent initiated an investigation into a user‑reported phishing email titled **“Subject Redacted”**, originating from IP address `xxx.xxx.xxx.xxx`.  
It completed evidence collection in **1.2 seconds**.

### Analysis Tasks

- Investigated sender identity  
- Checked agent memory for similar past submissions  
- Analyzed URLs, IPs, and message content  
- Correlated threat intelligence  
- Performed email metadata inspection  

### Verdict

After a one‑minute investigation involving five evidence‑based tasks, the agent concluded the email was **non‑malicious**.

---

## 8. Evaluation Metrics (30‑Day Window)

<img width="848" height="315" alt="image" src="https://github.com/user-attachments/assets/a1349ea0-55b3-4324-a2d1-7515cf37b311" />

### Submission Volume
- **95** user‑reported phishing submissions triggered incidents

### Agent Coverage
- **64 / 95** incidents were addressed by the Phishing Triage Agent  
- Remaining incidents did not meet criteria for automated triage

### Resolution Effectiveness
- **57 / 64** incidents were resolved by the agent  
- These were classified as **false positives**, reducing analyst workload


<img width="555" height="205" alt="Screenshot from 2026-01-08 13-17-33" src="https://github.com/user-attachments/assets/21bb114f-3cab-44d2-9dd3-750d18db0c7e" />

### Mean Time to Triage (MTTT)
- Average time from submission to classification: **4 minutes 39 seconds**
  
<img width="603" height="472" alt="Screenshot from 2026-01-08 13-19-42" src="https://github.com/user-attachments/assets/b947fd04-7b53-415c-a77b-adfe81b27b58" />

### SCU Consumption
- Average SCU usage per agent run: **0.09 SCUs**  
- Indicates extremely efficient resource consumption
  
<img width="853" height="522" alt="image" src="https://github.com/user-attachments/assets/552a34ca-b3a1-49e1-9532-0501676a1380" />

---

## 9. Outcomes and Performance

### Operational Impact

- Significant reduction in manual triage workload  
- Faster classification of user‑reported phishing emails  
- Improved consistency in verdicts  
- Reduced noise from false positives  
- Analysts were able to focus on higher‑value investigations  

### Accuracy and Transparency

- Natural‑language explanations improved analyst trust  
- Clear reasoning reduced follow‑up questions  
- Feedback loop enabled continuous improvement  

### Efficiency Gains

- Automated triage accelerated response times  
- High‑volume submissions were processed in seconds  
- SCU usage remained low and predictable  

---

## 10. Lessons Learned

- The agent performs exceptionally well with user‑reported phishing emails, especially those containing URLs, attachments, or suspicious metadata.
- Transparent reasoning helps analysts validate decisions quickly.
- SCU consumption is minimal, making the agent cost‑effective at scale.
- Automated triage significantly reduces SOC fatigue and improves focus on real threats.
- Integrating analyst feedback enhances classification accuracy over time.

---

## 11. Conclusion

The Microsoft Security Copilot Phishing Triage Agent proved to be a highly effective tool for automating phishing triage, reducing manual workload, and improving SOC efficiency. Over the 23‑day evaluation period, the agent demonstrated strong performance, rapid processing times, and reliable classification accuracy. Its ability to filter out false positives and provide clear, explainable reasoning positions it as a valuable asset for modern security operations.

If expanded across an organization, the agent has the potential to dramatically reduce triage time, strengthen detection capabilities, and enhance overall security posture.
