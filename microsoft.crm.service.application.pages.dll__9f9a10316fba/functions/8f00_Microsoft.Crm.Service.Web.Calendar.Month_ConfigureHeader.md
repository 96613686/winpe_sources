# Microsoft.Crm.Service.Web.Calendar.Month::ConfigureHeader

- ea: `0x8f00`
- end: `0x8f47`
- name: `Microsoft.Crm.Service.Web.Calendar.Month::ConfigureHeader`
- size: `71`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config, service_task, broker_com_uri`

## string_xrefs

- `0x8f2c`: `/_common/styles/miniCal.css.aspx`

## pseudocode

```c

```

## disassembly

```asm
0x8f00  ldarg.0
0x8f01  call     instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::ConfigureHeader()
0x8f06  ldarg.0
0x8f07  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x8f0c  ldstr    aControlsMonthc// "/_controls/monthcalendar/monthcalendar."...
0x8f11  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0x8f16  ldarg.0
0x8f17  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x8f1c  ldstr    aStaticControls_5// "/_static/_controls/datetime/date.js"
0x8f21  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x8f26  ldarg.0
0x8f27  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x8f2c  ldstr    aCommonStylesMi// "/_common/styles/miniCal.css.aspx"
0x8f31  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0x8f36  ldarg.0
0x8f37  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x8f3c  ldstr    aStaticCalendar// "/_static/calendar/calendar.js"
0x8f41  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x8f46  ret
```
