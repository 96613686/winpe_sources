# Microsoft.Crm.Sdk.Messages.Internal.RenameFolderNameRequest::.ctor

- ea: `0xcca0`
- end: `0xccc7`
- name: `Microsoft.Crm.Sdk.Messages.Internal.RenameFolderNameRequest::.ctor`
- size: `39`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0xcbe0`
- `0xcc30`
- `0xcc80`

## string_xrefs

- `0xcca7`: `RenameFolderName`

## pseudocode

```c

```

## disassembly

```asm
0xcca0  ldarg.0
0xcca1  call     instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest::.ctor()
0xcca6  ldarg.0
0xcca7  ldstr    aRenamefolderna// "RenameFolderName"
0xccac  call     instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest::set_RequestName(string)
0xccb1  ldarg.0
0xccb2  ldnull
0xccb3  call     instance void Microsoft.Crm.Sdk.Messages.Internal.RenameFolderNameRequest::set_SiteUrl(string value)
0xccb8  ldarg.0
0xccb9  ldnull
0xccba  call     instance void Microsoft.Crm.Sdk.Messages.Internal.RenameFolderNameRequest::set_FolderPath(string value)
0xccbf  ldarg.0
0xccc0  ldnull
0xccc1  call     instance void Microsoft.Crm.Sdk.Messages.Internal.RenameFolderNameRequest::set_NewFolderName(string value)
0xccc6  ret
```
