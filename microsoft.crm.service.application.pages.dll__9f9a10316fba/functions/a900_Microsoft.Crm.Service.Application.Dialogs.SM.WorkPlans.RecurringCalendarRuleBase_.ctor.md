# Microsoft.Crm.Service.Application.Dialogs.SM.WorkPlans.RecurringCalendarRuleBase::.ctor

- ea: `0xa900`
- end: `0xa933`
- name: `Microsoft.Crm.Service.Application.Dialogs.SM.WorkPlans.RecurringCalendarRuleBase::.ctor`
- size: `51`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0xa2a0`
- `0xb060`

## callees

- `0xc520`

## pseudocode

```c

```

## disassembly

```asm
0xa900  ldarg.0
0xa901  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0xa906  stfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Service.Application.Dialogs.SM.WorkPlans.RecurringCalendarRuleBase::_innerCalendarId
0xa90b  ldarg.0
0xa90c  ldsfld   string [mscorlib]System.String::Empty
0xa911  stfld    string Microsoft.Crm.Service.Application.Dialogs.SM.WorkPlans.RecurringCalendarRuleBase::_recurringInstanceName
0xa916  ldarg.0
0xa917  ldsfld   string [mscorlib]System.String::Empty
0xa91c  stfld    string Microsoft.Crm.Service.Application.Dialogs.SM.WorkPlans.RecurringCalendarRuleBase::_recurrenceDetails
0xa921  ldarg.0
0xa922  ldsfld   string [mscorlib]System.String::Empty
0xa927  stfld    string Microsoft.Crm.Service.Application.Dialogs.SM.WorkPlans.RecurringCalendarRuleBase::_recurrenceFriendlyDescription
0xa92c  ldarg.0
0xa92d  call     instance void Microsoft.Crm.Service.Application.Dialogs.SM.WorkPlans.WorkCalendarRuleBase::.ctor()
0xa932  ret
```
