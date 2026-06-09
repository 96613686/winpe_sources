# Microsoft.Crm.Common.Application.Components.PageHandlers.RecurringAppointmentMasterRecordPageHandler::ConfigureHeaderHandler

- ea: `0x10db0`
- end: `0x10fe4`
- name: `Microsoft.Crm.Common.Application.Components.PageHandlers.RecurringAppointmentMasterRecordPageHandler::ConfigureHeaderHandler`
- size: `564`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callees

- `0x10db0`
- `0x11300`
- `0x11510`
- `0x11b00`

## string_xrefs

- `0x10dea`: `_syncCreateMax`
- `0x10e44`: `_redirectNewUrlOnUpdate`
- `0x10ea2`: `appointmentXml`
- `0x10eb9`: `_recurrenceUpdated`
- `0x10faa`: `Add Custom Remote Command Error handler`
- `0x10faf`: `customRemoteCommandErrorHandler = Mscrm.RecurringAppointment.remoteCommandErrorHandler;`

## pseudocode

```c

```

## disassembly

```asm
0x10db0  ldarg.0
0x10db1  call     instance void Microsoft.Crm.Common.Application.Components.PageHandlers.BasicActivityRecordPageHandler::ConfigureHeaderHandler()
0x10db6  ldarg.0
0x10db7  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppHeader [Microsoft.Crm.Application.Pages]Microsoft.Crm.Application.Components.PageHandlers.RecordPageHandler::get_CurrentHeader()
0x10dbc  ldstr    aFutureexpansio// "_futureExpansionWindow"
0x10dc1  ldarg.0
0x10dc2  ldfld    int32 Microsoft.Crm.Common.Application.Components.PageHandlers.RecurringAppointmentMasterRecordPageHandler::_futureExpansionWindow
0x10dc7  conv.i8
0x10dc8  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, int64)
0x10dcd  ldarg.0
0x10dce  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppHeader [Microsoft.Crm.Application.Pages]Microsoft.Crm.Application.Components.PageHandlers.RecordPageHandler::get_CurrentHeader()
0x10dd3  ldstr    aPastexpansionw// "_pastExpansionWindow"
0x10dd8  ldarg.0
0x10dd9  ldfld    int32 Microsoft.Crm.Common.Application.Components.PageHandlers.RecurringAppointmentMasterRecordPageHandler::_pastExpansionWindow
0x10dde  conv.i8
0x10ddf  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, int64)
0x10de4  ldarg.0
0x10de5  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppHeader [Microsoft.Crm.Application.Pages]Microsoft.Crm.Application.Components.PageHandlers.RecordPageHandler::get_CurrentHeader()
0x10dea  ldstr    aSynccreatemax// "_syncCreateMax"
0x10def  ldarg.0
0x10df0  ldfld    int32 Microsoft.Crm.Common.Application.Components.PageHandlers.RecurringAppointmentMasterRecordPageHandler::_syncCreateMax
0x10df5  conv.i8
0x10df6  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, int64)
0x10dfb  ldarg.0
0x10dfc  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppHeader [Microsoft.Crm.Application.Pages]Microsoft.Crm.Application.Components.PageHandlers.RecordPageHandler::get_CurrentHeader()
0x10e01  ldstr    aIactivitytypec// "_iActivityTypeCode"
0x10e06  ldarg.0
0x10e07  call     instance class [Microsoft.Crm.Common.Application.Platform]Microsoft.Crm.Common.Application.Platform.ActivityBase Microsoft.Crm.Common.Application.Components.PageHandlers.BasicActivityRecordPageHandler::get_CurrentActivity()
0x10e0c  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_EntityType()
0x10e11  callvirt instance int32 [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::get_TypeCode()
0x10e16  conv.i8
0x10e17  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, int64)
0x10e1c  ldarg.0
0x10e1d  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppHeader [Microsoft.Crm.Application.Pages]Microsoft.Crm.Application.Components.PageHandlers.RecordPageHandler::get_CurrentHeader()
0x10e22  ldstr    aBenableschedul// "_bEnableSchedulingDialog"
0x10e27  ldc.i4.0
0x10e28  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, bool)
0x10e2d  ldarg.0
0x10e2e  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppHeader [Microsoft.Crm.Application.Pages]Microsoft.Crm.Application.Components.PageHandlers.RecordPageHandler::get_CurrentHeader()
0x10e33  ldstr    aBallowschedule// "_bAllowSchedule"
0x10e38  ldc.i4.1
0x10e39  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, bool)
0x10e3e  ldarg.0
0x10e3f  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppHeader [Microsoft.Crm.Application.Pages]Microsoft.Crm.Application.Components.PageHandlers.RecordPageHandler::get_CurrentHeader()
0x10e44  ldstr    aRedirectnewurl// "_redirectNewUrlOnUpdate"
0x10e49  ldc.i4.1
0x10e4a  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, bool)
0x10e4f  ldarg.0
0x10e50  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Common.Application.Components.PageHandlers.RecurringAppointmentMasterRecordPageHandler::_appointmentId
0x10e55  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x10e5a  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x10e5f  brfalse.s loc_10E77
0x10e61  ldarg.0
0x10e62  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppHeader [Microsoft.Crm.Application.Pages]Microsoft.Crm.Application.Components.PageHandlers.RecordPageHandler::get_CurrentHeader()
0x10e67  ldstr    aAppointid// "_appointId"
0x10e6c  ldarg.0
0x10e6d  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Common.Application.Components.PageHandlers.RecurringAppointmentMasterRecordPageHandler::_appointmentId
0x10e72  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, valuetype [mscorlib]System.Guid)
0x10e77  ldarg.0
0x10e78  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm [Microsoft.Crm.Application.Pages]Microsoft.Crm.Application.Components.PageHandlers.RecordPageHandler::get_CurrentForm()
0x10e7d  callvirt instance valuetype [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.FormState [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm::get_State()
0x10e82  ldc.i4.1
0x10e83  ceq
0x10e85  stloc.0
0x10e86  ldarg.0
0x10e87  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppHeader [Microsoft.Crm.Application.Pages]Microsoft.Crm.Application.Components.PageHandlers.RecordPageHandler::get_CurrentHeader()
0x10e8c  ldstr    aBisnew// "_bIsNew"
0x10e91  ldloc.0
0x10e92  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, bool)
0x10e97  ldarg.0
0x10e98  call     instance class [System.Web]System.Web.HttpRequest [Microsoft.Crm.Application.Pages]Microsoft.Crm.Application.Components.PageHandlers.RecordPageHandler::get_Request()
0x10e9d  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_Form()
0x10ea2  ldstr    aAppointmentxml// "appointmentXml"
0x10ea7  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x10eac  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x10eb1  brtrue.s loc_10EC4
0x10eb3  ldarg.0
0x10eb4  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppHeader [Microsoft.Crm.Application.Pages]Microsoft.Crm.Application.Components.PageHandlers.RecordPageHandler::get_CurrentHeader()
0x10eb9  ldstr    aRecurrenceupda// "_recurrenceUpdated"
0x10ebe  ldc.i4.1
0x10ebf  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, bool)
0x10ec4  ldarg.0
0x10ec5  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppHeader [Microsoft.Crm.Application.Pages]Microsoft.Crm.Application.Components.PageHandlers.RecordPageHandler::get_CurrentHeader()
0x10eca  ldstr    aSeriesactive// "_seriesActive"
0x10ecf  ldarg.0
0x10ed0  call     instance bool Microsoft.Crm.Common.Application.Components.PageHandlers.RecurringAppointmentMasterRecordPageHandler::IsSeriesActive()
0x10ed5  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, bool)
0x10eda  ldarg.0
0x10edb  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppHeader [Microsoft.Crm.Application.Pages]Microsoft.Crm.Application.Components.PageHandlers.RecordPageHandler::get_CurrentHeader()
0x10ee0  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::AddWrpcTokenActionPath()
0x10ee5  ldarg.0
0x10ee6  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppHeader [Microsoft.Crm.Application.Pages]Microsoft.Crm.Application.Components.PageHandlers.RecordPageHandler::get_CurrentHeader()
0x10eeb  ldstr    aInitializeForm// "Initialize Form"
0x10ef0  ldstr    aMscrmRecurring// "Mscrm.RecurringAppointment.initializeRe"...
0x10ef5  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptBlockForOnLoad(string, string)
0x10efa  ldarg.0
0x10efb  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppHeader [Microsoft.Crm.Application.Pages]Microsoft.Crm.Application.Components.PageHandlers.RecordPageHandler::get_CurrentHeader()
0x10f00  ldstr    aLocidEndseries// "LOCID_ENDSERIESDLG_WIDTH"
0x10f05  ldarg.0
0x10f06  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Pages]Microsoft.Crm.Application.Components.PageHandlers.RecordPageHandler::get_CurrentResourceManager()
0x10f0b  ldstr    aActivitiesActD_2// "activities/act_dlgs/dlg_seriesaction.as"...
0x10f10  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x10f15  ldc.i4.0
0x10f16  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x10f1b  ldarg.0
0x10f1c  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppHeader [Microsoft.Crm.Application.Pages]Microsoft.Crm.Application.Components.PageHandlers.RecordPageHandler::get_CurrentHeader()
0x10f21  ldstr    aLocidEndseries_0// "LOCID_ENDSERIESDLG_HEIGHT"
0x10f26  ldarg.0
0x10f27  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Pages]Microsoft.Crm.Application.Components.PageHandlers.RecordPageHandler::get_CurrentResourceManager()
0x10f2c  ldstr    aActivitiesActD_3// "activities/act_dlgs/dlg_seriesaction.as"...
0x10f31  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x10f36  ldc.i4.0
0x10f37  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x10f3c  ldarg.0
0x10f3d  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppHeader [Microsoft.Crm.Application.Pages]Microsoft.Crm.Application.Components.PageHandlers.RecordPageHandler::get_CurrentHeader()
0x10f42  ldstr    aLocidRecurdlgW// "LOCID_RECURDLG_WIDTH"
0x10f47  ldarg.0
0x10f48  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Pages]Microsoft.Crm.Application.Components.PageHandlers.RecordPageHandler::get_CurrentResourceManager()
0x10f4d  ldstr    aActivitiesActD_34// "activities_act_dlgs_recurrencedialog_WI"...
0x10f52  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x10f57  ldc.i4.0
0x10f58  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x10f5d  ldarg.0
0x10f5e  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppHeader [Microsoft.Crm.Application.Pages]Microsoft.Crm.Application.Components.PageHandlers.RecordPageHandler::get_CurrentHeader()
0x10f63  ldstr    aLocidRecurdlgH// "LOCID_RECURDLG_HEIGHT"
0x10f68  ldarg.0
0x10f69  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Pages]Microsoft.Crm.Application.Components.PageHandlers.RecordPageHandler::get_CurrentResourceManager()
0x10f6e  ldstr    aActivitiesActD_35// "activities_act_dlgs_recurrencedialog_WI"...
0x10f73  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x10f78  ldc.i4.0
0x10f79  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x10f7e  ldarg.0
0x10f7f  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppHeader [Microsoft.Crm.Application.Pages]Microsoft.Crm.Application.Components.PageHandlers.RecordPageHandler::get_CurrentHeader()
0x10f84  ldstr    aAddCustomError// "Add Custom Error handler"
0x10f89  ldstr    aCustomerrorhan// "customErrorHandler = Mscrm.RecurringApp"...
0x10f8e  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptBlockForOnLoad(string, string)
0x10f93  ldarg.0
0x10f94  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppHeader [Microsoft.Crm.Application.Pages]Microsoft.Crm.Application.Components.PageHandlers.RecordPageHandler::get_CurrentHeader()
0x10f99  ldstr    aUsecustomrcerr// "_useCustomRCErrorHandler"
0x10f9e  ldc.i4.1
0x10f9f  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, bool)
0x10fa4  ldarg.0
0x10fa5  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppHeader [Microsoft.Crm.Application.Pages]Microsoft.Crm.Application.Components.PageHandlers.RecordPageHandler::get_CurrentHeader()
0x10faa  ldstr    aAddCustomRemot// "Add Custom Remote Command Error handler"
0x10faf  ldstr    aCustomremoteco// "customRemoteCommandErrorHandler = Mscrm"...
0x10fb4  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptBlockForOnLoad(string, string)
0x10fb9  ldarg.0
0x10fba  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppHeader [Microsoft.Crm.Application.Pages]Microsoft.Crm.Application.Components.PageHandlers.RecordPageHandler::get_CurrentHeader()
0x10fbf  ldstr    aAddHandlerWhen// "Add handler when scheduling dialog is c"...
0x10fc4  ldstr    aCancelschedule// "cancelScheduleHandler = Mscrm.Recurring"...
0x10fc9  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptBlockForOnLoad(string, string)
0x10fce  ldarg.0
0x10fcf  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppHeader [Microsoft.Crm.Application.Pages]Microsoft.Crm.Application.Components.PageHandlers.RecordPageHandler::get_CurrentHeader()
0x10fd4  ldstr    aAddCustomGridR// "Add Custom Grid Refresh handler"
0x10fd9  ldstr    aMscrmRecurrenc_3// "Mscrm.RecurrenceUtil.addCustomGridRefre"...
0x10fde  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptBlockForOnLoad(string, string)
0x10fe3  ret
```
