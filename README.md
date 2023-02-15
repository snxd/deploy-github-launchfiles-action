# Solsta Launch Files Action for GitHub

This project is a GitHub Action that uses Solid State Networks tools and services to assign launch files and arguments to a Solsta environment.

The action is compatible with Windows, Linux, and OSX runners.  Windows self-hosted runners require git-bash (https://git-scm.com/) in the %PATH%.

## Variables

* **solsta_client_id:** Client ID to authenticate usage of Solid State Networks console tools
* **solsta_client_secret:** Secret Key to authenticate usage of Solid State Networks console tools
* **console_version:** Version of Solsta Console Tools to use
* **scripts_version:** Version of Solsta Deploy Scripts to use
* **target_product:** Target product to cleanup (case-sensitive)
* **target_environment:** Target environment for launch files (case-sensitive)
* **launch_file1:** Up to 10 launch file entry names, paths, and arguments, format for each row is ("entry name" "path" "arg1 arg2 ...")

## Using

Here is an example YAML Fragment in the steps section of a build:

```yaml
    steps:
    - name: Launch Files CDN data for a Product and location
      uses: snxd/deploy-github-launchfiles-action@v2
      with:
        console_version: '6.1.2.84'
        scripts_version: '3.7.30'
        target_product: 'Emutil'
        target_environment: 'Java'
        solsta_client_id:  ${{ secrets.SNXD_CLIENT_ID }}
        solsta_client_secret:  ${{ secrets.SNXD_CLIENT_SECRET }}
        launch_file1: '("Entry Name 1" "/path/to/exec" "arg1 arg2 ...")'
        launch_file2: '("Entry Name 2" "/path/to/exec" "arg1 arg2 ...")'
```

## License
(C) 2022 Solid State Networks, LLC.  All Rights Reserved.
