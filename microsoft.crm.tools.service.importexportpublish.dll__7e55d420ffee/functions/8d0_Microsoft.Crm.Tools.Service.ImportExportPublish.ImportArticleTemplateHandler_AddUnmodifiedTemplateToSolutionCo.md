# Microsoft.Crm.Tools.Service.ImportExportPublish.ImportArticleTemplateHandler::AddUnmodifiedTemplateToSolutionComponent

- ea: `0x8d0`
- end: `0x982`
- name: `Microsoft.Crm.Tools.Service.ImportExportPublish.ImportArticleTemplateHandler::AddUnmodifiedTemplateToSolutionComponent`
- size: `178`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x6d0`

## callees

- `0x8d0`

## string_xrefs

- `0x929`: `KbArticleTemplate`
- `0x92e`: `kbarticletemplateid`

## pseudocode

```c

```

## disassembly

```asm
0x8d0  ldarg.1
0x8d1  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x8d6  ldstr    aUnmodified// "unmodified"
0x8db  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0x8e0  brfalse  loc_980
0x8e5  ldarg.1
0x8e6  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x8eb  ldstr    aUnmodified// "unmodified"
0x8f0  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0x8f5  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Value()
0x8fa  ldstr    a1// "1"
0x8ff  call     int32 [mscorlib]System.String::CompareOrdinal(string, string)
0x904  brtrue.s loc_980
0x906  ldloca.s 0
0x908  ldarg.1
0x909  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x90e  ldstr    aId// "id"
0x913  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNamedNodeMap::GetNamedItem(string)
0x918  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Value()
0x91d  call     instance void [mscorlib]System.Guid::.ctor(string)
0x922  ldarg.0
0x923  ldfld    class [Microsoft.Crm.Tools.Core.ImportExportPublish]Microsoft.Crm.Tools.ImportExportPublish.ImportHelper Microsoft.Crm.Tools.Service.ImportExportPublish.ImportArticleTemplateHandler::_importHelper
0x928  ldarg.2
0x929  ldstr    aKbarticletempl_0// "KbArticleTemplate"
0x92e  ldstr    aKbarticletempl_1// "kbarticletemplateid"
0x933  ldloc.0
0x934  ldarg.0
0x935  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.Service.ImportExportPublish.ImportArticleTemplateHandler::context
0x93a  ldc.i4.0
0x93b  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity [Microsoft.Crm.Tools.Core.ImportExportPublish]Microsoft.Crm.Tools.ImportExportPublish.ImportHelper::TryGetEntity(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject, string, string, valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext, bool)
0x940  castclass [Microsoft.Crm.Service.Entities]Microsoft.Crm.Service.Entities.KbArticleTemplate
0x945  brtrue.s loc_97E
0x947  ldarg.0
0x948  ldc.i4.s 0x26
0x94a  ldarg.0
0x94b  ldfld    string Microsoft.Crm.Tools.Service.ImportExportPublish.ImportArticleTemplateHandler::_templateId
0x950  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x955  call     instance void [Microsoft.Crm.Tools.Core.ImportExportPublish]Microsoft.Crm.Tools.ImportExportPublish.ImportHandler::RemoveFromRootComponentsList(int32, valuetype [mscorlib]System.Guid)
0x95a  ldc.i4   0x8004847C
0x95f  ldc.i4.0
0x960  newarr   [mscorlib]System.Object
0x965  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(int32, object[])
0x96a  stloc.1
0x96b  ldarg.0
0x96c  ldarg.0
0x96d  callvirt instance string [Microsoft.Crm.Tools.Core.ImportExportPublish]Microsoft.Crm.Tools.ImportExportPublish.ImportHandler::GetParameterXPath()
0x972  ldstr    aWarning// "warning"
0x977  ldloc.1
0x978  ldc.i4.1
0x979  call     instance void [Microsoft.Crm.Tools.Core.ImportExportPublish]Microsoft.Crm.Tools.ImportExportPublish.ImportHandler::UpdateProgress(string, string, class [mscorlib]System.Exception, bool)
0x97e  ldc.i4.1
0x97f  ret
0x980  ldc.i4.0
0x981  ret
```
