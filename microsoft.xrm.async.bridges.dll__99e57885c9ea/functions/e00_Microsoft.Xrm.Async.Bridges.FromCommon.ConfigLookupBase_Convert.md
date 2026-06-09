# Microsoft.Xrm.Async.Bridges.FromCommon.ConfigLookupBase::Convert

- ea: `0xe00`
- end: `0xe3e`
- name: `Microsoft.Xrm.Async.Bridges.FromCommon.ConfigLookupBase::Convert`
- size: `62`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0xd10`

## callees

- `0xe00`

## pseudocode

```c

```

## disassembly

```asm
0xe00  ldarg.2
0xe01  ldtoken  [mscorlib]System.String
0xe06  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xe0b  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0xe10  brfalse.s loc_E14
0xe12  ldarg.1
0xe13  ret
0xe14  ldarg.2
0xe15  callvirt instance bool [mscorlib]System.Type::get_IsEnum()
0xe1a  brfalse.s loc_E25
0xe1c  ldarg.2
0xe1d  ldarg.1
0xe1e  ldc.i4.1
0xe1f  call     object [mscorlib]System.Enum::Parse(class [mscorlib]System.Type, string, bool)
0xe24  ret
0xe25  ldsfld   class [mscorlib]System.Collections.Generic.IReadOnlyDictionary`2<class [mscorlib]System.Type, class [mscorlib]System.Func`2<string, object>> Microsoft.Xrm.Async.Bridges.FromCommon.ConfigLookupBase::converters
0xe2a  ldarg.2
0xe2b  ldloca.s 0
0xe2d  callvirt instance bool class [mscorlib]System.Collections.Generic.IReadOnlyDictionary`2<class [mscorlib]System.Type, class [mscorlib]System.Func`2<string, object>>::TryGetValue(var<u1>, !!T0)
0xe32  brfalse.s loc_E3C
0xe34  ldloc.0
0xe35  ldarg.1
0xe36  callvirt instance var<u1> class [mscorlib]System.Func`2<string, object>::Invoke(void)
0xe3b  ret
0xe3c  ldnull
0xe3d  ret
```
