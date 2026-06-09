# Microsoft.Crm.Web.Tools.Views.ViewManagerPage::ConfigureHeader

- ea: `0x81be0`
- end: `0x81e69`
- name: `Microsoft.Crm.Web.Tools.Views.ViewManagerPage::ConfigureHeader`
- size: `649`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x81ba0`
- `0x81be0`

## string_xrefs

- `0x81e04`: `Grid.Common.Alt.SortedColumn.Down`
- `0x81e25`: `Grid.Common.Alt.SortedColumn.Up`
- `0x81bec`: `/_nav/taskbox.css.aspx`
- `0x81c2c`: `/_static/_common/scripts/formevt.js`
- `0x81c8e`: `LOCID_VIEWEDITOR_REMOVECOLUMN`
- `0x81d5f`: `Web.Tools.ViewEditor.Errors.CannotRemoveRequiredColumn`

## pseudocode

```c

```

## disassembly

```asm
0x81be0  ldarg.0
0x81be1  call     instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::ConfigureHeader()
0x81be6  ldarg.0
0x81be7  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x81bec  ldstr    aNavTaskboxCssA// "/_nav/taskbox.css.aspx"
0x81bf1  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0x81bf6  ldarg.0
0x81bf7  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x81bfc  ldstr    aStaticToolsVie// "/_static/tools/vieweditor/scripts/objec"...
0x81c01  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x81c06  ldarg.0
0x81c07  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x81c0c  ldstr    aStaticToolsVie_0// "/_static/tools/vieweditor/scripts/util."...
0x81c11  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x81c16  ldarg.0
0x81c17  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x81c1c  ldstr    aStaticToolsVie_1// "/_static/tools/vieweditor/scripts/viewm"...
0x81c21  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x81c26  ldarg.0
0x81c27  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x81c2c  ldstr    aStaticCommonSc_23// "/_static/_common/scripts/formevt.js"
0x81c31  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x81c36  ldarg.0
0x81c37  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x81c3c  ldstr    aStaticToolsDep// "/_static/tools/dependency/scripts/depen"...
0x81c41  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x81c46  ldarg.0
0x81c47  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x81c4c  ldstr    aLocidViewedito// "LOCID_VIEWEDITOR_BASICINFO"
0x81c51  ldarg.0
0x81c52  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x81c57  ldstr    aWebToolsViewed_6// "Web.Tools.ViewEditor.scripts.viewManage"...
0x81c5c  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x81c61  ldc.i4.0
0x81c62  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x81c67  ldarg.0
0x81c68  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x81c6d  ldstr    aLocidViewedito_0// "LOCID_VIEWEDITOR_RMSELECTCOLUMN"
0x81c72  ldarg.0
0x81c73  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x81c78  ldstr    aWebToolsViewed_7// "Web.Tools.ViewEditor.scripts.viewManage"...
0x81c7d  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x81c82  ldc.i4.0
0x81c83  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x81c88  ldarg.0
0x81c89  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x81c8e  ldstr    aLocidViewedito_1// "LOCID_VIEWEDITOR_REMOVECOLUMN"
0x81c93  ldarg.0
0x81c94  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x81c99  ldstr    aWebToolsViewed_8// "Web.Tools.ViewEditor.scripts.viewManage"...
0x81c9e  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x81ca3  ldc.i4.0
0x81ca4  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x81ca9  ldarg.0
0x81caa  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x81caf  ldstr    aLocidViewedito_2// "LOCID_VIEWEDITOR_QFINVALIDFIELDS"
0x81cb4  ldarg.0
0x81cb5  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x81cba  ldstr    aWebToolsViewed_9// "Web.Tools.ViewEditor.Scripts.viewManage"...
0x81cbf  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x81cc4  ldc.i4.0
0x81cc5  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x81cca  ldarg.0
0x81ccb  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x81cd0  ldstr    aLocidViewedito_3// "LOCID_VIEWEDITOR_EDSELECTCOLUMN"
0x81cd5  ldarg.0
0x81cd6  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x81cdb  ldstr    aWebToolsViewed_10// "Web.Tools.ViewEditor.scripts.viewManage"...
0x81ce0  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x81ce5  ldc.i4.0
0x81ce6  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x81ceb  ldarg.0
0x81cec  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x81cf1  ldstr    aLocidViewedito_4// "LOCID_VIEWEDITOR_INVALIDCOLUMN"
0x81cf6  ldarg.0
0x81cf7  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x81cfc  ldstr    aWebToolsViewed_11// "Web.Tools.ViewEditor.scripts.viewManage"...
0x81d01  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x81d06  ldc.i4.0
0x81d07  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x81d0c  ldarg.0
0x81d0d  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x81d12  ldstr    aLocidViewedito_5// "LOCID_VIEWEDITOR_FILTERCRITERIA"
0x81d17  ldarg.0
0x81d18  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x81d1d  ldstr    aWebToolsViewed_12// "Web.Tools.ViewEditor.scripts.viewManage"...
0x81d22  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x81d27  ldc.i4.0
0x81d28  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x81d2d  ldarg.0
0x81d2e  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x81d33  ldstr    aLocidViewedito_6// "LOCID_VIEWEDITOR_MVSELECTCOLUMN"
0x81d38  ldarg.0
0x81d39  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x81d3e  ldstr    aWebToolsViewed_13// "Web.Tools.ViewEditor.scripts.viewManage"...
0x81d43  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x81d48  ldc.i4.0
0x81d49  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x81d4e  ldarg.0
0x81d4f  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x81d54  ldstr    aLocidViewedito_7// "LOCID_VIEWEDITOR_CANTRMREQCOL"
0x81d59  ldarg.0
0x81d5a  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x81d5f  ldstr    aWebToolsViewed_14// "Web.Tools.ViewEditor.Errors.CannotRemov"...
0x81d64  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x81d69  ldc.i4.0
0x81d6a  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x81d6f  ldarg.0
0x81d70  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x81d75  ldstr    aLocidViewedito_8// "LOCID_VIEWEDITOR_NOSRTBLFIELDS"
0x81d7a  ldarg.0
0x81d7b  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x81d80  ldstr    aWebToolsViewed_15// "Web.Tools.ViewEditor.Errors.NoSortableF"...
0x81d85  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x81d8a  ldc.i4.0
0x81d8b  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x81d90  ldarg.0
0x81d91  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x81d96  ldstr    aLocidViewedito_9// "LOCID_VIEWEDITOR_NOFIELDS"
0x81d9b  ldarg.0
0x81d9c  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x81da1  ldstr    aWebToolsViewed_16// "Web.Tools.ViewEditor.Errors.NoFieldsInV"...
0x81da6  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x81dab  ldc.i4.0
0x81dac  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x81db1  ldarg.0
0x81db2  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x81db7  ldstr    aLocidViewedito_10// "LOCID_VIEWEDITOR_COLTOOLTIP"
0x81dbc  ldarg.0
0x81dbd  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x81dc2  ldstr    aWebToolsViewed_17// "Web.Tools.ViewEditor.Tooltips.Column"
0x81dc7  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x81dcc  ldc.i4.0
0x81dcd  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x81dd2  ldarg.0
0x81dd3  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x81dd8  ldstr    aLocidViewedito_11// "LOCID_VIEWEDITOR_COLERR_TOOLTIP"
0x81ddd  ldarg.0
0x81dde  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x81de3  ldstr    aWebToolsViewed_18// "Web.Tools.ViewEditor.Tooltips.ColumnErr"...
0x81de8  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x81ded  ldc.i4.0
0x81dee  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x81df3  ldarg.0
0x81df4  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x81df9  ldstr    aLocidAltColumn// "LOCID_ALT_COLUMNSORTORDER_DOWN"
0x81dfe  ldarg.0
0x81dff  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x81e04  ldstr    aGridCommonAltS// "Grid.Common.Alt.SortedColumn.Down"
0x81e09  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x81e0e  ldc.i4.0
0x81e0f  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x81e14  ldarg.0
0x81e15  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x81e1a  ldstr    aLocidAltColumn_0// "LOCID_ALT_COLUMNSORTORDER_UP"
0x81e1f  ldarg.0
0x81e20  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x81e25  ldstr    aGridCommonAltS_0// "Grid.Common.Alt.SortedColumn.Up"
0x81e2a  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x81e2f  ldc.i4.0
0x81e30  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x81e35  ldarg.0
0x81e36  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x81e3b  ldstr    aBfromexportexc// "_bFromExportExcel"
0x81e40  ldarg.0
0x81e41  call     instance bool Microsoft.Crm.Web.Tools.Views.ViewManagerPage::get_IsFromExportToExcelEditor()
0x81e46  brtrue.s loc_81E4B
0x81e48  ldc.i4.0
0x81e49  br.s     loc_81E4C
0x81e4b  ldc.i4.1
0x81e4c  conv.i8
0x81e4d  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, int64)
0x81e52  ldarg.0
0x81e53  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x81e58  ldstr    aIdefaultgridco// "_iDefaultGridColumnWidth"
0x81e5d  ldc.i4   0x12C
0x81e62  conv.i8
0x81e63  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, int64)
0x81e68  ret
```
