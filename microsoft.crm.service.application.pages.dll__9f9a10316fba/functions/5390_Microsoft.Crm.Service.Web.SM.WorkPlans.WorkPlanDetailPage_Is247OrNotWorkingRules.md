# Microsoft.Crm.Service.Web.SM.WorkPlans.WorkPlanDetailPage::Is247OrNotWorkingRules

- ea: `0x5390`
- end: `0x5421`
- name: `Microsoft.Crm.Service.Web.SM.WorkPlans.WorkPlanDetailPage::Is247OrNotWorkingRules`
- size: `145`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x5390`
- `0x5430`
- `0x5680`

## pseudocode

```c

```

## disassembly

```asm
0x5390  ldarg.0
0x5391  ldfld    string Microsoft.Crm.Service.Web.SM.WorkPlans.WorkPlanDetailPage::CalendarType
0x5396  ldstr    a1// "1"
0x539b  call     bool [mscorlib]System.String::op_Inequality(string, string)
0x53a0  brfalse.s loc_53BD
0x53a2  ldarg.0
0x53a3  ldfld    class [Microsoft.Crm.Service.Application.Components.Platform]Microsoft.Crm.Service.Application.Platform.CalendarRule Microsoft.Crm.Service.Web.SM.WorkPlans.WorkPlanDetailPage::_recurringRule
0x53a8  brtrue.s loc_53AC
0x53aa  ldc.i4.0
0x53ab  ret
0x53ac  ldstr    aNotworkingtime// "NotWorkingTimeType"
0x53b1  ldarg.0
0x53b2  ldfld    class [Microsoft.Crm.Service.Application.Components.Platform]Microsoft.Crm.Service.Application.Platform.CalendarRule Microsoft.Crm.Service.Web.SM.WorkPlans.WorkPlanDetailPage::_workingHoursRule
0x53b7  call     bool [Microsoft.Crm.Service.Application.Components.Platform]Microsoft.Crm.Service.Application.SMWorkPlans::CompareCalendarRuleTimeType(string, class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase)
0x53bc  ret
0x53bd  ldarg.0
0x53be  ldfld    class [Microsoft.Crm.Service.Application.Components.Platform]Microsoft.Crm.Service.Application.Platform.CalendarRule Microsoft.Crm.Service.Web.SM.WorkPlans.WorkPlanDetailPage::_recurringRule
0x53c3  brfalse.s loc_541F
0x53c5  ldarg.0
0x53c6  ldfld    class [Microsoft.Crm.Service.Application.Components.Platform]Microsoft.Crm.Service.Application.Platform.CalendarRule Microsoft.Crm.Service.Web.SM.WorkPlans.WorkPlanDetailPage::_recurringRule
0x53cb  call     bool Microsoft.Crm.Service.Web.SM.WorkPlans.WorkPlanDetailPage::IsRecurringRuleVaried(class [Microsoft.Crm.Service.Application.Components.Platform]Microsoft.Crm.Service.Application.Platform.CalendarRule recurringRule)
0x53d0  brtrue.s loc_541F
0x53d2  ldstr    aWorkinghoursti// "WorkingHoursTimeType"
0x53d7  ldarg.0
0x53d8  ldfld    class [Microsoft.Crm.Service.Application.Components.Platform]Microsoft.Crm.Service.Application.Platform.CalendarRule Microsoft.Crm.Service.Web.SM.WorkPlans.WorkPlanDetailPage::_workingHoursRule
0x53dd  call     bool [Microsoft.Crm.Service.Application.Components.Platform]Microsoft.Crm.Service.Application.SMWorkPlans::CompareCalendarRuleTimeType(string, class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase)
0x53e2  brfalse.s loc_541D
0x53e4  ldarg.0
0x53e5  ldfld    class [Microsoft.Crm.Service.Application.Components.Platform]Microsoft.Crm.Service.Application.Platform.CalendarRule Microsoft.Crm.Service.Web.SM.WorkPlans.WorkPlanDetailPage::_workingHoursRule
0x53ea  callvirt instance valuetype [mscorlib]System.TimeSpan [Microsoft.Crm.Service.Application.Components.Platform]Microsoft.Crm.Service.Application.Platform.CalendarRule::get_Duration()
0x53ef  stloc.0
0x53f0  ldloca.s 0
0x53f2  call     instance float64 [mscorlib]System.TimeSpan::get_TotalMinutes()
0x53f7  ldc.r8   1440.0
0x5400  bne.un.s loc_541B
0x5402  ldarg.0
0x5403  call     instance bool Microsoft.Crm.Service.Web.SM.WorkPlans.WorkPlanDetailPage::IsBreaksAvailable()
0x5408  brtrue.s loc_541B
0x540a  ldarg.0
0x540b  ldfld    class [Microsoft.Crm.Service.Application.Components.Platform]Microsoft.Crm.Service.Application.Platform.CalendarRule Microsoft.Crm.Service.Web.SM.WorkPlans.WorkPlanDetailPage::_recurringRule
0x5410  callvirt instance string [Microsoft.Crm.Service.Application.Components.Platform]Microsoft.Crm.Service.Application.Platform.CalendarRule::get_Pattern()
0x5415  call     bool [Microsoft.Crm.Service.Application.Components.Platform]Microsoft.Crm.Service.Application.SMWorkPlans::IsAllDaysInRule(string)
0x541a  ret
0x541b  ldc.i4.0
0x541c  ret
0x541d  ldc.i4.0
0x541e  ret
0x541f  ldc.i4.0
0x5420  ret
```
