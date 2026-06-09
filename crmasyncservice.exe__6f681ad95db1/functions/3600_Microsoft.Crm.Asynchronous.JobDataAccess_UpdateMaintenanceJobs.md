# Microsoft.Crm.Asynchronous.JobDataAccess::UpdateMaintenanceJobs

- ea: `0x3600`
- end: `0x369b`
- name: `Microsoft.Crm.Asynchronous.JobDataAccess::UpdateMaintenanceJobs`
- size: `155`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x2b30`

## callees

- `0x3600`
- `0x3850`

## string_xrefs

- `0x3683`: `d:\dbs\sh\dccm2\1101_190851\cmd\34\src\Core\ObjectModel\Async\AsyncService\JobDataAccess.cs`
- `0x3600`: `UPDATE ScaleGroupOrganizationMaintenanceJobs SET \n								HostId = @hostId, State = @lockedState, ModifiedOn = @modifiedOn, StartedOn = @modifiedOn\n								WHERE Id IN {0}`
- `0x367e`: `UpdateMaintenanceJobs`

## pseudocode

```c

```

## disassembly

```asm
0x3600  ldstr    aUpdateScalegro_2// "UPDATE ScaleGroupOrganizationMaintenanc"...
0x3605  stloc.0
0x3606  ldarg.1
0x3607  callvirt instance class [System.Data]System.Data.IDbCommand [System.Data]System.Data.IDbConnection::CreateCommand()
0x360c  stloc.1
0x360d  ldloc.1
0x360e  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x3613  ldloc.0
0x3614  ldc.i4.1
0x3615  newarr   [mscorlib]System.Object
0x361a  dup
0x361b  ldc.i4.0
0x361c  ldarg.0
0x361d  ldarg.2
0x361e  call     instance string Microsoft.Crm.Asynchronous.JobDataAccess::GetInClause(class [mscorlib]System.Collections.Generic.IList`1<valuetype [mscorlib]System.Guid> list)
0x3623  stelem.ref
0x3624  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x3629  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0x362e  ldloc.1
0x362f  callvirt instance class [System.Data]System.Data.IDataParameterCollection [System.Data]System.Data.IDbCommand::get_Parameters()
0x3634  castclass [System.Data]System.Data.SqlClient.SqlParameterCollection
0x3639  dup
0x363a  ldstr    aHostid// "@hostId"
0x363f  ldarg.0
0x3640  ldfld    class Microsoft.Crm.Asynchronous.JobManager Microsoft.Crm.Asynchronous.JobDataAccess::_jobManager
0x3645  callvirt instance string [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncManagerBase::get_InstanceName()
0x364a  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x364f  pop
0x3650  dup
0x3651  ldstr    aLockedstate// "@lockedState"
0x3656  ldc.i4.1
0x3657  box      [mscorlib]System.Int32
0x365c  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x3661  pop
0x3662  ldstr    aModifiedon// "@modifiedOn"
0x3667  ldarg.0
0x3668  call     instance valuetype [mscorlib]System.DateTime [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessBase::GetUTCDateWithoutMilliseconds()
0x366d  box      [mscorlib]System.DateTime
0x3672  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x3677  pop
0x3678  ldloc.1
0x3679  ldc.i4   0x43C
0x367e  ldstr    aUpdatemaintena// "UpdateMaintenanceJobs"
0x3683  ldstr    aDDbsShDccm2110// "d:\\dbs\\sh\\dccm2\\1101_190851\\cmd\\3"...
0x3688  call     int32 [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::ExecuteNonQuery(class [System.Data]System.Data.IDbCommand, int32, string, string)
0x368d  pop
0x368e  leave.s  loc_369A
0x3690  ldloc.1
0x3691  brfalse.s loc_3699
0x3693  ldloc.1
0x3694  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x3699  endfinally
0x369a  ret
```
