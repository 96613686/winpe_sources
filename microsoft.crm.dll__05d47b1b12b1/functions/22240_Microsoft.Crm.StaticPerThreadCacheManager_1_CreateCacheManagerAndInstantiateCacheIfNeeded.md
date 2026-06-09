# Microsoft.Crm.StaticPerThreadCacheManager`1::CreateCacheManagerAndInstantiateCacheIfNeeded

- ea: `0x22240`
- end: `0x22304`
- name: `Microsoft.Crm.StaticPerThreadCacheManager`1::CreateCacheManagerAndInstantiateCacheIfNeeded`
- size: `196`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x1bbc0`
- `0x1bc10`
- `0x22240`
- `0x22500`

## string_xrefs

- `0x222c7`: `StaticPerThreadCacheManager: Could not add IPerThreadCacheManager to the _perThreadCacheManagers concurrent dictionary`
- `0x222ee`: `StaticPerThreadCacheManager: Could not CreateCacheManagerAndInstantiateCacheIfNeeded.`

## pseudocode

```c

```

## disassembly

```asm
0x22240  ldloca.s 0
0x22242  initobj  var<u1>
0x22248  ldarg.0
0x22249  brfalse.s loc_2225D
0x2224b  ldarg.0
0x2224c  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext::TryGetOrganizationId()
0x22251  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x22256  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x2225b  brfalse.s loc_2226C
0x2225d  ldloca.s 2
0x2225f  initobj  var<u1>
0x22265  ldloc.2
0x22266  stloc.2
0x22267  leave    loc_22302
0x2226c  ldc.i4.0
0x2226d  stloc.1
0x2226e  ldarg.1
0x2226f  brfalse.s loc_2227D
0x22271  ldarg.0
0x22272  call     bool Microsoft.Crm.CrmCacheUtility::IsInStagingContextAndStagedCacheEnabled(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x22277  brfalse.s loc_22287
0x22279  ldc.i4.1
0x2227a  stloc.1
0x2227b  br.s     loc_22287
0x2227d  ldarg.0
0x2227e  call     bool Microsoft.Crm.CrmCacheUtility::IsPerThreadCachingRequired(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x22283  brfalse.s loc_22287
0x22285  ldc.i4.1
0x22286  stloc.1
0x22287  ldloc.1
0x22288  brfalse.s loc_222E5
0x2228a  ldarg.0
0x2228b  call     var<u1> class Microsoft.Crm.StaticPerThreadCacheManager`1<var<u1>>::InstantiatePerThreadCacheManager(!!T0)
0x22290  stloc.0
0x22291  call     class [mscorlib]System.Threading.Thread [mscorlib]System.Threading.Thread::get_CurrentThread()
0x22296  callvirt instance int32 [mscorlib]System.Threading.Thread::get_ManagedThreadId()
0x2229b  stloc.3
0x2229c  ldsfld   class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<int32, var<u1>> class Microsoft.Crm.StaticPerThreadCacheManager`1<var<u1>>::_perThreadCacheManagers
0x222a1  ldloc.3
0x222a2  callvirt instance bool class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<int32, var<u1>>::ContainsKey(var<u1>)
0x222a7  brtrue.s loc_222D9
0x222a9  ldsfld   class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<int32, var<u1>> class Microsoft.Crm.StaticPerThreadCacheManager`1<var<u1>>::_perThreadCacheManagers
0x222ae  ldloc.3
0x222af  ldloc.0
0x222b0  callvirt instance bool class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<int32, var<u1>>::TryAdd(var<u1>, !!T0)
0x222b5  brtrue.s loc_222E5
0x222b7  ldnull
0x222b8  ldloca.s 0
0x222ba  constrained. var<u1>
0x222c0  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.IPerThreadCacheManager::get_OrganizationId()
0x222c5  ldc.i4.s 0x14
0x222c7  ldstr    aStaticperthrea// "StaticPerThreadCacheManager: Could not "...
0x222cc  ldc.i4.0
0x222cd  newarr   [mscorlib]System.Object
0x222d2  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x222d7  br.s     loc_222E5
0x222d9  ldsfld   class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<int32, var<u1>> class Microsoft.Crm.StaticPerThreadCacheManager`1<var<u1>>::_perThreadCacheManagers
0x222de  ldloc.3
0x222df  ldloc.0
0x222e0  callvirt instance void class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<int32, var<u1>>::set_Item(var<u1>, !!T0)
0x222e5  leave.s  loc_22300
0x222e7  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x222ec  ldc.i4.s 0x14
0x222ee  ldstr    aStaticperthrea_0// "StaticPerThreadCacheManager: Could not "...
0x222f3  ldc.i4.0
0x222f4  newarr   [mscorlib]System.Object
0x222f9  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x222fe  leave.s  loc_22300
0x22300  ldloc.0
0x22301  ret
0x22302  ldloc.2
0x22303  ret
```
