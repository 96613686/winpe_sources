# Microsoft.Crm.Asynchronous.ImportDataAccess::SetImportFileStatus

- ea: `0x3d80`
- end: `0x3de5`
- name: `Microsoft.Crm.Asynchronous.ImportDataAccess::SetImportFileStatus`
- size: `101`
- prototype: ``
- caller_count: `7`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callers

- `0xbe90`
- `0xe130`
- `0x13c50`
- `0x13cf0`
- `0x14370`
- `0x14cb0`
- `0x16bf0`

## callees

- `0x3d80`
- `0x4540`

## string_xrefs

- `0x3d80`: `UPDATE ImportFileBase SET StatusCode = @status WHERE ImportFileId = @importfileid AND StatusCode <> @statusCode`

## pseudocode

```c

```

## disassembly

```asm
0x3d80  ldstr    aUpdateImportfi_1// "UPDATE ImportFileBase SET StatusCode = "...
0x3d85  call     class [System.Data]System.Data.IDbCommand [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::NewCommand(string)
0x3d8a  stloc.0
0x3d8b  ldloc.0
0x3d8c  callvirt instance class [System.Data]System.Data.IDataParameterCollection [System.Data]System.Data.IDbCommand::get_Parameters()
0x3d91  castclass [System.Data]System.Data.SqlClient.SqlParameterCollection
0x3d96  dup
0x3d97  ldstr    aStatus// "@status"
0x3d9c  ldarg.2
0x3d9d  box      [mscorlib]System.Int32
0x3da2  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x3da7  pop
0x3da8  dup
0x3da9  ldstr    aImportfileid// "@importfileid"
0x3dae  ldarga.s 1
0x3db0  ldstr    aD_0// "D"
0x3db5  call     instance string [mscorlib]System.Guid::ToString(string)
0x3dba  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x3dbf  pop
0x3dc0  ldstr    aStatuscode_0// "@statusCode"
0x3dc5  ldc.i4.5
0x3dc6  box      [mscorlib]System.Int32
0x3dcb  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x3dd0  pop
0x3dd1  ldarg.0
0x3dd2  ldloc.0
0x3dd3  call     instance void Microsoft.Crm.Asynchronous.ImportDataAccess::ExecuteSqlCommandWithNoExpectedRecords(class [System.Data]System.Data.IDbCommand sqlCommand)
0x3dd8  leave.s  loc_3DE4
0x3dda  ldloc.0
0x3ddb  brfalse.s loc_3DE3
0x3ddd  ldloc.0
0x3dde  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x3de3  endfinally
0x3de4  ret
```
