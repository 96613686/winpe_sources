# Microsoft.Xrm.Sdk.Client.OrganizationServiceContext::DetachEntityTracking

- ea: `0x13b30`
- end: `0x13b94`
- name: `Microsoft.Xrm.Sdk.Client.OrganizationServiceContext::DetachEntityTracking`
- size: `100`
- prototype: ``
- caller_count: `7`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x135a0`
- `0x13f40`
- `0x14110`
- `0x141d0`
- `0x14840`
- `0x14a70`
- `0x23d90`

## callees

- `0x3890`
- `0x38e0`
- `0x3f00`
- `0x4250`
- `0x13b30`
- `0x15270`

## pseudocode

```c

```

## disassembly

```asm
0x13b30  ldarg.0
0x13b31  ldfld    bool Microsoft.Xrm.Sdk.Client.OrganizationServiceContext::_trackEntityChanges
0x13b36  brfalse.s loc_13B44
0x13b38  ldarg.1
0x13b39  callvirt instance class Microsoft.Xrm.Sdk.Entity Microsoft.Xrm.Sdk.EntityDescriptor::get_Entity()
0x13b3e  ldc.i4.0
0x13b3f  callvirt instance void Microsoft.Xrm.Sdk.Entity::set_IsReadOnly(bool value)
0x13b44  ldarg.1
0x13b45  ldc.i4.1
0x13b46  callvirt instance void Microsoft.Xrm.Sdk.Descriptor::set_State(valuetype Microsoft.Xrm.Sdk.EntityStates value)
0x13b4b  ldarg.0
0x13b4c  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<class Microsoft.Xrm.Sdk.Entity, class Microsoft.Xrm.Sdk.EntityDescriptor> Microsoft.Xrm.Sdk.Client.OrganizationServiceContext::_descriptors
0x13b51  ldarg.1
0x13b52  callvirt instance class Microsoft.Xrm.Sdk.Entity Microsoft.Xrm.Sdk.EntityDescriptor::get_Entity()
0x13b57  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<class Microsoft.Xrm.Sdk.Entity, class Microsoft.Xrm.Sdk.EntityDescriptor>::Remove(var<u1>)
0x13b5c  ldarg.0
0x13b5d  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<class Microsoft.Xrm.Sdk.EntityReference, class Microsoft.Xrm.Sdk.EntityDescriptor> Microsoft.Xrm.Sdk.Client.OrganizationServiceContext::_identityToDescriptor
0x13b62  ldarg.1
0x13b63  callvirt instance class Microsoft.Xrm.Sdk.Entity Microsoft.Xrm.Sdk.EntityDescriptor::get_Entity()
0x13b68  callvirt instance class Microsoft.Xrm.Sdk.EntityReference Microsoft.Xrm.Sdk.Entity::ToEntityReference()
0x13b6d  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<class Microsoft.Xrm.Sdk.EntityReference, class Microsoft.Xrm.Sdk.EntityDescriptor>::Remove(var<u1>)
0x13b72  pop
0x13b73  ldarg.0
0x13b74  ldfld    class [System.Core]System.Collections.Generic.HashSet`1<class Microsoft.Xrm.Sdk.Entity> Microsoft.Xrm.Sdk.Client.OrganizationServiceContext::_roots
0x13b79  ldarg.1
0x13b7a  callvirt instance class Microsoft.Xrm.Sdk.Entity Microsoft.Xrm.Sdk.EntityDescriptor::get_Entity()
0x13b7f  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<class Microsoft.Xrm.Sdk.Entity>::Remove(var<u1>)
0x13b84  pop
0x13b85  brfalse.s loc_13B93
0x13b87  ldarg.0
0x13b88  ldarg.1
0x13b89  callvirt instance class Microsoft.Xrm.Sdk.Entity Microsoft.Xrm.Sdk.EntityDescriptor::get_Entity()
0x13b8e  callvirt instance void Microsoft.Xrm.Sdk.Client.OrganizationServiceContext::OnEndEntityTracking(class Microsoft.Xrm.Sdk.Entity entity)
0x13b93  ret
```
