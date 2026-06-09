# Microsoft.Crm.Tools.ImportExportPublish.ProfileRuleItemHandler::ExportItem

- ea: `0x72610`
- end: `0x7277b`
- name: `Microsoft.Crm.Tools.ImportExportPublish.ProfileRuleItemHandler::ExportItem`
- size: `363`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x391e0`
- `0x39940`
- `0x39ac0`
- `0x3b380`
- `0x3b3c0`
- `0x72610`

## string_xrefs

- `0x7265d`: `channelaccessprofileruleid`
- `0x7262e`: `ChannelAccessProfileRuleItems`
- `0x72674`: `ChannelAccessProfileRuleItem`
- `0x72682`: `ChannelAccessProfileRuleItemId`
- `0x72688`: `channelaccessprofileruleitemid`

## pseudocode

```c

```

## disassembly

```asm
0x72610  call     class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl [Microsoft.Crm.Core]Microsoft.Crm.FeatureControl::get_Current()
0x72615  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl::get_Features()
0x7261a  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer::get_OnePartyModel()
0x7261f  ldarg.0
0x72620  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.ProfileRuleItemHandler::_context
0x72625  call     bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.FeatureEnabledHelper::IsFeatureEnabled(class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x7262a  brtrue.s loc_7262D
0x7262c  ret
0x7262d  ldarg.1
0x7262e  ldstr    aChannelaccessp_17// "ChannelAccessProfileRuleItems"
0x72633  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::CreateElement(string)
0x72638  stloc.0
0x72639  ldarg.0
0x7263a  ldfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection Microsoft.Crm.Tools.ImportExportPublish.ProfileRuleItemHandler::_entityCollection
0x7263f  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.CollectionBase::GetEnumerator()
0x72644  stloc.1
0x72645  br       loc_726D5
0x7264a  ldloc.1
0x7264b  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x72650  castclass [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity
0x72655  stloc.2
0x72656  ldarg.0
0x72657  ldflda   valuetype [mscorlib]System.Guid Microsoft.Crm.Tools.ImportExportPublish.ProfileRuleItemHandler::_profileRuleId
0x7265c  ldloc.2
0x7265d  ldstr    aChannelaccessp_3// "channelaccessprofileruleid"
0x72662  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x72667  unbox.any [mscorlib]System.Guid
0x7266c  call     instance bool [mscorlib]System.Guid::Equals(valuetype [mscorlib]System.Guid)
0x72671  brfalse.s loc_726D5
0x72673  ldarg.1
0x72674  ldstr    aChannelaccessp_18// "ChannelAccessProfileRuleItem"
0x72679  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::CreateElement(string)
0x7267e  stloc.3
0x7267f  ldarg.0
0x72680  ldarg.1
0x72681  ldloc.3
0x72682  ldstr    aChannelaccessp_19// "ChannelAccessProfileRuleItemId"
0x72687  ldloc.2
0x72688  ldstr    aChannelaccessp_20// "channelaccessprofileruleitemid"
0x7268d  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x72692  callvirt instance string [mscorlib]System.Object::ToString()
0x72697  call     instance void Microsoft.Crm.Tools.ImportExportPublish.ExportHandler::AddXmlAttributeNode(class [System.Xml]System.Xml.XmlDocument importDocument, class [System.Xml]System.Xml.XmlNode parentNode, string nodeName, string value)
0x7269c  ldarg.0
0x7269d  ldarg.1
0x7269e  ldloc.3
0x7269f  ldstr    aName_1// "Name"
0x726a4  ldloc.2
0x726a5  ldstr    aName// "name"
0x726aa  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x726af  callvirt instance string [mscorlib]System.Object::ToString()
0x726b4  call     instance void Microsoft.Crm.Tools.ImportExportPublish.ExportHandler::AddXmlAttributeNode(class [System.Xml]System.Xml.XmlDocument importDocument, class [System.Xml]System.Xml.XmlNode parentNode, string nodeName, string value)
0x726b9  ldarg.0
0x726ba  ldstr    aProfileruleite// "ProfileRuleItemAttributes"
0x726bf  ldarg.1
0x726c0  ldloc.3
0x726c1  ldloc.2
0x726c2  newobj   instance void Microsoft.Crm.Tools.ImportExportPublish.GenericTypeBusinessEntity::.ctor(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity be)
0x726c7  ldc.i4.0
0x726c8  call     instance void Microsoft.Crm.Tools.ImportExportPublish.ExportHandler::AddXmlProperties(string itemType, class [System.Xml]System.Xml.XmlDocument importDocument, class [System.Xml]System.Xml.XmlNode parentNode, class Microsoft.Crm.Tools.ImportExportPublish.GenericType container, bool managed)
0x726cd  ldloc.0
0x726ce  ldloc.3
0x726cf  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::AppendChild(class [System.Xml]System.Xml.XmlNode)
0x726d4  pop
0x726d5  ldloc.1
0x726d6  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x726db  brtrue   loc_7264A
0x726e0  leave.s  loc_726F6
0x726e2  ldloc.1
0x726e3  isinst   [mscorlib]System.IDisposable
0x726e8  stloc.s  4
0x726ea  ldloc.s  4
0x726ec  brfalse.s loc_726F5
0x726ee  ldloc.s  4
0x726f0  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x726f5  endfinally
0x726f6  ldarg.0
0x726f7  ldfld    class [System.Xml]System.Xml.XmlNode Microsoft.Crm.Tools.ImportExportPublish.ProfileRuleItemHandler::_profileRuleNode
0x726fc  ldloc.0
0x726fd  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::AppendChild(class [System.Xml]System.Xml.XmlNode)
0x72702  pop
0x72703  leave.s  loc_72743
0x72705  stloc.s  5
0x72707  ldarg.0
0x72708  ldfld    class Microsoft.Crm.Tools.ImportExportPublish.ExportTracer Microsoft.Crm.Tools.ImportExportPublish.ProfileRuleItemHandler::tracer
0x7270d  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x72712  ldsfld   string Microsoft.Crm.Tools.ImportExportPublish.ImportExportStrings::ProfileRuleExportFailureMessage
0x72717  ldc.i4.2
0x72718  newarr   [mscorlib]System.Object
0x7271d  dup
0x7271e  ldc.i4.0
0x7271f  ldarg.0
0x72720  ldfld    string Microsoft.Crm.Tools.ImportExportPublish.ProfileRuleItemHandler::_profileRuleName
0x72725  stelem.ref
0x72726  dup
0x72727  ldc.i4.1
0x72728  ldarg.0
0x72729  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Tools.ImportExportPublish.ProfileRuleItemHandler::_profileRuleId
0x7272e  box      [mscorlib]System.Guid
0x72733  stelem.ref
0x72734  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x72739  ldloc.s  5
0x7273b  ldc.i4.3
0x7273c  callvirt instance void Microsoft.Crm.Tools.ImportExportPublish.ExportTracer::AddError(string errorMessage, class [mscorlib]System.Exception errorException, int32 severity)
0x72741  rethrow
0x72743  ldarg.0
0x72744  ldfld    class Microsoft.Crm.Tools.ImportExportPublish.ExportTracer Microsoft.Crm.Tools.ImportExportPublish.ProfileRuleItemHandler::tracer
0x72749  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x7274e  ldsfld   string Microsoft.Crm.Tools.ImportExportPublish.ImportExportStrings::ProfileRuleExportSuccessMessage
0x72753  ldc.i4.2
0x72754  newarr   [mscorlib]System.Object
0x72759  dup
0x7275a  ldc.i4.0
0x7275b  ldarg.0
0x7275c  ldfld    string Microsoft.Crm.Tools.ImportExportPublish.ProfileRuleItemHandler::_profileRuleName
0x72761  stelem.ref
0x72762  dup
0x72763  ldc.i4.1
0x72764  ldarg.0
0x72765  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Tools.ImportExportPublish.ProfileRuleItemHandler::_profileRuleId
0x7276a  box      [mscorlib]System.Guid
0x7276f  stelem.ref
0x72770  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x72775  callvirt instance void Microsoft.Crm.Tools.ImportExportPublish.ExportTracer::AddSuccess(string successMessage)
0x7277a  ret
```
