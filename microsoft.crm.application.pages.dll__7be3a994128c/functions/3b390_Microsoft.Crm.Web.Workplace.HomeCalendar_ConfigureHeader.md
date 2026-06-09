# Microsoft.Crm.Web.Workplace.HomeCalendar::ConfigureHeader

- ea: `0x3b390`
- end: `0x3b439`
- name: `Microsoft.Crm.Web.Workplace.HomeCalendar::ConfigureHeader`
- size: `169`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config, broker_com_uri`

## string_xrefs

- `0x3b3bc`: `/_common/styles/miniCal.css.aspx`
- `0x3b407`: `Grid.Common.Alt.SortedColumn.Down`
- `0x3b428`: `Grid.Common.Alt.SortedColumn.Up`
- `0x3b3cc`: `/_static/_common/scripts/stage.js`
- `0x3b3ec`: `/_static/_common/scripts/appoint.js`

## pseudocode

```c

```

## disassembly

```asm
0x3b390  ldarg.0
0x3b391  call     instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::ConfigureHeader()
0x3b396  ldarg.0
0x3b397  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x3b39c  ldstr    aCalendarCalend// "/calendar/calendar.css.aspx"
0x3b3a1  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0x3b3a6  ldarg.0
0x3b3a7  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x3b3ac  ldstr    aStaticCalendar// "/_static/calendar/calendar.js"
0x3b3b1  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x3b3b6  ldarg.0
0x3b3b7  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x3b3bc  ldstr    aCommonStylesMi// "/_common/styles/miniCal.css.aspx"
0x3b3c1  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0x3b3c6  ldarg.0
0x3b3c7  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x3b3cc  ldstr    aStaticCommonSc_4// "/_static/_common/scripts/stage.js"
0x3b3d1  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x3b3d6  ldarg.0
0x3b3d7  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x3b3dc  ldstr    aStaticControls// "/_static/_controls/datetime/date.js"
0x3b3e1  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x3b3e6  ldarg.0
0x3b3e7  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x3b3ec  ldstr    aStaticCommonSc_19// "/_static/_common/scripts/appoint.js"
0x3b3f1  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x3b3f6  ldarg.0
0x3b3f7  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x3b3fc  ldstr    aLocidAltColumn// "LOCID_ALT_COLUMNSORTORDER_DOWN"
0x3b401  ldarg.0
0x3b402  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x3b407  ldstr    aGridCommonAltS// "Grid.Common.Alt.SortedColumn.Down"
0x3b40c  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x3b411  ldc.i4.0
0x3b412  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x3b417  ldarg.0
0x3b418  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x3b41d  ldstr    aLocidAltColumn_0// "LOCID_ALT_COLUMNSORTORDER_UP"
0x3b422  ldarg.0
0x3b423  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x3b428  ldstr    aGridCommonAltS_0// "Grid.Common.Alt.SortedColumn.Up"
0x3b42d  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x3b432  ldc.i4.0
0x3b433  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x3b438  ret
```
