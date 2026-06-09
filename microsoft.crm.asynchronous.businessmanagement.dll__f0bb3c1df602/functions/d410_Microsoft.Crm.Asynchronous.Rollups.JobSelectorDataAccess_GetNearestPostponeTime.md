# Microsoft.Crm.Asynchronous.Rollups.JobSelectorDataAccess::GetNearestPostponeTime

- ea: `0xd410`
- end: `0xd48a`
- name: `Microsoft.Crm.Asynchronous.Rollups.JobSelectorDataAccess::GetNearestPostponeTime`
- size: `122`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0xd010`

## callees

- `0xd210`
- `0xd410`
- `0xd670`
- `0xd6b0`
- `0xe600`

## pseudocode

```c

```

## disassembly

```asm
0xd410  call     class [System.Data]System.Data.IDbCommand [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::NewCommand()
0xd415  stloc.0
0xd416  ldloc.0
0xd417  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xd41c  ldstr    aSelectMinRjPos// "SELECT \r\n\tMIN(RJ.[PostponeUntil])\r"...
0xd421  ldc.i4.1
0xd422  newarr   [mscorlib]System.Object
0xd427  dup
0xd428  ldc.i4.0
0xd429  ldarg.0
0xd42a  ldc.i4.0
0xd42b  call     instance string Microsoft.Crm.Asynchronous.Rollups.JobSelectorDataAccess::GetSqlForWhereClause(valuetype PostponeUntilBehavior postponeUntilBehavior)
0xd430  stelem.ref
0xd431  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xd436  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0xd43b  ldarg.0
0xd43c  ldloc.0
0xd43d  callvirt instance class [System.Data]System.Data.IDataParameterCollection [System.Data]System.Data.IDbCommand::get_Parameters()
0xd442  castclass [System.Data]System.Data.SqlClient.SqlParameterCollection
0xd447  call     instance void Microsoft.Crm.Asynchronous.Rollups.JobSelectorDataAccess::AddParametersForWhereClause(class [System.Data]System.Data.SqlClient.SqlParameterCollection parameters)
0xd44c  ldarg.0
0xd44d  call     instance class Microsoft.Crm.Asynchronous.Rollups.RollupsDataAccess Microsoft.Crm.Asynchronous.Rollups.JobSelectorDataAccess::get_DataAccess()
0xd452  ldloc.0
0xd453  callvirt instance object Microsoft.Crm.Asynchronous.Rollups.RollupsDataAccess::ExecuteSqlCommand(class [System.Data]System.Data.IDbCommand command)
0xd458  stloc.1
0xd459  ldloc.1
0xd45a  brfalse.s loc_D472
0xd45c  ldloc.1
0xd45d  isinst   [mscorlib]System.DateTime
0xd462  brfalse.s loc_D472
0xd464  ldloc.1
0xd465  unbox.any [mscorlib]System.DateTime
0xd46a  newobj   instance void valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>::.ctor(var<u1>)
0xd46f  stloc.2
0xd470  leave.s  loc_D488
0xd472  ldloca.s 3
0xd474  initobj  valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>
0xd47a  ldloc.3
0xd47b  stloc.2
0xd47c  leave.s  loc_D488
0xd47e  ldloc.0
0xd47f  brfalse.s loc_D487
0xd481  ldloc.0
0xd482  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xd487  endfinally
0xd488  ldloc.2
0xd489  ret
```
