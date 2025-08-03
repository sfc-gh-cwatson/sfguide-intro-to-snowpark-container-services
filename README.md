
# Intro to Snowpark Container Services
---
This repository is the source code for the [Intro to Snowpark Container Services Quickstart](https://quickstarts.snowflake.com/guide/intro_to_snowpark_container_services/index.html). Please refer to the quickstart for all instructions.

Through this quickstart guide, you will explore Snowpark Container Services. You will learn the basic mechanics of working with Snowpark Container Services and build several introductory services. **Please note: this quickstart assumes some existing knowledge and familiarity with containerization (e.g. Docker) and basic familiarity with container orchestration.**


## Notes
During snow connection test, if you are using an auth method, it will come up on your phone (e.g. DUO).

In the spot where it says <local_repository> in step 4, that's where you should type the name of the repository
you want in your local folder

The "volumes" tag in the yaml file specifies where data can be uploaded to stage. 
CONTAINER_HOL.PUBLIC.VOLUMES

<repository_url> sfsenorthamerica-cwatson-aws1.registry.snowflakecomputing.com/container_hol_db/public/image_repo
docker tag <local_repository>/python-jupyter-snowpark:latest <repository_url>/python-jupyter-snowpark:dev
docker tag local_repository/python-jupyter-snowpark:latest sfsenorthamerica-cwatson-aws1.registry.snowflakecomputing.com/container_hol_db/public/image_repo/python-jupyter-snowpark:dev

docker push <repository_url>/python-jupyter-snowpark:dev
docker push sfsenorthamerica-cwatson-aws1.registry.snowflakecomputing.com/container_hol_db/public/image_repo/python-jupyter-snowpark:dev

## Supporting Docs


Managing SF connections
https://docs.snowflake.com/en/developer-guide/snowflake-cli/connecting/configure-connections

snow connection add
https://docs.snowflake.com/en/developer-guide/snowflake-cli/command-reference/connection-commands/add-connection

snow connection test
https://docs.snowflake.com/developer-guide/snowflake-cli/command-reference/connection-commands/test-connection

## ERRORS DURING SETUP

Step 3. Set up your local environment

When running `snow spcs image-registry login` an error may pop up because the command login does not exist. 
Some other snow commands don't work e.g. having aws in the URL

FIX - edit `conda_env.yml` to include the following:
- snowflake-cli-labs==3.10.0