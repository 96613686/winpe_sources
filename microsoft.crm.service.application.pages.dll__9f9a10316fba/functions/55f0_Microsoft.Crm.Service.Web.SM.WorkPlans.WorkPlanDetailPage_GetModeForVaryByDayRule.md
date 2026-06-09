# Microsoft.Crm.Service.Web.SM.WorkPlans.WorkPlanDetailPage::GetModeForVaryByDayRule

- ea: `0x55f0`
- end: `0x5623`
- name: `Microsoft.Crm.Service.Web.SM.WorkPlans.WorkPlanDetailPage::GetModeForVaryByDayRule`
- size: `51`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x50f0`

## callees

- `0x55f0`
- `0x5680`

## pseudocode

```c

```

## disassembly

```asm
0x55f0  ldarg.0
0x55f1  ldfld    class [Microsoft.Crm.Service.Application.Components.Platform]Microsoft.Crm.Service.Application.Platform.CalendarRule Microsoft.Crm.Service.Web.SM.WorkPlans.WorkPlanDetailPage::_recurringRule
0x55f6  call     bool Microsoft.Crm.Service.Web.SM.WorkPlans.WorkPlanDetailPage::IsRecurringRuleVaried(class [Microsoft.Crm.Service.Application.Components.Platform]Microsoft.Crm.Service.Application.Platform.CalendarRule recurringRule)
0x55fb  brfalse.s loc_561D
0x55fd  ldarg.0
0x55fe  ldfld    class [Microsoft.Crm.Service.Application.Components.Platform]Microsoft.Crm.Service.Application.Platform.Calendar Microsoft.Crm.Service.Web.SM.WorkPlans.WorkPlanDetailPage::_calendar
0x5603  ldarg.0
0x5604  ldfld    class [Microsoft.Crm.Service.Application.Components.Platform]Microsoft.Crm.Service.Application.Platform.CalendarRule Microsoft.Crm.Service.Web.SM.WorkPlans.WorkPlanDetailPage::_recurringRule
0x5609  ldarg.1
0x560a  callvirt instance class [Microsoft.Crm.Service.Application.Components.Platform]Microsoft.Crm.Service.Application.Platform.CalendarRule [Microsoft.Crm.Service.Application.Components.Platform]Microsoft.Crm.Service.Application.Platform.Calendar::FindSubRuleCorrespondingToDay(class [Microsoft.Crm.Service.Application.Components.Platform]Microsoft.Crm.Service.Application.Platform.CalendarRule, int32)
0x560f  brtrue.s loc_5617
0x5611  ldstr    aNew// "new"
0x5616  ret
0x5617  ldstr    aEdit// "edit"
0x561c  ret
0x561d  ldstr    aNew// "new"
0x5622  ret
```
