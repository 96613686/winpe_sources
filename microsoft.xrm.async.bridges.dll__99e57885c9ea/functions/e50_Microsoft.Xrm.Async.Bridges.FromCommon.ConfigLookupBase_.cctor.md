# Microsoft.Xrm.Async.Bridges.FromCommon.ConfigLookupBase::.cctor

- ea: `0xe50`
- end: `0xee8`
- name: `Microsoft.Xrm.Async.Bridges.FromCommon.ConfigLookupBase::.cctor`
- size: `152`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config, broker_com_uri`

## pseudocode

```c

```

## disassembly

```asm
0xe50  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<class [mscorlib]System.Type, class [mscorlib]System.Func`2<string, object>>::.ctor()
0xe55  ldtoken  [mscorlib]System.Int32
0xe5a  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xe5f  stloc.0
0xe60  dup
0xe61  ldloc.0
0xe62  ldsfld   class <>c <>c::<>9
0xe67  ldftn    instance object <>c::<.cctor>b__7_0(string value)
0xe6d  newobj   instance void class [mscorlib]System.Func`2<string, object>::.ctor(object, native int)
0xe72  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<class [mscorlib]System.Type, class [mscorlib]System.Func`2<string, object>>::set_Item(var<u1>, !!T0)
0xe77  ldtoken  [mscorlib]System.Boolean
0xe7c  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xe81  stloc.1
0xe82  dup
0xe83  ldloc.1
0xe84  ldsfld   class <>c <>c::<>9
0xe89  ldftn    instance object <>c::<.cctor>b__7_1(string value)
0xe8f  newobj   instance void class [mscorlib]System.Func`2<string, object>::.ctor(object, native int)
0xe94  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<class [mscorlib]System.Type, class [mscorlib]System.Func`2<string, object>>::set_Item(var<u1>, !!T0)
0xe99  ldtoken  [System]System.Uri
0xe9e  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xea3  stloc.2
0xea4  dup
0xea5  ldloc.2
0xea6  ldsfld   class <>c <>c::<>9
0xeab  ldftn    instance object <>c::<.cctor>b__7_2(string value)
0xeb1  newobj   instance void class [mscorlib]System.Func`2<string, object>::.ctor(object, native int)
0xeb6  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<class [mscorlib]System.Type, class [mscorlib]System.Func`2<string, object>>::set_Item(var<u1>, !!T0)
0xebb  ldtoken  [mscorlib]System.Guid
0xec0  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xec5  stloc.3
0xec6  dup
0xec7  ldloc.3
0xec8  ldsfld   class <>c <>c::<>9
0xecd  ldftn    instance object <>c::<.cctor>b__7_3(string value)
0xed3  newobj   instance void class [mscorlib]System.Func`2<string, object>::.ctor(object, native int)
0xed8  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<class [mscorlib]System.Type, class [mscorlib]System.Func`2<string, object>>::set_Item(var<u1>, !!T0)
0xedd  newobj   instance void class [mscorlib]System.Collections.ObjectModel.ReadOnlyDictionary`2<class [mscorlib]System.Type, class [mscorlib]System.Func`2<string, object>>::.ctor(class [mscorlib]System.Collections.Generic.IDictionary`2<var<u1>, !!T0>)
0xee2  stsfld   class [mscorlib]System.Collections.Generic.IReadOnlyDictionary`2<class [mscorlib]System.Type, class [mscorlib]System.Func`2<string, object>> Microsoft.Xrm.Async.Bridges.FromCommon.ConfigLookupBase::converters
0xee7  ret
```
