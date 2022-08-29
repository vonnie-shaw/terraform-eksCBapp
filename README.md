# terraform-eksCBapp
# This repo is for running a simple application using terraform and eks
run terraform init
vi eks-clusters and change instance types to t2.micro
vi variables.tf and change default region to us-west-2
vi main.tf, under providers add default region to us-west-2, attach your access key and secret key
run terraform plan
run terraform apply
vi output.tf under region:values, change to us-west-2
run aws eks --region $(terraform output -raw region) update-kubeconfig \
    --name $(terraform output -raw cluster_name)

terraform output kubeconfig
