# Microsoft.Crm.Common.Web.Activities.Dialogs.RecurrenceDialog::ConfigureHeader

- ea: `0xd410`
- end: `0xd867`
- name: `Microsoft.Crm.Common.Web.Activities.Dialogs.RecurrenceDialog::ConfigureHeader`
- size: `1111`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config, service_task, broker_com_uri`

## string_xrefs

- `0xd85c`: `ActivitiesWebService`
- `0xd80c`: `_syncCreateMax`

## pseudocode

```c

```

## disassembly

```asm
0xd410  ldarg.0
0xd411  call     instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.DialogBase::ConfigureHeader()
0xd416  ldarg.0
0xd417  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xd41c  ldstr    aActivitiesActD// "/activities/act_dlgs/recurrenceDialog.c"...
0xd421  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0xd426  ldarg.0
0xd427  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xd42c  ldarg.0
0xd42d  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xd432  ldstr    aRecurrencerule// "RecurrenceRule.Dialog.Title"
0xd437  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xd43c  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::set_Title(string)
0xd441  ldarg.0
0xd442  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xd447  ldstr    aLocidRdialogIn// "LOCID_RDIALOG_INVALID_ENDDATE"
0xd44c  ldarg.0
0xd44d  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xd452  ldstr    aRecurrencerule_0// "RecurrenceRule.Dialog.Errors.InvalidEnd"...
0xd457  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xd45c  ldc.i4.0
0xd45d  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xd462  ldarg.0
0xd463  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xd468  ldstr    aLocidRdialogFe// "LOCID_RDIALOG_FEB29_WARN"
0xd46d  ldarg.0
0xd46e  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xd473  ldstr    aRecurrencerule_1// "RecurrenceRule.Dialog.Feb29Warn"
0xd478  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xd47d  ldc.i4.0
0xd47e  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xd483  ldarg.0
0xd484  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xd489  ldstr    aLocidRdialogIn_0// "LOCID_RDIALOG_INVALID_RPAT"
0xd48e  ldarg.0
0xd48f  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xd494  ldstr    aErrorMessage0x_2// "Error_Message_0x8004e100"
0xd499  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xd49e  ldc.i4.0
0xd49f  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xd4a4  ldarg.0
0xd4a5  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xd4aa  ldstr    aLocidRdialogIn_1// "LOCID_RDIALOG_INVALID_STARTDATE"
0xd4af  ldarg.0
0xd4b0  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xd4b5  ldstr    aRecurrencerule_2// "RecurrenceRule.Dialog.Errors.InvalidSta"...
0xd4ba  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xd4bf  ldc.i4.0
0xd4c0  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xd4c5  ldarg.0
0xd4c6  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xd4cb  ldstr    aLocidRdialogIn_2// "LOCID_RDIALOG_INVALID_INSTANCES"
0xd4d0  ldarg.0
0xd4d1  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xd4d6  ldstr    aRecurrencerule_3// "RecurrenceRule.Dialog.Errors.NoInstance"...
0xd4db  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xd4e0  ldc.i4.0
0xd4e1  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xd4e6  ldarg.0
0xd4e7  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xd4ec  ldstr    aLocidRdialogIn_3// "LOCID_RDIALOG_INVALID_DURATION"
0xd4f1  ldarg.0
0xd4f2  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xd4f7  ldstr    aRecurrencerule_4// "RecurrenceRule.Dialog.Errors.InvalidDur"...
0xd4fc  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xd501  ldc.i4.0
0xd502  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xd507  ldarg.0
0xd508  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xd50d  ldstr    aLocidRdialogIn_4// "LOCID_RDIALOG_INVALID_NUMBER"
0xd512  ldarg.0
0xd513  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xd518  ldstr    aRecurrencerule_5// "RecurrenceRule.Dialog.Errors.InvalidNum"...
0xd51d  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xd522  ldc.i4.0
0xd523  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xd528  ldarg.0
0xd529  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xd52e  ldstr    aLocidRdialogIn_5// "LOCID_RDIALOG_INVALID_NUMBER2"
0xd533  ldarg.0
0xd534  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xd539  ldstr    aRecurrencerule_6// "RecurrenceRule.Dialog.Errors.InvalidNum"...
0xd53e  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xd543  ldc.i4.0
0xd544  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xd549  ldarg.0
0xd54a  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xd54f  ldstr    aLocidRdialogIn_6// "LOCID_RDIALOG_INVALID_MONTH"
0xd554  ldarg.0
0xd555  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xd55a  ldstr    aRecurrencerule_7// "RecurrenceRule.Dialog.Errors.InvalidMon"...
0xd55f  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xd564  ldc.i4.0
0xd565  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xd56a  ldarg.0
0xd56b  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xd570  ldstr    aLocidRdialogMo// "LOCID_RDIALOG_MONTHWARN"
0xd575  ldarg.0
0xd576  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xd57b  ldstr    aRecurrencerule_8// "RecurrenceRule.Dialog.Errors.MonthWarn"
0xd580  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xd585  ldc.i4.0
0xd586  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xd58b  ldarg.0
0xd58c  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xd591  ldstr    aLocidRdialogSt// "LOCID_RDIALOG_STARTDTERROR"
0xd596  ldarg.0
0xd597  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xd59c  ldstr    aRecurrencerule_9// "RecurrenceRule.Dialog.Errors.StartDateR"...
0xd5a1  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xd5a6  ldc.i4.0
0xd5a7  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xd5ac  ldarg.0
0xd5ad  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xd5b2  ldstr    aLocidRdialogSt_0// "LOCID_RDIALOG_STDTLESSTHANTODY"
0xd5b7  ldarg.0
0xd5b8  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xd5bd  ldstr    aRecurrencerule_10// "RecurrenceRule.Dialog.Errors.StartDateI"...
0xd5c2  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xd5c7  ldc.i4.0
0xd5c8  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xd5cd  ldarg.0
0xd5ce  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xd5d3  ldstr    aLocidRdialogEn// "LOCID_RDIALOG_ENDDTLESSTHANTODY"
0xd5d8  ldarg.0
0xd5d9  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xd5de  ldstr    aRecurrencerule_11// "RecurrenceRule.Dialog.Errors.EndDateIsL"...
0xd5e3  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xd5e8  ldc.i4.0
0xd5e9  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xd5ee  ldarg.0
0xd5ef  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xd5f4  ldstr    aLocidRdialogSe// "LOCID_RDIALOG_SERIESDLG_WIDTH"
0xd5f9  ldarg.0
0xd5fa  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xd5ff  ldstr    aActivitiesActD_0// "activities/act_dlgs/dlg_seriesaction.as"...
0xd604  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xd609  ldc.i4.0
0xd60a  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xd60f  ldarg.0
0xd610  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xd615  ldstr    aLocidRdialogSe_0// "LOCID_RDIALOG_SERIESDLG_HEIGHT"
0xd61a  ldarg.0
0xd61b  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xd620  ldstr    aActivitiesActD_1// "activities/act_dlgs/dlg_seriesaction.as"...
0xd625  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xd62a  ldc.i4.0
0xd62b  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xd630  ldarg.0
0xd631  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xd636  ldstr    aLocidEndseries// "LOCID_ENDSERIESDLG_WIDTH"
0xd63b  ldarg.0
0xd63c  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xd641  ldstr    aActivitiesActD_2// "activities/act_dlgs/dlg_seriesaction.as"...
0xd646  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xd64b  ldc.i4.0
0xd64c  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xd651  ldarg.0
0xd652  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xd657  ldstr    aLocidEndseries_0// "LOCID_ENDSERIESDLG_HEIGHT"
0xd65c  ldarg.0
0xd65d  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xd662  ldstr    aActivitiesActD_3// "activities/act_dlgs/dlg_seriesaction.as"...
0xd667  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xd66c  ldc.i4.0
0xd66d  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xd672  ldarg.0
0xd673  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xd678  ldstr    aLocidServerMax// "LOCID_SERVER_MAX_INSTANCE_WARN"
0xd67d  ldarg.0
0xd67e  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xd683  ldstr    aRecurringInsta// "Recurring_Instance_CreationWarn"
0xd688  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xd68d  ldc.i4.1
0xd68e  newarr   [mscorlib]System.Object
0xd693  dup
0xd694  ldc.i4.0
0xd695  ldarg.0
0xd696  ldfld    int32 Microsoft.Crm.Common.Web.Activities.Dialogs.RecurrenceDialog::_syncCreateMax
0xd69b  box      [mscorlib]System.Int32
0xd6a0  stelem.ref
0xd6a1  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext, object[])
0xd6a6  ldc.i4.0
0xd6a7  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xd6ac  ldarg.0
0xd6ad  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xd6b2  ldstr    aStaticControls_8// "/_static/_controls/startendduration/sta"...
0xd6b7  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0xd6bc  ldarg.0
0xd6bd  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xd6c2  ldstr    aStaticActiviti// "/_static/activities/recurrencedialog/re"...
0xd6c7  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0xd6cc  ldarg.0
0xd6cd  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xd6d2  ldstr    aStaticActiviti_0// "/_static/activities/recurrenceutil/recu"...
0xd6d7  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0xd6dc  ldarg.0
0xd6dd  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xd6e2  ldstr    aInitialization// "Initialization"
0xd6e7  ldstr    aMscrmRecurrenc// "Mscrm.RecurrenceDialog.initialize();"
0xd6ec  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptBlockForOnLoad(string, string)
0xd6f1  ldarg.0
0xd6f2  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xd6f7  ldstr    aBisnew// "_bIsNew"
0xd6fc  ldarg.0
0xd6fd  ldfld    int32 Microsoft.Crm.Common.Web.Activities.Dialogs.RecurrenceDialog::loadDefaults
0xd702  ldc.i4.1
0xd703  ceq
0xd705  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, bool)
0xd70a  ldarg.0
0xd70b  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xd710  ldstr    aDialogdisabled// "_dialogDisabled"
0xd715  ldarg.0
0xd716  ldfld    bool Microsoft.Crm.Common.Web.Activities.Dialogs.RecurrenceDialog::enableEndSeries
0xd71b  ldc.i4.0
0xd71c  ceq
0xd71e  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, bool)
0xd723  ldarg.0
0xd724  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xd729  ldstr    aEntityid// "_entityId"
0xd72e  ldarg.0
0xd72f  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Common.Web.Activities.Dialogs.RecurrenceDialog::entityId
0xd734  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, valuetype [mscorlib]System.Guid)
0xd739  ldarg.0
0xd73a  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xd73f  ldstr    aEntitytypecode// "_entityTypeCode"
0xd744  ldarg.0
0xd745  ldfld    int32 Microsoft.Crm.Common.Web.Activities.Dialogs.RecurrenceDialog::objectTypeCode
0xd74a  conv.i8
0xd74b  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, int64)
0xd750  ldarg.0
0xd751  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xd756  ldstr    aWeekdays// "_weekDays"
0xd75b  ldarg.0
0xd75c  ldfld    int32 Microsoft.Crm.Common.Web.Activities.Dialogs.RecurrenceDialog::_weekDays
0xd761  conv.i8
0xd762  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, int64)
0xd767  ldarg.0
0xd768  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xd76d  ldstr    aSallowblankdat// "_sAllowBlankDate"
0xd772  ldstr    a0// "0"
0xd777  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, string)
0xd77c  ldarg.0
0xd77d  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xd782  ldstr    aWeekenddays// "_weekEndDays"
0xd787  ldarg.0
0xd788  ldfld    int32 Microsoft.Crm.Common.Web.Activities.Dialogs.RecurrenceDialog::_weekEndDays
0xd78d  conv.i8
0xd78e  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, int64)
0xd793  ldarg.0
0xd794  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xd799  ldstr    aCurrentmonth// "_currentMonth"
0xd79e  ldarg.0
0xd79f  ldfld    int32 Microsoft.Crm.Common.Web.Activities.Dialogs.RecurrenceDialog::_currentMonth
0xd7a4  conv.i8
0xd7a5  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, int64)
0xd7aa  ldarg.0
0xd7ab  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xd7b0  ldstr    aMaxdaysinmonth// "_maxDaysInMonth"
0xd7b5  ldarg.0
0xd7b6  ldfld    int32 Microsoft.Crm.Common.Web.Activities.Dialogs.RecurrenceDialog::_maxDaysInMonth
0xd7bb  conv.i8
0xd7bc  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, int64)
0xd7c1  ldarg.0
0xd7c2  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xd7c7  ldstr    aMindaysinmonth// "_minDaysInMonth"
0xd7cc  ldarg.0
0xd7cd  ldfld    int32 Microsoft.Crm.Common.Web.Activities.Dialogs.RecurrenceDialog::_minDaysInMonth
0xd7d2  conv.i8
0xd7d3  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, int64)
0xd7d8  ldarg.0
0xd7d9  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xd7de  ldstr    aFutureexpansio// "_futureExpansionWindow"
0xd7e3  ldarg.0
0xd7e4  ldfld    int32 Microsoft.Crm.Common.Web.Activities.Dialogs.RecurrenceDialog::_futureExpansionWindow
0xd7e9  conv.i8
0xd7ea  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, int64)
0xd7ef  ldarg.0
0xd7f0  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xd7f5  ldstr    aPastexpansionw// "_pastExpansionWindow"
0xd7fa  ldarg.0
0xd7fb  ldfld    int32 Microsoft.Crm.Common.Web.Activities.Dialogs.RecurrenceDialog::_pastExpansionWindow
0xd800  conv.i8
0xd801  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, int64)
0xd806  ldarg.0
0xd807  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xd80c  ldstr    aSynccreatemax// "_syncCreateMax"
0xd811  ldarg.0
0xd812  ldfld    int32 Microsoft.Crm.Common.Web.Activities.Dialogs.RecurrenceDialog::_syncCreateMax
0xd817  conv.i8
0xd818  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, int64)
0xd81d  ldarg.0
0xd81e  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xd823  ldstr    aDefaultrecurre// "_defaultRecurrenceEndRangeType"
0xd828  ldarg.0
0xd829  ldfld    int32 Microsoft.Crm.Common.Web.Activities.Dialogs.RecurrenceDialog::_defaultRecurrenceEndRangeType
0xd82e  conv.i8
0xd82f  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, int64)
0xd834  ldarg.0
0xd835  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
  ... truncated ...
```
