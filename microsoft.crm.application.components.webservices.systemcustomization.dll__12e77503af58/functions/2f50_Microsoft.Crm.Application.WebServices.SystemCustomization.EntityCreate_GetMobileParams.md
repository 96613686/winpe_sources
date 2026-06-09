# Microsoft.Crm.Application.WebServices.SystemCustomization.EntityCreate::GetMobileParams

- ea: `0x2f50`
- end: `0x2fbf`
- name: `Microsoft.Crm.Application.WebServices.SystemCustomization.EntityCreate::GetMobileParams`
- size: `111`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x26f0`

## callees

- `0x190`
- `0x270`
- `0x2b0`
- `0x2f50`

## string_xrefs

- `0x2f74`: `readonlyinmobileclient`

## pseudocode

```c

```

## disassembly

```asm
0x2f50  ldarg.0
0x2f51  ldarg.1
0x2f52  ldstr    aVisibleinmobil// "visibleinmobile"
0x2f57  callvirt instance bool Microsoft.Crm.Application.WebServices.ParameterBag::GetBool(string name)
0x2f5c  callvirt instance void [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.EntityCreateInfo::set_IsVisibleInMobile(bool)
0x2f61  ldarg.0
0x2f62  ldarg.1
0x2f63  ldstr    aVisibleinmobil_0// "visibleinmobileclient"
0x2f68  callvirt instance bool Microsoft.Crm.Application.WebServices.ParameterBag::GetBool(string name)
0x2f6d  callvirt instance void [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.EntityCreateInfo::set_IsVisibleInMobileClient(bool)
0x2f72  ldarg.0
0x2f73  ldarg.1
0x2f74  ldstr    aReadonlyinmobi// "readonlyinmobileclient"
0x2f79  callvirt instance bool Microsoft.Crm.Application.WebServices.ParameterBag::GetBool(string name)
0x2f7e  callvirt instance void [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.EntityCreateInfo::set_IsReadOnlyInMobileClient(bool)
0x2f83  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x2f88  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::IsMocaOfflineFeatureAvailable(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x2f8d  brfalse.s loc_2FBE
0x2f8f  ldarg.0
0x2f90  ldarg.1
0x2f91  ldstr    aOfflineinmobil// "offlineinmobileclient"
0x2f96  callvirt instance bool Microsoft.Crm.Application.WebServices.ParameterBag::GetBool(string name)
0x2f9b  callvirt instance void [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.EntityCreateInfo::set_IsOfflineInMobileClient(bool)
0x2fa0  ldarg.1
0x2fa1  ldstr    aDayssincerecor// "dayssincerecordlastmodified"
0x2fa6  callvirt instance bool Microsoft.Crm.Application.WebServices.ParameterBag::Exists(string name)
0x2fab  brfalse.s loc_2FBE
0x2fad  ldarg.0
0x2fae  ldarg.1
0x2faf  ldstr    aDayssincerecor// "dayssincerecordlastmodified"
0x2fb4  callvirt instance int32 Microsoft.Crm.Application.WebServices.ParameterBag::GetInt(string name)
0x2fb9  callvirt instance void [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.EntityCreateInfo::set_DaysSinceRecordLastModified(int32)
0x2fbe  ret
```
