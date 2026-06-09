# Microsoft.Crm.Asynchronous.DTAManager::ExecuteRemoteFile

- ea: `0x1dd0`
- end: `0x1e14`
- name: `Microsoft.Crm.Asynchronous.DTAManager::ExecuteRemoteFile`
- size: `68`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1d70`

## callees

- `0x1dd0`

## string_xrefs

- `0x1de2`: `xp_cmdshell 'sqlcmd -S %COMPUTERNAME% -i {0}', no_output`

## pseudocode

```c

```

## disassembly

```asm
0x1dd0  ldarg.0
0x1dd1  ldfld    class [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection Microsoft.Crm.Asynchronous.DTAManager::_connection
0x1dd6  callvirt instance class [System.Data]System.Data.IDbCommand [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::CreateCommand()
0x1ddb  stloc.0
0x1ddc  ldloc.0
0x1ddd  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1de2  ldstr    aXpCmdshellSqlc// "xp_cmdshell 'sqlcmd -S %COMPUTERNAME% -"...
0x1de7  ldc.i4.1
0x1de8  newarr   [mscorlib]System.Object
0x1ded  dup
0x1dee  ldc.i4.0
0x1def  ldarg.0
0x1df0  ldfld    string Microsoft.Crm.Asynchronous.DTAManager::_fullOutputFilePath
0x1df5  stelem.ref
0x1df6  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x1dfb  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0x1e00  ldloc.0
0x1e01  callvirt instance int32 [System.Data]System.Data.IDbCommand::ExecuteNonQuery()
0x1e06  pop
0x1e07  leave.s  loc_1E13
0x1e09  ldloc.0
0x1e0a  brfalse.s loc_1E12
0x1e0c  ldloc.0
0x1e0d  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1e12  endfinally
0x1e13  ret
```
