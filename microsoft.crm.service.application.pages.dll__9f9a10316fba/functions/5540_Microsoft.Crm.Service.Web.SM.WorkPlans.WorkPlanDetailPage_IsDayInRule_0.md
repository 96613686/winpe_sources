# Microsoft.Crm.Service.Web.SM.WorkPlans.WorkPlanDetailPage::IsDayInRule_0

- ea: `0x5540`
- end: `0x55b3`
- name: `Microsoft.Crm.Service.Web.SM.WorkPlans.WorkPlanDetailPage::IsDayInRule_0`
- size: `115`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x4fd0`
- `0x5090`

## callees

- `0x54c0`
- `0x5540`
- `0x5680`

## pseudocode

```c

```

## disassembly

```asm
0x5540  ldarg.0
0x5541  ldfld    class [Microsoft.Crm.Service.Application.Components.Platform]Microsoft.Crm.Service.Application.Platform.CalendarRule Microsoft.Crm.Service.Web.SM.WorkPlans.WorkPlanDetailPage::_recurringRule
0x5546  brfalse.s loc_55AF
0x5548  ldarg.0
0x5549  ldfld    class [Microsoft.Crm.Service.Application.Components.Platform]Microsoft.Crm.Service.Application.Platform.CalendarRule Microsoft.Crm.Service.Web.SM.WorkPlans.WorkPlanDetailPage::_recurringRule
0x554e  call     bool Microsoft.Crm.Service.Web.SM.WorkPlans.WorkPlanDetailPage::IsRecurringRuleVaried(class [Microsoft.Crm.Service.Application.Components.Platform]Microsoft.Crm.Service.Application.Platform.CalendarRule recurringRule)
0x5553  brfalse.s loc_55A0
0x5555  ldarg.0
0x5556  ldfld    class [Microsoft.Crm.Service.Application.Components.Platform]Microsoft.Crm.Service.Application.Platform.Calendar Microsoft.Crm.Service.Web.SM.WorkPlans.WorkPlanDetailPage::_calendar
0x555b  ldarg.0
0x555c  ldfld    class [Microsoft.Crm.Service.Application.Components.Platform]Microsoft.Crm.Service.Application.Platform.CalendarRule Microsoft.Crm.Service.Web.SM.WorkPlans.WorkPlanDetailPage::_recurringRule
0x5561  callvirt instance class [mscorlib]System.Collections.ArrayList [Microsoft.Crm.Service.Application.Components.Platform]Microsoft.Crm.Service.Application.Platform.Calendar::GetSubRules(class [Microsoft.Crm.Service.Application.Components.Platform]Microsoft.Crm.Service.Application.Platform.CalendarRule)
0x5566  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.ArrayList::GetEnumerator()
0x556b  stloc.0
0x556c  br.s     loc_5585
0x556e  ldloc.0
0x556f  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x5574  castclass [Microsoft.Crm.Service.Application.Components.Platform]Microsoft.Crm.Service.Application.Platform.CalendarRule
0x5579  ldarg.1
0x557a  call     bool Microsoft.Crm.Service.Web.SM.WorkPlans.WorkPlanDetailPage::IsDayInRule(class [Microsoft.Crm.Service.Application.Components.Platform]Microsoft.Crm.Service.Application.Platform.CalendarRule rule, int32 checkIndex)
0x557f  brfalse.s loc_5585
0x5581  ldc.i4.1
0x5582  stloc.1
0x5583  leave.s  loc_55B1
0x5585  ldloc.0
0x5586  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x558b  brtrue.s loc_556E
0x558d  leave.s  loc_55AD
0x558f  ldloc.0
0x5590  isinst   [mscorlib]System.IDisposable
0x5595  stloc.2
0x5596  ldloc.2
0x5597  brfalse.s loc_559F
0x5599  ldloc.2
0x559a  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x559f  endfinally
0x55a0  ldarg.0
0x55a1  ldfld    class [Microsoft.Crm.Service.Application.Components.Platform]Microsoft.Crm.Service.Application.Platform.CalendarRule Microsoft.Crm.Service.Web.SM.WorkPlans.WorkPlanDetailPage::_recurringRule
0x55a6  ldarg.1
0x55a7  call     bool Microsoft.Crm.Service.Web.SM.WorkPlans.WorkPlanDetailPage::IsDayInRule(class [Microsoft.Crm.Service.Application.Components.Platform]Microsoft.Crm.Service.Application.Platform.CalendarRule rule, int32 checkIndex)
0x55ac  ret
0x55ad  ldc.i4.0
0x55ae  ret
0x55af  ldc.i4.1
0x55b0  ret
0x55b1  ldloc.1
0x55b2  ret
```
