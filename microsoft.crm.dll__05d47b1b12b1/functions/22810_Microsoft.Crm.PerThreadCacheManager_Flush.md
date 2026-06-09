# Microsoft.Crm.PerThreadCacheManager::Flush

- ea: `0x22810`
- end: `0x22849`
- name: `Microsoft.Crm.PerThreadCacheManager::Flush`
- size: `57`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x229e0`

## callees

- `0x22850`
- `0x22b20`
- `0x22b80`

## string_xrefs

- `0x2282b`: `Flushed PerThreadCache with CacheIdentifier:PerThreadCacheIdentifier={0}:{1}`

## pseudocode

```c

```

## disassembly

```asm
0x22810  ldarg.0
0x22811  ldarg.1
0x22812  ldarg.1
0x22813  ldarg.0
0x22814  call     instance string Microsoft.Crm.PerThreadCacheManager::get_ThreadLevelCacheIdentifier()
0x22819  call     string [mscorlib]System.String::Concat(string, string)
0x2281e  call     instance void Microsoft.Crm.PerThreadCacheManager::RemoveExactEntry(string cacheIdentifier, string exactCacheKey)
0x22823  ldarg.0
0x22824  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.PerThreadCacheManager::get_OrganizationId()
0x22829  ldc.i4.s 0x1A
0x2282b  ldstr    aFlushedPerthre// "Flushed PerThreadCache with CacheIdenti"...
0x22830  ldc.i4.2
0x22831  newarr   [mscorlib]System.Object
0x22836  dup
0x22837  ldc.i4.0
0x22838  ldarg.1
0x22839  stelem.ref
0x2283a  dup
0x2283b  ldc.i4.1
0x2283c  ldarg.0
0x2283d  call     instance string Microsoft.Crm.PerThreadCacheManager::get_ThreadLevelCacheIdentifier()
0x22842  stelem.ref
0x22843  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x22848  ret
```
