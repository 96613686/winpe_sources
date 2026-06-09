# Microsoft.Crm.Service.Application.Pages.SM.AppointmentBook.AppointmentHome::ConfigurePage

- ea: `0x135a0`
- end: `0x13e2f`
- name: `Microsoft.Crm.Service.Application.Pages.SM.AppointmentBook.AppointmentHome::ConfigurePage`
- size: `2191`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x135a0`
- `0x13ea0`
- `0x13ed0`

## string_xrefs

- `0x13652`: `/_static/_common/scripts/stage.js`
- `0x135f2`: `/_common/styles/miniCal.css.aspx`
- `0x13632`: `/_static/_common/scripts/appoint.js`
- `0x1369e`: `Web._common.scripts.stage.js_30`
- `0x136bf`: `Web._common.scripts.stage.js_17`
- `0x136d5`: `LOCID_SEARCH_LIST_NOT_OPEN`
- `0x136e0`: `Web._common.scripts.stage.js_35`
- `0x13743`: `Appointment_Book_No_Service_Appointment_Selected`
- `0x1377a`: `LOCID_APPTBOOK_ACTIVITY_READONLY`
- `0x13785`: `Appointment_Book_Read_Only`
- `0x13882`: `Web.Workplace.home_calendar.aspx_ServiceCalendarAppointmentViewSummary`
- `0x13df0`: `Web.Workplace.home_calendar.aspx_ServiceCalendarAppointmentViewSummary`
- `0x1394c`: `Appointment_Book_Type_Appointments_And_Service_Activities`

## pseudocode

```c

