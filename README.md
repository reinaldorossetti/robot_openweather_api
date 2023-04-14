# robot_automation

Project Test with Robot Framework using behave directory pattern .

Report do Projeto:   
https://reinaldorossetti.github.io/robot_samples_api_test/allure-results/#  
Na esteira estamos usando o Pabot para rodar em paralelo as features:  
https://github.com/reinaldorossetti/robot_samples_api_test/blob/main/.github/workflows/test_robot_pabot.yml  

How to install:
```
 git clone https://github.com/reinaldorossetti/robot_automation_ui.git
 cd robot_automation_ui   
 pip install -r requirements.txt
```

** Setting PYTHONPATH inside project (python problem only):

Windows:
```
set PYTHONPATH=%PYTHONPATH%;.;
```
Linux: 
```
export PYTHONPATH=%PYTHONPATH%;.;
```
** If Set PYTHONPATH need set python path in SO system path variables.

Command line to runner:

Api features, by tag api_tests:
```
python -m robot -d my_reports -i api_tests ./  
```
Api features, By File Path:
```
python -m robot -d my_reports --loglevel DEBUG:FAIL features/specifications/weather
python -m robot -d my_reports --loglevel DEBUG:INFO features/specifications/weather
```

Add variable in command line:
```
python -m robot -d my_reports --variable LOG_LEVEL:INFO features/specifications/weather
```

Comando diretamente pelo robot.
```
robot --loglevel DEBUG:INFO -d my_reports -i api_tests ./  
```
Rodando o report local:
```
python -m robot --listener allure_robotframework --rerunfailed my_reports/output.xml -d my_reports -i api_tests ./ 
allure generate ./output/allure -o allure-results/
allure serve
```

Link do Report pelo Git Actions:
https://reinaldorossetti.github.io/robot_openweather_api/allure-results/

Folder Structure Conventions
============================

> Folder structure and naming conventions for my project.

### A typical cucumber directory pattern.
 .
├── atests                      # Pasta Feature é principal do projeto (root code).
    ├── support                 # Funções comuns que são compartilhadas no projeto.
    ├── features                # Pasta aonde vai conter as features e seus respectivos testes.
        ├── keywords            # Keywords que serão utilizadas nos testes.
        ├── resources           # Arquivos Json ou YAML que fazem parte dos testes.
        feature_test.robot      # Arquivos _test vão conter a escrita dos testes.
        feature_variables.robot # Arquivo que vai conter as variáveis e Resource da feature. 
    ├── global_variables.robot  # Arquivo que vai conter as variáveis e Resource do Projeto. 

├── .gitignore                  # Arquivos/pastas que serão ignorados no github.
├── LICENSE
├── README.md                   # Documentação Simplificada do Projeto.
└── requirements.txt          # Aqui vão estar as bibliotecas do Projeto, definir as versões utilizadas.


> Use short lowercase names at least for the top-level files and folders except  
> `LICENSE`, `README.md`, in folder pages the name follow github default in Letter case.  
> Use yaml file to store as environment variables and locators, used in the robot files.   
> The Variables that are not mutable must follow upcase in python by default.  

** This project follow the best pratices, below refences of the same.

Dependencies of project:
```
robotframework-requests==0.9.2
robotframework==5.0.0
robotframework-faker
allure-robotframework
pyyaml>=5.4
robotframework-tidy
robotframework-jsonlibrary
robotframework-jsonschemalibrary
jsonschema
pyopenssl
pycryptodome
Pylance
robotframework-pabot
psycopg2
```

References:    
https://marketsquare.github.io/robotframework-requests/doc/RequestsLibrary.html  
https://github.com/MarketSquare/robotframework-requests  
https://github.com/kennethreitz/requests  
https://requests.readthedocs.io/en/latest/  

Cursos de Robot  
https://www.udemy.com/course/automacao-de-testes-com-robot-framework-basico/  
https://www.udemy.com/course/automacao-de-testes-com-robot-framework-avancado    
