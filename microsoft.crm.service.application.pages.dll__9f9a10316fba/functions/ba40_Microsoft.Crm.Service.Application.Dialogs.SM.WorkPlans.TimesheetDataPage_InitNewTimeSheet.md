# Microsoft.Crm.Service.Application.Dialogs.SM.WorkPlans.TimesheetDataPage::InitNewTimeSheet

- ea: `0xba40`
- end: `0xbacb`
- name: `Microsoft.Crm.Service.Application.Dialogs.SM.WorkPlans.TimesheetDataPage::InitNewTimeSheet`
- size: `139`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0xb6b0`

## callees

- `0xba40`

## pseudocode

```c

```

## disassembly

```asm
0xba40  ldstr    a111980// "1/1/1980 "
0xba45  ldarg.0
0xba46  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentUser()
0xba4b  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser::get_WorkDayStartTime()
0xba50  call     string [mscorlib]System.String::Concat(string, string)
0xba55  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xba5a  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::Parse(string, class [mscorlib]System.IFormatProvider)
0xba5f  stloc.0
0xba60  ldstr    a111980// "1/1/1980 "
0xba65  ldarg.0
0xba66  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentUser()
0xba6b  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser::get_WorkDayStopTime()
0xba70  call     string [mscorlib]System.String::Concat(string, string)
0xba75  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xba7a  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::Parse(string, class [mscorlib]System.IFormatProvider)
0xba7f  stloc.1
0xba80  ldarg.0
0xba81  ldfld    class [Microsoft.Crm.Service.Application.Components.Application]Microsoft.Crm.Service.Application.Controls.AppTimesheet Microsoft.Crm.Service.Application.Dialogs.SM.WorkPlans.TimesheetDataPage::crmTimesheet
0xba86  ldloc.0
0xba87  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.TimeSheet::set_StartTime(valuetype [mscorlib]System.DateTime)
0xba8c  ldloc.1
0xba8d  ldloc.0
0xba8e  call     bool [mscorlib]System.DateTime::op_LessThan(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTime)
0xba93  brfalse.s loc_BAAE
0xba95  ldloca.s 0
0xba97  ldc.r8   1.0
0xbaa0  call     instance valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::AddDays(float64)
0xbaa5  stloc.2
0xbaa6  ldloca.s 2
0xbaa8  call     instance valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_Date()
0xbaad  stloc.1
0xbaae  ldarg.0
0xbaaf  ldfld    class [Microsoft.Crm.Service.Application.Components.Application]Microsoft.Crm.Service.Application.Controls.AppTimesheet Microsoft.Crm.Service.Application.Dialogs.SM.WorkPlans.TimesheetDataPage::crmTimesheet
0xbab4  ldloc.1
0xbab5  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.TimeSheet::set_EndTime(valuetype [mscorlib]System.DateTime)
0xbaba  ldarg.0
0xbabb  ldfld    class [Microsoft.Crm.Service.Application.Components.Application]Microsoft.Crm.Service.Application.Controls.AppTimesheet Microsoft.Crm.Service.Application.Dialogs.SM.WorkPlans.TimesheetDataPage::crmTimesheet
0xbac0  ldstr    aRulesRules// "<rules></rules>"
0xbac5  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.TimeSheet::set_InitStateData(string)
0xbaca  ret
```
