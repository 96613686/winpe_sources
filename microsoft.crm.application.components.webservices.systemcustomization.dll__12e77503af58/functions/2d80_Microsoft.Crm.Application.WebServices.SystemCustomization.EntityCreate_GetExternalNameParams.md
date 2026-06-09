# Microsoft.Crm.Application.WebServices.SystemCustomization.EntityCreate::GetExternalNameParams

- ea: `0x2d80`
- end: `0x2db3`
- name: `Microsoft.Crm.Application.WebServices.SystemCustomization.EntityCreate::GetExternalNameParams`
- size: `51`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x26f0`

## callees

- `0x200`
- `0x2d80`

## pseudocode

```c

```

## disassembly

```asm
0x2d80  call     class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl [Microsoft.Crm.Core]Microsoft.Crm.FeatureControl::get_Current()
0x2d85  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl::get_Features()
0x2d8a  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer::get_VirtualEntity()
0x2d8f  callvirt instance string [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail::get_Name()
0x2d94  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x2d99  call     bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.FeatureEnabledHelper::IsFeatureEnabled(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x2d9e  brfalse.s loc_2DB2
0x2da0  ldarg.0
0x2da1  ldarg.1
0x2da2  ldstr    aExternalname// "externalname"
0x2da7  ldnull
0x2da8  callvirt instance string Microsoft.Crm.Application.WebServices.ParameterBag::GetString(string name, string defaultValue)
0x2dad  callvirt instance void [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.EntityCreateInfo::set_ExternalName(string)
0x2db2  ret
```
