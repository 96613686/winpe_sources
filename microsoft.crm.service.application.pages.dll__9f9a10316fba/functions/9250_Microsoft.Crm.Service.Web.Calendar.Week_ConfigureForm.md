# Microsoft.Crm.Service.Web.Calendar.Week::ConfigureForm

- ea: `0x9250`
- end: `0x9498`
- name: `Microsoft.Crm.Service.Web.Calendar.Week::ConfigureForm`
- size: `584`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x82d0`
- `0x82f0`
- `0x89e0`
- `0x9250`

## pseudocode

```c

```

## disassembly

```asm
0x9250  ldarg.0
0x9251  ldarg.0
0x9252  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x9257  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x925c  ldstr    aDate// "date"
0x9261  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x9266  call     valuetype [mscorlib]System.DateTime [Microsoft.Crm]Microsoft.Crm.CrmCalendarUtil::IsoDateTimeStringToDateTime(string)
0x926b  stfld    valuetype [mscorlib]System.DateTime Microsoft.Crm.Service.Web.Calendar.Week::_initDate
0x9270  ldarg.0
0x9271  ldarg.0
0x9272  ldflda   valuetype [mscorlib]System.DateTime Microsoft.Crm.Service.Web.Calendar.Week::_initDate
0x9277  call     instance valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_Date()
0x927c  stfld    valuetype [mscorlib]System.DateTime Microsoft.Crm.Service.Web.Calendar.Week::_initDate
0x9281  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentCulture()
0x9286  callvirt instance class [mscorlib]System.Globalization.DateTimeFormatInfo [mscorlib]System.Globalization.CultureInfo::get_DateTimeFormat()
0x928b  callvirt instance valuetype [mscorlib]System.DayOfWeek [mscorlib]System.Globalization.DateTimeFormatInfo::get_FirstDayOfWeek()
0x9290  stloc.2
0x9291  ldarg.0
0x9292  ldflda   valuetype [mscorlib]System.DateTime Microsoft.Crm.Service.Web.Calendar.Week::_initDate
0x9297  call     instance valuetype [mscorlib]System.DayOfWeek [mscorlib]System.DateTime::get_DayOfWeek()
0x929c  ldloc.2
0x929d  blt.s    loc_92BD
0x929f  ldarg.0
0x92a0  ldflda   valuetype [mscorlib]System.DateTime Microsoft.Crm.Service.Web.Calendar.Week::_initDate
0x92a5  ldarg.0
0x92a6  ldflda   valuetype [mscorlib]System.DateTime Microsoft.Crm.Service.Web.Calendar.Week::_initDate
0x92ab  call     instance valuetype [mscorlib]System.DayOfWeek [mscorlib]System.DateTime::get_DayOfWeek()
0x92b0  ldloc.2
0x92b1  sub
0x92b2  ldc.i4.m1
0x92b3  mul
0x92b4  conv.r8
0x92b5  call     instance valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::AddDays(float64)
0x92ba  stloc.0
0x92bb  br.s     loc_92DB
0x92bd  ldarg.0
0x92be  ldflda   valuetype [mscorlib]System.DateTime Microsoft.Crm.Service.Web.Calendar.Week::_initDate
0x92c3  ldarg.0
0x92c4  ldflda   valuetype [mscorlib]System.DateTime Microsoft.Crm.Service.Web.Calendar.Week::_initDate
0x92c9  call     instance valuetype [mscorlib]System.DayOfWeek [mscorlib]System.DateTime::get_DayOfWeek()
0x92ce  ldc.i4.7
0x92cf  add
0x92d0  ldloc.2
0x92d1  sub
0x92d2  ldc.i4.m1
0x92d3  mul
0x92d4  conv.r8
0x92d5  call     instance valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::AddDays(float64)
0x92da  stloc.0
0x92db  ldloca.s 0
0x92dd  ldc.r8   7.0
0x92e6  call     instance valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::AddDays(float64)
0x92eb  stloc.1
0x92ec  ldarg.0
0x92ed  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x92f2  ldstr    aWorkplaceCalen// "Workplace_Calendar_Week_Title"
0x92f7  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x92fc  stloc.3
0x92fd  ldarg.0
0x92fe  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentUser()
0x9303  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.ISecurityPrincipal::get_OrganizationId()
0x9308  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::.ctor(valuetype [mscorlib]System.Guid)
0x930d  stloc.s  4
0x930f  ldarg.0
0x9310  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentCulture()
0x9315  ldloc.3
0x9316  ldc.i4.2
0x9317  newarr   [mscorlib]System.Object
0x931c  dup
0x931d  ldc.i4.0
0x931e  ldloc.0
0x931f  ldarg.0
0x9320  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentUser()
0x9325  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser::get_SystemUserId()
0x932a  ldc.i4.1
0x932b  ldloc.s  4
0x932d  call     string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Formatting.CrmFormatter::FormatDate(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Formatting.CrmFormatter/DateFormat, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x9332  stelem.ref
0x9333  dup
0x9334  ldc.i4.1
0x9335  ldloc.1
0x9336  ldarg.0
0x9337  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentUser()
0x933c  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser::get_SystemUserId()
0x9341  ldloc.s  4
0x9343  call     string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Formatting.CrmFormatter::FormatDate(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x9348  stelem.ref
0x9349  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x934e  stfld    string Microsoft.Crm.Service.Web.Calendar.Week::_calendarTitle
0x9353  ldarg.0
0x9354  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentCulture()
0x9359  ldloc.3
0x935a  ldc.i4.2
0x935b  newarr   [mscorlib]System.Object
0x9360  dup
0x9361  ldc.i4.0
0x9362  ldloca.s 0
0x9364  ldstr    aD_0// "d"
0x9369  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentCulture()
0x936e  call     instance string [mscorlib]System.DateTime::ToString(string, class [mscorlib]System.IFormatProvider)
0x9373  stelem.ref
0x9374  dup
0x9375  ldc.i4.1
0x9376  ldloca.s 1
0x9378  ldstr    aD_0// "d"
0x937d  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentCulture()
0x9382  call     instance string [mscorlib]System.DateTime::ToString(string, class [mscorlib]System.IFormatProvider)
0x9387  stelem.ref
0x9388  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x938d  stfld    string Microsoft.Crm.Service.Web.Calendar.Week::_calendarTitle
0x9392  ldarg.0
0x9393  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentUser()
0x9398  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser::get_SystemUserId()
0x939d  ldloc.0
0x939e  ldloc.1
0x939f  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ApplicationEntityCollection Microsoft.Crm.Service.Web.Calendar.CalendarPageHelper::RetrieveActivitiesForCalendar(valuetype [mscorlib]System.Guid partyId, valuetype [mscorlib]System.DateTime start, valuetype [mscorlib]System.DateTime end)
0x93a4  stloc.s  5
0x93a6  ldc.i4.2
0x93a7  newarr   [mscorlib]System.String
0x93ac  dup
0x93ad  ldc.i4.0
0x93ae  ldstr    aSystemuserid// "systemuserid"
0x93b3  stelem.ref
0x93b4  dup
0x93b5  ldc.i4.1
0x93b6  ldstr    aCalendarid_1// "calendarid"
0x93bb  stelem.ref
0x93bc  stloc.s  6
0x93be  ldstr    aSystemuser// "systemuser"
0x93c3  ldarg.0
0x93c4  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentUser()
0x93c9  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser::get_SystemUserId()
0x93ce  ldloc.s  6
0x93d0  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x93d5  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.DataSource::Retrieve(string, valuetype [mscorlib]System.Guid, string[], class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x93da  stloc.s  7
0x93dc  ldloc.s  7
0x93de  ldstr    aCalendarid_1// "calendarid"
0x93e3  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0x93e8  castclass [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.LookupValue
0x93ed  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.LookupValue::get_ID()
0x93f2  stloc.s  8
0x93f4  ldarg.0
0x93f5  ldloc.s  7
0x93f7  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Id()
0x93fc  stfld    string Microsoft.Crm.Service.Web.Calendar.Week::_resourceId
0x9401  ldarg.0
0x9402  ldloc.s  8
0x9404  stfld    string Microsoft.Crm.Service.Web.Calendar.Week::_calendarId
0x9409  ldnull
0x940a  stloc.s  9
0x940c  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x9411  call     bool [Microsoft.Crm.Service.Application.Components.Platform]Microsoft.Crm.Service.Application.SMWorkPlans::CurrentUserPrivilegedToReadCalendar(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x9416  brfalse.s loc_943E
0x9418  ldarg.0
0x9419  ldfld    string Microsoft.Crm.Service.Web.Calendar.Week::_calendarId
0x941e  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x9423  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x9428  call     class [Microsoft.Crm.Service.Application.Components.Platform]Microsoft.Crm.Service.Application.Platform.Calendar [Microsoft.Crm.Service.Application.Components.Platform]Microsoft.Crm.Service.Application.SMWorkPlans::RetrieveCalendar(valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x942d  stloc.s  9
0x942f  ldarg.0
0x9430  ldloc.0
0x9431  ldloc.1
0x9432  ldloc.s  9
0x9434  call     valuetype [Microsoft.Crm.Core.Extensions]Microsoft.Crm.Scheduling.TimeBlock[] Microsoft.Crm.Service.Web.Calendar.CalendarPageHelper::ExpandCalendar(valuetype [mscorlib]System.DateTime startDate, valuetype [mscorlib]System.DateTime endDate, class [Microsoft.Crm.Service.Application.Components.Platform]Microsoft.Crm.Service.Application.Platform.Calendar calendar)
0x9439  stfld    valuetype [Microsoft.Crm.Core.Extensions]Microsoft.Crm.Scheduling.TimeBlock[] Microsoft.Crm.Service.Web.Calendar.Week::_timeBlocks
0x943e  ldarg.0
0x943f  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.WeekCalendar Microsoft.Crm.Service.Web.Calendar.Week::crmWeekCalendar
0x9444  ldarg.0
0x9445  ldfld    string Microsoft.Crm.Service.Web.Calendar.Week::_calendarTitle
0x944a  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.AppointmentCalendar::set_CalendarTitle(string)
0x944f  ldarg.0
0x9450  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.WeekCalendar Microsoft.Crm.Service.Web.Calendar.Week::crmWeekCalendar
0x9455  ldloc.0
0x9456  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.WeekCalendar::set_StartDate(valuetype [mscorlib]System.DateTime)
0x945b  ldarg.0
0x945c  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.WeekCalendar Microsoft.Crm.Service.Web.Calendar.Week::crmWeekCalendar
0x9461  ldloc.s  5
0x9463  ldarg.0
0x9464  ldfld    valuetype [Microsoft.Crm.Core.Extensions]Microsoft.Crm.Scheduling.TimeBlock[] Microsoft.Crm.Service.Web.Calendar.Week::_timeBlocks
0x9469  ldloc.s  9
0x946b  call     class [Microsoft.Crm.Core.Extensions]Microsoft.Crm.Scheduling.SortedTimeBlockArray Microsoft.Crm.Service.Web.Calendar.CalendarPageHelper::GenerateCalendarBlocks(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ApplicationEntityCollection activities, valuetype [Microsoft.Crm.Core.Extensions]Microsoft.Crm.Scheduling.TimeBlock[] timeBlocks, class [Microsoft.Crm.Service.Application.Components.Platform]Microsoft.Crm.Service.Application.Platform.Calendar calendar)
0x9470  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.AppointmentCalendar::SetBlocks(class [Microsoft.Crm.Core.Extensions]Microsoft.Crm.Scheduling.SortedTimeBlockArray)
0x9475  ldarg.0
0x9476  ldfld    class [System.Web]System.Web.UI.HtmlControls.HtmlInputHidden Microsoft.Crm.Service.Web.Calendar.Week::oId
0x947b  ldarg.0
0x947c  ldfld    string Microsoft.Crm.Service.Web.Calendar.Week::_resourceId
0x9481  callvirt instance void [System.Web]System.Web.UI.HtmlControls.HtmlInputControl::set_Value(string)
0x9486  ldarg.0
0x9487  ldfld    class [System.Web]System.Web.UI.HtmlControls.HtmlInputHidden Microsoft.Crm.Service.Web.Calendar.Week::calendarId
0x948c  ldarg.0
0x948d  ldfld    string Microsoft.Crm.Service.Web.Calendar.Week::_calendarId
0x9492  callvirt instance void [System.Web]System.Web.UI.HtmlControls.HtmlInputControl::set_Value(string)
0x9497  ret
```
