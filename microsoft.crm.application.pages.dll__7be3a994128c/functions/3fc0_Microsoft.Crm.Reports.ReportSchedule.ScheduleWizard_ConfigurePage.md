# Microsoft.Crm.Reports.ReportSchedule.ScheduleWizard::ConfigurePage

- ea: `0x3fc0`
- end: `0x4a4e`
- name: `Microsoft.Crm.Reports.ReportSchedule.ScheduleWizard::ConfigurePage`
- size: `2702`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0x3fc0`

## string_xrefs

- `0x41c3`: `/_common/styles/dialogs.css.aspx`
- `0x4001`: `<columnset><column>name</column><column>reporttypecode</column><column>isscheduledreport</column><column>schedulexml</column><column>defaultfilter</column><column>bodytext</column></columnset>`
- `0x406b`: `isscheduledreport`
- `0x4156`: `schedulexml`
- `0x41b3`: `/_static/_common/styles/AutoToolTip.js`
- `0x41e4`: `/_common/styles/miniCal.css.aspx`
- `0x42c9`: `LOCID_BUTTON_CREATE`
- `0x42d4`: `Button_Create`
- `0x42ea`: `LOCID_BUTTON_UPDATE`
- `0x42f5`: `Button_Update`
- `0x434d`: `LOCID_SNAPSHOT_COPY_SUFFIX`
- `0x436e`: `LOCID_SCHEDULE_COPY_SUFFIX`
- `0x438f`: `LOCID_SUMHEAD_SNAP_CREATEGEN`
- `0x439a`: `Head_SnapshotCreateGenerateSuccess`
- `0x43b0`: `LOCID_SUMHEAD_SNAP_CREATE`
- `0x43bb`: `Head_SnapshotCreateSuccess`
- `0x43d1`: `LOCID_SUMHEAD_SNAP_UPDATEGEN`
- `0x43dc`: `Head_SnapshotUpdateGenerateSuccess`
- `0x43f2`: `LOCID_SUMHEAD_SNAP_UPDATE`
- `0x43fd`: `Head_SnapshotUpdateSuccess`
- `0x4476`: `LOCID_DESC_SCHED_CREATE_SUMMARY`
- `0x4481`: `Desc_ScheduleCreateSummary`
- `0x4497`: `LOCID_DESC_SCHED_UPDATE_SUMMARY`
- `0x44a2`: `Desc_ScheduleUpdateSummary`
- `0x45d1`: `LOCID_HEAD_SCHEDUPDATEFIRST`
- `0x45dc`: `Header_ScheduleUpdateFirst`
- `0x45f2`: `LOCID_HEADDESC_SCHEDUPDATEFIRST`
- `0x45fd`: `HeaderDesc_ScheduleUpdateFirst`
- `0x4613`: `LOCID_HEAD_SNAPUPDATEFIRST`
- `0x461e`: `Header_SnapshotUpdateFirst`
- `0x4634`: `LOCID_HEADDESC_SNAPUPDATEFIRST`
- `0x463f`: `HeaderDesc_SnapshotUpdateFirst`
- `0x4886`: `LOCID_HEADDESC_SUCCSNAPCREATE`
- `0x4891`: `HeaderDesc_SuccessSnapshotCreate`
- `0x48a7`: `LOCID_HEADDESC_SUCCSNAPUPDATE`
- `0x48b2`: `HeaderDesc_SuccessSnapshotUpdate`
- `0x48c8`: `WIZARD_TYPE_CREATE`
- `0x48f2`: `WIZARD_TYPE_UPDATE`
- `0x4a2e`: `ScheduleService`

## pseudocode

```c

