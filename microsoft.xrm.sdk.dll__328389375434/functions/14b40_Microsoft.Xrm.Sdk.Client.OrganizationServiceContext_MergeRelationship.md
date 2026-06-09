# Microsoft.Xrm.Sdk.Client.OrganizationServiceContext::MergeRelationship

- ea: `0x14b40`
- end: `0x14c69`
- name: `Microsoft.Xrm.Sdk.Client.OrganizationServiceContext::MergeRelationship`
- size: `297`
- prototype: ``
- caller_count: `1`
- callee_count: `16`
- tags: `service_task, broker_com_uri`

## callers

- `0x133c0`

## callees

- `0x2e40`
- `0x2e60`
- `0x2f70`
- `0x3880`
- `0x3930`
- `0x3950`
- `0x3970`
- `0x3990`
- `0x3b90`
- `0x3c90`
- `0x3f00`
- `0x13170`
- `0x14b40`
- `0x14c70`
- `0x15280`
- `0x24810`

## pseudocode

```c

```

## disassembly

```asm
0x14b40  ldarg.1
0x14b41  brtrue.s loc_14B4E
0x14b43  ldstr    aSource// "source"
0x14b48  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x14b4d  throw
0x14b4e  ldarg.3
0x14b4f  brtrue.s loc_14B5C
0x14b51  ldstr    aTarget_0// "target"
0x14b56  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x14b5b  throw
0x14b5c  ldarg.2
0x14b5d  brtrue.s loc_14B6A
0x14b5f  ldstr    aRelationship_0// "relationship"
0x14b64  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x14b69  throw
0x14b6a  ldarg.s  4
0x14b6c  brfalse.s loc_14BE0
0x14b6e  ldarg.1
0x14b6f  ldarg.2
0x14b70  ldarg.3
0x14b71  newobj   instance void Microsoft.Xrm.Sdk.LinkDescriptor::.ctor(class Microsoft.Xrm.Sdk.Entity source, class Microsoft.Xrm.Sdk.Relationship relationship, class Microsoft.Xrm.Sdk.Entity target)
0x14b76  stloc.0
0x14b77  ldarg.0
0x14b78  call     instance valuetype Microsoft.Xrm.Sdk.Client.MergeOption Microsoft.Xrm.Sdk.Client.OrganizationServiceContext::get_MergeOption()
0x14b7d  ldc.i4.3
0x14b7e  bne.un.s loc_14B81
0x14b80  ret
0x14b81  ldarg.0
0x14b82  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<class Microsoft.Xrm.Sdk.LinkDescriptor, class Microsoft.Xrm.Sdk.LinkDescriptor> Microsoft.Xrm.Sdk.Client.OrganizationServiceContext::_bindings
0x14b87  ldloc.0
0x14b88  ldloca.s 1
0x14b8a  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<class Microsoft.Xrm.Sdk.LinkDescriptor, class Microsoft.Xrm.Sdk.LinkDescriptor>::TryGetValue(var<u1>, !!T0)
0x14b8f  pop
0x14b90  ldloc.1
0x14b91  brfalse.s loc_14BBB
0x14b93  ldarg.0
0x14b94  call     instance valuetype Microsoft.Xrm.Sdk.Client.MergeOption Microsoft.Xrm.Sdk.Client.OrganizationServiceContext::get_MergeOption()
0x14b99  brfalse.s loc_14BAD
0x14b9b  ldarg.0
0x14b9c  call     instance valuetype Microsoft.Xrm.Sdk.Client.MergeOption Microsoft.Xrm.Sdk.Client.OrganizationServiceContext::get_MergeOption()
0x14ba1  ldc.i4.2
0x14ba2  bne.un.s loc_14BBB
0x14ba4  ldloc.1
0x14ba5  callvirt instance valuetype Microsoft.Xrm.Sdk.EntityStates Microsoft.Xrm.Sdk.Descriptor::get_State()
0x14baa  ldc.i4.2
0x14bab  beq.s    loc_14BBB
0x14bad  ldarg.1
0x14bae  ldarg.2
0x14baf  ldloc.1
0x14bb0  callvirt instance class Microsoft.Xrm.Sdk.Entity Microsoft.Xrm.Sdk.LinkDescriptor::get_Target()
0x14bb5  call     void Microsoft.Xrm.Sdk.Client.OrganizationServiceContext::AddRelationshipIfNotContains(class Microsoft.Xrm.Sdk.Entity source, class Microsoft.Xrm.Sdk.Relationship relationship, class Microsoft.Xrm.Sdk.Entity target)
0x14bba  ret
0x14bbb  ldarg.0
0x14bbc  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<class Microsoft.Xrm.Sdk.LinkDescriptor, class Microsoft.Xrm.Sdk.LinkDescriptor> Microsoft.Xrm.Sdk.Client.OrganizationServiceContext::_bindings
0x14bc1  ldloc.0
0x14bc2  ldloc.0
0x14bc3  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<class Microsoft.Xrm.Sdk.LinkDescriptor, class Microsoft.Xrm.Sdk.LinkDescriptor>::set_Item(var<u1>, !!T0)
0x14bc8  ldarg.0
0x14bc9  ldloc.0
0x14bca  callvirt instance class Microsoft.Xrm.Sdk.Entity Microsoft.Xrm.Sdk.LinkDescriptor::get_Source()
0x14bcf  ldloc.0
0x14bd0  callvirt instance class Microsoft.Xrm.Sdk.Relationship Microsoft.Xrm.Sdk.LinkDescriptor::get_Relationship()
0x14bd5  ldloc.0
0x14bd6  callvirt instance class Microsoft.Xrm.Sdk.Entity Microsoft.Xrm.Sdk.LinkDescriptor::get_Target()
0x14bdb  callvirt instance void Microsoft.Xrm.Sdk.Client.OrganizationServiceContext::OnBeginLinkTracking(class Microsoft.Xrm.Sdk.Entity source, class Microsoft.Xrm.Sdk.Relationship relationship, class Microsoft.Xrm.Sdk.Entity target)
0x14be0  ldarg.1
0x14be1  callvirt instance class Microsoft.Xrm.Sdk.RelatedEntityCollection Microsoft.Xrm.Sdk.Entity::get_RelatedEntities()
0x14be6  ldarg.2
0x14be7  callvirt instance bool class Microsoft.Xrm.Sdk.DataCollection`2<class Microsoft.Xrm.Sdk.Relationship, class Microsoft.Xrm.Sdk.EntityCollection>::Contains(var<u1>)
0x14bec  brtrue.s loc_14C18
0x14bee  ldc.i4.1
0x14bef  newarr   Microsoft.Xrm.Sdk.Entity
0x14bf4  dup
0x14bf5  ldc.i4.0
0x14bf6  ldarg.3
0x14bf7  stelem.ref
0x14bf8  newobj   instance void Microsoft.Xrm.Sdk.EntityCollection::.ctor(class [mscorlib]System.Collections.Generic.IList`1<class Microsoft.Xrm.Sdk.Entity> list)
0x14bfd  stloc.2
0x14bfe  ldloc.2
0x14bff  ldarg.3
0x14c00  callvirt instance string Microsoft.Xrm.Sdk.Entity::get_LogicalName()
0x14c05  callvirt instance void Microsoft.Xrm.Sdk.EntityCollection::set_EntityName(string value)
0x14c0a  ldarg.1
0x14c0b  callvirt instance class Microsoft.Xrm.Sdk.RelatedEntityCollection Microsoft.Xrm.Sdk.Entity::get_RelatedEntities()
0x14c10  ldarg.2
0x14c11  ldloc.2
0x14c12  callvirt instance void class Microsoft.Xrm.Sdk.DataCollection`2<class Microsoft.Xrm.Sdk.Relationship, class Microsoft.Xrm.Sdk.EntityCollection>::SetItemInternal(var<u1>, !!T0)
0x14c17  ret
0x14c18  newobj   instance void <>c__DisplayClass92_0::.ctor()
0x14c1d  stloc.3
0x14c1e  ldloc.3
0x14c1f  ldarg.3
0x14c20  callvirt instance class Microsoft.Xrm.Sdk.EntityReference Microsoft.Xrm.Sdk.Entity::ToEntityReference()
0x14c25  stfld    class Microsoft.Xrm.Sdk.EntityReference <>c__DisplayClass92_0::targetReference
0x14c2a  ldarg.1
0x14c2b  callvirt instance class Microsoft.Xrm.Sdk.RelatedEntityCollection Microsoft.Xrm.Sdk.Entity::get_RelatedEntities()
0x14c30  ldarg.2
0x14c31  callvirt instance var<u1> class Microsoft.Xrm.Sdk.DataCollection`2<class Microsoft.Xrm.Sdk.Relationship, class Microsoft.Xrm.Sdk.EntityCollection>::get_Item(void)
0x14c36  callvirt instance class Microsoft.Xrm.Sdk.DataCollection`1<class Microsoft.Xrm.Sdk.Entity> Microsoft.Xrm.Sdk.EntityCollection::get_Entities()
0x14c3b  stloc.s  4
0x14c3d  ldloc.s  4
0x14c3f  ldloc.3
0x14c40  ldftn    instance bool <>c__DisplayClass92_0::<MergeRelationship>b__0(class Microsoft.Xrm.Sdk.Entity e)
0x14c46  newobj   instance void class [mscorlib]System.Func`2<class Microsoft.Xrm.Sdk.Entity, bool>::.ctor(object, native int)
0x14c4b  call     T0x2B000056
0x14c50  stloc.s  5
0x14c52  ldloc.s  5
0x14c54  brfalse.s loc_14C60
0x14c56  ldloc.s  4
0x14c58  ldloc.s  5
0x14c5a  callvirt instance bool class [mscorlib]System.Collections.ObjectModel.Collection`1<class Microsoft.Xrm.Sdk.Entity>::Remove(var<u1>)
0x14c5f  pop
0x14c60  ldloc.s  4
0x14c62  ldarg.3
0x14c63  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class Microsoft.Xrm.Sdk.Entity>::Add(var<u1>)
0x14c68  ret
```
