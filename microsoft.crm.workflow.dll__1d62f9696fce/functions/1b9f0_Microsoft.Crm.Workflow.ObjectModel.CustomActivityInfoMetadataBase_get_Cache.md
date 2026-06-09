# Microsoft.Crm.Workflow.ObjectModel.CustomActivityInfoMetadataBase::get_Cache

- ea: `0x1b9f0`
- end: `0x1ba15`
- name: `Microsoft.Crm.Workflow.ObjectModel.CustomActivityInfoMetadataBase::get_Cache`
- size: `37`
- prototype: ``
- caller_count: `10`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1bd20`
- `0x1bf70`
- `0x1c3d0`
- `0x1c490`
- `0x1c500`
- `0x1c560`
- `0x1c800`
- `0x1c830`
- `0x1caf0`
- `0x20bc0`

## callees

- `0x1b9f0`
- `0x1c720`

## pseudocode

```c

```

## disassembly

```asm
0x1b9f0  ldarg.0
0x1b9f1  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Workflow.ObjectModel.CustomActivityInfoMetadataBase::_context
0x1b9f6  brtrue.s loc_1BA09
0x1b9f8  ldarg.0
0x1b9f9  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Workflow.ObjectModel.CustomActivityInfoMetadataBase::get_OrganizationId()
0x1b9fe  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::.ctor(valuetype [mscorlib]System.Guid)
0x1ba03  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x1ba08  ret
0x1ba09  ldarg.0
0x1ba0a  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Workflow.ObjectModel.CustomActivityInfoMetadataBase::_context
0x1ba0f  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x1ba14  ret
```