```

## disassembly

```asm
0x3fc0  ldarg.0
0x3fc1  ldarg.0
0x3fc2  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x3fc7  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x3fcc  ldstr    aId// "id"
0x3fd1  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x3fd6  stfld    string Microsoft.Crm.Reports.ReportSchedule.ScheduleWizard::_reportBaseId
0x3fdb  ldarg.0
0x3fdc  ldstr    aReport// "report"
0x3fe1  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x3fe6  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x3feb  newobj   instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Report::.ctor(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType)
0x3ff0  stfld    class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Report Microsoft.Crm.Reports.ReportSchedule.ScheduleWizard::_report
0x3ff5  ldarg.0
0x3ff6  ldfld    class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Report Microsoft.Crm.Reports.ReportSchedule.ScheduleWizard::_report
0x3ffb  ldarg.0
0x3ffc  ldfld    string Microsoft.Crm.Reports.ReportSchedule.ScheduleWizard::_reportBaseId
0x4001  ldstr    aColumnsetColum_1// "<columnset><column>name</column><column"...
0x4006  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityProxy::Retrieve(string, string)
0x400b  ldarg.0
0x400c  ldfld    class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Report Microsoft.Crm.Reports.ReportSchedule.ScheduleWizard::_report
0x4011  ldstr    aBodytext// "bodytext"
0x4016  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0x401b  castclass [mscorlib]System.String
0x4020  newobj   instance void [Microsoft.Crm.Reporting]Microsoft.Crm.Reporting.SRSReport::.ctor(string)
0x4025  callvirt instance valuetype [Microsoft.Crm.Reporting]Microsoft.Crm.Reporting.DataProviderType [Microsoft.Crm.Reporting]Microsoft.Crm.Reporting.SRSReport::get_MSCRMDataSourceType()
0x402a  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x402f  call     void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.DataSource::ConfigureReportingDataConnector(valuetype [Microsoft.Crm.Reporting]Microsoft.Crm.Reporting.DataProviderType, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x4034  ldarg.0
0x4035  ldfld    class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Report Microsoft.Crm.Reports.ReportSchedule.ScheduleWizard::_report
0x403a  ldstr    aName// "name"
0x403f  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0x4044  castclass [mscorlib]System.String
0x4049  stloc.0
0x404a  ldarg.0
0x404b  ldfld    class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Report Microsoft.Crm.Reports.ReportSchedule.ScheduleWizard::_report
0x4050  ldstr    aReporttypecode// "reporttypecode"
0x4055  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0x405a  unbox.any [mscorlib]System.Int32
0x405f  ldc.i4.1
0x4060  bne.un   loc_418D
0x4065  ldarg.0
0x4066  ldfld    class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Report Microsoft.Crm.Reports.ReportSchedule.ScheduleWizard::_report
0x406b  ldstr    aIsscheduledrep// "isscheduledreport"
0x4070  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0x4075  unbox.any [mscorlib]System.Boolean
0x407a  brfalse.s loc_4085
0x407c  ldarg.0
0x407d  ldc.i4.1
0x407e  stfld    valuetype WizardType Microsoft.Crm.Reports.ReportSchedule.ScheduleWizard::_wizardType
0x4083  br.s     loc_408C
0x4085  ldarg.0
0x4086  ldc.i4.0
0x4087  stfld    valuetype WizardType Microsoft.Crm.Reports.ReportSchedule.ScheduleWizard::_wizardType
0x408c  ldarg.0
0x408d  ldfld    class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Report Microsoft.Crm.Reports.ReportSchedule.ScheduleWizard::_report
0x4092  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Id()
0x4097  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x409c  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x40a1  call     int32 [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.DataSource::GetReportHistoryLimit(valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x40a6  stloc.1
0x40a7  ldloc.1
0x40a8  ldc.i4.0
0x40a9  ble.s    loc_40B2
0x40ab  ldarg.0
0x40ac  ldloc.1
0x40ad  stfld    int32 Microsoft.Crm.Reports.ReportSchedule.ScheduleWizard::_reportHistoryLimit
0x40b2  ldarg.0
0x40b3  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.DateTimeUI Microsoft.Crm.Reports.ReportSchedule.ScheduleWizard::dtuiStart
0x40b8  ldc.i4.0
0x40b9  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.DateTimeUIBase::set_AllowBlankDate(bool)
0x40be  ldarg.0
0x40bf  ldfld    class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Report Microsoft.Crm.Reports.ReportSchedule.ScheduleWizard::_report
0x40c4  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Id()
0x40c9  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x40ce  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x40d3  call     class [Microsoft.Crm.ReportObjectModel]Microsoft.Crm.ReportObjectModel.CrmReportParameter[] [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.DataSource::GetReportParameters(valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x40d8  stloc.2
0x40d9  ldarg.0
0x40da  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.ParameterControl Microsoft.Crm.Reports.ReportSchedule.ScheduleWizard::pc
0x40df  ldloc.2
0x40e0  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.ParameterControl::set_Parameters(class [Microsoft.Crm.ReportObjectModel]Microsoft.Crm.ReportObjectModel.CrmReportParameter[])
0x40e5  ldarg.0
0x40e6  ldfld    class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Report Microsoft.Crm.Reports.ReportSchedule.ScheduleWizard::_report
0x40eb  ldstr    aDefaultfilter// "defaultfilter"
0x40f0  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0x40f5  castclass [mscorlib]System.String
0x40fa  call     class [System.Xml]System.Xml.XmlDocument [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Reports.ReportUtility::GetAndVerifyFilter(string)
0x40ff  stloc.3
0x4100  ldloc.3
0x4101  ldstr    aReportfilterRe// "/ReportFilter/ReportEntity"
0x4106  callvirt instance class [System.Xml]System.Xml.XmlNodeList [System.Xml]System.Xml.XmlNode::SelectNodes(string)
0x410b  callvirt instance int32 [System.Xml]System.Xml.XmlNodeList::get_Count()
0x4110  ldc.i4.0
0x4111  ble.s    loc_4121
0x4113  ldarg.0
0x4114  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppFilterEditor Microsoft.Crm.Reports.ReportSchedule.ScheduleWizard::filterEditor
0x4119  ldloc.3
0x411a  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppFilterEditor::set_DefaultFilter(class [System.Xml]System.Xml.XmlDocument)
0x411f  br.s     loc_4147
0x4121  ldarg.0
0x4122  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppFilterEditor Microsoft.Crm.Reports.ReportSchedule.ScheduleWizard::filterEditor
0x4127  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x412c  ldstr    aReportviewerMe// "ReportViewer_Message_NotFilterable"
0x4131  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x4136  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppFilterEditor::set_DisabledMessage(string)
0x413b  ldarg.0
0x413c  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppFilterEditor Microsoft.Crm.Reports.ReportSchedule.ScheduleWizard::filterEditor
0x4141  ldc.i4.1
0x4142  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::set_Disabled(bool)
0x4147  ldarg.0
0x4148  ldfld    valuetype WizardType Microsoft.Crm.Reports.ReportSchedule.ScheduleWizard::_wizardType
0x414d  ldc.i4.1
0x414e  bne.un.s loc_418D
0x4150  ldarg.0
0x4151  ldfld    class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Report Microsoft.Crm.Reports.ReportSchedule.ScheduleWizard::_report
0x4156  ldstr    aSchedulexml// "schedulexml"
0x415b  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0x4160  castclass [mscorlib]System.String
0x4165  stloc.s  4
0x4167  ldarg.0
0x4168  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.FrequencyControl Microsoft.Crm.Reports.ReportSchedule.ScheduleWizard::fc
0x416d  ldloc.s  4
0x416f  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.FrequencyControl::set_ScheduleDefinitionXml(string)
0x4174  ldloc.s  4
0x4176  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x417b  brfalse.s loc_4186
0x417d  ldarg.0
0x417e  ldc.i4.1
0x417f  stfld    valuetype WizardObject Microsoft.Crm.Reports.ReportSchedule.ScheduleWizard::_wizardObject
0x4184  br.s     loc_418D
0x4186  ldarg.0
0x4187  ldc.i4.0
0x4188  stfld    valuetype WizardObject Microsoft.Crm.Reports.ReportSchedule.ScheduleWizard::_wizardObject
0x418d  ldarg.0
0x418e  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x4193  ldstr    aStaticControls// "/_static/_controls/datetime/date.js"
0x4198  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x419d  ldarg.0
0x419e  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x41a3  ldstr    aStaticControls_0// "/_static/_controls/datetime/time.js"
0x41a8  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x41ad  ldarg.0
0x41ae  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x41b3  ldstr    aStaticCommonSt// "/_static/_common/styles/AutoToolTip.js"
0x41b8  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x41bd  ldarg.0
0x41be  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x41c3  ldstr    aCommonStylesDi// "/_common/styles/dialogs.css.aspx"
0x41c8  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0x41cd  ldarg.0
0x41ce  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x41d3  ldstr    aMscrmDialogsco// "Mscrm.DialogsControl"
0x41d8  ldnull
0x41d9  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::CreateClientAjaxComponent(string, string)
0x41de  ldarg.0
0x41df  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x41e4  ldstr    aCommonStylesMi// "/_common/styles/miniCal.css.aspx"
0x41e9  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0x41ee  ldarg.0
0x41ef  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x41f4  ldstr    aFormsControlsC// "/_forms/controls/controls.css.aspx"
0x41f9  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0x41fe  ldarg.0
0x41ff  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x4204  ldstr    aFormsControlsF// "/_forms/controls/form.css.aspx"
0x4209  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0x420e  ldarg.0
0x420f  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x4214  ldstr    aCrmreportsRepo// "/crmreports/reportschedule/schedulewiza"...
0x4219  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0x421e  ldarg.0
0x421f  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x4224  ldstr    aLocidWarnClose// "LOCID_WARN_CLOSE_WIZARD"
0x4229  ldarg.0
0x422a  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x422f  ldstr    aWarnClosewizar// "Warn_CloseWizard"
0x4234  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x4239  ldc.i4.0
0x423a  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x423f  ldarg.0
0x4240  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x4245  ldstr    aLocidInProgres// "LOCID_IN_PROGRESS_PROCESSING"
0x424a  ldarg.0
0x424b  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x4250  ldstr    aInprogressProc// "InProgress_ProcessingRequest"
0x4255  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x425a  ldc.i4.0
0x425b  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x4260  ldarg.0
0x4261  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x4266  ldstr    aLocidButtonFin// "LOCID_BUTTON_FINISH"
0x426b  ldarg.0
0x426c  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x4271  ldstr    aButtonFinish// "Button_Finish"
0x4276  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x427b  ldc.i4.0
0x427c  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x4281  ldarg.0
0x4282  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x4287  ldstr    aLocidButtonNex// "LOCID_BUTTON_NEXT"
0x428c  ldarg.0
0x428d  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x4292  ldstr    aButtonNext// "Button_Next"
0x4297  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x429c  ldc.i4.0
0x429d  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x42a2  ldarg.0
0x42a3  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x42a8  ldstr    aLocidButtonSav// "LOCID_BUTTON_SAVE"
0x42ad  ldarg.0
0x42ae  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x42b3  ldstr    aButtonSave// "Button_Save"
0x42b8  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x42bd  ldc.i4.0
0x42be  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x42c3  ldarg.0
0x42c4  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x42c9  ldstr    aLocidButtonCre// "LOCID_BUTTON_CREATE"
0x42ce  ldarg.0
0x42cf  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x42d4  ldstr    aButtonCreate// "Button_Create"
0x42d9  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x42de  ldc.i4.0
0x42df  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x42e4  ldarg.0
0x42e5  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x42ea  ldstr    aLocidButtonUpd// "LOCID_BUTTON_UPDATE"
0x42ef  ldarg.0
0x42f0  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x42f5  ldstr    aButtonUpdate// "Button_Update"
0x42fa  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x42ff  ldc.i4.0
0x4300  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x4305  ldarg.0
0x4306  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x430b  ldstr    aLocidErrorStar// "LOCID_ERROR_START_AFTER_END"
0x4310  ldarg.0
0x4311  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x4316  ldstr    aErrorStartafte// "Error_StartAfterEnd"
0x431b  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x4320  ldc.i4.0
0x4321  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x4326  ldarg.0
0x4327  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x432c  ldstr    aLocidNotSrsRep// "LOCID_NOT_SRS_REPORT"
0x4331  ldarg.0
0x4332  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x4337  ldstr    aErrorNotsrsrep// "Error_NotSRSReport"
0x433c  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x4341  ldc.i4.0
0x4342  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x4347  ldarg.0
0x4348  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x434d  ldstr    aLocidSnapshotC// "LOCID_SNAPSHOT_COPY_SUFFIX"
0x4352  ldarg.0
0x4353  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x4358  ldstr    aSuffixSnapshot// "Suffix_SnapshotReport"
0x435d  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x4362  ldc.i4.0
0x4363  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x4368  ldarg.0
0x4369  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x436e  ldstr    aLocidScheduleC// "LOCID_SCHEDULE_COPY_SUFFIX"
0x4373  ldarg.0
0x4374  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x4379  ldstr    aSuffixSchedule// "Suffix_ScheduleReport"
0x437e  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x4383  ldc.i4.0
0x4384  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x4389  ldarg.0
0x438a  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x438f  ldstr    aLocidSumheadSn// "LOCID_SUMHEAD_SNAP_CREATEGEN"
0x4394  ldarg.0
0x4395  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x439a  ldstr    aHeadSnapshotcr// "Head_SnapshotCreateGenerateSuccess"
0x439f  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x43a4  ldc.i4.0
0x43a5  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x43aa  ldarg.0
0x43ab  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x43b0  ldstr    aLocidSumheadSn_0// "LOCID_SUMHEAD_SNAP_CREATE"
0x43b5  ldarg.0
0x43b6  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x43bb  ldstr    aHeadSnapshotcr_0// "Head_SnapshotCreateSuccess"
0x43c0  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x43c5  ldc.i4.0
0x43c6  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x43cb  ldarg.0
0x43cc  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x43d1  ldstr    aLocidSumheadSn_1// "LOCID_SUMHEAD_SNAP_UPDATEGEN"
0x43d6  ldarg.0
0x43d7  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x43dc  ldstr    aHeadSnapshotup// "Head_SnapshotUpdateGenerateSuccess"
0x43e1  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x43e6  ldc.i4.0
0x43e7  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x43ec  ldarg.0
0x43ed  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x43f2  ldstr    aLocidSumheadSn_2// "LOCID_SUMHEAD_SNAP_UPDATE"
  ... truncated ...
```
