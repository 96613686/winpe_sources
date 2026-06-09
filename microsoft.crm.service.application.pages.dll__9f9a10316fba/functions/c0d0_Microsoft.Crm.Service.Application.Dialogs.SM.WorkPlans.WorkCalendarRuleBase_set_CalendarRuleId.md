# Microsoft.Crm.Service.Application.Dialogs.SM.WorkPlans.WorkCalendarRuleBase::set_CalendarRuleId

- ea: `0xc0d0`
- end: `0xc0f5`
- name: `Microsoft.Crm.Service.Application.Dialogs.SM.WorkPlans.WorkCalendarRuleBase::set_CalendarRuleId`
- size: `37`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x9d10`
- `0xa450`
- `0xb0e0`

## callees

- `0xc0d0`

## pseudocode

```c

```

## disassembly

```asm
0xc0d0  ldarg.1
0xc0d1  brfalse.s loc_C0E9
0xc0d3  ldarg.1
0xc0d4  callvirt instance int32 [mscorlib]System.String::get_Length()
0xc0d9  ldc.i4.0
0xc0da  ble.s    loc_C0E9
0xc0dc  ldarg.0
0xc0dd  ldarg.1
0xc0de  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0xc0e3  stfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Service.Application.Dialogs.SM.WorkPlans.WorkCalendarRuleBase::_calendarRuleId
0xc0e8  ret
0xc0e9  ldarg.0
0xc0ea  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0xc0ef  stfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Service.Application.Dialogs.SM.WorkPlans.WorkCalendarRuleBase::_calendarRuleId
0xc0f4  ret
```
