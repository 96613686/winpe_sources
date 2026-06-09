# Microsoft.Crm.Service.Application.Dialogs.SM.WorkPlans.TimeOffRulePage::EditCalendarRule

- ea: `0xaec0`
- end: `0xaf70`
- name: `Microsoft.Crm.Service.Application.Dialogs.SM.WorkPlans.TimeOffRulePage::EditCalendarRule`
- size: `176`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callees

- `0xa3b0`
- `0xa640`
- `0xb030`
- `0xbf80`

## pseudocode

```c

```

## disassembly

```asm
0xaec0  ldarg.0
0xaec1  call     instance class [Microsoft.Crm.Service.Application.Components.Platform]Microsoft.Crm.Service.Application.Platform.CalendarRule Microsoft.Crm.Service.Application.Dialogs.SM.WorkPlans.TimeOffRulePage::RetrieveTimeOffRule()
0xaec6  stloc.0
0xaec7  ldarg.0
0xaec8  call     instance class [Microsoft.Crm.Service.Application.Components.Platform]Microsoft.Crm.Service.Application.Platform.CalendarRule Microsoft.Crm.Service.Application.Dialogs.SM.WorkPlans.RecurringCalendarRuleBase::get_RecurringRule()
0xaecd  callvirt instance valuetype [mscorlib]System.DateTime [Microsoft.Crm.Service.Application.Components.Platform]Microsoft.Crm.Service.Application.Platform.CalendarRule::get_Start()
0xaed2  stloc.s  4
0xaed4  ldloca.s 4
0xaed6  call     instance valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_Date()
0xaedb  stloc.s  4
0xaedd  ldloca.s 4
0xaedf  ldloc.0
0xaee0  callvirt instance valuetype [mscorlib]System.TimeSpan [Microsoft.Crm.Service.Application.Components.Platform]Microsoft.Crm.Service.Application.Platform.CalendarRule::get_Offset()
0xaee5  call     instance valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::Add(valuetype [mscorlib]System.TimeSpan)
0xaeea  stloc.1
0xaeeb  ldarg.0
0xaeec  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.DateTimeUI Microsoft.Crm.Service.Application.Dialogs.SM.WorkPlans.TimeOffRulePage::scheduledstart
0xaef1  ldloc.1
0xaef2  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.DateTimeUIBase::set_Value(valuetype [mscorlib]System.DateTime)
0xaef7  ldloca.s 1
0xaef9  ldloc.0
0xaefa  callvirt instance valuetype [mscorlib]System.TimeSpan [Microsoft.Crm.Service.Application.Components.Platform]Microsoft.Crm.Service.Application.Platform.CalendarRule::get_Duration()
0xaeff  call     instance valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::Add(valuetype [mscorlib]System.TimeSpan)
0xaf04  stloc.2
0xaf05  ldarg.0
0xaf06  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.DateTimeUI Microsoft.Crm.Service.Application.Dialogs.SM.WorkPlans.TimeOffRulePage::scheduledend
0xaf0b  ldloc.2
0xaf0c  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.DateTimeUIBase::set_Value(valuetype [mscorlib]System.DateTime)
0xaf11  ldloca.s 2
0xaf13  ldloc.1
0xaf14  call     instance valuetype [mscorlib]System.TimeSpan [mscorlib]System.DateTime::Subtract(valuetype [mscorlib]System.DateTime)
0xaf19  stloc.3
0xaf1a  ldarg.0
0xaf1b  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Duration Microsoft.Crm.Service.Application.Dialogs.SM.WorkPlans.TimeOffRulePage::scheduleddurationminutes
0xaf20  ldloca.s 3
0xaf22  call     instance float64 [mscorlib]System.TimeSpan::get_TotalMinutes()
0xaf27  conv.i4
0xaf28  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Duration::set_Value(int32)
0xaf2d  ldarg.0
0xaf2e  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppTimeZoneControl Microsoft.Crm.Service.Application.Dialogs.SM.WorkPlans.TimeOffRulePage::timeZone
0xaf33  ldarg.0
0xaf34  call     instance class [Microsoft.Crm.Service.Application.Components.Platform]Microsoft.Crm.Service.Application.Platform.CalendarRule Microsoft.Crm.Service.Application.Dialogs.SM.WorkPlans.RecurringCalendarRuleBase::get_RecurringRule()
0xaf39  callvirt instance int32 [Microsoft.Crm.Service.Application.Components.Platform]Microsoft.Crm.Service.Application.Platform.CalendarRule::get_TimeZoneCode()
0xaf3e  stloc.s  5
0xaf40  ldloca.s 5
0xaf42  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xaf47  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0xaf4c  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppTimeZoneControl::set_Default(string)
0xaf51  ldarg.0
0xaf52  ldloc.1
0xaf53  ldloc.3
0xaf54  call     bool [Microsoft.Crm.Service.Application.Components.Platform]Microsoft.Crm.Service.Application.SMWorkPlans::IsAllDayEvent(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.TimeSpan)
0xaf59  call     instance void Microsoft.Crm.Service.Application.Dialogs.SM.WorkPlans.WorkCalendarRuleBase::set_AllDayEvent(bool value)
0xaf5e  ldarg.0
0xaf5f  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.TextBox Microsoft.Crm.Service.Application.Dialogs.SM.WorkPlans.TimeOffRulePage::name
0xaf64  ldarg.0
0xaf65  call     instance string Microsoft.Crm.Service.Application.Dialogs.SM.WorkPlans.RecurringCalendarRuleBase::get_RuleTypeName()
0xaf6a  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.TextBox::set_Text(string)
0xaf6f  ret
```
