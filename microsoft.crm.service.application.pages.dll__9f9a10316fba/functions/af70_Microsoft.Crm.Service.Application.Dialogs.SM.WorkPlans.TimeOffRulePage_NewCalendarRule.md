# Microsoft.Crm.Service.Application.Dialogs.SM.WorkPlans.TimeOffRulePage::NewCalendarRule

- ea: `0xaf70`
- end: `0xb017`
- name: `Microsoft.Crm.Service.Application.Dialogs.SM.WorkPlans.TimeOffRulePage::NewCalendarRule`
- size: `167`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callees

- `0xaf70`
- `0xbf80`
- `0xbf90`
- `0xbfb0`

## pseudocode

```c

```

## disassembly

```asm
0xaf70  ldarg.0
0xaf71  ldc.i4.1
0xaf72  call     instance void Microsoft.Crm.Service.Application.Dialogs.SM.WorkPlans.WorkCalendarRuleBase::set_AllDayEvent(bool value)
0xaf77  ldarg.0
0xaf78  ldfld    valuetype [mscorlib]System.DateTime[] Microsoft.Crm.Service.Application.Dialogs.SM.WorkPlans.TimeOffRulePage::_selectedDates
0xaf7d  brfalse.s loc_AF97
0xaf7f  ldarg.0
0xaf80  ldfld    valuetype [mscorlib]System.DateTime[] Microsoft.Crm.Service.Application.Dialogs.SM.WorkPlans.TimeOffRulePage::_selectedDates
0xaf85  ldlen
0xaf86  brfalse.s loc_AF97
0xaf88  ldarg.0
0xaf89  ldfld    valuetype [mscorlib]System.DateTime[] Microsoft.Crm.Service.Application.Dialogs.SM.WorkPlans.TimeOffRulePage::_selectedDates
0xaf8e  ldc.i4.0
0xaf8f  ldelem   [mscorlib]System.DateTime
0xaf94  stloc.0
0xaf95  br.s     loc_AFA3
0xaf97  ldarg.0
0xaf98  ldflda   valuetype [mscorlib]System.DateTime Microsoft.Crm.Service.Application.Dialogs.SM.WorkPlans.TimeOffRulePage::_localNow
0xaf9d  call     instance valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_Date()
0xafa2  stloc.0
0xafa3  ldarg.0
0xafa4  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.DateTimeUI Microsoft.Crm.Service.Application.Dialogs.SM.WorkPlans.TimeOffRulePage::scheduledstart
0xafa9  ldloc.0
0xafaa  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.DateTimeUIBase::set_Value(valuetype [mscorlib]System.DateTime)
0xafaf  ldloca.s 0
0xafb1  ldc.r8   1.0
0xafba  call     instance valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::AddDays(float64)
0xafbf  stloc.1
0xafc0  ldarg.0
0xafc1  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.DateTimeUI Microsoft.Crm.Service.Application.Dialogs.SM.WorkPlans.TimeOffRulePage::scheduledend
0xafc6  ldloc.1
0xafc7  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.DateTimeUIBase::set_Value(valuetype [mscorlib]System.DateTime)
0xafcc  ldloca.s 1
0xafce  ldloc.0
0xafcf  call     instance valuetype [mscorlib]System.TimeSpan [mscorlib]System.DateTime::Subtract(valuetype [mscorlib]System.DateTime)
0xafd4  stloc.2
0xafd5  ldarg.0
0xafd6  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Duration Microsoft.Crm.Service.Application.Dialogs.SM.WorkPlans.TimeOffRulePage::scheduleddurationminutes
0xafdb  ldloca.s 2
0xafdd  call     instance float64 [mscorlib]System.TimeSpan::get_TotalMinutes()
0xafe2  conv.i4
0xafe3  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Duration::set_Value(int32)
0xafe8  ldarg.0
0xafe9  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppTimeZoneControl Microsoft.Crm.Service.Application.Dialogs.SM.WorkPlans.TimeOffRulePage::timeZone
0xafee  ldarg.0
0xafef  call     instance string Microsoft.Crm.Service.Application.Dialogs.SM.WorkPlans.WorkCalendarRuleBase::get_ResourceId()
0xaff4  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xaff9  ldarg.0
0xaffa  call     instance int32 Microsoft.Crm.Service.Application.Dialogs.SM.WorkPlans.WorkCalendarRuleBase::get_ObjectTypeCode()
0xafff  call     int32 [Microsoft.Crm.Service.Application.Components.Platform]Microsoft.Crm.Service.Application.SMWorkPlans::GetUserTimeZoneIndex(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext, int32)
0xb004  stloc.3
0xb005  ldloca.s 3
0xb007  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xb00c  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0xb011  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppTimeZoneControl::set_Default(string)
0xb016  ret
```
