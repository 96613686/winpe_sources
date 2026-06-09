# Microsoft.Crm.Asynchronous.Rollups.BootstrapDataAccess::CleanupJobs

- ea: `0xe9c0`
- end: `0xea6f`
- name: `Microsoft.Crm.Asynchronous.Rollups.BootstrapDataAccess::CleanupJobs`
- size: `175`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callees

- `0xc9b0`
- `0xe7b0`
- `0xe930`
- `0xe9c0`

## string_xrefs

- `0xe9e6`: `RollupPropertiesId`
- `0xea34`: `@rollupPropertiesId`
- `0xe9cc`: `DELETE TOP({0}) FROM {2} WHERE {1} = @rollupPropertiesId`

## pseudocode

```c

```

## disassembly

```asm
0xe9c0  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor()
0xe9c5  stloc.0
0xe9c6  ldloc.0
0xe9c7  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xe9cc  ldstr    aDeleteTop0From_0// "DELETE TOP({0}) FROM {2} WHERE {1} = @r"...
0xe9d1  ldc.i4.3
0xe9d2  newarr   [mscorlib]System.Object
0xe9d7  dup
0xe9d8  ldc.i4.0
0xe9d9  call     int32 Microsoft.Crm.Asynchronous.Rollups.RollupConfiguration::get_BootstrapRollupUpdateBatchSize()
0xe9de  box      [mscorlib]System.Int32
0xe9e3  stelem.ref
0xe9e4  dup
0xe9e5  ldc.i4.1
0xe9e6  ldstr    aRollupproperti// "RollupPropertiesId"
0xe9eb  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::SqlIdentifierEncode(string)
0xe9f0  stelem.ref
0xe9f1  dup
0xe9f2  ldc.i4.2
0xe9f3  ldstr    aRollupjobbase// "RollupJobBase"
0xe9f8  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::SqlIdentifierEncode(string)
0xe9fd  stelem.ref
0xe9fe  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendFormat(class [mscorlib]System.IFormatProvider, string, object[])
0xea03  pop
0xea04  ldloc.0
0xea05  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine()
0xea0a  pop
0xea0b  ldloc.0
0xea0c  ldstr    aSelectRowcount// "SELECT @@ROWCOUNT"
0xea11  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine(string)
0xea16  pop
0xea17  call     class [System.Data]System.Data.IDbCommand [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::NewCommand()
0xea1c  stloc.1
0xea1d  ldloc.1
0xea1e  ldloc.0
0xea1f  callvirt instance string [mscorlib]System.Object::ToString()
0xea24  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0xea29  ldloc.1
0xea2a  callvirt instance class [System.Data]System.Data.IDataParameterCollection [System.Data]System.Data.IDbCommand::get_Parameters()
0xea2f  castclass [System.Data]System.Data.SqlClient.SqlParameterCollection
0xea34  ldstr    aRollupproperti_0// "@rollupPropertiesId"
0xea39  ldarg.0
0xea3a  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.Rollups.BootstrapDataAccess::get_RollupPropertiesId()
0xea3f  box      [mscorlib]System.Guid
0xea44  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0xea49  pop
0xea4a  ldarg.0
0xea4b  ldloc.1
0xea4c  call     instance object Microsoft.Crm.Asynchronous.Rollups.BootstrapDataAccess::ExecuteSqlCommand(class [System.Data]System.Data.IDbCommand command)
0xea51  dup
0xea52  brtrue.s loc_EA5B
0xea54  pop
0xea55  ldc.i4.0
0xea56  box      [mscorlib]System.Int32
0xea5b  unbox.any [mscorlib]System.Int32
0xea60  stloc.2
0xea61  leave.s  loc_EA6D
0xea63  ldloc.1
0xea64  brfalse.s loc_EA6C
0xea66  ldloc.1
0xea67  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xea6c  endfinally
0xea6d  ldloc.2
0xea6e  ret
```
