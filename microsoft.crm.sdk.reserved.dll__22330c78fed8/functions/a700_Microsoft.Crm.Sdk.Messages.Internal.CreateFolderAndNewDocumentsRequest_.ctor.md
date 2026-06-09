# Microsoft.Crm.Sdk.Messages.Internal.CreateFolderAndNewDocumentsRequest::.ctor

- ea: `0xa700`
- end: `0xa72e`
- name: `Microsoft.Crm.Sdk.Messages.Internal.CreateFolderAndNewDocumentsRequest::.ctor`
- size: `46`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0xa5a0`
- `0xa5f0`
- `0xa640`
- `0xa690`

## string_xrefs

- `0xa707`: `CreateFolderAndNewDocuments`

## pseudocode

```c

```

## disassembly

```asm
0xa700  ldarg.0
0xa701  call     instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest::.ctor()
0xa706  ldarg.0
0xa707  ldstr    aCreatefolderan// "CreateFolderAndNewDocuments"
0xa70c  call     instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest::set_RequestName(string)
0xa711  ldarg.0
0xa712  ldnull
0xa713  call     instance void Microsoft.Crm.Sdk.Messages.Internal.CreateFolderAndNewDocumentsRequest::set_FolderName(string value)
0xa718  ldarg.0
0xa719  ldnull
0xa71a  call     instance void Microsoft.Crm.Sdk.Messages.Internal.CreateFolderAndNewDocumentsRequest::set_FileNameList(string[] value)
0xa71f  ldarg.0
0xa720  ldc.i4.0
0xa721  call     instance void Microsoft.Crm.Sdk.Messages.Internal.CreateFolderAndNewDocumentsRequest::set_LocationType(int32 value)
0xa726  ldarg.0
0xa727  ldnull
0xa728  call     instance void Microsoft.Crm.Sdk.Messages.Internal.CreateFolderAndNewDocumentsRequest::set_ParentEntityReference(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference value)
0xa72d  ret
```
