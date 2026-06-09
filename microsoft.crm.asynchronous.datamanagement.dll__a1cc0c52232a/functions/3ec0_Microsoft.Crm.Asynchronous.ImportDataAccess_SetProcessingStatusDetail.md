# Microsoft.Crm.Asynchronous.ImportDataAccess::SetProcessingStatusDetail

- ea: `0x3ec0`
- end: `0x3f25`
- name: `Microsoft.Crm.Asynchronous.ImportDataAccess::SetProcessingStatusDetail`
- size: `101`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callers

- `0xe130`
- `0x10b00`
- `0x16690`

## callees

- `0x3ec0`
- `0x4540`

## string_xrefs

- `0x3ec0`: `UPDATE ImportFileBase SET ProcessingStatus = @processingStatusDetail, ProgressCounter = @progressCounter WHERE ImportFileId = @importfileid`

## pseudocode

```c

```

## disassembly

```asm
0x3ec0  ldstr    aUpdateImportfi_3// "UPDATE ImportFileBase SET ProcessingSta"...
0x3ec5  call     class [System.Data]System.Data.IDbCommand [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::NewCommand(string)
0x3eca  stloc.0
0x3ecb  ldloc.0
0x3ecc  callvirt instance class [System.Data]System.Data.IDataParameterCollection [System.Data]System.Data.IDbCommand::get_Parameters()
0x3ed1  castclass [System.Data]System.Data.SqlClient.SqlParameterCollection
0x3ed6  dup
0x3ed7  ldstr    aProcessingstat// "@processingStatusDetail"
0x3edc  ldarg.2
0x3edd  box      [mscorlib]System.Int32
0x3ee2  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x3ee7  pop
0x3ee8  dup
0x3ee9  ldstr    aProgresscounte// "@progressCounter"
0x3eee  ldarg.3
0x3eef  box      [mscorlib]System.Int32
0x3ef4  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x3ef9  pop
0x3efa  ldstr    aImportfileid// "@importfileid"
0x3eff  ldarga.s 1
0x3f01  ldstr    aD_0// "D"
0x3f06  call     instance string [mscorlib]System.Guid::ToString(string)
0x3f0b  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x3f10  pop
0x3f11  ldarg.0
0x3f12  ldloc.0
0x3f13  call     instance void Microsoft.Crm.Asynchronous.ImportDataAccess::ExecuteSqlCommandWithNoExpectedRecords(class [System.Data]System.Data.IDbCommand sqlCommand)
0x3f18  leave.s  loc_3F24
0x3f1a  ldloc.0
0x3f1b  brfalse.s loc_3F23
0x3f1d  ldloc.0
0x3f1e  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x3f23  endfinally
0x3f24  ret
```
