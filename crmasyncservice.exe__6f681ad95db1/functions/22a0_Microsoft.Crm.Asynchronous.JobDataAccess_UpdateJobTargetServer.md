# Microsoft.Crm.Asynchronous.JobDataAccess::UpdateJobTargetServer

- ea: `0x22a0`
- end: `0x235d`
- name: `Microsoft.Crm.Asynchronous.JobDataAccess::UpdateJobTargetServer`
- size: `189`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `installer_update, broker_com_uri`

## callers

- `0x2980`
- `0x3060`

## callees

- `0x9d0`
- `0x9f0`
- `0xa00`
- `0x22a0`
- `0x37f0`

## string_xrefs

- `0x22da`: `\n					UPDATE ScaleGroupOrganizationMaintenanceJobs\n					SET \n						TargetServer = @serverName,\n						ModifiedOn = @modifiedOn	\n					OUTPUT\n						INSERTED.OrganizationId,\n						INSERTED.OperationType,\n						INSERTED.TargetServer\n					WHERE \n						 OrganizationId = @orgId\n\n				`

## pseudocode

```c

```

## disassembly

```asm
0x22a0  ldarg.0
0x22a1  ldarg.1
0x22a2  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.AsyncJob::get_OrganizationId()
0x22a7  call     instance string Microsoft.Crm.Asynchronous.JobDataAccess::RetrieveSqlServerName(valuetype [mscorlib]System.Guid orgId)
0x22ac  stloc.0
0x22ad  ldarg.1
0x22ae  callvirt instance string Microsoft.Crm.Asynchronous.AsyncJob::get_SqlServerName()
0x22b3  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x22b8  brtrue.s loc_22CC
0x22ba  ldarg.1
0x22bb  callvirt instance string Microsoft.Crm.Asynchronous.AsyncJob::get_SqlServerName()
0x22c0  ldloc.0
0x22c1  ldc.i4.5
0x22c2  callvirt instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0x22c7  brtrue   loc_235C
0x22cc  ldarg.1
0x22cd  ldloc.0
0x22ce  callvirt instance void Microsoft.Crm.Asynchronous.AsyncJob::set_SqlServerName(string value)
0x22d3  call     class [System.Data]System.Data.IDbCommand [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::NewCommand()
0x22d8  stloc.1
0x22d9  ldloc.1
0x22da  ldstr    aUpdateScalegro// "\r\n\t\t\t\t\tUPDATE ScaleGroupOrganiza"...
0x22df  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0x22e4  ldloc.1
0x22e5  callvirt instance class [System.Data]System.Data.IDataParameterCollection [System.Data]System.Data.IDbCommand::get_Parameters()
0x22ea  castclass [System.Data]System.Data.SqlClient.SqlParameterCollection
0x22ef  dup
0x22f0  ldstr    aOrgid// "@orgId"
0x22f5  ldarg.1
0x22f6  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.AsyncJob::get_OrganizationId()
0x22fb  box      [mscorlib]System.Guid
0x2300  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x2305  pop
0x2306  dup
0x2307  ldstr    aServername// "@serverName"
0x230c  ldloc.0
0x230d  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x2312  pop
0x2313  ldstr    aModifiedon// "@modifiedOn"
0x2318  ldarg.0
0x2319  call     instance valuetype [mscorlib]System.DateTime [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessBase::GetUTCDateWithoutMilliseconds()
0x231e  box      [mscorlib]System.DateTime
0x2323  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x2328  pop
0x2329  ldarg.0
0x232a  ldloc.1
0x232b  ldsfld   class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessBase/RecordProcessor <>c::<>9__4_0
0x2330  dup
0x2331  brtrue.s loc_234A
0x2333  pop
0x2334  ldsfld   class <>c <>c::<>9
0x2339  ldftn    instance void <>c::<UpdateJobTargetServer>b__4_0(object[] values)
0x233f  newobj   instance void [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessBase/RecordProcessor::.ctor(object, native int)
0x2344  dup
0x2345  stsfld   class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessBase/RecordProcessor <>c::<>9__4_0
0x234a  call     instance int32 [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessBase::ExecuteSqlCommandAndProcessRecords(class [System.Data]System.Data.IDbCommand, class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessBase/RecordProcessor)
0x234f  pop
0x2350  leave.s  loc_235C
0x2352  ldloc.1
0x2353  brfalse.s loc_235B
0x2355  ldloc.1
0x2356  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x235b  endfinally
0x235c  ret
```
