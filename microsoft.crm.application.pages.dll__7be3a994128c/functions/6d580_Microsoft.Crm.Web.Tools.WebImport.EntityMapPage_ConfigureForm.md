# Microsoft.Crm.Web.Tools.WebImport.EntityMapPage::ConfigureForm

- ea: `0x6d580`
- end: `0x6d6ed`
- name: `Microsoft.Crm.Web.Tools.WebImport.EntityMapPage::ConfigureForm`
- size: `365`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x6d750`
- `0x6d860`
- `0x6df20`

## string_xrefs

- `0x6d5a6`: `javascript:moveBack();`
- `0x6d61b`: `ENTITY_MAPPING_ACTION_CREATENEW`
- `0x6d620`: `2-create`
- `0x6d683`: `ImportEntityProcessCode_Create`
- `0x6d6d6`: `hasSystemUserCreatePrivilege`

## pseudocode

```c

```

## disassembly

```asm
0x6d580  ldarg.0
0x6d581  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentForm()
0x6d586  isinst   [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.WizardForm
0x6d58b  dup
0x6d58c  ldarg.0
0x6d58d  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x6d592  ldstr    aImportwizardEn_14// "ImportWizard.EntityMapPage.Title"
0x6d597  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x6d59c  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.WizardForm::set_PageTitle(string)
0x6d5a1  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Button [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.WizardForm::get_BackButton()
0x6d5a6  ldstr    aJavascriptMove// "javascript:moveBack();"
0x6d5ab  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Button::set_OnClick(string)
0x6d5b0  ldarg.0
0x6d5b1  ldfld    class [System.Web]System.Web.UI.HtmlControls.HtmlTable Microsoft.Crm.Web.Tools.WebImport.EntityMapPage::entityMappingTable
0x6d5b6  ldc.i4.0
0x6d5b7  callvirt instance void [System.Web]System.Web.UI.HtmlControls.HtmlTable::set_CellPadding(int32)
0x6d5bc  ldarg.0
0x6d5bd  ldfld    class [System.Web]System.Web.UI.HtmlControls.HtmlTable Microsoft.Crm.Web.Tools.WebImport.EntityMapPage::entityMappingTable
0x6d5c2  ldc.i4.0
0x6d5c3  callvirt instance void [System.Web]System.Web.UI.HtmlControls.HtmlTable::set_CellSpacing(int32)
0x6d5c8  ldarg.0
0x6d5c9  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x6d5ce  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_Form()
0x6d5d3  ldstr    aWizardpagepost// "wizardPagePostData"
0x6d5d8  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x6d5dd  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x6d5e2  newobj   instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ImportWizardState::.ctor(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x6d5e7  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ImportWizardState::get_MapXml()
0x6d5ec  call     class [System.Xml]System.Xml.XmlDocument [Microsoft.Crm.Core]Microsoft.Crm.SharedUtil::CreateXmlDocument(string)
0x6d5f1  stloc.0
0x6d5f2  ldarg.0
0x6d5f3  ldloc.0
0x6d5f4  call     instance void Microsoft.Crm.Web.Tools.WebImport.EntityMapPage::ProcessSFME(class [System.Xml]System.Xml.XmlDocument mapDoc)
0x6d5f9  ldarg.0
0x6d5fa  ldloc.0
0x6d5fb  call     instance void Microsoft.Crm.Web.Tools.WebImport.EntityMapPage::FillTable(class [System.Xml]System.Xml.XmlDocument mapDoc)
0x6d600  ldarg.0
0x6d601  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x6d606  ldstr    aEntityMappingA// "ENTITY_MAPPING_ACTION_SELECT"
0x6d60b  ldstr    a1Select// "1-select"
0x6d610  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, string)
0x6d615  ldarg.0
0x6d616  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x6d61b  ldstr    aEntityMappingA_0// "ENTITY_MAPPING_ACTION_CREATENEW"
0x6d620  ldstr    a2Create// "2-create"
0x6d625  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, string)
0x6d62a  ldarg.0
0x6d62b  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x6d630  ldstr    aEntityMappingA_1// "ENTITY_MAPPING_ACTION_IGNORE"
0x6d635  ldstr    a3Ignore// "3-ignore"
0x6d63a  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, string)
0x6d63f  ldarg.0
0x6d640  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x6d645  ldstr    aImportentitypr_0// "ImportEntityProcessCode_Process"
0x6d64a  ldc.i4.2
0x6d64b  stloc.1
0x6d64c  ldloca.s 1
0x6d64e  constrained. [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.ImportWizard.ImportEntityProcessCode
0x6d654  callvirt instance string [mscorlib]System.Object::ToString()
0x6d659  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, string)
0x6d65e  ldarg.0
0x6d65f  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x6d664  ldstr    aImportentitypr_1// "ImportEntityProcessCode_Ignore"
0x6d669  ldc.i4.0
0x6d66a  stloc.1
0x6d66b  ldloca.s 1
0x6d66d  constrained. [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.ImportWizard.ImportEntityProcessCode
0x6d673  callvirt instance string [mscorlib]System.Object::ToString()
0x6d678  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, string)
0x6d67d  ldarg.0
0x6d67e  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x6d683  ldstr    aImportentitypr_2// "ImportEntityProcessCode_Create"
0x6d688  ldc.i4.3
0x6d689  stloc.1
0x6d68a  ldloca.s 1
0x6d68c  constrained. [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.ImportWizard.ImportEntityProcessCode
0x6d692  callvirt instance string [mscorlib]System.Object::ToString()
0x6d697  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, string)
0x6d69c  ldarg.0
0x6d69d  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x6d6a2  ldstr    aImportentitypr// "ImportEntityProcessCode_Unmapped"
0x6d6a7  ldc.i4.1
0x6d6a8  stloc.1
0x6d6a9  ldloca.s 1
0x6d6ab  constrained. [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.ImportWizard.ImportEntityProcessCode
0x6d6b1  callvirt instance string [mscorlib]System.Object::ToString()
0x6d6b6  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, string)
0x6d6bb  ldarg.0
0x6d6bc  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x6d6c1  ldstr    aSchemaprefix// "schemaPrefix"
0x6d6c6  call     string [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Utility.WebUtility::get_LowercaseSchemaName()
0x6d6cb  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, string)
0x6d6d0  ldarg.0
0x6d6d1  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x6d6d6  ldstr    aHassystemuserc// "hasSystemUserCreatePrivilege"
0x6d6db  ldarg.0
0x6d6dc  ldfld    bool Microsoft.Crm.Web.Tools.WebImport.EntityMapPage::hasSystemUserCreatePrivilege
0x6d6e1  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, bool)
0x6d6e6  ldarg.0
0x6d6e7  call     instance void Microsoft.Crm.Web.Tools.WebImport.EntityMapPage::SetMetadataDictionary()
0x6d6ec  ret
```
