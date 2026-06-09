# Microsoft.Crm.Admin.AdminService.CrmDeploymentService::AddDefaults

- ea: `0x2f830`
- end: `0x3098e`
- name: `Microsoft.Crm.Admin.AdminService.CrmDeploymentService::AddDefaults`
- size: `4446`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x2f320`

## callees

- `0x2f830`
- `0x30990`
- `0x309c0`

## string_xrefs

- `0x30359`: `SqlCommandTimeout`
- `0x2f84c`: `AsyncMoveToReadyInterval`
- `0x2f8cf`: `AsyncMaximumThreadsPercent`
- `0x2f8e8`: `AsyncMaximumThreadsPerCPU`
- `0x2f91d`: `AsyncStateStatusUpdateInterval`
- `0x2f92e`: `AsyncStateStatusUpdateMaxRetryCount`
- `0x2f9e1`: `ImportCountUpdateBatchSize`
- `0x2fa77`: `DumpChartXmlInResponse`
- `0x2fb04`: `DTATemplate`
- `0x2fb09`: `<?xml version='1.0' encoding='utf-16' ?>\n<DTAXML xmlns:xsi='http://www.w3.org/2001/XMLSchema-instance' xmlns='http://schemas.microsoft.com/sqlserver/2004/07/dta'>\n  <DTAInput>\n	<Server>\n	  <Name>{0}</Name>\n	  <Database>\n		<Name>{1}</Name>\n	  </Database>\n	</Server>\n	<Workload>\n	  <File>{2}</File>\n	</Workload>\n	<TuningOptions>\n	  <TuningTimeInMin>5</TuningTimeInMin>\n	  <FeatureSet>IDX_IV</FeatureSet>\n	  <Partitioning>NONE</Partitioning>\n	  <KeepExisting>ALL</KeepExi`
- `0x2fbb0`: `Default=1;DeletionService=5;IndexManagement=3;DatabaseLogBackup=25;ShrinkLogFile=7;ReindexAll=4;CleanupInactiveWorkflowAssemblies=1;CalculateOrgStorageSize=2;OrgDBUpdate=100;OptInFcbOrgSync=200;SolutionUpdate=90;`
- `0x2fbc0`: `Default=1;DeletionService=1;IndexManagement=2;DatabaseLogBackup=2;ShrinkLogFile=1;ReindexAll=2;CleanupInactiveWorkflowAssemblies=2;OrgDBUpdate=2;OptInFcbOrgSync=1;SolutionUpdate=1;CheckForLanguagePackUpdates=2;CheckFullTextIndexColumnStatus=2;`
- `0x2fbdd`: `ECMessageIDCacheCapacity`
- `0x2ffc2`: `ECMessageIDCacheCapacity`
- `0x2fbf2`: `ECMessageIDCacheRetentionTime`
- `0x2ffd7`: `ECMessageIDCacheRetentionTime`
- `0x2fc7d`: `ETMStatisticsUpdateEnabled`
- `0x2fd32`: `ETMStatisticsUpdateEnabled`
- `0x2fc8e`: `AsyncThrottlingConfiguration`
- `0x2fc93`: `BulkDelete=15;Parse=15;Transform=15;Import=15;ImportingFile=15;GoalRollup=15;ExecuteSdkMessage=3;ImportTranslation=15;IncrementalRollup=10;BootstrapRollup=10;ConvertDateAndTimeBehavior=5`
- `0x2fc9e`: `AsyncItemsInMemoryHigh`
- `0x2fd43`: `AsyncItemsInMemoryHigh`
- `0x2fcb3`: `AsyncItemsInMemoryLow`
- `0x2fd58`: `AsyncItemsInMemoryLow`
- `0x2fd8f`: `ActivityQueueItemsInMemoryHigh`
- `0x2fdca`: `ActivityQueueItemsInMemoryHigh`
- `0x2fda4`: `ActivityQueueItemsInMemoryLow`
- `0x2fddf`: `ActivityQueueItemsInMemoryLow`
- `0x2fe06`: `ActivityQueueMaximumThreadsPercent`
- `0x2fe1f`: `ActivityQueueMaximumThreadsPerCPU`
- `0x2fe98`: `MailboxQueueItemsInMemoryHigh`
- `0x2fed3`: `MailboxQueueItemsInMemoryHigh`
- `0x2fead`: `MailboxQueueItemsInMemoryLow`
- `0x2fee8`: `MailboxQueueItemsInMemoryLow`
- `0x2ff0f`: `MailboxQueueMaximumThreadsPercent`
- `0x2ff28`: `MailboxQueueMaximumThreadsPerCPU`
- `0x2ff9d`: `ETMProviderConfiguration`
- `0x2ffe9`: `ECMaximumEmailDeliveryAttempts`
- `0x3000d`: `ECIncomingMaximumEmailsPerCycle`
- `0x300af`: `ECIncomingEmailMaximumSizeLimit`
- `0x300d9`: `ECIncomingEmailExchangeEmailRetrievalBatchSize`
- `0x30153`: `ECTestEmailConfigurationRetryInterval`
- `0x30194`: `ECAllowADBasedAuthenticationProtocols`
- `0x30207`: `ECAllowADBasedAuthenticationProtocols`
- `0x301a5`: `S2SActAsAccessTokenLifetime`
- `0x30218`: `S2SActAsAccessTokenLifetime`
- `0x301b7`: `S2SSelfIssuedAccessTokenLifetime`
- `0x3022a`: `S2SSelfIssuedAccessTokenLifetime`
- `0x301c9`: `S2SAccessTokenMinimumAllowedRemainingLifetime`
- `0x3023c`: `S2SAccessTokenMinimumAllowedRemainingLifetime`
- `0x301db`: `S2SAccessTokenMaximumAllowedElapsedLifetime`
- `0x3024e`: `S2SAccessTokenMaximumAllowedElapsedLifetime`
- `0x303af`: `ClaimsSessionSecurityTokenLifetime`
- `0x303d2`: `IfdIntranetAccessEnabled`
- `0x304b0`: `QueryTemplate=%27((NOT+(HideFromDelve%3aTrue+OR+OnHold%3aTrue))+AND+(NOT+(Title%3aOneNote_DeletedPages+OR+Title%3aOneNote_RecycleBin+OR+ContentClass%3aSTS_ListItem_Categories+OR+ContentClass%3aSTS_ListItem_852+OR+SecondaryFileExtension%3aonetoc2+OR+ContentType%3aFolder+OR+ContentClass%3aSTS_ListItem_Tasks+OR+ContentClass%3aSTS_ListItem_GenericList+OR+FileExtension%3aurl+OR+ContentClass%3aSTS_ListItem_544+OR+ContentClass%3aSTS_List_DocumentLibrary)))%27&Properties=%27GraphQuery%3aand(actor(me%5c%`
- `0x30516`: `AllowReadCommittedSnapshotIsolation`
- `0x3059a`: `BootstrapRollupUpdateBatchSize`
- `0x306e8`: `PluginTraceLogRecordMaxRetryCount`
- `0x306f9`: `PluginTraceLogMaxQueueSizeBeforeStoppingRetries`
- `0x3070e`: `PluginTraceLogMaxQueueSizeBeforeStoppingEnqueue`
- `0x30723`: `PluginTraceLogMaxDaysStored`
- `0x30734`: `PluginTraceLoggingVerboseEnabled`
- `0x30745`: `MaxThreadCountToDequeuePluginTraceLog`
- `0x30757`: `PluginTraceLogTimerIntervalInSeconds`
- `0x30769`: `ReservedPluginTraceLogCountPerOrg`
- `0x3077b`: `MaxPluginTraceLogCountPerOrg`
- `0x30790`: `PluginTraceLogMaxTimeInSecondsToDequeue`
- `0x307a5`: `PluginTraceLogSizeToAcceptBeyondOrgReserved`
- `0x307ba`: `PluginTraceLogDbWriteTimeoutInSeconds`
- `0x307f5`: `FileJoiningThreadCount`
- `0x30851`: `AzureUploadThreadCount`
- `0x30863`: `AzureDownloadThreadCount`
- `0x308e2`: `AzureUploadBlockBlobThreadCount`
- `0x30978`: `MetadataCacheLockTimeoutInMilliseconds`

## pseudocode

```c

```

## disassembly

```asm
0x2f830  ldarg.0
0x2f831  ldstr    aPropertyBag// "property bag"
0x2f836  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x2f83b  ldstr    aAsyncselectint// "AsyncSelectInterval"
0x2f840  ldc.i4.5
0x2f841  box      [mscorlib]System.Int32
0x2f846  ldarg.0
0x2f847  call     void Microsoft.Crm.Admin.AdminService.CrmDeploymentService::AddPropertyIfMissing(string propertyName, object value, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag bag)
0x2f84c  ldstr    aAsyncmovetorea// "AsyncMoveToReadyInterval"
0x2f851  ldc.i4.s 0xA
0x2f853  box      [mscorlib]System.Int32
0x2f858  ldarg.0
0x2f859  call     void Microsoft.Crm.Admin.AdminService.CrmDeploymentService::AddPropertyIfMissing(string propertyName, object value, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag bag)
0x2f85e  ldstr    aAsynckeepalive// "AsyncKeepAliveInterval"
0x2f863  ldc.i4.s 0x3C
0x2f865  box      [mscorlib]System.Int32
0x2f86a  ldarg.0
0x2f86b  call     void Microsoft.Crm.Admin.AdminService.CrmDeploymentService::AddPropertyIfMissing(string propertyName, object value, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag bag)
0x2f870  ldstr    aAsynctimeoutlo// "AsyncTimeoutLockedInterval"
0x2f875  ldc.i4   0x12C
0x2f87a  box      [mscorlib]System.Int32
0x2f87f  ldarg.0
0x2f880  call     void Microsoft.Crm.Admin.AdminService.CrmDeploymentService::AddPropertyIfMissing(string propertyName, object value, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag bag)
0x2f885  ldstr    aAsyncmaximumre// "AsyncMaximumRetries"
0x2f88a  ldc.i4.s 0xA
0x2f88c  box      [mscorlib]System.Int32
0x2f891  ldarg.0
0x2f892  call     void Microsoft.Crm.Admin.AdminService.CrmDeploymentService::AddPropertyIfMissing(string propertyName, object value, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag bag)
0x2f897  ldstr    aAsynctimebetwe// "AsyncTimeBetweenRetries"
0x2f89c  ldc.i4.s 0x1E
0x2f89e  box      [mscorlib]System.Int32
0x2f8a3  ldarg.0
0x2f8a4  call     void Microsoft.Crm.Admin.AdminService.CrmDeploymentService::AddPropertyIfMissing(string propertyName, object value, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag bag)
0x2f8a9  ldstr    aAsynctimeuntil// "AsyncTimeUntilLockExpires"
0x2f8ae  ldc.i4   0x12C
0x2f8b3  box      [mscorlib]System.Int32
0x2f8b8  ldarg.0
0x2f8b9  call     void Microsoft.Crm.Admin.AdminService.CrmDeploymentService::AddPropertyIfMissing(string propertyName, object value, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag bag)
0x2f8be  ldstr    aUsepredictivea// "UsePredictiveAsyncOrgLevelThrottle"
0x2f8c3  ldc.i4.0
0x2f8c4  box      [mscorlib]System.Boolean
0x2f8c9  ldarg.0
0x2f8ca  call     void Microsoft.Crm.Admin.AdminService.CrmDeploymentService::AddPropertyIfMissing(string propertyName, object value, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag bag)
0x2f8cf  ldstr    aAsyncmaximumth// "AsyncMaximumThreadsPercent"
0x2f8d4  ldc.r8   0.6
0x2f8dd  box      [mscorlib]System.Double
0x2f8e2  ldarg.0
0x2f8e3  call     void Microsoft.Crm.Admin.AdminService.CrmDeploymentService::AddPropertyIfMissing(string propertyName, object value, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag bag)
0x2f8e8  ldstr    aAsyncmaximumth_0// "AsyncMaximumThreadsPerCPU"
0x2f8ed  ldc.i4.3
0x2f8ee  box      [mscorlib]System.Int32
0x2f8f3  ldarg.0
0x2f8f4  call     void Microsoft.Crm.Admin.AdminService.CrmDeploymentService::AddPropertyIfMissing(string propertyName, object value, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag bag)
0x2f8f9  ldstr    aAsyncmaximumse// "AsyncMaximumSelectInterval"
0x2f8fe  ldc.i4.s 0x3C
0x2f900  box      [mscorlib]System.Int32
0x2f905  ldarg.0
0x2f906  call     void Microsoft.Crm.Admin.AdminService.CrmDeploymentService::AddPropertyIfMissing(string propertyName, object value, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag bag)
0x2f90b  ldstr    aAsyncmaximumpr// "AsyncMaximumPriority"
0x2f910  ldc.i4.s 0xA
0x2f912  box      [mscorlib]System.Int32
0x2f917  ldarg.0
0x2f918  call     void Microsoft.Crm.Admin.AdminService.CrmDeploymentService::AddPropertyIfMissing(string propertyName, object value, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag bag)
0x2f91d  ldstr    aAsyncstatestat// "AsyncStateStatusUpdateInterval"
0x2f922  ldc.i4.5
0x2f923  box      [mscorlib]System.Int32
0x2f928  ldarg.0
0x2f929  call     void Microsoft.Crm.Admin.AdminService.CrmDeploymentService::AddPropertyIfMissing(string propertyName, object value, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag bag)
0x2f92e  ldstr    aAsyncstatestat_0// "AsyncStateStatusUpdateMaxRetryCount"
0x2f933  ldc.i4.s 0xC
0x2f935  box      [mscorlib]System.Int32
0x2f93a  ldarg.0
0x2f93b  call     void Microsoft.Crm.Admin.AdminService.CrmDeploymentService::AddPropertyIfMissing(string propertyName, object value, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag bag)
0x2f940  ldstr    aAsyncwaitsubsc// "AsyncWaitSubscriptionInterval"
0x2f945  ldc.i4   0x708
0x2f94a  box      [mscorlib]System.Int32
0x2f94f  ldarg.0
0x2f950  call     void Microsoft.Crm.Admin.AdminService.CrmDeploymentService::AddPropertyIfMissing(string propertyName, object value, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag bag)
0x2f955  ldstr    aImportbatchsiz// "ImportBatchSize"
0x2f95a  ldc.i4   0x3E8
0x2f95f  box      [mscorlib]System.Int32
0x2f964  ldarg.0
0x2f965  call     void Microsoft.Crm.Admin.AdminService.CrmDeploymentService::AddPropertyIfMissing(string propertyName, object value, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag bag)
0x2f96a  ldstr    aImportbatchtim// "ImportBatchTime"
0x2f96f  ldc.i4   0x3E8
0x2f974  box      [mscorlib]System.Int32
0x2f979  ldarg.0
0x2f97a  call     void Microsoft.Crm.Admin.AdminService.CrmDeploymentService::AddPropertyIfMissing(string propertyName, object value, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag bag)
0x2f97f  ldstr    aImportparsedco// "ImportParsedColumnDefaultSize"
0x2f984  ldc.i4   0x1F4
0x2f989  box      [mscorlib]System.Int32
0x2f98e  ldarg.0
0x2f98f  call     void Microsoft.Crm.Admin.AdminService.CrmDeploymentService::AddPropertyIfMissing(string propertyName, object value, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag bag)
0x2f994  ldstr    aImportpicklist// "ImportPickListBatchSize"
0x2f999  ldc.i4.s 0x64
0x2f99b  box      [mscorlib]System.Int32
0x2f9a0  ldarg.0
0x2f9a1  call     void Microsoft.Crm.Admin.AdminService.CrmDeploymentService::AddPropertyIfMissing(string propertyName, object value, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag bag)
0x2f9a6  ldstr    aImportcontentb// "ImportContentBufferSize"
0x2f9ab  ldc.i4   0x4000
0x2f9b0  box      [mscorlib]System.Int32
0x2f9b5  ldarg.0
0x2f9b6  call     void Microsoft.Crm.Admin.AdminService.CrmDeploymentService::AddPropertyIfMissing(string propertyName, object value, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag bag)
0x2f9bb  ldstr    aImportmaxretry// "ImportMaxRetryCountForDataTruncation"
0x2f9c0  ldc.i4.5
0x2f9c1  box      [mscorlib]System.Int32
0x2f9c6  ldarg.0
0x2f9c7  call     void Microsoft.Crm.Admin.AdminService.CrmDeploymentService::AddPropertyIfMissing(string propertyName, object value, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag bag)
0x2f9cc  ldstr    aImportmaxcolum// "ImportMaxColumnsAllowed"
0x2f9d1  ldc.i4   0x3FE
0x2f9d6  box      [mscorlib]System.Int32
0x2f9db  ldarg.0
0x2f9dc  call     void Microsoft.Crm.Admin.AdminService.CrmDeploymentService::AddPropertyIfMissing(string propertyName, object value, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag bag)
0x2f9e1  ldstr    aImportcountupd// "ImportCountUpdateBatchSize"
0x2f9e6  ldc.i4.s 0xA
0x2f9e8  box      [mscorlib]System.Int32
0x2f9ed  ldarg.0
0x2f9ee  call     void Microsoft.Crm.Admin.AdminService.CrmDeploymentService::AddPropertyIfMissing(string propertyName, object value, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag bag)
0x2f9f3  ldstr    aMessageprocess// "MessageProcessorMaximumDepth"
0x2f9f8  ldc.i4.8
0x2f9f9  box      [mscorlib]System.Int32
0x2f9fe  ldarg.0
0x2f9ff  call     void Microsoft.Crm.Admin.AdminService.CrmDeploymentService::AddPropertyIfMissing(string propertyName, object value, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag bag)
0x2fa04  ldstr    aMessageprocess_0// "MessageProcessorMinimumInactiveSeconds"
0x2fa09  ldc.i4   0xE10
0x2fa0e  box      [mscorlib]System.Int32
0x2fa13  ldarg.0
0x2fa14  call     void Microsoft.Crm.Admin.AdminService.CrmDeploymentService::AddPropertyIfMissing(string propertyName, object value, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag bag)
0x2fa19  ldstr    aDupmatchcodepe// "DupMatchcodePersistenceInterval"
0x2fa1e  ldc.i4.5
0x2fa1f  box      [mscorlib]System.Int32
0x2fa24  ldarg.0
0x2fa25  call     void Microsoft.Crm.Admin.AdminService.CrmDeploymentService::AddPropertyIfMissing(string propertyName, object value, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag bag)
0x2fa2a  ldstr    aDuppublishpage// "DupPublishPageSize"
0x2fa2f  ldc.i4   0xFA
0x2fa34  box      [mscorlib]System.Int32
0x2fa39  ldarg.0
0x2fa3a  call     void Microsoft.Crm.Admin.AdminService.CrmDeploymentService::AddPropertyIfMissing(string propertyName, object value, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag bag)
0x2fa3f  ldstr    aDuppublishasyn// "DupPublishAsyncPollingInterval"
0x2fa44  ldc.i4.s 0x64
0x2fa46  box      [mscorlib]System.Int32
0x2fa4b  ldarg.0
0x2fa4c  call     void Microsoft.Crm.Admin.AdminService.CrmDeploymentService::AddPropertyIfMissing(string propertyName, object value, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag bag)
0x2fa51  ldstr    aDupmatchcodele// "DupMatchcodeLength"
0x2fa56  ldc.i4   0x3E8
0x2fa5b  box      [mscorlib]System.Int32
0x2fa60  ldarg.0
0x2fa61  call     void Microsoft.Crm.Admin.AdminService.CrmDeploymentService::AddPropertyIfMissing(string propertyName, object value, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag bag)
0x2fa66  ldstr    aDupmaxpublishe// "DupMaxPublishedRules"
0x2fa6b  ldc.i4.5
0x2fa6c  box      [mscorlib]System.Int32
0x2fa71  ldarg.0
0x2fa72  call     void Microsoft.Crm.Admin.AdminService.CrmDeploymentService::AddPropertyIfMissing(string propertyName, object value, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag bag)
0x2fa77  ldstr    aDumpchartxmlin// "DumpChartXmlInResponse"
0x2fa7c  ldc.i4.0
0x2fa7d  box      [mscorlib]System.Boolean
0x2fa82  ldarg.0
0x2fa83  call     void Microsoft.Crm.Admin.AdminService.CrmDeploymentService::AddPropertyIfMissing(string propertyName, object value, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag bag)
0x2fa88  ldstr    aDupbulkdetectb// "DupBulkDetectBatchSize"
0x2fa8d  ldc.i4   0x3E8
0x2fa92  box      [mscorlib]System.Int32
0x2fa97  ldarg.0
0x2fa98  call     void Microsoft.Crm.Admin.AdminService.CrmDeploymentService::AddPropertyIfMissing(string propertyName, object value, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag bag)
0x2fa9d  ldstr    aAppuseinproces// "AppUseInProcessSdk"
0x2faa2  ldc.i4.1
0x2faa3  box      [mscorlib]System.Int32
0x2faa8  ldarg.0
0x2faa9  call     void Microsoft.Crm.Admin.AdminService.CrmDeploymentService::AddPropertyIfMissing(string propertyName, object value, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag bag)
0x2faae  ldstr    aAsyncjoborgdat// "AsyncJobOrgDatabaseMaintenanceInterval"
0x2fab3  ldc.i4.5
0x2fab4  box      [mscorlib]System.Int32
0x2fab9  ldarg.0
0x2faba  call     void Microsoft.Crm.Admin.AdminService.CrmDeploymentService::AddPropertyIfMissing(string propertyName, object value, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag bag)
0x2fabf  ldstr    aAsyncjobtimeou// "AsyncJobTimeoutLockedInterval"
0x2fac4  ldc.i4.s 0x1E
0x2fac6  box      [mscorlib]System.Int32
0x2facb  ldarg.0
0x2facc  call     void Microsoft.Crm.Admin.AdminService.CrmDeploymentService::AddPropertyIfMissing(string propertyName, object value, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag bag)
0x2fad1  ldstr    aAsyncjobmaxexe// "AsyncJobMaxExecutionTime"
0x2fad6  ldc.i4.s 0x3C
0x2fad8  box      [mscorlib]System.Int32
0x2fadd  ldarg.0
0x2fade  call     void Microsoft.Crm.Admin.AdminService.CrmDeploymentService::AddPropertyIfMissing(string propertyName, object value, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag bag)
0x2fae3  ldstr    aAsyncsdkrootdo// "AsyncSdkRootDomain"
0x2fae8  ldstr    asc_4C8CE// ""
0x2faed  ldarg.0
0x2faee  call     void Microsoft.Crm.Admin.AdminService.CrmDeploymentService::AddPropertyIfMissing(string propertyName, object value, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag bag)
0x2faf3  ldstr    aAttributevalid// "AttributeValidationEnabled"
0x2faf8  ldc.i4.1
0x2faf9  box      [mscorlib]System.Boolean
0x2fafe  ldarg.0
0x2faff  call     void Microsoft.Crm.Admin.AdminService.CrmDeploymentService::AddPropertyIfMissing(string propertyName, object value, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag bag)
0x2fb04  ldstr    aDtatemplate// "DTATemplate"
0x2fb09  ldstr    aXmlVersion10En_0// "<?xml version='1.0' encoding='utf-16' ?"...
0x2fb0e  ldarg.0
0x2fb0f  call     void Microsoft.Crm.Admin.AdminService.CrmDeploymentService::AddPropertyIfMissing(string propertyName, object value, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag bag)
0x2fb14  ldstr    aDatabasebackup// "DatabaseBackupShareLocation"
0x2fb19  ldstr    aNone// "none"
0x2fb1e  ldarg.0
0x2fb1f  call     void Microsoft.Crm.Admin.AdminService.CrmDeploymentService::AddPropertyIfMissing(string propertyName, object value, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag bag)
0x2fb24  call     class [mscorlib]System.Tuple`2<valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTime> Microsoft.Crm.Admin.AdminService.CrmDeploymentService::GetMaintenanceWindowStartAndEndTimeForGeo()
0x2fb29  stloc.0
0x2fb2a  ldstr    aMaintenancewin// "MaintenanceWindowStartTime"
0x2fb2f  ldloc.0
0x2fb30  callvirt instance var<u1> class [mscorlib]System.Tuple`2<valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTime>::get_Item1()
0x2fb35  box      [mscorlib]System.DateTime
0x2fb3a  ldarg.0
0x2fb3b  call     void Microsoft.Crm.Admin.AdminService.CrmDeploymentService::AddPropertyIfMissing(string propertyName, object value, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag bag)
0x2fb40  ldstr    aMaintenancewin_0// "MaintenanceWindowEndTime"
0x2fb45  ldloc.0
0x2fb46  callvirt instance var<u1> class [mscorlib]System.Tuple`2<valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTime>::get_Item2()
0x2fb4b  box      [mscorlib]System.DateTime
0x2fb50  ldarg.0
0x2fb51  call     void Microsoft.Crm.Admin.AdminService.CrmDeploymentService::AddPropertyIfMissing(string propertyName, object value, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag bag)
0x2fb56  ldstr    aAsyncuseinproc// "AsyncUseInProcessSdk"
0x2fb5b  ldc.i4.1
0x2fb5c  box      [mscorlib]System.Boolean
0x2fb61  ldarg.0
0x2fb62  call     void Microsoft.Crm.Admin.AdminService.CrmDeploymentService::AddPropertyIfMissing(string propertyName, object value, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag bag)
0x2fb67  ldstr    aAsyncmaximumse_0// "AsyncMaximumServerConcurrentJobs"
0x2fb6c  ldc.i4.5
0x2fb6d  box      [mscorlib]System.Int32
0x2fb72  ldarg.0
0x2fb73  call     void Microsoft.Crm.Admin.AdminService.CrmDeploymentService::AddPropertyIfMissing(string propertyName, object value, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag bag)
0x2fb78  ldstr    aAsyncmaximumor// "AsyncMaximumOrganizationConcurrentJobs"
0x2fb7d  ldc.i4.3
0x2fb7e  box      [mscorlib]System.Int32
0x2fb83  ldarg.0
0x2fb84  call     void Microsoft.Crm.Admin.AdminService.CrmDeploymentService::AddPropertyIfMissing(string propertyName, object value, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag bag)
0x2fb89  ldstr    aAsyncpriorityc// "AsyncPriorityCoefficient"
0x2fb8e  ldc.i4.3
0x2fb8f  box      [mscorlib]System.Int32
0x2fb94  ldarg.0
0x2fb95  call     void Microsoft.Crm.Admin.AdminService.CrmDeploymentService::AddPropertyIfMissing(string propertyName, object value, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag bag)
0x2fb9a  ldstr    aAsyncoverdueco// "AsyncOverdueCoefficient"
0x2fb9f  ldc.i4.2
0x2fba0  box      [mscorlib]System.Int32
0x2fba5  ldarg.0
0x2fba6  call     void Microsoft.Crm.Admin.AdminService.CrmDeploymentService::AddPropertyIfMissing(string propertyName, object value, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag bag)
0x2fbab  ldstr    aAsyncprioritym// "AsyncPriorityMapping"
0x2fbb0  ldstr    aDefault1Deleti// "Default=1;DeletionService=5;IndexManage"...
0x2fbb5  ldarg.0
0x2fbb6  call     void Microsoft.Crm.Admin.AdminService.CrmDeploymentService::AddPropertyIfMissing(string propertyName, object value, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag bag)
0x2fbbb  ldstr    aAsynccapacitym// "AsyncCapacityMapping"
0x2fbc0  ldstr    aDefault1Deleti_0// "Default=1;DeletionService=1;IndexManage"...
0x2fbc5  ldarg.0
0x2fbc6  call     void Microsoft.Crm.Admin.AdminService.CrmDeploymentService::AddPropertyIfMissing(string propertyName, object value, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag bag)
0x2fbcb  ldstr    aAsyncscalegrou// "AsyncScaleGroupDatabaseCleanupInterval"
0x2fbd0  ldc.i4.s 0xC
0x2fbd2  box      [mscorlib]System.Int32
0x2fbd7  ldarg.0
0x2fbd8  call     void Microsoft.Crm.Admin.AdminService.CrmDeploymentService::AddPropertyIfMissing(string propertyName, object value, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag bag)
0x2fbdd  ldstr    aEcmessageidcac// "ECMessageIDCacheCapacity"
0x2fbe2  ldc.i4   0x186A0
0x2fbe7  box      [mscorlib]System.Int32
0x2fbec  ldarg.0
0x2fbed  call     void Microsoft.Crm.Admin.AdminService.CrmDeploymentService::AddPropertyIfMissing(string propertyName, object value, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag bag)
0x2fbf2  ldstr    aEcmessageidcac_0// "ECMessageIDCacheRetentionTime"
0x2fbf7  ldc.i4.s 0x3C
0x2fbf9  box      [mscorlib]System.Int32
0x2fbfe  ldarg.0
0x2fbff  call     void Microsoft.Crm.Admin.AdminService.CrmDeploymentService::AddPropertyIfMissing(string propertyName, object value, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag bag)
0x2fc04  ldstr    aAsyncjobstopro// "AsyncJobsToProcessAtOnce"
0x2fc09  ldc.i4.s 0xA
0x2fc0b  box      [mscorlib]System.Int32
0x2fc10  ldarg.0
0x2fc11  call     void Microsoft.Crm.Admin.AdminService.CrmDeploymentService::AddPropertyIfMissing(string propertyName, object value, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag bag)
0x2fc16  ldstr    aAsyncjobstoret// "AsyncJobsToReturnInSql"
0x2fc1b  ldc.i4.s 0x64
0x2fc1d  box      [mscorlib]System.Int32
0x2fc22  ldarg.0
0x2fc23  call     void Microsoft.Crm.Admin.AdminService.CrmDeploymentService::AddPropertyIfMissing(string propertyName, object value, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag bag)
0x2fc28  ldstr    aAsyncjobsmodul// "AsyncJobsModuloForNewJobRetrieval"
0x2fc2d  ldc.i4.8
0x2fc2e  box      [mscorlib]System.Int32
0x2fc33  ldarg.0
0x2fc34  call     void Microsoft.Crm.Admin.AdminService.CrmDeploymentService::AddPropertyIfMissing(string propertyName, object value, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag bag)
0x2fc39  ldstr    aAsyncjobstimer// "AsyncJobsTimerFrequencyMultiplier"
0x2fc3e  ldc.i4.2
0x2fc3f  box      [mscorlib]System.Int32
0x2fc44  ldarg.0
0x2fc45  call     void Microsoft.Crm.Admin.AdminService.CrmDeploymentService::AddPropertyIfMissing(string propertyName, object value, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag bag)
0x2fc4a  ldstr    aAsyncmailboxre// "AsyncMailboxReportEventInterval"
0x2fc4f  ldc.i4.s 0x3C
0x2fc51  box      [mscorlib]System.Int32
0x2fc56  ldarg.0
0x2fc57  call     void Microsoft.Crm.Admin.AdminService.CrmDeploymentService::AddPropertyIfMissing(string propertyName, object value, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag bag)
0x2fc5c  call     class [Microsoft.Crm.Core]Microsoft.Crm.ISkuInfoProvider [Microsoft.Crm.Core]Microsoft.Crm.SkuInfoProvider::get_Instance()
0x2fc61  callvirt instance valuetype [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.ConfigSku [Microsoft.Crm.Core]Microsoft.Crm.ISkuInfoProvider::GetSku()
0x2fc66  ldc.i4.2
0x2fc67  bne.un   loc_2FD21
0x2fc6c  ldstr    aEtmenabled// "ETMEnabled"
0x2fc71  ldc.i4.1
0x2fc72  box      [mscorlib]System.Boolean
0x2fc77  ldarg.0
0x2fc78  call     void Microsoft.Crm.Admin.AdminService.CrmDeploymentService::AddPropertyIfMissing(string propertyName, object value, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag bag)
0x2fc7d  ldstr    aEtmstatisticsu// "ETMStatisticsUpdateEnabled"
0x2fc82  ldc.i4.1
0x2fc83  box      [mscorlib]System.Boolean
0x2fc88  ldarg.0
  ... truncated ...
```
