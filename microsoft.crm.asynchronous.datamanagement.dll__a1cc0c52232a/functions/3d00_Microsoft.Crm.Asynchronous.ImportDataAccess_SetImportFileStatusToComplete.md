# Microsoft.Crm.Asynchronous.ImportDataAccess::SetImportFileStatusToComplete

- ea: `0x3d00`
- end: `0x3d7c`
- name: `Microsoft.Crm.Asynchronous.ImportDataAccess::SetImportFileStatusToComplete`
- size: `124`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callers

- `0xb850`
- `0x10b00`
- `0x13c50`
- `0x16bf0`

## callees

- `0x3d00`
- `0x4540`

## string_xrefs

- `0x3d00`: `UPDATE ImportFileBase SET StatusCode = @status, CompletedOn = @modifiedOn WHERE ImportFileId = @importfileid AND StatusCode <> @statusCode`

## pseudocode

```c

```

## disassembly

```asm
0x3d00  ldstr    aUpdateImportfi_0// "UPDATE ImportFileBase SET StatusCode = "...
0x3d05  call     class [System.Data]System.Data.IDbCommand [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::NewCommand(string)
0x3d0a  stloc.0
0x3d0b  ldloc.0
0x3d0c  callvirt instance class [System.Data]System.Data.IDataParameterCollection [System.Data]System.Data.IDbCommand::get_Parameters()
0x3d11  castclass [System.Data]System.Data.SqlClient.SqlParameterCollection
0x3d16  dup
0x3d17  ldstr    aStatus// "@status"
0x3d1c  ldarg.2
0x3d1d  box      [mscorlib]System.Int32
0x3d22  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x3d27  pop
0x3d28  dup
0x3d29  ldstr    aImportfileid// "@importfileid"
0x3d2e  ldarga.s 1
0x3d30  ldstr    aD_0// "D"
0x3d35  call     instance string [mscorlib]System.Guid::ToString(string)
0x3d3a  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x3d3f  pop
0x3d40  dup
0x3d41  ldstr    aModifiedon// "@modifiedOn"
0x3d46  ldarg.0
0x3d47  call     instance valuetype [mscorlib]System.DateTime [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessBase::GetUTCDateWithoutMilliseconds()
0x3d4c  box      [mscorlib]System.DateTime
0x3d51  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x3d56  pop
0x3d57  ldstr    aStatuscode_0// "@statusCode"
0x3d5c  ldc.i4.5
0x3d5d  box      [mscorlib]System.Int32
0x3d62  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x3d67  pop
0x3d68  ldarg.0
0x3d69  ldloc.0
0x3d6a  call     instance void Microsoft.Crm.Asynchronous.ImportDataAccess::ExecuteSqlCommandWithNoExpectedRecords(class [System.Data]System.Data.IDbCommand sqlCommand)
0x3d6f  leave.s  loc_3D7B
0x3d71  ldloc.0
0x3d72  brfalse.s loc_3D7A
0x3d74  ldloc.0
0x3d75  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x3d7a  endfinally
0x3d7b  ret
```
