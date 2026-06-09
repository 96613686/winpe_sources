# Microsoft.Crm.Asynchronous.SqmDatabaseAccessor::CollectChartsPoints

- ea: `0x7b10`
- end: `0x7ce8`
- name: `Microsoft.Crm.Asynchronous.SqmDatabaseAccessor::CollectChartsPoints`
- size: `472`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x5350`

## callees

- `0x7b10`
- `0xefa0`

## pseudocode

```c

```

## disassembly

```asm
0x7b10  newobj   instance void <>c__DisplayClass40_0::.ctor()
0x7b15  stloc.0
0x7b16  ldloc.0
0x7b17  ldarg.0
0x7b18  stfld    class Microsoft.Crm.Asynchronous.SqmDatabaseAccessor <>c__DisplayClass40_0::<>4__this
0x7b1d  ldloc.0
0x7b1e  ldc.i4.s 0xE
0x7b20  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [Microsoft.Crm]Microsoft.Crm.SqmDataPointId, int32>::.ctor(int32)
0x7b25  stfld    class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [Microsoft.Crm]Microsoft.Crm.SqmDataPointId, int32> <>c__DisplayClass40_0::sqmDataPoints
0x7b2a  ldloc.0
0x7b2b  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [Microsoft.Crm]Microsoft.Crm.SqmDataPointId, int32> <>c__DisplayClass40_0::sqmDataPoints
0x7b30  ldc.i4   0x1FD
0x7b35  ldc.i4.0
0x7b36  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [Microsoft.Crm]Microsoft.Crm.SqmDataPointId, int32>::Add(var<u1>, !!T0)
0x7b3b  ldloc.0
0x7b3c  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [Microsoft.Crm]Microsoft.Crm.SqmDataPointId, int32> <>c__DisplayClass40_0::sqmDataPoints
0x7b41  ldc.i4   0x1FE
0x7b46  ldc.i4.0
0x7b47  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [Microsoft.Crm]Microsoft.Crm.SqmDataPointId, int32>::Add(var<u1>, !!T0)
0x7b4c  ldloc.0
0x7b4d  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [Microsoft.Crm]Microsoft.Crm.SqmDataPointId, int32> <>c__DisplayClass40_0::sqmDataPoints
0x7b52  ldc.i4   0x1FF
0x7b57  ldc.i4.0
0x7b58  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [Microsoft.Crm]Microsoft.Crm.SqmDataPointId, int32>::Add(var<u1>, !!T0)
0x7b5d  ldloc.0
0x7b5e  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [Microsoft.Crm]Microsoft.Crm.SqmDataPointId, int32> <>c__DisplayClass40_0::sqmDataPoints
0x7b63  ldc.i4   0x200
0x7b68  ldc.i4.0
0x7b69  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [Microsoft.Crm]Microsoft.Crm.SqmDataPointId, int32>::Add(var<u1>, !!T0)
0x7b6e  ldloc.0
0x7b6f  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [Microsoft.Crm]Microsoft.Crm.SqmDataPointId, int32> <>c__DisplayClass40_0::sqmDataPoints
0x7b74  ldc.i4   0x201
0x7b79  ldc.i4.0
0x7b7a  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [Microsoft.Crm]Microsoft.Crm.SqmDataPointId, int32>::Add(var<u1>, !!T0)
0x7b7f  ldloc.0
0x7b80  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [Microsoft.Crm]Microsoft.Crm.SqmDataPointId, int32> <>c__DisplayClass40_0::sqmDataPoints
0x7b85  ldc.i4   0x202
0x7b8a  ldc.i4.0
0x7b8b  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [Microsoft.Crm]Microsoft.Crm.SqmDataPointId, int32>::Add(var<u1>, !!T0)
0x7b90  ldloc.0
0x7b91  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [Microsoft.Crm]Microsoft.Crm.SqmDataPointId, int32> <>c__DisplayClass40_0::sqmDataPoints
0x7b96  ldc.i4   0x203
0x7b9b  ldc.i4.0
0x7b9c  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [Microsoft.Crm]Microsoft.Crm.SqmDataPointId, int32>::Add(var<u1>, !!T0)
0x7ba1  ldloc.0
0x7ba2  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [Microsoft.Crm]Microsoft.Crm.SqmDataPointId, int32> <>c__DisplayClass40_0::sqmDataPoints
0x7ba7  ldc.i4   0x204
0x7bac  ldc.i4.0
0x7bad  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [Microsoft.Crm]Microsoft.Crm.SqmDataPointId, int32>::Add(var<u1>, !!T0)
0x7bb2  ldloc.0
0x7bb3  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [Microsoft.Crm]Microsoft.Crm.SqmDataPointId, int32> <>c__DisplayClass40_0::sqmDataPoints
0x7bb8  ldc.i4   0x205
0x7bbd  ldc.i4.0
0x7bbe  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [Microsoft.Crm]Microsoft.Crm.SqmDataPointId, int32>::Add(var<u1>, !!T0)
0x7bc3  ldloc.0
0x7bc4  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [Microsoft.Crm]Microsoft.Crm.SqmDataPointId, int32> <>c__DisplayClass40_0::sqmDataPoints
0x7bc9  ldc.i4   0x206
0x7bce  ldc.i4.0
0x7bcf  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [Microsoft.Crm]Microsoft.Crm.SqmDataPointId, int32>::Add(var<u1>, !!T0)
0x7bd4  ldloc.0
0x7bd5  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [Microsoft.Crm]Microsoft.Crm.SqmDataPointId, int32> <>c__DisplayClass40_0::sqmDataPoints
0x7bda  ldc.i4   0x207
0x7bdf  ldc.i4.0
0x7be0  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [Microsoft.Crm]Microsoft.Crm.SqmDataPointId, int32>::Add(var<u1>, !!T0)
0x7be5  ldloc.0
0x7be6  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [Microsoft.Crm]Microsoft.Crm.SqmDataPointId, int32> <>c__DisplayClass40_0::sqmDataPoints
0x7beb  ldc.i4   0x208
0x7bf0  ldc.i4.0
0x7bf1  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [Microsoft.Crm]Microsoft.Crm.SqmDataPointId, int32>::Add(var<u1>, !!T0)
0x7bf6  ldloc.0
0x7bf7  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [Microsoft.Crm]Microsoft.Crm.SqmDataPointId, int32> <>c__DisplayClass40_0::sqmDataPoints
0x7bfc  ldc.i4   0x209
0x7c01  ldc.i4.0
0x7c02  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [Microsoft.Crm]Microsoft.Crm.SqmDataPointId, int32>::Add(var<u1>, !!T0)
0x7c07  ldloc.0
0x7c08  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [Microsoft.Crm]Microsoft.Crm.SqmDataPointId, int32> <>c__DisplayClass40_0::sqmDataPoints
0x7c0d  ldc.i4   0x20A
0x7c12  ldc.i4.0
0x7c13  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [Microsoft.Crm]Microsoft.Crm.SqmDataPointId, int32>::Add(var<u1>, !!T0)
0x7c18  ldloc.0
0x7c19  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [Microsoft.Crm]Microsoft.Crm.SqmDataPointId, int32> <>c__DisplayClass40_0::sqmDataPoints
0x7c1e  ldc.i4   0x20F
0x7c23  ldc.i4.0
0x7c24  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [Microsoft.Crm]Microsoft.Crm.SqmDataPointId, int32>::Add(var<u1>, !!T0)
0x7c29  ldloc.0
0x7c2a  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [Microsoft.Crm]Microsoft.Crm.SqmDataPointId, int32> <>c__DisplayClass40_0::sqmDataPoints
0x7c2f  ldc.i4   0x210
0x7c34  ldc.i4.0
0x7c35  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [Microsoft.Crm]Microsoft.Crm.SqmDataPointId, int32>::Add(var<u1>, !!T0)
0x7c3a  call     class [System.Data]System.Data.IDbCommand [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::NewCommand()
0x7c3f  stloc.2
0x7c40  ldloc.2
0x7c41  ldstr    aSelectDatadesc// "select DataDescription, PresentationDes"...
0x7c46  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0x7c4b  ldarg.0
0x7c4c  ldloc.2
0x7c4d  ldloc.0
0x7c4e  ldftn    instance void <>c__DisplayClass40_0::<CollectChartsPoints>b__0(object[] values)
0x7c54  newobj   instance void [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessBase/RecordProcessor::.ctor(object, native int)
0x7c59  call     instance int32 [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessBase::ExecuteSqlCommandAndProcessRecords(class [System.Data]System.Data.IDbCommand, class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessBase/RecordProcessor)
0x7c5e  stloc.1
0x7c5f  leave.s  loc_7C6B
0x7c61  ldloc.2
0x7c62  brfalse.s loc_7C6A
0x7c64  ldloc.2
0x7c65  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x7c6a  endfinally
0x7c6b  call     class [System.Data]System.Data.IDbCommand [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::NewCommand()
0x7c70  stloc.3
0x7c71  ldloc.3
0x7c72  ldstr    aSelectDatadesc_0// "select DataDescription, PresentationDes"...
0x7c77  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0x7c7c  ldloc.1
0x7c7d  ldarg.0
0x7c7e  ldloc.3
0x7c7f  ldloc.0
0x7c80  ldftn    instance void <>c__DisplayClass40_0::<CollectChartsPoints>b__1(object[] values)
0x7c86  newobj   instance void [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessBase/RecordProcessor::.ctor(object, native int)
0x7c8b  call     instance int32 [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessBase::ExecuteSqlCommandAndProcessRecords(class [System.Data]System.Data.IDbCommand, class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessBase/RecordProcessor)
0x7c90  add
0x7c91  stloc.1
0x7c92  leave.s  loc_7C9E
0x7c94  ldloc.3
0x7c95  brfalse.s loc_7C9D
0x7c97  ldloc.3
0x7c98  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x7c9d  endfinally
0x7c9e  ldloc.1
0x7c9f  brtrue.s loc_7CA2
0x7ca1  ret
0x7ca2  ldloc.0
0x7ca3  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [Microsoft.Crm]Microsoft.Crm.SqmDataPointId, int32> <>c__DisplayClass40_0::sqmDataPoints
0x7ca8  callvirt instance valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<var<u1>, !!T0> class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [Microsoft.Crm]Microsoft.Crm.SqmDataPointId, int32>::GetEnumerator()
0x7cad  stloc.s  4
0x7caf  br.s     loc_7CCE
0x7cb1  ldloca.s 4
0x7cb3  call     instance valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<var<u1>, !!T0> valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<valuetype [Microsoft.Crm]Microsoft.Crm.SqmDataPointId, int32>::get_Current()
0x7cb8  stloc.s  5
0x7cba  ldarg.1
0x7cbb  ldloca.s 5
0x7cbd  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<valuetype [Microsoft.Crm]Microsoft.Crm.SqmDataPointId, int32>::get_Key()
0x7cc2  ldloca.s 5
0x7cc4  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<valuetype [Microsoft.Crm]Microsoft.Crm.SqmDataPointId, int32>::get_Value()
0x7cc9  callvirt instance void [Microsoft.Crm]Microsoft.Crm.ISqmSession::set_Item(valuetype [Microsoft.Crm]Microsoft.Crm.SqmDataPointId, int32)
0x7cce  ldloca.s 4
0x7cd0  call     instance bool valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<valuetype [Microsoft.Crm]Microsoft.Crm.SqmDataPointId, int32>::MoveNext()
0x7cd5  brtrue.s loc_7CB1
0x7cd7  leave.s  loc_7CE7
0x7cd9  ldloca.s 4
0x7cdb  constrained. valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<valuetype [Microsoft.Crm]Microsoft.Crm.SqmDataPointId, int32>
0x7ce1  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x7ce6  endfinally
0x7ce7  ret
```
