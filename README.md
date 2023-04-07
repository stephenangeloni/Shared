# iSeries

## Debug a Running Program
STRDBG SRVPGM(PGMXYZ)  
SBREAK 346 user USRNAME  
then follow instructions  

sql performance
Start the SQL Performance Monitor:
Use the STRSQLPRF command to start the SQL Performance Monitor. This command will enable the collection of SQL performance data for the current job.

### STRSQLPRF OPTION(*SUMMARY)
This command starts the SQL Performance Monitor with summary level data collection. For more detailed data collection, you can use OPTION(*DETAIL) instead.
Call your SQLRPGLE program:
After starting the SQL Performance Monitor, call your SQLRPGLE program as you normally would, using the CALL command:

### CALL PGM(YOUR_SQLRPGLE_PROGRAM_NAME)
Replace YOUR_SQLRPGLE_PROGRAM_NAME with the name of your SQLRPGLE program.
End the SQL Performance Monitor:
After your program has finished executing, use the ENDSQLPRF command to end the SQL Performance Monitor and write the collected data to an output file.

### ENDSQLPRF
Analyze the SQL performance data:
The collected SQL performance data is now available in an output file named QASYSPRF in the QTEMP library. You can view this file using the RUNQRY command or any other method you prefer to analyze the time taken by each SQL statement in your program.

### RUNQRY QRYFILE((QTEMP/QASYSPRF))
This will display the SQL performance data, which includes the time taken by each SQL statement in your SQLRPGLE program. You can examine this data to identify which SQL statements are taking the most time and potentially optimize your program accordingly.
