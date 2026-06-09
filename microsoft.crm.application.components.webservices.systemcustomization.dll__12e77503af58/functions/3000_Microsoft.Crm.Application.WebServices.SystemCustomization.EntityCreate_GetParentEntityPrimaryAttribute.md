# Microsoft.Crm.Application.WebServices.SystemCustomization.EntityCreate::GetParentEntityPrimaryAttribute

- ea: `0x3000`
- end: `0x302e`
- name: `Microsoft.Crm.Application.WebServices.SystemCustomization.EntityCreate::GetParentEntityPrimaryAttribute`
- size: `46`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x2b70`

## callees

- `0x3000`

## pseudocode

```c

```

## disassembly

```asm
0x3000  ldnull
0x3001  stloc.0
0x3002  ldc.i4.m1
0x3003  stloc.1
0x3004  ldarg.0
0x3005  callvirt instance bool [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.EntityCreateInfo::get_IsActivity()
0x300a  brfalse.s loc_3012
0x300c  ldc.i4   0x1068
0x3011  stloc.1
0x3012  ldloc.1
0x3013  ldc.i4.m1
0x3014  beq.s    loc_302C
0x3016  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x301b  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x3020  ldloc.1
0x3021  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::GetEntity(int32)
0x3026  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_PrimaryField()
0x302b  stloc.0
0x302c  ldloc.0
0x302d  ret
```
