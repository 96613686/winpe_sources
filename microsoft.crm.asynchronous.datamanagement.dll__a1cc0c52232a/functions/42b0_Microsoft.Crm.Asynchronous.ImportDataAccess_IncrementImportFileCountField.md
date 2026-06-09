# Microsoft.Crm.Asynchronous.ImportDataAccess::IncrementImportFileCountField

- ea: `0x42b0`
- end: `0x4312`
- name: `Microsoft.Crm.Asynchronous.ImportDataAccess::IncrementImportFileCountField`
- size: `98`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callers

- `0x51f0`
- `0xe960`

## callees

- `0x42b0`
- `0x4540`

## string_xrefs

- `0x42b9`: `UPDATE ImportFileBase SET {0} = {0} + {1} WHERE ImportFileId = @importfileid`

## pseudocode

```c

```

## disassembly

```asm
0x42b0  ldarg.3
0x42b1  brtrue.s loc_42B4
0x42b3  ret
0x42b4  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x42b9  ldstr    aUpdateImportfi_8// "UPDATE ImportFileBase SET {0} = {0} + {"...
0x42be  ldc.i4.2
0x42bf  newarr   [mscorlib]System.Object
0x42c4  dup
0x42c5  ldc.i4.0
0x42c6  ldarg.2
0x42c7  stelem.ref
0x42c8  dup
0x42c9  ldc.i4.1
0x42ca  ldarg.3
0x42cb  box      [mscorlib]System.Int32
0x42d0  stelem.ref
0x42d1  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x42d6  call     class [System.Data]System.Data.IDbCommand [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::NewCommand(string)
0x42db  stloc.0
0x42dc  ldloc.0
0x42dd  callvirt instance class [System.Data]System.Data.IDataParameterCollection [System.Data]System.Data.IDbCommand::get_Parameters()
0x42e2  castclass [System.Data]System.Data.SqlClient.SqlParameterCollection
0x42e7  ldstr    aImportfileid// "@importfileid"
0x42ec  ldarga.s 1
0x42ee  ldstr    aD_0// "D"
0x42f3  call     instance string [mscorlib]System.Guid::ToString(string)
0x42f8  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x42fd  pop
0x42fe  ldarg.0
0x42ff  ldloc.0
0x4300  call     instance void Microsoft.Crm.Asynchronous.ImportDataAccess::ExecuteSqlCommandWithNoExpectedRecords(class [System.Data]System.Data.IDbCommand sqlCommand)
0x4305  leave.s  loc_4311
0x4307  ldloc.0
0x4308  brfalse.s loc_4310
0x430a  ldloc.0
0x430b  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x4310  endfinally
0x4311  ret
```
