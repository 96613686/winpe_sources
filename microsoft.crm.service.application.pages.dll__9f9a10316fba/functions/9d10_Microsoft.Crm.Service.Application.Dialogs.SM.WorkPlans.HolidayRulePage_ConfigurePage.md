# Microsoft.Crm.Service.Application.Dialogs.SM.WorkPlans.HolidayRulePage::ConfigurePage

- ea: `0x9d10`
- end: `0x9f4f`
- name: `Microsoft.Crm.Service.Application.Dialogs.SM.WorkPlans.HolidayRulePage::ConfigurePage`
- size: `575`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x9d10`
- `0xbff0`
- `0xc060`
- `0xc0d0`
- `0xc120`
- `0xc130`
- `0xc140`
- `0xc150`
- `0xc440`
- `0xc4c0`

## string_xrefs

- `0x9e27`: `/_static/_common/styles/AutoToolTip.js`

## pseudocode

```c

```

## disassembly

```asm
0x9d10  ldarg.0
0x9d11  ldstr    aCalendar// "calendar"
0x9d16  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x9d1b  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x9d20  newobj   instance void [Microsoft.Crm.Service.Application.Components.Platform]Microsoft.Crm.Service.Application.Platform.Calendar::.ctor(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType)
0x9d25  call     instance void Microsoft.Crm.Service.Application.Dialogs.SM.WorkPlans.WorkCalendarRuleBase::set_FormEntity(class [Microsoft.Crm.Service.Application.Components.Platform]Microsoft.Crm.Service.Application.Platform.Calendar value)
0x9d2a  ldarg.0
0x9d2b  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x9d30  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x9d35  ldstr    aCtype// "cType"
0x9d3a  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x9d3f  brfalse.s loc_9D61
0x9d41  ldarg.0
0x9d42  ldarg.0
0x9d43  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x9d48  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x9d4d  ldstr    aCtype// "cType"
0x9d52  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x9d57  callvirt instance string [mscorlib]System.Object::ToString()
0x9d5c  call     instance void Microsoft.Crm.Service.Application.Dialogs.SM.WorkPlans.WorkCalendarRuleBase::set_CalendarType(string value)
0x9d61  ldarg.0
0x9d62  call     instance string Microsoft.Crm.Service.Application.Dialogs.SM.WorkPlans.WorkCalendarRuleBase::get_CalendarType()
0x9d67  ldstr    aHs// "hs"
0x9d6c  call     bool [mscorlib]System.String::op_Equality(string, string)
0x9d71  brfalse.s loc_9D8D
0x9d73  ldarg.0
0x9d74  call     instance class [Microsoft.Crm.Service.Application.Components.Platform]Microsoft.Crm.Service.Application.Platform.Calendar Microsoft.Crm.Service.Application.Dialogs.SM.WorkPlans.WorkCalendarRuleBase::get_FormEntity()
0x9d79  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x9d7e  call     bool [Microsoft.Crm.Service.Application.Components.Platform]Microsoft.Crm.Service.Application.SMWorkPlans::CurrentUserPrivilegedToCreateHolidayClosures(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x9d83  ldc.i4.0
0x9d84  ceq
0x9d86  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::set_Disabled(bool)
0x9d8b  br.s     loc_9DA5
0x9d8d  ldarg.0
0x9d8e  call     instance class [Microsoft.Crm.Service.Application.Components.Platform]Microsoft.Crm.Service.Application.Platform.Calendar Microsoft.Crm.Service.Application.Dialogs.SM.WorkPlans.WorkCalendarRuleBase::get_FormEntity()
0x9d93  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x9d98  call     bool [Microsoft.Crm.Service.Application.Components.Platform]Microsoft.Crm.Service.Application.SMWorkPlans::CurrentUserPrivilegedToCreateBusinessClosures(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x9d9d  ldc.i4.0
0x9d9e  ceq
0x9da0  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::set_Disabled(bool)
0x9da5  ldarg.0
0x9da6  ldarg.0
0x9da7  call     instance class [Microsoft.Crm.Service.Application.Components.Platform]Microsoft.Crm.Service.Application.Platform.Calendar Microsoft.Crm.Service.Application.Dialogs.SM.WorkPlans.WorkCalendarRuleBase::get_FormEntity()
0x9dac  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_EntityType()
0x9db1  call     instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::set_CurrentType(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType)
0x9db6  ldarg.0
0x9db7  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::crmForm
0x9dbc  isinst   [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm
0x9dc1  dup
0x9dc2  ldc.i4.s 0x20
0x9dc4  ldstr    aButtonLabelHel// "Button_Label_Help"
0x9dc9  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::AddButton(valuetype [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogButtonStyles, string)
0x9dce  ldc.i4   0x12C
0x9dd3  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppControl::set_MinWidth(int32)
0x9dd8  ldarg.0
0x9dd9  ldarg.0
0x9dda  ldstr    aResourceid// "resourceId"
0x9ddf  call     instance string Microsoft.Crm.Service.Application.Dialogs.SM.WorkPlans.WorkCalendarRuleBase::AssignStringQueryStringGuid(string parameter)
0x9de4  call     instance void Microsoft.Crm.Service.Application.Dialogs.SM.WorkPlans.WorkCalendarRuleBase::set_ResourceId(string value)
0x9de9  ldarg.0
0x9dea  ldarg.0
0x9deb  ldstr    aCalendarid// "calendarId"
0x9df0  call     instance string Microsoft.Crm.Service.Application.Dialogs.SM.WorkPlans.WorkCalendarRuleBase::AssignStringQueryStringGuid(string parameter)
0x9df5  call     instance void Microsoft.Crm.Service.Application.Dialogs.SM.WorkPlans.WorkCalendarRuleBase::set_CalendarId(string value)
0x9dfa  ldarg.0
0x9dfb  ldarg.0
0x9dfc  ldstr    aId_0// "Id"
0x9e01  call     instance string Microsoft.Crm.Service.Application.Dialogs.SM.WorkPlans.WorkCalendarRuleBase::AssignStringQueryStringGuid(string parameter)
0x9e06  call     instance void Microsoft.Crm.Service.Application.Dialogs.SM.WorkPlans.WorkCalendarRuleBase::set_CalendarRuleId(string value)
0x9e0b  ldarg.0
0x9e0c  callvirt instance void Microsoft.Crm.Service.Application.Dialogs.SM.WorkPlans.WorkCalendarRuleBase::InitDialog()
0x9e11  ldarg.0
0x9e12  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x9e17  ldstr    aStaticControls_6// "/_static/_controls/startendduration/sta"...
0x9e1c  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x9e21  ldarg.0
0x9e22  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x9e27  ldstr    aStaticCommonSt// "/_static/_common/styles/AutoToolTip.js"
0x9e2c  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x9e31  ldarg.0
0x9e32  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x9e37  ldstr    aScheduleplanni// "SchedulePlanning"
0x9e3c  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::AddWrpcTokenActionPathWebService(string)
0x9e41  ldarg.0
0x9e42  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x9e47  ldstr    aLocidNameTooLo// "LOCID_NAME_TOO_LONG"
0x9e4c  ldarg.0
0x9e4d  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x9e52  ldstr    aWebSmWorkplans// "Web.SM.WorkPlans.Dialogs.timeoff.aspx__"...
0x9e57  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x9e5c  ldc.i4.0
0x9e5d  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x9e62  ldarg.0
0x9e63  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x9e68  ldstr    aLocidNameTooSh// "LOCID_NAME_TOO_SHORT"
0x9e6d  ldarg.0
0x9e6e  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x9e73  ldstr    aWebSmWorkplans_0// "Web.SM.WorkPlans.Dialogs.holiday.aspx__"...
0x9e78  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x9e7d  ldc.i4.0
0x9e7e  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x9e83  ldarg.0
0x9e84  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x9e89  ldstr    aLocidMerge0x80// "LOCID_MERGE_0X8004F873"
0x9e8e  ldarg.0
0x9e8f  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x9e94  ldstr    aErrorMessage0x_0// "Error_Message_0x8004f873"
0x9e99  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x9e9e  ldc.i4.0
0x9e9f  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x9ea4  ldarg.0
0x9ea5  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x9eaa  ldstr    aMscrmAutotoolt// "Mscrm.AutoToolTip"
0x9eaf  ldstr    aNamelabel// "nameLabel"
0x9eb4  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::CreateClientAjaxComponent(string, string)
0x9eb9  ldarg.0
0x9eba  call     instance string Microsoft.Crm.Service.Application.Dialogs.SM.WorkPlans.WorkCalendarRuleBase::get_CalendarType()
0x9ebf  stloc.1
0x9ec0  ldloc.1
0x9ec1  ldstr    aBc// "bc"
0x9ec6  call     bool [mscorlib]System.String::op_Equality(string, string)
0x9ecb  brtrue.s loc_9EDC
0x9ecd  ldloc.1
0x9ece  ldstr    aHs// "hs"
0x9ed3  call     bool [mscorlib]System.String::op_Equality(string, string)
0x9ed8  brtrue.s loc_9EFB
0x9eda  br.s     loc_9F18
0x9edc  ldarg.0
0x9edd  callvirt instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppNotifications [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_Notifications()
0x9ee2  ldc.i4.3
0x9ee3  ldarg.0
0x9ee4  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x9ee9  ldstr    aDialogsHoliday// "Dialogs_Holiday_Notification"
0x9eee  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x9ef3  ldc.i4.0
0x9ef4  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppNotifications::AddNotification(int32, string, bool)
0x9ef9  br.s     loc_9F18
0x9efb  ldarg.0
0x9efc  callvirt instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppNotifications [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_Notifications()
0x9f01  ldc.i4.3
0x9f02  ldarg.0
0x9f03  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x9f08  ldstr    aDialogsHoliday_0// "Dialogs_Holiday_Calendar_Notification"
0x9f0d  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x9f12  ldc.i4.0
0x9f13  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppNotifications::AddNotification(int32, string, bool)
0x9f18  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x9f1d  ldstr    aRequiredFields// "Required_Fields_Background_Color"
0x9f22  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x9f27  stloc.0
0x9f28  ldloc.0
0x9f29  brfalse.s loc_9F4E
0x9f2b  ldloc.0
0x9f2c  callvirt instance int32 [mscorlib]System.String::get_Length()
0x9f31  brfalse.s loc_9F4E
0x9f33  ldarg.0
0x9f34  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.TextBox Microsoft.Crm.Service.Application.Dialogs.SM.WorkPlans.HolidayRulePage::name
0x9f39  ldstr    aStyle// "Style"
0x9f3e  ldstr    aBackgroundColo// "background-color:"
0x9f43  ldloc.0
0x9f44  call     string [mscorlib]System.String::Concat(string, string)
0x9f49  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControl::AddExpando(string, string)
0x9f4e  ret
```
