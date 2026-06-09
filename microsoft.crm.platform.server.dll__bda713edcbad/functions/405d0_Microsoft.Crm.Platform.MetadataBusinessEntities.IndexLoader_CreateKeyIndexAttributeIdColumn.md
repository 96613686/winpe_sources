# Microsoft.Crm.Platform.MetadataBusinessEntities.IndexLoader::CreateKeyIndexAttributeIdColumn

- ea: `0x405d0`
- end: `0x40659`
- name: `Microsoft.Crm.Platform.MetadataBusinessEntities.IndexLoader::CreateKeyIndexAttributeIdColumn`
- size: `137`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callers

- `0x404c0`

## callees

- `0x405d0`

## string_xrefs

- `0x405e7`: `CreateKeyIndexAttributeIdColumn`
- `0x4063c`: `CreateKeyIndexAttributeIdColumn`
- `0x4062f`: `\nUPDATE EntityIndex SET KeyIndexAttributeId = '089E6AE8-E306-4C6D-8306-B8A473170D1E' WHERE NAME = 'BusinessDataLocalizedLabel_FullText'\nUPDATE EntityIndex SET KeyIndexAttributeId = '9DA6F50F-8E79-4518-A5B3-323E23AE7E50' WHERE NAME = 'DocumentIndex_FullText'\nUPDATE EntityIndex SET KeyIndexAttributeId = '51360A6E-C913-4D20-AD6D-9D423CA138FB' WHERE NAME = 'MultiSelectAttributeOptionValues_FullText'`

## pseudocode

```c

```

## disassembly

```asm
0x405d0  ldc.i4.0
0x405d1  stloc.0
0x405d2  ldarg.0
0x405d3  callvirt instance class [System.Data]System.Data.IDbCommand [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext::CreateSqlCommand()
0x405d8  stloc.1
0x405d9  ldloc.1
0x405da  ldstr    aIfNotExistsSel_2// "\r\nIF NOT EXISTS (SELECT * FROM sys.co"...
0x405df  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0x405e4  ldloc.1
0x405e5  ldc.i4.s 0x6E
0x405e7  ldstr    aCreatekeyindex// "CreateKeyIndexAttributeIdColumn"
0x405ec  ldstr    aDA1SSrcManaged_6// "D:\\a\\1\\s\\src\\ManagedPlatform\\Serv"...
0x405f1  call     class [System.Data]System.Data.IDataReader [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::ExecuteReader(class [System.Data]System.Data.IDbCommand, int32, string, string)
0x405f6  stloc.2
0x405f7  ldloc.2
0x405f8  callvirt instance bool [System.Data]System.Data.IDataReader::Read()
0x405fd  pop
0x405fe  ldloc.2
0x405ff  ldc.i4.0
0x40600  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(int32)
0x40605  unbox.any [mscorlib]System.Int32
0x4060a  ldc.i4.1
0x4060b  ceq
0x4060d  stloc.0
0x4060e  leave.s  loc_40624
0x40610  ldloc.2
0x40611  brfalse.s loc_40619
0x40613  ldloc.2
0x40614  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x40619  endfinally
0x4061a  ldloc.1
0x4061b  brfalse.s loc_40623
0x4061d  ldloc.1
0x4061e  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x40623  endfinally
0x40624  ldloc.0
0x40625  brfalse.s loc_40658
0x40627  ldarg.0
0x40628  callvirt instance class [System.Data]System.Data.IDbCommand [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext::CreateSqlCommand()
0x4062d  stloc.3
0x4062e  ldloc.3
0x4062f  ldstr    aUpdateEntityin// "\r\nUPDATE EntityIndex SET KeyIndexAttr"...
0x40634  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0x40639  ldloc.3
0x4063a  ldc.i4.s 0x7E
0x4063c  ldstr    aCreatekeyindex// "CreateKeyIndexAttributeIdColumn"
0x40641  ldstr    aDA1SSrcManaged_6// "D:\\a\\1\\s\\src\\ManagedPlatform\\Serv"...
0x40646  call     int32 [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::ExecuteNonQuery(class [System.Data]System.Data.IDbCommand, int32, string, string)
0x4064b  pop
0x4064c  leave.s  loc_40658
0x4064e  ldloc.3
0x4064f  brfalse.s loc_40657
0x40651  ldloc.3
0x40652  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x40657  endfinally
0x40658  ret
```
