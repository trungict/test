# Using ParamSetCli utility by Lambda

![architecture.png](images%2Farchitecture.png)

# Requirements
- [Java 21 runtime environment (SE JRE)](https://www.oracle.com/java/technologies/javase-downloads.html)
- [Maven 3](https://maven.apache.org/docs/history.html)
- The Bash shell. For Linux and macOS, this is included by default. In Windows 10, you can install the [Windows Subsystem for Linux](https://docs.microsoft.com/en-us/windows/wsl/install-win10) to get a Windows-integrated version of Ubuntu and Bash.
- [The AWS CLI](https://docs.aws.amazon.com/cli/latest/userguide/cli-chap-install.html) v1.17 or newer.
- [Informatica ParamSetCli Utility](https://docs.informatica.com/integration-cloud/data-integration/h2l/1683-how-to-configure-a-parameter-set-in-a-taskflow/how-to-configure-a-parameter-set-in-a-taskflow/about-paramsetcli.html)

# Deploy

To deploy the application, run `deploy.sh`.

    $./deploy.sh
    1. Checking S3 bucket "kpz-74"...
    S3 Bucket "kpz-74" existed.
    2. Syncing S3 Resources...
    3. Building deployment package...
    ...

# Test

Using ParamSetCli Utility to delete parameter set `kpz60-params`

    bash paramsetcli.sh runParamSetCli -un kpz60-params -a delete

To invoke the function directly, run `invoke.sh`.

    $./invoke.sh
    {
        "StatusCode": 200,
        "ExecutedVersion": "$LATEST"
    }

Using ParamSetCli Utility check list parameter set

    bash paramsetcli.sh runParamSetCli -a list

You can find parameter set name "kpz60-params"

![result.png](images%2Fresult.png)

# Cleanup
To delete the application, run `cleanup.sh`.

    $./cleanup.sh

