# Microsoft.Crm.Service.Web.Calendar.Day::ConfigureForm

- ea: `0x8b40`
- end: `0x8e07`
- name: `Microsoft.Crm.Service.Web.Calendar.Day::ConfigureForm`
- size: `711`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x82d0`
- `0x82f0`
- `0x89e0`
- `0x8b40`
- `0x8e10`
- `0x8e70`
- `0x8eb0`

## pseudocode

```c

```

## disassembly

```asm
0x8b40  ldarg.0
0x8b41  ldarg.0
0x8b42  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x8b47  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x8b4c  ldstr    aDate// "date"
0x8b51  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x8b56  call     valuetype [mscorlib]System.DateTime [Microsoft.Crm]Microsoft.Crm.CrmCalendarUtil::IsoDateTimeStringToDateTime(string)
0x8b5b  stfld    valuetype [mscorlib]System.DateTime Microsoft.Crm.Service.Web.Calendar.Day::_initDate
0x8b60  ldarg.0
0x8b61  ldarg.0
0x8b62  ldflda   valuetype [mscorlib]System.DateTime Microsoft.Crm.Service.Web.Calendar.Day::_initDate
0x8b67  call     instance valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_Date()
0x8b6c  stfld    valuetype [mscorlib]System.DateTime Microsoft.Crm.Service.Web.Calendar.Day::_initDate
0x8b71  ldarg.0
0x8b72  ldflda   valuetype [mscorlib]System.DateTime Microsoft.Crm.Service.Web.Calendar.Day::_initDate
0x8b77  ldc.r8   1.0
0x8b80  call     instance valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::AddDays(float64)
0x8b85  stloc.0
0x8b86  ldloca.s 0
0x8b88  ldc.r8   -1.0
0x8b91  call     instance valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::AddMinutes(float64)
0x8b96  stloc.0
0x8b97  ldarg.0
0x8b98  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentUser()
0x8b9d  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser::get_SystemUserId()
0x8ba2  ldarg.0
0x8ba3  ldfld    valuetype [mscorlib]System.DateTime Microsoft.Crm.Service.Web.Calendar.Day::_initDate
0x8ba8  ldloc.0
0x8ba9  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ApplicationEntityCollection Microsoft.Crm.Service.Web.Calendar.CalendarPageHelper::RetrieveActivitiesForCalendar(valuetype [mscorlib]System.Guid partyId, valuetype [mscorlib]System.DateTime start, valuetype [mscorlib]System.DateTime end)
0x8bae  stloc.1
0x8baf  ldarg.0
0x8bb0  ldarg.0
0x8bb1  ldfld    valuetype [mscorlib]System.DateTime Microsoft.Crm.Service.Web.Calendar.Day::_initDate
0x8bb6  ldloc.1
0x8bb7  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ApplicationEntityCollection Microsoft.Crm.Service.Web.Calendar.Day::FilterPreviousAllDayActivities(valuetype [mscorlib]System.DateTime day, class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ApplicationEntityCollection activities)
0x8bbc  stloc.1
0x8bbd  ldc.i4.2
0x8bbe  newarr   [mscorlib]System.String
0x8bc3  dup
0x8bc4  ldc.i4.0
0x8bc5  ldstr    aSystemuserid// "systemuserid"
0x8bca  stelem.ref
0x8bcb  dup
0x8bcc  ldc.i4.1
0x8bcd  ldstr    aCalendarid_1// "calendarid"
0x8bd2  stelem.ref
0x8bd3  stloc.2
0x8bd4  ldstr    aSystemuser// "systemuser"
0x8bd9  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.User::get_Current()
0x8bde  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser::get_SystemUserId()
0x8be3  ldloc.2
0x8be4  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x8be9  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.DataSource::Retrieve(string, valuetype [mscorlib]System.Guid, string[], class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x8bee  stloc.3
0x8bef  ldarg.0
0x8bf0  ldloc.3
0x8bf1  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Id()
0x8bf6  stfld    string Microsoft.Crm.Service.Web.Calendar.Day::_resourceId
0x8bfb  ldarg.0
0x8bfc  ldloc.3
0x8bfd  ldstr    aCalendarid_1// "calendarid"
0x8c02  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0x8c07  castclass [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.LookupValue
0x8c0c  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.LookupValue::get_ID()
0x8c11  stfld    string Microsoft.Crm.Service.Web.Calendar.Day::_calendarId
0x8c16  ldnull
0x8c17  stloc.s  4
0x8c19  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x8c1e  call     bool [Microsoft.Crm.Service.Application.Components.Platform]Microsoft.Crm.Service.Application.SMWorkPlans::CurrentUserPrivilegedToReadCalendar(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x8c23  brfalse  loc_8CEE
0x8c28  ldarg.0
0x8c29  ldfld    string Microsoft.Crm.Service.Web.Calendar.Day::_calendarId
0x8c2e  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x8c33  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x8c38  call     class [Microsoft.Crm.Service.Application.Components.Platform]Microsoft.Crm.Service.Application.Platform.Calendar [Microsoft.Crm.Service.Application.Components.Platform]Microsoft.Crm.Service.Application.SMWorkPlans::RetrieveCalendar(valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x8c3d  stloc.s  4
0x8c3f  ldarg.0
0x8c40  ldarg.0
0x8c41  ldfld    valuetype [mscorlib]System.DateTime Microsoft.Crm.Service.Web.Calendar.Day::_initDate
0x8c46  ldarg.0
0x8c47  ldflda   valuetype [mscorlib]System.DateTime Microsoft.Crm.Service.Web.Calendar.Day::_initDate
0x8c4c  ldc.r8   1.0
0x8c55  call     instance valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::AddDays(float64)
0x8c5a  ldloc.s  4
0x8c5c  call     valuetype [Microsoft.Crm.Core.Extensions]Microsoft.Crm.Scheduling.TimeBlock[] Microsoft.Crm.Service.Web.Calendar.CalendarPageHelper::ExpandCalendar(valuetype [mscorlib]System.DateTime startDate, valuetype [mscorlib]System.DateTime endDate, class [Microsoft.Crm.Service.Application.Components.Platform]Microsoft.Crm.Service.Application.Platform.Calendar calendar)
0x8c61  stfld    valuetype [Microsoft.Crm.Core.Extensions]Microsoft.Crm.Scheduling.TimeBlock[] Microsoft.Crm.Service.Web.Calendar.Day::_timeBlocks
0x8c66  ldarg.0
0x8c67  ldarg.0
0x8c68  ldfld    valuetype [Microsoft.Crm.Core.Extensions]Microsoft.Crm.Scheduling.TimeBlock[] Microsoft.Crm.Service.Web.Calendar.Day::_timeBlocks
0x8c6d  call     instance valuetype [Microsoft.Crm.Core.Extensions]Microsoft.Crm.Scheduling.TimeBlock Microsoft.Crm.Service.Web.Calendar.Day::GetWorkingHourRule(valuetype [Microsoft.Crm.Core.Extensions]Microsoft.Crm.Scheduling.TimeBlock[] timeBlockArray)
0x8c72  stloc.s  6
0x8c74  ldarg.0
0x8c75  ldarg.0
0x8c76  ldloca.s 6
0x8c78  call     instance valuetype [Microsoft.Crm.Core.Extensions]Microsoft.Crm.Scheduling.TimeInterval [Microsoft.Crm.Core.Extensions]Microsoft.Crm.Scheduling.TimeBlock::get_Interval()
0x8c7d  stloc.s  7
0x8c7f  ldloca.s 7
0x8c81  call     instance valuetype [mscorlib]System.DateTime [Microsoft.Crm.Core.Extensions]Microsoft.Crm.Scheduling.TimeInterval::get_Start()
0x8c86  call     instance string Microsoft.Crm.Service.Web.Calendar.Day::ConvertToSpanString(valuetype [mscorlib]System.DateTime dateTime)
0x8c8b  ldc.i4.0
0x8c8c  ldstr    a00// "00"
0x8c91  call     instance int32 [mscorlib]System.String::get_Length()
0x8c96  callvirt instance string [mscorlib]System.String::Substring(int32, int32)
0x8c9b  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x8ca0  call     int32 [mscorlib]System.Int32::Parse(string, class [mscorlib]System.IFormatProvider)
0x8ca5  stfld    int32 Microsoft.Crm.Service.Web.Calendar.Day::_startHour
0x8caa  ldarg.0
0x8cab  ldarg.0
0x8cac  ldloca.s 6
0x8cae  call     instance valuetype [Microsoft.Crm.Core.Extensions]Microsoft.Crm.Scheduling.TimeInterval [Microsoft.Crm.Core.Extensions]Microsoft.Crm.Scheduling.TimeBlock::get_Interval()
0x8cb3  stloc.s  7
0x8cb5  ldloca.s 7
0x8cb7  call     instance valuetype [mscorlib]System.DateTime [Microsoft.Crm.Core.Extensions]Microsoft.Crm.Scheduling.TimeInterval::get_Start()
0x8cbc  call     instance string Microsoft.Crm.Service.Web.Calendar.Day::ConvertToSpanString(valuetype [mscorlib]System.DateTime dateTime)
0x8cc1  call     valuetype [mscorlib]System.DateTime [Microsoft.Crm]Microsoft.Crm.CrmCalendarUtil::IsoTimeStringToDateTime(string)
0x8cc6  stfld    valuetype [mscorlib]System.DateTime Microsoft.Crm.Service.Web.Calendar.Day::_workdayStartTime
0x8ccb  ldarg.0
0x8ccc  ldarg.0
0x8ccd  ldloca.s 6
0x8ccf  call     instance valuetype [Microsoft.Crm.Core.Extensions]Microsoft.Crm.Scheduling.TimeInterval [Microsoft.Crm.Core.Extensions]Microsoft.Crm.Scheduling.TimeBlock::get_Interval()
0x8cd4  stloc.s  7
0x8cd6  ldloca.s 7
0x8cd8  call     instance valuetype [mscorlib]System.DateTime [Microsoft.Crm.Core.Extensions]Microsoft.Crm.Scheduling.TimeInterval::get_End()
0x8cdd  call     instance string Microsoft.Crm.Service.Web.Calendar.Day::ConvertToSpanString(valuetype [mscorlib]System.DateTime dateTime)
0x8ce2  call     valuetype [mscorlib]System.DateTime [Microsoft.Crm]Microsoft.Crm.CrmCalendarUtil::IsoTimeStringToDateTime(string)
0x8ce7  stfld    valuetype [mscorlib]System.DateTime Microsoft.Crm.Service.Web.Calendar.Day::_workdayStopTime
0x8cec  br.s     loc_8D45
0x8cee  ldarg.0
0x8cef  ldarg.0
0x8cf0  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentUser()
0x8cf5  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser::get_WorkDayStartTime()
0x8cfa  ldc.i4.0
0x8cfb  ldstr    a00// "00"
0x8d00  call     instance int32 [mscorlib]System.String::get_Length()
0x8d05  callvirt instance string [mscorlib]System.String::Substring(int32, int32)
0x8d0a  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x8d0f  call     int32 [mscorlib]System.Int32::Parse(string, class [mscorlib]System.IFormatProvider)
0x8d14  stfld    int32 Microsoft.Crm.Service.Web.Calendar.Day::_startHour
0x8d19  ldarg.0
0x8d1a  ldarg.0
0x8d1b  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentUser()
0x8d20  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser::get_WorkDayStartTime()
0x8d25  call     valuetype [mscorlib]System.DateTime [Microsoft.Crm]Microsoft.Crm.CrmCalendarUtil::IsoTimeStringToDateTime(string)
0x8d2a  stfld    valuetype [mscorlib]System.DateTime Microsoft.Crm.Service.Web.Calendar.Day::_workdayStartTime
0x8d2f  ldarg.0
0x8d30  ldarg.0
0x8d31  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentUser()
0x8d36  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser::get_WorkDayStopTime()
0x8d3b  call     valuetype [mscorlib]System.DateTime [Microsoft.Crm]Microsoft.Crm.CrmCalendarUtil::IsoTimeStringToDateTime(string)
0x8d40  stfld    valuetype [mscorlib]System.DateTime Microsoft.Crm.Service.Web.Calendar.Day::_workdayStopTime
0x8d45  ldarg.0
0x8d46  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentUser()
0x8d4b  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.ISecurityPrincipal::get_OrganizationId()
0x8d50  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::.ctor(valuetype [mscorlib]System.Guid)
0x8d55  stloc.s  5
0x8d57  ldarg.0
0x8d58  ldarg.0
0x8d59  ldfld    valuetype [mscorlib]System.DateTime Microsoft.Crm.Service.Web.Calendar.Day::_initDate
0x8d5e  ldarg.0
0x8d5f  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentUser()
0x8d64  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser::get_SystemUserId()
0x8d69  ldc.i4.1
0x8d6a  ldloc.s  5
0x8d6c  call     string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Formatting.CrmFormatter::FormatDate(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Formatting.CrmFormatter/DateFormat, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x8d71  stfld    string Microsoft.Crm.Service.Web.Calendar.Day::_calendarTitle
0x8d76  ldarg.0
0x8d77  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.DayCalendar Microsoft.Crm.Service.Web.Calendar.Day::crmDayCalendar
0x8d7c  ldarg.0
0x8d7d  ldfld    string Microsoft.Crm.Service.Web.Calendar.Day::_calendarTitle
0x8d82  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.AppointmentCalendar::set_CalendarTitle(string)
0x8d87  ldarg.0
0x8d88  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.DayCalendar Microsoft.Crm.Service.Web.Calendar.Day::crmDayCalendar
0x8d8d  ldarg.0
0x8d8e  ldfld    valuetype [mscorlib]System.DateTime Microsoft.Crm.Service.Web.Calendar.Day::_initDate
0x8d93  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.DayCalendar::set_CurrentDisplayDate(valuetype [mscorlib]System.DateTime)
0x8d98  ldarg.0
0x8d99  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.DayCalendar Microsoft.Crm.Service.Web.Calendar.Day::crmDayCalendar
0x8d9e  ldarg.0
0x8d9f  ldfld    int32 Microsoft.Crm.Service.Web.Calendar.Day::_startHour
0x8da4  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.DayCalendar::set_StartHour(int32)
0x8da9  ldarg.0
0x8daa  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.DayCalendar Microsoft.Crm.Service.Web.Calendar.Day::crmDayCalendar
0x8daf  ldarg.0
0x8db0  ldfld    valuetype [mscorlib]System.DateTime Microsoft.Crm.Service.Web.Calendar.Day::_workdayStartTime
0x8db5  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.DayCalendar::set_WorkdayStartTime(valuetype [mscorlib]System.DateTime)
0x8dba  ldarg.0
0x8dbb  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.DayCalendar Microsoft.Crm.Service.Web.Calendar.Day::crmDayCalendar
0x8dc0  ldarg.0
0x8dc1  ldfld    valuetype [mscorlib]System.DateTime Microsoft.Crm.Service.Web.Calendar.Day::_workdayStopTime
0x8dc6  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.DayCalendar::set_WorkdayStopTime(valuetype [mscorlib]System.DateTime)
0x8dcb  ldarg.0
0x8dcc  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.DayCalendar Microsoft.Crm.Service.Web.Calendar.Day::crmDayCalendar
0x8dd1  ldloc.1
0x8dd2  ldarg.0
0x8dd3  ldfld    valuetype [Microsoft.Crm.Core.Extensions]Microsoft.Crm.Scheduling.TimeBlock[] Microsoft.Crm.Service.Web.Calendar.Day::_timeBlocks
0x8dd8  ldloc.s  4
0x8dda  call     class [Microsoft.Crm.Core.Extensions]Microsoft.Crm.Scheduling.SortedTimeBlockArray Microsoft.Crm.Service.Web.Calendar.CalendarPageHelper::GenerateCalendarBlocks(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ApplicationEntityCollection activities, valuetype [Microsoft.Crm.Core.Extensions]Microsoft.Crm.Scheduling.TimeBlock[] timeBlocks, class [Microsoft.Crm.Service.Application.Components.Platform]Microsoft.Crm.Service.Application.Platform.Calendar calendar)
0x8ddf  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.AppointmentCalendar::SetBlocks(class [Microsoft.Crm.Core.Extensions]Microsoft.Crm.Scheduling.SortedTimeBlockArray)
0x8de4  ldarg.0
0x8de5  ldfld    class [System.Web]System.Web.UI.HtmlControls.HtmlInputHidden Microsoft.Crm.Service.Web.Calendar.Day::oId
0x8dea  ldarg.0
0x8deb  ldfld    string Microsoft.Crm.Service.Web.Calendar.Day::_resourceId
0x8df0  callvirt instance void [System.Web]System.Web.UI.HtmlControls.HtmlInputControl::set_Value(string)
0x8df5  ldarg.0
0x8df6  ldfld    class [System.Web]System.Web.UI.HtmlControls.HtmlInputHidden Microsoft.Crm.Service.Web.Calendar.Day::calendarId
0x8dfb  ldarg.0
0x8dfc  ldfld    string Microsoft.Crm.Service.Web.Calendar.Day::_calendarId
0x8e01  callvirt instance void [System.Web]System.Web.UI.HtmlControls.HtmlInputControl::set_Value(string)
0x8e06  ret
```
