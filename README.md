## Container healthcheck

The **Container healthcheck** GitHub action allows you to check the status of a Docker container and restart it if it's unhealthy. This action takes the name of the container to check as an input, along with optional timeout and interval values. The timeout value specifies the maximum time to wait for the container to become healthy, while the interval value specifies how often to check the container's status. By default, the action waits for 120 seconds and checks the container's status every second.

When you run this action, it outputs status messages to the console, indicating whether the container is healthy, unhealthy, or has timed out. If the container is unhealthy, the action restarts it automatically. If the container is healthy, the action exits with a success status code.

This action is authored by "zethuman" and runs as a composite action, executing a job that includes a Bash script to check the container's status.

### Inputs

* `name` (required): Name of the container to check
* `timeout` (optional, default: 120): Timeout in seconds. Default is 120 seconds
* `interval` (optional, default: 1): Interval of checking in seconds. Default is 1 second

### Example usage

```yaml
uses: zethuman/healthcheck@v0.0.1
with:
  name: my-container
  timeout: 180
  interval: 2
