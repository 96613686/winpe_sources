# Microsoft.Crm.FeatureDetailContainer::InitializeOfflineVersionedFeatureMetadata

- ea: `0x27550`
- end: `0x29ed7`
- name: `Microsoft.Crm.FeatureDetailContainer::InitializeOfflineVersionedFeatureMetadata`
- size: `10631`
- prototype: ``
- caller_count: `1`
- callee_count: `17`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x25ae0`

## callees

- `0x1f80`
- `0x5600`
- `0x25ab0`
- `0x25ac0`
- `0x25d00`
- `0x25dd0`
- `0x272a0`
- `0x27380`
- `0x273c0`
- `0x273f0`
- `0x27550`
- `0x29ee0`
- `0x2bc20`
- `0x2bc60`
- `0x2bc80`
- `0x51360`
- `0x51370`

## string_xrefs

- `0x279b4`: `FCB.SharedCache`
- `0x279d7`: `FCB.SharedCache2`
- `0x27a07`: `FCB.FlushMetadataCacheOnMiss`
- `0x27602`: `FCB.Refresh.Common`
- `0x27652`: `FCB.Refresh.Service`
- `0x27f24`: `FCB.LeoServiceFeatures`
- `0x28488`: `FCB.EnableExcelTemplatePerfFix`
- `0x284b8`: `FCB.AllowExcelBrowserCache`
- `0x285b9`: `FCB.PluginTraceLogging`
- `0x28333`: `FCB.AppDesigner.WelcomePage`
- `0x28028`: `FCB.AssignedTaskSync`
- `0x27df2`: `FCB.TelemetryAsyncDBAccessEvents`
- `0x29402`: `FCB.DBUpdateThrottling`
- `0x29425`: `FCB.DBUpdateScheduling`
- `0x29448`: `FCB.DBUpdateRetry`
- `0x294f7`: `FCB.UseSqlDataAccessorForMetadataCache`
- `0x2946b`: `FCB.ForceSkipDBUpdateScheduling`
- `0x2948e`: `FCB.MetadataCacheStorageOnHttpRuntimeForAsync`
- `0x2953d`: `FCB.MutableStagedPerThreadMetadataCache`
- `0x29560`: `FCB.LockFreeMetadataCache`
- `0x295c9`: `FCB.UseExecutionContextForMetadataCache`
- `0x294b1`: `FCB.MetadataCacheStorageOnHttpRuntimeForWebApi`
- `0x2951a`: `FCB.MultiOrgCacheLoadingUnderRecordLevelLock`
- `0x29615`: `FCB.SingleProcessPackageDeployOnCreate`
- `0x29638`: `FCB.SingleProcessPackageDeployOnUpdate`
- `0x2806e`: `FCB.ConfigurableSync`
- `0x298ba`: `FCB.DocumentRecommendations`
- `0x28e7c`: `FCB.InteractionCentricEmailLink`
- `0x289cc`: `FCB.UnifiedClientCacheModeEnabled`
- `0x29db7`: `FCB.UninstallPerformance`
- `0x28fcc`: `FCB.WorkflowSecuredCustomPluginRegistration`
- `0x2922f`: `FCB.ProductRecommendations`
- `0x2925f`: `FCB.ServiceCaseTopicAnalysis`
- `0x2928f`: `FCB.ProductRecommendationsStaging`
- `0x292bf`: `FCB.ServiceCaseTopicAnalysisStaging`
- `0x27aca`: `FCB.AMMUpdateForOfflineAppsOnly`
- `0x27afa`: `FCB.AMMUpdateEnqueueCheck`
- `0x27bba`: `FCB.AppConfigForOrganization`
- `0x29bba`: `FCB.D365SecurityRoleAssignment`

## pseudocode

```c

