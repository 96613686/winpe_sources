# Microsoft.Crm.Application.Components.UI.MocaDateTimeUI::RenderTimeScroller

- ea: `0x16d80`
- end: `0x16dd3`
- name: `Microsoft.Crm.Application.Components.UI.MocaDateTimeUI::RenderTimeScroller`
- size: `83`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x16d40`

## callees

- `0x16d80`
- `0x16e60`

## string_xrefs

- `0x16d8d`: `hourComponent`
- `0x16d99`: `minuteComponent`
- `0x16dbd`: `periodComponent`

## pseudocode

```c

```

## disassembly

```asm
0x16d80  ldarg.1
0x16d81  ldstr    aDivClassScroll// "<div class=\"scroller timeScroller\">"
0x16d86  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x16d8b  ldarg.0
0x16d8c  ldarg.1
0x16d8d  ldstr    aHourcomponent// "hourComponent"
0x16d92  call     instance void Microsoft.Crm.Application.Components.UI.MocaDateTimeUI::RenderScrollerComponent(class [System.Web]System.Web.UI.HtmlTextWriter writer, string componentClass)
0x16d97  ldarg.0
0x16d98  ldarg.1
0x16d99  ldstr    aMinutecomponen// "minuteComponent"
0x16d9e  call     instance void Microsoft.Crm.Application.Components.UI.MocaDateTimeUI::RenderScrollerComponent(class [System.Web]System.Web.UI.HtmlTextWriter writer, string componentClass)
0x16da3  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentCulture()
0x16da8  callvirt instance class [mscorlib]System.Globalization.DateTimeFormatInfo [mscorlib]System.Globalization.CultureInfo::get_DateTimeFormat()
0x16dad  callvirt instance string [mscorlib]System.Globalization.DateTimeFormatInfo::get_ShortTimePattern()
0x16db2  ldc.i4.s 0x68
0x16db4  call     T0x2B00001F
0x16db9  brfalse.s loc_16DC7
0x16dbb  ldarg.0
0x16dbc  ldarg.1
0x16dbd  ldstr    aPeriodcomponen// "periodComponent"
0x16dc2  call     instance void Microsoft.Crm.Application.Components.UI.MocaDateTimeUI::RenderScrollerComponent(class [System.Web]System.Web.UI.HtmlTextWriter writer, string componentClass)
0x16dc7  ldarg.1
0x16dc8  ldstr    aDiv// "</div>"
0x16dcd  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x16dd2  ret
```
