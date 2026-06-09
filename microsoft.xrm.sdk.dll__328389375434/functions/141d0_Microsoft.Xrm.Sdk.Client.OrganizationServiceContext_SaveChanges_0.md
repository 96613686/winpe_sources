# Microsoft.Xrm.Sdk.Client.OrganizationServiceContext::SaveChanges_0

- ea: `0x141d0`
- end: `0x143f0`
- name: `Microsoft.Xrm.Sdk.Client.OrganizationServiceContext::SaveChanges_0`
- size: `544`
- prototype: ``
- caller_count: `1`
- callee_count: `21`
- tags: `service_task, broker_com_uri`

## callers

- `0x141c0`

## callees

- `0x38e0`
- `0x3f00`
- `0x7960`
- `0x7e40`
- `0x7ea0`
- `0x12780`
- `0x127d0`
- `0x127f0`
- `0x13b30`
- `0x13ba0`
- `0x141d0`
- `0x143f0`
- `0x144f0`
- `0x14510`
- `0x14540`
- `0x14550`
- `0x14580`
- `0x14840`
- `0x15040`
- `0x15240`
- `0x15250`

## pseudocode

```c

```

## disassembly

```asm
0x141d0  ldarg.0
0x141d1  ldarg.1
0x141d2  callvirt instance void Microsoft.Xrm.Sdk.Client.OrganizationServiceContext::OnSavingChanges(valuetype Microsoft.Xrm.Sdk.Client.SaveChangesOptions options)
0x141d7  ldarg.1
0x141d8  newobj   instance void Microsoft.Xrm.Sdk.SaveChangesResultCollection::.ctor(valuetype Microsoft.Xrm.Sdk.Client.SaveChangesOptions options)
0x141dd  stloc.0
0x141de  ldarg.0
0x141df  call     instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class [mscorlib]System.Tuple`2<class Microsoft.Xrm.Sdk.Messages.DisassociateRequest, class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.Xrm.Sdk.LinkDescriptor>>> Microsoft.Xrm.Sdk.Client.OrganizationServiceContext::GetDisassociateRequests()
0x141e4  call     T0x2B00004E
0x141e9  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<class [mscorlib]System.Tuple`2<class Microsoft.Xrm.Sdk.Messages.DisassociateRequest, class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.Xrm.Sdk.LinkDescriptor>>>::GetEnumerator()
0x141ee  stloc.1
0x141ef  br.s     loc_1425B
0x141f1  ldloca.s 1
0x141f3  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class [mscorlib]System.Tuple`2<class Microsoft.Xrm.Sdk.Messages.DisassociateRequest, class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.Xrm.Sdk.LinkDescriptor>>>::get_Current()
0x141f8  stloc.2
0x141f9  ldarg.0
0x141fa  ldloc.2
0x141fb  callvirt instance var<u1> class [mscorlib]System.Tuple`2<class Microsoft.Xrm.Sdk.Messages.DisassociateRequest, class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.Xrm.Sdk.LinkDescriptor>>::get_Item1()
0x14200  ldloc.0
0x14201  call     instance class Microsoft.Xrm.Sdk.SaveChangesResult Microsoft.Xrm.Sdk.Client.OrganizationServiceContext::SaveChange(class Microsoft.Xrm.Sdk.OrganizationRequest request, class [mscorlib]System.Collections.Generic.IList`1<class Microsoft.Xrm.Sdk.SaveChangesResult> results)
0x14206  stloc.3
0x14207  ldarg.1
0x14208  ldloc.3
0x14209  call     bool Microsoft.Xrm.Sdk.Client.OrganizationServiceContext::CanContinue(valuetype Microsoft.Xrm.Sdk.Client.SaveChangesOptions options, class Microsoft.Xrm.Sdk.SaveChangesResult result)
0x1420e  brtrue.s loc_14224
0x14210  ldarg.0
0x14211  ldloc.0
0x14212  callvirt instance void Microsoft.Xrm.Sdk.Client.OrganizationServiceContext::OnSaveChanges(class Microsoft.Xrm.Sdk.SaveChangesResultCollection results)
0x14217  ldloc.3
0x14218  callvirt instance class [mscorlib]System.Exception Microsoft.Xrm.Sdk.SaveChangesResult::get_Error()
0x1421d  ldloc.0
0x1421e  newobj   instance void Microsoft.Xrm.Sdk.SaveChangesException::.ctor(class [mscorlib]System.Exception innerException, class Microsoft.Xrm.Sdk.SaveChangesResultCollection results)
0x14223  throw
0x14224  ldloc.2
0x14225  callvirt instance var<u1> class [mscorlib]System.Tuple`2<class Microsoft.Xrm.Sdk.Messages.DisassociateRequest, class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.Xrm.Sdk.LinkDescriptor>>::get_Item2()
0x1422a  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.Xrm.Sdk.LinkDescriptor>::GetEnumerator()
0x1422f  stloc.s  4
0x14231  br.s     loc_14244
0x14233  ldloc.s  4
0x14235  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class Microsoft.Xrm.Sdk.LinkDescriptor>::get_Current()
0x1423a  stloc.s  5
0x1423c  ldarg.0
0x1423d  ldloc.s  5
0x1423f  call     instance void Microsoft.Xrm.Sdk.Client.OrganizationServiceContext::DetachLinkTracking(class Microsoft.Xrm.Sdk.LinkDescriptor existingLink)
0x14244  ldloc.s  4
0x14246  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x1424b  brtrue.s loc_14233
0x1424d  leave.s  loc_1425B
0x1424f  ldloc.s  4
0x14251  brfalse.s loc_1425A
0x14253  ldloc.s  4
0x14255  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1425a  endfinally
0x1425b  ldloca.s 1
0x1425d  call     instance bool valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class [mscorlib]System.Tuple`2<class Microsoft.Xrm.Sdk.Messages.DisassociateRequest, class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.Xrm.Sdk.LinkDescriptor>>>::MoveNext()
0x14262  brtrue.s loc_141F1
0x14264  leave.s  loc_14274
0x14266  ldloca.s 1
0x14268  constrained. valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class [mscorlib]System.Tuple`2<class Microsoft.Xrm.Sdk.Messages.DisassociateRequest, class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.Xrm.Sdk.LinkDescriptor>>>
0x1426e  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x14273  endfinally
0x14274  ldarg.0
0x14275  call     instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.Xrm.Sdk.EntityDescriptor> Microsoft.Xrm.Sdk.Client.OrganizationServiceContext::GetDeletedEntities()
0x1427a  call     T0x2B00004D
0x1427f  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Xrm.Sdk.EntityDescriptor>::GetEnumerator()
0x14284  stloc.s  6
0x14286  br       loc_14334
0x1428b  ldloca.s 6
0x1428d  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.Xrm.Sdk.EntityDescriptor>::get_Current()
0x14292  stloc.s  7
0x14294  ldloc.s  7
0x14296  callvirt instance class Microsoft.Xrm.Sdk.Entity Microsoft.Xrm.Sdk.EntityDescriptor::get_Entity()
0x1429b  callvirt instance class Microsoft.Xrm.Sdk.EntityReference Microsoft.Xrm.Sdk.Entity::ToEntityReference()
0x142a0  stloc.s  8
0x142a2  newobj   instance void Microsoft.Xrm.Sdk.Messages.DeleteRequest::.ctor()
0x142a7  dup
0x142a8  ldloc.s  8
0x142aa  callvirt instance void Microsoft.Xrm.Sdk.Messages.DeleteRequest::set_Target(class Microsoft.Xrm.Sdk.EntityReference value)
0x142af  dup
0x142b0  ldarg.0
0x142b1  ldfld    valuetype Microsoft.Xrm.Sdk.ConcurrencyBehavior Microsoft.Xrm.Sdk.Client.OrganizationServiceContext::_concurrencyBehavior
0x142b6  callvirt instance void Microsoft.Xrm.Sdk.Messages.DeleteRequest::set_ConcurrencyBehavior(valuetype Microsoft.Xrm.Sdk.ConcurrencyBehavior value)
0x142bb  stloc.s  9
0x142bd  ldarg.0
0x142be  ldloc.s  9
0x142c0  ldloc.0
0x142c1  call     instance class Microsoft.Xrm.Sdk.SaveChangesResult Microsoft.Xrm.Sdk.Client.OrganizationServiceContext::SaveChange(class Microsoft.Xrm.Sdk.OrganizationRequest request, class [mscorlib]System.Collections.Generic.IList`1<class Microsoft.Xrm.Sdk.SaveChangesResult> results)
0x142c6  stloc.s  0xA
0x142c8  ldarg.1
0x142c9  ldloc.s  0xA
0x142cb  call     bool Microsoft.Xrm.Sdk.Client.OrganizationServiceContext::CanContinue(valuetype Microsoft.Xrm.Sdk.Client.SaveChangesOptions options, class Microsoft.Xrm.Sdk.SaveChangesResult result)
0x142d0  brtrue.s loc_142E7
0x142d2  ldarg.0
0x142d3  ldloc.0
0x142d4  callvirt instance void Microsoft.Xrm.Sdk.Client.OrganizationServiceContext::OnSaveChanges(class Microsoft.Xrm.Sdk.SaveChangesResultCollection results)
0x142d9  ldloc.s  0xA
0x142db  callvirt instance class [mscorlib]System.Exception Microsoft.Xrm.Sdk.SaveChangesResult::get_Error()
0x142e0  ldloc.0
0x142e1  newobj   instance void Microsoft.Xrm.Sdk.SaveChangesException::.ctor(class [mscorlib]System.Exception innerException, class Microsoft.Xrm.Sdk.SaveChangesResultCollection results)
0x142e6  throw
0x142e7  ldarg.0
0x142e8  ldloc.s  7
0x142ea  call     instance void Microsoft.Xrm.Sdk.Client.OrganizationServiceContext::DetachEntityTracking(class Microsoft.Xrm.Sdk.EntityDescriptor existingEntity)
0x142ef  ldarg.0
0x142f0  ldloc.s  7
0x142f2  callvirt instance class Microsoft.Xrm.Sdk.Entity Microsoft.Xrm.Sdk.EntityDescriptor::get_Entity()
0x142f7  call     instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.Xrm.Sdk.LinkDescriptor> Microsoft.Xrm.Sdk.Client.OrganizationServiceContext::GetTargetingLinks(class Microsoft.Xrm.Sdk.Entity target)
0x142fc  call     T0x2B00004B
0x14301  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Xrm.Sdk.LinkDescriptor>::GetEnumerator()
0x14306  stloc.s  0xB
0x14308  br.s     loc_1431B
0x1430a  ldloca.s 0xB
0x1430c  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.Xrm.Sdk.LinkDescriptor>::get_Current()
0x14311  stloc.s  0xC
0x14313  ldarg.0
0x14314  ldloc.s  0xC
0x14316  call     instance void Microsoft.Xrm.Sdk.Client.OrganizationServiceContext::DetachLinkTracking(class Microsoft.Xrm.Sdk.LinkDescriptor existingLink)
0x1431b  ldloca.s 0xB
0x1431d  call     instance bool valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.Xrm.Sdk.LinkDescriptor>::MoveNext()
0x14322  brtrue.s loc_1430A
0x14324  leave.s  loc_14334
0x14326  ldloca.s 0xB
0x14328  constrained. valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.Xrm.Sdk.LinkDescriptor>
0x1432e  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x14333  endfinally
0x14334  ldloca.s 6
0x14336  call     instance bool valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.Xrm.Sdk.EntityDescriptor>::MoveNext()
0x1433b  brtrue   loc_1428B
0x14340  leave.s  loc_14350
0x14342  ldloca.s 6
0x14344  constrained. valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.Xrm.Sdk.EntityDescriptor>
0x1434a  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1434f  endfinally
0x14350  ldarg.0
0x14351  ldfld    class [System.Core]System.Collections.Generic.HashSet`1<class Microsoft.Xrm.Sdk.Entity> Microsoft.Xrm.Sdk.Client.OrganizationServiceContext::_roots
0x14356  newobj   instance void class [System.Core]System.Collections.Generic.HashSet`1<class Microsoft.Xrm.Sdk.Entity>::.ctor(class [mscorlib]System.Collections.Generic.IEnumerable`1<var<u1>>)
0x1435b  call     class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.Xrm.Sdk.Entity> Microsoft.Xrm.Sdk.Client.OrganizationServiceContext::FilterRoots(class [mscorlib]System.Collections.Generic.ICollection`1<class Microsoft.Xrm.Sdk.Entity> roots)
0x14360  call     T0x2B00002B
0x14365  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Xrm.Sdk.Entity>::GetEnumerator()
0x1436a  stloc.s  0xD
0x1436c  br.s     loc_143C8
0x1436e  ldloca.s 0xD
0x14370  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.Xrm.Sdk.Entity>::get_Current()
0x14375  stloc.s  0xE
0x14377  ldarg.0
0x14378  ldloc.0
0x14379  ldloc.s  0xE
0x1437b  call     instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.Xrm.Sdk.SaveChangesResult> Microsoft.Xrm.Sdk.Client.OrganizationServiceContext::GetChangeRequests(class Microsoft.Xrm.Sdk.SaveChangesResultCollection results, class Microsoft.Xrm.Sdk.Entity entity)
0x14380  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.Xrm.Sdk.SaveChangesResult>::GetEnumerator()
0x14385  stloc.s  0xF
0x14387  br.s     loc_143B1
0x14389  ldloc.s  0xF
0x1438b  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class Microsoft.Xrm.Sdk.SaveChangesResult>::get_Current()
0x14390  stloc.s  0x10
0x14392  ldarg.1
0x14393  ldloc.s  0x10
0x14395  call     bool Microsoft.Xrm.Sdk.Client.OrganizationServiceContext::CanContinue(valuetype Microsoft.Xrm.Sdk.Client.SaveChangesOptions options, class Microsoft.Xrm.Sdk.SaveChangesResult result)
0x1439a  brtrue.s loc_143B1
0x1439c  ldarg.0
0x1439d  ldloc.0
0x1439e  callvirt instance void Microsoft.Xrm.Sdk.Client.OrganizationServiceContext::OnSaveChanges(class Microsoft.Xrm.Sdk.SaveChangesResultCollection results)
0x143a3  ldloc.s  0x10
0x143a5  callvirt instance class [mscorlib]System.Exception Microsoft.Xrm.Sdk.SaveChangesResult::get_Error()
0x143aa  ldloc.0
0x143ab  newobj   instance void Microsoft.Xrm.Sdk.SaveChangesException::.ctor(class [mscorlib]System.Exception innerException, class Microsoft.Xrm.Sdk.SaveChangesResultCollection results)
0x143b0  throw
0x143b1  ldloc.s  0xF
0x143b3  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x143b8  brtrue.s loc_14389
0x143ba  leave.s  loc_143C8
0x143bc  ldloc.s  0xF
0x143be  brfalse.s loc_143C7
0x143c0  ldloc.s  0xF
0x143c2  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x143c7  endfinally
0x143c8  ldloca.s 0xD
0x143ca  call     instance bool valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.Xrm.Sdk.Entity>::MoveNext()
0x143cf  brtrue.s loc_1436E
0x143d1  leave.s  loc_143E1
0x143d3  ldloca.s 0xD
0x143d5  constrained. valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.Xrm.Sdk.Entity>
0x143db  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x143e0  endfinally
0x143e1  ldarg.0
0x143e2  call     instance void Microsoft.Xrm.Sdk.Client.OrganizationServiceContext::DetachAllOnSave()
0x143e7  ldarg.0
0x143e8  ldloc.0
0x143e9  callvirt instance void Microsoft.Xrm.Sdk.Client.OrganizationServiceContext::OnSaveChanges(class Microsoft.Xrm.Sdk.SaveChangesResultCollection results)
0x143ee  ldloc.0
0x143ef  ret
```
