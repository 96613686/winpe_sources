# Microsoft.Crm.SqlCellLevelEncryption.OrgDBEncryptionImplementationWithAdditionalSecurityChecks::DropTempTable

- ea: `0xd00`
- end: `0xd35`
- name: `Microsoft.Crm.SqlCellLevelEncryption.OrgDBEncryptionImplementationWithAdditionalSecurityChecks::DropTempTable`
- size: `53`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x260`

## callees

- `0xab0`
- `0xd00`

## string_xrefs

- `0xd1d`: `D:\a\1\s\src\Core\ObjectModel\Metadata\MetadataService\SqlEncryption\OrgDBEncryptionImplementation.cs`
- `0xd08`: `IF OBJECT_ID('tempdb..#DecryptedData') IS NOT NULL\n	DROP TABLE #DecryptedData`
- `0xd18`: `DropTempTable`

## pseudocode

```c

```

## disassembly

```asm
0xd00  ldarg.0
0xd01  call     instance class [System.Data]System.Data.IDbCommand Microsoft.Crm.SqlCellLevelEncryption.OrgDBEncryptionImplementationBase::CreateCommand()
0xd06  stloc.0
0xd07  ldloc.0
0xd08  ldstr    aIfObjectIdTemp// "IF OBJECT_ID('tempdb..#DecryptedData') "...
0xd0d  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0xd12  ldloc.0
0xd13  ldc.i4   0x1C1
0xd18  ldstr    aDroptemptable// "DropTempTable"
0xd1d  ldstr    aDA1SSrcCoreObj// "D:\\a\\1\\s\\src\\Core\\ObjectModel\\Me"...
0xd22  call     int32 [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::ExecuteNonQuery(class [System.Data]System.Data.IDbCommand, int32, string, string)
0xd27  pop
0xd28  leave.s  loc_D34
0xd2a  ldloc.0
0xd2b  brfalse.s loc_D33
0xd2d  ldloc.0
0xd2e  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xd33  endfinally
0xd34  ret
```
