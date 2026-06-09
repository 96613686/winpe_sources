# Microsoft.Crm.ObjectModel.RibbonMetadata.RibbonClientMetadataHelper::DoSafeCacheFlushBeforeRibbonMDGeneration

- ea: `0x1eb620`
- end: `0x1eb72e`
- name: `Microsoft.Crm.ObjectModel.RibbonMetadata.RibbonClientMetadataHelper::DoSafeCacheFlushBeforeRibbonMDGeneration`
- size: `270`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x13c070`
- `0x1995a0`

## callees

- `0x1eb570`
- `0x1eb5f0`
- `0x1eb620`

## string_xrefs

- `0x1eb620`: `MetadataCache`
- `0x1eb62c`: `CustomControlResourceCache`
- `0x1eb63d`: `DependenciesCache`
- `0x1eb64e`: `WebResourceInfoCache`
- `0x1eb65f`: `WebResourceDependencyCache`
- `0x1eb670`: `WebResourceResxCache`
- `0x1eb681`: `RibbonCommandCache`
- `0x1eb692`: `RibbonRuleCache`
- `0x1eb6a3`: `RibbonTabDisplayCache`
- `0x1eb6b4`: `RibbonTabCommandMapCache`
- `0x1eb6c5`: `RibbonDiffCache`
- `0x1eb6d6`: `RibbonContextGroupCache`
- `0x1eb6e7`: `LabelCache`
- `0x1eb700`: `RibbonClientMetadataCache`
- `0x1eb714`: `DoSafeCacheFlushBeforeRibbonMDGeneration: Caught Exception during cache Flush:{0}`

## pseudocode

```c

