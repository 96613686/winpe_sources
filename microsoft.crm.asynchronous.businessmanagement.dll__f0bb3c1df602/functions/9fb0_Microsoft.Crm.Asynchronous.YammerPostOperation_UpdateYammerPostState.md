# Microsoft.Crm.Asynchronous.YammerPostOperation::UpdateYammerPostState

- ea: `0x9fb0`
- end: `0xa177`
- name: `Microsoft.Crm.Asynchronous.YammerPostOperation::UpdateYammerPostState`
- size: `455`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callers

- `0x9450`
- `0x9610`

## callees

- `0x9fb0`

## string_xrefs

- `0x9fca`: `UpdateYammerPostState`
- `0xa146`: `UpdateYammerPostState`
- `0xa00f`: `UPDATE {1}  SET [YammerPostState]=@YammerState  WHERE {2} IN ({0})`
- `0xa01b`: `UPDATE {1}  SET [YammerPostState]=CASE WHEN ((ISNULL([YammerRetryCount],0)+1) >= @MaxRetryCount) THEN  @YammerState ELSE [YammerPostState] END, [YammerRetryCount]=(ISNULL([YammerRetryCount],0)+1) WHERE {2} IN ({0})`

## pseudocode

```c

```

## disassembly

```asm
0x9fb0  ldarg.2
0x9fb1  ldstr    aActivities// "activities"
0x9fb6  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x9fbb  ldarg.2
0x9fbc  call     T0x2B00001D
0x9fc1  brtrue.s loc_9FC4
0x9fc3  ret
0x9fc4  ldarg.0
0x9fc5  ldfld    class [Microsoft.Crm.Core]Microsoft.Crm.CounterList Microsoft.Crm.Asynchronous.YammerPostOperation::_listCounters
0x9fca  ldstr    aUpdateyammerpo_0// "UpdateYammerPostState"
0x9fcf  ldc.i4.1
0x9fd0  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.CounterList [Microsoft.Crm.Core]Microsoft.Crm.CounterList::InitStepListCounter(string, bool)
0x9fd5  stloc.0
0x9fd6  ldarg.0
0x9fd7  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.YammerPostOperation::_organizationId
0x9fdc  ldc.i4.0
0x9fdd  ldc.i4.0
0x9fde  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::.ctor(valuetype [mscorlib]System.Guid, bool, valuetype [Microsoft.Crm.Core]Microsoft.Crm.ReadPriority)
0x9fe3  stloc.1
0x9fe4  ldloc.1
0x9fe5  callvirt instance class [System.Data]System.Data.IDbCommand [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::CreateCommand()
0x9fea  stloc.2
0x9feb  ldloc.1
0x9fec  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::Open()
0x9ff1  ldnull
0x9ff2  stloc.3
0x9ff3  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor()
0x9ff8  stloc.s  4
0x9ffa  ldloc.2
0x9ffb  callvirt instance class [System.Data]System.Data.IDataParameterCollection [System.Data]System.Data.IDbCommand::get_Parameters()
0xa000  castclass [System.Data]System.Data.SqlClient.SqlParameterCollection
0xa005  stloc.s  5
0xa007  ldarg.1
0xa008  ldc.i4.1
0xa009  beq.s    loc_A00F
0xa00b  ldarg.1
0xa00c  ldc.i4.3
0xa00d  bne.un.s loc_A017
0xa00f  ldstr    aUpdate1SetYamm// "UPDATE {1}  SET [YammerPostState]=@Yamm"...
0xa014  stloc.3
0xa015  br.s     loc_A039
0xa017  ldarg.1
0xa018  ldc.i4.2
0xa019  bne.un.s loc_A039
0xa01b  ldstr    aUpdate1SetYamm_0// "UPDATE {1}  SET [YammerPostState]=CASE "...
0xa020  stloc.3
0xa021  ldloc.s  5
0xa023  ldstr    aMaxretrycount// "@MaxRetryCount"
0xa028  ldarg.0
0xa029  ldfld    int32 Microsoft.Crm.Asynchronous.YammerPostOperation::_maxYammerPostsRetryCount
0xa02e  box      [mscorlib]System.Int32
0xa033  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0xa038  pop
0xa039  ldloc.s  5
0xa03b  ldstr    aYammerstate// "@YammerState"
0xa040  ldarg.1
0xa041  box      [mscorlib]System.Int32
0xa046  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0xa04b  pop
0xa04c  ldc.i4.0
0xa04d  stloc.s  6
0xa04f  ldarg.2
0xa050  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.Crm.YammerIntegration]Microsoft.Crm.YammerIntegration.YammerActivity>::GetEnumerator()
0xa055  stloc.s  8
0xa057  br.s     loc_A0B3
0xa059  ldloc.s  8
0xa05b  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.Crm.YammerIntegration]Microsoft.Crm.YammerIntegration.YammerActivity>::get_Current()
0xa060  stloc.s  9
0xa062  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xa067  ldstr    aPostid0_0// "@postid{0}"
0xa06c  ldc.i4.1
0xa06d  newarr   [mscorlib]System.Object
0xa072  dup
0xa073  ldc.i4.0
0xa074  ldloc.s  6
0xa076  box      [mscorlib]System.Int32
0xa07b  stelem.ref
0xa07c  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xa081  stloc.s  0xA
0xa083  ldloc.s  4
0xa085  ldloc.s  0xA
0xa087  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0xa08c  pop
0xa08d  ldloc.s  4
0xa08f  ldc.i4.s 0x2C
0xa091  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(char)
0xa096  pop
0xa097  ldloc.s  5
0xa099  ldloc.s  0xA
0xa09b  ldloc.s  9
0xa09d  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.YammerIntegration]Microsoft.Crm.YammerIntegration.YammerActivity::get_Id()
0xa0a2  box      [mscorlib]System.Guid
0xa0a7  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0xa0ac  pop
0xa0ad  ldloc.s  6
0xa0af  ldc.i4.1
0xa0b0  add
0xa0b1  stloc.s  6
0xa0b3  ldloc.s  8
0xa0b5  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0xa0ba  brtrue.s loc_A059
0xa0bc  leave.s  loc_A0CA
0xa0be  ldloc.s  8
0xa0c0  brfalse.s loc_A0C9
0xa0c2  ldloc.s  8
0xa0c4  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xa0c9  endfinally
0xa0ca  ldloc.s  4
0xa0cc  callvirt instance string [mscorlib]System.Object::ToString()
0xa0d1  ldc.i4.1
0xa0d2  newarr   [mscorlib]System.Char
0xa0d7  dup
0xa0d8  ldc.i4.0
0xa0d9  ldc.i4.s 0x2C
0xa0db  stelem.i2
0xa0dc  callvirt instance string [mscorlib]System.String::TrimEnd(char[])
0xa0e1  stloc.s  7
0xa0e3  ldarg.3
0xa0e4  brfalse.s loc_A114
0xa0e6  ldloc.2
0xa0e7  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xa0ec  ldloc.3
0xa0ed  ldc.i4.3
0xa0ee  newarr   [mscorlib]System.Object
0xa0f3  dup
0xa0f4  ldc.i4.0
0xa0f5  ldloc.s  7
0xa0f7  stelem.ref
0xa0f8  dup
0xa0f9  ldc.i4.1
0xa0fa  ldstr    aPostfollowbase// "PostFollowBase"
0xa0ff  stelem.ref
0xa100  dup
0xa101  ldc.i4.2
0xa102  ldstr    aPostfollowid// "PostFollowId"
0xa107  stelem.ref
0xa108  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xa10d  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0xa112  br.s     loc_A140
0xa114  ldloc.2
0xa115  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xa11a  ldloc.3
0xa11b  ldc.i4.3
0xa11c  newarr   [mscorlib]System.Object
0xa121  dup
0xa122  ldc.i4.0
0xa123  ldloc.s  7
0xa125  stelem.ref
0xa126  dup
0xa127  ldc.i4.1
0xa128  ldstr    aPostbase// "PostBase"
0xa12d  stelem.ref
0xa12e  dup
0xa12f  ldc.i4.2
0xa130  ldstr    aPostid_0// "PostId"
0xa135  stelem.ref
0xa136  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xa13b  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0xa140  ldloc.2
0xa141  ldc.i4   0x3B9
0xa146  ldstr    aUpdateyammerpo_0// "UpdateYammerPostState"
0xa14b  ldstr    aDDbsShDccm2110_2// "d:\\dbs\\sh\\dccm2\\1101_190851\\cmd\\7"...
0xa150  call     int32 [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::ExecuteNonQuery(class [System.Data]System.Data.IDbCommand, int32, string, string)
0xa155  pop
0xa156  leave.s  loc_A176
0xa158  ldloc.2
0xa159  brfalse.s loc_A161
0xa15b  ldloc.2
0xa15c  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xa161  endfinally
0xa162  ldloc.1
0xa163  brfalse.s loc_A16B
0xa165  ldloc.1
0xa166  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xa16b  endfinally
0xa16c  ldloc.0
0xa16d  brfalse.s loc_A175
0xa16f  ldloc.0
0xa170  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xa175  endfinally
0xa176  ret
```
