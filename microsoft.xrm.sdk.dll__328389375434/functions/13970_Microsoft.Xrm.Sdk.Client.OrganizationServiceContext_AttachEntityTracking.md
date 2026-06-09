# Microsoft.Xrm.Sdk.Client.OrganizationServiceContext::AttachEntityTracking

- ea: `0x13970`
- end: `0x13a09`
- name: `Microsoft.Xrm.Sdk.Client.OrganizationServiceContext::AttachEntityTracking`
- size: `153`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `service_task, broker_com_uri`

## callers

- `0x23400`

## callees

- `0x3880`
- `0x38c0`
- `0x38e0`
- `0x3c30`
- `0x4250`
- `0x4280`
- `0x4390`
- `0x137e0`
- `0x13970`
- `0x13a10`
- `0x15260`

## pseudocode

```c

```

## disassembly

```asm
0x13970  ldarg.0
0x13971  ldarg.1
0x13972  callvirt instance class Microsoft.Xrm.Sdk.Entity Microsoft.Xrm.Sdk.EntityDescriptor::get_Entity()
0x13977  call     instance bool Microsoft.Xrm.Sdk.Client.OrganizationServiceContext::IsAttached(class Microsoft.Xrm.Sdk.Entity entity)
0x1397c  brfalse.s loc_1397F
0x1397e  ret
0x1397f  ldarg.1
0x13980  callvirt instance class Microsoft.Xrm.Sdk.EntityReference Microsoft.Xrm.Sdk.EntityDescriptor::get_Identity()
0x13985  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Xrm.Sdk.EntityReference::get_Id()
0x1398a  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x1398f  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x13994  brfalse.s loc_139A8
0x13996  ldarg.0
0x13997  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<class Microsoft.Xrm.Sdk.EntityReference, class Microsoft.Xrm.Sdk.EntityDescriptor> Microsoft.Xrm.Sdk.Client.OrganizationServiceContext::_identityToDescriptor
0x1399c  ldarg.1
0x1399d  callvirt instance class Microsoft.Xrm.Sdk.EntityReference Microsoft.Xrm.Sdk.EntityDescriptor::get_Identity()
0x139a2  ldarg.1
0x139a3  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<class Microsoft.Xrm.Sdk.EntityReference, class Microsoft.Xrm.Sdk.EntityDescriptor>::Add(var<u1>, !!T0)
0x139a8  ldarg.0
0x139a9  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<class Microsoft.Xrm.Sdk.Entity, class Microsoft.Xrm.Sdk.EntityDescriptor> Microsoft.Xrm.Sdk.Client.OrganizationServiceContext::_descriptors
0x139ae  ldarg.1
0x139af  callvirt instance class Microsoft.Xrm.Sdk.Entity Microsoft.Xrm.Sdk.EntityDescriptor::get_Entity()
0x139b4  ldarg.1
0x139b5  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<class Microsoft.Xrm.Sdk.Entity, class Microsoft.Xrm.Sdk.EntityDescriptor>::Add(var<u1>, !!T0)
0x139ba  ldarg.0
0x139bb  ldfld    bool Microsoft.Xrm.Sdk.Client.OrganizationServiceContext::_trackEntityChanges
0x139c0  brfalse.s loc_139CE
0x139c2  ldarg.1
0x139c3  callvirt instance class Microsoft.Xrm.Sdk.Entity Microsoft.Xrm.Sdk.EntityDescriptor::get_Entity()
0x139c8  ldc.i4.1
0x139c9  callvirt instance void Microsoft.Xrm.Sdk.Entity::set_IsReadOnly(bool value)
0x139ce  ldarg.1
0x139cf  callvirt instance class Microsoft.Xrm.Sdk.Entity Microsoft.Xrm.Sdk.EntityDescriptor::get_Entity()
0x139d4  ldarg.1
0x139d5  callvirt instance valuetype Microsoft.Xrm.Sdk.EntityStates Microsoft.Xrm.Sdk.Descriptor::get_State()
0x139da  call     valuetype [mscorlib]System.Nullable`1<valuetype Microsoft.Xrm.Sdk.EntityState> Microsoft.Xrm.Sdk.Client.OrganizationServiceContext::MapEntityState(valuetype Microsoft.Xrm.Sdk.EntityStates state)
0x139df  stloc.0
0x139e0  ldloca.s 0
0x139e2  call     instance bool valuetype [mscorlib]System.Nullable`1<valuetype Microsoft.Xrm.Sdk.EntityState>::get_HasValue()
0x139e7  brtrue.s loc_139F6
0x139e9  ldarg.1
0x139ea  callvirt instance class Microsoft.Xrm.Sdk.Entity Microsoft.Xrm.Sdk.EntityDescriptor::get_Entity()
0x139ef  callvirt instance valuetype [mscorlib]System.Nullable`1<valuetype Microsoft.Xrm.Sdk.EntityState> Microsoft.Xrm.Sdk.Entity::get_EntityState()
0x139f4  br.s     loc_139F7
0x139f6  ldloc.0
0x139f7  callvirt instance void Microsoft.Xrm.Sdk.Entity::SetEntityStateInternal(valuetype [mscorlib]System.Nullable`1<valuetype Microsoft.Xrm.Sdk.EntityState> entityState)
0x139fc  ldarg.0
0x139fd  ldarg.1
0x139fe  callvirt instance class Microsoft.Xrm.Sdk.Entity Microsoft.Xrm.Sdk.EntityDescriptor::get_Entity()
0x13a03  callvirt instance void Microsoft.Xrm.Sdk.Client.OrganizationServiceContext::OnBeginEntityTracking(class Microsoft.Xrm.Sdk.Entity entity)
0x13a08  ret
```
