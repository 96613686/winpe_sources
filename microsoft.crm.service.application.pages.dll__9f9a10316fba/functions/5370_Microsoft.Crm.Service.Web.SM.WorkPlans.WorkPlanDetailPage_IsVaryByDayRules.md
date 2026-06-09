# Microsoft.Crm.Service.Web.SM.WorkPlans.WorkPlanDetailPage::IsVaryByDayRules

- ea: `0x5370`
- end: `0x5386`
- name: `Microsoft.Crm.Service.Web.SM.WorkPlans.WorkPlanDetailPage::IsVaryByDayRules`
- size: `22`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x54e0`

## callees

- `0x5370`
- `0x5680`

## pseudocode

```c

```

## disassembly

```asm
0x5370  ldarg.0
0x5371  ldfld    class [Microsoft.Crm.Service.Application.Components.Platform]Microsoft.Crm.Service.Application.Platform.CalendarRule Microsoft.Crm.Service.Web.SM.WorkPlans.WorkPlanDetailPage::_recurringRule
0x5376  brtrue.s loc_537A
0x5378  ldc.i4.0
0x5379  ret
0x537a  ldarg.0
0x537b  ldfld    class [Microsoft.Crm.Service.Application.Components.Platform]Microsoft.Crm.Service.Application.Platform.CalendarRule Microsoft.Crm.Service.Web.SM.WorkPlans.WorkPlanDetailPage::_recurringRule
0x5380  call     bool Microsoft.Crm.Service.Web.SM.WorkPlans.WorkPlanDetailPage::IsRecurringRuleVaried(class [Microsoft.Crm.Service.Application.Components.Platform]Microsoft.Crm.Service.Application.Platform.CalendarRule recurringRule)
0x5385  ret
```
