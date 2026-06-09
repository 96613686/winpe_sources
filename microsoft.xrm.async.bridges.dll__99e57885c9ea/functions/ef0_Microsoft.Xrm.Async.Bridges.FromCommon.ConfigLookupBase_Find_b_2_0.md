# Microsoft.Xrm.Async.Bridges.FromCommon.ConfigLookupBase::<Find>b__2_0

- ea: `0xef0`
- end: `0xf07`
- name: `Microsoft.Xrm.Async.Bridges.FromCommon.ConfigLookupBase::<Find>b__2_0`
- size: `23`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callees

- `0xdd0`
- `0xef0`

## pseudocode

```c

```

## disassembly

```asm
0xef0  ldarg.1
0xef1  callvirt instance bool [mscorlib]System.Reflection.PropertyInfo::get_CanWrite()
0xef6  brfalse.s loc_F05
0xef8  ldarg.0
0xef9  ldarg.1
0xefa  callvirt instance class [mscorlib]System.Type [mscorlib]System.Reflection.PropertyInfo::get_PropertyType()
0xeff  callvirt instance bool Microsoft.Xrm.Async.Bridges.FromCommon.ConfigLookupBase::IsSupportedType(class [mscorlib]System.Type type)
0xf04  ret
0xf05  ldc.i4.0
0xf06  ret
```
