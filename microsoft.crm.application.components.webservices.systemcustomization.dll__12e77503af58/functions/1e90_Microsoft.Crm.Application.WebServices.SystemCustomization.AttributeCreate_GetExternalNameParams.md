# Microsoft.Crm.Application.WebServices.SystemCustomization.AttributeCreate::GetExternalNameParams

- ea: `0x1e90`
- end: `0x1ec8`
- name: `Microsoft.Crm.Application.WebServices.SystemCustomization.AttributeCreate::GetExternalNameParams`
- size: `56`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x430`

## callees

- `0x200`
- `0x1e90`

## pseudocode

```c

```

## disassembly

```asm
0x1e90  call     class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl [Microsoft.Crm.Core]Microsoft.Crm.FeatureControl::get_Current()
0x1e95  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl::get_Features()
0x1e9a  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer::get_VirtualEntity()
0x1e9f  callvirt instance string [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail::get_Name()
0x1ea4  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x1ea9  call     bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.FeatureEnabledHelper::IsFeatureEnabled(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x1eae  brfalse.s loc_1EC7
0x1eb0  ldarg.0
0x1eb1  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescriptionPropertyBag [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.AttributeInfo::get_AttributeDescription()
0x1eb6  ldarg.1
0x1eb7  ldstr    aExternalname// "externalname"
0x1ebc  ldnull
0x1ebd  callvirt instance string Microsoft.Crm.Application.WebServices.ParameterBag::GetString(string name, string defaultValue)
0x1ec2  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescription::set_ExternalName(string)
0x1ec7  ret
```
