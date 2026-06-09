# Microsoft.Crm.Service.Web.SM.WorkPlans.WorkPlanDetailPage::RenderCurrentNotificationString

- ea: `0x5700`
- end: `0x57b3`
- name: `Microsoft.Crm.Service.Web.SM.WorkPlans.WorkPlanDetailPage::RenderCurrentNotificationString`
- size: `179`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x43e0`

## callees

- `0x5700`
- `0x57c0`

## pseudocode

```c

```

## disassembly

```asm
0x5700  ldarg.0
0x5701  ldfld    class [Microsoft.Crm.Service.Application.Components.Platform]Microsoft.Crm.Service.Application.Platform.CalendarRule Microsoft.Crm.Service.Web.SM.WorkPlans.WorkPlanDetailPage::_recurringRule
0x5706  callvirt instance valuetype [mscorlib]System.DateTime [Microsoft.Crm.Service.Application.Components.Platform]Microsoft.Crm.Service.Application.Platform.CalendarRule::get_EffectiveIntervalEnd()
0x570b  ldsfld   valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::MaxValue
0x5710  stloc.1
0x5711  ldloca.s 1
0x5713  call     instance valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_Date()
0x5718  call     bool [mscorlib]System.DateTime::op_LessThan(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTime)
0x571d  brfalse.s loc_5749
0x571f  ldarg.0
0x5720  ldfld    class [Microsoft.Crm.Service.Application.Components.Platform]Microsoft.Crm.Service.Application.Platform.CalendarRule Microsoft.Crm.Service.Web.SM.WorkPlans.WorkPlanDetailPage::_recurringRule
0x5725  callvirt instance valuetype [mscorlib]System.DateTime [Microsoft.Crm.Service.Application.Components.Platform]Microsoft.Crm.Service.Application.Platform.CalendarRule::get_EffectiveIntervalEnd()
0x572a  stloc.1
0x572b  ldloca.s 1
0x572d  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentCulture()
0x5732  callvirt instance class [mscorlib]System.Globalization.DateTimeFormatInfo [mscorlib]System.Globalization.CultureInfo::get_DateTimeFormat()
0x5737  callvirt instance string [mscorlib]System.Globalization.DateTimeFormatInfo::get_ShortDatePattern()
0x573c  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentCulture()
0x5741  call     instance string [mscorlib]System.DateTime::ToString(string, class [mscorlib]System.IFormatProvider)
0x5746  stloc.0
0x5747  br.s     loc_575A
0x5749  ldarg.0
0x574a  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x574f  ldstr    aSmNoEndDate// "SM_No_End_Date"
0x5754  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x5759  stloc.0
0x575a  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x575f  ldarg.0
0x5760  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x5765  ldstr    aSmWeeklySchedu_0// "SM_Weekly_Schedule_Is_Current_Warning"
0x576a  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x576f  ldc.i4.3
0x5770  newarr   [mscorlib]System.Object
0x5775  dup
0x5776  ldc.i4.0
0x5777  ldarg.0
0x5778  ldfld    class [Microsoft.Crm.Service.Application.Components.Platform]Microsoft.Crm.Service.Application.Platform.CalendarRule Microsoft.Crm.Service.Web.SM.WorkPlans.WorkPlanDetailPage::_recurringRule
0x577d  callvirt instance valuetype [mscorlib]System.DateTime [Microsoft.Crm.Service.Application.Components.Platform]Microsoft.Crm.Service.Application.Platform.CalendarRule::get_Start()
0x5782  stloc.1
0x5783  ldloca.s 1
0x5785  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentCulture()
0x578a  callvirt instance class [mscorlib]System.Globalization.DateTimeFormatInfo [mscorlib]System.Globalization.CultureInfo::get_DateTimeFormat()
0x578f  callvirt instance string [mscorlib]System.Globalization.DateTimeFormatInfo::get_ShortDatePattern()
0x5794  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentCulture()
0x5799  call     instance string [mscorlib]System.DateTime::ToString(string, class [mscorlib]System.IFormatProvider)
0x579e  stelem.ref
0x579f  dup
0x57a0  ldc.i4.1
0x57a1  ldloc.0
0x57a2  stelem.ref
0x57a3  dup
0x57a4  ldc.i4.2
0x57a5  ldarg.0
0x57a6  ldarg.1
0x57a7  call     instance string Microsoft.Crm.Service.Web.SM.WorkPlans.WorkPlanDetailPage::RenderNewLinkString(valuetype [mscorlib]System.Guid resourceId)
0x57ac  stelem.ref
0x57ad  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x57b2  ret
```
