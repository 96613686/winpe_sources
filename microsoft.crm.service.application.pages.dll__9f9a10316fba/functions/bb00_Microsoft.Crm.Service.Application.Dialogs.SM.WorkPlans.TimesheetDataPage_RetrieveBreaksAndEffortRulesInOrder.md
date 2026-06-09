# Microsoft.Crm.Service.Application.Dialogs.SM.WorkPlans.TimesheetDataPage::RetrieveBreaksAndEffortRulesInOrder

- ea: `0xbb00`
- end: `0xbb70`
- name: `Microsoft.Crm.Service.Application.Dialogs.SM.WorkPlans.TimesheetDataPage::RetrieveBreaksAndEffortRulesInOrder`
- size: `112`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0xb6b0`

## callees

- `0xbb00`
- `0xbb70`
- `0x142e0`

## pseudocode

```c

```

## disassembly

```asm
0xbb00  newobj   instance void [mscorlib]System.Collections.ArrayList::.ctor()
0xbb05  stloc.0
0xbb06  ldarg.1
0xbb07  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xbb0c  call     class [Microsoft.Crm.Service.Application.Components.Platform]Microsoft.Crm.Service.Application.Platform.Calendar [Microsoft.Crm.Service.Application.Components.Platform]Microsoft.Crm.Service.Application.SMWorkPlans::RetrieveCalendar(valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xbb11  callvirt instance class [mscorlib]System.Collections.Generic.IList`1<class [Microsoft.Crm.Service.Application.Components.Platform]Microsoft.Crm.Service.Application.Platform.CalendarRule> [Microsoft.Crm.Service.Application.Components.Platform]Microsoft.Crm.Service.Application.Platform.Calendar::get_CalendarRules()
0xbb16  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.Crm.Service.Application.Components.Platform]Microsoft.Crm.Service.Application.Platform.CalendarRule>::GetEnumerator()
0xbb1b  stloc.1
0xbb1c  br.s     loc_BB47
0xbb1e  ldloc.1
0xbb1f  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.Crm.Service.Application.Components.Platform]Microsoft.Crm.Service.Application.Platform.CalendarRule>::get_Current()
0xbb24  stloc.2
0xbb25  ldstr    aBreaktimetype// "BreakTimeType"
0xbb2a  ldloc.2
0xbb2b  call     bool [Microsoft.Crm.Service.Application.Components.Platform]Microsoft.Crm.Service.Application.SMWorkPlans::CompareCalendarRuleTimeType(string, class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase)
0xbb30  brtrue.s loc_BB3F
0xbb32  ldstr    aResourcecapaci// "ResourceCapacityTimeType"
0xbb37  ldloc.2
0xbb38  call     bool [Microsoft.Crm.Service.Application.Components.Platform]Microsoft.Crm.Service.Application.SMWorkPlans::CompareCalendarRuleTimeType(string, class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase)
0xbb3d  brfalse.s loc_BB47
0xbb3f  ldloc.0
0xbb40  ldloc.2
0xbb41  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0xbb46  pop
0xbb47  ldloc.1
0xbb48  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0xbb4d  brtrue.s loc_BB1E
0xbb4f  leave.s  loc_BB5B
0xbb51  ldloc.1
0xbb52  brfalse.s loc_BB5A
0xbb54  ldloc.1
0xbb55  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xbb5a  endfinally
0xbb5b  ldloc.0
0xbb5c  ldc.i4.0
0xbb5d  newobj   instance void TimeSpanComparer::.ctor(bool direction)
0xbb62  callvirt instance void [mscorlib]System.Collections.ArrayList::Sort(class [mscorlib]System.Collections.IComparer)
0xbb67  ldarg.0
0xbb68  ldarg.2
0xbb69  ldloc.0
0xbb6a  call     instance string Microsoft.Crm.Service.Application.Dialogs.SM.WorkPlans.TimesheetDataPage::GenerateTimeSheetXml(class [Microsoft.Crm.Service.Application.Components.Platform]Microsoft.Crm.Service.Application.Platform.CalendarRule workingHoursRule, class [mscorlib]System.Collections.ArrayList rules)
0xbb6f  ret
```
