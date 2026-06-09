# Microsoft.Crm.Application.Components.Sdk.InlineEditControls.Web.CompositionLinkControl::ConfigureHeader

- ea: `0x96f0`
- end: `0x9753`
- name: `Microsoft.Crm.Application.Components.Sdk.InlineEditControls.Web.CompositionLinkControl::ConfigureHeader`
- size: `99`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callees

- `0x9630`
- `0x96f0`
- `0xed30`

## string_xrefs

- `0x96fc`: `/_static/_controls/CompositeData/CompositeDataControl.js`

## pseudocode

```c

```

## disassembly

```asm
0x96f0  ldarg.0
0x96f1  call     instance void Microsoft.Crm.Application.Components.Sdk.InlineEditControls.Web.LinkControl::ConfigureHeader()
0x96f6  ldarg.0
0x96f7  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x96fc  ldstr    aStaticControls_3// "/_static/_controls/CompositeData/Compos"...
0x9701  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x9706  ldarg.0
0x9707  call     instance int32 Microsoft.Crm.Application.Components.Sdk.InlineEditControls.Web.CompositionLinkControl::get_CompositeFieldType()
0x970c  ldc.i4.1
0x970d  bne.un.s loc_972A
0x970f  ldarg.0
0x9710  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x9715  ldstr    aFullnameconven// "FullNameConventionCode"
0x971a  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IOrganizationSettings [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.Organization::get_CurrentSettings()
0x971f  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IOrganizationSettings::get_FullNameConventionCode()
0x9724  conv.i8
0x9725  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, int64)
0x972a  ldarg.0
0x972b  call     instance int32 Microsoft.Crm.Application.Components.Sdk.InlineEditControls.Web.CompositionLinkControl::get_CompositeFieldType()
0x9730  ldc.i4.2
0x9731  bne.un.s loc_9752
0x9733  ldarg.0
0x9734  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x9739  ldstr    aCountrynamelis// "CountryNameList"
0x973e  call     class [Microsoft.Crm]Microsoft.Crm.CompositeAddress.CountryTable [Microsoft.Crm]Microsoft.Crm.CompositeAddress.CountryTable::get_Instance()
0x9743  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentUICulture()
0x9748  callvirt instance string [Microsoft.Crm]Microsoft.Crm.CompositeAddress.CountryTable::CreateJsonObject(class [mscorlib]System.Globalization.CultureInfo)
0x974d  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, string)
0x9752  ret
```