```

## disassembly

```asm
0x135a0  ldarg.0
0x135a1  call     instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.PageManager::ConfigurePage()
0x135a6  ldstr    aActivitypointe// "activitypointer"
0x135ab  ldc.i4.1
0x135ac  stloc.s  7
0x135ae  ldloca.s 7
0x135b0  constrained. [Microsoft.Crm.Sdk.Reserved]Microsoft.Crm.Sdk.Types.ActivityPointerState
0x135b6  callvirt instance string [mscorlib]System.Object::ToString()
0x135bb  call     int32 [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityProxy::ConvertStateToNumber(string, string)
0x135c0  stloc.0
0x135c1  ldstr    aActivitypointe// "activitypointer"
0x135c6  ldc.i4.2
0x135c7  stloc.s  7
0x135c9  ldloca.s 7
0x135cb  constrained. [Microsoft.Crm.Sdk.Reserved]Microsoft.Crm.Sdk.Types.ActivityPointerState
0x135d1  callvirt instance string [mscorlib]System.Object::ToString()
0x135d6  call     int32 [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityProxy::ConvertStateToNumber(string, string)
0x135db  stloc.1
0x135dc  ldarg.0
0x135dd  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x135e2  ldstr    aNavMenuCssAspx// "/_nav/menu.css.aspx"
0x135e7  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0x135ec  ldarg.0
0x135ed  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x135f2  ldstr    aCommonStylesMi// "/_common/styles/miniCal.css.aspx"
0x135f7  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0x135fc  ldarg.0
0x135fd  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x13602  ldstr    aSmApptbookAppt// "/sm/apptbook/apptbook.css.aspx"
0x13607  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0x1360c  ldarg.0
0x1360d  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x13612  ldstr    aStaticSmApptbo_0// "/_static/sm/apptbook/apptbook.js"
0x13617  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x1361c  ldarg.0
0x1361d  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x13622  ldstr    aStaticFormsAdd// "/_static/_forms/addrelated.js"
0x13627  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x1362c  ldarg.0
0x1362d  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x13632  ldstr    aStaticCommonSc_10// "/_static/_common/scripts/appoint.js"
0x13637  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x1363c  ldarg.0
0x1363d  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x13642  ldstr    aStaticControls_5// "/_static/_controls/datetime/date.js"
0x13647  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x1364c  ldarg.0
0x1364d  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x13652  ldstr    aStaticCommonSc_3// "/_static/_common/scripts/stage.js"
0x13657  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x1365c  ldarg.0
0x1365d  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x13662  ldstr    aLocidAfErrorda// "LOCID_AF_ERRORDATEINTERVAL_MSG"
0x13667  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentCulture()
0x1366c  ldarg.0
0x1366d  ldfld    class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Service.Application.Pages.SM.AppointmentBook.AppointmentHome::_rm
0x13672  ldstr    aSmMsgWrongdate// "SM_Msg_WrongDateInterval"
0x13677  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x1367c  ldc.i4.0
0x1367d  newarr   [mscorlib]System.Object
0x13682  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x13687  ldc.i4.0
0x13688  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x1368d  ldarg.0
0x1368e  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x13693  ldstr    aLocidSearchRes// "LOCID_SEARCH_RESULTS"
0x13698  ldarg.0
0x13699  ldfld    class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Service.Application.Pages.SM.AppointmentBook.AppointmentHome::_rm
0x1369e  ldstr    aWebCommonScrip// "Web._common.scripts.stage.js_30"
0x136a3  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x136a8  ldc.i4.0
0x136a9  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x136ae  ldarg.0
0x136af  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x136b4  ldstr    aLocidSearchAle// "LOCID_SEARCH_ALERT_NO_CRITERIA"
0x136b9  ldarg.0
0x136ba  ldfld    class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Service.Application.Pages.SM.AppointmentBook.AppointmentHome::_rm
0x136bf  ldstr    aWebCommonScrip_0// "Web._common.scripts.stage.js_17"
0x136c4  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x136c9  ldc.i4.0
0x136ca  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x136cf  ldarg.0
0x136d0  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x136d5  ldstr    aLocidSearchLis// "LOCID_SEARCH_LIST_NOT_OPEN"
0x136da  ldarg.0
0x136db  ldfld    class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Service.Application.Pages.SM.AppointmentBook.AppointmentHome::_rm
0x136e0  ldstr    aWebCommonScrip_1// "Web._common.scripts.stage.js_35"
0x136e5  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x136ea  ldc.i4.0
0x136eb  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x136f0  ldarg.0
0x136f1  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x136f6  ldstr    aLocidApptbookI// "LOCID_APPTBOOK_INVALID_ACTION"
0x136fb  ldarg.0
0x136fc  ldfld    class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Service.Application.Pages.SM.AppointmentBook.AppointmentHome::_rm
0x13701  ldstr    aAppointmentBoo// "Appointment_Book_Invalid_Action"
0x13706  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x1370b  ldc.i4.0
0x1370c  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x13711  ldarg.0
0x13712  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x13717  ldstr    aLocidDirectEma// "LOCID_DIRECT_EMAIL_NO_SELECTION"
0x1371c  ldarg.0
0x1371d  ldfld    class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Service.Application.Pages.SM.AppointmentBook.AppointmentHome::_rm
0x13722  ldstr    aErrorDirectEma// "Error_Direct_Email_No_Selection"
0x13727  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x1372c  ldc.i4.0
0x1372d  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x13732  ldarg.0
0x13733  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x13738  ldstr    aLocidApptbookN// "LOCID_APPTBOOK_NO_SVC_APPT"
0x1373d  ldarg.0
0x1373e  ldfld    class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Service.Application.Pages.SM.AppointmentBook.AppointmentHome::_rm
0x13743  ldstr    aAppointmentBoo_0// "Appointment_Book_No_Service_Appointment"...
0x13748  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x1374d  ldc.i4.0
0x1374e  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x13753  ldarg.0
0x13754  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x13759  ldstr    aLocidApptbookN_0// "LOCID_APPTBOOK_NO_SELECTION"
0x1375e  ldarg.0
0x1375f  ldfld    class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Service.Application.Pages.SM.AppointmentBook.AppointmentHome::_rm
0x13764  ldstr    aAppointmentBoo_1// "Appointment_Book_No_Selection"
0x13769  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x1376e  ldc.i4.0
0x1376f  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x13774  ldarg.0
0x13775  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x1377a  ldstr    aLocidApptbookA// "LOCID_APPTBOOK_ACTIVITY_READONLY"
0x1377f  ldarg.0
0x13780  ldfld    class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Service.Application.Pages.SM.AppointmentBook.AppointmentHome::_rm
0x13785  ldstr    aAppointmentBoo_2// "Appointment_Book_Read_Only"
0x1378a  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x1378f  ldc.i4.0
0x13790  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x13795  ldarg.0
0x13796  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x1379b  ldstr    aLocidShowConfl// "LOCID_SHOW_CONFLICTS"
0x137a0  ldarg.0
0x137a1  ldfld    class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Service.Application.Pages.SM.AppointmentBook.AppointmentHome::_rm
0x137a6  ldstr    aSmMenuitemButt// "SM_MenuItem_Button_ShowConflicts"
0x137ab  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x137b0  ldc.i4.0
0x137b1  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x137b6  ldarg.0
0x137b7  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x137bc  ldstr    aLocidHideConfl// "LOCID_HIDE_CONFLICTS"
0x137c1  ldarg.0
0x137c2  ldfld    class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Service.Application.Pages.SM.AppointmentBook.AppointmentHome::_rm
0x137c7  ldstr    aSmMenuitemButt_0// "SM_MenuItem_Button_HideConflicts"
0x137cc  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x137d1  ldc.i4.0
0x137d2  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x137d7  ldarg.0
0x137d8  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x137dd  ldstr    aLocidCannotRes// "LOCID_CANNOT_RESCHED_CLOSED"
0x137e2  ldarg.0
0x137e3  ldfld    class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Service.Application.Pages.SM.AppointmentBook.AppointmentHome::_rm
0x137e8  ldstr    aErrorCannotRes// "Error_Cannot_Reschedule_Closed_Or_Cance"...
0x137ed  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x137f2  ldc.i4.0
0x137f3  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x137f8  ldarg.0
0x137f9  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x137fe  ldstr    aLocidHideresou// "LOCID_HIDERESOURCEDETAILS"
0x13803  ldarg.0
0x13804  ldfld    class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Service.Application.Pages.SM.AppointmentBook.AppointmentHome::_rm
0x13809  ldstr    aSmApptbookHide// "SM.Apptbook.Hide.Resourcedetails"
0x1380e  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x13813  ldc.i4.0
0x13814  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x13819  ldarg.0
0x1381a  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x1381f  ldstr    aLocidShowresou// "LOCID_SHOWRESOURCEDETAILS"
0x13824  ldarg.0
0x13825  ldfld    class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Service.Application.Pages.SM.AppointmentBook.AppointmentHome::_rm
0x1382a  ldstr    aSmApptbookShow// "SM.Apptbook.Show.Resourcedetails"
0x1382f  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x13834  ldc.i4.0
0x13835  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x1383a  ldarg.0
0x1383b  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x13840  ldstr    aIclosedstate// "_iClosedState"
0x13845  ldloc.0
0x13846  conv.i8
0x13847  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, int64)
0x1384c  ldarg.0
0x1384d  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x13852  ldstr    aIcancelledstat// "_iCancelledState"
0x13857  ldloc.1
0x13858  conv.i8
0x13859  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, int64)
0x1385e  ldarg.0
0x1385f  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x13864  ldstr    aImaxdaterange// "_iMaxDateRange"
0x13869  ldc.i4.s 0x2A
0x1386b  conv.i8
0x1386c  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, int64)
0x13871  ldarg.0
0x13872  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x13877  ldstr    aLocidOuterSumm// "LOCID_OUTER_SUMMARY_STRING"
0x1387c  ldarg.0
0x1387d  ldfld    class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Service.Application.Pages.SM.AppointmentBook.AppointmentHome::_rm
0x13882  ldstr    aWebWorkplaceHo// "Web.Workplace.home_calendar.aspx_Servic"...
0x13887  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x1388c  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, string)
0x13891  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x13896  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_OrganizationId()
0x1389b  call     valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::GetTraceCategory()
0x138a0  ldstr    aSmHomeApptbook// "/SM/home_apptbook.aspx parameters: suba"...
0x138a5  ldc.i4.6
0x138a6  newarr   [mscorlib]System.Object
0x138ab  dup
0x138ac  ldc.i4.0
0x138ad  ldarg.0
0x138ae  callvirt instance class [System.Web]System.Web.UI.Page [System.Web]System.Web.UI.Control::get_Page()
0x138b3  callvirt instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x138b8  ldstr    aSubareatype// "subareatype"
0x138bd  callvirt instance string [System.Web]System.Web.HttpRequest::get_Item(string)
0x138c2  stelem.ref
0x138c3  dup
0x138c4  ldc.i4.1
0x138c5  ldarg.0
0x138c6  callvirt instance class [System.Web]System.Web.UI.Page [System.Web]System.Web.UI.Control::get_Page()
0x138cb  callvirt instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x138d0  ldstr    aStartdate// "startDate"
0x138d5  callvirt instance string [System.Web]System.Web.HttpRequest::get_Item(string)
0x138da  stelem.ref
0x138db  dup
0x138dc  ldc.i4.2
0x138dd  ldarg.0
0x138de  callvirt instance class [System.Web]System.Web.UI.Page [System.Web]System.Web.UI.Control::get_Page()
0x138e3  callvirt instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x138e8  ldstr    aEnddate// "endDate"
0x138ed  callvirt instance string [System.Web]System.Web.HttpRequest::get_Item(string)
0x138f2  stelem.ref
0x138f3  dup
0x138f4  ldc.i4.3
0x138f5  ldarg.0
0x138f6  callvirt instance class [System.Web]System.Web.UI.Page [System.Web]System.Web.UI.Control::get_Page()
0x138fb  callvirt instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x13900  ldstr    aZoomlevel// "zoomLevel"
0x13905  callvirt instance string [System.Web]System.Web.HttpRequest::get_Item(string)
0x1390a  stelem.ref
0x1390b  dup
0x1390c  ldc.i4.4
0x1390d  ldarg.0
0x1390e  callvirt instance class [System.Web]System.Web.UI.Page [System.Web]System.Web.UI.Control::get_Page()
0x13913  callvirt instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x13918  ldstr    aShowconflict// "showConflict"
0x1391d  callvirt instance string [System.Web]System.Web.HttpRequest::get_Item(string)
0x13922  stelem.ref
0x13923  dup
0x13924  ldc.i4.5
0x13925  ldarg.0
0x13926  callvirt instance class [System.Web]System.Web.UI.Page [System.Web]System.Web.UI.Control::get_Page()
0x1392b  callvirt instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x13930  ldstr    aViewid// "viewID"
0x13935  callvirt instance string [System.Web]System.Web.HttpRequest::get_Item(string)
0x1393a  stelem.ref
0x1393b  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x13940  ldarg.0
0x13941  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Select Microsoft.Crm.Service.Application.Pages.SM.AppointmentBook.AppointmentHome::crmTypeSelector
0x13946  ldarg.0
0x13947  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x1394c  ldstr    aAppointmentBoo_3// "Appointment_Book_Type_Appointments_And_"...
0x13951  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x13956  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x1395b  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x13960  ldc.i4   0x1068
0x13965  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::GetEntity(int32)
0x1396a  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_LogicalName()
0x1396f  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Select::AddItem(string, string)
0x13974  ldarg.0
0x13975  ldc.i4   0x1076
0x1397a  call     instance void Microsoft.Crm.Service.Application.Pages.SM.AppointmentBook.AppointmentHome::AddEntityTypeOption(int32 entityType)
0x1397f  ldarg.0
0x13980  ldc.i4   0x1069
0x13985  call     instance void Microsoft.Crm.Service.Application.Pages.SM.AppointmentBook.AppointmentHome::AddEntityTypeOption(int32 entityType)
0x1398a  ldarg.0
0x1398b  ldc.i4   0xFA2
0x13990  call     instance void Microsoft.Crm.Service.Application.Pages.SM.AppointmentBook.AppointmentHome::AddEntityTypeOption(int32 entityType)
0x13995  ldarg.0
0x13996  ldc.i4.8
0x13997  call     instance void Microsoft.Crm.Service.Application.Pages.SM.AppointmentBook.AppointmentHome::AddEntityTypeOption(int32 entityType)
0x1399c  ldarg.0
0x1399d  ldc.i4   0xFA0
0x139a2  call     instance void Microsoft.Crm.Service.Application.Pages.SM.AppointmentBook.AppointmentHome::AddEntityTypeOption(int32 entityType)
0x139a7  ldarg.0
0x139a8  callvirt instance class [System.Web]System.Web.UI.Page [System.Web]System.Web.UI.Control::get_Page()
0x139ad  callvirt instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x139b2  ldstr    aType// "type"
0x139b7  callvirt instance string [System.Web]System.Web.HttpRequest::get_Item(string)
0x139bc  stloc.2
0x139bd  ldarg.0
0x139be  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Select Microsoft.Crm.Service.Application.Pages.SM.AppointmentBook.AppointmentHome::crmTypeSelector
0x139c3  ldloc.2
0x139c4  brtrue.s loc_139E1
0x139c6  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x139cb  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
  ... truncated ...
```
