# Microsoft.Crm.Tools.ImportExportPublish.ImportSavedOrgInsightsConfigurationHandler::ImportItem

- ea: `0x1fb50`
- end: `0x1fce8`
- name: `Microsoft.Crm.Tools.ImportExportPublish.ImportSavedOrgInsightsConfigurationHandler::ImportItem`
- size: `408`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x1fb50`
- `0x1fe50`
- `0x35e50`
- `0x46410`
- `0x464d0`
- `0x50dc0`
- `0x50e50`
- `0x63db0`
- `0x63df0`

## string_xrefs

- `0x1fb56`: `/ImportExportXml/SavedOrgInsightsConfigurations`
- `0x1fba1`: `SavedOrgInsightsConfiguration`
- `0x1fbe8`: `SavedOrgInsightsConfiguration`

## pseudocode

```c

```

## disassembly

```asm
0x1fb50  ldarg.0
0x1fb51  ldfld    class [System.Xml]System.Xml.XmlDocument Microsoft.Crm.Tools.ImportExportPublish.ImportEntityHandlerBase::_doc
0x1fb56  ldstr    aImportexportxm_32// "/ImportExportXml/SavedOrgInsightsConfig"...
0x1fb5b  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x1fb60  stloc.0
0x1fb61  ldloc.0
0x1fb62  brtrue.s loc_1FB65
0x1fb64  ret
0x1fb65  nop
0x1fb66  newobj   instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.SavedOrgInsightsConfigurationService::.ctor()
0x1fb6b  stloc.1
0x1fb6c  newobj   instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.BusinessDataLocalizedLabelService::.ctor()
0x1fb71  stloc.2
0x1fb72  ldarg.0
0x1fb73  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.ImportEntityHandlerBase::_context
0x1fb78  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x1fb7d  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::get_LanguageCode()
0x1fb82  stloc.s  5
0x1fb84  ldloca.s 5
0x1fb86  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1fb8b  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x1fb90  stloc.3
0x1fb91  ldloc.3
0x1fb92  ldloca.s 4
0x1fb94  call     bool [mscorlib]System.Int32::TryParse(string, int32&)
0x1fb99  brtrue.s loc_1FBA0
0x1fb9b  leave    loc_1FCE7
0x1fba0  ldloc.0
0x1fba1  ldstr    aSavedorginsigh// "SavedOrgInsightsConfiguration"
0x1fba6  callvirt instance class [System.Xml]System.Xml.XmlNodeList [System.Xml]System.Xml.XmlNode::SelectNodes(string)
0x1fbab  stloc.s  6
0x1fbad  ldloc.s  6
0x1fbaf  callvirt instance class [mscorlib]System.Collections.IEnumerator [System.Xml]System.Xml.XmlNodeList::GetEnumerator()
0x1fbb4  stloc.s  7
0x1fbb6  br       loc_1FC80
0x1fbbb  ldloc.s  7
0x1fbbd  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x1fbc2  castclass [System.Xml]System.Xml.XmlNode
0x1fbc7  stloc.s  8
0x1fbc9  ldarg.0
0x1fbca  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.ImportEntityHandlerBase::_context
0x1fbcf  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x1fbd4  newobj   instance void [Microsoft.Crm.Entities]Microsoft.Crm.Entities.SavedOrgInsightsConfiguration::.ctor(valuetype [mscorlib]System.Guid)
0x1fbd9  stloc.s  9
0x1fbdb  ldarg.0
0x1fbdc  ldloc.s  8
0x1fbde  ldloc.s  9
0x1fbe0  ldc.i4.4
0x1fbe1  newarr   [mscorlib]System.String
0x1fbe6  dup
0x1fbe7  ldc.i4.0
0x1fbe8  ldstr    aSavedorginsigh// "SavedOrgInsightsConfiguration"
0x1fbed  stelem.ref
0x1fbee  dup
0x1fbef  ldc.i4.1
0x1fbf0  ldstr    aParameters_0// "Parameters"
0x1fbf5  stelem.ref
0x1fbf6  dup
0x1fbf7  ldc.i4.2
0x1fbf8  ldstr    aDescriptions// "Descriptions"
0x1fbfd  stelem.ref
0x1fbfe  dup
0x1fbff  ldc.i4.3
0x1fc00  ldstr    aLocalizednames_1// "LocalizedNames"
0x1fc05  stelem.ref
0x1fc06  call     instance void Microsoft.Crm.Tools.ImportExportPublish.ImportEntityHandlerBase::InitializeEntity(class [System.Xml]System.Xml.XmlNode entityNode, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity entity, string[] excludedNodes)
0x1fc0b  ldloc.s  8
0x1fc0d  ldstr    aParameters_0// "Parameters"
0x1fc12  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x1fc17  brfalse.s loc_1FC36
0x1fc19  ldloc.s  9
0x1fc1b  ldstr    aParameters// "parameters"
0x1fc20  ldloc.s  8
0x1fc22  ldstr    aParameters_0// "Parameters"
0x1fc27  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x1fc2c  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerXml()
0x1fc31  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x1fc36  ldloc.s  8
0x1fc38  ldloc.3
0x1fc39  ldloc.3
0x1fc3a  call     string Microsoft.Crm.Tools.ImportExportPublish.ImportHandler::GetBaseLanguageDescription(class [System.Xml]System.Xml.XmlNode node, string baseLanguage, string originalBaseLanguage)
0x1fc3f  stloc.s  0xA
0x1fc41  ldloc.s  9
0x1fc43  ldstr    aDescription// "description"
0x1fc48  ldloc.s  0xA
0x1fc4a  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x1fc4f  ldloc.s  8
0x1fc51  ldloc.3
0x1fc52  ldloc.3
0x1fc53  call     string Microsoft.Crm.Tools.ImportExportPublish.ImportHandler::GetBaseLanguageName(class [System.Xml]System.Xml.XmlNode node, string baseLanguage, string originalBaseLanguage)
0x1fc58  stloc.s  0xB
0x1fc5a  ldloc.s  9
0x1fc5c  ldstr    aName// "name"
0x1fc61  ldloc.s  0xB
0x1fc63  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x1fc68  ldarg.0
0x1fc69  ldloc.1
0x1fc6a  ldloc.s  9
0x1fc6c  ldarg.0
0x1fc6d  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.ImportEntityHandlerBase::_context
0x1fc72  call     instance void Microsoft.Crm.Tools.ImportExportPublish.ImportEntityHandlerBase::EnsureEntityExisted(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject service, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity entity, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x1fc77  ldarg.0
0x1fc78  ldloc.2
0x1fc79  ldloc.s  8
0x1fc7b  call     instance void Microsoft.Crm.Tools.ImportExportPublish.ImportSavedOrgInsightsConfigurationHandler::CreateUpdateMUILabelBusinessData(class [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.BusinessDataLocalizedLabelService localizedLabelService, class [System.Xml]System.Xml.XmlNode savedOrgInsightsConfigurationNode)
0x1fc80  ldloc.s  7
0x1fc82  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x1fc87  brtrue   loc_1FBBB
0x1fc8c  leave.s  loc_1FCA3
0x1fc8e  ldloc.s  7
0x1fc90  isinst   [mscorlib]System.IDisposable
0x1fc95  stloc.s  0xC
0x1fc97  ldloc.s  0xC
0x1fc99  brfalse.s loc_1FCA2
0x1fc9b  ldloc.s  0xC
0x1fc9d  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1fca2  endfinally
0x1fca3  leave.s  loc_1FCB1
0x1fca5  ldloc.s  6
0x1fca7  brfalse.s loc_1FCB0
0x1fca9  ldloc.s  6
0x1fcab  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1fcb0  endfinally
0x1fcb1  ldarg.0
0x1fcb2  ldfld    class Microsoft.Crm.Tools.ImportExportPublish.ImportTracer Microsoft.Crm.Tools.ImportExportPublish.ImportEntityHandlerBase::_tracer
0x1fcb7  ldsfld   string Microsoft.Crm.Tools.ImportExportPublish.ImportExportStrings::SavedOrgInsightsConfigurationImportSuccessMessage
0x1fcbc  ldc.i4.1
0x1fcbd  callvirt instance void Microsoft.Crm.Tools.ImportExportPublish.ImportTracer::AddSuccess(string successMessage, int32 count)
0x1fcc2  leave.s  loc_1FCE7
0x1fcc4  stloc.s  0xD
0x1fcc6  ldsfld   string Microsoft.Crm.Tools.ImportExportPublish.ImportExportStrings::SavedOrgInsightsConfigurationImportErrorMessage
0x1fccb  stloc.s  0xE
0x1fccd  ldarg.0
0x1fcce  ldfld    class Microsoft.Crm.Tools.ImportExportPublish.ImportTracer Microsoft.Crm.Tools.ImportExportPublish.ImportEntityHandlerBase::_tracer
0x1fcd3  ldloc.s  0xE
0x1fcd5  ldloc.s  0xD
0x1fcd7  ldc.i4.1
0x1fcd8  callvirt instance void Microsoft.Crm.Tools.ImportExportPublish.ImportTracer::AddError(string errorMessage, class [mscorlib]System.Exception errorException, int32 severity)
0x1fcdd  ldloc.s  0xE
0x1fcdf  ldloc.s  0xD
0x1fce1  newobj   instance void Microsoft.Crm.Tools.ImportExportPublish.ImportGenericEntitiesException::.ctor(string message, class [mscorlib]System.Exception innerException)
0x1fce6  throw
0x1fce7  ret
```
