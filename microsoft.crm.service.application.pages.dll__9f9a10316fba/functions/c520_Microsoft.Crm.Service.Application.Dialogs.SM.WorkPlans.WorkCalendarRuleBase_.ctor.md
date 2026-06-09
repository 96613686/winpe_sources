# Microsoft.Crm.Service.Application.Dialogs.SM.WorkPlans.WorkCalendarRuleBase::.ctor

- ea: `0xc520`
- end: `0xc553`
- name: `Microsoft.Crm.Service.Application.Dialogs.SM.WorkPlans.WorkCalendarRuleBase::.ctor`
- size: `51`
- prototype: ``
- caller_count: `3`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## callers

- `0x9cf0`
- `0xa900`
- `0xb5a0`

## pseudocode

```c

```

## disassembly

```asm
0xc520  ldarg.0
0xc521  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0xc526  stfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Service.Application.Dialogs.SM.WorkPlans.WorkCalendarRuleBase::_resourceId
0xc52b  ldarg.0
0xc52c  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0xc531  stfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Service.Application.Dialogs.SM.WorkPlans.WorkCalendarRuleBase::_calendarId
0xc536  ldarg.0
0xc537  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0xc53c  stfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Service.Application.Dialogs.SM.WorkPlans.WorkCalendarRuleBase::_calendarRuleId
0xc541  ldarg.0
0xc542  ldstr    aBc// "bc"
0xc547  stfld    string Microsoft.Crm.Service.Application.Dialogs.SM.WorkPlans.WorkCalendarRuleBase::_calendarType
0xc54c  ldarg.0
0xc54d  call     instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.DialogBase::.ctor()
0xc552  ret
```
