# Microsoft.Crm.Tools.ImportExportPublish.RootImportHandler::RunImport

- ea: `0x793b0`
- end: `0x79750`
- name: `Microsoft.Crm.Tools.ImportExportPublish.RootImportHandler::RunImport`
- size: `928`
- prototype: ``
- caller_count: `1`
- callee_count: `17`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x67560`

## callees

- `0x66b60`
- `0x66c00`
- `0x77cb0`
- `0x77cd0`
- `0x784a0`
- `0x793b0`
- `0x79750`
- `0x79f20`
- `0x79fa0`
- `0x7a020`
- `0x7a0d0`
- `0x7afe0`
- `0x7b700`
- `0x7c580`
- `0x7c630`
- `0x975c0`
- `0x975e0`

## string_xrefs

- `0x7957b`: `UpdateClientRibbonMetadataInSolutionFlow`
- `0x795af`: `CommitTransaction`
- `0x795c0`: `Import_BEGIN_{0}.RunImport(setup).CommitTransactionSetup`
- `0x79611`: `Microsoft.Crm.Tools.ImportExportPublish.CommitTransaction`
- `0x79640`: `Import_END_{0}.RunImport(setup).CommitTransaction`
- `0x796a0`: `Microsoft.Crm.Tools.ImportExportPublish.FlushAllCachesAfterImportCompletes`

## pseudocode

```c

