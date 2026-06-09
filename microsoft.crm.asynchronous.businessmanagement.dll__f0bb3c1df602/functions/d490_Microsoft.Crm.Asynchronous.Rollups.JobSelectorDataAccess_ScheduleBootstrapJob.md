# Microsoft.Crm.Asynchronous.Rollups.JobSelectorDataAccess::ScheduleBootstrapJob

- ea: `0xd490`
- end: `0xd505`
- name: `Microsoft.Crm.Asynchronous.Rollups.JobSelectorDataAccess::ScheduleBootstrapJob`
- size: `117`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0xc1b0`

## callees

- `0xd210`
- `0xd490`
- `0xe610`
- `0xe620`

## string_xrefs

- `0xd497`: `UPDATE AsyncOperationBase \n					SET PostponeUntil = @postPoneUntil,\n					ModifiedOn = @modifiedOn,\n					ModifiedBy = CreatedBy\n					WHERE  AsyncOperationId = (SELECT RP.BootstrapRollupAsyncJobId FROM RollupPropertiesBase AS RP WHERE RP.RollupPropertiesId = @rollupId)\n					AND RecurrencePattern IS NOT NULL`

## pseudocode

```c

```

## disassembly

```asm
0xd490  call     class [System.Data]System.Data.IDbCommand [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::NewCommand()
0xd495  stloc.0
0xd496  ldloc.0
0xd497  ldstr    aUpdateAsyncope_2// "UPDATE AsyncOperationBase \r\n\t\t\t\t"...
0xd49c  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0xd4a1  ldloc.0
0xd4a2  callvirt instance class [System.Data]System.Data.IDataParameterCollection [System.Data]System.Data.IDbCommand::get_Parameters()
0xd4a7  castclass [System.Data]System.Data.SqlClient.SqlParameterCollection
0xd4ac  dup
0xd4ad  ldstr    aPostponeuntil_0// "@postPoneUntil"
0xd4b2  ldarg.1
0xd4b3  box      [mscorlib]System.DateTime
0xd4b8  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0xd4bd  pop
0xd4be  dup
0xd4bf  ldstr    aRollupid// "@rollupId"
0xd4c4  ldarg.2
0xd4c5  box      [mscorlib]System.Guid
0xd4ca  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0xd4cf  pop
0xd4d0  ldstr    aModifiedon_1// "@modifiedOn"
0xd4d5  ldarg.0
0xd4d6  call     instance class Microsoft.Crm.Asynchronous.Rollups.RollupsDataAccess Microsoft.Crm.Asynchronous.Rollups.JobSelectorDataAccess::get_DataAccess()
0xd4db  callvirt instance valuetype [mscorlib]System.DateTime Microsoft.Crm.Asynchronous.Rollups.RollupsDataAccess::GetUTCDateWithoutMilliseconds()
0xd4e0  box      [mscorlib]System.DateTime
0xd4e5  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0xd4ea  pop
0xd4eb  ldarg.0
0xd4ec  call     instance class Microsoft.Crm.Asynchronous.Rollups.RollupsDataAccess Microsoft.Crm.Asynchronous.Rollups.JobSelectorDataAccess::get_DataAccess()
0xd4f1  ldloc.0
0xd4f2  callvirt instance int32 Microsoft.Crm.Asynchronous.Rollups.RollupsDataAccess::ExecuteNonQuery(class [System.Data]System.Data.IDbCommand command)
0xd4f7  pop
0xd4f8  leave.s  loc_D504
0xd4fa  ldloc.0
0xd4fb  brfalse.s loc_D503
0xd4fd  ldloc.0
0xd4fe  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xd503  endfinally
0xd504  ret
```
