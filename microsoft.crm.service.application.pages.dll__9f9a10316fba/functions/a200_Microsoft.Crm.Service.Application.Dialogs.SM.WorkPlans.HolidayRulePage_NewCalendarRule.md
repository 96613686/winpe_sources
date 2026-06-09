# Microsoft.Crm.Service.Application.Dialogs.SM.WorkPlans.HolidayRulePage::NewCalendarRule

- ea: `0xa200`
- end: `0xa260`
- name: `Microsoft.Crm.Service.Application.Dialogs.SM.WorkPlans.HolidayRulePage::NewCalendarRule`
- size: `96`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0xa380`
- `0xbf80`

## pseudocode

```c

```

## disassembly

```asm
0xa200  ldarg.0
0xa201  ldc.i4.0
0xa202  call     instance void Microsoft.Crm.Service.Application.Dialogs.SM.WorkPlans.RecurringCalendarRuleBase::set_RecurrenceDefined(bool value)
0xa207  ldarg.0
0xa208  ldc.i4.1
0xa209  call     instance void Microsoft.Crm.Service.Application.Dialogs.SM.WorkPlans.WorkCalendarRuleBase::set_AllDayEvent(bool value)
0xa20e  ldarg.0
0xa20f  ldflda   valuetype [mscorlib]System.DateTime Microsoft.Crm.Service.Application.Dialogs.SM.WorkPlans.HolidayRulePage::_localNow
0xa214  call     instance valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_Date()
0xa219  stloc.0
0xa21a  ldarg.0
0xa21b  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.DateTimeUI Microsoft.Crm.Service.Application.Dialogs.SM.WorkPlans.HolidayRulePage::scheduledstart
0xa220  ldloc.0
0xa221  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.DateTimeUIBase::set_Value(valuetype [mscorlib]System.DateTime)
0xa226  ldloca.s 0
0xa228  ldc.r8   1.0
0xa231  call     instance valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::AddDays(float64)
0xa236  stloc.1
0xa237  ldarg.0
0xa238  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.DateTimeUI Microsoft.Crm.Service.Application.Dialogs.SM.WorkPlans.HolidayRulePage::scheduledend
0xa23d  ldloc.1
0xa23e  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.DateTimeUIBase::set_Value(valuetype [mscorlib]System.DateTime)
0xa243  ldloca.s 1
0xa245  ldloc.0
0xa246  call     instance valuetype [mscorlib]System.TimeSpan [mscorlib]System.DateTime::Subtract(valuetype [mscorlib]System.DateTime)
0xa24b  stloc.2
0xa24c  ldarg.0
0xa24d  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Duration Microsoft.Crm.Service.Application.Dialogs.SM.WorkPlans.HolidayRulePage::scheduleddurationminutes
0xa252  ldloca.s 2
0xa254  call     instance float64 [mscorlib]System.TimeSpan::get_TotalMinutes()
0xa259  conv.i4
0xa25a  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Duration::set_Value(int32)
0xa25f  ret
```
