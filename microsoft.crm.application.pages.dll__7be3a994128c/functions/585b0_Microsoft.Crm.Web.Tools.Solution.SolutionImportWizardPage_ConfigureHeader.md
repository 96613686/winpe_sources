# Microsoft.Crm.Web.Tools.Solution.SolutionImportWizardPage::ConfigureHeader

- ea: `0x585b0`
- end: `0x5881d`
- name: `Microsoft.Crm.Web.Tools.Solution.SolutionImportWizardPage::ConfigureHeader`
- size: `621`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callees

- `0x58870`

## string_xrefs

- `0x58812`: `/_static/_common/scripts/Performance.js`
- `0x58694`: `SystemCustomization.EntityUtil.Messages.CannotUpdateSystemEntityIcons`
- `0x586b5`: `SystemCustomization.EntityUtil.Messages.CannotDeleteSystemEntity`
- `0x587c1`: `/_common/styles/Dialogs.css.aspx`
- `0x585f4`: `Errors.InvalidFileExtension`
- `0x5860a`: `LOCID_IMPORT_INVALIDFILEPATH`
- `0x58610`: `Errors.InvalidFilePath`

## pseudocode

```c

```

## disassembly

```asm
0x585b0  ldarg.0
0x585b1  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x585b6  ldstr    aLocidImportNof// "LOCID_IMPORT_NOFILESPECIFIED"
0x585bb  ldarg.0
0x585bc  ldstr    aErrorsNofilesp// "Errors.NoFileSpecified"
0x585c1  call     instance string Microsoft.Crm.Web.Tools.Solution.SolutionImportWizardPage::GetString(string name)
0x585c6  ldc.i4.0
0x585c7  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x585cc  ldarg.0
0x585cd  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x585d2  ldstr    aLocidImportInv// "LOCID_IMPORT_INVALIDFILENAME"
0x585d7  ldarg.0
0x585d8  ldstr    aErrorsInvalidf// "Errors.InvalidFileName"
0x585dd  call     instance string Microsoft.Crm.Web.Tools.Solution.SolutionImportWizardPage::GetString(string name)
0x585e2  ldc.i4.0
0x585e3  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x585e8  ldarg.0
0x585e9  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x585ee  ldstr    aLocidImportInv_0// "LOCID_IMPORT_INVALIDFILEEXT"
0x585f3  ldarg.0
0x585f4  ldstr    aErrorsInvalidf_0// "Errors.InvalidFileExtension"
0x585f9  call     instance string Microsoft.Crm.Web.Tools.Solution.SolutionImportWizardPage::GetString(string name)
0x585fe  ldc.i4.0
0x585ff  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x58604  ldarg.0
0x58605  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x5860a  ldstr    aLocidImportInv_1// "LOCID_IMPORT_INVALIDFILEPATH"
0x5860f  ldarg.0
0x58610  ldstr    aErrorsInvalidf_1// "Errors.InvalidFilePath"
0x58615  call     instance string Microsoft.Crm.Web.Tools.Solution.SolutionImportWizardPage::GetString(string name)
0x5861a  ldc.i4.0
0x5861b  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x58620  ldarg.0
0x58621  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x58626  ldstr    aLocidSyscustCa// "LOCID_SYSCUST_CANTBEBLANK"
0x5862b  ldarg.0
0x5862c  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x58631  ldstr    aSystemcustomiz_11// "SystemCustomization.Validation.Errors.C"...
0x58636  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x5863b  ldc.i4.0
0x5863c  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x58641  ldarg.0
0x58642  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x58647  ldstr    aLocidSyscustIn// "LOCID_SYSCUST_INVALCHARS"
0x5864c  ldarg.0
0x5864d  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x58652  ldstr    aSystemcustomiz_12// "SystemCustomization.Validation.Errors.C"...
0x58657  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x5865c  ldc.i4.0
0x5865d  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x58662  ldarg.0
0x58663  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x58668  ldstr    aLocidSyscustAl// "LOCID_SYSCUST_ALPHANUMSONLY"
0x5866d  ldarg.0
0x5866e  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x58673  ldstr    aSystemcustomiz_13// "SystemCustomization.Validation.Errors.C"...
0x58678  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x5867d  ldc.i4.0
0x5867e  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x58683  ldarg.0
0x58684  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x58689  ldstr    aLocidEntutlCan// "LOCID_ENTUTL_CANTUPDSYSENTICN"
0x5868e  ldarg.0
0x5868f  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x58694  ldstr    aSystemcustomiz_4// "SystemCustomization.EntityUtil.Messages"...
0x58699  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x5869e  ldc.i4.0
0x5869f  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x586a4  ldarg.0
0x586a5  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x586aa  ldstr    aLocidEntutlCan_0// "LOCID_ENTUTL_CANTDELSYSENT"
0x586af  ldarg.0
0x586b0  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x586b5  ldstr    aSystemcustomiz_5// "SystemCustomization.EntityUtil.Messages"...
0x586ba  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x586bf  ldc.i4.0
0x586c0  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x586c5  ldarg.0
0x586c6  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x586cb  ldstr    aLocidEntutlCan_1// "LOCID_ENTUTL_CANTPUBLISHENT"
0x586d0  ldarg.0
0x586d1  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x586d6  ldstr    aSystemcustomiz_6// "SystemCustomization.EntityUtil.Messages"...
0x586db  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x586e0  ldc.i4.0
0x586e1  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x586e6  ldarg.0
0x586e7  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x586ec  ldstr    aLocidEntutlCre// "LOCID_ENTUTL_CREATINGENT"
0x586f1  ldarg.0
0x586f2  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x586f7  ldstr    aSystemcustomiz_7// "SystemCustomization.EntityUtil.Messages"...
0x586fc  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x58701  ldc.i4.0
0x58702  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x58707  ldarg.0
0x58708  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x5870d  ldstr    aLocidEntutlUpd// "LOCID_ENTUTL_UPDATINGENT"
0x58712  ldarg.0
0x58713  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x58718  ldstr    aSystemcustomiz_8// "SystemCustomization.EntityUtil.Messages"...
0x5871d  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x58722  ldc.i4.0
0x58723  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x58728  ldarg.0
0x58729  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x5872e  ldstr    aLocidEntutlDel// "LOCID_ENTUTL_DELETINGENT"
0x58733  ldarg.0
0x58734  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x58739  ldstr    aSystemcustomiz_9// "SystemCustomization.EntityUtil.Messages"...
0x5873e  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x58743  ldc.i4.0
0x58744  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x58749  ldarg.0
0x5874a  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x5874f  ldstr    aLocidEntutlPub// "LOCID_ENTUTL_PUBLISHINGENT"
0x58754  ldarg.0
0x58755  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x5875a  ldstr    aSystemcustomiz_10// "SystemCustomization.EntityUtil.Messages"...
0x5875f  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x58764  ldc.i4.0
0x58765  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x5876a  ldarg.0
0x5876b  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x58770  ldstr    aLocidApplyingS// "LOCID_APPLYING_SOLUTION_UPGRADE"
0x58775  ldarg.0
0x58776  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x5877b  ldstr    aSolutionwizard// "SolutionWizard.Button.Promote.DisplayMe"...
0x58780  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x58785  ldc.i4.0
0x58786  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x5878b  ldarg.0
0x5878c  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x58791  ldstr    aSolution_0// "Solution"
0x58796  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::AddWrpcTokenActionPathWebService(string)
0x5879b  ldarg.0
0x5879c  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x587a1  ldstr    aFormsControlsF// "/_forms/controls/form.css.aspx"
0x587a6  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0x587ab  ldarg.0
0x587ac  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x587b1  ldstr    aToolsSolutionI_0// "/tools/solution/import/solutionimport.c"...
0x587b6  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0x587bb  ldarg.0
0x587bc  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x587c1  ldstr    aCommonStylesDi_0// "/_common/styles/Dialogs.css.aspx"
0x587c6  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0x587cb  ldarg.0
0x587cc  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x587d1  ldstr    aMscrmDialogsco// "Mscrm.DialogsControl"
0x587d6  ldnull
0x587d7  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::CreateClientAjaxComponent(string, string)
0x587dc  ldarg.0
0x587dd  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x587e2  ldstr    aStaticControls_20// "/_static/_controls/SolutionWizardContro"...
0x587e7  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x587ec  ldarg.0
0x587ed  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x587f2  ldstr    aStaticToolsSol_2// "/_static/tools/solution/scripts/solutio"...
0x587f7  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x587fc  ldarg.0
0x587fd  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x58802  ldstr    aStaticToolsFor_1// "/_static/tools/formeditor/scripts/util."...
0x58807  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x5880c  ldarg.0
0x5880d  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x58812  ldstr    aStaticCommonSc_5// "/_static/_common/scripts/Performance.js"
0x58817  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x5881c  ret
```
