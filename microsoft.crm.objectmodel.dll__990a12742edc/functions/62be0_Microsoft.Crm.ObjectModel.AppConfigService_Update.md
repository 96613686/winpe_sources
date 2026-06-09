# Microsoft.Crm.ObjectModel.AppConfigService::Update

- ea: `0x62be0`
- end: `0x62fa2`
- name: `Microsoft.Crm.ObjectModel.AppConfigService::Update`
- size: `962`
- prototype: ``
- caller_count: `0`
- callee_count: `11`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0x628e0`
- `0x62be0`
- `0x632e0`
- `0x63a90`
- `0x63aa0`
- `0x63ab0`
- `0x63b50`
- `0x1c8460`
- `0x1c8c50`
- `0x1c8ca0`
- `0x1c8d00`

## string_xrefs

- `0x62c7a`: `AppConfig`
- `0x62d32`: `AppConfig`
- `0x62c35`: `appconfigid`
- `0x62c8e`: `appconfigid`
- `0x62cc5`: `appconfigid`
- `0x62d57`: `appconfigid`
- `0x62d68`: `appconfigid`
- `0x62c43`: `appconfigidunique`
- `0x62d46`: `appconfigidunique`
- `0x62d9b`: `appconfigidunique`
- `0x62daf`: `appconfigidunique`
- `0x62cac`: `componentstate`

## pseudocode

```c

