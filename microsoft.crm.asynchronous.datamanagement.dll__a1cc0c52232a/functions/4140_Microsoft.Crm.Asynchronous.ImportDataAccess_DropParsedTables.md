# Microsoft.Crm.Asynchronous.ImportDataAccess::DropParsedTables

- ea: `0x4140`
- end: `0x41de`
- name: `Microsoft.Crm.Asynchronous.ImportDataAccess::DropParsedTables`
- size: `158`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callers

- `0xafb0`

## callees

- `0x4140`
- `0x4540`

## string_xrefs

- `0x41ae`: `UPDATE ImportFileBase SET ParsedTableName = NULL, ModifiedOn = GETDATE() WHERE ImportId = @importId;\n`

## pseudocode

```c

```

## disassembly

```asm
0x4140  ldarg.1
0x4141  ldlen
0x4142  brtrue.s loc_4145
0x4144  ret
0x4145  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor()
0x414a  stloc.0
0x414b  ldloc.0
0x414c  ldstr    aDropTable// "DROP TABLE "
0x4151  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x4156  pop
0x4157  ldc.i4.0
0x4158  stloc.2
0x4159  br.s     loc_4175
0x415b  ldloc.0
0x415c  ldarg.1
0x415d  ldloc.2
0x415e  ldelem.ref
0x415f  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x4164  pop
0x4165  ldloc.0
0x4166  ldstr    asc_24112// ","
0x416b  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x4170  pop
0x4171  ldloc.2
0x4172  ldc.i4.1
0x4173  add
0x4174  stloc.2
0x4175  ldloc.2
0x4176  ldarg.1
0x4177  ldlen
0x4178  conv.i4
0x4179  blt.s    loc_415B
0x417b  ldloc.0
0x417c  ldc.i4.0
0x417d  ldloc.0
0x417e  callvirt instance int32 [mscorlib]System.Text.StringBuilder::get_Length()
0x4183  ldc.i4.1
0x4184  sub
0x4185  callvirt instance string [mscorlib]System.Text.StringBuilder::ToString(int32, int32)
0x418a  stloc.1
0x418b  call     class [System.Data]System.Data.IDbCommand [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::NewCommand()
0x4190  stloc.3
0x4191  ldloc.3
0x4192  callvirt instance class [System.Data]System.Data.IDataParameterCollection [System.Data]System.Data.IDbCommand::get_Parameters()
0x4197  castclass [System.Data]System.Data.SqlClient.SqlParameterCollection
0x419c  ldstr    aImportid// "@importId"
0x41a1  ldarg.2
0x41a2  box      [mscorlib]System.Guid
0x41a7  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x41ac  pop
0x41ad  ldloc.3
0x41ae  ldstr    aUpdateImportfi_6// "UPDATE ImportFileBase SET ParsedTableNa"...
0x41b3  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0x41b8  ldloc.3
0x41b9  dup
0x41ba  callvirt instance string [System.Data]System.Data.IDbCommand::get_CommandText()
0x41bf  ldloc.1
0x41c0  call     string [mscorlib]System.String::Concat(string, string)
0x41c5  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0x41ca  ldarg.0
0x41cb  ldloc.3
0x41cc  call     instance void Microsoft.Crm.Asynchronous.ImportDataAccess::ExecuteSqlCommandWithNoExpectedRecords(class [System.Data]System.Data.IDbCommand sqlCommand)
0x41d1  leave.s  loc_41DD
0x41d3  ldloc.3
0x41d4  brfalse.s loc_41DC
0x41d6  ldloc.3
0x41d7  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x41dc  endfinally
0x41dd  ret
```
