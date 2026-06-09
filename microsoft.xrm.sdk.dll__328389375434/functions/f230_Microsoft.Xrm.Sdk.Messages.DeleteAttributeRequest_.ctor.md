# Microsoft.Xrm.Sdk.Messages.DeleteAttributeRequest::.ctor

- ea: `0xf230`
- end: `0xf250`
- name: `Microsoft.Xrm.Sdk.Messages.DeleteAttributeRequest::.ctor`
- size: `32`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x3670`
- `0x36a0`
- `0xf1c0`
- `0xf210`

## string_xrefs

- `0xf237`: `DeleteAttribute`

## pseudocode

```c

```

## disassembly

```asm
0xf230  ldarg.0
0xf231  call     instance void Microsoft.Xrm.Sdk.OrganizationRequest::.ctor()
0xf236  ldarg.0
0xf237  ldstr    aDeleteattribut// "DeleteAttribute"
0xf23c  call     instance void Microsoft.Xrm.Sdk.OrganizationRequest::set_RequestName(string value)
0xf241  ldarg.0
0xf242  ldnull
0xf243  call     instance void Microsoft.Xrm.Sdk.Messages.DeleteAttributeRequest::set_LogicalName(string value)
0xf248  ldarg.0
0xf249  ldnull
0xf24a  call     instance void Microsoft.Xrm.Sdk.Messages.DeleteAttributeRequest::set_EntityLogicalName(string value)
0xf24f  ret
```
