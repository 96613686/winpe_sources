# Microsoft.Crm.Service.Application.Dialogs.SM.WorkPlans.TimeOffRulePage::InitDialog

- ea: `0xacd0`
- end: `0xaebe`
- name: `Microsoft.Crm.Service.Application.Dialogs.SM.WorkPlans.TimeOffRulePage::InitDialog`
- size: `494`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0xa3a0`
- `0xacd0`

## pseudocode

```c

```

## disassembly

```asm
0xacd0  ldarg.0
0xacd1  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0xacd6  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0xacdb  ldstr    aTypename// "typename"
0xace0  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0xace5  stloc.0
0xace6  ldloc.0
0xace7  brfalse.s loc_ACF0
0xace9  ldarg.0
0xacea  ldloc.0
0xaceb  stfld    string Microsoft.Crm.Service.Application.Dialogs.SM.WorkPlans.TimeOffRulePage::_typeName
0xacf0  ldarg.0
0xacf1  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppTabBar [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::crmTabBar
0xacf6  ldarg.0
0xacf7  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xacfc  ldstr    aCalendarRuleTi// "Calendar_Rule_Time_Off"
0xad01  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xad06  ldstr    aTab0// "tab0"
0xad0b  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.TabBar::AddTab(string, string)
0xad10  ldarg.0
0xad11  ldarg.0
0xad12  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xad17  ldstr    aCalendarRuleTi// "Calendar_Rule_Time_Off"
0xad1c  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xad21  call     instance void Microsoft.Crm.Service.Application.Dialogs.SM.WorkPlans.RecurringCalendarRuleBase::set_RecurringInstanceName(string value)
0xad26  ldarg.0
0xad27  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xad2c  ldarg.0
0xad2d  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xad32  ldstr    aWebSmWorkplans_4// "Web.SM.WorkPlans.Dialogs.timeoff.aspx_1"...
0xad37  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xad3c  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::set_Title(string)
0xad41  ldarg.0
0xad42  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::crmForm
0xad47  isinst   [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm
0xad4c  dup
0xad4d  ldarg.0
0xad4e  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xad53  ldstr    aScheduleTimeOf// "Schedule_Time_Off"
0xad58  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xad5d  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::set_DialogTitle(string)
0xad62  dup
0xad63  ldarg.0
0xad64  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xad69  ldstr    aTimeOffDescrip// "Time_Off_Description"
0xad6e  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xad73  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::set_DialogDescription(string)
0xad78  ldc.i4.1
0xad79  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::set_IsInlined(bool)
0xad7e  ldarg.0
0xad7f  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.DateTimeUI Microsoft.Crm.Service.Application.Dialogs.SM.WorkPlans.TimeOffRulePage::scheduledstart
0xad84  ldstr    aDatetime// "datetime"
0xad89  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.DateTimeUIBase::set_DisplayFormat(string)
0xad8e  ldarg.0
0xad8f  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.DateTimeUI Microsoft.Crm.Service.Application.Dialogs.SM.WorkPlans.TimeOffRulePage::scheduledend
0xad94  ldstr    aDatetime// "datetime"
0xad99  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.DateTimeUIBase::set_DisplayFormat(string)
0xad9e  ldarg.0
0xad9f  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Duration Microsoft.Crm.Service.Application.Dialogs.SM.WorkPlans.TimeOffRulePage::scheduleddurationminutes
0xada4  ldarg.0
0xada5  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xadaa  ldstr    aAppdurationcon// "AppDurationControl_Minute"
0xadaf  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xadb4  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Duration::set_MinuteFormatString(string)
0xadb9  ldarg.0
0xadba  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Duration Microsoft.Crm.Service.Application.Dialogs.SM.WorkPlans.TimeOffRulePage::scheduleddurationminutes
0xadbf  ldarg.0
0xadc0  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xadc5  ldstr    aAppdurationcon_0// "AppDurationControl_Minutes"
0xadca  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xadcf  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Duration::set_MinutesFormatString(string)
0xadd4  ldarg.0
0xadd5  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Duration Microsoft.Crm.Service.Application.Dialogs.SM.WorkPlans.TimeOffRulePage::scheduleddurationminutes
0xadda  ldarg.0
0xaddb  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xade0  ldstr    aAppdurationcon_1// "AppDurationControl_Hour"
0xade5  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xadea  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Duration::set_HourFormatString(string)
0xadef  ldarg.0
0xadf0  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Duration Microsoft.Crm.Service.Application.Dialogs.SM.WorkPlans.TimeOffRulePage::scheduleddurationminutes
0xadf5  ldarg.0
0xadf6  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xadfb  ldstr    aAppdurationcon_2// "AppDurationControl_Hours"
0xae00  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xae05  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Duration::set_HoursFormatString(string)
0xae0a  ldarg.0
0xae0b  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Duration Microsoft.Crm.Service.Application.Dialogs.SM.WorkPlans.TimeOffRulePage::scheduleddurationminutes
0xae10  ldarg.0
0xae11  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xae16  ldstr    aAppdurationcon_3// "AppDurationControl_Day"
0xae1b  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xae20  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Duration::set_DayFormatString(string)
0xae25  ldarg.0
0xae26  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Duration Microsoft.Crm.Service.Application.Dialogs.SM.WorkPlans.TimeOffRulePage::scheduleddurationminutes
0xae2b  ldarg.0
0xae2c  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xae31  ldstr    aAppdurationcon_4// "AppDurationControl_Days"
0xae36  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xae3b  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Duration::set_DaysFormatString(string)
0xae40  ldarg.0
0xae41  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0xae46  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0xae4b  ldstr    aSelecteddates// "selecteddates"
0xae50  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0xae55  stloc.1
0xae56  ldloc.1
0xae57  brfalse.s loc_AEBD
0xae59  ldloc.1
0xae5a  callvirt instance int32 [mscorlib]System.String::get_Length()
0xae5f  ldc.i4.0
0xae60  ble.s    loc_AEBD
0xae62  ldloc.1
0xae63  ldc.i4.1
0xae64  newarr   [mscorlib]System.Char
0xae69  dup
0xae6a  ldc.i4.0
0xae6b  ldc.i4.s 0x2C
0xae6d  stelem.i2
0xae6e  callvirt instance string[] [mscorlib]System.String::Split(char[])
0xae73  stloc.2
0xae74  ldarg.0
0xae75  ldloc.2
0xae76  ldlen
0xae77  conv.i4
0xae78  newarr   [mscorlib]System.DateTime
0xae7d  stfld    valuetype [mscorlib]System.DateTime[] Microsoft.Crm.Service.Application.Dialogs.SM.WorkPlans.TimeOffRulePage::_selectedDates
0xae82  ldc.i4.0
0xae83  stloc.3
0xae84  ldloc.2
0xae85  stloc.s  4
0xae87  ldc.i4.0
0xae88  stloc.s  5
0xae8a  br.s     loc_AEB5
0xae8c  ldloc.s  4
0xae8e  ldloc.s  5
0xae90  ldelem.ref
0xae91  stloc.s  6
0xae93  ldarg.0
0xae94  ldfld    valuetype [mscorlib]System.DateTime[] Microsoft.Crm.Service.Application.Dialogs.SM.WorkPlans.TimeOffRulePage::_selectedDates
0xae99  ldloc.3
0xae9a  ldloc.s  6
0xae9c  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xaea1  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::Parse(string, class [mscorlib]System.IFormatProvider)
0xaea6  stelem   [mscorlib]System.DateTime
0xaeab  ldloc.3
0xaeac  ldc.i4.1
0xaead  add
0xaeae  stloc.3
0xaeaf  ldloc.s  5
0xaeb1  ldc.i4.1
0xaeb2  add
0xaeb3  stloc.s  5
0xaeb5  ldloc.s  5
0xaeb7  ldloc.s  4
0xaeb9  ldlen
0xaeba  conv.i4
0xaebb  blt.s    loc_AE8C
0xaebd  ret
```
