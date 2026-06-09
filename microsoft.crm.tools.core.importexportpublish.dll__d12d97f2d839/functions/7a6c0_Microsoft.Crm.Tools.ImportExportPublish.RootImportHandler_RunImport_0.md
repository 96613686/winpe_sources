# Microsoft.Crm.Tools.ImportExportPublish.RootImportHandler::RunImport_0

- ea: `0x7a6c0`
- end: `0x7ac9e`
- name: `Microsoft.Crm.Tools.ImportExportPublish.RootImportHandler::RunImport_0`
- size: `1502`
- prototype: ``
- caller_count: `1`
- callee_count: `23`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x680f0`

## callees

- `0x34d40`
- `0x66b60`
- `0x66c00`
- `0x686f0`
- `0x77cb0`
- `0x77cd0`
- `0x77ce0`
- `0x77d00`
- `0x784a0`
- `0x792c0`
- `0x79750`
- `0x7a310`
- `0x7a6c0`
- `0x7aca0`
- `0x7acf0`
- `0x7ad90`
- `0x7ae60`
- `0x7c580`
- `0x7c5d0`
- `0x7c630`
- `0x97630`
- `0x97670`
- `0x97690`

## string_xrefs

- `0x7a996`: `ImportExportXml/SolutionManifest/UniqueName`
- `0x7a9ad`: `msdynce_Service`
- `0x7a9d0`: `UpdateClientRibbonMetadataInSolutionFlow`
- `0x7aa0d`: `CommitTransaction`
- `0x7ab50`: `Microsoft.Crm.Tools.ImportExportPublish.FlushAllCachesAfterImportCompletes`
- `0x7a981`: `/importexportxml/dependencies/dependency`
- `0x7aa1e`: `Import_BEGIN_{0}.RunImport().CommitTransaction`
- `0x7aa7e`: `Microsoft.Crm.Tools.ImportExportPublish.CommitTransactionProcessDependencies`
- `0x7aab2`: `Import_END_{0}.RunImport().CommitTransaction`
- `0x7aae4`: `UpdateProgress`

## pseudocode

```c

