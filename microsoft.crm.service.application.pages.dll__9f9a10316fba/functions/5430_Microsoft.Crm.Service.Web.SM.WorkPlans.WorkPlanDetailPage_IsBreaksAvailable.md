# Microsoft.Crm.Service.Web.SM.WorkPlans.WorkPlanDetailPage::IsBreaksAvailable

- ea: `0x5430`
- end: `0x54b3`
- name: `Microsoft.Crm.Service.Web.SM.WorkPlans.WorkPlanDetailPage::IsBreaksAvailable`
- size: `131`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x52b0`
- `0x5390`

## callees

- `0x5430`

## pseudocode

```c

```

## disassembly

```asm
0x5430  ldc.i4.0
0x5431  stloc.0
0x5432  ldarg.0
0x5433  ldfld    class [Microsoft.Crm.Service.Application.Components.Platform]Microsoft.Crm.Service.Application.Platform.Calendar Microsoft.Crm.Service.Web.SM.WorkPlans.WorkPlanDetailPage::_innerCalendar
0x5438  brfalse.s loc_54B1
0x543a  ldarg.0
0x543b  ldfld    class [Microsoft.Crm.Service.Application.Components.Platform]Microsoft.Crm.Service.Application.Platform.Calendar Microsoft.Crm.Service.Web.SM.WorkPlans.WorkPlanDetailPage::_innerCalendar
0x5440  callvirt instance class [mscorlib]System.Collections.Generic.IList`1<class [Microsoft.Crm.Service.Application.Components.Platform]Microsoft.Crm.Service.Application.Platform.CalendarRule> [Microsoft.Crm.Service.Application.Components.Platform]Microsoft.Crm.Service.Application.Platform.Calendar::get_CalendarRules()
0x5445  brfalse.s loc_54B1
0x5447  ldarg.0
0x5448  ldfld    class [Microsoft.Crm.Service.Application.Components.Platform]Microsoft.Crm.Service.Application.Platform.Calendar Microsoft.Crm.Service.Web.SM.WorkPlans.WorkPlanDetailPage::_innerCalendar
0x544d  callvirt instance class [mscorlib]System.Collections.Generic.IList`1<class [Microsoft.Crm.Service.Application.Components.Platform]Microsoft.Crm.Service.Application.Platform.CalendarRule> [Microsoft.Crm.Service.Application.Components.Platform]Microsoft.Crm.Service.Application.Platform.Calendar::get_CalendarRules()
0x5452  callvirt instance int32 class [mscorlib]System.Collections.Generic.ICollection`1<class [Microsoft.Crm.Service.Application.Components.Platform]Microsoft.Crm.Service.Application.Platform.CalendarRule>::get_Count()
0x5457  ldc.i4.0
0x5458  ble.s    loc_54B1
0x545a  ldarg.0
0x545b  ldfld    class [Microsoft.Crm.Service.Application.Components.Platform]Microsoft.Crm.Service.Application.Platform.Calendar Microsoft.Crm.Service.Web.SM.WorkPlans.WorkPlanDetailPage::_innerCalendar
0x5460  callvirt instance class [mscorlib]System.Collections.Generic.IList`1<class [Microsoft.Crm.Service.Application.Components.Platform]Microsoft.Crm.Service.Application.Platform.CalendarRule> [Microsoft.Crm.Service.Application.Components.Platform]Microsoft.Crm.Service.Application.Platform.Calendar::get_CalendarRules()
0x5465  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.Crm.Service.Application.Components.Platform]Microsoft.Crm.Service.Application.Platform.CalendarRule>::GetEnumerator()
0x546a  stloc.1
0x546b  br.s     loc_549D
0x546d  ldloc.1
0x546e  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.Crm.Service.Application.Components.Platform]Microsoft.Crm.Service.Application.Platform.CalendarRule>::get_Current()
0x5473  stloc.2
0x5474  ldloc.2
0x5475  brfalse.s loc_549D
0x5477  ldloc.2
0x5478  callvirt instance valuetype [Microsoft.Crm.Core.Extensions]Microsoft.Crm.Scheduling.SubCode [Microsoft.Crm.Service.Application.Components.Platform]Microsoft.Crm.Service.Application.Platform.CalendarRule::get_SubCode()
0x547d  ldc.i4.4
0x547e  bne.un.s loc_549D
0x5480  ldloc.2
0x5481  callvirt instance valuetype [mscorlib]System.TimeSpan [Microsoft.Crm.Service.Application.Components.Platform]Microsoft.Crm.Service.Application.Platform.CalendarRule::get_Duration()
0x5486  stloc.3
0x5487  ldloca.s 3
0x5489  call     instance float64 [mscorlib]System.TimeSpan::get_TotalMinutes()
0x548e  ldc.r8   0.0
0x5497  ble.un.s loc_549D
0x5499  ldc.i4.1
0x549a  stloc.0
0x549b  leave.s  loc_54B1
0x549d  ldloc.1
0x549e  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x54a3  brtrue.s loc_546D
0x54a5  leave.s  loc_54B1
0x54a7  ldloc.1
0x54a8  brfalse.s loc_54B0
0x54aa  ldloc.1
0x54ab  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x54b0  endfinally
0x54b1  ldloc.0
0x54b2  ret
```
