# Microsoft.Crm.PerThreadCacheManager::TryLookupEntryWithExactKey

- ea: `0x225a0`
- end: `0x22638`
- name: `Microsoft.Crm.PerThreadCacheManager::TryLookupEntryWithExactKey`
- size: `152`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x22570`
- `0x22720`

## callees

- `0x225a0`
- `0x22b20`
- `0x22b80`

## string_xrefs

- `0x225a8`: `Try lookup cache item with key {0} in PerThreadCache with CacheIdentifier:PerThreadCacheIdentifier={1}:{2}`
- `0x225e7`: `Cache item with key {0} was not found in the PerThreadCache with CacheIdentifier:PerThreadCacheIdentifier={1}:{2}`
- `0x22610`: `Cache item with key {0} and value {1} was found in the PerThreadCache with CacheIdentifier:PerThreadCacheIdentifier={2}:{3}`

## pseudocode

```c

```

## disassembly

```asm
0x225a0  ldarg.0
0x225a1  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.PerThreadCacheManager::get_OrganizationId()
0x225a6  ldc.i4.s 0x1A
0x225a8  ldstr    aTryLookupCache// "Try lookup cache item with key {0} in P"...
0x225ad  ldc.i4.3
0x225ae  newarr   [mscorlib]System.Object
0x225b3  dup
0x225b4  ldc.i4.0
0x225b5  ldarg.2
0x225b6  stelem.ref
0x225b7  dup
0x225b8  ldc.i4.1
0x225b9  ldarg.1
0x225ba  stelem.ref
0x225bb  dup
0x225bc  ldc.i4.2
0x225bd  ldarg.0
0x225be  call     instance string Microsoft.Crm.PerThreadCacheManager::get_ThreadLevelCacheIdentifier()
0x225c3  stelem.ref
0x225c4  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x225c9  ldarg.3
0x225ca  call     class [System.Web]System.Web.Caching.Cache [System.Web]System.Web.HttpRuntime::get_Cache()
0x225cf  ldarg.2
0x225d0  callvirt instance object [System.Web]System.Web.Caching.Cache::Get(string)
0x225d5  stind.ref
0x225d6  ldarg.3
0x225d7  ldind.ref
0x225d8  ldnull
0x225d9  cgt.un
0x225db  stloc.0
0x225dc  ldloc.0
0x225dd  brtrue.s loc_22608
0x225df  ldarg.0
0x225e0  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.PerThreadCacheManager::get_OrganizationId()
0x225e5  ldc.i4.s 0x1A
0x225e7  ldstr    aCacheItemWithK_0// "Cache item with key {0} was not found i"...
0x225ec  ldc.i4.3
0x225ed  newarr   [mscorlib]System.Object
0x225f2  dup
0x225f3  ldc.i4.0
0x225f4  ldarg.2
0x225f5  stelem.ref
0x225f6  dup
0x225f7  ldc.i4.1
0x225f8  ldarg.1
0x225f9  stelem.ref
0x225fa  dup
0x225fb  ldc.i4.2
0x225fc  ldarg.0
0x225fd  call     instance string Microsoft.Crm.PerThreadCacheManager::get_ThreadLevelCacheIdentifier()
0x22602  stelem.ref
0x22603  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x22608  ldarg.0
0x22609  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.PerThreadCacheManager::get_OrganizationId()
0x2260e  ldc.i4.s 0x1A
0x22610  ldstr    aCacheItemWithK_1// "Cache item with key {0} and value {1} w"...
0x22615  ldc.i4.4
0x22616  newarr   [mscorlib]System.Object
0x2261b  dup
0x2261c  ldc.i4.0
0x2261d  ldarg.2
0x2261e  stelem.ref
0x2261f  dup
0x22620  ldc.i4.1
0x22621  ldarg.3
0x22622  ldind.ref
0x22623  stelem.ref
0x22624  dup
0x22625  ldc.i4.2
0x22626  ldarg.1
0x22627  stelem.ref
0x22628  dup
0x22629  ldc.i4.3
0x2262a  ldarg.0
0x2262b  call     instance string Microsoft.Crm.PerThreadCacheManager::get_ThreadLevelCacheIdentifier()
0x22630  stelem.ref
0x22631  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x22636  ldloc.0
0x22637  ret
```
