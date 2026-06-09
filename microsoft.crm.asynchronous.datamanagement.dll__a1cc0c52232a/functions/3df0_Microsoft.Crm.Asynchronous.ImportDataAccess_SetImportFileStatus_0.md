# Microsoft.Crm.Asynchronous.ImportDataAccess::SetImportFileStatus_0

- ea: `0x3df0`
- end: `0x3e67`
- name: `Microsoft.Crm.Asynchronous.ImportDataAccess::SetImportFileStatus_0`
- size: `119`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callers

- `0x14370`

## callees

- `0x3df0`
- `0x4540`

## string_xrefs

- `0x3df0`: `UPDATE ImportFileBase SET StatusCode = @status, ProcessingStatus = @processingStatusDetail WHERE ImportFileId = @importfileid AND StatusCode <> @statusCode`

## pseudocode

```c

```

## disassembly

```asm
0x3df0  ldstr    aUpdateImportfi_2// "UPDATE ImportFileBase SET StatusCode = "...
0x3df5  call     class [System.Data]System.Data.IDbCommand [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::NewCommand(string)
0x3dfa  stloc.0
0x3dfb  ldloc.0
0x3dfc  callvirt instance class [System.Data]System.Data.IDataParameterCollection [System.Data]System.Data.IDbCommand::get_Parameters()
0x3e01  castclass [System.Data]System.Data.SqlClient.SqlParameterCollection
0x3e06  dup
0x3e07  ldstr    aStatus// "@status"
0x3e0c  ldarg.2
0x3e0d  box      [mscorlib]System.Int32
0x3e12  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x3e17  pop
0x3e18  dup
0x3e19  ldstr    aProcessingstat// "@processingStatusDetail"
0x3e1e  ldarg.3
0x3e1f  box      [mscorlib]System.Int32
0x3e24  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x3e29  pop
0x3e2a  dup
0x3e2b  ldstr    aImportfileid// "@importfileid"
0x3e30  ldarga.s 1
0x3e32  ldstr    aD_0// "D"
0x3e37  call     instance string [mscorlib]System.Guid::ToString(string)
0x3e3c  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x3e41  pop
0x3e42  ldstr    aStatuscode_0// "@statusCode"
0x3e47  ldc.i4.5
0x3e48  box      [mscorlib]System.Int32
0x3e4d  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x3e52  pop
0x3e53  ldarg.0
0x3e54  ldloc.0
0x3e55  call     instance void Microsoft.Crm.Asynchronous.ImportDataAccess::ExecuteSqlCommandWithNoExpectedRecords(class [System.Data]System.Data.IDbCommand sqlCommand)
0x3e5a  leave.s  loc_3E66
0x3e5c  ldloc.0
0x3e5d  brfalse.s loc_3E65
0x3e5f  ldloc.0
0x3e60  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x3e65  endfinally
0x3e66  ret
```
