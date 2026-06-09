# Microsoft.Crm.LocatorCacheKey::GetFixedKeyType

- ea: `0x4060`
- end: `0x40dc`
- name: `Microsoft.Crm.LocatorCacheKey::GetFixedKeyType`
- size: `124`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x4030`

## callees

- `0x4060`

## string_xrefs

- `0x4066`: `CrmConfigDb`
- `0x408d`: `CrmConfigDb`

## pseudocode

```c

```

## disassembly

```asm
0x4060  ldarg.0
0x4061  callvirt instance int32 [mscorlib]System.String::get_Length()
0x4066  ldstr    aCrmconfigdb// "CrmConfigDb"
0x406b  call     instance int32 [mscorlib]System.String::get_Length()
0x4070  sub
0x4071  ldc.i4.1
0x4072  sub
0x4073  stloc.0
0x4074  ldc.i4.0
0x4075  stloc.1
0x4076  br.s     loc_40D0
0x4078  ldloc.0
0x4079  ldsfld   class Microsoft.Crm.FixedCacheKey[] Microsoft.Crm.LocatorCacheKey::FixedCacheKeys
0x407e  ldloc.1
0x407f  ldelem.ref
0x4080  ldfld    string Microsoft.Crm.FixedCacheKey::keyName
0x4085  callvirt instance int32 [mscorlib]System.String::get_Length()
0x408a  bne.un.s loc_40CC
0x408c  ldarg.0
0x408d  ldstr    aCrmconfigdb// "CrmConfigDb"
0x4092  call     instance int32 [mscorlib]System.String::get_Length()
0x4097  ldc.i4.1
0x4098  sub
0x4099  ldsfld   class Microsoft.Crm.FixedCacheKey[] Microsoft.Crm.LocatorCacheKey::FixedCacheKeys
0x409e  ldloc.1
0x409f  ldelem.ref
0x40a0  ldfld    string Microsoft.Crm.FixedCacheKey::keyName
0x40a5  ldc.i4.0
0x40a6  ldsfld   class Microsoft.Crm.FixedCacheKey[] Microsoft.Crm.LocatorCacheKey::FixedCacheKeys
0x40ab  ldloc.1
0x40ac  ldelem.ref
0x40ad  ldfld    string Microsoft.Crm.FixedCacheKey::keyName
0x40b2  callvirt instance int32 [mscorlib]System.String::get_Length()
0x40b7  ldc.i4.4
0x40b8  call     int32 [mscorlib]System.String::Compare(string, int32, string, int32, int32, valuetype [mscorlib]System.StringComparison)
0x40bd  brtrue.s loc_40CC
0x40bf  ldsfld   class Microsoft.Crm.FixedCacheKey[] Microsoft.Crm.LocatorCacheKey::FixedCacheKeys
0x40c4  ldloc.1
0x40c5  ldelem.ref
0x40c6  ldfld    valuetype Microsoft.Crm.LocatorKeyType Microsoft.Crm.FixedCacheKey::keyType
0x40cb  ret
0x40cc  ldloc.1
0x40cd  ldc.i4.1
0x40ce  add
0x40cf  stloc.1
0x40d0  ldloc.1
0x40d1  ldsfld   class Microsoft.Crm.FixedCacheKey[] Microsoft.Crm.LocatorCacheKey::FixedCacheKeys
0x40d6  ldlen
0x40d7  conv.i4
0x40d8  blt.s    loc_4078
0x40da  ldc.i4.0
0x40db  ret
```
