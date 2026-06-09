# Microsoft.Crm.Web.Tools.DocumentManagement.S2SDefaultSite::ConfigureForm

- ea: `0x7b450`
- end: `0x7b630`
- name: `Microsoft.Crm.Web.Tools.DocumentManagement.S2SDefaultSite::ConfigureForm`
- size: `480`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callees

- `0x7b450`
- `0x7b630`

## string_xrefs

- `0x7b47e`: `Web.Tools.S2SConfigure.SettingsPage.Wizard.Title`
- `0x7b4ff`: `<a target='_blank' style='text-decoration:underline' href='http://go.microsoft.com/fwlink/?LinkID=402112'>{0}</a> `
- `0x7b512`: `Web.Tools.DocumentManagement.S2SUpgrade.AbsoluteUrlWarningHelpLinkTitle`
- `0x7b5d2`: `<a target='_blank' href='http://go.microsoft.com/fwlink/p/?LinkID=513066'>{0}</a> `
- `0x7b5e5`: `Web.Tools.S2SUpgrade.Wizard.S2SDefaultSite.link.CRMOnlineSPOnPremise`

## pseudocode

```c

```

## disassembly

```asm
0x7b450  ldarg.0
0x7b451  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentForm()
0x7b456  isinst   [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.WizardForm
0x7b45b  stloc.0
0x7b45c  call     class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl [Microsoft.Crm.Core]Microsoft.Crm.FeatureControl::get_Current()
0x7b461  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl::get_Features()
0x7b466  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer::get_SharePointS2S()
0x7b46b  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x7b470  call     bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.FeatureEnabledHelper::IsFeatureEnabled(class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x7b475  brfalse.s loc_7B48F
0x7b477  ldloc.0
0x7b478  ldarg.0
0x7b479  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x7b47e  ldstr    aWebToolsS2scon// "Web.Tools.S2SConfigure.SettingsPage.Wiz"...
0x7b483  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x7b488  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.WizardForm::set_PageTitle(string)
0x7b48d  br.s     loc_7B4A5
0x7b48f  ldloc.0
0x7b490  ldarg.0
0x7b491  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x7b496  ldstr    aWebToolsS2supg_0// "Web.Tools.S2SUpgrade.SettingsPage.Wizar"...
0x7b49b  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x7b4a0  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.WizardForm::set_PageTitle(string)
0x7b4a5  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.SystemCustomizationSecurity::CheckS2SEnableDocumentPrivileges()
0x7b4aa  brtrue.s loc_7B4EF
0x7b4ac  ldarg.0
0x7b4ad  ldc.i4.1
0x7b4ae  stfld    bool Microsoft.Crm.Web.Tools.DocumentManagement.S2SDefaultSite::isInsufficientPrivilegesVisible
0x7b4b3  ldarg.0
0x7b4b4  ldfld    class [System.Web]System.Web.UI.HtmlControls.HtmlContainerControl Microsoft.Crm.Web.Tools.DocumentManagement.S2SDefaultSite::absoluteURLWarningTable
0x7b4b9  ldc.i4.0
0x7b4ba  callvirt instance void [System.Web]System.Web.UI.Control::set_Visible(bool)
0x7b4bf  ldarg.0
0x7b4c0  ldc.i4.0
0x7b4c1  stfld    bool Microsoft.Crm.Web.Tools.DocumentManagement.S2SDefaultSite::isAbsoluteWarningVisible
0x7b4c6  ldarg.0
0x7b4c7  ldfld    class [System.Web]System.Web.UI.HtmlControls.HtmlTable Microsoft.Crm.Web.Tools.DocumentManagement.S2SDefaultSite::InsufficientPrivileges
0x7b4cc  ldc.i4.1
0x7b4cd  callvirt instance void [System.Web]System.Web.UI.Control::set_Visible(bool)
0x7b4d2  ldarg.0
0x7b4d3  ldfld    class [System.Web]System.Web.UI.HtmlControls.HtmlContainerControl Microsoft.Crm.Web.Tools.DocumentManagement.S2SDefaultSite::DefaultSiteContent
0x7b4d8  ldc.i4.0
0x7b4d9  callvirt instance void [System.Web]System.Web.UI.Control::set_Visible(bool)
0x7b4de  ldloc.0
0x7b4df  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Button [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.WizardForm::get_NextButton()
0x7b4e4  ldc.i4.1
0x7b4e5  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::set_Disabled(bool)
0x7b4ea  br       loc_7B5B9
0x7b4ef  ldarg.0
0x7b4f0  call     instance bool Microsoft.Crm.Web.Tools.DocumentManagement.S2SDefaultSite::IsAbsoluteUrlsExistsinOrganization()
0x7b4f5  brfalse  loc_7B595
0x7b4fa  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x7b4ff  ldstr    aATargetBlankSt// "<a target='_blank' style='text-decorati"...
0x7b504  ldc.i4.1
0x7b505  newarr   [mscorlib]System.Object
0x7b50a  dup
0x7b50b  ldc.i4.0
0x7b50c  ldarg.0
0x7b50d  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x7b512  ldstr    aWebToolsDocume_53// "Web.Tools.DocumentManagement.S2SUpgrade"...
0x7b517  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x7b51c  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlEncode(string)
0x7b521  stelem.ref
0x7b522  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x7b527  stloc.2
0x7b528  ldarg.0
0x7b529  ldfld    class [System.Web]System.Web.UI.HtmlControls.HtmlContainerControl Microsoft.Crm.Web.Tools.DocumentManagement.S2SDefaultSite::absoluteURLWarningTable
0x7b52e  ldc.i4.1
0x7b52f  callvirt instance void [System.Web]System.Web.UI.Control::set_Visible(bool)
0x7b534  ldarg.0
0x7b535  ldfld    class [System.Web]System.Web.UI.HtmlControls.HtmlGenericControl Microsoft.Crm.Web.Tools.DocumentManagement.S2SDefaultSite::absoluteURLWarningLabel
0x7b53a  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentCulture()
0x7b53f  ldarg.0
0x7b540  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x7b545  ldstr    aWebToolsDocume_54// "Web.Tools.DocumentManagement.S2SUpgrade"...
0x7b54a  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x7b54f  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlEncode(string)
0x7b554  ldc.i4.1
0x7b555  newarr   [mscorlib]System.Object
0x7b55a  dup
0x7b55b  ldc.i4.0
0x7b55c  ldloc.2
0x7b55d  stelem.ref
0x7b55e  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x7b563  callvirt instance void [System.Web]System.Web.UI.HtmlControls.HtmlContainerControl::set_InnerHtml(string)
0x7b568  ldarg.0
0x7b569  ldfld    class [System.Web]System.Web.UI.HtmlControls.HtmlTable Microsoft.Crm.Web.Tools.DocumentManagement.S2SDefaultSite::InsufficientPrivileges
0x7b56e  ldc.i4.0
0x7b56f  callvirt instance void [System.Web]System.Web.UI.Control::set_Visible(bool)
0x7b574  ldarg.0
0x7b575  ldc.i4.1
0x7b576  stfld    bool Microsoft.Crm.Web.Tools.DocumentManagement.S2SDefaultSite::isAbsoluteWarningVisible
0x7b57b  ldarg.0
0x7b57c  ldfld    class [System.Web]System.Web.UI.HtmlControls.HtmlContainerControl Microsoft.Crm.Web.Tools.DocumentManagement.S2SDefaultSite::DefaultSiteContent
0x7b581  ldc.i4.0
0x7b582  callvirt instance void [System.Web]System.Web.UI.Control::set_Visible(bool)
0x7b587  ldloc.0
0x7b588  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Button [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.WizardForm::get_NextButton()
0x7b58d  ldc.i4.1
0x7b58e  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::set_Disabled(bool)
0x7b593  br.s     loc_7B5B9
0x7b595  ldarg.0
0x7b596  ldfld    class [System.Web]System.Web.UI.HtmlControls.HtmlContainerControl Microsoft.Crm.Web.Tools.DocumentManagement.S2SDefaultSite::absoluteURLWarningTable
0x7b59b  ldc.i4.0
0x7b59c  callvirt instance void [System.Web]System.Web.UI.Control::set_Visible(bool)
0x7b5a1  ldarg.0
0x7b5a2  ldfld    class [System.Web]System.Web.UI.HtmlControls.HtmlTable Microsoft.Crm.Web.Tools.DocumentManagement.S2SDefaultSite::InsufficientPrivileges
0x7b5a7  ldc.i4.0
0x7b5a8  callvirt instance void [System.Web]System.Web.UI.Control::set_Visible(bool)
0x7b5ad  ldarg.0
0x7b5ae  ldfld    class [System.Web]System.Web.UI.HtmlControls.HtmlContainerControl Microsoft.Crm.Web.Tools.DocumentManagement.S2SDefaultSite::DefaultSiteContent
0x7b5b3  ldc.i4.1
0x7b5b4  callvirt instance void [System.Web]System.Web.UI.Control::set_Visible(bool)
0x7b5b9  call     class [Microsoft.Crm.Core]Microsoft.Crm.ISkuInfoProvider [Microsoft.Crm.Core]Microsoft.Crm.SkuInfoProvider::get_Instance()
0x7b5be  callvirt instance valuetype [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.ConfigSku [Microsoft.Crm.Core]Microsoft.Crm.ISkuInfoProvider::GetSku()
0x7b5c3  ldc.i4.2
0x7b5c4  bne.un.s loc_7B5CD
0x7b5c6  ldarg.0
0x7b5c7  ldc.i4.1
0x7b5c8  stfld    bool Microsoft.Crm.Web.Tools.DocumentManagement.S2SDefaultSite::isOnline
0x7b5cd  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x7b5d2  ldstr    aATargetBlankHr// "<a target='_blank' href='http://go.micr"...
0x7b5d7  ldc.i4.1
0x7b5d8  newarr   [mscorlib]System.Object
0x7b5dd  dup
0x7b5de  ldc.i4.0
0x7b5df  ldarg.0
0x7b5e0  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x7b5e5  ldstr    aWebToolsS2supg_1// "Web.Tools.S2SUpgrade.Wizard.S2SDefaultS"...
0x7b5ea  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x7b5ef  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlEncode(string)
0x7b5f4  stelem.ref
0x7b5f5  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x7b5fa  stloc.1
0x7b5fb  ldarg.0
0x7b5fc  ldfld    class [System.Web]System.Web.UI.HtmlControls.HtmlTableCell Microsoft.Crm.Web.Tools.DocumentManagement.S2SDefaultSite::crmOnlineSPOnPremise
0x7b601  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentCulture()
0x7b606  ldarg.0
0x7b607  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x7b60c  ldstr    aWebToolsS2supg_2// "Web.Tools.S2SUpgrade.Wizard.S2SDefaultS"...
0x7b611  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x7b616  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlEncode(string)
0x7b61b  ldc.i4.1
0x7b61c  newarr   [mscorlib]System.Object
0x7b621  dup
0x7b622  ldc.i4.0
0x7b623  ldloc.1
0x7b624  stelem.ref
0x7b625  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x7b62a  callvirt instance void [System.Web]System.Web.UI.HtmlControls.HtmlContainerControl::set_InnerHtml(string)
0x7b62f  ret
```
