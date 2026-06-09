# Microsoft.Crm.SharedDatabase.DatabaseService::ExecuteUpdateCommand

- ea: `0x63b70`
- end: `0x63c4c`
- name: `Microsoft.Crm.SharedDatabase.DatabaseService::ExecuteUpdateCommand`
- size: `220`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x6ecb0`

## callees

- `0xd2f0`
- `0xd380`
- `0xd5f0`
- `0xdac0`
- `0x2e9f0`
- `0x60870`
- `0x62b10`
- `0x62f80`
- `0x630a0`
- `0x63b70`
- `0x63da0`
- `0x63e20`
- `0x63ff0`
- `0x64060`
- `0x64580`

## string_xrefs

- `0x63c08`: `D:\a\1\s\src\Platform\Core\DataServices\ObjectModel\DatabaseService.cs`
- `0x63c03`: `ExecuteUpdateCommand`

## pseudocode

```c

```

## disassembly

```asm
0x63b70  ldarg.3
0x63b71  callvirt instance class [System.Data]System.Data.IDbCommand Microsoft.Crm.CrmDbConnection::CreateCommand()
0x63b76  stloc.0
0x63b77  ldarg.0
0x63b78  ldloc.0
0x63b79  stfld    class [System.Data]System.Data.IDbCommand Microsoft.Crm.SharedDatabase.DatabaseService::_baseCommand
0x63b7e  ldarg.0
0x63b7f  ldfld    bool Microsoft.Crm.SharedDatabase.DatabaseService::_hasBaseColumns
0x63b84  brfalse.s loc_63B9F
0x63b86  ldarg.0
0x63b87  ldarg.1
0x63b88  ldarg.2
0x63b89  call     instance void Microsoft.Crm.SharedDatabase.DatabaseService::BuildBaseUpdateSql(class Microsoft.Crm.Data.PropertyBag columnSet, class Microsoft.Crm.Data.PropertyBag[] conditions)
0x63b8e  ldarg.0
0x63b8f  ldfld    class [mscorlib]System.Text.StringBuilder Microsoft.Crm.SharedDatabase.DatabaseService::_baseSqlBuilder
0x63b94  ldstr    asc_7C4D8// ";"
0x63b99  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x63b9e  pop
0x63b9f  ldarg.0
0x63ba0  callvirt instance bool Microsoft.Crm.SharedDatabase.DatabaseService::get_HasPropertiesColumns()
0x63ba5  brfalse.s loc_63BAF
0x63ba7  ldarg.0
0x63ba8  ldarg.1
0x63ba9  ldarg.2
0x63baa  call     instance void Microsoft.Crm.SharedDatabase.DatabaseService::BuildUpsertSql(class Microsoft.Crm.Data.PropertyBag columnSet, class Microsoft.Crm.Data.PropertyBag[] conditions)
0x63baf  ldarg.0
0x63bb0  call     instance void Microsoft.Crm.SharedDatabase.DatabaseService::BuildOpenSymmetricKeySql()
0x63bb5  ldarg.0
0x63bb6  call     instance void Microsoft.Crm.SharedDatabase.DatabaseService::BuildCloseSymmetricKeySql()
0x63bbb  ldarg.3
0x63bbc  callvirt instance void Microsoft.Crm.CrmDbConnection::Open()
0x63bc1  ldloc.0
0x63bc2  ldc.i4.3
0x63bc3  newarr   [mscorlib]System.String
0x63bc8  dup
0x63bc9  ldc.i4.0
0x63bca  ldarg.0
0x63bcb  ldfld    class [mscorlib]System.Text.StringBuilder Microsoft.Crm.SharedDatabase.DatabaseService::_preSqlBuilder
0x63bd0  callvirt instance string [mscorlib]System.Object::ToString()
0x63bd5  stelem.ref
0x63bd6  dup
0x63bd7  ldc.i4.1
0x63bd8  ldarg.0
0x63bd9  ldfld    class [mscorlib]System.Text.StringBuilder Microsoft.Crm.SharedDatabase.DatabaseService::_baseSqlBuilder
0x63bde  callvirt instance string [mscorlib]System.Object::ToString()
0x63be3  stelem.ref
0x63be4  dup
0x63be5  ldc.i4.2
0x63be6  ldarg.0
0x63be7  ldfld    class [mscorlib]System.Text.StringBuilder Microsoft.Crm.SharedDatabase.DatabaseService::_postSqlBuilder
0x63bec  callvirt instance string [mscorlib]System.Object::ToString()
0x63bf1  stelem.ref
0x63bf2  call     string Microsoft.Crm.SharedDatabase.DatabaseService::BuildSql(string[] sqlStatements)
0x63bf7  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0x63bfc  ldloc.0
0x63bfd  ldc.i4.1
0x63bfe  ldc.i4   0xAFC
0x63c03  ldstr    aExecuteupdatec// "ExecuteUpdateCommand"
0x63c08  ldstr    aDA1SSrcPlatfor_44// "D:\\a\\1\\s\\src\\Platform\\Core\\DataS"...
0x63c0d  call     int32 Microsoft.Crm.CrmDbConnection::ExecuteNonQuery(class [System.Data]System.Data.IDbCommand command, bool impersonate, [opt] int32 sourceLineNumber, [opt] string memberName, [opt] string sourceFilePath)
0x63c12  ldc.i4.1
0x63c13  ldarg.0
0x63c14  ldfld    class Microsoft.Crm.SharedDatabase.Table Microsoft.Crm.SharedDatabase.DatabaseService::_table
0x63c19  callvirt instance valuetype Microsoft.Crm.SharedDatabase.ConfigScope Microsoft.Crm.SharedDatabase.Table::get_Scope()
0x63c1e  ldloc.0
0x63c1f  call     void Microsoft.Crm.AsyncConfigDbLoadInstrumentation::LogResult(valuetype Microsoft.Crm.InstrumentationOperationType operationType, valuetype Microsoft.Crm.SharedDatabase.ConfigScope scope, class [System.Data]System.Data.IDbCommand command)
0x63c24  ldarg.0
0x63c25  ldc.i4.1
0x63c26  ldloc.0
0x63c27  call     instance void Microsoft.Crm.SharedDatabase.DatabaseService::InstrumentQuery(valuetype Microsoft.Crm.InstrumentationOperationType type, class [System.Data]System.Data.IDbCommand command)
0x63c2c  stloc.1
0x63c2d  leave.s  loc_63C4A
0x63c2f  stloc.2
0x63c30  ldarg.0
0x63c31  ldloc.2
0x63c32  call     instance void Microsoft.Crm.SharedDatabase.DatabaseService::LogSqlError(class [mscorlib]System.Exception exception)
0x63c37  rethrow
0x63c39  ldarg.3
0x63c3a  callvirt instance void Microsoft.Crm.CrmDbConnection::Close()
0x63c3f  endfinally
0x63c40  ldloc.0
0x63c41  brfalse.s loc_63C49
0x63c43  ldloc.0
0x63c44  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x63c49  endfinally
0x63c4a  ldloc.1
0x63c4b  ret
```
