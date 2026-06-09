# Microsoft.Crm.Tools.ImportExportPublish.ImportRootComponentsHandler::IsExcluded

- ea: `0x5a7a0`
- end: `0x5a8f4`
- name: `Microsoft.Crm.Tools.ImportExportPublish.ImportRootComponentsHandler::IsExcluded`
- size: `340`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x5a190`

## callees

- `0x5a7a0`

## string_xrefs

- `0x5a7fd`: `/ImportExportXml/SiteMap`
- `0x5a826`: `/ImportExportXml/SdkMessageProcessingSteps/SdkMessageProcessingStep[@SdkMessageProcessingStepId='{`
- `0x5a843`: `/ImportExportXml/SolutionPluginAssemblies/PluginAssembly[@FullName='`
- `0x5a85b`: `/ImportExportXml/Entities/Entity/FormXml/forms[systemform/formid='{`

## pseudocode

```c

```

## disassembly

```asm
0x5a7a0  ldsfld   string [mscorlib]System.String::Empty
0x5a7a5  stloc.0
0x5a7a6  ldarg.2
0x5a7a7  callvirt instance int32 [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.ComponentInfo::get_ComponentType()
0x5a7ac  stloc.2
0x5a7ad  ldloc.2
0x5a7ae  ldc.i4.s 0x3E
0x5a7b0  bgt.s    loc_5A7CC
0x5a7b2  ldloc.2
0x5a7b3  ldc.i4.s 0x14
0x5a7b5  beq      loc_5A878
0x5a7ba  ldloc.2
0x5a7bb  ldc.i4.s 0x3C
0x5a7bd  beq      loc_5A85B
0x5a7c2  ldloc.2
0x5a7c3  ldc.i4.s 0x3E
0x5a7c5  beq.s    loc_5A7E3
0x5a7c7  br       loc_5A8A7
0x5a7cc  ldloc.2
0x5a7cd  ldc.i4.s 0x50
0x5a7cf  beq      loc_5A889
0x5a7d4  ldloc.2
0x5a7d5  ldc.i4.s 0x5B
0x5a7d7  beq.s    loc_5A843
0x5a7d9  ldloc.2
0x5a7da  ldc.i4.s 0x5C
0x5a7dc  beq.s    loc_5A826
0x5a7de  br       loc_5A8A7
0x5a7e3  ldarg.2
0x5a7e4  callvirt instance string [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.ComponentInfo::get_SchemaName()
0x5a7e9  brfalse.s loc_5A7FD
0x5a7eb  ldarg.2
0x5a7ec  callvirt instance string [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.ComponentInfo::get_SchemaName()
0x5a7f1  ldsfld   string [mscorlib]System.String::Empty
0x5a7f6  call     bool [mscorlib]System.String::op_Equality(string, string)
0x5a7fb  brfalse.s loc_5A808
0x5a7fd  ldstr    aImportexportxm_150// "/ImportExportXml/SiteMap"
0x5a802  stloc.0
0x5a803  br       loc_5A8A9
0x5a808  call     class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl [Microsoft.Crm.Core]Microsoft.Crm.FeatureControl::get_Current()
0x5a80d  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl::get_Features()
0x5a812  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer::get_AppModuleForOrganization()
0x5a817  ldarg.0
0x5a818  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.ImportRootComponentsHandler::context
0x5a81d  call     bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.FeatureEnabledHelper::IsFeatureEnabled(class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x5a822  ldc.i4.0
0x5a823  ceq
0x5a825  ret
0x5a826  ldstr    aImportexportxm_151// "/ImportExportXml/SdkMessageProcessingSt"...
0x5a82b  ldarg.2
0x5a82c  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.ComponentInfo::get_ObjectId()
0x5a831  box      [mscorlib]System.Guid
0x5a836  ldstr    asc_EA17A// "}']"
0x5a83b  call     string [mscorlib]System.String::Concat(object, object, object)
0x5a840  stloc.0
0x5a841  br.s     loc_5A8A9
0x5a843  ldstr    aImportexportxm_152// "/ImportExportXml/SolutionPluginAssembli"...
0x5a848  ldarg.2
0x5a849  callvirt instance string [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.ComponentInfo::get_SchemaName()
0x5a84e  ldstr    asc_A2596// "']"
0x5a853  call     string [mscorlib]System.String::Concat(string, string, string)
0x5a858  stloc.0
0x5a859  br.s     loc_5A8A9
0x5a85b  ldstr    aImportexportxm_153// "/ImportExportXml/Entities/Entity/FormXm"...
0x5a860  ldarg.2
0x5a861  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.ComponentInfo::get_ObjectId()
0x5a866  box      [mscorlib]System.Guid
0x5a86b  ldstr    asc_EA17A// "}']"
0x5a870  call     string [mscorlib]System.String::Concat(object, object, object)
0x5a875  stloc.0
0x5a876  br.s     loc_5A8A9
0x5a878  ldarg.2
0x5a879  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.ComponentInfo::get_ParentObjectId()
0x5a87e  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x5a883  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x5a888  ret
0x5a889  call     class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl [Microsoft.Crm.Core]Microsoft.Crm.FeatureControl::get_Current()
0x5a88e  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl::get_Features()
0x5a893  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer::get_AppModuleForOrganization()
0x5a898  ldarg.0
0x5a899  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.ImportRootComponentsHandler::context
0x5a89e  call     bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.FeatureEnabledHelper::IsFeatureEnabled(class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x5a8a3  ldc.i4.0
0x5a8a4  ceq
0x5a8a6  ret
0x5a8a7  ldc.i4.0
0x5a8a8  ret
0x5a8a9  ldarg.1
0x5a8aa  ldloc.0
0x5a8ab  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x5a8b0  stloc.1
0x5a8b1  ldloc.1
0x5a8b2  brfalse.s loc_5A8C1
0x5a8b4  ldloc.1
0x5a8b5  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerXml()
0x5a8ba  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x5a8bf  brfalse.s loc_5A8C3
0x5a8c1  ldc.i4.1
0x5a8c2  ret
0x5a8c3  ldarg.2
0x5a8c4  callvirt instance int32 [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.ComponentInfo::get_ComponentType()
0x5a8c9  ldc.i4.s 0x3C
0x5a8cb  bne.un.s loc_5A8F2
0x5a8cd  ldloc.1
0x5a8ce  brfalse.s loc_5A8F0
0x5a8d0  ldloc.1
0x5a8d1  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x5a8d6  ldstr    aType_0// "type"
0x5a8db  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0x5a8e0  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Value()
0x5a8e5  ldstr    aMobile// "mobile"
0x5a8ea  call     bool [mscorlib]System.String::op_Equality(string, string)
0x5a8ef  ret
0x5a8f0  ldc.i4.0
0x5a8f1  ret
0x5a8f2  ldc.i4.0
0x5a8f3  ret
```
