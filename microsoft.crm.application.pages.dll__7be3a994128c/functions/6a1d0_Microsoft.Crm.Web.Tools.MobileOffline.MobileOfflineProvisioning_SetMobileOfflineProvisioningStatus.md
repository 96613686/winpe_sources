# Microsoft.Crm.Web.Tools.MobileOffline.MobileOfflineProvisioning::SetMobileOfflineProvisioningStatus

- ea: `0x6a1d0`
- end: `0x6a57d`
- name: `Microsoft.Crm.Web.Tools.MobileOffline.MobileOfflineProvisioning::SetMobileOfflineProvisioningStatus`
- size: `941`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, broker_com_uri`

## callers

- `0x69f80`

## callees

- `0x69e50`
- `0x69e60`
- `0x69e70`
- `0x69e80`
- `0x69ea0`
- `0x69ec0`
- `0x69ee0`
- `0x69f00`
- `0x69f20`
- `0x69f40`
- `0x6a1d0`

## string_xrefs

- `0x6a2b6`: `Web.Tools.MobileOfflineProvisioning.Config.MobileOfflineProvisioningStatusInProcess`
- `0x6a2db`: `Web.Tools.MobileOfflineProvisioning.Config.MobileOfflineDedicatedStatusInProcess`
- `0x6a215`: `<a id='a_helplink' target='_blank' class='help_link' href='{0}' selectEnable='true' >{1}</a>`
- `0x6a257`: `Web.Tools.MobileOfflineProvisioning.Config.MobileOfflineProvisioningStatusFailed`
- `0x6a27c`: `Web.Tools.MobileOfflineProvisioning.Config.MobileOfflineDeprovisioningStatusFailed`
- `0x6a2c7`: `Web.Tools.MobileOfflineProvisioning.Config.MobileOfflineProvisioningStatusCompleted`
- `0x6a2ec`: `Web.Tools.MobileOfflineProvisioning.Config.MobileOfflineDedicatedStatusCompleted`

## pseudocode

```c

