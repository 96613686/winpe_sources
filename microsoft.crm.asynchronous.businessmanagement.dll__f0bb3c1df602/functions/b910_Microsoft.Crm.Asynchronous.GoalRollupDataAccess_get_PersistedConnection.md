# Microsoft.Crm.Asynchronous.GoalRollupDataAccess::get_PersistedConnection

- ea: `0xb910`
- end: `0xb9ae`
- name: `Microsoft.Crm.Asynchronous.GoalRollupDataAccess::get_PersistedConnection`
- size: `158`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0xb830`

## callees

- `0xb910`

## string_xrefs

- `0xb985`: `Exception while trying to open database connection for organization {0}`

## pseudocode

```c

```

## disassembly

```asm
0xb910  ldarg.0
0xb911  ldfld    class [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection Microsoft.Crm.Asynchronous.GoalRollupDataAccess::_persistedConnection
0xb916  brtrue   loc_B9A7
0xb91b  ldarg.0
0xb91c  ldarg.0
0xb91d  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessSharedBase::CreateConnection()
0xb922  stfld    class [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection Microsoft.Crm.Asynchronous.GoalRollupDataAccess::_persistedConnection
0xb927  ldarg.0
0xb928  ldfld    class [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection Microsoft.Crm.Asynchronous.GoalRollupDataAccess::_persistedConnection
0xb92d  ldc.i4.0
0xb92e  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::set_TimeOut(int32)
0xb933  ldarg.0
0xb934  ldfld    class [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection Microsoft.Crm.Asynchronous.GoalRollupDataAccess::_persistedConnection
0xb939  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::Open()
0xb93e  ldarg.0
0xb93f  ldarg.0
0xb940  ldfld    class [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection Microsoft.Crm.Asynchronous.GoalRollupDataAccess::_persistedConnection
0xb945  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmTransaction::.ctor(class [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection)
0xb94a  stfld    class [Microsoft.Crm.Core]Microsoft.Crm.CrmTransaction Microsoft.Crm.Asynchronous.GoalRollupDataAccess::_persistedTransaction
0xb94f  ldarg.0
0xb950  ldfld    class [Microsoft.Crm.Core]Microsoft.Crm.CrmTransaction Microsoft.Crm.Asynchronous.GoalRollupDataAccess::_persistedTransaction
0xb955  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmTransaction::StartTransaction()
0xb95a  leave.s  loc_B9A7
0xb95c  stloc.0
0xb95d  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xb962  ldstr    aConnectionstri// "ConnectionString: {0}, "
0xb967  ldc.i4.1
0xb968  newarr   [mscorlib]System.Object
0xb96d  dup
0xb96e  ldc.i4.0
0xb96f  ldarg.0
0xb970  ldfld    class [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection Microsoft.Crm.Asynchronous.GoalRollupDataAccess::_persistedConnection
0xb975  callvirt instance string [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::get_ConnectionString()
0xb97a  stelem.ref
0xb97b  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xb980  stloc.1
0xb981  ldarg.0
0xb982  ldloc.0
0xb983  ldnull
0xb984  ldloc.1
0xb985  ldstr    aExceptionWhile_0// "Exception while trying to open database"...
0xb98a  call     string [mscorlib]System.String::Concat(string, string)
0xb98f  ldarg.0
0xb990  ldfld    class [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection Microsoft.Crm.Asynchronous.GoalRollupDataAccess::_persistedConnection
0xb995  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::get_OrganizationId()
0xb99a  ldarg.0
0xb99b  callvirt instance string [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessSharedBase::get_Name()
0xb9a0  callvirt instance void [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessSharedBase::HandleDatabaseException(class [mscorlib]System.Exception, class [System.Data]System.Data.IDbCommand, string, valuetype [mscorlib]System.Guid, string)
0xb9a5  rethrow
0xb9a7  ldarg.0
0xb9a8  ldfld    class [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection Microsoft.Crm.Asynchronous.GoalRollupDataAccess::_persistedConnection
0xb9ad  ret
```
