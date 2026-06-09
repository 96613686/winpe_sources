# Microsoft.Crm.Service.ObjectModel.RoutingRuleService::InternalSetState

- ea: `0x81c0`
- end: `0x8382`
- name: `Microsoft.Crm.Service.ObjectModel.RoutingRuleService::InternalSetState`
- size: `450`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callees

- `0x81c0`
- `0x86a0`
- `0x8740`
- `0x87f0`
- `0x8880`
- `0x88f0`
- `0xb430`

## pseudocode

```c

```

## disassembly

```asm
0x81c0  newobj   instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.WorkflowService::.ctor()
0x81c5  stloc.0
0x81c6  ldarg.s  5
0x81c8  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x81cd  newobj   instance void [Microsoft.Crm.Entities]Microsoft.Crm.Entities.WorkflowEntity::.ctor(valuetype [mscorlib]System.Guid)
0x81d2  stloc.1
0x81d3  ldarg.s  4
0x81d5  castclass [Microsoft.Crm.Service.Entities]Microsoft.Crm.Service.Entities.RoutingRule
0x81da  stloc.2
0x81db  ldarg.0
0x81dc  ldc.i4.1
0x81dd  ldarg.s  5
0x81df  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity Microsoft.Crm.Service.ObjectModel.RoutingRuleService::GetActiveRoutingRule(bool activeOnly, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x81e4  stloc.3
0x81e5  ldarg.0
0x81e6  ldarg.1
0x81e7  ldarg.s  5
0x81e9  ldloc.3
0x81ea  call     instance void Microsoft.Crm.Service.ObjectModel.RoutingRuleService::CheckForOwnerOfRoutingRule(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker moniker, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity existingActiveRoutingRule)
0x81ef  ldc.i4.0
0x81f0  stloc.s  4
0x81f2  ldarg.2
0x81f3  ldc.i4.1
0x81f4  bne.un.s loc_8254
0x81f6  ldloc.2
0x81f7  ldstr    aStatecode// "statecode"
0x81fc  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x8201  unbox.any [mscorlib]System.Int32
0x8206  ldc.i4.1
0x8207  bne.un.s loc_821A
0x8209  ldc.i4   0x8004F852
0x820e  ldc.i4.0
0x820f  newarr   [mscorlib]System.Object
0x8214  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(int32, object[])
0x8219  throw
0x821a  ldstr    aIncident_0// "incident"
0x821f  ldarg.1
0x8220  ldarg.s  5
0x8222  ldc.i4.1
0x8223  call     class [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.IWorkflowAuthorService Microsoft.Crm.Service.ObjectModel.WorkflowAuthorServiceFactory::Create(string entityName, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker moniker, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context, valuetype [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.WorkflowAuthorType type)
0x8228  callvirt instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.IWorkflowAuthorService::AuthorWorkflow()
0x822d  ldarg.1
0x822e  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker::get_EntityMetadata()
0x8233  ldarg.s  5
0x8235  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x823a  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.EntityClassFactory::CreateInstance(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata, valuetype [mscorlib]System.Guid)
0x823f  starg.s  4
0x8241  ldarg.0
0x8242  ldarg.1
0x8243  ldarg.s  5
0x8245  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity Microsoft.Crm.Service.ObjectModel.RoutingRuleService::RetrieveRoutingRuleRecod(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker moniker, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x824a  starg.s  4
0x824c  ldarg.s  4
0x824e  castclass [Microsoft.Crm.Service.Entities]Microsoft.Crm.Service.Entities.RoutingRule
0x8253  stloc.2
0x8254  leave.s  loc_8261
0x8256  callvirt instance string [mscorlib]System.Exception::get_Message()
0x825b  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string)
0x8260  throw
0x8261  ldarg.2
0x8262  ldc.i4.1
0x8263  bne.un   loc_8341
0x8268  ldloc.2
0x8269  ldstr    aStatecode// "statecode"
0x826e  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x8273  unbox.any [mscorlib]System.Int32
0x8278  ldc.i4.1
0x8279  bne.un.s loc_828C
0x827b  ldc.i4   0x8004F852
0x8280  ldc.i4.0
0x8281  newarr   [mscorlib]System.Object
0x8286  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(int32, object[])
0x828b  throw
0x828c  ldloc.3
0x828d  brfalse  loc_8330
0x8292  ldloc.3
0x8293  ldstr    aRoutingruleid_0// "routingruleid"
0x8298  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x829d  unbox.any [mscorlib]System.Guid
0x82a2  ldloc.2
0x82a3  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_PlatformName()
0x82a8  ldarg.s  5
0x82aa  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker::.ctor(valuetype [mscorlib]System.Guid, string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x82af  stloc.s  5
0x82b1  ldarg.s  5
0x82b3  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.CrmTransaction [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_Transaction()
0x82b8  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmTransaction::StartTransaction()
0x82bd  ldc.i4.0
0x82be  stloc.s  6
0x82c0  ldarg.0
0x82c1  ldloc.s  5
0x82c3  ldc.i4.0
0x82c4  ldc.i4.1
0x82c5  ldloc.3
0x82c6  ldarg.s  5
0x82c8  call     instance bool [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::InternalSetState(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker, int32, int32, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x82cd  brfalse.s loc_830B
0x82cf  ldarg.0
0x82d0  ldarg.1
0x82d1  ldarg.2
0x82d2  ldarg.3
0x82d3  ldarg.s  4
0x82d5  ldarg.s  5
0x82d7  call     instance bool [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::InternalSetState(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker, int32, int32, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x82dc  brfalse.s loc_830B
0x82de  ldloc.2
0x82df  ldstr    aWorkflowid// "workflowid"
0x82e4  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x82e9  unbox.any [mscorlib]System.Guid
0x82ee  ldloc.1
0x82ef  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_PlatformName()
0x82f4  ldarg.s  5
0x82f6  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker::.ctor(valuetype [mscorlib]System.Guid, string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x82fb  stloc.s  7
0x82fd  ldloc.0
0x82fe  ldloc.s  7
0x8300  ldc.i4.1
0x8301  ldc.i4.2
0x8302  ldarg.s  5
0x8304  callvirt instance bool [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::SetState(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker, int32, int32, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x8309  stloc.s  6
0x830b  ldloc.s  6
0x830d  brfalse.s loc_831D
0x830f  ldarg.s  5
0x8311  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.CrmTransaction [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_Transaction()
0x8316  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmTransaction::CommitTransaction()
0x831b  br.s     loc_832A
0x831d  ldarg.s  5
0x831f  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.CrmTransaction [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_Transaction()
0x8324  ldc.i4.1
0x8325  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmTransaction::RollbackTransaction(bool)
0x832a  ldloc.s  6
0x832c  stloc.s  4
0x832e  br.s     loc_8373
0x8330  ldarg.0
0x8331  ldarg.1
0x8332  ldarg.2
0x8333  ldarg.3
0x8334  ldarg.s  4
0x8336  ldarg.s  5
0x8338  call     instance bool Microsoft.Crm.Service.ObjectModel.RoutingRuleService::SetStateRuleandWorkflow(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker moniker, int32 newState, int32 newStatusCode, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity originalEntity, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x833d  stloc.s  4
0x833f  br.s     loc_8373
0x8341  ldloc.2
0x8342  ldstr    aStatecode// "statecode"
0x8347  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x834c  unbox.any [mscorlib]System.Int32
0x8351  brtrue.s loc_8364
0x8353  ldc.i4   0x8004F853
0x8358  ldc.i4.0
0x8359  newarr   [mscorlib]System.Object
0x835e  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(int32, object[])
0x8363  throw
0x8364  ldarg.0
0x8365  ldarg.1
0x8366  ldarg.2
0x8367  ldarg.3
0x8368  ldarg.s  4
0x836a  ldarg.s  5
0x836c  call     instance bool Microsoft.Crm.Service.ObjectModel.RoutingRuleService::SetStateRuleandWorkflow(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker moniker, int32 newState, int32 newStatusCode, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity originalEntity, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x8371  stloc.s  4
0x8373  ldarg.2
0x8374  brtrue.s loc_837F
0x8376  ldarg.0
0x8377  ldarg.1
0x8378  ldarg.s  5
0x837a  call     instance void Microsoft.Crm.Service.ObjectModel.RoutingRuleService::DeleteRoutingRuleWorkflow(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker moniker, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x837f  ldloc.s  4
0x8381  ret
```
