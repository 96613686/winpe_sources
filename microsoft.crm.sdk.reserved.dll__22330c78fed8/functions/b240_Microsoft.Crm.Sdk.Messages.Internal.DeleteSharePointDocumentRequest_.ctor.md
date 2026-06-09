# Microsoft.Crm.Sdk.Messages.Internal.DeleteSharePointDocumentRequest::.ctor

- ea: `0xb240`
- end: `0xb26e`
- name: `Microsoft.Crm.Sdk.Messages.Internal.DeleteSharePointDocumentRequest::.ctor`
- size: `46`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0xb130`
- `0xb180`
- `0xb1d0`
- `0xb220`

## string_xrefs

- `0xb247`: `DeleteSharePointDocument`

## pseudocode

```c

```

## disassembly

```asm
0xb240  ldarg.0
0xb241  call     instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest::.ctor()
0xb246  ldarg.0
0xb247  ldstr    aDeletesharepoi// "DeleteSharePointDocument"
0xb24c  call     instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest::set_RequestName(string)
0xb251  ldarg.0
0xb252  ldnull
0xb253  call     instance void Microsoft.Crm.Sdk.Messages.Internal.DeleteSharePointDocumentRequest::set_DocumentIds(string[] value)
0xb258  ldarg.0
0xb259  ldnull
0xb25a  call     instance void Microsoft.Crm.Sdk.Messages.Internal.DeleteSharePointDocumentRequest::set_SiteUrl(string value)
0xb25f  ldarg.0
0xb260  ldnull
0xb261  call     instance void Microsoft.Crm.Sdk.Messages.Internal.DeleteSharePointDocumentRequest::set_DocumentLocation(string value)
0xb266  ldarg.0
0xb267  ldnull
0xb268  call     instance void Microsoft.Crm.Sdk.Messages.Internal.DeleteSharePointDocumentRequest::set_ReferencedEntity(string value)
0xb26d  ret
```
