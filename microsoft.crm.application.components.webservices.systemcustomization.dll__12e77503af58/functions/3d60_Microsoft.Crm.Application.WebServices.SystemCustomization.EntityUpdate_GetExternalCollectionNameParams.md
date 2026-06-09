# Microsoft.Crm.Application.WebServices.SystemCustomization.EntityUpdate::GetExternalCollectionNameParams

- ea: `0x3d60`
- end: `0x3d93`
- name: `Microsoft.Crm.Application.WebServices.SystemCustomization.EntityUpdate::GetExternalCollectionNameParams`
- size: `51`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x3450`

## callees

- `0x200`
- `0x3d60`

## pseudocode

```c

```

## disassembly

```asm
0x3d60  call     class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl [Microsoft.Crm.Core]Microsoft.Crm.FeatureControl::get_Current()
0x3d65  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl::get_Features()
0x3d6a  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer::get_VirtualEntity()
0x3d6f  callvirt instance string [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail::get_Name()
0x3d74  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x3d79  call     bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.FeatureEnabledHelper::IsFeatureEnabled(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x3d7e  brfalse.s loc_3D92
0x3d80  ldarg.0
0x3d81  ldarg.1
0x3d82  ldstr    aExternalcollec// "externalcollectionname"
0x3d87  ldnull
0x3d88  callvirt instance string Microsoft.Crm.Application.WebServices.ParameterBag::GetString(string name, string defaultValue)
0x3d8d  callvirt instance void [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.EntityUpdateInfo::set_ExternalCollectionName(string)
0x3d92  ret
```
