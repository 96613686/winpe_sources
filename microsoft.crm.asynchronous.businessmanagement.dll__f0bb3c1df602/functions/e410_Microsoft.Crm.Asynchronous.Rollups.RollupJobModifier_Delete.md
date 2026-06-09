# Microsoft.Crm.Asynchronous.Rollups.RollupJobModifier::Delete

- ea: `0xe410`
- end: `0xe498`
- name: `Microsoft.Crm.Asynchronous.Rollups.RollupJobModifier::Delete`
- size: `136`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callers

- `0xe0a0`

## callees

- `0xdc20`
- `0xe410`
- `0xe770`
- `0x170b0`

## string_xrefs

- `0xe433`: `DELETE FROM \n	[RollupJobBase]\nWHERE \n	[RollupJobId] = @rollupJobId`

## pseudocode

```c

```

## disassembly

```asm
0xe410  newobj   instance void <>c__DisplayClass9_0::.ctor()
0xe415  stloc.0
0xe416  ldloc.0
0xe417  ldarg.0
0xe418  stfld    class Microsoft.Crm.Asynchronous.Rollups.RollupJobModifier <>c__DisplayClass9_0::<>4__this
0xe41d  ldloc.0
0xe41e  call     class [System.Data]System.Data.IDbCommand [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::NewCommand()
0xe423  stfld    class [System.Data]System.Data.IDbCommand <>c__DisplayClass9_0::crmDbCommand
0xe428  ldloc.0
0xe429  ldfld    class [System.Data]System.Data.IDbCommand <>c__DisplayClass9_0::crmDbCommand
0xe42e  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xe433  ldstr    aDeleteFromRoll// "DELETE FROM \r\n\t[RollupJobBase]\r\nWH"...
0xe438  ldc.i4.0
0xe439  newarr   [mscorlib]System.Object
0xe43e  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xe443  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0xe448  ldloc.0
0xe449  ldfld    class [System.Data]System.Data.IDbCommand <>c__DisplayClass9_0::crmDbCommand
0xe44e  callvirt instance class [System.Data]System.Data.IDataParameterCollection [System.Data]System.Data.IDbCommand::get_Parameters()
0xe453  castclass [System.Data]System.Data.SqlClient.SqlParameterCollection
0xe458  ldstr    aRollupjobid_0// "@rollupJobId"
0xe45d  ldarg.1
0xe45e  callvirt instance int64 Microsoft.Crm.Asynchronous.Rollups.RollupJob::get_RollupJobId()
0xe463  box      [mscorlib]System.Int64
0xe468  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0xe46d  pop
0xe46e  ldloc.0
0xe46f  ldftn    instance valuetype Microsoft.Crm.Asynchronous.Rollups.SqlCommandResult <>c__DisplayClass9_0::<Delete>b__0()
0xe475  newobj   instance void class [mscorlib]System.Func`1<valuetype Microsoft.Crm.Asynchronous.Rollups.SqlCommandResult>::.ctor(object, native int)
0xe47a  call     valuetype Microsoft.Crm.Asynchronous.Rollups.SqlCommandResult Microsoft.Crm.Asynchronous.Rollups.SqlErrorCodes::WrapSqlException(class [mscorlib]System.Func`1<valuetype Microsoft.Crm.Asynchronous.Rollups.SqlCommandResult> sqlFunc)
0xe47f  stloc.1
0xe480  leave.s  loc_E496
0xe482  ldloc.0
0xe483  ldfld    class [System.Data]System.Data.IDbCommand <>c__DisplayClass9_0::crmDbCommand
0xe488  brfalse.s loc_E495
0xe48a  ldloc.0
0xe48b  ldfld    class [System.Data]System.Data.IDbCommand <>c__DisplayClass9_0::crmDbCommand
0xe490  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xe495  endfinally
0xe496  ldloc.1
0xe497  ret
```
