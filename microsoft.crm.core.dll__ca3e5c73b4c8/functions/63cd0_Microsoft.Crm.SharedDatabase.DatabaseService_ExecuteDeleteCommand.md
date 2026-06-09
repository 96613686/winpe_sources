# Microsoft.Crm.SharedDatabase.DatabaseService::ExecuteDeleteCommand

- ea: `0x63cd0`
- end: `0x63d9a`
- name: `Microsoft.Crm.SharedDatabase.DatabaseService::ExecuteDeleteCommand`
- size: `202`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `service_task, broker_com_uri`

## callers

- `0x6ed40`

## callees

- `0xd2f0`
- `0xd380`
- `0xd5f0`
- `0xdac0`
- `0x61120`
- `0x63000`
- `0x63cd0`
- `0x63ff0`
- `0x64580`

## string_xrefs

- `0x63d3f`: `D:\a\1\s\src\Platform\Core\DataServices\ObjectModel\DatabaseService.cs`
- `0x63d5e`: `D:\a\1\s\src\Platform\Core\DataServices\ObjectModel\DatabaseService.cs`
- `0x63d3a`: `ExecuteDeleteCommand`
- `0x63d59`: `ExecuteDeleteCommand`

## pseudocode

```c

```

## disassembly

```asm
0x63cd0  ldarg.2
0x63cd1  callvirt instance class [System.Data]System.Data.IDbCommand Microsoft.Crm.CrmDbConnection::CreateCommand()
0x63cd6  stloc.0
0x63cd7  ldarg.0
0x63cd8  callvirt instance bool Microsoft.Crm.SharedDatabase.DatabaseService::IsSettingsTableEnabled()
0x63cdd  brfalse.s loc_63CE6
0x63cdf  ldarg.0
0x63ce0  ldloc.0
0x63ce1  stfld    class [System.Data]System.Data.IDbCommand Microsoft.Crm.SharedDatabase.DatabaseService::_propertiesCommand
0x63ce6  ldarg.2
0x63ce7  callvirt instance class [System.Data]System.Data.IDbCommand Microsoft.Crm.CrmDbConnection::CreateCommand()
0x63cec  stloc.1
0x63ced  ldarg.0
0x63cee  ldloc.1
0x63cef  stfld    class [System.Data]System.Data.IDbCommand Microsoft.Crm.SharedDatabase.DatabaseService::_baseCommand
0x63cf4  ldarg.0
0x63cf5  ldarg.1
0x63cf6  call     instance void Microsoft.Crm.SharedDatabase.DatabaseService::BuildDeleteSql(class Microsoft.Crm.Data.PropertyBag[] conditions)
0x63cfb  ldarg.0
0x63cfc  callvirt instance bool Microsoft.Crm.SharedDatabase.DatabaseService::IsSettingsTableEnabled()
0x63d01  brfalse.s loc_63D14
0x63d03  ldloc.0
0x63d04  ldarg.0
0x63d05  ldfld    class [mscorlib]System.Text.StringBuilder Microsoft.Crm.SharedDatabase.DatabaseService::_propertiesSqlBuilder
0x63d0a  callvirt instance string [mscorlib]System.Object::ToString()
0x63d0f  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0x63d14  ldloc.1
0x63d15  ldarg.0
0x63d16  ldfld    class [mscorlib]System.Text.StringBuilder Microsoft.Crm.SharedDatabase.DatabaseService::_baseSqlBuilder
0x63d1b  callvirt instance string [mscorlib]System.Object::ToString()
0x63d20  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0x63d25  ldarg.2
0x63d26  callvirt instance void Microsoft.Crm.CrmDbConnection::Open()
0x63d2b  ldarg.0
0x63d2c  callvirt instance bool Microsoft.Crm.SharedDatabase.DatabaseService::IsSettingsTableEnabled()
0x63d31  brfalse.s loc_63D4A
0x63d33  ldloc.0
0x63d34  ldc.i4.1
0x63d35  ldc.i4   0xB54
0x63d3a  ldstr    aExecutedeletec// "ExecuteDeleteCommand"
0x63d3f  ldstr    aDA1SSrcPlatfor_44// "D:\\a\\1\\s\\src\\Platform\\Core\\DataS"...
0x63d44  call     int32 Microsoft.Crm.CrmDbConnection::ExecuteNonQuery(class [System.Data]System.Data.IDbCommand command, bool impersonate, [opt] int32 sourceLineNumber, [opt] string memberName, [opt] string sourceFilePath)
0x63d49  pop
0x63d4a  ldarg.0
0x63d4b  ldc.i4.1
0x63d4c  ldloc.1
0x63d4d  call     instance void Microsoft.Crm.SharedDatabase.DatabaseService::InstrumentQuery(valuetype Microsoft.Crm.InstrumentationOperationType type, class [System.Data]System.Data.IDbCommand command)
0x63d52  ldloc.1
0x63d53  ldc.i4.1
0x63d54  ldc.i4   0xB5C
0x63d59  ldstr    aExecutedeletec// "ExecuteDeleteCommand"
0x63d5e  ldstr    aDA1SSrcPlatfor_44// "D:\\a\\1\\s\\src\\Platform\\Core\\DataS"...
0x63d63  call     int32 Microsoft.Crm.CrmDbConnection::ExecuteNonQuery(class [System.Data]System.Data.IDbCommand command, bool impersonate, [opt] int32 sourceLineNumber, [opt] string memberName, [opt] string sourceFilePath)
0x63d68  stloc.2
0x63d69  leave.s  loc_63D98
0x63d6b  stloc.3
0x63d6c  ldloc.3
0x63d6d  isinst   Microsoft.Crm.CrmDBObjectNotFoundException
0x63d72  brtrue.s loc_63D7B
0x63d74  ldarg.0
0x63d75  ldloc.3
0x63d76  call     instance void Microsoft.Crm.SharedDatabase.DatabaseService::LogSqlError(class [mscorlib]System.Exception exception)
0x63d7b  rethrow
0x63d7d  ldarg.2
0x63d7e  callvirt instance void Microsoft.Crm.CrmDbConnection::Close()
0x63d83  endfinally
0x63d84  ldloc.1
0x63d85  brfalse.s loc_63D8D
0x63d87  ldloc.1
0x63d88  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x63d8d  endfinally
0x63d8e  ldloc.0
0x63d8f  brfalse.s loc_63D97
0x63d91  ldloc.0
0x63d92  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x63d97  endfinally
0x63d98  ldloc.2
0x63d99  ret
```
