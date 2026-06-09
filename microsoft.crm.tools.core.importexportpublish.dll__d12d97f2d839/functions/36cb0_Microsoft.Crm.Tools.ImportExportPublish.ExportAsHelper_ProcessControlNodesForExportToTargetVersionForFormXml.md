# Microsoft.Crm.Tools.ImportExportPublish.ExportAsHelper::ProcessControlNodesForExportToTargetVersionForFormXml

- ea: `0x36cb0`
- end: `0x37290`
- name: `Microsoft.Crm.Tools.ImportExportPublish.ExportAsHelper::ProcessControlNodesForExportToTargetVersionForFormXml`
- size: `1504`
- prototype: ``
- caller_count: `4`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18800`
- `0x2d2f0`
- `0x2e170`
- `0x3bee0`

## callees

- `0x36920`
- `0x369f0`
- `0x36cb0`
- `0x373a0`
- `0x37410`
- `0x3aa70`
- `0x3aa80`
- `0x964a0`

## string_xrefs

- `0x36ed3`: `SolutionComponentType.Attribute`
- `0x37165`: `SolutionComponentType.Attribute`
- `0x37005`: `Customization.Type_FormXml`
- `0x37087`: `Customization.Type_FormXml`
- `0x37249`: `Customization.Type_FormXml`
- `0x36cec`: `SolutionComponentType.Control`
- `0x36d02`: `//cell/control/@classid`
- `0x36f1f`: `SolutionComponentType.EntityRelationship`
- `0x37118`: `SolutionComponentType.EntityRelationship`
- `0x36fb8`: `SolutionComponentType.View`
- `0x3703b`: `SolutionComponentType.View`
- `0x371b1`: `SolutionComponentType.View`
- `0x371fd`: `SolutionComponentType.View`

## pseudocode

```c

```

## disassembly

