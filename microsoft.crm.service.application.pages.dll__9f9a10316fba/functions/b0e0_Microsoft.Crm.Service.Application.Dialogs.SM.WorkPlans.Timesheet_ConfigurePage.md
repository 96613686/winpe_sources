# Microsoft.Crm.Service.Application.Dialogs.SM.WorkPlans.Timesheet::ConfigurePage

- ea: `0xb0e0`
- end: `0xb255`
- name: `Microsoft.Crm.Service.Application.Dialogs.SM.WorkPlans.Timesheet::ConfigurePage`
- size: `373`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0xb0e0`
- `0xbf90`
- `0xbfb0`
- `0xbff0`
- `0xc060`
- `0xc090`
- `0xc0d0`
- `0xc160`
- `0xc4c0`

## pseudocode

```c

```

## disassembly

```asm
0xb0e0  ldarg.0
0xb0e1  call     instance void Microsoft.Crm.Service.Application.Dialogs.SM.WorkPlans.WorkCalendarRuleBase::ConfigurePage()
0xb0e6  ldarg.0
0xb0e7  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xb0ec  ldstr    aSmWorkplansDia// "/sm/workplans/dialogs/workplaningdialog"...
0xb0f1  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0xb0f6  ldarg.0
0xb0f7  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xb0fc  ldstr    aScheduleplanni// "SchedulePlanning"
0xb101  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::AddWrpcTokenActionPathWebService(string)
0xb106  ldarg.0
0xb107  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xb10c  ldstr    aLocidHideCapac// "LOCID_HIDE_CAPACITY"
0xb111  ldarg.0
0xb112  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xb117  ldstr    aSmHideCapacity// "SM_Hide_Capacity"
0xb11c  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xb121  ldc.i4.0
0xb122  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xb127  ldarg.0
0xb128  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xb12d  ldstr    aLocidShowCapac// "LOCID_SHOW_CAPACITY"
0xb132  ldarg.0
0xb133  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xb138  ldstr    aSmShowCapacity// "SM_Show_Capacity"
0xb13d  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xb142  ldc.i4.0
0xb143  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xb148  ldstr    aCalendar// "calendar"
0xb14d  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xb152  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xb157  newobj   instance void [Microsoft.Crm.Service.Application.Components.Platform]Microsoft.Crm.Service.Application.Platform.Calendar::.ctor(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType)
0xb15c  stloc.0
0xb15d  ldarg.0
0xb15e  ldloc.0
0xb15f  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_EntityType()
0xb164  call     instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::set_CurrentType(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType)
0xb169  ldarg.0
0xb16a  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::crmForm
0xb16f  isinst   [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm
0xb174  dup
0xb175  ldc.i4.0
0xb176  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::set_ButtonStyle(valuetype [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogButtonStyles)
0xb17b  dup
0xb17c  ldc.i4.1
0xb17d  ldstr    aButtonLabelOk// "Button_Label_OK"
0xb182  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::AddButton(valuetype [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogButtonStyles, string)
0xb187  dup
0xb188  ldc.i4.2
0xb189  ldstr    aButtonLabelCan// "Button_Label_Cancel"
0xb18e  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::AddButton(valuetype [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogButtonStyles, string)
0xb193  ldc.i4.s 0x20
0xb195  ldstr    aButtonLabelHel// "Button_Label_Help"
0xb19a  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::AddButton(valuetype [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogButtonStyles, string)
0xb19f  ldarg.0
0xb1a0  ldarg.0
0xb1a1  ldstr    aResourceid// "resourceId"
0xb1a6  call     instance string Microsoft.Crm.Service.Application.Dialogs.SM.WorkPlans.WorkCalendarRuleBase::AssignStringQueryStringGuid(string parameter)
0xb1ab  call     instance void Microsoft.Crm.Service.Application.Dialogs.SM.WorkPlans.WorkCalendarRuleBase::set_ResourceId(string value)
0xb1b0  ldarg.0
0xb1b1  ldarg.0
0xb1b2  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0xb1b7  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0xb1bc  ldstr    aCalendartype// "calendarType"
0xb1c1  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0xb1c6  stfld    string Microsoft.Crm.Service.Application.Dialogs.SM.WorkPlans.Timesheet::calendarType
0xb1cb  ldarg.0
0xb1cc  ldarg.0
0xb1cd  call     instance string Microsoft.Crm.Service.Application.Dialogs.SM.WorkPlans.WorkCalendarRuleBase::get_ResourceId()
0xb1d2  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xb1d7  ldarg.0
0xb1d8  call     instance int32 Microsoft.Crm.Service.Application.Dialogs.SM.WorkPlans.WorkCalendarRuleBase::get_ObjectTypeCode()
0xb1dd  call     string [Microsoft.Crm.Service.Application.Components.Platform]Microsoft.Crm.Service.Application.SMWorkPlans::FindOrCreateResourceCalendar(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext, int32)
0xb1e2  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0xb1e7  stfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Service.Application.Dialogs.SM.WorkPlans.Timesheet::outerCalendarId
0xb1ec  ldarg.0
0xb1ed  ldarg.0
0xb1ee  ldstr    aId_0// "Id"
0xb1f3  call     instance string Microsoft.Crm.Service.Application.Dialogs.SM.WorkPlans.WorkCalendarRuleBase::AssignStringQueryStringGuid(string parameter)
0xb1f8  call     instance void Microsoft.Crm.Service.Application.Dialogs.SM.WorkPlans.WorkCalendarRuleBase::set_CalendarId(string value)
0xb1fd  ldarg.0
0xb1fe  ldarg.0
0xb1ff  ldstr    aId_0// "Id"
0xb204  call     instance string Microsoft.Crm.Service.Application.Dialogs.SM.WorkPlans.WorkCalendarRuleBase::AssignStringQueryStringGuid(string parameter)
0xb209  call     instance void Microsoft.Crm.Service.Application.Dialogs.SM.WorkPlans.WorkCalendarRuleBase::set_CalendarRuleId(string value)
0xb20e  ldarg.0
0xb20f  call     instance string Microsoft.Crm.Service.Application.Dialogs.SM.WorkPlans.WorkCalendarRuleBase::get_CalendarRuleId()
0xb214  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0xb219  brtrue.s loc_B254
0xb21b  ldarg.0
0xb21c  call     instance string Microsoft.Crm.Service.Application.Dialogs.SM.WorkPlans.WorkCalendarRuleBase::get_CalendarRuleId()
0xb221  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0xb226  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0xb22b  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0xb230  brfalse.s loc_B254
0xb232  ldarg.0
0xb233  ldarg.0
0xb234  ldstr    aCalendarid_1// "calendarid"
0xb239  call     instance string Microsoft.Crm.Service.Application.Dialogs.SM.WorkPlans.WorkCalendarRuleBase::AssignStringQueryStringGuid(string parameter)
0xb23e  call     instance void Microsoft.Crm.Service.Application.Dialogs.SM.WorkPlans.WorkCalendarRuleBase::set_CalendarId(string value)
0xb243  ldarg.0
0xb244  ldarg.0
0xb245  ldstr    aId_0// "Id"
0xb24a  call     instance string Microsoft.Crm.Service.Application.Dialogs.SM.WorkPlans.WorkCalendarRuleBase::AssignStringQueryStringGuid(string parameter)
0xb24f  call     instance void Microsoft.Crm.Service.Application.Dialogs.SM.WorkPlans.WorkCalendarRuleBase::set_CalendarRuleId(string value)
0xb254  ret
```
