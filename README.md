# IBMMQ_Jmeter
Sample JMeter Script to connect to MQ. Thanks to 



Sample Issues Faced:

MQ Error 2035 - JMSWMQ2013: The security authentication was not valid that was supplied for queue manager 'QM1' with connection mode 'Client' and host name '127.0.0.1(1871)'.
Please check if the supplied username and password are correct on the queue manager to which you are connecting

Possible Solution  - Provide access to Queue Manager and Queues to your ID

Here are the steps to perform to overcome the following access issue:

On command prompt there four commands should be executed (here you can change the username(OS), queue name and queue manager name which is AS, DEV.QUEUE.1 and QM1 respectively, in my case)

setmqaut -m QM1 -t qmgr -p "AS" -all

setmqaut -m QM1 -t qmgr -p "AS" +setall +setid +altusr +connect +inq

setmqaut -m QM1 -n "DEV.QUEUE.1" -t q -p "AS" -remove

setmqaut -m QM1 -n "DEV.QUEUE.1" -t q -p "AS" +passall +passid +setall +setid +browse +get +inq +put +set








Credits: https://www.blazemeter.com/blog/ibm-mq-testing-with-jmeter-learn-how
