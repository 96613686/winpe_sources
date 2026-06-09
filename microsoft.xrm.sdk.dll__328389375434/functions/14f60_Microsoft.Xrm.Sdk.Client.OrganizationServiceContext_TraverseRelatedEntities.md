# Microsoft.Xrm.Sdk.Client.OrganizationServiceContext::TraverseRelatedEntities

- ea: `0x14f60`
- end: `0x14ff6`
- name: `Microsoft.Xrm.Sdk.Client.OrganizationServiceContext::TraverseRelatedEntities`
- size: `150`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x135a0`
- `0x13dd0`
- `0x248a0`

## callees

- `0x3c90`
- `0x14f60`
- `0x24b00`

## pseudocode

```c

```

## disassembly

```asm
0x14f60  newobj   instance void <>c__DisplayClass101_0::.ctor()
0x14f65  stloc.0
0x14f66  ldloc.0
0x14f67  ldarg.0
0x14f68  stfld    class Microsoft.Xrm.Sdk.Entity <>c__DisplayClass101_0::entity
0x14f6d  ldloc.0
0x14f6e  ldfld    class Microsoft.Xrm.Sdk.Entity <>c__DisplayClass101_0::entity
0x14f73  callvirt instance class Microsoft.Xrm.Sdk.RelatedEntityCollection Microsoft.Xrm.Sdk.Entity::get_RelatedEntities()
0x14f78  call     T0x2B000057
0x14f7d  ldsfld   class [mscorlib]System.Func`2<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<class Microsoft.Xrm.Sdk.Relationship, class Microsoft.Xrm.Sdk.EntityCollection>, class <>f__AnonymousType8`2<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<class Microsoft.Xrm.Sdk.Relationship, class Microsoft.Xrm.Sdk.EntityCollection>, class Microsoft.Xrm.Sdk.Relationship>> <>c::<>9__101_0
0x14f82  dup
0x14f83  brtrue.s loc_14F9C
0x14f85  pop
0x14f86  ldsfld   class <>c <>c::<>9
0x14f8b  ldftn    instance class <>f__AnonymousType8`2<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<class Microsoft.Xrm.Sdk.Relationship, class Microsoft.Xrm.Sdk.EntityCollection>, class Microsoft.Xrm.Sdk.Relationship> <>c::<TraverseRelatedEntities>b__101_0(valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<class Microsoft.Xrm.Sdk.Relationship, class Microsoft.Xrm.Sdk.EntityCollection> relatedEntity)
0x14f91  newobj   instance void class [mscorlib]System.Func`2<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<class Microsoft.Xrm.Sdk.Relationship, class Microsoft.Xrm.Sdk.EntityCollection>, class <>f__AnonymousType8`2<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<class Microsoft.Xrm.Sdk.Relationship, class Microsoft.Xrm.Sdk.EntityCollection>, class Microsoft.Xrm.Sdk.Relationship>>::.ctor(object, native int)
0x14f96  dup
0x14f97  stsfld   class [mscorlib]System.Func`2<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<class Microsoft.Xrm.Sdk.Relationship, class Microsoft.Xrm.Sdk.EntityCollection>, class <>f__AnonymousType8`2<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<class Microsoft.Xrm.Sdk.Relationship, class Microsoft.Xrm.Sdk.EntityCollection>, class Microsoft.Xrm.Sdk.Relationship>> <>c::<>9__101_0
0x14f9c  call     T0x2B000058
0x14fa1  ldsfld   class [mscorlib]System.Func`2<class <>f__AnonymousType8`2<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<class Microsoft.Xrm.Sdk.Relationship, class Microsoft.Xrm.Sdk.EntityCollection>, class Microsoft.Xrm.Sdk.Relationship>, class <>f__AnonymousType9`2<class <>f__AnonymousType8`2<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<class Microsoft.Xrm.Sdk.Relationship, class Microsoft.Xrm.Sdk.EntityCollection>, class Microsoft.Xrm.Sdk.Relationship>, class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Xrm.Sdk.Entity>>> <>c::<>9__101_1
0x14fa6  dup
0x14fa7  brtrue.s loc_14FC0
0x14fa9  pop
0x14faa  ldsfld   class <>c <>c::<>9
0x14faf  ldftn    instance class <>f__AnonymousType9`2<class <>f__AnonymousType8`2<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<class Microsoft.Xrm.Sdk.Relationship, class Microsoft.Xrm.Sdk.EntityCollection>, class Microsoft.Xrm.Sdk.Relationship>, class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Xrm.Sdk.Entity>> <>c::<TraverseRelatedEntities>b__101_1(class <>f__AnonymousType8`2<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<class Microsoft.Xrm.Sdk.Relationship, class Microsoft.Xrm.Sdk.EntityCollection>, class Microsoft.Xrm.Sdk.Relationship> <>h__TransparentIdentifier0)
0x14fb5  newobj   instance void class [mscorlib]System.Func`2<class <>f__AnonymousType8`2<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<class Microsoft.Xrm.Sdk.Relationship, class Microsoft.Xrm.Sdk.EntityCollection>, class Microsoft.Xrm.Sdk.Relationship>, class <>f__AnonymousType9`2<class <>f__AnonymousType8`2<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<class Microsoft.Xrm.Sdk.Relationship, class Microsoft.Xrm.Sdk.EntityCollection>, class Microsoft.Xrm.Sdk.Relationship>, class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Xrm.Sdk.Entity>>>::.ctor(object, native int)
0x14fba  dup
0x14fbb  stsfld   class [mscorlib]System.Func`2<class <>f__AnonymousType8`2<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<class Microsoft.Xrm.Sdk.Relationship, class Microsoft.Xrm.Sdk.EntityCollection>, class Microsoft.Xrm.Sdk.Relationship>, class <>f__AnonymousType9`2<class <>f__AnonymousType8`2<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<class Microsoft.Xrm.Sdk.Relationship, class Microsoft.Xrm.Sdk.EntityCollection>, class Microsoft.Xrm.Sdk.Relationship>, class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Xrm.Sdk.Entity>>> <>c::<>9__101_1
0x14fc0  call     T0x2B000059
0x14fc5  ldsfld   class [mscorlib]System.Func`2<class <>f__AnonymousType9`2<class <>f__AnonymousType8`2<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<class Microsoft.Xrm.Sdk.Relationship, class Microsoft.Xrm.Sdk.EntityCollection>, class Microsoft.Xrm.Sdk.Relationship>, class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Xrm.Sdk.Entity>>, class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.Xrm.Sdk.Entity>> <>c::<>9__101_2
0x14fca  dup
0x14fcb  brtrue.s loc_14FE4
0x14fcd  pop
0x14fce  ldsfld   class <>c <>c::<>9
0x14fd3  ldftn    instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.Xrm.Sdk.Entity> <>c::<TraverseRelatedEntities>b__101_2(class <>f__AnonymousType9`2<class <>f__AnonymousType8`2<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<class Microsoft.Xrm.Sdk.Relationship, class Microsoft.Xrm.Sdk.EntityCollection>, class Microsoft.Xrm.Sdk.Relationship>, class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Xrm.Sdk.Entity>> <>h__TransparentIdentifier1)
0x14fd9  newobj   instance void class [mscorlib]System.Func`2<class <>f__AnonymousType9`2<class <>f__AnonymousType8`2<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<class Microsoft.Xrm.Sdk.Relationship, class Microsoft.Xrm.Sdk.EntityCollection>, class Microsoft.Xrm.Sdk.Relationship>, class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Xrm.Sdk.Entity>>, class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.Xrm.Sdk.Entity>>::.ctor(object, native int)
0x14fde  dup
0x14fdf  stsfld   class [mscorlib]System.Func`2<class <>f__AnonymousType9`2<class <>f__AnonymousType8`2<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<class Microsoft.Xrm.Sdk.Relationship, class Microsoft.Xrm.Sdk.EntityCollection>, class Microsoft.Xrm.Sdk.Relationship>, class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Xrm.Sdk.Entity>>, class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.Xrm.Sdk.Entity>> <>c::<>9__101_2
0x14fe4  ldloc.0
0x14fe5  ldftn    instance class [mscorlib]System.Tuple`3<class Microsoft.Xrm.Sdk.Entity, class Microsoft.Xrm.Sdk.Relationship, class Microsoft.Xrm.Sdk.Entity> <>c__DisplayClass101_0::<TraverseRelatedEntities>b__3(class <>f__AnonymousType9`2<class <>f__AnonymousType8`2<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<class Microsoft.Xrm.Sdk.Relationship, class Microsoft.Xrm.Sdk.EntityCollection>, class Microsoft.Xrm.Sdk.Relationship>, class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Xrm.Sdk.Entity>> <>h__TransparentIdentifier1, class Microsoft.Xrm.Sdk.Entity target)
0x14feb  newobj   instance void class [mscorlib]System.Func`3<class <>f__AnonymousType9`2<class <>f__AnonymousType8`2<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<class Microsoft.Xrm.Sdk.Relationship, class Microsoft.Xrm.Sdk.EntityCollection>, class Microsoft.Xrm.Sdk.Relationship>, class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Xrm.Sdk.Entity>>, class Microsoft.Xrm.Sdk.Entity, class [mscorlib]System.Tuple`3<class Microsoft.Xrm.Sdk.Entity, class Microsoft.Xrm.Sdk.Relationship, class Microsoft.Xrm.Sdk.Entity>>::.ctor(object, native int)
0x14ff0  call     T0x2B00005A
0x14ff5  ret
```
