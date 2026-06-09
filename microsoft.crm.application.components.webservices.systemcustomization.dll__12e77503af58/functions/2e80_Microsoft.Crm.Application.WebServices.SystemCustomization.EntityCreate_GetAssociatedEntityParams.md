# Microsoft.Crm.Application.WebServices.SystemCustomization.EntityCreate::GetAssociatedEntityParams

- ea: `0x2e80`
- end: `0x2eee`
- name: `Microsoft.Crm.Application.WebServices.SystemCustomization.EntityCreate::GetAssociatedEntityParams`
- size: `110`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x26f0`

## callees

- `0x190`
- `0x290`
- `0x2b0`
- `0x2e80`

## pseudocode

```c

```

## disassembly

```asm
0x2e80  ldarg.0
0x2e81  ldarg.1
0x2e82  ldstr    aNotes// "notes"
0x2e87  callvirt instance bool Microsoft.Crm.Application.WebServices.ParameterBag::GetBool(string name)
0x2e8c  callvirt instance void [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.EntityCreateInfo::set_HasRelatedNotes(bool)
0x2e91  call     class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl [Microsoft.Crm.Core]Microsoft.Crm.FeatureControl::get_Current()
0x2e96  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl::get_Features()
0x2e9b  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer::get_Feedback()
0x2ea0  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x2ea5  call     bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.FeatureEnabledHelper::IsFeatureEnabled(class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x2eaa  brfalse.s loc_2ECB
0x2eac  ldarg.1
0x2ead  ldstr    aFeedback// "feedback"
0x2eb2  callvirt instance bool Microsoft.Crm.Application.WebServices.ParameterBag::Exists(string name)
0x2eb7  brfalse.s loc_2ECB
0x2eb9  ldarg.0
0x2eba  ldarg.1
0x2ebb  ldstr    aFeedback// "feedback"
0x2ec0  ldc.i4.0
0x2ec1  callvirt instance bool Microsoft.Crm.Application.WebServices.ParameterBag::GetBool(string name, bool defaultValue)
0x2ec6  callvirt instance void [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.EntityCreateInfo::set_HasRelatedFeedback(bool)
0x2ecb  ldarg.0
0x2ecc  ldarg.1
0x2ecd  ldstr    aActivities// "activities"
0x2ed2  callvirt instance bool Microsoft.Crm.Application.WebServices.ParameterBag::GetBool(string name)
0x2ed7  callvirt instance void [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.EntityCreateInfo::set_HasRelatedActivities(bool)
0x2edc  ldarg.0
0x2edd  ldarg.1
0x2ede  ldstr    aActivitypartie// "activityparties"
0x2ee3  callvirt instance bool Microsoft.Crm.Application.WebServices.ParameterBag::GetBool(string name)
0x2ee8  callvirt instance void [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.EntityCreateInfo::set_IsActivityParty(bool)
0x2eed  ret
```
