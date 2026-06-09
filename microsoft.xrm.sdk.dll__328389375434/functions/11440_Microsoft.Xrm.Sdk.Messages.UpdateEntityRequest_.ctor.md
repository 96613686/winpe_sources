# Microsoft.Xrm.Sdk.Messages.UpdateEntityRequest::.ctor

- ea: `0x11440`
- end: `0x11460`
- name: `Microsoft.Xrm.Sdk.Messages.UpdateEntityRequest::.ctor`
- size: `32`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callees

- `0x3670`
- `0x36a0`
- `0x11260`
- `0x112b0`

## string_xrefs

- `0x11447`: `UpdateEntity`

## pseudocode

```c

```

## disassembly

```asm
0x11440  ldarg.0
0x11441  call     instance void Microsoft.Xrm.Sdk.OrganizationRequest::.ctor()
0x11446  ldarg.0
0x11447  ldstr    aUpdateentity// "UpdateEntity"
0x1144c  call     instance void Microsoft.Xrm.Sdk.OrganizationRequest::set_RequestName(string value)
0x11451  ldarg.0
0x11452  ldnull
0x11453  call     instance void Microsoft.Xrm.Sdk.Messages.UpdateEntityRequest::set_Entity(class Microsoft.Xrm.Sdk.Metadata.EntityMetadata value)
0x11458  ldarg.0
0x11459  ldc.i4.0
0x1145a  call     instance void Microsoft.Xrm.Sdk.Messages.UpdateEntityRequest::set_MergeLabels(bool value)
0x1145f  ret
```
