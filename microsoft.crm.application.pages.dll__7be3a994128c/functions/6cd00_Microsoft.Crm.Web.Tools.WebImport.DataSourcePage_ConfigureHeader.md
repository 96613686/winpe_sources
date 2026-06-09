# Microsoft.Crm.Web.Tools.WebImport.DataSourcePage::ConfigureHeader

- ea: `0x6cd00`
- end: `0x6cdf3`
- name: `Microsoft.Crm.Web.Tools.WebImport.DataSourcePage::ConfigureHeader`
- size: `243`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## string_xrefs

- `0x6cd16`: `/_static/_common/scripts/main.js`
- `0x6cd26`: `ImportWebService`
- `0x6cd7c`: `ImportType_CreateWithoutTemplate`
- `0x6cd9b`: `ImportType_CreateWithTemplate`
- `0x6cdd9`: `ImportType_Update`
- `0x6cdba`: `ImportType_XlsxCreateUpdate`

## pseudocode

```c

```

## disassembly

```asm
0x6cd00  ldarg.0
0x6cd01  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x6cd06  ldstr    aStaticToolsImp// "/_static/tools/importwizard/scripts/imp"...
0x6cd0b  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x6cd10  ldarg.0
0x6cd11  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x6cd16  ldstr    aStaticCommonSc_9// "/_static/_common/scripts/main.js"
0x6cd1b  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x6cd20  ldarg.0
0x6cd21  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x6cd26  ldstr    aImportwebservi// "ImportWebService"
0x6cd2b  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::AddWrpcTokenActionPathWebService(string)
0x6cd30  ldarg.0
0x6cd31  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x6cd36  ldstr    aImportwizardon// "ImportWizardOnLoad"
0x6cd3b  ldstr    aImportwizardpa// "ImportWizardPage_OnLoad();"
0x6cd40  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptBlockForOnLoad(string, string)
0x6cd45  ldarg.0
0x6cd46  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x6cd4b  ldstr    aToolsImportwiz_2// "/tools/importwizard/importwizard.css.as"...
0x6cd50  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0x6cd55  ldarg.0
0x6cd56  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x6cd5b  ldstr    aLocidMappingWi// "LOCID_MAPPING_WILLBE_LOST"
0x6cd60  ldarg.0
0x6cd61  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x6cd66  ldstr    aImportwizardGe// "ImportWizard.Generic.AllMappingsWillBeL"...
0x6cd6b  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x6cd70  ldc.i4.0
0x6cd71  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x6cd76  ldarg.0
0x6cd77  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x6cd7c  ldstr    aImporttypeCrea// "ImportType_CreateWithoutTemplate"
0x6cd81  ldc.i4.0
0x6cd82  stloc.0
0x6cd83  ldloca.s 0
0x6cd85  constrained. [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.ImportWizard.ImportType
0x6cd8b  callvirt instance string [mscorlib]System.Object::ToString()
0x6cd90  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, string)
0x6cd95  ldarg.0
0x6cd96  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x6cd9b  ldstr    aImporttypeCrea_0// "ImportType_CreateWithTemplate"
0x6cda0  ldc.i4.1
0x6cda1  stloc.0
0x6cda2  ldloca.s 0
0x6cda4  constrained. [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.ImportWizard.ImportType
0x6cdaa  callvirt instance string [mscorlib]System.Object::ToString()
0x6cdaf  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, string)
0x6cdb4  ldarg.0
0x6cdb5  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x6cdba  ldstr    aImporttypeXlsx// "ImportType_XlsxCreateUpdate"
0x6cdbf  ldc.i4.4
0x6cdc0  stloc.0
0x6cdc1  ldloca.s 0
0x6cdc3  constrained. [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.ImportWizard.ImportType
0x6cdc9  callvirt instance string [mscorlib]System.Object::ToString()
0x6cdce  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, string)
0x6cdd3  ldarg.0
0x6cdd4  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x6cdd9  ldstr    aImporttypeUpda// "ImportType_Update"
0x6cdde  ldc.i4.2
0x6cddf  stloc.0
0x6cde0  ldloca.s 0
0x6cde2  constrained. [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.ImportWizard.ImportType
0x6cde8  callvirt instance string [mscorlib]System.Object::ToString()
0x6cded  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, string)
0x6cdf2  ret
```
