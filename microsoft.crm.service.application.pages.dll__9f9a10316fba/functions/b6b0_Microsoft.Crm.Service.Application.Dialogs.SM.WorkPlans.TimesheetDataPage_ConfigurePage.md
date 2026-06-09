# Microsoft.Crm.Service.Application.Dialogs.SM.WorkPlans.TimesheetDataPage::ConfigurePage

- ea: `0xb6b0`
- end: `0xba31`
- name: `Microsoft.Crm.Service.Application.Dialogs.SM.WorkPlans.TimesheetDataPage::ConfigurePage`
- size: `897`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0xb6b0`
- `0xba40`
- `0xbad0`
- `0xbb00`
- `0xbec0`

## pseudocode

```c

```

## disassembly

```asm
0xb6b0  call     valuetype [mscorlib]System.DateTime [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.User::get_LocalDateTime()
0xb6b5  stloc.s  4
0xb6b7  ldloca.s 4
0xb6b9  call     instance valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_Date()
0xb6be  stloc.1
0xb6bf  ldarg.0
0xb6c0  ldarg.0
0xb6c1  ldstr    aId_0// "Id"
0xb6c6  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.Service.Application.Dialogs.SM.WorkPlans.TimesheetDataPage::AssignQueryStringGuid(string param)
0xb6cb  stfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Service.Application.Dialogs.SM.WorkPlans.TimesheetDataPage::_oId
0xb6d0  ldarg.0
0xb6d1  ldarg.0
0xb6d2  ldstr    aCalendarid_1// "calendarid"
0xb6d7  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.Service.Application.Dialogs.SM.WorkPlans.TimesheetDataPage::AssignQueryStringGuid(string param)
0xb6dc  stfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Service.Application.Dialogs.SM.WorkPlans.TimesheetDataPage::_calendarId
0xb6e1  ldarg.0
0xb6e2  ldarg.0
0xb6e3  ldstr    aResourceid_0// "resourceid"
0xb6e8  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.Service.Application.Dialogs.SM.WorkPlans.TimesheetDataPage::AssignQueryStringGuid(string param)
0xb6ed  stfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Service.Application.Dialogs.SM.WorkPlans.TimesheetDataPage::_resourceId
0xb6f2  ldarg.0
0xb6f3  ldarg.0
0xb6f4  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0xb6f9  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0xb6fe  ldstr    aCalendartype// "calendarType"
0xb703  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0xb708  stfld    string Microsoft.Crm.Service.Application.Dialogs.SM.WorkPlans.TimesheetDataPage::CalendarType
0xb70d  ldarg.0
0xb70e  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0xb713  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0xb718  ldstr    aOtype// "oType"
0xb71d  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0xb722  call     int32 [mscorlib]System.Convert::ToInt32(string)
0xb727  stloc.2
0xb728  ldarg.0
0xb729  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.DateTimeUI Microsoft.Crm.Service.Application.Dialogs.SM.WorkPlans.TimesheetDataPage::startTC
0xb72e  ldstr    aTime// "time"
0xb733  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.DateTimeUIBase::set_DisplayFormat(string)
0xb738  ldarg.0
0xb739  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.DateTimeUI Microsoft.Crm.Service.Application.Dialogs.SM.WorkPlans.TimesheetDataPage::startTC
0xb73e  ldloc.1
0xb73f  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.DateTimeUIBase::set_Value(valuetype [mscorlib]System.DateTime)
0xb744  ldarg.0
0xb745  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.DateTimeUI Microsoft.Crm.Service.Application.Dialogs.SM.WorkPlans.TimesheetDataPage::startTC
0xb74a  ldc.i4.1
0xb74b  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.DateTimeUIBase::set_DisableInit(bool)
0xb750  ldarg.0
0xb751  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.DateTimeUI Microsoft.Crm.Service.Application.Dialogs.SM.WorkPlans.TimesheetDataPage::endTC
0xb756  ldstr    aTime// "time"
0xb75b  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.DateTimeUIBase::set_DisplayFormat(string)
0xb760  ldarg.0
0xb761  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.DateTimeUI Microsoft.Crm.Service.Application.Dialogs.SM.WorkPlans.TimesheetDataPage::endTC
0xb766  ldloc.1
0xb767  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.DateTimeUIBase::set_Value(valuetype [mscorlib]System.DateTime)
0xb76c  ldarg.0
0xb76d  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.DateTimeUI Microsoft.Crm.Service.Application.Dialogs.SM.WorkPlans.TimesheetDataPage::endTC
0xb772  ldc.i4.1
0xb773  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.DateTimeUIBase::set_PositionMidnightLast(bool)
0xb778  ldarg.0
0xb779  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.DateTimeUI Microsoft.Crm.Service.Application.Dialogs.SM.WorkPlans.TimesheetDataPage::endTC
0xb77e  ldc.i4.1
0xb77f  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.DateTimeUIBase::set_DisableInit(bool)
0xb784  ldarg.0
0xb785  call     instance class [Microsoft.Crm.Service.Application.Components.Platform]Microsoft.Crm.Service.Application.Platform.CalendarRule Microsoft.Crm.Service.Application.Dialogs.SM.WorkPlans.TimesheetDataPage::RetrieveWorkingHoursRule()
0xb78a  stloc.3
0xb78b  ldloc.3
0xb78c  brfalse.s loc_B7DF
0xb78e  ldloca.s 1
0xb790  ldloc.3
0xb791  callvirt instance valuetype [mscorlib]System.TimeSpan [Microsoft.Crm.Service.Application.Components.Platform]Microsoft.Crm.Service.Application.Platform.CalendarRule::get_Offset()
0xb796  call     instance valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::Add(valuetype [mscorlib]System.TimeSpan)
0xb79b  stloc.s  5
0xb79d  ldloca.s 5
0xb79f  ldloc.3
0xb7a0  callvirt instance valuetype [mscorlib]System.TimeSpan [Microsoft.Crm.Service.Application.Components.Platform]Microsoft.Crm.Service.Application.Platform.CalendarRule::get_Duration()
0xb7a5  call     instance valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::Add(valuetype [mscorlib]System.TimeSpan)
0xb7aa  stloc.s  6
0xb7ac  ldarg.0
0xb7ad  ldfld    class [Microsoft.Crm.Service.Application.Components.Application]Microsoft.Crm.Service.Application.Controls.AppTimesheet Microsoft.Crm.Service.Application.Dialogs.SM.WorkPlans.TimesheetDataPage::crmTimesheet
0xb7b2  ldloc.s  5
0xb7b4  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.TimeSheet::set_StartTime(valuetype [mscorlib]System.DateTime)
0xb7b9  ldarg.0
0xb7ba  ldfld    class [Microsoft.Crm.Service.Application.Components.Application]Microsoft.Crm.Service.Application.Controls.AppTimesheet Microsoft.Crm.Service.Application.Dialogs.SM.WorkPlans.TimesheetDataPage::crmTimesheet
0xb7bf  ldloc.s  6
0xb7c1  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.TimeSheet::set_EndTime(valuetype [mscorlib]System.DateTime)
0xb7c6  ldarg.0
0xb7c7  ldfld    class [Microsoft.Crm.Service.Application.Components.Application]Microsoft.Crm.Service.Application.Controls.AppTimesheet Microsoft.Crm.Service.Application.Dialogs.SM.WorkPlans.TimesheetDataPage::crmTimesheet
0xb7cc  ldarg.0
0xb7cd  ldarg.0
0xb7ce  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Service.Application.Dialogs.SM.WorkPlans.TimesheetDataPage::_oId
0xb7d3  ldloc.3
0xb7d4  call     instance string Microsoft.Crm.Service.Application.Dialogs.SM.WorkPlans.TimesheetDataPage::RetrieveBreaksAndEffortRulesInOrder(valuetype [mscorlib]System.Guid calendarId, class [Microsoft.Crm.Service.Application.Components.Platform]Microsoft.Crm.Service.Application.Platform.CalendarRule workingHoursRule)
0xb7d9  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.TimeSheet::set_InitStateData(string)
0xb7de  ret
0xb7df  ldarg.0
0xb7e0  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0xb7e5  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0xb7ea  ldstr    aSelecteddates// "selecteddates"
0xb7ef  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0xb7f4  stloc.s  7
0xb7f6  ldloc.s  7
0xb7f8  brfalse  loc_BA2A
0xb7fd  ldloc.s  7
0xb7ff  callvirt instance int32 [mscorlib]System.String::get_Length()
0xb804  ldc.i4.0
0xb805  ble      loc_BA2A
0xb80a  ldloc.s  7
0xb80c  ldc.i4.1
0xb80d  newarr   [mscorlib]System.Char
0xb812  dup
0xb813  ldc.i4.0
0xb814  ldc.i4.s 0x2C
0xb816  stelem.i2
0xb817  callvirt instance string[] [mscorlib]System.String::Split(char[])
0xb81c  dup
0xb81d  ldlen
0xb81e  conv.i4
0xb81f  newarr   [mscorlib]System.DateTime
0xb824  stloc.0
0xb825  ldc.i4.0
0xb826  stloc.s  8
0xb828  stloc.s  0xA
0xb82a  ldc.i4.0
0xb82b  stloc.s  0xB
0xb82d  br.s     loc_B856
0xb82f  ldloc.s  0xA
0xb831  ldloc.s  0xB
0xb833  ldelem.ref
0xb834  stloc.s  0xC
0xb836  ldloc.0
0xb837  ldloc.s  8
0xb839  ldloc.s  0xC
0xb83b  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xb840  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::Parse(string, class [mscorlib]System.IFormatProvider)
0xb845  stelem   [mscorlib]System.DateTime
0xb84a  ldloc.s  8
0xb84c  ldc.i4.1
0xb84d  add
0xb84e  stloc.s  8
0xb850  ldloc.s  0xB
0xb852  ldc.i4.1
0xb853  add
0xb854  stloc.s  0xB
0xb856  ldloc.s  0xB
0xb858  ldloc.s  0xA
0xb85a  ldlen
0xb85b  conv.i4
0xb85c  blt.s    loc_B82F
0xb85e  ldc.i4.0
0xb85f  stloc.s  9
0xb861  ldloc.s  8
0xb863  ldc.i4.0
0xb864  ble      loc_BA1F
0xb869  ldloc.2
0xb86a  ldc.i4   0x47E
0xb86f  bne.un.s loc_B8BE
0xb871  ldarg.0
0xb872  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Service.Application.Dialogs.SM.WorkPlans.TimesheetDataPage::_resourceId
0xb877  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xb87c  ldc.i4.0
0xb87d  newarr   [mscorlib]System.String
0xb882  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity [Microsoft.Crm.Service.Application.Components.Platform]Microsoft.Crm.Service.Application.SMWorkPlans::RetrieveBookableResource(valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext, string[])
0xb887  stloc.s  0xD
0xb889  ldloc.s  0xD
0xb88b  ldstr    aCalendarid_1// "calendarid"
0xb890  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0xb895  brfalse.s loc_B8FB
0xb897  ldloc.s  0xD
0xb899  ldstr    aCalendarid_1// "calendarid"
0xb89e  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0xb8a3  isinst   [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.LookupValue
0xb8a8  stloc.s  0xE
0xb8aa  ldarg.0
0xb8ab  ldloc.s  0xE
0xb8ad  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.LookupValue::get_ID()
0xb8b2  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0xb8b7  stfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Service.Application.Dialogs.SM.WorkPlans.TimesheetDataPage::_calendarId
0xb8bc  br.s     loc_B8FB
0xb8be  ldarg.0
0xb8bf  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Service.Application.Dialogs.SM.WorkPlans.TimesheetDataPage::_resourceId
0xb8c4  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xb8c9  ldc.i4.0
0xb8ca  newarr   [mscorlib]System.String
0xb8cf  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity [Microsoft.Crm.Service.Application.Components.Platform]Microsoft.Crm.Service.Application.SMWorkPlans::RetrieveResource(valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext, string[])
0xb8d4  stloc.s  0xF
0xb8d6  ldloc.s  0xF
0xb8d8  ldstr    aCalendarid_1// "calendarid"
0xb8dd  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0xb8e2  brfalse.s loc_B8FB
0xb8e4  ldarg.0
0xb8e5  ldloc.s  0xF
0xb8e7  ldstr    aCalendarid_1// "calendarid"
0xb8ec  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0xb8f1  unbox.any [mscorlib]System.Guid
0xb8f6  stfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Service.Application.Dialogs.SM.WorkPlans.TimesheetDataPage::_calendarId
0xb8fb  ldarg.0
0xb8fc  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Service.Application.Dialogs.SM.WorkPlans.TimesheetDataPage::_calendarId
0xb901  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0xb906  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0xb90b  brfalse  loc_BA1F
0xb910  ldarg.0
0xb911  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Service.Application.Dialogs.SM.WorkPlans.TimesheetDataPage::_calendarId
0xb916  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xb91b  call     class [Microsoft.Crm.Service.Application.Components.Platform]Microsoft.Crm.Service.Application.Platform.Calendar [Microsoft.Crm.Service.Application.Components.Platform]Microsoft.Crm.Service.Application.SMWorkPlans::RetrieveCalendar(valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xb920  ldloc.0
0xb921  ldc.i4.0
0xb922  ldelem   [mscorlib]System.DateTime
0xb927  ldloc.0
0xb928  ldc.i4.0
0xb929  ldelema  [mscorlib]System.DateTime
0xb92e  ldc.r8   1.0
0xb937  call     instance valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::AddDays(float64)
0xb93c  newobj   instance void [Microsoft.Crm.Core.Extensions]Microsoft.Crm.Scheduling.TimeInterval::.ctor(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTime)
0xb941  callvirt instance valuetype [Microsoft.Crm.Core.Extensions]Microsoft.Crm.Scheduling.TimeBlock[] [Microsoft.Crm.Service.Application.Components.Platform]Microsoft.Crm.Service.Application.Platform.Calendar::Expand(valuetype [Microsoft.Crm.Core.Extensions]Microsoft.Crm.Scheduling.TimeInterval)
0xb946  stloc.s  0x10
0xb948  ldc.i4.0
0xb949  stloc.s  0xB
0xb94b  br       loc_BA14
0xb950  ldloc.s  0x10
0xb952  ldloc.s  0xB
0xb954  ldelem   [Microsoft.Crm.Core.Extensions]Microsoft.Crm.Scheduling.TimeBlock
0xb959  stloc.s  0x11
0xb95b  ldloca.s 0x11
0xb95d  call     instance class [Microsoft.Crm.Core.Extensions]Microsoft.Crm.Scheduling.ITimeMetadata [Microsoft.Crm.Core.Extensions]Microsoft.Crm.Scheduling.TimeBlock::get_Metadata()
0xb962  castclass [Microsoft.Crm.Core.Extensions]Microsoft.Crm.Scheduling.TimeMetadata
0xb967  stloc.s  0x12
0xb969  ldstr    aWorkinghoursti// "WorkingHoursTimeType"
0xb96e  ldloc.s  0x12
0xb970  call     bool [Microsoft.Crm.Service.Application.Components.Platform]Microsoft.Crm.Service.Application.SMWorkPlans::CompareTimeMetadataTimeType(string, class [Microsoft.Crm.Core.Extensions]Microsoft.Crm.Scheduling.TimeMetadata)
0xb975  brfalse  loc_BA0E
0xb97a  ldloc.s  0x12
0xb97c  ldstr    aCalendarid_0// "CalendarId"
0xb981  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0xb986  unbox.any [mscorlib]System.Guid
0xb98b  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xb990  call     class [Microsoft.Crm.Service.Application.Components.Platform]Microsoft.Crm.Service.Application.Platform.Calendar [Microsoft.Crm.Service.Application.Components.Platform]Microsoft.Crm.Service.Application.SMWorkPlans::RetrieveCalendar(valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xb995  ldloc.s  0x12
0xb997  ldstr    aSourceid// "SourceId"
0xb99c  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0xb9a1  unbox.any [mscorlib]System.Guid
0xb9a6  callvirt instance class [Microsoft.Crm.Service.Application.Components.Platform]Microsoft.Crm.Service.Application.Platform.CalendarRule [Microsoft.Crm.Service.Application.Components.Platform]Microsoft.Crm.Service.Application.Platform.Calendar::FindCalendarRuleById(valuetype [mscorlib]System.Guid)
0xb9ab  stloc.s  0x13
0xb9ad  ldloca.s 1
0xb9af  ldloc.s  0x13
0xb9b1  callvirt instance valuetype [mscorlib]System.TimeSpan [Microsoft.Crm.Service.Application.Components.Platform]Microsoft.Crm.Service.Application.Platform.CalendarRule::get_Offset()
0xb9b6  call     instance valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::Add(valuetype [mscorlib]System.TimeSpan)
0xb9bb  stloc.s  0x14
0xb9bd  ldloca.s 0x14
0xb9bf  ldloc.s  0x13
0xb9c1  callvirt instance valuetype [mscorlib]System.TimeSpan [Microsoft.Crm.Service.Application.Components.Platform]Microsoft.Crm.Service.Application.Platform.CalendarRule::get_Duration()
0xb9c6  call     instance valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::Add(valuetype [mscorlib]System.TimeSpan)
0xb9cb  stloc.s  0x15
0xb9cd  ldarg.0
0xb9ce  ldfld    class [Microsoft.Crm.Service.Application.Components.Application]Microsoft.Crm.Service.Application.Controls.AppTimesheet Microsoft.Crm.Service.Application.Dialogs.SM.WorkPlans.TimesheetDataPage::crmTimesheet
0xb9d3  ldloc.s  0x14
0xb9d5  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.TimeSheet::set_StartTime(valuetype [mscorlib]System.DateTime)
0xb9da  ldarg.0
0xb9db  ldfld    class [Microsoft.Crm.Service.Application.Components.Application]Microsoft.Crm.Service.Application.Controls.AppTimesheet Microsoft.Crm.Service.Application.Dialogs.SM.WorkPlans.TimesheetDataPage::crmTimesheet
0xb9e0  ldloc.s  0x15
0xb9e2  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.TimeSheet::set_EndTime(valuetype [mscorlib]System.DateTime)
0xb9e7  ldarg.0
0xb9e8  ldfld    class [Microsoft.Crm.Service.Application.Components.Application]Microsoft.Crm.Service.Application.Controls.AppTimesheet Microsoft.Crm.Service.Application.Dialogs.SM.WorkPlans.TimesheetDataPage::crmTimesheet
0xb9ed  ldarg.0
0xb9ee  ldloc.s  0x12
0xb9f0  ldstr    aCalendarid_0// "CalendarId"
0xb9f5  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0xb9fa  unbox.any [mscorlib]System.Guid
0xb9ff  ldloc.s  0x13
0xba01  call     instance string Microsoft.Crm.Service.Application.Dialogs.SM.WorkPlans.TimesheetDataPage::RetrieveBreaksAndEffortRulesInOrder(valuetype [mscorlib]System.Guid calendarId, class [Microsoft.Crm.Service.Application.Components.Platform]Microsoft.Crm.Service.Application.Platform.CalendarRule workingHoursRule)
0xba06  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.TimeSheet::set_InitStateData(string)
0xba0b  ldc.i4.1
0xba0c  stloc.s  9
0xba0e  ldloc.s  0xB
0xba10  ldc.i4.1
0xba11  add
0xba12  stloc.s  0xB
0xba14  ldloc.s  0xB
0xba16  ldloc.s  0x10
0xba18  ldlen
0xba19  conv.i4
0xba1a  blt      loc_B950
0xba1f  ldloc.s  9
0xba21  brtrue.s loc_BA30
0xba23  ldarg.0
0xba24  call     instance void Microsoft.Crm.Service.Application.Dialogs.SM.WorkPlans.TimesheetDataPage::InitNewTimeSheet()
0xba29  ret
0xba2a  ldarg.0
0xba2b  call     instance void Microsoft.Crm.Service.Application.Dialogs.SM.WorkPlans.TimesheetDataPage::InitNewTimeSheet()
0xba30  ret
```
