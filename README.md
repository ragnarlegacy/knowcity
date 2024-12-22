# Knowcity

# Architectural Design:
  Host the application in multiple US regions. For Saudi Arabia, either host an application on Google or Oracle cloud and then create VPN 
  route between the cloud providers.

# High Availability
  Application Load Balancer
  Cloudfront distribution for caching data at edge locations
  Autoscaling Groups based on resource utilisation or predictive autoscaling by analysing the traffic pattern
  Database primary and secondary synchronous data replication
  Upload raw video to S3 buckets
  S3 buckets geo replication
  AWS backups
  CloudWatch Alarms and auto-scaling policies to handle failover
  Hosted on a global CDN such as AWS CloudFront or Azure Front Door for low latency, regional edge caching, and automatic failover

# Security and Compliance
  Security Groups at instance and VPC levels
  Create public and private subets
  Configure Nacl at subnet levels
  Configure WAF
  AWS Shield Advanced
  Integrate SSO with tools like AWS SSO or Azure AD
  Use IAM role for authentication and authorization
  KMS keys for database and S3 buckets encryption
  Use Secrets Manager for storing sensitive data
  Use ACM
  Ensure compliance with local regulations (e.g., GDPR, Saudi Arabia’s Personal Data Protection Law) by routing user requests and storing 
  data in their respective regions

# Scalabilty and Storage
  Use multi-region EKS or ECS clusters to host microservices
  AWS MediaConvert or FFmpeg for video processing
  Built on ClickHouse deployed on Kubernetes with storage in Amazon S3/Glacier for cost-effective long-term storage of logs

# Logging and Cost Management
  Set Cloudwatch for logging
  Aggregate Cloudwatch logs at Splunk or ELK stack
  Implement OpenTelemetry for distributed tracing
  Use AWS Cost Explorer for estimating cost
  Use AWS budgets for setting up budgets and cloudwatch alarms for threshold budget
  
