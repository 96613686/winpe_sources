# Microsoft.Crm.Service.Application.Dialogs.SM.WorkPlans.RecurringCalendarRuleBase::get_InnerCalendarId

- ea: `0xa300`
- end: `0xa333`
- name: `Microsoft.Crm.Service.Application.Dialogs.SM.WorkPlans.RecurringCalendarRuleBase::get_InnerCalendarId`
- size: `51`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0xb030`

## callees

- `0xa300`

## pseudocode

```c

```

## disassembly

```asm
0xa300  ldarg.0
0xa301  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Service.Application.Dialogs.SM.WorkPlans.RecurringCalendarRuleBase::_innerCalendarId
0xa306  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0xa30b  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0xa310  brtrue.s loc_A32D
0xa312  ldarg.0
0xa313  ldflda   valuetype [mscorlib]System.Guid Microsoft.Crm.Service.Application.Dialogs.SM.WorkPlans.RecurringCalendarRuleBase::_innerCalendarId
0xa318  ldstr    aB// "B"
0xa31d  call     instance string [mscorlib]System.Guid::ToString(string)
0xa322  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xa327  callvirt instance string [mscorlib]System.String::ToUpper(class [mscorlib]System.Globalization.CultureInfo)
0xa32c  ret
0xa32d  ldsfld   string [mscorlib]System.String::Empty
0xa332  ret
```
