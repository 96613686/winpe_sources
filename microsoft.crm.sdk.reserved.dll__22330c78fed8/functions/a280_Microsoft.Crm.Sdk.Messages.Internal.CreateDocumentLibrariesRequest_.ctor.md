# Microsoft.Crm.Sdk.Messages.Internal.CreateDocumentLibrariesRequest::.ctor

- ea: `0xa280`
- end: `0xa2a0`
- name: `Microsoft.Crm.Sdk.Messages.Internal.CreateDocumentLibrariesRequest::.ctor`
- size: `32`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0xa210`
- `0xa260`

## string_xrefs

- `0xa287`: `CreateDocumentLibraries`

## pseudocode

```c

```

## disassembly

```asm
0xa280  ldarg.0
0xa281  call     instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest::.ctor()
0xa286  ldarg.0
0xa287  ldstr    aCreatedocument// "CreateDocumentLibraries"
0xa28c  call     instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest::set_RequestName(string)
0xa291  ldarg.0
0xa292  ldnull
0xa293  call     instance void Microsoft.Crm.Sdk.Messages.Internal.CreateDocumentLibrariesRequest::set_DocumentLibraryNames(string value)
0xa298  ldarg.0
0xa299  ldnull
0xa29a  call     instance void Microsoft.Crm.Sdk.Messages.Internal.CreateDocumentLibrariesRequest::set_Url(string value)
0xa29f  ret
```
