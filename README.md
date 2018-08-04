import os, time
import serial, random    
ser = serial.Serial('com36', 9600）    # open serial port
print ser.portstr    # check which port was really used
for i in range(1):
    print "Round ", i+1
    ser.write("\xA0\x01\x01\xA2")    # turn on
    t = random.uniform(0.35, 0.35)
    print "sleep ", t
    time.sleep(t)
    ser.write("\xA0\x01\x00\xA1")    # turn off
    print "sleep 3"
    time.sleep(2)
    
ser.close()    # close port
