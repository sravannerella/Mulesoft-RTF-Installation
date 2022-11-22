# Configuration

AWS Configure

```bash
aws configure
```

Create Key Pair

```bash
aws ec2 create-key-pair --region us-east-1 --key-name {KEY_NAME}
```

Creation of EKS Cluster

```bash
eksctl create cluster --name my-mule-eks --version 1.20 --region ap-southeast-2 --with-oidc --ssh-access --ssh-public-key {KEY_NAME}
```

Once the EKS Cluster is created, run the following command to retrieve the nodes.
```bash
kubectl get nodes -o wide
```

# Creation Runtime Fabric

- Navigate to `Anypoint Platform > Runtime Manager > RTF > Create RTF`
- Choose Amazon Elastic Kubernetes Service and Provide a name
- Select RTFCTL and capture the activation key


### Validation
```bash
rtfctl validate {ACTIVATION_KEY}
```

### Activate
Following command will install RTF on your kubernetes instance. Once installation is complete, Anypoint Platform RTF Section will reflect the changes.

```bash
rtfctl install {ACTIVATION_KEY}
```

