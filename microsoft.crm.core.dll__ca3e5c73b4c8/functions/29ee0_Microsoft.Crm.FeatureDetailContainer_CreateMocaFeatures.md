# Microsoft.Crm.FeatureDetailContainer::CreateMocaFeatures

- ea: `0x29ee0`
- end: `0x2b58b`
- name: `Microsoft.Crm.FeatureDetailContainer::CreateMocaFeatures`
- size: `5803`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x27550`

## callees

- `0x272a0`
- `0x27380`
- `0x2bc20`
- `0x2bc60`
- `0x2bc80`

## string_xrefs

- `0x2a7af`: `FCB.Moca.PrivilegeBasedMetadataSync`
- `0x2a27a`: `FCB.DocumentTemplateUCI`
- `0x2a24a`: `FCB.Moca.WordDocumentTemplate`
- `0x2a21a`: `FCB.Moca.ExcelDocumentTemplate`
- `0x2a2dc`: `FCB.MultiThreadMetadataGeneration`
- `0x2a35f`: `FCB.TaskBasedFlow`
- `0x2a38f`: `FCB.TaskBasedFlowEditor`
- `0x2a3bf`: `FCB.TaskBasedFlowSolutionAware`
- `0x2a3ef`: `FCB.TaskBasedFlowCustomControls`
- `0x2a41f`: `FCB.Moca.AppLinking`
- `0x2a0e4`: `FCB.KMSimpleRelevanceSearch`
- `0x29f94`: `FCB.CustomControlSolutionUninstall`
- `0x2b358`: `FCB.EmailEngagementComposeForUCI`
- `0x2a7df`: `FCB.TaskBasedFlowListSupport`
- `0x2a8cf`: `FCB.CommandbarDesigner`
- `0x2ab0f`: `FCB.LinkedInAnalysis`
- `0x2ab9f`: `FCB.OfficeMailAppOutlookMacCompose`
- `0x2abff`: `FCB.EnableStagedComponents`
- `0x2ad4f`: `FCB.UCIMetadataClientBrowserCache`
- `0x2ad7f`: `FCB.OwinOpenIdAuthentication`
- `0x2add2`: `FCB.EnablePartialLoadMetadataCache`
- `0x2af22`: `FCB.TimelineWall.CommandBar.Activities`
- `0x2b072`: `FCB.UseMetadataCacheForStagedData`
- `0x2b0a2`: `FCB.EnableReadCommittedTransactions`
- `0x2b0f5`: `FCB.AzureWebAppPlugins`
- `0x2b155`: `FCB.ConfigServiceEnabled`
- `0x2b1d8`: `FCB.RibbonMDUpdateDuringSolutionImport`
- `0x2b208`: `FCB.RibbonMDUpdateDuringSolutionUninstall`
- `0x2b298`: `FCB.SSSMailboxErrorDynamicLink`
- `0x2b328`: `FCB.UseNewRIConfig`
- `0x2b538`: `FCB.DelayOpenConnectionInSqlExecutionContext`

## pseudocode

```c

