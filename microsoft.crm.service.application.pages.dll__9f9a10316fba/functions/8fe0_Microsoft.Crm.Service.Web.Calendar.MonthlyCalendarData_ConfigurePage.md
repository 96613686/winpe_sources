# Microsoft.Crm.Service.Web.Calendar.MonthlyCalendarData::ConfigurePage

- ea: `0x8fe0`
- end: `0x91b4`
- name: `Microsoft.Crm.Service.Web.Calendar.MonthlyCalendarData::ConfigurePage`
- size: `468`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x82d0`
- `0x82f0`
- `0x89e0`
- `0x8fe0`

## pseudocode

```c

```

## disassembly

```asm
0x8fe0  ldarg.0
0x8fe1  ldfld    class [Microsoft.Crm.Service.Application.Components.Application]Microsoft.Crm.Service.Application.Controls.AppMonthCalendar Microsoft.Crm.Service.Web.Calendar.MonthlyCalendarData::crmMonthlyCalendar
0x8fe6  callvirt instance valuetype [mscorlib]System.DateTime [Microsoft.Crm.Service.Application.Components.Application]Microsoft.Crm.Service.Application.Controls.AppMonthCalendar::get_FirstDisplayDate()
0x8feb  stloc.0
0x8fec  ldloca.s 0
0x8fee  ldarg.0
0x8fef  ldfld    class [Microsoft.Crm.Service.Application.Components.Application]Microsoft.Crm.Service.Application.Controls.AppMonthCalendar Microsoft.Crm.Service.Web.Calendar.MonthlyCalendarData::crmMonthlyCalendar
0x8ff4  callvirt instance int32 [Microsoft.Crm.Service.Application.Components.Application]Microsoft.Crm.Service.Application.Controls.AppMonthCalendar::get_DaysInMonthlyCalendar()
0x8ff9  conv.r8
0x8ffa  call     instance valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::AddDays(float64)
0x8fff  stloc.1
0x9000  ldarg.0
0x9001  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentUser()
0x9006  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser::get_SystemUserId()
0x900b  ldloc.0
0x900c  ldloc.1
0x900d  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ApplicationEntityCollection Microsoft.Crm.Service.Web.Calendar.CalendarPageHelper::RetrieveActivitiesForCalendar(valuetype [mscorlib]System.Guid partyId, valuetype [mscorlib]System.DateTime start, valuetype [mscorlib]System.DateTime end)
0x9012  stloc.2
0x9013  ldc.i4.2
0x9014  newarr   [mscorlib]System.String
0x9019  dup
0x901a  ldc.i4.0
0x901b  ldstr    aSystemuserid// "systemuserid"
0x9020  stelem.ref
0x9021  dup
0x9022  ldc.i4.1
0x9023  ldstr    aCalendarid_1// "calendarid"
0x9028  stelem.ref
0x9029  stloc.3
0x902a  ldstr    aSystemuser// "systemuser"
0x902f  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.User::get_Current()
0x9034  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser::get_SystemUserId()
0x9039  ldloc.3
0x903a  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x903f  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.DataSource::Retrieve(string, valuetype [mscorlib]System.Guid, string[], class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x9044  ldstr    aCalendarid_1// "calendarid"
0x9049  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0x904e  castclass [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.LookupValue
0x9053  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.LookupValue::get_ID()
0x9058  stloc.s  4
0x905a  ldnull
0x905b  stloc.s  5
0x905d  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x9062  call     bool [Microsoft.Crm.Service.Application.Components.Platform]Microsoft.Crm.Service.Application.SMWorkPlans::CurrentUserPrivilegedToReadCalendar(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x9067  brfalse.s loc_908B
0x9069  ldloc.s  4
0x906b  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x9070  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x9075  call     class [Microsoft.Crm.Service.Application.Components.Platform]Microsoft.Crm.Service.Application.Platform.Calendar [Microsoft.Crm.Service.Application.Components.Platform]Microsoft.Crm.Service.Application.SMWorkPlans::RetrieveCalendar(valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x907a  stloc.s  5
0x907c  ldarg.0
0x907d  ldloc.0
0x907e  ldloc.1
0x907f  ldloc.s  5
0x9081  call     valuetype [Microsoft.Crm.Core.Extensions]Microsoft.Crm.Scheduling.TimeBlock[] Microsoft.Crm.Service.Web.Calendar.CalendarPageHelper::ExpandCalendar(valuetype [mscorlib]System.DateTime startDate, valuetype [mscorlib]System.DateTime endDate, class [Microsoft.Crm.Service.Application.Components.Platform]Microsoft.Crm.Service.Application.Platform.Calendar calendar)
0x9086  stfld    valuetype [Microsoft.Crm.Core.Extensions]Microsoft.Crm.Scheduling.TimeBlock[] Microsoft.Crm.Service.Web.Calendar.MonthlyCalendarData::_timeBlocks
0x908b  ldarg.0
0x908c  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppDateNavigationBar Microsoft.Crm.Service.Web.Calendar.MonthlyCalendarData::crmDateNavBar
0x9091  ldc.i4.1
0x9092  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.DateNavigationBar::set_DateIncrement(int32)
0x9097  ldarg.0
0x9098  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppDateNavigationBar Microsoft.Crm.Service.Web.Calendar.MonthlyCalendarData::crmDateNavBar
0x909d  ldarg.0
0x909e  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x90a3  ldstr    aSmPrevMonth// "SM_Prev_Month"
0x90a8  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x90ad  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.DateNavigationBar::set_PrevToolTip(string)
0x90b2  ldarg.0
0x90b3  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppDateNavigationBar Microsoft.Crm.Service.Web.Calendar.MonthlyCalendarData::crmDateNavBar
0x90b8  ldarg.0
0x90b9  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x90be  ldstr    aSmNextMonth// "SM_Next_Month"
0x90c3  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x90c8  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.DateNavigationBar::set_NextToolTip(string)
0x90cd  ldarg.0
0x90ce  ldarg.0
0x90cf  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x90d4  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x90d9  ldstr    aOid// "oId"
0x90de  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x90e3  stfld    string Microsoft.Crm.Service.Web.Calendar.MonthlyCalendarData::_oId
0x90e8  ldarg.0
0x90e9  ldfld    string Microsoft.Crm.Service.Web.Calendar.MonthlyCalendarData::_oId
0x90ee  brtrue.s loc_9106
0x90f0  ldarg.0
0x90f1  ldarg.0
0x90f2  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentUser()
0x90f7  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser::get_SystemUserId()
0x90fc  call     string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::GuidToString(valuetype [mscorlib]System.Guid)
0x9101  stfld    string Microsoft.Crm.Service.Web.Calendar.MonthlyCalendarData::_oId
0x9106  ldarg.0
0x9107  ldfld    class [Microsoft.Crm.Service.Application.Components.Application]Microsoft.Crm.Service.Application.Controls.AppMonthCalendar Microsoft.Crm.Service.Web.Calendar.MonthlyCalendarData::crmMonthlyCalendar
0x910c  ldstr    aOid// "oId"
0x9111  ldarg.0
0x9112  ldfld    string Microsoft.Crm.Service.Web.Calendar.MonthlyCalendarData::_oId
0x9117  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.AppointmentCalendar::AddFormParam(string, string)
0x911c  ldarg.0
0x911d  ldfld    class [Microsoft.Crm.Service.Application.Components.Application]Microsoft.Crm.Service.Application.Controls.AppMonthCalendar Microsoft.Crm.Service.Web.Calendar.MonthlyCalendarData::crmMonthlyCalendar
0x9122  ldstr    aOtype// "oType"
0x9127  ldc.i4.8
0x9128  stloc.s  6
0x912a  ldloca.s 6
0x912c  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x9131  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x9136  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.AppointmentCalendar::AddFormParam(string, string)
0x913b  ldarg.0
0x913c  ldfld    class [Microsoft.Crm.Service.Application.Components.Application]Microsoft.Crm.Service.Application.Controls.AppMonthCalendar Microsoft.Crm.Service.Web.Calendar.MonthlyCalendarData::crmMonthlyCalendar
0x9141  ldstr    aCalendarid// "calendarId"
0x9146  ldloc.s  4
0x9148  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.AppointmentCalendar::AddFormParam(string, string)
0x914d  ldarg.0
0x914e  ldfld    class [Microsoft.Crm.Service.Application.Components.Application]Microsoft.Crm.Service.Application.Controls.AppMonthCalendar Microsoft.Crm.Service.Web.Calendar.MonthlyCalendarData::crmMonthlyCalendar
0x9153  ldstr    aMode// "mode"
0x9158  ldstr    aEdit_0// "Edit"
0x915d  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.AppointmentCalendar::AddFormParam(string, string)
0x9162  ldarg.0
0x9163  ldfld    class [Microsoft.Crm.Service.Application.Components.Application]Microsoft.Crm.Service.Application.Controls.AppMonthCalendar Microsoft.Crm.Service.Web.Calendar.MonthlyCalendarData::crmMonthlyCalendar
0x9168  ldstr    aObjecttypeid// "ObjectTypeId"
0x916d  ldarg.0
0x916e  ldflda   int32 Microsoft.Crm.Service.Web.Calendar.MonthlyCalendarData::_otype
0x9173  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x9178  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x917d  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.AppointmentCalendar::AddFormParam(string, string)
0x9182  ldarg.0
0x9183  ldfld    class [Microsoft.Crm.Service.Application.Components.Application]Microsoft.Crm.Service.Application.Controls.AppMonthCalendar Microsoft.Crm.Service.Web.Calendar.MonthlyCalendarData::crmMonthlyCalendar
0x9188  ldc.i4.0
0x9189  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.MonthCalendar::set_CellSelectEnable(bool)
0x918e  ldarg.0
0x918f  ldfld    class [Microsoft.Crm.Service.Application.Components.Application]Microsoft.Crm.Service.Application.Controls.AppMonthCalendar Microsoft.Crm.Service.Web.Calendar.MonthlyCalendarData::crmMonthlyCalendar
0x9194  ldc.i4.1
0x9195  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.MonthCalendar::set_ItemSelectEnable(bool)
0x919a  ldarg.0
0x919b  ldfld    class [Microsoft.Crm.Service.Application.Components.Application]Microsoft.Crm.Service.Application.Controls.AppMonthCalendar Microsoft.Crm.Service.Web.Calendar.MonthlyCalendarData::crmMonthlyCalendar
0x91a0  ldloc.2
0x91a1  ldarg.0
0x91a2  ldfld    valuetype [Microsoft.Crm.Core.Extensions]Microsoft.Crm.Scheduling.TimeBlock[] Microsoft.Crm.Service.Web.Calendar.MonthlyCalendarData::_timeBlocks
0x91a7  ldloc.s  5
0x91a9  call     class [Microsoft.Crm.Core.Extensions]Microsoft.Crm.Scheduling.SortedTimeBlockArray Microsoft.Crm.Service.Web.Calendar.CalendarPageHelper::GenerateCalendarBlocks(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ApplicationEntityCollection activities, valuetype [Microsoft.Crm.Core.Extensions]Microsoft.Crm.Scheduling.TimeBlock[] timeBlocks, class [Microsoft.Crm.Service.Application.Components.Platform]Microsoft.Crm.Service.Application.Platform.Calendar calendar)
0x91ae  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.AppointmentCalendar::SetBlocks(class [Microsoft.Crm.Core.Extensions]Microsoft.Crm.Scheduling.SortedTimeBlockArray)
0x91b3  ret
```
