# Microsoft.Crm.Web.BusinessManagement.MailMergeTemplateDetailPage::ConfigurePage

- ea: `0x371c0`
- end: `0x37479`
- name: `Microsoft.Crm.Web.BusinessManagement.MailMergeTemplateDetailPage::ConfigurePage`
- size: `697`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x37160`
- `0x371c0`

## string_xrefs

- `0x37377`: `MailMerge_Button_Label_ViewOrUpdateColumns`
- `0x372fd`: `mailmergetemplate`
- `0x3728d`: `mailmergetemplate/mailmergetemplateid`
- `0x373fa`: `LOCID_PUBLISHTEMPLATE_DIRTY`
- `0x3741b`: `LOCID_UNPUBLISHTEMPLATE_DIRTY`

## pseudocode

```c

```

## disassembly

```asm
0x371c0  ldarg.0
0x371c1  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x371c6  ldstr    aStaticToolsVie// "/_static/tools/vieweditor/scripts/objec"...
0x371cb  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x371d0  ldarg.0
0x371d1  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x371d6  ldstr    aStaticToolsVie_0// "/_static/tools/vieweditor/scripts/util."...
0x371db  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x371e0  ldarg.0
0x371e1  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x371e6  ldstr    aStaticToolsVie_1// "/_static/tools/vieweditor/scripts/viewm"...
0x371eb  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x371f0  ldarg.0
0x371f1  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x371f6  ldstr    aToolsMailmerge// "/tools/mailmerge/styles/mailmerge.css.a"...
0x371fb  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0x37200  ldarg.0
0x37201  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x37206  ldstr    aFormsControlsF// "/_forms/controls/form.css.aspx"
0x3720b  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0x37210  ldarg.0
0x37211  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppAttachment Microsoft.Crm.Web.BusinessManagement.MailMergeTemplateDetailPage::crmAttachment
0x37216  ldstr    aToolsMailmerge_0// "/Tools/MailMerge/edit.aspx"
0x3721b  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x37220  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x37225  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppAttachment::set_SuccessUrl(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri)
0x3722a  ldarg.0
0x3722b  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppAttachment Microsoft.Crm.Web.BusinessManagement.MailMergeTemplateDetailPage::crmAttachment
0x37230  ldstr    aToolsMailmerge_0// "/Tools/MailMerge/edit.aspx"
0x37235  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x3723a  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x3723f  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppAttachment::set_SaveUrl(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri)
0x37244  ldarg.0
0x37245  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppAttachment Microsoft.Crm.Web.BusinessManagement.MailMergeTemplateDetailPage::crmAttachment
0x3724a  ldstr    aActivitiesAtta_0// "/Activities/Attachment/upload.aspx"
0x3724f  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x37254  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x37259  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppAttachment::set_UploadHandlerUrl(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri)
0x3725e  ldarg.0
0x3725f  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppAttachment Microsoft.Crm.Web.BusinessManagement.MailMergeTemplateDetailPage::crmAttachment
0x37264  ldstr    aActivitiesAtta// "/Activities/Attachment/download.aspx"
0x37269  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x3726e  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x37273  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppAttachment::set_DownloadHandlerUrl(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri)
0x37278  ldarg.0
0x37279  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppAttachment Microsoft.Crm.Web.BusinessManagement.MailMergeTemplateDetailPage::crmAttachment
0x3727e  ldstr    asc_13CDBE// "/"
0x37283  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x37288  call     string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::RetrieveOrganizationName(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x3728d  ldstr    aMailmergetempl_0// "mailmergetemplate/mailmergetemplateid"
0x37292  call     string [mscorlib]System.String::Concat(string, string, string)
0x37297  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppAttachment::set_IdXmlNode(string)
0x3729c  ldarg.0
0x3729d  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppAttachment Microsoft.Crm.Web.BusinessManagement.MailMergeTemplateDetailPage::crmAttachment
0x372a2  ldarg.0
0x372a3  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x372a8  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x372ad  ldstr    aId// "id"
0x372b2  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x372b7  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x372bc  brtrue.s loc_372D5
0x372be  ldarg.0
0x372bf  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x372c4  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x372c9  ldstr    aId// "id"
0x372ce  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x372d3  br.s     loc_372E8
0x372d5  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x372da  stloc.1
0x372db  ldloca.s 1
0x372dd  constrained. [mscorlib]System.Guid
0x372e3  callvirt instance string [mscorlib]System.Object::ToString()
0x372e8  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppAttachment::set_ParentId(string)
0x372ed  ldarg.0
0x372ee  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppAttachment Microsoft.Crm.Web.BusinessManagement.MailMergeTemplateDetailPage::crmAttachment
0x372f3  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x372f8  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x372fd  ldstr    aMailmergetempl// "mailmergetemplate"
0x37302  ldc.i4.1
0x37303  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::GetEntity(string, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.NameMappingType)
0x37308  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_Code()
0x3730d  stloc.2
0x3730e  ldloca.s 2
0x37310  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x37315  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x3731a  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppAttachment::set_ParentType(string)
0x3731f  ldarg.0
0x37320  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x37325  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x3732a  ldstr    aPopuperrorurl// "popupErrorUrl"
0x3732f  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x37334  stloc.0
0x37335  ldloc.0
0x37336  brfalse.s loc_3736B
0x37338  ldloc.0
0x37339  ldc.i4.2
0x3733a  call     bool [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmUtility::IsValidRedirectUrl(string, valuetype [System]System.UriKind)
0x3733f  brfalse.s loc_3736B
0x37341  ldarg.0
0x37342  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppAttachment Microsoft.Crm.Web.BusinessManagement.MailMergeTemplateDetailPage::crmAttachment
0x37347  ldarg.0
0x37348  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x3734d  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x37352  ldstr    aPopuperrorurl// "popupErrorUrl"
0x37357  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x3735c  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x37361  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x37366  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppAttachment::set_PopupErrorUrl(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri)
0x3736b  ldarg.0
0x3736c  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Button Microsoft.Crm.Web.BusinessManagement.MailMergeTemplateDetailPage::get_ViewOrUpdateButton()
0x37371  ldarg.0
0x37372  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x37377  ldstr    aMailmergeButto_0// "MailMerge_Button_Label_ViewOrUpdateColu"...
0x3737c  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x37381  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Button::set_Text(string)
0x37386  ldarg.0
0x37387  ldarg.0
0x37388  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x3738d  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x37392  ldstr    aId// "id"
0x37397  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x3739c  stfld    string Microsoft.Crm.Web.BusinessManagement.MailMergeTemplateDetailPage::objectId
0x373a1  ldarg.0
0x373a2  ldarg.0
0x373a3  ldfld    string Microsoft.Crm.Web.BusinessManagement.MailMergeTemplateDetailPage::objectId
0x373a8  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x373ad  stfld    bool Microsoft.Crm.Web.BusinessManagement.MailMergeTemplateDetailPage::isNew
0x373b2  ldarg.0
0x373b3  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x373b8  ldstr    aLocidColumnsSe_0// "LOCID_COLUMNS_SELECTED_SAVE"
0x373bd  ldarg.0
0x373be  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x373c3  ldstr    aMailmergeButto_1// "MailMerge_Button_Label_SelectedColumns_"...
0x373c8  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x373cd  ldc.i4.0
0x373ce  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x373d3  ldarg.0
0x373d4  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x373d9  ldstr    aLocidColumnsDe// "LOCID_COLUMNS_DEFAULT"
0x373de  ldarg.0
0x373df  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x373e4  ldstr    aMailmergeDefau// "MailMerge_DefaultSelectedColumns"
0x373e9  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x373ee  ldc.i4.0
0x373ef  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x373f4  ldarg.0
0x373f5  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x373fa  ldstr    aLocidPublishte// "LOCID_PUBLISHTEMPLATE_DIRTY"
0x373ff  ldarg.0
0x37400  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x37405  ldstr    aMailmergePubli// "MailMerge_Publish_Error_Dirty"
0x3740a  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x3740f  ldc.i4.0
0x37410  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x37415  ldarg.0
0x37416  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x3741b  ldstr    aLocidUnpublish// "LOCID_UNPUBLISHTEMPLATE_DIRTY"
0x37420  ldarg.0
0x37421  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x37426  ldstr    aMailmergeUnpub// "MailMerge_Unpublish_Error_Dirty"
0x3742b  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x37430  ldc.i4.0
0x37431  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x37436  ldarg.0
0x37437  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x3743c  ldstr    aLocidLaunchwor// "LOCID_LAUNCHWORD_DIRTY"
0x37441  ldarg.0
0x37442  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x37447  ldstr    aMailmergeLaunc// "MailMerge_LaunchWord_Error_Dirty"
0x3744c  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x37451  ldc.i4.0
0x37452  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x37457  ldarg.0
0x37458  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x3745d  ldstr    aLocidMaxcolumn// "LOCID_MAXCOLUMN_ERROR"
0x37462  ldarg.0
0x37463  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x37468  ldstr    aAlertMailMerge_1// "Alert_Mail_Merge_MaxColumn_Error"
0x3746d  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x37472  ldc.i4.0
0x37473  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x37478  ret
```
