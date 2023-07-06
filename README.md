# threat-detection-pipeline
✨ A compilation of valuable resources and example data pipelines that aim to help design effective threat detection pipelines. 👷 🏗 

> I want to emphasize that although I am not an expert in Data Engineering, my goal is to gather and organize useful information from public blog posts, conference talks, and contributions from data engineering experts and companies. This is done with the purpose of creating a reference hub for designing detection pipelines. Join us, explore the curated content, and contribute to this collaborative effort.

## Example Detection Pipelines & Components

Please note that while this repo includes example pipelines extracted from blog posts or talks, it's important to understand that these examples may not be comprehensive or reflect the current state of the companies' pipelines. Some examples within this repo may focus on specific components, such as the correlation engine, rather than covering the entire pipeline. They are intended as starting points or illustrations of certain concepts.

Therefore, it is advisable to approach these examples with a degree of caution and view them as informative rather than definitive solutions. If you have additional information or insights about any of the examples included here and have permission to share them, we encourage you to contribute by sending a pull request to enhance or add more details. 

| # | Technologies / Components | Note  | References  |
|---|---|---|---|
| 0 | Databricks, Apache Spark, Delta Lake, Scala | _"Apple must detect a wide variety of security threats, and rises to the challenge using Apache Spark across a diverse pool of telemetry. This talk covers some of the home-grown solutions we’ve built to address complications of scale: <br>1. **Notebook-based testing CI** – Previously we had a hybrid development model for Structured Streaming jobs wherein most code would be written and tested inside of notebooks, but unit tests required export of the notebook into a user’s IDE along with JSON sample files to be executed by a local SparkSession. We’ve deployed a novel CI solution leveraging the Databricks Jobs API that executes the notebooks on a real cluster using sample files in DBFS. When coupled with our new test-generation library, we’ve seen 2/3 reduction in the amount of time required for testing and 85% less LoC. <br>2. **Self-Tuning Alerts** – Apple has a team of security analysts triaging the alerts generated by our detection rules. They annotate them as either ‘False Positive’ or ‘True Positive’ following the results of their analysis. We’ve incorporated this feedback into our Structured Streaming pipeline, so the system automatically learns from consensus and adjusts future behavior. This helps us amplify the signal from the rest of the noise. <br>3. **Automated Investigations** – There are some standard questions an analyst might ask when triaging an alert, like: what does this system usually do, where is it, and who uses it? Using ODBC and the Workspace API, we’ve been able to templatize many investigations and in some cases automate the entire process up to and including incident containment. <br>4. **DetectionKit** – We’ve written a custom SDK to formalize the configuration and testing of jobs, including some interesting features such as modular pre/post processor transform functions, and a stream-compatible exclusion mechanism using foreach Batch."_ | 1. [Scaling Security Threat Detection with Apache Spark and Databricks](https://www.youtube.com/watch?v=YxTE4mff5dk) by Josh Gillner (Apple Detection Engineering) <br> 2. [Threat Detection and Response at Scale](https://www.youtube.com/watch?v=SFeBJxI4Q98) by Dominque Brezinski (Apple) |
| 1  | [go-audit](https://github.com/slackhq/go-audit), Elasticsearch, [ElastAlert](https://github.com/Yelp/elastalert)[0] | _"We send the events to an Elasticsearch cluster. From there we use ElastAlert to query our incoming data continuously for alert generation and general monitoring."_  | [Syscall Auditing at Scale](https://slack.engineering/syscall-auditing-at-scale/) by Ryan Huber (Slack)  |
| 2 | [StreamAlert](https://github.com/airbnb/streamalert) | _"StreamAlert is a serverless, real-time data analysis framework which empowers you to ingest, analyze, and alert on data from any environment, using data sources and alerting logic you define. Computer security teams use StreamAlert to scan terabytes of log data every day for incident detection and response."_ | [StreamAlert: Real-time Data Analysis and Alerting](https://medium.com/airbnb-engineering/streamalert-real-time-data-analysis-and-alerting-e8619e3e5043) by Airbnb Eng


0. ElastAlert is no longer maintained. You can use [ElastAlert2](https://github.com/jertel/elastalert2) instead.

## License

[![CC0](http://mirrors.creativecommons.org/presskit/buttons/88x31/svg/cc-zero.svg)](http://creativecommons.org/publicdomain/zero/1.0)

To the extent possible under law, Adel "0x4D31" Karimi has waived all copyright and related or neighboring rights to this work.
