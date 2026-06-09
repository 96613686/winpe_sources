# Microsoft.Crm.Tools.ImportExportPublish.SavedQueryHandler::HandleLayoutXML

- ea: `0x848c0`
- end: `0x849b0`
- name: `Microsoft.Crm.Tools.ImportExportPublish.SavedQueryHandler::HandleLayoutXML`
- size: `240`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x845b0`

## callees

- `0x36a60`
- `0x848c0`
- `0x849b0`
- `0x84c70`

## string_xrefs

- `0x848c1`: `layoutxml`
- `0x8499f`: `layoutxml`
- `0x84984`: `fetchxml`
- `0x8494e`: `SolutionComponentType.Attribute`
- `0x8492e`: `SolutionComponentType.View`

## pseudocode

```c

```

## disassembly

```asm
0x848c0  ldarg.1
0x848c1  ldstr    aLayoutxml// "layoutxml"
0x848c6  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x848cb  isinst   [mscorlib]System.String
0x848d0  stloc.0
0x848d1  ldloc.0
0x848d2  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0x848d7  brtrue   loc_849AF
0x848dc  ldc.i4.0
0x848dd  stloc.1
0x848de  ldloc.0
0x848df  call     class [System.Xml]System.Xml.XmlDocument [Microsoft.Crm.Core]Microsoft.Crm.SharedUtil::CreateXmlDocument(string)
0x848e4  stloc.2
0x848e5  ldloc.2
0x848e6  ldstr    aGridObject// "/grid/@object"
0x848eb  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x848f0  stloc.3
0x848f1  ldloc.3
0x848f2  brfalse  loc_849AF
0x848f7  ldloc.3
0x848f8  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Value()
0x848fd  ldloca.s 4
0x848ff  call     bool [mscorlib]System.Int32::TryParse(string, int32&)
0x84904  brfalse  loc_849AF
0x84909  ldarg.0
0x8490a  ldloc.s  4
0x8490c  call     instance string Microsoft.Crm.Tools.ImportExportPublish.SavedQueryHandler::GetEntityNameFromEntityCode(int32 entityCode)
0x84911  stloc.s  5
0x84913  ldloc.s  5
0x84915  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0x8491a  brtrue.s loc_8499B
0x8491c  ldarg.0
0x8491d  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.SavedQueryHandler::_context
0x84922  callvirt instance int32 [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_CallerLanguageCode()
0x84927  newobj   instance void [mscorlib]System.Globalization.CultureInfo::.ctor(int32)
0x8492c  stloc.s  6
0x8492e  ldstr    aSolutioncompon_3// "SolutionComponentType.View"
0x84933  ldloc.s  6
0x84935  call     string [Microsoft.Crm.ObjectModel]Microsoft.Crm.Resources.ObjectModelResourceManager::GetString(string, class [mscorlib]System.Globalization.CultureInfo)
0x8493a  stloc.s  7
0x8493c  ldarg.1
0x8493d  ldstr    aName// "name"
0x84942  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x84947  isinst   [mscorlib]System.String
0x8494c  stloc.s  8
0x8494e  ldstr    aSolutioncompon_0// "SolutionComponentType.Attribute"
0x84953  ldloc.s  6
0x84955  call     string [Microsoft.Crm.ObjectModel]Microsoft.Crm.Resources.ObjectModelResourceManager::GetString(string, class [mscorlib]System.Globalization.CultureInfo)
0x8495a  stloc.s  9
0x8495c  ldstr    aCellNotContain// "//cell[not(contains(@name, \".\"))]/@na"...
0x84961  stloc.s  0xA
0x84963  ldloc.1
0x84964  ldarg.0
0x84965  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.SavedQueryHandler::_context
0x8496a  ldloc.2
0x8496b  ldloc.s  0xA
0x8496d  ldc.i4.2
0x8496e  ldloc.s  5
0x84970  ldarg.3
0x84971  ldarg.2
0x84972  ldc.i4.1
0x84973  ldloc.s  7
0x84975  ldloc.s  8
0x84977  ldloc.s  9
0x84979  call     bool Microsoft.Crm.Tools.ImportExportPublish.ExportAsHelper::ProcessXpathForExportToTargetVersion(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context, class [System.Xml]System.Xml.XmlDocument document, string xpath, int32 solutionComponentType, string currentEntityName, class Microsoft.Crm.Tools.ImportExportPublish.FilteredComponent currentFilteredComponent, class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity> dependencies, int32 nodeParentLevelToRemove, string componentType, string componentId, string dependentType)
0x8497e  or
0x8497f  stloc.1
0x84980  ldloc.1
0x84981  ldarg.0
0x84982  ldloc.2
0x84983  ldarg.1
0x84984  ldstr    aFetchxml// "fetchxml"
0x84989  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x8498e  isinst   [mscorlib]System.String
0x84993  ldarg.2
0x84994  call     instance bool Microsoft.Crm.Tools.ImportExportPublish.SavedQueryHandler::HandleCellsWithRelationshipInLayoutXML(class [System.Xml]System.Xml.XmlDocument layoutXmlDoc, string fetchXml, class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity> dependencies)
0x84999  or
0x8499a  stloc.1
0x8499b  ldloc.1
0x8499c  brfalse.s loc_849AF
0x8499e  ldarg.1
0x8499f  ldstr    aLayoutxml// "layoutxml"
0x849a4  ldloc.2
0x849a5  callvirt instance string [System.Xml]System.Xml.XmlNode::get_OuterXml()
0x849aa  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x849af  ret
```
