# Microsoft.Crm.Asynchronous.ImportDataAccess::UpdateProgressCounter

- ea: `0x3f30`
- end: `0x3f83`
- name: `Microsoft.Crm.Asynchronous.ImportDataAccess::UpdateProgressCounter`
- size: `83`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callers

- `0xe550`
- `0x10b00`
- `0x17420`

## callees

- `0x3f30`
- `0x4540`

## string_xrefs

- `0x3f30`: `UPDATE ImportFileBase SET ProgressCounter = @progressCounter WHERE ImportFileId = @importfileid`

## pseudocode

```c

```

## disassembly

```asm
0x3f30  ldstr    aUpdateImportfi_4// "UPDATE ImportFileBase SET ProgressCount"...
0x3f35  call     class [System.Data]System.Data.IDbCommand [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::NewCommand(string)
0x3f3a  stloc.0
0x3f3b  ldloc.0
0x3f3c  callvirt instance class [System.Data]System.Data.IDataParameterCollection [System.Data]System.Data.IDbCommand::get_Parameters()
0x3f41  castclass [System.Data]System.Data.SqlClient.SqlParameterCollection
0x3f46  dup
0x3f47  ldstr    aProgresscounte// "@progressCounter"
0x3f4c  ldarg.2
0x3f4d  box      [mscorlib]System.Int32
0x3f52  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x3f57  pop
0x3f58  ldstr    aImportfileid// "@importfileid"
0x3f5d  ldarga.s 1
0x3f5f  ldstr    aD_0// "D"
0x3f64  call     instance string [mscorlib]System.Guid::ToString(string)
0x3f69  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x3f6e  pop
0x3f6f  ldarg.0
0x3f70  ldloc.0
0x3f71  call     instance void Microsoft.Crm.Asynchronous.ImportDataAccess::ExecuteSqlCommandWithNoExpectedRecords(class [System.Data]System.Data.IDbCommand sqlCommand)
0x3f76  leave.s  loc_3F82
0x3f78  ldloc.0
0x3f79  brfalse.s loc_3F81
0x3f7b  ldloc.0
0x3f7c  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x3f81  endfinally
0x3f82  ret
```
