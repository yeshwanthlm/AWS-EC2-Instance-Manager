# AWS EC2 Instance Manager

A browser-based tool to manage EC2 instances across all AWS regions.

![EC2 Manager Screenshot](images/logo.png)

## Overview

AWS EC2 Instance Manager is a static web application that allows users to:

- View all running EC2 instances across all AWS regions
- Stop or terminate instances with a single click
- Manage instances without needing to switch between regions in the AWS Console

This application runs entirely in your browser with no backend server required, making it easy to use without complex setup.

## Features

- **Cross-Region Management**: Automatically discovers and queries all AWS regions
- **Instance Filtering**: Shows only running instances to focus on active resources
- **Quick Actions**: Stop or terminate instances directly from the interface
- **Secure Credential Handling**: AWS credentials are stored only in memory, never persisted
- **Responsive Design**: Works on desktop and mobile browsers

## Security Notice

This application runs entirely in your browser. Your AWS credentials are stored only in memory and are never sent to any server other than AWS directly. However, storing AWS credentials in a browser application is not recommended for production use.

For production environments, consider:
- Using Amazon Cognito for authentication
- Creating an API Gateway + Lambda backend to handle AWS operations
- Implementing proper IAM roles with least privilege

## Getting Started

### Prerequisites

- A modern web browser (Chrome, Firefox, Safari, Edge)
- Valid AWS credentials with permissions for:
  - `ec2:DescribeRegions`
  - `ec2:DescribeInstances`
  - `ec2:StopInstances`
  - `ec2:TerminateInstances`

### Usage

1. Clone or download this repository
2. Open `index.html` in your web browser
3. Enter your AWS Account ID, Access Key ID, and Secret Access Key
4. Click "Connect to AWS" to fetch running instances
5. Use the "Stop Instance" or "Terminate Instance" buttons to manage instances

## Implementation Details

This application uses:
- AWS SDK for JavaScript v2
- Pure HTML, CSS, and JavaScript (no frameworks)
- Client-side only architecture

## Troubleshooting

### Common Issues

1. **"Error connecting to AWS" message**
   - Verify your AWS credentials are correct
   - Ensure your IAM user has the required permissions
   - Check your internet connection

2. **No instances appear**
   - Confirm you have running EC2 instances in your account
   - Check browser console for any errors

3. **Browser security warnings**
   - Some browsers may block scripts from loading
   - Check browser console for CORS-related errors

## Future Enhancements

Potential improvements for future versions:
- Add ability to start stopped instances
- Include more instance details and filtering options
- Add support for other AWS resources (RDS, Lambda, etc.)
- Implement secure credential storage with Amazon Cognito

## License

This project is licensed under the MIT License - see the LICENSE file for details.

## Acknowledgments

Developed by Yeshwanth L M at [A Monk in Cloud](https://amonkincloud.com)

---

&copy; 2025 A Monk in Cloud. All rights reserved.
