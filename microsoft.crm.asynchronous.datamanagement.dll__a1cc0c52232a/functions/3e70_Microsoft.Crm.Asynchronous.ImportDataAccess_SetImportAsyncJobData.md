# Microsoft.Crm.Asynchronous.ImportDataAccess::SetImportAsyncJobData

- ea: `0x3e70`
- end: `0x3eb8`
- name: `Microsoft.Crm.Asynchronous.ImportDataAccess::SetImportAsyncJobData`
- size: `72`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callers

- `0xd7d0`
- `0x1d5e0`

## callees

- `0x3e70`
- `0x4540`

## string_xrefs

- `0x3e70`: `UPDATE AsyncOperationBase SET Data = @data WHERE AsyncOperationId = @asyncOperationId`

## pseudocode

```c

```

## disassembly

```asm
0x3e70  ldstr    aUpdateAsyncope// "UPDATE AsyncOperationBase SET Data = @d"...
0x3e75  call     class [System.Data]System.Data.IDbCommand [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::NewCommand(string)
0x3e7a  stloc.0
0x3e7b  ldloc.0
0x3e7c  callvirt instance class [System.Data]System.Data.IDataParameterCollection [System.Data]System.Data.IDbCommand::get_Parameters()
0x3e81  castclass [System.Data]System.Data.SqlClient.SqlParameterCollection
0x3e86  dup
0x3e87  ldstr    aAsyncoperation// "@asyncOperationId"
0x3e8c  ldarg.1
0x3e8d  box      [mscorlib]System.Guid
0x3e92  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x3e97  pop
0x3e98  ldstr    aData// "@data"
0x3e9d  ldarg.2
0x3e9e  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x3ea3  pop
0x3ea4  ldarg.0
0x3ea5  ldloc.0
0x3ea6  call     instance void Microsoft.Crm.Asynchronous.ImportDataAccess::ExecuteSqlCommandWithNoExpectedRecords(class [System.Data]System.Data.IDbCommand sqlCommand)
0x3eab  leave.s  loc_3EB7
0x3ead  ldloc.0
0x3eae  brfalse.s loc_3EB6
0x3eb0  ldloc.0
0x3eb1  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x3eb6  endfinally
0x3eb7  ret
```
