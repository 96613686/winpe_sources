# Microsoft.Crm.Service.Application.Dialogs.SM.WorkPlans.ServiceAvailabilityRulePage::InitDialog

- ea: `0xaa10`
- end: `0xab8a`
- name: `Microsoft.Crm.Service.Application.Dialogs.SM.WorkPlans.ServiceAvailabilityRulePage::InitDialog`
- size: `378`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## callers

- `0xa950`

## string_xrefs

- `0xaaea`: `Calendar_Rule_Service_Restriction`
- `0xab0a`: `Web.SM.WorkPlans.Dialogs.serviceavailability.aspx_10`
- `0xab2b`: `Service_Restriction_Description`
- `0xab41`: `Service_Restriction_SubDescription`

## pseudocode

```c

```

## disassembly

```asm
0xaa10  ldarg.0
0xaa11  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.DateTimeUI Microsoft.Crm.Service.Application.Dialogs.SM.WorkPlans.ServiceAvailabilityRulePage::scheduledstart
0xaa16  ldstr    aTime// "time"
0xaa1b  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.DateTimeUIBase::set_DisplayFormat(string)
0xaa20  ldarg.0
0xaa21  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.DateTimeUI Microsoft.Crm.Service.Application.Dialogs.SM.WorkPlans.ServiceAvailabilityRulePage::scheduledend
0xaa26  ldstr    aTime// "time"
0xaa2b  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.DateTimeUIBase::set_DisplayFormat(string)
0xaa30  ldarg.0
0xaa31  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.DateTimeUI Microsoft.Crm.Service.Application.Dialogs.SM.WorkPlans.ServiceAvailabilityRulePage::scheduledend
0xaa36  ldc.i4.1
0xaa37  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.DateTimeUIBase::set_PositionMidnightLast(bool)
0xaa3c  ldarg.0
0xaa3d  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Duration Microsoft.Crm.Service.Application.Dialogs.SM.WorkPlans.ServiceAvailabilityRulePage::scheduleddurationminutes
0xaa42  ldarg.0
0xaa43  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xaa48  ldstr    aAppdurationcon// "AppDurationControl_Minute"
0xaa4d  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xaa52  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Duration::set_MinuteFormatString(string)
0xaa57  ldarg.0
0xaa58  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Duration Microsoft.Crm.Service.Application.Dialogs.SM.WorkPlans.ServiceAvailabilityRulePage::scheduleddurationminutes
0xaa5d  ldarg.0
0xaa5e  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xaa63  ldstr    aAppdurationcon_0// "AppDurationControl_Minutes"
0xaa68  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xaa6d  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Duration::set_MinutesFormatString(string)
0xaa72  ldarg.0
0xaa73  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Duration Microsoft.Crm.Service.Application.Dialogs.SM.WorkPlans.ServiceAvailabilityRulePage::scheduleddurationminutes
0xaa78  ldarg.0
0xaa79  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xaa7e  ldstr    aAppdurationcon_1// "AppDurationControl_Hour"
0xaa83  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xaa88  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Duration::set_HourFormatString(string)
0xaa8d  ldarg.0
0xaa8e  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Duration Microsoft.Crm.Service.Application.Dialogs.SM.WorkPlans.ServiceAvailabilityRulePage::scheduleddurationminutes
0xaa93  ldarg.0
0xaa94  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xaa99  ldstr    aAppdurationcon_2// "AppDurationControl_Hours"
0xaa9e  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xaaa3  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Duration::set_HoursFormatString(string)
0xaaa8  ldarg.0
0xaaa9  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Duration Microsoft.Crm.Service.Application.Dialogs.SM.WorkPlans.ServiceAvailabilityRulePage::scheduleddurationminutes
0xaaae  ldarg.0
0xaaaf  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xaab4  ldstr    aAppdurationcon_3// "AppDurationControl_Day"
0xaab9  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xaabe  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Duration::set_DayFormatString(string)
0xaac3  ldarg.0
0xaac4  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Duration Microsoft.Crm.Service.Application.Dialogs.SM.WorkPlans.ServiceAvailabilityRulePage::scheduleddurationminutes
0xaac9  ldarg.0
0xaaca  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xaacf  ldstr    aAppdurationcon_4// "AppDurationControl_Days"
0xaad4  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xaad9  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Duration::set_DaysFormatString(string)
0xaade  ldarg.0
0xaadf  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppTabBar [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::crmTabBar
0xaae4  ldarg.0
0xaae5  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xaaea  ldstr    aCalendarRuleSe// "Calendar_Rule_Service_Restriction"
0xaaef  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xaaf4  ldstr    aTab0// "tab0"
0xaaf9  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.TabBar::AddTab(string, string)
0xaafe  ldarg.0
0xaaff  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xab04  ldarg.0
0xab05  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xab0a  ldstr    aWebSmWorkplans_3// "Web.SM.WorkPlans.Dialogs.serviceavailab"...
0xab0f  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xab14  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::set_Title(string)
0xab19  ldarg.0
0xab1a  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::crmForm
0xab1f  isinst   [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm
0xab24  dup
0xab25  ldarg.0
0xab26  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xab2b  ldstr    aServiceRestric_0// "Service_Restriction_Description"
0xab30  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xab35  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::set_DialogTitle(string)
0xab3a  dup
0xab3b  ldarg.0
0xab3c  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xab41  ldstr    aServiceRestric_1// "Service_Restriction_SubDescription"
0xab46  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xab4b  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::set_DialogDescription(string)
0xab50  dup
0xab51  ldc.i4.0
0xab52  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::set_ButtonStyle(valuetype [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogButtonStyles)
0xab57  dup
0xab58  ldc.i4.1
0xab59  ldstr    aButtonLabelOk// "Button_Label_OK"
0xab5e  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::AddButton(valuetype [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogButtonStyles, string)
0xab63  dup
0xab64  ldc.i4.2
0xab65  ldstr    aButtonLabelCan// "Button_Label_Cancel"
0xab6a  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::AddButton(valuetype [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogButtonStyles, string)
0xab6f  dup
0xab70  ldc.i4.s 0x20
0xab72  ldstr    aButtonLabelHel// "Button_Label_Help"
0xab77  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::AddButton(valuetype [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogButtonStyles, string)
0xab7c  dup
0xab7d  ldc.i4.1
0xab7e  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::set_OverrideDefaultTabbing(bool)
0xab83  ldc.i4.0
0xab84  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::set_OverriddenMaxTabIndex(int32)
0xab89  ret
```
