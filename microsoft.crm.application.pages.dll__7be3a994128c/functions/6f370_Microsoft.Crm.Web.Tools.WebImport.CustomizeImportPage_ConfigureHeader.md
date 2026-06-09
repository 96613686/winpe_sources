# Microsoft.Crm.Web.Tools.WebImport.CustomizeImportPage::ConfigureHeader

- ea: `0x6f370`
- end: `0x6f586`
- name: `Microsoft.Crm.Web.Tools.WebImport.CustomizeImportPage::ConfigureHeader`
- size: `534`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## string_xrefs

- `0x6f386`: `/_static/_common/scripts/main.js`
- `0x6f396`: `ImportWebService`
- `0x6f52e`: `ImportType_CreateWithoutTemplate`
- `0x6f54d`: `ImportType_CreateWithTemplate`
- `0x6f56c`: `ImportType_Update`
- `0x6f50f`: `ImportEntityProcessCode_Create`
- `0x6f418`: `ImportWizard.CustomizationError.EntityCreate`
- `0x6f44f`: `LOCID_ERROR_PICKLIST_CREATE`
- `0x6f45a`: `ImportWizard.CustomizationError.PicklistCreate`
- `0x6f47b`: `ImportWizard.CustomizationError.AttributeCreate`

## pseudocode

```c

```

## disassembly

