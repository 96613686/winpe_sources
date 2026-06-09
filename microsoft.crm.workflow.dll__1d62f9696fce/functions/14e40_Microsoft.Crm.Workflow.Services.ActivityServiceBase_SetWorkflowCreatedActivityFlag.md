# Microsoft.Crm.Workflow.Services.ActivityServiceBase::SetWorkflowCreatedActivityFlag

- ea: `0x14e40`
- end: `0x14e8e`
- name: `Microsoft.Crm.Workflow.Services.ActivityServiceBase::SetWorkflowCreatedActivityFlag`
- size: `78`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x16b80`
- `0x2ee70`

## callees

- `0x14770`
- `0x14e40`

## string_xrefs

- `0x14e70`: `isworkflowcreated`
- `0x14e7d`: `isworkflowcreated`

## pseudocode

```c

```

## disassembly

```asm
0x14e40  ldarg.0
0x14e41  call     instance class Microsoft.Crm.Workflow.ICommonWorkflowContext Microsoft.Crm.Workflow.Services.ActivityServiceBase::get_WorkflowContext()
0x14e46  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext::get_OrganizationId()
0x14e4b  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::.ctor(valuetype [mscorlib]System.Guid)
0x14e50  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x14e55  ldarg.1
0x14e56  callvirt instance string [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_LogicalName()
0x14e5b  ldc.i4.1
0x14e5c  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::GetEntity(string, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.NameMappingType)
0x14e61  stloc.0
0x14e62  ldloc.0
0x14e63  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_IsActivity()
0x14e68  brfalse.s loc_14E8D
0x14e6a  ldloc.0
0x14e6b  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IAttributeMetadataCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_AttributesByName()
0x14e70  ldstr    aIsworkflowcrea// "isworkflowcreated"
0x14e75  callvirt instance bool class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IMetadataHashtable`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata>::ContainsKey(object)
0x14e7a  brfalse.s loc_14E8D
0x14e7c  ldarg.1
0x14e7d  ldstr    aIsworkflowcrea// "isworkflowcreated"
0x14e82  ldc.i4.1
0x14e83  box      [mscorlib]System.Boolean
0x14e88  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::set_Item(string, object)
0x14e8d  ret
```
