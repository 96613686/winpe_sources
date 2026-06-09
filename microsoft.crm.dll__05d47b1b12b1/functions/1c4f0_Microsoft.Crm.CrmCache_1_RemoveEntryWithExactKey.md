# Microsoft.Crm.CrmCache`1::RemoveEntryWithExactKey

- ea: `0x1c4f0`
- end: `0x1c573`
- name: `Microsoft.Crm.CrmCache`1::RemoveEntryWithExactKey`
- size: `131`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x1c4f0`

## string_xrefs

- `0x1c53c`: `Cache {0} had item with key {0} removed`

## pseudocode

```c

```

## disassembly

```asm
0x1c4f0  ldnull
0x1c4f1  stloc.0
0x1c4f2  ldarg.0
0x1c4f3  call     instance bool class Microsoft.Crm.CrmCache`1<var<u1>>::get_EnableMemoryCache()
0x1c4f8  brfalse.s loc_1C509
0x1c4fa  call     class [System.Runtime.Caching]System.Runtime.Caching.MemoryCache [System.Runtime.Caching]System.Runtime.Caching.MemoryCache::get_Default()
0x1c4ff  ldarg.1
0x1c500  ldnull
0x1c501  callvirt instance object [System.Runtime.Caching]System.Runtime.Caching.ObjectCache::Remove(string, string)
0x1c506  stloc.0
0x1c507  br.s     loc_1C515
0x1c509  call     class [System.Web]System.Web.Caching.Cache [System.Web]System.Web.HttpRuntime::get_Cache()
0x1c50e  ldarg.1
0x1c50f  callvirt instance object [System.Web]System.Web.Caching.Cache::Remove(string)
0x1c514  stloc.0
0x1c515  ldloc.0
0x1c516  isinst   [mscorlib]System.IDisposable
0x1c51b  stloc.1
0x1c51c  ldloc.1
0x1c51d  brfalse.s loc_1C52A
0x1c51f  ldloc.1
0x1c520  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1c525  leave.s  loc_1C52A
0x1c527  pop
0x1c528  leave.s  loc_1C52A
0x1c52a  ldarg.3
0x1c52b  brtrue.s loc_1C534
0x1c52d  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x1c532  br.s     loc_1C53A
0x1c534  ldarg.3
0x1c535  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext::get_OrganizationId()
0x1c53a  ldc.i4.s 0x1A
0x1c53c  ldstr    aCache0HadItemW// "Cache {0} had item with key {0} removed"
0x1c541  ldc.i4.2
0x1c542  newarr   [mscorlib]System.Object
0x1c547  dup
0x1c548  ldc.i4.0
0x1c549  ldarg.0
0x1c54a  ldfld    string class Microsoft.Crm.CrmCache`1<var<u1>>::_cacheIdentifier
0x1c54f  stelem.ref
0x1c550  dup
0x1c551  ldc.i4.1
0x1c552  ldarg.1
0x1c553  stelem.ref
0x1c554  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x1c559  ldarg.2
0x1c55a  brfalse.s loc_1C572
0x1c55c  call     bool [Microsoft.Crm.Core]Microsoft.Crm.RegControl::IsInClientContext()
0x1c561  brtrue.s loc_1C572
0x1c563  call     bool [Microsoft.Crm.Core]Microsoft.Crm.RegControl::IsInCrmInternalToolContext()
0x1c568  brtrue.s loc_1C572
0x1c56a  ldarg.0
0x1c56b  ldarg.1
0x1c56c  ldarg.3
0x1c56d  call     instance void class Microsoft.Crm.CrmCache`1<var<u1>>::FireCacheItemRemoveNotificationOnExactCacheKey(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x1c572  ret
```
