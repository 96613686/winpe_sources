# Microsoft.Crm.PerThreadCacheManager::AddEntryWithExactKey

- ea: `0x226a0`
- end: `0x226ec`
- name: `Microsoft.Crm.PerThreadCacheManager::AddEntryWithExactKey`
- size: `76`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x22640`
- `0x22720`

## callees

- `0x22b20`
- `0x22b80`

## string_xrefs

- `0x226c6`: `Cache item with key {0} and value {1} was added to the PerThreadCache with CacheIdentifier:PerThreadCacheIdentifier={2}:{3}`

## pseudocode

```c

```

## disassembly

```asm
0x226a0  call     class [System.Web]System.Web.Caching.Cache [System.Web]System.Web.HttpRuntime::get_Cache()
0x226a5  ldarg.2
0x226a6  ldarg.3
0x226a7  ldarg.s  4
0x226a9  ldsfld   valuetype [mscorlib]System.DateTime [System.Web]System.Web.Caching.Cache::NoAbsoluteExpiration
0x226ae  ldc.i4.0
0x226af  ldc.i4.s 0xF
0x226b1  ldc.i4.0
0x226b2  newobj   instance void [mscorlib]System.TimeSpan::.ctor(int32, int32, int32)
0x226b7  ldc.i4.6
0x226b8  ldnull
0x226b9  callvirt instance void [System.Web]System.Web.Caching.Cache::Insert(string, object, class [System.Web]System.Web.Caching.CacheDependency, valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.TimeSpan, valuetype [System.Web]System.Web.Caching.CacheItemPriority, class [System.Web]System.Web.Caching.CacheItemRemovedCallback)
0x226be  ldarg.0
0x226bf  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.PerThreadCacheManager::get_OrganizationId()
0x226c4  ldc.i4.s 0x1A
0x226c6  ldstr    aCacheItemWithK_2// "Cache item with key {0} and value {1} w"...
0x226cb  ldc.i4.4
0x226cc  newarr   [mscorlib]System.Object
0x226d1  dup
0x226d2  ldc.i4.0
0x226d3  ldarg.2
0x226d4  stelem.ref
0x226d5  dup
0x226d6  ldc.i4.1
0x226d7  ldarg.3
0x226d8  stelem.ref
0x226d9  dup
0x226da  ldc.i4.2
0x226db  ldarg.1
0x226dc  stelem.ref
0x226dd  dup
0x226de  ldc.i4.3
0x226df  ldarg.0
0x226e0  call     instance string Microsoft.Crm.PerThreadCacheManager::get_ThreadLevelCacheIdentifier()
0x226e5  stelem.ref
0x226e6  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x226eb  ret
```
