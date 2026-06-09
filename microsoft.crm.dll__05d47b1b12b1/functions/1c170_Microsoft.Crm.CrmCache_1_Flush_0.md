# Microsoft.Crm.CrmCache`1::Flush_0

- ea: `0x1c170`
- end: `0x1c20a`
- name: `Microsoft.Crm.CrmCache`1::Flush_0`
- size: `154`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x19b80`
- `0x19c50`
- `0x19c70`
- `0x1c170`
- `0x22740`

## string_xrefs

- `0x1c1df`: `Cache {0} was flushed`

## pseudocode

```c

```

## disassembly

```asm
0x1c170  ldarg.2
0x1c171  brtrue.s loc_1C17A
0x1c173  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x1c178  br.s     loc_1C180
0x1c17a  ldarg.2
0x1c17b  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext::get_OrganizationId()
0x1c180  stloc.0
0x1c181  ldloca.s 0
0x1c183  constrained. [mscorlib]System.Guid
0x1c189  callvirt instance string [mscorlib]System.Object::ToString()
0x1c18e  stloc.1
0x1c18f  call     class Microsoft.Crm.CacheEventSource Microsoft.Crm.CacheEventSource::get_Instance()
0x1c194  ldloc.1
0x1c195  ldarg.0
0x1c196  ldfld    string class Microsoft.Crm.CrmCache`1<var<u1>>::_cacheIdentifier
0x1c19b  callvirt instance void Microsoft.Crm.CacheEventSource::FlushCacheStarted(string organizationId, string cacheName)
0x1c1a0  ldc.i4.0
0x1c1a1  stloc.2
0x1c1a2  ldarg.0
0x1c1a3  call     instance bool class Microsoft.Crm.CrmCache`1<var<u1>>::get_EnablePerThreadCacheManager()
0x1c1a8  brfalse.s loc_1C1CB
0x1c1aa  ldarg.2
0x1c1ab  ldc.i4.0
0x1c1ac  call     var<u1> class Microsoft.Crm.StaticPerThreadCacheManager`1<class Microsoft.Crm.PerThreadCacheManager>::TryGetOrCreateInstance(!!T0, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x1c1b1  stloc.3
0x1c1b2  ldloc.3
0x1c1b3  brfalse.s loc_1C1CB
0x1c1b5  ldloc.3
0x1c1b6  ldarg.0
0x1c1b7  ldfld    string class Microsoft.Crm.CrmCache`1<var<u1>>::_cacheIdentifier
0x1c1bc  ldarg.0
0x1c1bd  ldfld    string class Microsoft.Crm.CrmCache`1<var<u1>>::_cacheIdentifier
0x1c1c2  ldc.i4.1
0x1c1c3  ldarg.2
0x1c1c4  ldarg.0
0x1c1c5  callvirt instance bool Microsoft.Crm.PerThreadCacheManager::RemoveEntryFromThreadLevelCacheAndMarkForRemovalFromStandardCacheIfRequired(string cacheIdentifier, string cacheKey, bool isRootEntry, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context, class Microsoft.Crm.ICrmCacheRemove crmCache)
0x1c1ca  stloc.2
0x1c1cb  ldloc.2
0x1c1cc  brtrue.s loc_1C1F8
0x1c1ce  ldarg.0
0x1c1cf  ldarg.0
0x1c1d0  ldfld    string class Microsoft.Crm.CrmCache`1<var<u1>>::_cacheIdentifier
0x1c1d5  ldarg.1
0x1c1d6  ldarg.2
0x1c1d7  call     instance void class Microsoft.Crm.CrmCache`1<var<u1>>::RemoveEntryWithExactKey(string, bool, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x1c1dc  ldloc.0
0x1c1dd  ldc.i4.s 0x1A
0x1c1df  ldstr    aCache0WasFlush// "Cache {0} was flushed"
0x1c1e4  ldc.i4.1
0x1c1e5  newarr   [mscorlib]System.Object
0x1c1ea  dup
0x1c1eb  ldc.i4.0
0x1c1ec  ldarg.0
0x1c1ed  ldfld    string class Microsoft.Crm.CrmCache`1<var<u1>>::_cacheIdentifier
0x1c1f2  stelem.ref
0x1c1f3  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x1c1f8  call     class Microsoft.Crm.CacheEventSource Microsoft.Crm.CacheEventSource::get_Instance()
0x1c1fd  ldloc.1
0x1c1fe  ldarg.0
0x1c1ff  ldfld    string class Microsoft.Crm.CrmCache`1<var<u1>>::_cacheIdentifier
0x1c204  callvirt instance void Microsoft.Crm.CacheEventSource::FlushCacheEnded(string organizationId, string cacheName)
0x1c209  ret
```
