# Microsoft.Crm.Tools.ImportExportPublish.SolutionHandler::AddMissingDependencies

- ea: `0x89dc0`
- end: `0x8a567`
- name: `Microsoft.Crm.Tools.ImportExportPublish.SolutionHandler::AddMissingDependencies`
- size: `1959`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x776a0`

## callees

- `0x136c0`
- `0x17d60`
- `0x89dc0`
- `0x8a570`
- `0x8a6b0`

## string_xrefs

- `0x89e8a`: `requiredcomponentobjectid`
- `0x8a147`: `requiredcomponentobjectid`
- `0x8a2da`: `requiredcomponentobjectid`
- `0x89e77`: `requiredcomponenttype`
- `0x8a134`: `requiredcomponenttype`
- `0x8a2c8`: `requiredcomponenttype`
- `0x89fc3`: `dependentcomponentobjectid`
- `0x8a1d4`: `dependentcomponentobjectid`
- `0x89fb0`: `dependentcomponenttype`
- `0x8a1c1`: `dependentcomponenttype`
- `0x89dd2`: `SolutionManifest`
- `0x89e64`: `requiredcomponentbasesolutionid`
- `0x8a110`: `requiredcomponentbasesolutionid`
- `0x89e9d`: `requiredcomponentparentid`
- `0x89eab`: `requiredcomponentparentid`
- `0x8a15a`: `requiredcomponentparentid`
- `0x8a168`: `requiredcomponentparentid`
- `0x8a2ec`: `requiredcomponentparentid`
- `0x8a2fa`: `requiredcomponentparentid`
- `0x89f76`: `Opening_Parentheses_Symbol`
- `0x89fd6`: `dependentcomponentparentid`
- `0x89fe4`: `dependentcomponentparentid`
- `0x8a1e7`: `dependentcomponentparentid`
- `0x8a1f5`: `dependentcomponentparentid`

## pseudocode

```c

