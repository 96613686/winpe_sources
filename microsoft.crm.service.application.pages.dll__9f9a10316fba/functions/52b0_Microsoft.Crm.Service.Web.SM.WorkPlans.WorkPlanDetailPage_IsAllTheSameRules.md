# Microsoft.Crm.Service.Web.SM.WorkPlans.WorkPlanDetailPage::IsAllTheSameRules

- ea: `0x52b0`
- end: `0x536b`
- name: `Microsoft.Crm.Service.Web.SM.WorkPlans.WorkPlanDetailPage::IsAllTheSameRules`
- size: `187`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x54e0`

## callees

- `0x52b0`
- `0x5430`
- `0x5680`

## pseudocode

```c

```

## disassembly

```asm
0x52b0  ldarg.0
0x52b1  ldfld    class [Microsoft.Crm.Service.Application.Components.Platform]Microsoft.Crm.Service.Application.Platform.CalendarRule Microsoft.Crm.Service.Web.SM.WorkPlans.WorkPlanDetailPage::_recurringRule
0x52b6  brtrue.s loc_52BA
0x52b8  ldc.i4.1
0x52b9  ret
0x52ba  ldarg.0
0x52bb  ldfld    string Microsoft.Crm.Service.Web.SM.WorkPlans.WorkPlanDetailPage::CalendarType
0x52c0  ldstr    a1// "1"
0x52c5  call     bool [mscorlib]System.String::op_Inequality(string, string)
0x52ca  brfalse.s loc_52EC
0x52cc  ldarg.0
0x52cd  ldfld    class [Microsoft.Crm.Service.Application.Components.Platform]Microsoft.Crm.Service.Application.Platform.CalendarRule Microsoft.Crm.Service.Web.SM.WorkPlans.WorkPlanDetailPage::_recurringRule
0x52d2  call     bool Microsoft.Crm.Service.Web.SM.WorkPlans.WorkPlanDetailPage::IsRecurringRuleVaried(class [Microsoft.Crm.Service.Application.Components.Platform]Microsoft.Crm.Service.Application.Platform.CalendarRule recurringRule)
0x52d7  brtrue.s loc_52EA
0x52d9  ldstr    aWorkinghoursti// "WorkingHoursTimeType"
0x52de  ldarg.0
0x52df  ldfld    class [Microsoft.Crm.Service.Application.Components.Platform]Microsoft.Crm.Service.Application.Platform.CalendarRule Microsoft.Crm.Service.Web.SM.WorkPlans.WorkPlanDetailPage::_workingHoursRule
0x52e4  call     bool [Microsoft.Crm.Service.Application.Components.Platform]Microsoft.Crm.Service.Application.SMWorkPlans::CompareCalendarRuleTimeType(string, class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase)
0x52e9  ret
0x52ea  ldc.i4.0
0x52eb  ret
0x52ec  ldarg.0
0x52ed  ldfld    class [Microsoft.Crm.Service.Application.Components.Platform]Microsoft.Crm.Service.Application.Platform.CalendarRule Microsoft.Crm.Service.Web.SM.WorkPlans.WorkPlanDetailPage::_recurringRule
0x52f2  call     bool Microsoft.Crm.Service.Web.SM.WorkPlans.WorkPlanDetailPage::IsRecurringRuleVaried(class [Microsoft.Crm.Service.Application.Components.Platform]Microsoft.Crm.Service.Application.Platform.CalendarRule recurringRule)
0x52f7  brtrue.s loc_5369
0x52f9  ldstr    aWorkinghoursti// "WorkingHoursTimeType"
0x52fe  ldarg.0
0x52ff  ldfld    class [Microsoft.Crm.Service.Application.Components.Platform]Microsoft.Crm.Service.Application.Platform.CalendarRule Microsoft.Crm.Service.Web.SM.WorkPlans.WorkPlanDetailPage::_workingHoursRule
0x5304  call     bool [Microsoft.Crm.Service.Application.Components.Platform]Microsoft.Crm.Service.Application.SMWorkPlans::CompareCalendarRuleTimeType(string, class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase)
0x5309  brfalse.s loc_5367
0x530b  ldarg.0
0x530c  ldfld    class [Microsoft.Crm.Service.Application.Components.Platform]Microsoft.Crm.Service.Application.Platform.CalendarRule Microsoft.Crm.Service.Web.SM.WorkPlans.WorkPlanDetailPage::_workingHoursRule
0x5311  callvirt instance valuetype [mscorlib]System.TimeSpan [Microsoft.Crm.Service.Application.Components.Platform]Microsoft.Crm.Service.Application.Platform.CalendarRule::get_Duration()
0x5316  stloc.0
0x5317  ldloca.s 0
0x5319  call     instance float64 [mscorlib]System.TimeSpan::get_TotalMinutes()
0x531e  ldc.r8   1440.0
0x5327  bne.un.s loc_5343
0x5329  ldarg.0
0x532a  call     instance bool Microsoft.Crm.Service.Web.SM.WorkPlans.WorkPlanDetailPage::IsBreaksAvailable()
0x532f  brtrue.s loc_5365
0x5331  ldarg.0
0x5332  ldfld    class [Microsoft.Crm.Service.Application.Components.Platform]Microsoft.Crm.Service.Application.Platform.CalendarRule Microsoft.Crm.Service.Web.SM.WorkPlans.WorkPlanDetailPage::_recurringRule
0x5337  callvirt instance string [Microsoft.Crm.Service.Application.Components.Platform]Microsoft.Crm.Service.Application.Platform.CalendarRule::get_Pattern()
0x533c  call     bool [Microsoft.Crm.Service.Application.Components.Platform]Microsoft.Crm.Service.Application.SMWorkPlans::IsAllDaysInRule(string)
0x5341  brfalse.s loc_5365
0x5343  ldarg.0
0x5344  ldfld    class [Microsoft.Crm.Service.Application.Components.Platform]Microsoft.Crm.Service.Application.Platform.CalendarRule Microsoft.Crm.Service.Web.SM.WorkPlans.WorkPlanDetailPage::_workingHoursRule
0x5349  callvirt instance valuetype [mscorlib]System.TimeSpan [Microsoft.Crm.Service.Application.Components.Platform]Microsoft.Crm.Service.Application.Platform.CalendarRule::get_Duration()
0x534e  stloc.0
0x534f  ldloca.s 0
0x5351  call     instance float64 [mscorlib]System.TimeSpan::get_TotalMinutes()
0x5356  ldc.r8   1440.0
0x535f  ceq
0x5361  ldc.i4.0
0x5362  ceq
0x5364  ret
0x5365  ldc.i4.1
0x5366  ret
0x5367  ldc.i4.0
0x5368  ret
0x5369  ldc.i4.0
0x536a  ret
```
