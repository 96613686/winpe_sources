# Microsoft.Crm.Sdk.Messages.Internal.CreateSharePointFolderRequest::.ctor

- ea: `0xba20`
- end: `0xba4e`
- name: `Microsoft.Crm.Sdk.Messages.Internal.CreateSharePointFolderRequest::.ctor`
- size: `46`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0xb8c0`
- `0xb910`
- `0xb960`
- `0xb9b0`

## string_xrefs

- `0xba27`: `CreateSharePointFolder`

## pseudocode

```c

```

## disassembly

```asm
0xba20  ldarg.0
0xba21  call     instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest::.ctor()
0xba26  ldarg.0
0xba27  ldstr    aCreatesharepoi_0// "CreateSharePointFolder"
0xba2c  call     instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest::set_RequestName(string)
0xba31  ldarg.0
0xba32  ldnull
0xba33  call     instance void Microsoft.Crm.Sdk.Messages.Internal.CreateSharePointFolderRequest::set_FolderName(string value)
0xba38  ldarg.0
0xba39  ldnull
0xba3a  call     instance void Microsoft.Crm.Sdk.Messages.Internal.CreateSharePointFolderRequest::set_Path(string value)
0xba3f  ldarg.0
0xba40  ldnull
0xba41  call     instance void Microsoft.Crm.Sdk.Messages.Internal.CreateSharePointFolderRequest::set_DocumentLibrary(string value)
0xba46  ldarg.0
0xba47  ldnull
0xba48  call     instance void Microsoft.Crm.Sdk.Messages.Internal.CreateSharePointFolderRequest::set_SiteUrl(string value)
0xba4d  ret
```
