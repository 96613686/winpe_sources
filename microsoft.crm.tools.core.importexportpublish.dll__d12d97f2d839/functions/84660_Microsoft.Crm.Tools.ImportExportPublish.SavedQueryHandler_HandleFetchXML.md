# Microsoft.Crm.Tools.ImportExportPublish.SavedQueryHandler::HandleFetchXML

- ea: `0x84660`
- end: `0x848b1`
- name: `Microsoft.Crm.Tools.ImportExportPublish.SavedQueryHandler::HandleFetchXML`
- size: `593`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x845b0`

## callees

- `0x36a60`
- `0x3ca30`
- `0x3ca40`
- `0x84660`

## string_xrefs

- `0x84661`: `fetchxml`
- `0x8486f`: `fetchxml`
- `0x846d1`: `SolutionComponentType.Attribute`
- `0x846b1`: `SolutionComponentType.View`
- `0x8474b`: `/fetch/entity//link-entity`
- `0x847ad`: `/link-entity/attribute/@name`
- `0x847d4`: `/link-entity/order/@attribute`

## pseudocode

```c

```

## disassembly

```asm
0x84660  ldarg.1
0x84661  ldstr    aFetchxml// "fetchxml"
0x84666  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x8466b  isinst   [mscorlib]System.String
0x84670  stloc.0
0x84671  ldloc.0
0x84672  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0x84677  brtrue   loc_848B0
0x8467c  ldc.i4.0
0x8467d  stloc.1
0x8467e  ldloc.0
0x8467f  call     class [System.Xml]System.Xml.XmlDocument [Microsoft.Crm.Core]Microsoft.Crm.SharedUtil::CreateXmlDocument(string)
0x84684  stloc.2
0x84685  ldloc.2
0x84686  ldstr    aFetchEntityNam// "/fetch/entity/@name"
0x8468b  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x84690  stloc.3
0x84691  ldloc.3
0x84692  brfalse  loc_8486B
0x84697  ldloc.3
0x84698  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Value()
0x8469d  stloc.s  4
0x8469f  ldarg.0
0x846a0  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.SavedQueryHandler::_context
0x846a5  callvirt instance int32 [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_CallerLanguageCode()
0x846aa  newobj   instance void [mscorlib]System.Globalization.CultureInfo::.ctor(int32)
0x846af  stloc.s  5
0x846b1  ldstr    aSolutioncompon_3// "SolutionComponentType.View"
0x846b6  ldloc.s  5
0x846b8  call     string [Microsoft.Crm.ObjectModel]Microsoft.Crm.Resources.ObjectModelResourceManager::GetString(string, class [mscorlib]System.Globalization.CultureInfo)
0x846bd  stloc.s  6
0x846bf  ldarg.1
0x846c0  ldstr    aName// "name"
0x846c5  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x846ca  isinst   [mscorlib]System.String
0x846cf  stloc.s  7
0x846d1  ldstr    aSolutioncompon_0// "SolutionComponentType.Attribute"
0x846d6  ldloc.s  5
0x846d8  call     string [Microsoft.Crm.ObjectModel]Microsoft.Crm.Resources.ObjectModelResourceManager::GetString(string, class [mscorlib]System.Globalization.CultureInfo)
0x846dd  stloc.s  8
0x846df  ldstr    aFetchEntityAtt// "/fetch/entity/attribute/@name"
0x846e4  stloc.s  9
0x846e6  ldloc.1
0x846e7  ldarg.0
0x846e8  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.SavedQueryHandler::_context
0x846ed  ldloc.2
0x846ee  ldloc.s  9
0x846f0  ldc.i4.2
0x846f1  ldloc.s  4
0x846f3  ldarg.3
0x846f4  ldarg.2
0x846f5  ldc.i4.1
0x846f6  ldloc.s  6
0x846f8  ldloc.s  7
0x846fa  ldloc.s  8
0x846fc  call     bool Microsoft.Crm.Tools.ImportExportPublish.ExportAsHelper::ProcessXpathForExportToTargetVersion(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context, class [System.Xml]System.Xml.XmlDocument document, string xpath, int32 solutionComponentType, string currentEntityName, class Microsoft.Crm.Tools.ImportExportPublish.FilteredComponent currentFilteredComponent, class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity> dependencies, int32 nodeParentLevelToRemove, string componentType, string componentId, string dependentType)
0x84701  or
0x84702  stloc.1
0x84703  ldstr    aFetchEntityFil// "/fetch/entity/filter//condition/@attrib"...
0x84708  stloc.s  9
0x8470a  ldloc.1
0x8470b  ldarg.0
0x8470c  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.SavedQueryHandler::_context
0x84711  ldloc.2
0x84712  ldloc.s  9
0x84714  ldc.i4.2
0x84715  ldloc.s  4
0x84717  ldarg.3
0x84718  ldarg.2
0x84719  ldc.i4.1
0x8471a  ldloc.s  6
0x8471c  ldloc.s  7
0x8471e  ldloc.s  8
0x84720  call     bool Microsoft.Crm.Tools.ImportExportPublish.ExportAsHelper::ProcessXpathForExportToTargetVersion(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context, class [System.Xml]System.Xml.XmlDocument document, string xpath, int32 solutionComponentType, string currentEntityName, class Microsoft.Crm.Tools.ImportExportPublish.FilteredComponent currentFilteredComponent, class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity> dependencies, int32 nodeParentLevelToRemove, string componentType, string componentId, string dependentType)
0x84725  or
0x84726  stloc.1
0x84727  ldstr    aFetchEntityOrd// "/fetch/entity/order/@attribute"
0x8472c  stloc.s  9
0x8472e  ldloc.1
0x8472f  ldarg.0
0x84730  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.SavedQueryHandler::_context
0x84735  ldloc.2
0x84736  ldloc.s  9
0x84738  ldc.i4.2
0x84739  ldloc.s  4
0x8473b  ldarg.3
0x8473c  ldarg.2
0x8473d  ldc.i4.1
0x8473e  ldloc.s  6
0x84740  ldloc.s  7
0x84742  ldloc.s  8
0x84744  call     bool Microsoft.Crm.Tools.ImportExportPublish.ExportAsHelper::ProcessXpathForExportToTargetVersion(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context, class [System.Xml]System.Xml.XmlDocument document, string xpath, int32 solutionComponentType, string currentEntityName, class Microsoft.Crm.Tools.ImportExportPublish.FilteredComponent currentFilteredComponent, class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity> dependencies, int32 nodeParentLevelToRemove, string componentType, string componentId, string dependentType)
0x84749  or
0x8474a  stloc.1
0x8474b  ldstr    aFetchEntityLin// "/fetch/entity//link-entity"
0x84750  stloc.s  9
0x84752  ldloc.2
0x84753  ldloc.s  9
0x84755  callvirt instance class [System.Xml]System.Xml.XmlNodeList [System.Xml]System.Xml.XmlNode::SelectNodes(string)
0x8475a  stloc.s  0xA
0x8475c  ldloc.s  0xA
0x8475e  callvirt instance class [mscorlib]System.Collections.IEnumerator [System.Xml]System.Xml.XmlNodeList::GetEnumerator()
0x84763  stloc.s  0xB
0x84765  br       loc_8483C
0x8476a  ldloc.s  0xB
0x8476c  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x84771  castclass [System.Xml]System.Xml.XmlNode
0x84776  stloc.s  0xC
0x84778  ldloc.s  0xC
0x8477a  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x8477f  ldstr    aName// "name"
0x84784  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0x84789  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Value()
0x8478e  stloc.s  0xD
0x84790  ldloc.s  0xD
0x84792  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0x84797  brtrue   loc_8483C
0x8479c  ldc.i4.0
0x8479d  stloc.s  0xE
0x8479f  ldloc.s  0xC
0x847a1  callvirt instance string [System.Xml]System.Xml.XmlNode::get_OuterXml()
0x847a6  call     class [System.Xml]System.Xml.XmlDocument [Microsoft.Crm.Core]Microsoft.Crm.SharedUtil::CreateXmlDocument(string)
0x847ab  stloc.s  0xF
0x847ad  ldstr    aLinkEntityAttr// "/link-entity/attribute/@name"
0x847b2  stloc.s  9
0x847b4  ldloc.s  0xE
0x847b6  ldarg.0
0x847b7  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.SavedQueryHandler::_context
0x847bc  ldloc.s  0xF
0x847be  ldloc.s  9
0x847c0  ldc.i4.2
0x847c1  ldloc.s  0xD
0x847c3  ldarg.3
0x847c4  ldarg.2
0x847c5  ldc.i4.1
0x847c6  ldloc.s  6
0x847c8  ldloc.s  7
0x847ca  ldloc.s  8
0x847cc  call     bool Microsoft.Crm.Tools.ImportExportPublish.ExportAsHelper::ProcessXpathForExportToTargetVersion(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context, class [System.Xml]System.Xml.XmlDocument document, string xpath, int32 solutionComponentType, string currentEntityName, class Microsoft.Crm.Tools.ImportExportPublish.FilteredComponent currentFilteredComponent, class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity> dependencies, int32 nodeParentLevelToRemove, string componentType, string componentId, string dependentType)
0x847d1  or
0x847d2  stloc.s  0xE
0x847d4  ldstr    aLinkEntityOrde// "/link-entity/order/@attribute"
0x847d9  stloc.s  9
0x847db  ldloc.s  0xE
0x847dd  ldarg.0
0x847de  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.SavedQueryHandler::_context
0x847e3  ldloc.s  0xF
0x847e5  ldloc.s  9
0x847e7  ldc.i4.2
0x847e8  ldloc.s  0xD
0x847ea  ldarg.3
0x847eb  ldarg.2
0x847ec  ldc.i4.1
0x847ed  ldloc.s  6
0x847ef  ldloc.s  7
0x847f1  ldloc.s  8
0x847f3  call     bool Microsoft.Crm.Tools.ImportExportPublish.ExportAsHelper::ProcessXpathForExportToTargetVersion(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context, class [System.Xml]System.Xml.XmlDocument document, string xpath, int32 solutionComponentType, string currentEntityName, class Microsoft.Crm.Tools.ImportExportPublish.FilteredComponent currentFilteredComponent, class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity> dependencies, int32 nodeParentLevelToRemove, string componentType, string componentId, string dependentType)
0x847f8  or
0x847f9  stloc.s  0xE
0x847fb  ldstr    aFilterConditio// "./filter//condition/@attribute"
0x84800  stloc.s  9
0x84802  ldloc.s  0xE
0x84804  ldarg.0
0x84805  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.SavedQueryHandler::_context
0x8480a  ldloc.s  0xF
0x8480c  ldloc.s  9
0x8480e  ldc.i4.2
0x8480f  ldloc.s  0xD
0x84811  ldarg.3
0x84812  ldarg.2
0x84813  ldc.i4.1
0x84814  ldloc.s  6
0x84816  ldloc.s  7
0x84818  ldloc.s  8
0x8481a  call     bool Microsoft.Crm.Tools.ImportExportPublish.ExportAsHelper::ProcessXpathForExportToTargetVersion(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context, class [System.Xml]System.Xml.XmlDocument document, string xpath, int32 solutionComponentType, string currentEntityName, class Microsoft.Crm.Tools.ImportExportPublish.FilteredComponent currentFilteredComponent, class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity> dependencies, int32 nodeParentLevelToRemove, string componentType, string componentId, string dependentType)
0x8481f  or
0x84820  stloc.s  0xE
0x84822  ldloc.s  0xE
0x84824  brfalse.s loc_8483C
0x84826  ldloc.s  0xC
0x84828  ldloc.s  0xF
0x8482a  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::get_DocumentElement()
0x8482f  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerXml()
0x84834  callvirt instance void [System.Xml]System.Xml.XmlNode::set_InnerXml(string)
0x84839  ldloc.s  0xE
0x8483b  stloc.1
0x8483c  ldloc.s  0xB
0x8483e  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x84843  brtrue   loc_8476A
0x84848  leave.s  loc_8486B
0x8484a  ldloc.s  0xB
0x8484c  isinst   [mscorlib]System.IDisposable
0x84851  stloc.s  0x10
0x84853  ldloc.s  0x10
0x84855  brfalse.s loc_8485E
0x84857  ldloc.s  0x10
0x84859  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x8485e  endfinally
0x8485f  ldloc.s  0xA
0x84861  brfalse.s loc_8486A
0x84863  ldloc.s  0xA
0x84865  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x8486a  endfinally
0x8486b  ldloc.1
0x8486c  brfalse.s loc_8487F
0x8486e  ldarg.1
0x8486f  ldstr    aFetchxml// "fetchxml"
0x84874  ldloc.2
0x84875  callvirt instance string [System.Xml]System.Xml.XmlNode::get_OuterXml()
0x8487a  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x8487f  ldarg.3
0x84880  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<string> Microsoft.Crm.Tools.ImportExportPublish.FilteredComponent::get_Comments()
0x84885  brfalse.s loc_848B0
0x84887  ldarg.3
0x84888  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<string> Microsoft.Crm.Tools.ImportExportPublish.FilteredComponent::get_Comments()
0x8488d  callvirt instance int32 class [mscorlib]System.Collections.ObjectModel.Collection`1<string>::get_Count()
0x84892  ldc.i4.1
0x84893  ble.s    loc_848B0
0x84895  ldarg.3
0x84896  ldarg.3
0x84897  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<string> Microsoft.Crm.Tools.ImportExportPublish.FilteredComponent::get_Comments()
0x8489c  call     T0x2B000035
0x848a1  call     T0x2B000004
0x848a6  newobj   instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<string>::.ctor(class [mscorlib]System.Collections.Generic.IList`1<var<u1>>)
0x848ab  callvirt instance void Microsoft.Crm.Tools.ImportExportPublish.FilteredComponent::set_Comments(class [mscorlib]System.Collections.ObjectModel.Collection`1<string> value)
0x848b0  ret
```