```

## disassembly

```asm
0x6a1d0  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x6a1d5  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_OrganizationId()
0x6a1da  call     void [Microsoft.Crm]Microsoft.Crm.MobileOfflineUtility::ReInitializeOrgApplicationMapIfGroupIdInvalid(valuetype [mscorlib]System.Guid)
0x6a1df  ldarg.0
0x6a1e0  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x6a1e5  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_OrganizationId()
0x6a1ea  ldc.i4.1
0x6a1eb  ldnull
0x6a1ec  call     class [Microsoft.Crm]Microsoft.Crm.IMobileOfflineState [Microsoft.Crm]Microsoft.Crm.MobileOfflineUtility::Read(valuetype [mscorlib]System.Guid, bool, string)
0x6a1f1  callvirt instance int32 [Microsoft.Crm]Microsoft.Crm.IMobileOfflineState::get_MobileOfflineStatus()
0x6a1f6  call     instance void Microsoft.Crm.Web.Tools.MobileOffline.MobileOfflineProvisioning::set_MobileOfflineStatus(int32 value)
0x6a1fb  ldarg.0
0x6a1fc  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x6a201  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_OrganizationId()
0x6a206  call     bool [Microsoft.Crm]Microsoft.Crm.MobileOfflineUtility::IsOrgDedicated(valuetype [mscorlib]System.Guid)
0x6a20b  call     instance void Microsoft.Crm.Web.Tools.MobileOffline.MobileOfflineProvisioning::set_OrgDedicated(bool value)
0x6a210  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentCulture()
0x6a215  ldstr    aAIdAHelplinkTa_1// "<a id='a_helplink' target='_blank' clas"...
0x6a21a  ldc.i4.2
0x6a21b  newarr   [mscorlib]System.Object
0x6a220  dup
0x6a221  ldc.i4.0
0x6a222  ldarg.0
0x6a223  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x6a228  ldstr    aCrmSupportAddr// "CRM_Support_Address"
0x6a22d  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x6a232  stelem.ref
0x6a233  dup
0x6a234  ldc.i4.1
0x6a235  ldarg.0
0x6a236  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x6a23b  ldstr    aCrmSupportMess// "CRM_Support_Message"
0x6a240  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x6a245  stelem.ref
0x6a246  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x6a24b  stloc.0
0x6a24c  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentCulture()
0x6a251  ldarg.0
0x6a252  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x6a257  ldstr    aWebToolsMobile_9// "Web.Tools.MobileOfflineProvisioning.Con"...
0x6a25c  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x6a261  ldc.i4.1
0x6a262  newarr   [mscorlib]System.Object
0x6a267  dup
0x6a268  ldc.i4.0
0x6a269  ldloc.0
0x6a26a  stelem.ref
0x6a26b  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x6a270  stloc.1
0x6a271  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentCulture()
0x6a276  ldarg.0
0x6a277  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x6a27c  ldstr    aWebToolsMobile_10// "Web.Tools.MobileOfflineProvisioning.Con"...
0x6a281  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x6a286  ldc.i4.1
0x6a287  newarr   [mscorlib]System.Object
0x6a28c  dup
0x6a28d  ldc.i4.0
0x6a28e  ldloc.0
0x6a28f  stelem.ref
0x6a290  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x6a295  stloc.2
0x6a296  ldarg.0
0x6a297  call     instance bool Microsoft.Crm.Web.Tools.MobileOffline.MobileOfflineProvisioning::get_OrgDedicated()
0x6a29c  brfalse.s loc_6A2B0
0x6a29e  ldarg.0
0x6a29f  call     instance int32 Microsoft.Crm.Web.Tools.MobileOffline.MobileOfflineProvisioning::get_MobileOfflineStatus()
0x6a2a4  ldc.i4.1
0x6a2a5  beq.s    loc_6A2B0
0x6a2a7  ldarg.0
0x6a2a8  call     instance int32 Microsoft.Crm.Web.Tools.MobileOffline.MobileOfflineProvisioning::get_MobileOfflineStatus()
0x6a2ad  ldc.i4.4
0x6a2ae  bne.un.s loc_6A2D5
0x6a2b0  ldarg.0
0x6a2b1  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x6a2b6  ldstr    aWebToolsMobile_3// "Web.Tools.MobileOfflineProvisioning.Con"...
0x6a2bb  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x6a2c0  stloc.3
0x6a2c1  ldarg.0
0x6a2c2  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x6a2c7  ldstr    aWebToolsMobile_11// "Web.Tools.MobileOfflineProvisioning.Con"...
0x6a2cc  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x6a2d1  stloc.s  4
0x6a2d3  br.s     loc_6A2F8
0x6a2d5  ldarg.0
0x6a2d6  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x6a2db  ldstr    aWebToolsMobile_4// "Web.Tools.MobileOfflineProvisioning.Con"...
0x6a2e0  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x6a2e5  stloc.3
0x6a2e6  ldarg.0
0x6a2e7  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x6a2ec  ldstr    aWebToolsMobile_12// "Web.Tools.MobileOfflineProvisioning.Con"...
0x6a2f1  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x6a2f6  stloc.s  4
0x6a2f8  ldarg.0
0x6a2f9  call     instance int32 Microsoft.Crm.Web.Tools.MobileOffline.MobileOfflineProvisioning::get_MobileOfflineStatus()
0x6a2fe  stloc.s  5
0x6a300  ldloc.s  5
0x6a302  ldc.i4.1
0x6a303  sub
0x6a304  switch   loc_6A483, loc_6A37D, loc_6A326, loc_6A42C, loc_6A3D5, loc_6A4DB
0x6a321  br       loc_6A532
0x6a326  ldarg.0
0x6a327  ldfld    class [System.Web]System.Web.UI.WebControls.Label Microsoft.Crm.Web.Tools.MobileOffline.MobileOfflineProvisioning::enableStatusLabel
0x6a32c  ldloc.3
0x6a32d  callvirt instance void [System.Web]System.Web.UI.WebControls.Label::set_Text(string)
0x6a332  ldarg.0
0x6a333  ldfld    class [System.Web]System.Web.UI.WebControls.Label Microsoft.Crm.Web.Tools.MobileOffline.MobileOfflineProvisioning::disableStatusLabel
0x6a338  ldsfld   string [mscorlib]System.String::Empty
0x6a33d  callvirt instance void [System.Web]System.Web.UI.WebControls.Label::set_Text(string)
0x6a342  ldarg.0
0x6a343  ldfld    class [System.Web]System.Web.UI.WebControls.Label Microsoft.Crm.Web.Tools.MobileOffline.MobileOfflineProvisioning::enableStatusLabel
0x6a348  ldstr    aProvisioningEr// "provisioning-errorMessage"
0x6a34d  callvirt instance void [System.Web]System.Web.UI.WebControls.WebControl::set_CssClass(string)
0x6a352  ldarg.0
0x6a353  ldc.i4.1
0x6a354  call     instance void Microsoft.Crm.Web.Tools.MobileOffline.MobileOfflineProvisioning::set_DisableMobileOfflineEnabledRadio(bool value)
0x6a359  ldarg.0
0x6a35a  ldc.i4.1
0x6a35b  call     instance void Microsoft.Crm.Web.Tools.MobileOffline.MobileOfflineProvisioning::set_DisableMobileOfflineDisabledRadio(bool value)
0x6a360  ldarg.0
0x6a361  ldc.i4.1
0x6a362  call     instance void Microsoft.Crm.Web.Tools.MobileOffline.MobileOfflineProvisioning::set_HideMobileOfflineEnabledRadio(bool value)
0x6a367  ldarg.0
0x6a368  ldc.i4.1
0x6a369  call     instance void Microsoft.Crm.Web.Tools.MobileOffline.MobileOfflineProvisioning::set_HideMobileOfflineDisabledRadio(bool value)
0x6a36e  ldarg.0
0x6a36f  ldc.i4.1
0x6a370  call     instance void Microsoft.Crm.Web.Tools.MobileOffline.MobileOfflineProvisioning::set_IsEnableSelected(bool value)
0x6a375  ldarg.0
0x6a376  ldc.i4.0
0x6a377  call     instance void Microsoft.Crm.Web.Tools.MobileOffline.MobileOfflineProvisioning::set_IsDisableSelected(bool value)
0x6a37c  ret
0x6a37d  ldarg.0
0x6a37e  ldfld    class [System.Web]System.Web.UI.WebControls.Label Microsoft.Crm.Web.Tools.MobileOffline.MobileOfflineProvisioning::enableStatusLabel
0x6a383  ldloc.s  4
0x6a385  callvirt instance void [System.Web]System.Web.UI.WebControls.Label::set_Text(string)
0x6a38a  ldarg.0
0x6a38b  ldfld    class [System.Web]System.Web.UI.WebControls.Label Microsoft.Crm.Web.Tools.MobileOffline.MobileOfflineProvisioning::disableStatusLabel
0x6a390  ldsfld   string [mscorlib]System.String::Empty
0x6a395  callvirt instance void [System.Web]System.Web.UI.WebControls.Label::set_Text(string)
0x6a39a  ldarg.0
0x6a39b  ldfld    class [System.Web]System.Web.UI.WebControls.Label Microsoft.Crm.Web.Tools.MobileOffline.MobileOfflineProvisioning::enableStatusLabel
0x6a3a0  ldstr    aProvisioningSt// "provisioning-statusMessage"
0x6a3a5  callvirt instance void [System.Web]System.Web.UI.WebControls.WebControl::set_CssClass(string)
0x6a3aa  ldarg.0
0x6a3ab  ldc.i4.0
0x6a3ac  call     instance void Microsoft.Crm.Web.Tools.MobileOffline.MobileOfflineProvisioning::set_DisableMobileOfflineEnabledRadio(bool value)
0x6a3b1  ldarg.0
0x6a3b2  ldc.i4.0
0x6a3b3  call     instance void Microsoft.Crm.Web.Tools.MobileOffline.MobileOfflineProvisioning::set_DisableMobileOfflineDisabledRadio(bool value)
0x6a3b8  ldarg.0
0x6a3b9  ldc.i4.1
0x6a3ba  call     instance void Microsoft.Crm.Web.Tools.MobileOffline.MobileOfflineProvisioning::set_HideMobileOfflineEnabledRadio(bool value)
0x6a3bf  ldarg.0
0x6a3c0  ldc.i4.0
0x6a3c1  call     instance void Microsoft.Crm.Web.Tools.MobileOffline.MobileOfflineProvisioning::set_HideMobileOfflineDisabledRadio(bool value)
0x6a3c6  ldarg.0
0x6a3c7  ldc.i4.1
0x6a3c8  call     instance void Microsoft.Crm.Web.Tools.MobileOffline.MobileOfflineProvisioning::set_IsEnableSelected(bool value)
0x6a3cd  ldarg.0
0x6a3ce  ldc.i4.0
0x6a3cf  call     instance void Microsoft.Crm.Web.Tools.MobileOffline.MobileOfflineProvisioning::set_IsDisableSelected(bool value)
0x6a3d4  ret
0x6a3d5  ldarg.0
0x6a3d6  ldfld    class [System.Web]System.Web.UI.WebControls.Label Microsoft.Crm.Web.Tools.MobileOffline.MobileOfflineProvisioning::enableStatusLabel
0x6a3db  ldloc.1
0x6a3dc  callvirt instance void [System.Web]System.Web.UI.WebControls.Label::set_Text(string)
0x6a3e1  ldarg.0
0x6a3e2  ldfld    class [System.Web]System.Web.UI.WebControls.Label Microsoft.Crm.Web.Tools.MobileOffline.MobileOfflineProvisioning::disableStatusLabel
0x6a3e7  ldsfld   string [mscorlib]System.String::Empty
0x6a3ec  callvirt instance void [System.Web]System.Web.UI.WebControls.Label::set_Text(string)
0x6a3f1  ldarg.0
0x6a3f2  ldfld    class [System.Web]System.Web.UI.WebControls.Label Microsoft.Crm.Web.Tools.MobileOffline.MobileOfflineProvisioning::enableStatusLabel
0x6a3f7  ldstr    aProvisioningEr// "provisioning-errorMessage"
0x6a3fc  callvirt instance void [System.Web]System.Web.UI.WebControls.WebControl::set_CssClass(string)
0x6a401  ldarg.0
0x6a402  ldc.i4.0
0x6a403  call     instance void Microsoft.Crm.Web.Tools.MobileOffline.MobileOfflineProvisioning::set_DisableMobileOfflineEnabledRadio(bool value)
0x6a408  ldarg.0
0x6a409  ldc.i4.1
0x6a40a  call     instance void Microsoft.Crm.Web.Tools.MobileOffline.MobileOfflineProvisioning::set_DisableMobileOfflineDisabledRadio(bool value)
0x6a40f  ldarg.0
0x6a410  ldc.i4.0
0x6a411  call     instance void Microsoft.Crm.Web.Tools.MobileOffline.MobileOfflineProvisioning::set_HideMobileOfflineEnabledRadio(bool value)
0x6a416  ldarg.0
0x6a417  ldc.i4.1
0x6a418  call     instance void Microsoft.Crm.Web.Tools.MobileOffline.MobileOfflineProvisioning::set_HideMobileOfflineDisabledRadio(bool value)
0x6a41d  ldarg.0
0x6a41e  ldc.i4.0
0x6a41f  call     instance void Microsoft.Crm.Web.Tools.MobileOffline.MobileOfflineProvisioning::set_IsEnableSelected(bool value)
0x6a424  ldarg.0
0x6a425  ldc.i4.0
0x6a426  call     instance void Microsoft.Crm.Web.Tools.MobileOffline.MobileOfflineProvisioning::set_IsDisableSelected(bool value)
0x6a42b  ret
0x6a42c  ldarg.0
0x6a42d  ldfld    class [System.Web]System.Web.UI.WebControls.Label Microsoft.Crm.Web.Tools.MobileOffline.MobileOfflineProvisioning::enableStatusLabel
0x6a432  ldsfld   string [mscorlib]System.String::Empty
0x6a437  callvirt instance void [System.Web]System.Web.UI.WebControls.Label::set_Text(string)
0x6a43c  ldarg.0
0x6a43d  ldfld    class [System.Web]System.Web.UI.WebControls.Label Microsoft.Crm.Web.Tools.MobileOffline.MobileOfflineProvisioning::disableStatusLabel
0x6a442  ldloc.3
0x6a443  callvirt instance void [System.Web]System.Web.UI.WebControls.Label::set_Text(string)
0x6a448  ldarg.0
0x6a449  ldfld    class [System.Web]System.Web.UI.WebControls.Label Microsoft.Crm.Web.Tools.MobileOffline.MobileOfflineProvisioning::disableStatusLabel
0x6a44e  ldstr    aProvisioningEr// "provisioning-errorMessage"
0x6a453  callvirt instance void [System.Web]System.Web.UI.WebControls.WebControl::set_CssClass(string)
0x6a458  ldarg.0
0x6a459  ldc.i4.1
0x6a45a  call     instance void Microsoft.Crm.Web.Tools.MobileOffline.MobileOfflineProvisioning::set_DisableMobileOfflineEnabledRadio(bool value)
0x6a45f  ldarg.0
0x6a460  ldc.i4.1
0x6a461  call     instance void Microsoft.Crm.Web.Tools.MobileOffline.MobileOfflineProvisioning::set_DisableMobileOfflineDisabledRadio(bool value)
0x6a466  ldarg.0
0x6a467  ldc.i4.1
0x6a468  call     instance void Microsoft.Crm.Web.Tools.MobileOffline.MobileOfflineProvisioning::set_HideMobileOfflineEnabledRadio(bool value)
0x6a46d  ldarg.0
0x6a46e  ldc.i4.1
0x6a46f  call     instance void Microsoft.Crm.Web.Tools.MobileOffline.MobileOfflineProvisioning::set_HideMobileOfflineDisabledRadio(bool value)
0x6a474  ldarg.0
0x6a475  ldc.i4.0
0x6a476  call     instance void Microsoft.Crm.Web.Tools.MobileOffline.MobileOfflineProvisioning::set_IsEnableSelected(bool value)
0x6a47b  ldarg.0
0x6a47c  ldc.i4.1
0x6a47d  call     instance void Microsoft.Crm.Web.Tools.MobileOffline.MobileOfflineProvisioning::set_IsDisableSelected(bool value)
0x6a482  ret
0x6a483  ldarg.0
0x6a484  ldfld    class [System.Web]System.Web.UI.WebControls.Label Microsoft.Crm.Web.Tools.MobileOffline.MobileOfflineProvisioning::enableStatusLabel
0x6a489  ldsfld   string [mscorlib]System.String::Empty
0x6a48e  callvirt instance void [System.Web]System.Web.UI.WebControls.Label::set_Text(string)
0x6a493  ldarg.0
0x6a494  ldfld    class [System.Web]System.Web.UI.WebControls.Label Microsoft.Crm.Web.Tools.MobileOffline.MobileOfflineProvisioning::disableStatusLabel
0x6a499  ldloc.s  4
0x6a49b  callvirt instance void [System.Web]System.Web.UI.WebControls.Label::set_Text(string)
0x6a4a0  ldarg.0
0x6a4a1  ldfld    class [System.Web]System.Web.UI.WebControls.Label Microsoft.Crm.Web.Tools.MobileOffline.MobileOfflineProvisioning::disableStatusLabel
0x6a4a6  ldstr    aProvisioningSt// "provisioning-statusMessage"
0x6a4ab  callvirt instance void [System.Web]System.Web.UI.WebControls.WebControl::set_CssClass(string)
0x6a4b0  ldarg.0
0x6a4b1  ldc.i4.0
0x6a4b2  call     instance void Microsoft.Crm.Web.Tools.MobileOffline.MobileOfflineProvisioning::set_DisableMobileOfflineEnabledRadio(bool value)
0x6a4b7  ldarg.0
0x6a4b8  ldc.i4.0
0x6a4b9  call     instance void Microsoft.Crm.Web.Tools.MobileOffline.MobileOfflineProvisioning::set_DisableMobileOfflineDisabledRadio(bool value)
0x6a4be  ldarg.0
0x6a4bf  ldc.i4.0
0x6a4c0  call     instance void Microsoft.Crm.Web.Tools.MobileOffline.MobileOfflineProvisioning::set_HideMobileOfflineEnabledRadio(bool value)
0x6a4c5  ldarg.0
0x6a4c6  ldc.i4.1
0x6a4c7  call     instance void Microsoft.Crm.Web.Tools.MobileOffline.MobileOfflineProvisioning::set_HideMobileOfflineDisabledRadio(bool value)
0x6a4cc  ldarg.0
0x6a4cd  ldc.i4.0
0x6a4ce  call     instance void Microsoft.Crm.Web.Tools.MobileOffline.MobileOfflineProvisioning::set_IsEnableSelected(bool value)
0x6a4d3  ldarg.0
0x6a4d4  ldc.i4.1
0x6a4d5  call     instance void Microsoft.Crm.Web.Tools.MobileOffline.MobileOfflineProvisioning::set_IsDisableSelected(bool value)
0x6a4da  ret
0x6a4db  ldarg.0
0x6a4dc  ldfld    class [System.Web]System.Web.UI.WebControls.Label Microsoft.Crm.Web.Tools.MobileOffline.MobileOfflineProvisioning::enableStatusLabel
0x6a4e1  ldsfld   string [mscorlib]System.String::Empty
0x6a4e6  callvirt instance void [System.Web]System.Web.UI.WebControls.Label::set_Text(string)
0x6a4eb  ldarg.0
0x6a4ec  ldfld    class [System.Web]System.Web.UI.WebControls.Label Microsoft.Crm.Web.Tools.MobileOffline.MobileOfflineProvisioning::disableStatusLabel
0x6a4f1  ldloc.2
0x6a4f2  callvirt instance void [System.Web]System.Web.UI.WebControls.Label::set_Text(string)
0x6a4f7  ldarg.0
0x6a4f8  ldfld    class [System.Web]System.Web.UI.WebControls.Label Microsoft.Crm.Web.Tools.MobileOffline.MobileOfflineProvisioning::disableStatusLabel
0x6a4fd  ldstr    aProvisioningEr// "provisioning-errorMessage"
0x6a502  callvirt instance void [System.Web]System.Web.UI.WebControls.WebControl::set_CssClass(string)
0x6a507  ldarg.0
0x6a508  ldc.i4.0
0x6a509  call     instance void Microsoft.Crm.Web.Tools.MobileOffline.MobileOfflineProvisioning::set_DisableMobileOfflineEnabledRadio(bool value)
0x6a50e  ldarg.0
0x6a50f  ldc.i4.0
0x6a510  call     instance void Microsoft.Crm.Web.Tools.MobileOffline.MobileOfflineProvisioning::set_DisableMobileOfflineDisabledRadio(bool value)
0x6a515  ldarg.0
0x6a516  ldc.i4.1
0x6a517  call     instance void Microsoft.Crm.Web.Tools.MobileOffline.MobileOfflineProvisioning::set_HideMobileOfflineEnabledRadio(bool value)
0x6a51c  ldarg.0
0x6a51d  ldc.i4.0
0x6a51e  call     instance void Microsoft.Crm.Web.Tools.MobileOffline.MobileOfflineProvisioning::set_HideMobileOfflineDisabledRadio(bool value)
0x6a523  ldarg.0
0x6a524  ldc.i4.1
0x6a525  call     instance void Microsoft.Crm.Web.Tools.MobileOffline.MobileOfflineProvisioning::set_IsEnableSelected(bool value)
0x6a52a  ldarg.0
0x6a52b  ldc.i4.0
0x6a52c  call     instance void Microsoft.Crm.Web.Tools.MobileOffline.MobileOfflineProvisioning::set_IsDisableSelected(bool value)
0x6a531  ret
0x6a532  ldarg.0
0x6a533  ldfld    class [System.Web]System.Web.UI.WebControls.Label Microsoft.Crm.Web.Tools.MobileOffline.MobileOfflineProvisioning::enableStatusLabel
0x6a538  ldsfld   string [mscorlib]System.String::Empty
0x6a53d  callvirt instance void [System.Web]System.Web.UI.WebControls.Label::set_Text(string)
0x6a542  ldarg.0
0x6a543  ldfld    class [System.Web]System.Web.UI.WebControls.Label Microsoft.Crm.Web.Tools.MobileOffline.MobileOfflineProvisioning::disableStatusLabel
0x6a548  ldsfld   string [mscorlib]System.String::Empty
0x6a54d  callvirt instance void [System.Web]System.Web.UI.WebControls.Label::set_Text(string)
0x6a552  ldarg.0
0x6a553  ldc.i4.0
0x6a554  call     instance void Microsoft.Crm.Web.Tools.MobileOffline.MobileOfflineProvisioning::set_DisableMobileOfflineEnabledRadio(bool value)
0x6a559  ldarg.0
  ... truncated ...
```
