# Microsoft.Crm.Application.WebServices.SystemCustomization.EntityUpdate::GetAssociatedFeedbackParams

- ea: `0x3f20`
- end: `0x3f7c`
- name: `Microsoft.Crm.Application.WebServices.SystemCustomization.EntityUpdate::GetAssociatedFeedbackParams`
- size: `92`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x3450`

## callees

- `0x190`
- `0x1a0`
- `0x290`
- `0x3f20`

## pseudocode

```c

```

## disassembly

```asm
0x3f20  ldarg.2
0x3f21  ldstr    aAssociatedenti// "associatedentity"
0x3f26  callvirt instance bool Microsoft.Crm.Application.WebServices.ParameterBag::Exists(string name)
0x3f2b  brfalse.s loc_3F7B
0x3f2d  ldarg.2
0x3f2e  ldstr    aAssociatedenti// "associatedentity"
0x3f33  callvirt instance class Microsoft.Crm.Application.WebServices.ParameterBag Microsoft.Crm.Application.WebServices.ParameterBag::GetBag(string name)
0x3f38  stloc.0
0x3f39  call     class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl [Microsoft.Crm.Core]Microsoft.Crm.FeatureControl::get_Current()
0x3f3e  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl::get_Features()
0x3f43  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer::get_Feedback()
0x3f48  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x3f4d  call     bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.FeatureEnabledHelper::IsFeatureEnabled(class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x3f52  brfalse.s loc_3F7B
0x3f54  ldarg.0
0x3f55  callvirt instance bool [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.EntityUpdateInfo::get_HasRelatedFeedback()
0x3f5a  brtrue.s loc_3F7B
0x3f5c  ldloc.0
0x3f5d  ldstr    aFeedback// "feedback"
0x3f62  callvirt instance bool Microsoft.Crm.Application.WebServices.ParameterBag::Exists(string name)
0x3f67  brfalse.s loc_3F7B
0x3f69  ldarg.0
0x3f6a  ldloc.0
0x3f6b  ldstr    aFeedback// "feedback"
0x3f70  ldc.i4.0
0x3f71  callvirt instance bool Microsoft.Crm.Application.WebServices.ParameterBag::GetBool(string name, bool defaultValue)
0x3f76  callvirt instance void [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.EntityUpdateInfo::set_HasRelatedFeedback(bool)
0x3f7b  ret
```
