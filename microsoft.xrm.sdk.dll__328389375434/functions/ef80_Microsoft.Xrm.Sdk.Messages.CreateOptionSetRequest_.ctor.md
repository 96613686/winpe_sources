# Microsoft.Xrm.Sdk.Messages.CreateOptionSetRequest::.ctor

- ea: `0xef80`
- end: `0xef99`
- name: `Microsoft.Xrm.Sdk.Messages.CreateOptionSetRequest::.ctor`
- size: `25`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x3670`
- `0x36a0`
- `0xef10`

## string_xrefs

- `0xef87`: `CreateOptionSet`

## pseudocode

```c

```

## disassembly

```asm
0xef80  ldarg.0
0xef81  call     instance void Microsoft.Xrm.Sdk.OrganizationRequest::.ctor()
0xef86  ldarg.0
0xef87  ldstr    aCreateoptionse// "CreateOptionSet"
0xef8c  call     instance void Microsoft.Xrm.Sdk.OrganizationRequest::set_RequestName(string value)
0xef91  ldarg.0
0xef92  ldnull
0xef93  call     instance void Microsoft.Xrm.Sdk.Messages.CreateOptionSetRequest::set_OptionSet(class Microsoft.Xrm.Sdk.Metadata.OptionSetMetadataBase value)
0xef98  ret
```
