# Microsoft.Crm.Service.Application.Dialogs.SM.WorkPlans.WorkCalendarRuleBase::get_CalendarRuleId

- ea: `0xc090`
- end: `0xc0c3`
- name: `Microsoft.Crm.Service.Application.Dialogs.SM.WorkPlans.WorkCalendarRuleBase::get_CalendarRuleId`
- size: `51`
- prototype: ``
- caller_count: `5`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0xa270`
- `0xa450`
- `0xa7e0`
- `0xb0e0`
- `0xb260`

## callees

- `0xc090`

## pseudocode

```c

```

## disassembly

```asm
0xc090  ldarg.0
0xc091  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Service.Application.Dialogs.SM.WorkPlans.WorkCalendarRuleBase::_calendarRuleId
0xc096  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0xc09b  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0xc0a0  brtrue.s loc_C0BD
0xc0a2  ldarg.0
0xc0a3  ldflda   valuetype [mscorlib]System.Guid Microsoft.Crm.Service.Application.Dialogs.SM.WorkPlans.WorkCalendarRuleBase::_calendarRuleId
0xc0a8  ldstr    aB// "B"
0xc0ad  call     instance string [mscorlib]System.Guid::ToString(string)
0xc0b2  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xc0b7  callvirt instance string [mscorlib]System.String::ToUpper(class [mscorlib]System.Globalization.CultureInfo)
0xc0bc  ret
0xc0bd  ldsfld   string [mscorlib]System.String::Empty
0xc0c2  ret
```
