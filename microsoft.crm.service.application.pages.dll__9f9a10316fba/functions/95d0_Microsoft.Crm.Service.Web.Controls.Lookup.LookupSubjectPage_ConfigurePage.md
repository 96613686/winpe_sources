# Microsoft.Crm.Service.Web.Controls.Lookup.LookupSubjectPage::ConfigurePage

- ea: `0x95d0`
- end: `0x98d2`
- name: `Microsoft.Crm.Service.Web.Controls.Lookup.LookupSubjectPage::ConfigurePage`
- size: `770`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x95d0`

## string_xrefs

- `0x95fc`: `/_static/_common/styles/AutoToolTip.js`
- `0x9634`: `Dialog_Lookup_Security_Error`
- `0x9732`: `_fetchXml[`
- `0x9754`: `] = "<tr onclick='selectRow();' ondblclick='selectRowNow();' oType='subject'><xsl:attribute name='oid'><xsl:value-of select='subject'/></xsl:attribute><td nowrap='' class='sel'><img alt='' src='/_imgs/ico_18_acct.gif' align='absmiddle' CLASS='LookupSubjectPage_ConfigurePage_img' /><xsl:value-of select='name'/></td></tr>";`

## pseudocode

```c

```

## disassembly

```asm
0x95d0  ldarg.0
0x95d1  call     instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Pages.DialogPage::ConfigurePage()
0x95d6  ldarg.0
0x95d7  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x95dc  ldstr    aControlsLookup// "/_controls/lookup/lookupdialogs.css.asp"...
0x95e1  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0x95e6  ldarg.0
0x95e7  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x95ec  ldstr    aStaticControls_3// "/_static/_controls/lookup/lookup.js"
0x95f1  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x95f6  ldarg.0
0x95f7  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x95fc  ldstr    aStaticCommonSt// "/_static/_common/styles/AutoToolTip.js"
0x9601  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x9606  ldc.i4   0x81
0x960b  ldc.i4.1
0x960c  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x9611  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.User::GetPrivilege(int32, valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.PrivilegeId, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x9616  brtrue.s loc_965D
0x9618  ldarg.0
0x9619  call     instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.UI.Page::get_Response()
0x961e  callvirt instance void [System.Web]System.Web.HttpResponse::Clear()
0x9623  ldarg.0
0x9624  call     instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.UI.Page::get_Response()
0x9629  ldstr    aScriptLanguage// "<script language=\"javascript\">alert("...
0x962e  ldarg.0
0x962f  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x9634  ldstr    aDialogLookupSe// "Dialog_Lookup_Security_Error"
0x9639  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x963e  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmJavaScriptEncodeNoQuotes(string)
0x9643  ldstr    aClosewindowScr// "\");closeWindow();</script>"
0x9648  call     string [mscorlib]System.String::Concat(string, string, string)
0x964d  callvirt instance void [System.Web]System.Web.HttpResponse::Write(string)
0x9652  ldarg.0
0x9653  call     instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.UI.Page::get_Response()
0x9658  callvirt instance void [System.Web]System.Web.HttpResponse::End()
0x965d  ldarg.0
0x965e  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x9663  ldstr    aLocidSelectSub// "LOCID_SELECT_SUBJECT"
0x9668  ldarg.0
0x9669  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x966e  ldstr    aWebControlsLoo// "Web._controls.lookup.lookupsubject.aspx"...
0x9673  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x9678  ldc.i4.0
0x9679  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x967e  ldarg.0
0x967f  ldfld    unsigned int32 Microsoft.Crm.Service.Web.Controls.Lookup.LookupSubjectPage::featureMask
0x9684  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x9689  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ApplicationEntityCollection [Microsoft.Crm.Service.Application.Components.Platform]Microsoft.Crm.Service.Application.Platform.ServiceDataSource::RetrieveRootSubjects(unsigned int32, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x968e  call     string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ApplicationEntityCollection::Serialize(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ApplicationEntityCollection)
0x9693  stloc.0
0x9694  ldarg.0
0x9695  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppTree Microsoft.Crm.Service.Web.Controls.Lookup.LookupSubjectPage::crmTree
0x969a  ldstr    aTreesubject// "TreeSubject"
0x969f  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Tree::set_ClientId(string)
0x96a4  ldarg.0
0x96a5  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppTree Microsoft.Crm.Service.Web.Controls.Lookup.LookupSubjectPage::crmTree
0x96aa  ldstr    aGetsubject// "getSubject"
0x96af  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Tree::set_ReturnFunction(string)
0x96b4  ldarg.0
0x96b5  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppTree Microsoft.Crm.Service.Web.Controls.Lookup.LookupSubjectPage::crmTree
0x96ba  ldc.i4.5
0x96bb  newarr   [mscorlib]System.String
0x96c0  dup
0x96c1  ldc.i4.0
0x96c2  ldstr    aTree// "<tree>"
0x96c7  stelem.ref
0x96c8  dup
0x96c9  ldc.i4.1
0x96ca  ldloc.0
0x96cb  stelem.ref
0x96cc  dup
0x96cd  ldc.i4.2
0x96ce  ldstr    aRootalttag// "<rootalttag>"
0x96d3  stelem.ref
0x96d4  dup
0x96d5  ldc.i4.3
0x96d6  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x96db  ldstr    aTreeAltExpand// "Tree.Alt.Expand"
0x96e0  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x96e5  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmXmlEncode(string)
0x96ea  stelem.ref
0x96eb  dup
0x96ec  ldc.i4.4
0x96ed  ldstr    aRootalttagTree// "</rootalttag></tree>"
0x96f2  stelem.ref
0x96f3  call     string [mscorlib]System.String::Concat(string[])
0x96f8  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Tree::set_Data(string)
0x96fd  ldc.i4.0
0x96fe  stloc.1
0x96ff  ldarg.0
0x9700  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x9705  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x970a  ldstr    aSubject// "subject"
0x970f  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x9714  brfalse  loc_97B4
0x9719  ldloca.s 1
0x971b  ldstr    aD// "D"
0x9720  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x9725  call     instance string [mscorlib]System.Int32::ToString(string, class [mscorlib]System.IFormatProvider)
0x972a  stloc.3
0x972b  ldarg.0
0x972c  ldarg.0
0x972d  ldfld    string Microsoft.Crm.Service.Web.Controls.Lookup.LookupSubjectPage::fetchArray
0x9732  ldstr    aFetchxml// "_fetchXml["
0x9737  ldloc.3
0x9738  ldstr    aEntityNameSubj// "] = \"<entity name='subject'><attribute"...
0x973d  call     string [mscorlib]System.String::Concat(string, string, string, string)
0x9742  stfld    string Microsoft.Crm.Service.Web.Controls.Lookup.LookupSubjectPage::fetchArray
0x9747  ldarg.0
0x9748  ldarg.0
0x9749  ldfld    string Microsoft.Crm.Service.Web.Controls.Lookup.LookupSubjectPage::xslArray
0x974e  ldstr    aObjectxsl// "_objectXsl["
0x9753  ldloc.3
0x9754  ldstr    aTrOnclickSelec// "] = \"<tr onclick='selectRow();' ondblc"...
0x9759  call     string [mscorlib]System.String::Concat(string, string, string, string)
0x975e  stfld    string Microsoft.Crm.Service.Web.Controls.Lookup.LookupSubjectPage::xslArray
0x9763  ldarg.0
0x9764  ldc.i4.6
0x9765  newarr   [mscorlib]System.String
0x976a  dup
0x976b  ldc.i4.0
0x976c  ldarg.0
0x976d  ldfld    string Microsoft.Crm.Service.Web.Controls.Lookup.LookupSubjectPage::selectOptions
0x9772  stelem.ref
0x9773  dup
0x9774  ldc.i4.1
0x9775  ldstr    aOptionValue// "<option value='"
0x977a  stelem.ref
0x977b  dup
0x977c  ldc.i4.2
0x977d  ldloc.3
0x977e  stelem.ref
0x977f  dup
0x9780  ldc.i4.3
0x9781  ldstr    aObjectSubj// "' object='subj'>"
0x9786  stelem.ref
0x9787  dup
0x9788  ldc.i4.4
0x9789  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x978e  ldstr    aWebControlsLoo_0// "Web._controls.lookup.lookupsubject.aspx"...
0x9793  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x9798  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmXmlEncode(string)
0x979d  stelem.ref
0x979e  dup
0x979f  ldc.i4.5
0x97a0  ldstr    aOption// "</option>"
0x97a5  stelem.ref
0x97a6  call     string [mscorlib]System.String::Concat(string[])
0x97ab  stfld    string Microsoft.Crm.Service.Web.Controls.Lookup.LookupSubjectPage::selectOptions
0x97b0  ldloc.1
0x97b1  ldc.i4.1
0x97b2  add
0x97b3  stloc.1
0x97b4  ldarg.0
0x97b5  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x97ba  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x97bf  ldstr    aMultiselect// "multiselect"
0x97c4  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x97c9  brfalse.s loc_97F0
0x97cb  ldarg.0
0x97cc  ldarg.0
0x97cd  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x97d2  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x97d7  ldstr    aMultiselect// "multiselect"
0x97dc  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x97e1  ldstr    a1// "1"
0x97e6  call     bool [mscorlib]System.String::op_Equality(string, string)
0x97eb  stfld    bool Microsoft.Crm.Service.Web.Controls.Lookup.LookupSubjectPage::selectMultiple
0x97f0  ldarg.0
0x97f1  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x97f6  ldstr    aBmultiselect// "_bMultiSelect"
0x97fb  ldarg.0
0x97fc  ldflda   bool Microsoft.Crm.Service.Web.Controls.Lookup.LookupSubjectPage::selectMultiple
0x9801  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x9806  call     instance string [mscorlib]System.Boolean::ToString(class [mscorlib]System.IFormatProvider)
0x980b  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x9810  callvirt instance string [mscorlib]System.String::ToLower(class [mscorlib]System.Globalization.CultureInfo)
0x9815  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, string)
0x981a  ldarg.0
0x981b  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x9820  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x9825  ldstr    aXml// "xml"
0x982a  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x982f  brfalse.s loc_984C
0x9831  ldarg.0
0x9832  ldarg.0
0x9833  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x9838  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x983d  ldstr    aXml// "xml"
0x9842  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x9847  stfld    string Microsoft.Crm.Service.Web.Controls.Lookup.LookupSubjectPage::xml
0x984c  ldarg.0
0x984d  ldarg.0
0x984e  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x9853  ldstr    aDialogSubjects_5// "Dialog_Subjects_Lookup_Title"
0x9858  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x985d  call     instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Pages.DialogPage::set_DialogTitle(string)
0x9862  ldarg.0
0x9863  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Pages.DialogButtonCollection [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Pages.DialogPage::get_Buttons()
0x9868  ldc.i4.1
0x9869  callvirt instance int32 [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Pages.DialogButtonCollection::AddStandardButton(valuetype [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Pages.StandardDialogButtons)
0x986e  stloc.2
0x986f  ldarg.0
0x9870  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Pages.DialogButtonCollection [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Pages.DialogPage::get_Buttons()
0x9875  ldloc.2
0x9876  callvirt instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Pages.DialogButton [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Pages.DialogButtonCollection::get_Item(int32)
0x987b  ldstr    aButtonLabelSel// "Button_Label_Select"
0x9880  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Button::set_ResourceId(string)
0x9885  ldarg.0
0x9886  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Pages.DialogButtonCollection [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Pages.DialogPage::get_Buttons()
0x988b  ldc.i4.2
0x988c  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Pages.DialogButtonCollection::AddStandardButtons(valuetype [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Pages.StandardDialogButtons)
0x9891  ldarg.0
0x9892  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x9897  ldstr    aStyleTypeTextC_0// "<style type=\"text/css\">DIV.ms-crm-Dia"...
0x989c  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetCustomResource(string)
0x98a1  ldarg.0
0x98a2  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x98a7  ldarg.0
0x98a8  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x98ad  ldstr    aWebControlsLoo_1// "Web._controls.lookup.lookupsubject.aspx"...
0x98b2  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x98b7  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::set_Title(string)
0x98bc  ldarg.0
0x98bd  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x98c2  ldstr    aMscrmAutotoolt// "Mscrm.AutoToolTip"
0x98c7  ldstr    aNoneC// "none_c"
0x98cc  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::CreateClientAjaxComponent(string, string)
0x98d1  ret
```
