# Microsoft.Crm.Service.Web.SM.WorkPlans.WorkPlanDetailPage::RenderRuleParameters_0

- ea: `0x50f0`
- end: `0x5149`
- name: `Microsoft.Crm.Service.Web.SM.WorkPlans.WorkPlanDetailPage::RenderRuleParameters_0`
- size: `89`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x50f0`
- `0x55f0`
- `0x5630`

## pseudocode

```c

```

## disassembly

```asm
0x50f0  ldarg.0
0x50f1  ldfld    class [Microsoft.Crm.Service.Application.Components.Platform]Microsoft.Crm.Service.Application.Platform.CalendarRule Microsoft.Crm.Service.Web.SM.WorkPlans.WorkPlanDetailPage::_recurringRule
0x50f6  brtrue.s loc_50FE
0x50f8  ldsfld   string [mscorlib]System.String::Empty
0x50fd  ret
0x50fe  ldarg.1
0x50ff  call     int32 [Microsoft.Crm.Service.Application.Components.Platform]Microsoft.Crm.Service.Application.SMWorkPlans::ConvertCheckIndexToDay(int32)
0x5104  stloc.0
0x5105  ldc.i4.5
0x5106  newarr   [mscorlib]System.String
0x510b  dup
0x510c  ldc.i4.0
0x510d  ldarg.0
0x510e  ldloc.0
0x510f  call     instance string Microsoft.Crm.Service.Web.SM.WorkPlans.WorkPlanDetailPage::GetIdForVaryByDayRule(int32 day)
0x5114  stelem.ref
0x5115  dup
0x5116  ldc.i4.1
0x5117  ldstr    aMode_0// "&mode="
0x511c  stelem.ref
0x511d  dup
0x511e  ldc.i4.2
0x511f  ldarg.0
0x5120  ldloc.0
0x5121  call     instance string Microsoft.Crm.Service.Web.SM.WorkPlans.WorkPlanDetailPage::GetModeForVaryByDayRule(int32 day)
0x5126  stelem.ref
0x5127  dup
0x5128  ldc.i4.3
0x5129  ldstr    aDay// "&day="
0x512e  stelem.ref
0x512f  dup
0x5130  ldc.i4.4
0x5131  ldloca.s 0
0x5133  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x5138  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x513d  stelem.ref
0x513e  call     string [mscorlib]System.String::Concat(string[])
0x5143  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmJavaScriptEncodeNoQuotes(string)
0x5148  ret
```
