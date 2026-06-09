# Microsoft.Crm.Common.Web.Tools.Yammer.YammerConfiguration::ConfigureHeader

- ea: `0x79f0`
- end: `0x7c4f`
- name: `Microsoft.Crm.Common.Web.Tools.Yammer.YammerConfiguration::ConfigureHeader`
- size: `607`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x7720`
- `0x7750`
- `0x79f0`
- `0x8950`

## string_xrefs

- `0x7a12`: `/_static/_common/scripts/jquery_ui_1.8.21.min.js`
- `0x7a22`: `/_static/_common/scripts/CrmInternalUtility.js`
- `0x7a32`: `/_static/_common/scripts/Mscrm.Caching.js`
- `0x7a42`: `/_static/_common/scripts/ScriptClientApi.js`
- `0x7a52`: `/_static/_common/scripts/SalesCommonImported.js`
- `0x7a62`: `/_static/_common/scripts/Mscrm.Data.js`
- `0x7a72`: `/_static/_common/scripts/SalesCommonFramework.js`
- `0x7a82`: `/_static/_common/scripts/InlineEditCommon.js`
- `0x7b42`: `/_static/_controls/YammerConfigHandler/YammerConfigHandler.js`
- `0x7b94`: `postRuleConfigUrl`
- `0x7b99`: `/_root/homepage.aspx?etn=msdyn_postruleconfig&layout=0&pagemode=iframe&sitemappath=Settings%7cSystem_Setting%7cmsdyn_postruleconfig&viewid=%7b47AC0AB8-1F34-E211-AD0F-00155DB6575D%7d&viewtype=1039&visualizationId=&visualizationPaneMode=0&visualizationType=0`
- `0x7bb4`: `Web.Tools.Yammer.Config.NoNetwork`
- `0x7bca`: `LOCID_COULDNOTREADACCESSTOKEN`
- `0x7c0c`: `LOCID_YAMMER_ALLCOMPANY`

## pseudocode

```c

