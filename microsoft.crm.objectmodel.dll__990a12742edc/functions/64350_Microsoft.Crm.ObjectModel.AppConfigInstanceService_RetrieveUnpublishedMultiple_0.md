# Microsoft.Crm.ObjectModel.AppConfigInstanceService::RetrieveUnpublishedMultiple_0

- ea: `0x64350`
- end: `0x644a4`
- name: `Microsoft.Crm.ObjectModel.AppConfigInstanceService::RetrieveUnpublishedMultiple_0`
- size: `340`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x64350`
- `0x64640`
- `0x64910`
- `0x64920`
- `0x1c8460`
- `0x1c8a20`
- `0x1c8a70`

## string_xrefs

- `0x64393`: `appconfigid`
- `0x6439b`: `appconfigidunique`
- `0x64416`: `appconfigidunique`
- `0x64427`: `appconfigidunique`
- `0x643fd`: `componentstate`
- `0x643c4`: `AppConfigInstance`

## pseudocode

```c

```

## disassembly

```asm
0x64350  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Core.Telemetry.EventSources.TelemetryExecutionToken::.ctor()
0x64355  stloc.0
0x64356  call     class Microsoft.Crm.ObjectModel.BPOOverrideCrmTelemetryEvents Microsoft.Crm.ObjectModel.BPOOverrideCrmTelemetryEvents::get_Instance()
0x6435b  ldarg.2
0x6435c  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x64361  call     string [Microsoft.Crm.Core]Microsoft.Crm.Core.Telemetry.CrmTelemetryHelper::get_ApplicationVersion()
0x64366  ldarg.1
0x64367  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Entity()
0x6436c  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_LogicalName()
0x64371  call     string [Microsoft.Crm.Core]Microsoft.Crm.Core.Telemetry.CrmTelemetryHelper::get_UserPuid()
0x64376  call     string Microsoft.Crm.ObjectModel.AppConfigInstanceService::get_CurrentClientId()
0x6437b  call     string Microsoft.Crm.ObjectModel.AppConfigInstanceService::get_CurrentClientType()
0x64380  callvirt instance void Microsoft.Crm.ObjectModel.BPOOverrideCrmTelemetryEvents::BPOOverrideRetrieveUMultipleStarted(valuetype [mscorlib]System.Guid organizationId, string applicationVersion, string entityName, string userPuid, string clientSessionId, string clientType)
0x64385  ldarg.1
0x64386  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_ColumnSet()
0x6438b  ldc.i4.2
0x6438c  newarr   [mscorlib]System.String
0x64391  dup
0x64392  ldc.i4.0
0x64393  ldstr    aAppconfigid// "appconfigid"
0x64398  stelem.ref
0x64399  dup
0x6439a  ldc.i4.1
0x6439b  ldstr    aAppconfigiduni// "appconfigidunique"
0x643a0  stelem.ref
0x643a1  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::AddColumns(string[])
0x643a6  ldarg.2
0x643a7  callvirt instance bool [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_IsProcessingDependenciesFromTransactionCommit()
0x643ac  brfalse.s loc_643BA
0x643ae  ldarg.0
0x643af  ldarg.1
0x643b0  ldc.i4.0
0x643b1  ldarg.2
0x643b2  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::RetrieveUnpublishedMultiple(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression, bool, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x643b7  stloc.1
0x643b8  br.s     loc_643C4
0x643ba  ldarg.0
0x643bb  ldarg.1
0x643bc  ldc.i4.1
0x643bd  ldarg.2
0x643be  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::RetrieveUnpublishedMultiple(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression, bool, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x643c3  stloc.1
0x643c4  ldstr    aAppconfiginsta_0// "AppConfigInstance"
0x643c9  ldarg.2
0x643ca  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x643cf  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection::.ctor(string, valuetype [mscorlib]System.Guid)
0x643d4  stloc.2
0x643d5  ldloc.1
0x643d6  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.CollectionBase::GetEnumerator()
0x643db  stloc.3
0x643dc  br.s     loc_64446
0x643de  ldloc.3
0x643df  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x643e4  castclass [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity
0x643e9  stloc.s  4
0x643eb  ldarg.0
0x643ec  ldloc.s  4
0x643ee  ldc.i4.0
0x643ef  ldarg.2
0x643f0  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity Microsoft.Crm.ObjectModel.AppConfigInstanceService::RetrieveAppConfig(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity entity, bool sendPublished, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x643f5  stloc.s  5
0x643f7  ldloc.s  5
0x643f9  brfalse.s loc_64446
0x643fb  ldloc.s  5
0x643fd  ldstr    aComponentstate_0// "componentstate"
0x64402  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x64407  callvirt instance string [mscorlib]System.Object::ToString()
0x6440c  call     int32 [mscorlib]System.Convert::ToInt32(string)
0x64411  ldc.i4.1
0x64412  bne.un.s loc_64446
0x64414  ldloc.s  5
0x64416  ldstr    aAppconfigiduni// "appconfigidunique"
0x6441b  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x64420  callvirt instance string [mscorlib]System.Object::ToString()
0x64425  ldloc.s  4
0x64427  ldstr    aAppconfigiduni// "appconfigidunique"
0x6442c  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x64431  callvirt instance string [mscorlib]System.Object::ToString()
0x64436  call     bool [mscorlib]System.String::op_Equality(string, string)
0x6443b  brfalse.s loc_64446
0x6443d  ldloc.2
0x6443e  ldloc.s  4
0x64440  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection::Add(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity)
0x64445  pop
0x64446  ldloc.3
0x64447  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x6444c  brtrue.s loc_643DE
0x6444e  leave.s  loc_64464
0x64450  ldloc.3
0x64451  isinst   [mscorlib]System.IDisposable
0x64456  stloc.s  6
0x64458  ldloc.s  6
0x6445a  brfalse.s loc_64463
0x6445c  ldloc.s  6
0x6445e  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x64463  endfinally
0x64464  ldloc.0
0x64465  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.Core.Telemetry.EventSources.TelemetryExecutionToken [Microsoft.Crm.Core]Microsoft.Crm.Core.Telemetry.EventSources.TelemetryExecutionToken::Stop()
0x6446a  pop
0x6446b  call     class Microsoft.Crm.ObjectModel.BPOOverrideCrmTelemetryEvents Microsoft.Crm.ObjectModel.BPOOverrideCrmTelemetryEvents::get_Instance()
0x64470  ldarg.2
0x64471  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x64476  call     string [Microsoft.Crm.Core]Microsoft.Crm.Core.Telemetry.CrmTelemetryHelper::get_ApplicationVersion()
0x6447b  ldarg.1
0x6447c  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Entity()
0x64481  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_LogicalName()
0x64486  call     string [Microsoft.Crm.Core]Microsoft.Crm.Core.Telemetry.CrmTelemetryHelper::get_UserPuid()
0x6448b  ldloc.0
0x6448c  callvirt instance int64 [Microsoft.Crm.Core]Microsoft.Crm.Core.Telemetry.EventSources.TelemetryExecutionToken::get_ElapsedMilliseconds()
0x64491  ldarg.1
0x64492  call     string Microsoft.Crm.ObjectModel.AppConfigInstanceService::get_CurrentClientId()
0x64497  call     string Microsoft.Crm.ObjectModel.AppConfigInstanceService::get_CurrentClientType()
0x6449c  ldc.i4.1
0x6449d  callvirt instance void Microsoft.Crm.ObjectModel.BPOOverrideCrmTelemetryEvents::BPOOverrideRetrieveMultipleSucceeded(valuetype [mscorlib]System.Guid organizationId, string applicationVersion, string entityName, string userPuid, int64 executionTime, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression entityExpression, string clientSessionId, string clientType, bool logUnpublished)
0x644a2  ldloc.2
0x644a3  ret
```
