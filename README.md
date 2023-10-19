
# Formação Power Bi da DIO

Desafio de Projeto:
Processando e Transformando Dados com Power BI

# Passos do projeto:

- Criação de uma instância no Microsoft Azure;
- Criação do Banco de Dados;
- Realizado a integração do Power BI com o MySQL da Azure;
- Feito analises dos dados e correção dos dados nas tabelas;
- Realizado diversas consultas com MySQL para facilitar o manuseio dos dados;
- Criação do Relatório com o Power BI.

# Script das Consultas Realizadas no MySQL

Consulta de Colaborador por Departamento e Localização

*SELECT e.Dno, concat(e.Fname, ' ', e.Minit, ' ', e.Lname) AS Ename, e.Sex, e.Salary, e.Bdate ,d.Dname, dl.Dlocation FROM employee e INNER JOIN departament d ON e.Dno = d.Dnumber INNER JOIN dept_locations dl ON d.Dnumber = dl.Dnumber*

#
Consulta de Dependente por Funcionário

*SELECT d.Essn, d.Dependent_name, d.Sex, d.Bdate, d.Relationship, d.Bdate, concat(e.Fname, ' ', e.Minit, ' ', e.Lname) as Ename FROM dependent d INNER JOIN employee e ON d.Essn = e.Ssn*

#
Consulta de Departamento por Gerente

*SELECT d.Dnumber, d.Dname, concat(e.Fname, ' ', e.Minit, ' ', e.Lname) AS Mgrname FROM departament d INNER JOIN employee e*

#
Consulta de Colaborador por Gerente


*SELECT e1.Ssn, concat(e1.Fname, ' ', e1.Minit, ' ', e1.Lname) AS Ename, e1.Super_ssn, concat(e2.Fname, ' ', e2.Minit, ' ', e2.Lname) AS Manager FROM employee e1 LEFT JOIN employee e2  ON e1.Super_ssn = e2.Ssn*


#
Consulta de projeto por departamento


*SELECT p.Pnumber, p.Pname, p.Plocation, d.Dname FROM project p INNER JOIN departament d ON d.Dnumber = p.Dnum*

#
Consulta de horas de projeto por funcionario


*SELECT e.Ssn, concat(e.Fname, ' ', e.Minit, ' ', e.Lname) AS Ename, w.Pno, w.Hours FROM employee e INNER JOIN works_on w ON e.Ssn = w.Essn*
