# Key Concepts
* Describe Networking on AWS
* Differentiate between Object and Block Storage
* Describe the different use cases for Amazon S3, Amazon EBS, Amazon EFS

## Networking Quiz. Graded Quiz • 10 min
[Networking Quiz](images/Networking%20Quiz.png)

# Storage on AWS
## Introduction to Storage on AWS
* Storage is one of the most important part of any application. For our directory application we are storing images on S3, names and location in RDS and static HTML files on webserver.
* S3: object lavel storage. In case of object level storage, to update or change the object we have to change the entire object. For e.g. changing the image
* RDS: Block level storage. Relational databases are block level storage where we can change perticular block in a datafile. for.e.g changing the location for a user.
* So S3 is more suitable for images, videos, text files etc and rest all we can use RDS

## Amazon Elastic Block Storage (EBS)
EBS provides the most common way of block storage that we use in AWS. EBS is a persistant block sorage volume to use with EC2 instance. Every EBL volume is automatically replicated to avaibality zones to protect you from component failure, which offers high availability and durability. EBS provide consistnce and low latency perfromance. In order to optimize the performance and cost of storage EBS provide the storage options like SSD and HDD. Note that EBS only attaches to one EC2 at a time.

## Amazon Simple Storage Service (S3)
It is highly scalable and durable service to store and retreive any maount of data. In S3 objects are stored in a bucket, you can write, read, and delete objects in your bucket. Buckets are the repositories of the objects like images, videos, text files etc. We get the url for each bucket.  Object inside the buckets are accessible using HTTP/HTTPS url. Because of this, bucket name should be unique across AWS and it should be DNS compliant.
Bucket url format> http://bucketname.s3.amazonaws.com/objectname
You can control the bucket and object access using access control lists. You can also enforce the https only connection. Max size limit for a object is 5 TB but there is no cap on size of a bucket. Note that all objects are by default private, so if you want to give someone access to it, you must do it explicitly.
You can choose the AWs region where bucket will be stored to reduce the latency, minimize cost and address regulatory requirements.

## Amazon Elastic File System (EFS)
Unlike EBS, Elastic File System is regionaly distributed that can automatucally attached to multiple EC2 simultaniously, including the instances in different VPC.
for e.g. We can use EFS to create a corporate file store where everyone connects to the same document store. And we can even enable the EFS File Sync, to sync data with on premise data storage.

