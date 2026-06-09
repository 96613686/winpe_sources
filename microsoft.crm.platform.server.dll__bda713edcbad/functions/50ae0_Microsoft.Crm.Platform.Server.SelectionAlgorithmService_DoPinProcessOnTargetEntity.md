# Microsoft.Crm.Platform.Server.SelectionAlgorithmService::DoPinProcessOnTargetEntity

- ea: `0x50ae0`
- end: `0x50bad`
- name: `Microsoft.Crm.Platform.Server.SelectionAlgorithmService::DoPinProcessOnTargetEntity`
- size: `205`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x4ffa0`

## callees

- `0x4ccd0`
- `0x4dc10`
- `0x4dc20`
- `0x4dc40`
- `0x4dc50`
- `0x4df40`
- `0x4e290`
- `0x4e880`
- `0x4edf0`
- `0x50ae0`
- `0x78330`

## string_xrefs

- `0x50b84`: `processid`
- `0x50b91`: `processid`

## pseudocode

```c

```

## disassembly

```asm
0x50ae0  ldarg.0
0x50ae1  ldfld    class Microsoft.Crm.Platform.Server.IBusinessProcessFlowFactory Microsoft.Crm.Platform.Server.SelectionAlgorithmService::businessProcessFlowFactory
0x50ae6  ldarg.3
0x50ae7  callvirt instance class Microsoft.Crm.Platform.Server.IProcessUnificationFeature Microsoft.Crm.Platform.Server.IBusinessProcessFlowFactory::CreateProcessUnificationFeature(class Microsoft.Crm.Platform.Server.IExecutionContext executionContext)
0x50aec  callvirt instance bool Microsoft.Crm.Platform.Server.IProcessUnificationFeature::get_FeatureEnabled()
0x50af1  brtrue.s loc_50AF4
0x50af3  ret
0x50af4  ldstr    aUserentityuise// "UserEntityUISettings"
0x50af9  ldarg.3
0x50afa  callvirt instance class Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Platform.Server.IExecutionContext::get_Instance()
0x50aff  call     class Microsoft.Crm.BusinessEntities.BusinessProcessObject Microsoft.Crm.BusinessEntities.ServiceClassFactory::CreateInstance(string entityName, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext orgContext)
0x50b04  stloc.0
0x50b05  ldarg.0
0x50b06  ldfld    class Microsoft.Crm.Platform.Server.IBusinessProcessFlowFactory Microsoft.Crm.Platform.Server.SelectionAlgorithmService::businessProcessFlowFactory
0x50b0b  ldarg.3
0x50b0c  callvirt instance class Microsoft.Crm.Platform.Server.ILocalizationSettings Microsoft.Crm.Platform.Server.IBusinessProcessFlowFactory::CreateLocalizationSettings(class Microsoft.Crm.Platform.Server.IExecutionContext executionContext)
0x50b11  stloc.1
0x50b12  ldarg.0
0x50b13  ldfld    class Microsoft.Crm.Platform.Server.IBusinessProcessFlowFactory Microsoft.Crm.Platform.Server.SelectionAlgorithmService::businessProcessFlowFactory
0x50b18  ldarg.3
0x50b19  callvirt instance class Microsoft.Crm.Platform.Server.IDynamicMetadataCache Microsoft.Crm.Platform.Server.IBusinessProcessFlowFactory::CreateMetadataCache(class Microsoft.Crm.Platform.Server.IExecutionContext executionContext)
0x50b1e  stloc.2
0x50b1f  ldarg.3
0x50b20  ldloc.1
0x50b21  ldloc.2
0x50b22  ldarg.0
0x50b23  ldfld    class Microsoft.Crm.Platform.Server.IRecentlyViewedRecordComparer Microsoft.Crm.Platform.Server.SelectionAlgorithmService::recentlyViewedRecordComparer
0x50b28  ldarg.0
0x50b29  ldfld    class Microsoft.Crm.Platform.Server.IRecentlyViewedRecordSerializer Microsoft.Crm.Platform.Server.SelectionAlgorithmService::recentlyViewedRecordSerializer
0x50b2e  newobj   instance void Microsoft.Crm.Platform.Server.RecentlyViewedListBuilder::.ctor(class Microsoft.Crm.Platform.Server.IExecutionContext context, class Microsoft.Crm.Platform.Server.ILocalizationSettings localizationSettings, class Microsoft.Crm.Platform.Server.IDynamicMetadataCache metadataCache, class Microsoft.Crm.Platform.Server.IRecentlyViewedRecordComparer comparer, class Microsoft.Crm.Platform.Server.IRecentlyViewedRecordSerializer serializer)
0x50b33  stloc.3
0x50b34  ldarg.3
0x50b35  ldloc.2
0x50b36  ldloc.0
0x50b37  ldloc.3
0x50b38  ldarg.0
0x50b39  ldfld    class Microsoft.Crm.Platform.Server.IBusinessProcessFlowFactory Microsoft.Crm.Platform.Server.SelectionAlgorithmService::businessProcessFlowFactory
0x50b3e  newobj   instance void Microsoft.Crm.Platform.Server.UserEntityUISettingsServiceAdapter::.ctor(class Microsoft.Crm.Platform.Server.IExecutionContext context, class Microsoft.Crm.Platform.Server.IDynamicMetadataCache metadataCache, class Microsoft.Crm.BusinessEntities.IBusinessProcessObject service, class Microsoft.Crm.Platform.Server.IRecentlyViewedListBuilder recentlyViewedListBuilder, class Microsoft.Crm.Platform.Server.IBusinessProcessFlowFactory businessProcessFlowFactory)
0x50b43  stloc.s  4
0x50b45  ldarg.0
0x50b46  ldfld    class Microsoft.Crm.Platform.Server.IBusinessProcessFlowFactory Microsoft.Crm.Platform.Server.SelectionAlgorithmService::businessProcessFlowFactory
0x50b4b  ldarg.3
0x50b4c  ldloc.s  4
0x50b4e  callvirt instance class Microsoft.Crm.Platform.Server.IRecentlyViewedProcessService Microsoft.Crm.Platform.Server.IBusinessProcessFlowFactory::CreateRecentlyViewedProcessService(class Microsoft.Crm.Platform.Server.IExecutionContext executionContext, class Microsoft.Crm.Platform.Server.IUserEntityUISettingsService userEntityUiSettingsService)
0x50b53  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x50b58  stloc.s  5
0x50b5a  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x50b5f  stloc.s  6
0x50b61  ldarg.1
0x50b62  brfalse.s loc_50BA2
0x50b64  ldarg.1
0x50b65  ldstr    aBusinessproces_0// "businessprocessflowinstanceid"
0x50b6a  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::IsAttributeNull(string)
0x50b6f  brtrue.s loc_50B83
0x50b71  ldarg.1
0x50b72  ldstr    aBusinessproces_0// "businessprocessflowinstanceid"
0x50b77  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0x50b7c  unbox.any [mscorlib]System.Guid
0x50b81  stloc.s  5
0x50b83  ldarg.1
0x50b84  ldstr    aProcessid// "processid"
0x50b89  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::IsAttributeNull(string)
0x50b8e  brtrue.s loc_50BA2
0x50b90  ldarg.1
0x50b91  ldstr    aProcessid// "processid"
0x50b96  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0x50b9b  unbox.any [mscorlib]System.Guid
0x50ba0  stloc.s  6
0x50ba2  ldloc.s  5
0x50ba4  ldloc.s  6
0x50ba6  ldarg.2
0x50ba7  callvirt instance void Microsoft.Crm.Platform.Server.IRecentlyViewedProcessService::PinProcessForTargetEntityRecord(valuetype [mscorlib]System.Guid processInstanceId, valuetype [mscorlib]System.Guid processId, class Microsoft.Crm.Platform.Server.IEntityReference targetEntity)
0x50bac  ret
```
