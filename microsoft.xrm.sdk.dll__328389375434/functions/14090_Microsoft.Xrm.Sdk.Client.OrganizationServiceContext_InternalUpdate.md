# Microsoft.Xrm.Sdk.Client.OrganizationServiceContext::InternalUpdate

- ea: `0x14090`
- end: `0x140c5`
- name: `Microsoft.Xrm.Sdk.Client.OrganizationServiceContext::InternalUpdate`
- size: `53`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x13fd0`

## callees

- `0x3880`
- `0x3890`
- `0x38e0`
- `0x4280`
- `0x14090`

## pseudocode

```c

```

## disassembly

```asm
0x14090  ldarg.1
0x14091  callvirt instance valuetype Microsoft.Xrm.Sdk.EntityStates Microsoft.Xrm.Sdk.Descriptor::get_State()
0x14096  ldc.i4.2
0x14097  bne.un.s loc_140C4
0x14099  ldarg.1
0x1409a  ldc.i4.s 0x10
0x1409c  callvirt instance void Microsoft.Xrm.Sdk.Descriptor::set_State(valuetype Microsoft.Xrm.Sdk.EntityStates value)
0x140a1  ldarg.1
0x140a2  callvirt instance class Microsoft.Xrm.Sdk.Entity Microsoft.Xrm.Sdk.EntityDescriptor::get_Entity()
0x140a7  ldc.i4.2
0x140a8  newobj   instance void valuetype [mscorlib]System.Nullable`1<valuetype Microsoft.Xrm.Sdk.EntityState>::.ctor(var<u1>)
0x140ad  callvirt instance void Microsoft.Xrm.Sdk.Entity::SetEntityStateInternal(valuetype [mscorlib]System.Nullable`1<valuetype Microsoft.Xrm.Sdk.EntityState> entityState)
0x140b2  ldarg.0
0x140b3  ldfld    class [System.Core]System.Collections.Generic.HashSet`1<class Microsoft.Xrm.Sdk.Entity> Microsoft.Xrm.Sdk.Client.OrganizationServiceContext::_roots
0x140b8  ldarg.1
0x140b9  callvirt instance class Microsoft.Xrm.Sdk.Entity Microsoft.Xrm.Sdk.EntityDescriptor::get_Entity()
0x140be  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<class Microsoft.Xrm.Sdk.Entity>::Add(var<u1>)
0x140c3  pop
0x140c4  ret
```
