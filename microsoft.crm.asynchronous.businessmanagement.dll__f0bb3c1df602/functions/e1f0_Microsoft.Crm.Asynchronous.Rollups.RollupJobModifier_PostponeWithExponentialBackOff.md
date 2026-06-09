# Microsoft.Crm.Asynchronous.Rollups.RollupJobModifier::PostponeWithExponentialBackOff

- ea: `0xe1f0`
- end: `0xe352`
- name: `Microsoft.Crm.Asynchronous.Rollups.RollupJobModifier::PostponeWithExponentialBackOff`
- size: `354`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `installer_update, broker_com_uri`

## callers

- `0xdfe0`

## callees

- `0xc8b0`
- `0xc930`
- `0xdc20`
- `0xdc60`
- `0xdce0`
- `0xdd00`
- `0xdd40`
- `0xdd60`
- `0xddb0`
- `0xe1f0`
- `0xe770`
- `0x17030`

## string_xrefs

- `0xe2af`: `@readyStateCode`
- `0xe288`: `UPDATE \n	[RollupJobBase] \nSET \n	[StateCode] = @readyStateCode,\n	[PostponeUntil] = @postponeUntilUtc, \n	[RegardingObjectId] = @newRegardingObjectId,\n	[RetryCount] = @retryCount,\n	[DepthProcessed] = @depthProcessed\nWHERE \n	[RollupJobId] = @rollupJobId`

## pseudocode

```c

```

## disassembly

