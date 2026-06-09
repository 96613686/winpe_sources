# Microsoft.Crm.Sdk.Crm2007.UpdateEntityRequest::Process

- ea: `0xb340`
- end: `0xb35d`
- name: `Microsoft.Crm.Sdk.Crm2007.UpdateEntityRequest::Process`
- size: `29`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callees

- `0xb360`
- `0xb380`
- `0xb3c0`

## pseudocode

```c

```

## disassembly

```asm
0xb340  newobj   instance void [Microsoft.Crm.MetadataService]Microsoft.Crm.Sdk.Metadata.LegacyMetadataServiceProvider::.ctor()
0xb345  ldarg.0
0xb346  call     instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.EntityMetadata Microsoft.Crm.Sdk.Crm2007.UpdateEntityRequest::get_Entity()
0xb34b  ldarg.0
0xb34c  call     instance bool Microsoft.Crm.Sdk.Crm2007.UpdateEntityRequest::get_MergeLabels()
0xb351  ldarg.1
0xb352  callvirt instance void [Microsoft.Crm.MetadataService]Microsoft.Crm.Sdk.Metadata.LegacyMetadataServiceProvider::UpdateEntity(class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.EntityMetadata, bool, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0xb357  newobj   instance void Microsoft.Crm.Sdk.Crm2007.UpdateEntityResponse::.ctor()
0xb35c  ret
```
