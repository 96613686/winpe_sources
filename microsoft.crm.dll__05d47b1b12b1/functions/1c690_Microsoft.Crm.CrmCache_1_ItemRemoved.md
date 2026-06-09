# Microsoft.Crm.CrmCache`1::ItemRemoved

- ea: `0x1c690`
- end: `0x1c6cc`
- name: `Microsoft.Crm.CrmCache`1::ItemRemoved`
- size: `60`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x1c930`

## string_xrefs

- `0x1c697`: `Cache item with key {0} was removed from cache {1} for the following reason: {2}`

## pseudocode

```c

```

## disassembly

```asm
0x1c690  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x1c695  ldc.i4.s 0x1A
0x1c697  ldstr    aCacheItemWithK// "Cache item with key {0} was removed fro"...
0x1c69c  ldc.i4.3
0x1c69d  newarr   [mscorlib]System.Object
0x1c6a2  dup
0x1c6a3  ldc.i4.0
0x1c6a4  ldarg.1
0x1c6a5  stelem.ref
0x1c6a6  dup
0x1c6a7  ldc.i4.1
0x1c6a8  ldarg.0
0x1c6a9  ldfld    string class Microsoft.Crm.CrmCache`1<var<u1>>::_cacheIdentifier
0x1c6ae  stelem.ref
0x1c6af  dup
0x1c6b0  ldc.i4.2
0x1c6b1  ldarg.3
0x1c6b2  box      [System.Web]System.Web.Caching.CacheItemRemovedReason
0x1c6b7  stelem.ref
0x1c6b8  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x1c6bd  ldarg.0
0x1c6be  ldarg.1
0x1c6bf  ldarg.2
0x1c6c0  ldarg.3
0x1c6c1  newobj   instance void Microsoft.Crm.CrmCacheItemRemovedEventArgs::.ctor(string key, object value, valuetype [System.Web]System.Web.Caching.CacheItemRemovedReason reason)
0x1c6c6  call     instance void class Microsoft.Crm.CrmCache`1<var<u1>>::RaiseCachedItemRemoved(class Microsoft.Crm.CrmCacheItemRemovedEventArgs)
0x1c6cb  ret
```
