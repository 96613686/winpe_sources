# Microsoft.Xrm.Sdk.Client.OrganizationServiceContext::DeleteEntityTracking

- ea: `0x13f40`
- end: `0x13f72`
- name: `Microsoft.Xrm.Sdk.Client.OrganizationServiceContext::DeleteEntityTracking`
- size: `50`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x13dd0`

## callees

- `0x3880`
- `0x3890`
- `0x38e0`
- `0x13b30`
- `0x13f40`

## pseudocode

```c

```

## disassembly

```asm
0x13f40  ldarg.1
0x13f41  callvirt instance valuetype Microsoft.Xrm.Sdk.EntityStates Microsoft.Xrm.Sdk.Descriptor::get_State()
0x13f46  stloc.0
0x13f47  ldloc.0
0x13f48  ldc.i4.4
0x13f49  bne.un.s loc_13F54
0x13f4b  ldarg.0
0x13f4c  ldarg.1
0x13f4d  call     instance void Microsoft.Xrm.Sdk.Client.OrganizationServiceContext::DetachEntityTracking(class Microsoft.Xrm.Sdk.EntityDescriptor existingEntity)
0x13f52  br.s     loc_13F5F
0x13f54  ldloc.0
0x13f55  ldc.i4.8
0x13f56  beq.s    loc_13F5F
0x13f58  ldarg.1
0x13f59  ldc.i4.8
0x13f5a  callvirt instance void Microsoft.Xrm.Sdk.Descriptor::set_State(valuetype Microsoft.Xrm.Sdk.EntityStates value)
0x13f5f  ldarg.0
0x13f60  ldfld    class [System.Core]System.Collections.Generic.HashSet`1<class Microsoft.Xrm.Sdk.Entity> Microsoft.Xrm.Sdk.Client.OrganizationServiceContext::_roots
0x13f65  ldarg.1
0x13f66  callvirt instance class Microsoft.Xrm.Sdk.Entity Microsoft.Xrm.Sdk.EntityDescriptor::get_Entity()
0x13f6b  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<class Microsoft.Xrm.Sdk.Entity>::Remove(var<u1>)
0x13f70  pop
0x13f71  ret
```
