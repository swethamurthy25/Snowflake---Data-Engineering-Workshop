# Snowflake -- Data-Engineering-Workshop

### $\textcolor{red}{Setting\ up\ Snowflake\ Trail\ Account\}$
* Register on snowflake trial account on AWS
* Confirm if we have access to a warehouse named COMPUTE_WH sized XS and will auto-suspend. If not, we need to create one. 

  ![image](https://github.com/swethamurthy25/Snowflake---Data-Engineering-Workshop/assets/112581595/61c556d7-a5a8-4579-9d64-476d4888727e)


* Check and confirm if we have access to a database named UTIL_DB and if not, we need to consider creating one that can serve as the home to our DORA GRADER function.
  
  ![image](https://github.com/swethamurthy25/Snowflake---Data-Engineering-Workshop/assets/112581595/2bfebc85-4c26-4f96-ad1a-3492c7bb0793)

* Make sure the SYSADMIN role owns the COMPUTE_WH, the UTIL_DB database, and the PUBLIC schema of the UTIL_DB database.
  
  ![image](https://github.com/swethamurthy25/Snowflake---Data-Engineering-Workshop/assets/112581595/d3e06f66-1ee8-42d3-aec9-d1b1040dd144)

  ![image](https://github.com/swethamurthy25/Snowflake---Data-Engineering-Workshop/assets/112581595/670f5b0f-24a1-46a8-ab41-dd5a7af58a87)


### $\textcolor{red}{Creating\ Project\ Infrastructure\}$
* Use SYSADMIN and Create a database named AGS_GAME_AUDIENCE
* Drop the PUBLIC schema and Create a schema named RAW.

  ![image](https://github.com/swethamurthy25/Snowflake---Data-Engineering-Workshop/assets/112581595/5b208992-7e38-43fc-a7fb-189dfc75ae18)

  ![image](https://github.com/swethamurthy25/Snowflake---Data-Engineering-Workshop/assets/112581595/c89b247a-0d0c-4764-9b75-19d91578611e)

* Now navigate into AGS_GAME_AUDIENCE database --> RAW Schema --> Create new Table named GAME_LOGS

   ![image](https://github.com/swethamurthy25/Snowflake---Data-Engineering-Workshop/assets/112581595/35cebf8b-c367-44b1-bcb7-fcca714c67a6)

* Create an AMAZON S3 External Stage. Go back to AGS_GAME_AUDIENCE database --> RAW Schema --> Create --> Stage --> Amazon S3
* Provide the stage name and bucket URL and click on Create.

   ![image](https://github.com/swethamurthy25/Snowflake---Data-Engineering-Workshop/assets/112581595/d72ad4cc-c145-4e86-bdf6-49c3a9f7721c)

   ![image](https://github.com/swethamurthy25/Snowflake---Data-Engineering-Workshop/assets/112581595/f88aceaa-fd80-4136-8b0a-39b9eac3b857)

* Use the SYSADMIN role and Create a File Format in the AGS_GAME_AUDIENCE.RAW schema named FF_JSON_LOGS.
* Set the data file Type to JSON and Set the Strip Outer Array Property to TRUE (strip_outer_array = true)

   ![image](https://github.com/swethamurthy25/Snowflake---Data-Engineering-Workshop/assets/112581595/57a15617-c02b-43da-ae3f-bb010641077a)

* Loaded the JSON File into the GAME_LOGS table

    ![image](https://github.com/swethamurthy25/Snowflake---Data-Engineering-Workshop/assets/112581595/b48dad62-03d1-4813-856b-d050a1291118)






