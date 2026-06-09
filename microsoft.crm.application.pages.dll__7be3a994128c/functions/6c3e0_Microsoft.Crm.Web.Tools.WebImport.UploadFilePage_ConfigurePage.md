# Microsoft.Crm.Web.Tools.WebImport.UploadFilePage::ConfigurePage

- ea: `0x6c3e0`
- end: `0x6c53b`
- name: `Microsoft.Crm.Web.Tools.WebImport.UploadFilePage::ConfigurePage`
- size: `347`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## string_xrefs

- `0x6c3e6`: `ImportWebService`
- `0x6c459`: `LOCID_PRIVILEGES_MISSING`
- `0x6c464`: `ImportWizard.WelcomePage.PrivilegesMissingAlert`
- `0x6c4e8`: `ImportWizard.UploadFilePage.UpdateViaImport.EntityAutomapFailure`
- `0x6c509`: `ImportWizard.UploadFilePage.UpdateViaImport.AttributeAutomapFailure`
- `0x6c52a`: `ImportWizard.UploadFilePage.UpdateViaImport.PicklistAutomapFailure`

## pseudocode

```c

```

## disassembly

```asm
0x6c3e0  ldarg.0
0x6c3e1  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x6c3e6  ldstr    aImportwebservi// "ImportWebService"
0x6c3eb  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::AddWrpcTokenActionPathWebService(string)
0x6c3f0  ldarg.0
0x6c3f1  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x6c3f6  ldstr    aLocidIwImportC// "LOCID_IW_IMPORT_CLEAN_FAILED"
0x6c3fb  ldarg.0
0x6c3fc  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x6c401  ldstr    aIwMsgImportCle// "IW_MSG_Import_Clean_Failed_Alert"
0x6c406  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x6c40b  ldc.i4.0
0x6c40c  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x6c411  ldarg.0
0x6c412  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x6c417  ldstr    aLocidIwImportI// "LOCID_IW_IMPORT_INVALID_FILE"
0x6c41c  ldarg.0
0x6c41d  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x6c422  ldstr    aIwMsgInvalidFi// "IW_MSG_Invalid_File"
0x6c427  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x6c42c  ldc.i4.0
0x6c42d  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x6c432  ldarg.0
0x6c433  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x6c438  ldstr    aLocidIwFileupl// "LOCID_IW_FILEUPLOAD_PROGRESS"
0x6c43d  ldarg.0
0x6c43e  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x6c443  ldstr    aIwMsgFileuploa// "IW_MSG_FileUpload_Progress"
0x6c448  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x6c44d  ldc.i4.0
0x6c44e  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x6c453  ldarg.0
0x6c454  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x6c459  ldstr    aLocidPrivilege_5// "LOCID_PRIVILEGES_MISSING"
0x6c45e  ldarg.0
0x6c45f  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x6c464  ldstr    aImportwizardWe// "ImportWizard.WelcomePage.PrivilegesMiss"...
0x6c469  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x6c46e  ldc.i4.0
0x6c46f  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x6c474  ldarg.0
0x6c475  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x6c47a  ldstr    aLocidMappingWi// "LOCID_MAPPING_WILLBE_LOST"
0x6c47f  ldarg.0
0x6c480  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x6c485  ldstr    aImportwizardGe// "ImportWizard.Generic.AllMappingsWillBeL"...
0x6c48a  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x6c48f  ldc.i4.0
0x6c490  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x6c495  ldarg.0
0x6c496  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x6c49b  ldstr    aLocidIwUnsuppo// "LOCID_IW_UNSUPPORTED_FILETYPE"
0x6c4a0  ldarg.0
0x6c4a1  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x6c4a6  ldstr    aIwMsgUnsupport// "IW_MSG_Unsupported_FileType_Alert"
0x6c4ab  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x6c4b0  ldc.i4.0
0x6c4b1  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x6c4b6  ldarg.0
0x6c4b7  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x6c4bc  ldstr    aLocidFileUploa// "LOCID_FILE_UPLOAD_IN_PROGRESS"
0x6c4c1  ldarg.0
0x6c4c2  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x6c4c7  ldstr    aImportwizardUp// "ImportWizard.UploadFilePage.FileUploadI"...
0x6c4cc  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x6c4d1  ldc.i4.0
0x6c4d2  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x6c4d7  ldarg.0
0x6c4d8  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x6c4dd  ldstr    aLocidUviEntity// "LOCID_UVI_ENTITY_AUTOMAP_FAILED"
0x6c4e2  ldarg.0
0x6c4e3  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x6c4e8  ldstr    aImportwizardUp_0// "ImportWizard.UploadFilePage.UpdateViaIm"...
0x6c4ed  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x6c4f2  ldc.i4.0
0x6c4f3  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x6c4f8  ldarg.0
0x6c4f9  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x6c4fe  ldstr    aLocidUviAttrAu// "LOCID_UVI_ATTR_AUTOMAP_FAILED"
0x6c503  ldarg.0
0x6c504  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x6c509  ldstr    aImportwizardUp_1// "ImportWizard.UploadFilePage.UpdateViaIm"...
0x6c50e  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x6c513  ldc.i4.0
0x6c514  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x6c519  ldarg.0
0x6c51a  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x6c51f  ldstr    aLocidUviPklstA// "LOCID_UVI_PKLST_AUTOMAP_FAILED"
0x6c524  ldarg.0
0x6c525  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x6c52a  ldstr    aImportwizardUp_2// "ImportWizard.UploadFilePage.UpdateViaIm"...
0x6c52f  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x6c534  ldc.i4.0
0x6c535  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x6c53a  ret
```
