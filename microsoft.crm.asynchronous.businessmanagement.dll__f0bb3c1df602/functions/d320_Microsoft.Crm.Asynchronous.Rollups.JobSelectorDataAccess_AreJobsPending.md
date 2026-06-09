# Microsoft.Crm.Asynchronous.Rollups.JobSelectorDataAccess::AreJobsPending

- ea: `0xd320`
- end: `0xd3aa`
- name: `Microsoft.Crm.Asynchronous.Rollups.JobSelectorDataAccess::AreJobsPending`
- size: `138`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0xd000`

## callees

- `0xc4a0`
- `0xd200`
- `0xd210`
- `0xd320`
- `0xd670`
- `0xd6b0`
- `0xda20`
- `0xdbc0`
- `0xe600`

## pseudocode

```c

```

## disassembly

```asm
0xd320  call     class [System.Data]System.Data.IDbCommand [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::NewCommand()
0xd325  stloc.0
0xd326  ldloc.0
0xd327  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xd32c  ldstr    aSelectCaseWhen// "SELECT\r\n\tCASE WHEN EXISTS(SELECT \r"...
0xd331  ldc.i4.1
0xd332  newarr   [mscorlib]System.Object
0xd337  dup
0xd338  ldc.i4.0
0xd339  ldarg.0
0xd33a  ldc.i4.1
0xd33b  call     instance string Microsoft.Crm.Asynchronous.Rollups.JobSelectorDataAccess::GetSqlForWhereClause(valuetype PostponeUntilBehavior postponeUntilBehavior)
0xd340  stelem.ref
0xd341  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xd346  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0xd34b  ldarg.0
0xd34c  ldloc.0
0xd34d  callvirt instance class [System.Data]System.Data.IDataParameterCollection [System.Data]System.Data.IDbCommand::get_Parameters()
0xd352  castclass [System.Data]System.Data.SqlClient.SqlParameterCollection
0xd357  call     instance void Microsoft.Crm.Asynchronous.Rollups.JobSelectorDataAccess::AddParametersForWhereClause(class [System.Data]System.Data.SqlClient.SqlParameterCollection parameters)
0xd35c  ldc.i4.1
0xd35d  ldarg.0
0xd35e  call     instance class Microsoft.Crm.Asynchronous.Rollups.RollupsDataAccess Microsoft.Crm.Asynchronous.Rollups.JobSelectorDataAccess::get_DataAccess()
0xd363  ldloc.0
0xd364  callvirt instance object Microsoft.Crm.Asynchronous.Rollups.RollupsDataAccess::ExecuteSqlCommand(class [System.Data]System.Data.IDbCommand command)
0xd369  unbox.any [mscorlib]System.Int32
0xd36e  ceq
0xd370  stloc.1
0xd371  leave.s  loc_D3A8
0xd373  ldloc.0
0xd374  brfalse.s loc_D37C
0xd376  ldloc.0
0xd377  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xd37c  endfinally
0xd37d  stloc.2
0xd37e  call     class Microsoft.Crm.Asynchronous.Rollups.RollupAsyncEventSource Microsoft.Crm.Asynchronous.Rollups.RollupAsyncEventSource::get_Instance()
0xd383  ldarg.0
0xd384  ldfld    class Microsoft.Crm.Asynchronous.RollupsAsyncContext Microsoft.Crm.Asynchronous.Rollups.JobSelectorDataAccess::_rollupsAsyncContext
0xd389  callvirt instance class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEvent Microsoft.Crm.Asynchronous.RollupsAsyncContext::get_AsyncEvent()
0xd38e  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEventBase::get_OrganizationId()
0xd393  ldarg.0
0xd394  call     instance int32 Microsoft.Crm.Asynchronous.Rollups.JobSelectorDataAccess::get_EntityTypeCode()
0xd399  ldloc.2
0xd39a  callvirt instance string [mscorlib]System.Object::ToString()
0xd39f  callvirt instance void Microsoft.Crm.Asynchronous.Rollups.RollupAsyncEventSource::IncrementalJobSelectorFailure(valuetype [mscorlib]System.Guid orgId, int32 entityTypeCode, string exception)
0xd3a4  ldc.i4.0
0xd3a5  stloc.1
0xd3a6  leave.s  loc_D3A8
0xd3a8  ldloc.1
0xd3a9  ret
```
