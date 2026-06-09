# Microsoft.Crm.Controls.MonthCalendar::ConfigureHeader

- ea: `0x9770`
- end: `0x97b0`
- name: `Microsoft.Crm.Controls.MonthCalendar::ConfigureHeader`
- size: `64`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x3160`
- `0x3380`
- `0x149e0`
- `0x23b60`
- `0x23f10`

## string_xrefs

- `0x9781`: `if ((Sys.Browser.agent == Sys.Browser.InternetExplorer && Sys.Browser.version < 8) || Mscrm.Utilities.isIosDevice()) {\n				var emptyDayCell = $get('emptyDayCell');\n				emptyDayCell.parentNode.removeChild(emptyDayCell);}`

## pseudocode

```c

```

## disassembly

```asm
0x9770  ldarg.0
0x9771  call     instance void Microsoft.Crm.Application.Components.UI.AppointmentCalendar::ConfigureHeader()
0x9776  ldarg.0
0x9777  call     instance class Microsoft.Crm.Controls.PageResourceManager Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x977c  ldstr    aIe7tablecalend// "IE7TableCalendarFix"
0x9781  ldstr    aIfSysBrowserAg// "if ((Sys.Browser.agent == Sys.Browser.I"...
0x9786  callvirt instance void Microsoft.Crm.Controls.PageResourceManager::SetScriptBlockForOnLoad(string key, string scriptBlock)
0x978b  ldarg.0
0x978c  call     instance class Microsoft.Crm.Controls.PageResourceManager Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x9791  ldstr    aStaticControls_17// "/_static/_controls/MonthCalendar/MonthC"...
0x9796  callvirt instance void Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string file)
0x979b  ldarg.0
0x979c  ldstr    aMscrmMonthcale// "Mscrm.MonthCalendarControl"
0x97a1  ldnull
0x97a2  ldnull
0x97a3  ldnull
0x97a4  ldarg.0
0x97a5  ldfld    string Microsoft.Crm.Controls.MonthCalendar::_innerTableId
0x97aa  callvirt instance void Microsoft.Crm.Application.Components.UI.CrmUIControlBase::RegisterClientAjaxComponent(string componentTypeName, class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> properties, class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> events, class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> references, string elementId)
0x97af  ret
```
