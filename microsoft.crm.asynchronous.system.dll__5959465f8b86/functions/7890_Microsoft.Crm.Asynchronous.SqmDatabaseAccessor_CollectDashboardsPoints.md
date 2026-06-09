# Microsoft.Crm.Asynchronous.SqmDatabaseAccessor::CollectDashboardsPoints

- ea: `0x7890`
- end: `0x799a`
- name: `Microsoft.Crm.Asynchronous.SqmDatabaseAccessor::CollectDashboardsPoints`
- size: `266`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x5390`

## callees

- `0x7890`
- `0xef40`

## string_xrefs

- `0x78f3`: `select FormXml from SystemForm where Type = 0`
- `0x7924`: `select FormXml from UserForm where Type = 0`

## pseudocode

```c

```

## disassembly

```asm
0x7890  newobj   instance void <>c__DisplayClass38_0::.ctor()
0x7895  stloc.0
0x7896  ldloc.0
0x7897  ldarg.0
0x7898  stfld    class Microsoft.Crm.Asynchronous.SqmDatabaseAccessor <>c__DisplayClass38_0::<>4__this
0x789d  ldloc.0
0x789e  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [Microsoft.Crm]Microsoft.Crm.SqmDataPointId, int32>::.ctor()
0x78a3  stfld    class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [Microsoft.Crm]Microsoft.Crm.SqmDataPointId, int32> <>c__DisplayClass38_0::sqmDataPoints
0x78a8  ldloc.0
0x78a9  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [Microsoft.Crm]Microsoft.Crm.SqmDataPointId, int32> <>c__DisplayClass38_0::sqmDataPoints
0x78ae  ldc.i4   0x20B
0x78b3  ldc.i4.0
0x78b4  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [Microsoft.Crm]Microsoft.Crm.SqmDataPointId, int32>::Add(var<u1>, !!T0)
0x78b9  ldloc.0
0x78ba  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [Microsoft.Crm]Microsoft.Crm.SqmDataPointId, int32> <>c__DisplayClass38_0::sqmDataPoints
0x78bf  ldc.i4   0x20C
0x78c4  ldc.i4.0
0x78c5  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [Microsoft.Crm]Microsoft.Crm.SqmDataPointId, int32>::Add(var<u1>, !!T0)
0x78ca  ldloc.0
0x78cb  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [Microsoft.Crm]Microsoft.Crm.SqmDataPointId, int32> <>c__DisplayClass38_0::sqmDataPoints
0x78d0  ldc.i4   0x20E
0x78d5  ldc.i4.0
0x78d6  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [Microsoft.Crm]Microsoft.Crm.SqmDataPointId, int32>::Add(var<u1>, !!T0)
0x78db  ldloc.0
0x78dc  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [Microsoft.Crm]Microsoft.Crm.SqmDataPointId, int32> <>c__DisplayClass38_0::sqmDataPoints
0x78e1  ldc.i4   0x20D
0x78e6  ldc.i4.0
0x78e7  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [Microsoft.Crm]Microsoft.Crm.SqmDataPointId, int32>::Add(var<u1>, !!T0)
0x78ec  call     class [System.Data]System.Data.IDbCommand [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::NewCommand()
0x78f1  stloc.2
0x78f2  ldloc.2
0x78f3  ldstr    aSelectFormxmlF// "select FormXml from SystemForm where Ty"...
0x78f8  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0x78fd  ldarg.0
0x78fe  ldloc.2
0x78ff  ldloc.0
0x7900  ldftn    instance void <>c__DisplayClass38_0::<CollectDashboardsPoints>b__0(object[] values)
0x7906  newobj   instance void [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessBase/RecordProcessor::.ctor(object, native int)
0x790b  call     instance int32 [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessBase::ExecuteSqlCommandAndProcessRecords(class [System.Data]System.Data.IDbCommand, class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessBase/RecordProcessor)
0x7910  stloc.1
0x7911  leave.s  loc_791D
0x7913  ldloc.2
0x7914  brfalse.s loc_791C
0x7916  ldloc.2
0x7917  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x791c  endfinally
0x791d  call     class [System.Data]System.Data.IDbCommand [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::NewCommand()
0x7922  stloc.3
0x7923  ldloc.3
0x7924  ldstr    aSelectFormxmlF_0// "select FormXml from UserForm where Type"...
0x7929  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0x792e  ldloc.1
0x792f  ldarg.0
0x7930  ldloc.3
0x7931  ldloc.0
0x7932  ldftn    instance void <>c__DisplayClass38_0::<CollectDashboardsPoints>b__1(object[] values)
0x7938  newobj   instance void [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessBase/RecordProcessor::.ctor(object, native int)
0x793d  call     instance int32 [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessBase::ExecuteSqlCommandAndProcessRecords(class [System.Data]System.Data.IDbCommand, class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessBase/RecordProcessor)
0x7942  add
0x7943  stloc.1
0x7944  leave.s  loc_7950
0x7946  ldloc.3
0x7947  brfalse.s loc_794F
0x7949  ldloc.3
0x794a  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x794f  endfinally
0x7950  ldloc.1
0x7951  brtrue.s loc_7954
0x7953  ret
0x7954  ldloc.0
0x7955  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [Microsoft.Crm]Microsoft.Crm.SqmDataPointId, int32> <>c__DisplayClass38_0::sqmDataPoints
0x795a  callvirt instance valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<var<u1>, !!T0> class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [Microsoft.Crm]Microsoft.Crm.SqmDataPointId, int32>::GetEnumerator()
0x795f  stloc.s  4
0x7961  br.s     loc_7980
0x7963  ldloca.s 4
0x7965  call     instance valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<var<u1>, !!T0> valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<valuetype [Microsoft.Crm]Microsoft.Crm.SqmDataPointId, int32>::get_Current()
0x796a  stloc.s  5
0x796c  ldarg.1
0x796d  ldloca.s 5
0x796f  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<valuetype [Microsoft.Crm]Microsoft.Crm.SqmDataPointId, int32>::get_Key()
0x7974  ldloca.s 5
0x7976  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<valuetype [Microsoft.Crm]Microsoft.Crm.SqmDataPointId, int32>::get_Value()
0x797b  callvirt instance void [Microsoft.Crm]Microsoft.Crm.ISqmSession::set_Item(valuetype [Microsoft.Crm]Microsoft.Crm.SqmDataPointId, int32)
0x7980  ldloca.s 4
0x7982  call     instance bool valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<valuetype [Microsoft.Crm]Microsoft.Crm.SqmDataPointId, int32>::MoveNext()
0x7987  brtrue.s loc_7963
0x7989  leave.s  loc_7999
0x798b  ldloca.s 4
0x798d  constrained. valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<valuetype [Microsoft.Crm]Microsoft.Crm.SqmDataPointId, int32>
0x7993  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x7998  endfinally
0x7999  ret
```
