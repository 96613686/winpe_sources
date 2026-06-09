# Microsoft.Crm.Service.Web.SM.WorkPlans.WorkPlanDetailPage::ConfigurePage

- ea: `0x43e0`
- end: `0x4a20`
- name: `Microsoft.Crm.Service.Web.SM.WorkPlans.WorkPlanDetailPage::ConfigurePage`
- size: `1600`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x4300`
- `0x4340`
- `0x4370`
- `0x43e0`
- `0x5210`
- `0x55c0`
- `0x56b0`
- `0x5700`

## string_xrefs

- `0x4532`: `SM_Customer_Service_Schedule`

## pseudocode

```c

```

## disassembly

```asm
0x43e0  call     valuetype [mscorlib]System.DateTime [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.User::get_LocalDateTime()
0x43e5  stloc.0
0x43e6  ldarg.0
0x43e7  ldloc.0
0x43e8  stfld    valuetype [mscorlib]System.DateTime Microsoft.Crm.Service.Web.SM.WorkPlans.WorkPlanDetailPage::_originalStart
0x43ed  ldarg.0
0x43ee  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x43f3  ldstr    aSmWorkplansDia// "/sm/workplans/dialogs/workplaningdialog"...
0x43f8  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0x43fd  ldarg.0
0x43fe  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x4403  ldstr    aScheduleplanni// "SchedulePlanning"
0x4408  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::AddWrpcTokenActionPathWebService(string)
0x440d  ldarg.0
0x440e  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x4413  ldstr    aLocidNotWorkin// "LOCID_NOT_WORKING"
0x4418  ldarg.0
0x4419  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x441e  ldstr    aSmNotWorkingCh// "SM_Not_Working_Check"
0x4423  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x4428  ldc.i4.0
0x4429  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x442e  ldarg.0
0x442f  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x4434  ldstr    aLocidAtleastWo// "LOCID_ATLEAST_WORKINGDAY_CHK"
0x4439  ldarg.0
0x443a  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x443f  ldstr    aSmHolidayAtlea// "SM_HOLIDAY_AtleastOne_WorkingDay_Check"
0x4444  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x4449  ldc.i4.0
0x444a  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x444f  ldarg.0
0x4450  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x4455  ldstr    aLocidDefineWor// "LOCID_DEFINE_WORKING_HOURS"
0x445a  ldarg.0
0x445b  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x4460  ldstr    aSmFullyDefineW// "SM_Fully_Define_Working_Hours"
0x4465  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x446a  ldc.i4.0
0x446b  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x4470  ldarg.0
0x4471  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x4476  ldstr    aLocidDefineHol// "LOCID_DEFINE_HOLIDAY_CALENDAR"
0x447b  ldarg.0
0x447c  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x4481  ldstr    aSmFullyDefineH// "SM_Fully_Define_Holiday_Calendar"
0x4486  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x448b  ldc.i4.0
0x448c  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x4491  ldarg.0
0x4492  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x4497  ldstr    aLocidUntilDate// "LOCID_UNTIL_DATE"
0x449c  ldarg.0
0x449d  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x44a2  ldstr    aSmUntilDate// "SM_Until_Date"
0x44a7  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x44ac  ldc.i4.0
0x44ad  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x44b2  ldarg.0
0x44b3  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x44b8  ldstr    aLocidLastCheck// "LOCID_LAST_CHECK_NOT_ALLOWED"
0x44bd  ldarg.0
0x44be  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x44c3  ldstr    aSmLastCheckNot// "SM_Last_Check_Not_Allowed"
0x44c8  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x44cd  ldc.i4.0
0x44ce  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x44d3  ldarg.0
0x44d4  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x44d9  ldstr    aLocidSpecifyHo// "LOCID_SPECIFY_HOLIDAY_SCHEDULE"
0x44de  ldarg.0
0x44df  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x44e4  ldstr    aSmSpecifyHolid// "SM_Specify_Holiday_Schedule"
0x44e9  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x44ee  ldc.i4.0
0x44ef  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x44f4  ldarg.0
0x44f5  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppTabBar [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::crmTabBar
0x44fa  ldarg.0
0x44fb  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x4500  ldstr    aSmWeeklySchedu// "SM_Weekly_Schedule"
0x4505  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x450a  ldstr    aTab0// "tab0"
0x450f  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.TabBar::AddTab(string, string)
0x4514  ldarg.0
0x4515  ldfld    string Microsoft.Crm.Service.Web.SM.WorkPlans.WorkPlanDetailPage::CalendarType
0x451a  ldstr    a1// "1"
0x451f  call     bool [mscorlib]System.String::op_Equality(string, string)
0x4524  brfalse.s loc_4541
0x4526  ldarg.0
0x4527  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x452c  ldarg.0
0x452d  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x4532  ldstr    aSmCustomerServ_5// "SM_Customer_Service_Schedule"
0x4537  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x453c  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::set_Title(string)
0x4541  ldarg.0
0x4542  ldstr    aCalendar// "calendar"
0x4547  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x454c  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x4551  call     instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::set_CurrentType(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType)
0x4556  ldarg.0
0x4557  ldarg.0
0x4558  ldstr    aId// "id"
0x455d  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.Service.Web.SM.WorkPlans.WorkPlanDetailPage::AssignQueryStringGuid(string param)
0x4562  stfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Service.Web.SM.WorkPlans.WorkPlanDetailPage::_innerCalendarId
0x4567  ldarg.0
0x4568  ldarg.0
0x4569  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x456e  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x4573  ldstr    aCalendarid// "calendarId"
0x4578  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x457d  brfalse.s loc_458C
0x457f  ldarg.0
0x4580  ldstr    aCalendarid// "calendarId"
0x4585  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.Service.Web.SM.WorkPlans.WorkPlanDetailPage::AssignQueryStringGuid(string param)
0x458a  br.s     loc_4592
0x458c  ldarg.0
0x458d  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Service.Web.SM.WorkPlans.WorkPlanDetailPage::_innerCalendarId
0x4592  stfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Service.Web.SM.WorkPlans.WorkPlanDetailPage::_calendarId
0x4597  ldarg.0
0x4598  ldarg.0
0x4599  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x459e  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x45a3  ldstr    aResourceid// "resourceId"
0x45a8  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x45ad  brfalse.s loc_45BC
0x45af  ldarg.0
0x45b0  ldstr    aResourceid// "resourceId"
0x45b5  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.Service.Web.SM.WorkPlans.WorkPlanDetailPage::AssignQueryStringGuid(string param)
0x45ba  br.s     loc_45C6
0x45bc  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x45c1  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_UserId()
0x45c6  stfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Service.Web.SM.WorkPlans.WorkPlanDetailPage::_resourceId
0x45cb  ldarg.0
0x45cc  ldarg.0
0x45cd  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x45d2  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x45d7  ldstr    aCalendartype// "calendarType"
0x45dc  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x45e1  stfld    string Microsoft.Crm.Service.Web.SM.WorkPlans.WorkPlanDetailPage::CalendarType
0x45e6  ldarg.0
0x45e7  ldarg.0
0x45e8  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x45ed  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x45f2  ldstr    aMode// "mode"
0x45f7  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x45fc  brfalse.s loc_4615
0x45fe  ldarg.0
0x45ff  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x4604  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x4609  ldstr    aMode// "mode"
0x460e  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x4613  br.s     loc_461A
0x4615  ldstr    aEdit// "edit"
0x461a  stfld    string Microsoft.Crm.Service.Web.SM.WorkPlans.WorkPlanDetailPage::Mode
0x461f  ldarg.0
0x4620  ldarg.0
0x4621  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x4626  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x462b  ldstr    aOtype// "oType"
0x4630  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x4635  brfalse.s loc_464E
0x4637  ldarg.0
0x4638  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x463d  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x4642  ldstr    aOtype// "oType"
0x4647  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x464c  br.s     loc_465C
0x464e  ldc.i4.8
0x464f  stloc.3
0x4650  ldloca.s 3
0x4652  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x4657  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x465c  stfld    string Microsoft.Crm.Service.Web.SM.WorkPlans.WorkPlanDetailPage::_parentType
0x4661  ldarg.0
0x4662  ldarg.0
0x4663  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x4668  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x466d  ldstr    aClosuremode// "closuremode"
0x4672  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x4677  stfld    string Microsoft.Crm.Service.Web.SM.WorkPlans.WorkPlanDetailPage::_closureMode
0x467c  ldarg.0
0x467d  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.DateTimeUI Microsoft.Crm.Service.Web.SM.WorkPlans.WorkPlanDetailPage::start
0x4682  ldstr    aDate// "date"
0x4687  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.DateTimeUIBase::set_DisplayFormat(string)
0x468c  ldarg.0
0x468d  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x4692  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x4697  ldstr    aSelecteddates// "selecteddates"
0x469c  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x46a1  stloc.1
0x46a2  ldnull
0x46a3  stloc.2
0x46a4  ldloc.1
0x46a5  brfalse.s loc_46FE
0x46a7  ldloc.1
0x46a8  callvirt instance int32 [mscorlib]System.String::get_Length()
0x46ad  ldc.i4.0
0x46ae  ble.s    loc_46FE
0x46b0  ldloc.1
0x46b1  ldc.i4.1
0x46b2  newarr   [mscorlib]System.Char
0x46b7  dup
0x46b8  ldc.i4.0
0x46b9  ldc.i4.s 0x2C
0x46bb  stelem.i2
0x46bc  callvirt instance string[] [mscorlib]System.String::Split(char[])
0x46c1  dup
0x46c2  ldlen
0x46c3  conv.i4
0x46c4  newarr   [mscorlib]System.DateTime
0x46c9  stloc.2
0x46ca  ldc.i4.0
0x46cb  stloc.s  4
0x46cd  stloc.s  5
0x46cf  ldc.i4.0
0x46d0  stloc.3
0x46d1  br.s     loc_46F7
0x46d3  ldloc.s  5
0x46d5  ldloc.3
0x46d6  ldelem.ref
0x46d7  stloc.s  6
0x46d9  ldloc.2
0x46da  ldloc.s  4
0x46dc  ldloc.s  6
0x46de  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x46e3  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::Parse(string, class [mscorlib]System.IFormatProvider)
0x46e8  stelem   [mscorlib]System.DateTime
0x46ed  ldloc.s  4
0x46ef  ldc.i4.1
0x46f0  add
0x46f1  stloc.s  4
0x46f3  ldloc.3
0x46f4  ldc.i4.1
0x46f5  add
0x46f6  stloc.3
0x46f7  ldloc.3
0x46f8  ldloc.s  5
0x46fa  ldlen
0x46fb  conv.i4
0x46fc  blt.s    loc_46D3
0x46fe  ldarg.0
0x46ff  ldfld    string Microsoft.Crm.Service.Web.SM.WorkPlans.WorkPlanDetailPage::CalendarType
0x4704  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x4709  brfalse.s loc_4745
0x470b  ldarg.0
0x470c  ldarg.0
0x470d  ldflda   valuetype [mscorlib]System.Guid Microsoft.Crm.Service.Web.SM.WorkPlans.WorkPlanDetailPage::_resourceId
0x4712  ldstr    aB// "B"
0x4717  call     instance string [mscorlib]System.Guid::ToString(string)
0x471c  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x4721  callvirt instance string [mscorlib]System.String::ToUpper(class [mscorlib]System.Globalization.CultureInfo)
0x4726  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x472b  ldarg.0
0x472c  call     instance string Microsoft.Crm.Service.Web.SM.WorkPlans.WorkPlanDetailPage::get_ParentType()
0x4731  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x4736  call     int32 [mscorlib]System.Convert::ToInt32(string, class [mscorlib]System.IFormatProvider)
0x473b  call     string [Microsoft.Crm.Service.Application.Components.Platform]Microsoft.Crm.Service.Application.SMWorkPlans::FindOrCreateResourceCalendar(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext, int32)
0x4740  call     instance void Microsoft.Crm.Service.Web.SM.WorkPlans.WorkPlanDetailPage::set_CalendarId(string value)
0x4745  ldarg.0
0x4746  ldarg.0
0x4747  call     instance string Microsoft.Crm.Service.Web.SM.WorkPlans.WorkPlanDetailPage::get_CalendarId()
0x474c  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x4751  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x4756  call     class [Microsoft.Crm.Service.Application.Components.Platform]Microsoft.Crm.Service.Application.Platform.Calendar [Microsoft.Crm.Service.Application.Components.Platform]Microsoft.Crm.Service.Application.SMWorkPlans::RetrieveCalendar(valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x475b  stfld    class [Microsoft.Crm.Service.Application.Components.Platform]Microsoft.Crm.Service.Application.Platform.Calendar Microsoft.Crm.Service.Web.SM.WorkPlans.WorkPlanDetailPage::_calendar
0x4760  ldarg.0
0x4761  ldfld    class [Microsoft.Crm.Service.Application.Components.Platform]Microsoft.Crm.Service.Application.Platform.Calendar Microsoft.Crm.Service.Web.SM.WorkPlans.WorkPlanDetailPage::_calendar
0x4766  ldstr    aName// "name"
0x476b  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0x4770  brfalse.s loc_47AD
0x4772  ldarg.0
0x4773  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.TextBox Microsoft.Crm.Service.Web.SM.WorkPlans.WorkPlanDetailPage::name
0x4778  ldarg.0
0x4779  ldfld    class [Microsoft.Crm.Service.Application.Components.Platform]Microsoft.Crm.Service.Application.Platform.Calendar Microsoft.Crm.Service.Web.SM.WorkPlans.WorkPlanDetailPage::_calendar
0x477e  ldstr    aName// "name"
0x4783  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0x4788  callvirt instance string [mscorlib]System.Object::ToString()
0x478d  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.TextBox::set_Text(string)
0x4792  ldarg.0
0x4793  ldarg.0
0x4794  ldfld    class [Microsoft.Crm.Service.Application.Components.Platform]Microsoft.Crm.Service.Application.Platform.Calendar Microsoft.Crm.Service.Web.SM.WorkPlans.WorkPlanDetailPage::_calendar
0x4799  ldstr    aName// "name"
0x479e  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0x47a3  callvirt instance string [mscorlib]System.Object::ToString()
0x47a8  stfld    string Microsoft.Crm.Service.Web.SM.WorkPlans.WorkPlanDetailPage::_calendarName
0x47ad  ldarg.0
0x47ae  ldfld    class [Microsoft.Crm.Service.Application.Components.Platform]Microsoft.Crm.Service.Application.Platform.Calendar Microsoft.Crm.Service.Web.SM.WorkPlans.WorkPlanDetailPage::_calendar
0x47b3  ldstr    aDescription// "description"
0x47b8  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0x47bd  brfalse.s loc_47DF
0x47bf  ldarg.0
0x47c0  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.TextArea Microsoft.Crm.Service.Web.SM.WorkPlans.WorkPlanDetailPage::description
0x47c5  ldarg.0
0x47c6  ldfld    class [Microsoft.Crm.Service.Application.Components.Platform]Microsoft.Crm.Service.Application.Platform.Calendar Microsoft.Crm.Service.Web.SM.WorkPlans.WorkPlanDetailPage::_calendar
0x47cb  ldstr    aDescription// "description"
0x47d0  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0x47d5  callvirt instance string [mscorlib]System.Object::ToString()
0x47da  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.TextArea::set_Text(string)
  ... truncated ...
```