```

## disassembly

```asm
0x62be0  ldarg.0
0x62be1  ldarg.2
0x62be2  call     instance void Microsoft.Crm.ObjectModel.AppConfigService::ThrowExceptionIfFeatureNotEnabled(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x62be7  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Core.Telemetry.EventSources.TelemetryExecutionToken::.ctor()
0x62bec  stloc.0
0x62bed  call     class Microsoft.Crm.ObjectModel.BPOOverrideCrmTelemetryEvents Microsoft.Crm.ObjectModel.BPOOverrideCrmTelemetryEvents::get_Instance()
0x62bf2  ldarg.1
0x62bf3  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_OrganizationId()
0x62bf8  call     string [Microsoft.Crm.Core]Microsoft.Crm.Core.Telemetry.CrmTelemetryHelper::get_ApplicationVersion()
0x62bfd  ldarg.1
0x62bfe  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Metadata()
0x62c03  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_LogicalName()
0x62c08  call     string [Microsoft.Crm.Core]Microsoft.Crm.Core.Telemetry.CrmTelemetryHelper::get_UserPuid()
0x62c0d  call     string Microsoft.Crm.ObjectModel.AppConfigService::get_CurrentClientId()
0x62c12  call     string Microsoft.Crm.ObjectModel.AppConfigService::get_CurrentClientType()
0x62c17  callvirt instance void Microsoft.Crm.ObjectModel.BPOOverrideCrmTelemetryEvents::BPOOverrideUpdateStarted(valuetype [mscorlib]System.Guid organizationId, string applicationVersion, string entityName, string userPuid, string clientSessionId, string clientType)
0x62c1c  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x62c21  stloc.1
0x62c22  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x62c27  stloc.2
0x62c28  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x62c2d  stloc.3
0x62c2e  ldc.i4.m1
0x62c2f  stloc.s  4
0x62c31  ldc.i4.m1
0x62c32  stloc.s  5
0x62c34  ldarg.1
0x62c35  ldstr    aAppconfigid// "appconfigid"
0x62c3a  ldloca.s 1
0x62c3c  callvirt T0x2B0000EF
0x62c41  pop
0x62c42  ldarg.1
0x62c43  ldstr    aAppconfigiduni// "appconfigidunique"
0x62c48  ldloca.s 2
0x62c4a  callvirt T0x2B0000EF
0x62c4f  pop
0x62c50  ldarg.1
0x62c51  ldstr    aSolutionid// "solutionid"
0x62c56  ldloca.s 3
0x62c58  callvirt T0x2B0000EF
0x62c5d  pop
0x62c5e  ldarg.1
0x62c5f  ldstr    aStatecode// "statecode"
0x62c64  ldloca.s 4
0x62c66  callvirt T0x2B000101
0x62c6b  pop
0x62c6c  ldarg.1
0x62c6d  ldstr    aStatuscode// "statuscode"
0x62c72  ldloca.s 5
0x62c74  callvirt T0x2B000101
0x62c79  pop
0x62c7a  ldstr    aAppconfig// "AppConfig"
0x62c7f  ldarg.2
0x62c80  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::.ctor(string, class [Microsoft.Crm.Core]Microsoft.Crm.IUserAndOrganizationContext)
0x62c85  stloc.s  6
0x62c87  ldloc.s  6
0x62c89  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_ColumnSet()
0x62c8e  ldstr    aAppconfigid// "appconfigid"
0x62c93  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::AddColumn(string)
0x62c98  ldloc.s  6
0x62c9a  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Criteria()
0x62c9f  ldc.i4.0
0x62ca0  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::set_FilterOperator(valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.LogicalOperator)
0x62ca5  ldloc.s  6
0x62ca7  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Criteria()
0x62cac  ldstr    aComponentstate_0// "componentstate"
0x62cb1  ldc.i4.0
0x62cb2  ldc.i4.1
0x62cb3  box      [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Platform.ComponentState
0x62cb8  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0x62cbd  pop
0x62cbe  ldloc.s  6
0x62cc0  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Criteria()
0x62cc5  ldstr    aAppconfigid// "appconfigid"
0x62cca  ldc.i4.0
0x62ccb  ldloc.1
0x62ccc  box      [mscorlib]System.Guid
0x62cd1  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0x62cd6  pop
0x62cd7  ldarg.0
0x62cd8  ldloc.s  6
0x62cda  ldarg.2
0x62cdb  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::RetrieveUnpublishedMultiple(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x62ce0  stloc.s  7
0x62ce2  ldloc.s  7
0x62ce4  callvirt instance int32 [mscorlib]System.Collections.CollectionBase::get_Count()
0x62ce9  brtrue   loc_62EB6
0x62cee  ldarg.0
0x62cef  ldarg.1
0x62cf0  ldloc.s  4
0x62cf2  ldloc.s  5
0x62cf4  ldc.i4.0
0x62cf5  ldc.i4.0
0x62cf6  conv.i8
0x62cf7  call     instance void Microsoft.Crm.ObjectModel.AppConfigService::logAppConfigStateTelemetry(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity entity, int32 statecode, int32 statuscode, int32 opcode, int64 elapsedMilliseconds)
0x62cfc  ldarg.2
0x62cfd  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.CrmTransaction [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_Transaction()
0x62d02  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmTransaction::StartTransaction()
0x62d07  ldarg.0
0x62d08  ldarg.1
0x62d09  ldarg.2
0x62d0a  call     instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::Update(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x62d0f  ldloc.3
0x62d10  ldsfld   valuetype [mscorlib]System.Guid [Microsoft.Crm.Constants]Microsoft.Crm.SolutionConstants::ActiveSolutionId
0x62d15  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x62d1a  brtrue.s loc_62D1F
0x62d1c  ldc.i4.1
0x62d1d  br.s     loc_62D20
0x62d1f  ldc.i4.0
0x62d20  stloc.s  8
0x62d22  ldloc.2
0x62d23  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x62d28  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x62d2d  brfalse  loc_62DBF
0x62d32  ldstr    aAppconfig// "AppConfig"
0x62d37  ldarg.2
0x62d38  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::.ctor(string, class [Microsoft.Crm.Core]Microsoft.Crm.IUserAndOrganizationContext)
0x62d3d  stloc.s  9
0x62d3f  ldloc.s  9
0x62d41  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_ColumnSet()
0x62d46  ldstr    aAppconfigiduni// "appconfigidunique"
0x62d4b  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::AddColumn(string)
0x62d50  ldloc.s  9
0x62d52  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_ColumnSet()
0x62d57  ldstr    aAppconfigid// "appconfigid"
0x62d5c  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::AddColumn(string)
0x62d61  ldloc.s  9
0x62d63  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Criteria()
0x62d68  ldstr    aAppconfigid// "appconfigid"
0x62d6d  ldc.i4.0
0x62d6e  ldloc.1
0x62d6f  box      [mscorlib]System.Guid
0x62d74  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0x62d79  pop
0x62d7a  ldarg.0
0x62d7b  ldloc.s  9
0x62d7d  ldarg.2
0x62d7e  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::RetrieveMultiple(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x62d83  stloc.s  7
0x62d85  ldloc.s  7
0x62d87  callvirt instance int32 [mscorlib]System.Collections.CollectionBase::get_Count()
0x62d8c  brfalse.s loc_62DBF
0x62d8e  ldloc.s  7
0x62d90  ldc.i4.0
0x62d91  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection::get_Item(int32)
0x62d96  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IAttributeInfoCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Attributes()
0x62d9b  ldstr    aAppconfigiduni// "appconfigidunique"
0x62da0  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IAttributeInfoCollection::Contains(string)
0x62da5  brfalse.s loc_62DBF
0x62da7  ldloc.s  7
0x62da9  ldc.i4.0
0x62daa  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection::get_Item(int32)
0x62daf  ldstr    aAppconfigiduni// "appconfigidunique"
0x62db4  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x62db9  unbox.any [mscorlib]System.Guid
0x62dbe  stloc.2
0x62dbf  ldarg.0
0x62dc0  ldloc.1
0x62dc1  ldloc.2
0x62dc2  ldarg.2
0x62dc3  ldloc.s  8
0x62dc5  call     instance bool Microsoft.Crm.ObjectModel.AppConfigService::CloneAppConfigInstancesAndNavigationSettings(valuetype [mscorlib]System.Guid appconfigid, valuetype [mscorlib]System.Guid publishedAppConfigIdUnique, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context, bool isManaged)
0x62dca  pop
0x62dcb  ldarg.2
0x62dcc  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.CrmTransaction [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_Transaction()
0x62dd1  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmTransaction::CommitTransaction()
0x62dd6  ldloc.0
0x62dd7  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.Core.Telemetry.EventSources.TelemetryExecutionToken [Microsoft.Crm.Core]Microsoft.Crm.Core.Telemetry.EventSources.TelemetryExecutionToken::Stop()
0x62ddc  pop
0x62ddd  ldarg.0
0x62dde  ldarg.1
0x62ddf  ldloc.s  4
0x62de1  ldloc.s  5
0x62de3  ldc.i4.1
0x62de4  ldloc.0
0x62de5  callvirt instance int64 [Microsoft.Crm.Core]Microsoft.Crm.Core.Telemetry.EventSources.TelemetryExecutionToken::get_ElapsedMilliseconds()
0x62dea  call     instance void Microsoft.Crm.ObjectModel.AppConfigService::logAppConfigStateTelemetry(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity entity, int32 statecode, int32 statuscode, int32 opcode, int64 elapsedMilliseconds)
0x62def  call     class Microsoft.Crm.ObjectModel.BPOOverrideCrmTelemetryEvents Microsoft.Crm.ObjectModel.BPOOverrideCrmTelemetryEvents::get_Instance()
0x62df4  ldarg.1
0x62df5  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_OrganizationId()
0x62dfa  call     string [Microsoft.Crm.Core]Microsoft.Crm.Core.Telemetry.CrmTelemetryHelper::get_ApplicationVersion()
0x62dff  ldarg.1
0x62e00  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Metadata()
0x62e05  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_LogicalName()
0x62e0a  call     string [Microsoft.Crm.Core]Microsoft.Crm.Core.Telemetry.CrmTelemetryHelper::get_UserPuid()
0x62e0f  ldloc.0
0x62e10  callvirt instance int64 [Microsoft.Crm.Core]Microsoft.Crm.Core.Telemetry.EventSources.TelemetryExecutionToken::get_ElapsedMilliseconds()
0x62e15  call     string Microsoft.Crm.ObjectModel.AppConfigService::get_CurrentClientId()
0x62e1a  call     string Microsoft.Crm.ObjectModel.AppConfigService::get_CurrentClientType()
0x62e1f  callvirt instance void Microsoft.Crm.ObjectModel.BPOOverrideCrmTelemetryEvents::BPOOverrideUpdateSucceeded(valuetype [mscorlib]System.Guid organizationId, string applicationVersion, string entityName, string userPuid, int64 executionTime, string clientSessionId, string clientType)
0x62e24  leave    loc_62FA1
0x62e29  stloc.s  0xA
0x62e2b  ldloc.s  0xA
0x62e2d  call     string Microsoft.Crm.ObjectModel.AppConfigService::RetrieveExceptionMessage(class [mscorlib]System.Exception exception)
0x62e32  stloc.s  0xB
0x62e34  ldloc.0
0x62e35  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.Core.Telemetry.EventSources.TelemetryExecutionToken [Microsoft.Crm.Core]Microsoft.Crm.Core.Telemetry.EventSources.TelemetryExecutionToken::Stop()
0x62e3a  pop
0x62e3b  ldarg.0
0x62e3c  ldarg.1
0x62e3d  ldloc.s  4
0x62e3f  ldloc.s  5
0x62e41  ldc.i4.2
0x62e42  ldloc.0
0x62e43  callvirt instance int64 [Microsoft.Crm.Core]Microsoft.Crm.Core.Telemetry.EventSources.TelemetryExecutionToken::get_ElapsedMilliseconds()
0x62e48  call     instance void Microsoft.Crm.ObjectModel.AppConfigService::logAppConfigStateTelemetry(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity entity, int32 statecode, int32 statuscode, int32 opcode, int64 elapsedMilliseconds)
0x62e4d  call     class Microsoft.Crm.ObjectModel.BPOOverrideCrmTelemetryEvents Microsoft.Crm.ObjectModel.BPOOverrideCrmTelemetryEvents::get_Instance()
0x62e52  ldarg.1
0x62e53  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_OrganizationId()
0x62e58  call     string [Microsoft.Crm.Core]Microsoft.Crm.Core.Telemetry.CrmTelemetryHelper::get_ApplicationVersion()
0x62e5d  ldarg.1
0x62e5e  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Metadata()
0x62e63  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_LogicalName()
0x62e68  call     string [Microsoft.Crm.Core]Microsoft.Crm.Core.Telemetry.CrmTelemetryHelper::get_UserPuid()
0x62e6d  ldloc.0
0x62e6e  callvirt instance int64 [Microsoft.Crm.Core]Microsoft.Crm.Core.Telemetry.EventSources.TelemetryExecutionToken::get_ElapsedMilliseconds()
0x62e73  call     string Microsoft.Crm.ObjectModel.AppConfigService::get_CurrentClientId()
0x62e78  call     string Microsoft.Crm.ObjectModel.AppConfigService::get_CurrentClientType()
0x62e7d  ldloc.s  0xB
0x62e7f  callvirt instance void Microsoft.Crm.ObjectModel.BPOOverrideCrmTelemetryEvents::BPOOverrideUpdateErrored(valuetype [mscorlib]System.Guid organizationId, string applicationVersion, string entityName, string userPuid, int64 executionTime, string clientSessionId, string clientType, string exceptionMessage)
0x62e84  ldloc.s  0xA
0x62e86  ldarg.2
0x62e87  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x62e8c  ldc.i4.s 0x14
0x62e8e  ldstr    a0_0// "{0}"
0x62e93  ldc.i4.1
0x62e94  newarr   [mscorlib]System.Object
0x62e99  dup
0x62e9a  ldc.i4.0
0x62e9b  ldloc.s  0xA
0x62e9d  callvirt instance string [mscorlib]System.Exception::get_Message()
0x62ea2  stelem.ref
0x62ea3  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x62ea8  ldarg.2
0x62ea9  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.CrmTransaction [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_Transaction()
0x62eae  ldc.i4.0
0x62eaf  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmTransaction::RollbackTransaction(bool)
0x62eb4  rethrow
0x62eb6  nop
0x62eb7  ldarg.0
0x62eb8  ldarg.1
0x62eb9  ldloc.s  4
0x62ebb  ldloc.s  5
0x62ebd  ldc.i4.0
0x62ebe  ldc.i4.0
0x62ebf  conv.i8
0x62ec0  call     instance void Microsoft.Crm.ObjectModel.AppConfigService::logAppConfigStateTelemetry(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity entity, int32 statecode, int32 statuscode, int32 opcode, int64 elapsedMilliseconds)
0x62ec5  ldarg.0
0x62ec6  ldarg.1
0x62ec7  ldarg.2
0x62ec8  call     instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::Update(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x62ecd  ldloc.0
0x62ece  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.Core.Telemetry.EventSources.TelemetryExecutionToken [Microsoft.Crm.Core]Microsoft.Crm.Core.Telemetry.EventSources.TelemetryExecutionToken::Stop()
0x62ed3  pop
0x62ed4  ldarg.0
0x62ed5  ldarg.1
0x62ed6  ldloc.s  4
0x62ed8  ldloc.s  5
0x62eda  ldc.i4.1
0x62edb  ldloc.0
0x62edc  callvirt instance int64 [Microsoft.Crm.Core]Microsoft.Crm.Core.Telemetry.EventSources.TelemetryExecutionToken::get_ElapsedMilliseconds()
0x62ee1  call     instance void Microsoft.Crm.ObjectModel.AppConfigService::logAppConfigStateTelemetry(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity entity, int32 statecode, int32 statuscode, int32 opcode, int64 elapsedMilliseconds)
0x62ee6  call     class Microsoft.Crm.ObjectModel.BPOOverrideCrmTelemetryEvents Microsoft.Crm.ObjectModel.BPOOverrideCrmTelemetryEvents::get_Instance()
0x62eeb  ldarg.1
0x62eec  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_OrganizationId()
0x62ef1  call     string [Microsoft.Crm.Core]Microsoft.Crm.Core.Telemetry.CrmTelemetryHelper::get_ApplicationVersion()
0x62ef6  ldarg.1
0x62ef7  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Metadata()
0x62efc  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_LogicalName()
0x62f01  call     string [Microsoft.Crm.Core]Microsoft.Crm.Core.Telemetry.CrmTelemetryHelper::get_UserPuid()
0x62f06  ldloc.0
0x62f07  callvirt instance int64 [Microsoft.Crm.Core]Microsoft.Crm.Core.Telemetry.EventSources.TelemetryExecutionToken::get_ElapsedMilliseconds()
0x62f0c  call     string Microsoft.Crm.ObjectModel.AppConfigService::get_CurrentClientId()
0x62f11  call     string Microsoft.Crm.ObjectModel.AppConfigService::get_CurrentClientType()
0x62f16  callvirt instance void Microsoft.Crm.ObjectModel.BPOOverrideCrmTelemetryEvents::BPOOverrideUpdateSucceeded(valuetype [mscorlib]System.Guid organizationId, string applicationVersion, string entityName, string userPuid, int64 executionTime, string clientSessionId, string clientType)
0x62f1b  leave    loc_62FA1
0x62f20  stloc.s  0xC
0x62f22  ldloc.s  0xC
0x62f24  call     string Microsoft.Crm.ObjectModel.AppConfigService::RetrieveExceptionMessage(class [mscorlib]System.Exception exception)
0x62f29  stloc.s  0xD
0x62f2b  ldloc.0
0x62f2c  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.Core.Telemetry.EventSources.TelemetryExecutionToken [Microsoft.Crm.Core]Microsoft.Crm.Core.Telemetry.EventSources.TelemetryExecutionToken::Stop()
0x62f31  pop
0x62f32  ldarg.0
0x62f33  ldarg.1
0x62f34  ldloc.s  4
0x62f36  ldloc.s  5
0x62f38  ldc.i4.2
0x62f39  ldloc.0
0x62f3a  callvirt instance int64 [Microsoft.Crm.Core]Microsoft.Crm.Core.Telemetry.EventSources.TelemetryExecutionToken::get_ElapsedMilliseconds()
0x62f3f  call     instance void Microsoft.Crm.ObjectModel.AppConfigService::logAppConfigStateTelemetry(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity entity, int32 statecode, int32 statuscode, int32 opcode, int64 elapsedMilliseconds)
0x62f44  call     class Microsoft.Crm.ObjectModel.BPOOverrideCrmTelemetryEvents Microsoft.Crm.ObjectModel.BPOOverrideCrmTelemetryEvents::get_Instance()
0x62f49  ldarg.1
0x62f4a  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_OrganizationId()
0x62f4f  call     string [Microsoft.Crm.Core]Microsoft.Crm.Core.Telemetry.CrmTelemetryHelper::get_ApplicationVersion()
0x62f54  ldarg.1
0x62f55  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Metadata()
0x62f5a  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_LogicalName()
0x62f5f  call     string [Microsoft.Crm.Core]Microsoft.Crm.Core.Telemetry.CrmTelemetryHelper::get_UserPuid()
0x62f64  ldloc.0
  ... truncated ...
```
