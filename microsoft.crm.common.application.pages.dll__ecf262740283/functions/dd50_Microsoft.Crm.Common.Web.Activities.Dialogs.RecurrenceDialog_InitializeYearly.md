# Microsoft.Crm.Common.Web.Activities.Dialogs.RecurrenceDialog::InitializeYearly

- ea: `0xdd50`
- end: `0xdf40`
- name: `Microsoft.Crm.Common.Web.Activities.Dialogs.RecurrenceDialog::InitializeYearly`
- size: `496`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0xd870`

## callees

- `0xe240`
- `0xe320`
- `0xe3f0`
- `0xe480`

## pseudocode

```c

```

## disassembly

```asm
0xdd50  ldarg.0
0xdd51  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::crmForm
0xdd56  ldstr    aYearlypattern// "yearlyPattern"
0xdd5b  callvirt instance class [System.Web]System.Web.UI.Control [System.Web]System.Web.UI.Control::FindControl(string)
0xdd60  isinst   [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.PatternContainer
0xdd65  stloc.0
0xdd66  ldarg.0
0xdd67  ldstr    aYearlyoption1I// "yearlyOption1_interval"
0xdd6c  ldc.i4.1
0xdd6d  ldc.i4.s 0x63
0xdd6f  ldc.i4.0
0xdd70  call     instance class [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.TextBoxControl Microsoft.Crm.Common.Web.Activities.Dialogs.RecurrenceDialog::GetInitializedNumber(string id, int32 min, int32 max, bool monthly)
0xdd75  stloc.1
0xdd76  ldloc.1
0xdd77  ldstr    aTitle// "title"
0xdd7c  ldarg.0
0xdd7d  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xdd82  ldstr    aWebVisualizati// "Web.Visualization.AxisTitle.DateGroupin"...
0xdd87  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xdd8c  callvirt instance void [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormControlBase::AddExpando(string, string)
0xdd91  ldarg.0
0xdd92  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xdd97  ldstr    aRecurrencerule_21// "RecurrenceRule.RecurrencePatternSection"...
0xdd9c  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xdda1  stloc.2
0xdda2  ldc.i4.1
0xdda3  ldloc.2
0xdda4  newobj   instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.LocalizableOptionControl::.ctor(int32, string)
0xdda9  stloc.3
0xddaa  ldloc.3
0xddab  ldloc.1
0xddac  ldstr    aMsCrmRecurrenc// "ms-crm-recurrence-dialog-Number"
0xddb1  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.LocalizableOptionControl::AddControl(class [System.Web]System.Web.UI.Control, string)
0xddb6  ldloc.3
0xddb7  ldc.i4.0
0xddb8  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.LocalizableOptionControl::set_RenderRadio(bool)
0xddbd  ldarg.0
0xddbe  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xddc3  ldstr    aRecurrencerule_22// "RecurrenceRule.RecurrencePatternSection"...
0xddc8  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xddcd  stloc.s  4
0xddcf  ldc.i4.2
0xddd0  ldloc.s  4
0xddd2  newobj   instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.LocalizableOptionControl::.ctor(int32, string)
0xddd7  stloc.s  5
0xddd9  ldarg.0
0xddda  ldstr    aYearlyoption2M// "yearlyOption2_monthofyear"
0xdddf  call     instance class [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.PicklistControl Microsoft.Crm.Common.Web.Activities.Dialogs.RecurrenceDialog::GetInitializedMonthPicklist(string id)
0xdde4  stloc.s  6
0xdde6  ldloc.s  6
0xdde8  ldstr    aTitle// "title"
0xdded  ldarg.0
0xddee  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xddf3  ldstr    aCalendarViewLa_0// "Calendar_View_Label_Month"
0xddf8  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xddfd  callvirt instance void [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormControlBase::AddExpando(string, string)
0xde02  ldarg.0
0xde03  ldstr    aYearlyoption2D// "yearlyOption2_dayofmonth"
0xde08  ldc.i4.1
0xde09  ldc.i4.s 0x63
0xde0b  ldc.i4.1
0xde0c  call     instance class [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.TextBoxControl Microsoft.Crm.Common.Web.Activities.Dialogs.RecurrenceDialog::GetInitializedNumber(string id, int32 min, int32 max, bool monthly)
0xde11  stloc.s  7
0xde13  ldloc.s  7
0xde15  ldstr    aTitle// "title"
0xde1a  ldarg.0
0xde1b  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xde20  ldstr    aRecurrencerule_15// "RecurrenceRule.Dialog.DayList.Day"
0xde25  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xde2a  callvirt instance void [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormControlBase::AddExpando(string, string)
0xde2f  ldloc.s  5
0xde31  ldloc.s  6
0xde33  ldstr    aMsCrmRecurrenc_0// "ms-crm-recurrence-dialog-Picklist"
0xde38  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.LocalizableOptionControl::AddControl(class [System.Web]System.Web.UI.Control, string)
0xde3d  ldloc.s  5
0xde3f  ldloc.s  7
0xde41  ldstr    aMsCrmRecurrenc// "ms-crm-recurrence-dialog-Number"
0xde46  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.LocalizableOptionControl::AddControl(class [System.Web]System.Web.UI.Control, string)
0xde4b  ldarg.0
0xde4c  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xde51  ldstr    aRecurrencerule_23// "RecurrenceRule.RecurrencePatternSection"...
0xde56  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xde5b  stloc.s  8
0xde5d  ldc.i4.3
0xde5e  ldloc.s  8
0xde60  newobj   instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.LocalizableOptionControl::.ctor(int32, string)
0xde65  stloc.s  9
0xde67  ldarg.0
0xde68  ldstr    aYearlyoption3I// "yearlyOption3_instance"
0xde6d  call     instance class [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.PicklistControl Microsoft.Crm.Common.Web.Activities.Dialogs.RecurrenceDialog::GetInitializedInstancePicklist(string id)
0xde72  stloc.s  0xA
0xde74  ldloc.s  0xA
0xde76  ldstr    aTitle// "title"
0xde7b  ldarg.0
0xde7c  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xde81  ldstr    aRecurrencerule_15// "RecurrenceRule.Dialog.DayList.Day"
0xde86  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xde8b  callvirt instance void [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormControlBase::AddExpando(string, string)
0xde90  ldarg.0
0xde91  ldstr    aYearlyoption3D// "yearlyOption3_daysofweekmask"
0xde96  call     instance class [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.PicklistControl Microsoft.Crm.Common.Web.Activities.Dialogs.RecurrenceDialog::GetInitializedDayPicklist(string id)
0xde9b  stloc.s  0xB
0xde9d  ldloc.s  0xB
0xde9f  ldstr    aTitle// "title"
0xdea4  ldarg.0
0xdea5  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xdeaa  ldstr    aCalendarViewLa// "Calendar_View_Label_Week"
0xdeaf  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xdeb4  callvirt instance void [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormControlBase::AddExpando(string, string)
0xdeb9  ldarg.0
0xdeba  ldstr    aYearlyoption3M// "yearlyOption3_monthofyear"
0xdebf  call     instance class [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.PicklistControl Microsoft.Crm.Common.Web.Activities.Dialogs.RecurrenceDialog::GetInitializedMonthPicklist(string id)
0xdec4  stloc.s  0xC
0xdec6  ldloc.s  0xC
0xdec8  ldstr    aTitle// "title"
0xdecd  ldarg.0
0xdece  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xded3  ldstr    aCalendarViewLa_0// "Calendar_View_Label_Month"
0xded8  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xdedd  callvirt instance void [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormControlBase::AddExpando(string, string)
0xdee2  ldloc.s  9
0xdee4  ldloc.s  0xA
0xdee6  ldstr    aMsCrmRecurrenc_0// "ms-crm-recurrence-dialog-Picklist"
0xdeeb  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.LocalizableOptionControl::AddControl(class [System.Web]System.Web.UI.Control, string)
0xdef0  ldloc.s  9
0xdef2  ldloc.s  0xB
0xdef4  ldstr    aMsCrmRecurrenc_0// "ms-crm-recurrence-dialog-Picklist"
0xdef9  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.LocalizableOptionControl::AddControl(class [System.Web]System.Web.UI.Control, string)
0xdefe  ldloc.s  9
0xdf00  ldloc.s  0xC
0xdf02  ldstr    aMsCrmRecurrenc_0// "ms-crm-recurrence-dialog-Picklist"
0xdf07  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.LocalizableOptionControl::AddControl(class [System.Web]System.Web.UI.Control, string)
0xdf0c  ldloc.0
0xdf0d  ldc.i4.1
0xdf0e  ldloc.3
0xdf0f  ldc.i4.0
0xdf10  newarr   [System.Web]System.Web.UI.Control
0xdf15  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.PatternContainer::AddControls(int32, class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.LocalizableOptionControl, class [System.Web]System.Web.UI.Control[])
0xdf1a  ldloc.0
0xdf1b  ldc.i4.2
0xdf1c  ldloc.s  5
0xdf1e  ldc.i4.0
0xdf1f  newarr   [System.Web]System.Web.UI.Control
0xdf24  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.PatternContainer::AddControls(int32, class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.LocalizableOptionControl, class [System.Web]System.Web.UI.Control[])
0xdf29  ldloc.0
0xdf2a  ldc.i4.3
0xdf2b  ldloc.s  9
0xdf2d  ldc.i4.0
0xdf2e  newarr   [System.Web]System.Web.UI.Control
0xdf33  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.PatternContainer::AddControls(int32, class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.LocalizableOptionControl, class [System.Web]System.Web.UI.Control[])
0xdf38  ldloc.0
0xdf39  ldc.i4.2
0xdf3a  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.PatternContainer::set_CheckedOption(int32)
0xdf3f  ret
```