```

## disassembly

```asm
0x27550  ldarg.0
0x27551  ldarg.0
0x27552  ldfld    class Microsoft.Crm.ILocatorService Microsoft.Crm.FeatureDetailContainer::locatorService
0x27557  callvirt instance valuetype Microsoft.Crm.SharedDatabase.ConfigSku Microsoft.Crm.ILocatorService::GetSku()
0x2755c  newobj   instance void Microsoft.Crm.Core.Telemetry.CrmTelemetryFeature::.ctor(valuetype Microsoft.Crm.SharedDatabase.ConfigSku configSku)
0x27561  stfld    class Microsoft.Crm.IFeatureDetail Microsoft.Crm.FeatureDetailContainer::telemetryETWCollection
0x27566  ldarg.0
0x27567  ldstr    aFcbRefreshFall// "FCB.Refresh.Fall"
0x2756c  ldc.i4.1
0x2756d  ldc.i4.7
0x2756e  ldnull
0x2756f  ldc.i4.2
0x27570  newarr   Microsoft.Crm.FeatureVersionDetail
0x27575  dup
0x27576  ldc.i4.0
0x27577  newobj   instance void Microsoft.Crm.FeatureVersionDetail::.ctor()
0x2757c  dup
0x2757d  ldarg.0
0x2757e  ldfld    class [mscorlib]System.Version Microsoft.Crm.FeatureDetailContainer::FallVersion
0x27583  callvirt instance void Microsoft.Crm.FeatureVersionDetail::set_MinimumOrgDBVersion(class [mscorlib]System.Version value)
0x27588  dup
0x27589  ldc.i4.0
0x2758a  callvirt instance void Microsoft.Crm.FeatureVersionDetail::set_DefaultValue(bool value)
0x2758f  stelem.ref
0x27590  dup
0x27591  ldc.i4.1
0x27592  newobj   instance void Microsoft.Crm.FeatureVersionDetail::.ctor()
0x27597  dup
0x27598  ldarg.0
0x27599  ldfld    class [mscorlib]System.Version Microsoft.Crm.FeatureDetailContainer::OrionAirVersion
0x2759e  callvirt instance void Microsoft.Crm.FeatureVersionDetail::set_MinimumOrgDBVersion(class [mscorlib]System.Version value)
0x275a3  dup
0x275a4  ldc.i4.1
0x275a5  callvirt instance void Microsoft.Crm.FeatureVersionDetail::set_DefaultValue(bool value)
0x275aa  stelem.ref
0x275ab  call     instance class Microsoft.Crm.IFeatureDetail Microsoft.Crm.FeatureDetailContainer::AddOfflineOrgFeature(string name, valuetype Microsoft.Crm.FeatureType featureType, valuetype Microsoft.Crm.SharedDatabase.ConfigSku configSku, class Microsoft.Crm.IFeatureDetail parentFeature, class Microsoft.Crm.FeatureVersionDetail[] versionDetails)
0x275b0  pop
0x275b1  ldarg.0
0x275b2  ldstr    aFcbRefreshSale// "FCB.Refresh.Sales"
0x275b7  ldc.i4.1
0x275b8  ldc.i4.7
0x275b9  ldarg.0
0x275ba  call     instance class Microsoft.Crm.IFeatureDetail Microsoft.Crm.FeatureDetailContainer::get_RefreshFall()
0x275bf  ldc.i4.2
0x275c0  newarr   Microsoft.Crm.FeatureVersionDetail
0x275c5  dup
0x275c6  ldc.i4.0
0x275c7  newobj   instance void Microsoft.Crm.FeatureVersionDetail::.ctor()
0x275cc  dup
0x275cd  ldarg.0
0x275ce  ldfld    class [mscorlib]System.Version Microsoft.Crm.FeatureDetailContainer::FallVersion
0x275d3  callvirt instance void Microsoft.Crm.FeatureVersionDetail::set_MinimumOrgDBVersion(class [mscorlib]System.Version value)
0x275d8  dup
0x275d9  ldc.i4.0
0x275da  callvirt instance void Microsoft.Crm.FeatureVersionDetail::set_DefaultValue(bool value)
0x275df  stelem.ref
0x275e0  dup
0x275e1  ldc.i4.1
0x275e2  newobj   instance void Microsoft.Crm.FeatureVersionDetail::.ctor()
0x275e7  dup
0x275e8  ldarg.0
0x275e9  ldfld    class [mscorlib]System.Version Microsoft.Crm.FeatureDetailContainer::OrionAirVersion
0x275ee  callvirt instance void Microsoft.Crm.FeatureVersionDetail::set_MinimumOrgDBVersion(class [mscorlib]System.Version value)
0x275f3  dup
0x275f4  ldc.i4.1
0x275f5  callvirt instance void Microsoft.Crm.FeatureVersionDetail::set_DefaultValue(bool value)
0x275fa  stelem.ref
0x275fb  call     instance class Microsoft.Crm.IFeatureDetail Microsoft.Crm.FeatureDetailContainer::AddOfflineOrgFeature(string name, valuetype Microsoft.Crm.FeatureType featureType, valuetype Microsoft.Crm.SharedDatabase.ConfigSku configSku, class Microsoft.Crm.IFeatureDetail parentFeature, class Microsoft.Crm.FeatureVersionDetail[] versionDetails)
0x27600  pop
0x27601  ldarg.0
0x27602  ldstr    aFcbRefreshComm// "FCB.Refresh.Common"
0x27607  ldc.i4.1
0x27608  ldc.i4.7
0x27609  ldarg.0
0x2760a  call     instance class Microsoft.Crm.IFeatureDetail Microsoft.Crm.FeatureDetailContainer::get_RefreshFall()
0x2760f  ldc.i4.2
0x27610  newarr   Microsoft.Crm.FeatureVersionDetail
0x27615  dup
0x27616  ldc.i4.0
0x27617  newobj   instance void Microsoft.Crm.FeatureVersionDetail::.ctor()
0x2761c  dup
0x2761d  ldarg.0
0x2761e  ldfld    class [mscorlib]System.Version Microsoft.Crm.FeatureDetailContainer::FallVersion
0x27623  callvirt instance void Microsoft.Crm.FeatureVersionDetail::set_MinimumOrgDBVersion(class [mscorlib]System.Version value)
0x27628  dup
0x27629  ldc.i4.0
0x2762a  callvirt instance void Microsoft.Crm.FeatureVersionDetail::set_DefaultValue(bool value)
0x2762f  stelem.ref
0x27630  dup
0x27631  ldc.i4.1
0x27632  newobj   instance void Microsoft.Crm.FeatureVersionDetail::.ctor()
0x27637  dup
0x27638  ldarg.0
0x27639  ldfld    class [mscorlib]System.Version Microsoft.Crm.FeatureDetailContainer::OrionAirVersion
0x2763e  callvirt instance void Microsoft.Crm.FeatureVersionDetail::set_MinimumOrgDBVersion(class [mscorlib]System.Version value)
0x27643  dup
0x27644  ldc.i4.1
0x27645  callvirt instance void Microsoft.Crm.FeatureVersionDetail::set_DefaultValue(bool value)
0x2764a  stelem.ref
0x2764b  call     instance class Microsoft.Crm.IFeatureDetail Microsoft.Crm.FeatureDetailContainer::AddOfflineOrgFeature(string name, valuetype Microsoft.Crm.FeatureType featureType, valuetype Microsoft.Crm.SharedDatabase.ConfigSku configSku, class Microsoft.Crm.IFeatureDetail parentFeature, class Microsoft.Crm.FeatureVersionDetail[] versionDetails)
0x27650  pop
0x27651  ldarg.0
0x27652  ldstr    aFcbRefreshServ// "FCB.Refresh.Service"
0x27657  ldc.i4.1
0x27658  ldc.i4.7
0x27659  ldarg.0
0x2765a  call     instance class Microsoft.Crm.IFeatureDetail Microsoft.Crm.FeatureDetailContainer::get_RefreshFall()
0x2765f  ldc.i4.2
0x27660  newarr   Microsoft.Crm.FeatureVersionDetail
0x27665  dup
0x27666  ldc.i4.0
0x27667  newobj   instance void Microsoft.Crm.FeatureVersionDetail::.ctor()
0x2766c  dup
0x2766d  ldarg.0
0x2766e  ldfld    class [mscorlib]System.Version Microsoft.Crm.FeatureDetailContainer::FallVersion
0x27673  callvirt instance void Microsoft.Crm.FeatureVersionDetail::set_MinimumOrgDBVersion(class [mscorlib]System.Version value)
0x27678  dup
0x27679  ldc.i4.0
0x2767a  callvirt instance void Microsoft.Crm.FeatureVersionDetail::set_DefaultValue(bool value)
0x2767f  stelem.ref
0x27680  dup
0x27681  ldc.i4.1
0x27682  newobj   instance void Microsoft.Crm.FeatureVersionDetail::.ctor()
0x27687  dup
0x27688  ldarg.0
0x27689  ldfld    class [mscorlib]System.Version Microsoft.Crm.FeatureDetailContainer::OrionAirVersion
0x2768e  callvirt instance void Microsoft.Crm.FeatureVersionDetail::set_MinimumOrgDBVersion(class [mscorlib]System.Version value)
0x27693  dup
0x27694  ldc.i4.1
0x27695  callvirt instance void Microsoft.Crm.FeatureVersionDetail::set_DefaultValue(bool value)
0x2769a  stelem.ref
0x2769b  call     instance class Microsoft.Crm.IFeatureDetail Microsoft.Crm.FeatureDetailContainer::AddOfflineOrgFeature(string name, valuetype Microsoft.Crm.FeatureType featureType, valuetype Microsoft.Crm.SharedDatabase.ConfigSku configSku, class Microsoft.Crm.IFeatureDetail parentFeature, class Microsoft.Crm.FeatureVersionDetail[] versionDetails)
0x276a0  pop
0x276a1  ldarg.0
0x276a2  ldstr    aFcbOrionAir// "FCB.Orion.Air"
0x276a7  ldc.i4.0
0x276a8  ldc.i4.7
0x276a9  ldnull
0x276aa  ldc.i4.1
0x276ab  newarr   Microsoft.Crm.FeatureVersionDetail
0x276b0  dup
0x276b1  ldc.i4.0
0x276b2  newobj   instance void Microsoft.Crm.FeatureVersionDetail::.ctor()
0x276b7  dup
0x276b8  ldarg.0
0x276b9  ldfld    class [mscorlib]System.Version Microsoft.Crm.FeatureDetailContainer::OrionAirVersion
0x276be  callvirt instance void Microsoft.Crm.FeatureVersionDetail::set_MinimumOrgDBVersion(class [mscorlib]System.Version value)
0x276c3  dup
0x276c4  ldc.i4.1
0x276c5  callvirt instance void Microsoft.Crm.FeatureVersionDetail::set_DefaultValue(bool value)
0x276ca  stelem.ref
0x276cb  call     instance class Microsoft.Crm.IFeatureDetail Microsoft.Crm.FeatureDetailContainer::AddOfflineOrgFeature(string name, valuetype Microsoft.Crm.FeatureType featureType, valuetype Microsoft.Crm.SharedDatabase.ConfigSku configSku, class Microsoft.Crm.IFeatureDetail parentFeature, class Microsoft.Crm.FeatureVersionDetail[] versionDetails)
0x276d0  pop
0x276d1  ldarg.0
0x276d2  ldstr    aFcbMocaApplica// "FCB.Moca.ApplicationMetadataOnDemandSyn"...
0x276d7  ldc.i4.0
0x276d8  ldc.i4.7
0x276d9  ldnull
0x276da  ldc.i4.1
0x276db  newarr   Microsoft.Crm.FeatureVersionDetail
0x276e0  dup
0x276e1  ldc.i4.0
0x276e2  newobj   instance void Microsoft.Crm.FeatureVersionDetail::.ctor()
0x276e7  dup
0x276e8  ldarg.0
0x276e9  ldfld    class [mscorlib]System.Version Microsoft.Crm.FeatureDetailContainer::CentaurusVersion
0x276ee  callvirt instance void Microsoft.Crm.FeatureVersionDetail::set_MinimumOrgDBVersion(class [mscorlib]System.Version value)
0x276f3  dup
0x276f4  ldc.i4.0
0x276f5  callvirt instance void Microsoft.Crm.FeatureVersionDetail::set_DefaultValue(bool value)
0x276fa  stelem.ref
0x276fb  call     instance class Microsoft.Crm.IFeatureDetail Microsoft.Crm.FeatureDetailContainer::AddOfflineOrgFeature(string name, valuetype Microsoft.Crm.FeatureType featureType, valuetype Microsoft.Crm.SharedDatabase.ConfigSku configSku, class Microsoft.Crm.IFeatureDetail parentFeature, class Microsoft.Crm.FeatureVersionDetail[] versionDetails)
0x27700  pop
0x27701  ldarg.0
0x27702  ldstr    aFcbMultientity// "FCB.MultiEntitySearch"
0x27707  ldc.i4.1
0x27708  ldc.i4.7
0x27709  ldnull
0x2770a  ldc.i4.1
0x2770b  newarr   Microsoft.Crm.FeatureVersionDetail
0x27710  dup
0x27711  ldc.i4.0
0x27712  newobj   instance void Microsoft.Crm.FeatureVersionDetail::.ctor()
0x27717  dup
0x27718  ldarg.0
0x27719  ldfld    class [mscorlib]System.Version Microsoft.Crm.FeatureDetailContainer::OrionAirVersion
0x2771e  callvirt instance void Microsoft.Crm.FeatureVersionDetail::set_MinimumOrgDBVersion(class [mscorlib]System.Version value)
0x27723  dup
0x27724  ldc.i4.1
0x27725  callvirt instance void Microsoft.Crm.FeatureVersionDetail::set_DefaultValue(bool value)
0x2772a  stelem.ref
0x2772b  call     instance class Microsoft.Crm.IFeatureDetail Microsoft.Crm.FeatureDetailContainer::AddOfflineOrgFeature(string name, valuetype Microsoft.Crm.FeatureType featureType, valuetype Microsoft.Crm.SharedDatabase.ConfigSku configSku, class Microsoft.Crm.IFeatureDetail parentFeature, class Microsoft.Crm.FeatureVersionDetail[] versionDetails)
0x27730  pop
0x27731  ldarg.0
0x27732  ldstr    aFcbUpgradeform// "FCB.UpgradeFormMerge"
0x27737  ldc.i4.1
0x27738  ldc.i4.7
0x27739  ldnull
0x2773a  ldc.i4.1
0x2773b  newarr   Microsoft.Crm.FeatureVersionDetail
0x27740  dup
0x27741  ldc.i4.0
0x27742  newobj   instance void Microsoft.Crm.FeatureVersionDetail::.ctor()
0x27747  dup
0x27748  ldarg.0
0x27749  ldfld    class [mscorlib]System.Version Microsoft.Crm.FeatureDetailContainer::OrionAirVersion
0x2774e  callvirt instance void Microsoft.Crm.FeatureVersionDetail::set_MinimumOrgDBVersion(class [mscorlib]System.Version value)
0x27753  dup
0x27754  ldc.i4.1
0x27755  callvirt instance void Microsoft.Crm.FeatureVersionDetail::set_DefaultValue(bool value)
0x2775a  stelem.ref
0x2775b  call     instance class Microsoft.Crm.IFeatureDetail Microsoft.Crm.FeatureDetailContainer::AddOfflineOrgFeature(string name, valuetype Microsoft.Crm.FeatureType featureType, valuetype Microsoft.Crm.SharedDatabase.ConfigSku configSku, class Microsoft.Crm.IFeatureDetail parentFeature, class Microsoft.Crm.FeatureVersionDetail[] versionDetails)
0x27760  pop
0x27761  ldarg.0
0x27762  ldstr    aFcbVersionnumb// "FCB.VersionNumberFiltering"
0x27767  ldc.i4.1
0x27768  ldc.i4.7
0x27769  ldnull
0x2776a  ldc.i4.1
0x2776b  newarr   Microsoft.Crm.FeatureVersionDetail
0x27770  dup
0x27771  ldc.i4.0
0x27772  newobj   instance void Microsoft.Crm.FeatureVersionDetail::.ctor()
0x27777  dup
0x27778  ldarg.0
0x27779  call     instance class [mscorlib]System.Version Microsoft.Crm.FeatureDetailContainer::get_PotassiumVersionValue()
0x2777e  callvirt instance void Microsoft.Crm.FeatureVersionDetail::set_MinimumOrgDBVersion(class [mscorlib]System.Version value)
0x27783  dup
0x27784  ldc.i4.1
0x27785  callvirt instance void Microsoft.Crm.FeatureVersionDetail::set_DefaultValue(bool value)
0x2778a  stelem.ref
0x2778b  call     instance class Microsoft.Crm.IFeatureDetail Microsoft.Crm.FeatureDetailContainer::AddOfflineOrgFeature(string name, valuetype Microsoft.Crm.FeatureType featureType, valuetype Microsoft.Crm.SharedDatabase.ConfigSku configSku, class Microsoft.Crm.IFeatureDetail parentFeature, class Microsoft.Crm.FeatureVersionDetail[] versionDetails)
0x27790  pop
0x27791  ldarg.0
0x27792  ldstr    aFcbSkipnavigat// "FCB.SkipNavigation"
0x27797  ldc.i4.0
0x27798  ldc.i4.7
0x27799  ldnull
0x2779a  ldc.i4.1
0x2779b  newarr   Microsoft.Crm.FeatureVersionDetail
0x277a0  dup
0x277a1  ldc.i4.0
0x277a2  newobj   instance void Microsoft.Crm.FeatureVersionDetail::.ctor()
0x277a7  dup
0x277a8  ldarg.0
0x277a9  ldfld    class [mscorlib]System.Version Microsoft.Crm.FeatureDetailContainer::VegaVersion
0x277ae  callvirt instance void Microsoft.Crm.FeatureVersionDetail::set_MinimumOrgDBVersion(class [mscorlib]System.Version value)
0x277b3  dup
0x277b4  ldc.i4.1
0x277b5  callvirt instance void Microsoft.Crm.FeatureVersionDetail::set_DefaultValue(bool value)
0x277ba  stelem.ref
0x277bb  call     instance class Microsoft.Crm.IFeatureDetail Microsoft.Crm.FeatureDetailContainer::AddOfflineOrgFeature(string name, valuetype Microsoft.Crm.FeatureType featureType, valuetype Microsoft.Crm.SharedDatabase.ConfigSku configSku, class Microsoft.Crm.IFeatureDetail parentFeature, class Microsoft.Crm.FeatureVersionDetail[] versionDetails)
0x277c0  pop
0x277c1  ldarg.0
0x277c2  ldstr    aFcbCalculatedf// "FCB.CalculatedFields"
0x277c7  ldc.i4.1
0x277c8  ldc.i4.7
0x277c9  ldnull
0x277ca  ldc.i4.1
0x277cb  newarr   Microsoft.Crm.FeatureVersionDetail
0x277d0  dup
0x277d1  ldc.i4.0
0x277d2  newobj   instance void Microsoft.Crm.FeatureVersionDetail::.ctor()
0x277d7  dup
0x277d8  ldarg.0
0x277d9  ldfld    class [mscorlib]System.Version Microsoft.Crm.FeatureDetailContainer::VegaVersion
0x277de  callvirt instance void Microsoft.Crm.FeatureVersionDetail::set_MinimumOrgDBVersion(class [mscorlib]System.Version value)
0x277e3  dup
0x277e4  ldc.i4.1
0x277e5  callvirt instance void Microsoft.Crm.FeatureVersionDetail::set_DefaultValue(bool value)
0x277ea  stelem.ref
0x277eb  call     instance class Microsoft.Crm.IFeatureDetail Microsoft.Crm.FeatureDetailContainer::AddOfflineOrgFeature(string name, valuetype Microsoft.Crm.FeatureType featureType, valuetype Microsoft.Crm.SharedDatabase.ConfigSku configSku, class Microsoft.Crm.IFeatureDetail parentFeature, class Microsoft.Crm.FeatureVersionDetail[] versionDetails)
0x277f0  pop
0x277f1  call     valuetype Microsoft.Crm.SharedDatabase.ConfigSku Microsoft.Crm.BootstrapService::GetSku()
0x277f6  ldc.i4.2
0x277f7  beq.s    loc_27813
0x277f9  newobj   instance void Microsoft.Crm.FeatureVersionDetail::.ctor()
0x277fe  dup
0x277ff  ldarg.0
0x27800  ldfld    class [mscorlib]System.Version Microsoft.Crm.FeatureDetailContainer::VegaVersion
0x27805  callvirt instance void Microsoft.Crm.FeatureVersionDetail::set_MinimumOrgDBVersion(class [mscorlib]System.Version value)
0x2780a  dup
0x2780b  ldc.i4.1
0x2780c  callvirt instance void Microsoft.Crm.FeatureVersionDetail::set_DefaultValue(bool value)
0x27811  br.s     loc_2782B
0x27813  newobj   instance void Microsoft.Crm.FeatureVersionDetail::.ctor()
0x27818  dup
0x27819  ldarg.0
0x2781a  ldfld    class [mscorlib]System.Version Microsoft.Crm.FeatureDetailContainer::LeoVersion
0x2781f  callvirt instance void Microsoft.Crm.FeatureVersionDetail::set_MinimumOrgDBVersion(class [mscorlib]System.Version value)
0x27824  dup
0x27825  ldc.i4.1
0x27826  callvirt instance void Microsoft.Crm.FeatureVersionDetail::set_DefaultValue(bool value)
0x2782b  stloc.0
0x2782c  ldarg.0
0x2782d  ldstr    aFcbSocialinsig// "FCB.SocialInsights"
0x27832  ldc.i4.0
0x27833  ldc.i4.7
0x27834  ldnull
0x27835  ldc.i4.1
  ... truncated ...
```
