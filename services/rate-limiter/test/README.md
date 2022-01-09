# How To Test Rate Limiter

## Prerequisites

### Setting Python Environment Variable PYTHONPATH on Mac
To set the python environment variable PYTHONPATH on Mac, follow the given steps:

- Step 1: Open the Terminal.
- Step 2: In your text editor, open the `~/.bash_profile` file. For example: vi `~/.bash_profile`;
- Step 3: To this file, add the following line at the bottom: 
  ```bash
  export PYTHONPATH="/Users/my_user/xxx/rate-limiter/01-solution/services/rate-limiter/"
  ```
- Step 4: Save this text editor file.
- Step 5: Close the terminal.
- Step 6: Restart the terminal. You can now read the new settings. Type:
  ```bash
  echo $PYTHONPATH
  ```

It would show something like `/Users/my_user/xxx/rate-limiter/01-solution/services/rate-limiter/`. That is it. `PYTHONPATH` is set. 

## Unit Test
```
$ cd unit
$ pytest
```

## Functional Test
```bash
$ cd functional
$ python 02_rate_limiter_test_user.py
```

## Integration Test

**Run Docker containers: api-gateway, rate-limiter, fake upload-app**
```bash
$ docker-compose up
```

**Check if Docker containers are being run**
```bash
$ docker ps
CONTAINER ID   PORTS                            NAMES
bdfc48e1f8d1   8001/tcp, 0.0.0.0:8001->80/tcp   01-solution_upload-app_1
64548a7a44dd   0.0.0.0:9001->9001/tcp           01-solution_rate-limiter_1
91241a540678   0.0.0.0:80->80/tcp, 8001/tcp     01-solution_api-gateway_1
```