```

## disassembly

```asm
0x79f0  ldarg.0
0x79f1  call     instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::ConfigureHeader()
0x79f6  newobj   instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Button::.ctor()
0x79fb  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::SetHeaders()
0x7a00  ldarg.0
0x7a01  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x7a06  ldc.i4.1
0x7a07  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::set_LoadJQuery(bool)
0x7a0c  ldarg.0
0x7a0d  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x7a12  ldstr    aStaticCommonSc_3// "/_static/_common/scripts/jquery_ui_1.8."...
0x7a17  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x7a1c  ldarg.0
0x7a1d  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x7a22  ldstr    aStaticCommonSc_4// "/_static/_common/scripts/CrmInternalUti"...
0x7a27  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x7a2c  ldarg.0
0x7a2d  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x7a32  ldstr    aStaticCommonSc_5// "/_static/_common/scripts/Mscrm.Caching."...
0x7a37  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x7a3c  ldarg.0
0x7a3d  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x7a42  ldstr    aStaticCommonSc_6// "/_static/_common/scripts/ScriptClientAp"...
0x7a47  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x7a4c  ldarg.0
0x7a4d  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x7a52  ldstr    aStaticCommonSc_7// "/_static/_common/scripts/SalesCommonImp"...
0x7a57  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x7a5c  ldarg.0
0x7a5d  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x7a62  ldstr    aStaticCommonSc_8// "/_static/_common/scripts/Mscrm.Data.js"
0x7a67  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x7a6c  ldarg.0
0x7a6d  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x7a72  ldstr    aStaticCommonSc_9// "/_static/_common/scripts/SalesCommonFra"...
0x7a77  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x7a7c  ldarg.0
0x7a7d  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x7a82  ldstr    aStaticCommonSc_10// "/_static/_common/scripts/InlineEditComm"...
0x7a87  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x7a8c  ldarg.0
0x7a8d  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x7a92  ldstr    aStaticFormsFor// "/_static/_forms/form.js"
0x7a97  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x7a9c  ldarg.0
0x7a9d  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x7aa2  ldstr    aStaticFormsSel// "/_static/_forms/select.js"
0x7aa7  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x7aac  ldarg.0
0x7aad  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x7ab2  ldstr    aStaticFormsTex// "/_static/_forms/TextInputBehavior.js"
0x7ab7  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x7abc  ldarg.0
0x7abd  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x7ac2  ldstr    aStaticFormsLoo// "/_static/_forms/LookupBehavior.js"
0x7ac7  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x7acc  ldarg.0
0x7acd  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x7ad2  ldstr    aStaticFormsNum// "/_static/_forms/NumberInputBehavior.js"
0x7ad7  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x7adc  ldarg.0
0x7add  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x7ae2  ldstr    aStaticFormsDat// "/_static/_forms/DateTime.js"
0x7ae7  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x7aec  ldarg.0
0x7aed  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x7af2  ldstr    aStaticFormsChe// "/_static/_forms/Checkbox.js"
0x7af7  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x7afc  ldarg.0
0x7afd  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x7b02  ldstr    aStaticControls_2// "/_static/_controls/editableselect/edita"...
0x7b07  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x7b0c  ldarg.0
0x7b0d  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x7b12  ldstr    aStaticControls_3// "/_static/_controls/inlineedit/InlineEdi"...
0x7b17  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x7b1c  ldarg.0
0x7b1d  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x7b22  ldstr    aStaticControls_4// "/_static/_controls/inlineedit/inlineedi"...
0x7b27  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x7b2c  ldarg.0
0x7b2d  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x7b32  ldstr    aStaticControls_5// "/_static/_controls/FlyoutDialog/FlyoutD"...
0x7b37  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x7b3c  ldarg.0
0x7b3d  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x7b42  ldstr    aStaticControls_6// "/_static/_controls/YammerConfigHandler/"...
0x7b47  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x7b4c  ldarg.0
0x7b4d  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x7b52  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x7b57  ldstr    aStaticCss0Inli// "/_static/css/{0}/InlineEditControls.css"
0x7b5c  ldc.i4.1
0x7b5d  newarr   [mscorlib]System.Object
0x7b62  dup
0x7b63  ldc.i4.0
0x7b64  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentUICulture()
0x7b69  callvirt instance int32 [mscorlib]System.Globalization.CultureInfo::get_LCID()
0x7b6e  box      [mscorlib]System.Int32
0x7b73  stelem.ref
0x7b74  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x7b79  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0x7b7e  ldarg.0
0x7b7f  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x7b84  ldstr    aToolsYammerYam// "/tools/yammer/yammerstyles.css.aspx"
0x7b89  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0x7b8e  ldarg.0
0x7b8f  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x7b94  ldstr    aPostruleconfig// "postRuleConfigUrl"
0x7b99  ldstr    aRootHomepageAs_0// "/_root/homepage.aspx?etn=msdyn_postrule"...
0x7b9e  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, string)
0x7ba3  ldarg.0
0x7ba4  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x7ba9  ldstr    aLocidYammerNon// "LOCID_YAMMER_NONETWORK"
0x7bae  ldarg.0
0x7baf  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x7bb4  ldstr    aWebToolsYammer_2// "Web.Tools.Yammer.Config.NoNetwork"
0x7bb9  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x7bbe  ldc.i4.0
0x7bbf  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x7bc4  ldarg.0
0x7bc5  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x7bca  ldstr    aLocidCouldnotr// "LOCID_COULDNOTREADACCESSTOKEN"
0x7bcf  ldarg.0
0x7bd0  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x7bd5  ldstr    aErrorMessage0x// "Error_Message_0x8005f105"
0x7bda  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x7bdf  ldc.i4.0
0x7be0  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x7be5  ldarg.0
0x7be6  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x7beb  ldstr    aLocidNotverifi// "LOCID_NOTVERIFIEDADMIN"
0x7bf0  ldarg.0
0x7bf1  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x7bf6  ldstr    aErrorMessage0x_0// "Error_Message_0x8005f106"
0x7bfb  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x7c00  ldc.i4.0
0x7c01  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x7c06  ldarg.0
0x7c07  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x7c0c  ldstr    aLocidYammerAll// "LOCID_YAMMER_ALLCOMPANY"
0x7c11  ldarg.0
0x7c12  call     instance string Microsoft.Crm.Common.Web.Tools.Yammer.YammerConfiguration::get_AllCompany()
0x7c17  ldc.i4.0
0x7c18  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x7c1d  ldarg.0
0x7c1e  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x7c23  ldstr    aDisableAuthori// "DISABLE_AUTHORIZATION"
0x7c28  ldarg.0
0x7c29  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x7c2e  callvirt instance bool [System.Web]System.Web.HttpRequest::get_IsSecureConnection()
0x7c33  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::AllowCredentialsEntry(bool)
0x7c38  ldc.i4.0
0x7c39  ceq
0x7c3b  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, bool)
0x7c40  ldarg.0
0x7c41  call     instance bool Microsoft.Crm.Common.Web.Tools.Yammer.YammerConfiguration::get_IsOrgOnPremise()
0x7c46  brtrue.s loc_7C4E
0x7c48  ldarg.0
0x7c49  call     void Microsoft.Crm.Common.Web.Tools.Yammer.YammerOAuthCommon::SetHandlerWrpc(class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage page)
0x7c4e  ret
```