```

## disassembly

```asm
0x7a6c0  newobj   instance void <>c__DisplayClass99_0::.ctor()
0x7a6c5  stloc.0
0x7a6c6  ldloc.0
0x7a6c7  ldarg.0
0x7a6c8  stfld    class Microsoft.Crm.Tools.ImportExportPublish.RootImportHandler <>c__DisplayClass99_0::<>4__this
0x7a6cd  ldloc.0
0x7a6ce  ldarg.1
0x7a6cf  stfld    string[] <>c__DisplayClass99_0::ImportEntities
0x7a6d4  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x7a6d9  ldstr    aImportBegin0Ru_1// "Import_BEGIN_{0}.RunImport()"
0x7a6de  ldc.i4.1
0x7a6df  newarr   [mscorlib]System.Object
0x7a6e4  dup
0x7a6e5  ldc.i4.0
0x7a6e6  ldarg.0
0x7a6e7  stelem.ref
0x7a6e8  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x7a6ed  call     void [Microsoft.Crm.Core]Microsoft.Crm.PerfControl::LogPerf(string)
0x7a6f2  newobj   instance void <>c__DisplayClass99_1::.ctor()
0x7a6f7  stloc.1
0x7a6f8  ldloc.1
0x7a6f9  ldloc.0
0x7a6fa  stfld    class <>c__DisplayClass99_0 <>c__DisplayClass99_1::CS$<>8__locals1
0x7a6ff  ldloc.1
0x7a700  ldstr    aRootimporthand_0// "RootImportHandler.RunImport(string[] Im"...
0x7a705  ldc.i4.1
0x7a706  call     class [Microsoft.Crm.Core]Microsoft.Crm.CounterList [Microsoft.Crm.Core]Microsoft.Crm.CounterList::CreateAndStart(string, bool)
0x7a70b  stfld    class [Microsoft.Crm.Core]Microsoft.Crm.CounterList <>c__DisplayClass99_1::listCounters
0x7a710  newobj   instance void <>c__DisplayClass99_2::.ctor()
0x7a715  stloc.2
0x7a716  ldloc.2
0x7a717  ldloc.1
0x7a718  stfld    class <>c__DisplayClass99_1 <>c__DisplayClass99_2::CS$<>8__locals2
0x7a71d  ldloc.2
0x7a71e  ldfld    class <>c__DisplayClass99_1 <>c__DisplayClass99_2::CS$<>8__locals2
0x7a723  ldfld    class [Microsoft.Crm.Core]Microsoft.Crm.CounterList <>c__DisplayClass99_1::listCounters
0x7a728  ldc.i4.2
0x7a729  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.CounterList::set_LevelOfTrace(valuetype [System]System.Diagnostics.TraceLevel)
0x7a72e  ldarg.0
0x7a72f  ldloc.2
0x7a730  ldfld    class <>c__DisplayClass99_1 <>c__DisplayClass99_2::CS$<>8__locals2
0x7a735  ldfld    class <>c__DisplayClass99_0 <>c__DisplayClass99_1::CS$<>8__locals1
0x7a73a  ldfld    string[] <>c__DisplayClass99_0::ImportEntities
0x7a73f  ldloc.2
0x7a740  ldfld    class <>c__DisplayClass99_1 <>c__DisplayClass99_2::CS$<>8__locals2
0x7a745  ldfld    class [Microsoft.Crm.Core]Microsoft.Crm.CounterList <>c__DisplayClass99_1::listCounters
0x7a74a  call     instance class [mscorlib]System.Collections.Hashtable Microsoft.Crm.Tools.ImportExportPublish.RootImportHandler::InitializeImportEntities(string[] ImportEntities, class [Microsoft.Crm.Core]Microsoft.Crm.CounterList listCounters)
0x7a74f  stloc.3
0x7a750  ldnull
0x7a751  stloc.s  4
0x7a753  ldnull
0x7a754  stloc.s  5
0x7a756  ldarg.0
0x7a757  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.RootImportHandler::context
0x7a75c  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_Connection()
0x7a761  call     int32 Microsoft.Crm.Tools.ImportExportPublish.RootImportHandler::get_Timeout()
0x7a766  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::set_TimeOut(int32)
0x7a76b  ldloc.2
0x7a76c  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x7a771  stfld    valuetype [mscorlib]System.Guid <>c__DisplayClass99_2::solutionId
0x7a776  ldloc.2
0x7a777  ldarg.0
0x7a778  ldfld    class [mscorlib]System.Version Microsoft.Crm.Tools.ImportExportPublish.RootImportHandler::existingDatabaseVersion
0x7a77d  ldnull
0x7a77e  call     bool [mscorlib]System.Version::op_Inequality(class [mscorlib]System.Version, class [mscorlib]System.Version)
0x7a783  brtrue.s loc_7A78C
0x7a785  ldsfld   string [mscorlib]System.String::Empty
0x7a78a  br.s     loc_7A797
0x7a78c  ldarg.0
0x7a78d  ldfld    class [mscorlib]System.Version Microsoft.Crm.Tools.ImportExportPublish.RootImportHandler::existingDatabaseVersion
0x7a792  callvirt instance string [mscorlib]System.Object::ToString()
0x7a797  stfld    string <>c__DisplayClass99_2::existingDBVersion
0x7a79c  ldloc.2
0x7a79d  ldarg.0
0x7a79e  ldfld    class Microsoft.Crm.Tools.ImportExportPublish.ImportXml Microsoft.Crm.Tools.ImportExportPublish.RootImportHandler::parent
0x7a7a3  callvirt instance class [mscorlib]System.Version Microsoft.Crm.Tools.ImportExportPublish.ImportXml::get_CurrentVersion()
0x7a7a8  ldnull
0x7a7a9  call     bool [mscorlib]System.Version::op_Inequality(class [mscorlib]System.Version, class [mscorlib]System.Version)
0x7a7ae  brtrue.s loc_7A7B7
0x7a7b0  ldsfld   string [mscorlib]System.String::Empty
0x7a7b5  br.s     loc_7A7C7
0x7a7b7  ldarg.0
0x7a7b8  ldfld    class Microsoft.Crm.Tools.ImportExportPublish.ImportXml Microsoft.Crm.Tools.ImportExportPublish.RootImportHandler::parent
0x7a7bd  callvirt instance class [mscorlib]System.Version Microsoft.Crm.Tools.ImportExportPublish.ImportXml::get_CurrentVersion()
0x7a7c2  callvirt instance string [mscorlib]System.Object::ToString()
0x7a7c7  stfld    string <>c__DisplayClass99_2::currentVersion
0x7a7cc  ldarg.0
0x7a7cd  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.RootImportHandler::context
0x7a7d2  ldc.i4.1
0x7a7d3  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.AutoAddRootsContextModifier::.ctor(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext, valuetype [Microsoft.Crm.Core]Microsoft.Crm.AddRootsOption)
0x7a7d8  stloc.s  6
0x7a7da  ldarg.0
0x7a7db  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.RootImportHandler::context
0x7a7e0  ldstr    aShoulddeferrep// "ShouldDeferReportViewGeneration"
0x7a7e5  ldarg.0
0x7a7e6  call     instance bool Microsoft.Crm.Tools.ImportExportPublish.RootImportHandler::get_IsInternalSolution()
0x7a7eb  box      [mscorlib]System.Boolean
0x7a7f0  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.SetVariableInContextModifier::.ctor(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext, string, object)
0x7a7f5  stloc.s  7
0x7a7f7  ldarg.0
0x7a7f8  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.RootImportHandler::context
0x7a7fd  ldstr    aIsfirstpartyso// "isfirstpartysolutioncontext"
0x7a802  ldarg.0
0x7a803  call     instance bool Microsoft.Crm.Tools.ImportExportPublish.RootImportHandler::get_IsFirstPartySolution()
0x7a808  box      [mscorlib]System.Boolean
0x7a80d  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.SetVariableInContextModifier::.ctor(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext, string, object)
0x7a812  stloc.s  8
0x7a814  ldarg.0
0x7a815  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.RootImportHandler::context
0x7a81a  ldstr    aImportData// "Import_Data"
0x7a81f  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::.ctor()
0x7a824  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.SetVariableInContextModifier::.ctor(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext, string, object)
0x7a829  stloc.s  9
0x7a82b  ldarg.0
0x7a82c  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.RootImportHandler::context
0x7a831  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_SqlContext()
0x7a836  newobj   instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.CustomizationSqlLockManager::.ctor(class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext)
0x7a83b  stloc.s  0xA
0x7a83d  ldarg.0
0x7a83e  call     instance bool Microsoft.Crm.Tools.ImportExportPublish.RootImportHandler::get_IsInternalSolution()
0x7a843  brfalse.s loc_7A851
0x7a845  ldarg.0
0x7a846  ldarg.0
0x7a847  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.RootImportHandler::context
0x7a84c  call     instance void Microsoft.Crm.Tools.ImportExportPublish.RootImportHandler::GetOverridesForSolutions(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x7a851  ldarg.0
0x7a852  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.RootImportHandler::context
0x7a857  ldarg.0
0x7a858  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.RootImportHandler::context
0x7a85d  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x7a862  ldc.i4.1
0x7a863  ldc.i4.1
0x7a864  newobj   instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.SystemFormService::.ctor()
0x7a869  newobj   instance void [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataHelper::.ctor(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext, valuetype [mscorlib]System.Guid, bool, bool, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.IBusinessProcessObject)
0x7a86e  stloc.s  0xB
0x7a870  ldloc.s  0xB
0x7a872  ldc.i4.0
0x7a873  callvirt instance void [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataHelper::set_ProcessFK(bool)
0x7a878  ldloc.s  0xB
0x7a87a  ldarg.0
0x7a87b  call     instance bool Microsoft.Crm.Tools.ImportExportPublish.RootImportHandler::get_IsInternalSolution()
0x7a880  callvirt instance void [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataHelper::set_IgnoreAttributeLengthDecreases(bool)
0x7a885  ldarg.0
0x7a886  ldloc.2
0x7a887  ldflda   valuetype [mscorlib]System.Guid <>c__DisplayClass99_2::solutionId
0x7a88c  ldloc.2
0x7a88d  ldflda   valuetype [Microsoft.Crm.Core]Microsoft.Crm.SolutionOperationContext <>c__DisplayClass99_2::solutionOperationContext
0x7a892  ldloca.s 0xC
0x7a894  call     instance void Microsoft.Crm.Tools.ImportExportPublish.RootImportHandler::GetSolutionIdAndOperationContext([out] valuetype [mscorlib]System.Guid& solutionId, [out] valuetype [Microsoft.Crm.Core]Microsoft.Crm.SolutionOperationContext& solutionOperationContext, [out] valuetype [Microsoft.Crm.Core]Microsoft.Crm.SolutionImportContext& solutionImportContext)
0x7a899  ldarg.0
0x7a89a  call     instance bool Microsoft.Crm.Tools.ImportExportPublish.RootImportHandler::get_IsInternalSolution()
0x7a89f  brfalse.s loc_7A8D1
0x7a8a1  ldarg.0
0x7a8a2  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.RootImportHandler::context
0x7a8a7  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IPluginExecutionContext [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_PluginContext()
0x7a8ac  brfalse.s loc_7A8D1
0x7a8ae  ldarg.0
0x7a8af  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.RootImportHandler::context
0x7a8b4  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IPluginExecutionContext [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_PluginContext()
0x7a8b9  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext::get_InputParameters()
0x7a8be  ldsfld   string [Microsoft.Crm.ObjectModel]Microsoft.Crm.Caching.SDKRequestParametersConstants::InternalUpgradeImportFlag
0x7a8c3  callvirt instance bool class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::ContainsKey(var<u1>)
0x7a8c8  brfalse.s loc_7A8D1
0x7a8ca  ldloc.2
0x7a8cb  ldc.i4.8
0x7a8cc  stfld    valuetype [Microsoft.Crm.Core]Microsoft.Crm.SolutionOperationContext <>c__DisplayClass99_2::solutionOperationContext
0x7a8d1  ldarg.0
0x7a8d2  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.RootImportHandler::context
0x7a8d7  ldloc.2
0x7a8d8  ldfld    valuetype [Microsoft.Crm.Core]Microsoft.Crm.SolutionOperationContext <>c__DisplayClass99_2::solutionOperationContext
0x7a8dd  ldloc.2
0x7a8de  ldfld    valuetype [mscorlib]System.Guid <>c__DisplayClass99_2::solutionId
0x7a8e3  ldc.i4.0
0x7a8e4  ldloc.s  0xC
0x7a8e6  ldarg.0
0x7a8e7  call     instance bool Microsoft.Crm.Tools.ImportExportPublish.RootImportHandler::get_IsInternalSolution()
0x7a8ec  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.AutoSolutionOperationContextModifier::.ctor(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext, valuetype [Microsoft.Crm.Core]Microsoft.Crm.SolutionOperationContext, valuetype [mscorlib]System.Guid, bool, valuetype [Microsoft.Crm.Core]Microsoft.Crm.SolutionImportContext, bool)
0x7a8f1  stloc.s  0xE
0x7a8f3  ldarg.0
0x7a8f4  ldloc.2
0x7a8f5  ldfld    valuetype [mscorlib]System.Guid <>c__DisplayClass99_2::solutionId
0x7a8fa  ldloc.s  0xB
0x7a8fc  ldloc.2
0x7a8fd  ldfld    class <>c__DisplayClass99_1 <>c__DisplayClass99_2::CS$<>8__locals2
0x7a902  ldfld    class [Microsoft.Crm.Core]Microsoft.Crm.CounterList <>c__DisplayClass99_1::listCounters
0x7a907  ldloc.s  0xA
0x7a909  call     instance void Microsoft.Crm.Tools.ImportExportPublish.RootImportHandler::InitializeImportHelpers(valuetype [mscorlib]System.Guid solutionId, class [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataHelper metadataHelper, class [Microsoft.Crm.Core]Microsoft.Crm.CounterList listCounters, class [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.ICustomizationSqlLockManager lockManager)
0x7a90e  ldarg.0
0x7a90f  ldloc.2
0x7a910  ldfld    class <>c__DisplayClass99_1 <>c__DisplayClass99_2::CS$<>8__locals2
0x7a915  ldfld    class [Microsoft.Crm.Core]Microsoft.Crm.CounterList <>c__DisplayClass99_1::listCounters
0x7a91a  call     instance void Microsoft.Crm.Tools.ImportExportPublish.RootImportHandler::CheckLanguages(class [Microsoft.Crm.Core]Microsoft.Crm.CounterList listCounters)
0x7a91f  ldarg.0
0x7a920  ldloc.2
0x7a921  ldfld    class <>c__DisplayClass99_1 <>c__DisplayClass99_2::CS$<>8__locals2
0x7a926  ldfld    class <>c__DisplayClass99_0 <>c__DisplayClass99_1::CS$<>8__locals1
0x7a92b  ldfld    string[] <>c__DisplayClass99_0::ImportEntities
0x7a930  ldloc.3
0x7a931  ldloca.s 4
0x7a933  ldloca.s 5
0x7a935  ldloc.2
0x7a936  ldfld    class <>c__DisplayClass99_1 <>c__DisplayClass99_2::CS$<>8__locals2
0x7a93b  ldfld    class [Microsoft.Crm.Core]Microsoft.Crm.CounterList <>c__DisplayClass99_1::listCounters
0x7a940  call     instance void Microsoft.Crm.Tools.ImportExportPublish.RootImportHandler::ProcessHandlers(string[] ImportEntities, class [mscorlib]System.Collections.Hashtable ht, string& curPath, class Microsoft.Crm.Tools.ImportExportPublish.ImportHandler& ihForCurrentPath, class [Microsoft.Crm.Core]Microsoft.Crm.CounterList listCounters)
0x7a945  ldarg.0
0x7a946  call     instance bool Microsoft.Crm.Tools.ImportExportPublish.RootImportHandler::get_IsSolutionInternal()
0x7a94b  brtrue.s loc_7A962
0x7a94d  ldarg.0
0x7a94e  ldloc.s  4
0x7a950  ldloc.2
0x7a951  ldfld    class <>c__DisplayClass99_1 <>c__DisplayClass99_2::CS$<>8__locals2
0x7a956  ldfld    class [Microsoft.Crm.Core]Microsoft.Crm.CounterList <>c__DisplayClass99_1::listCounters
0x7a95b  call     instance string Microsoft.Crm.Tools.ImportExportPublish.RootImportHandler::ProcessDependencies(string curPath, class [Microsoft.Crm.Core]Microsoft.Crm.CounterList listCounters)
0x7a960  stloc.s  4
0x7a962  leave.s  loc_7A970
0x7a964  ldloc.s  0xE
0x7a966  brfalse.s loc_7A96F
0x7a968  ldloc.s  0xE
0x7a96a  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x7a96f  endfinally
0x7a970  ldarg.0
0x7a971  ldloc.2
0x7a972  ldfld    class <>c__DisplayClass99_1 <>c__DisplayClass99_2::CS$<>8__locals2
0x7a977  ldfld    class [Microsoft.Crm.Core]Microsoft.Crm.CounterList <>c__DisplayClass99_1::listCounters
0x7a97c  call     instance void Microsoft.Crm.Tools.ImportExportPublish.RootImportHandler::UpdateCustomEntityFeatureStateIfNecessary(class [Microsoft.Crm.Core]Microsoft.Crm.CounterList listCounters)
0x7a981  ldstr    aImportexportxm_195// "/importexportxml/dependencies/dependenc"...
0x7a986  stloc.s  4
0x7a988  ldarg.0
0x7a989  call     instance bool Microsoft.Crm.Tools.ImportExportPublish.RootImportHandler::get_IsInternalSolution()
0x7a98e  brfalse.s loc_7A9CA
0x7a990  ldarg.0
0x7a991  ldfld    class [System.Xml]System.Xml.XmlDocument Microsoft.Crm.Tools.ImportExportPublish.RootImportHandler::importDocument
0x7a996  ldstr    aImportexportxm_1// "ImportExportXml/SolutionManifest/Unique"...
0x7a99b  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x7a9a0  stloc.s  0xF
0x7a9a2  ldloc.s  0xF
0x7a9a4  brfalse.s loc_7A9CA
0x7a9a6  ldloc.s  0xF
0x7a9a8  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x7a9ad  ldstr    aMsdynceService// "msdynce_Service"
0x7a9b2  ldc.i4.5
0x7a9b3  call     bool [mscorlib]System.String::Equals(string, string, valuetype [mscorlib]System.StringComparison)
0x7a9b8  brfalse.s loc_7A9CA
0x7a9ba  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.UserDataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.UserDataCache::Instance()
0x7a9bf  ldarg.0
0x7a9c0  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.RootImportHandler::context
0x7a9c5  callvirt instance void class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.CrmMultiOrgCacheBase`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser>::Flush(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x7a9ca  ldarg.0
0x7a9cb  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.RootImportHandler::context
0x7a9d0  ldstr    aUpdateclientri// "UpdateClientRibbonMetadataInSolutionFlo"...
0x7a9d5  ldc.i4.1
0x7a9d6  box      [mscorlib]System.Boolean
0x7a9db  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.SetVariableInContextModifier::.ctor(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext, string, object)
0x7a9e0  stloc.s  0x10
0x7a9e2  ldarg.0
0x7a9e3  ldloc.2
0x7a9e4  ldfld    string <>c__DisplayClass99_2::currentVersion
0x7a9e9  ldloc.2
0x7a9ea  ldfld    string <>c__DisplayClass99_2::existingDBVersion
0x7a9ef  call     instance void Microsoft.Crm.Tools.ImportExportPublish.RootImportHandler::UpdateClientRibbonMetadata(string currentVersion, string existingDBVersion)
0x7a9f4  leave.s  loc_7AA02
0x7a9f6  ldloc.s  0x10
0x7a9f8  brfalse.s loc_7AA01
0x7a9fa  ldloc.s  0x10
0x7a9fc  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x7aa01  endfinally
0x7aa02  ldloc.2
0x7aa03  ldfld    class <>c__DisplayClass99_1 <>c__DisplayClass99_2::CS$<>8__locals2
0x7aa08  ldfld    class [Microsoft.Crm.Core]Microsoft.Crm.CounterList <>c__DisplayClass99_1::listCounters
0x7aa0d  ldstr    aCommittransact// "CommitTransaction"
0x7aa12  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.Counter [Microsoft.Crm.Core]Microsoft.Crm.CounterList::InitStepCounter(string)
0x7aa17  stloc.s  0x11
0x7aa19  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x7aa1e  ldstr    aImportBegin0Ru_2// "Import_BEGIN_{0}.RunImport().CommitTran"...
0x7aa23  ldc.i4.1
0x7aa24  newarr   [mscorlib]System.Object
0x7aa29  dup
0x7aa2a  ldc.i4.0
0x7aa2b  ldarg.0
0x7aa2c  stelem.ref
0x7aa2d  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x7aa32  call     void [Microsoft.Crm.Core]Microsoft.Crm.PerfControl::LogPerf(string)
0x7aa37  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Core.Telemetry.EventSources.TelemetryExecutionToken::.ctor()
0x7aa3c  stloc.s  0x12
0x7aa3e  ldsfld   class [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.ILogger Microsoft.Crm.Tools.ImportExportPublish.RootImportHandler::Logger
0x7aa43  call     var<u1> class [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmTelemetrySingletonActivityType`1<class [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.SolutionImportCommitTransactionActivityType>::get_Instance()
0x7aa48  ldloc.2
0x7aa49  ldfld    class <>c__DisplayClass99_1 <>c__DisplayClass99_2::CS$<>8__locals2
0x7aa4e  ldfld    class <>c__DisplayClass99_0 <>c__DisplayClass99_1::CS$<>8__locals1
0x7aa53  ldftn    instance void <>c__DisplayClass99_0::<RunImport>b__4()
0x7aa59  newobj   instance void [mscorlib]System.Action::.ctor(object, native int)
0x7aa5e  call     void [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmTelemetryExtensions::Execute(class [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.ILogger, class [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmTelemetryActivityType, class [mscorlib]System.Action)
0x7aa63  call     class [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.SolutionTelemetryEvents [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.SolutionTelemetryEvents::get_Instance()
0x7aa68  ldarg.0
0x7aa69  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.RootImportHandler::context
0x7aa6e  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x7aa73  call     string [Microsoft.Crm.Core]Microsoft.Crm.Core.Telemetry.CrmTelemetryHelper::get_ApplicationVersion()
0x7aa78  ldloc.2
0x7aa79  ldfld    string <>c__DisplayClass99_2::currentVersion
0x7aa7e  ldstr    aMicrosoftCrmTo_11// "Microsoft.Crm.Tools.ImportExportPublish"...
  ... truncated ...
```
