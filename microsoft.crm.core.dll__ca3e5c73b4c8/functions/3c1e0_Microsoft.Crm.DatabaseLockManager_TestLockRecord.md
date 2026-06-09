# Microsoft.Crm.DatabaseLockManager::TestLockRecord

- ea: `0x3c1e0`
- end: `0x3c2bd`
- name: `Microsoft.Crm.DatabaseLockManager::TestLockRecord`
- size: `221`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x3beb0`

## callees

- `0xd140`
- `0xdb70`
- `0x1f510`
- `0x3c190`
- `0x3c1e0`
- `0x3c2c0`
- `0x3c380`

## string_xrefs

- `0x3c26e`: `D:\a\1\s\src\Platform\Core\Security\SqlUtils\DatabaseLockManager.cs`
- `0x3c1e9`: `BEGIN TRAN; SELECT APPLOCK_TEST(@databasePrincipal , @resourceName , @lockMode , @lockOwner); COMMIT TRAN;`

## pseudocode

```c

```

## disassembly

```asm
0x3c1e0  ldarg.0
0x3c1e1  ldc.i4.1
0x3c1e2  call     instance class [System.Data]System.Data.IDbCommand Microsoft.Crm.DatabaseLockManager::CreateCommand([opt] bool forCheckOnly)
0x3c1e7  stloc.0
0x3c1e8  ldloc.0
0x3c1e9  ldstr    aBeginTranSelec// "BEGIN TRAN; SELECT APPLOCK_TEST(@databa"...
0x3c1ee  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0x3c1f3  ldloc.0
0x3c1f4  ldc.i4.1
0x3c1f5  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandType(valuetype [System.Data]System.Data.CommandType)
0x3c1fa  ldloc.0
0x3c1fb  callvirt instance class [System.Data]System.Data.IDataParameterCollection [System.Data]System.Data.IDbCommand::get_Parameters()
0x3c200  castclass [System.Data]System.Data.SqlClient.SqlParameterCollection
0x3c205  dup
0x3c206  ldstr    aDatabaseprinci// "@databasePrincipal"
0x3c20b  ldc.i4.s 0xC
0x3c20d  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType)
0x3c212  ldstr    aPublic// "public"
0x3c217  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x3c21c  dup
0x3c21d  ldstr    aResourcename// "@resourceName"
0x3c222  ldc.i4.s 0xC
0x3c224  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType)
0x3c229  ldarg.1
0x3c22a  callvirt instance string Microsoft.Crm.ILockResource::get_ResourceName()
0x3c22f  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x3c234  dup
0x3c235  ldstr    aLockmode_0// "@lockMode"
0x3c23a  ldc.i4.s 0xC
0x3c23c  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType)
0x3c241  ldarg.0
0x3c242  ldarg.2
0x3c243  call     instance string Microsoft.Crm.DatabaseLockManager::GetLockModeStringFromEnum(valuetype Microsoft.Crm.LockType lockType)
0x3c248  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x3c24d  ldstr    aLockowner// "@lockOwner"
0x3c252  ldc.i4.s 0xC
0x3c254  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType)
0x3c259  ldstr    aTransaction// "Transaction"
0x3c25e  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x3c263  ldloc.0
0x3c264  ldc.i4   0x13C
0x3c269  ldstr    aTestlockrecord// "TestLockRecord"
0x3c26e  ldstr    aDA1SSrcPlatfor_22// "D:\\a\\1\\s\\src\\Platform\\Core\\Secur"...
0x3c273  call     object Microsoft.Crm.CrmDbConnection::ExecuteScalar(class [System.Data]System.Data.IDbCommand command, [opt] int32 sourceLineNumber, [opt] string memberName, [opt] string sourceFilePath)
0x3c278  unbox.any [mscorlib]System.Int32
0x3c27d  ldc.i4.0
0x3c27e  cgt
0x3c280  stloc.1
0x3c281  leave.s  loc_3C2BB
0x3c283  ldloc.0
0x3c284  brfalse.s loc_3C28C
0x3c286  ldloc.0
0x3c287  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x3c28c  endfinally
0x3c28d  stloc.2
0x3c28e  ldloc.2
0x3c28f  ldarg.0
0x3c290  ldfld    class Microsoft.Crm.CrmDbConnection Microsoft.Crm.DatabaseLockManager::_connection
0x3c295  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.CrmDbConnection::get_OrganizationId()
0x3c29a  ldc.i4.s 0x14
0x3c29c  ldstr    aSqlexceptionWh_0// "SqlException when trying to check the l"...
0x3c2a1  ldc.i4.2
0x3c2a2  newarr   [mscorlib]System.Object
0x3c2a7  dup
0x3c2a8  ldc.i4.0
0x3c2a9  ldarg.1
0x3c2aa  callvirt instance string Microsoft.Crm.ILockResource::get_ResourceName()
0x3c2af  stelem.ref
0x3c2b0  dup
0x3c2b1  ldc.i4.1
0x3c2b2  ldloc.2
0x3c2b3  stelem.ref
0x3c2b4  call     void Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception ex, valuetype [mscorlib]System.Guid orgId, valuetype Microsoft.Crm.TraceCategory traceCategory, string format, object[] args)
0x3c2b9  rethrow
0x3c2bb  ldloc.1
0x3c2bc  ret
```
