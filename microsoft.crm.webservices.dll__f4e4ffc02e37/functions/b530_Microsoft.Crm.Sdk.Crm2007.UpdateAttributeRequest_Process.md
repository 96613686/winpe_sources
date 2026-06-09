# Microsoft.Crm.Sdk.Crm2007.UpdateAttributeRequest::Process

- ea: `0xb530`
- end: `0xb553`
- name: `Microsoft.Crm.Sdk.Crm2007.UpdateAttributeRequest::Process`
- size: `35`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callees

- `0xb560`
- `0xb580`
- `0xb5a0`
- `0xb5e0`

## pseudocode

```c

```

## disassembly

```asm
0xb530  newobj   instance void [Microsoft.Crm.MetadataService]Microsoft.Crm.Sdk.Metadata.LegacyMetadataServiceProvider::.ctor()
0xb535  ldarg.0
0xb536  call     instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.AttributeMetadata Microsoft.Crm.Sdk.Crm2007.UpdateAttributeRequest::get_Attribute()
0xb53b  ldarg.0
0xb53c  call     instance string Microsoft.Crm.Sdk.Crm2007.UpdateAttributeRequest::get_EntityName()
0xb541  ldarg.0
0xb542  call     instance bool Microsoft.Crm.Sdk.Crm2007.UpdateAttributeRequest::get_MergeLabels()
0xb547  ldarg.1
0xb548  callvirt instance void [Microsoft.Crm.MetadataService]Microsoft.Crm.Sdk.Metadata.LegacyMetadataServiceProvider::UpdateAttribute(class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.AttributeMetadata, string, bool, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0xb54d  newobj   instance void Microsoft.Crm.Sdk.Crm2007.UpdateAttributeResponse::.ctor()
0xb552  ret
```
