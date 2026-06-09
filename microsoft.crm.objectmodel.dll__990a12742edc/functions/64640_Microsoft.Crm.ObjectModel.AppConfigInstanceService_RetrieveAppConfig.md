# Microsoft.Crm.ObjectModel.AppConfigInstanceService::RetrieveAppConfig

- ea: `0x64640`
- end: `0x646de`
- name: `Microsoft.Crm.ObjectModel.AppConfigInstanceService::RetrieveAppConfig`
- size: `158`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x64190`
- `0x64350`

## callees

- `0x64640`

## string_xrefs

- `0x64640`: `AppConfig`
- `0x6469d`: `AppConfig`
- `0x646c6`: `AppConfig`
- `0x64672`: `appconfigid`
- `0x64679`: `appconfigid`
- `0x6468e`: `appconfigid`
- `0x646b7`: `appconfigid`
- `0x64662`: `appconfigidunique`
- `0x64652`: `componentstate`

## pseudocode

```c

```

## disassembly

```asm
0x64640  ldstr    aAppconfig// "AppConfig"
0x64645  ldarg.3
0x64646  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::.ctor(string, class [Microsoft.Crm.Core]Microsoft.Crm.IUserAndOrganizationContext)
0x6464b  stloc.0
0x6464c  ldloc.0
0x6464d  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_ColumnSet()
0x64652  ldstr    aComponentstate_0// "componentstate"
0x64657  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::AddColumn(string)
0x6465c  ldloc.0
0x6465d  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_ColumnSet()
0x64662  ldstr    aAppconfigiduni// "appconfigidunique"
0x64667  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::AddColumn(string)
0x6466c  ldloc.0
0x6466d  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Criteria()
0x64672  ldstr    aAppconfigid// "appconfigid"
0x64677  ldc.i4.0
0x64678  ldarg.1
0x64679  ldstr    aAppconfigid// "appconfigid"
0x6467e  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x64683  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0x64688  pop
0x64689  ldarg.2
0x6468a  brfalse.s loc_646B5
0x6468c  ldarg.0
0x6468d  ldarg.1
0x6468e  ldstr    aAppconfigid// "appconfigid"
0x64693  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x64698  unbox.any [mscorlib]System.Guid
0x6469d  ldstr    aAppconfig// "AppConfig"
0x646a2  ldarg.3
0x646a3  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x646a8  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker::.ctor(valuetype [mscorlib]System.Guid, string, valuetype [mscorlib]System.Guid)
0x646ad  ldloc.0
0x646ae  ldarg.3
0x646af  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::Retrieve(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x646b4  ret
0x646b5  ldarg.0
0x646b6  ldarg.1
0x646b7  ldstr    aAppconfigid// "appconfigid"
0x646bc  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x646c1  unbox.any [mscorlib]System.Guid
0x646c6  ldstr    aAppconfig// "AppConfig"
0x646cb  ldarg.3
0x646cc  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x646d1  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker::.ctor(valuetype [mscorlib]System.Guid, string, valuetype [mscorlib]System.Guid)
0x646d6  ldloc.0
0x646d7  ldarg.3
0x646d8  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::RetrieveUnpublished(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x646dd  ret
```
