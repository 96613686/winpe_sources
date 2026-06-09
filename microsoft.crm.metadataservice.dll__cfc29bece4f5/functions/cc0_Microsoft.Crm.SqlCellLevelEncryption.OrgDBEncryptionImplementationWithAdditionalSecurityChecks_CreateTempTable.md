# Microsoft.Crm.SqlCellLevelEncryption.OrgDBEncryptionImplementationWithAdditionalSecurityChecks::CreateTempTable

- ea: `0xcc0`
- end: `0xcf5`
- name: `Microsoft.Crm.SqlCellLevelEncryption.OrgDBEncryptionImplementationWithAdditionalSecurityChecks::CreateTempTable`
- size: `53`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x260`

## callees

- `0xab0`
- `0xcc0`

## string_xrefs

- `0xcdd`: `D:\a\1\s\src\Core\ObjectModel\Metadata\MetadataService\SqlEncryption\OrgDBEncryptionImplementation.cs`
- `0xcc8`: `CREATE TABLE #DecryptedData\n(\n	[ObjectId] [uniqueidentifier] NOT NULL,\n	[ColumnNumber] [int] NOT NULL,\n	[ObjectTypeCode] [int] NOT NULL,\n	[Value] [varbinary](max) NULL,\n	CONSTRAINT [PrimaryKey_DecryptedData] PRIMARY KEY CLUSTERED\n	(\n		[ObjectId],\n		[ObjectTypeCode],\n		[ColumnNumber]\n	)\n)\n`
- `0xcd8`: `CreateTempTable`

## pseudocode

```c

```

## disassembly

```asm
0xcc0  ldarg.0
0xcc1  call     instance class [System.Data]System.Data.IDbCommand Microsoft.Crm.SqlCellLevelEncryption.OrgDBEncryptionImplementationBase::CreateCommand()
0xcc6  stloc.0
0xcc7  ldloc.0
0xcc8  ldstr    aCreateTableDec// "CREATE TABLE #DecryptedData\r\n(\r\n\t["...
0xccd  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0xcd2  ldloc.0
0xcd3  ldc.i4   0x1B4
0xcd8  ldstr    aCreatetemptabl// "CreateTempTable"
0xcdd  ldstr    aDA1SSrcCoreObj// "D:\\a\\1\\s\\src\\Core\\ObjectModel\\Me"...
0xce2  call     int32 [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::ExecuteNonQuery(class [System.Data]System.Data.IDbCommand, int32, string, string)
0xce7  pop
0xce8  leave.s  loc_CF4
0xcea  ldloc.0
0xceb  brfalse.s loc_CF3
0xced  ldloc.0
0xcee  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xcf3  endfinally
0xcf4  ret
```
