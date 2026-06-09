# Microsoft.Crm.Service.Application.Dialogs.SM.WorkPlans.TimesheetDataPage::GenerateTimeSheetXml

- ea: `0xbb70`
- end: `0xbcc8`
- name: `Microsoft.Crm.Service.Application.Dialogs.SM.WorkPlans.TimesheetDataPage::GenerateTimeSheetXml`
- size: `344`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0xbb00`

## callees

- `0xbb70`
- `0xbcd0`
- `0xbdf0`
- `0xbef0`

## pseudocode

```c

```

## disassembly

```asm
0xbb70  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor()
0xbb75  stloc.0
0xbb76  ldloc.0
0xbb77  ldstr    aRules// "<rules>"
0xbb7c  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0xbb81  pop
0xbb82  ldc.i4.0
0xbb83  stloc.1
0xbb84  ldnull
0xbb85  stloc.2
0xbb86  ldarg.2
0xbb87  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.ArrayList::GetEnumerator()
0xbb8c  stloc.3
0xbb8d  br       loc_BC41
0xbb92  ldloc.3
0xbb93  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0xbb98  castclass [Microsoft.Crm.Service.Application.Components.Platform]Microsoft.Crm.Service.Application.Platform.CalendarRule
0xbb9d  stloc.s  4
0xbb9f  ldloc.1
0xbba0  brtrue.s loc_BBE4
0xbba2  ldloc.s  4
0xbba4  callvirt instance valuetype [mscorlib]System.TimeSpan [Microsoft.Crm.Service.Application.Components.Platform]Microsoft.Crm.Service.Application.Platform.CalendarRule::get_Offset()
0xbba9  ldarg.1
0xbbaa  callvirt instance valuetype [mscorlib]System.TimeSpan [Microsoft.Crm.Service.Application.Components.Platform]Microsoft.Crm.Service.Application.Platform.CalendarRule::get_Offset()
0xbbaf  call     bool [mscorlib]System.TimeSpan::op_GreaterThan(valuetype [mscorlib]System.TimeSpan, valuetype [mscorlib]System.TimeSpan)
0xbbb4  brfalse.s loc_BC2B
0xbbb6  ldloc.0
0xbbb7  ldarg.0
0xbbb8  ldarg.1
0xbbb9  callvirt instance valuetype [mscorlib]System.TimeSpan [Microsoft.Crm.Service.Application.Components.Platform]Microsoft.Crm.Service.Application.Platform.CalendarRule::get_Offset()
0xbbbe  ldloc.s  4
0xbbc0  callvirt instance valuetype [mscorlib]System.TimeSpan [Microsoft.Crm.Service.Application.Components.Platform]Microsoft.Crm.Service.Application.Platform.CalendarRule::get_Offset()
0xbbc5  ldarg.1
0xbbc6  callvirt instance valuetype [mscorlib]System.TimeSpan [Microsoft.Crm.Service.Application.Components.Platform]Microsoft.Crm.Service.Application.Platform.CalendarRule::get_Offset()
0xbbcb  call     valuetype [mscorlib]System.TimeSpan [mscorlib]System.TimeSpan::op_Subtraction(valuetype [mscorlib]System.TimeSpan, valuetype [mscorlib]System.TimeSpan)
0xbbd0  ldarg.0
0xbbd1  ldarg.1
0xbbd2  call     instance float64 Microsoft.Crm.Service.Application.Dialogs.SM.WorkPlans.TimesheetDataPage::GetEffort(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity calendarRule)
0xbbd7  call     instance string Microsoft.Crm.Service.Application.Dialogs.SM.WorkPlans.TimesheetDataPage::AddDiffRuleXml(valuetype [mscorlib]System.TimeSpan offset, valuetype [mscorlib]System.TimeSpan duration, float64 effort)
0xbbdc  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0xbbe1  pop
0xbbe2  br.s     loc_BC2B
0xbbe4  ldloc.2
0xbbe5  callvirt instance valuetype [mscorlib]System.TimeSpan [Microsoft.Crm.Service.Application.Components.Platform]Microsoft.Crm.Service.Application.Platform.CalendarRule::get_Offset()
0xbbea  ldloc.2
0xbbeb  callvirt instance valuetype [mscorlib]System.TimeSpan [Microsoft.Crm.Service.Application.Components.Platform]Microsoft.Crm.Service.Application.Platform.CalendarRule::get_Duration()
0xbbf0  call     valuetype [mscorlib]System.TimeSpan [mscorlib]System.TimeSpan::op_Addition(valuetype [mscorlib]System.TimeSpan, valuetype [mscorlib]System.TimeSpan)
0xbbf5  stloc.s  5
0xbbf7  ldloc.s  4
0xbbf9  callvirt instance valuetype [mscorlib]System.TimeSpan [Microsoft.Crm.Service.Application.Components.Platform]Microsoft.Crm.Service.Application.Platform.CalendarRule::get_Offset()
0xbbfe  ldloc.s  5
0xbc00  call     bool [mscorlib]System.TimeSpan::op_GreaterThan(valuetype [mscorlib]System.TimeSpan, valuetype [mscorlib]System.TimeSpan)
0xbc05  brfalse.s loc_BC2B
0xbc07  ldloc.0
0xbc08  ldarg.0
0xbc09  ldloc.s  5
0xbc0b  ldloc.s  4
0xbc0d  callvirt instance valuetype [mscorlib]System.TimeSpan [Microsoft.Crm.Service.Application.Components.Platform]Microsoft.Crm.Service.Application.Platform.CalendarRule::get_Offset()
0xbc12  ldloc.s  5
0xbc14  call     valuetype [mscorlib]System.TimeSpan [mscorlib]System.TimeSpan::op_Subtraction(valuetype [mscorlib]System.TimeSpan, valuetype [mscorlib]System.TimeSpan)
0xbc19  ldarg.0
0xbc1a  ldarg.1
0xbc1b  call     instance float64 Microsoft.Crm.Service.Application.Dialogs.SM.WorkPlans.TimesheetDataPage::GetEffort(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity calendarRule)
0xbc20  call     instance string Microsoft.Crm.Service.Application.Dialogs.SM.WorkPlans.TimesheetDataPage::AddDiffRuleXml(valuetype [mscorlib]System.TimeSpan offset, valuetype [mscorlib]System.TimeSpan duration, float64 effort)
0xbc25  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0xbc2a  pop
0xbc2b  ldloc.0
0xbc2c  ldarg.0
0xbc2d  ldloc.s  4
0xbc2f  call     instance string Microsoft.Crm.Service.Application.Dialogs.SM.WorkPlans.TimesheetDataPage::AddRuleXml(class [Microsoft.Crm.Service.Application.Components.Platform]Microsoft.Crm.Service.Application.Platform.CalendarRule rule)
0xbc34  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0xbc39  pop
0xbc3a  ldloc.s  4
0xbc3c  stloc.2
0xbc3d  ldloc.1
0xbc3e  ldc.i4.1
0xbc3f  add
0xbc40  stloc.1
0xbc41  ldloc.3
0xbc42  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0xbc47  brtrue   loc_BB92
0xbc4c  leave.s  loc_BC62
0xbc4e  ldloc.3
0xbc4f  isinst   [mscorlib]System.IDisposable
0xbc54  stloc.s  6
0xbc56  ldloc.s  6
0xbc58  brfalse.s loc_BC61
0xbc5a  ldloc.s  6
0xbc5c  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xbc61  endfinally
0xbc62  ldloc.2
0xbc63  brfalse.s loc_BCB5
0xbc65  ldarg.1
0xbc66  callvirt instance valuetype [mscorlib]System.TimeSpan [Microsoft.Crm.Service.Application.Components.Platform]Microsoft.Crm.Service.Application.Platform.CalendarRule::get_Offset()
0xbc6b  ldarg.1
0xbc6c  callvirt instance valuetype [mscorlib]System.TimeSpan [Microsoft.Crm.Service.Application.Components.Platform]Microsoft.Crm.Service.Application.Platform.CalendarRule::get_Duration()
0xbc71  call     valuetype [mscorlib]System.TimeSpan [mscorlib]System.TimeSpan::op_Addition(valuetype [mscorlib]System.TimeSpan, valuetype [mscorlib]System.TimeSpan)
0xbc76  stloc.s  7
0xbc78  ldloc.2
0xbc79  callvirt instance valuetype [mscorlib]System.TimeSpan [Microsoft.Crm.Service.Application.Components.Platform]Microsoft.Crm.Service.Application.Platform.CalendarRule::get_Offset()
0xbc7e  ldloc.2
0xbc7f  callvirt instance valuetype [mscorlib]System.TimeSpan [Microsoft.Crm.Service.Application.Components.Platform]Microsoft.Crm.Service.Application.Platform.CalendarRule::get_Duration()
0xbc84  call     valuetype [mscorlib]System.TimeSpan [mscorlib]System.TimeSpan::op_Addition(valuetype [mscorlib]System.TimeSpan, valuetype [mscorlib]System.TimeSpan)
0xbc89  stloc.s  8
0xbc8b  ldloc.s  7
0xbc8d  ldloc.s  8
0xbc8f  call     bool [mscorlib]System.TimeSpan::op_GreaterThan(valuetype [mscorlib]System.TimeSpan, valuetype [mscorlib]System.TimeSpan)
0xbc94  brfalse.s loc_BCB5
0xbc96  ldloc.0
0xbc97  ldarg.0
0xbc98  ldloc.s  8
0xbc9a  ldloc.s  7
0xbc9c  ldloc.s  8
0xbc9e  call     valuetype [mscorlib]System.TimeSpan [mscorlib]System.TimeSpan::op_Subtraction(valuetype [mscorlib]System.TimeSpan, valuetype [mscorlib]System.TimeSpan)
0xbca3  ldarg.0
0xbca4  ldarg.1
0xbca5  call     instance float64 Microsoft.Crm.Service.Application.Dialogs.SM.WorkPlans.TimesheetDataPage::GetEffort(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity calendarRule)
0xbcaa  call     instance string Microsoft.Crm.Service.Application.Dialogs.SM.WorkPlans.TimesheetDataPage::AddDiffRuleXml(valuetype [mscorlib]System.TimeSpan offset, valuetype [mscorlib]System.TimeSpan duration, float64 effort)
0xbcaf  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0xbcb4  pop
0xbcb5  ldloc.0
0xbcb6  ldstr    aRules_0// "</rules>"
0xbcbb  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0xbcc0  pop
0xbcc1  ldloc.0
0xbcc2  callvirt instance string [mscorlib]System.Object::ToString()
0xbcc7  ret
```
