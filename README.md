# How to run the code?
To run the code
1. BMV2 VM used: https://drive.google.com/uc?id=1lYF4NgFkYoRqtskdGTMxy3sXUV0jkMxo&export=download

2. Copy the SwitchTree folder to tutorials/exercises/Folder

3. cd to SwitchTree folder 

4. `make`

5. Open a new terminal and cd to tutorials/exercises/switchtree folder. Add rules (trained Decision Trees were translated to SwitchTree P4 rules using a script) to P4 switch by 

`simple_switch_CLI < decisiontree.txt`

6. Send the traffic using tcpreplay. A demo test file containing 1000 packets is provided in demo_data. It is extracted from UNSW database.

`sudo tcpreplay -i s1-eth1 demo_data/UNSW_1000_packets.pcap`

7. To obtain results, you make check the counter values. The number of malware flows injected (tracked using other means for statistics) is provided by counter_malware_flows and 
the actually detected ones are provided by counter_true_detection_flows. 

`simple_switch_CLI < get_results.txt`

8. Send the crafted packets using send.py file.

9. To capture the packets, execute the 'sudo wireshark' command while sending the crafted packet using send.py

10. To test the pcap file that we generated using send.py, use the command `sudo tcpreplay -i s1-eth1 demo_data/testing1.pcap` and then execute 'simple_switch_CLI < get_results.txt'
