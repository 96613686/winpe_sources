# Microsoft.Crm.Service.Application.Dialogs.SM.WorkPlans.HolidayRulePage::InitDialog

- ea: `0x9f50`
- end: `0xa166`
- name: `Microsoft.Crm.Service.Application.Dialogs.SM.WorkPlans.HolidayRulePage::InitDialog`
- size: `534`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x9f50`
- `0xa3a0`
- `0xc140`

## pseudocode

```c

```

## disassembly

```asm
0x9f50  ldarg.0
0x9f51  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::crmForm
0x9f56  isinst   [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm
0x9f5b  stloc.0
0x9f5c  ldloc.0
0x9f5d  ldc.i4.1
0x9f5e  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::set_IsInlined(bool)
0x9f63  ldarg.0
0x9f64  call     instance string Microsoft.Crm.Service.Application.Dialogs.SM.WorkPlans.WorkCalendarRuleBase::get_CalendarType()
0x9f69  stloc.1
0x9f6a  ldloc.1
0x9f6b  ldstr    aBc// "bc"
0x9f70  call     bool [mscorlib]System.String::op_Equality(string, string)
0x9f75  brtrue.s loc_9F8C
0x9f77  ldloc.1
0x9f78  ldstr    aHs// "hs"
0x9f7d  call     bool [mscorlib]System.String::op_Equality(string, string)
0x9f82  brtrue   loc_A00E
0x9f87  br       loc_A0A3
0x9f8c  ldarg.0
0x9f8d  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppTabBar [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::crmTabBar
0x9f92  ldarg.0
0x9f93  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x9f98  ldstr    aCalendarRuleHo// "Calendar_Rule_Holiday"
0x9f9d  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x9fa2  ldstr    aTab0// "tab0"
0x9fa7  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.TabBar::AddTab(string, string)
0x9fac  ldarg.0
0x9fad  ldarg.0
0x9fae  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x9fb3  ldstr    aCalendarRuleHo// "Calendar_Rule_Holiday"
0x9fb8  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x9fbd  call     instance void Microsoft.Crm.Service.Application.Dialogs.SM.WorkPlans.RecurringCalendarRuleBase::set_RecurringInstanceName(string value)
0x9fc2  ldarg.0
0x9fc3  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x9fc8  ldarg.0
0x9fc9  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x9fce  ldstr    aWebSmWorkplans_1// "Web.SM.WorkPlans.Dialogs.holiday.aspx_1"...
0x9fd3  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x9fd8  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::set_Title(string)
0x9fdd  ldloc.0
0x9fde  ldarg.0
0x9fdf  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x9fe4  ldstr    aScheduleHolida// "Schedule_Holiday"
0x9fe9  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x9fee  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::set_DialogTitle(string)
0x9ff3  ldloc.0
0x9ff4  ldarg.0
0x9ff5  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x9ffa  ldstr    aHolidayDescrip// "Holiday_Description"
0x9fff  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xa004  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::set_DialogDescription(string)
0xa009  br       loc_A0A3
0xa00e  ldarg.0
0xa00f  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppTabBar [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::crmTabBar
0xa014  ldarg.0
0xa015  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xa01a  ldstr    aCalendarRuleHo_0// "Calendar_Rule_HolidayCalendar"
0xa01f  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xa024  ldstr    aTab0// "tab0"
0xa029  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.TabBar::AddTab(string, string)
0xa02e  ldarg.0
0xa02f  ldarg.0
0xa030  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xa035  ldstr    aCalendarRuleHo_0// "Calendar_Rule_HolidayCalendar"
0xa03a  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xa03f  call     instance void Microsoft.Crm.Service.Application.Dialogs.SM.WorkPlans.RecurringCalendarRuleBase::set_RecurringInstanceName(string value)
0xa044  ldarg.0
0xa045  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xa04a  ldarg.0
0xa04b  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xa050  ldstr    aWebSmWorkplans_2// "Web.SM.WorkPlans.Dialogs.holiday.aspx_1"...
0xa055  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xa05a  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::set_Title(string)
0xa05f  ldloc.0
0xa060  ldarg.0
0xa061  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xa066  ldstr    aWebSmWorkplans_2// "Web.SM.WorkPlans.Dialogs.holiday.aspx_1"...
0xa06b  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xa070  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::set_DialogTitle(string)
0xa075  ldloc.0
0xa076  ldarg.0
0xa077  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xa07c  ldstr    aHolidayCalenda// "Holiday_Calendar_Description"
0xa081  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xa086  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::set_DialogDescription(string)
0xa08b  ldarg.0
0xa08c  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Duration Microsoft.Crm.Service.Application.Dialogs.SM.WorkPlans.HolidayRulePage::scheduleddurationminutes
0xa091  ldc.i4.1
0xa092  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Duration::set_IsOnlyDays(bool)
0xa097  ldarg.0
0xa098  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Duration Microsoft.Crm.Service.Application.Dialogs.SM.WorkPlans.HolidayRulePage::scheduleddurationminutes
0xa09d  ldc.i4.1
0xa09e  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControl::set_TabIndex(int32)
0xa0a3  ldarg.0
0xa0a4  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.DateTimeUI Microsoft.Crm.Service.Application.Dialogs.SM.WorkPlans.HolidayRulePage::scheduledstart
0xa0a9  ldstr    aDatetime// "datetime"
0xa0ae  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.DateTimeUIBase::set_DisplayFormat(string)
0xa0b3  ldarg.0
0xa0b4  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.DateTimeUI Microsoft.Crm.Service.Application.Dialogs.SM.WorkPlans.HolidayRulePage::scheduledend
0xa0b9  ldstr    aDatetime// "datetime"
0xa0be  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.DateTimeUIBase::set_DisplayFormat(string)
0xa0c3  ldarg.0
0xa0c4  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Duration Microsoft.Crm.Service.Application.Dialogs.SM.WorkPlans.HolidayRulePage::scheduleddurationminutes
0xa0c9  ldarg.0
0xa0ca  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xa0cf  ldstr    aAppdurationcon// "AppDurationControl_Minute"
0xa0d4  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xa0d9  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Duration::set_MinuteFormatString(string)
0xa0de  ldarg.0
0xa0df  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Duration Microsoft.Crm.Service.Application.Dialogs.SM.WorkPlans.HolidayRulePage::scheduleddurationminutes
0xa0e4  ldarg.0
0xa0e5  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xa0ea  ldstr    aAppdurationcon_0// "AppDurationControl_Minutes"
0xa0ef  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xa0f4  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Duration::set_MinutesFormatString(string)
0xa0f9  ldarg.0
0xa0fa  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Duration Microsoft.Crm.Service.Application.Dialogs.SM.WorkPlans.HolidayRulePage::scheduleddurationminutes
0xa0ff  ldarg.0
0xa100  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xa105  ldstr    aAppdurationcon_1// "AppDurationControl_Hour"
0xa10a  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xa10f  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Duration::set_HourFormatString(string)
0xa114  ldarg.0
0xa115  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Duration Microsoft.Crm.Service.Application.Dialogs.SM.WorkPlans.HolidayRulePage::scheduleddurationminutes
0xa11a  ldarg.0
0xa11b  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xa120  ldstr    aAppdurationcon_2// "AppDurationControl_Hours"
0xa125  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xa12a  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Duration::set_HoursFormatString(string)
0xa12f  ldarg.0
0xa130  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Duration Microsoft.Crm.Service.Application.Dialogs.SM.WorkPlans.HolidayRulePage::scheduleddurationminutes
0xa135  ldarg.0
0xa136  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xa13b  ldstr    aAppdurationcon_3// "AppDurationControl_Day"
0xa140  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xa145  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Duration::set_DayFormatString(string)
0xa14a  ldarg.0
0xa14b  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Duration Microsoft.Crm.Service.Application.Dialogs.SM.WorkPlans.HolidayRulePage::scheduleddurationminutes
0xa150  ldarg.0
0xa151  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xa156  ldstr    aAppdurationcon_4// "AppDurationControl_Days"
0xa15b  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xa160  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Duration::set_DaysFormatString(string)
0xa165  ret
```