```

## disassembly

```asm
0x793b0  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x793b5  ldstr    aImportBegin0Ru// "Import_BEGIN_{0}.RunImport(setup)"
0x793ba  ldc.i4.1
0x793bb  newarr   [mscorlib]System.Object
0x793c0  dup
0x793c1  ldc.i4.0
0x793c2  ldarg.0
0x793c3  stelem.ref
0x793c4  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x793c9  call     void [Microsoft.Crm.Core]Microsoft.Crm.PerfControl::LogPerf(string)
0x793ce  newobj   instance void <>c__DisplayClass81_0::.ctor()
0x793d3  stloc.0
0x793d4  ldloc.0
0x793d5  ldarg.0
0x793d6  stfld    class Microsoft.Crm.Tools.ImportExportPublish.RootImportHandler <>c__DisplayClass81_0::<>4__this
0x793db  ldloc.0
0x793dc  ldstr    aRootimporthand// "RootImportHandler.RunImport"
0x793e1  ldc.r8   60000.0
0x793ea  ldc.i4.1
0x793eb  call     class [Microsoft.Crm.Core]Microsoft.Crm.CounterList [Microsoft.Crm.Core]Microsoft.Crm.CounterList::CreateAndStart(string, float64, bool)
0x793f0  stfld    class [Microsoft.Crm.Core]Microsoft.Crm.CounterList <>c__DisplayClass81_0::listCounters
0x793f5  ldloc.0
0x793f6  ldfld    class [Microsoft.Crm.Core]Microsoft.Crm.CounterList <>c__DisplayClass81_0::listCounters
0x793fb  ldc.i4.2
0x793fc  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.CounterList::set_LevelOfTrace(valuetype [System]System.Diagnostics.TraceLevel)
0x79401  ldarg.0
0x79402  ldloc.0
0x79403  ldfld    class [Microsoft.Crm.Core]Microsoft.Crm.CounterList <>c__DisplayClass81_0::listCounters
0x79408  call     instance void Microsoft.Crm.Tools.ImportExportPublish.RootImportHandler::ValidateImportDocument(class [Microsoft.Crm.Core]Microsoft.Crm.CounterList listCounters)
0x7940d  ldarg.0
0x7940e  ldloc.0
0x7940f  ldfld    class [Microsoft.Crm.Core]Microsoft.Crm.CounterList <>c__DisplayClass81_0::listCounters
0x79414  call     instance void Microsoft.Crm.Tools.ImportExportPublish.RootImportHandler::InitializeLabelHelper(class [Microsoft.Crm.Core]Microsoft.Crm.CounterList cl)
0x79419  ldarg.0
0x7941a  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.RootImportHandler::context
0x7941f  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_Connection()
0x79424  call     int32 Microsoft.Crm.Tools.ImportExportPublish.RootImportHandler::get_Timeout()
0x79429  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::set_TimeOut(int32)
0x7942e  ldarg.0
0x7942f  ldfld    class [mscorlib]System.Version Microsoft.Crm.Tools.ImportExportPublish.RootImportHandler::existingDatabaseVersion
0x79434  ldnull
0x79435  call     bool [mscorlib]System.Version::op_Inequality(class [mscorlib]System.Version, class [mscorlib]System.Version)
0x7943a  brtrue.s loc_79443
0x7943c  ldsfld   string [mscorlib]System.String::Empty
0x79441  br.s     loc_7944E
0x79443  ldarg.0
0x79444  ldfld    class [mscorlib]System.Version Microsoft.Crm.Tools.ImportExportPublish.RootImportHandler::existingDatabaseVersion
0x79449  callvirt instance string [mscorlib]System.Object::ToString()
0x7944e  stloc.1
0x7944f  ldarg.0
0x79450  ldfld    class Microsoft.Crm.Tools.ImportExportPublish.ImportXml Microsoft.Crm.Tools.ImportExportPublish.RootImportHandler::parent
0x79455  callvirt instance class [mscorlib]System.Version Microsoft.Crm.Tools.ImportExportPublish.ImportXml::get_CurrentVersion()
0x7945a  ldnull
0x7945b  call     bool [mscorlib]System.Version::op_Inequality(class [mscorlib]System.Version, class [mscorlib]System.Version)
0x79460  brtrue.s loc_79469
0x79462  ldsfld   string [mscorlib]System.String::Empty
0x79467  br.s     loc_79479
0x79469  ldarg.0
0x7946a  ldfld    class Microsoft.Crm.Tools.ImportExportPublish.ImportXml Microsoft.Crm.Tools.ImportExportPublish.RootImportHandler::parent
0x7946f  callvirt instance class [mscorlib]System.Version Microsoft.Crm.Tools.ImportExportPublish.ImportXml::get_CurrentVersion()
0x79474  callvirt instance string [mscorlib]System.Object::ToString()
0x79479  stloc.2
0x7947a  ldarg.0
0x7947b  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.RootImportHandler::context
0x79480  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_SqlContext()
0x79485  newobj   instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.CustomizationSqlLockManager::.ctor(class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext)
0x7948a  stloc.3
0x7948b  newobj   instance void <>c__DisplayClass81_1::.ctor()
0x79490  stloc.s  4
0x79492  ldloc.s  4
0x79494  ldloc.0
0x79495  stfld    class <>c__DisplayClass81_0 <>c__DisplayClass81_1::CS$<>8__locals1
0x7949a  ldarg.0
0x7949b  ldloc.s  4
0x7949d  ldfld    class <>c__DisplayClass81_0 <>c__DisplayClass81_1::CS$<>8__locals1
0x794a2  ldfld    class [Microsoft.Crm.Core]Microsoft.Crm.CounterList <>c__DisplayClass81_0::listCounters
0x794a7  ldloca.s 5
0x794a9  ldloca.s 6
0x794ab  ldloc.s  4
0x794ad  ldflda   valuetype [mscorlib]System.Guid <>c__DisplayClass81_1::solutionId
0x794b2  call     instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.AutoOperationContextModifier Microsoft.Crm.Tools.ImportExportPublish.RootImportHandler::InitContext(class [Microsoft.Crm.Core]Microsoft.Crm.CounterList listCounters, [out] class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.SystemUserContext& systemUserContext, [out] class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.AutoDisableDependencyCalculationContextModifier& disableDependencyContextModifier, [out] valuetype [mscorlib]System.Guid& solutionId)
0x794b7  stloc.s  7
0x794b9  ldarg.0
0x794ba  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.RootImportHandler::context
0x794bf  ldarg.0
0x794c0  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.RootImportHandler::context
0x794c5  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x794ca  ldc.i4.1
0x794cb  ldc.i4.1
0x794cc  newobj   instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.SystemFormService::.ctor()
0x794d1  newobj   instance void [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataHelper::.ctor(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext, valuetype [mscorlib]System.Guid, bool, bool, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.IBusinessProcessObject)
0x794d6  stloc.s  8
0x794d8  ldloc.s  8
0x794da  ldc.i4.0
0x794db  callvirt instance void [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataHelper::set_ProcessFK(bool)
0x794e0  ldloc.s  8
0x794e2  ldarg.0
0x794e3  call     instance bool Microsoft.Crm.Tools.ImportExportPublish.RootImportHandler::get_IsInternalSolution()
0x794e8  callvirt instance void [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataHelper::set_IgnoreAttributeLengthDecreases(bool)
0x794ed  ldarg.0
0x794ee  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x794f3  ldloc.s  8
0x794f5  ldloc.s  4
0x794f7  ldfld    class <>c__DisplayClass81_0 <>c__DisplayClass81_1::CS$<>8__locals1
0x794fc  ldfld    class [Microsoft.Crm.Core]Microsoft.Crm.CounterList <>c__DisplayClass81_0::listCounters
0x79501  ldloc.3
0x79502  call     instance void Microsoft.Crm.Tools.ImportExportPublish.RootImportHandler::InitializeImportHelpers(valuetype [mscorlib]System.Guid solutionId, class [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataHelper metadataHelper, class [Microsoft.Crm.Core]Microsoft.Crm.CounterList listCounters, class [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.ICustomizationSqlLockManager lockManager)
0x79507  ldarg.0
0x79508  ldloc.s  4
0x7950a  ldfld    class <>c__DisplayClass81_0 <>c__DisplayClass81_1::CS$<>8__locals1
0x7950f  ldfld    class [Microsoft.Crm.Core]Microsoft.Crm.CounterList <>c__DisplayClass81_0::listCounters
0x79514  call     instance void Microsoft.Crm.Tools.ImportExportPublish.RootImportHandler::ProcessHandlers(class [Microsoft.Crm.Core]Microsoft.Crm.CounterList listCounters)
0x79519  ldarg.0
0x7951a  ldloc.s  4
0x7951c  ldfld    class <>c__DisplayClass81_0 <>c__DisplayClass81_1::CS$<>8__locals1
0x79521  ldfld    class [Microsoft.Crm.Core]Microsoft.Crm.CounterList <>c__DisplayClass81_0::listCounters
0x79526  call     instance void Microsoft.Crm.Tools.ImportExportPublish.RootImportHandler::ProcessNonExistantDependencies(class [Microsoft.Crm.Core]Microsoft.Crm.CounterList listCounters)
0x7952b  ldarg.0
0x7952c  ldloc.s  4
0x7952e  ldfld    class <>c__DisplayClass81_0 <>c__DisplayClass81_1::CS$<>8__locals1
0x79533  ldfld    class [Microsoft.Crm.Core]Microsoft.Crm.CounterList <>c__DisplayClass81_0::listCounters
0x79538  ldloc.2
0x79539  ldloc.1
0x7953a  call     instance void Microsoft.Crm.Tools.ImportExportPublish.RootImportHandler::PostImportActions(class [Microsoft.Crm.Core]Microsoft.Crm.CounterList listCounters, string currentVersion, string existingDBVersion)
0x7953f  leave.s  loc_79563
0x79541  ldloc.s  5
0x79543  brfalse.s loc_7954C
0x79545  ldloc.s  5
0x79547  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.DisposableBase::Dispose()
0x7954c  ldloc.s  7
0x7954e  brfalse.s loc_79557
0x79550  ldloc.s  7
0x79552  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.DisposableBase::Dispose()
0x79557  ldloc.s  6
0x79559  brfalse.s loc_79562
0x7955b  ldloc.s  6
0x7955d  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.DisposableBase::Dispose()
0x79562  endfinally
0x79563  ldarg.0
0x79564  ldloc.s  4
0x79566  ldfld    class <>c__DisplayClass81_0 <>c__DisplayClass81_1::CS$<>8__locals1
0x7956b  ldfld    class [Microsoft.Crm.Core]Microsoft.Crm.CounterList <>c__DisplayClass81_0::listCounters
0x79570  call     instance void Microsoft.Crm.Tools.ImportExportPublish.RootImportHandler::UpdateCustomEntityFeatureStateIfNecessary(class [Microsoft.Crm.Core]Microsoft.Crm.CounterList listCounters)
0x79575  ldarg.0
0x79576  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.RootImportHandler::context
0x7957b  ldstr    aUpdateclientri// "UpdateClientRibbonMetadataInSolutionFlo"...
0x79580  ldc.i4.1
0x79581  box      [mscorlib]System.Boolean
0x79586  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.SetVariableInContextModifier::.ctor(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext, string, object)
0x7958b  stloc.s  0xA
0x7958d  ldarg.0
0x7958e  ldloc.2
0x7958f  ldloc.1
0x79590  call     instance void Microsoft.Crm.Tools.ImportExportPublish.RootImportHandler::UpdateClientRibbonMetadata(string currentVersion, string existingDBVersion)
0x79595  leave.s  loc_795A3
0x79597  ldloc.s  0xA
0x79599  brfalse.s loc_795A2
0x7959b  ldloc.s  0xA
0x7959d  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x795a2  endfinally
0x795a3  ldloc.s  4
0x795a5  ldfld    class <>c__DisplayClass81_0 <>c__DisplayClass81_1::CS$<>8__locals1
0x795aa  ldfld    class [Microsoft.Crm.Core]Microsoft.Crm.CounterList <>c__DisplayClass81_0::listCounters
0x795af  ldstr    aCommittransact// "CommitTransaction"
0x795b4  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.Counter [Microsoft.Crm.Core]Microsoft.Crm.CounterList::InitStepCounter(string)
0x795b9  stloc.s  0xB
0x795bb  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x795c0  ldstr    aImportBegin0Ru_0// "Import_BEGIN_{0}.RunImport(setup).Commi"...
0x795c5  ldc.i4.1
0x795c6  newarr   [mscorlib]System.Object
0x795cb  dup
0x795cc  ldc.i4.0
0x795cd  ldarg.0
0x795ce  stelem.ref
0x795cf  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x795d4  call     void [Microsoft.Crm.Core]Microsoft.Crm.PerfControl::LogPerf(string)
0x795d9  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Core.Telemetry.EventSources.TelemetryExecutionToken::.ctor()
0x795de  stloc.s  0xC
0x795e0  ldsfld   class [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.ILogger Microsoft.Crm.Tools.ImportExportPublish.RootImportHandler::Logger
0x795e5  call     var<u1> class [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmTelemetrySingletonActivityType`1<class [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.SolutionImportCommitTransactionActivityType>::get_Instance()
0x795ea  ldarg.0
0x795eb  ldftn    instance void Microsoft.Crm.Tools.ImportExportPublish.RootImportHandler::<RunImport>b__81_1()
0x795f1  newobj   instance void [mscorlib]System.Action::.ctor(object, native int)
0x795f6  call     void [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmTelemetryExtensions::Execute(class [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.ILogger, class [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmTelemetryActivityType, class [mscorlib]System.Action)
0x795fb  call     class [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.SolutionTelemetryEvents [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.SolutionTelemetryEvents::get_Instance()
0x79600  ldarg.0
0x79601  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.RootImportHandler::context
0x79606  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x7960b  call     string [Microsoft.Crm.Core]Microsoft.Crm.Core.Telemetry.CrmTelemetryHelper::get_ApplicationVersion()
0x79610  ldloc.2
0x79611  ldstr    aMicrosoftCrmTo_8// "Microsoft.Crm.Tools.ImportExportPublish"...
0x79616  ldloc.s  0xC
0x79618  callvirt instance int64 [Microsoft.Crm.Core]Microsoft.Crm.Core.Telemetry.EventSources.TelemetryExecutionToken::get_ElapsedMilliseconds()
0x7961d  ldloc.1
0x7961e  ldc.i4.0
0x7961f  ldc.i4.0
0x79620  ldarg.0
0x79621  ldfld    class Microsoft.Crm.Tools.ImportExportPublish.ImportXml Microsoft.Crm.Tools.ImportExportPublish.RootImportHandler::parent
0x79626  callvirt instance string Microsoft.Crm.Tools.ImportExportPublish.ImportXml::get_SolutionName()
0x7962b  ldsfld   string [mscorlib]System.String::Empty
0x79630  ldsfld   string [mscorlib]System.String::Empty
0x79635  ldc.i4.1
0x79636  callvirt instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.SolutionTelemetryEvents::ImportHandlerExecuted(valuetype [mscorlib]System.Guid, string, string, string, int64, string, int32, int32, string, string, string, bool)
0x7963b  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x79640  ldstr    aImportEnd0Runi// "Import_END_{0}.RunImport(setup).CommitT"...
0x79645  ldc.i4.1
0x79646  newarr   [mscorlib]System.Object
0x7964b  dup
0x7964c  ldc.i4.0
0x7964d  ldarg.0
0x7964e  stelem.ref
0x7964f  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x79654  call     void [Microsoft.Crm.Core]Microsoft.Crm.PerfControl::LogPerf(string)
0x79659  leave.s  loc_79667
0x7965b  ldloc.s  0xB
0x7965d  brfalse.s loc_79666
0x7965f  ldloc.s  0xB
0x79661  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x79666  endfinally
0x79667  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Core.Telemetry.EventSources.TelemetryExecutionToken::.ctor()
0x7966c  stloc.s  9
0x7966e  ldsfld   class [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.ILogger Microsoft.Crm.Tools.ImportExportPublish.RootImportHandler::Logger
0x79673  call     var<u1> class [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmTelemetrySingletonActivityType`1<class [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.SolutionImportCacheFlushActivityType>::get_Instance()
0x79678  ldloc.s  4
0x7967a  ldftn    instance void <>c__DisplayClass81_1::<RunImport>b__0()
0x79680  newobj   instance void [mscorlib]System.Action::.ctor(object, native int)
0x79685  call     void [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmTelemetryExtensions::Execute(class [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.ILogger, class [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmTelemetryActivityType, class [mscorlib]System.Action)
0x7968a  call     class [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.SolutionTelemetryEvents [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.SolutionTelemetryEvents::get_Instance()
0x7968f  ldarg.0
0x79690  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.RootImportHandler::context
0x79695  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x7969a  call     string [Microsoft.Crm.Core]Microsoft.Crm.Core.Telemetry.CrmTelemetryHelper::get_ApplicationVersion()
0x7969f  ldloc.2
0x796a0  ldstr    aMicrosoftCrmTo_9// "Microsoft.Crm.Tools.ImportExportPublish"...
0x796a5  ldloc.s  9
0x796a7  callvirt instance int64 [Microsoft.Crm.Core]Microsoft.Crm.Core.Telemetry.EventSources.TelemetryExecutionToken::get_ElapsedMilliseconds()
0x796ac  ldloc.1
0x796ad  ldc.i4.0
0x796ae  ldc.i4.0
0x796af  ldarg.0
0x796b0  ldfld    class Microsoft.Crm.Tools.ImportExportPublish.ImportXml Microsoft.Crm.Tools.ImportExportPublish.RootImportHandler::parent
0x796b5  callvirt instance string Microsoft.Crm.Tools.ImportExportPublish.ImportXml::get_SolutionName()
0x796ba  ldsfld   string [mscorlib]System.String::Empty
0x796bf  ldsfld   string [mscorlib]System.String::Empty
0x796c4  ldc.i4.1
0x796c5  callvirt instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.SolutionTelemetryEvents::ImportHandlerExecuted(valuetype [mscorlib]System.Guid, string, string, string, int64, string, int32, int32, string, string, string, bool)
0x796ca  call     class [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.AppModuleMetadataChangeNotifier [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.AppModuleMetadataChangeNotifier::get_Instance()
0x796cf  ldarg.0
0x796d0  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.RootImportHandler::context
0x796d5  callvirt instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.AppModuleMetadataChangeNotifier::NotifyMetadataChange(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x796da  leave.s  loc_79731
0x796dc  pop
0x796dd  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x796e2  ldstr    aImportEnd0Runi_0// "Import_END_{0}.RunImport(setup)"
0x796e7  ldc.i4.1
0x796e8  newarr   [mscorlib]System.Object
0x796ed  dup
0x796ee  ldc.i4.0
0x796ef  ldarg.0
0x796f0  stelem.ref
0x796f1  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x796f6  call     void [Microsoft.Crm.Core]Microsoft.Crm.PerfControl::LogPerf(string)
0x796fb  ldarg.0
0x796fc  call     instance void Microsoft.Crm.Tools.ImportExportPublish.RootImportHandler::TryDeleteStagedComponents()
0x79701  ldarg.0
0x79702  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.RootImportHandler::context
0x79707  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_SqlContext()
0x7970c  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext::RollbackTransaction()
0x79711  rethrow
0x79713  ldloc.3
0x79714  brfalse.s loc_7971C
0x79716  ldloc.3
0x79717  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x7971c  endfinally
0x7971d  ldloc.0
0x7971e  ldfld    class [Microsoft.Crm.Core]Microsoft.Crm.CounterList <>c__DisplayClass81_0::listCounters
0x79723  brfalse.s loc_79730
0x79725  ldloc.0
0x79726  ldfld    class [Microsoft.Crm.Core]Microsoft.Crm.CounterList <>c__DisplayClass81_0::listCounters
0x7972b  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x79730  endfinally
0x79731  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x79736  ldstr    aImportEnd0Runi_0// "Import_END_{0}.RunImport(setup)"
0x7973b  ldc.i4.1
0x7973c  newarr   [mscorlib]System.Object
0x79741  dup
0x79742  ldc.i4.0
0x79743  ldarg.0
0x79744  stelem.ref
0x79745  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x7974a  call     void [Microsoft.Crm.Core]Microsoft.Crm.PerfControl::LogPerf(string)
0x7974f  ret
```
