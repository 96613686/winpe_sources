# Microsoft.Crm.Asynchronous.IndexManagementOperation::DoIndexManagement

- ea: `0x3b60`
- end: `0x3d92`
- name: `Microsoft.Crm.Asynchronous.IndexManagementOperation::DoIndexManagement`
- size: `562`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0xe1f0`

## callees

- `0x3790`

## string_xrefs

- `0x3bd4`: `  Completed Execution: QuickFindIndexUtility.ProcessIndexesForAllEntities`
- `0x3c1e`: `  Started Execution: ForeignKeyManagementService.FindMissedIndexesOnForeignKeys`
- `0x3c62`: `  Completed Execution: ForeignKeyManagementService.FindMissedIndexesOnForeignKeys`
- `0x3ca0`: `  Started Execution: ForeignKeyManagementService.RecreateAllForeignKeyConstraints`
- `0x3ce8`: `  Completed Execution: ForeignKeyManagementService.RecreateAllForeignKeyConstraints`
- `0x3d26`: `  Started Execution: IndexAndConstraintManagementService.Instance.RecreateAllIndexes`
- `0x3d73`: `  Completed Execution: IndexAndConstraintManagementService.Instance.RecreateAllIndexes`

## pseudocode

```c

```

## disassembly

```asm
0x3b60  ldarg.0
0x3b61  call     instance class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEventHandlerCommand::get_Configuration()
0x3b66  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration::get_OrganizationId()
0x3b6b  stloc.0
0x3b6c  newobj   instance void [System]System.Diagnostics.Stopwatch::.ctor()
0x3b71  stloc.1
0x3b72  call     class [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.IndexManagementOperationEventSource [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.IndexManagementOperationEventSource::get_Instance()
0x3b77  ldloc.0
0x3b78  ldstr    aIndexmanagemen_2// "IndexManagementOperation.DoIndexManagem"...
0x3b7d  ldstr    aSqlconenctionS// "SQLConenction State: "
0x3b82  ldarg.1
0x3b83  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_Connection()
0x3b88  callvirt instance valuetype [System.Data]System.Data.ConnectionState [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::get_State()
0x3b8d  box      [System.Data]System.Data.ConnectionState
0x3b92  ldstr    aStartedExecuti_0// "  Started Execution: QuickFindIndexUtil"...
0x3b97  call     string [mscorlib]System.String::Concat(object, object, object)
0x3b9c  ldc.i4.m1
0x3b9d  callvirt instance void [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.IndexManagementOperationEventSource::IndexManagementServiceInformation(valuetype [mscorlib]System.Guid, string, string, int32)
0x3ba2  ldloc.1
0x3ba3  callvirt instance void [System]System.Diagnostics.Stopwatch::Start()
0x3ba8  ldarg.1
0x3ba9  call     void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.QuickFindIndexUtility::ProcessIndexesForAllEntities(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x3bae  ldloc.1
0x3baf  callvirt instance void [System]System.Diagnostics.Stopwatch::Stop()
0x3bb4  call     class [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.IndexManagementOperationEventSource [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.IndexManagementOperationEventSource::get_Instance()
0x3bb9  ldloc.0
0x3bba  ldstr    aIndexmanagemen_2// "IndexManagementOperation.DoIndexManagem"...
0x3bbf  ldstr    aSqlconenctionS// "SQLConenction State: "
0x3bc4  ldarg.1
0x3bc5  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_Connection()
0x3bca  callvirt instance valuetype [System.Data]System.Data.ConnectionState [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::get_State()
0x3bcf  box      [System.Data]System.Data.ConnectionState
0x3bd4  ldstr    aCompletedExecu_0// "  Completed Execution: QuickFindIndexUt"...
0x3bd9  call     string [mscorlib]System.String::Concat(object, object, object)
0x3bde  ldloc.1
0x3bdf  callvirt instance valuetype [mscorlib]System.TimeSpan [System]System.Diagnostics.Stopwatch::get_Elapsed()
0x3be4  stloc.3
0x3be5  ldloca.s 3
0x3be7  call     instance float64 [mscorlib]System.TimeSpan::get_TotalSeconds()
0x3bec  conv.i4
0x3bed  callvirt instance void [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.IndexManagementOperationEventSource::IndexManagementServiceInformation(valuetype [mscorlib]System.Guid, string, string, int32)
0x3bf2  ldarg.1
0x3bf3  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x3bf8  newobj   instance void Microsoft.Crm.Asynchronous.MetadataCacheIndexMetadataProvider::.ctor(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache metadataCache)
0x3bfd  stloc.2
0x3bfe  call     class [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.IndexManagementOperationEventSource [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.IndexManagementOperationEventSource::get_Instance()
0x3c03  ldloc.0
0x3c04  ldstr    aIndexmanagemen_2// "IndexManagementOperation.DoIndexManagem"...
0x3c09  ldstr    aSqlconenctionS// "SQLConenction State: "
0x3c0e  ldarg.1
0x3c0f  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_Connection()
0x3c14  callvirt instance valuetype [System.Data]System.Data.ConnectionState [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::get_State()
0x3c19  box      [System.Data]System.Data.ConnectionState
0x3c1e  ldstr    aStartedExecuti_1// "  Started Execution: ForeignKeyManageme"...
0x3c23  call     string [mscorlib]System.String::Concat(object, object, object)
0x3c28  ldc.i4.m1
0x3c29  callvirt instance void [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.IndexManagementOperationEventSource::IndexManagementServiceInformation(valuetype [mscorlib]System.Guid, string, string, int32)
0x3c2e  ldloc.1
0x3c2f  callvirt instance void [System]System.Diagnostics.Stopwatch::Restart()
0x3c34  ldloc.2
0x3c35  ldarg.1
0x3c36  call     int32 [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.ForeignKeyManagementService::FindMissedIndexesOnForeignKeys(class [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.IIndexMetadataProvider, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x3c3b  pop
0x3c3c  ldloc.1
0x3c3d  callvirt instance void [System]System.Diagnostics.Stopwatch::Stop()
0x3c42  call     class [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.IndexManagementOperationEventSource [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.IndexManagementOperationEventSource::get_Instance()
0x3c47  ldloc.0
0x3c48  ldstr    aIndexmanagemen_2// "IndexManagementOperation.DoIndexManagem"...
0x3c4d  ldstr    aSqlconenctionS// "SQLConenction State: "
0x3c52  ldarg.1
0x3c53  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_Connection()
0x3c58  callvirt instance valuetype [System.Data]System.Data.ConnectionState [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::get_State()
0x3c5d  box      [System.Data]System.Data.ConnectionState
0x3c62  ldstr    aCompletedExecu_1// "  Completed Execution: ForeignKeyManage"...
0x3c67  call     string [mscorlib]System.String::Concat(object, object, object)
0x3c6c  ldloc.1
0x3c6d  callvirt instance valuetype [mscorlib]System.TimeSpan [System]System.Diagnostics.Stopwatch::get_Elapsed()
0x3c72  stloc.3
0x3c73  ldloca.s 3
0x3c75  call     instance float64 [mscorlib]System.TimeSpan::get_TotalSeconds()
0x3c7a  conv.i4
0x3c7b  callvirt instance void [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.IndexManagementOperationEventSource::IndexManagementServiceInformation(valuetype [mscorlib]System.Guid, string, string, int32)
0x3c80  call     class [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.IndexManagementOperationEventSource [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.IndexManagementOperationEventSource::get_Instance()
0x3c85  ldloc.0
0x3c86  ldstr    aIndexmanagemen_2// "IndexManagementOperation.DoIndexManagem"...
0x3c8b  ldstr    aSqlconenctionS// "SQLConenction State: "
0x3c90  ldarg.1
0x3c91  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_Connection()
0x3c96  callvirt instance valuetype [System.Data]System.Data.ConnectionState [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::get_State()
0x3c9b  box      [System.Data]System.Data.ConnectionState
0x3ca0  ldstr    aStartedExecuti_2// "  Started Execution: ForeignKeyManageme"...
0x3ca5  call     string [mscorlib]System.String::Concat(object, object, object)
0x3caa  ldc.i4.m1
0x3cab  callvirt instance void [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.IndexManagementOperationEventSource::IndexManagementServiceInformation(valuetype [mscorlib]System.Guid, string, string, int32)
0x3cb0  ldloc.1
0x3cb1  callvirt instance void [System]System.Diagnostics.Stopwatch::Restart()
0x3cb6  ldloc.2
0x3cb7  ldarg.1
0x3cb8  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_SqlContext()
0x3cbd  call     void [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.ForeignKeyManagementService::RecreateAllForeignKeyConstraints(class [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.IIndexMetadataProvider, class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext)
0x3cc2  ldloc.1
0x3cc3  callvirt instance void [System]System.Diagnostics.Stopwatch::Stop()
0x3cc8  call     class [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.IndexManagementOperationEventSource [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.IndexManagementOperationEventSource::get_Instance()
0x3ccd  ldloc.0
0x3cce  ldstr    aIndexmanagemen_2// "IndexManagementOperation.DoIndexManagem"...
0x3cd3  ldstr    aSqlconenctionS// "SQLConenction State: "
0x3cd8  ldarg.1
0x3cd9  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_Connection()
0x3cde  callvirt instance valuetype [System.Data]System.Data.ConnectionState [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::get_State()
0x3ce3  box      [System.Data]System.Data.ConnectionState
0x3ce8  ldstr    aCompletedExecu_2// "  Completed Execution: ForeignKeyManage"...
0x3ced  call     string [mscorlib]System.String::Concat(object, object, object)
0x3cf2  ldloc.1
0x3cf3  callvirt instance valuetype [mscorlib]System.TimeSpan [System]System.Diagnostics.Stopwatch::get_Elapsed()
0x3cf8  stloc.3
0x3cf9  ldloca.s 3
0x3cfb  call     instance float64 [mscorlib]System.TimeSpan::get_TotalSeconds()
0x3d00  conv.i4
0x3d01  callvirt instance void [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.IndexManagementOperationEventSource::IndexManagementServiceInformation(valuetype [mscorlib]System.Guid, string, string, int32)
0x3d06  call     class [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.IndexManagementOperationEventSource [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.IndexManagementOperationEventSource::get_Instance()
0x3d0b  ldloc.0
0x3d0c  ldstr    aIndexmanagemen_2// "IndexManagementOperation.DoIndexManagem"...
0x3d11  ldstr    aSqlconenctionS// "SQLConenction State: "
0x3d16  ldarg.1
0x3d17  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_Connection()
0x3d1c  callvirt instance valuetype [System.Data]System.Data.ConnectionState [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::get_State()
0x3d21  box      [System.Data]System.Data.ConnectionState
0x3d26  ldstr    aStartedExecuti_3// "  Started Execution: IndexAndConstraint"...
0x3d2b  call     string [mscorlib]System.String::Concat(object, object, object)
0x3d30  ldc.i4.m1
0x3d31  callvirt instance void [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.IndexManagementOperationEventSource::IndexManagementServiceInformation(valuetype [mscorlib]System.Guid, string, string, int32)
0x3d36  ldloc.1
0x3d37  callvirt instance void [System]System.Diagnostics.Stopwatch::Restart()
0x3d3c  call     class [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.IndexAndConstraintManagementService [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.IndexAndConstraintManagementService::get_Instance()
0x3d41  ldloc.2
0x3d42  ldarg.1
0x3d43  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_SqlContext()
0x3d48  callvirt instance void [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.IndexAndConstraintManagementService::RecreateAllIndexes(class [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.IIndexMetadataProvider, class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext)
0x3d4d  ldloc.1
0x3d4e  callvirt instance void [System]System.Diagnostics.Stopwatch::Stop()
0x3d53  call     class [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.IndexManagementOperationEventSource [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.IndexManagementOperationEventSource::get_Instance()
0x3d58  ldloc.0
0x3d59  ldstr    aIndexmanagemen_2// "IndexManagementOperation.DoIndexManagem"...
0x3d5e  ldstr    aSqlconenctionS// "SQLConenction State: "
0x3d63  ldarg.1
0x3d64  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_Connection()
0x3d69  callvirt instance valuetype [System.Data]System.Data.ConnectionState [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::get_State()
0x3d6e  box      [System.Data]System.Data.ConnectionState
0x3d73  ldstr    aCompletedExecu_3// "  Completed Execution: IndexAndConstrai"...
0x3d78  call     string [mscorlib]System.String::Concat(object, object, object)
0x3d7d  ldloc.1
0x3d7e  callvirt instance valuetype [mscorlib]System.TimeSpan [System]System.Diagnostics.Stopwatch::get_Elapsed()
0x3d83  stloc.3
0x3d84  ldloca.s 3
0x3d86  call     instance float64 [mscorlib]System.TimeSpan::get_TotalSeconds()
0x3d8b  conv.i4
0x3d8c  callvirt instance void [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.IndexManagementOperationEventSource::IndexManagementServiceInformation(valuetype [mscorlib]System.Guid, string, string, int32)
0x3d91  ret
```
