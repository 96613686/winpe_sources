# Microsoft.Xrm.Sdk.Messages.CreateAttributeRequest::.ctor

- ea: `0xe840`
- end: `0xe860`
- name: `Microsoft.Xrm.Sdk.Messages.CreateAttributeRequest::.ctor`
- size: `32`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x3670`
- `0x36a0`
- `0xe780`
- `0xe7d0`

## string_xrefs

- `0xe847`: `CreateAttribute`

## pseudocode

```c

```

## disassembly

```asm
0xe840  ldarg.0
0xe841  call     instance void Microsoft.Xrm.Sdk.OrganizationRequest::.ctor()
0xe846  ldarg.0
0xe847  ldstr    aCreateattribut_0// "CreateAttribute"
0xe84c  call     instance void Microsoft.Xrm.Sdk.OrganizationRequest::set_RequestName(string value)
0xe851  ldarg.0
0xe852  ldnull
0xe853  call     instance void Microsoft.Xrm.Sdk.Messages.CreateAttributeRequest::set_Attribute(class Microsoft.Xrm.Sdk.Metadata.AttributeMetadata value)
0xe858  ldarg.0
0xe859  ldnull
0xe85a  call     instance void Microsoft.Xrm.Sdk.Messages.CreateAttributeRequest::set_EntityName(string value)
0xe85f  ret
```
