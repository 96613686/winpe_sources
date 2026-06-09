# Microsoft.Crm.Metadata.Dependency.DependencyProcessor::GenerateViewContext

- ea: `0x645b0`
- end: `0x64669`
- name: `Microsoft.Crm.Metadata.Dependency.DependencyProcessor::GenerateViewContext`
- size: `185`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x63870`

## callees

- `0x645b0`
- `0x64670`
- `0x64700`
- `0x64790`
- `0x647f0`

## string_xrefs

- `0x64621`: `controldescriptionxml`
- `0x6462e`: `controldescriptionxml`
- `0x6463b`: `controldescriptionxml`

## pseudocode

```c

```

## disassembly

```asm
0x645b0  ldarg.2
0x645b1  callvirt instance string [Microsoft.Crm.ObjectModel]Microsoft.Crm.Metadata.MetadataContext::get_EntityLogicalName()
0x645b6  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x645bb  brtrue   loc_64668
0x645c0  ldarg.s  4
0x645c2  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x645c7  ldarg.2
0x645c8  callvirt instance string [Microsoft.Crm.ObjectModel]Microsoft.Crm.Metadata.MetadataContext::get_EntityLogicalName()
0x645cd  ldc.i4.1
0x645ce  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::GetEntity(string, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.NameMappingType)
0x645d3  stloc.0
0x645d4  ldloc.0
0x645d5  brfalse  loc_64668
0x645da  ldarg.0
0x645db  ldloc.0
0x645dc  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_Code()
0x645e1  ldarg.1
0x645e2  ldarg.3
0x645e3  ldarg.s  4
0x645e5  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity Microsoft.Crm.Metadata.Dependency.DependencyProcessor::AddCustomControlConfigCandidateItem(int32 entityTypeCode, class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Crm.ObjectModel]Microsoft.Crm.Metadata.Generators.CandidateItem> roots, class [Microsoft.Crm.ObjectModel]Microsoft.Crm.Metadata.QueryContext queryContext, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext executionContext)
0x645ea  stloc.1
0x645eb  ldloc.1
0x645ec  brfalse.s loc_6461D
0x645ee  call     class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl [Microsoft.Crm.Core]Microsoft.Crm.FeatureControl::get_Current()
0x645f3  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl::get_Features()
0x645f8  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer::get_EditableGridControlPbl()
0x645fd  ldarg.s  4
0x645ff  call     bool [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.FeatureControlUtilities::IsFeatureEnabled(class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x64604  brfalse.s loc_6461D
0x64606  ldarg.0
0x64607  ldarg.2
0x64608  callvirt instance string [Microsoft.Crm.ObjectModel]Microsoft.Crm.Metadata.MetadataContext::get_EntityLogicalName()
0x6460d  ldarg.1
0x6460e  ldarg.3
0x6460f  ldloc.1
0x64610  ldloc.0
0x64611  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_Code()
0x64616  ldarg.s  4
0x64618  call     instance void Microsoft.Crm.Metadata.Dependency.DependencyProcessor::AddGridBusinessLogicCandidateItem(string entityLogicalName, class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Crm.ObjectModel]Microsoft.Crm.Metadata.Generators.CandidateItem> roots, class [Microsoft.Crm.ObjectModel]Microsoft.Crm.Metadata.QueryContext queryContext, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity config, int32 entityTypeCode, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext executionContext)
0x6461d  ldloc.1
0x6461e  brfalse.s loc_6465B
0x64620  ldloc.1
0x64621  ldstr    aControldescrip// "controldescriptionxml"
0x64626  callvirt instance bool [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::Contains(string)
0x6462b  brfalse.s loc_6465B
0x6462d  ldloc.1
0x6462e  ldstr    aControldescrip// "controldescriptionxml"
0x64633  callvirt instance object [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Item(string)
0x64638  brfalse.s loc_6465B
0x6463a  ldloc.1
0x6463b  ldstr    aControldescrip// "controldescriptionxml"
0x64640  callvirt instance object [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Item(string)
0x64645  callvirt instance string [mscorlib]System.Object::ToString()
0x6464a  call     class [System.Xml]System.Xml.XmlDocument [Microsoft.Crm.Core]Microsoft.Crm.SharedUtil::CreateXmlDocument(string)
0x6464f  stloc.2
0x64650  ldarg.0
0x64651  ldloc.2
0x64652  ldarg.1
0x64653  ldarg.3
0x64654  ldarg.s  4
0x64656  call     instance void Microsoft.Crm.Metadata.Dependency.DependencyProcessor::AddCustomControlCandidateItem(class [System.Xml]System.Xml.XmlDocument controlDescriptionXml, class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Crm.ObjectModel]Microsoft.Crm.Metadata.Generators.CandidateItem> roots, class [Microsoft.Crm.ObjectModel]Microsoft.Crm.Metadata.QueryContext queryContext, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext executionContext)
0x6465b  ldarg.2
0x6465c  ldstr    aViewselector// "viewselector"
0x64661  ldarg.1
0x64662  ldarg.3
0x64663  call     void Microsoft.Crm.Metadata.Dependency.DependencyProcessor::AddSelectorCandidateItem(class [Microsoft.Crm.ObjectModel]Microsoft.Crm.Metadata.MetadataContext metadataContext, string selectorType, class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Crm.ObjectModel]Microsoft.Crm.Metadata.Generators.CandidateItem> roots, class [Microsoft.Crm.ObjectModel]Microsoft.Crm.Metadata.QueryContext queryContext)
0x64668  ret
```
