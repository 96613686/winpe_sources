# Microsoft.Crm.Web.Tools.WebImport.UploadPreviewPage::ConfigureHeader

- ea: `0x6c660`
- end: `0x6c793`
- name: `Microsoft.Crm.Web.Tools.WebImport.UploadPreviewPage::ConfigureHeader`
- size: `307`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## string_xrefs

- `0x6c676`: `/_static/_common/scripts/main.js`
- `0x6c686`: `ImportWebService`
- `0x6c73b`: `ImportType_CreateWithoutTemplate`
- `0x6c75a`: `ImportType_CreateWithTemplate`
- `0x6c779`: `ImportType_Update`

## pseudocode

```c

```

## disassembly

```asm
0x6c660  ldarg.0
0x6c661  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x6c666  ldstr    aStaticToolsImp// "/_static/tools/importwizard/scripts/imp"...
0x6c66b  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x6c670  ldarg.0
0x6c671  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x6c676  ldstr    aStaticCommonSc_9// "/_static/_common/scripts/main.js"
0x6c67b  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x6c680  ldarg.0
0x6c681  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x6c686  ldstr    aImportwebservi// "ImportWebService"
0x6c68b  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::AddWrpcTokenActionPathWebService(string)
0x6c690  ldarg.0
0x6c691  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x6c696  ldstr    aToolsImportwiz_2// "/tools/importwizard/importwizard.css.as"...
0x6c69b  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0x6c6a0  ldarg.0
0x6c6a1  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x6c6a6  ldstr    aImportwizardon// "ImportWizardOnLoad"
0x6c6ab  ldstr    aImportwizardpa// "ImportWizardPage_OnLoad();"
0x6c6b0  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptBlockForOnLoad(string, string)
0x6c6b5  ldarg.0
0x6c6b6  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x6c6bb  ldstr    aLocidOneHeader// "LOCID_ONE_HEADER_DETECTED"
0x6c6c0  ldarg.0
0x6c6c1  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x6c6c6  ldstr    aImportwizardUp_4// "ImportWizard.UploadPreviewPage.OneHeade"...
0x6c6cb  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x6c6d0  ldc.i4.0
0x6c6d1  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x6c6d6  ldarg.0
0x6c6d7  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x6c6dc  ldstr    aLocidEmptyFile// "LOCID_EMPTY_FILE_DETECTED"
0x6c6e1  ldarg.0
0x6c6e2  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x6c6e7  ldstr    aImportwizardUp_5// "ImportWizard.UploadPreviewPage.EmptyFil"...
0x6c6ec  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x6c6f1  ldc.i4.0
0x6c6f2  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x6c6f7  ldarg.0
0x6c6f8  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x6c6fd  ldstr    aLocidMappingWi// "LOCID_MAPPING_WILLBE_LOST"
0x6c702  ldarg.0
0x6c703  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x6c708  ldstr    aImportwizardGe// "ImportWizard.Generic.AllMappingsWillBeL"...
0x6c70d  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x6c712  ldc.i4.0
0x6c713  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x6c718  ldarg.0
0x6c719  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x6c71e  ldstr    aLocidEmptyfile// "LOCID_EMPTYFILE_ERRORCODE"
0x6c723  ldc.i4   0x80040365
0x6c728  ldc.i4.s 0x10
0x6c72a  call     string [mscorlib]System.Convert::ToString(int32, int32)
0x6c72f  ldc.i4.0
0x6c730  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x6c735  ldarg.0
0x6c736  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x6c73b  ldstr    aImporttypeCrea// "ImportType_CreateWithoutTemplate"
0x6c740  ldc.i4.0
0x6c741  stloc.0
0x6c742  ldloca.s 0
0x6c744  constrained. [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.ImportWizard.ImportType
0x6c74a  callvirt instance string [mscorlib]System.Object::ToString()
0x6c74f  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, string)
0x6c754  ldarg.0
0x6c755  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x6c75a  ldstr    aImporttypeCrea_0// "ImportType_CreateWithTemplate"
0x6c75f  ldc.i4.1
0x6c760  stloc.0
0x6c761  ldloca.s 0
0x6c763  constrained. [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.ImportWizard.ImportType
0x6c769  callvirt instance string [mscorlib]System.Object::ToString()
0x6c76e  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, string)
0x6c773  ldarg.0
0x6c774  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x6c779  ldstr    aImporttypeUpda// "ImportType_Update"
0x6c77e  ldc.i4.2
0x6c77f  stloc.0
0x6c780  ldloca.s 0
0x6c782  constrained. [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.ImportWizard.ImportType
0x6c788  callvirt instance string [mscorlib]System.Object::ToString()
0x6c78d  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, string)
0x6c792  ret
```
