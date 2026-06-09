# Microsoft.Crm.Web.AdvancedFind.AdvancedFindPage::ConfigureHeader

- ea: `0x37db0`
- end: `0x37f43`
- name: `Microsoft.Crm.Web.AdvancedFind.AdvancedFindPage::ConfigureHeader`
- size: `403`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x37f50`

## string_xrefs

- `0x37e4f`: `/_static/_common/scripts/stage.js`
- `0x37ec2`: `/_static/_common/scripts/Performance.js`
- `0x37dbc`: `/Tools/PersonalSettings/cmds/cmd_update.aspx`
- `0x37dcc`: `XML_LANGUAGE_NAME`
- `0x37e3f`: `/_static/_common/scripts/ribbonactions.js`
- `0x37ea1`: `LOCID_FILENAME_FETCHXML`
- `0x37eac`: `FileName_FetchXml`

## pseudocode

```c

```

## disassembly

```asm
0x37db0  ldarg.0
0x37db1  call     instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.PageManager::ConfigureHeader()
0x37db6  ldarg.0
0x37db7  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x37dbc  ldstr    aToolsPersonals// "/Tools/PersonalSettings/cmds/cmd_update"...
0x37dc1  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::AddWrpcTokenActionPath(string)
0x37dc6  ldarg.0
0x37dc7  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x37dcc  ldstr    aXmlLanguageNam// "XML_LANGUAGE_NAME"
0x37dd1  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentUICulture()
0x37dd6  callvirt instance class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_Parent()
0x37ddb  callvirt instance string [mscorlib]System.Globalization.CultureInfo::get_TwoLetterISOLanguageName()
0x37de0  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, string)
0x37de5  ldarg.0
0x37de6  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x37deb  ldstr    aEntitytype_0// "_entityType"
0x37df0  ldarg.0
0x37df1  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x37df6  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x37dfb  ldstr    aEntitycode// "EntityCode"
0x37e00  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x37e05  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x37e0a  newobj   instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::.ctor(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x37e0f  call     instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::get_LogicalName()
0x37e14  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, string)
0x37e19  ldarg.0
0x37e1a  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x37e1f  ldstr    aFormsControlsF// "/_forms/controls/form.css.aspx"
0x37e24  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0x37e29  ldarg.0
0x37e2a  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x37e2f  ldstr    aStaticAdvanced_1// "/_static/advancedfind/AdvancedFindPage."...
0x37e34  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x37e39  ldarg.0
0x37e3a  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x37e3f  ldstr    aStaticCommonSc_14// "/_static/_common/scripts/ribbonactions."...
0x37e44  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x37e49  ldarg.0
0x37e4a  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x37e4f  ldstr    aStaticCommonSc_4// "/_static/_common/scripts/stage.js"
0x37e54  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x37e59  ldarg.0
0x37e5a  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x37e5f  ldstr    aLocidAfExecuti// "LOCID_AF_EXECUTINGSEARCH"
0x37e64  ldarg.0
0x37e65  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x37e6a  ldstr    aAfMessageExecu// "AF_Message_ExecutingSearch"
0x37e6f  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x37e74  ldc.i4.0
0x37e75  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x37e7a  ldarg.0
0x37e7b  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x37e80  ldstr    aLocidPageloadi// "LOCID_PAGELOADING"
0x37e85  ldarg.0
0x37e86  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x37e8b  ldstr    aPageloadingmes// "PageLoadingMessage"
0x37e90  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x37e95  ldc.i4.0
0x37e96  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x37e9b  ldarg.0
0x37e9c  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x37ea1  ldstr    aLocidFilenameF// "LOCID_FILENAME_FETCHXML"
0x37ea6  ldarg.0
0x37ea7  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x37eac  ldstr    aFilenameFetchx// "FileName_FetchXml"
0x37eb1  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x37eb6  ldc.i4.0
0x37eb7  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x37ebc  ldarg.0
0x37ebd  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x37ec2  ldstr    aStaticCommonSc_5// "/_static/_common/scripts/Performance.js"
0x37ec7  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x37ecc  ldarg.0
0x37ecd  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x37ed2  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x37ed7  ldstr    aTitleAdvancedf// "Title_AdvancedFind"
0x37edc  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x37ee1  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::set_Title(string)
0x37ee6  ldarg.0
0x37ee7  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x37eec  ldstr    aSettitle// "SetTitle"
0x37ef1  ldstr    aSetpagetitle// "setPageTitle("
0x37ef6  ldarg.0
0x37ef7  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x37efc  callvirt instance string [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::get_Title()
0x37f01  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmJavaScriptEncode(string)
0x37f06  ldstr    asc_12EE04// ");"
0x37f0b  call     string [mscorlib]System.String::Concat(string, string, string)
0x37f10  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptBlockForOnLoad(string, string)
0x37f15  ldarg.0
0x37f16  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x37f1b  ldstr    aOnloadhandler// "OnLoadHandler"
0x37f20  ldstr    aOnloadhandler_0// "OnLoadHandler();"
0x37f25  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptBlockForOnLoad(string, string)
0x37f2a  ldarg.0
0x37f2b  call     instance class [mscorlib]System.Collections.Generic.IDictionary`2<string, int32> Microsoft.Crm.Web.AdvancedFind.AdvancedFindPage::BuildEntityTypeMapScript()
0x37f30  stloc.0
0x37f31  ldarg.0
0x37f32  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x37f37  ldstr    aEntitytypemap// "EntityTypeMap"
0x37f3c  ldloc.0
0x37f3d  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, class [mscorlib]System.Collections.Generic.IDictionary`2<string, int32>)
0x37f42  ret
```
