# Microsoft.Crm.Tools.ImportExportPublish.ImportServiceEndpointHandler::CreateOrUpdate

- ea: `0x60430`
- end: `0x604e5`
- name: `Microsoft.Crm.Tools.ImportExportPublish.ImportServiceEndpointHandler::CreateOrUpdate`
- size: `181`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x601c0`

## callees

- `0x60430`

## string_xrefs

- `0x60430`: `ServiceEndpoint`
- `0x60463`: `ServiceEndpoint`
- `0x60442`: `serviceendpointid`
- `0x60449`: `serviceendpointid`
- `0x60493`: `serviceendpointid`

## pseudocode

```c

```

## disassembly

```asm
0x60430  ldstr    aServiceendpoin// "ServiceEndpoint"
0x60435  ldarg.0
0x60436  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.ImportServiceEndpointHandler::_context
0x6043b  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::.ctor(string, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x60440  stloc.0
0x60441  ldloc.0
0x60442  ldstr    aServiceendpoin_0// "serviceendpointid"
0x60447  ldc.i4.0
0x60448  ldarg.1
0x60449  ldstr    aServiceendpoin_0// "serviceendpointid"
0x6044e  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x60453  unbox.any [mscorlib]System.Guid
0x60458  box      [mscorlib]System.Guid
0x6045d  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0x60462  pop
0x60463  ldstr    aServiceendpoin// "ServiceEndpoint"
0x60468  ldarg.0
0x60469  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.ImportServiceEndpointHandler::_context
0x6046e  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::.ctor(string, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x60473  stloc.1
0x60474  ldloc.0
0x60475  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::get_EntityMetadata()
0x6047a  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_PlatformName()
0x6047f  ldarg.0
0x60480  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.ImportServiceEndpointHandler::_context
0x60485  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::.ctor(string, class [Microsoft.Crm.Core]Microsoft.Crm.IUserAndOrganizationContext)
0x6048a  stloc.2
0x6048b  ldloc.2
0x6048c  ldloc.0
0x6048d  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::set_Criteria(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression)
0x60492  ldloc.1
0x60493  ldstr    aServiceendpoin_0// "serviceendpointid"
0x60498  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::AddColumn(string)
0x6049d  ldloc.2
0x6049e  ldloc.1
0x6049f  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::set_ColumnSet(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression)
0x604a4  ldarg.2
0x604a5  ldloc.2
0x604a6  ldarg.0
0x604a7  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.ImportServiceEndpointHandler::_context
0x604ac  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::RetrieveMultiple(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x604b1  stloc.3
0x604b2  ldarg.2
0x604b3  castclass [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.ServiceEndpointService
0x604b8  stloc.s  4
0x604ba  ldloc.3
0x604bb  brfalse.s loc_604C6
0x604bd  ldloc.3
0x604be  callvirt instance int32 [mscorlib]System.Collections.CollectionBase::get_Count()
0x604c3  ldc.i4.1
0x604c4  bge.s    loc_604D6
0x604c6  ldloc.s  4
0x604c8  ldarg.1
0x604c9  ldarg.0
0x604ca  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.ImportServiceEndpointHandler::_context
0x604cf  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.ServiceEndpointService::CreateInternalWithoutSecretsValidation(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x604d4  pop
0x604d5  ret
0x604d6  ldloc.s  4
0x604d8  ldarg.1
0x604d9  ldarg.0
0x604da  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.ImportServiceEndpointHandler::_context
0x604df  callvirt instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.ServiceEndpointService::UpdateInternalWithoutSecretsValidation(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x604e4  ret
```
