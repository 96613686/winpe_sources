# Microsoft.Crm.Service.Application.Dialogs.SM.WorkPlans.RecurringCalendarRuleBase::RetrieveRecurrenceRule

- ea: `0xa7e0`
- end: `0xa806`
- name: `Microsoft.Crm.Service.Application.Dialogs.SM.WorkPlans.RecurringCalendarRuleBase::RetrieveRecurrenceRule`
- size: `38`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0xa450`

## callees

- `0xc020`
- `0xc090`

## pseudocode

```c

```

## disassembly

```asm
0xa7e0  ldarg.0
0xa7e1  call     instance string Microsoft.Crm.Service.Application.Dialogs.SM.WorkPlans.WorkCalendarRuleBase::get_CalendarId()
0xa7e6  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0xa7eb  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xa7f0  call     class [Microsoft.Crm.Service.Application.Components.Platform]Microsoft.Crm.Service.Application.Platform.Calendar [Microsoft.Crm.Service.Application.Components.Platform]Microsoft.Crm.Service.Application.SMWorkPlans::RetrieveCalendar(valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xa7f5  ldarg.0
0xa7f6  call     instance string Microsoft.Crm.Service.Application.Dialogs.SM.WorkPlans.WorkCalendarRuleBase::get_CalendarRuleId()
0xa7fb  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0xa800  callvirt instance class [Microsoft.Crm.Service.Application.Components.Platform]Microsoft.Crm.Service.Application.Platform.CalendarRule [Microsoft.Crm.Service.Application.Components.Platform]Microsoft.Crm.Service.Application.Platform.Calendar::FindCalendarRuleById(valuetype [mscorlib]System.Guid)
0xa805  ret
```
