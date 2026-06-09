# Microsoft.Crm.Tools.LangProvisioning.LanguageActivation::ProcessComplexControlXml

- ea: `0x9060`
- end: `0x91be`
- name: `Microsoft.Crm.Tools.LangProvisioning.LanguageActivation::ProcessComplexControlXml`
- size: `350`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x7050`
- `0xddc0`

## callees

- `0x6ea0`
- `0x6ec0`
- `0x9060`
- `0xa1b0`
- `0xa910`
- `0xd3b0`
- `0xf7a0`

## string_xrefs

- `0x9098`: `/ImportExportXml/ComplexControls`
- `0x90f8`: `ComplexControl`
- `0x9112`: `ComplexControl`
- `0x9172`: `ComplexControlXml`

## pseudocode

```c

```

## disassembly

```asm
0x9060  call     class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl [Microsoft.Crm.Core]Microsoft.Crm.FeatureControl::get_Current()
0x9065  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl::get_Features()
0x906a  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer::get_RefreshSales()
0x906f  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.OrganizationBuildVersionCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.OrganizationBuildVersionCache::Instance()
0x9074  ldarg.0
0x9075  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.LangProvisioning.LanguageActivation::_context
0x907a  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x907f  ldarg.0
0x9080  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.LangProvisioning.LanguageActivation::_context
0x9085  callvirt instance var<u1> class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.BasicCrmCache`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.VersionCacheData>::LookupEntry(void, var<u1>)
0x908a  callvirt instance class [mscorlib]System.Version [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.VersionCacheData::get_CrmVersion()
0x908f  callvirt instance bool [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail::IsAvailable(class [mscorlib]System.Version)
0x9094  brtrue.s loc_9097
0x9096  ret
0x9097  ldarg.1
0x9098  ldstr    aImportexportxm_13// "/ImportExportXml/ComplexControls"
0x909d  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x90a2  stloc.0
0x90a3  ldloc.0
0x90a4  brfalse.s loc_90B3
0x90a6  ldloc.0
0x90a7  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerXml()
0x90ac  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x90b1  brfalse.s loc_90B4
0x90b3  ret
0x90b4  ldarg.0
0x90b5  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.LangProvisioning.LanguageActivation::_context
0x90ba  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x90bf  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::get_LanguageCode()
0x90c4  stloc.1
0x90c5  newobj   instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.ComplexControlService::.ctor()
0x90ca  stloc.2
0x90cb  ldloc.0
0x90cc  callvirt instance class [System.Xml]System.Xml.XmlNodeList [System.Xml]System.Xml.XmlNode::get_ChildNodes()
0x90d1  callvirt instance class [mscorlib]System.Collections.IEnumerator [System.Xml]System.Xml.XmlNodeList::GetEnumerator()
0x90d6  stloc.3
0x90d7  br       loc_919C
0x90dc  ldloc.3
0x90dd  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x90e2  castclass [System.Xml]System.Xml.XmlNode
0x90e7  stloc.s  4
0x90e9  ldloc.s  4
0x90eb  ldstr    aName// "name"
0x90f0  call     string Microsoft.Crm.Tools.LangProvisioning.LanguageProvisioningUtility::GetXmlNodeValue(class [System.Xml]System.Xml.XmlNode xmlNode, string name)
0x90f5  stloc.s  5
0x90f7  ldarg.3
0x90f8  ldstr    aComplexcontrol// "ComplexControl"
0x90fd  ldstr    aName// "name"
0x9102  ldloc.s  5
0x9104  ldc.i4.0
0x9105  ldarg.0
0x9106  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.LangProvisioning.LanguageActivation::_context
0x910b  call     bool Microsoft.Crm.Tools.LangProvisioning.LanguageActivation::ShouldSkipComponent(class Microsoft.Crm.Tools.LangProvisioning.LabelSolutionInfo labelSolutionInfo, string entityName, string primaryAttributeName, object attributeValue, bool isMetadata, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x9110  brfalse.s loc_912D
0x9112  ldstr    aComplexcontrol// "ComplexControl"
0x9117  ldstr    aName// "name"
0x911c  ldloc.s  5
0x911e  ldarg.2
0x911f  ldarg.3
0x9120  ldarg.0
0x9121  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.LangProvisioning.LanguageActivation::_context
0x9126  call     void Microsoft.Crm.Tools.LangProvisioning.LanguageActivation::LogComponentSkippedTrace(string componentName, string idName, string id, int32 languageCode, class Microsoft.Crm.Tools.LangProvisioning.LabelSolutionInfo labelSolutionInfo, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext _context)
0x912b  br.s     loc_919C
0x912d  ldloc.1
0x912e  ldloc.s  4
0x9130  call     bool Microsoft.Crm.Tools.LangProvisioning.LanguageActivation::IsNodeValidForLcid(int32 language, class [System.Xml]System.Xml.XPath.IXPathNavigable nodeNavigable)
0x9135  stloc.s  6
0x9137  ldloc.s  4
0x9139  ldstr    aId// "id"
0x913e  call     string Microsoft.Crm.Tools.LangProvisioning.LanguageProvisioningUtility::GetXmlNodeAttributesValue(class [System.Xml]System.Xml.XmlNode xmlNode, string name)
0x9143  stloc.s  7
0x9145  ldloc.s  4
0x9147  ldstr    aEntitylogicaln// "entitylogicalname"
0x914c  call     string Microsoft.Crm.Tools.LangProvisioning.LanguageProvisioningUtility::GetXmlNodeValue(class [System.Xml]System.Xml.XmlNode xmlNode, string name)
0x9151  stloc.s  8
0x9153  ldstr    aProcessingLabe_8// "Processing Labels for Name={0}, EntityL"...
0x9158  ldloc.s  5
0x915a  ldloc.s  8
0x915c  ldloc.s  6
0x915e  box      [mscorlib]System.Boolean
0x9163  call     string [mscorlib]System.String::Format(string, object, object, object)
0x9168  stloc.s  9
0x916a  ldarg.0
0x916b  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.LangProvisioning.LanguageActivation::_context
0x9170  ldloc.s  7
0x9172  ldstr    aComplexcontrol_0// "ComplexControlXml"
0x9177  ldarg.2
0x9178  ldloc.s  9
0x917a  call     void Microsoft.Crm.Tools.Core.ImportExportPublish.ProvisionLanguageTelemetry::LangProvisioningTrace(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context, string componentId, string componentType, int32 languageCode, string message)
0x917f  ldloc.s  6
0x9181  brfalse.s loc_919C
0x9183  ldloc.2
0x9184  ldloc.s  4
0x9186  callvirt instance string [System.Xml]System.Xml.XmlNode::get_OuterXml()
0x918b  ldarg.0
0x918c  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.LangProvisioning.LanguageActivation::_context
0x9191  ldarg.2
0x9192  newobj   instance void valuetype [mscorlib]System.Nullable`1<int32>::.ctor(var<u1>)
0x9197  callvirt instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.ComplexControlService::UpdateComplexControlLabels(string, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext, valuetype [mscorlib]System.Nullable`1<int32>)
0x919c  ldloc.3
0x919d  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x91a2  brtrue   loc_90DC
0x91a7  leave.s  loc_91BD
0x91a9  ldloc.3
0x91aa  isinst   [mscorlib]System.IDisposable
0x91af  stloc.s  0xA
0x91b1  ldloc.s  0xA
0x91b3  brfalse.s loc_91BC
0x91b5  ldloc.s  0xA
0x91b7  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x91bc  endfinally
0x91bd  ret
```
