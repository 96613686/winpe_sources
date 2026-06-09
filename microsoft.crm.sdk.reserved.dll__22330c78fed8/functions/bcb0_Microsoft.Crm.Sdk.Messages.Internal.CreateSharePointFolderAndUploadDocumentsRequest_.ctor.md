# Microsoft.Crm.Sdk.Messages.Internal.CreateSharePointFolderAndUploadDocumentsRequest::.ctor

- ea: `0xbcb0`
- end: `0xbcf3`
- name: `Microsoft.Crm.Sdk.Messages.Internal.CreateSharePointFolderAndUploadDocumentsRequest::.ctor`
- size: `67`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `broker_com_uri`

## callees

- `0xbab0`
- `0xbb00`
- `0xbb50`
- `0xbba0`
- `0xbbf0`
- `0xbc40`
- `0xbc90`

## string_xrefs

- `0xbcb7`: `CreateSharePointFolderAndUploadDocuments`

## pseudocode

```c

```

## disassembly

```asm
0xbcb0  ldarg.0
0xbcb1  call     instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest::.ctor()
0xbcb6  ldarg.0
0xbcb7  ldstr    aCreatesharepoi_1// "CreateSharePointFolderAndUploadDocument"...
0xbcbc  call     instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest::set_RequestName(string)
0xbcc1  ldarg.0
0xbcc2  ldnull
0xbcc3  call     instance void Microsoft.Crm.Sdk.Messages.Internal.CreateSharePointFolderAndUploadDocumentsRequest::set_FolderName(string value)
0xbcc8  ldarg.0
0xbcc9  ldnull
0xbcca  call     instance void Microsoft.Crm.Sdk.Messages.Internal.CreateSharePointFolderAndUploadDocumentsRequest::set_Path(string value)
0xbccf  ldarg.0
0xbcd0  ldnull
0xbcd1  call     instance void Microsoft.Crm.Sdk.Messages.Internal.CreateSharePointFolderAndUploadDocumentsRequest::set_DocumentLibrary(string value)
0xbcd6  ldarg.0
0xbcd7  ldnull
0xbcd8  call     instance void Microsoft.Crm.Sdk.Messages.Internal.CreateSharePointFolderAndUploadDocumentsRequest::set_SiteUrl(string value)
0xbcdd  ldarg.0
0xbcde  ldc.i4.0
0xbcdf  call     instance void Microsoft.Crm.Sdk.Messages.Internal.CreateSharePointFolderAndUploadDocumentsRequest::set_IsNoteBookFolder(bool value)
0xbce4  ldarg.0
0xbce5  ldnull
0xbce6  call     instance void Microsoft.Crm.Sdk.Messages.Internal.CreateSharePointFolderAndUploadDocumentsRequest::set_FileName(string[] value)
0xbceb  ldarg.0
0xbcec  ldnull
0xbced  call     instance void Microsoft.Crm.Sdk.Messages.Internal.CreateSharePointFolderAndUploadDocumentsRequest::set_DocumentContents(string[] value)
0xbcf2  ret
```
