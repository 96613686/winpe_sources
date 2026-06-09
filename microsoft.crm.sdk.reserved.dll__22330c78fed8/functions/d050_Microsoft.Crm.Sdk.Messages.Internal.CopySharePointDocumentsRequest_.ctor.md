# Microsoft.Crm.Sdk.Messages.Internal.CopySharePointDocumentsRequest::.ctor

- ea: `0xd050`
- end: `0xd08c`
- name: `Microsoft.Crm.Sdk.Messages.Internal.CopySharePointDocumentsRequest::.ctor`
- size: `60`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0xcea0`
- `0xcef0`
- `0xcf40`
- `0xcf90`
- `0xcfe0`
- `0xd030`

## string_xrefs

- `0xd057`: `CopySharePointDocuments`

## pseudocode

```c

```

## disassembly

```asm
0xd050  ldarg.0
0xd051  call     instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest::.ctor()
0xd056  ldarg.0
0xd057  ldstr    aCopysharepoint// "CopySharePointDocuments"
0xd05c  call     instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest::set_RequestName(string)
0xd061  ldarg.0
0xd062  ldnull
0xd063  call     instance void Microsoft.Crm.Sdk.Messages.Internal.CopySharePointDocumentsRequest::set_DestinationLocation(string value)
0xd068  ldarg.0
0xd069  ldnull
0xd06a  call     instance void Microsoft.Crm.Sdk.Messages.Internal.CopySharePointDocumentsRequest::set_ParentEntityReference(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference value)
0xd06f  ldarg.0
0xd070  ldnull
0xd071  call     instance void Microsoft.Crm.Sdk.Messages.Internal.CopySharePointDocumentsRequest::set_FolderPath(string value)
0xd076  ldarg.0
0xd077  ldnull
0xd078  call     instance void Microsoft.Crm.Sdk.Messages.Internal.CopySharePointDocumentsRequest::set_AbsoluteUrls(string[] value)
0xd07d  ldarg.0
0xd07e  ldnull
0xd07f  call     instance void Microsoft.Crm.Sdk.Messages.Internal.CopySharePointDocumentsRequest::set_RelativeUrls(string[] value)
0xd084  ldarg.0
0xd085  ldnull
0xd086  call     instance void Microsoft.Crm.Sdk.Messages.Internal.CopySharePointDocumentsRequest::set_Source(string value)
0xd08b  ret
```