```

## disassembly

```asm
0x89dc0  ldarg.1
0x89dc1  ldstr    aMissingdepende_2// "MissingDependencies"
0x89dc6  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::CreateElement(string)
0x89dcb  stloc.0
0x89dcc  ldarg.1
0x89dcd  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::get_DocumentElement()
0x89dd2  ldstr    aSolutionmanife_2// "SolutionManifest"
0x89dd7  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x89ddc  ldloc.0
0x89ddd  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::AppendChild(class [System.Xml]System.Xml.XmlNode)
0x89de2  pop
0x89de3  ldarg.0
0x89de4  ldfld    bool Microsoft.Crm.Tools.ImportExportPublish.ExportHandler::_exportDeltaOverride
0x89de9  brfalse.s loc_89DEC
0x89deb  ret
0x89dec  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.ComponentInfo>::.ctor()
0x89df1  stloc.1
0x89df2  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, string>::.ctor()
0x89df7  stloc.2
0x89df8  newobj   instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.DependencyService::.ctor()
0x89dfd  ldarg.0
0x89dfe  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Tools.ImportExportPublish.SolutionHandler::_solutionId
0x89e03  ldc.i4.0
0x89e04  ldc.i4.0
0x89e05  ldarg.0
0x89e06  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.SolutionHandler::_context
0x89e0b  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.DependencyService::RetrieveDependenciesForExport(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Platform.Server]Microsoft.Crm.Dependency.DependencyIncludeOption, bool, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x89e10  stloc.3
0x89e11  newobj   instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.DependencyFilter::.ctor()
0x89e16  ldloc.3
0x89e17  ldarg.0
0x89e18  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.SolutionHandler::_context
0x89e1d  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.DependencyFilter::FilterHiddenComponents(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x89e22  stloc.3
0x89e23  ldarg.0
0x89e24  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Tools.ImportExportPublish.SolutionHandler::_solutionId
0x89e29  ldloc.3
0x89e2a  ldarg.0
0x89e2b  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.SolutionHandler::_context
0x89e30  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection Microsoft.Crm.Tools.ImportExportPublish.DefaultSolutionFilterForActivityFeeds::FilterMissingDependencies(valuetype [mscorlib]System.Guid solutionId, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection dependencies, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x89e35  stloc.3
0x89e36  ldarg.0
0x89e37  ldloc.3
0x89e38  ldarg.0
0x89e39  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.SolutionHandler::_context
0x89e3e  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection Microsoft.Crm.Tools.ImportExportPublish.SolutionHandler::FilterRemovedDependencies(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection dependencies, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x89e43  stloc.3
0x89e44  ldc.i4.0
0x89e45  stloc.s  4
0x89e47  ldloc.3
0x89e48  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.CollectionBase::GetEnumerator()
0x89e4d  stloc.s  5
0x89e4f  br       loc_8A055
0x89e54  ldloc.s  5
0x89e56  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x89e5b  castclass [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity
0x89e60  stloc.s  6
0x89e62  ldloc.s  6
0x89e64  ldstr    aRequiredcompon_2// "requiredcomponentbasesolutionid"
0x89e69  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x89e6e  unbox.any [mscorlib]System.Guid
0x89e73  stloc.s  7
0x89e75  ldloc.s  6
0x89e77  ldstr    aRequiredcompon_0// "requiredcomponenttype"
0x89e7c  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x89e81  unbox.any [mscorlib]System.Int32
0x89e86  stloc.s  8
0x89e88  ldloc.s  6
0x89e8a  ldstr    aRequiredcompon// "requiredcomponentobjectid"
0x89e8f  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x89e94  unbox.any [mscorlib]System.Guid
0x89e99  stloc.s  9
0x89e9b  ldloc.s  6
0x89e9d  ldstr    aRequiredcompon_3// "requiredcomponentparentid"
0x89ea2  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::IsAttributeNull(string)
0x89ea7  brtrue.s loc_89EBC
0x89ea9  ldloc.s  6
0x89eab  ldstr    aRequiredcompon_3// "requiredcomponentparentid"
0x89eb0  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x89eb5  unbox.any [mscorlib]System.Guid
0x89eba  br.s     loc_89EC1
0x89ebc  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x89ec1  stloc.s  0xA
0x89ec3  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x89ec8  ldstr    a012_3// "{0}-{1}-{2}"
0x89ecd  ldc.i4.3
0x89ece  newarr   [mscorlib]System.Object
0x89ed3  dup
0x89ed4  ldc.i4.0
0x89ed5  ldloc.s  8
0x89ed7  box      [mscorlib]System.Int32
0x89edc  stelem.ref
0x89edd  dup
0x89ede  ldc.i4.1
0x89edf  ldloc.s  9
0x89ee1  box      [mscorlib]System.Guid
0x89ee6  stelem.ref
0x89ee7  dup
0x89ee8  ldc.i4.2
0x89ee9  ldloc.s  0xA
0x89eeb  box      [mscorlib]System.Guid
0x89ef0  stelem.ref
0x89ef1  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x89ef6  stloc.s  0xB
0x89ef8  ldloc.1
0x89ef9  ldloc.s  0xB
0x89efb  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.ComponentInfo>::ContainsKey(var<u1>)
0x89f00  brtrue.s loc_89F1C
0x89f02  ldloc.1
0x89f03  ldloc.s  0xB
0x89f05  ldloc.s  8
0x89f07  ldloc.s  9
0x89f09  ldloc.s  0xA
0x89f0b  ldloc.s  4
0x89f0d  dup
0x89f0e  ldc.i4.1
0x89f0f  add
0x89f10  stloc.s  4
0x89f12  newobj   instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.ComponentInfo::.ctor(int32, valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid, int32)
0x89f17  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.ComponentInfo>::Add(var<u1>, !!T0)
0x89f1c  ldloc.2
0x89f1d  ldloc.s  7
0x89f1f  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, string>::ContainsKey(var<u1>)
0x89f24  brtrue   loc_89FAE
0x89f29  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.SolutionCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.SolutionCache::Instance()
0x89f2e  ldloc.s  7
0x89f30  ldarg.0
0x89f31  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.SolutionHandler::_context
0x89f36  callvirt instance var<u1> class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.CrmMultiOrgCacheBase`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.ISolution>::LookupEntry(void, var<u1>)
0x89f3b  stloc.s  0xC
0x89f3d  ldloc.s  7
0x89f3f  call     bool [Microsoft.Crm.Constants]Microsoft.Crm.SolutionConstants::IsRestrictedSolution(valuetype [mscorlib]System.Guid)
0x89f44  brfalse.s loc_89F57
0x89f46  ldloc.2
0x89f47  ldloc.s  7
0x89f49  ldloc.s  0xC
0x89f4b  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.ISolution::get_UniqueName()
0x89f50  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, string>::Add(var<u1>, !!T0)
0x89f55  br.s     loc_89FAE
0x89f57  ldloc.2
0x89f58  ldloc.s  7
0x89f5a  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x89f5f  ldstr    a0123_0// "{0} {1}{2}{3}"
0x89f64  ldc.i4.4
0x89f65  newarr   [mscorlib]System.Object
0x89f6a  dup
0x89f6b  ldc.i4.0
0x89f6c  ldloc.s  0xC
0x89f6e  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.ISolution::get_UniqueName()
0x89f73  stelem.ref
0x89f74  dup
0x89f75  ldc.i4.1
0x89f76  ldstr    aOpeningParenth// "Opening_Parentheses_Symbol"
0x89f7b  ldarg.0
0x89f7c  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.SolutionHandler::_context
0x89f81  call     string [Microsoft.Crm.ObjectModel]Microsoft.Crm.Resources.ObjectModelResourceManager::GetString(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x89f86  stelem.ref
0x89f87  dup
0x89f88  ldc.i4.2
0x89f89  ldloc.s  0xC
0x89f8b  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.ISolution::get_Version()
0x89f90  stelem.ref
0x89f91  dup
0x89f92  ldc.i4.3
0x89f93  ldstr    aClosingParenth// "Closing_Parentheses_Symbol"
0x89f98  ldarg.0
0x89f99  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.SolutionHandler::_context
0x89f9e  call     string [Microsoft.Crm.ObjectModel]Microsoft.Crm.Resources.ObjectModelResourceManager::GetString(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x89fa3  stelem.ref
0x89fa4  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x89fa9  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, string>::Add(var<u1>, !!T0)
0x89fae  ldloc.s  6
0x89fb0  ldstr    aDependentcompo_0// "dependentcomponenttype"
0x89fb5  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x89fba  unbox.any [mscorlib]System.Int32
0x89fbf  stloc.s  8
0x89fc1  ldloc.s  6
0x89fc3  ldstr    aDependentcompo// "dependentcomponentobjectid"
0x89fc8  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x89fcd  unbox.any [mscorlib]System.Guid
0x89fd2  stloc.s  9
0x89fd4  ldloc.s  6
0x89fd6  ldstr    aDependentcompo_2// "dependentcomponentparentid"
0x89fdb  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::IsAttributeNull(string)
0x89fe0  brtrue.s loc_89FF5
0x89fe2  ldloc.s  6
0x89fe4  ldstr    aDependentcompo_2// "dependentcomponentparentid"
0x89fe9  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x89fee  unbox.any [mscorlib]System.Guid
0x89ff3  br.s     loc_89FFA
0x89ff5  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x89ffa  stloc.s  0xA
0x89ffc  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x8a001  ldstr    a012_3// "{0}-{1}-{2}"
0x8a006  ldc.i4.3
0x8a007  newarr   [mscorlib]System.Object
0x8a00c  dup
0x8a00d  ldc.i4.0
0x8a00e  ldloc.s  8
0x8a010  box      [mscorlib]System.Int32
0x8a015  stelem.ref
0x8a016  dup
0x8a017  ldc.i4.1
0x8a018  ldloc.s  9
0x8a01a  box      [mscorlib]System.Guid
0x8a01f  stelem.ref
0x8a020  dup
0x8a021  ldc.i4.2
0x8a022  ldloc.s  0xA
0x8a024  box      [mscorlib]System.Guid
0x8a029  stelem.ref
0x8a02a  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x8a02f  stloc.s  0xB
0x8a031  ldloc.1
0x8a032  ldloc.s  0xB
0x8a034  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.ComponentInfo>::ContainsKey(var<u1>)
0x8a039  brtrue.s loc_8A055
0x8a03b  ldloc.1
0x8a03c  ldloc.s  0xB
0x8a03e  ldloc.s  8
0x8a040  ldloc.s  9
0x8a042  ldloc.s  0xA
0x8a044  ldloc.s  4
0x8a046  dup
0x8a047  ldc.i4.1
0x8a048  add
0x8a049  stloc.s  4
0x8a04b  newobj   instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.ComponentInfo::.ctor(int32, valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid, int32)
0x8a050  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.ComponentInfo>::Add(var<u1>, !!T0)
0x8a055  ldloc.s  5
0x8a057  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x8a05c  brtrue   loc_89E54
0x8a061  leave.s  loc_8A078
0x8a063  ldloc.s  5
0x8a065  isinst   [mscorlib]System.IDisposable
0x8a06a  stloc.s  0xD
0x8a06c  ldloc.s  0xD
0x8a06e  brfalse.s loc_8A077
0x8a070  ldloc.s  0xD
0x8a072  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x8a077  endfinally
0x8a078  ldloc.1
0x8a079  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2/ValueCollection<var<u1>, !!T0> class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.ComponentInfo>::get_Values()
0x8a07e  callvirt instance valuetype [mscorlib]System.Collections.Generic.Dictionary`2/ValueCollection/Enumerator<var<u1>, !!T0> class [mscorlib]System.Collections.Generic.Dictionary`2/ValueCollection<string, class [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.ComponentInfo>::GetEnumerator()
0x8a083  stloc.s  0xE
0x8a085  br.s     loc_8A0DA
0x8a087  ldloca.s 0xE
0x8a089  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.Dictionary`2/ValueCollection/Enumerator<string, class [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.ComponentInfo>::get_Current()
0x8a08e  stloc.s  0xF
0x8a090  ldloc.s  0xF
0x8a092  callvirt instance int32 [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.ComponentInfo::get_ComponentType()
0x8a097  ldc.i4.s 0x42
0x8a099  bne.un.s loc_8A0C1
0x8a09b  ldloc.s  0xF
0x8a09d  callvirt instance int32 [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.ComponentInfo::get_ComponentType()
0x8a0a2  call     class [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.IImportExportDependencyHelper [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.ImportExportDependencyHelperFactory::RetrieveHelper(int32)
0x8a0a7  castclass Microsoft.Crm.Tools.ImportExportPublish.CustomControlsImportExportDependencyHelper
0x8a0ac  ldloc.s  0xF
0x8a0ae  ldarg.0
0x8a0af  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Tools.ImportExportPublish.SolutionHandler::_solutionId
0x8a0b4  ldarg.0
0x8a0b5  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.SolutionHandler::_context
0x8a0ba  callvirt instance void Microsoft.Crm.Tools.ImportExportPublish.CustomControlsImportExportDependencyHelper::FillComponentInfoForExport(class [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.ComponentInfo component, valuetype [mscorlib]System.Guid exportingSolutionId, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x8a0bf  br.s     loc_8A0DA
0x8a0c1  ldloc.s  0xF
0x8a0c3  callvirt instance int32 [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.ComponentInfo::get_ComponentType()
0x8a0c8  call     class [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.IImportExportDependencyHelper [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.ImportExportDependencyHelperFactory::RetrieveHelper(int32)
0x8a0cd  ldloc.s  0xF
0x8a0cf  ldarg.0
0x8a0d0  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.SolutionHandler::_context
0x8a0d5  callvirt instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.IImportExportDependencyHelper::FillComponentInfoForExport(class [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.ComponentInfo, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x8a0da  ldloca.s 0xE
0x8a0dc  call     instance bool valuetype [mscorlib]System.Collections.Generic.Dictionary`2/ValueCollection/Enumerator<string, class [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.ComponentInfo>::MoveNext()
0x8a0e1  brtrue.s loc_8A087
0x8a0e3  leave.s  loc_8A0F3
0x8a0e5  ldloca.s 0xE
0x8a0e7  constrained. valuetype [mscorlib]System.Collections.Generic.Dictionary`2/ValueCollection/Enumerator<string, class [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.ComponentInfo>
0x8a0ed  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x8a0f2  endfinally
0x8a0f3  ldloc.3
0x8a0f4  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.CollectionBase::GetEnumerator()
0x8a0f9  stloc.s  5
0x8a0fb  br       loc_8A543
0x8a100  ldloc.s  5
0x8a102  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x8a107  castclass [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity
0x8a10c  stloc.s  0x10
0x8a10e  ldloc.s  0x10
0x8a110  ldstr    aRequiredcompon_2// "requiredcomponentbasesolutionid"
0x8a115  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x8a11a  unbox.any [mscorlib]System.Guid
0x8a11f  stloc.s  0x11
0x8a121  ldloc.s  0x11
0x8a123  ldsfld   valuetype [mscorlib]System.Guid [Microsoft.Crm.Constants]Microsoft.Crm.SolutionConstants::SystemSolutionId
0x8a128  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x8a12d  brtrue   loc_8A543
0x8a132  ldloc.s  0x10
0x8a134  ldstr    aRequiredcompon_0// "requiredcomponenttype"
0x8a139  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x8a13e  unbox.any [mscorlib]System.Int32
  ... truncated ...
```