```

## disassembly

```asm
0x29ee0  ldarg.0
0x29ee1  ldstr    aFcbMocaInterac// "FCB.Moca.InteractionCentricDashboard"
0x29ee6  ldc.i4.0
0x29ee7  ldc.i4.7
0x29ee8  ldnull
0x29ee9  ldc.i4.1
0x29eea  newarr   Microsoft.Crm.FeatureVersionDetail
0x29eef  dup
0x29ef0  ldc.i4.0
0x29ef1  newobj   instance void Microsoft.Crm.FeatureVersionDetail::.ctor()
0x29ef6  dup
0x29ef7  ldarg.0
0x29ef8  ldfld    class [mscorlib]System.Version Microsoft.Crm.FeatureDetailContainer::AraVersion
0x29efd  callvirt instance void Microsoft.Crm.FeatureVersionDetail::set_MinimumOrgDBVersion(class [mscorlib]System.Version value)
0x29f02  dup
0x29f03  ldc.i4.1
0x29f04  callvirt instance void Microsoft.Crm.FeatureVersionDetail::set_DefaultValue(bool value)
0x29f09  stelem.ref
0x29f0a  call     instance class Microsoft.Crm.IFeatureDetail Microsoft.Crm.FeatureDetailContainer::AddOfflineOrgFeature(string name, valuetype Microsoft.Crm.FeatureType featureType, valuetype Microsoft.Crm.SharedDatabase.ConfigSku configSku, class Microsoft.Crm.IFeatureDetail parentFeature, class Microsoft.Crm.FeatureVersionDetail[] versionDetails)
0x29f0f  pop
0x29f10  ldarg.0
0x29f11  ldstr    aFcbMocaMashups// "FCB.Moca.Mashups"
0x29f16  ldc.i4.2
0x29f17  ldc.i4.7
0x29f18  ldc.i4.1
0x29f19  newarr   Microsoft.Crm.FeatureVersionDetail
0x29f1e  dup
0x29f1f  ldc.i4.0
0x29f20  newobj   instance void Microsoft.Crm.FeatureVersionDetail::.ctor()
0x29f25  dup
0x29f26  ldc.i4.1
0x29f27  callvirt instance void Microsoft.Crm.FeatureVersionDetail::set_DefaultValue(bool value)
0x29f2c  stelem.ref
0x29f2d  call     instance class Microsoft.Crm.IFeatureDetail Microsoft.Crm.FeatureDetailContainer::AddOfflineNonOrgFeature(string name, valuetype Microsoft.Crm.FeatureLocation featureLocation, valuetype Microsoft.Crm.SharedDatabase.ConfigSku configSku, class Microsoft.Crm.FeatureVersionDetail[] versionDetails)
0x29f32  pop
0x29f33  ldarg.0
0x29f34  ldstr    aFcbCustomcontr// "FCB.CustomControlMobile"
0x29f39  ldc.i4.0
0x29f3a  ldc.i4.7
0x29f3b  ldnull
0x29f3c  ldc.i4.1
0x29f3d  newarr   Microsoft.Crm.FeatureVersionDetail
0x29f42  dup
0x29f43  ldc.i4.0
0x29f44  newobj   instance void Microsoft.Crm.FeatureVersionDetail::.ctor()
0x29f49  dup
0x29f4a  ldarg.0
0x29f4b  ldfld    class [mscorlib]System.Version Microsoft.Crm.FeatureDetailContainer::AraVersion
0x29f50  callvirt instance void Microsoft.Crm.FeatureVersionDetail::set_MinimumOrgDBVersion(class [mscorlib]System.Version value)
0x29f55  dup
0x29f56  ldc.i4.1
0x29f57  callvirt instance void Microsoft.Crm.FeatureVersionDetail::set_DefaultValue(bool value)
0x29f5c  stelem.ref
0x29f5d  call     instance class Microsoft.Crm.IFeatureDetail Microsoft.Crm.FeatureDetailContainer::AddOfflineOrgFeature(string name, valuetype Microsoft.Crm.FeatureType featureType, valuetype Microsoft.Crm.SharedDatabase.ConfigSku configSku, class Microsoft.Crm.IFeatureDetail parentFeature, class Microsoft.Crm.FeatureVersionDetail[] versionDetails)
0x29f62  pop
0x29f63  ldarg.0
0x29f64  ldstr    aFcbCustomcontr_0// "FCB.CustomControlSolutionImport"
0x29f69  ldc.i4.0
0x29f6a  ldc.i4.7
0x29f6b  ldnull
0x29f6c  ldc.i4.1
0x29f6d  newarr   Microsoft.Crm.FeatureVersionDetail
0x29f72  dup
0x29f73  ldc.i4.0
0x29f74  newobj   instance void Microsoft.Crm.FeatureVersionDetail::.ctor()
0x29f79  dup
0x29f7a  ldarg.0
0x29f7b  ldfld    class [mscorlib]System.Version Microsoft.Crm.FeatureDetailContainer::AraVersion
0x29f80  callvirt instance void Microsoft.Crm.FeatureVersionDetail::set_MinimumOrgDBVersion(class [mscorlib]System.Version value)
0x29f85  dup
0x29f86  ldc.i4.1
0x29f87  callvirt instance void Microsoft.Crm.FeatureVersionDetail::set_DefaultValue(bool value)
0x29f8c  stelem.ref
0x29f8d  call     instance class Microsoft.Crm.IFeatureDetail Microsoft.Crm.FeatureDetailContainer::AddOfflineOrgFeature(string name, valuetype Microsoft.Crm.FeatureType featureType, valuetype Microsoft.Crm.SharedDatabase.ConfigSku configSku, class Microsoft.Crm.IFeatureDetail parentFeature, class Microsoft.Crm.FeatureVersionDetail[] versionDetails)
0x29f92  pop
0x29f93  ldarg.0
0x29f94  ldstr    aFcbCustomcontr_1// "FCB.CustomControlSolutionUninstall"
0x29f99  ldc.i4.0
0x29f9a  ldc.i4.7
0x29f9b  ldnull
0x29f9c  ldc.i4.1
0x29f9d  newarr   Microsoft.Crm.FeatureVersionDetail
0x29fa2  dup
0x29fa3  ldc.i4.0
0x29fa4  newobj   instance void Microsoft.Crm.FeatureVersionDetail::.ctor()
0x29fa9  dup
0x29faa  ldarg.0
0x29fab  ldfld    class [mscorlib]System.Version Microsoft.Crm.FeatureDetailContainer::CentaurusVersion
0x29fb0  callvirt instance void Microsoft.Crm.FeatureVersionDetail::set_MinimumOrgDBVersion(class [mscorlib]System.Version value)
0x29fb5  dup
0x29fb6  ldc.i4.0
0x29fb7  callvirt instance void Microsoft.Crm.FeatureVersionDetail::set_DefaultValue(bool value)
0x29fbc  stelem.ref
0x29fbd  call     instance class Microsoft.Crm.IFeatureDetail Microsoft.Crm.FeatureDetailContainer::AddOfflineOrgFeature(string name, valuetype Microsoft.Crm.FeatureType featureType, valuetype Microsoft.Crm.SharedDatabase.ConfigSku configSku, class Microsoft.Crm.IFeatureDetail parentFeature, class Microsoft.Crm.FeatureVersionDetail[] versionDetails)
0x29fc2  pop
0x29fc3  ldarg.0
0x29fc4  ldstr    aFcbCustomcontr_2// "FCB.CustomControlSolutionExport"
0x29fc9  ldc.i4.0
0x29fca  ldc.i4.7
0x29fcb  ldnull
0x29fcc  ldc.i4.1
0x29fcd  newarr   Microsoft.Crm.FeatureVersionDetail
0x29fd2  dup
0x29fd3  ldc.i4.0
0x29fd4  newobj   instance void Microsoft.Crm.FeatureVersionDetail::.ctor()
0x29fd9  dup
0x29fda  ldarg.0
0x29fdb  ldfld    class [mscorlib]System.Version Microsoft.Crm.FeatureDetailContainer::CentaurusVersion
0x29fe0  callvirt instance void Microsoft.Crm.FeatureVersionDetail::set_MinimumOrgDBVersion(class [mscorlib]System.Version value)
0x29fe5  dup
0x29fe6  ldc.i4.1
0x29fe7  callvirt instance void Microsoft.Crm.FeatureVersionDetail::set_DefaultValue(bool value)
0x29fec  stelem.ref
0x29fed  call     instance class Microsoft.Crm.IFeatureDetail Microsoft.Crm.FeatureDetailContainer::AddOfflineOrgFeature(string name, valuetype Microsoft.Crm.FeatureType featureType, valuetype Microsoft.Crm.SharedDatabase.ConfigSku configSku, class Microsoft.Crm.IFeatureDetail parentFeature, class Microsoft.Crm.FeatureVersionDetail[] versionDetails)
0x29ff2  pop
0x29ff3  ldarg.0
0x29ff4  ldstr    aFcbCustomcontr_3// "FCB.CustomControlViewSupport"
0x29ff9  ldc.i4.0
0x29ffa  ldc.i4.7
0x29ffb  ldnull
0x29ffc  ldc.i4.1
0x29ffd  newarr   Microsoft.Crm.FeatureVersionDetail
0x2a002  dup
0x2a003  ldc.i4.0
0x2a004  newobj   instance void Microsoft.Crm.FeatureVersionDetail::.ctor()
0x2a009  dup
0x2a00a  ldarg.0
0x2a00b  ldfld    class [mscorlib]System.Version Microsoft.Crm.FeatureDetailContainer::PotassiumVersion
0x2a010  callvirt instance void Microsoft.Crm.FeatureVersionDetail::set_MinimumOrgDBVersion(class [mscorlib]System.Version value)
0x2a015  dup
0x2a016  ldc.i4.1
0x2a017  callvirt instance void Microsoft.Crm.FeatureVersionDetail::set_DefaultValue(bool value)
0x2a01c  stelem.ref
0x2a01d  call     instance class Microsoft.Crm.IFeatureDetail Microsoft.Crm.FeatureDetailContainer::AddOfflineOrgFeature(string name, valuetype Microsoft.Crm.FeatureType featureType, valuetype Microsoft.Crm.SharedDatabase.ConfigSku configSku, class Microsoft.Crm.IFeatureDetail parentFeature, class Microsoft.Crm.FeatureVersionDetail[] versionDetails)
0x2a022  pop
0x2a023  ldarg.0
0x2a024  ldstr    aFcbCustomcontr_4// "FCB.CustomControlSitemapSupport"
0x2a029  ldc.i4.0
0x2a02a  ldc.i4.7
0x2a02b  ldnull
0x2a02c  ldc.i4.1
0x2a02d  newarr   Microsoft.Crm.FeatureVersionDetail
0x2a032  dup
0x2a033  ldc.i4.0
0x2a034  newobj   instance void Microsoft.Crm.FeatureVersionDetail::.ctor()
0x2a039  dup
0x2a03a  ldarg.0
0x2a03b  ldfld    class [mscorlib]System.Version Microsoft.Crm.FeatureDetailContainer::PotassiumVersion
0x2a040  callvirt instance void Microsoft.Crm.FeatureVersionDetail::set_MinimumOrgDBVersion(class [mscorlib]System.Version value)
0x2a045  dup
0x2a046  ldc.i4.0
0x2a047  callvirt instance void Microsoft.Crm.FeatureVersionDetail::set_DefaultValue(bool value)
0x2a04c  stelem.ref
0x2a04d  call     instance class Microsoft.Crm.IFeatureDetail Microsoft.Crm.FeatureDetailContainer::AddOfflineOrgFeature(string name, valuetype Microsoft.Crm.FeatureType featureType, valuetype Microsoft.Crm.SharedDatabase.ConfigSku configSku, class Microsoft.Crm.IFeatureDetail parentFeature, class Microsoft.Crm.FeatureVersionDetail[] versionDetails)
0x2a052  pop
0x2a053  ldarg.0
0x2a054  ldstr    aFcbUnboundcust// "FCB.UnboundCustomControlSupport"
0x2a059  ldc.i4.0
0x2a05a  ldc.i4.7
0x2a05b  ldnull
0x2a05c  ldc.i4.1
0x2a05d  newarr   Microsoft.Crm.FeatureVersionDetail
0x2a062  dup
0x2a063  ldc.i4.0
0x2a064  newobj   instance void Microsoft.Crm.FeatureVersionDetail::.ctor()
0x2a069  dup
0x2a06a  ldarg.0
0x2a06b  ldfld    class [mscorlib]System.Version Microsoft.Crm.FeatureDetailContainer::PotassiumVersion
0x2a070  callvirt instance void Microsoft.Crm.FeatureVersionDetail::set_MinimumOrgDBVersion(class [mscorlib]System.Version value)
0x2a075  dup
0x2a076  ldc.i4.0
0x2a077  callvirt instance void Microsoft.Crm.FeatureVersionDetail::set_DefaultValue(bool value)
0x2a07c  stelem.ref
0x2a07d  call     instance class Microsoft.Crm.IFeatureDetail Microsoft.Crm.FeatureDetailContainer::AddOfflineOrgFeature(string name, valuetype Microsoft.Crm.FeatureType featureType, valuetype Microsoft.Crm.SharedDatabase.ConfigSku configSku, class Microsoft.Crm.IFeatureDetail parentFeature, class Microsoft.Crm.FeatureVersionDetail[] versionDetails)
0x2a082  pop
0x2a083  ldarg.0
0x2a084  ldstr    aFcbReferencepa// "FCB.ReferencePanelControl"
0x2a089  ldc.i4.0
0x2a08a  ldc.i4.7
0x2a08b  ldnull
0x2a08c  ldc.i4.1
0x2a08d  newarr   Microsoft.Crm.FeatureVersionDetail
0x2a092  dup
0x2a093  ldc.i4.0
0x2a094  newobj   instance void Microsoft.Crm.FeatureVersionDetail::.ctor()
0x2a099  dup
0x2a09a  ldarg.0
0x2a09b  ldfld    class [mscorlib]System.Version Microsoft.Crm.FeatureDetailContainer::PotassiumVersion
0x2a0a0  callvirt instance void Microsoft.Crm.FeatureVersionDetail::set_MinimumOrgDBVersion(class [mscorlib]System.Version value)
0x2a0a5  dup
0x2a0a6  ldc.i4.1
0x2a0a7  callvirt instance void Microsoft.Crm.FeatureVersionDetail::set_DefaultValue(bool value)
0x2a0ac  stelem.ref
0x2a0ad  call     instance class Microsoft.Crm.IFeatureDetail Microsoft.Crm.FeatureDetailContainer::AddOfflineOrgFeature(string name, valuetype Microsoft.Crm.FeatureType featureType, valuetype Microsoft.Crm.SharedDatabase.ConfigSku configSku, class Microsoft.Crm.IFeatureDetail parentFeature, class Microsoft.Crm.FeatureVersionDetail[] versionDetails)
0x2a0b2  pop
0x2a0b3  ldarg.0
0x2a0b4  ldstr    aFcbLookupchang// "FCB.LookupChangeViewOnUCI"
0x2a0b9  ldc.i4.0
0x2a0ba  ldc.i4.7
0x2a0bb  ldnull
0x2a0bc  ldc.i4.1
0x2a0bd  newarr   Microsoft.Crm.FeatureVersionDetail
0x2a0c2  dup
0x2a0c3  ldc.i4.0
0x2a0c4  newobj   instance void Microsoft.Crm.FeatureVersionDetail::.ctor()
0x2a0c9  dup
0x2a0ca  ldarg.0
0x2a0cb  ldfld    class [mscorlib]System.Version Microsoft.Crm.FeatureDetailContainer::PotassiumVersion
0x2a0d0  callvirt instance void Microsoft.Crm.FeatureVersionDetail::set_MinimumOrgDBVersion(class [mscorlib]System.Version value)
0x2a0d5  dup
0x2a0d6  ldc.i4.0
0x2a0d7  callvirt instance void Microsoft.Crm.FeatureVersionDetail::set_DefaultValue(bool value)
0x2a0dc  stelem.ref
0x2a0dd  call     instance class Microsoft.Crm.IFeatureDetail Microsoft.Crm.FeatureDetailContainer::AddOfflineOrgFeature(string name, valuetype Microsoft.Crm.FeatureType featureType, valuetype Microsoft.Crm.SharedDatabase.ConfigSku configSku, class Microsoft.Crm.IFeatureDetail parentFeature, class Microsoft.Crm.FeatureVersionDetail[] versionDetails)
0x2a0e2  pop
0x2a0e3  ldarg.0
0x2a0e4  ldstr    aFcbKmsimplerel// "FCB.KMSimpleRelevanceSearch"
0x2a0e9  ldc.i4.0
0x2a0ea  ldc.i4.7
0x2a0eb  ldnull
0x2a0ec  ldc.i4.1
0x2a0ed  newarr   Microsoft.Crm.FeatureVersionDetail
0x2a0f2  dup
0x2a0f3  ldc.i4.0
0x2a0f4  newobj   instance void Microsoft.Crm.FeatureVersionDetail::.ctor()
0x2a0f9  dup
0x2a0fa  ldarg.0
0x2a0fb  ldfld    class [mscorlib]System.Version Microsoft.Crm.FeatureDetailContainer::PotassiumVersion
0x2a100  callvirt instance void Microsoft.Crm.FeatureVersionDetail::set_MinimumOrgDBVersion(class [mscorlib]System.Version value)
0x2a105  dup
0x2a106  ldc.i4.0
0x2a107  callvirt instance void Microsoft.Crm.FeatureVersionDetail::set_DefaultValue(bool value)
0x2a10c  stelem.ref
0x2a10d  call     instance class Microsoft.Crm.IFeatureDetail Microsoft.Crm.FeatureDetailContainer::AddOfflineOrgFeature(string name, valuetype Microsoft.Crm.FeatureType featureType, valuetype Microsoft.Crm.SharedDatabase.ConfigSku configSku, class Microsoft.Crm.IFeatureDetail parentFeature, class Microsoft.Crm.FeatureVersionDetail[] versionDetails)
0x2a112  pop
0x2a113  ldarg.0
0x2a114  ldstr    aFcbEditablegri// "FCB.EditableGridControlPbl"
0x2a119  ldc.i4.0
0x2a11a  ldc.i4.7
0x2a11b  ldnull
0x2a11c  ldc.i4.1
0x2a11d  newarr   Microsoft.Crm.FeatureVersionDetail
0x2a122  dup
0x2a123  ldc.i4.0
0x2a124  newobj   instance void Microsoft.Crm.FeatureVersionDetail::.ctor()
0x2a129  dup
0x2a12a  ldarg.0
0x2a12b  ldfld    class [mscorlib]System.Version Microsoft.Crm.FeatureDetailContainer::CentaurusVersion
0x2a130  callvirt instance void Microsoft.Crm.FeatureVersionDetail::set_MinimumOrgDBVersion(class [mscorlib]System.Version value)
0x2a135  dup
0x2a136  ldc.i4.1
0x2a137  callvirt instance void Microsoft.Crm.FeatureVersionDetail::set_DefaultValue(bool value)
0x2a13c  stelem.ref
0x2a13d  call     instance class Microsoft.Crm.IFeatureDetail Microsoft.Crm.FeatureDetailContainer::AddOfflineOrgFeature(string name, valuetype Microsoft.Crm.FeatureType featureType, valuetype Microsoft.Crm.SharedDatabase.ConfigSku configSku, class Microsoft.Crm.IFeatureDetail parentFeature, class Microsoft.Crm.FeatureVersionDetail[] versionDetails)
0x2a142  pop
0x2a143  ldarg.0
0x2a144  ldstr    aFcbEditablegri_0// "FCB.EditableGridControlJsEvents"
0x2a149  ldc.i4.0
0x2a14a  ldc.i4.7
0x2a14b  ldnull
0x2a14c  ldc.i4.1
0x2a14d  newarr   Microsoft.Crm.FeatureVersionDetail
0x2a152  dup
0x2a153  ldc.i4.0
0x2a154  newobj   instance void Microsoft.Crm.FeatureVersionDetail::.ctor()
0x2a159  dup
0x2a15a  ldarg.0
0x2a15b  ldfld    class [mscorlib]System.Version Microsoft.Crm.FeatureDetailContainer::CentaurusVersion
0x2a160  callvirt instance void Microsoft.Crm.FeatureVersionDetail::set_MinimumOrgDBVersion(class [mscorlib]System.Version value)
0x2a165  dup
0x2a166  ldc.i4.1
0x2a167  callvirt instance void Microsoft.Crm.FeatureVersionDetail::set_DefaultValue(bool value)
0x2a16c  stelem.ref
0x2a16d  call     instance class Microsoft.Crm.IFeatureDetail Microsoft.Crm.FeatureDetailContainer::AddOfflineOrgFeature(string name, valuetype Microsoft.Crm.FeatureType featureType, valuetype Microsoft.Crm.SharedDatabase.ConfigSku configSku, class Microsoft.Crm.IFeatureDetail parentFeature, class Microsoft.Crm.FeatureVersionDetail[] versionDetails)
0x2a172  pop
0x2a173  ldarg.0
0x2a174  ldstr    aFcbDatasetcont// "FCB.DataSetControl"
0x2a179  ldc.i4.0
0x2a17a  ldc.i4.7
0x2a17b  ldnull
0x2a17c  ldc.i4.1
0x2a17d  newarr   Microsoft.Crm.FeatureVersionDetail
0x2a182  dup
0x2a183  ldc.i4.0
0x2a184  newobj   instance void Microsoft.Crm.FeatureVersionDetail::.ctor()
0x2a189  dup
0x2a18a  ldarg.0
0x2a18b  ldfld    class [mscorlib]System.Version Microsoft.Crm.FeatureDetailContainer::CentaurusVersion
0x2a190  callvirt instance void Microsoft.Crm.FeatureVersionDetail::set_MinimumOrgDBVersion(class [mscorlib]System.Version value)
0x2a195  dup
0x2a196  ldc.i4.1
0x2a197  callvirt instance void Microsoft.Crm.FeatureVersionDetail::set_DefaultValue(bool value)
0x2a19c  stelem.ref
0x2a19d  call     instance class Microsoft.Crm.IFeatureDetail Microsoft.Crm.FeatureDetailContainer::AddOfflineOrgFeature(string name, valuetype Microsoft.Crm.FeatureType featureType, valuetype Microsoft.Crm.SharedDatabase.ConfigSku configSku, class Microsoft.Crm.IFeatureDetail parentFeature, class Microsoft.Crm.FeatureVersionDetail[] versionDetails)
0x2a1a2  pop
0x2a1a3  ldarg.0
0x2a1a4  ldstr    aFcbMocaOffline// "FCB.Moca.Offline"
0x2a1a9  ldc.i4.2
0x2a1aa  ldc.i4.7
0x2a1ab  ldc.i4.1
  ... truncated ...
```
