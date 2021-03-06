# Cloud Foundry Binary Buildpack

[![CF Slack](https://www.google.com/s2/favicons?domain=www.slack.com) Join us on Slack](https://cloudfoundry.slack.com/messages/buildpacks/)

A Cloud Foundry [buildpack](http://docs.cloudfoundry.org/buildpacks/) for running arbitrary binary web servers.

### Buildpack User Documentation

Official buildpack documentation can be found at [binary buildpack docs](http://docs.cloudfoundry.org/buildpacks/binary/index.html).

### Building the Buildpack

1. Make sure you have fetched submodules
   ```shell   
   
   git submodule update --init
   ```

2. Get latest buildpack dependencies

  ```shell
  BUNDLE_GEMFILE=cf.Gemfile bundle
  ```

3. Build the buildpack

  ```shell
  BUNDLE_GEMFILE=cf.Gemfile bundle exec buildpack-packager [ --uncached | --cached ]
  ```

4. Use in Cloud Foundry

    Upload the buildpack to your Cloud Foundry and optionally specify it by name

    ```bash
    cf create-buildpack custom_binary_buildpack binary_buildpack-cached-custom.zip 1
    cf push my_app -b custom_binary_buildpack
    ```

### Testing
Buildpacks use the [Machete](https://github.com/cloudfoundry/machete) framework for running integration tests.

To test a buildpack, run the following command from the buildpack's directory:

```
BUNDLE_GEMFILE=cf.Gemfile bundle exec buildpack-build
```

More options can be found on Machete's [Github page](https://github.com/cloudfoundry/machete).

### Contributing

Find our guidelines [here](./CONTRIBUTING.md).

### Help and Support

Join the #buildpacks channel in our [Slack community](http://slack.cloudfoundry.org/) if you need any further assistance.

### Reporting Issues

Open a GitHub issue on this project [here](https://github.com/cloudfoundry/binary-buildpack/issues/new)

### Active Development

The project backlog is on [Pivotal Tracker](https://www.pivotaltracker.com/projects/1042066)
