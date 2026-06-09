# Microsoft.Crm.Tools.ImportExportPublish.ChannelAccessProfileHandler::ExportRuleDefinition

- ea: `0x2bf80`
- end: `0x2c0fb`
- name: `Microsoft.Crm.Tools.ImportExportPublish.ChannelAccessProfileHandler::ExportRuleDefinition`
- size: `379`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x2bf00`

## callees

- `0x2bf80`
- `0x2c100`
- `0x2c1f0`
- `0x2c2c0`
- `0x391e0`
- `0x39930`
- `0x39940`
- `0x3a5e0`
- `0x3b380`

## string_xrefs

- `0x2bfe6`: `ChannelAccessProfileAttributes`
- `0x2c04a`: `ChannelAccessProfileId`
- `0x2c038`: `channelaccessprofileid`
- `0x2bfac`: `ChannelAccessProfile`
- `0x2c00d`: `ChannelAccessProfileAttribute`

## pseudocode

```c

```

## disassembly

```asm
0x2bf80  ldarg.0
0x2bf81  ldarg.0
0x2bf82  ldfld    class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid> Microsoft.Crm.Tools.ImportExportPublish.ChannelAccessProfileHandler::_channelAccessProfiles
0x2bf87  ldarg.0
0x2bf88  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.ChannelAccessProfileHandler::_context
0x2bf8d  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection Microsoft.Crm.Tools.ImportExportPublish.ChannelAccessProfileHandler::RetrieveChannelAccessProfiles(class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid> channelAccessProfileIds, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x2bf92  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.CollectionBase::GetEnumerator()
0x2bf97  stloc.0
0x2bf98  br       loc_2C0D9
0x2bf9d  ldloc.0
0x2bf9e  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x2bfa3  castclass [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity
0x2bfa8  stloc.1
0x2bfa9  ldc.i4.0
0x2bfaa  stloc.2
0x2bfab  ldarg.1
0x2bfac  ldstr    aChannelaccessp_4// "ChannelAccessProfile"
0x2bfb1  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::CreateElement(string)
0x2bfb6  stloc.3
0x2bfb7  ldloc.1
0x2bfb8  ldstr    aSolutionid// "solutionid"
0x2bfbd  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x2bfc2  unbox.any [mscorlib]System.Guid
0x2bfc7  ldsfld   valuetype [mscorlib]System.Guid [Microsoft.Crm.Constants]Microsoft.Crm.SolutionConstants::ActiveSolutionId
0x2bfcc  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x2bfd1  ldloc.1
0x2bfd2  ldstr    aIsmanaged// "ismanaged"
0x2bfd7  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x2bfdc  unbox.any [mscorlib]System.Boolean
0x2bfe1  stloc.s  4
0x2bfe3  brfalse.s loc_2BFFE
0x2bfe5  ldarg.0
0x2bfe6  ldstr    aChannelaccessp// "ChannelAccessProfileAttributes"
0x2bfeb  ldarg.1
0x2bfec  ldloc.3
0x2bfed  ldloc.1
0x2bfee  newobj   instance void Microsoft.Crm.Tools.ImportExportPublish.GenericTypeBusinessEntity::.ctor(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity be)
0x2bff3  ldloc.s  4
0x2bff5  call     instance void Microsoft.Crm.Tools.ImportExportPublish.ExportHandler::AddXmlProperties(string itemType, class [System.Xml]System.Xml.XmlDocument importDocument, class [System.Xml]System.Xml.XmlNode parentNode, class Microsoft.Crm.Tools.ImportExportPublish.GenericType container, bool managed)
0x2bffa  ldc.i4.1
0x2bffb  stloc.2
0x2bffc  br.s     loc_2C031
0x2bffe  ldarg.1
0x2bfff  ldarg.0
0x2c000  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.ChannelAccessProfileHandler::_context
0x2c005  call     bool Microsoft.Crm.Tools.ImportExportPublish.ExportHandler::ExportAsUnmodified(class [System.Xml]System.Xml.XmlDocument importDocument, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x2c00a  brfalse.s loc_2C031
0x2c00c  ldarg.0
0x2c00d  ldstr    aChannelaccessp_6// "ChannelAccessProfileAttribute"
0x2c012  ldarg.1
0x2c013  ldloc.3
0x2c014  ldloc.1
0x2c015  newobj   instance void Microsoft.Crm.Tools.ImportExportPublish.GenericTypeBusinessEntity::.ctor(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity be)
0x2c01a  call     instance void Microsoft.Crm.Tools.ImportExportPublish.ExportHandler::AddXmlProperties(string itemType, class [System.Xml]System.Xml.XmlDocument importDocument, class [System.Xml]System.Xml.XmlNode parentNode, class Microsoft.Crm.Tools.ImportExportPublish.GenericType container)
0x2c01f  ldloc.3
0x2c020  ldstr    aUnmodified// "unmodified"
0x2c025  ldstr    a1// "1"
0x2c02a  callvirt instance void [System.Xml]System.Xml.XmlElement::SetAttribute(string, string)
0x2c02f  ldc.i4.1
0x2c030  stloc.2
0x2c031  ldloc.2
0x2c032  brfalse  loc_2C0D9
0x2c037  ldloc.1
0x2c038  ldstr    aChannelaccessp_1// "channelaccessprofileid"
0x2c03d  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x2c042  unbox.any [mscorlib]System.Guid
0x2c047  stloc.s  5
0x2c049  ldloc.3
0x2c04a  ldstr    aChannelaccessp_0// "ChannelAccessProfileId"
0x2c04f  ldloca.s 5
0x2c051  constrained. [mscorlib]System.Guid
0x2c057  callvirt instance string [mscorlib]System.Object::ToString()
0x2c05c  callvirt instance void [System.Xml]System.Xml.XmlElement::SetAttribute(string, string)
0x2c061  ldloc.3
0x2c062  ldstr    aName_1// "Name"
0x2c067  ldloc.1
0x2c068  ldstr    aName// "name"
0x2c06d  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x2c072  castclass [mscorlib]System.String
0x2c077  callvirt instance void [System.Xml]System.Xml.XmlElement::SetAttribute(string, string)
0x2c07c  ldarg.0
0x2c07d  ldarg.1
0x2c07e  ldloc.3
0x2c07f  call     instance void Microsoft.Crm.Tools.ImportExportPublish.ChannelAccessProfileHandler::AddEnabledEntities(class [System.Xml]System.Xml.XmlDocument importDocument, class [System.Xml]System.Xml.XmlElement channelAccessProfileNode)
0x2c084  ldarg.0
0x2c085  ldloc.s  5
0x2c087  ldarg.0
0x2c088  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.ChannelAccessProfileHandler::_context
0x2c08d  ldarg.1
0x2c08e  ldloc.3
0x2c08f  call     instance void Microsoft.Crm.Tools.ImportExportPublish.ChannelAccessProfileHandler::AddChannelAccessProfilePrivileges(valuetype [mscorlib]System.Guid ChannelAccessProfileId, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context, class [System.Xml]System.Xml.XmlDocument importDocument, class [System.Xml]System.Xml.XmlElement channelAccessProfileNode)
0x2c094  ldarg.2
0x2c095  ldloc.3
0x2c096  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::AppendChild(class [System.Xml]System.Xml.XmlNode)
0x2c09b  pop
0x2c09c  ldarg.0
0x2c09d  ldfld    class Microsoft.Crm.Tools.ImportExportPublish.ExportTracer Microsoft.Crm.Tools.ImportExportPublish.ChannelAccessProfileHandler::_tracer
0x2c0a2  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x2c0a7  ldsfld   string Microsoft.Crm.Tools.ImportExportPublish.ImportExportStrings::ChannelAccessProfileExportSuccessMessage
0x2c0ac  ldc.i4.2
0x2c0ad  newarr   [mscorlib]System.Object
0x2c0b2  dup
0x2c0b3  ldc.i4.0
0x2c0b4  ldloc.1
0x2c0b5  ldstr    aName// "name"
0x2c0ba  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x2c0bf  castclass [mscorlib]System.String
0x2c0c4  stelem.ref
0x2c0c5  dup
0x2c0c6  ldc.i4.1
0x2c0c7  ldloc.s  5
0x2c0c9  box      [mscorlib]System.Guid
0x2c0ce  stelem.ref
0x2c0cf  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x2c0d4  callvirt instance void Microsoft.Crm.Tools.ImportExportPublish.ExportTracer::AddSuccess(string successMessage)
0x2c0d9  ldloc.0
0x2c0da  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x2c0df  brtrue   loc_2BF9D
0x2c0e4  leave.s  loc_2C0FA
0x2c0e6  ldloc.0
0x2c0e7  isinst   [mscorlib]System.IDisposable
0x2c0ec  stloc.s  6
0x2c0ee  ldloc.s  6
0x2c0f0  brfalse.s loc_2C0F9
0x2c0f2  ldloc.s  6
0x2c0f4  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x2c0f9  endfinally
0x2c0fa  ret
```