```

## disassembly

```asm
0x1eb620  ldstr    aMetadatacache// "MetadataCache"
0x1eb625  stloc.0
0x1eb626  ldarg.0
0x1eb627  call     void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::Flush(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x1eb62c  ldstr    aCustomcontrolr_1// "CustomControlResourceCache"
0x1eb631  stloc.0
0x1eb632  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.CustomControlResourceCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.CustomControlResourceCache::Instance()
0x1eb637  ldarg.0
0x1eb638  callvirt instance void class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.CrmMultiOrgCacheBase`2<string, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.CustomControlResourceCacheData>::Flush(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x1eb63d  ldstr    aDependenciesca// "DependenciesCache"
0x1eb642  stloc.0
0x1eb643  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.DependenciesCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.DependenciesCache::Instance()
0x1eb648  ldarg.0
0x1eb649  callvirt instance void class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.CrmMultiOrgCacheBase`2<int32, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.DependenciesCacheData>::Flush(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x1eb64e  ldstr    aWebresourceinf// "WebResourceInfoCache"
0x1eb653  stloc.0
0x1eb654  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.WebResourceInfoCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.WebResourceInfoCache::Instance()
0x1eb659  ldarg.0
0x1eb65a  callvirt instance void class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.CrmMultiOrgCacheBase`2<string, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.WebResourceInfoCacheData>::Flush(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x1eb65f  ldstr    aWebresourcedep_0// "WebResourceDependencyCache"
0x1eb664  stloc.0
0x1eb665  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.WebResourceDependencyCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.WebResourceDependencyCache::Instance()
0x1eb66a  ldarg.0
0x1eb66b  callvirt instance void class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.CrmMultiOrgCacheBase`2<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IWebResourceDependencyCacheKey, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IWebResourceDependencyCacheValue>::Flush(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x1eb670  ldstr    aWebresourceres// "WebResourceResxCache"
0x1eb675  stloc.0
0x1eb676  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.WebResourceResxCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.WebResourceResxCache::Instance()
0x1eb67b  ldarg.0
0x1eb67c  callvirt instance void class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.CrmMultiOrgCacheBase`2<int32, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.WebResourceResxCacheData>::Flush(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x1eb681  ldstr    aRibboncommandc// "RibbonCommandCache"
0x1eb686  stloc.0
0x1eb687  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.RibbonCommandCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.RibbonCommandCache::get_InstanceForBatchLoading()
0x1eb68c  ldarg.0
0x1eb68d  callvirt instance void class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.CrmMultiOrgCacheBase`2<string, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.RibbonCommandsCacheValue>::Flush(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x1eb692  ldstr    aRibbonrulecach// "RibbonRuleCache"
0x1eb697  stloc.0
0x1eb698  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.RibbonRuleCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.RibbonRuleCache::get_InstanceForBatchLoading()
0x1eb69d  ldarg.0
0x1eb69e  callvirt instance void class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.CrmMultiOrgCacheBase`2<string, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.RibbonRulesCacheValue>::Flush(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x1eb6a3  ldstr    aRibbontabdispl// "RibbonTabDisplayCache"
0x1eb6a8  stloc.0
0x1eb6a9  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.RibbonTabDisplayCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.RibbonTabDisplayCache::get_InstanceForBatchLoading()
0x1eb6ae  ldarg.0
0x1eb6af  callvirt instance void class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.CrmMultiOrgCacheBase`2<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.RibbonTabDisplayCacheKey, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.RibbonTabDisplayCacheValue>::Flush(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x1eb6b4  ldstr    aRibbontabcomma// "RibbonTabCommandMapCache"
0x1eb6b9  stloc.0
0x1eb6ba  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.RibbonTabCommandMapCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.RibbonTabCommandMapCache::get_Instance()
0x1eb6bf  ldarg.0
0x1eb6c0  callvirt instance void class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.CrmMultiOrgCacheBase`2<string, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.RibbonTabsCommandMapCacheValue>::Flush(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x1eb6c5  ldstr    aRibbondiffcach// "RibbonDiffCache"
0x1eb6ca  stloc.0
0x1eb6cb  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.RibbonDiffCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.RibbonDiffCache::get_Instance()
0x1eb6d0  ldarg.0
0x1eb6d1  callvirt instance void class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.CrmMultiOrgCacheBase`2<string, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.RibbonDiffsCacheValue>::Flush(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x1eb6d6  ldstr    aRibboncontextg_1// "RibbonContextGroupCache"
0x1eb6db  stloc.0
0x1eb6dc  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.RibbonContextGroupCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.RibbonContextGroupCache::get_Instance()
0x1eb6e1  ldarg.0
0x1eb6e2  callvirt instance void class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.CrmMultiOrgCacheBase`2<string, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.RibbonContextGroupsCacheValue>::Flush(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x1eb6e7  ldstr    aLabelcache// "LabelCache"
0x1eb6ec  stloc.0
0x1eb6ed  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LabelCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LabelCache::Instance()
0x1eb6f2  ldarg.0
0x1eb6f3  ldc.i4.1
0x1eb6f4  ldc.i4.0
0x1eb6f5  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LabelCache::Flush(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext, bool, bool)
0x1eb6fa  ldarg.0
0x1eb6fb  call     void Microsoft.Crm.ObjectModel.RibbonMetadata.RibbonClientMetadataHelper::DeleteRibbonTemplateFromDB(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x1eb700  ldstr    aRibbonclientme_4// "RibbonClientMetadataCache"
0x1eb705  stloc.0
0x1eb706  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.RibbonClientMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.RibbonClientMetadataCache::get_Instance()
0x1eb70b  ldarg.0
0x1eb70c  callvirt instance void class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.CrmMultiOrgCacheBase`2<string, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.RibbonClientMetadataCacheValue>::Flush(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x1eb711  leave.s  loc_1EB72D
0x1eb713  stloc.1
0x1eb714  ldstr    aDosafecacheflu// "DoSafeCacheFlushBeforeRibbonMDGeneratio"...
0x1eb719  ldloc.0
0x1eb71a  call     string [mscorlib]System.String::Format(string, object)
0x1eb71f  ldc.i4.1
0x1eb720  ldloc.1
0x1eb721  call     void Microsoft.Crm.ObjectModel.RibbonMetadata.RibbonClientMetadataHelper::LogCrmTraceAndLoggerMessage(string message, bool error, [opt] class [mscorlib]System.Exception exception)
0x1eb726  ldarg.1
0x1eb727  brfalse.s loc_1EB72B
0x1eb729  ldloc.1
0x1eb72a  throw
0x1eb72b  leave.s  loc_1EB72D
0x1eb72d  ret
```
