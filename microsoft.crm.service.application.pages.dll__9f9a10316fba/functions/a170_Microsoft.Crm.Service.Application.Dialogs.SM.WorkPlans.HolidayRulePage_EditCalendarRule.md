# Microsoft.Crm.Service.Application.Dialogs.SM.WorkPlans.HolidayRulePage::EditCalendarRule

- ea: `0xa170`
- end: `0xa1f4`
- name: `Microsoft.Crm.Service.Application.Dialogs.SM.WorkPlans.HolidayRulePage::EditCalendarRule`
- size: `132`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0xa270`
- `0xa3b0`
- `0xbf80`

## pseudocode

```c

```

## disassembly

```asm
0xa170  ldarg.0
0xa171  call     instance class [Microsoft.Crm.Service.Application.Components.Platform]Microsoft.Crm.Service.Application.Platform.CalendarRule Microsoft.Crm.Service.Application.Dialogs.SM.WorkPlans.HolidayRulePage::RetrieveHolidayRule()
0xa176  stloc.0
0xa177  ldarg.0
0xa178  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.DateTimeUI Microsoft.Crm.Service.Application.Dialogs.SM.WorkPlans.HolidayRulePage::scheduledstart
0xa17d  ldarg.0
0xa17e  call     instance class [Microsoft.Crm.Service.Application.Components.Platform]Microsoft.Crm.Service.Application.Platform.CalendarRule Microsoft.Crm.Service.Application.Dialogs.SM.WorkPlans.RecurringCalendarRuleBase::get_RecurringRule()
0xa183  callvirt instance valuetype [mscorlib]System.DateTime [Microsoft.Crm.Service.Application.Components.Platform]Microsoft.Crm.Service.Application.Platform.CalendarRule::get_Start()
0xa188  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.DateTimeUIBase::set_Value(valuetype [mscorlib]System.DateTime)
0xa18d  ldarg.0
0xa18e  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.DateTimeUI Microsoft.Crm.Service.Application.Dialogs.SM.WorkPlans.HolidayRulePage::scheduledend
0xa193  ldarg.0
0xa194  call     instance class [Microsoft.Crm.Service.Application.Components.Platform]Microsoft.Crm.Service.Application.Platform.CalendarRule Microsoft.Crm.Service.Application.Dialogs.SM.WorkPlans.RecurringCalendarRuleBase::get_RecurringRule()
0xa199  callvirt instance valuetype [mscorlib]System.DateTime [Microsoft.Crm.Service.Application.Components.Platform]Microsoft.Crm.Service.Application.Platform.CalendarRule::get_Start()
0xa19e  stloc.2
0xa19f  ldloca.s 2
0xa1a1  ldloc.0
0xa1a2  callvirt instance valuetype [mscorlib]System.TimeSpan [Microsoft.Crm.Service.Application.Components.Platform]Microsoft.Crm.Service.Application.Platform.CalendarRule::get_Duration()
0xa1a7  call     instance valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::Add(valuetype [mscorlib]System.TimeSpan)
0xa1ac  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.DateTimeUIBase::set_Value(valuetype [mscorlib]System.DateTime)
0xa1b1  ldloc.0
0xa1b2  callvirt instance valuetype [mscorlib]System.TimeSpan [Microsoft.Crm.Service.Application.Components.Platform]Microsoft.Crm.Service.Application.Platform.CalendarRule::get_Duration()
0xa1b7  stloc.1
0xa1b8  ldarg.0
0xa1b9  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Duration Microsoft.Crm.Service.Application.Dialogs.SM.WorkPlans.HolidayRulePage::scheduleddurationminutes
0xa1be  ldloca.s 1
0xa1c0  call     instance float64 [mscorlib]System.TimeSpan::get_TotalMinutes()
0xa1c5  conv.i4
0xa1c6  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Duration::set_Value(int32)
0xa1cb  ldarg.0
0xa1cc  ldarg.0
0xa1cd  call     instance class [Microsoft.Crm.Service.Application.Components.Platform]Microsoft.Crm.Service.Application.Platform.CalendarRule Microsoft.Crm.Service.Application.Dialogs.SM.WorkPlans.RecurringCalendarRuleBase::get_RecurringRule()
0xa1d2  callvirt instance valuetype [mscorlib]System.DateTime [Microsoft.Crm.Service.Application.Components.Platform]Microsoft.Crm.Service.Application.Platform.CalendarRule::get_Start()
0xa1d7  ldloc.1
0xa1d8  call     bool [Microsoft.Crm.Service.Application.Components.Platform]Microsoft.Crm.Service.Application.SMWorkPlans::IsAllDayEvent(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.TimeSpan)
0xa1dd  call     instance void Microsoft.Crm.Service.Application.Dialogs.SM.WorkPlans.WorkCalendarRuleBase::set_AllDayEvent(bool value)
0xa1e2  ldarg.0
0xa1e3  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.TextBox Microsoft.Crm.Service.Application.Dialogs.SM.WorkPlans.HolidayRulePage::name
0xa1e8  ldloc.0
0xa1e9  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_DisplayName()
0xa1ee  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.TextBox::set_Text(string)
0xa1f3  ret
```
