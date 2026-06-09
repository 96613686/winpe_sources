# Microsoft.Crm.Tools.LangProvisioning.LanguageActivation::ProcessRibbonComonents

- ea: `0x8230`
- end: `0x840b`
- name: `Microsoft.Crm.Tools.LangProvisioning.LanguageActivation::ProcessRibbonComonents`
- size: `475`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, broker_com_uri`

## callers

- `0x95710`

## callees

- `0x8230`
- `0x505e0`
- `0x59760`
- `0x59770`
- `0x59780`
- `0x66b10`
- `0x66b20`
- `0x66bd0`
- `0x690a0`
- `0x77d50`

## string_xrefs

- `0x823d`: `Process Application Ribbon Components for {0}`
- `0x825c`: `ImportExportXml/RibbonDiffXml/LocLabels/LocLabel`
- `0x82a6`: `ImportExportXml/Entities/Entity`
- `0x82ca`: `./RibbonDiffXml/LocLabels/LocLabel`
- `0x8315`: `Process Entity Name Ribbon Components for entity {0}, language {1}`
- `0x838d`: `Process Entity Name Ribbon Components for entity {0}, language {1}`

## pseudocode

```c

```

## disassembly

```asm
0x8230  ldarg.0
0x8231  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.LangProvisioning.LanguageActivation::_context
0x8236  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x823b  ldc.i4.s 0x18
0x823d  ldstr    aProcessApplica// "Process Application Ribbon Components f"...
0x8242  ldc.i4.1
0x8243  newarr   [mscorlib]System.Object
0x8248  dup
0x8249  ldc.i4.0
0x824a  ldarg.2
0x824b  box      [mscorlib]System.Int32
0x8250  stelem.ref
0x8251  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x8256  ldarg.1
0x8257  callvirt instance class [System.Xml]System.Xml.XmlDocument Microsoft.Crm.Tools.ImportExportPublish.ImportXml::get_ImportDocument()
0x825c  ldstr    aImportexportxm_6// "ImportExportXml/RibbonDiffXml/LocLabels"...
0x8261  callvirt instance class [System.Xml]System.Xml.XmlNodeList [System.Xml]System.Xml.XmlNode::SelectNodes(string)
0x8266  stloc.0
0x8267  ldloc.0
0x8268  brfalse.s loc_82A0
0x826a  ldloc.0
0x826b  callvirt instance int32 [System.Xml]System.Xml.XmlNodeList::get_Count()
0x8270  ldc.i4.0
0x8271  ble.s    loc_82A0
0x8273  ldarg.1
0x8274  callvirt instance class [System.Xml]System.Xml.XmlDocument Microsoft.Crm.Tools.ImportExportPublish.ImportXml::get_ImportDocument()
0x8279  ldarg.1
0x827a  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.ImportXml::get_Context()
0x827f  ldarg.1
0x8280  callvirt instance class Microsoft.Crm.Tools.ImportExportPublish.ImportTracer Microsoft.Crm.Tools.ImportExportPublish.ImportXml::get_Tracer()
0x8285  ldarg.1
0x8286  callvirt instance class Microsoft.Crm.Tools.ImportExportPublish.RootImportHandler Microsoft.Crm.Tools.ImportExportPublish.ImportXml::get_RootHandler()
0x828b  callvirt instance class Microsoft.Crm.Tools.ImportExportPublish.ImportHelper Microsoft.Crm.Tools.ImportExportPublish.RootImportHandler::get_ImportHelper()
0x8290  ldarg.1
0x8291  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, bool>::.ctor()
0x8296  call     class Microsoft.Crm.Tools.ImportExportPublish.ImportRibbonsHandler Microsoft.Crm.Tools.ImportExportPublish.ImportRibbonsHandler::CreateRibbonsHandler(class [System.Xml]System.Xml.XmlDocument importDocument, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context, class Microsoft.Crm.Tools.ImportExportPublish.ImportTracer tracer, class Microsoft.Crm.Tools.ImportExportPublish.ImportHelper importHelper, class Microsoft.Crm.Tools.ImportExportPublish.ImportXml parent, class [mscorlib]System.Collections.Generic.Dictionary`2<string, bool> entitiesWithRibbon)
0x829b  callvirt instance void Microsoft.Crm.Tools.ImportExportPublish.ImportHandler::ImportItem()
0x82a0  ldarg.1
0x82a1  callvirt instance class [System.Xml]System.Xml.XmlDocument Microsoft.Crm.Tools.ImportExportPublish.ImportXml::get_ImportDocument()
0x82a6  ldstr    aImportexportxm_7// "ImportExportXml/Entities/Entity"
0x82ab  callvirt instance class [System.Xml]System.Xml.XmlNodeList [System.Xml]System.Xml.XmlNode::SelectNodes(string)
0x82b0  stloc.1
0x82b1  ldloc.1
0x82b2  callvirt instance class [mscorlib]System.Collections.IEnumerator [System.Xml]System.Xml.XmlNodeList::GetEnumerator()
0x82b7  stloc.2
0x82b8  br       loc_83DF
0x82bd  ldloc.2
0x82be  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x82c3  castclass [System.Xml]System.Xml.XmlNode
0x82c8  stloc.3
0x82c9  ldloc.3
0x82ca  ldstr    aRibbondiffxmlL// "./RibbonDiffXml/LocLabels/LocLabel"
0x82cf  callvirt instance class [System.Xml]System.Xml.XmlNodeList [System.Xml]System.Xml.XmlNode::SelectNodes(string)
0x82d4  stloc.s  4
0x82d6  ldloc.s  4
0x82d8  brfalse  loc_83DF
0x82dd  ldloc.s  4
0x82df  callvirt instance int32 [System.Xml]System.Xml.XmlNodeList::get_Count()
0x82e4  ldc.i4.0
0x82e5  ble      loc_83DF
0x82ea  ldloc.3
0x82eb  ldstr    aName_1// "Name"
0x82f0  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x82f5  stloc.s  5
0x82f7  ldloc.3
0x82f8  ldstr    aObjecttypecode// "ObjectTypeCode"
0x82fd  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x8302  stloc.s  6
0x8304  ldloc.s  5
0x8306  brfalse.s loc_836E
0x8308  ldarg.0
0x8309  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.LangProvisioning.LanguageActivation::_context
0x830e  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x8313  ldc.i4.s 0x18
0x8315  ldstr    aProcessEntityN// "Process Entity Name Ribbon Components f"...
0x831a  ldc.i4.2
0x831b  newarr   [mscorlib]System.Object
0x8320  dup
0x8321  ldc.i4.0
0x8322  ldloc.s  5
0x8324  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerXml()
0x8329  stelem.ref
0x832a  dup
0x832b  ldc.i4.1
0x832c  ldarg.2
0x832d  box      [mscorlib]System.Int32
0x8332  stelem.ref
0x8333  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x8338  ldarg.1
0x8339  callvirt instance class [System.Xml]System.Xml.XmlDocument Microsoft.Crm.Tools.ImportExportPublish.ImportXml::get_ImportDocument()
0x833e  ldarg.1
0x833f  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.ImportXml::get_Context()
0x8344  ldarg.1
0x8345  callvirt instance class Microsoft.Crm.Tools.ImportExportPublish.ImportTracer Microsoft.Crm.Tools.ImportExportPublish.ImportXml::get_Tracer()
0x834a  ldloc.s  5
0x834c  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerXml()
0x8351  ldarg.1
0x8352  callvirt instance class Microsoft.Crm.Tools.ImportExportPublish.RootImportHandler Microsoft.Crm.Tools.ImportExportPublish.ImportXml::get_RootHandler()
0x8357  callvirt instance class Microsoft.Crm.Tools.ImportExportPublish.ImportHelper Microsoft.Crm.Tools.ImportExportPublish.RootImportHandler::get_ImportHelper()
0x835c  ldarg.1
0x835d  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, bool>::.ctor()
0x8362  call     class Microsoft.Crm.Tools.ImportExportPublish.ImportRibbonsHandler Microsoft.Crm.Tools.ImportExportPublish.ImportRibbonsHandler::CreateRibbonsHandler(class [System.Xml]System.Xml.XmlDocument importDocument, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context, class Microsoft.Crm.Tools.ImportExportPublish.ImportTracer tracer, string entityName, class Microsoft.Crm.Tools.ImportExportPublish.ImportHelper importHelper, class Microsoft.Crm.Tools.ImportExportPublish.ImportXml parent, class [mscorlib]System.Collections.Generic.Dictionary`2<string, bool> entitiesWithRibbon)
0x8367  callvirt instance void Microsoft.Crm.Tools.ImportExportPublish.ImportHandler::ImportItem()
0x836c  br.s     loc_83DF
0x836e  ldloc.s  6
0x8370  brfalse.s loc_83DF
0x8372  ldloc.s  6
0x8374  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerXml()
0x8379  call     int32 [mscorlib]System.Convert::ToInt32(string)
0x837e  stloc.s  7
0x8380  ldarg.0
0x8381  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.LangProvisioning.LanguageActivation::_context
0x8386  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x838b  ldc.i4.s 0x18
0x838d  ldstr    aProcessEntityN// "Process Entity Name Ribbon Components f"...
0x8392  ldc.i4.2
0x8393  newarr   [mscorlib]System.Object
0x8398  dup
0x8399  ldc.i4.0
0x839a  ldloc.s  7
0x839c  box      [mscorlib]System.Int32
0x83a1  stelem.ref
0x83a2  dup
0x83a3  ldc.i4.1
0x83a4  ldarg.2
0x83a5  box      [mscorlib]System.Int32
0x83aa  stelem.ref
0x83ab  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x83b0  ldarg.1
0x83b1  callvirt instance class [System.Xml]System.Xml.XmlDocument Microsoft.Crm.Tools.ImportExportPublish.ImportXml::get_ImportDocument()
0x83b6  ldarg.1
0x83b7  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.ImportXml::get_Context()
0x83bc  ldarg.1
0x83bd  callvirt instance class Microsoft.Crm.Tools.ImportExportPublish.ImportTracer Microsoft.Crm.Tools.ImportExportPublish.ImportXml::get_Tracer()
0x83c2  ldloc.s  7
0x83c4  ldarg.1
0x83c5  callvirt instance class Microsoft.Crm.Tools.ImportExportPublish.RootImportHandler Microsoft.Crm.Tools.ImportExportPublish.ImportXml::get_RootHandler()
0x83ca  callvirt instance class Microsoft.Crm.Tools.ImportExportPublish.ImportHelper Microsoft.Crm.Tools.ImportExportPublish.RootImportHandler::get_ImportHelper()
0x83cf  ldarg.1
0x83d0  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, bool>::.ctor()
0x83d5  call     class Microsoft.Crm.Tools.ImportExportPublish.ImportRibbonsHandler Microsoft.Crm.Tools.ImportExportPublish.ImportRibbonsHandler::CreateRibbonsHandler(class [System.Xml]System.Xml.XmlDocument importDocument, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context, class Microsoft.Crm.Tools.ImportExportPublish.ImportTracer tracer, int32 entityTypeCode, class Microsoft.Crm.Tools.ImportExportPublish.ImportHelper importHelper, class Microsoft.Crm.Tools.ImportExportPublish.ImportXml parent, class [mscorlib]System.Collections.Generic.Dictionary`2<string, bool> entitiesWithRibbon)
0x83da  callvirt instance void Microsoft.Crm.Tools.ImportExportPublish.ImportHandler::ImportItem()
0x83df  ldloc.2
0x83e0  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x83e5  brtrue   loc_82BD
0x83ea  leave.s  loc_840A
0x83ec  ldloc.2
0x83ed  isinst   [mscorlib]System.IDisposable
0x83f2  stloc.s  8
0x83f4  ldloc.s  8
0x83f6  brfalse.s loc_83FF
0x83f8  ldloc.s  8
0x83fa  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x83ff  endfinally
0x8400  ldloc.1
0x8401  brfalse.s loc_8409
0x8403  ldloc.1
0x8404  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x8409  endfinally
0x840a  ret
```
