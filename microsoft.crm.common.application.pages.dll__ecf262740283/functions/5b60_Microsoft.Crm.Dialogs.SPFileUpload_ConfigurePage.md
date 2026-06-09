# Microsoft.Crm.Dialogs.SPFileUpload::ConfigurePage

- ea: `0x5b60`
- end: `0x5de1`
- name: `Microsoft.Crm.Dialogs.SPFileUpload::ConfigurePage`
- size: `641`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x5b60`

## string_xrefs

- `0x5b8d`: `/_static/_common/scripts/CommandBarActions.js`
- `0x5b9d`: `/_static/_common/styles/AutoToolTip.js`
- `0x5d35`: `isOneDriveLocationCreated`

## pseudocode

```c

```

## disassembly

```asm
0x5b60  ldarg.0
0x5b61  call     instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.PageManager::ConfigurePage()
0x5b66  ldarg.0
0x5b67  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x5b6c  ldstr    aMscrmDialogsco// "Mscrm.DialogsControl"
0x5b71  ldnull
0x5b72  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::CreateClientAjaxComponent(string, string)
0x5b77  ldarg.0
0x5b78  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x5b7d  ldstr    aStaticControls_1// "/_static/_controls/attachment/attachmen"...
0x5b82  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x5b87  ldarg.0
0x5b88  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x5b8d  ldstr    aStaticCommonSc_2// "/_static/_common/scripts/CommandBarActi"...
0x5b92  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x5b97  ldarg.0
0x5b98  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x5b9d  ldstr    aStaticCommonSt// "/_static/_common/styles/AutoToolTip.js"
0x5ba2  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x5ba7  ldarg.0
0x5ba8  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x5bad  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::AddWrpcTokenActionPath()
0x5bb2  ldarg.0
0x5bb3  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppAttachment Microsoft.Crm.Dialogs.SPFileUpload::crmAttachment
0x5bb8  ldstr    aGridCmdsDlgSpU// "/_grid/cmds/dlg_sp_upload.aspx"
0x5bbd  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x5bc2  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x5bc7  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppAttachment::set_SuccessUrl(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri)
0x5bcc  ldarg.0
0x5bcd  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppAttachment Microsoft.Crm.Dialogs.SPFileUpload::crmAttachment
0x5bd2  ldstr    aActivitiesAtta// "/Activities/Attachment/save.aspx"
0x5bd7  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x5bdc  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x5be1  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppAttachment::set_SaveUrl(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri)
0x5be6  ldarg.0
0x5be7  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppAttachment Microsoft.Crm.Dialogs.SPFileUpload::crmAttachment
0x5bec  ldstr    aActivitiesAtta_0// "/Activities/Attachment/upload.aspx"
0x5bf1  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x5bf6  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x5bfb  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppAttachment::set_UploadHandlerUrl(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri)
0x5c00  ldarg.0
0x5c01  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppAttachment Microsoft.Crm.Dialogs.SPFileUpload::crmAttachment
0x5c06  ldstr    aActivitiesAtta_1// "/Activities/Attachment/download.aspx"
0x5c0b  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x5c10  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x5c15  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppAttachment::set_DownloadHandlerUrl(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri)
0x5c1a  ldarg.0
0x5c1b  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppAttachment Microsoft.Crm.Dialogs.SPFileUpload::crmAttachment
0x5c20  ldstr    aAnnotationAnno// "annotation/annotationid"
0x5c25  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppAttachment::set_IdXmlNode(string)
0x5c2a  ldarg.0
0x5c2b  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppAttachment Microsoft.Crm.Dialogs.SPFileUpload::crmAttachment
0x5c30  ldarg.0
0x5c31  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x5c36  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x5c3b  ldstr    aPid// "pId"
0x5c40  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x5c45  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppAttachment::set_ParentId(string)
0x5c4a  ldarg.0
0x5c4b  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppAttachment Microsoft.Crm.Dialogs.SPFileUpload::crmAttachment
0x5c50  ldarg.0
0x5c51  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x5c56  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x5c5b  ldstr    aPtype// "pType"
0x5c60  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x5c65  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppAttachment::set_ParentType(string)
0x5c6a  ldarg.0
0x5c6b  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppAttachment Microsoft.Crm.Dialogs.SPFileUpload::crmAttachment
0x5c70  ldarg.0
0x5c71  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x5c76  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x5c7b  ldstr    aLocationid_0// "locationId"
0x5c80  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x5c85  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppAttachment::set_LocationId(string)
0x5c8a  ldarg.0
0x5c8b  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppAttachment Microsoft.Crm.Dialogs.SPFileUpload::crmAttachment
0x5c90  ldarg.0
0x5c91  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x5c96  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x5c9b  ldstr    aStepid// "stepId"
0x5ca0  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x5ca5  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppAttachment::set_StepId(string)
0x5caa  ldarg.0
0x5cab  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppAttachment Microsoft.Crm.Dialogs.SPFileUpload::crmAttachment
0x5cb0  ldc.i4.1
0x5cb1  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppAttachment::set_IsAttachmentDialog(bool)
0x5cb6  ldarg.0
0x5cb7  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppAttachment Microsoft.Crm.Dialogs.SPFileUpload::crmAttachment
0x5cbc  ldc.i4.0
0x5cbd  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppAttachment::set_IsNotesV2Attachment(bool)
0x5cc2  ldarg.0
0x5cc3  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x5cc8  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x5ccd  ldstr    aPopuperrorurl// "popupErrorUrl"
0x5cd2  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x5cd7  stloc.0
0x5cd8  ldloc.0
0x5cd9  brfalse.s loc_5D0E
0x5cdb  ldloc.0
0x5cdc  ldc.i4.2
0x5cdd  call     bool [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmUtility::IsValidRedirectUrl(string, valuetype [System]System.UriKind)
0x5ce2  brfalse.s loc_5D0E
0x5ce4  ldarg.0
0x5ce5  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppAttachment Microsoft.Crm.Dialogs.SPFileUpload::crmAttachment
0x5cea  ldarg.0
0x5ceb  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x5cf0  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x5cf5  ldstr    aPopuperrorurl// "popupErrorUrl"
0x5cfa  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x5cff  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x5d04  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x5d09  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppAttachment::set_PopupErrorUrl(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri)
0x5d0e  ldarg.0
0x5d0f  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::IsPersonalSitePresent()
0x5d14  stfld    bool Microsoft.Crm.Dialogs.SPFileUpload::isPersonalSitePresent
0x5d19  ldarg.0
0x5d1a  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x5d1f  ldstr    aIspersonalsite// "isPersonalSitePresent"
0x5d24  ldarg.0
0x5d25  ldfld    bool Microsoft.Crm.Dialogs.SPFileUpload::isPersonalSitePresent
0x5d2a  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, bool)
0x5d2f  ldarg.0
0x5d30  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x5d35  ldstr    aIsonedriveloca// "isOneDriveLocationCreated"
0x5d3a  ldc.i4.1
0x5d3b  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, bool)
0x5d40  ldarg.0
0x5d41  ldarg.0
0x5d42  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x5d47  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::IsInternetExplorer(class [System.Web]System.Web.HttpRequest)
0x5d4c  brtrue.s loc_5D55
0x5d4e  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::IsForOutlookClient()
0x5d53  br.s     loc_5D56
0x5d55  ldc.i4.1
0x5d56  stfld    bool Microsoft.Crm.Dialogs.SPFileUpload::isInternetExplorer
0x5d5b  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IOrganizationSettings [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.Organization::get_CurrentSettings()
0x5d60  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IOrganizationSettings::get_MaxUploadFileSize()
0x5d65  conv.r8
0x5d66  stloc.1
0x5d67  ldloc.1
0x5d68  ldc.r8   1048576.0
0x5d71  div
0x5d72  stloc.2
0x5d73  ldloc.2
0x5d74  ldc.r8   30.0
0x5d7d  ble.un.s loc_5D95
0x5d7f  ldc.r8   30.0
0x5d88  stloc.2
0x5d89  ldloc.2
0x5d8a  ldc.r8   1048576.0
0x5d93  mul
0x5d94  stloc.1
0x5d95  ldarg.0
0x5d96  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x5d9b  ldstr    aMaxuploadfiles// "maxUploadFileSize"
0x5da0  ldloc.1
0x5da1  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, float64)
0x5da6  ldarg.0
0x5da7  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentCulture()
0x5dac  ldarg.0
0x5dad  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x5db2  ldstr    aWebGridCmdsDlg_17// "Web._grid.cmds.dlg_sp_upload.LargeFile"
0x5db7  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x5dbc  ldc.i4.1
0x5dbd  newarr   [mscorlib]System.Object
0x5dc2  dup
0x5dc3  ldc.i4.0
0x5dc4  ldloca.s 2
0x5dc6  ldstr    aF2// "F2"
0x5dcb  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x5dd0  call     instance string [mscorlib]System.Double::ToString(string, class [mscorlib]System.IFormatProvider)
0x5dd5  stelem.ref
0x5dd6  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x5ddb  stfld    string Microsoft.Crm.Dialogs.SPFileUpload::LargeFileLabel
0x5de0  ret
```
