# Microsoft.Crm.Tools.ImportExportPublish.RibbonTabDisplayRuleHandler::HandleRule

- ea: `0x71fb0`
- end: `0x720d1`
- name: `Microsoft.Crm.Tools.ImportExportPublish.RibbonTabDisplayRuleHandler::HandleRule`
- size: `289`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x36900`
- `0x71fb0`
- `0x72100`
- `0x72120`

## string_xrefs

- `0x71fbd`: `SolutionComponentType.RibbonItem`
- `0x71fc9`: `SolutionComponentType.RibbonItem`
- `0x7202c`: `TabCommand`
- `0x72059`: `TabCommand`
- `0x72070`: `TabCommand`

## pseudocode

```c

```

## disassembly

```asm
0x71fb0  ldarg.s  4
0x71fb2  callvirt instance int32 [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_CallerLanguageCode()
0x71fb7  newobj   instance void [mscorlib]System.Globalization.CultureInfo::.ctor(int32)
0x71fbc  stloc.0
0x71fbd  ldstr    aSolutioncompon_5// "SolutionComponentType.RibbonItem"
0x71fc2  ldloc.0
0x71fc3  call     string [Microsoft.Crm.ObjectModel]Microsoft.Crm.Resources.ObjectModelResourceManager::GetString(string, class [mscorlib]System.Globalization.CultureInfo)
0x71fc8  stloc.1
0x71fc9  ldstr    aSolutioncompon_5// "SolutionComponentType.RibbonItem"
0x71fce  ldloc.0
0x71fcf  call     string [Microsoft.Crm.ObjectModel]Microsoft.Crm.Resources.ObjectModelResourceManager::GetString(string, class [mscorlib]System.Globalization.CultureInfo)
0x71fd4  stloc.2
0x71fd5  ldarg.2
0x71fd6  castclass [System.Xml]System.Xml.XmlNode
0x71fdb  ldarg.s  4
0x71fdd  ldarg.s  5
0x71fdf  newobj   instance void Microsoft.Crm.Tools.ImportExportPublish.RibbonHelper::.ctor(class [System.Xml]System.Xml.XmlNode ribbonDiff, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context, class [mscorlib]System.Version targetVersion)
0x71fe4  stloc.3
0x71fe5  ldarg.1
0x71fe6  isinst   [System.Xml]System.Xml.XmlNode
0x71feb  ldstr    aTabdisplayrule// "TabDisplayRule"
0x71ff0  callvirt instance class [System.Xml]System.Xml.XmlNodeList [System.Xml]System.Xml.XmlNode::SelectNodes(string)
0x71ff5  stloc.s  4
0x71ff7  ldloc.s  4
0x71ff9  callvirt instance class [mscorlib]System.Collections.IEnumerator [System.Xml]System.Xml.XmlNodeList::GetEnumerator()
0x71ffe  stloc.s  5
0x72000  br       loc_720A1
0x72005  ldloc.s  5
0x72007  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x7200c  castclass [System.Xml]System.Xml.XmlNode
0x72011  stloc.s  6
0x72013  ldloc.s  6
0x72015  ldstr    aEntityrule_0// "EntityRule"
0x7201a  callvirt instance class [System.Xml]System.Xml.XmlNodeList [System.Xml]System.Xml.XmlNode::SelectNodes(string)
0x7201f  stloc.s  7
0x72021  ldloc.3
0x72022  ldloc.s  7
0x72024  ldarg.3
0x72025  ldloc.s  6
0x72027  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x7202c  ldstr    aTabcommand// "TabCommand"
0x72031  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0x72036  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Value()
0x7203b  callvirt instance void Microsoft.Crm.Tools.ImportExportPublish.RibbonHelper::HandleEntityEnableDisableRules(class [System.Xml]System.Xml.XmlNodeList entityList, class Microsoft.Crm.Tools.ImportExportPublish.FilteredComponent filteredComponent, string componentId)
0x72040  ldloc.s  6
0x72042  callvirt instance class [System.Xml]System.Xml.XmlNodeList [System.Xml]System.Xml.XmlNode::get_ChildNodes()
0x72047  callvirt instance int32 [System.Xml]System.Xml.XmlNodeList::get_Count()
0x7204c  brtrue.s loc_72093
0x7204e  ldarg.s  4
0x72050  ldarg.3
0x72051  ldloc.1
0x72052  ldloc.s  6
0x72054  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x72059  ldstr    aTabcommand// "TabCommand"
0x7205e  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0x72063  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Value()
0x72068  ldloc.2
0x72069  ldloc.s  6
0x7206b  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x72070  ldstr    aTabcommand// "TabCommand"
0x72075  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0x7207a  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Value()
0x7207f  call     void Microsoft.Crm.Tools.ImportExportPublish.ExportAsHelper::AddRemovedComment(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context, class Microsoft.Crm.Tools.ImportExportPublish.FilteredComponent currentFilteredComponent, string componentType, string componentId, string dependentType, string dependentId)
0x72084  ldloc.s  6
0x72086  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::get_ParentNode()
0x7208b  ldloc.s  6
0x7208d  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::RemoveChild(class [System.Xml]System.Xml.XmlNode)
0x72092  pop
0x72093  leave.s  loc_720A1
0x72095  ldloc.s  7
0x72097  brfalse.s loc_720A0
0x72099  ldloc.s  7
0x7209b  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x720a0  endfinally
0x720a1  ldloc.s  5
0x720a3  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x720a8  brtrue   loc_72005
0x720ad  leave.s  loc_720D0
0x720af  ldloc.s  5
0x720b1  isinst   [mscorlib]System.IDisposable
0x720b6  stloc.s  8
0x720b8  ldloc.s  8
0x720ba  brfalse.s loc_720C3
0x720bc  ldloc.s  8
0x720be  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x720c3  endfinally
0x720c4  ldloc.s  4
0x720c6  brfalse.s loc_720CF
0x720c8  ldloc.s  4
0x720ca  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x720cf  endfinally
0x720d0  ret
```
