# Microsoft.Crm.Asynchronous.ImportDataAccess::UpdateImportFileCountField

- ea: `0x4240`
- end: `0x42a7`
- name: `Microsoft.Crm.Asynchronous.ImportDataAccess::UpdateImportFileCountField`
- size: `103`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callers

- `0x14940`
- `0x14cb0`
- `0x156f0`

## callees

- `0x4240`
- `0x4540`

## string_xrefs

- `0x4245`: `UPDATE ImportFileBase SET {0} = @count WHERE ImportFileId = @importfileid`

## pseudocode

```c

```

## disassembly

```asm
0x4240  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x4245  ldstr    aUpdateImportfi_7// "UPDATE ImportFileBase SET {0} = @count "...
0x424a  ldc.i4.1
0x424b  newarr   [mscorlib]System.Object
0x4250  dup
0x4251  ldc.i4.0
0x4252  ldarg.2
0x4253  stelem.ref
0x4254  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x4259  call     class [System.Data]System.Data.IDbCommand [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::NewCommand(string)
0x425e  stloc.0
0x425f  ldloc.0
0x4260  callvirt instance class [System.Data]System.Data.IDataParameterCollection [System.Data]System.Data.IDbCommand::get_Parameters()
0x4265  castclass [System.Data]System.Data.SqlClient.SqlParameterCollection
0x426a  dup
0x426b  ldstr    aCount// "@count"
0x4270  ldarg.3
0x4271  box      [mscorlib]System.Int64
0x4276  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x427b  pop
0x427c  ldstr    aImportfileid// "@importfileid"
0x4281  ldarga.s 1
0x4283  ldstr    aD_0// "D"
0x4288  call     instance string [mscorlib]System.Guid::ToString(string)
0x428d  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x4292  pop
0x4293  ldarg.0
0x4294  ldloc.0
0x4295  call     instance void Microsoft.Crm.Asynchronous.ImportDataAccess::ExecuteSqlCommandWithNoExpectedRecords(class [System.Data]System.Data.IDbCommand sqlCommand)
0x429a  leave.s  loc_42A6
0x429c  ldloc.0
0x429d  brfalse.s loc_42A5
0x429f  ldloc.0
0x42a0  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x42a5  endfinally
0x42a6  ret
```
