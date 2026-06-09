# Microsoft.Crm.Sandbox.SandboxAssemblyManager::InitializeOrgCacheObject

- ea: `0x34b0`
- end: `0x3521`
- name: `Microsoft.Crm.Sandbox.SandboxAssemblyManager::InitializeOrgCacheObject`
- size: `113`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x3390`

## callees

- `0x2580`
- `0x2620`
- `0x34b0`
- `0x3880`

## string_xrefs

- `0x350a`: `Could not add assembly to cache`

## pseudocode

```c

```

## disassembly

```asm
0x34b0  ldsfld   class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Sandbox.SandboxAssemblyCache> Microsoft.Crm.Sandbox.SandboxAssemblyManager::_cacheMap
0x34b5  callvirt instance int32 class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Sandbox.SandboxAssemblyCache>::get_Count()
0x34ba  ldc.i4.1
0x34bb  add
0x34bc  call     float64 Microsoft.Crm.Sandbox.SandboxAssemblyManager::MaxCacheSizePerOrgInMByte(int32 numberOfOrgs)
0x34c1  stloc.0
0x34c2  ldsfld   class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Sandbox.SandboxAssemblyCache> Microsoft.Crm.Sandbox.SandboxAssemblyManager::_cacheMap
0x34c7  callvirt instance class [mscorlib]System.Collections.Generic.ICollection`1<var<u1>> class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Sandbox.SandboxAssemblyCache>::get_Values()
0x34cc  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.Crm.Sandbox.SandboxAssemblyCache>::GetEnumerator()
0x34d1  stloc.2
0x34d2  br.s     loc_34E0
0x34d4  ldloc.2
0x34d5  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class Microsoft.Crm.Sandbox.SandboxAssemblyCache>::get_Current()
0x34da  ldloc.0
0x34db  callvirt instance void Microsoft.Crm.Sandbox.SandboxAssemblyCache::SetMaxSizeInMByte(float64 maxSize)
0x34e0  ldloc.2
0x34e1  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x34e6  brtrue.s loc_34D4
0x34e8  leave.s  loc_34F4
0x34ea  ldloc.2
0x34eb  brfalse.s loc_34F3
0x34ed  ldloc.2
0x34ee  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x34f3  endfinally
0x34f4  ldarg.0
0x34f5  ldloc.0
0x34f6  newobj   instance void Microsoft.Crm.Sandbox.SandboxAssemblyCache::.ctor(valuetype [mscorlib]System.Guid organizationId, float64 maxCacheSizeInMByte)
0x34fb  stloc.1
0x34fc  ldsfld   class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Sandbox.SandboxAssemblyCache> Microsoft.Crm.Sandbox.SandboxAssemblyManager::_cacheMap
0x3501  ldarg.0
0x3502  ldloc.1
0x3503  callvirt instance bool class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Sandbox.SandboxAssemblyCache>::TryAdd(var<u1>, !!T0)
0x3508  brtrue.s loc_3515
0x350a  ldstr    aCouldNotAddAss_0// "Could not add assembly to cache"
0x350f  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string)
0x3514  throw
0x3515  ldarg.0
0x3516  call     class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCounter [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCounter::GetCounter(valuetype [mscorlib]System.Guid)
0x351b  callvirt instance void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCounter::AddedToAssemblyCache()
0x3520  ret
```