```asm
0xe1f0  ldarg.1
0xe1f1  callvirt instance int32 Microsoft.Crm.Asynchronous.Rollups.RollupJob::get_RetryCount()
0xe1f6  stloc.0
0xe1f7  ldarg.1
0xe1f8  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.Rollups.RollupJob::get_RegardingObjectId()
0xe1fd  stloc.1
0xe1fe  ldarg.1
0xe1ff  callvirt instance int32 Microsoft.Crm.Asynchronous.Rollups.RollupJob::get_DepthProcessed()
0xe204  stloc.2
0xe205  ldarg.1
0xe206  callvirt instance bool Microsoft.Crm.Asynchronous.Rollups.RollupJob::get_ShouldRegardingObjectIdChange()
0xe20b  brfalse.s loc_E226
0xe20d  ldc.i4.1
0xe20e  stloc.0
0xe20f  ldarg.1
0xe210  callvirt instance valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid> Microsoft.Crm.Asynchronous.Rollups.RollupJob::get_NewRegardingObjectId()
0xe215  stloc.s  6
0xe217  ldloca.s 6
0xe219  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::get_Value()
0xe21e  stloc.1
0xe21f  ldarg.1
0xe220  callvirt instance int32 Microsoft.Crm.Asynchronous.Rollups.RollupJob::get_CurrentDepthProcessed()
0xe225  stloc.2
0xe226  call     valuetype [mscorlib]System.TimeSpan Microsoft.Crm.Asynchronous.Rollups.RollupConfiguration::get_IncrementalRollupFailurePostponeInterval()
0xe22b  stloc.3
0xe22c  call     float64 Microsoft.Crm.Asynchronous.Rollups.RollupConfiguration::get_IncrementalRollupFailureBackOffFactor()
0xe231  stloc.s  4
0xe233  ldloca.s 3
0xe235  call     instance int32 [mscorlib]System.TimeSpan::get_Minutes()
0xe23a  conv.r8
0xe23b  ldloc.s  4
0xe23d  ldloc.0
0xe23e  conv.r8
0xe23f  call     float64 [mscorlib]System.Math::Pow(float64, float64)
0xe244  mul
0xe245  conv.i4
0xe246  stloc.s  5
0xe248  ldarg.2
0xe249  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_UtcNow()
0xe24e  ldc.i4.0
0xe24f  ldloc.s  5
0xe251  ldc.i4.0
0xe252  newobj   instance void [mscorlib]System.TimeSpan::.ctor(int32, int32, int32)
0xe257  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::op_Addition(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.TimeSpan)
0xe25c  stobj    [mscorlib]System.DateTime
0xe261  newobj   instance void <>c__DisplayClass7_0::.ctor()
0xe266  stloc.s  7
0xe268  ldloc.s  7
0xe26a  ldarg.0
0xe26b  stfld    class Microsoft.Crm.Asynchronous.Rollups.RollupJobModifier <>c__DisplayClass7_0::<>4__this
0xe270  ldloc.s  7
0xe272  call     class [System.Data]System.Data.IDbCommand [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::NewCommand()
0xe277  stfld    class [System.Data]System.Data.IDbCommand <>c__DisplayClass7_0::crmDbCommand
0xe27c  ldloc.s  7
0xe27e  ldfld    class [System.Data]System.Data.IDbCommand <>c__DisplayClass7_0::crmDbCommand
0xe283  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xe288  ldstr    aUpdateRollupjo_0// "UPDATE \r\n\t[RollupJobBase] \r\nSET \r"...
0xe28d  ldc.i4.0
0xe28e  newarr   [mscorlib]System.Object
0xe293  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xe298  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0xe29d  ldloc.s  7
0xe29f  ldfld    class [System.Data]System.Data.IDbCommand <>c__DisplayClass7_0::crmDbCommand
0xe2a4  callvirt instance class [System.Data]System.Data.IDataParameterCollection [System.Data]System.Data.IDbCommand::get_Parameters()
0xe2a9  castclass [System.Data]System.Data.SqlClient.SqlParameterCollection
0xe2ae  dup
0xe2af  ldstr    aReadystatecode// "@readyStateCode"
0xe2b4  ldc.i4.0
0xe2b5  box      [Microsoft.Crm.Sdk.Reserved]Microsoft.Crm.Sdk.Types.RollupJobState
0xe2ba  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0xe2bf  pop
0xe2c0  dup
0xe2c1  ldstr    aPostponeuntilu// "@postponeUntilUtc"
0xe2c6  ldarg.2
0xe2c7  ldobj    [mscorlib]System.DateTime
0xe2cc  box      [mscorlib]System.DateTime
0xe2d1  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0xe2d6  pop
0xe2d7  dup
0xe2d8  ldstr    aRollupjobid_0// "@rollupJobId"
0xe2dd  ldarg.1
0xe2de  callvirt instance int64 Microsoft.Crm.Asynchronous.Rollups.RollupJob::get_RollupJobId()
0xe2e3  box      [mscorlib]System.Int64
0xe2e8  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0xe2ed  pop
0xe2ee  dup
0xe2ef  ldstr    aNewregardingob// "@newRegardingObjectId"
0xe2f4  ldloc.1
0xe2f5  box      [mscorlib]System.Guid
0xe2fa  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0xe2ff  pop
0xe300  dup
0xe301  ldstr    aRetrycount// "@retryCount"
0xe306  ldloc.0
0xe307  box      [mscorlib]System.Int32
0xe30c  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0xe311  pop
0xe312  ldstr    aDepthprocessed_0// "@depthProcessed"
0xe317  ldloc.2
0xe318  box      [mscorlib]System.Int32
0xe31d  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0xe322  pop
0xe323  ldloc.s  7
0xe325  ldftn    instance valuetype Microsoft.Crm.Asynchronous.Rollups.SqlCommandResult <>c__DisplayClass7_0::<PostponeWithExponentialBackOff>b__0()
0xe32b  newobj   instance void class [mscorlib]System.Func`1<valuetype Microsoft.Crm.Asynchronous.Rollups.SqlCommandResult>::.ctor(object, native int)
0xe330  call     valuetype Microsoft.Crm.Asynchronous.Rollups.SqlCommandResult Microsoft.Crm.Asynchronous.Rollups.SqlErrorCodes::WrapSqlException(class [mscorlib]System.Func`1<valuetype Microsoft.Crm.Asynchronous.Rollups.SqlCommandResult> sqlFunc)
0xe335  stloc.s  8
0xe337  leave.s  loc_E34F
0xe339  ldloc.s  7
0xe33b  ldfld    class [System.Data]System.Data.IDbCommand <>c__DisplayClass7_0::crmDbCommand
0xe340  brfalse.s loc_E34E
0xe342  ldloc.s  7
0xe344  ldfld    class [System.Data]System.Data.IDbCommand <>c__DisplayClass7_0::crmDbCommand
0xe349  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xe34e  endfinally
0xe34f  ldloc.s  8
0xe351  ret
```
