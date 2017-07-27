# Apache Hadoop 2.8.1 Docker image

Forked from https://github.com/sequenceiq/docker-hadoop-ubuntu

Updated to Hadoop 2.8.1 and Java 8.

# Build the image

```
docker build -t zoltannz/hadoop-ubuntu:2.8.1
```
# Pull the image

```
docker pull zoltannz/hadoop-ubuntu:2.8.1
```

# Start a container

In order to use the Docker image you have just build or pulled use:

```
docker run -it -p 2122:2122 -p 8020:8020 -p 8030:8030 -p 8040:8040 -p 8042:8042 -p  8088:8088 -p 9000:9000 -p 10020:10020 -p 19888:19888 -p 49707:49707 -p 50010:50010 -p 50020:50020 -p 50070:50070 -p 50075:50075 -p 50090:50090 zoltannz/hadoop-ubuntu:2.8.1 /etc/bootstrap.sh -bash
```

## Testing

You can run one of the stock examples:

```
cd $HADOOP_PREFIX
# run the mapreduce
bin/hadoop jar share/hadoop/mapreduce/hadoop-mapreduce-examples-2.8.1.jar grep input output 'dfs[a-z.]+'

# check the output
bin/hdfs dfs -cat output/*
```

# Hadoop management site

http://localhost:50070/dfshealth.html#tab-overview
