AWS is one of the world's leading cloud service providers. Anybody can easily create an AWS account. The email address and password used to create the AWS account will be used as root account credentials (the account owner). After creating an AWS account, we can log in using the root user or IAM user credentials. However, AWS strongly advises against using the root account credentials for daily tasks. The person/user must be successfully authenticated and authorised by the AWS Identity and Access Management service to use any AWS service.

**What is AWS IAM?**
IAM stands for Identity and Access Management.

The AWS IAM service is used for creating users or roles that will be used to work around the AWS service.

AWS IAM is the first level of authentication that occurs when a user attempts to log in to their AWS account or access AWS services through the AWS management console or CLI.

If the credentials are incorrect or the user does not have the required permission, it will show an Unauthorized error. 

In layman's terms, AWS IAM is responsible for who (IAM user) can access (policies) the what(AWS services).

IAM is a free service. There are no charges incurred for using the IAM service.



**Main Concept of AWS IAM**

AWS IAM, or Identity and Access Management, is a service that helps you control who can access your AWS resources and what they can do with them. Think of it as a security guard that checks if someone has the right key to enter a building and what rooms they can go into.

**Key Features of AWS IAM**

1. **Users**
2. **User Groups**
3. **Roles**
4. **Policies**
5. **Identity Providers**

Now, let's dive into each feature one at a time.

**1. Users**

**Brief Explanation:** Users are individual accounts that you create for people who need access to your AWS resources.

**Detailed Explanation:** 
- Each user gets their own username and password.
- Users can log in to the AWS Management Console (the web interface) or use the AWS CLI (command line interface) to access resources.
- You can create up to 5000 users in one AWS account.

**Example:** Imagine you have a team of developers. Each developer gets their own IAM user account with specific permissions to access only the resources they need, like certain databases or servers.

**2. User Groups**

**Brief Explanation:** User groups are collections of users that share the same permissions.

**Detailed Explanation:**
- You can create a group and add users to it.
- Any permissions you give to the group are automatically given to all users in that group.
- A group can have up to 20 policies, and a user can be in up to 10 groups.

**Example:** You can create a "Developers" group and attach policies that allow access to development resources. Any user added to this group will automatically get these permissions.

**3. Roles**

**Brief Explanation:** Roles are like users, but they can be used by anyone who needs them, including AWS services or external entities.

**Detailed Explanation:**
- Roles don't have a username and password. Instead, they are assumed by users or services that need them.
- Roles can be used to give temporary access to AWS resources.

**Example:** If an EC2 instance (a virtual server) needs to upload files to an S3 bucket (storage), you create a role with the necessary permissions and assign it to the EC2 instance.

**4. Policies**

**Brief Explanation:** Policies are rules that define what actions are allowed or denied for users, groups, or roles.

**Detailed Explanation:**
- Policies are written in JSON (a simple data format).
- They specify what actions (like read, write, delete) are allowed on which resources (like S3 buckets, EC2 instances).
- There are AWS Managed Policies (pre-made by AWS) and Custom Managed Policies (created by you).

**Example:** You can create a policy that allows read access to an S3 bucket and attach it to a user or group.

**5. Identity Providers**

**Brief Explanation:** Identity providers are external systems that manage user identities and can be connected to AWS.

**Detailed Explanation:**
- If your company already uses a system like ADFS for managing users, you can link it to AWS.
- This allows users to log in to AWS using their existing credentials.

**Example:** If your company uses ADFS for user management, you can integrate it with AWS IAM so employees can use their usual login details to access AWS resources.













**IAM Security Best Practices - Basic**

1. **IAM Root User**
   - The root user is the top-level identity in an AWS account with full access to all services and administrative tasks.
   - It's important to protect the root user and avoid using it for daily tasks to prevent potential security risks.

   **Example:** Think of the root user as the master key to your house. You wouldn't use it for everyday tasks; instead, you'd use regular keys and keep the master key safe.

2. **Enforce MFA (Multi-Factor Authentication)**
   - MFA adds an extra layer of security by requiring two or more forms of verification.
   - AWS supports both virtual and physical MFA tokens.

   **Example:** MFA is like having a lock on your door and a security code. Even if someone gets your key, they still need the code to get in.

**IAM Security Best Practices - Advanced**

1. **Utilize IAM Groups**
   - Groups make it easier to manage permissions for multiple users.
   - You can assign permissions to a group, and all users in that group will inherit those permissions.

   **Example:** Instead of giving each employee a separate key to the office, you give a group key that works for everyone in the team.

2. **Make Use of Roles and Role Assumption**
   - Roles are not tied to specific users and can be assumed by anyone with permission.
   - Roles are useful for temporary access and can be assumed by multiple entities.

   **Example:** A role is like a guest pass that can be used by different people for specific tasks without needing a permanent key.

3. **Implement Resource-Based Policies**
   - These policies are attached to resources like S3 buckets and define who can access them.
   - They work alongside identity-based policies for more precise control.

   **Example:** Resource-based policies are like setting rules for who can enter specific rooms in a building, regardless of their general access level.

4. **Avoid Inline Policies**
   - Inline policies are embedded directly into IAM identities, making management harder.
   - It's better to use standard managed policies for easier administration.

   **Example:** Inline policies are like writing rules directly on each key, while managed policies are like having a central rulebook that applies to all keys.

5. **Configure Policies with Conditional Values**
   - Conditions add extra constraints to policies, like time of day or IP address.
   - They provide additional security for sensitive actions.

   **Example:** Conditions are like setting rules that only allow access during business hours or from specific locations.

**Other Security Best Practices**

1. **Make Use of Strong Passwords**
   - Enforce strong password policies to ensure better security.
   - Require regular password updates.

   **Example:** Strong passwords are like using a complex lock that is harder to pick.

2. **Remove Any Expired IAM Credentials**
   - Regularly check and remove unused IAM passwords and keys.
   - This prevents old credentials from being exploited.

   **Example:** Removing expired credentials is like changing locks when someone leaves the company to ensure they can't get back in.

3. **Use Distinct Access Keys**
   - Use unique access keys for different applications.
   - Encrypt keys and avoid reusing them.

   **Example:** Distinct access keys are like giving each application its own unique key, rather than sharing one key among many.

**Conclusion**

Securing IAM is critical for AWS security. By following these best practices, you can significantly improve your security posture and ensure that your AWS environment is well-protected.

