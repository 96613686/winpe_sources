# <GetChangeRequestsFromSubtree>d__81::MoveNext

- ea: `0x24360`
- end: `0x246bd`
- name: `<GetChangeRequestsFromSubtree>d__81::MoveNext`
- size: `861`
- prototype: ``
- caller_count: `0`
- callee_count: `15`
- tags: ``

## callees

- `0x3880`
- `0x3930`
- `0x3970`
- `0x3990`
- `0x3c30`
- `0x3c90`
- `0x13bd0`
- `0x145a0`
- `0x145d0`
- `0x14600`
- `0x14990`
- `0x24330`
- `0x24360`
- `0x246c0`
- `0x246e0`

## pseudocode

```c

```

## disassembly

```asm
0x24360  ldarg.0
0x24361  ldfld    int32 <GetChangeRequestsFromSubtree>d__81::<>1__state
0x24366  stloc.1
0x24367  ldarg.0
0x24368  ldfld    class Microsoft.Xrm.Sdk.Client.OrganizationServiceContext <GetChangeRequestsFromSubtree>d__81::<>4__this
0x2436d  stloc.2
0x2436e  ldloc.1
0x2436f  brfalse.s loc_2437F
0x24371  ldloc.1
0x24372  ldc.i4.1
0x24373  beq      loc_245F4
0x24378  ldc.i4.0
0x24379  stloc.0
0x2437a  leave    loc_246BB
0x2437f  ldarg.0
0x24380  ldc.i4.m1
0x24381  stfld    int32 <GetChangeRequestsFromSubtree>d__81::<>1__state
0x24386  ldarg.0
0x24387  ldfld    class Microsoft.Xrm.Sdk.Entity <GetChangeRequestsFromSubtree>d__81::entity
0x2438c  callvirt instance class Microsoft.Xrm.Sdk.RelatedEntityCollection Microsoft.Xrm.Sdk.Entity::get_RelatedEntities()
0x24391  ldsfld   class [mscorlib]System.Func`2<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<class Microsoft.Xrm.Sdk.Relationship, class Microsoft.Xrm.Sdk.EntityCollection>, class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.Xrm.Sdk.Entity>> <>c::<>9__81_0
0x24396  dup
0x24397  brtrue.s loc_243B0
0x24399  pop
0x2439a  ldsfld   class <>c <>c::<>9
0x2439f  ldftn    instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.Xrm.Sdk.Entity> <>c::<GetChangeRequestsFromSubtree>b__81_0(valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<class Microsoft.Xrm.Sdk.Relationship, class Microsoft.Xrm.Sdk.EntityCollection> relationship)
0x243a5  newobj   instance void class [mscorlib]System.Func`2<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<class Microsoft.Xrm.Sdk.Relationship, class Microsoft.Xrm.Sdk.EntityCollection>, class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.Xrm.Sdk.Entity>>::.ctor(object, native int)
0x243aa  dup
0x243ab  stsfld   class [mscorlib]System.Func`2<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<class Microsoft.Xrm.Sdk.Relationship, class Microsoft.Xrm.Sdk.EntityCollection>, class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.Xrm.Sdk.Entity>> <>c::<>9__81_0
0x243b0  ldsfld   class [mscorlib]System.Func`3<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<class Microsoft.Xrm.Sdk.Relationship, class Microsoft.Xrm.Sdk.EntityCollection>, class Microsoft.Xrm.Sdk.Entity, class <>f__AnonymousType5`2<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<class Microsoft.Xrm.Sdk.Relationship, class Microsoft.Xrm.Sdk.EntityCollection>, class Microsoft.Xrm.Sdk.Entity>> <>c::<>9__81_1
0x243b5  dup
0x243b6  brtrue.s loc_243CF
0x243b8  pop
0x243b9  ldsfld   class <>c <>c::<>9
0x243be  ldftn    instance class <>f__AnonymousType5`2<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<class Microsoft.Xrm.Sdk.Relationship, class Microsoft.Xrm.Sdk.EntityCollection>, class Microsoft.Xrm.Sdk.Entity> <>c::<GetChangeRequestsFromSubtree>b__81_1(valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<class Microsoft.Xrm.Sdk.Relationship, class Microsoft.Xrm.Sdk.EntityCollection> relationship, class Microsoft.Xrm.Sdk.Entity target)
0x243c4  newobj   instance void class [mscorlib]System.Func`3<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<class Microsoft.Xrm.Sdk.Relationship, class Microsoft.Xrm.Sdk.EntityCollection>, class Microsoft.Xrm.Sdk.Entity, class <>f__AnonymousType5`2<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<class Microsoft.Xrm.Sdk.Relationship, class Microsoft.Xrm.Sdk.EntityCollection>, class Microsoft.Xrm.Sdk.Entity>>::.ctor(object, native int)
0x243c9  dup
0x243ca  stsfld   class [mscorlib]System.Func`3<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<class Microsoft.Xrm.Sdk.Relationship, class Microsoft.Xrm.Sdk.EntityCollection>, class Microsoft.Xrm.Sdk.Entity, class <>f__AnonymousType5`2<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<class Microsoft.Xrm.Sdk.Relationship, class Microsoft.Xrm.Sdk.EntityCollection>, class Microsoft.Xrm.Sdk.Entity>> <>c::<>9__81_1
0x243cf  call     T0x2B00007B
0x243d4  ldsfld   class [mscorlib]System.Func`2<class <>f__AnonymousType5`2<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<class Microsoft.Xrm.Sdk.Relationship, class Microsoft.Xrm.Sdk.EntityCollection>, class Microsoft.Xrm.Sdk.Entity>, class Microsoft.Xrm.Sdk.Entity> <>c::<>9__81_2
0x243d9  dup
0x243da  brtrue.s loc_243F3
0x243dc  pop
0x243dd  ldsfld   class <>c <>c::<>9
0x243e2  ldftn    instance class Microsoft.Xrm.Sdk.Entity <>c::<GetChangeRequestsFromSubtree>b__81_2(class <>f__AnonymousType5`2<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<class Microsoft.Xrm.Sdk.Relationship, class Microsoft.Xrm.Sdk.EntityCollection>, class Microsoft.Xrm.Sdk.Entity> <>h__TransparentIdentifier0)
0x243e8  newobj   instance void class [mscorlib]System.Func`2<class <>f__AnonymousType5`2<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<class Microsoft.Xrm.Sdk.Relationship, class Microsoft.Xrm.Sdk.EntityCollection>, class Microsoft.Xrm.Sdk.Entity>, class Microsoft.Xrm.Sdk.Entity>::.ctor(object, native int)
0x243ed  dup
0x243ee  stsfld   class [mscorlib]System.Func`2<class <>f__AnonymousType5`2<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<class Microsoft.Xrm.Sdk.Relationship, class Microsoft.Xrm.Sdk.EntityCollection>, class Microsoft.Xrm.Sdk.Entity>, class Microsoft.Xrm.Sdk.Entity> <>c::<>9__81_2
0x243f3  ldsfld   class [mscorlib]System.Func`2<class <>f__AnonymousType5`2<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<class Microsoft.Xrm.Sdk.Relationship, class Microsoft.Xrm.Sdk.EntityCollection>, class Microsoft.Xrm.Sdk.Entity>, class <>f__AnonymousType6`2<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<class Microsoft.Xrm.Sdk.Relationship, class Microsoft.Xrm.Sdk.EntityCollection>, class Microsoft.Xrm.Sdk.Entity>> <>c::<>9__81_3
0x243f8  dup
0x243f9  brtrue.s loc_24412
0x243fb  pop
0x243fc  ldsfld   class <>c <>c::<>9
0x24401  ldftn    instance class <>f__AnonymousType6`2<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<class Microsoft.Xrm.Sdk.Relationship, class Microsoft.Xrm.Sdk.EntityCollection>, class Microsoft.Xrm.Sdk.Entity> <>c::<GetChangeRequestsFromSubtree>b__81_3(class <>f__AnonymousType5`2<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<class Microsoft.Xrm.Sdk.Relationship, class Microsoft.Xrm.Sdk.EntityCollection>, class Microsoft.Xrm.Sdk.Entity> <>h__TransparentIdentifier0)
0x24407  newobj   instance void class [mscorlib]System.Func`2<class <>f__AnonymousType5`2<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<class Microsoft.Xrm.Sdk.Relationship, class Microsoft.Xrm.Sdk.EntityCollection>, class Microsoft.Xrm.Sdk.Entity>, class <>f__AnonymousType6`2<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<class Microsoft.Xrm.Sdk.Relationship, class Microsoft.Xrm.Sdk.EntityCollection>, class Microsoft.Xrm.Sdk.Entity>>::.ctor(object, native int)
0x2440c  dup
0x2440d  stsfld   class [mscorlib]System.Func`2<class <>f__AnonymousType5`2<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<class Microsoft.Xrm.Sdk.Relationship, class Microsoft.Xrm.Sdk.EntityCollection>, class Microsoft.Xrm.Sdk.Entity>, class <>f__AnonymousType6`2<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<class Microsoft.Xrm.Sdk.Relationship, class Microsoft.Xrm.Sdk.EntityCollection>, class Microsoft.Xrm.Sdk.Entity>> <>c::<>9__81_3
0x24412  call     T0x2B00007C
0x24417  ldsfld   class [mscorlib]System.Func`2<class [System.Core]System.Linq.IGrouping`2<class Microsoft.Xrm.Sdk.Entity, class <>f__AnonymousType6`2<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<class Microsoft.Xrm.Sdk.Relationship, class Microsoft.Xrm.Sdk.EntityCollection>, class Microsoft.Xrm.Sdk.Entity>>, class <>f__AnonymousType7`2<class Microsoft.Xrm.Sdk.Entity, class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<class Microsoft.Xrm.Sdk.Relationship, class Microsoft.Xrm.Sdk.EntityCollection>>>> <>c::<>9__81_4
0x2441c  dup
0x2441d  brtrue.s loc_24436
0x2441f  pop
0x24420  ldsfld   class <>c <>c::<>9
0x24425  ldftn    instance class <>f__AnonymousType7`2<class Microsoft.Xrm.Sdk.Entity, class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<class Microsoft.Xrm.Sdk.Relationship, class Microsoft.Xrm.Sdk.EntityCollection>>> <>c::<GetChangeRequestsFromSubtree>b__81_4(class [System.Core]System.Linq.IGrouping`2<class Microsoft.Xrm.Sdk.Entity, class <>f__AnonymousType6`2<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<class Microsoft.Xrm.Sdk.Relationship, class Microsoft.Xrm.Sdk.EntityCollection>, class Microsoft.Xrm.Sdk.Entity>> grp)
0x2442b  newobj   instance void class [mscorlib]System.Func`2<class [System.Core]System.Linq.IGrouping`2<class Microsoft.Xrm.Sdk.Entity, class <>f__AnonymousType6`2<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<class Microsoft.Xrm.Sdk.Relationship, class Microsoft.Xrm.Sdk.EntityCollection>, class Microsoft.Xrm.Sdk.Entity>>, class <>f__AnonymousType7`2<class Microsoft.Xrm.Sdk.Entity, class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<class Microsoft.Xrm.Sdk.Relationship, class Microsoft.Xrm.Sdk.EntityCollection>>>>::.ctor(object, native int)
0x24430  dup
0x24431  stsfld   class [mscorlib]System.Func`2<class [System.Core]System.Linq.IGrouping`2<class Microsoft.Xrm.Sdk.Entity, class <>f__AnonymousType6`2<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<class Microsoft.Xrm.Sdk.Relationship, class Microsoft.Xrm.Sdk.EntityCollection>, class Microsoft.Xrm.Sdk.Entity>>, class <>f__AnonymousType7`2<class Microsoft.Xrm.Sdk.Entity, class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<class Microsoft.Xrm.Sdk.Relationship, class Microsoft.Xrm.Sdk.EntityCollection>>>> <>c::<>9__81_4
0x24436  call     T0x2B00007D
0x2443b  call     T0x2B00007E
0x24440  stloc.3
0x24441  ldarg.0
0x24442  ldloc.3
0x24443  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<class <>f__AnonymousType7`2<class Microsoft.Xrm.Sdk.Entity, class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<class Microsoft.Xrm.Sdk.Relationship, class Microsoft.Xrm.Sdk.EntityCollection>>>>::GetEnumerator()
0x24448  stfld    valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class <>f__AnonymousType7`2<class Microsoft.Xrm.Sdk.Entity, class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<class Microsoft.Xrm.Sdk.Relationship, class Microsoft.Xrm.Sdk.EntityCollection>>>> <GetChangeRequestsFromSubtree>d__81::<>7__wrap1
0x2444d  ldarg.0
0x2444e  ldc.i4.s 0xFD
0x24450  stfld    int32 <GetChangeRequestsFromSubtree>d__81::<>1__state
0x24455  br       loc_2468E
0x2445a  ldarg.0
0x2445b  ldflda   valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class <>f__AnonymousType7`2<class Microsoft.Xrm.Sdk.Entity, class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<class Microsoft.Xrm.Sdk.Relationship, class Microsoft.Xrm.Sdk.EntityCollection>>>> <GetChangeRequestsFromSubtree>d__81::<>7__wrap1
0x24460  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class <>f__AnonymousType7`2<class Microsoft.Xrm.Sdk.Entity, class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<class Microsoft.Xrm.Sdk.Relationship, class Microsoft.Xrm.Sdk.EntityCollection>>>>::get_Current()
0x24465  dup
0x24466  callvirt instance var<u1> class <>f__AnonymousType7`2<class Microsoft.Xrm.Sdk.Entity, class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<class Microsoft.Xrm.Sdk.Relationship, class Microsoft.Xrm.Sdk.EntityCollection>>>::get_Target()
0x2446b  stloc.s  4
0x2446d  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Xrm.Sdk.LinkDescriptor>::.ctor()
0x24472  stloc.s  5
0x24474  callvirt instance var<u1> class <>f__AnonymousType7`2<class Microsoft.Xrm.Sdk.Entity, class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<class Microsoft.Xrm.Sdk.Relationship, class Microsoft.Xrm.Sdk.EntityCollection>>>::get_Relationships()
0x24479  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<class Microsoft.Xrm.Sdk.Relationship, class Microsoft.Xrm.Sdk.EntityCollection>>::GetEnumerator()
0x2447e  stloc.s  8
0x24480  br.s     loc_244CB
0x24482  ldloca.s 8
0x24484  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<class Microsoft.Xrm.Sdk.Relationship, class Microsoft.Xrm.Sdk.EntityCollection>>::get_Current()
0x24489  stloc.s  9
0x2448b  ldloc.2
0x2448c  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<class Microsoft.Xrm.Sdk.LinkDescriptor, class Microsoft.Xrm.Sdk.LinkDescriptor> Microsoft.Xrm.Sdk.Client.OrganizationServiceContext::_bindings
0x24491  ldarg.0
0x24492  ldfld    class Microsoft.Xrm.Sdk.Entity <GetChangeRequestsFromSubtree>d__81::entity
0x24497  ldloca.s 9
0x24499  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<class Microsoft.Xrm.Sdk.Relationship, class Microsoft.Xrm.Sdk.EntityCollection>::get_Key()
0x2449e  ldloc.s  4
0x244a0  newobj   instance void Microsoft.Xrm.Sdk.LinkDescriptor::.ctor(class Microsoft.Xrm.Sdk.Entity source, class Microsoft.Xrm.Sdk.Relationship relationship, class Microsoft.Xrm.Sdk.Entity target)
0x244a5  ldloca.s 0xA
0x244a7  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<class Microsoft.Xrm.Sdk.LinkDescriptor, class Microsoft.Xrm.Sdk.LinkDescriptor>::TryGetValue(var<u1>, !!T0)
0x244ac  brfalse.s loc_244CB
0x244ae  ldloc.s  0xA
0x244b0  callvirt instance valuetype Microsoft.Xrm.Sdk.EntityStates Microsoft.Xrm.Sdk.Descriptor::get_State()
0x244b5  ldc.i4.4
0x244b6  bne.un.s loc_244C3
0x244b8  ldloc.s  5
0x244ba  ldloc.s  0xA
0x244bc  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Xrm.Sdk.LinkDescriptor>::Add(var<u1>)
0x244c1  br.s     loc_244CB
0x244c3  ldloc.2
0x244c4  ldloc.s  0xA
0x244c6  call     instance void Microsoft.Xrm.Sdk.Client.OrganizationServiceContext::DetachLinkTrackingAndRemoveEntity(class Microsoft.Xrm.Sdk.LinkDescriptor existingLink)
0x244cb  ldloca.s 8
0x244cd  call     instance bool valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<class Microsoft.Xrm.Sdk.Relationship, class Microsoft.Xrm.Sdk.EntityCollection>>::MoveNext()
0x244d2  brtrue.s loc_24482
0x244d4  leave.s  loc_244E4
0x244d6  ldloca.s 8
0x244d8  constrained. valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<class Microsoft.Xrm.Sdk.Relationship, class Microsoft.Xrm.Sdk.EntityCollection>>
0x244de  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x244e3  endfinally
0x244e4  ldarg.0
0x244e5  ldfld    class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.Xrm.Sdk.Entity> <GetChangeRequestsFromSubtree>d__81::localPath
0x244ea  ldloc.s  4
0x244ec  call     T0x2B00007F
0x244f1  stloc.s  6
0x244f3  ldarg.0
0x244f4  ldfld    class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.Xrm.Sdk.Entity> <GetChangeRequestsFromSubtree>d__81::path
0x244f9  ldloc.s  4
0x244fb  call     T0x2B00007F
0x24500  stloc.s  7
0x24502  ldloc.s  6
0x24504  brtrue   loc_24618
0x24509  ldloc.s  7
0x2450b  brtrue   loc_24618
0x24510  ldarg.0
0x24511  ldfld    class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.Xrm.Sdk.Entity> <GetChangeRequestsFromSubtree>d__81::localPath
0x24516  ldc.i4.1
0x24517  newarr   Microsoft.Xrm.Sdk.Entity
0x2451c  dup
0x2451d  ldc.i4.0
0x2451e  ldloc.s  4
0x24520  stelem.ref
0x24521  call     T0x2B000080
0x24526  stloc.s  0xB
0x24528  ldarg.0
0x24529  ldfld    class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.Xrm.Sdk.Entity> <GetChangeRequestsFromSubtree>d__81::path
0x2452e  ldc.i4.1
0x2452f  newarr   Microsoft.Xrm.Sdk.Entity
0x24534  dup
0x24535  ldc.i4.0
0x24536  ldloc.s  4
0x24538  stelem.ref
0x24539  call     T0x2B000080
0x2453e  stloc.s  0xC
0x24540  ldloc.s  5
0x24542  call     T0x2B00007A
0x24547  brtrue.s loc_2459A
0x24549  ldloc.s  4
0x2454b  callvirt instance valuetype [mscorlib]System.Nullable`1<valuetype Microsoft.Xrm.Sdk.EntityState> Microsoft.Xrm.Sdk.Entity::get_EntityState()
0x24550  stloc.s  0xE
0x24552  ldc.i4.0
0x24553  stloc.s  0xF
0x24555  ldloca.s 0xE
0x24557  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<valuetype Microsoft.Xrm.Sdk.EntityState>::GetValueOrDefault()
0x2455c  ldloc.s  0xF
0x2455e  ceq
0x24560  ldloca.s 0xE
0x24562  call     instance bool valuetype [mscorlib]System.Nullable`1<valuetype Microsoft.Xrm.Sdk.EntityState>::get_HasValue()
0x24567  and
0x24568  brtrue.s loc_24582
0x2456a  ldloc.2
0x2456b  ldarg.0
0x2456c  ldfld    class Microsoft.Xrm.Sdk.SaveChangesResultCollection <GetChangeRequestsFromSubtree>d__81::results
0x24571  ldloc.s  4
0x24573  ldloc.s  0xC
0x24575  ldarg.0
0x24576  ldfld    class [mscorlib]System.Collections.Generic.IList`1<class Microsoft.Xrm.Sdk.LinkDescriptor> <GetChangeRequestsFromSubtree>d__81::circularLinks
0x2457b  call     instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.Xrm.Sdk.SaveChangesResult> Microsoft.Xrm.Sdk.Client.OrganizationServiceContext::GetChangeRequestsFromChangedTree(class Microsoft.Xrm.Sdk.SaveChangesResultCollection results, class Microsoft.Xrm.Sdk.Entity entity, class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.Xrm.Sdk.Entity> path, class [mscorlib]System.Collections.Generic.IList`1<class Microsoft.Xrm.Sdk.LinkDescriptor> circularLinks)
0x24580  br.s     loc_245B8
0x24582  ldloc.2
0x24583  ldarg.0
0x24584  ldfld    class Microsoft.Xrm.Sdk.SaveChangesResultCollection <GetChangeRequestsFromSubtree>d__81::results
0x24589  ldloc.s  4
0x2458b  ldloc.s  0xC
0x2458d  ldarg.0
0x2458e  ldfld    class [mscorlib]System.Collections.Generic.IList`1<class Microsoft.Xrm.Sdk.LinkDescriptor> <GetChangeRequestsFromSubtree>d__81::circularLinks
0x24593  call     instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.Xrm.Sdk.SaveChangesResult> Microsoft.Xrm.Sdk.Client.OrganizationServiceContext::GetChangeRequestsFromUnchangedTree(class Microsoft.Xrm.Sdk.SaveChangesResultCollection results, class Microsoft.Xrm.Sdk.Entity entity, class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.Xrm.Sdk.Entity> path, class [mscorlib]System.Collections.Generic.IList`1<class Microsoft.Xrm.Sdk.LinkDescriptor> circularLinks)
0x24598  br.s     loc_245B8
0x2459a  ldloc.2
0x2459b  ldarg.0
0x2459c  ldfld    class Microsoft.Xrm.Sdk.SaveChangesResultCollection <GetChangeRequestsFromSubtree>d__81::results
0x245a1  ldloc.s  4
0x245a3  ldloc.s  0xB
0x245a5  ldarg.0
0x245a6  ldfld    class [mscorlib]System.Collections.Generic.IList`1<class Microsoft.Xrm.Sdk.LinkDescriptor> <GetChangeRequestsFromSubtree>d__81::localCircularLinks
0x245ab  ldloc.s  0xC
0x245ad  ldarg.0
0x245ae  ldfld    class [mscorlib]System.Collections.Generic.IList`1<class Microsoft.Xrm.Sdk.LinkDescriptor> <GetChangeRequestsFromSubtree>d__81::circularLinks
0x245b3  call     instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.Xrm.Sdk.SaveChangesResult> Microsoft.Xrm.Sdk.Client.OrganizationServiceContext::GetChangeRequestsFromSubtree(class Microsoft.Xrm.Sdk.SaveChangesResultCollection results, class Microsoft.Xrm.Sdk.Entity entity, class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.Xrm.Sdk.Entity> localPath, class [mscorlib]System.Collections.Generic.IList`1<class Microsoft.Xrm.Sdk.LinkDescriptor> localCircularLinks, class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.Xrm.Sdk.Entity> path, class [mscorlib]System.Collections.Generic.IList`1<class Microsoft.Xrm.Sdk.LinkDescriptor> circularLinks)
0x245b8  stloc.s  0xD
0x245ba  ldarg.0
0x245bb  ldloc.s  0xD
0x245bd  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.Xrm.Sdk.SaveChangesResult>::GetEnumerator()
0x245c2  stfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class Microsoft.Xrm.Sdk.SaveChangesResult> <GetChangeRequestsFromSubtree>d__81::<>7__wrap2
0x245c7  ldarg.0
0x245c8  ldc.i4.s 0xFC
0x245ca  stfld    int32 <GetChangeRequestsFromSubtree>d__81::<>1__state
0x245cf  br.s     loc_245FC
0x245d1  ldarg.0
0x245d2  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class Microsoft.Xrm.Sdk.SaveChangesResult> <GetChangeRequestsFromSubtree>d__81::<>7__wrap2
0x245d7  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class Microsoft.Xrm.Sdk.SaveChangesResult>::get_Current()
0x245dc  stloc.s  0x10
0x245de  ldarg.0
0x245df  ldloc.s  0x10
0x245e1  stfld    class Microsoft.Xrm.Sdk.SaveChangesResult <GetChangeRequestsFromSubtree>d__81::<>2__current
0x245e6  ldarg.0
0x245e7  ldc.i4.1
0x245e8  stfld    int32 <GetChangeRequestsFromSubtree>d__81::<>1__state
0x245ed  ldc.i4.1
0x245ee  stloc.0
0x245ef  leave    loc_246BB
0x245f4  ldarg.0
0x245f5  ldc.i4.s 0xFC
0x245f7  stfld    int32 <GetChangeRequestsFromSubtree>d__81::<>1__state
0x245fc  ldarg.0
0x245fd  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class Microsoft.Xrm.Sdk.SaveChangesResult> <GetChangeRequestsFromSubtree>d__81::<>7__wrap2
0x24602  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x24607  brtrue.s loc_245D1
0x24609  ldarg.0
0x2460a  call     instance void <GetChangeRequestsFromSubtree>d__81::<>m__Finally2()
0x2460f  ldarg.0
0x24610  ldnull
0x24611  stfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class Microsoft.Xrm.Sdk.SaveChangesResult> <GetChangeRequestsFromSubtree>d__81::<>7__wrap2
0x24616  br.s     loc_2468E
0x24618  ldloc.s  5
0x2461a  call     T0x2B00007A
0x2461f  brfalse.s loc_2468E
0x24621  ldloc.s  5
0x24623  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Xrm.Sdk.LinkDescriptor>::GetEnumerator()
0x24628  stloc.s  0x11
0x2462a  br.s     loc_24675
0x2462c  ldloca.s 0x11
0x2462e  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.Xrm.Sdk.LinkDescriptor>::get_Current()
0x24633  stloc.s  0x12
0x24635  ldloc.s  6
0x24637  brfalse.s loc_24648
0x24639  ldarg.0
0x2463a  ldfld    class [mscorlib]System.Collections.Generic.IList`1<class Microsoft.Xrm.Sdk.LinkDescriptor> <GetChangeRequestsFromSubtree>d__81::localCircularLinks
0x2463f  ldloc.s  0x12
0x24641  callvirt instance void class [mscorlib]System.Collections.Generic.ICollection`1<class Microsoft.Xrm.Sdk.LinkDescriptor>::Add(var<u1>)
0x24646  br.s     loc_24655
0x24648  ldarg.0
0x24649  ldfld    class [mscorlib]System.Collections.Generic.IList`1<class Microsoft.Xrm.Sdk.LinkDescriptor> <GetChangeRequestsFromSubtree>d__81::circularLinks
0x2464e  ldloc.s  0x12
0x24650  callvirt instance void class [mscorlib]System.Collections.Generic.ICollection`1<class Microsoft.Xrm.Sdk.LinkDescriptor>::Add(var<u1>)
0x24655  ldloc.2
0x24656  ldloc.s  0x12
0x24658  call     instance void Microsoft.Xrm.Sdk.Client.OrganizationServiceContext::DetachLinkTrackingAndRemoveEntity(class Microsoft.Xrm.Sdk.LinkDescriptor existingLink)
0x2465d  ldloc.s  0x12
0x2465f  callvirt instance class Microsoft.Xrm.Sdk.Entity Microsoft.Xrm.Sdk.LinkDescriptor::get_Source()
0x24664  call     void Microsoft.Xrm.Sdk.Client.OrganizationServiceContext::SetNewId(class Microsoft.Xrm.Sdk.Entity entity)
0x24669  ldloc.s  0x12
0x2466b  callvirt instance class Microsoft.Xrm.Sdk.Entity Microsoft.Xrm.Sdk.LinkDescriptor::get_Target()
0x24670  call     void Microsoft.Xrm.Sdk.Client.OrganizationServiceContext::SetNewId(class Microsoft.Xrm.Sdk.Entity entity)
0x24675  ldloca.s 0x11
0x24677  call     instance bool valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.Xrm.Sdk.LinkDescriptor>::MoveNext()
0x2467c  brtrue.s loc_2462C
0x2467e  leave.s  loc_2468E
0x24680  ldloca.s 0x11
0x24682  constrained. valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.Xrm.Sdk.LinkDescriptor>
0x24688  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x2468d  endfinally
0x2468e  ldarg.0
0x2468f  ldflda   valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class <>f__AnonymousType7`2<class Microsoft.Xrm.Sdk.Entity, class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<class Microsoft.Xrm.Sdk.Relationship, class Microsoft.Xrm.Sdk.EntityCollection>>>> <GetChangeRequestsFromSubtree>d__81::<>7__wrap1
0x24694  call     instance bool valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class <>f__AnonymousType7`2<class Microsoft.Xrm.Sdk.Entity, class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<class Microsoft.Xrm.Sdk.Relationship, class Microsoft.Xrm.Sdk.EntityCollection>>>>::MoveNext()
0x24699  brtrue   loc_2445A
0x2469e  ldarg.0
0x2469f  call     instance void <GetChangeRequestsFromSubtree>d__81::<>m__Finally1()
0x246a4  ldarg.0
0x246a5  ldflda   valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class <>f__AnonymousType7`2<class Microsoft.Xrm.Sdk.Entity, class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<class Microsoft.Xrm.Sdk.Relationship, class Microsoft.Xrm.Sdk.EntityCollection>>>> <GetChangeRequestsFromSubtree>d__81::<>7__wrap1
0x246aa  initobj  valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class <>f__AnonymousType7`2<class Microsoft.Xrm.Sdk.Entity, class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<class Microsoft.Xrm.Sdk.Relationship, class Microsoft.Xrm.Sdk.EntityCollection>>>>
0x246b0  ldc.i4.0
0x246b1  stloc.0
0x246b2  leave.s  loc_246BB
0x246b4  ldarg.0
0x246b5  call     instance void <GetChangeRequestsFromSubtree>d__81::System.IDisposable.Dispose()
0x246ba  endfinally
0x246bb  ldloc.0
0x246bc  ret
```
