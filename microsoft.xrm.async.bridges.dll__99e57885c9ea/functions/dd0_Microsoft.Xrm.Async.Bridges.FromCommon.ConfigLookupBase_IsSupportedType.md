# Microsoft.Xrm.Async.Bridges.FromCommon.ConfigLookupBase::IsSupportedType

- ea: `0xdd0`
- end: `0xdf8`
- name: `Microsoft.Xrm.Async.Bridges.FromCommon.ConfigLookupBase::IsSupportedType`
- size: `40`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0xef0`

## callees

- `0xdd0`

## pseudocode

```c

```

## disassembly

```asm
0xdd0  ldarg.1
0xdd1  callvirt instance bool [mscorlib]System.Type::get_IsEnum()
0xdd6  brtrue.s loc_DF6
0xdd8  ldarg.1
0xdd9  ldtoken  [mscorlib]System.String
0xdde  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xde3  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0xde8  brtrue.s loc_DF6
0xdea  ldsfld   class [mscorlib]System.Collections.Generic.IReadOnlyDictionary`2<class [mscorlib]System.Type, class [mscorlib]System.Func`2<string, object>> Microsoft.Xrm.Async.Bridges.FromCommon.ConfigLookupBase::converters
0xdef  ldarg.1
0xdf0  callvirt instance bool class [mscorlib]System.Collections.Generic.IReadOnlyDictionary`2<class [mscorlib]System.Type, class [mscorlib]System.Func`2<string, object>>::ContainsKey(var<u1>)
0xdf5  ret
0xdf6  ldc.i4.1
0xdf7  ret
```
