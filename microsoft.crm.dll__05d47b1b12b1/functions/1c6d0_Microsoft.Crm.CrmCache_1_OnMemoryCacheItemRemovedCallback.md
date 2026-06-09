# Microsoft.Crm.CrmCache`1::OnMemoryCacheItemRemovedCallback

- ea: `0x1c6d0`
- end: `0x1c72f`
- name: `Microsoft.Crm.CrmCache`1::OnMemoryCacheItemRemovedCallback`
- size: `95`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x1c930`

## string_xrefs

- `0x1c6d7`: `Cache item with key {0} was removed from cache {1} for the following reason: {2}`

## pseudocode

```c

```

## disassembly

```asm
0x1c6d0  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x1c6d5  ldc.i4.s 0x1A
0x1c6d7  ldstr    aCacheItemWithK// "Cache item with key {0} was removed fro"...
0x1c6dc  ldc.i4.3
0x1c6dd  newarr   [mscorlib]System.Object
0x1c6e2  dup
0x1c6e3  ldc.i4.0
0x1c6e4  ldarg.1
0x1c6e5  callvirt instance class [System.Runtime.Caching]System.Runtime.Caching.CacheItem [System.Runtime.Caching]System.Runtime.Caching.CacheEntryRemovedArguments::get_CacheItem()
0x1c6ea  callvirt instance string [System.Runtime.Caching]System.Runtime.Caching.CacheItem::get_Key()
0x1c6ef  stelem.ref
0x1c6f0  dup
0x1c6f1  ldc.i4.1
0x1c6f2  ldarg.0
0x1c6f3  ldfld    string class Microsoft.Crm.CrmCache`1<var<u1>>::_cacheIdentifier
0x1c6f8  stelem.ref
0x1c6f9  dup
0x1c6fa  ldc.i4.2
0x1c6fb  ldarg.1
0x1c6fc  stelem.ref
0x1c6fd  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x1c702  ldarg.0
0x1c703  ldarg.1
0x1c704  callvirt instance class [System.Runtime.Caching]System.Runtime.Caching.CacheItem [System.Runtime.Caching]System.Runtime.Caching.CacheEntryRemovedArguments::get_CacheItem()
0x1c709  callvirt instance string [System.Runtime.Caching]System.Runtime.Caching.CacheItem::get_Key()
0x1c70e  ldarg.1
0x1c70f  callvirt instance class [System.Runtime.Caching]System.Runtime.Caching.CacheItem [System.Runtime.Caching]System.Runtime.Caching.CacheEntryRemovedArguments::get_CacheItem()
0x1c714  callvirt instance object [System.Runtime.Caching]System.Runtime.Caching.CacheItem::get_Value()
0x1c719  ldarg.1
0x1c71a  callvirt instance valuetype [System.Runtime.Caching]System.Runtime.Caching.CacheEntryRemovedReason [System.Runtime.Caching]System.Runtime.Caching.CacheEntryRemovedArguments::get_RemovedReason()
0x1c71f  call     valuetype [System.Web]System.Web.Caching.CacheItemRemovedReason class Microsoft.Crm.CrmCache`1<var<u1>>::ConvertMemoryCacheRemovedReasonToWebCacheRemovedReason(valuetype [System.Runtime.Caching]System.Runtime.Caching.CacheEntryRemovedReason)
0x1c724  newobj   instance void Microsoft.Crm.CrmCacheItemRemovedEventArgs::.ctor(string key, object value, valuetype [System.Web]System.Web.Caching.CacheItemRemovedReason reason)
0x1c729  call     instance void class Microsoft.Crm.CrmCache`1<var<u1>>::RaiseCachedItemRemoved(class Microsoft.Crm.CrmCacheItemRemovedEventArgs)
0x1c72e  ret
```
