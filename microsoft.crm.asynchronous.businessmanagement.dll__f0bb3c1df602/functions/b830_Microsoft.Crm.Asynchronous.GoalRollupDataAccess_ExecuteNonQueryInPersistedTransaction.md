# Microsoft.Crm.Asynchronous.GoalRollupDataAccess::ExecuteNonQueryInPersistedTransaction

- ea: `0xb830`
- end: `0xb8b8`
- name: `Microsoft.Crm.Asynchronous.GoalRollupDataAccess::ExecuteNonQueryInPersistedTransaction`
- size: `136`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0xb830`
- `0xb900`
- `0xb910`

## string_xrefs

- `0xb856`: `d:\dbs\sh\dccm2\1101_190851\cmd\77\src\Core\ObjectModel\Async\Handlers\BusinessManagement\GoalManagement\GoalRollupDataAccess.cs`

## pseudocode

```c

```

## disassembly

```asm
0xb830  ldarg.0
0xb831  call     instance class [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection Microsoft.Crm.Asynchronous.GoalRollupDataAccess::get_PersistedConnection()
0xb836  ldarga.s 1
0xb838  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::CreateCommand(class [System.Data]System.Data.IDbCommand&)
0xb83d  ldarg.1
0xb83e  ldarg.0
0xb83f  call     instance class [Microsoft.Crm.Core]Microsoft.Crm.CrmTransaction Microsoft.Crm.Asynchronous.GoalRollupDataAccess::get_PersistedTransaction()
0xb844  callvirt instance class [System.Data]System.Data.IDbTransaction [Microsoft.Crm.Core]Microsoft.Crm.CrmTransaction::get_SqlTrans()
0xb849  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::SetTransaction(class [System.Data]System.Data.IDbCommand, class [System.Data]System.Data.IDbTransaction)
0xb84e  ldarg.1
0xb84f  ldc.i4.s 0x60
0xb851  ldstr    aExecutenonquer// "ExecuteNonQueryInPersistedTransaction"
0xb856  ldstr    aDDbsShDccm2110_3// "d:\\dbs\\sh\\dccm2\\1101_190851\\cmd\\7"...
0xb85b  call     int32 [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::ExecuteNonQuery(class [System.Data]System.Data.IDbCommand, int32, string, string)
0xb860  ldarg.2
0xb861  brfalse.s loc_B892
0xb863  ldarg.0
0xb864  call     instance class [Microsoft.Crm.Core]Microsoft.Crm.CrmTransaction Microsoft.Crm.Asynchronous.GoalRollupDataAccess::get_PersistedTransaction()
0xb869  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmTransaction::CommitTransaction()
0xb86e  ldarg.0
0xb86f  call     instance class [Microsoft.Crm.Core]Microsoft.Crm.CrmTransaction Microsoft.Crm.Asynchronous.GoalRollupDataAccess::get_PersistedTransaction()
0xb874  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmTransaction::Dispose()
0xb879  ldarg.0
0xb87a  call     instance class [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection Microsoft.Crm.Asynchronous.GoalRollupDataAccess::get_PersistedConnection()
0xb87f  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::Dispose()
0xb884  ldarg.0
0xb885  ldnull
0xb886  stfld    class [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection Microsoft.Crm.Asynchronous.GoalRollupDataAccess::_persistedConnection
0xb88b  ldarg.0
0xb88c  ldnull
0xb88d  stfld    class [Microsoft.Crm.Core]Microsoft.Crm.CrmTransaction Microsoft.Crm.Asynchronous.GoalRollupDataAccess::_persistedTransaction
0xb892  stloc.0
0xb893  leave.s  loc_B8B6
0xb895  stloc.1
0xb896  ldarg.0
0xb897  ldloc.1
0xb898  ldarg.1
0xb899  ldstr    aExceptionWhile// "Exception while executing database quer"...
0xb89e  ldarg.0
0xb89f  call     instance class [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection Microsoft.Crm.Asynchronous.GoalRollupDataAccess::get_PersistedConnection()
0xb8a4  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::get_OrganizationId()
0xb8a9  ldarg.0
0xb8aa  callvirt instance string [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessSharedBase::get_Name()
0xb8af  callvirt instance void [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessSharedBase::HandleDatabaseException(class [mscorlib]System.Exception, class [System.Data]System.Data.IDbCommand, string, valuetype [mscorlib]System.Guid, string)
0xb8b4  rethrow
0xb8b6  ldloc.0
0xb8b7  ret
```
