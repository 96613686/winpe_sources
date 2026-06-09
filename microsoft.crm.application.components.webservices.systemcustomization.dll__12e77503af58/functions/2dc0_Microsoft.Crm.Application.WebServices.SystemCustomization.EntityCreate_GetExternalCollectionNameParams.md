# Microsoft.Crm.Application.WebServices.SystemCustomization.EntityCreate::GetExternalCollectionNameParams

- ea: `0x2dc0`
- end: `0x2df3`
- name: `Microsoft.Crm.Application.WebServices.SystemCustomization.EntityCreate::GetExternalCollectionNameParams`
- size: `51`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x26f0`

## callees

- `0x200`
- `0x2dc0`

## pseudocode

```c

```

## disassembly

```asm
0x2dc0  call     class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl [Microsoft.Crm.Core]Microsoft.Crm.FeatureControl::get_Current()
0x2dc5  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl::get_Features()
0x2dca  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer::get_VirtualEntity()
0x2dcf  callvirt instance string [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail::get_Name()
0x2dd4  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x2dd9  call     bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.FeatureEnabledHelper::IsFeatureEnabled(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x2dde  brfalse.s loc_2DF2
0x2de0  ldarg.0
0x2de1  ldarg.1
0x2de2  ldstr    aExternalcollec// "externalcollectionname"
0x2de7  ldnull
0x2de8  callvirt instance string Microsoft.Crm.Application.WebServices.ParameterBag::GetString(string name, string defaultValue)
0x2ded  callvirt instance void [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.EntityCreateInfo::set_ExternalCollectionName(string)
0x2df2  ret
```
