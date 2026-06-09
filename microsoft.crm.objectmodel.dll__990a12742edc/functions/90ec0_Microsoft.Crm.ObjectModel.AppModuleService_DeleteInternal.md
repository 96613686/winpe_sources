# Microsoft.Crm.ObjectModel.AppModuleService::DeleteInternal

- ea: `0x90ec0`
- end: `0x9103e`
- name: `Microsoft.Crm.ObjectModel.AppModuleService::DeleteInternal`
- size: `382`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x90d50`
- `0x1c0c60`

## callees

- `0x15bc0`
- `0x15be0`
- `0x25f40`
- `0x62830`
- `0x90ec0`
- `0x94a50`
- `0x94b30`

## string_xrefs

- `0x90ef0`: `AppConfig`
- `0x90f5d`: `AppConfig`
- `0x90f02`: `appconfigid`
- `0x90f4e`: `appconfigid`
- `0x90f9c`: `AppModuleDelete`
- `0x90fcf`: `AppModuleService.DeleteInternal(): Error while deleteing appmodule with [appmoduleid:{0}], Exception : {1}`

## pseudocode

```c

```

## disassembly

```asm
0x90ec0  ldarg.0
0x90ec1  ldarg.2
0x90ec2  call     instance void Microsoft.Crm.ObjectModel.AppModuleService::ThrowExceptionIfFeatureNotEnabled(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x90ec7  ldarg.1
0x90ec8  ldstr    aMoniker// "moniker"
0x90ecd  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x90ed2  ldarg.2
0x90ed3  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.CrmTransaction [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_Transaction()
0x90ed8  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmTransaction::StartTransaction()
0x90edd  ldarg.0
0x90ede  ldarg.1
0x90edf  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker::get_Id()
0x90ee4  ldarg.2
0x90ee5  call     instance void Microsoft.Crm.ObjectModel.AppModuleService::DeleteAppModuleComponentsForAppModuleId(valuetype [mscorlib]System.Guid appModuleId, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x90eea  newobj   instance void Microsoft.Crm.ObjectModel.AppConfigService::.ctor()
0x90eef  stloc.0
0x90ef0  ldstr    aAppconfig// "AppConfig"
0x90ef5  ldarg.2
0x90ef6  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::.ctor(string, class [Microsoft.Crm.Core]Microsoft.Crm.IUserAndOrganizationContext)
0x90efb  stloc.1
0x90efc  ldloc.1
0x90efd  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_ColumnSet()
0x90f02  ldstr    aAppconfigid// "appconfigid"
0x90f07  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::AddColumn(string)
0x90f0c  ldloc.1
0x90f0d  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Criteria()
0x90f12  ldc.i4.0
0x90f13  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::set_FilterOperator(valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.LogicalOperator)
0x90f18  ldloc.1
0x90f19  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Criteria()
0x90f1e  ldstr    aAppmoduleid// "appmoduleid"
0x90f23  ldc.i4.0
0x90f24  ldarg.1
0x90f25  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker::get_Id()
0x90f2a  box      [mscorlib]System.Guid
0x90f2f  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0x90f34  pop
0x90f35  ldloc.0
0x90f36  ldloc.1
0x90f37  ldarg.2
0x90f38  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::RetrieveMultiple(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x90f3d  stloc.2
0x90f3e  ldloc.2
0x90f3f  callvirt instance int32 [mscorlib]System.Collections.CollectionBase::get_Count()
0x90f44  ldc.i4.0
0x90f45  ble.s    loc_90F76
0x90f47  ldloc.2
0x90f48  ldc.i4.0
0x90f49  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection::get_Item(int32)
0x90f4e  ldstr    aAppconfigid// "appconfigid"
0x90f53  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x90f58  unbox.any [mscorlib]System.Guid
0x90f5d  ldstr    aAppconfig// "AppConfig"
0x90f62  ldarg.2
0x90f63  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x90f68  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker::.ctor(valuetype [mscorlib]System.Guid, string, valuetype [mscorlib]System.Guid)
0x90f6d  stloc.3
0x90f6e  ldloc.0
0x90f6f  ldloc.3
0x90f70  ldarg.2
0x90f71  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::Delete(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x90f76  ldarg.0
0x90f77  ldarg.1
0x90f78  ldarg.2
0x90f79  call     instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::Delete(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x90f7e  ldarg.0
0x90f7f  ldarg.1
0x90f80  ldarg.2
0x90f81  call     instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::PublishDeleteShared(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x90f86  ldarg.2
0x90f87  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.CrmTransaction [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_Transaction()
0x90f8c  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmTransaction::CommitTransaction()
0x90f91  call     class Microsoft.Crm.AppModule.AppModuleTelemetryEvents Microsoft.Crm.AppModule.AppModuleTelemetryEvents::get_Instance()
0x90f96  ldarg.2
0x90f97  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x90f9c  ldstr    aAppmoduledelet// "AppModuleDelete"
0x90fa1  ldarg.1
0x90fa2  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker::get_Id()
0x90fa7  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x90fac  ldc.i4.0
0x90fad  ldc.i4.0
0x90fae  ldc.i4.0
0x90faf  ldc.i4.0
0x90fb0  callvirt instance void Microsoft.Crm.AppModule.AppModuleTelemetryEvents::AppModuleEvent(valuetype [mscorlib]System.Guid OrganizationId, string AppEvent, valuetype [mscorlib]System.Guid AppModuleId, valuetype [mscorlib]System.Guid AppModuleIdUnique, int32 Dashboards, int32 BusinessProcessFlows, int32 Charts, int32 Views)
0x90fb5  ldarg.2
0x90fb6  ldarg.1
0x90fb7  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker::get_Id()
0x90fbc  call     void Microsoft.Crm.Sdk.AppModuleCacheUtils::FlushAppModuleCache(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context, valuetype [mscorlib]System.Guid publishedAppId)
0x90fc1  leave.s  loc_9103D
0x90fc3  stloc.s  4
0x90fc5  ldloc.s  4
0x90fc7  ldarg.2
0x90fc8  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x90fcd  ldc.i4.s 0x47
0x90fcf  ldstr    aAppmoduleservi_34// "AppModuleService.DeleteInternal(): Erro"...
0x90fd4  ldc.i4.2
0x90fd5  newarr   [mscorlib]System.Object
0x90fda  dup
0x90fdb  ldc.i4.0
0x90fdc  ldarg.1
0x90fdd  brtrue.s loc_90FEB
0x90fdf  ldloca.s 5
0x90fe1  initobj  valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>
0x90fe7  ldloc.s  5
0x90fe9  br.s     loc_90FF6
0x90feb  ldarg.1
0x90fec  call     instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker::get_Id()
0x90ff1  newobj   instance void valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::.ctor(var<u1>)
0x90ff6  box      valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>
0x90ffb  stelem.ref
0x90ffc  dup
0x90ffd  ldc.i4.1
0x90ffe  ldloc.s  4
0x91000  callvirt instance string [mscorlib]System.Exception::get_Message()
0x91005  stelem.ref
0x91006  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x9100b  ldloc.s  4
0x9100d  ldarg.2
0x9100e  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x91013  ldc.i4.s 0x14
0x91015  ldstr    aExceptionWhile_2// "Exception while deleting the Entity : {"...
0x9101a  ldc.i4.1
0x9101b  newarr   [mscorlib]System.Object
0x91020  dup
0x91021  ldc.i4.0
0x91022  ldloc.s  4
0x91024  callvirt instance string [mscorlib]System.Exception::get_Message()
0x91029  stelem.ref
0x9102a  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x9102f  ldarg.2
0x91030  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.CrmTransaction [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_Transaction()
0x91035  ldc.i4.0
0x91036  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmTransaction::RollbackTransaction(bool)
0x9103b  rethrow
0x9103d  ret
```
