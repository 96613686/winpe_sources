# Microsoft.Crm.Tools.ImportExportPublish.ConvertRuleItemHandler::ExportItem

- ea: `0x2b030`
- end: `0x2b290`
- name: `Microsoft.Crm.Tools.ImportExportPublish.ConvertRuleItemHandler::ExportItem`
- size: `608`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x2b030`
- `0x39770`
- `0x39ac0`
- `0x3a780`
- `0x3aa60`
- `0x3b380`
- `0x3b3c0`

## string_xrefs

- `0x2b122`: `ConditionXml`
- `0x2b128`: `conditionxml`
- `0x2b13f`: `PropertiesXml`
- `0x2b145`: `propertiesxml`

## pseudocode

```c

```

## disassembly

```asm
0x2b030  ldarg.1
0x2b031  ldstr    aConvertruleite_2// "ConvertRuleItems"
0x2b036  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::CreateElement(string)
0x2b03b  stloc.0
0x2b03c  ldarg.0
0x2b03d  ldfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection Microsoft.Crm.Tools.ImportExportPublish.ConvertRuleItemHandler::Collection
0x2b042  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.CollectionBase::GetEnumerator()
0x2b047  stloc.1
0x2b048  br       loc_2B1FC
0x2b04d  ldloc.1
0x2b04e  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x2b053  castclass [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity
0x2b058  stloc.2
0x2b059  ldarg.0
0x2b05a  ldflda   valuetype [mscorlib]System.Guid Microsoft.Crm.Tools.ImportExportPublish.ConvertRuleItemHandler::_convertRuleId
0x2b05f  ldloc.2
0x2b060  ldstr    aConvertruleid// "convertruleid"
0x2b065  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x2b06a  unbox.any [mscorlib]System.Guid
0x2b06f  call     instance bool [mscorlib]System.Guid::Equals(valuetype [mscorlib]System.Guid)
0x2b074  brfalse  loc_2B1FC
0x2b079  ldarg.1
0x2b07a  ldstr    aConvertruleite_0// "ConvertRuleItem"
0x2b07f  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::CreateElement(string)
0x2b084  stloc.3
0x2b085  ldarg.0
0x2b086  ldarg.1
0x2b087  ldloc.3
0x2b088  ldstr    aConvertruleite_3// "ConvertRuleItemId"
0x2b08d  ldloc.2
0x2b08e  ldstr    aConvertruleite_1// "convertruleitemid"
0x2b093  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x2b098  unbox.any [mscorlib]System.Guid
0x2b09d  stloc.s  4
0x2b09f  ldloca.s 4
0x2b0a1  ldstr    aB// "B"
0x2b0a6  call     instance string [mscorlib]System.Guid::ToString(string)
0x2b0ab  callvirt instance string [mscorlib]System.String::ToUpperInvariant()
0x2b0b0  call     instance void Microsoft.Crm.Tools.ImportExportPublish.ExportHandler::AddXmlNode(class [System.Xml]System.Xml.XmlDocument importDocument, class [System.Xml]System.Xml.XmlNode parentNode, string nodeName, string value)
0x2b0b5  ldarg.0
0x2b0b6  ldarg.1
0x2b0b7  ldloc.3
0x2b0b8  ldstr    aConvertruleid_0// "ConvertRuleId"
0x2b0bd  ldloc.2
0x2b0be  ldstr    aConvertruleid// "convertruleid"
0x2b0c3  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x2b0c8  unbox.any [mscorlib]System.Guid
0x2b0cd  stloc.s  4
0x2b0cf  ldloca.s 4
0x2b0d1  ldstr    aB// "B"
0x2b0d6  call     instance string [mscorlib]System.Guid::ToString(string)
0x2b0db  callvirt instance string [mscorlib]System.String::ToUpperInvariant()
0x2b0e0  call     instance void Microsoft.Crm.Tools.ImportExportPublish.ExportHandler::AddXmlNode(class [System.Xml]System.Xml.XmlDocument importDocument, class [System.Xml]System.Xml.XmlNode parentNode, string nodeName, string value)
0x2b0e5  ldarg.0
0x2b0e6  ldarg.1
0x2b0e7  ldloc.3
0x2b0e8  ldstr    aName_1// "Name"
0x2b0ed  ldloc.2
0x2b0ee  ldstr    aName// "name"
0x2b0f3  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x2b0f8  castclass [mscorlib]System.String
0x2b0fd  call     instance void Microsoft.Crm.Tools.ImportExportPublish.ExportHandler::AddXmlNode(class [System.Xml]System.Xml.XmlDocument importDocument, class [System.Xml]System.Xml.XmlNode parentNode, string nodeName, string value)
0x2b102  ldarg.0
0x2b103  ldarg.1
0x2b104  ldloc.3
0x2b105  ldstr    aDescription_0// "Description"
0x2b10a  ldloc.2
0x2b10b  ldstr    aDescription// "description"
0x2b110  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x2b115  castclass [mscorlib]System.String
0x2b11a  call     instance void Microsoft.Crm.Tools.ImportExportPublish.ExportHandler::AddXmlNode(class [System.Xml]System.Xml.XmlDocument importDocument, class [System.Xml]System.Xml.XmlNode parentNode, string nodeName, string value)
0x2b11f  ldarg.0
0x2b120  ldarg.1
0x2b121  ldloc.3
0x2b122  ldstr    aConditionxml// "ConditionXml"
0x2b127  ldloc.2
0x2b128  ldstr    aConditionxml_0// "conditionxml"
0x2b12d  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x2b132  castclass [mscorlib]System.String
0x2b137  call     instance void Microsoft.Crm.Tools.ImportExportPublish.ExportHandler::AddXmlNode(class [System.Xml]System.Xml.XmlDocument importDocument, class [System.Xml]System.Xml.XmlNode parentNode, string nodeName, string value)
0x2b13c  ldarg.0
0x2b13d  ldarg.1
0x2b13e  ldloc.3
0x2b13f  ldstr    aPropertiesxml// "PropertiesXml"
0x2b144  ldloc.2
0x2b145  ldstr    aPropertiesxml_0// "propertiesxml"
0x2b14a  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x2b14f  castclass [mscorlib]System.String
0x2b154  call     instance void Microsoft.Crm.Tools.ImportExportPublish.ExportHandler::AddXmlNode(class [System.Xml]System.Xml.XmlDocument importDocument, class [System.Xml]System.Xml.XmlNode parentNode, string nodeName, string value)
0x2b159  ldloc.2
0x2b15a  ldstr    aWorkflowid_0// "workflowid"
0x2b15f  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::IsAttributeNull(string)
0x2b164  brtrue.s loc_2B1BA
0x2b166  ldarg.0
0x2b167  ldfld    class Microsoft.Crm.Tools.ImportExportPublish.ExportToTargetVersionContext Microsoft.Crm.Tools.ImportExportPublish.ConvertRuleItemHandler::exportToTargetVersionContext
0x2b16c  callvirt instance bool Microsoft.Crm.Tools.ImportExportPublish.ExportToTargetVersionContext::IsTargetVersionSpecified()
0x2b171  brfalse.s loc_2B18A
0x2b173  ldarg.0
0x2b174  ldfld    class Microsoft.Crm.Tools.ImportExportPublish.ExportToTargetVersionContext Microsoft.Crm.Tools.ImportExportPublish.ConvertRuleItemHandler::exportToTargetVersionContext
0x2b179  callvirt instance class [mscorlib]System.Version Microsoft.Crm.Tools.ImportExportPublish.ExportToTargetVersionContext::get_TargetVersion()
0x2b17e  ldsfld   class [mscorlib]System.Version [Microsoft.Crm]Microsoft.Crm.CrmVersions::VegaVersion
0x2b183  call     bool [mscorlib]System.Version::op_LessThanOrEqual(class [mscorlib]System.Version, class [mscorlib]System.Version)
0x2b188  brtrue.s loc_2B1BA
0x2b18a  ldarg.0
0x2b18b  ldarg.1
0x2b18c  ldloc.3
0x2b18d  ldstr    aWorkflowid// "WorkflowId"
0x2b192  ldloc.2
0x2b193  ldstr    aWorkflowid_0// "workflowid"
0x2b198  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x2b19d  unbox.any [mscorlib]System.Guid
0x2b1a2  stloc.s  4
0x2b1a4  ldloca.s 4
0x2b1a6  ldstr    aB// "B"
0x2b1ab  call     instance string [mscorlib]System.Guid::ToString(string)
0x2b1b0  callvirt instance string [mscorlib]System.String::ToUpperInvariant()
0x2b1b5  call     instance void Microsoft.Crm.Tools.ImportExportPublish.ExportHandler::AddXmlNode(class [System.Xml]System.Xml.XmlDocument importDocument, class [System.Xml]System.Xml.XmlNode parentNode, string nodeName, string value)
0x2b1ba  ldarg.0
0x2b1bb  ldarg.1
0x2b1bc  ldloc.3
0x2b1bd  ldstr    aConvertruleite_3// "ConvertRuleItemId"
0x2b1c2  ldloc.2
0x2b1c3  ldstr    aConvertruleite_1// "convertruleitemid"
0x2b1c8  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x2b1cd  callvirt instance string [mscorlib]System.Object::ToString()
0x2b1d2  call     instance void Microsoft.Crm.Tools.ImportExportPublish.ExportHandler::AddXmlAttributeNode(class [System.Xml]System.Xml.XmlDocument importDocument, class [System.Xml]System.Xml.XmlNode parentNode, string nodeName, string value)
0x2b1d7  ldarg.0
0x2b1d8  ldarg.1
0x2b1d9  ldloc.3
0x2b1da  ldstr    aName_1// "Name"
0x2b1df  ldloc.2
0x2b1e0  ldstr    aName// "name"
0x2b1e5  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x2b1ea  callvirt instance string [mscorlib]System.Object::ToString()
0x2b1ef  call     instance void Microsoft.Crm.Tools.ImportExportPublish.ExportHandler::AddXmlAttributeNode(class [System.Xml]System.Xml.XmlDocument importDocument, class [System.Xml]System.Xml.XmlNode parentNode, string nodeName, string value)
0x2b1f4  ldloc.0
0x2b1f5  ldloc.3
0x2b1f6  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::AppendChild(class [System.Xml]System.Xml.XmlNode)
0x2b1fb  pop
0x2b1fc  ldloc.1
0x2b1fd  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x2b202  brtrue   loc_2B04D
0x2b207  leave.s  loc_2B21D
0x2b209  ldloc.1
0x2b20a  isinst   [mscorlib]System.IDisposable
0x2b20f  stloc.s  5
0x2b211  ldloc.s  5
0x2b213  brfalse.s loc_2B21C
0x2b215  ldloc.s  5
0x2b217  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x2b21c  endfinally
0x2b21d  ldarg.0
0x2b21e  ldfld    class [System.Xml]System.Xml.XmlNode Microsoft.Crm.Tools.ImportExportPublish.ConvertRuleItemHandler::covnertRuleNode
0x2b223  ldloc.0
0x2b224  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::AppendChild(class [System.Xml]System.Xml.XmlNode)
0x2b229  pop
0x2b22a  leave.s  loc_2B261
0x2b22c  stloc.s  6
0x2b22e  ldarg.0
0x2b22f  ldfld    class Microsoft.Crm.Tools.ImportExportPublish.ExportTracer Microsoft.Crm.Tools.ImportExportPublish.ConvertRuleItemHandler::tracer
0x2b234  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x2b239  ldsfld   string Microsoft.Crm.Tools.ImportExportPublish.ImportExportStrings::ConvertRuleItemExportErrorMessage
0x2b23e  ldc.i4.1
0x2b23f  newarr   [mscorlib]System.Object
0x2b244  dup
0x2b245  ldc.i4.0
0x2b246  ldarg.0
0x2b247  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Tools.ImportExportPublish.ConvertRuleItemHandler::_convertRuleId
0x2b24c  box      [mscorlib]System.Guid
0x2b251  stelem.ref
0x2b252  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x2b257  ldloc.s  6
0x2b259  ldc.i4.1
0x2b25a  callvirt instance void Microsoft.Crm.Tools.ImportExportPublish.ExportTracer::AddError(string errorMessage, class [mscorlib]System.Exception errorException, int32 severity)
0x2b25f  rethrow
0x2b261  ldarg.0
0x2b262  ldfld    class Microsoft.Crm.Tools.ImportExportPublish.ExportTracer Microsoft.Crm.Tools.ImportExportPublish.ConvertRuleItemHandler::tracer
0x2b267  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x2b26c  ldsfld   string Microsoft.Crm.Tools.ImportExportPublish.ImportExportStrings::ConvertRuleItemExportSuccessMessage
0x2b271  ldc.i4.1
0x2b272  newarr   [mscorlib]System.Object
0x2b277  dup
0x2b278  ldc.i4.0
0x2b279  ldarg.0
0x2b27a  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Tools.ImportExportPublish.ConvertRuleItemHandler::_convertRuleId
0x2b27f  box      [mscorlib]System.Guid
0x2b284  stelem.ref
0x2b285  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x2b28a  callvirt instance void Microsoft.Crm.Tools.ImportExportPublish.ExportTracer::AddSuccess(string successMessage)
0x2b28f  ret
```
