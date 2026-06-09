# Microsoft.Crm.LocatorCacheKey::GetKeyType

- ea: `0x4030`
- end: `0x4057`
- name: `Microsoft.Crm.LocatorCacheKey::GetKeyType`
- size: `39`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x3760`
- `0x3e60`
- `0x258d0`

## callees

- `0x4030`
- `0x4060`

## string_xrefs

- `0x4031`: `CrmConfigDb:Full:`
- `0x4041`: `CrmConfigDb:Full:`

## pseudocode

```c

```

## disassembly

```asm
0x4030  ldarg.0
0x4031  ldstr    aCrmconfigdbFul// "CrmConfigDb:Full:"
0x4036  ldc.i4.5
0x4037  callvirt instance bool [mscorlib]System.String::StartsWith(string, valuetype [mscorlib]System.StringComparison)
0x403c  brfalse.s loc_4040
0x403e  ldc.i4.1
0x403f  ret
0x4040  ldarg.0
0x4041  ldstr    aCrmconfigdbFul// "CrmConfigDb:Full:"
0x4046  ldc.i4.5
0x4047  callvirt instance bool [mscorlib]System.String::StartsWith(string, valuetype [mscorlib]System.StringComparison)
0x404c  brfalse.s loc_4050
0x404e  ldc.i4.2
0x404f  ret
0x4050  ldarg.0
0x4051  call     valuetype Microsoft.Crm.LocatorKeyType Microsoft.Crm.LocatorCacheKey::GetFixedKeyType(string key)
0x4056  ret
```
