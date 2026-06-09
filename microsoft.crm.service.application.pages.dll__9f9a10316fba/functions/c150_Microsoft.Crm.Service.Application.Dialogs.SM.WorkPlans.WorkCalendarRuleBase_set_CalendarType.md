# Microsoft.Crm.Service.Application.Dialogs.SM.WorkPlans.WorkCalendarRuleBase::set_CalendarType

- ea: `0xc150`
- end: `0xc160`
- name: `Microsoft.Crm.Service.Application.Dialogs.SM.WorkPlans.WorkCalendarRuleBase::set_CalendarType`
- size: `16`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x9d10`
- `0xa450`

## callees

- `0xc150`

## pseudocode

```c

```

## disassembly

```asm
0xc150  ldarg.1
0xc151  brfalse.s loc_C15F
0xc153  ldarg.0
0xc154  ldarg.1
0xc155  callvirt instance string [mscorlib]System.Object::ToString()
0xc15a  stfld    string Microsoft.Crm.Service.Application.Dialogs.SM.WorkPlans.WorkCalendarRuleBase::_calendarType
0xc15f  ret
```
