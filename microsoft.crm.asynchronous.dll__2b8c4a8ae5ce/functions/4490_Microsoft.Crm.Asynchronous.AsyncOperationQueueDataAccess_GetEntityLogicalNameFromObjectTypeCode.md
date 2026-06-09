# Microsoft.Crm.Asynchronous.AsyncOperationQueueDataAccess::GetEntityLogicalNameFromObjectTypeCode

- ea: `0x4490`
- end: `0x44b1`
- name: `Microsoft.Crm.Asynchronous.AsyncOperationQueueDataAccess::GetEntityLogicalNameFromObjectTypeCode`
- size: `33`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x4430`
- `0x4460`

## callees

- `0xd5a0`

## pseudocode

```c

```

## disassembly

```asm
0x4490  ldarg.0
0x4491  call     instance class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration Microsoft.Crm.Asynchronous.DataAccessBase::get_Configuration()
0x4496  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration::get_OrganizationId()
0x449b  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::.ctor(valuetype [mscorlib]System.Guid)
0x44a0  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x44a5  ldarg.1
0x44a6  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::GetEntity(int32)
0x44ab  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_LogicalName()
0x44b0  ret
```
