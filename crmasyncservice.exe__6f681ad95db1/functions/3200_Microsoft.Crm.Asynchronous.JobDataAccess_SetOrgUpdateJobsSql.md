# Microsoft.Crm.Asynchronous.JobDataAccess::SetOrgUpdateJobsSql

- ea: `0x3200`
- end: `0x3283`
- name: `Microsoft.Crm.Asynchronous.JobDataAccess::SetOrgUpdateJobsSql`
- size: `131`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callers

- `0x2d10`

## callees

- `0x23b0`
- `0x3200`

## string_xrefs

- `0x3260`: `@readyState`
- `0x3205`: `\n			SELECT TOP {0}\n				Id, OrganizationId, TargetServer, OperationType as OpType, RecurrenceStartTime, RecurrencePattern, CapacityType = 2 {1}\n			FROM \n				ScaleGroupOrganizationMaintenanceJobs j\n			WHERE\n				j.NextRunTime < @startCycleTime\n				AND j.State=@readyState\n				AND j.Enabled = 1\n				{2}\n				AND j.OrganizationId NOT IN\n					(\n						SELECT DISTINCT OrganizationId FROM ScaleGroupOrganizationMaintenanceJobs\n						WHERE ScaleGroupOrganizationMaintenanceJobs.State `

## pseudocode

```c

```

## disassembly

```asm
0x3200  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x3205  ldstr    aSelectTop0IdOr// "\r\n\t\t\tSELECT TOP {0}\r\n\t\t\t\tId,"...
0x320a  ldc.i4.3
0x320b  newarr   [mscorlib]System.Object
0x3210  dup
0x3211  ldc.i4.0
0x3212  ldarg.2
0x3213  box      [mscorlib]System.Int32
0x3218  stelem.ref
0x3219  dup
0x321a  ldc.i4.1
0x321b  ldarg.0
0x321c  call     instance bool Microsoft.Crm.Asynchronous.JobDataAccess::ReadJobParameters()
0x3221  brtrue.s loc_322A
0x3223  ldsfld   string [mscorlib]System.String::Empty
0x3228  br.s     loc_322F
0x322a  ldstr    aJobparameters_0// " , JobParameters"
0x322f  stelem.ref
0x3230  dup
0x3231  ldc.i4.2
0x3232  ldarg.3
0x3233  stelem.ref
0x3234  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x3239  stloc.0
0x323a  ldarg.1
0x323b  ldloc.0
0x323c  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0x3241  ldarg.1
0x3242  callvirt instance class [System.Data]System.Data.IDataParameterCollection [System.Data]System.Data.IDbCommand::get_Parameters()
0x3247  castclass [System.Data]System.Data.SqlClient.SqlParameterCollection
0x324c  dup
0x324d  ldstr    aStartcycletime// "@startCycleTime"
0x3252  ldarg.s  4
0x3254  box      [mscorlib]System.DateTime
0x3259  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x325e  pop
0x325f  dup
0x3260  ldstr    aReadystate// "@readyState"
0x3265  ldc.i4.0
0x3266  box      [mscorlib]System.Int32
0x326b  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x3270  pop
0x3271  ldstr    aLockedstate// "@lockedState"
0x3276  ldc.i4.1
0x3277  box      [mscorlib]System.Int32
0x327c  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x3281  pop
0x3282  ret
```
