# Microsoft.Crm.Asynchronous.JobDataAccess::SetJobNextRunTime

- ea: `0x3580`
- end: `0x3600`
- name: `Microsoft.Crm.Asynchronous.JobDataAccess::SetJobNextRunTime`
- size: `128`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x3060`

## callees

- `0x9e0`
- `0x3580`

## string_xrefs

- `0x35e8`: `d:\dbs\sh\dccm2\1101_190851\cmd\34\src\Core\ObjectModel\Async\AsyncService\JobDataAccess.cs`
- `0x3580`: `UPDATE ScaleGroupOrganizationMaintenanceJobs SET \n							ModifiedOn = @modifiedOn, NextRunTime = @nextRunTime\n								WHERE Id = @jobId`

## pseudocode

```c

```

## disassembly

```asm
0x3580  ldstr    aUpdateScalegro_1// "UPDATE ScaleGroupOrganizationMaintenanc"...
0x3585  stloc.0
0x3586  ldarg.1
0x3587  callvirt instance class [System.Data]System.Data.IDbCommand [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::CreateCommand()
0x358c  stloc.1
0x358d  ldloc.1
0x358e  ldloc.0
0x358f  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0x3594  ldloc.1
0x3595  callvirt instance class [System.Data]System.Data.IDataParameterCollection [System.Data]System.Data.IDbCommand::get_Parameters()
0x359a  castclass [System.Data]System.Data.SqlClient.SqlParameterCollection
0x359f  dup
0x35a0  ldstr    aNextruntime// "@nextRunTime"
0x35a5  ldarg.3
0x35a6  box      [mscorlib]System.DateTime
0x35ab  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x35b0  pop
0x35b1  dup
0x35b2  ldstr    aModifiedon// "@modifiedOn"
0x35b7  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_UtcNow()
0x35bc  box      [mscorlib]System.DateTime
0x35c1  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x35c6  pop
0x35c7  ldstr    aJobid// "@jobId"
0x35cc  ldarg.2
0x35cd  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.AsyncJob::get_JobId()
0x35d2  box      [mscorlib]System.Guid
0x35d7  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x35dc  pop
0x35dd  ldloc.1
0x35de  ldc.i4   0x42B
0x35e3  ldstr    aSetjobnextrunt// "SetJobNextRunTime"
0x35e8  ldstr    aDDbsShDccm2110// "d:\\dbs\\sh\\dccm2\\1101_190851\\cmd\\3"...
0x35ed  call     int32 [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::ExecuteNonQuery(class [System.Data]System.Data.IDbCommand, int32, string, string)
0x35f2  pop
0x35f3  leave.s  loc_35FF
0x35f5  ldloc.1
0x35f6  brfalse.s loc_35FE
0x35f8  ldloc.1
0x35f9  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x35fe  endfinally
0x35ff  ret
```
