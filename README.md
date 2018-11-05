# SEC334 Lab Documentation
AWS SEC334 Labs are sections out between Lab 1 and 2, and their parts.

# Lab 1

Identity and Access Management / Organizations

1. Explain how to use SCP in AWS Organizations to enforce compliance
  1. Create SCPs to enforce Health Care Compliance
2. Deploy restricted-ssh Config Rule from Console
  1. restricted-ssh Config Rule checks whether security groups that are in use disallow unrestricted incoming SSH traffic.

## Part 1

Explain how to use SCP in AWS Organizations to enforce compliance

Create SCPs to enforce Health Care Compliance

##

Sign in to the AWS Console

1. Browse to [https://aws.amazon.com/console/](https://aws.amazon.com/console/)

1. Click the &quot;Sign In to the Console&quot; button in the upper right hand corner of the screen
2. Enter your account ID, your IAM user name, and Password and then click the Sign In button



1. Type AWS Organizations in the &quot;Find a service by name or feature&quot; field and hit enter

1. Click Create Organization
2. Click Create Organization again to confirm
3. Click on Policies



1. Click Create Policy and name it (whatever you want). Add a description. From here, we will want to describe it as a custom policy that applies to our compliance needs. For the overall effect, we will select Allow.



1. Scroll down the page to the Statement Builder. From here, we will select the services we want the other accounts to have access to and applies to our compliance need. From here, we can dynamically add the services we want, and control what functions are available to the account. Create statements one at a time. Click on select service and choose a service. Select as many actions as you want to include for that service and click add statement. Once all services are completed, click Create Policy.



1. This will bring you back the Policies screen. From here, you can manage the policy. You can attach it to the accounts you specify, edit the JSON policy manually, or attach the policy to an OU.



1. If you wish to edit the policy manually, select the policy you created, and click Policy Editor.



1. From this page, you can view the ID, and ARN of the policy. This information can be view via the AWS CLI using aws organizations list-polices –filter SERVICE\_CONTROL\_POLICY



1. Scroll down to the bottom on the page, and you will see the JSON object for the policy we have built. From here you can manually edit the policy to add/remove services and features from the policy.



1. If you wish to create your own policy via template, and upload it, you can using the AWS CLI. Here I have created a policy named &quot;cli-example-policy&quot; using the aws organizations createpolicy command and importing my custom JSON object.



1. Go back to the Organizations Policies page, and I can see the policy I have created using the AWS CLI.





## Part 2



Deploy from Console

restricted-ssh Config Rule - Checks whether security groups that are in use disallow unrestricted incoming SSH traffic.

Purpose - Checks whether security groups that are in use disallow unrestricted incoming SSH traffic.

1. Click Services at the top left hand corner of the screen

2. Type &quot;Config&quot; into the search field in the AWS services section. Hit enter.

3. Click &quot;Rules&quot; on left hand navigation menu under AWS Config

4. Click Add rule button in the top center of the screen

5. In the Filter by rule name, label or description field, type &quot;ssh&quot; and click enter.

6. Click restricted-ssh box

7. Review settings and click Save button in the bottom right hand corner.

8. Rule has been successfully added and is currently being evaluated for compliance

9. Evaluate restricted-ssh rule by looking under Rule name and clicking on restricted-ssh.
