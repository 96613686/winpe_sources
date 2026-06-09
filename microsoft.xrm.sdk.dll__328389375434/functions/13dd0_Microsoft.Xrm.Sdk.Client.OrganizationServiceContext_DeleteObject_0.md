# Microsoft.Xrm.Sdk.Client.OrganizationServiceContext::DeleteObject_0

- ea: `0x13dd0`
- end: `0x13f05`
- name: `Microsoft.Xrm.Sdk.Client.OrganizationServiceContext::DeleteObject_0`
- size: `309`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `service_task, broker_com_uri`

## callers

- `0x13db0`

## callees

- `0x3890`
- `0x3990`
- `0x13dd0`
- `0x13f10`
- `0x13f40`
- `0x13fa0`
- `0x14f60`
- `0x15040`
- `0x15070`

## pseudocode

```c

```

## disassembly

```asm
0x13dd0  ldarg.1
0x13dd1  brtrue.s loc_13DDE
0x13dd3  ldstr    aEntity// "entity"
0x13dd8  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x13ddd  throw
0x13dde  ldarg.0
0x13ddf  ldarg.1
0x13de0  ldstr    aEntity// "entity"
0x13de5  call     instance class Microsoft.Xrm.Sdk.EntityDescriptor Microsoft.Xrm.Sdk.Client.OrganizationServiceContext::EnsureTracked(class Microsoft.Xrm.Sdk.Entity entity, string parameterName)
0x13dea  stloc.0
0x13deb  ldarg.2
0x13dec  brtrue   loc_13E94
0x13df1  ldarg.0
0x13df2  ldloc.0
0x13df3  call     instance void Microsoft.Xrm.Sdk.Client.OrganizationServiceContext::DeleteEntityTracking(class Microsoft.Xrm.Sdk.EntityDescriptor existingEntity)
0x13df8  ldarg.1
0x13df9  call     class [mscorlib]System.Collections.Generic.IEnumerable`1<class [mscorlib]System.Tuple`3<class Microsoft.Xrm.Sdk.Entity, class Microsoft.Xrm.Sdk.Relationship, class Microsoft.Xrm.Sdk.Entity>> Microsoft.Xrm.Sdk.Client.OrganizationServiceContext::TraverseRelatedEntities(class Microsoft.Xrm.Sdk.Entity entity)
0x13dfe  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class [mscorlib]System.Tuple`3<class Microsoft.Xrm.Sdk.Entity, class Microsoft.Xrm.Sdk.Relationship, class Microsoft.Xrm.Sdk.Entity>>::GetEnumerator()
0x13e03  stloc.1
0x13e04  br.s     loc_13E41
0x13e06  ldloc.1
0x13e07  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [mscorlib]System.Tuple`3<class Microsoft.Xrm.Sdk.Entity, class Microsoft.Xrm.Sdk.Relationship, class Microsoft.Xrm.Sdk.Entity>>::get_Current()
0x13e0c  dup
0x13e0d  callvirt instance var<u1> class [mscorlib]System.Tuple`3<class Microsoft.Xrm.Sdk.Entity, class Microsoft.Xrm.Sdk.Relationship, class Microsoft.Xrm.Sdk.Entity>::get_Item1()
0x13e12  stloc.2
0x13e13  dup
0x13e14  callvirt instance var<u1> class [mscorlib]System.Tuple`3<class Microsoft.Xrm.Sdk.Entity, class Microsoft.Xrm.Sdk.Relationship, class Microsoft.Xrm.Sdk.Entity>::get_Item2()
0x13e19  stloc.3
0x13e1a  callvirt instance var<u1> class [mscorlib]System.Tuple`3<class Microsoft.Xrm.Sdk.Entity, class Microsoft.Xrm.Sdk.Relationship, class Microsoft.Xrm.Sdk.Entity>::get_Item3()
0x13e1f  stloc.s  4
0x13e21  ldarg.0
0x13e22  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<class Microsoft.Xrm.Sdk.LinkDescriptor, class Microsoft.Xrm.Sdk.LinkDescriptor> Microsoft.Xrm.Sdk.Client.OrganizationServiceContext::_bindings
0x13e27  ldloc.2
0x13e28  ldloc.3
0x13e29  ldloc.s  4
0x13e2b  newobj   instance void Microsoft.Xrm.Sdk.LinkDescriptor::.ctor(class Microsoft.Xrm.Sdk.Entity source, class Microsoft.Xrm.Sdk.Relationship relationship, class Microsoft.Xrm.Sdk.Entity target)
0x13e30  ldloca.s 5
0x13e32  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<class Microsoft.Xrm.Sdk.LinkDescriptor, class Microsoft.Xrm.Sdk.LinkDescriptor>::TryGetValue(var<u1>, !!T0)
0x13e37  brfalse.s loc_13E41
0x13e39  ldloc.s  5
0x13e3b  ldc.i4.8
0x13e3c  callvirt instance void Microsoft.Xrm.Sdk.Descriptor::set_State(valuetype Microsoft.Xrm.Sdk.EntityStates value)
0x13e41  ldloc.1
0x13e42  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x13e47  brtrue.s loc_13E06
0x13e49  leave.s  loc_13E55
0x13e4b  ldloc.1
0x13e4c  brfalse.s loc_13E54
0x13e4e  ldloc.1
0x13e4f  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x13e54  endfinally
0x13e55  ldarg.0
0x13e56  ldarg.1
0x13e57  call     instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.Xrm.Sdk.LinkDescriptor> Microsoft.Xrm.Sdk.Client.OrganizationServiceContext::GetTargetingLinks(class Microsoft.Xrm.Sdk.Entity target)
0x13e5c  call     T0x2B00004B
0x13e61  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Xrm.Sdk.LinkDescriptor>::GetEnumerator()
0x13e66  stloc.s  6
0x13e68  br.s     loc_13E7B
0x13e6a  ldloca.s 6
0x13e6c  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.Xrm.Sdk.LinkDescriptor>::get_Current()
0x13e71  stloc.s  7
0x13e73  ldarg.0
0x13e74  ldloc.s  7
0x13e76  call     instance void Microsoft.Xrm.Sdk.Client.OrganizationServiceContext::DeleteLinkTrackingAndRemoveEntity(class Microsoft.Xrm.Sdk.LinkDescriptor existingLink)
0x13e7b  ldloca.s 6
0x13e7d  call     instance bool valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.Xrm.Sdk.LinkDescriptor>::MoveNext()
0x13e82  brtrue.s loc_13E6A
0x13e84  leave.s  loc_13F04
0x13e86  ldloca.s 6
0x13e88  constrained. valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.Xrm.Sdk.LinkDescriptor>
0x13e8e  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x13e93  endfinally
0x13e94  ldarg.0
0x13e95  ldarg.1
0x13e96  call     instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.Xrm.Sdk.Entity> Microsoft.Xrm.Sdk.Client.OrganizationServiceContext::DeleteEntityGraph(class Microsoft.Xrm.Sdk.Entity entity)
0x13e9b  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.Xrm.Sdk.Entity>::GetEnumerator()
0x13ea0  stloc.s  8
0x13ea2  br.s     loc_13EED
0x13ea4  ldloc.s  8
0x13ea6  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class Microsoft.Xrm.Sdk.Entity>::get_Current()
0x13eab  stloc.s  9
0x13ead  ldarg.0
0x13eae  ldloc.s  9
0x13eb0  call     instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.Xrm.Sdk.LinkDescriptor> Microsoft.Xrm.Sdk.Client.OrganizationServiceContext::GetTargetingLinks(class Microsoft.Xrm.Sdk.Entity target)
0x13eb5  call     T0x2B00004B
0x13eba  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Xrm.Sdk.LinkDescriptor>::GetEnumerator()
0x13ebf  stloc.s  6
0x13ec1  br.s     loc_13ED4
0x13ec3  ldloca.s 6
0x13ec5  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.Xrm.Sdk.LinkDescriptor>::get_Current()
0x13eca  stloc.s  0xA
0x13ecc  ldarg.0
0x13ecd  ldloc.s  0xA
0x13ecf  call     instance void Microsoft.Xrm.Sdk.Client.OrganizationServiceContext::DeleteLinkTrackingAndRemoveEntity(class Microsoft.Xrm.Sdk.LinkDescriptor existingLink)
0x13ed4  ldloca.s 6
0x13ed6  call     instance bool valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.Xrm.Sdk.LinkDescriptor>::MoveNext()
0x13edb  brtrue.s loc_13EC3
0x13edd  leave.s  loc_13EED
0x13edf  ldloca.s 6
0x13ee1  constrained. valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.Xrm.Sdk.LinkDescriptor>
0x13ee7  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x13eec  endfinally
0x13eed  ldloc.s  8
0x13eef  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x13ef4  brtrue.s loc_13EA4
0x13ef6  leave.s  loc_13F04
0x13ef8  ldloc.s  8
0x13efa  brfalse.s loc_13F03
0x13efc  ldloc.s  8
0x13efe  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x13f03  endfinally
0x13f04  ret
```
