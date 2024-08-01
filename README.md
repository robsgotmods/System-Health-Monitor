# System-Health-Monitor

How to Use
Configure the Script:

Set the LOG_FILE path to where you want to store the log file.
Adjust the thresholds (CPU_THRESHOLD, MEMORY_THRESHOLD, DISK_THRESHOLD, NETWORK_THRESHOLD) as needed.
Configure the email settings in EMAIL_CONFIG if you want to receive email alerts.
Run the Script: You can run the script manually to test it:


python system_health_monitor.py
Run the Script in the Background: To ensure the script runs continuously, you can run it in the background or use a tool like screen or tmux:



nohup python system_health_monitor.py &
Schedule the Script Using System Services:

For more robust usage, you can create a systemd service to ensure it runs on startup and restarts on failure.
system_health_monitor.service (systemd service file)
ini

[Unit]
Description=System Health Monitor

[Service]
ExecStart=/usr/bin/python3 /path/to/system_health_monitor.py
Restart=always

[Install]
WantedBy=multi-user.target
Save the above service file as system_health_monitor.service in /etc/systemd/system/.
Enable and start the service:

sudo systemctl enable system_health_monitor.service
sudo systemctl start system_health_monitor.service