```asm
0x6f370  ldarg.0
0x6f371  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x6f376  ldstr    aStaticToolsImp// "/_static/tools/importwizard/scripts/imp"...
0x6f37b  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x6f380  ldarg.0
0x6f381  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x6f386  ldstr    aStaticCommonSc_9// "/_static/_common/scripts/main.js"
0x6f38b  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x6f390  ldarg.0
0x6f391  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x6f396  ldstr    aImportwebservi// "ImportWebService"
0x6f39b  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::AddWrpcTokenActionPathWebService(string)
0x6f3a0  ldarg.0
0x6f3a1  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x6f3a6  ldstr    aImportwizardon// "ImportWizardOnLoad"
0x6f3ab  ldstr    aImportwizardpa// "ImportWizardPage_OnLoad();"
0x6f3b0  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptBlockForOnLoad(string, string)
0x6f3b5  ldarg.0
0x6f3b6  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x6f3bb  ldstr    aToolsImportwiz_2// "/tools/importwizard/importwizard.css.as"...
0x6f3c0  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0x6f3c5  ldarg.0
0x6f3c6  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x6f3cb  ldstr    aLocidCustomiza// "LOCID_CUSTOMIZATION_ERRORS"
0x6f3d0  ldarg.0
0x6f3d1  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x6f3d6  ldstr    aImportwizardCu// "ImportWizard.CustomizeImportPage.Custom"...
0x6f3db  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x6f3e0  ldc.i4.0
0x6f3e1  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x6f3e6  ldarg.0
0x6f3e7  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x6f3ec  ldstr    aLocidMappingWi// "LOCID_MAPPING_WILLBE_LOST"
0x6f3f1  ldarg.0
0x6f3f2  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x6f3f7  ldstr    aImportwizardGe// "ImportWizard.Generic.AllMappingsWillBeL"...
0x6f3fc  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x6f401  ldc.i4.0
0x6f402  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x6f407  ldarg.0
0x6f408  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x6f40d  ldstr    aLocidErrorEnti_0// "LOCID_ERROR_ENTITY_CREATION"
0x6f412  ldarg.0
0x6f413  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x6f418  ldstr    aImportwizardCu_0// "ImportWizard.CustomizationError.EntityC"...
0x6f41d  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x6f422  ldc.i4.0
0x6f423  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x6f428  ldarg.0
0x6f429  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x6f42e  ldstr    aLocidErrorPubl// "LOCID_ERROR_PUBLISH"
0x6f433  ldarg.0
0x6f434  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x6f439  ldstr    aImportwizardPu// "ImportWizard.PublishError"
0x6f43e  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x6f443  ldc.i4.0
0x6f444  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x6f449  ldarg.0
0x6f44a  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x6f44f  ldstr    aLocidErrorPick// "LOCID_ERROR_PICKLIST_CREATE"
0x6f454  ldarg.0
0x6f455  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x6f45a  ldstr    aImportwizardCu_1// "ImportWizard.CustomizationError.Picklis"...
0x6f45f  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x6f464  ldc.i4.0
0x6f465  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x6f46a  ldarg.0
0x6f46b  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x6f470  ldstr    aLocidErrorAttr// "LOCID_ERROR_ATTRIBUTE_CREATION"
0x6f475  ldarg.0
0x6f476  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x6f47b  ldstr    aImportwizardCu_2// "ImportWizard.CustomizationError.Attribu"...
0x6f480  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x6f485  ldc.i4.0
0x6f486  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x6f48b  ldarg.0
0x6f48c  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x6f491  ldstr    aLocidDuplicate// "LOCID_DUPLICATE_MAP_EXISTS"
0x6f496  ldarg.0
0x6f497  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x6f49c  ldstr    aImportwizardSa// "ImportWizard.SaveMapError.DuplicateName"
0x6f4a1  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x6f4a6  ldc.i4.0
0x6f4a7  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x6f4ac  ldarg.0
0x6f4ad  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x6f4b2  ldstr    aLocidDuplicate_0// "LOCID_DUPLICATE_MAP_ERRORCODE"
0x6f4b7  ldc.i4   0x80048443
0x6f4bc  ldc.i4.s 0x10
0x6f4be  call     string [mscorlib]System.Convert::ToString(int32, int32)
0x6f4c3  ldc.i4.0
0x6f4c4  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x6f4c9  ldarg.0
0x6f4ca  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x6f4cf  ldstr    aLocidCustomizi// "LOCID_CUSTOMIZING_PROGRESS_MESSAGE"
0x6f4d4  ldarg.0
0x6f4d5  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x6f4da  ldstr    aImportwizardCu_3// "ImportWizard.CustomizeImportPage.Custom"...
0x6f4df  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x6f4e4  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, string)
0x6f4e9  ldarg.0
0x6f4ea  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x6f4ef  ldstr    aLocidProgressM// "LOCID_PROGRESS_MESSAGE"
0x6f4f4  ldarg.0
0x6f4f5  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x6f4fa  ldstr    aImportwizardCu_4// "ImportWizard.CustomizeImportPage.Progre"...
0x6f4ff  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x6f504  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, string)
0x6f509  ldarg.0
0x6f50a  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x6f50f  ldstr    aImportentitypr_2// "ImportEntityProcessCode_Create"
0x6f514  ldc.i4.3
0x6f515  stloc.0
0x6f516  ldloca.s 0
0x6f518  constrained. [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.ImportWizard.ImportEntityProcessCode
0x6f51e  callvirt instance string [mscorlib]System.Object::ToString()
0x6f523  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, string)
0x6f528  ldarg.0
0x6f529  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x6f52e  ldstr    aImporttypeCrea// "ImportType_CreateWithoutTemplate"
0x6f533  ldc.i4.0
0x6f534  stloc.1
0x6f535  ldloca.s 1
0x6f537  constrained. [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.ImportWizard.ImportType
0x6f53d  callvirt instance string [mscorlib]System.Object::ToString()
0x6f542  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, string)
0x6f547  ldarg.0
0x6f548  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x6f54d  ldstr    aImporttypeCrea_0// "ImportType_CreateWithTemplate"
0x6f552  ldc.i4.1
0x6f553  stloc.1
0x6f554  ldloca.s 1
0x6f556  constrained. [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.ImportWizard.ImportType
0x6f55c  callvirt instance string [mscorlib]System.Object::ToString()
0x6f561  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, string)
0x6f566  ldarg.0
0x6f567  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x6f56c  ldstr    aImporttypeUpda// "ImportType_Update"
0x6f571  ldc.i4.2
0x6f572  stloc.1
0x6f573  ldloca.s 1
0x6f575  constrained. [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.ImportWizard.ImportType
0x6f57b  callvirt instance string [mscorlib]System.Object::ToString()
0x6f580  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, string)
0x6f585  ret
```
