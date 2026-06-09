# Microsoft.Crm.Application.Pages.Grids.ExportDialog::ConfigurePage

- ea: `0xf7b30`
- end: `0xf7efe`
- name: `Microsoft.Crm.Application.Pages.Grids.ExportDialog::ConfigurePage`
- size: `974`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0xf7b10`
- `0xf7b30`
- `0xf7f00`
- `0xf7f50`

## string_xrefs

- `0xf7b3c`: `/_common/styles/dialogs.css.aspx`
- `0xf7d56`: `fetchXml`
- `0xf7c4f`: `UpdateViaImport.ExportToExcelDialog.DuplicateColumnsInGrid`
- `0xf7c6a`: `UpdateViaImport.ExportToExcelDialog.Excel2010Warning`

## pseudocode

```c

```

## disassembly

```asm
0xf7b30  ldarg.0
0xf7b31  call     instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.DialogBase::ConfigurePage()
0xf7b36  ldarg.0
0xf7b37  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xf7b3c  ldstr    aCommonStylesDi// "/_common/styles/dialogs.css.aspx"
0xf7b41  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0xf7b46  ldarg.0
0xf7b47  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xf7b4c  ldstr    aMscrmDialogsco// "Mscrm.DialogsControl"
0xf7b51  ldnull
0xf7b52  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::CreateClientAjaxComponent(string, string)
0xf7b57  ldarg.0
0xf7b58  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xf7b5d  ldstr    aStaticToolsFor// "/_static/tools/formeditor/scripts/objec"...
0xf7b62  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0xf7b67  ldarg.0
0xf7b68  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0xf7b6d  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0xf7b72  ldstr    aOtc// "otc"
0xf7b77  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0xf7b7c  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xf7b81  call     int32 [mscorlib]System.Int32::Parse(string, class [mscorlib]System.IFormatProvider)
0xf7b86  stloc.0
0xf7b87  ldarg.0
0xf7b88  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xf7b8d  ldstr    aObjectTypeCode// "OBJECT_TYPE_CODE"
0xf7b92  ldloc.0
0xf7b93  conv.i8
0xf7b94  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, int64)
0xf7b99  ldarg.0
0xf7b9a  ldarg.0
0xf7b9b  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0xf7ba0  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0xf7ba5  ldstr    aMultipage// "multipage"
0xf7baa  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0xf7baf  ldstr    a1// "1"
0xf7bb4  call     bool [mscorlib]System.String::op_Equality(string, string)
0xf7bb9  stfld    bool Microsoft.Crm.Application.Pages.Grids.ExportDialog::showMultiplePage
0xf7bbe  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor()
0xf7bc3  stloc.1
0xf7bc4  ldloc.1
0xf7bc5  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xf7bca  newobj   instance void [mscorlib]System.IO.StringWriter::.ctor(class [mscorlib]System.Text.StringBuilder, class [mscorlib]System.IFormatProvider)
0xf7bcf  newobj   instance void [System.Web]System.Web.UI.HtmlTextWriter::.ctor(class [mscorlib]System.IO.TextWriter)
0xf7bd4  stloc.2
0xf7bd5  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xf7bda  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_OrganizationId()
0xf7bdf  stloc.3
0xf7be0  ldloc.3
0xf7be1  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::.ctor(valuetype [mscorlib]System.Guid)
0xf7be6  stloc.s  4
0xf7be8  ldarg.0
0xf7be9  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.OrganizationCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.OrganizationCache::Instance()
0xf7bee  ldloc.3
0xf7bef  ldloc.s  4
0xf7bf1  callvirt instance var<u1> class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.CrmMultiOrgCacheBase`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IOrganizationSettings>::LookupEntry(void, var<u1>)
0xf7bf6  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IOrganizationSettings::get_AllowWebExcelExport()
0xf7bfb  stfld    bool Microsoft.Crm.Application.Pages.Grids.ExportDialog::showStatic
0xf7c00  ldloc.s  4
0xf7c02  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xf7c07  ldloc.0
0xf7c08  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::GetEntity(int32)
0xf7c0d  stloc.s  5
0xf7c0f  ldarg.0
0xf7c10  ldloc.s  5
0xf7c12  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_IsImportable()
0xf7c17  stfld    bool Microsoft.Crm.Application.Pages.Grids.ExportDialog::showReimport
0xf7c1c  ldarg.0
0xf7c1d  ldarg.0
0xf7c1e  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0xf7c23  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0xf7c28  ldstr    aDuplicatecolum// "DuplicateColumnsPresent"
0xf7c2d  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0xf7c32  ldstr    a1// "1"
0xf7c37  call     bool [mscorlib]System.String::op_Inequality(string, string)
0xf7c3c  stfld    bool Microsoft.Crm.Application.Pages.Grids.ExportDialog::enableReimport
0xf7c41  ldarg.0
0xf7c42  ldfld    bool Microsoft.Crm.Application.Pages.Grids.ExportDialog::enableReimport
0xf7c47  brtrue.s loc_F7C5C
0xf7c49  ldarg.0
0xf7c4a  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppNotifications Microsoft.Crm.Application.Pages.Grids.ExportDialog::updateViaImportNotification
0xf7c4f  ldstr    aUpdateviaimpor_0// "UpdateViaImport.ExportToExcelDialog.Dup"...
0xf7c54  ldc.i4.1
0xf7c55  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppNotifications::AddNotification(string, int32)
0xf7c5a  br.s     loc_F7C75
0xf7c5c  ldarg.0
0xf7c5d  call     instance bool Microsoft.Crm.Application.Pages.Grids.ExportDialog::get_ExportToExcelEnabled()
0xf7c62  brtrue.s loc_F7C75
0xf7c64  ldarg.0
0xf7c65  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppNotifications Microsoft.Crm.Application.Pages.Grids.ExportDialog::updateViaImportNotification
0xf7c6a  ldstr    aUpdateviaimpor_1// "UpdateViaImport.ExportToExcelDialog.Exc"...
0xf7c6f  ldc.i4.2
0xf7c70  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppNotifications::AddNotification(string, int32)
0xf7c75  ldarg.0
0xf7c76  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppNotifications Microsoft.Crm.Application.Pages.Grids.ExportDialog::updateViaImportNotification
0xf7c7b  callvirt instance class [System.Web]System.Web.UI.CssStyleCollection [System.Web]System.Web.UI.HtmlControls.HtmlControl::get_Style()
0xf7c80  ldc.i4.s 0x12
0xf7c82  ldstr    aNone_0// "none"
0xf7c87  callvirt instance void [System.Web]System.Web.UI.CssStyleCollection::Add(valuetype [System.Web]System.Web.UI.HtmlTextWriterStyle, string)
0xf7c8c  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::IsOnline()
0xf7c91  brfalse.s loc_F7CB6
0xf7c93  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xf7c98  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_OrganizationId()
0xf7c9d  call     bool [Microsoft.Crm]Microsoft.Crm.ApplicationConfig::UseWebQueryForLiveExport(valuetype [mscorlib]System.Guid)
0xf7ca2  brtrue.s loc_F7CB3
0xf7ca4  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xf7ca9  callvirt instance int32 [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_AuthenticationType()
0xf7cae  ldc.i4.0
0xf7caf  ceq
0xf7cb1  br.s     loc_F7CB7
0xf7cb3  ldc.i4.0
0xf7cb4  br.s     loc_F7CB7
0xf7cb6  ldc.i4.1
0xf7cb7  stloc.s  6
0xf7cb9  ldarg.0
0xf7cba  ldloc.s  6
0xf7cbc  ldloc.s  5
0xf7cbe  call     instance bool Microsoft.Crm.Application.Pages.Grids.ExportDialog::AllowLiveExport(bool useSqlQueryForLiveExport, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata entity)
0xf7cc3  brfalse.s loc_F7CE6
0xf7cc5  ldarg.0
0xf7cc6  ldc.i4.1
0xf7cc7  stfld    bool Microsoft.Crm.Application.Pages.Grids.ExportDialog::enableLive
0xf7ccc  ldarg.0
0xf7ccd  ldloc.2
0xf7cce  ldstr    aUsesqlquery// "useSqlQuery"
0xf7cd3  ldloca.s 6
0xf7cd5  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xf7cda  call     instance string [mscorlib]System.Boolean::ToString(class [mscorlib]System.IFormatProvider)
0xf7cdf  call     instance void Microsoft.Crm.Application.Pages.Grids.ExportDialog::writeParam(class [System.Web]System.Web.UI.HtmlTextWriter writer, string id, string value)
0xf7ce4  br.s     loc_F7CF7
0xf7ce6  ldarg.0
0xf7ce7  callvirt instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppNotifications [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_Notifications()
0xf7cec  ldstr    aMessageSpecial// "Message_SpecialView_ExportXL"
0xf7cf1  ldc.i4.3
0xf7cf2  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppNotifications::AddNotification(string, int32)
0xf7cf7  ldarg.0
0xf7cf8  ldfld    bool Microsoft.Crm.Application.Pages.Grids.ExportDialog::enableLive
0xf7cfd  brfalse.s loc_F7D67
0xf7cff  ldloc.s  6
0xf7d01  brtrue.s loc_F7D67
0xf7d03  ldarg.0
0xf7d04  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0xf7d09  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_Params()
0xf7d0e  ldstr    aViewid// "viewid"
0xf7d13  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0xf7d18  ldloca.s 0xA
0xf7d1a  call     bool [mscorlib]System.Guid::TryParse(string, valuetype [mscorlib]System.Guid&)
0xf7d1f  brfalse.s loc_F7D67
0xf7d21  ldarg.0
0xf7d22  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0xf7d27  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_Params()
0xf7d2c  ldstr    aViewtype// "viewtype"
0xf7d31  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0xf7d36  ldc.i4.7
0xf7d37  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xf7d3c  ldloca.s 0xB
0xf7d3e  call     bool [mscorlib]System.Int32::TryParse(string, valuetype [mscorlib]System.Globalization.NumberStyles, class [mscorlib]System.IFormatProvider, int32&)
0xf7d43  brfalse.s loc_F7D67
0xf7d45  ldloc.s  0xA
0xf7d47  ldloc.s  0xB
0xf7d49  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.View [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Caching.ViewLoader::GetView(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.ViewType)
0xf7d4e  stloc.s  0xC
0xf7d50  ldloc.s  0xC
0xf7d52  brfalse.s loc_F7D67
0xf7d54  ldarg.0
0xf7d55  ldloc.2
0xf7d56  ldstr    aFetchxml// "fetchXml"
0xf7d5b  ldloc.s  0xC
0xf7d5d  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.View::get_FetchXml()
0xf7d62  call     instance void Microsoft.Crm.Application.Pages.Grids.ExportDialog::writeParam(class [System.Web]System.Web.UI.HtmlTextWriter writer, string id, string value)
0xf7d67  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.OrganizationCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.OrganizationCache::Instance()
0xf7d6c  ldloc.3
0xf7d6d  ldloc.s  4
0xf7d6f  callvirt instance var<u1> class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.CrmMultiOrgCacheBase`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IOrganizationSettings>::LookupEntry(void, var<u1>)
0xf7d74  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IOrganizationSettings::get_MaxRecordsForExportToExcel()
0xf7d79  stloc.s  7
0xf7d7b  ldc.i4.0
0xf7d7c  stloc.s  8
0xf7d7e  ldc.i4.0
0xf7d7f  stloc.s  9
0xf7d81  ldarg.0
0xf7d82  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0xf7d87  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0xf7d8c  ldstr    aTotalrecordcou// "TotalRecordCount"
0xf7d91  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0xf7d96  brfalse.s loc_F7DBE
0xf7d98  ldarg.0
0xf7d99  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0xf7d9e  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0xf7da3  ldstr    aTotalrecordcou// "TotalRecordCount"
0xf7da8  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0xf7dad  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xf7db2  call     int32 [mscorlib]System.Int32::Parse(string, class [mscorlib]System.IFormatProvider)
0xf7db7  ldloc.s  7
0xf7db9  ble.s    loc_F7DBE
0xf7dbb  ldc.i4.1
0xf7dbc  stloc.s  8
0xf7dbe  ldarg.0
0xf7dbf  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0xf7dc4  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0xf7dc9  ldstr    aPagerecordcoun// "PageRecordCount"
0xf7dce  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0xf7dd3  brfalse.s loc_F7DFB
0xf7dd5  ldarg.0
0xf7dd6  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0xf7ddb  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0xf7de0  ldstr    aPagerecordcoun// "PageRecordCount"
0xf7de5  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0xf7dea  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xf7def  call     int32 [mscorlib]System.Int32::Parse(string, class [mscorlib]System.IFormatProvider)
0xf7df4  ldloc.s  7
0xf7df6  ble.s    loc_F7DFB
0xf7df8  ldc.i4.1
0xf7df9  stloc.s  9
0xf7dfb  ldarg.0
0xf7dfc  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xf7e01  ldstr    aTotalrecordcou_0// "totalRecordCountExceedsLimit"
0xf7e06  ldloc.s  8
0xf7e08  brtrue.s loc_F7E11
0xf7e0a  ldstr    a0_1// "0"
0xf7e0f  br.s     loc_F7E16
0xf7e11  ldstr    a1// "1"
0xf7e16  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, string)
0xf7e1b  ldarg.0
0xf7e1c  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xf7e21  ldstr    aPagerecordcoun_0// "pageRecordCountExceedsLimit"
0xf7e26  ldloc.s  9
0xf7e28  brtrue.s loc_F7E31
0xf7e2a  ldstr    a0_1// "0"
0xf7e2f  br.s     loc_F7E36
0xf7e31  ldstr    a1// "1"
0xf7e36  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, string)
0xf7e3b  ldloc.s  8
0xf7e3d  ldloc.s  9
0xf7e3f  or
0xf7e40  brfalse.s loc_F7EA6
0xf7e42  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xf7e47  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xf7e4c  ldstr    aMessageMaxreco// "Message_MaxRecordsWarning_ExportXL"
0xf7e51  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xf7e56  ldc.i4.2
0xf7e57  newarr   [mscorlib]System.Object
0xf7e5c  dup
0xf7e5d  ldc.i4.0
0xf7e5e  ldloc.s  7
0xf7e60  box      [mscorlib]System.Int32
0xf7e65  stelem.ref
0xf7e66  dup
0xf7e67  ldc.i4.1
0xf7e68  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xf7e6d  ldstr    aC5c18b6a47d141// "C5C18B6A-47D1-4176-BD01-CD39ACF15234"
0xf7e72  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xf7e77  stelem.ref
0xf7e78  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xf7e7d  stloc.s  0xD
0xf7e7f  ldstr    aMessageMaxreco// "Message_MaxRecordsWarning_ExportXL"
0xf7e84  ldc.i4.2
0xf7e85  ldstr    aServer// "Server"
0xf7e8a  ldloc.s  0xD
0xf7e8c  ldsfld   string [mscorlib]System.String::Empty
0xf7e91  newobj   instance void [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.Platform.Notifications.Notification::.ctor(string, int32, string, string, string)
0xf7e96  stloc.s  0xE
0xf7e98  ldarg.0
0xf7e99  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppNotifications Microsoft.Crm.Application.Pages.Grids.ExportDialog::maxWarningNotifications
0xf7e9e  ldloc.s  0xE
0xf7ea0  ldc.i4.1
0xf7ea1  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppNotifications::AddNotification(class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.Platform.Notifications.Notification, bool)
0xf7ea6  ldarg.0
0xf7ea7  ldfld    bool Microsoft.Crm.Application.Pages.Grids.ExportDialog::showStatic
0xf7eac  brtrue.s loc_F7EC2
0xf7eae  ldarg.0
0xf7eaf  ldfld    bool Microsoft.Crm.Application.Pages.Grids.ExportDialog::enableLive
0xf7eb4  brtrue.s loc_F7EC2
0xf7eb6  ldarg.0
0xf7eb7  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Button Microsoft.Crm.Application.Pages.Grids.ExportDialog::dialogOkButton
0xf7ebc  ldc.i4.1
0xf7ebd  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::set_Disabled(bool)
0xf7ec2  ldarg.0
0xf7ec3  ldfld    class [System.Web]System.Web.UI.HtmlControls.HtmlGenericControl Microsoft.Crm.Application.Pages.Grids.ExportDialog::divParameters
0xf7ec8  ldloc.1
0xf7ec9  callvirt instance string [mscorlib]System.Object::ToString()
0xf7ece  callvirt instance void [System.Web]System.Web.UI.HtmlControls.HtmlContainerControl::set_InnerHtml(string)
0xf7ed3  ldarg.0
0xf7ed4  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xf7ed9  ldstr    aButtonExportxl// "Button_ExportXL"
0xf7ede  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xf7ee3  stfld    string Microsoft.Crm.Application.Pages.Grids.ExportDialog::exportResourceId
0xf7ee8  ldarg.0
0xf7ee9  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xf7eee  ldstr    aButtonNext// "Button_Next"
0xf7ef3  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xf7ef8  stfld    string Microsoft.Crm.Application.Pages.Grids.ExportDialog::nextResourceId
0xf7efd  ret
```
