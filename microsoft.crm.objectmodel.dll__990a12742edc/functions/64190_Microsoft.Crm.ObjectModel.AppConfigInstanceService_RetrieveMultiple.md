# Microsoft.Crm.ObjectModel.AppConfigInstanceService::RetrieveMultiple

- ea: `0x64190`
- end: `0x642c8`
- name: `Microsoft.Crm.ObjectModel.AppConfigInstanceService::RetrieveMultiple`
- size: `312`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x64190`
- `0x64640`
- `0x64910`
- `0x64920`
- `0x1c8460`
- `0x1c88b0`
- `0x1c8a70`

## string_xrefs

- `0x641d3`: `appconfigid`
- `0x641db`: `appconfigidunique`
- `0x6423c`: `appconfigidunique`
- `0x6424c`: `appconfigidunique`
- `0x64224`: `componentstate`
- `0x641ee`: `AppConfigInstance`

## pseudocode

```c

```

## disassembly

```asm
0x64190  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Core.Telemetry.EventSources.TelemetryExecutionToken::.ctor()
0x64195  stloc.0
0x64196  call     class Microsoft.Crm.ObjectModel.BPOOverrideCrmTelemetryEvents Microsoft.Crm.ObjectModel.BPOOverrideCrmTelemetryEvents::get_Instance()
0x6419b  ldarg.2
0x6419c  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x641a1  call     string [Microsoft.Crm.Core]Microsoft.Crm.Core.Telemetry.CrmTelemetryHelper::get_ApplicationVersion()
0x641a6  ldarg.1
0x641a7  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Entity()
0x641ac  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_LogicalName()
0x641b1  call     string [Microsoft.Crm.Core]Microsoft.Crm.Core.Telemetry.CrmTelemetryHelper::get_UserPuid()
0x641b6  call     string Microsoft.Crm.ObjectModel.AppConfigInstanceService::get_CurrentClientId()
0x641bb  call     string Microsoft.Crm.ObjectModel.AppConfigInstanceService::get_CurrentClientType()
0x641c0  callvirt instance void Microsoft.Crm.ObjectModel.BPOOverrideCrmTelemetryEvents::BPOOverrideRetrieveMultipleStarted(valuetype [mscorlib]System.Guid organizationId, string applicationVersion, string entityName, string userPuid, string clientSessionId, string clientType)
0x641c5  ldarg.1
0x641c6  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_ColumnSet()
0x641cb  ldc.i4.2
0x641cc  newarr   [mscorlib]System.String
0x641d1  dup
0x641d2  ldc.i4.0
0x641d3  ldstr    aAppconfigid// "appconfigid"
0x641d8  stelem.ref
0x641d9  dup
0x641da  ldc.i4.1
0x641db  ldstr    aAppconfigiduni// "appconfigidunique"
0x641e0  stelem.ref
0x641e1  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::AddColumns(string[])
0x641e6  ldarg.0
0x641e7  ldarg.1
0x641e8  ldarg.2
0x641e9  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::RetrieveMultiple(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x641ee  ldstr    aAppconfiginsta_0// "AppConfigInstance"
0x641f3  ldarg.2
0x641f4  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x641f9  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection::.ctor(string, valuetype [mscorlib]System.Guid)
0x641fe  stloc.1
0x641ff  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.CollectionBase::GetEnumerator()
0x64204  stloc.2
0x64205  br.s     loc_6426A
0x64207  ldloc.2
0x64208  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x6420d  castclass [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity
0x64212  stloc.3
0x64213  ldarg.0
0x64214  ldloc.3
0x64215  ldc.i4.1
0x64216  ldarg.2
0x64217  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity Microsoft.Crm.ObjectModel.AppConfigInstanceService::RetrieveAppConfig(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity entity, bool sendPublished, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x6421c  stloc.s  4
0x6421e  ldloc.s  4
0x64220  brfalse.s loc_6426A
0x64222  ldloc.s  4
0x64224  ldstr    aComponentstate_0// "componentstate"
0x64229  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x6422e  callvirt instance string [mscorlib]System.Object::ToString()
0x64233  call     int32 [mscorlib]System.Convert::ToInt32(string)
0x64238  brtrue.s loc_6426A
0x6423a  ldloc.s  4
0x6423c  ldstr    aAppconfigiduni// "appconfigidunique"
0x64241  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x64246  callvirt instance string [mscorlib]System.Object::ToString()
0x6424b  ldloc.3
0x6424c  ldstr    aAppconfigiduni// "appconfigidunique"
0x64251  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x64256  callvirt instance string [mscorlib]System.Object::ToString()
0x6425b  call     bool [mscorlib]System.String::op_Equality(string, string)
0x64260  brfalse.s loc_6426A
0x64262  ldloc.1
0x64263  ldloc.3
0x64264  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection::Add(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity)
0x64269  pop
0x6426a  ldloc.2
0x6426b  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x64270  brtrue.s loc_64207
0x64272  leave.s  loc_64288
0x64274  ldloc.2
0x64275  isinst   [mscorlib]System.IDisposable
0x6427a  stloc.s  5
0x6427c  ldloc.s  5
0x6427e  brfalse.s loc_64287
0x64280  ldloc.s  5
0x64282  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x64287  endfinally
0x64288  ldloc.0
0x64289  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.Core.Telemetry.EventSources.TelemetryExecutionToken [Microsoft.Crm.Core]Microsoft.Crm.Core.Telemetry.EventSources.TelemetryExecutionToken::Stop()
0x6428e  pop
0x6428f  call     class Microsoft.Crm.ObjectModel.BPOOverrideCrmTelemetryEvents Microsoft.Crm.ObjectModel.BPOOverrideCrmTelemetryEvents::get_Instance()
0x64294  ldarg.2
0x64295  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x6429a  call     string [Microsoft.Crm.Core]Microsoft.Crm.Core.Telemetry.CrmTelemetryHelper::get_ApplicationVersion()
0x6429f  ldarg.1
0x642a0  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Entity()
0x642a5  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_LogicalName()
0x642aa  call     string [Microsoft.Crm.Core]Microsoft.Crm.Core.Telemetry.CrmTelemetryHelper::get_UserPuid()
0x642af  ldloc.0
0x642b0  callvirt instance int64 [Microsoft.Crm.Core]Microsoft.Crm.Core.Telemetry.EventSources.TelemetryExecutionToken::get_ElapsedMilliseconds()
0x642b5  ldarg.1
0x642b6  call     string Microsoft.Crm.ObjectModel.AppConfigInstanceService::get_CurrentClientId()
0x642bb  call     string Microsoft.Crm.ObjectModel.AppConfigInstanceService::get_CurrentClientType()
0x642c0  ldc.i4.0
0x642c1  callvirt instance void Microsoft.Crm.ObjectModel.BPOOverrideCrmTelemetryEvents::BPOOverrideRetrieveMultipleSucceeded(valuetype [mscorlib]System.Guid organizationId, string applicationVersion, string entityName, string userPuid, int64 executionTime, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression entityExpression, string clientSessionId, string clientType, bool logUnpublished)
0x642c6  ldloc.1
0x642c7  ret
```
