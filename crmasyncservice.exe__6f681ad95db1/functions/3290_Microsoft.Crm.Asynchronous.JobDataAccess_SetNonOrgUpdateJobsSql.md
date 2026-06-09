# Microsoft.Crm.Asynchronous.JobDataAccess::SetNonOrgUpdateJobsSql

- ea: `0x3290`
- end: `0x3391`
- name: `Microsoft.Crm.Asynchronous.JobDataAccess::SetNonOrgUpdateJobsSql`
- size: `257`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callers

- `0x2d10`

## callees

- `0x23b0`
- `0x3290`
- `0x3930`
- `0x4a50`

## string_xrefs

- `0x32f9`: `@readyState`
- `0x3295`: `\n			DECLARE @priorityTable table\n			(\n				OperationType int not null,\n				Priority int not null,\n				CapacityType int not null\n			)\n\n			{0}\n\n			DECLARE @invalidIds table\n			(\n				Id uniqueidentifier not null\n			)\n			\n			INSERT INTO @invalidIds \n				SELECT Id FROM ScaleGroupOrganizationMaintenanceJobs  \n				INNER JOIN @priorityTable q ON q.OperationType = ScaleGroupOrganizationMaintenanceJobs.OperationType\n				WHERE CapacityType = @limitedServer \n				AND Targ`

## pseudocode

```c

```

## disassembly

```asm
0x3290  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x3295  ldstr    aDeclarePriorit// "\r\n\t\t\tDECLARE @priorityTable table"...
0x329a  ldc.i4.4
0x329b  newarr   [mscorlib]System.Object
0x32a0  dup
0x32a1  ldc.i4.0
0x32a2  ldarg.0
0x32a3  call     instance string Microsoft.Crm.Asynchronous.JobDataAccess::GetPriorityTable()
0x32a8  stelem.ref
0x32a9  dup
0x32aa  ldc.i4.1
0x32ab  ldarg.2
0x32ac  box      [mscorlib]System.Int32
0x32b1  stelem.ref
0x32b2  dup
0x32b3  ldc.i4.2
0x32b4  ldarg.3
0x32b5  stelem.ref
0x32b6  dup
0x32b7  ldc.i4.3
0x32b8  ldarg.0
0x32b9  call     instance bool Microsoft.Crm.Asynchronous.JobDataAccess::ReadJobParameters()
0x32be  brtrue.s loc_32C7
0x32c0  ldsfld   string [mscorlib]System.String::Empty
0x32c5  br.s     loc_32CC
0x32c7  ldstr    aJobparameters_0// " , JobParameters"
0x32cc  stelem.ref
0x32cd  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x32d2  stloc.0
0x32d3  ldarg.1
0x32d4  ldloc.0
0x32d5  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0x32da  ldarg.1
0x32db  callvirt instance class [System.Data]System.Data.IDataParameterCollection [System.Data]System.Data.IDbCommand::get_Parameters()
0x32e0  castclass [System.Data]System.Data.SqlClient.SqlParameterCollection
0x32e5  dup
0x32e6  ldstr    aStartcycletime// "@startCycleTime"
0x32eb  ldarg.s  4
0x32ed  box      [mscorlib]System.DateTime
0x32f2  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x32f7  pop
0x32f8  dup
0x32f9  ldstr    aReadystate// "@readyState"
0x32fe  ldc.i4.0
0x32ff  box      [mscorlib]System.Int32
0x3304  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x3309  pop
0x330a  dup
0x330b  ldstr    aLockedstate// "@lockedState"
0x3310  ldc.i4.1
0x3311  box      [mscorlib]System.Int32
0x3316  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x331b  pop
0x331c  dup
0x331d  ldstr    aMaxconcurrents// "@maxConcurrentServerJobs"
0x3322  ldarg.0
0x3323  ldfld    class Microsoft.Crm.Asynchronous.JobManager Microsoft.Crm.Asynchronous.JobDataAccess::_jobManager
0x3328  callvirt instance class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.IJobConfiguration Microsoft.Crm.Asynchronous.JobManager::get_Configuration()
0x332d  callvirt instance int32 [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.IJobConfiguration::get_OrgMaintenanceServerMaximumConcurrentJobs()
0x3332  box      [mscorlib]System.Int32
0x3337  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x333c  pop
0x333d  dup
0x333e  ldstr    aPrioritycoeffi// "@priorityCoefficient"
0x3343  ldarg.0
0x3344  ldfld    class Microsoft.Crm.Asynchronous.JobManager Microsoft.Crm.Asynchronous.JobDataAccess::_jobManager
0x3349  callvirt instance class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.IJobConfiguration Microsoft.Crm.Asynchronous.JobManager::get_Configuration()
0x334e  callvirt instance int32 [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.IJobConfiguration::get_OrgMaintenancePriorityCoefficient()
0x3353  box      [mscorlib]System.Int32
0x3358  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x335d  pop
0x335e  dup
0x335f  ldstr    aOverduecoeffic// "@overdueCoefficient"
0x3364  ldarg.0
0x3365  ldfld    class Microsoft.Crm.Asynchronous.JobManager Microsoft.Crm.Asynchronous.JobDataAccess::_jobManager
0x336a  callvirt instance class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.IJobConfiguration Microsoft.Crm.Asynchronous.JobManager::get_Configuration()
0x336f  callvirt instance int32 [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.IJobConfiguration::get_OrgMaintenanceOverdueCoefficient()
0x3374  box      [mscorlib]System.Int32
0x3379  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x337e  pop
0x337f  ldstr    aLimitedserver// "@limitedServer"
0x3384  ldc.i4.1
0x3385  box      [mscorlib]System.Int32
0x338a  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x338f  pop
0x3390  ret
```
