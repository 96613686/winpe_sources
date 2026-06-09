# Microsoft.Crm.Web.Tools.ReportProperty.ReportPropertyPage::ConfigurePage

- ea: `0x8cb00`
- end: `0x8cce8`
- name: `Microsoft.Crm.Web.Tools.ReportProperty.ReportPropertyPage::ConfigurePage`
- size: `488`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x8cb00`

## string_xrefs

- `0x8cb06`: `/_static/_common/scripts/newdialog.js`
- `0x8cb47`: `LOCID_REPORT_PATH_NOT_SPECIFIED`
- `0x8cb52`: `Web.Reports.ReportPathNotSpecified`
- `0x8cc2e`: `LOCID_TYPE_CHANGE_FROM_LINK`
- `0x8cc39`: `Web.Reports.TypeChange.FromLink`

## pseudocode

```c

```

## disassembly

```asm
0x8cb00  ldarg.0
0x8cb01  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x8cb06  ldstr    aStaticCommonSc_25// "/_static/_common/scripts/newdialog.js"
0x8cb0b  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x8cb10  ldarg.0
0x8cb11  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x8cb16  ldstr    aAdvancedfindAd_0// "/advancedfind/advfind.css.aspx"
0x8cb1b  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0x8cb20  ldarg.0
0x8cb21  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x8cb26  ldstr    aLocidInvalidRe// "LOCID_INVALID_REPORT_NAME"
0x8cb2b  ldarg.0
0x8cb2c  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x8cb31  ldstr    aErrorMessage0x_26// "Error_Message_0x80632901"
0x8cb36  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x8cb3b  ldc.i4.0
0x8cb3c  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x8cb41  ldarg.0
0x8cb42  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x8cb47  ldstr    aLocidReportPat// "LOCID_REPORT_PATH_NOT_SPECIFIED"
0x8cb4c  ldarg.0
0x8cb4d  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x8cb52  ldstr    aWebReportsRepo// "Web.Reports.ReportPathNotSpecified"
0x8cb57  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x8cb5c  ldc.i4.0
0x8cb5d  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x8cb62  ldarg.0
0x8cb63  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x8cb68  ldstr    aLocidInvalidUp// "LOCID_INVALID_UPLOAD_FILE"
0x8cb6d  ldarg.0
0x8cb6e  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x8cb73  ldstr    aWebReportsInva// "Web.Reports.InvalidUploadFile"
0x8cb78  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x8cb7d  ldc.i4.0
0x8cb7e  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x8cb83  ldarg.0
0x8cb84  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x8cb89  ldstr    aLocidMustRunWi// "LOCID_MUST_RUN_WIZARD"
0x8cb8e  ldarg.0
0x8cb8f  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x8cb94  ldstr    aWebReportsMust// "Web.Reports.MustRunWizard"
0x8cb99  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x8cb9e  ldc.i4.0
0x8cb9f  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x8cba4  ldarg.0
0x8cba5  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x8cbaa  ldstr    aLocidTypeChang// "LOCID_TYPE_CHANGE_FROM_WIZARD1"
0x8cbaf  ldarg.0
0x8cbb0  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x8cbb5  ldstr    aWebReportsType// "Web.Reports.TypeChange.FromWizard1"
0x8cbba  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x8cbbf  ldc.i4.0
0x8cbc0  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x8cbc5  ldarg.0
0x8cbc6  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x8cbcb  ldstr    aLocidTypeChang_0// "LOCID_TYPE_CHANGE_FROM_FILE1"
0x8cbd0  ldarg.0
0x8cbd1  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x8cbd6  ldstr    aWebReportsType_0// "Web.Reports.TypeChange.FromFile1"
0x8cbdb  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x8cbe0  ldc.i4.0
0x8cbe1  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x8cbe6  ldarg.0
0x8cbe7  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x8cbec  ldstr    aLocidTypeChang_1// "LOCID_TYPE_CHANGE_FROM_FILE3"
0x8cbf1  ldarg.0
0x8cbf2  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x8cbf7  ldstr    aWebReportsType_1// "Web.Reports.TypeChange.FromFile3"
0x8cbfc  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x8cc01  ldc.i4.0
0x8cc02  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x8cc07  ldarg.0
0x8cc08  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x8cc0d  ldstr    aLocidTypeChang_2// "LOCID_TYPE_CHANGE_DOWNLOAD"
0x8cc12  ldarg.0
0x8cc13  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x8cc18  ldstr    aWebReportsType_2// "Web.Reports.TypeChange.FromFileOrWizard"...
0x8cc1d  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x8cc22  ldc.i4.0
0x8cc23  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x8cc28  ldarg.0
0x8cc29  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x8cc2e  ldstr    aLocidTypeChang_3// "LOCID_TYPE_CHANGE_FROM_LINK"
0x8cc33  ldarg.0
0x8cc34  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x8cc39  ldstr    aWebReportsType_3// "Web.Reports.TypeChange.FromLink"
0x8cc3e  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x8cc43  ldc.i4.0
0x8cc44  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x8cc49  ldarg.0
0x8cc4a  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x8cc4f  ldstr    aLocidFormRequi// "LOCID_FORM_REQUIRED_ALT"
0x8cc54  ldarg.0
0x8cc55  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x8cc5a  ldstr    aFormsRequiredA// "Forms.Required.AltTag"
0x8cc5f  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x8cc64  ldc.i4.0
0x8cc65  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x8cc6a  ldarg.0
0x8cc6b  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x8cc70  ldstr    aLocidTypecodeC// "LOCID_TYPECODE_CHANGE"
0x8cc75  ldarg.0
0x8cc76  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x8cc7b  ldstr    aWebReportsTypc// "Web.Reports.TypCodeChange.NotAllowed"
0x8cc80  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x8cc85  ldc.i4.0
0x8cc86  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x8cc8b  ldarg.0
0x8cc8c  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x8cc91  ldstr    aReports// "Reports"
0x8cc96  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::AddWrpcTokenActionPathWebService(string)
0x8cc9b  ldarg.0
0x8cc9c  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x8cca1  ldstr    aRequiredFields// "Required_Fields_Background_Color"
0x8cca6  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x8ccab  stloc.0
0x8ccac  ldloc.0
0x8ccad  brfalse.s loc_8CCD2
0x8ccaf  ldloc.0
0x8ccb0  callvirt instance int32 [mscorlib]System.String::get_Length()
0x8ccb5  brfalse.s loc_8CCD2
0x8ccb7  ldarg.0
0x8ccb8  ldfld    class [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.UrlControl Microsoft.Crm.Web.Tools.ReportProperty.ReportPropertyPage::bodyurl
0x8ccbd  ldstr    aStyle_1// "Style"
0x8ccc2  ldstr    aBackgroundColo_0// "background-color:"
0x8ccc7  ldloc.0
0x8ccc8  call     string [mscorlib]System.String::Concat(string, string)
0x8cccd  callvirt instance void [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormControlBase::AddExpando(string, string)
0x8ccd2  ldarg.0
0x8ccd3  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x8ccd8  ldstr    aMscrmAutotoolt// "Mscrm.AutoToolTip"
0x8ccdd  ldstr    aSelectreportty// "selectReportType_c"
0x8cce2  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::CreateClientAjaxComponent(string, string)
0x8cce7  ret
```
