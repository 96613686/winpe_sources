# Microsoft.Crm.Asynchronous.Rollups.RollupJobModifier::ResetStateToReady

- ea: `0xe150`
- end: `0xe1ea`
- name: `Microsoft.Crm.Asynchronous.Rollups.RollupJobModifier::ResetStateToReady`
- size: `154`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callers

- `0xdf80`

## callees

- `0xdc20`
- `0xe150`
- `0xe770`
- `0x16ff0`

## string_xrefs

- `0xe173`: `UPDATE \n	[RollupJobBase] \nSET \n	[StateCode] = @readyStateCode,\n	[RetryCount] = CASE WHEN COALESCE([RetryCount], 0) > 0 THEN [RetryCount]-1 ELSE 0 END\nWHERE \n	[RollupJobId] = @rollupJobId`
- `0xe199`: `@readyStateCode`

## pseudocode

```c

```

## disassembly

```asm
0xe150  newobj   instance void <>c__DisplayClass6_0::.ctor()
0xe155  stloc.0
0xe156  ldloc.0
0xe157  ldarg.0
0xe158  stfld    class Microsoft.Crm.Asynchronous.Rollups.RollupJobModifier <>c__DisplayClass6_0::<>4__this
0xe15d  ldloc.0
0xe15e  call     class [System.Data]System.Data.IDbCommand [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::NewCommand()
0xe163  stfld    class [System.Data]System.Data.IDbCommand <>c__DisplayClass6_0::crmDbCommand
0xe168  ldloc.0
0xe169  ldfld    class [System.Data]System.Data.IDbCommand <>c__DisplayClass6_0::crmDbCommand
0xe16e  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xe173  ldstr    aUpdateRollupjo// "UPDATE \r\n\t[RollupJobBase] \r\nSET \r"...
0xe178  ldc.i4.0
0xe179  newarr   [mscorlib]System.Object
0xe17e  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xe183  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0xe188  ldloc.0
0xe189  ldfld    class [System.Data]System.Data.IDbCommand <>c__DisplayClass6_0::crmDbCommand
0xe18e  callvirt instance class [System.Data]System.Data.IDataParameterCollection [System.Data]System.Data.IDbCommand::get_Parameters()
0xe193  castclass [System.Data]System.Data.SqlClient.SqlParameterCollection
0xe198  dup
0xe199  ldstr    aReadystatecode// "@readyStateCode"
0xe19e  ldc.i4.0
0xe19f  box      [Microsoft.Crm.Sdk.Reserved]Microsoft.Crm.Sdk.Types.RollupJobState
0xe1a4  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0xe1a9  pop
0xe1aa  ldstr    aRollupjobid_0// "@rollupJobId"
0xe1af  ldarg.1
0xe1b0  callvirt instance int64 Microsoft.Crm.Asynchronous.Rollups.RollupJob::get_RollupJobId()
0xe1b5  box      [mscorlib]System.Int64
0xe1ba  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0xe1bf  pop
0xe1c0  ldloc.0
0xe1c1  ldftn    instance valuetype Microsoft.Crm.Asynchronous.Rollups.SqlCommandResult <>c__DisplayClass6_0::<ResetStateToReady>b__0()
0xe1c7  newobj   instance void class [mscorlib]System.Func`1<valuetype Microsoft.Crm.Asynchronous.Rollups.SqlCommandResult>::.ctor(object, native int)
0xe1cc  call     valuetype Microsoft.Crm.Asynchronous.Rollups.SqlCommandResult Microsoft.Crm.Asynchronous.Rollups.SqlErrorCodes::WrapSqlException(class [mscorlib]System.Func`1<valuetype Microsoft.Crm.Asynchronous.Rollups.SqlCommandResult> sqlFunc)
0xe1d1  stloc.1
0xe1d2  leave.s  loc_E1E8
0xe1d4  ldloc.0
0xe1d5  ldfld    class [System.Data]System.Data.IDbCommand <>c__DisplayClass6_0::crmDbCommand
0xe1da  brfalse.s loc_E1E7
0xe1dc  ldloc.0
0xe1dd  ldfld    class [System.Data]System.Data.IDbCommand <>c__DisplayClass6_0::crmDbCommand
0xe1e2  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xe1e7  endfinally
0xe1e8  ldloc.1
0xe1e9  ret
```
