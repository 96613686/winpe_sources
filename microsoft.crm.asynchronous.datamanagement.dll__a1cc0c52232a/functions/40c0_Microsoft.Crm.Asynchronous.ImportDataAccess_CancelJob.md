# Microsoft.Crm.Asynchronous.ImportDataAccess::CancelJob

- ea: `0x40c0`
- end: `0x4132`
- name: `Microsoft.Crm.Asynchronous.ImportDataAccess::CancelJob`
- size: `114`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callers

- `0xaf70`

## callees

- `0x40c0`
- `0x4540`

## string_xrefs

- `0x40c0`: `UPDATE AsyncOperationBase SET StateCode = @stateCode, StatusCode = @statusCode WHERE RegardingObjectId = @importId AND OperationType = @operationType`

## pseudocode

```c

```

## disassembly

```asm
0x40c0  ldstr    aUpdateAsyncope_0// "UPDATE AsyncOperationBase SET StateCode"...
0x40c5  call     class [System.Data]System.Data.IDbCommand [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::NewCommand(string)
0x40ca  stloc.0
0x40cb  ldloc.0
0x40cc  callvirt instance class [System.Data]System.Data.IDataParameterCollection [System.Data]System.Data.IDbCommand::get_Parameters()
0x40d1  castclass [System.Data]System.Data.SqlClient.SqlParameterCollection
0x40d6  dup
0x40d7  ldstr    aStatecode_0// "@stateCode"
0x40dc  ldc.i4.3
0x40dd  box      [mscorlib]System.Int32
0x40e2  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x40e7  pop
0x40e8  dup
0x40e9  ldstr    aStatuscode_0// "@statusCode"
0x40ee  ldc.i4.s 0x20
0x40f0  box      [mscorlib]System.Int32
0x40f5  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x40fa  pop
0x40fb  dup
0x40fc  ldstr    aImportid// "@importId"
0x4101  ldarg.1
0x4102  box      [mscorlib]System.Guid
0x4107  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x410c  pop
0x410d  ldstr    aOperationtype_0// "@operationType"
0x4112  ldarg.2
0x4113  box      [mscorlib]System.Int32
0x4118  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x411d  pop
0x411e  ldarg.0
0x411f  ldloc.0
0x4120  call     instance void Microsoft.Crm.Asynchronous.ImportDataAccess::ExecuteSqlCommandWithNoExpectedRecords(class [System.Data]System.Data.IDbCommand sqlCommand)
0x4125  leave.s  loc_4131
0x4127  ldloc.0
0x4128  brfalse.s loc_4130
0x412a  ldloc.0
0x412b  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x4130  endfinally
0x4131  ret
```
