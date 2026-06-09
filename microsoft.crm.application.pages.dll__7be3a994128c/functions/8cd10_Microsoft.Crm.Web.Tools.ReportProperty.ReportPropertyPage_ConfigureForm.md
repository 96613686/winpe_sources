# Microsoft.Crm.Web.Tools.ReportProperty.ReportPropertyPage::ConfigureForm

- ea: `0x8cd10`
- end: `0x8d30e`
- name: `Microsoft.Crm.Web.Tools.ReportProperty.ReportPropertyPage::ConfigureForm`
- size: `1534`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0x8cd10`
- `0x8d370`

## string_xrefs

- `0x8cede`: `isscheduledreport`
- `0x8cd16`: `<columnset><column>reportid</column><column>reporttypecode</column><column>languagecode</column><column>parentreportid</column><column>bodyurl</column><column>name</column><column>description</column><column>filename</column><column>ispersonal</column><column>isscheduledreport</column><column>ownerid</column><column>iscustomreport</column><column>createdby</column><column>createdon</column><column>modifiedby</column><column>modifiedon</column></columnset>`
- `0x8cdf6`: `Web.Reports.ProvisioningIncomplete`
- `0x8ce74`: `Web.Reports.ReportWizard.FetchDataConnectorNotInstalled`

## pseudocode

```c

