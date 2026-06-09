# Microsoft.Crm.Sdk.Messages.Internal.UpdateDocumentManagementSettingsRequest::.ctor

- ea: `0xa930`
- end: `0xa965`
- name: `Microsoft.Crm.Sdk.Messages.Internal.UpdateDocumentManagementSettingsRequest::.ctor`
- size: `53`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0xa7d0`
- `0xa820`
- `0xa870`
- `0xa8c0`
- `0xa910`

## string_xrefs

- `0xa937`: `UpdateDocumentManagementSettings`

## pseudocode

```c

```

## disassembly

```asm
0xa930  ldarg.0
0xa931  call     instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest::.ctor()
0xa936  ldarg.0
0xa937  ldstr    aUpdatedocument// "UpdateDocumentManagementSettings"
0xa93c  call     instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest::set_RequestName(string)
0xa941  ldarg.0
0xa942  ldnull
0xa943  call     instance void Microsoft.Crm.Sdk.Messages.Internal.UpdateDocumentManagementSettingsRequest::set_SiteCollection(string value)
0xa948  ldarg.0
0xa949  ldc.i4.0
0xa94a  call     instance void Microsoft.Crm.Sdk.Messages.Internal.UpdateDocumentManagementSettingsRequest::set_FolderStructureEntity(int32 value)
0xa94f  ldarg.0
0xa950  ldnull
0xa951  call     instance void Microsoft.Crm.Sdk.Messages.Internal.UpdateDocumentManagementSettingsRequest::set_EntityDocMgmtXml(string value)
0xa956  ldarg.0
0xa957  ldc.i4.0
0xa958  call     instance void Microsoft.Crm.Sdk.Messages.Internal.UpdateDocumentManagementSettingsRequest::set_ValidateStatus(int32 value)
0xa95d  ldarg.0
0xa95e  ldc.i4.0
0xa95f  call     instance void Microsoft.Crm.Sdk.Messages.Internal.UpdateDocumentManagementSettingsRequest::set_ValidateStatusReason(int32 value)
0xa964  ret
```
