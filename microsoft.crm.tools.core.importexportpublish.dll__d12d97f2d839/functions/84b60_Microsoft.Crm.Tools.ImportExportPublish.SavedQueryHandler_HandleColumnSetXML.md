# Microsoft.Crm.Tools.ImportExportPublish.SavedQueryHandler::HandleColumnSetXML

- ea: `0x84b60`
- end: `0x84c6c`
- name: `Microsoft.Crm.Tools.ImportExportPublish.SavedQueryHandler::HandleColumnSetXML`
- size: `268`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x845b0`

## callees

- `0x36a60`
- `0x84b60`
- `0x84c70`

## string_xrefs

- `0x84b61`: `columnsetxml`
- `0x84c5a`: `columnsetxml`
- `0x84bdc`: `SolutionComponentType.Attribute`
- `0x84bbc`: `SolutionComponentType.View`

## pseudocode

```c

```

## disassembly

```asm
0x84b60  ldarg.1
0x84b61  ldstr    aColumnsetxml// "columnsetxml"
0x84b66  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x84b6b  isinst   [mscorlib]System.String
0x84b70  stloc.0
0x84b71  ldloc.0
0x84b72  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0x84b77  brtrue   loc_84C6B
0x84b7c  ldarg.1
0x84b7d  ldstr    aReturnedtypeco// "returnedtypecode"
0x84b82  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x84b87  unbox.any [mscorlib]System.Int32
0x84b8c  stloc.1
0x84b8d  ldarg.0
0x84b8e  ldloc.1
0x84b8f  call     instance string Microsoft.Crm.Tools.ImportExportPublish.SavedQueryHandler::GetEntityNameFromEntityCode(int32 entityCode)
0x84b94  stloc.2
0x84b95  ldc.i4.0
0x84b96  stloc.3
0x84b97  ldloc.2
0x84b98  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0x84b9d  brtrue   loc_84C6B
0x84ba2  ldloc.0
0x84ba3  call     class [System.Xml]System.Xml.XmlDocument [Microsoft.Crm.Core]Microsoft.Crm.SharedUtil::CreateXmlDocument(string)
0x84ba8  stloc.s  4
0x84baa  ldarg.0
0x84bab  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.SavedQueryHandler::_context
0x84bb0  callvirt instance int32 [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_CallerLanguageCode()
0x84bb5  newobj   instance void [mscorlib]System.Globalization.CultureInfo::.ctor(int32)
0x84bba  stloc.s  5
0x84bbc  ldstr    aSolutioncompon_3// "SolutionComponentType.View"
0x84bc1  ldloc.s  5
0x84bc3  call     string [Microsoft.Crm.ObjectModel]Microsoft.Crm.Resources.ObjectModelResourceManager::GetString(string, class [mscorlib]System.Globalization.CultureInfo)
0x84bc8  stloc.s  6
0x84bca  ldarg.1
0x84bcb  ldstr    aName// "name"
0x84bd0  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x84bd5  isinst   [mscorlib]System.String
0x84bda  stloc.s  7
0x84bdc  ldstr    aSolutioncompon_0// "SolutionComponentType.Attribute"
0x84be1  ldloc.s  5
0x84be3  call     string [Microsoft.Crm.ObjectModel]Microsoft.Crm.Resources.ObjectModelResourceManager::GetString(string, class [mscorlib]System.Globalization.CultureInfo)
0x84be8  stloc.s  8
0x84bea  ldstr    aColumnsetColum// "/columnset/column/text()"
0x84bef  stloc.s  9
0x84bf1  ldloc.3
0x84bf2  ldarg.0
0x84bf3  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.SavedQueryHandler::_context
0x84bf8  ldloc.s  4
0x84bfa  ldloc.s  9
0x84bfc  ldc.i4.2
0x84bfd  ldloc.2
0x84bfe  ldarg.3
0x84bff  ldarg.2
0x84c00  ldc.i4.1
0x84c01  ldloc.s  6
0x84c03  ldloc.s  7
0x84c05  ldloc.s  8
0x84c07  call     bool Microsoft.Crm.Tools.ImportExportPublish.ExportAsHelper::ProcessXpathForExportToTargetVersion(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context, class [System.Xml]System.Xml.XmlDocument document, string xpath, int32 solutionComponentType, string currentEntityName, class Microsoft.Crm.Tools.ImportExportPublish.FilteredComponent currentFilteredComponent, class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity> dependencies, int32 nodeParentLevelToRemove, string componentType, string componentId, string dependentType)
0x84c0c  or
0x84c0d  stloc.3
0x84c0e  ldstr    aColumnsetAscen// "/columnset/ascend/text()"
0x84c13  stloc.s  9
0x84c15  ldloc.3
0x84c16  ldarg.0
0x84c17  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.SavedQueryHandler::_context
0x84c1c  ldloc.s  4
0x84c1e  ldloc.s  9
0x84c20  ldc.i4.2
0x84c21  ldloc.2
0x84c22  ldarg.3
0x84c23  ldarg.2
0x84c24  ldc.i4.1
0x84c25  ldloc.s  6
0x84c27  ldloc.s  7
0x84c29  ldloc.s  8
0x84c2b  call     bool Microsoft.Crm.Tools.ImportExportPublish.ExportAsHelper::ProcessXpathForExportToTargetVersion(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context, class [System.Xml]System.Xml.XmlDocument document, string xpath, int32 solutionComponentType, string currentEntityName, class Microsoft.Crm.Tools.ImportExportPublish.FilteredComponent currentFilteredComponent, class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity> dependencies, int32 nodeParentLevelToRemove, string componentType, string componentId, string dependentType)
0x84c30  or
0x84c31  stloc.3
0x84c32  ldstr    aColumnsetDesce// "/columnset/descend/text()"
0x84c37  stloc.s  9
0x84c39  ldloc.3
0x84c3a  ldarg.0
0x84c3b  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.SavedQueryHandler::_context
0x84c40  ldloc.s  4
0x84c42  ldloc.s  9
0x84c44  ldc.i4.2
0x84c45  ldloc.2
0x84c46  ldarg.3
0x84c47  ldarg.2
0x84c48  ldc.i4.1
0x84c49  ldloc.s  6
0x84c4b  ldloc.s  7
0x84c4d  ldloc.s  8
0x84c4f  call     bool Microsoft.Crm.Tools.ImportExportPublish.ExportAsHelper::ProcessXpathForExportToTargetVersion(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context, class [System.Xml]System.Xml.XmlDocument document, string xpath, int32 solutionComponentType, string currentEntityName, class Microsoft.Crm.Tools.ImportExportPublish.FilteredComponent currentFilteredComponent, class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity> dependencies, int32 nodeParentLevelToRemove, string componentType, string componentId, string dependentType)
0x84c54  or
0x84c55  stloc.3
0x84c56  ldloc.3
0x84c57  brfalse.s loc_84C6B
0x84c59  ldarg.1
0x84c5a  ldstr    aColumnsetxml// "columnsetxml"
0x84c5f  ldloc.s  4
0x84c61  callvirt instance string [System.Xml]System.Xml.XmlNode::get_OuterXml()
0x84c66  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x84c6b  ret
```
