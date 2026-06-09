# Microsoft.Crm.Asynchronous.ImportDataAccess::CleanImportFileContent

- ea: `0x3ca0`
- end: `0x3cf2`
- name: `Microsoft.Crm.Asynchronous.ImportDataAccess::CleanImportFileContent`
- size: `82`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callers

- `0xb6b0`
- `0x14370`

## callees

- `0x3ca0`
- `0x4540`

## string_xrefs

- `0x3ca0`: `UPDATE ImportFileBase SET Content = @content WHERE ImportFileId = @importfileid`

## pseudocode

```c

```

## disassembly

```asm
0x3ca0  ldstr    aUpdateImportfi// "UPDATE ImportFileBase SET Content = @co"...
0x3ca5  call     class [System.Data]System.Data.IDbCommand [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::NewCommand(string)
0x3caa  stloc.0
0x3cab  ldloc.0
0x3cac  callvirt instance class [System.Data]System.Data.IDataParameterCollection [System.Data]System.Data.IDbCommand::get_Parameters()
0x3cb1  castclass [System.Data]System.Data.SqlClient.SqlParameterCollection
0x3cb6  dup
0x3cb7  ldstr    aContent// "@content"
0x3cbc  ldsfld   string [mscorlib]System.String::Empty
0x3cc1  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x3cc6  pop
0x3cc7  ldstr    aImportfileid// "@importfileid"
0x3ccc  ldarga.s 1
0x3cce  ldstr    aD_0// "D"
0x3cd3  call     instance string [mscorlib]System.Guid::ToString(string)
0x3cd8  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x3cdd  pop
0x3cde  ldarg.0
0x3cdf  ldloc.0
0x3ce0  call     instance void Microsoft.Crm.Asynchronous.ImportDataAccess::ExecuteSqlCommandWithNoExpectedRecords(class [System.Data]System.Data.IDbCommand sqlCommand)
0x3ce5  leave.s  loc_3CF1
0x3ce7  ldloc.0
0x3ce8  brfalse.s loc_3CF0
0x3cea  ldloc.0
0x3ceb  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x3cf0  endfinally
0x3cf1  ret
```
