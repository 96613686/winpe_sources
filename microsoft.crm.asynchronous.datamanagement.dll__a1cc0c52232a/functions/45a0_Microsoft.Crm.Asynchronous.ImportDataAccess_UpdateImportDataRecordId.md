# Microsoft.Crm.Asynchronous.ImportDataAccess::UpdateImportDataRecordId

- ea: `0x45a0`
- end: `0x45ed`
- name: `Microsoft.Crm.Asynchronous.ImportDataAccess::UpdateImportDataRecordId`
- size: `77`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callers

- `0xf190`

## callees

- `0x4540`
- `0x45a0`

## string_xrefs

- `0x45a0`: `UPDATE ImportDataBase SET RecordId = @value WHERE ImportDataId = @importdataid`

## pseudocode

```c

```

## disassembly

```asm
0x45a0  ldstr    aUpdateImportda// "UPDATE ImportDataBase SET RecordId = @v"...
0x45a5  call     class [System.Data]System.Data.IDbCommand [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::NewCommand(string)
0x45aa  stloc.0
0x45ab  ldloc.0
0x45ac  callvirt instance class [System.Data]System.Data.IDataParameterCollection [System.Data]System.Data.IDbCommand::get_Parameters()
0x45b1  castclass [System.Data]System.Data.SqlClient.SqlParameterCollection
0x45b6  dup
0x45b7  ldstr    aValue// "@value"
0x45bc  ldarg.2
0x45bd  box      [mscorlib]System.Guid
0x45c2  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x45c7  pop
0x45c8  ldstr    aImportdataid// "@importdataid"
0x45cd  ldarg.1
0x45ce  box      [mscorlib]System.Guid
0x45d3  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x45d8  pop
0x45d9  ldarg.0
0x45da  ldloc.0
0x45db  call     instance void Microsoft.Crm.Asynchronous.ImportDataAccess::ExecuteSqlCommandWithNoExpectedRecords(class [System.Data]System.Data.IDbCommand sqlCommand)
0x45e0  leave.s  loc_45EC
0x45e2  ldloc.0
0x45e3  brfalse.s loc_45EB
0x45e5  ldloc.0
0x45e6  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x45eb  endfinally
0x45ec  ret
```
