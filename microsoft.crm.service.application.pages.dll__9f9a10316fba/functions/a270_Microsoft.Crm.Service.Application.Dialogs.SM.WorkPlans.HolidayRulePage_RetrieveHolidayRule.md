# Microsoft.Crm.Service.Application.Dialogs.SM.WorkPlans.HolidayRulePage::RetrieveHolidayRule

- ea: `0xa270`
- end: `0xa296`
- name: `Microsoft.Crm.Service.Application.Dialogs.SM.WorkPlans.HolidayRulePage::RetrieveHolidayRule`
- size: `38`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0xa170`

## callees

- `0xc020`
- `0xc090`

## pseudocode

```c

```

## disassembly

```asm
0xa270  ldarg.0
0xa271  call     instance string Microsoft.Crm.Service.Application.Dialogs.SM.WorkPlans.WorkCalendarRuleBase::get_CalendarId()
0xa276  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0xa27b  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xa280  call     class [Microsoft.Crm.Service.Application.Components.Platform]Microsoft.Crm.Service.Application.Platform.Calendar [Microsoft.Crm.Service.Application.Components.Platform]Microsoft.Crm.Service.Application.SMWorkPlans::RetrieveCalendar(valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xa285  ldarg.0
0xa286  call     instance string Microsoft.Crm.Service.Application.Dialogs.SM.WorkPlans.WorkCalendarRuleBase::get_CalendarRuleId()
0xa28b  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0xa290  callvirt instance class [Microsoft.Crm.Service.Application.Components.Platform]Microsoft.Crm.Service.Application.Platform.CalendarRule [Microsoft.Crm.Service.Application.Components.Platform]Microsoft.Crm.Service.Application.Platform.Calendar::FindCalendarRuleById(valuetype [mscorlib]System.Guid)
0xa295  ret
```
