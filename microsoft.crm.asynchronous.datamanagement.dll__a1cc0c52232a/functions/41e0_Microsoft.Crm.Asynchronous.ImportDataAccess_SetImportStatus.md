# Microsoft.Crm.Asynchronous.ImportDataAccess::SetImportStatus

- ea: `0x41e0`
- end: `0x4233`
- name: `Microsoft.Crm.Asynchronous.ImportDataAccess::SetImportStatus`
- size: `83`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callers

- `0xb0e0`

## callees

- `0x41e0`
- `0x4540`

## string_xrefs

- `0x41e0`: `UPDATE ImportBase SET StatusCode = @status WHERE ImportId = @importid`

## pseudocode

```c

```

## disassembly

```asm
0x41e0  ldstr    aUpdateImportba// "UPDATE ImportBase SET StatusCode = @sta"...
0x41e5  call     class [System.Data]System.Data.IDbCommand [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::NewCommand(string)
0x41ea  stloc.0
0x41eb  ldloc.0
0x41ec  callvirt instance class [System.Data]System.Data.IDataParameterCollection [System.Data]System.Data.IDbCommand::get_Parameters()
0x41f1  castclass [System.Data]System.Data.SqlClient.SqlParameterCollection
0x41f6  dup
0x41f7  ldstr    aStatus// "@status"
0x41fc  ldarg.2
0x41fd  box      [mscorlib]System.Int32
0x4202  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x4207  pop
0x4208  ldstr    aImportid_0// "@importid"
0x420d  ldarga.s 1
0x420f  ldstr    aD_0// "D"
0x4214  call     instance string [mscorlib]System.Guid::ToString(string)
0x4219  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x421e  pop
0x421f  ldarg.0
0x4220  ldloc.0
0x4221  call     instance void Microsoft.Crm.Asynchronous.ImportDataAccess::ExecuteSqlCommandWithNoExpectedRecords(class [System.Data]System.Data.IDbCommand sqlCommand)
0x4226  leave.s  loc_4232
0x4228  ldloc.0
0x4229  brfalse.s loc_4231
0x422b  ldloc.0
0x422c  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x4231  endfinally
0x4232  ret
```
