# Microsoft.Xrm.Sdk.Client.OrganizationServiceContext::DetachOnSave

- ea: `0x14760`
- end: `0x14832`
- name: `Microsoft.Xrm.Sdk.Client.OrganizationServiceContext::DetachOnSave`
- size: `210`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `service_task, broker_com_uri`

## callers

- `0x23a20`

## callees

- `0x3880`
- `0x3970`
- `0x3c90`
- `0x4280`
- `0x137e0`
- `0x13930`
- `0x13b00`
- `0x13bd0`
- `0x14760`
- `0x15040`

## pseudocode

```c

```

## disassembly

```asm
0x14760  ldarg.0
0x14761  ldarg.1
0x14762  call     instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.Xrm.Sdk.Entity> Microsoft.Xrm.Sdk.Client.OrganizationServiceContext::DetachEntityGraph(class Microsoft.Xrm.Sdk.Entity graph)
0x14767  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.Xrm.Sdk.Entity>::GetEnumerator()
0x1476c  stloc.0
0x1476d  br       loc_1481A
0x14772  ldloc.0
0x14773  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class Microsoft.Xrm.Sdk.Entity>::get_Current()
0x14778  stloc.1
0x14779  ldc.i4.1
0x1477a  stloc.2
0x1477b  ldarg.0
0x1477c  ldloc.1
0x1477d  call     instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.Xrm.Sdk.LinkDescriptor> Microsoft.Xrm.Sdk.Client.OrganizationServiceContext::GetTargetingLinks(class Microsoft.Xrm.Sdk.Entity target)
0x14782  call     T0x2B00004B
0x14787  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Xrm.Sdk.LinkDescriptor>::GetEnumerator()
0x1478c  stloc.3
0x1478d  br.s     loc_147EE
0x1478f  ldloca.s 3
0x14791  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.Xrm.Sdk.LinkDescriptor>::get_Current()
0x14796  stloc.s  4
0x14798  ldloc.s  4
0x1479a  callvirt instance valuetype Microsoft.Xrm.Sdk.EntityStates Microsoft.Xrm.Sdk.Descriptor::get_State()
0x1479f  ldc.i4.4
0x147a0  bne.un.s loc_147E6
0x147a2  ldloc.s  4
0x147a4  callvirt instance class Microsoft.Xrm.Sdk.Entity Microsoft.Xrm.Sdk.LinkDescriptor::get_Target()
0x147a9  callvirt instance class Microsoft.Xrm.Sdk.RelatedEntityCollection Microsoft.Xrm.Sdk.Entity::get_RelatedEntities()
0x147ae  callvirt instance void class Microsoft.Xrm.Sdk.DataCollection`2<class Microsoft.Xrm.Sdk.Relationship, class Microsoft.Xrm.Sdk.EntityCollection>::ClearInternal()
0x147b3  ldarg.0
0x147b4  ldloc.s  4
0x147b6  callvirt instance class Microsoft.Xrm.Sdk.Entity Microsoft.Xrm.Sdk.LinkDescriptor::get_Target()
0x147bb  call     instance bool Microsoft.Xrm.Sdk.Client.OrganizationServiceContext::IsAttached(class Microsoft.Xrm.Sdk.Entity entity)
0x147c0  brtrue.s loc_147EE
0x147c2  ldarg.0
0x147c3  ldloc.s  4
0x147c5  callvirt instance class Microsoft.Xrm.Sdk.Entity Microsoft.Xrm.Sdk.LinkDescriptor::get_Target()
0x147ca  ldc.i4.2
0x147cb  call     instance void Microsoft.Xrm.Sdk.Client.OrganizationServiceContext::AttachEntityGraph(class Microsoft.Xrm.Sdk.Entity graph, valuetype Microsoft.Xrm.Sdk.EntityStates state)
0x147d0  ldloc.s  4
0x147d2  callvirt instance class Microsoft.Xrm.Sdk.Entity Microsoft.Xrm.Sdk.LinkDescriptor::get_Target()
0x147d7  ldc.i4.0
0x147d8  newobj   instance void valuetype [mscorlib]System.Nullable`1<valuetype Microsoft.Xrm.Sdk.EntityState>::.ctor(var<u1>)
0x147dd  callvirt instance void Microsoft.Xrm.Sdk.Entity::SetEntityStateInternal(valuetype [mscorlib]System.Nullable`1<valuetype Microsoft.Xrm.Sdk.EntityState> entityState)
0x147e2  ldc.i4.0
0x147e3  stloc.2
0x147e4  br.s     loc_147EE
0x147e6  ldarg.0
0x147e7  ldloc.s  4
0x147e9  call     instance void Microsoft.Xrm.Sdk.Client.OrganizationServiceContext::DetachLinkTrackingAndRemoveEntity(class Microsoft.Xrm.Sdk.LinkDescriptor existingLink)
0x147ee  ldloca.s 3
0x147f0  call     instance bool valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.Xrm.Sdk.LinkDescriptor>::MoveNext()
0x147f5  brtrue.s loc_1478F
0x147f7  leave.s  loc_14807
0x147f9  ldloca.s 3
0x147fb  constrained. valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.Xrm.Sdk.LinkDescriptor>
0x14801  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x14806  endfinally
0x14807  ldloc.2
0x14808  brfalse.s loc_1481A
0x1480a  ldloc.1
0x1480b  ldloca.s 5
0x1480d  initobj  valuetype [mscorlib]System.Nullable`1<valuetype Microsoft.Xrm.Sdk.EntityState>
0x14813  ldloc.s  5
0x14815  callvirt instance void Microsoft.Xrm.Sdk.Entity::SetEntityStateInternal(valuetype [mscorlib]System.Nullable`1<valuetype Microsoft.Xrm.Sdk.EntityState> entityState)
0x1481a  ldloc.0
0x1481b  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x14820  brtrue   loc_14772
0x14825  leave.s  loc_14831
0x14827  ldloc.0
0x14828  brfalse.s loc_14830
0x1482a  ldloc.0
0x1482b  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x14830  endfinally
0x14831  ret
```
