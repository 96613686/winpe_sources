# Microsoft.Crm.Web.Tools.DocumentManagement.AddLocationPage::ConfigurePage

- ea: `0x76c50`
- end: `0x77001`
- name: `Microsoft.Crm.Web.Tools.DocumentManagement.AddLocationPage::ConfigurePage`
- size: `945`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x76c50`
- `0x770d0`

## string_xrefs

- `0x76c81`: `/_common/styles/dialogs.css.aspx`
- `0x76d04`: `DocumentManagementWebService`
- `0x76dc8`: `DocumentManagement.CreateFolder.GenericError`
- `0x76e20`: `LOCID_SHAREPOINT_ACCESS_DENIED`
- `0x76e2b`: `DocumentManagement.AddLocation.AccessDenied`
- `0x76ec5`: `LOCID_DOCM__INVALID_PROTOCOL`
- `0x76ef1`: `DocumentManagement.Settings.AlternateAccessMappingError`
- `0x76fcc`: `cancreatefolder`
- `0x76fe6`: `cancreatefolder`

## pseudocode

```c

```

## disassembly

```asm
0x76c50  ldarg.0
0x76c51  call     instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.DialogBase::ConfigurePage()
0x76c56  ldarg.0
0x76c57  ldarg.0
0x76c58  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x76c5d  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x76c62  ldstr    aMode// "mode"
0x76c67  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x76c6c  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x76c71  call     int32 [mscorlib]System.Int32::Parse(string, class [mscorlib]System.IFormatProvider)
0x76c76  stfld    valuetype AddLocationDialogMode Microsoft.Crm.Web.Tools.DocumentManagement.AddLocationPage::mode
0x76c7b  ldarg.0
0x76c7c  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x76c81  ldstr    aCommonStylesDi// "/_common/styles/dialogs.css.aspx"
0x76c86  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0x76c8b  ldarg.0
0x76c8c  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x76c91  ldstr    aMscrmDialogsco// "Mscrm.DialogsControl"
0x76c96  ldnull
0x76c97  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::CreateClientAjaxComponent(string, string)
0x76c9c  ldarg.0
0x76c9d  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x76ca2  ldstr    aStaticToolsDoc_1// "/_static/tools/documentmanagement/scrip"...
0x76ca7  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x76cac  ldarg.0
0x76cad  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x76cb2  ldstr    aStaticToolsDoc_2// "/_static/tools/documentmanagement/scrip"...
0x76cb7  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x76cbc  ldarg.0
0x76cbd  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x76cc2  ldstr    aInitializedial// "InitializeDialogControls"
0x76cc7  ldstr    aInitializeaddl// "InitializeAddLocationDialogControls();"
0x76ccc  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptBlockForOnLoad(string, string)
0x76cd1  ldarg.0
0x76cd2  ldfld    class [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.LookupControl Microsoft.Crm.Web.Tools.DocumentManagement.AddLocationPage::locationLookup
0x76cd7  ldc.i4.2
0x76cd8  newarr   [mscorlib]System.Int32
0x76cdd  dup
0x76cde  ldc.i4.0
0x76cdf  ldc.i4   0x2524
0x76ce4  stelem.i4
0x76ce5  dup
0x76ce6  ldc.i4.1
0x76ce7  ldc.i4   0x251E
0x76cec  stelem.i4
0x76ced  callvirt instance void [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.LookupControl::set_LookupTypes(int32[])
0x76cf2  ldarg.0
0x76cf3  ldfld    class [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.LookupControl Microsoft.Crm.Web.Tools.DocumentManagement.AddLocationPage::locationLookup
0x76cf8  ldc.i4.1
0x76cf9  callvirt instance void [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.LookupControl::set_DisableViewPicker(bool)
0x76cfe  ldarg.0
0x76cff  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x76d04  ldstr    aDocumentmanage_1// "DocumentManagementWebService"
0x76d09  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::AddWrpcTokenActionPathWebService(string)
0x76d0e  ldarg.0
0x76d0f  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x76d14  ldstr    aLocidMessageCb// "LOCID_MESSAGE_CB_GRIDNOTPRESENT"
0x76d19  ldarg.0
0x76d1a  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x76d1f  ldstr    aDocumentmanage_2// "DocumentManagement.CrossBrowserGrid.Not"...
0x76d24  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x76d29  ldc.i4.0
0x76d2a  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x76d2f  ldarg.0
0x76d30  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x76d35  ldstr    aLocidConfirmCa_0// "LOCID_CONFIRM_CANCEL"
0x76d3a  ldarg.0
0x76d3b  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x76d40  ldstr    aDocumentmanage_3// "DocumentManagement.AddLocation.ConfirmC"...
0x76d45  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x76d4a  ldc.i4.0
0x76d4b  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x76d50  ldarg.0
0x76d51  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x76d56  ldstr    aLocidInvalidFo// "LOCID_INVALID_FOLDERNAME"
0x76d5b  ldarg.0
0x76d5c  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x76d61  ldstr    aErrorMessage0x_22// "Error_Message_0x80048054"
0x76d66  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x76d6b  ldc.i4.0
0x76d6c  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x76d71  ldarg.0
0x76d72  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x76d77  ldstr    aLocidDocmFolde// "LOCID_DOCM_FOLDERNAME_MAXLENGTH"
0x76d7c  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x76d81  ldarg.0
0x76d82  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x76d87  ldstr    aDocumentmanage_4// "DocumentManagement.AddLocation.FolderNa"...
0x76d8c  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x76d91  ldc.i4.1
0x76d92  newarr   [mscorlib]System.Object
0x76d97  dup
0x76d98  ldc.i4.0
0x76d99  ldc.i4   0x80
0x76d9e  stloc.0
0x76d9f  ldloca.s 0
0x76da1  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x76da6  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x76dab  stelem.ref
0x76dac  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x76db1  ldc.i4.0
0x76db2  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x76db7  ldarg.0
0x76db8  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x76dbd  ldstr    aLocidGenericMe// "LOCID_GENERIC_MESSAGE"
0x76dc2  ldarg.0
0x76dc3  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x76dc8  ldstr    aDocumentmanage_5// "DocumentManagement.CreateFolder.Generic"...
0x76dcd  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x76dd2  ldc.i4.0
0x76dd3  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x76dd8  ldarg.0
0x76dd9  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x76dde  ldstr    aLocidInvalidUr// "LOCID_INVALID_URL"
0x76de3  ldarg.0
0x76de4  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x76de9  ldstr    aDocumentmanage_6// "DocumentManagement.AddLocation.InvalidU"...
0x76dee  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x76df3  ldc.i4.0
0x76df4  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x76df9  ldarg.0
0x76dfa  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x76dff  ldstr    aLocidUrlNotifi// "LOCID_URL_NOTIFICATION"
0x76e04  ldarg.0
0x76e05  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x76e0a  ldstr    aDocumentmanage_7// "DocumentManagement.AddLocation.Notifica"...
0x76e0f  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x76e14  ldc.i4.0
0x76e15  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x76e1a  ldarg.0
0x76e1b  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x76e20  ldstr    aLocidSharepoin// "LOCID_SHAREPOINT_ACCESS_DENIED"
0x76e25  ldarg.0
0x76e26  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x76e2b  ldstr    aDocumentmanage_8// "DocumentManagement.AddLocation.AccessDe"...
0x76e30  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x76e35  ldc.i4.0
0x76e36  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x76e3b  ldarg.0
0x76e3c  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x76e41  ldstr    aLocidMessageGr// "LOCID_MESSAGE_GRIDNOTPRESENT"
0x76e46  ldarg.0
0x76e47  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x76e4c  ldstr    aWebToolsDocume_0// "Web.Tools.DocumentManagement.SettingsPa"...
0x76e51  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x76e56  ldc.i4.0
0x76e57  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x76e5c  ldarg.0
0x76e5d  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x76e62  ldstr    aLocidDocmParen// "LOCID_DOCM_PARENT_NOT_EXIST"
0x76e67  ldarg.0
0x76e68  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x76e6d  ldstr    aDocumentmanage_6// "DocumentManagement.AddLocation.InvalidU"...
0x76e72  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x76e77  ldc.i4.0
0x76e78  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x76e7d  ldarg.0
0x76e7e  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x76e83  ldstr    aLocidDocmSpsit// "LOCID_DOCM_SPSITE_INVALIDPARENT"
0x76e88  ldarg.0
0x76e89  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x76e8e  ldstr    aSharepointsite_1// "SharePointSite.Error.InvalidParentURL"
0x76e93  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x76e98  ldc.i4.0
0x76e99  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x76e9e  ldarg.0
0x76e9f  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x76ea4  ldstr    aLocidDocmSploc// "LOCID_DOCM_SPLOC_INVALIDPARENT"
0x76ea9  ldarg.0
0x76eaa  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x76eaf  ldstr    aSharepointdocu_2// "SharePointDocumentLocation.Error.Invali"...
0x76eb4  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x76eb9  ldc.i4.0
0x76eba  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x76ebf  ldarg.0
0x76ec0  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x76ec5  ldstr    aLocidDocmInval// "LOCID_DOCM__INVALID_PROTOCOL"
0x76eca  ldarg.0
0x76ecb  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x76ed0  ldstr    aWebFormsContro// "Web._forms.controls.INPUT.text.url.htc_"...
0x76ed5  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x76eda  ldc.i4.0
0x76edb  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x76ee0  ldarg.0
0x76ee1  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x76ee6  ldstr    aLocidDocmAamEr// "LOCID_DOCM_AAM_ERROR"
0x76eeb  ldarg.0
0x76eec  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x76ef1  ldstr    aDocumentmanage_9// "DocumentManagement.Settings.AlternateAc"...
0x76ef6  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x76efb  ldc.i4.0
0x76efc  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x76f01  ldarg.0
0x76f02  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x76f07  ldstr    aLocidStringLen// "LOCID_STRING_LENGTH_TOOLONG"
0x76f0c  ldarg.0
0x76f0d  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x76f12  ldstr    aErrorMessage0x_23// "Error_Message_0x8004f314"
0x76f17  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x76f1c  ldc.i4.0
0x76f1d  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x76f22  ldarg.0
0x76f23  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x76f28  ldstr    aDialogmode_0// "_dialogMode"
0x76f2d  ldarg.0
0x76f2e  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x76f33  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x76f38  ldstr    aMode// "mode"
0x76f3d  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x76f42  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, string)
0x76f47  ldarg.0
0x76f48  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x76f4d  ldstr    aSitecollection// "_siteCollectionUrl"
0x76f52  ldsfld   string [mscorlib]System.String::Empty
0x76f57  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, string)
0x76f5c  ldarg.0
0x76f5d  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x76f62  ldstr    aIntervalid// "_intervalId"
0x76f67  ldsfld   string [mscorlib]System.String::Empty
0x76f6c  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, string)
0x76f71  ldarg.0
0x76f72  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x76f77  ldstr    aSelectedlocati// "_selectedLocationUrl"
0x76f7c  ldsfld   string [mscorlib]System.String::Empty
0x76f81  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, string)
0x76f86  ldarg.0
0x76f87  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x76f8c  ldstr    aLocidDocmLangi// "LOCID_DOCM_LANGID"
0x76f91  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentUICulture()
0x76f96  callvirt instance string [mscorlib]System.Globalization.CultureInfo::get_Name()
0x76f9b  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, string)
0x76fa0  ldarg.0
0x76fa1  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x76fa6  ldstr    aDocmDefaultLoc// "DOCM_DEFAULT_LOCATION_NAME"
0x76fab  ldarg.0
0x76fac  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x76fb1  ldstr    aDocumentmanage_10// "DocumentManagement.DefaultLocationName."...
0x76fb6  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x76fbb  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, string)
0x76fc0  ldarg.0
0x76fc1  ldarg.0
0x76fc2  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x76fc7  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x76fcc  ldstr    aCancreatefolde// "cancreatefolder"
0x76fd1  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x76fd6  brtrue.s loc_76FDB
0x76fd8  ldc.i4.1
0x76fd9  br.s     loc_76FF5
0x76fdb  ldarg.0
0x76fdc  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x76fe1  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x76fe6  ldstr    aCancreatefolde// "cancreatefolder"
0x76feb  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x76ff0  call     bool [mscorlib]System.Boolean::Parse(string)
0x76ff5  stfld    bool Microsoft.Crm.Web.Tools.DocumentManagement.AddLocationPage::canCreateFolder
0x76ffa  ldarg.0
0x76ffb  call     instance void Microsoft.Crm.Web.Tools.DocumentManagement.AddLocationPage::InitializeControls()
0x77000  ret
```