```asm
0x36cb0  newobj   instance void <>c__DisplayClass33_0::.ctor()
0x36cb5  stloc.0
0x36cb6  ldloc.0
0x36cb7  ldarg.0
0x36cb8  stfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext <>c__DisplayClass33_0::context
0x36cbd  ldloc.0
0x36cbe  ldarg.s  6
0x36cc0  stfld    class Microsoft.Crm.Tools.ImportExportPublish.FilteredComponent <>c__DisplayClass33_0::currentFilteredComponent
0x36cc5  ldloc.0
0x36cc6  ldarg.2
0x36cc7  stfld    string <>c__DisplayClass33_0::componentType
0x36ccc  ldc.i4.0
0x36ccd  stloc.1
0x36cce  ldloc.0
0x36ccf  ldloc.0
0x36cd0  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext <>c__DisplayClass33_0::context
0x36cd5  callvirt instance int32 [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_CallerLanguageCode()
0x36cda  newobj   instance void [mscorlib]System.Globalization.CultureInfo::.ctor(int32)
0x36cdf  stfld    class [mscorlib]System.Globalization.CultureInfo <>c__DisplayClass33_0::cultureInfo
0x36ce4  ldloc.0
0x36ce5  ldarg.3
0x36ce6  stfld    string <>c__DisplayClass33_0::componentName
0x36ceb  ldloc.0
0x36cec  ldstr    aSolutioncompon_1// "SolutionComponentType.Control"
0x36cf1  ldloc.0
0x36cf2  ldfld    class [mscorlib]System.Globalization.CultureInfo <>c__DisplayClass33_0::cultureInfo
0x36cf7  call     string [Microsoft.Crm.ObjectModel]Microsoft.Crm.Resources.ObjectModelResourceManager::GetString(string, class [mscorlib]System.Globalization.CultureInfo)
0x36cfc  stfld    string <>c__DisplayClass33_0::dependentType
0x36d01  ldarg.1
0x36d02  ldstr    aCellControlCla// "//cell/control/@classid"
0x36d07  callvirt instance class [System.Xml]System.Xml.XmlNodeList [System.Xml]System.Xml.XmlNode::SelectNodes(string)
0x36d0c  stloc.s  5
0x36d0e  ldloc.s  5
0x36d10  callvirt instance class [mscorlib]System.Collections.IEnumerator [System.Xml]System.Xml.XmlNodeList::GetEnumerator()
0x36d15  stloc.s  6
0x36d17  br       loc_36E9D
0x36d1c  ldloc.s  6
0x36d1e  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x36d23  castclass [System.Xml]System.Xml.XmlNode
0x36d28  stloc.s  7
0x36d2a  ldloc.s  7
0x36d2c  isinst   [System.Xml]System.Xml.XmlAttribute
0x36d31  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlAttribute::get_OwnerElement()
0x36d36  stloc.s  8
0x36d38  ldloc.s  8
0x36d3a  brfalse  loc_36E9D
0x36d3f  ldloc.s  7
0x36d41  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Value()
0x36d46  dup
0x36d47  ldloca.s 9
0x36d49  call     bool [mscorlib]System.Guid::TryParse(string, valuetype [mscorlib]System.Guid&)
0x36d4e  brfalse  loc_36DD8
0x36d53  call     class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid> [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.SystemFormDependencyCalculator/FeatureDependencyClassIds::get_ClassIds()
0x36d58  ldloc.s  9
0x36d5a  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid>::ContainsKey(var<u1>)
0x36d5f  brfalse.s loc_36DD8
0x36d61  ldarg.s  8
0x36d63  call     class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid> [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.SystemFormDependencyCalculator/FeatureDependencyClassIds::get_ClassIds()
0x36d68  ldloc.s  9
0x36d6a  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid>::get_Item(void)
0x36d6f  ldc.i4   0xA0
0x36d74  call     T0x2B000017
0x36d79  callvirt instance valuetype Microsoft.Crm.Tools.ImportExportPublish.ComponentAction Microsoft.Crm.Tools.ImportExportPublish.ExportToTargetVersionContext::ActionToBeTakenOnComponent(class [mscorlib]System.Tuple`2<valuetype [mscorlib]System.Guid, int32> dependentComponent)
0x36d7e  ldc.i4.1
0x36d7f  bne.un.s loc_36DD8
0x36d81  ldloc.s  8
0x36d83  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x36d88  ldstr    aId// "id"
0x36d8d  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0x36d92  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Value()
0x36d97  stloc.s  0xA
0x36d99  ldarg.s  7
0x36d9b  ldloc.s  8
0x36d9d  callvirt instance void class [mscorlib]System.Action`1<class [System.Xml]System.Xml.XmlNode>::Invoke(var<u1>)
0x36da2  ldloc.s  8
0x36da4  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::get_ParentNode()
0x36da9  ldloc.s  8
0x36dab  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::RemoveChild(class [System.Xml]System.Xml.XmlNode)
0x36db0  pop
0x36db1  ldloc.0
0x36db2  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext <>c__DisplayClass33_0::context
0x36db7  ldloc.0
0x36db8  ldfld    class Microsoft.Crm.Tools.ImportExportPublish.FilteredComponent <>c__DisplayClass33_0::currentFilteredComponent
0x36dbd  ldloc.0
0x36dbe  ldfld    string <>c__DisplayClass33_0::componentType
0x36dc3  ldloc.0
0x36dc4  ldfld    string <>c__DisplayClass33_0::componentName
0x36dc9  ldloc.0
0x36dca  ldfld    string <>c__DisplayClass33_0::dependentType
0x36dcf  ldloc.s  0xA
0x36dd1  call     void Microsoft.Crm.Tools.ImportExportPublish.ExportAsHelper::AddUpdatedComment(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context, class Microsoft.Crm.Tools.ImportExportPublish.FilteredComponent currentFilteredComponent, string componentType, string componentId, string dependentType, string dependentId)
0x36dd6  ldc.i4.1
0x36dd7  stloc.1
0x36dd8  ldloca.s 9
0x36dda  call     bool [mscorlib]System.Guid::TryParse(string, valuetype [mscorlib]System.Guid&)
0x36ddf  brfalse  loc_36E9D
0x36de4  call     class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class [mscorlib]System.Collections.Generic.IList`1<class [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.SystemFormDependencyCalculator/ModifedControl>> [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.SystemFormDependencyCalculator/FeatureModifiedClassIds::get_ClassIds()
0x36de9  ldloc.s  9
0x36deb  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class [mscorlib]System.Collections.Generic.IList`1<class [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.SystemFormDependencyCalculator/ModifedControl>>::ContainsKey(var<u1>)
0x36df0  brfalse  loc_36E9D
0x36df5  call     class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class [mscorlib]System.Collections.Generic.IList`1<class [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.SystemFormDependencyCalculator/ModifedControl>> [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.SystemFormDependencyCalculator/FeatureModifiedClassIds::get_ClassIds()
0x36dfa  ldloc.s  9
0x36dfc  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class [mscorlib]System.Collections.Generic.IList`1<class [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.SystemFormDependencyCalculator/ModifedControl>>::get_Item(void)
0x36e01  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.SystemFormDependencyCalculator/ModifedControl>::GetEnumerator()
0x36e06  stloc.s  0xB
0x36e08  br.s     loc_36E83
0x36e0a  ldloc.s  0xB
0x36e0c  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.SystemFormDependencyCalculator/ModifedControl>::get_Current()
0x36e11  stloc.s  0xC
0x36e13  ldarg.s  8
0x36e15  ldloc.s  0xC
0x36e17  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.SystemFormDependencyCalculator/ModifedControl::get_Feature()
0x36e1c  ldc.i4   0xA0
0x36e21  call     T0x2B000017
0x36e26  ldc.i4.0
0x36e27  ldloc.s  0xC
0x36e29  callvirt instance class [mscorlib]System.Version [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.SystemFormDependencyCalculator/ModifedControl::get_IntroducedVersion()
0x36e2e  callvirt instance valuetype Microsoft.Crm.Tools.ImportExportPublish.ComponentAction Microsoft.Crm.Tools.ImportExportPublish.ExportToTargetVersionContext::ActionToBeTakenOnComponent(class [mscorlib]System.Tuple`2<valuetype [mscorlib]System.Guid, int32> dependentComponent, bool addFilteredComponentComment, [opt] class [mscorlib]System.Version introducedVersion)
0x36e33  ldc.i4.1
0x36e34  bne.un.s loc_36E83
0x36e36  ldloc.s  8
0x36e38  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x36e3d  ldstr    aId// "id"
0x36e42  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0x36e47  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Value()
0x36e4c  stloc.s  0xD
0x36e4e  ldloc.s  8
0x36e50  ldloc.s  0xC
0x36e52  callvirt instance string[] [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.SystemFormDependencyCalculator/ModifedControl::get_Parameters()
0x36e57  call     void Microsoft.Crm.Tools.ImportExportPublish.ExportAsHelper::RemoveControlParams(class [System.Xml]System.Xml.XmlNode controlNode, string[] paramsToRemove)
0x36e5c  ldloc.0
0x36e5d  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext <>c__DisplayClass33_0::context
0x36e62  ldloc.0
0x36e63  ldfld    class Microsoft.Crm.Tools.ImportExportPublish.FilteredComponent <>c__DisplayClass33_0::currentFilteredComponent
0x36e68  ldloc.0
0x36e69  ldfld    string <>c__DisplayClass33_0::componentType
0x36e6e  ldloc.0
0x36e6f  ldfld    string <>c__DisplayClass33_0::componentName
0x36e74  ldloc.0
0x36e75  ldfld    string <>c__DisplayClass33_0::dependentType
0x36e7a  ldloc.s  0xD
0x36e7c  call     void Microsoft.Crm.Tools.ImportExportPublish.ExportAsHelper::AddUpdatedComment(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context, class Microsoft.Crm.Tools.ImportExportPublish.FilteredComponent currentFilteredComponent, string componentType, string componentId, string dependentType, string dependentId)
0x36e81  ldc.i4.1
0x36e82  stloc.1
0x36e83  ldloc.s  0xB
0x36e85  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x36e8a  brtrue   loc_36E0A
0x36e8f  leave.s  loc_36E9D
0x36e91  ldloc.s  0xB
0x36e93  brfalse.s loc_36E9C
0x36e95  ldloc.s  0xB
0x36e97  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x36e9c  endfinally
0x36e9d  ldloc.s  6
0x36e9f  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x36ea4  brtrue   loc_36D1C
0x36ea9  leave.s  loc_36ECC
0x36eab  ldloc.s  6
0x36ead  isinst   [mscorlib]System.IDisposable
0x36eb2  stloc.s  0xE
0x36eb4  ldloc.s  0xE
0x36eb6  brfalse.s loc_36EBF
0x36eb8  ldloc.s  0xE
0x36eba  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x36ebf  endfinally
0x36ec0  ldloc.s  5
0x36ec2  brfalse.s loc_36ECB
0x36ec4  ldloc.s  5
0x36ec6  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x36ecb  endfinally
0x36ecc  ldstr    aCellControlDat// "//cell/control/@datafieldname"
0x36ed1  stloc.2
0x36ed2  ldloc.0
0x36ed3  ldstr    aSolutioncompon_0// "SolutionComponentType.Attribute"
0x36ed8  ldloc.0
0x36ed9  ldfld    class [mscorlib]System.Globalization.CultureInfo <>c__DisplayClass33_0::cultureInfo
0x36ede  call     string [Microsoft.Crm.ObjectModel]Microsoft.Crm.Resources.ObjectModelResourceManager::GetString(string, class [mscorlib]System.Globalization.CultureInfo)
0x36ee3  stfld    string <>c__DisplayClass33_0::dependentType
0x36ee8  ldloc.1
0x36ee9  ldloc.0
0x36eea  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext <>c__DisplayClass33_0::context
0x36eef  ldarg.1
0x36ef0  ldloc.2
0x36ef1  ldc.i4.2
0x36ef2  ldarg.s  4
0x36ef4  ldloc.0
0x36ef5  ldfld    class Microsoft.Crm.Tools.ImportExportPublish.FilteredComponent <>c__DisplayClass33_0::currentFilteredComponent
0x36efa  ldarg.s  5
0x36efc  ldc.i4.1
0x36efd  ldarg.s  7
0x36eff  ldloc.0
0x36f00  ldfld    string <>c__DisplayClass33_0::componentType
0x36f05  ldloc.0
0x36f06  ldfld    string <>c__DisplayClass33_0::componentName
0x36f0b  ldloc.0
0x36f0c  ldfld    string <>c__DisplayClass33_0::dependentType
0x36f11  call     bool Microsoft.Crm.Tools.ImportExportPublish.ExportAsHelper::ProcessXpathForExportToTargetVersion(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context, class [System.Xml]System.Xml.XmlDocument document, string xpath, int32 solutionComponentType, string currentEntityName, class Microsoft.Crm.Tools.ImportExportPublish.FilteredComponent currentFilteredComponent, class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity> dependencies, int32 nodeParentLevelToRemove, class [mscorlib]System.Action`1<class [System.Xml]System.Xml.XmlNode> actionBeforeDeleteNode, string componentType, string componentId, string dependentType)
0x36f16  or
0x36f17  stloc.1
0x36f18  ldstr    aControlParamet// "//control/parameters/RelationshipName"
0x36f1d  stloc.2
0x36f1e  ldloc.0
0x36f1f  ldstr    aSolutioncompon_2// "SolutionComponentType.EntityRelationshi"...
0x36f24  ldloc.0
0x36f25  ldfld    class [mscorlib]System.Globalization.CultureInfo <>c__DisplayClass33_0::cultureInfo
0x36f2a  call     string [Microsoft.Crm.ObjectModel]Microsoft.Crm.Resources.ObjectModelResourceManager::GetString(string, class [mscorlib]System.Globalization.CultureInfo)
0x36f2f  stfld    string <>c__DisplayClass33_0::dependentType
0x36f34  ldloc.1
0x36f35  ldloc.0
0x36f36  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext <>c__DisplayClass33_0::context
0x36f3b  ldarg.1
0x36f3c  ldloc.2
0x36f3d  ldc.i4.s 0xA
0x36f3f  ldarg.s  4
0x36f41  ldloc.0
0x36f42  ldfld    class Microsoft.Crm.Tools.ImportExportPublish.FilteredComponent <>c__DisplayClass33_0::currentFilteredComponent
0x36f47  ldarg.s  5
0x36f49  ldc.i4.2
0x36f4a  ldarg.s  7
0x36f4c  ldloc.0
0x36f4d  ldfld    string <>c__DisplayClass33_0::componentType
0x36f52  ldloc.0
0x36f53  ldfld    string <>c__DisplayClass33_0::componentName
0x36f58  ldloc.0
0x36f59  ldfld    string <>c__DisplayClass33_0::dependentType
0x36f5e  call     bool Microsoft.Crm.Tools.ImportExportPublish.ExportAsHelper::ProcessXpathForExportToTargetVersion(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context, class [System.Xml]System.Xml.XmlDocument document, string xpath, int32 solutionComponentType, string currentEntityName, class Microsoft.Crm.Tools.ImportExportPublish.FilteredComponent currentFilteredComponent, class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity> dependencies, int32 nodeParentLevelToRemove, class [mscorlib]System.Action`1<class [System.Xml]System.Xml.XmlNode> actionBeforeDeleteNode, string componentType, string componentId, string dependentType)
0x36f63  or
0x36f64  stloc.1
0x36f65  ldstr    aControlParamet_0// "//control/parameters/TargetEntityType"
0x36f6a  stloc.2
0x36f6b  ldloc.0
0x36f6c  ldstr    aCustomizationT_3// "Customization.Type_Entity"
0x36f71  ldloc.0
0x36f72  ldfld    class [mscorlib]System.Globalization.CultureInfo <>c__DisplayClass33_0::cultureInfo
0x36f77  call     string [Microsoft.Crm.ObjectModel]Microsoft.Crm.Resources.ObjectModelResourceManager::GetString(string, class [mscorlib]System.Globalization.CultureInfo)
0x36f7c  stfld    string <>c__DisplayClass33_0::dependentType
0x36f81  ldloc.1
0x36f82  ldloc.0
0x36f83  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext <>c__DisplayClass33_0::context
0x36f88  ldarg.1
0x36f89  ldloc.2
0x36f8a  ldc.i4.1
0x36f8b  ldarg.s  4
0x36f8d  ldloc.0
0x36f8e  ldfld    class Microsoft.Crm.Tools.ImportExportPublish.FilteredComponent <>c__DisplayClass33_0::currentFilteredComponent
0x36f93  ldarg.s  5
0x36f95  ldc.i4.2
0x36f96  ldarg.s  7
0x36f98  ldloc.0
0x36f99  ldfld    string <>c__DisplayClass33_0::componentType
0x36f9e  ldloc.0
0x36f9f  ldfld    string <>c__DisplayClass33_0::componentName
0x36fa4  ldloc.0
0x36fa5  ldfld    string <>c__DisplayClass33_0::dependentType
0x36faa  call     bool Microsoft.Crm.Tools.ImportExportPublish.ExportAsHelper::ProcessXpathForExportToTargetVersion(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context, class [System.Xml]System.Xml.XmlDocument document, string xpath, int32 solutionComponentType, string currentEntityName, class Microsoft.Crm.Tools.ImportExportPublish.FilteredComponent currentFilteredComponent, class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity> dependencies, int32 nodeParentLevelToRemove, class [mscorlib]System.Action`1<class [System.Xml]System.Xml.XmlNode> actionBeforeDeleteNode, string componentType, string componentId, string dependentType)
0x36faf  or
0x36fb0  stloc.1
0x36fb1  ldstr    aControlParamet_1// "//control/parameters/ViewIds"
0x36fb6  stloc.2
0x36fb7  ldloc.0
0x36fb8  ldstr    aSolutioncompon_3// "SolutionComponentType.View"
0x36fbd  ldloc.0
0x36fbe  ldfld    class [mscorlib]System.Globalization.CultureInfo <>c__DisplayClass33_0::cultureInfo
0x36fc3  call     string [Microsoft.Crm.ObjectModel]Microsoft.Crm.Resources.ObjectModelResourceManager::GetString(string, class [mscorlib]System.Globalization.CultureInfo)
0x36fc8  stfld    string <>c__DisplayClass33_0::dependentType
0x36fcd  ldloc.1
0x36fce  ldloc.0
0x36fcf  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext <>c__DisplayClass33_0::context
0x36fd4  ldarg.1
0x36fd5  ldloc.2
0x36fd6  ldc.i4.s 0x1A
0x36fd8  ldarg.s  4
0x36fda  ldloc.0
0x36fdb  ldfld    class Microsoft.Crm.Tools.ImportExportPublish.FilteredComponent <>c__DisplayClass33_0::currentFilteredComponent
0x36fe0  ldarg.s  5
0x36fe2  ldc.i4.0
0x36fe3  ldnull
0x36fe4  ldloc.0
0x36fe5  ldfld    string <>c__DisplayClass33_0::componentType
0x36fea  ldloc.0
0x36feb  ldfld    string <>c__DisplayClass33_0::componentName
0x36ff0  ldloc.0
0x36ff1  ldfld    string <>c__DisplayClass33_0::dependentType
0x36ff6  call     bool Microsoft.Crm.Tools.ImportExportPublish.ExportAsHelper::ProcessXpathForExportToTargetVersion(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context, class [System.Xml]System.Xml.XmlDocument document, string xpath, int32 solutionComponentType, string currentEntityName, class Microsoft.Crm.Tools.ImportExportPublish.FilteredComponent currentFilteredComponent, class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity> dependencies, int32 nodeParentLevelToRemove, class [mscorlib]System.Action`1<class [System.Xml]System.Xml.XmlNode> actionBeforeDeleteNode, string componentType, string componentId, string dependentType)
0x36ffb  or
0x36ffc  stloc.1
0x36ffd  ldnull
0x36ffe  stloc.3
0x36fff  ldloc.0
0x37000  ldfld    string <>c__DisplayClass33_0::componentType
0x37005  ldstr    aCustomizationT_5// "Customization.Type_FormXml"
0x3700a  ldloc.0
0x3700b  ldfld    class [mscorlib]System.Globalization.CultureInfo <>c__DisplayClass33_0::cultureInfo
0x37010  call     string [Microsoft.Crm.ObjectModel]Microsoft.Crm.Resources.ObjectModelResourceManager::GetString(string, class [mscorlib]System.Globalization.CultureInfo)
0x37015  callvirt instance bool [mscorlib]System.String::Equals(string)
0x3701a  brfalse.s loc_3702E
0x3701c  ldloc.0
0x3701d  ldftn    instance void <>c__DisplayClass33_0::<ProcessControlNodesForExportToTargetVersionForFormXml>b__0(class [System.Xml]System.Xml.XmlNode viewIdNode)
0x37023  newobj   instance void class [mscorlib]System.Action`1<class [System.Xml]System.Xml.XmlNode>::.ctor(object, native int)
0x37028  stloc.3
  ... truncated ...
```
