# Microsoft.Crm.Service.Application.Dialogs.SM.WorkPlans.WorkCalendarRuleBase::set_CalendarId

- ea: `0xc060`
- end: `0xc085`
- name: `Microsoft.Crm.Service.Application.Dialogs.SM.WorkPlans.WorkCalendarRuleBase::set_CalendarId`
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

- `0xc060`

## pseudocode

```c

```

## disassembly

```asm
0xc060  ldarg.1
0xc061  brfalse.s loc_C079
0xc063  ldarg.1
0xc064  callvirt instance int32 [mscorlib]System.String::get_Length()
0xc069  ldc.i4.0
0xc06a  ble.s    loc_C079
0xc06c  ldarg.0
0xc06d  ldarg.1
0xc06e  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0xc073  stfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Service.Application.Dialogs.SM.WorkPlans.WorkCalendarRuleBase::_calendarId
0xc078  ret
0xc079  ldarg.0
0xc07a  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0xc07f  stfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Service.Application.Dialogs.SM.WorkPlans.WorkCalendarRuleBase::_calendarId
0xc084  ret
```
