# Microsoft.Crm.Service.Application.Dialogs.SM.WorkPlans.WorkCalendarRuleBase::get_CalendarId

- ea: `0xc020`
- end: `0xc053`
- name: `Microsoft.Crm.Service.Application.Dialogs.SM.WorkPlans.WorkCalendarRuleBase::get_CalendarId`
- size: `51`
- prototype: ``
- caller_count: `5`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x9b90`
- `0xa270`
- `0xa450`
- `0xa7e0`
- `0xb500`

## callees

- `0xc020`

## pseudocode

```c

```

## disassembly

```asm
0xc020  ldarg.0
0xc021  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Service.Application.Dialogs.SM.WorkPlans.WorkCalendarRuleBase::_calendarId
0xc026  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0xc02b  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0xc030  brtrue.s loc_C04D
0xc032  ldarg.0
0xc033  ldflda   valuetype [mscorlib]System.Guid Microsoft.Crm.Service.Application.Dialogs.SM.WorkPlans.WorkCalendarRuleBase::_calendarId
0xc038  ldstr    aB// "B"
0xc03d  call     instance string [mscorlib]System.Guid::ToString(string)
0xc042  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xc047  callvirt instance string [mscorlib]System.String::ToUpper(class [mscorlib]System.Globalization.CultureInfo)
0xc04c  ret
0xc04d  ldsfld   string [mscorlib]System.String::Empty
0xc052  ret
```
