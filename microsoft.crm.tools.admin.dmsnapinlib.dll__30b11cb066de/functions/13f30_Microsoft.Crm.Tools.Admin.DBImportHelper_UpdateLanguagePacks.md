# Microsoft.Crm.Tools.Admin.DBImportHelper::UpdateLanguagePacks

- ea: `0x13f30`
- end: `0x13f6b`
- name: `Microsoft.Crm.Tools.Admin.DBImportHelper::UpdateLanguagePacks`
- size: `59`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callers

- `0x14630`
- `0x15350`

## callees

- `0x14170`
- `0x141b0`

## string_xrefs

- `0x13f31`: `UPDATE OrganizationLanguagePack SET OrganizationId = @newOrganizationId`
- `0x13f5a`: `UpdateLanguagePacks`

## pseudocode

```c

```

## disassembly

```asm
0x13f30  ldarg.0
0x13f31  ldstr    aUpdateOrganiza_0// "UPDATE OrganizationLanguagePack SET Org"...
0x13f36  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0x13f3b  ldarg.0
0x13f3c  call     void Microsoft.Crm.Tools.Admin.DBImportHelper::ClearParameters(class [System.Data]System.Data.IDbCommand command)
0x13f41  ldarg.0
0x13f42  ldarg.1
0x13f43  box      [mscorlib]System.Guid
0x13f48  ldstr    aNeworganizatio// "@newOrganizationId"
0x13f4d  ldc.i4.s 9
0x13f4f  call     void Microsoft.Crm.Tools.Admin.DBImportHelper::AddParameter(class [System.Data]System.Data.IDbCommand command, object value, string parameterName, valuetype [System.Data]System.Data.DbType dbType)
0x13f54  ldarg.0
0x13f55  ldc.i4   0x15B
0x13f5a  ldstr    aUpdatelanguage// "UpdateLanguagePacks"
0x13f5f  ldstr    aDDbsShDccm2110_10// "d:\\dbs\\sh\\dccm2\\1101_190851\\cmd\\4"...
0x13f64  call     int32 [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::ExecuteNonQuery(class [System.Data]System.Data.IDbCommand, int32, string, string)
0x13f69  pop
0x13f6a  ret
```
