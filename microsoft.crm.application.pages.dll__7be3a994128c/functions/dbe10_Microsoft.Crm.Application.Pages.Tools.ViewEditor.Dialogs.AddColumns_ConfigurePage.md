# Microsoft.Crm.Application.Pages.Tools.ViewEditor.Dialogs.AddColumns::ConfigurePage

- ea: `0xdbe10`
- end: `0xdc00a`
- name: `Microsoft.Crm.Application.Pages.Tools.ViewEditor.Dialogs.AddColumns::ConfigurePage`
- size: `506`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callees

- `0xdbe10`
- `0xdc3d0`

## string_xrefs

- `0xdbe36`: `/_common/styles/dialogs.css.aspx`
- `0xdbec3`: `Grid.Common.Alt.SortedColumn.Down`
- `0xdbee4`: `Grid.Common.Alt.SortedColumn.Up`
- `0xdbe1c`: `XML_LANGUAGE_NAME`
- `0xdbfa6`: `readOnly`

## pseudocode

```c

```

## disassembly

```asm
0xdbe10  ldarg.0
0xdbe11  call     instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.DialogBase::ConfigurePage()
0xdbe16  ldarg.0
0xdbe17  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xdbe1c  ldstr    aXmlLanguageNam// "XML_LANGUAGE_NAME"
0xdbe21  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentUICulture()
0xdbe26  callvirt instance string [mscorlib]System.Globalization.CultureInfo::get_Name()
0xdbe2b  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, string)
0xdbe30  ldarg.0
0xdbe31  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xdbe36  ldstr    aCommonStylesDi// "/_common/styles/dialogs.css.aspx"
0xdbe3b  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0xdbe40  ldarg.0
0xdbe41  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xdbe46  ldstr    aMscrmDialogsco// "Mscrm.DialogsControl"
0xdbe4b  ldnull
0xdbe4c  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::CreateClientAjaxComponent(string, string)
0xdbe51  ldarg.0
0xdbe52  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xdbe57  ldstr    aStaticToolsVie// "/_static/tools/vieweditor/scripts/objec"...
0xdbe5c  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0xdbe61  ldarg.0
0xdbe62  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xdbe67  ldstr    aStaticToolsVie_4// "/_static/tools/vieweditor/scripts/field"...
0xdbe6c  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0xdbe71  ldarg.0
0xdbe72  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xdbe77  ldstr    aStaticToolsVie_0// "/_static/tools/vieweditor/scripts/util."...
0xdbe7c  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0xdbe81  ldarg.0
0xdbe82  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xdbe87  ldstr    aStaticToolsVie_1// "/_static/tools/vieweditor/scripts/viewm"...
0xdbe8c  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0xdbe91  ldarg.0
0xdbe92  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xdbe97  ldstr    aLocidQuickFind_0// "LOCID_QUICK_FIND_FIELD_REQUIRED"
0xdbe9c  ldarg.0
0xdbe9d  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xdbea2  ldstr    aWebToolsViewed_39// "Web.Tools.ViewEditor.Dialogs.AddColumns"...
0xdbea7  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xdbeac  ldc.i4.0
0xdbead  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xdbeb2  ldarg.0
0xdbeb3  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xdbeb8  ldstr    aLocidAltColumn// "LOCID_ALT_COLUMNSORTORDER_DOWN"
0xdbebd  ldarg.0
0xdbebe  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xdbec3  ldstr    aGridCommonAltS// "Grid.Common.Alt.SortedColumn.Down"
0xdbec8  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xdbecd  ldc.i4.0
0xdbece  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xdbed3  ldarg.0
0xdbed4  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xdbed9  ldstr    aLocidAltColumn_0// "LOCID_ALT_COLUMNSORTORDER_UP"
0xdbede  ldarg.0
0xdbedf  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xdbee4  ldstr    aGridCommonAltS_0// "Grid.Common.Alt.SortedColumn.Up"
0xdbee9  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xdbeee  ldc.i4.0
0xdbeef  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xdbef4  ldarg.0
0xdbef5  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xdbefa  ldstr    aLocidColumnsSe// "LOCID_COLUMNS_SELECTED"
0xdbeff  ldarg.0
0xdbf00  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xdbf05  ldstr    aWebToolsViewed_40// "Web.Tools.ViewEditor.Dialogs.AddColumns"...
0xdbf0a  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xdbf0f  ldc.i4.0
0xdbf10  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xdbf15  ldarg.0
0xdbf16  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xdbf1b  ldstr    aLocidMaxcolumn// "LOCID_MAXCOLUMN_ERROR"
0xdbf20  ldarg.0
0xdbf21  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xdbf26  ldstr    aAlertMailMerge_1// "Alert_Mail_Merge_MaxColumn_Error"
0xdbf2b  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xdbf30  ldc.i4.0
0xdbf31  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xdbf36  ldarg.0
0xdbf37  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xdbf3c  ldstr    aSfriendlytypen// "_sFriendlyTypeNames"
0xdbf41  ldarg.0
0xdbf42  call     instance string Microsoft.Crm.Application.Pages.Tools.ViewEditor.Dialogs.AddColumns::GetFriendlyTypeNameXml()
0xdbf47  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, string)
0xdbf4c  ldarg.0
0xdbf4d  ldarg.0
0xdbf4e  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0xdbf53  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0xdbf58  ldstr    aMode// "mode"
0xdbf5d  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0xdbf62  stfld    string Microsoft.Crm.Application.Pages.Tools.ViewEditor.Dialogs.AddColumns::Mode
0xdbf67  ldarg.0
0xdbf68  ldfld    string Microsoft.Crm.Application.Pages.Tools.ViewEditor.Dialogs.AddColumns::Mode
0xdbf6d  ldnull
0xdbf6e  cgt.un
0xdbf70  ldstr    aAValidModeMust// "A valid mode must be passed to this pag"...
0xdbf75  call     void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Diagnostics.Debug::AssertEx(bool, string)
0xdbf7a  ldarg.0
0xdbf7b  ldfld    string Microsoft.Crm.Application.Pages.Tools.ViewEditor.Dialogs.AddColumns::Mode
0xdbf80  brfalse.s loc_DBF8F
0xdbf82  ldarg.0
0xdbf83  ldfld    string Microsoft.Crm.Application.Pages.Tools.ViewEditor.Dialogs.AddColumns::Mode
0xdbf88  callvirt instance int32 [mscorlib]System.String::get_Length()
0xdbf8d  brtrue.s loc_DBF9A
0xdbf8f  ldarg.0
0xdbf90  ldstr    aViewaddcol// "viewaddcol"
0xdbf95  stfld    string Microsoft.Crm.Application.Pages.Tools.ViewEditor.Dialogs.AddColumns::Mode
0xdbf9a  ldarg.0
0xdbf9b  ldarg.0
0xdbf9c  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0xdbfa1  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0xdbfa6  ldstr    aReadonly_1// "readOnly"
0xdbfab  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0xdbfb0  stfld    string Microsoft.Crm.Application.Pages.Tools.ViewEditor.Dialogs.AddColumns::ReadOnly
0xdbfb5  ldarg.0
0xdbfb6  ldfld    string Microsoft.Crm.Application.Pages.Tools.ViewEditor.Dialogs.AddColumns::ReadOnly
0xdbfbb  brtrue.s loc_DBFC8
0xdbfbd  ldarg.0
0xdbfbe  ldstr    aFalse// "false"
0xdbfc3  stfld    string Microsoft.Crm.Application.Pages.Tools.ViewEditor.Dialogs.AddColumns::ReadOnly
0xdbfc8  ldarg.0
0xdbfc9  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0xdbfce  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0xdbfd3  ldstr    aMaxcolumns// "maxcolumns"
0xdbfd8  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0xdbfdd  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0xdbfe2  brtrue.s loc_DC009
0xdbfe4  ldarg.0
0xdbfe5  ldarg.0
0xdbfe6  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0xdbfeb  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0xdbff0  ldstr    aMaxcolumns// "maxcolumns"
0xdbff5  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0xdbffa  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xdbfff  call     int32 [mscorlib]System.Int32::Parse(string, class [mscorlib]System.IFormatProvider)
0xdc004  stfld    int32 Microsoft.Crm.Application.Pages.Tools.ViewEditor.Dialogs.AddColumns::MaxSelectedColumns
0xdc009  ret
```
