# Microsoft.Crm.Caching.ChannelAccessProfileCacheData::Initialize

- ea: `0x84330`
- end: `0x8437b`
- name: `Microsoft.Crm.Caching.ChannelAccessProfileCacheData::Initialize`
- size: `75`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x81f50`
- `0x84310`
- `0x84320`
- `0x84330`

## string_xrefs

- `0x8434c`: `entityaccesslevelid`
- `0x8435c`: `entityaccessleveldepthmask`

## pseudocode

```c

```

## disassembly

```asm
0x84330  ldarg.0
0x84331  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, valuetype Microsoft.Crm.Caching.EntityAccessLevelDepth>::.ctor()
0x84336  call     instance void Microsoft.Crm.Caching.ChannelAccessProfileCacheData::set_EntityAccessLevelsDepths(class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, valuetype Microsoft.Crm.Caching.EntityAccessLevelDepth> value)
0x8433b  ldarg.1
0x8433c  stloc.0
0x8433d  ldc.i4.0
0x8433e  stloc.1
0x8433f  br.s     loc_84374
0x84341  ldloc.0
0x84342  ldloc.1
0x84343  ldelem.ref
0x84344  stloc.2
0x84345  ldarg.0
0x84346  call     instance class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, valuetype Microsoft.Crm.Caching.EntityAccessLevelDepth> Microsoft.Crm.Caching.ChannelAccessProfileCacheData::get_EntityAccessLevelsDepths()
0x8434b  ldloc.2
0x8434c  ldstr    aEntityaccessle// "entityaccesslevelid"
0x84351  callvirt instance object Microsoft.Crm.Caching.ICacheEntityWrapper::GetAttributeValue(string attributeName)
0x84356  unbox.any [mscorlib]System.Guid
0x8435b  ldloc.2
0x8435c  ldstr    aEntityaccessle_0// "entityaccessleveldepthmask"
0x84361  callvirt instance object Microsoft.Crm.Caching.ICacheEntityWrapper::GetAttributeValue(string attributeName)
0x84366  unbox.any Microsoft.Crm.Caching.EntityAccessLevelDepth
0x8436b  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, valuetype Microsoft.Crm.Caching.EntityAccessLevelDepth>::Add(var<u1>, !!T0)
0x84370  ldloc.1
0x84371  ldc.i4.1
0x84372  add
0x84373  stloc.1
0x84374  ldloc.1
0x84375  ldloc.0
0x84376  ldlen
0x84377  conv.i4
0x84378  blt.s    loc_84341
0x8437a  ret
```
