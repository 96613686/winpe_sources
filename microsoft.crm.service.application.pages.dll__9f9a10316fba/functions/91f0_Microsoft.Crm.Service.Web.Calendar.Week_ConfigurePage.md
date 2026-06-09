# Microsoft.Crm.Service.Web.Calendar.Week::ConfigurePage

- ea: `0x91f0`
- end: `0x9242`
- name: `Microsoft.Crm.Service.Web.Calendar.Week::ConfigurePage`
- size: `82`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config, service_task, broker_com_uri`

## string_xrefs

- `0x9216`: `/_common/styles/miniCal.css.aspx`

## pseudocode

```c

```

## disassembly

```asm
0x91f0  ldarg.0
0x91f1  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x91f6  ldstr    aCalendarCalend// "/calendar/calendar.css.aspx"
0x91fb  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0x9200  ldarg.0
0x9201  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x9206  ldstr    aStaticControls_5// "/_static/_controls/datetime/date.js"
0x920b  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x9210  ldarg.0
0x9211  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x9216  ldstr    aCommonStylesMi// "/_common/styles/miniCal.css.aspx"
0x921b  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0x9220  ldarg.0
0x9221  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x9226  ldstr    aStaticCalendar// "/_static/calendar/calendar.js"
0x922b  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x9230  ldarg.0
0x9231  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x9236  ldstr    aIsflatuipage// "_ISFLATUIPAGE"
0x923b  ldc.i4.1
0x923c  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, bool)
0x9241  ret
```
