# Microsoft.Xrm.Sdk.Client.OrganizationServiceContext::DeleteLinkTracking

- ea: `0x13f80`
- end: `0x13f9f`
- name: `Microsoft.Xrm.Sdk.Client.OrganizationServiceContext::DeleteLinkTracking`
- size: `31`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x13fa0`

## callees

- `0x3880`
- `0x3890`
- `0x13ba0`
- `0x13f80`

## pseudocode

```c

```

## disassembly

```asm
0x13f80  ldarg.1
0x13f81  callvirt instance valuetype Microsoft.Xrm.Sdk.EntityStates Microsoft.Xrm.Sdk.Descriptor::get_State()
0x13f86  stloc.0
0x13f87  ldloc.0
0x13f88  ldc.i4.4
0x13f89  bne.un.s loc_13F93
0x13f8b  ldarg.0
0x13f8c  ldarg.1
0x13f8d  call     instance void Microsoft.Xrm.Sdk.Client.OrganizationServiceContext::DetachLinkTracking(class Microsoft.Xrm.Sdk.LinkDescriptor existingLink)
0x13f92  ret
0x13f93  ldloc.0
0x13f94  ldc.i4.8
0x13f95  beq.s    loc_13F9E
0x13f97  ldarg.1
0x13f98  ldc.i4.8
0x13f99  callvirt instance void Microsoft.Xrm.Sdk.Descriptor::set_State(valuetype Microsoft.Xrm.Sdk.EntityStates value)
0x13f9e  ret
```
