# Microsoft.Crm.Asynchronous.PublishDuplicateRuleOperation::CreateAsyncOperation

- ea: `0x1e3f0`
- end: `0x1e41e`
- name: `Microsoft.Crm.Asynchronous.PublishDuplicateRuleOperation::CreateAsyncOperation`
- size: `46`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x1e3f0`
- `0x1e420`
- `0x1e570`

## pseudocode

```c

```

## disassembly

```asm
0x1e3f0  ldarg.2
0x1e3f1  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::.ctor(valuetype [mscorlib]System.Guid)
0x1e3f6  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x1e3fb  ldarg.1
0x1e3fc  ldc.i4.1
0x1e3fd  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::GetEntity(string, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.NameMappingType)
0x1e402  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_Code()
0x1e407  stloc.0
0x1e408  ldarg.2
0x1e409  ldarg.1
0x1e40a  ldloc.0
0x1e40b  ldarg.3
0x1e40c  call     bool Microsoft.Crm.Asynchronous.PublishDuplicateRuleOperation::IsAsyncOperationAlreadyPresent(valuetype [mscorlib]System.Guid organizationId, string entityName, int32 entityCode, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationService crmService)
0x1e411  brfalse.s loc_1E414
0x1e413  ret
0x1e414  ldarg.0
0x1e415  ldarg.1
0x1e416  ldarg.2
0x1e417  ldarg.3
0x1e418  call     instance void Microsoft.Crm.Asynchronous.PublishDuplicateRuleOperation::DoCreateAsyncOperation(string entityName, valuetype [mscorlib]System.Guid organizationId, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationService crmService)
0x1e41d  ret
```
