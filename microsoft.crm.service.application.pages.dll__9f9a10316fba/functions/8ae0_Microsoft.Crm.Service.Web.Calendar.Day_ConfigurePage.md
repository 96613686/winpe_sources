# Microsoft.Crm.Service.Web.Calendar.Day::ConfigurePage

- ea: `0x8ae0`
- end: `0x8b32`
- name: `Microsoft.Crm.Service.Web.Calendar.Day::ConfigurePage`
- size: `82`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config, service_task, broker_com_uri`

## string_xrefs

- `0x8b06`: `/_common/styles/miniCal.css.aspx`

## pseudocode

```c

```

## disassembly

```asm
0x8ae0  ldarg.0
0x8ae1  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x8ae6  ldstr    aCalendarCalend// "/calendar/calendar.css.aspx"
0x8aeb  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0x8af0  ldarg.0
0x8af1  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x8af6  ldstr    aStaticControls_5// "/_static/_controls/datetime/date.js"
0x8afb  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x8b00  ldarg.0
0x8b01  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x8b06  ldstr    aCommonStylesMi// "/_common/styles/miniCal.css.aspx"
0x8b0b  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0x8b10  ldarg.0
0x8b11  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x8b16  ldstr    aStaticCalendar// "/_static/calendar/calendar.js"
0x8b1b  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x8b20  ldarg.0
0x8b21  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x8b26  ldstr    aIsflatuipage// "_ISFLATUIPAGE"
0x8b2b  ldc.i4.1
0x8b2c  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, bool)
0x8b31  ret
```
