# Microsoft.Crm.Common.Web.Activities.Dialogs.RecurrenceDialog::InitializeMonthly

- ea: `0xdbc0`
- end: `0xdd4a`
- name: `Microsoft.Crm.Common.Web.Activities.Dialogs.RecurrenceDialog::InitializeMonthly`
- size: `394`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0xd870`

## callees

- `0xe240`
- `0xe320`
- `0xe3f0`

## pseudocode

```c

```

## disassembly

```asm
0xdbc0  ldarg.0
0xdbc1  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::crmForm
0xdbc6  ldstr    aMonthlypattern// "monthlyPattern"
0xdbcb  callvirt instance class [System.Web]System.Web.UI.Control [System.Web]System.Web.UI.Control::FindControl(string)
0xdbd0  isinst   [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.PatternContainer
0xdbd5  stloc.0
0xdbd6  ldarg.0
0xdbd7  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xdbdc  ldstr    aRecurrencerule_19// "RecurrenceRule.RecurrencePatternSection"...
0xdbe1  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xdbe6  stloc.1
0xdbe7  ldc.i4.1
0xdbe8  ldloc.1
0xdbe9  newobj   instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.LocalizableOptionControl::.ctor(int32, string)
0xdbee  stloc.2
0xdbef  ldarg.0
0xdbf0  ldstr    aMonthlyoption1// "monthlyOption1_dayofmonth"
0xdbf5  ldc.i4.1
0xdbf6  ldc.i4.s 0x63
0xdbf8  ldc.i4.1
0xdbf9  call     instance class [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.TextBoxControl Microsoft.Crm.Common.Web.Activities.Dialogs.RecurrenceDialog::GetInitializedNumber(string id, int32 min, int32 max, bool monthly)
0xdbfe  stloc.3
0xdbff  ldloc.3
0xdc00  ldstr    aTitle// "title"
0xdc05  ldarg.0
0xdc06  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xdc0b  ldstr    aRecurrencerule_15// "RecurrenceRule.Dialog.DayList.Day"
0xdc10  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xdc15  callvirt instance void [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormControlBase::AddExpando(string, string)
0xdc1a  ldarg.0
0xdc1b  ldstr    aMonthlyoption1_0// "monthlyOption1_interval"
0xdc20  ldc.i4.1
0xdc21  ldc.i4.s 0x63
0xdc23  ldc.i4.0
0xdc24  call     instance class [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.TextBoxControl Microsoft.Crm.Common.Web.Activities.Dialogs.RecurrenceDialog::GetInitializedNumber(string id, int32 min, int32 max, bool monthly)
0xdc29  stloc.s  4
0xdc2b  ldloc.s  4
0xdc2d  ldstr    aTitle// "title"
0xdc32  ldarg.0
0xdc33  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xdc38  ldstr    aCalendarViewLa_0// "Calendar_View_Label_Month"
0xdc3d  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xdc42  callvirt instance void [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormControlBase::AddExpando(string, string)
0xdc47  ldloc.2
0xdc48  ldloc.3
0xdc49  ldstr    aMsCrmRecurrenc// "ms-crm-recurrence-dialog-Number"
0xdc4e  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.LocalizableOptionControl::AddControl(class [System.Web]System.Web.UI.Control, string)
0xdc53  ldloc.2
0xdc54  ldloc.s  4
0xdc56  ldstr    aMsCrmRecurrenc// "ms-crm-recurrence-dialog-Number"
0xdc5b  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.LocalizableOptionControl::AddControl(class [System.Web]System.Web.UI.Control, string)
0xdc60  ldarg.0
0xdc61  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xdc66  ldstr    aRecurrencerule_20// "RecurrenceRule.RecurrencePatternSection"...
0xdc6b  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xdc70  stloc.s  5
0xdc72  ldc.i4.2
0xdc73  ldloc.s  5
0xdc75  newobj   instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.LocalizableOptionControl::.ctor(int32, string)
0xdc7a  stloc.s  6
0xdc7c  ldarg.0
0xdc7d  ldstr    aMonthlyoption2// "monthlyOption2_interval"
0xdc82  ldc.i4.1
0xdc83  ldc.i4.s 0x63
0xdc85  ldc.i4.0
0xdc86  call     instance class [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.TextBoxControl Microsoft.Crm.Common.Web.Activities.Dialogs.RecurrenceDialog::GetInitializedNumber(string id, int32 min, int32 max, bool monthly)
0xdc8b  stloc.s  7
0xdc8d  ldloc.s  7
0xdc8f  ldstr    aTitle// "title"
0xdc94  ldarg.0
0xdc95  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xdc9a  ldstr    aCalendarViewLa_0// "Calendar_View_Label_Month"
0xdc9f  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xdca4  callvirt instance void [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormControlBase::AddExpando(string, string)
0xdca9  ldarg.0
0xdcaa  ldstr    aMonthlyoption2_0// "monthlyOption2_instance"
0xdcaf  call     instance class [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.PicklistControl Microsoft.Crm.Common.Web.Activities.Dialogs.RecurrenceDialog::GetInitializedInstancePicklist(string id)
0xdcb4  stloc.s  8
0xdcb6  ldloc.s  8
0xdcb8  ldstr    aTitle// "title"
0xdcbd  ldarg.0
0xdcbe  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xdcc3  ldstr    aRecurrencerule_15// "RecurrenceRule.Dialog.DayList.Day"
0xdcc8  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xdccd  callvirt instance void [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormControlBase::AddExpando(string, string)
0xdcd2  ldarg.0
0xdcd3  ldstr    aMonthlyoption2_1// "monthlyOption2_daysofweekmask"
0xdcd8  call     instance class [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.PicklistControl Microsoft.Crm.Common.Web.Activities.Dialogs.RecurrenceDialog::GetInitializedDayPicklist(string id)
0xdcdd  stloc.s  9
0xdcdf  ldloc.s  9
0xdce1  ldstr    aTitle// "title"
0xdce6  ldarg.0
0xdce7  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xdcec  ldstr    aCalendarViewLa// "Calendar_View_Label_Week"
0xdcf1  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xdcf6  callvirt instance void [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormControlBase::AddExpando(string, string)
0xdcfb  ldloc.s  6
0xdcfd  ldloc.s  8
0xdcff  ldstr    aMsCrmRecurrenc_0// "ms-crm-recurrence-dialog-Picklist"
0xdd04  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.LocalizableOptionControl::AddControl(class [System.Web]System.Web.UI.Control, string)
0xdd09  ldloc.s  6
0xdd0b  ldloc.s  9
0xdd0d  ldstr    aMsCrmRecurrenc_0// "ms-crm-recurrence-dialog-Picklist"
0xdd12  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.LocalizableOptionControl::AddControl(class [System.Web]System.Web.UI.Control, string)
0xdd17  ldloc.s  6
0xdd19  ldloc.s  7
0xdd1b  ldstr    aMsCrmRecurrenc// "ms-crm-recurrence-dialog-Number"
0xdd20  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.LocalizableOptionControl::AddControl(class [System.Web]System.Web.UI.Control, string)
0xdd25  ldloc.0
0xdd26  ldc.i4.1
0xdd27  ldloc.2
0xdd28  ldc.i4.0
0xdd29  newarr   [System.Web]System.Web.UI.Control
0xdd2e  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.PatternContainer::AddControls(int32, class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.LocalizableOptionControl, class [System.Web]System.Web.UI.Control[])
0xdd33  ldloc.0
0xdd34  ldc.i4.2
0xdd35  ldloc.s  6
0xdd37  ldc.i4.0
0xdd38  newarr   [System.Web]System.Web.UI.Control
0xdd3d  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.PatternContainer::AddControls(int32, class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.LocalizableOptionControl, class [System.Web]System.Web.UI.Control[])
0xdd42  ldloc.0
0xdd43  ldc.i4.1
0xdd44  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.PatternContainer::set_CheckedOption(int32)
0xdd49  ret
```
