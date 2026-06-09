# Microsoft.Xrm.Sdk.Client.OrganizationServiceContext::AddRelationshipIfNotContains

- ea: `0x14c70`
- end: `0x14cd9`
- name: `Microsoft.Xrm.Sdk.Client.OrganizationServiceContext::AddRelationshipIfNotContains`
- size: `105`
- prototype: ``
- caller_count: `3`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x136e0`
- `0x13be0`
- `0x14b40`

## callees

- `0x2e40`
- `0x2e60`
- `0x2f70`
- `0x3b90`
- `0x3c90`
- `0x14c70`

## pseudocode

```c

```

## disassembly

```asm
0x14c70  ldarg.0
0x14c71  callvirt instance class Microsoft.Xrm.Sdk.RelatedEntityCollection Microsoft.Xrm.Sdk.Entity::get_RelatedEntities()
0x14c76  ldarg.1
0x14c77  callvirt instance bool class Microsoft.Xrm.Sdk.DataCollection`2<class Microsoft.Xrm.Sdk.Relationship, class Microsoft.Xrm.Sdk.EntityCollection>::Contains(var<u1>)
0x14c7c  brtrue.s loc_14CA8
0x14c7e  ldc.i4.1
0x14c7f  newarr   Microsoft.Xrm.Sdk.Entity
0x14c84  dup
0x14c85  ldc.i4.0
0x14c86  ldarg.2
0x14c87  stelem.ref
0x14c88  newobj   instance void Microsoft.Xrm.Sdk.EntityCollection::.ctor(class [mscorlib]System.Collections.Generic.IList`1<class Microsoft.Xrm.Sdk.Entity> list)
0x14c8d  stloc.0
0x14c8e  ldloc.0
0x14c8f  ldarg.2
0x14c90  callvirt instance string Microsoft.Xrm.Sdk.Entity::get_LogicalName()
0x14c95  callvirt instance void Microsoft.Xrm.Sdk.EntityCollection::set_EntityName(string value)
0x14c9a  ldarg.0
0x14c9b  callvirt instance class Microsoft.Xrm.Sdk.RelatedEntityCollection Microsoft.Xrm.Sdk.Entity::get_RelatedEntities()
0x14ca0  ldarg.1
0x14ca1  ldloc.0
0x14ca2  callvirt instance void class Microsoft.Xrm.Sdk.DataCollection`2<class Microsoft.Xrm.Sdk.Relationship, class Microsoft.Xrm.Sdk.EntityCollection>::SetItemInternal(var<u1>, !!T0)
0x14ca7  ret
0x14ca8  ldarg.0
0x14ca9  callvirt instance class Microsoft.Xrm.Sdk.RelatedEntityCollection Microsoft.Xrm.Sdk.Entity::get_RelatedEntities()
0x14cae  ldarg.1
0x14caf  callvirt instance var<u1> class Microsoft.Xrm.Sdk.DataCollection`2<class Microsoft.Xrm.Sdk.Relationship, class Microsoft.Xrm.Sdk.EntityCollection>::get_Item(void)
0x14cb4  callvirt instance class Microsoft.Xrm.Sdk.DataCollection`1<class Microsoft.Xrm.Sdk.Entity> Microsoft.Xrm.Sdk.EntityCollection::get_Entities()
0x14cb9  ldarg.2
0x14cba  callvirt instance bool class [mscorlib]System.Collections.ObjectModel.Collection`1<class Microsoft.Xrm.Sdk.Entity>::Contains(var<u1>)
0x14cbf  brtrue.s loc_14CD8
0x14cc1  ldarg.0
0x14cc2  callvirt instance class Microsoft.Xrm.Sdk.RelatedEntityCollection Microsoft.Xrm.Sdk.Entity::get_RelatedEntities()
0x14cc7  ldarg.1
0x14cc8  callvirt instance var<u1> class Microsoft.Xrm.Sdk.DataCollection`2<class Microsoft.Xrm.Sdk.Relationship, class Microsoft.Xrm.Sdk.EntityCollection>::get_Item(void)
0x14ccd  callvirt instance class Microsoft.Xrm.Sdk.DataCollection`1<class Microsoft.Xrm.Sdk.Entity> Microsoft.Xrm.Sdk.EntityCollection::get_Entities()
0x14cd2  ldarg.2
0x14cd3  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class Microsoft.Xrm.Sdk.Entity>::Add(var<u1>)
0x14cd8  ret
```
