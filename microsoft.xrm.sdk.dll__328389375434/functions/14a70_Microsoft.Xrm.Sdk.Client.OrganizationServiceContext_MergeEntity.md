# Microsoft.Xrm.Sdk.Client.OrganizationServiceContext::MergeEntity

- ea: `0x14a70`
- end: `0x14b39`
- name: `Microsoft.Xrm.Sdk.Client.OrganizationServiceContext::MergeEntity`
- size: `201`
- prototype: ``
- caller_count: `2`
- callee_count: `12`
- tags: `service_task, broker_com_uri`

## callers

- `0xb750`
- `0x133c0`

## callees

- `0x3880`
- `0x38c0`
- `0x38e0`
- `0x3900`
- `0x3bc0`
- `0x3f00`
- `0x4250`
- `0x4280`
- `0x13170`
- `0x13b30`
- `0x14a70`
- `0x15260`

## pseudocode

```c

```

## disassembly

```asm
0x14a70  ldarg.0
0x14a71  call     instance valuetype Microsoft.Xrm.Sdk.Client.MergeOption Microsoft.Xrm.Sdk.Client.OrganizationServiceContext::get_MergeOption()
0x14a76  ldc.i4.3
0x14a77  beq.s    loc_14A8E
0x14a79  ldarg.1
0x14a7a  brfalse.s loc_14A8E
0x14a7c  ldarg.1
0x14a7d  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Xrm.Sdk.Entity::get_Id()
0x14a82  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x14a87  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x14a8c  brfalse.s loc_14A90
0x14a8e  ldarg.1
0x14a8f  ret
0x14a90  ldc.i4.2
0x14a91  ldarg.1
0x14a92  callvirt instance class Microsoft.Xrm.Sdk.EntityReference Microsoft.Xrm.Sdk.Entity::ToEntityReference()
0x14a97  ldarg.1
0x14a98  newobj   instance void Microsoft.Xrm.Sdk.EntityDescriptor::.ctor(valuetype Microsoft.Xrm.Sdk.EntityStates state, class Microsoft.Xrm.Sdk.EntityReference identity, class Microsoft.Xrm.Sdk.Entity entity)
0x14a9d  stloc.0
0x14a9e  ldarg.0
0x14a9f  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<class Microsoft.Xrm.Sdk.EntityReference, class Microsoft.Xrm.Sdk.EntityDescriptor> Microsoft.Xrm.Sdk.Client.OrganizationServiceContext::_identityToDescriptor
0x14aa4  ldloc.0
0x14aa5  callvirt instance class Microsoft.Xrm.Sdk.EntityReference Microsoft.Xrm.Sdk.EntityDescriptor::get_Identity()
0x14aaa  ldloca.s 1
0x14aac  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<class Microsoft.Xrm.Sdk.EntityReference, class Microsoft.Xrm.Sdk.EntityDescriptor>::TryGetValue(var<u1>, !!T0)
0x14ab1  pop
0x14ab2  ldloc.1
0x14ab3  brfalse.s loc_14ADD
0x14ab5  ldarg.0
0x14ab6  call     instance valuetype Microsoft.Xrm.Sdk.Client.MergeOption Microsoft.Xrm.Sdk.Client.OrganizationServiceContext::get_MergeOption()
0x14abb  brfalse.s loc_14ACF
0x14abd  ldarg.0
0x14abe  call     instance valuetype Microsoft.Xrm.Sdk.Client.MergeOption Microsoft.Xrm.Sdk.Client.OrganizationServiceContext::get_MergeOption()
0x14ac3  ldc.i4.2
0x14ac4  bne.un.s loc_14AD6
0x14ac6  ldloc.1
0x14ac7  callvirt instance valuetype Microsoft.Xrm.Sdk.EntityStates Microsoft.Xrm.Sdk.Descriptor::get_State()
0x14acc  ldc.i4.2
0x14acd  beq.s    loc_14AD6
0x14acf  ldloc.1
0x14ad0  callvirt instance class Microsoft.Xrm.Sdk.Entity Microsoft.Xrm.Sdk.EntityDescriptor::get_Entity()
0x14ad5  ret
0x14ad6  ldarg.0
0x14ad7  ldloc.1
0x14ad8  call     instance void Microsoft.Xrm.Sdk.Client.OrganizationServiceContext::DetachEntityTracking(class Microsoft.Xrm.Sdk.EntityDescriptor existingEntity)
0x14add  ldarg.0
0x14ade  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<class Microsoft.Xrm.Sdk.Entity, class Microsoft.Xrm.Sdk.EntityDescriptor> Microsoft.Xrm.Sdk.Client.OrganizationServiceContext::_descriptors
0x14ae3  ldloc.0
0x14ae4  callvirt instance class Microsoft.Xrm.Sdk.Entity Microsoft.Xrm.Sdk.EntityDescriptor::get_Entity()
0x14ae9  ldloc.0
0x14aea  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<class Microsoft.Xrm.Sdk.Entity, class Microsoft.Xrm.Sdk.EntityDescriptor>::set_Item(var<u1>, !!T0)
0x14aef  ldarg.0
0x14af0  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<class Microsoft.Xrm.Sdk.EntityReference, class Microsoft.Xrm.Sdk.EntityDescriptor> Microsoft.Xrm.Sdk.Client.OrganizationServiceContext::_identityToDescriptor
0x14af5  ldloc.0
0x14af6  callvirt instance class Microsoft.Xrm.Sdk.EntityReference Microsoft.Xrm.Sdk.EntityDescriptor::get_Identity()
0x14afb  ldloc.0
0x14afc  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<class Microsoft.Xrm.Sdk.EntityReference, class Microsoft.Xrm.Sdk.EntityDescriptor>::set_Item(var<u1>, !!T0)
0x14b01  ldloc.0
0x14b02  callvirt instance class Microsoft.Xrm.Sdk.Entity Microsoft.Xrm.Sdk.EntityDescriptor::get_Entity()
0x14b07  ldc.i4.0
0x14b08  newobj   instance void valuetype [mscorlib]System.Nullable`1<valuetype Microsoft.Xrm.Sdk.EntityState>::.ctor(var<u1>)
0x14b0d  callvirt instance void Microsoft.Xrm.Sdk.Entity::SetEntityStateInternal(valuetype [mscorlib]System.Nullable`1<valuetype Microsoft.Xrm.Sdk.EntityState> entityState)
0x14b12  ldarg.0
0x14b13  ldfld    bool Microsoft.Xrm.Sdk.Client.OrganizationServiceContext::_trackEntityChanges
0x14b18  brfalse.s loc_14B26
0x14b1a  ldloc.0
0x14b1b  callvirt instance class Microsoft.Xrm.Sdk.Entity Microsoft.Xrm.Sdk.EntityDescriptor::get_Entity()
0x14b20  ldc.i4.1
0x14b21  callvirt instance void Microsoft.Xrm.Sdk.Entity::set_IsReadOnly(bool value)
0x14b26  ldarg.0
0x14b27  ldloc.0
0x14b28  callvirt instance class Microsoft.Xrm.Sdk.Entity Microsoft.Xrm.Sdk.EntityDescriptor::get_Entity()
0x14b2d  callvirt instance void Microsoft.Xrm.Sdk.Client.OrganizationServiceContext::OnBeginEntityTracking(class Microsoft.Xrm.Sdk.Entity entity)
0x14b32  ldloc.0
0x14b33  callvirt instance class Microsoft.Xrm.Sdk.Entity Microsoft.Xrm.Sdk.EntityDescriptor::get_Entity()
0x14b38  ret
```
