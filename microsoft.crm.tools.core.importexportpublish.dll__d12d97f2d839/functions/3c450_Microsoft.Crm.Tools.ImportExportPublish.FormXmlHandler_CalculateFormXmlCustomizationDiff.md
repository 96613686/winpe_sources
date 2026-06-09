# Microsoft.Crm.Tools.ImportExportPublish.FormXmlHandler::CalculateFormXmlCustomizationDiff

- ea: `0x3c450`
- end: `0x3c4c5`
- name: `Microsoft.Crm.Tools.ImportExportPublish.FormXmlHandler::CalculateFormXmlCustomizationDiff`
- size: `117`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x3b9c0`

## callees

- `0x3c450`
- `0x3c4d0`

## string_xrefs

- `0x3c45c`: `formxml`
- `0x3c486`: `formxml`
- `0x3c496`: `formxml`

## pseudocode

```c

```

## disassembly

```asm
0x3c450  ldarg.0
0x3c451  ldarg.1
0x3c452  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity Microsoft.Crm.Tools.ImportExportPublish.FormXmlHandler::RetrieveLastManagedFormsWithAllLanguages(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity systemFormEntity)
0x3c457  stloc.0
0x3c458  ldloc.0
0x3c459  brtrue.s loc_3C485
0x3c45b  ldarg.1
0x3c45c  ldstr    aFormxml_0// "formxml"
0x3c461  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x3c466  castclass [mscorlib]System.String
0x3c46b  call     class [System.Xml]System.Xml.XmlDocument [Microsoft.Crm.Core]Microsoft.Crm.SharedUtil::CreateXmlDocument(string)
0x3c470  stloc.3
0x3c471  ldloc.3
0x3c472  ldloc.3
0x3c473  ldarg.0
0x3c474  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.FormXmlHandler::context
0x3c479  call     void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.FormSolutionUtility::PreProcessCustomControls(class [System.Xml]System.Xml.XmlNode, class [System.Xml]System.Xml.XmlDocument, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x3c47e  ldloc.3
0x3c47f  callvirt instance string [System.Xml]System.Xml.XmlNode::get_OuterXml()
0x3c484  ret
0x3c485  ldloc.0
0x3c486  ldstr    aFormxml_0// "formxml"
0x3c48b  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x3c490  castclass [mscorlib]System.String
0x3c495  ldarg.1
0x3c496  ldstr    aFormxml_0// "formxml"
0x3c49b  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x3c4a0  castclass [mscorlib]System.String
0x3c4a5  stloc.1
0x3c4a6  ldarg.1
0x3c4a7  ldstr    aFormid// "formid"
0x3c4ac  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x3c4b1  unbox.any [mscorlib]System.Guid
0x3c4b6  stloc.2
0x3c4b7  ldloc.1
0x3c4b8  ldloc.2
0x3c4b9  ldarg.0
0x3c4ba  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.FormXmlHandler::context
0x3c4bf  call     string [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.FormSolutionUtility::CalculateFormXmlDiff(string, string, valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x3c4c4  ret
```
