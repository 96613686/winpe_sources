# Microsoft.Crm.Web.Controls.Lookup.LookupPageBase::ConfigurePage

- ea: `0x4ba60`
- end: `0x4bf4d`
- name: `Microsoft.Crm.Web.Controls.Lookup.LookupPageBase::ConfigurePage`
- size: `1261`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callees

- `0x4b5d0`
- `0x4b5e0`
- `0x4b610`
- `0x4b650`
- `0x4b660`
- `0x4ba60`
- `0x4bf50`
- `0x4c5d0`

## string_xrefs

- `0x4bb93`: `/_static/_common/scripts/CrmInternalUtility.js`
- `0x4bba3`: `/_static/_common/scripts/Mscrm.Caching.js`
- `0x4bb56`: `Dialog_Lookup_Security_Error`
- `0x4bd2a`: `enableRemoveBtn`
- `0x4bd57`: `btnRemoveValue`
- `0x4bd5c`: `Button_Label_RemoveValue`
- `0x4bd61`: `removeValue(new Sys.UI.DomEvent(event));`

## pseudocode

```c

```

## disassembly

```asm
0x4ba60  ldarg.0
0x4ba61  call     instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Pages.DialogPage::ConfigurePage()
0x4ba66  ldarg.0
0x4ba67  call     instance string Microsoft.Crm.Web.Controls.Lookup.LookupPageBase::get_DefaultObjectType()
0x4ba6c  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x4ba71  brfalse.s loc_4BACE
0x4ba73  ldarg.0
0x4ba74  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x4ba79  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x4ba7e  ldstr    aDefaulttype// "DefaultType"
0x4ba83  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x4ba88  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x4ba8d  brtrue.s loc_4BACE
0x4ba8f  ldarg.0
0x4ba90  ldarg.0
0x4ba91  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x4ba96  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x4ba9b  ldstr    aDefaulttype// "DefaultType"
0x4baa0  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x4baa5  ldstr    a9206// "9206"
0x4baaa  callvirt instance bool [mscorlib]System.String::Equals(string)
0x4baaf  brtrue.s loc_4BAC8
0x4bab1  ldarg.0
0x4bab2  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x4bab7  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x4babc  ldstr    aDefaulttype// "DefaultType"
0x4bac1  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x4bac6  br.s     loc_4BAC9
0x4bac8  ldnull
0x4bac9  call     instance void Microsoft.Crm.Web.Controls.Lookup.LookupPageBase::set_DefaultObjectType(string value)
0x4bace  ldarg.0
0x4bacf  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x4bad4  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x4bad9  ldstr    aBrowse// "Browse"
0x4bade  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x4bae3  stloc.0
0x4bae4  ldarg.0
0x4bae5  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x4baea  ldstr    aDefaultobjectt// "_defaultObjectType"
0x4baef  ldarg.0
0x4baf0  call     instance string Microsoft.Crm.Web.Controls.Lookup.LookupPageBase::get_DefaultObjectType()
0x4baf5  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, string)
0x4bafa  ldloc.0
0x4bafb  brfalse.s loc_4BB00
0x4bafd  ldloc.0
0x4bafe  br.s     loc_4BB05
0x4bb00  ldstr    a0_1// "0"
0x4bb05  stloc.0
0x4bb06  ldarg.0
0x4bb07  ldarg.0
0x4bb08  call     instance valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.LookupMode Microsoft.Crm.Web.Controls.Lookup.LookupPageBase::get_Mode()
0x4bb0d  ldloc.0
0x4bb0e  ldstr    a1// "1"
0x4bb13  call     bool [mscorlib]System.String::op_Equality(string, string)
0x4bb18  brtrue.s loc_4BB2B
0x4bb1a  ldloc.0
0x4bb1b  ldstr    aTrue_0// "true"
0x4bb20  ldc.i4.5
0x4bb21  callvirt instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0x4bb26  brtrue.s loc_4BB2B
0x4bb28  ldc.i4.0
0x4bb29  br.s     loc_4BB2C
0x4bb2b  ldc.i4.1
0x4bb2c  or
0x4bb2d  call     instance void Microsoft.Crm.Web.Controls.Lookup.LookupPageBase::set_Mode(valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.LookupMode value)
0x4bb32  ldarg.0
0x4bb33  call     instance bool Microsoft.Crm.Web.Controls.Lookup.LookupPageBase::ProcessSearchTypes()
0x4bb38  brtrue.s loc_4BB7F
0x4bb3a  ldarg.0
0x4bb3b  call     instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.UI.Page::get_Response()
0x4bb40  callvirt instance void [System.Web]System.Web.HttpResponse::Clear()
0x4bb45  ldarg.0
0x4bb46  call     instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.UI.Page::get_Response()
0x4bb4b  ldstr    aScriptLanguage_2// "<script language=\"javascript\">alert("...
0x4bb50  ldarg.0
0x4bb51  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x4bb56  ldstr    aDialogLookupSe// "Dialog_Lookup_Security_Error"
0x4bb5b  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x4bb60  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmJavaScriptEncodeNoQuotes(string)
0x4bb65  ldstr    aClosewindowScr// "\");closeWindow();</script>"
0x4bb6a  call     string [mscorlib]System.String::Concat(string, string, string)
0x4bb6f  callvirt instance void [System.Web]System.Web.HttpResponse::Write(string)
0x4bb74  ldarg.0
0x4bb75  call     instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.UI.Page::get_Response()
0x4bb7a  callvirt instance void [System.Web]System.Web.HttpResponse::End()
0x4bb7f  ldarg.0
0x4bb80  ldarg.0
0x4bb81  call     instance valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.LookupMode Microsoft.Crm.Web.Controls.Lookup.LookupPageBase::get_Mode()
0x4bb86  ldc.i4.2
0x4bb87  or
0x4bb88  call     instance void Microsoft.Crm.Web.Controls.Lookup.LookupPageBase::set_Mode(valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.LookupMode value)
0x4bb8d  ldarg.0
0x4bb8e  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x4bb93  ldstr    aStaticCommonSc// "/_static/_common/scripts/CrmInternalUti"...
0x4bb98  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x4bb9d  ldarg.0
0x4bb9e  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x4bba3  ldstr    aStaticCommonSc_13// "/_static/_common/scripts/Mscrm.Caching."...
0x4bba8  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x4bbad  ldarg.0
0x4bbae  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x4bbb3  ldstr    aStaticControls_13// "/_static/_controls/lookup/lookupstage.j"...
0x4bbb8  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x4bbbd  ldarg.0
0x4bbbe  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x4bbc3  ldstr    aStaticControls_14// "/_static/_controls/lookup/lookupdialogs"...
0x4bbc8  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x4bbcd  ldarg.0
0x4bbce  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x4bbd3  ldstr    aStaticFormsLoo// "/_static/_forms/lookupbehavior.js"
0x4bbd8  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x4bbdd  ldarg.0
0x4bbde  call     instance bool [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Pages.DialogPage::get_IsMobileRefresh()
0x4bbe3  brfalse.s loc_4BC16
0x4bbe5  ldarg.0
0x4bbe6  ldarg.0
0x4bbe7  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x4bbec  ldstr    aDialogLookupLo// "Dialog_Lookup_LookupRecord_Title_Mobile"...
0x4bbf1  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x4bbf6  call     instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Pages.DialogPage::set_DialogTitle(string)
0x4bbfb  ldarg.0
0x4bbfc  ldarg.0
0x4bbfd  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x4bc02  ldstr    aDialogLookupDe// "Dialog_Lookup_Desc_Browse"
0x4bc07  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x4bc0c  call     instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Pages.DialogPage::set_DialogDescription(string)
0x4bc11  br       loc_4BCB4
0x4bc16  ldarg.0
0x4bc17  call     instance valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.LookupMode Microsoft.Crm.Web.Controls.Lookup.LookupPageBase::get_Mode()
0x4bc1c  ldc.i4.1
0x4bc1d  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.General::CheckBit(unsigned int32, unsigned int32)
0x4bc22  brfalse.s loc_4BC52
0x4bc24  ldarg.0
0x4bc25  ldarg.0
0x4bc26  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x4bc2b  ldstr    aDialogLookupDe// "Dialog_Lookup_Desc_Browse"
0x4bc30  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x4bc35  call     instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Pages.DialogPage::set_DialogDescription(string)
0x4bc3a  ldarg.0
0x4bc3b  ldarg.0
0x4bc3c  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x4bc41  ldstr    aDialogLookupTi// "Dialog_Lookup_Title_Single"
0x4bc46  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x4bc4b  call     instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Pages.DialogPage::set_DialogTitle(string)
0x4bc50  br.s     loc_4BCB4
0x4bc52  ldarg.0
0x4bc53  call     instance bool Microsoft.Crm.Web.Controls.Lookup.LookupPageBase::get_IsMultipleLookup()
0x4bc58  brfalse.s loc_4BC88
0x4bc5a  ldarg.0
0x4bc5b  ldarg.0
0x4bc5c  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x4bc61  ldstr    aDialogLookupDe_0// "Dialog_Lookup_Desc_Multi"
0x4bc66  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x4bc6b  call     instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Pages.DialogPage::set_DialogDescription(string)
0x4bc70  ldarg.0
0x4bc71  ldarg.0
0x4bc72  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x4bc77  ldstr    aDialogLookupTi_0// "Dialog_Lookup_Title"
0x4bc7c  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x4bc81  call     instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Pages.DialogPage::set_DialogTitle(string)
0x4bc86  br.s     loc_4BCB4
0x4bc88  ldarg.0
0x4bc89  ldarg.0
0x4bc8a  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x4bc8f  ldstr    aDialogLookupDe_1// "Dialog_Lookup_Desc_Single"
0x4bc94  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x4bc99  call     instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Pages.DialogPage::set_DialogDescription(string)
0x4bc9e  ldarg.0
0x4bc9f  ldarg.0
0x4bca0  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x4bca5  ldstr    aDialogLookupTi// "Dialog_Lookup_Title_Single"
0x4bcaa  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x4bcaf  call     instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Pages.DialogPage::set_DialogTitle(string)
0x4bcb4  ldnull
0x4bcb5  stloc.1
0x4bcb6  ldstr    aButbegin// "butBegin"
0x4bcbb  ldstr    aButtonLabelAdd// "Button_Label_Add"
0x4bcc0  ldstr    aIfMscrmUtiliti_1// "if(!Mscrm.Utilities.resetValidationFail"...
0x4bcc5  ldc.i4.1
0x4bcc6  ldc.i4.1
0x4bcc7  newobj   instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Pages.DialogButton::.ctor(string, string, string, bool, bool)
0x4bccc  stloc.1
0x4bccd  ldarg.0
0x4bcce  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Pages.DialogButtonCollection [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Pages.DialogPage::get_Buttons()
0x4bcd3  ldloc.1
0x4bcd4  callvirt instance int32 [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Pages.DialogButtonCollection::Add(class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Pages.DialogButton)
0x4bcd9  pop
0x4bcda  leave.s  loc_4BCE6
0x4bcdc  ldloc.1
0x4bcdd  brfalse.s loc_4BCE5
0x4bcdf  ldloc.1
0x4bce0  callvirt instance void [System.Web]System.Web.UI.Control::Dispose()
0x4bce5  endfinally
0x4bce6  ldarg.0
0x4bce7  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Pages.DialogButtonCollection [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Pages.DialogPage::get_Buttons()
0x4bcec  ldc.i4.2
0x4bced  ldc.i4.0
0x4bcee  ldc.i4.1
0x4bcef  callvirt instance int32 [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Pages.DialogButtonCollection::AddStandardButton(valuetype [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Pages.StandardDialogButtons, bool, bool)
0x4bcf4  pop
0x4bcf5  call     class [System.Web]System.Web.HttpContext [System.Web]System.Web.HttpContext::get_Current()
0x4bcfa  callvirt instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.HttpContext::get_Request()
0x4bcff  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x4bd04  ldstr    aLookupstyle_0// "LookupStyle"
0x4bd09  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x4bd0e  callvirt instance string [mscorlib]System.String::ToUpperInvariant()
0x4bd13  ldstr    aSingle_0// "SINGLE"
0x4bd18  callvirt instance bool [mscorlib]System.String::Equals(string)
0x4bd1d  brfalse.s loc_4BD7B
0x4bd1f  ldarg.0
0x4bd20  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x4bd25  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x4bd2a  ldstr    aEnableremovebt// "enableRemoveBtn"
0x4bd2f  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x4bd34  stloc.2
0x4bd35  ldloc.2
0x4bd36  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x4bd3b  brtrue.s loc_4BD40
0x4bd3d  ldloc.2
0x4bd3e  br.s     loc_4BD45
0x4bd40  ldstr    a0_1// "0"
0x4bd45  stloc.2
0x4bd46  ldarg.0
0x4bd47  ldloc.2
0x4bd48  ldstr    a1// "1"
0x4bd4d  call     bool [mscorlib]System.String::op_Equality(string, string)
0x4bd52  stfld    bool Microsoft.Crm.Web.Controls.Lookup.LookupPageBase::_enableRemoveButton
0x4bd57  ldstr    aBtnremovevalue// "btnRemoveValue"
0x4bd5c  ldstr    aButtonLabelRem_0// "Button_Label_RemoveValue"
0x4bd61  ldstr    aRemovevalueNew// "removeValue(new Sys.UI.DomEvent(event))"...
0x4bd66  ldc.i4.1
0x4bd67  ldc.i4.0
0x4bd68  newobj   instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Pages.DialogButton::.ctor(string, string, string, bool, bool)
0x4bd6d  stloc.3
0x4bd6e  ldarg.0
0x4bd6f  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Pages.DialogButtonCollection [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Pages.DialogPage::get_Buttons()
0x4bd74  ldloc.3
0x4bd75  callvirt instance int32 [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Pages.DialogButtonCollection::Add(class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Pages.DialogButton)
0x4bd7a  pop
0x4bd7b  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x4bd80  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::UseTabletExperience(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x4bd85  brfalse.s loc_4BD93
0x4bd87  ldarg.0
0x4bd88  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppGrid Microsoft.Crm.Web.Controls.Lookup.LookupPageBase::crmGrid
0x4bd8d  ldc.i4.m1
0x4bd8e  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Grid.DataGrid::set_MaximumSelectableItems(int32)
0x4bd93  call     class [System.Web]System.Web.HttpContext [System.Web]System.Web.HttpContext::get_Current()
0x4bd98  callvirt instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.HttpContext::get_Request()
0x4bd9d  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x4bda2  ldstr    aLookupstyle_0// "LookupStyle"
0x4bda7  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x4bdac  callvirt instance string [mscorlib]System.String::ToUpperInvariant()
0x4bdb1  ldstr    aSingle_0// "SINGLE"
0x4bdb6  callvirt instance bool [mscorlib]System.String::Equals(string)
0x4bdbb  brfalse.s loc_4BDC9
0x4bdbd  ldarg.0
0x4bdbe  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppGrid Microsoft.Crm.Web.Controls.Lookup.LookupPageBase::crmGrid
0x4bdc3  ldc.i4.1
0x4bdc4  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Grid.DataGrid::set_MaximumSelectableItems(int32)
0x4bdc9  ldarg.0
0x4bdca  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppGrid Microsoft.Crm.Web.Controls.Lookup.LookupPageBase::crmGrid
0x4bdcf  ldstr    aDisabledblclic// "disableDblClick"
0x4bdd4  ldstr    a1// "1"
0x4bdd9  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Grid.DataGrid::AddParameter(string, string)
0x4bdde  ldarg.0
0x4bddf  call     instance void Microsoft.Crm.Web.Controls.Lookup.LookupPageBase::ParseFilterRelationship()
0x4bde4  ldarg.0
0x4bde5  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Select Microsoft.Crm.Web.Controls.Lookup.LookupPageBase::_objSelect
0x4bdea  brfalse.s loc_4BE3B
0x4bdec  ldarg.0
0x4bded  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Select Microsoft.Crm.Web.Controls.Lookup.LookupPageBase::_objSelect
0x4bdf2  callvirt instance class [mscorlib]System.Collections.ArrayList [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Select::get_OptionGroups()
0x4bdf7  callvirt instance int32 [mscorlib]System.Collections.ArrayList::get_Count()
0x4bdfc  ldc.i4.1
0x4bdfd  bne.un.s loc_4BE3B
0x4bdff  ldarg.0
0x4be00  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Select Microsoft.Crm.Web.Controls.Lookup.LookupPageBase::_objSelect
0x4be05  callvirt instance class [mscorlib]System.Collections.ArrayList [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Select::get_OptionGroups()
0x4be0a  ldc.i4.0
0x4be0b  callvirt instance object [mscorlib]System.Collections.ArrayList::get_Item(int32)
0x4be10  castclass [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.OptionGroup
0x4be15  callvirt instance class [mscorlib]System.Collections.ArrayList [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.OptionGroup::get_Options()
0x4be1a  callvirt instance int32 [mscorlib]System.Collections.ArrayList::get_Count()
0x4be1f  ldc.i4.1
0x4be20  bne.un.s loc_4BE3B
0x4be22  ldarg.0
0x4be23  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Select Microsoft.Crm.Web.Controls.Lookup.LookupPageBase::_objSelect
0x4be28  ldc.i4.1
0x4be29  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::set_Disabled(bool)
0x4be2e  ldarg.0
0x4be2f  ldstr    aCrmgridSavedqu// "crmGrid_SavedQuerySelector"
0x4be34  call     instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.DialogBase::set_OverriddenFirstFocusableElementId(string)
0x4be39  br.s     loc_4BE46
0x4be3b  ldarg.0
0x4be3c  ldstr    aSelobjects// "selObjects"
0x4be41  call     instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.DialogBase::set_OverriddenFirstFocusableElementId(string)
0x4be46  ldc.i4   0x406
0x4be4b  stloc.s  4
0x4be4d  ldloca.s 4
0x4be4f  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentCulture()
  ... truncated ...
```
