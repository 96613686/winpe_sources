# Microsoft.Crm.Application.WebServices.SystemCustomization.EntityDelete::GetEntityLogicalName

- ea: `0x3100`
- end: `0x3129`
- name: `Microsoft.Crm.Application.WebServices.SystemCustomization.EntityDelete::GetEntityLogicalName`
- size: `41`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x3040`

## callees

- `0x3100`

## pseudocode

```c

```

## disassembly

```asm
0x3100  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x3105  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x310a  ldarg.0
0x310b  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::GetEntity(valuetype [mscorlib]System.Guid)
0x3110  stloc.0
0x3111  ldloc.0
0x3112  brfalse.s loc_311C
0x3114  ldloc.0
0x3115  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_LogicalName()
0x311a  brtrue.s loc_3122
0x311c  ldsfld   string [mscorlib]System.String::Empty
0x3121  ret
0x3122  ldloc.0
0x3123  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_LogicalName()
0x3128  ret
```
