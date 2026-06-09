# Microsoft.Crm.Tools.ImportExportPublish.MailMergeTemplateHandler::PopulateMailMergeNode

- ea: `0x695c0`
- end: `0x69707`
- name: `Microsoft.Crm.Tools.ImportExportPublish.MailMergeTemplateHandler::PopulateMailMergeNode`
- size: `327`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x69710`

## callees

- `0x391e0`
- `0x39770`
- `0x39940`
- `0x39cd0`
- `0x3a5e0`
- `0x695c0`

## string_xrefs

- `0x69625`: `templatetypecode`
- `0x69611`: `MailMergeTemplate`
- `0x696c2`: `MailMergeTemplateAttributes`
- `0x695cd`: `mailmergetemplate`
- `0x69677`: `The mailMergeTemplate {0} was not exported because its otc {1} does not match any entity. This record is orphan`

## pseudocode

```c

```

## disassembly

```asm
0x695c0  ldarg.0
0x695c1  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.MailMergeTemplateHandler::context
0x695c6  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x695cb  stloc.0
0x695cc  ldarg.1
0x695cd  ldstr    aMailmergetempl_5// "mailmergetemplate"
0x695d2  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::CreateElement(string)
0x695d7  stloc.1
0x695d8  ldarg.2
0x695d9  ldstr    aSolutionid// "solutionid"
0x695de  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x695e3  unbox.any [mscorlib]System.Guid
0x695e8  ldsfld   valuetype [mscorlib]System.Guid [Microsoft.Crm.Constants]Microsoft.Crm.SolutionConstants::ActiveSolutionId
0x695ed  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x695f2  brtrue.s loc_695FF
0x695f4  ldarg.0
0x695f5  ldfld    bool Microsoft.Crm.Tools.ImportExportPublish.ExportHandler::_exportDeltaOverride
0x695fa  brfalse  loc_696B3
0x695ff  ldarg.2
0x69600  ldstr    aIsmanaged// "ismanaged"
0x69605  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x6960a  unbox.any [mscorlib]System.Boolean
0x6960f  stloc.2
0x69610  ldarg.0
0x69611  ldstr    aMailmergetempl_2// "MailMergeTemplate"
0x69616  ldarg.1
0x69617  ldloc.1
0x69618  ldarg.2
0x69619  newobj   instance void Microsoft.Crm.Tools.ImportExportPublish.GenericTypeBusinessEntity::.ctor(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity be)
0x6961e  ldloc.2
0x6961f  call     instance void Microsoft.Crm.Tools.ImportExportPublish.ExportHandler::AddXmlProperties(string itemType, class [System.Xml]System.Xml.XmlDocument importDocument, class [System.Xml]System.Xml.XmlNode parentNode, class Microsoft.Crm.Tools.ImportExportPublish.GenericType container, bool managed)
0x69624  ldarg.2
0x69625  ldstr    aTemplatetypeco// "templatetypecode"
0x6962a  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x6962f  unbox.any [mscorlib]System.Int32
0x69634  stloc.3
0x69635  ldloc.0
0x69636  ldloc.3
0x69637  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::TryGetEntity(int32)
0x6963c  stloc.s  4
0x6963e  ldloc.s  4
0x69640  brfalse.s loc_69660
0x69642  ldarg.0
0x69643  ldarg.1
0x69644  ldloc.1
0x69645  ldstr    aEntityplatform// "entityPlatformName"
0x6964a  ldloc.s  4
0x6964c  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_PlatformName()
0x69651  call     instance void Microsoft.Crm.Tools.ImportExportPublish.ExportHandler::AddXmlNode(class [System.Xml]System.Xml.XmlDocument importDocument, class [System.Xml]System.Xml.XmlNode parentNode, string nodeName, string value)
0x69656  ldarg.3
0x69657  ldloc.1
0x69658  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::AppendChild(class [System.Xml]System.Xml.XmlNode)
0x6965d  pop
0x6965e  br.s     loc_696B1
0x69660  ldarg.2
0x69661  ldstr    aName// "name"
0x69666  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x6966b  castclass [mscorlib]System.String
0x69670  stloc.s  5
0x69672  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentUICulture()
0x69677  ldstr    aTheMailmergete// "The mailMergeTemplate {0} was not expor"...
0x6967c  ldc.i4.2
0x6967d  newarr   [mscorlib]System.Object
0x69682  dup
0x69683  ldc.i4.0
0x69684  ldloc.s  5
0x69686  stelem.ref
0x69687  dup
0x69688  ldc.i4.1
0x69689  ldloc.3
0x6968a  box      [mscorlib]System.Int32
0x6968f  stelem.ref
0x69690  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x69695  stloc.s  6
0x69697  ldarg.0
0x69698  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.MailMergeTemplateHandler::context
0x6969d  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x696a2  ldc.i4.s 0x11
0x696a4  ldloc.s  6
0x696a6  ldc.i4.0
0x696a7  newarr   [mscorlib]System.Object
0x696ac  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceWarning(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x696b1  ldc.i4.1
0x696b2  ret
0x696b3  ldarg.1
0x696b4  ldarg.0
0x696b5  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.MailMergeTemplateHandler::context
0x696ba  call     bool Microsoft.Crm.Tools.ImportExportPublish.ExportHandler::ExportAsUnmodified(class [System.Xml]System.Xml.XmlDocument importDocument, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x696bf  brfalse.s loc_69705
0x696c1  ldarg.0
0x696c2  ldstr    aMailmergetempl_3// "MailMergeTemplateAttributes"
0x696c7  ldarg.1
0x696c8  ldloc.1
0x696c9  ldarg.2
0x696ca  newobj   instance void Microsoft.Crm.Tools.ImportExportPublish.GenericTypeBusinessEntity::.ctor(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity be)
0x696cf  call     instance void Microsoft.Crm.Tools.ImportExportPublish.ExportHandler::AddXmlAttributes(string itemType, class [System.Xml]System.Xml.XmlDocument importDocument, class [System.Xml]System.Xml.XmlNode parentNode, class Microsoft.Crm.Tools.ImportExportPublish.GenericType container)
0x696d4  ldarg.1
0x696d5  ldstr    aUnmodified// "unmodified"
0x696da  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlDocument::CreateAttribute(string)
0x696df  stloc.s  7
0x696e1  ldloc.s  7
0x696e3  ldstr    a1// "1"
0x696e8  callvirt instance void [System.Xml]System.Xml.XmlNode::set_Value(string)
0x696ed  ldloc.1
0x696ee  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x696f3  ldloc.s  7
0x696f5  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::Append(class [System.Xml]System.Xml.XmlAttribute)
0x696fa  pop
0x696fb  ldarg.3
0x696fc  ldloc.1
0x696fd  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::AppendChild(class [System.Xml]System.Xml.XmlNode)
0x69702  pop
0x69703  ldc.i4.1
0x69704  ret
0x69705  ldc.i4.0
0x69706  ret
```
