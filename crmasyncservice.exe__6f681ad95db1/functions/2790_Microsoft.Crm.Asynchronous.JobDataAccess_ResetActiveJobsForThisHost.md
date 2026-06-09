# Microsoft.Crm.Asynchronous.JobDataAccess::ResetActiveJobsForThisHost

- ea: `0x2790`
- end: `0x2809`
- name: `Microsoft.Crm.Asynchronous.JobDataAccess::ResetActiveJobsForThisHost`
- size: `121`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x2790`

## string_xrefs

- `0x2797`: `UPDATE ScaleGroupOrganizationMaintenanceJobs \n							SET HostId = NULL, State = @readyState\n							WHERE HostId = @hostId and State = @lockedState`
- `0x27c4`: `@readyState`
- `0x27f1`: `d:\dbs\sh\dccm2\1101_190851\cmd\34\src\Core\ObjectModel\Async\AsyncService\JobDataAccess.cs`

## pseudocode

```c

```

## disassembly

```asm
0x2790  call     class [System.Data]System.Data.IDbCommand [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::NewCommand()
0x2795  stloc.0
0x2796  ldloc.0
0x2797  ldstr    aUpdateScalegro_0// "UPDATE ScaleGroupOrganizationMaintenanc"...
0x279c  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0x27a1  ldloc.0
0x27a2  callvirt instance class [System.Data]System.Data.IDataParameterCollection [System.Data]System.Data.IDbCommand::get_Parameters()
0x27a7  castclass [System.Data]System.Data.SqlClient.SqlParameterCollection
0x27ac  dup
0x27ad  ldstr    aHostid// "@hostId"
0x27b2  ldarg.0
0x27b3  ldfld    class Microsoft.Crm.Asynchronous.JobManager Microsoft.Crm.Asynchronous.JobDataAccess::_jobManager
0x27b8  callvirt instance string [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncManagerBase::get_InstanceName()
0x27bd  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x27c2  pop
0x27c3  dup
0x27c4  ldstr    aReadystate// "@readyState"
0x27c9  ldc.i4.0
0x27ca  box      [mscorlib]System.Int32
0x27cf  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x27d4  pop
0x27d5  ldstr    aLockedstate// "@lockedState"
0x27da  ldc.i4.1
0x27db  box      [mscorlib]System.Int32
0x27e0  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x27e5  pop
0x27e6  ldloc.0
0x27e7  ldc.i4   0x174
0x27ec  ldstr    aResetactivejob// "ResetActiveJobsForThisHost"
0x27f1  ldstr    aDDbsShDccm2110// "d:\\dbs\\sh\\dccm2\\1101_190851\\cmd\\3"...
0x27f6  call     int32 [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::ExecuteNonQuery(class [System.Data]System.Data.IDbCommand, int32, string, string)
0x27fb  pop
0x27fc  leave.s  loc_2808
0x27fe  ldloc.0
0x27ff  brfalse.s loc_2807
0x2801  ldloc.0
0x2802  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x2807  endfinally
0x2808  ret
```
