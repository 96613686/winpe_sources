# Microsoft.Crm.Service.Web.SM.WorkPlans.WorkPlanDetailPage::RenderEndDateArray

- ea: `0x5210`
- end: `0x52a1`
- name: `Microsoft.Crm.Service.Web.SM.WorkPlans.WorkPlanDetailPage::RenderEndDateArray`
- size: `145`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x43e0`

## callees

- `0x5160`
- `0x5210`

## pseudocode

```c

```

## disassembly

```asm
0x5210  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor()
0x5215  stloc.0
0x5216  ldc.i4.0
0x5217  stloc.1
0x5218  ldarg.0
0x5219  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Service.Web.SM.WorkPlans.WorkPlanDetailPage::_calendarId
0x521e  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x5223  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x5228  brfalse.s loc_5283
0x522a  ldarg.0
0x522b  ldfld    class [Microsoft.Crm.Service.Application.Components.Platform]Microsoft.Crm.Service.Application.Platform.Calendar Microsoft.Crm.Service.Web.SM.WorkPlans.WorkPlanDetailPage::_calendar
0x5230  callvirt instance class [mscorlib]System.Collections.Generic.IList`1<class [Microsoft.Crm.Service.Application.Components.Platform]Microsoft.Crm.Service.Application.Platform.CalendarRule> [Microsoft.Crm.Service.Application.Components.Platform]Microsoft.Crm.Service.Application.Platform.Calendar::get_CalendarRules()
0x5235  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.Crm.Service.Application.Components.Platform]Microsoft.Crm.Service.Application.Platform.CalendarRule>::GetEnumerator()
0x523a  stloc.2
0x523b  br.s     loc_526F
0x523d  ldloc.2
0x523e  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.Crm.Service.Application.Components.Platform]Microsoft.Crm.Service.Application.Platform.CalendarRule>::get_Current()
0x5243  stloc.3
0x5244  ldarg.0
0x5245  ldloc.3
0x5246  call     instance bool Microsoft.Crm.Service.Web.SM.WorkPlans.WorkPlanDetailPage::IsRuleWeeklyRecurringAndNotCurrent(class [Microsoft.Crm.Service.Application.Components.Platform]Microsoft.Crm.Service.Application.Platform.CalendarRule rule)
0x524b  brfalse.s loc_526F
0x524d  ldloc.0
0x524e  ldloc.3
0x524f  callvirt instance valuetype [mscorlib]System.DateTime [Microsoft.Crm.Service.Application.Components.Platform]Microsoft.Crm.Service.Application.Platform.CalendarRule::get_Start()
0x5254  call     string [Microsoft.Crm]Microsoft.Crm.CrmCalendarUtil::DateTimeToIsoDateTimeString(valuetype [mscorlib]System.DateTime)
0x5259  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x525e  pop
0x525f  ldloc.0
0x5260  ldstr    asc_1B134// "|"
0x5265  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x526a  pop
0x526b  ldloc.1
0x526c  ldc.i4.1
0x526d  add
0x526e  stloc.1
0x526f  ldloc.2
0x5270  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x5275  brtrue.s loc_523D
0x5277  leave.s  loc_5283
0x5279  ldloc.2
0x527a  brfalse.s loc_5282
0x527c  ldloc.2
0x527d  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x5282  endfinally
0x5283  ldloc.0
0x5284  ldarg.0
0x5285  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x528a  ldstr    aSmNoEndDate// "SM_No_End_Date"
0x528f  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x5294  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x5299  pop
0x529a  ldloc.0
0x529b  callvirt instance string [mscorlib]System.Object::ToString()
0x52a0  ret
```
