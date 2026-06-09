# Microsoft.Crm.Tools.Service.ImportExportPublish.ImportContractTemplateHandler::AddUnmodifiedTemplateToSolutionComponent

- ea: `0xc80`
- end: `0xd2d`
- name: `Microsoft.Crm.Tools.Service.ImportExportPublish.ImportContractTemplateHandler::AddUnmodifiedTemplateToSolutionComponent`
- size: `173`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0xa50`

## callees

- `0xc80`

## string_xrefs

- `0xcd9`: `ContractTemplate`
- `0xcde`: `contracttemplateid`

## pseudocode

```c

```

## disassembly

```asm
0xc80  ldarg.1
0xc81  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0xc86  ldstr    aUnmodified// "unmodified"
0xc8b  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0xc90  brfalse  loc_D2B
0xc95  ldarg.1
0xc96  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0xc9b  ldstr    aUnmodified// "unmodified"
0xca0  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0xca5  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Value()
0xcaa  ldstr    a1// "1"
0xcaf  call     int32 [mscorlib]System.String::CompareOrdinal(string, string)
0xcb4  brtrue.s loc_D2B
0xcb6  ldloca.s 0
0xcb8  ldarg.1
0xcb9  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0xcbe  ldstr    aId// "id"
0xcc3  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNamedNodeMap::GetNamedItem(string)
0xcc8  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Value()
0xccd  call     instance void [mscorlib]System.Guid::.ctor(string)
0xcd2  ldarg.0
0xcd3  ldfld    class [Microsoft.Crm.Tools.Core.ImportExportPublish]Microsoft.Crm.Tools.ImportExportPublish.ImportHelper Microsoft.Crm.Tools.Service.ImportExportPublish.ImportContractTemplateHandler::_importHelper
0xcd8  ldarg.2
0xcd9  ldstr    aContracttempla_0// "ContractTemplate"
0xcde  ldstr    aContracttempla_1// "contracttemplateid"
0xce3  ldloc.0
0xce4  ldarg.0
0xce5  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.Service.ImportExportPublish.ImportContractTemplateHandler::context
0xcea  ldc.i4.0
0xceb  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity [Microsoft.Crm.Tools.Core.ImportExportPublish]Microsoft.Crm.Tools.ImportExportPublish.ImportHelper::TryGetEntity(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject, string, string, valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext, bool)
0xcf0  brtrue.s loc_D29
0xcf2  ldarg.0
0xcf3  ldc.i4.s 0x25
0xcf5  ldarg.0
0xcf6  ldfld    string Microsoft.Crm.Tools.Service.ImportExportPublish.ImportContractTemplateHandler::_templateId
0xcfb  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0xd00  call     instance void [Microsoft.Crm.Tools.Core.ImportExportPublish]Microsoft.Crm.Tools.ImportExportPublish.ImportHandler::RemoveFromRootComponentsList(int32, valuetype [mscorlib]System.Guid)
0xd05  ldc.i4   0x8004847C
0xd0a  ldc.i4.0
0xd0b  newarr   [mscorlib]System.Object
0xd10  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(int32, object[])
0xd15  stloc.1
0xd16  ldarg.0
0xd17  ldarg.0
0xd18  callvirt instance string [Microsoft.Crm.Tools.Core.ImportExportPublish]Microsoft.Crm.Tools.ImportExportPublish.ImportHandler::GetParameterXPath()
0xd1d  ldstr    aWarning// "warning"
0xd22  ldloc.1
0xd23  ldc.i4.1
0xd24  call     instance void [Microsoft.Crm.Tools.Core.ImportExportPublish]Microsoft.Crm.Tools.ImportExportPublish.ImportHandler::UpdateProgress(string, string, class [mscorlib]System.Exception, bool)
0xd29  ldc.i4.1
0xd2a  ret
0xd2b  ldc.i4.0
0xd2c  ret
```
