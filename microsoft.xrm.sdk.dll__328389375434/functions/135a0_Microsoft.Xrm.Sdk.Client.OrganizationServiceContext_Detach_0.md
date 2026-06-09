# Microsoft.Xrm.Sdk.Client.OrganizationServiceContext::Detach_0

- ea: `0x135a0`
- end: `0x136db`
- name: `Microsoft.Xrm.Sdk.Client.OrganizationServiceContext::Detach_0`
- size: `315`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callers

- `0x13580`

## callees

- `0x3990`
- `0x135a0`
- `0x13b00`
- `0x13b30`
- `0x13ba0`
- `0x13bd0`
- `0x14f60`
- `0x15040`

## pseudocode

```c

```

## disassembly

```asm
0x135a0  ldarg.1
0x135a1  brtrue.s loc_135AE
0x135a3  ldstr    aEntity// "entity"
0x135a8  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x135ad  throw
0x135ae  ldarg.0
0x135af  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<class Microsoft.Xrm.Sdk.Entity, class Microsoft.Xrm.Sdk.EntityDescriptor> Microsoft.Xrm.Sdk.Client.OrganizationServiceContext::_descriptors
0x135b4  ldarg.1
0x135b5  ldloca.s 0
0x135b7  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<class Microsoft.Xrm.Sdk.Entity, class Microsoft.Xrm.Sdk.EntityDescriptor>::TryGetValue(var<u1>, !!T0)
0x135bc  brtrue.s loc_135C0
0x135be  ldc.i4.0
0x135bf  ret
0x135c0  ldarg.2
0x135c1  brtrue   loc_13669
0x135c6  ldarg.0
0x135c7  ldloc.0
0x135c8  call     instance void Microsoft.Xrm.Sdk.Client.OrganizationServiceContext::DetachEntityTracking(class Microsoft.Xrm.Sdk.EntityDescriptor existingEntity)
0x135cd  ldarg.1
0x135ce  call     class [mscorlib]System.Collections.Generic.IEnumerable`1<class [mscorlib]System.Tuple`3<class Microsoft.Xrm.Sdk.Entity, class Microsoft.Xrm.Sdk.Relationship, class Microsoft.Xrm.Sdk.Entity>> Microsoft.Xrm.Sdk.Client.OrganizationServiceContext::TraverseRelatedEntities(class Microsoft.Xrm.Sdk.Entity entity)
0x135d3  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class [mscorlib]System.Tuple`3<class Microsoft.Xrm.Sdk.Entity, class Microsoft.Xrm.Sdk.Relationship, class Microsoft.Xrm.Sdk.Entity>>::GetEnumerator()
0x135d8  stloc.1
0x135d9  br.s     loc_13616
0x135db  ldloc.1
0x135dc  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [mscorlib]System.Tuple`3<class Microsoft.Xrm.Sdk.Entity, class Microsoft.Xrm.Sdk.Relationship, class Microsoft.Xrm.Sdk.Entity>>::get_Current()
0x135e1  dup
0x135e2  callvirt instance var<u1> class [mscorlib]System.Tuple`3<class Microsoft.Xrm.Sdk.Entity, class Microsoft.Xrm.Sdk.Relationship, class Microsoft.Xrm.Sdk.Entity>::get_Item1()
0x135e7  stloc.2
0x135e8  dup
0x135e9  callvirt instance var<u1> class [mscorlib]System.Tuple`3<class Microsoft.Xrm.Sdk.Entity, class Microsoft.Xrm.Sdk.Relationship, class Microsoft.Xrm.Sdk.Entity>::get_Item2()
0x135ee  stloc.3
0x135ef  callvirt instance var<u1> class [mscorlib]System.Tuple`3<class Microsoft.Xrm.Sdk.Entity, class Microsoft.Xrm.Sdk.Relationship, class Microsoft.Xrm.Sdk.Entity>::get_Item3()
0x135f4  stloc.s  4
0x135f6  ldarg.0
0x135f7  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<class Microsoft.Xrm.Sdk.LinkDescriptor, class Microsoft.Xrm.Sdk.LinkDescriptor> Microsoft.Xrm.Sdk.Client.OrganizationServiceContext::_bindings
0x135fc  ldloc.2
0x135fd  ldloc.3
0x135fe  ldloc.s  4
0x13600  newobj   instance void Microsoft.Xrm.Sdk.LinkDescriptor::.ctor(class Microsoft.Xrm.Sdk.Entity source, class Microsoft.Xrm.Sdk.Relationship relationship, class Microsoft.Xrm.Sdk.Entity target)
0x13605  ldloca.s 5
0x13607  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<class Microsoft.Xrm.Sdk.LinkDescriptor, class Microsoft.Xrm.Sdk.LinkDescriptor>::TryGetValue(var<u1>, !!T0)
0x1360c  brfalse.s loc_13616
0x1360e  ldarg.0
0x1360f  ldloc.s  5
0x13611  call     instance void Microsoft.Xrm.Sdk.Client.OrganizationServiceContext::DetachLinkTracking(class Microsoft.Xrm.Sdk.LinkDescriptor existingLink)
0x13616  ldloc.1
0x13617  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x1361c  brtrue.s loc_135DB
0x1361e  leave.s  loc_1362A
0x13620  ldloc.1
0x13621  brfalse.s loc_13629
0x13623  ldloc.1
0x13624  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x13629  endfinally
0x1362a  ldarg.0
0x1362b  ldarg.1
0x1362c  call     instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.Xrm.Sdk.LinkDescriptor> Microsoft.Xrm.Sdk.Client.OrganizationServiceContext::GetTargetingLinks(class Microsoft.Xrm.Sdk.Entity target)
0x13631  call     T0x2B00004B
0x13636  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Xrm.Sdk.LinkDescriptor>::GetEnumerator()
0x1363b  stloc.s  6
0x1363d  br.s     loc_13650
0x1363f  ldloca.s 6
0x13641  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.Xrm.Sdk.LinkDescriptor>::get_Current()
0x13646  stloc.s  7
0x13648  ldarg.0
0x13649  ldloc.s  7
0x1364b  call     instance void Microsoft.Xrm.Sdk.Client.OrganizationServiceContext::DetachLinkTrackingAndRemoveEntity(class Microsoft.Xrm.Sdk.LinkDescriptor existingLink)
0x13650  ldloca.s 6
0x13652  call     instance bool valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.Xrm.Sdk.LinkDescriptor>::MoveNext()
0x13657  brtrue.s loc_1363F
0x13659  leave.s  loc_136D9
0x1365b  ldloca.s 6
0x1365d  constrained. valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.Xrm.Sdk.LinkDescriptor>
0x13663  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x13668  endfinally
0x13669  ldarg.0
0x1366a  ldarg.1
0x1366b  call     instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.Xrm.Sdk.Entity> Microsoft.Xrm.Sdk.Client.OrganizationServiceContext::DetachEntityGraph(class Microsoft.Xrm.Sdk.Entity graph)
0x13670  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.Xrm.Sdk.Entity>::GetEnumerator()
0x13675  stloc.s  8
0x13677  br.s     loc_136C2
0x13679  ldloc.s  8
0x1367b  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class Microsoft.Xrm.Sdk.Entity>::get_Current()
0x13680  stloc.s  9
0x13682  ldarg.0
0x13683  ldloc.s  9
0x13685  call     instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.Xrm.Sdk.LinkDescriptor> Microsoft.Xrm.Sdk.Client.OrganizationServiceContext::GetTargetingLinks(class Microsoft.Xrm.Sdk.Entity target)
0x1368a  call     T0x2B00004B
0x1368f  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Xrm.Sdk.LinkDescriptor>::GetEnumerator()
0x13694  stloc.s  6
0x13696  br.s     loc_136A9
0x13698  ldloca.s 6
0x1369a  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.Xrm.Sdk.LinkDescriptor>::get_Current()
0x1369f  stloc.s  0xA
0x136a1  ldarg.0
0x136a2  ldloc.s  0xA
0x136a4  call     instance void Microsoft.Xrm.Sdk.Client.OrganizationServiceContext::DetachLinkTrackingAndRemoveEntity(class Microsoft.Xrm.Sdk.LinkDescriptor existingLink)
0x136a9  ldloca.s 6
0x136ab  call     instance bool valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.Xrm.Sdk.LinkDescriptor>::MoveNext()
0x136b0  brtrue.s loc_13698
0x136b2  leave.s  loc_136C2
0x136b4  ldloca.s 6
0x136b6  constrained. valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.Xrm.Sdk.LinkDescriptor>
0x136bc  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x136c1  endfinally
0x136c2  ldloc.s  8
0x136c4  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x136c9  brtrue.s loc_13679
0x136cb  leave.s  loc_136D9
0x136cd  ldloc.s  8
0x136cf  brfalse.s loc_136D8
0x136d1  ldloc.s  8
0x136d3  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x136d8  endfinally
0x136d9  ldc.i4.1
0x136da  ret
```
