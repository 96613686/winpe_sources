# <GetChangeRequestsFromUnchangedTree>d__80::MoveNext

- ea: `0x23d90`
- end: `0x241d3`
- name: `<GetChangeRequestsFromUnchangedTree>d__80::MoveNext`
- size: `1091`
- prototype: ``
- caller_count: `0`
- callee_count: `18`
- tags: ``

## callees

- `0x3880`
- `0x3930`
- `0x3970`
- `0x3990`
- `0x3c30`
- `0x3c90`
- `0x13b30`
- `0x13bd0`
- `0x145a0`
- `0x145d0`
- `0x14960`
- `0x14990`
- `0x23cc0`
- `0x23d30`
- `0x23d90`
- `0x241e0`
- `0x24200`
- `0x24220`

## pseudocode

```c

```

## disassembly

```asm
0x23d90  ldarg.0
0x23d91  ldfld    int32 <GetChangeRequestsFromUnchangedTree>d__80::<>1__state
0x23d96  stloc.1
0x23d97  ldarg.0
0x23d98  ldfld    class Microsoft.Xrm.Sdk.Client.OrganizationServiceContext <GetChangeRequestsFromUnchangedTree>d__80::<>4__this
0x23d9d  stloc.2
0x23d9e  ldloc.1
0x23d9f  switch   loc_23DB7, loc_23FDA, loc_24106
0x23db0  ldc.i4.0
0x23db1  stloc.0
0x23db2  leave    loc_241D1
0x23db7  ldarg.0
0x23db8  ldc.i4.m1
0x23db9  stfld    int32 <GetChangeRequestsFromUnchangedTree>d__80::<>1__state
0x23dbe  ldarg.0
0x23dbf  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Xrm.Sdk.LinkDescriptor>::.ctor()
0x23dc4  stfld    class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Xrm.Sdk.LinkDescriptor> <GetChangeRequestsFromUnchangedTree>d__80::<relatedLinks>5__2
0x23dc9  ldarg.0
0x23dca  ldfld    class Microsoft.Xrm.Sdk.Entity <GetChangeRequestsFromUnchangedTree>d__80::entity
0x23dcf  callvirt instance class Microsoft.Xrm.Sdk.RelatedEntityCollection Microsoft.Xrm.Sdk.Entity::get_RelatedEntities()
0x23dd4  ldsfld   class [mscorlib]System.Func`2<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<class Microsoft.Xrm.Sdk.Relationship, class Microsoft.Xrm.Sdk.EntityCollection>, class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.Xrm.Sdk.Entity>> <>c::<>9__80_0
0x23dd9  dup
0x23dda  brtrue.s loc_23DF3
0x23ddc  pop
0x23ddd  ldsfld   class <>c <>c::<>9
0x23de2  ldftn    instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.Xrm.Sdk.Entity> <>c::<GetChangeRequestsFromUnchangedTree>b__80_0(valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<class Microsoft.Xrm.Sdk.Relationship, class Microsoft.Xrm.Sdk.EntityCollection> relationship)
0x23de8  newobj   instance void class [mscorlib]System.Func`2<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<class Microsoft.Xrm.Sdk.Relationship, class Microsoft.Xrm.Sdk.EntityCollection>, class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.Xrm.Sdk.Entity>>::.ctor(object, native int)
0x23ded  dup
0x23dee  stsfld   class [mscorlib]System.Func`2<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<class Microsoft.Xrm.Sdk.Relationship, class Microsoft.Xrm.Sdk.EntityCollection>, class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.Xrm.Sdk.Entity>> <>c::<>9__80_0
0x23df3  ldsfld   class [mscorlib]System.Func`3<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<class Microsoft.Xrm.Sdk.Relationship, class Microsoft.Xrm.Sdk.EntityCollection>, class Microsoft.Xrm.Sdk.Entity, class <>f__AnonymousType5`2<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<class Microsoft.Xrm.Sdk.Relationship, class Microsoft.Xrm.Sdk.EntityCollection>, class Microsoft.Xrm.Sdk.Entity>> <>c::<>9__80_1
0x23df8  dup
0x23df9  brtrue.s loc_23E12
0x23dfb  pop
0x23dfc  ldsfld   class <>c <>c::<>9
0x23e01  ldftn    instance class <>f__AnonymousType5`2<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<class Microsoft.Xrm.Sdk.Relationship, class Microsoft.Xrm.Sdk.EntityCollection>, class Microsoft.Xrm.Sdk.Entity> <>c::<GetChangeRequestsFromUnchangedTree>b__80_1(valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<class Microsoft.Xrm.Sdk.Relationship, class Microsoft.Xrm.Sdk.EntityCollection> relationship, class Microsoft.Xrm.Sdk.Entity target)
0x23e07  newobj   instance void class [mscorlib]System.Func`3<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<class Microsoft.Xrm.Sdk.Relationship, class Microsoft.Xrm.Sdk.EntityCollection>, class Microsoft.Xrm.Sdk.Entity, class <>f__AnonymousType5`2<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<class Microsoft.Xrm.Sdk.Relationship, class Microsoft.Xrm.Sdk.EntityCollection>, class Microsoft.Xrm.Sdk.Entity>>::.ctor(object, native int)
0x23e0c  dup
0x23e0d  stsfld   class [mscorlib]System.Func`3<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<class Microsoft.Xrm.Sdk.Relationship, class Microsoft.Xrm.Sdk.EntityCollection>, class Microsoft.Xrm.Sdk.Entity, class <>f__AnonymousType5`2<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<class Microsoft.Xrm.Sdk.Relationship, class Microsoft.Xrm.Sdk.EntityCollection>, class Microsoft.Xrm.Sdk.Entity>> <>c::<>9__80_1
0x23e12  call     T0x2B00007B
0x23e17  ldsfld   class [mscorlib]System.Func`2<class <>f__AnonymousType5`2<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<class Microsoft.Xrm.Sdk.Relationship, class Microsoft.Xrm.Sdk.EntityCollection>, class Microsoft.Xrm.Sdk.Entity>, class Microsoft.Xrm.Sdk.Entity> <>c::<>9__80_2
0x23e1c  dup
0x23e1d  brtrue.s loc_23E36
0x23e1f  pop
0x23e20  ldsfld   class <>c <>c::<>9
0x23e25  ldftn    instance class Microsoft.Xrm.Sdk.Entity <>c::<GetChangeRequestsFromUnchangedTree>b__80_2(class <>f__AnonymousType5`2<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<class Microsoft.Xrm.Sdk.Relationship, class Microsoft.Xrm.Sdk.EntityCollection>, class Microsoft.Xrm.Sdk.Entity> <>h__TransparentIdentifier0)
0x23e2b  newobj   instance void class [mscorlib]System.Func`2<class <>f__AnonymousType5`2<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<class Microsoft.Xrm.Sdk.Relationship, class Microsoft.Xrm.Sdk.EntityCollection>, class Microsoft.Xrm.Sdk.Entity>, class Microsoft.Xrm.Sdk.Entity>::.ctor(object, native int)
0x23e30  dup
0x23e31  stsfld   class [mscorlib]System.Func`2<class <>f__AnonymousType5`2<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<class Microsoft.Xrm.Sdk.Relationship, class Microsoft.Xrm.Sdk.EntityCollection>, class Microsoft.Xrm.Sdk.Entity>, class Microsoft.Xrm.Sdk.Entity> <>c::<>9__80_2
0x23e36  ldsfld   class [mscorlib]System.Func`2<class <>f__AnonymousType5`2<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<class Microsoft.Xrm.Sdk.Relationship, class Microsoft.Xrm.Sdk.EntityCollection>, class Microsoft.Xrm.Sdk.Entity>, class <>f__AnonymousType6`2<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<class Microsoft.Xrm.Sdk.Relationship, class Microsoft.Xrm.Sdk.EntityCollection>, class Microsoft.Xrm.Sdk.Entity>> <>c::<>9__80_3
0x23e3b  dup
0x23e3c  brtrue.s loc_23E55
0x23e3e  pop
0x23e3f  ldsfld   class <>c <>c::<>9
0x23e44  ldftn    instance class <>f__AnonymousType6`2<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<class Microsoft.Xrm.Sdk.Relationship, class Microsoft.Xrm.Sdk.EntityCollection>, class Microsoft.Xrm.Sdk.Entity> <>c::<GetChangeRequestsFromUnchangedTree>b__80_3(class <>f__AnonymousType5`2<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<class Microsoft.Xrm.Sdk.Relationship, class Microsoft.Xrm.Sdk.EntityCollection>, class Microsoft.Xrm.Sdk.Entity> <>h__TransparentIdentifier0)
0x23e4a  newobj   instance void class [mscorlib]System.Func`2<class <>f__AnonymousType5`2<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<class Microsoft.Xrm.Sdk.Relationship, class Microsoft.Xrm.Sdk.EntityCollection>, class Microsoft.Xrm.Sdk.Entity>, class <>f__AnonymousType6`2<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<class Microsoft.Xrm.Sdk.Relationship, class Microsoft.Xrm.Sdk.EntityCollection>, class Microsoft.Xrm.Sdk.Entity>>::.ctor(object, native int)
0x23e4f  dup
0x23e50  stsfld   class [mscorlib]System.Func`2<class <>f__AnonymousType5`2<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<class Microsoft.Xrm.Sdk.Relationship, class Microsoft.Xrm.Sdk.EntityCollection>, class Microsoft.Xrm.Sdk.Entity>, class <>f__AnonymousType6`2<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<class Microsoft.Xrm.Sdk.Relationship, class Microsoft.Xrm.Sdk.EntityCollection>, class Microsoft.Xrm.Sdk.Entity>> <>c::<>9__80_3
0x23e55  call     T0x2B00007C
0x23e5a  ldsfld   class [mscorlib]System.Func`2<class [System.Core]System.Linq.IGrouping`2<class Microsoft.Xrm.Sdk.Entity, class <>f__AnonymousType6`2<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<class Microsoft.Xrm.Sdk.Relationship, class Microsoft.Xrm.Sdk.EntityCollection>, class Microsoft.Xrm.Sdk.Entity>>, class <>f__AnonymousType7`2<class Microsoft.Xrm.Sdk.Entity, class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<class Microsoft.Xrm.Sdk.Relationship, class Microsoft.Xrm.Sdk.EntityCollection>>>> <>c::<>9__80_4
0x23e5f  dup
0x23e60  brtrue.s loc_23E79
0x23e62  pop
0x23e63  ldsfld   class <>c <>c::<>9
0x23e68  ldftn    instance class <>f__AnonymousType7`2<class Microsoft.Xrm.Sdk.Entity, class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<class Microsoft.Xrm.Sdk.Relationship, class Microsoft.Xrm.Sdk.EntityCollection>>> <>c::<GetChangeRequestsFromUnchangedTree>b__80_4(class [System.Core]System.Linq.IGrouping`2<class Microsoft.Xrm.Sdk.Entity, class <>f__AnonymousType6`2<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<class Microsoft.Xrm.Sdk.Relationship, class Microsoft.Xrm.Sdk.EntityCollection>, class Microsoft.Xrm.Sdk.Entity>> grp)
0x23e6e  newobj   instance void class [mscorlib]System.Func`2<class [System.Core]System.Linq.IGrouping`2<class Microsoft.Xrm.Sdk.Entity, class <>f__AnonymousType6`2<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<class Microsoft.Xrm.Sdk.Relationship, class Microsoft.Xrm.Sdk.EntityCollection>, class Microsoft.Xrm.Sdk.Entity>>, class <>f__AnonymousType7`2<class Microsoft.Xrm.Sdk.Entity, class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<class Microsoft.Xrm.Sdk.Relationship, class Microsoft.Xrm.Sdk.EntityCollection>>>>::.ctor(object, native int)
0x23e73  dup
0x23e74  stsfld   class [mscorlib]System.Func`2<class [System.Core]System.Linq.IGrouping`2<class Microsoft.Xrm.Sdk.Entity, class <>f__AnonymousType6`2<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<class Microsoft.Xrm.Sdk.Relationship, class Microsoft.Xrm.Sdk.EntityCollection>, class Microsoft.Xrm.Sdk.Entity>>, class <>f__AnonymousType7`2<class Microsoft.Xrm.Sdk.Entity, class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<class Microsoft.Xrm.Sdk.Relationship, class Microsoft.Xrm.Sdk.EntityCollection>>>> <>c::<>9__80_4
0x23e79  call     T0x2B00007D
0x23e7e  call     T0x2B00007E
0x23e83  stloc.3
0x23e84  ldarg.0
0x23e85  ldloc.3
0x23e86  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<class <>f__AnonymousType7`2<class Microsoft.Xrm.Sdk.Entity, class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<class Microsoft.Xrm.Sdk.Relationship, class Microsoft.Xrm.Sdk.EntityCollection>>>>::GetEnumerator()
0x23e8b  stfld    valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class <>f__AnonymousType7`2<class Microsoft.Xrm.Sdk.Entity, class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<class Microsoft.Xrm.Sdk.Relationship, class Microsoft.Xrm.Sdk.EntityCollection>>>> <GetChangeRequestsFromUnchangedTree>d__80::<>7__wrap2
0x23e90  ldarg.0
0x23e91  ldc.i4.s 0xFD
0x23e93  stfld    int32 <GetChangeRequestsFromUnchangedTree>d__80::<>1__state
0x23e98  br       loc_24086
0x23e9d  ldarg.0
0x23e9e  ldflda   valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class <>f__AnonymousType7`2<class Microsoft.Xrm.Sdk.Entity, class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<class Microsoft.Xrm.Sdk.Relationship, class Microsoft.Xrm.Sdk.EntityCollection>>>> <GetChangeRequestsFromUnchangedTree>d__80::<>7__wrap2
0x23ea3  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class <>f__AnonymousType7`2<class Microsoft.Xrm.Sdk.Entity, class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<class Microsoft.Xrm.Sdk.Relationship, class Microsoft.Xrm.Sdk.EntityCollection>>>>::get_Current()
0x23ea8  dup
0x23ea9  callvirt instance var<u1> class <>f__AnonymousType7`2<class Microsoft.Xrm.Sdk.Entity, class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<class Microsoft.Xrm.Sdk.Relationship, class Microsoft.Xrm.Sdk.EntityCollection>>>::get_Target()
0x23eae  stloc.s  4
0x23eb0  ldarg.0
0x23eb1  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Xrm.Sdk.LinkDescriptor>::.ctor()
0x23eb6  stfld    class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Xrm.Sdk.LinkDescriptor> <GetChangeRequestsFromUnchangedTree>d__80::<addedLinks>5__4
0x23ebb  callvirt instance var<u1> class <>f__AnonymousType7`2<class Microsoft.Xrm.Sdk.Entity, class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<class Microsoft.Xrm.Sdk.Relationship, class Microsoft.Xrm.Sdk.EntityCollection>>>::get_Relationships()
0x23ec0  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<class Microsoft.Xrm.Sdk.Relationship, class Microsoft.Xrm.Sdk.EntityCollection>>::GetEnumerator()
0x23ec5  stloc.s  5
0x23ec7  br.s     loc_23F0C
0x23ec9  ldloca.s 5
0x23ecb  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<class Microsoft.Xrm.Sdk.Relationship, class Microsoft.Xrm.Sdk.EntityCollection>>::get_Current()
0x23ed0  stloc.s  6
0x23ed2  ldloc.2
0x23ed3  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<class Microsoft.Xrm.Sdk.LinkDescriptor, class Microsoft.Xrm.Sdk.LinkDescriptor> Microsoft.Xrm.Sdk.Client.OrganizationServiceContext::_bindings
0x23ed8  ldarg.0
0x23ed9  ldfld    class Microsoft.Xrm.Sdk.Entity <GetChangeRequestsFromUnchangedTree>d__80::entity
0x23ede  ldloca.s 6
0x23ee0  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<class Microsoft.Xrm.Sdk.Relationship, class Microsoft.Xrm.Sdk.EntityCollection>::get_Key()
0x23ee5  ldloc.s  4
0x23ee7  newobj   instance void Microsoft.Xrm.Sdk.LinkDescriptor::.ctor(class Microsoft.Xrm.Sdk.Entity source, class Microsoft.Xrm.Sdk.Relationship relationship, class Microsoft.Xrm.Sdk.Entity target)
0x23eec  ldloca.s 7
0x23eee  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<class Microsoft.Xrm.Sdk.LinkDescriptor, class Microsoft.Xrm.Sdk.LinkDescriptor>::TryGetValue(var<u1>, !!T0)
0x23ef3  brfalse.s loc_23F0C
0x23ef5  ldloc.s  7
0x23ef7  callvirt instance valuetype Microsoft.Xrm.Sdk.EntityStates Microsoft.Xrm.Sdk.Descriptor::get_State()
0x23efc  ldc.i4.4
0x23efd  bne.un.s loc_23F0C
0x23eff  ldarg.0
0x23f00  ldfld    class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Xrm.Sdk.LinkDescriptor> <GetChangeRequestsFromUnchangedTree>d__80::<addedLinks>5__4
0x23f05  ldloc.s  7
0x23f07  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Xrm.Sdk.LinkDescriptor>::Add(var<u1>)
0x23f0c  ldloca.s 5
0x23f0e  call     instance bool valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<class Microsoft.Xrm.Sdk.Relationship, class Microsoft.Xrm.Sdk.EntityCollection>>::MoveNext()
0x23f13  brtrue.s loc_23EC9
0x23f15  leave.s  loc_23F25
0x23f17  ldloca.s 5
0x23f19  constrained. valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<class Microsoft.Xrm.Sdk.Relationship, class Microsoft.Xrm.Sdk.EntityCollection>>
0x23f1f  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x23f24  endfinally
0x23f25  ldarg.0
0x23f26  ldfld    class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.Xrm.Sdk.Entity> <GetChangeRequestsFromUnchangedTree>d__80::path
0x23f2b  ldloc.s  4
0x23f2d  call     T0x2B00007F
0x23f32  brtrue   loc_2401C
0x23f37  ldarg.0
0x23f38  ldfld    class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.Xrm.Sdk.Entity> <GetChangeRequestsFromUnchangedTree>d__80::path
0x23f3d  ldc.i4.1
0x23f3e  newarr   Microsoft.Xrm.Sdk.Entity
0x23f43  dup
0x23f44  ldc.i4.0
0x23f45  ldloc.s  4
0x23f47  stelem.ref
0x23f48  call     T0x2B000080
0x23f4d  stloc.s  8
0x23f4f  ldloc.s  4
0x23f51  callvirt instance valuetype [mscorlib]System.Nullable`1<valuetype Microsoft.Xrm.Sdk.EntityState> Microsoft.Xrm.Sdk.Entity::get_EntityState()
0x23f56  stloc.s  0xA
0x23f58  ldc.i4.0
0x23f59  stloc.s  0xB
0x23f5b  ldloca.s 0xA
0x23f5d  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<valuetype Microsoft.Xrm.Sdk.EntityState>::GetValueOrDefault()
0x23f62  ldloc.s  0xB
0x23f64  ceq
0x23f66  ldloca.s 0xA
0x23f68  call     instance bool valuetype [mscorlib]System.Nullable`1<valuetype Microsoft.Xrm.Sdk.EntityState>::get_HasValue()
0x23f6d  and
0x23f6e  brtrue.s loc_23F88
0x23f70  ldloc.2
0x23f71  ldarg.0
0x23f72  ldfld    class Microsoft.Xrm.Sdk.SaveChangesResultCollection <GetChangeRequestsFromUnchangedTree>d__80::results
0x23f77  ldloc.s  4
0x23f79  ldloc.s  8
0x23f7b  ldarg.0
0x23f7c  ldfld    class [mscorlib]System.Collections.Generic.IList`1<class Microsoft.Xrm.Sdk.LinkDescriptor> <GetChangeRequestsFromUnchangedTree>d__80::circularLinks
0x23f81  call     instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.Xrm.Sdk.SaveChangesResult> Microsoft.Xrm.Sdk.Client.OrganizationServiceContext::GetChangeRequestsFromChangedTree(class Microsoft.Xrm.Sdk.SaveChangesResultCollection results, class Microsoft.Xrm.Sdk.Entity entity, class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.Xrm.Sdk.Entity> path, class [mscorlib]System.Collections.Generic.IList`1<class Microsoft.Xrm.Sdk.LinkDescriptor> circularLinks)
0x23f86  br.s     loc_23F9E
0x23f88  ldloc.2
0x23f89  ldarg.0
0x23f8a  ldfld    class Microsoft.Xrm.Sdk.SaveChangesResultCollection <GetChangeRequestsFromUnchangedTree>d__80::results
0x23f8f  ldloc.s  4
0x23f91  ldloc.s  8
0x23f93  ldarg.0
0x23f94  ldfld    class [mscorlib]System.Collections.Generic.IList`1<class Microsoft.Xrm.Sdk.LinkDescriptor> <GetChangeRequestsFromUnchangedTree>d__80::circularLinks
0x23f99  call     instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.Xrm.Sdk.SaveChangesResult> Microsoft.Xrm.Sdk.Client.OrganizationServiceContext::GetChangeRequestsFromUnchangedTree(class Microsoft.Xrm.Sdk.SaveChangesResultCollection results, class Microsoft.Xrm.Sdk.Entity entity, class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.Xrm.Sdk.Entity> path, class [mscorlib]System.Collections.Generic.IList`1<class Microsoft.Xrm.Sdk.LinkDescriptor> circularLinks)
0x23f9e  stloc.s  9
0x23fa0  ldarg.0
0x23fa1  ldloc.s  9
0x23fa3  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.Xrm.Sdk.SaveChangesResult>::GetEnumerator()
0x23fa8  stfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class Microsoft.Xrm.Sdk.SaveChangesResult> <GetChangeRequestsFromUnchangedTree>d__80::<>7__wrap4
0x23fad  ldarg.0
0x23fae  ldc.i4.s 0xFC
0x23fb0  stfld    int32 <GetChangeRequestsFromUnchangedTree>d__80::<>1__state
0x23fb5  br.s     loc_23FE2
0x23fb7  ldarg.0
0x23fb8  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class Microsoft.Xrm.Sdk.SaveChangesResult> <GetChangeRequestsFromUnchangedTree>d__80::<>7__wrap4
0x23fbd  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class Microsoft.Xrm.Sdk.SaveChangesResult>::get_Current()
0x23fc2  stloc.s  0xC
0x23fc4  ldarg.0
0x23fc5  ldloc.s  0xC
0x23fc7  stfld    class Microsoft.Xrm.Sdk.SaveChangesResult <GetChangeRequestsFromUnchangedTree>d__80::<>2__current
0x23fcc  ldarg.0
0x23fcd  ldc.i4.1
0x23fce  stfld    int32 <GetChangeRequestsFromUnchangedTree>d__80::<>1__state
0x23fd3  ldc.i4.1
0x23fd4  stloc.0
0x23fd5  leave    loc_241D1
0x23fda  ldarg.0
0x23fdb  ldc.i4.s 0xFC
0x23fdd  stfld    int32 <GetChangeRequestsFromUnchangedTree>d__80::<>1__state
0x23fe2  ldarg.0
0x23fe3  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class Microsoft.Xrm.Sdk.SaveChangesResult> <GetChangeRequestsFromUnchangedTree>d__80::<>7__wrap4
0x23fe8  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x23fed  brtrue.s loc_23FB7
0x23fef  ldarg.0
0x23ff0  call     instance void <GetChangeRequestsFromUnchangedTree>d__80::<>m__Finally2()
0x23ff5  ldarg.0
0x23ff6  ldnull
0x23ff7  stfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class Microsoft.Xrm.Sdk.SaveChangesResult> <GetChangeRequestsFromUnchangedTree>d__80::<>7__wrap4
0x23ffc  ldarg.0
0x23ffd  ldfld    class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Xrm.Sdk.LinkDescriptor> <GetChangeRequestsFromUnchangedTree>d__80::<addedLinks>5__4
0x24002  call     T0x2B00007A
0x24007  brfalse.s loc_2407F
0x24009  ldarg.0
0x2400a  ldfld    class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Xrm.Sdk.LinkDescriptor> <GetChangeRequestsFromUnchangedTree>d__80::<relatedLinks>5__2
0x2400f  ldarg.0
0x24010  ldfld    class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Xrm.Sdk.LinkDescriptor> <GetChangeRequestsFromUnchangedTree>d__80::<addedLinks>5__4
0x24015  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Xrm.Sdk.LinkDescriptor>::AddRange(class [mscorlib]System.Collections.Generic.IEnumerable`1<var<u1>>)
0x2401a  br.s     loc_2407F
0x2401c  ldarg.0
0x2401d  ldfld    class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Xrm.Sdk.LinkDescriptor> <GetChangeRequestsFromUnchangedTree>d__80::<addedLinks>5__4
0x24022  call     T0x2B00007A
0x24027  brfalse.s loc_2407F
0x24029  ldarg.0
0x2402a  ldfld    class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Xrm.Sdk.LinkDescriptor> <GetChangeRequestsFromUnchangedTree>d__80::<addedLinks>5__4
0x2402f  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Xrm.Sdk.LinkDescriptor>::GetEnumerator()
0x24034  stloc.s  0xD
0x24036  br.s     loc_24066
0x24038  ldloca.s 0xD
0x2403a  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.Xrm.Sdk.LinkDescriptor>::get_Current()
0x2403f  stloc.s  0xE
0x24041  ldarg.0
0x24042  ldfld    class [mscorlib]System.Collections.Generic.IList`1<class Microsoft.Xrm.Sdk.LinkDescriptor> <GetChangeRequestsFromUnchangedTree>d__80::circularLinks
0x24047  ldloc.s  0xE
0x24049  callvirt instance void class [mscorlib]System.Collections.Generic.ICollection`1<class Microsoft.Xrm.Sdk.LinkDescriptor>::Add(var<u1>)
0x2404e  ldloc.s  0xE
0x24050  callvirt instance class Microsoft.Xrm.Sdk.Entity Microsoft.Xrm.Sdk.LinkDescriptor::get_Source()
0x24055  call     void Microsoft.Xrm.Sdk.Client.OrganizationServiceContext::SetNewId(class Microsoft.Xrm.Sdk.Entity entity)
0x2405a  ldloc.s  0xE
0x2405c  callvirt instance class Microsoft.Xrm.Sdk.Entity Microsoft.Xrm.Sdk.LinkDescriptor::get_Target()
0x24061  call     void Microsoft.Xrm.Sdk.Client.OrganizationServiceContext::SetNewId(class Microsoft.Xrm.Sdk.Entity entity)
0x24066  ldloca.s 0xD
0x24068  call     instance bool valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.Xrm.Sdk.LinkDescriptor>::MoveNext()
0x2406d  brtrue.s loc_24038
0x2406f  leave.s  loc_2407F
0x24071  ldloca.s 0xD
0x24073  constrained. valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.Xrm.Sdk.LinkDescriptor>
0x24079  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x2407e  endfinally
0x2407f  ldarg.0
0x24080  ldnull
0x24081  stfld    class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Xrm.Sdk.LinkDescriptor> <GetChangeRequestsFromUnchangedTree>d__80::<addedLinks>5__4
0x24086  ldarg.0
0x24087  ldflda   valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class <>f__AnonymousType7`2<class Microsoft.Xrm.Sdk.Entity, class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<class Microsoft.Xrm.Sdk.Relationship, class Microsoft.Xrm.Sdk.EntityCollection>>>> <GetChangeRequestsFromUnchangedTree>d__80::<>7__wrap2
0x2408c  call     instance bool valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class <>f__AnonymousType7`2<class Microsoft.Xrm.Sdk.Entity, class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<class Microsoft.Xrm.Sdk.Relationship, class Microsoft.Xrm.Sdk.EntityCollection>>>>::MoveNext()
0x24091  brtrue   loc_23E9D
0x24096  ldarg.0
0x24097  call     instance void <GetChangeRequestsFromUnchangedTree>d__80::<>m__Finally1()
0x2409c  ldarg.0
0x2409d  ldflda   valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class <>f__AnonymousType7`2<class Microsoft.Xrm.Sdk.Entity, class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<class Microsoft.Xrm.Sdk.Relationship, class Microsoft.Xrm.Sdk.EntityCollection>>>> <GetChangeRequestsFromUnchangedTree>d__80::<>7__wrap2
0x240a2  initobj  valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class <>f__AnonymousType7`2<class Microsoft.Xrm.Sdk.Entity, class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<class Microsoft.Xrm.Sdk.Relationship, class Microsoft.Xrm.Sdk.EntityCollection>>>>
0x240a8  ldarg.0
0x240a9  ldfld    class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Xrm.Sdk.LinkDescriptor> <GetChangeRequestsFromUnchangedTree>d__80::<relatedLinks>5__2
0x240ae  call     T0x2B00007A
0x240b3  brfalse  loc_241B4
0x240b8  ldloc.2
0x240b9  ldarg.0
0x240ba  ldfld    class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Xrm.Sdk.LinkDescriptor> <GetChangeRequestsFromUnchangedTree>d__80::<relatedLinks>5__2
0x240bf  ldarg.0
0x240c0  ldfld    class Microsoft.Xrm.Sdk.SaveChangesResultCollection <GetChangeRequestsFromUnchangedTree>d__80::results
0x240c5  call     instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.Xrm.Sdk.SaveChangesResult> Microsoft.Xrm.Sdk.Client.OrganizationServiceContext::ToAssociateResults(class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.Xrm.Sdk.LinkDescriptor> links, class [mscorlib]System.Collections.Generic.IList`1<class Microsoft.Xrm.Sdk.SaveChangesResult> results)
0x240ca  stloc.s  0xF
0x240cc  ldarg.0
0x240cd  ldloc.s  0xF
0x240cf  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.Xrm.Sdk.SaveChangesResult>::GetEnumerator()
0x240d4  stfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class Microsoft.Xrm.Sdk.SaveChangesResult> <GetChangeRequestsFromUnchangedTree>d__80::<>7__wrap4
0x240d9  ldarg.0
0x240da  ldc.i4.s 0xFB
0x240dc  stfld    int32 <GetChangeRequestsFromUnchangedTree>d__80::<>1__state
0x240e1  br.s     loc_2410E
0x240e3  ldarg.0
0x240e4  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class Microsoft.Xrm.Sdk.SaveChangesResult> <GetChangeRequestsFromUnchangedTree>d__80::<>7__wrap4
0x240e9  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class Microsoft.Xrm.Sdk.SaveChangesResult>::get_Current()
0x240ee  stloc.s  0x10
0x240f0  ldarg.0
0x240f1  ldloc.s  0x10
0x240f3  stfld    class Microsoft.Xrm.Sdk.SaveChangesResult <GetChangeRequestsFromUnchangedTree>d__80::<>2__current
0x240f8  ldarg.0
0x240f9  ldc.i4.2
0x240fa  stfld    int32 <GetChangeRequestsFromUnchangedTree>d__80::<>1__state
0x240ff  ldc.i4.1
0x24100  stloc.0
0x24101  leave    loc_241D1
0x24106  ldarg.0
0x24107  ldc.i4.s 0xFB
0x24109  stfld    int32 <GetChangeRequestsFromUnchangedTree>d__80::<>1__state
0x2410e  ldarg.0
0x2410f  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class Microsoft.Xrm.Sdk.SaveChangesResult> <GetChangeRequestsFromUnchangedTree>d__80::<>7__wrap4
0x24114  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x24119  brtrue.s loc_240E3
0x2411b  ldarg.0
0x2411c  call     instance void <GetChangeRequestsFromUnchangedTree>d__80::<>m__Finally3()
0x24121  ldarg.0
0x24122  ldnull
0x24123  stfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class Microsoft.Xrm.Sdk.SaveChangesResult> <GetChangeRequestsFromUnchangedTree>d__80::<>7__wrap4
0x24128  ldarg.0
0x24129  ldfld    class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Xrm.Sdk.LinkDescriptor> <GetChangeRequestsFromUnchangedTree>d__80::<relatedLinks>5__2
0x2412e  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Xrm.Sdk.LinkDescriptor>::GetEnumerator()
0x24133  stloc.s  0xD
  ... truncated ...
```
