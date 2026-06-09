# Microsoft.Crm.Service.Application.Dialogs.SM.WorkPlans.ChangeSchedulePage::NewCalendarRule

- ea: `0x9a80`
- end: `0x9add`
- name: `Microsoft.Crm.Service.Application.Dialogs.SM.WorkPlans.ChangeSchedulePage::NewCalendarRule`
- size: `93`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x9a80`
- `0x9b90`

## pseudocode

```c

```

## disassembly

```asm
0x9a80  ldarg.0
0x9a81  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x9a86  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x9a8b  ldstr    aDate// "date"
0x9a90  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x9a95  stloc.1
0x9a96  ldloc.1
0x9a97  brfalse.s loc_9AA1
0x9a99  ldloc.1
0x9a9a  callvirt instance int32 [mscorlib]System.String::get_Length()
0x9a9f  brtrue.s loc_9AA9
0x9aa1  call     valuetype [mscorlib]System.DateTime [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.User::get_LocalDateTime()
0x9aa6  stloc.0
0x9aa7  br.s     loc_9AB5
0x9aa9  ldloc.1
0x9aaa  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x9aaf  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::Parse(string, class [mscorlib]System.IFormatProvider)
0x9ab4  stloc.0
0x9ab5  ldarg.0
0x9ab6  call     instance void Microsoft.Crm.Service.Application.Dialogs.SM.WorkPlans.ChangeSchedulePage::SetStartAndEndDatesFromCurrent()
0x9abb  ldarg.0
0x9abc  ldloca.s 0
0x9abe  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentCulture()
0x9ac3  callvirt instance class [mscorlib]System.Globalization.DateTimeFormatInfo [mscorlib]System.Globalization.CultureInfo::get_DateTimeFormat()
0x9ac8  callvirt instance string [mscorlib]System.Globalization.DateTimeFormatInfo::get_ShortDatePattern()
0x9acd  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentCulture()
0x9ad2  call     instance string [mscorlib]System.DateTime::ToString(string, class [mscorlib]System.IFormatProvider)
0x9ad7  stfld    string Microsoft.Crm.Service.Application.Dialogs.SM.WorkPlans.ChangeSchedulePage::_currentDate
0x9adc  ret
```
