# Microsoft.Crm.Tools.LangProvisioning.LanguageActivation::ProcessFormXml

- ea: `0x8680`
- end: `0x89ad`
- name: `Microsoft.Crm.Tools.LangProvisioning.LanguageActivation::ProcessFormXml`
- size: `813`
- prototype: ``
- caller_count: `2`
- callee_count: `11`
- tags: `registry_config, broker_com_uri`

## callers

- `0x7050`
- `0xddc0`

## callees

- `0x6ea0`
- `0x8680`
- `0xa1b0`
- `0xa3a0`
- `0xa5a0`
- `0xa910`
- `0xac20`
- `0xac90`
- `0xd390`
- `0xd3b0`
- `0xf7a0`

## string_xrefs

- `0x86a3`: `ImportExportXml/Entities/Entity`
- `0x873c`: `FormXml/forms`
- `0x87b2`: `FormXml`
- `0x88a3`: `FormXml`

## pseudocode

```c

```

## disassembly

```asm
0x8680  ldarg.0
0x8681  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.LangProvisioning.LanguageActivation::_context
0x8686  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x868b  stloc.0
0x868c  ldloc.0
0x868d  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::get_LanguageCode()
0x8692  stloc.1
0x8693  ldarg.0
0x8694  ldarg.s  5
0x8696  call     instance bool Microsoft.Crm.Tools.LangProvisioning.LanguageActivation::IsSystemSolution(class Microsoft.Crm.Tools.LangProvisioning.LabelSolutionInfo solutionInfo)
0x869b  stloc.2
0x869c  newobj   instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.SystemFormService::.ctor()
0x86a1  stloc.3
0x86a2  ldarg.1
0x86a3  ldstr    aImportexportxm_7// "ImportExportXml/Entities/Entity"
0x86a8  callvirt instance class [System.Xml]System.Xml.XmlNodeList [System.Xml]System.Xml.XmlNode::SelectNodes(string)
0x86ad  stloc.s  4
0x86af  ldloc.s  4
0x86b1  callvirt instance class [mscorlib]System.Collections.IEnumerator [System.Xml]System.Xml.XmlNodeList::GetEnumerator()
0x86b6  stloc.s  5
0x86b8  br       loc_897D
0x86bd  ldloc.s  5
0x86bf  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x86c4  castclass [System.Xml]System.Xml.XmlNode
0x86c9  stloc.s  6
0x86cb  ldsfld   string [mscorlib]System.String::Empty
0x86d0  stloc.s  7
0x86d2  ldloc.s  6
0x86d4  ldloca.s 7
0x86d6  call     string Microsoft.Crm.Tools.LangProvisioning.LanguageActivation::GetAttributeName(class [System.Xml]System.Xml.XmlNode attributeNode, [out] string& columnName)
0x86db  stloc.s  8
0x86dd  ldloc.s  8
0x86df  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0x86e4  brtrue.s loc_871B
0x86e6  ldarg.s  5
0x86e8  ldstr    aEntity_0// "Entity"
0x86ed  ldloc.s  7
0x86ef  ldloc.s  8
0x86f1  ldc.i4.1
0x86f2  ldarg.0
0x86f3  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.LangProvisioning.LanguageActivation::_context
0x86f8  call     bool Microsoft.Crm.Tools.LangProvisioning.LanguageActivation::ShouldSkipComponent(class Microsoft.Crm.Tools.LangProvisioning.LabelSolutionInfo labelSolutionInfo, string entityName, string primaryAttributeName, object attributeValue, bool isMetadata, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x86fd  brfalse.s loc_871B
0x86ff  ldstr    aEntity_0// "Entity"
0x8704  ldloc.s  7
0x8706  ldloc.s  8
0x8708  ldarg.2
0x8709  ldarg.s  5
0x870b  ldarg.0
0x870c  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.LangProvisioning.LanguageActivation::_context
0x8711  call     void Microsoft.Crm.Tools.LangProvisioning.LanguageActivation::LogComponentSkippedTrace(string componentName, string idName, string id, int32 languageCode, class Microsoft.Crm.Tools.LangProvisioning.LabelSolutionInfo labelSolutionInfo, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext _context)
0x8716  br       loc_897D
0x871b  ldloc.s  6
0x871d  ldloc.0
0x871e  ldloc.2
0x871f  ldarg.3
0x8720  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataHelper::get_OrganizationId()
0x8725  call     int32 Microsoft.Crm.Tools.LangProvisioning.LanguageActivation::GetObjectTypeCodeForEntity(class [System.Xml]System.Xml.XmlNode entityNode, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache mdCache, bool isSystemSolution, valuetype [mscorlib]System.Guid orgId)
0x872a  stloc.s  9
0x872c  ldloc.s  6
0x872e  ldstr    aLogicalname// "LogicalName"
0x8733  call     string Microsoft.Crm.Tools.LangProvisioning.LanguageProvisioningUtility::GetXmlNodeValue(class [System.Xml]System.Xml.XmlNode xmlNode, string name)
0x8738  stloc.s  0xA
0x873a  ldloc.s  6
0x873c  ldstr    aFormxmlForms// "FormXml/forms"
0x8741  callvirt instance class [System.Xml]System.Xml.XmlNodeList [System.Xml]System.Xml.XmlNode::SelectNodes(string)
0x8746  stloc.s  0xB
0x8748  ldloc.s  0xB
0x874a  callvirt instance class [mscorlib]System.Collections.IEnumerator [System.Xml]System.Xml.XmlNodeList::GetEnumerator()
0x874f  stloc.s  0xC
0x8751  br       loc_894E
0x8756  ldloc.s  0xC
0x8758  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x875d  castclass [System.Xml]System.Xml.XmlNode
0x8762  stloc.s  0xD
0x8764  ldloc.s  0xD
0x8766  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x876b  ldstr    aType_0// "type"
0x8770  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0x8775  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Value()
0x877a  stloc.s  0xE
0x877c  ldloc.s  0xE
0x877e  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0x8783  brtrue.s loc_87C7
0x8785  ldloc.s  0xE
0x8787  callvirt instance string [mscorlib]System.String::ToLowerInvariant()
0x878c  ldstr    aMobile// "mobile"
0x8791  call     bool [mscorlib]System.String::op_Equality(string, string)
0x8796  brfalse.s loc_87C7
0x8798  ldarg.0
0x8799  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.LangProvisioning.LanguageActivation::_context
0x879e  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x87a3  stloc.s  0xF
0x87a5  ldloca.s 0xF
0x87a7  constrained. [mscorlib]System.Guid
0x87ad  callvirt instance string [mscorlib]System.Object::ToString()
0x87b2  ldstr    aFormxml// "FormXml"
0x87b7  ldarg.2
0x87b8  ldstr    aNotProcessingM// "Not processing mobile / phone express f"...
0x87bd  call     void Microsoft.Crm.Tools.Core.ImportExportPublish.ProvisionLanguageTelemetry::LangProvisioningTrace(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context, string componentId, string componentType, int32 languageCode, string message)
0x87c2  br       loc_894E
0x87c7  ldloc.s  0xD
0x87c9  ldstr    aSystemform// "systemform"
0x87ce  callvirt instance class [System.Xml]System.Xml.XmlNodeList [System.Xml]System.Xml.XmlNode::SelectNodes(string)
0x87d3  stloc.s  0x10
0x87d5  ldloc.s  0x10
0x87d7  callvirt instance class [mscorlib]System.Collections.IEnumerator [System.Xml]System.Xml.XmlNodeList::GetEnumerator()
0x87dc  stloc.s  0x11
0x87de  br       loc_891F
0x87e3  ldloc.s  0x11
0x87e5  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x87ea  castclass [System.Xml]System.Xml.XmlNode
0x87ef  stloc.s  0x12
0x87f1  ldloc.1
0x87f2  ldloc.s  0x12
0x87f4  call     bool Microsoft.Crm.Tools.LangProvisioning.LanguageActivation::IsNodeValidForLcid(int32 language, class [System.Xml]System.Xml.XPath.IXPathNavigable nodeNavigable)
0x87f9  brfalse  loc_891F
0x87fe  ldloc.s  0x12
0x8800  ldstr    aFormid// "formid"
0x8805  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x880a  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x880f  call     valuetype [mscorlib]System.Guid [System.Xml]System.Xml.XmlConvert::ToGuid(string)
0x8814  stloc.s  0x13
0x8816  ldarg.s  5
0x8818  ldstr    aSystemform_0// "SystemForm"
0x881d  ldstr    aFormid// "formid"
0x8822  ldloc.s  0x13
0x8824  box      [mscorlib]System.Guid
0x8829  ldc.i4.0
0x882a  ldarg.0
0x882b  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.LangProvisioning.LanguageActivation::_context
0x8830  call     bool Microsoft.Crm.Tools.LangProvisioning.LanguageActivation::ShouldSkipComponent(class Microsoft.Crm.Tools.LangProvisioning.LabelSolutionInfo labelSolutionInfo, string entityName, string primaryAttributeName, object attributeValue, bool isMetadata, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x8835  brfalse.s loc_8861
0x8837  ldstr    aSystemform_0// "SystemForm"
0x883c  ldstr    aFormid// "formid"
0x8841  ldloca.s 0x13
0x8843  constrained. [mscorlib]System.Guid
0x8849  callvirt instance string [mscorlib]System.Object::ToString()
0x884e  ldarg.2
0x884f  ldarg.s  5
0x8851  ldarg.0
0x8852  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.LangProvisioning.LanguageActivation::_context
0x8857  call     void Microsoft.Crm.Tools.LangProvisioning.LanguageActivation::LogComponentSkippedTrace(string componentName, string idName, string id, int32 languageCode, class Microsoft.Crm.Tools.LangProvisioning.LabelSolutionInfo labelSolutionInfo, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext _context)
0x885c  br       loc_891F
0x8861  ldstr    aProcessingLabe_4// "Processing labels for entityName={1}, o"...
0x8866  ldc.i4.4
0x8867  newarr   [mscorlib]System.Object
0x886c  dup
0x886d  ldc.i4.0
0x886e  ldloc.2
0x886f  box      [mscorlib]System.Boolean
0x8874  stelem.ref
0x8875  dup
0x8876  ldc.i4.1
0x8877  ldloc.s  0xA
0x8879  stelem.ref
0x887a  dup
0x887b  ldc.i4.2
0x887c  ldloc.s  9
0x887e  box      [mscorlib]System.Int32
0x8883  stelem.ref
0x8884  dup
0x8885  ldc.i4.3
0x8886  ldloc.s  0xE
0x8888  stelem.ref
0x8889  call     string [mscorlib]System.String::Format(string, object[])
0x888e  stloc.s  0x14
0x8890  ldarg.0
0x8891  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.LangProvisioning.LanguageActivation::_context
0x8896  ldloca.s 0x13
0x8898  constrained. [mscorlib]System.Guid
0x889e  callvirt instance string [mscorlib]System.Object::ToString()
0x88a3  ldstr    aFormxml// "FormXml"
0x88a8  ldarg.2
0x88a9  ldloc.s  0x14
0x88ab  call     void Microsoft.Crm.Tools.Core.ImportExportPublish.ProvisionLanguageTelemetry::LangProvisioningTrace(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context, string componentId, string componentType, int32 languageCode, string message)
0x88b0  ldarg.0
0x88b1  ldloc.s  0x12
0x88b3  ldstr    aFormid// "formid"
0x88b8  ldstr    aName// "name"
0x88bd  ldarg.2
0x88be  ldc.i4.5
0x88bf  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LocalizedLabelDescriptionPropertyBag Microsoft.Crm.Tools.LangProvisioning.LanguageActivation::GetLabelDescriptionFromXml(class [System.Xml]System.Xml.XmlNode objectNode, string objectIdAttributeName, string objectColumnName, int32 languageCode, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LabelTypeCode labelType)
0x88c4  stloc.s  0x15
0x88c6  ldarg.0
0x88c7  ldarg.3
0x88c8  ldloc.s  0x15
0x88ca  ldarg.s  4
0x88cc  ldloc.2
0x88cd  call     instance void Microsoft.Crm.Tools.LangProvisioning.LanguageActivation::AddUpdateQueue(class [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataHelper metadataHelper, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LocalizedLabelDescriptionPropertyBag pb, bool reprovision, bool isSystemSolution)
0x88d2  ldarg.0
0x88d3  ldloc.s  0x12
0x88d5  ldstr    aFormid// "formid"
0x88da  ldstr    aDescription// "description"
0x88df  ldarg.2
0x88e0  ldc.i4.5
0x88e1  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LocalizedLabelDescriptionPropertyBag Microsoft.Crm.Tools.LangProvisioning.LanguageActivation::GetLabelDescriptionFromXml(class [System.Xml]System.Xml.XmlNode objectNode, string objectIdAttributeName, string objectColumnName, int32 languageCode, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LabelTypeCode labelType)
0x88e6  stloc.s  0x16
0x88e8  ldloc.s  0x16
0x88ea  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LocalizedLabelDescription::get_Label()
0x88ef  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x88f4  brtrue.s loc_8902
0x88f6  ldarg.0
0x88f7  ldarg.3
0x88f8  ldloc.s  0x16
0x88fa  ldarg.s  4
0x88fc  ldloc.2
0x88fd  call     instance void Microsoft.Crm.Tools.LangProvisioning.LanguageActivation::AddUpdateQueue(class [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataHelper metadataHelper, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LocalizedLabelDescriptionPropertyBag pb, bool reprovision, bool isSystemSolution)
0x8902  ldloc.3
0x8903  ldloc.s  0x13
0x8905  ldloc.s  0xD
0x8907  callvirt instance string [System.Xml]System.Xml.XmlNode::get_OuterXml()
0x890c  ldloc.s  9
0x890e  ldarg.0
0x890f  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.LangProvisioning.LanguageActivation::_context
0x8914  ldarg.2
0x8915  newobj   instance void valuetype [mscorlib]System.Nullable`1<int32>::.ctor(var<u1>)
0x891a  callvirt instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.SystemFormService::UpdateFormLabels(valuetype [mscorlib]System.Guid, string, int32, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext, valuetype [mscorlib]System.Nullable`1<int32>)
0x891f  ldloc.s  0x11
0x8921  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x8926  brtrue   loc_87E3
0x892b  leave.s  loc_894E
0x892d  ldloc.s  0x11
0x892f  isinst   [mscorlib]System.IDisposable
0x8934  stloc.s  0x17
0x8936  ldloc.s  0x17
0x8938  brfalse.s loc_8941
0x893a  ldloc.s  0x17
0x893c  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x8941  endfinally
0x8942  ldloc.s  0x10
0x8944  brfalse.s loc_894D
0x8946  ldloc.s  0x10
0x8948  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x894d  endfinally
0x894e  ldloc.s  0xC
0x8950  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x8955  brtrue   loc_8756
0x895a  leave.s  loc_897D
0x895c  ldloc.s  0xC
0x895e  isinst   [mscorlib]System.IDisposable
0x8963  stloc.s  0x17
0x8965  ldloc.s  0x17
0x8967  brfalse.s loc_8970
0x8969  ldloc.s  0x17
0x896b  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x8970  endfinally
0x8971  ldloc.s  0xB
0x8973  brfalse.s loc_897C
0x8975  ldloc.s  0xB
0x8977  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x897c  endfinally
0x897d  ldloc.s  5
0x897f  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x8984  brtrue   loc_86BD
0x8989  leave.s  loc_89AC
0x898b  ldloc.s  5
0x898d  isinst   [mscorlib]System.IDisposable
0x8992  stloc.s  0x17
0x8994  ldloc.s  0x17
0x8996  brfalse.s loc_899F
0x8998  ldloc.s  0x17
0x899a  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x899f  endfinally
0x89a0  ldloc.s  4
0x89a2  brfalse.s loc_89AB
0x89a4  ldloc.s  4
0x89a6  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x89ab  endfinally
0x89ac  ret
```
