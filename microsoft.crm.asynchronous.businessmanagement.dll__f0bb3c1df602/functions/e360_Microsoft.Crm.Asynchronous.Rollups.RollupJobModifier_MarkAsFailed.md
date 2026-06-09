# Microsoft.Crm.Asynchronous.Rollups.RollupJobModifier::MarkAsFailed

- ea: `0xe360`
- end: `0xe40d`
- name: `Microsoft.Crm.Asynchronous.Rollups.RollupJobModifier::MarkAsFailed`
- size: `173`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callers

- `0xe080`

## callees

- `0xdc20`
- `0xe360`
- `0xe770`
- `0x17070`

## string_xrefs

- `0xe383`: `UPDATE \n	[RollupJobBase] \nSET \n	[StateCode] = @completedState, \n	[StatusCode] = @failedStatus \nWHERE \n	[RollupJobId] = @rollupJobId`
- `0xe3c0`: `@completedState`

## pseudocode

```c

```

## disassembly

```asm
0xe360  newobj   instance void <>c__DisplayClass8_0::.ctor()
0xe365  stloc.0
0xe366  ldloc.0
0xe367  ldarg.0
0xe368  stfld    class Microsoft.Crm.Asynchronous.Rollups.RollupJobModifier <>c__DisplayClass8_0::<>4__this
0xe36d  ldloc.0
0xe36e  call     class [System.Data]System.Data.IDbCommand [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::NewCommand()
0xe373  stfld    class [System.Data]System.Data.IDbCommand <>c__DisplayClass8_0::crmDbCommand
0xe378  ldloc.0
0xe379  ldfld    class [System.Data]System.Data.IDbCommand <>c__DisplayClass8_0::crmDbCommand
0xe37e  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xe383  ldstr    aUpdateRollupjo_1// "UPDATE \r\n\t[RollupJobBase] \r\nSET \r"...
0xe388  ldc.i4.0
0xe389  newarr   [mscorlib]System.Object
0xe38e  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xe393  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0xe398  ldloc.0
0xe399  ldfld    class [System.Data]System.Data.IDbCommand <>c__DisplayClass8_0::crmDbCommand
0xe39e  callvirt instance class [System.Data]System.Data.IDataParameterCollection [System.Data]System.Data.IDbCommand::get_Parameters()
0xe3a3  castclass [System.Data]System.Data.SqlClient.SqlParameterCollection
0xe3a8  dup
0xe3a9  ldstr    aRollupjobid_0// "@rollupJobId"
0xe3ae  ldarg.1
0xe3af  callvirt instance int64 Microsoft.Crm.Asynchronous.Rollups.RollupJob::get_RollupJobId()
0xe3b4  box      [mscorlib]System.Int64
0xe3b9  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0xe3be  pop
0xe3bf  dup
0xe3c0  ldstr    aCompletedstate// "@completedState"
0xe3c5  ldc.i4.3
0xe3c6  box      [Microsoft.Crm.Sdk.Reserved]Microsoft.Crm.Sdk.Types.RollupJobState
0xe3cb  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0xe3d0  pop
0xe3d1  ldstr    aFailedstatus// "@failedStatus"
0xe3d6  ldc.i4.s 0x1F
0xe3d8  box      [mscorlib]System.Int32
0xe3dd  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0xe3e2  pop
0xe3e3  ldloc.0
0xe3e4  ldftn    instance valuetype Microsoft.Crm.Asynchronous.Rollups.SqlCommandResult <>c__DisplayClass8_0::<MarkAsFailed>b__0()
0xe3ea  newobj   instance void class [mscorlib]System.Func`1<valuetype Microsoft.Crm.Asynchronous.Rollups.SqlCommandResult>::.ctor(object, native int)
0xe3ef  call     valuetype Microsoft.Crm.Asynchronous.Rollups.SqlCommandResult Microsoft.Crm.Asynchronous.Rollups.SqlErrorCodes::WrapSqlException(class [mscorlib]System.Func`1<valuetype Microsoft.Crm.Asynchronous.Rollups.SqlCommandResult> sqlFunc)
0xe3f4  stloc.1
0xe3f5  leave.s  loc_E40B
0xe3f7  ldloc.0
0xe3f8  ldfld    class [System.Data]System.Data.IDbCommand <>c__DisplayClass8_0::crmDbCommand
0xe3fd  brfalse.s loc_E40A
0xe3ff  ldloc.0
0xe400  ldfld    class [System.Data]System.Data.IDbCommand <>c__DisplayClass8_0::crmDbCommand
0xe405  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xe40a  endfinally
0xe40b  ldloc.1
0xe40c  ret
```
