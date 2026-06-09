# Microsoft.Xrm.Sdk.Messages.CreateEntityRequest::.ctor

- ea: `0xeab0`
- end: `0xeae5`
- name: `Microsoft.Xrm.Sdk.Messages.CreateEntityRequest::.ctor`
- size: `53`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `broker_com_uri`

## callees

- `0x3670`
- `0x36a0`
- `0xe900`
- `0xe950`
- `0xe9a0`
- `0xe9f0`
- `0xea40`

## string_xrefs

- `0xeab7`: `CreateEntity`

## pseudocode

```c

```

## disassembly

```asm
0xeab0  ldarg.0
0xeab1  call     instance void Microsoft.Xrm.Sdk.OrganizationRequest::.ctor()
0xeab6  ldarg.0
0xeab7  ldstr    aCreateentity// "CreateEntity"
0xeabc  call     instance void Microsoft.Xrm.Sdk.OrganizationRequest::set_RequestName(string value)
0xeac1  ldarg.0
0xeac2  ldnull
0xeac3  call     instance void Microsoft.Xrm.Sdk.Messages.CreateEntityRequest::set_Entity(class Microsoft.Xrm.Sdk.Metadata.EntityMetadata value)
0xeac8  ldarg.0
0xeac9  ldc.i4.0
0xeaca  call     instance void Microsoft.Xrm.Sdk.Messages.CreateEntityRequest::set_HasActivities(bool value)
0xeacf  ldarg.0
0xead0  ldc.i4.0
0xead1  call     instance void Microsoft.Xrm.Sdk.Messages.CreateEntityRequest::set_HasNotes(bool value)
0xead6  ldarg.0
0xead7  ldc.i4.0
0xead8  call     instance void Microsoft.Xrm.Sdk.Messages.CreateEntityRequest::set_HasFeedback(bool value)
0xeadd  ldarg.0
0xeade  ldnull
0xeadf  call     instance void Microsoft.Xrm.Sdk.Messages.CreateEntityRequest::set_PrimaryAttribute(class Microsoft.Xrm.Sdk.Metadata.StringAttributeMetadata value)
0xeae4  ret
```
