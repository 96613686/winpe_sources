# Microsoft.Crm.Service.Web.SM.WorkPlans.WorkPlanDetailPage::IsRuleWeeklyRecurringAndNotCurrent

- ea: `0x5160`
- end: `0x520c`
- name: `Microsoft.Crm.Service.Web.SM.WorkPlans.WorkPlanDetailPage::IsRuleWeeklyRecurringAndNotCurrent`
- size: `172`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x5210`

## callees

- `0x5160`
- `0x5680`

## pseudocode

```c

```

## disassembly

```asm
0x5160  ldarg.0
0x5161  ldfld    class [Microsoft.Crm.Service.Application.Components.Platform]Microsoft.Crm.Service.Application.Platform.CalendarRule Microsoft.Crm.Service.Web.SM.WorkPlans.WorkPlanDetailPage::_recurringRule
0x5166  brfalse  loc_5203
0x516b  ldarg.0
0x516c  ldfld    class [Microsoft.Crm.Service.Application.Components.Platform]Microsoft.Crm.Service.Application.Platform.CalendarRule Microsoft.Crm.Service.Web.SM.WorkPlans.WorkPlanDetailPage::_recurringRule
0x5171  call     bool Microsoft.Crm.Service.Web.SM.WorkPlans.WorkPlanDetailPage::IsRecurringRuleVaried(class [Microsoft.Crm.Service.Application.Components.Platform]Microsoft.Crm.Service.Application.Platform.CalendarRule recurringRule)
0x5176  brfalse.s loc_51E2
0x5178  ldarg.0
0x5179  ldfld    class [Microsoft.Crm.Service.Application.Components.Platform]Microsoft.Crm.Service.Application.Platform.Calendar Microsoft.Crm.Service.Web.SM.WorkPlans.WorkPlanDetailPage::_calendar
0x517e  ldarg.0
0x517f  ldfld    class [Microsoft.Crm.Service.Application.Components.Platform]Microsoft.Crm.Service.Application.Platform.CalendarRule Microsoft.Crm.Service.Web.SM.WorkPlans.WorkPlanDetailPage::_recurringRule
0x5184  callvirt instance class [mscorlib]System.Collections.ArrayList [Microsoft.Crm.Service.Application.Components.Platform]Microsoft.Crm.Service.Application.Platform.Calendar::GetSubRules(class [Microsoft.Crm.Service.Application.Components.Platform]Microsoft.Crm.Service.Application.Platform.CalendarRule)
0x5189  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.ArrayList::GetEnumerator()
0x518e  stloc.0
0x518f  br.s     loc_51C7
0x5191  ldloc.0
0x5192  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x5197  castclass [Microsoft.Crm.Service.Application.Components.Platform]Microsoft.Crm.Service.Application.Platform.CalendarRule
0x519c  stloc.1
0x519d  ldloc.1
0x519e  callvirt instance string [Microsoft.Crm.Service.Application.Components.Platform]Microsoft.Crm.Service.Application.Platform.CalendarRule::get_Pattern()
0x51a3  ldarg.1
0x51a4  callvirt instance string [Microsoft.Crm.Service.Application.Components.Platform]Microsoft.Crm.Service.Application.Platform.CalendarRule::get_Pattern()
0x51a9  call     bool [mscorlib]System.String::op_Equality(string, string)
0x51ae  brfalse.s loc_51C7
0x51b0  ldloc.1
0x51b1  callvirt instance valuetype [mscorlib]System.DateTime [Microsoft.Crm.Service.Application.Components.Platform]Microsoft.Crm.Service.Application.Platform.CalendarRule::get_Start()
0x51b6  ldarg.1
0x51b7  callvirt instance valuetype [mscorlib]System.DateTime [Microsoft.Crm.Service.Application.Components.Platform]Microsoft.Crm.Service.Application.Platform.CalendarRule::get_Start()
0x51bc  call     bool [mscorlib]System.DateTime::op_Equality(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTime)
0x51c1  brfalse.s loc_51C7
0x51c3  ldc.i4.0
0x51c4  stloc.2
0x51c5  leave.s  loc_520A
0x51c7  ldloc.0
0x51c8  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x51cd  brtrue.s loc_5191
0x51cf  leave.s  loc_5203
0x51d1  ldloc.0
0x51d2  isinst   [mscorlib]System.IDisposable
0x51d7  stloc.3
0x51d8  ldloc.3
0x51d9  brfalse.s loc_51E1
0x51db  ldloc.3
0x51dc  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x51e1  endfinally
0x51e2  ldarg.1
0x51e3  callvirt instance bool [Microsoft.Crm.Service.Application.Components.Platform]Microsoft.Crm.Service.Application.Platform.CalendarRule::IsRecurrenceDefined()
0x51e8  brfalse.s loc_5201
0x51ea  ldarg.1
0x51eb  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Service.Application.Components.Platform]Microsoft.Crm.Service.Application.Platform.CalendarRule::get_CalendarRuleId()
0x51f0  ldarg.0
0x51f1  ldfld    class [Microsoft.Crm.Service.Application.Components.Platform]Microsoft.Crm.Service.Application.Platform.CalendarRule Microsoft.Crm.Service.Web.SM.WorkPlans.WorkPlanDetailPage::_recurringRule
0x51f6  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Service.Application.Components.Platform]Microsoft.Crm.Service.Application.Platform.CalendarRule::get_CalendarRuleId()
0x51fb  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x5200  ret
0x5201  ldc.i4.0
0x5202  ret
0x5203  ldarg.1
0x5204  callvirt instance bool [Microsoft.Crm.Service.Application.Components.Platform]Microsoft.Crm.Service.Application.Platform.CalendarRule::IsRecurrenceDefined()
0x5209  ret
0x520a  ldloc.2
0x520b  ret
```
