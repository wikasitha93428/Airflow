## Airflow
------------------------------------------
Apache Airflow introduction Note & Testing 
-------------------------------------------
01: Prerequisites 
        1:Docker Desktop
        2:Astro CLI  
        https://www.astronomer.io/docs/astro/cli/install-cli?tab=linux#install-the-astro-cli 
            
1.1: curl -sSL install.astronomer.io | sudo bash -s
            ![image](https://github.com/user-attachments/assets/fcb83949-b594-4dd0-9aac-d5fe8e9ee559)
        
1.2: astro version  
            ![image](https://github.com/user-attachments/assets/6fac962b-0f42-4d52-a534-615e476a2033)


02: Basics of Airflow 
            Airflow is workflow orchestration tool, build, schedule pipelines 
            Airflow has multiple DAGs and each DAG has multiple tasks 
            Task = a unit of operation that we  need perform 
            ![image](https://github.com/user-attachments/assets/adf2a9e1-bccc-4f6b-8286-4abfa750e18e) 
            

03: Why do we need workflow orchestration? 
        The definition of data orchestration is the process of coordinating and automating the movement, 
        transformation and integration of data across different systems and processes to ensure efficient
        and reliable data workflows. 

04: Why we need Airflow?
        ![image](https://github.com/user-attachments/assets/e0a3c0c2-1aa2-434d-a7ec-f853544efb3c) 
         1: A reliability orchestration for our data workflow at scale
         2: Integrations and customizations
         3: Accessibility and dynamism
         4: Monitoring and data lineage
         5: Huge community support
         
05: dbt + snowflake + Airflow 
        ![image](https://github.com/user-attachments/assets/4843d502-d5f3-4502-b3af-f9ee4d2eb0ad)
        
06 Airflow Components 
        ![image](https://github.com/user-attachments/assets/c17b8697-eaef-4dce-84f5-9cffa1a0894c)

07: Airflow core concepts
        ![image](https://github.com/user-attachments/assets/206ad3e7-c23a-4287-872b-5b98d53f4936)

 08:  What happened in DAG when we ran it
         8.1: First we can see 4 major components below, below folder(directory is DAG directory where we can store our DAGs)
                 ![image](https://github.com/user-attachments/assets/517556ab-46fd-4d78-aed8-0e4929d9894d)
        8.2: Add our DAG file (my_dag.py) to schedule 
                 ![image](https://github.com/user-attachments/assets/8504fa2f-65e0-4e16-8cb1-8c72e099759f)
        8.3: Second, the Airflow schedular scans the DAG directory for new files (scan every 5 min by default)
                ![image](https://github.com/user-attachments/assets/cfb1d35c-2962-4aa2-b68c-f01ee42c4192)
        8.4: Once the scheduler detects a new DAG file, then it serializes to Meta Database, web server can also access Meta Database
                ![image](https://github.com/user-attachments/assets/075c9fcd-5102-4710-b8b1-9e40b8a0725a)
        8.5: If DAG is ready to run , Scheduler creates DAG run
                ![image](https://github.com/user-attachments/assets/d6fb890a-2c33-43ab-9741-08fa9efcb91a)
        8.6: Then the scheduler checks if there are tasks to run.If so, it creates a task instance for every task.Like for the Dag run.
                ![image](https://github.com/user-attachments/assets/c3c7cc0d-6cc1-42ad-88bb-bcc5189f9269) 
        8.7: Then the scheduler sends the task instance to the executor. Remember that the executor is responsible for defining how and on which system to execute your 
             tasks.
                ![image](https://github.com/user-attachments/assets/b52122b6-e361-47e5-85d7-7723241f0505)

-----------------------------------------------------------------------------------------------------------------------------------------------------------------
09: Installing Airflow via Docker
initial setting up - VSCode
![image](https://github.com/user-attachments/assets/363ea0db-fd66-4205-b893-6f4eca1ad686)
                
Astro dev init > initialize the project for astro 
![image](https://github.com/user-attachments/assets/41b61a8e-7cb9-49c6-b747-1191f239ba9a)

docker container port : /home/wiks/Documents/2024_learn/2024_nov/airflow_udemy/airflow-materials/airflow-materials/airflow-section-3/docker-compose.yml
![image](https://github.com/user-attachments/assets/79936fa5-f71d-4b06-8f60-aa293644b2ba)


-----------------------------------------------------------------------------------------------------------------------------------------------------------------
#### Erorrs handling Airflow ####
01: ports are in use 
https://www.astronomer.io/docs/astro/cli/troubleshoot-locally/#ports-are-not-available-for-my-local-airflow-webserver)
path =/home/wiks/Documents/2024_learn/2024_nov/airflow_udemy/udemy_airflow

## Commands 
----------------------------------------------------
astro dev start
if any error occured
docker stop container_id
astro config set webserver.port 8081
astro config set postgres.port 5435
astro dev start
-----------------------------------------------------
![image](https://github.com/user-attachments/assets/3f278d31-b744-4e55-ac20-96de96f3e244)

![image](https://github.com/user-attachments/assets/a0b919fe-0861-43b2-a693-0636c5c265d3)


        


         



        


        
