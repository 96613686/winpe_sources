# Microsoft.Crm.ObjectModel.AppConfigPublisher::Publish_0

- ea: `0x140470`
- end: `0x1405dd`
- name: `Microsoft.Crm.ObjectModel.AppConfigPublisher::Publish_0`
- size: `365`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140280`

## callees

- `0x140240`
- `0x140470`
- `0x1405e0`
- `0x140720`
- `0x140860`
- `0x140870`
- `0x1c8460`
- `0x1c8d60`
- `0x1c8db0`

## string_xrefs

- `0x140470`: `AppConfig`
- `0x1404de`: `AppConfig`
- `0x140580`: `AppConfig`
- `0x1404a3`: `appconfigid`
- `0x140487`: `appconfigidunique`
- `0x140504`: `appconfigidunique`
- `0x1404c0`: `componentstate`

## pseudocode

```c

```

## disassembly

```asm
0x140470  ldstr    aAppconfig// "AppConfig"
0x140475  ldarg.0
0x140476  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.ObjectModel.AppConfigPublisher::_context
0x14047b  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::.ctor(string, class [Microsoft.Crm.Core]Microsoft.Crm.IUserAndOrganizationContext)
0x140480  stloc.0
0x140481  ldloc.0
0x140482  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_ColumnSet()
0x140487  ldstr    aAppconfigiduni// "appconfigidunique"
0x14048c  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::AddColumn(string)
0x140491  ldloc.0
0x140492  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Criteria()
0x140497  ldc.i4.0
0x140498  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::set_FilterOperator(valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.LogicalOperator)
0x14049d  ldloc.0
0x14049e  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Criteria()
0x1404a3  ldstr    aAppconfigid// "appconfigid"
0x1404a8  ldc.i4.0
0x1404a9  ldarg.0
0x1404aa  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.ObjectModel.AppConfigPublisher::get__appConfigId()
0x1404af  box      [mscorlib]System.Guid
0x1404b4  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0x1404b9  pop
0x1404ba  ldloc.0
0x1404bb  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Criteria()
0x1404c0  ldstr    aComponentstate_0// "componentstate"
0x1404c5  ldc.i4.0
0x1404c6  ldc.i4.1
0x1404c7  box      [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Platform.ComponentState
0x1404cc  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0x1404d1  pop
0x1404d2  ldarg.0
0x1404d3  ldfld    class Microsoft.Crm.ObjectModel.AppConfigService Microsoft.Crm.ObjectModel.AppConfigPublisher::_appConfigService
0x1404d8  ldarg.0
0x1404d9  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.ObjectModel.AppConfigPublisher::get__appConfigId()
0x1404de  ldstr    aAppconfig// "AppConfig"
0x1404e3  ldarg.0
0x1404e4  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.ObjectModel.AppConfigPublisher::_context
0x1404e9  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x1404ee  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker::.ctor(valuetype [mscorlib]System.Guid, string, valuetype [mscorlib]System.Guid)
0x1404f3  ldloc.0
0x1404f4  ldarg.0
0x1404f5  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.ObjectModel.AppConfigPublisher::_context
0x1404fa  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::RetrieveUnpublished(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x1404ff  stloc.1
0x140500  ldloc.1
0x140501  brfalse.s loc_14053A
0x140503  ldloc.1
0x140504  ldstr    aAppconfigiduni// "appconfigidunique"
0x140509  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x14050e  unbox.any [mscorlib]System.Guid
0x140513  stloc.3
0x140514  ldarg.0
0x140515  ldarg.0
0x140516  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.ObjectModel.AppConfigPublisher::get__appConfigId()
0x14051b  ldloc.3
0x14051c  ldarg.0
0x14051d  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.ObjectModel.AppConfigPublisher::_context
0x140522  call     instance void Microsoft.Crm.ObjectModel.AppConfigPublisher::PublishAppConfigInstances(valuetype [mscorlib]System.Guid appconfigID, valuetype [mscorlib]System.Guid appconfigidUnique, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x140527  ldarg.0
0x140528  ldarg.0
0x140529  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.ObjectModel.AppConfigPublisher::get__appConfigId()
0x14052e  ldloc.3
0x14052f  ldarg.0
0x140530  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.ObjectModel.AppConfigPublisher::_context
0x140535  call     instance void Microsoft.Crm.ObjectModel.AppConfigPublisher::PublishNavigationSettings(valuetype [mscorlib]System.Guid appconfigID, valuetype [mscorlib]System.Guid appconfigidUnique, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x14053a  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Core.Telemetry.EventSources.TelemetryExecutionToken::.ctor()
0x14053f  stloc.2
0x140540  call     class Microsoft.Crm.ObjectModel.BPOOverrideCrmTelemetryEvents Microsoft.Crm.ObjectModel.BPOOverrideCrmTelemetryEvents::get_Instance()
0x140545  ldarg.0
0x140546  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.ObjectModel.AppConfigPublisher::_context
0x14054b  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x140550  call     string [Microsoft.Crm.Core]Microsoft.Crm.Core.Telemetry.CrmTelemetryHelper::get_ApplicationVersion()
0x140555  ldloc.0
0x140556  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Entity()
0x14055b  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_LogicalName()
0x140560  call     string [Microsoft.Crm.Core]Microsoft.Crm.Core.Telemetry.CrmTelemetryHelper::get_UserPuid()
0x140565  call     string Microsoft.Crm.ObjectModel.AppConfigPublisher::get_CurrentClientId()
0x14056a  call     string Microsoft.Crm.ObjectModel.AppConfigPublisher::get_CurrentClientType()
0x14056f  callvirt instance void Microsoft.Crm.ObjectModel.BPOOverrideCrmTelemetryEvents::BPOOverridePublishStarted(valuetype [mscorlib]System.Guid organizationId, string applicationVersion, string entityName, string userPuid, string clientSessionId, string clientType)
0x140574  ldarg.0
0x140575  ldfld    class Microsoft.Crm.ObjectModel.AppConfigService Microsoft.Crm.ObjectModel.AppConfigPublisher::_appConfigService
0x14057a  ldarg.0
0x14057b  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.ObjectModel.AppConfigPublisher::get__appConfigId()
0x140580  ldstr    aAppconfig// "AppConfig"
0x140585  ldarg.0
0x140586  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.ObjectModel.AppConfigPublisher::_context
0x14058b  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker::.ctor(valuetype [mscorlib]System.Guid, string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x140590  ldarg.0
0x140591  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.ObjectModel.AppConfigPublisher::_context
0x140596  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::PublishShared(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x14059b  ldloc.2
0x14059c  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.Core.Telemetry.EventSources.TelemetryExecutionToken [Microsoft.Crm.Core]Microsoft.Crm.Core.Telemetry.EventSources.TelemetryExecutionToken::Stop()
0x1405a1  pop
0x1405a2  call     class Microsoft.Crm.ObjectModel.BPOOverrideCrmTelemetryEvents Microsoft.Crm.ObjectModel.BPOOverrideCrmTelemetryEvents::get_Instance()
0x1405a7  ldarg.0
0x1405a8  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.ObjectModel.AppConfigPublisher::_context
0x1405ad  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x1405b2  call     string [Microsoft.Crm.Core]Microsoft.Crm.Core.Telemetry.CrmTelemetryHelper::get_ApplicationVersion()
0x1405b7  ldloc.0
0x1405b8  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Entity()
0x1405bd  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_LogicalName()
0x1405c2  call     string [Microsoft.Crm.Core]Microsoft.Crm.Core.Telemetry.CrmTelemetryHelper::get_UserPuid()
0x1405c7  ldloc.2
0x1405c8  callvirt instance int64 [Microsoft.Crm.Core]Microsoft.Crm.Core.Telemetry.EventSources.TelemetryExecutionToken::get_ElapsedMilliseconds()
0x1405cd  call     string Microsoft.Crm.ObjectModel.AppConfigPublisher::get_CurrentClientId()
0x1405d2  call     string Microsoft.Crm.ObjectModel.AppConfigPublisher::get_CurrentClientType()
0x1405d7  callvirt instance void Microsoft.Crm.ObjectModel.BPOOverrideCrmTelemetryEvents::BPOOverridePublishSucceeded(valuetype [mscorlib]System.Guid organizationId, string applicationVersion, string entityName, string userPuid, int64 executionTime, string clientSessionId, string clientType)
0x1405dc  ret
```
