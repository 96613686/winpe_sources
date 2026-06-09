# Microsoft.Crm.PerThreadCacheManager::RemoveExactEntry

- ea: `0x22850`
- end: `0x22890`
- name: `Microsoft.Crm.PerThreadCacheManager::RemoveExactEntry`
- size: `64`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x227f0`
- `0x22810`

## callees

- `0x22850`
- `0x22b20`
- `0x22b80`

## string_xrefs

- `0x22872`: `Cache item with key {0} was removed from the PerThreadCache with CacheIdentifier:PerThreadCacheIdentifier={0}:{1}`

## pseudocode

```c

```

## disassembly

```asm
0x22850  call     class [System.Web]System.Web.Caching.Cache [System.Web]System.Web.HttpRuntime::get_Cache()
0x22855  ldarg.2
0x22856  callvirt instance object [System.Web]System.Web.Caching.Cache::Remove(string)
0x2285b  isinst   [mscorlib]System.IDisposable
0x22860  stloc.0
0x22861  ldloc.0
0x22862  brfalse.s loc_2286A
0x22864  ldloc.0
0x22865  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x2286a  ldarg.0
0x2286b  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.PerThreadCacheManager::get_OrganizationId()
0x22870  ldc.i4.s 0x1A
0x22872  ldstr    aCacheItemWithK_3// "Cache item with key {0} was removed fro"...
0x22877  ldc.i4.2
0x22878  newarr   [mscorlib]System.Object
0x2287d  dup
0x2287e  ldc.i4.0
0x2287f  ldarg.1
0x22880  stelem.ref
0x22881  dup
0x22882  ldc.i4.1
0x22883  ldarg.0
0x22884  call     instance string Microsoft.Crm.PerThreadCacheManager::get_ThreadLevelCacheIdentifier()
0x22889  stelem.ref
0x2288a  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x2288f  ret
```