```

## disassembly

```asm
0x8cd10  ldarg.0
0x8cd11  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::crmForm
0x8cd16  ldstr    aColumnsetColum_11// "<columnset><column>reportid</column><co"...
0x8cd1b  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm::set_ColumnSetXml(string)
0x8cd20  ldarg.0
0x8cd21  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::crmForm
0x8cd26  ldc.i4.4
0x8cd27  ldarg.0
0x8cd28  ldftn    instance void Microsoft.Crm.Web.Tools.ReportProperty.ReportPropertyPage::AfterLoad(object sender, class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DataEventArgs e)
0x8cd2e  newobj   instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DataEventHandler::.ctor(object, native int)
0x8cd33  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm::RegisterAfterDataEvent(valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.FormEventId, class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DataEventHandler)
0x8cd38  ldarg.0
0x8cd39  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::crmForm
0x8cd3e  ldc.i4.s 0x2F
0x8cd40  ldarg.0
0x8cd41  ldftn    instance void Microsoft.Crm.Web.Tools.ReportProperty.ReportPropertyPage::AfterLoad(object sender, class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DataEventArgs e)
0x8cd47  newobj   instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DataEventHandler::.ctor(object, native int)
0x8cd4c  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm::RegisterAfterDataEvent(valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.FormEventId, class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DataEventHandler)
0x8cd51  ldarg.0
0x8cd52  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::crmForm
0x8cd57  ldc.i4.1
0x8cd58  ldarg.0
0x8cd59  ldftn    instance void Microsoft.Crm.Web.Tools.ReportProperty.ReportPropertyPage::Save(object sender, class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DataEventArgs e)
0x8cd5f  newobj   instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DataEventHandler::.ctor(object, native int)
0x8cd64  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm::RegisterDataEvent(valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.FormEventId, class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DataEventHandler)
0x8cd69  ldarg.0
0x8cd6a  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::crmForm
0x8cd6f  ldc.i4.2
0x8cd70  ldarg.0
0x8cd71  ldftn    instance void Microsoft.Crm.Web.Tools.ReportProperty.ReportPropertyPage::Save(object sender, class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DataEventArgs e)
0x8cd77  newobj   instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DataEventHandler::.ctor(object, native int)
0x8cd7c  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm::RegisterDataEvent(valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.FormEventId, class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DataEventHandler)
0x8cd81  ldarg.0
0x8cd82  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::crmForm
0x8cd87  ldc.i4.s 0x3B
0x8cd89  ldarg.0
0x8cd8a  ldftn    instance void Microsoft.Crm.Web.Tools.ReportProperty.ReportPropertyPage::Save(object sender, class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DataEventArgs e)
0x8cd90  newobj   instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DataEventHandler::.ctor(object, native int)
0x8cd95  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm::RegisterDataEvent(valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.FormEventId, class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DataEventHandler)
0x8cd9a  ldarg.0
0x8cd9b  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::crmForm
0x8cda0  ldc.i4.s 0x3C
0x8cda2  ldarg.0
0x8cda3  ldftn    instance void Microsoft.Crm.Web.Tools.ReportProperty.ReportPropertyPage::MakeOrgAvailable(object sender, class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DataEventArgs e)
0x8cda9  newobj   instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DataEventHandler::.ctor(object, native int)
0x8cdae  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm::RegisterDataEvent(valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.FormEventId, class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DataEventHandler)
0x8cdb3  ldarg.0
0x8cdb4  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::crmForm
0x8cdb9  ldc.i4.s 0x3D
0x8cdbb  ldarg.0
0x8cdbc  ldftn    instance void Microsoft.Crm.Web.Tools.ReportProperty.ReportPropertyPage::MakeOrgUnavailable(object sender, class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DataEventArgs e)
0x8cdc2  newobj   instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DataEventHandler::.ctor(object, native int)
0x8cdc7  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm::RegisterDataEvent(valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.FormEventId, class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DataEventHandler)
0x8cdcc  ldarg.0
0x8cdcd  ldfld    class [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.RadioControl Microsoft.Crm.Web.Tools.ReportProperty.ReportPropertyPage::ispersonal
0x8cdd2  call     class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition [Microsoft.Crm.Privileges]Microsoft.Crm.Privileges::get_PublishOrgReport()
0x8cdd7  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x8cddc  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.User::GetPrivilege(class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x8cde1  ldc.i4.0
0x8cde2  ceq
0x8cde4  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::set_Disabled(bool)
0x8cde9  call     bool [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Reports.ReportUtility::IsPostProvisioningComplete()
0x8cdee  brtrue.s loc_8CE61
0x8cdf0  ldarg.0
0x8cdf1  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppNotifications Microsoft.Crm.Web.Tools.ReportProperty.ReportPropertyPage::notifications
0x8cdf6  ldstr    aWebReportsProv// "Web.Reports.ProvisioningIncomplete"
0x8cdfb  ldc.i4.1
0x8cdfc  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppNotifications::AddNotification(string, int32)
0x8ce01  ldarg.0
0x8ce02  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Button Microsoft.Crm.Web.Tools.ReportProperty.ReportPropertyPage::reportWizardButton
0x8ce07  ldc.i4.1
0x8ce08  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::set_Disabled(bool)
0x8ce0d  ldarg.0
0x8ce0e  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::crmForm
0x8ce13  ldc.i4.1
0x8ce14  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm::set_ReadOnly(bool)
0x8ce19  ldarg.0
0x8ce1a  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Select Microsoft.Crm.Web.Tools.ReportProperty.ReportPropertyPage::selectReportType
0x8ce1f  ldc.i4.1
0x8ce20  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::set_Disabled(bool)
0x8ce25  ldarg.0
0x8ce26  ldfld    class [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.RadioControl Microsoft.Crm.Web.Tools.ReportProperty.ReportPropertyPage::ispersonal
0x8ce2b  ldc.i4.1
0x8ce2c  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::set_Disabled(bool)
0x8ce31  ldarg.0
0x8ce32  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.MultiPicklist Microsoft.Crm.Web.Tools.ReportProperty.ReportPropertyPage::picklistCategorySpan
0x8ce37  ldc.i4.1
0x8ce38  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::set_Disabled(bool)
0x8ce3d  ldarg.0
0x8ce3e  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.MultiPicklist Microsoft.Crm.Web.Tools.ReportProperty.ReportPropertyPage::picklistRelatedEntitySpan
0x8ce43  ldc.i4.1
0x8ce44  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::set_Disabled(bool)
0x8ce49  ldarg.0
0x8ce4a  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.MultiPicklist Microsoft.Crm.Web.Tools.ReportProperty.ReportPropertyPage::picklistVisibilitySpan
0x8ce4f  ldc.i4.1
0x8ce50  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::set_Disabled(bool)
0x8ce55  ldarg.0
0x8ce56  ldfld    class [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.LanguagePicker Microsoft.Crm.Web.Tools.ReportProperty.ReportPropertyPage::languagecode
0x8ce5b  ldc.i4.1
0x8ce5c  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::set_Disabled(bool)
0x8ce61  ldc.i4.1
0x8ce62  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x8ce67  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.DataSource::IsReportingDataConnectorInstalled(valuetype [Microsoft.Crm.Reporting]Microsoft.Crm.Reporting.DataProviderType, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x8ce6c  brtrue.s loc_8CE9F
0x8ce6e  ldarg.0
0x8ce6f  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppNotifications Microsoft.Crm.Web.Tools.ReportProperty.ReportPropertyPage::fetchDataConnectorNotification
0x8ce74  ldstr    aWebReportsRepo_0// "Web.Reports.ReportWizard.FetchDataConne"...
0x8ce79  ldc.i4.3
0x8ce7a  ldc.i4.s 0x50
0x8ce7c  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppNotifications::AddNotification(string, int32, int32)
0x8ce81  ldarg.0
0x8ce82  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppNotifications Microsoft.Crm.Web.Tools.ReportProperty.ReportPropertyPage::fetchDataConnectorNotification
0x8ce87  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppNotifications::RegisterClientAjaxComponent()
0x8ce8c  ldarg.0
0x8ce8d  ldc.i4.0
0x8ce8e  stfld    bool Microsoft.Crm.Web.Tools.ReportProperty.ReportPropertyPage::isFetchDataConnectorInstalled
0x8ce93  ldarg.0
0x8ce94  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Button Microsoft.Crm.Web.Tools.ReportProperty.ReportPropertyPage::reportWizardButton
0x8ce99  ldc.i4.1
0x8ce9a  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::set_Disabled(bool)
0x8ce9f  ldarg.0
0x8cea0  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::crmForm
0x8cea5  ldarg.0
0x8cea6  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.EntityPage::get_CurrentEntity()
0x8ceab  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm::Execute(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity)
0x8ceb0  ldarg.0
0x8ceb1  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x8ceb6  ldstr    aBisnew// "_bIsNew"
0x8cebb  ldarg.0
0x8cebc  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.EntityPage::get_CurrentEntity()
0x8cec1  callvirt instance bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_IsNew()
0x8cec6  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, bool)
0x8cecb  ldarg.0
0x8cecc  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.EntityPage::get_CurrentEntity()
0x8ced1  callvirt instance bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_IsNew()
0x8ced6  brtrue.s loc_8CEEF
0x8ced8  ldarg.0
0x8ced9  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.EntityPage::get_CurrentEntity()
0x8cede  ldstr    aIsscheduledrep// "isscheduledreport"
0x8cee3  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0x8cee8  unbox.any [mscorlib]System.Boolean
0x8ceed  br.s     loc_8CEF0
0x8ceef  ldc.i4.0
0x8cef0  stloc.0
0x8cef1  ldarg.0
0x8cef2  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.EntityPage::get_CurrentEntity()
0x8cef7  callvirt instance bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_IsNew()
0x8cefc  brtrue.s loc_8CF18
0x8cefe  ldarg.0
0x8ceff  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.EntityPage::get_CurrentEntity()
0x8cf04  ldstr    aReporttypecode// "reporttypecode"
0x8cf09  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0x8cf0e  unbox.any [mscorlib]System.Int32
0x8cf13  ldc.i4.1
0x8cf14  ceq
0x8cf16  br.s     loc_8CF19
0x8cf18  ldc.i4.0
0x8cf19  stloc.1
0x8cf1a  ldarg.0
0x8cf1b  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.EntityPage::get_CurrentEntity()
0x8cf20  callvirt instance bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_IsNew()
0x8cf25  brtrue.s loc_8CF3E
0x8cf27  ldarg.0
0x8cf28  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.EntityPage::get_CurrentEntity()
0x8cf2d  ldstr    aIscustomreport// "iscustomreport"
0x8cf32  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0x8cf37  unbox.any [mscorlib]System.Boolean
0x8cf3c  br.s     loc_8CF3F
0x8cf3e  ldc.i4.0
0x8cf3f  stloc.2
0x8cf40  ldc.i4.1
0x8cf41  stloc.3
0x8cf42  ldloc.0
0x8cf43  brtrue.s loc_8CF57
0x8cf45  ldarg.0
0x8cf46  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentForm()
0x8cf4b  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.PrivilegeCheck [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm::get_PrivilegeCheck()
0x8cf50  callvirt instance bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.PrivilegeCheck::get_CanWrite()
0x8cf55  brtrue.s loc_8CF89
0x8cf57  ldarg.0
0x8cf58  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Select Microsoft.Crm.Web.Tools.ReportProperty.ReportPropertyPage::selectReportType
0x8cf5d  ldc.i4.1
0x8cf5e  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::set_Disabled(bool)
0x8cf63  ldarg.0
0x8cf64  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Button Microsoft.Crm.Web.Tools.ReportProperty.ReportPropertyPage::reportWizardButton
0x8cf69  ldc.i4.1
0x8cf6a  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::set_Disabled(bool)
0x8cf6f  ldarg.0
0x8cf70  ldfld    class [System.Web]System.Web.UI.HtmlControls.HtmlInputFile Microsoft.Crm.Web.Tools.ReportProperty.ReportPropertyPage::Template
0x8cf75  ldc.i4.1
0x8cf76  callvirt instance void [System.Web]System.Web.UI.HtmlControls.HtmlControl::set_Disabled(bool)
0x8cf7b  ldarg.0
0x8cf7c  ldfld    class [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.UrlControl Microsoft.Crm.Web.Tools.ReportProperty.ReportPropertyPage::bodyurl
0x8cf81  ldc.i4.1
0x8cf82  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::set_Disabled(bool)
0x8cf87  ldc.i4.0
0x8cf88  stloc.3
0x8cf89  ldarg.0
0x8cf8a  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x8cf8f  ldstr    aBenableupload// "_bEnableUpload"
0x8cf94  ldloc.3
0x8cf95  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, bool)
0x8cf9a  ldarg.0
0x8cf9b  ldloc.2
0x8cf9c  call     instance void Microsoft.Crm.Web.Tools.ReportProperty.ReportPropertyPage::SetUpReportTypeSelect(bool isWizardReport)
0x8cfa1  ldarg.0
0x8cfa2  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x8cfa7  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x8cfac  ldstr    aFromwizard// "fromwizard"
0x8cfb1  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x8cfb6  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x8cfbb  brtrue.s loc_8CFEF
0x8cfbd  ldarg.0
0x8cfbe  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x8cfc3  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x8cfc8  ldstr    aFromwizard// "fromwizard"
0x8cfcd  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x8cfd2  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x8cfd7  call     bool [mscorlib]System.Convert::ToBoolean(string, class [mscorlib]System.IFormatProvider)
0x8cfdc  brfalse.s loc_8CFEF
0x8cfde  ldarg.0
0x8cfdf  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppNotifications Microsoft.Crm.Web.Tools.ReportProperty.ReportPropertyPage::notifications
0x8cfe4  ldstr    aWebReportsWiza// "Web.Reports.WizardNotification"
0x8cfe9  ldc.i4.3
0x8cfea  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppNotifications::AddNotification(string, int32)
0x8cfef  ldarg.0
0x8cff0  ldfld    class [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.LookupControl Microsoft.Crm.Web.Tools.ReportProperty.ReportPropertyPage::parentreportid
0x8cff5  ldc.i4.0
0x8cff6  callvirt instance void [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.LookupControl::set_ShowProperty(bool)
0x8cffb  ldarg.0
0x8cffc  ldfld    class [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.LookupControl Microsoft.Crm.Web.Tools.ReportProperty.ReportPropertyPage::parentreportid
0x8d001  ldc.i4.1
0x8d002  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::set_Disabled(bool)
0x8d007  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.User::get_Current()
0x8d00c  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.ISecurityPrincipal::get_OrganizationId()
0x8d011  call     bool [Microsoft.Crm]Microsoft.Crm.ApplicationConfig::AllowReportDefinitionUpload(valuetype [mscorlib]System.Guid)
0x8d016  ldloc.1
0x8d017  and
0x8d018  brfalse.s loc_8D03B
0x8d01a  ldarg.0
0x8d01b  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentForm()
0x8d020  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.PrivilegeCheck [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm::get_PrivilegeCheck()
0x8d025  callvirt instance bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.PrivilegeCheck::get_CanWrite()
0x8d02a  brfalse.s loc_8D03B
0x8d02c  ldloc.0
0x8d02d  brtrue.s loc_8D03B
0x8d02f  ldarg.0
0x8d030  ldfld    class [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.LookupControl Microsoft.Crm.Web.Tools.ReportProperty.ReportPropertyPage::parentreportid
0x8d035  ldc.i4.0
0x8d036  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::set_Disabled(bool)
0x8d03b  ldarg.0
0x8d03c  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentForm()
0x8d041  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.PrivilegeCheck [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm::get_PrivilegeCheck()
0x8d046  callvirt instance bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.PrivilegeCheck::get_CanWrite()
0x8d04b  brtrue.s loc_8D07D
0x8d04d  ldarg.0
0x8d04e  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.MultiPicklist Microsoft.Crm.Web.Tools.ReportProperty.ReportPropertyPage::picklistCategorySpan
0x8d053  ldc.i4.1
0x8d054  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::set_Disabled(bool)
0x8d059  ldarg.0
0x8d05a  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.MultiPicklist Microsoft.Crm.Web.Tools.ReportProperty.ReportPropertyPage::picklistRelatedEntitySpan
0x8d05f  ldc.i4.1
0x8d060  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::set_Disabled(bool)
0x8d065  ldarg.0
0x8d066  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.MultiPicklist Microsoft.Crm.Web.Tools.ReportProperty.ReportPropertyPage::picklistVisibilitySpan
0x8d06b  ldc.i4.1
0x8d06c  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::set_Disabled(bool)
0x8d071  ldarg.0
0x8d072  ldfld    class [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.LanguagePicker Microsoft.Crm.Web.Tools.ReportProperty.ReportPropertyPage::languagecode
0x8d077  ldc.i4.1
0x8d078  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::set_Disabled(bool)
0x8d07d  ldarg.0
0x8d07e  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.EntityPage::get_CurrentEntity()
0x8d083  callvirt instance bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_IsNew()
0x8d088  brtrue.s loc_8D0F5
0x8d08a  ldarg.0
0x8d08b  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.EntityPage::get_CurrentEntity()
0x8d090  isinst   [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Report
0x8d095  stloc.s  6
0x8d097  ldarg.0
0x8d098  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x8d09d  ldstr    aSreportentity// "_sReportEntity"
0x8d0a2  ldloc.s  6
0x8d0a4  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Report::RetrieveRelatedEntitiesString()
0x8d0a9  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, string)
0x8d0ae  ldarg.0
0x8d0af  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x8d0b4  ldstr    aSreportcategor// "_sReportCategory"
0x8d0b9  ldloc.s  6
0x8d0bb  ldstr    aReportcategory// "reportcategory"
0x8d0c0  ldstr    aCategorycode// "categorycode"
0x8d0c5  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Report::RetrieveMultiplePicklistString(string, string)
0x8d0ca  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, string)
0x8d0cf  ldarg.0
0x8d0d0  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x8d0d5  ldstr    aSreportvisibil// "_sReportVisibility"
0x8d0da  ldloc.s  6
0x8d0dc  ldstr    aReportvisibili// "reportvisibility"
0x8d0e1  ldstr    aVisibilitycode// "visibilitycode"
0x8d0e6  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Report::RetrieveMultiplePicklistString(string, string)
  ... truncated ...
```
