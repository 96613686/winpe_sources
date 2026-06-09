# Microsoft.Crm.Sandbox.SandboxAssemblyManager::MonitorAssemblyCacheInternal

- ea: `0x36a0`
- end: `0x3815`
- name: `Microsoft.Crm.Sandbox.SandboxAssemblyManager::MonitorAssemblyCacheInternal`
- size: `373`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callers

- `0x3660`

## callees

- `0x2620`
- `0x2670`
- `0x36a0`
- `0x3820`
- `0x3880`

## string_xrefs

- `0x36a7`: `SandboxAssemblyManager.MonitorAssemblyCacheInternal: ENTER`
- `0x3707`: `SandboxAssemblyManager.MonitorAssemblyCacheInternal: Empty cache: {0}`
- `0x3787`: `SandboxAssemblyManager.MonitorAssemblyCacheInternal: Could not remove organization from assembly cache`
- `0x3804`: `SandboxAssemblyManager.MonitorAssemblyCacheInternal: EXIT`

## pseudocode

```c

```

## disassembly

```asm
0x36a0  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x36a5  ldc.i4.s 0x22
0x36a7  ldstr    aSandboxassembl_52// "SandboxAssemblyManager.MonitorAssemblyC"...
0x36ac  ldc.i4.0
0x36ad  newarr   [mscorlib]System.Object
0x36b2  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x36b7  ldsfld   bool Microsoft.Crm.Sandbox.SandboxAssemblyManager::_timerCallbackEntered
0x36bc  brfalse.s loc_36BF
0x36be  ret
0x36bf  ldc.i4.1
0x36c0  stsfld   bool Microsoft.Crm.Sandbox.SandboxAssemblyManager::_timerCallbackEntered
0x36c5  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::.ctor()
0x36ca  stloc.0
0x36cb  ldsfld   class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Sandbox.SandboxAssemblyCache> Microsoft.Crm.Sandbox.SandboxAssemblyManager::_cacheMap
0x36d0  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<var<u1>, !!T0>> class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Sandbox.SandboxAssemblyCache>::GetEnumerator()
0x36d5  stloc.2
0x36d6  br.s     loc_3733
0x36d8  ldloc.2
0x36d9  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Sandbox.SandboxAssemblyCache>>::get_Current()
0x36de  stloc.3
0x36df  ldloca.s 3
0x36e1  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Sandbox.SandboxAssemblyCache>::get_Key()
0x36e6  stloc.s  5
0x36e8  ldloca.s 3
0x36ea  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Sandbox.SandboxAssemblyCache>::get_Key()
0x36ef  ldloca.s 3
0x36f1  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Sandbox.SandboxAssemblyCache>::get_Value()
0x36f6  ldloca.s 4
0x36f8  call     bool Microsoft.Crm.Sandbox.SandboxAssemblyManager::TryRecoverDiskSpace(valuetype [mscorlib]System.Guid organizationId, class Microsoft.Crm.Sandbox.SandboxAssemblyCache cache, [out] int32& numberOfFiles)
0x36fd  brfalse.s loc_372B
0x36ff  ldloc.s  4
0x3701  brtrue.s loc_3733
0x3703  ldloc.s  5
0x3705  ldc.i4.s 0x22
0x3707  ldstr    aSandboxassembl_53// "SandboxAssemblyManager.MonitorAssemblyC"...
0x370c  ldc.i4.1
0x370d  newarr   [mscorlib]System.Object
0x3712  dup
0x3713  ldc.i4.0
0x3714  ldloc.s  5
0x3716  box      [mscorlib]System.Guid
0x371b  stelem.ref
0x371c  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x3721  ldloc.0
0x3722  ldloc.s  5
0x3724  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::Add(var<u1>)
0x3729  br.s     loc_3733
0x372b  ldloc.0
0x372c  ldloc.s  5
0x372e  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::Add(var<u1>)
0x3733  ldloc.2
0x3734  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x3739  brtrue.s loc_36D8
0x373b  leave.s  loc_3747
0x373d  ldloc.2
0x373e  brfalse.s loc_3746
0x3740  ldloc.2
0x3741  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x3746  endfinally
0x3747  ldloc.0
0x3748  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::GetEnumerator()
0x374d  stloc.s  6
0x374f  br.s     loc_3797
0x3751  ldloca.s 6
0x3753  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<valuetype [mscorlib]System.Guid>::get_Current()
0x3758  stloc.s  7
0x375a  ldnull
0x375b  stloc.s  8
0x375d  ldsfld   class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Sandbox.SandboxAssemblyCache> Microsoft.Crm.Sandbox.SandboxAssemblyManager::_cacheMap
0x3762  ldloc.s  7
0x3764  ldloca.s 8
0x3766  callvirt instance bool class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Sandbox.SandboxAssemblyCache>::TryRemove(var<u1>, !!T0)
0x376b  brfalse.s loc_3782
0x376d  ldloc.s  8
0x376f  callvirt instance void Microsoft.Crm.Sandbox.SandboxAssemblyCache::DeleteDirectory()
0x3774  ldloc.s  7
0x3776  call     class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCounter [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCounter::GetCounter(valuetype [mscorlib]System.Guid)
0x377b  callvirt instance void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCounter::RemovedFromAssemblyCache()
0x3780  br.s     loc_3797
0x3782  ldnull
0x3783  ldloc.s  7
0x3785  ldc.i4.s 0x21
0x3787  ldstr    aSandboxassembl_54// "SandboxAssemblyManager.MonitorAssemblyC"...
0x378c  ldc.i4.0
0x378d  newarr   [mscorlib]System.Object
0x3792  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x3797  ldloca.s 6
0x3799  call     instance bool valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<valuetype [mscorlib]System.Guid>::MoveNext()
0x379e  brtrue.s loc_3751
0x37a0  leave.s  loc_37B0
0x37a2  ldloca.s 6
0x37a4  constrained. valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<valuetype [mscorlib]System.Guid>
0x37aa  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x37af  endfinally
0x37b0  ldsfld   class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Sandbox.SandboxAssemblyCache> Microsoft.Crm.Sandbox.SandboxAssemblyManager::_cacheMap
0x37b5  callvirt instance int32 class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Sandbox.SandboxAssemblyCache>::get_Count()
0x37ba  call     float64 Microsoft.Crm.Sandbox.SandboxAssemblyManager::MaxCacheSizePerOrgInMByte(int32 numberOfOrgs)
0x37bf  stloc.1
0x37c0  ldsfld   class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Sandbox.SandboxAssemblyCache> Microsoft.Crm.Sandbox.SandboxAssemblyManager::_cacheMap
0x37c5  callvirt instance class [mscorlib]System.Collections.Generic.ICollection`1<var<u1>> class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Sandbox.SandboxAssemblyCache>::get_Values()
0x37ca  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.Crm.Sandbox.SandboxAssemblyCache>::GetEnumerator()
0x37cf  stloc.s  9
0x37d1  br.s     loc_37E0
0x37d3  ldloc.s  9
0x37d5  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class Microsoft.Crm.Sandbox.SandboxAssemblyCache>::get_Current()
0x37da  ldloc.1
0x37db  callvirt instance void Microsoft.Crm.Sandbox.SandboxAssemblyCache::SetMaxSizeInMByte(float64 maxSize)
0x37e0  ldloc.s  9
0x37e2  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x37e7  brtrue.s loc_37D3
0x37e9  leave.s  loc_37F7
0x37eb  ldloc.s  9
0x37ed  brfalse.s loc_37F6
0x37ef  ldloc.s  9
0x37f1  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x37f6  endfinally
0x37f7  ldc.i4.0
0x37f8  stsfld   bool Microsoft.Crm.Sandbox.SandboxAssemblyManager::_timerCallbackEntered
0x37fd  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x3802  ldc.i4.s 0x22
0x3804  ldstr    aSandboxassembl_55// "SandboxAssemblyManager.MonitorAssemblyC"...
0x3809  ldc.i4.0
0x380a  newarr   [mscorlib]System.Object
0x380f  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x3814  ret
```
