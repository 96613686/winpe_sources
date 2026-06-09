# Microsoft.Crm.Service.ObjectModel.SLAService::SetStateRuleandWorkflow

- ea: `0xa710`
- end: `0xa80d`
- name: `Microsoft.Crm.Service.ObjectModel.SLAService::SetStateRuleandWorkflow`
- size: `253`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x9fc0`

## callees

- `0xa710`
- `0xa810`
- `0xa870`

## pseudocode

```c

```

## disassembly

```asm
0xa710  newobj   instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.WorkflowService::.ctor()
0xa715  stloc.0
0xa716  ldarg.s  4
0xa718  castclass [Microsoft.Crm.Service.Entities]Microsoft.Crm.Service.Entities.SLA
0xa71d  stloc.1
0xa71e  ldarg.s  5
0xa720  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0xa725  newobj   instance void [Microsoft.Crm.Entities]Microsoft.Crm.Entities.WorkflowEntity::.ctor(valuetype [mscorlib]System.Guid)
0xa72a  stloc.2
0xa72b  ldarg.0
0xa72c  ldarg.1
0xa72d  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker::get_Id()
0xa732  ldarg.s  5
0xa734  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection Microsoft.Crm.Service.ObjectModel.SLAService::RetrieveSLAItemWorkflows(valuetype [mscorlib]System.Guid SLAId, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0xa739  stloc.3
0xa73a  ldc.i4.0
0xa73b  stloc.s  4
0xa73d  ldloc.1
0xa73e  ldstr    aName// "name"
0xa743  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0xa748  callvirt instance string [mscorlib]System.Object::ToString()
0xa74d  stloc.s  5
0xa74f  ldarg.0
0xa750  ldarg.1
0xa751  ldarg.2
0xa752  ldarg.3
0xa753  ldarg.s  4
0xa755  ldarg.s  5
0xa757  call     instance bool [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::InternalSetState(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker, int32, int32, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0xa75c  stloc.s  6
0xa75e  ldarg.0
0xa75f  ldarg.2
0xa760  ldarg.s  5
0xa762  ldloc.s  6
0xa764  ldloc.2
0xa765  ldloc.1
0xa766  ldstr    aWorkflowid// "workflowid"
0xa76b  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0xa770  unbox.any [mscorlib]System.Guid
0xa775  ldloc.0
0xa776  ldloc.s  5
0xa778  call     instance bool Microsoft.Crm.Service.ObjectModel.SLAService::Activateworkflow(int32 newState, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context, bool setStateSLAResult, class [Microsoft.Crm.Entities]Microsoft.Crm.Entities.WorkflowEntity workflowEntity, valuetype [mscorlib]System.Guid workflowId, class [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.WorkflowService workflowService, string workflowName)
0xa77d  stloc.s  7
0xa77f  ldloc.s  7
0xa781  brfalse  loc_A80A
0xa786  ldloc.3
0xa787  callvirt instance int32 [mscorlib]System.Collections.CollectionBase::get_Count()
0xa78c  ldc.i4.0
0xa78d  ble.s    loc_A80A
0xa78f  ldnull
0xa790  stloc.s  5
0xa792  ldloc.3
0xa793  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.CollectionBase::GetEnumerator()
0xa798  stloc.s  8
0xa79a  br.s     loc_A7E4
0xa79c  ldloc.s  8
0xa79e  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0xa7a3  castclass [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity
0xa7a8  dup
0xa7a9  ldstr    aWorkflowid// "workflowid"
0xa7ae  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0xa7b3  unbox.any [mscorlib]System.Guid
0xa7b8  stloc.s  9
0xa7ba  ldstr    aName// "name"
0xa7bf  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0xa7c4  callvirt instance string [mscorlib]System.Object::ToString()
0xa7c9  stloc.s  5
0xa7cb  ldarg.0
0xa7cc  ldarg.2
0xa7cd  ldarg.s  5
0xa7cf  ldloc.s  6
0xa7d1  ldloc.2
0xa7d2  ldloc.s  9
0xa7d4  ldloc.0
0xa7d5  ldloc.s  5
0xa7d7  call     instance bool Microsoft.Crm.Service.ObjectModel.SLAService::Activateworkflow(int32 newState, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context, bool setStateSLAResult, class [Microsoft.Crm.Entities]Microsoft.Crm.Entities.WorkflowEntity workflowEntity, valuetype [mscorlib]System.Guid workflowId, class [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.WorkflowService workflowService, string workflowName)
0xa7dc  stloc.s  4
0xa7de  ldloc.s  4
0xa7e0  brtrue.s loc_A7E4
0xa7e2  leave.s  loc_A804
0xa7e4  ldloc.s  8
0xa7e6  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0xa7eb  brtrue.s loc_A79C
0xa7ed  leave.s  loc_A804
0xa7ef  ldloc.s  8
0xa7f1  isinst   [mscorlib]System.IDisposable
0xa7f6  stloc.s  0xA
0xa7f8  ldloc.s  0xA
0xa7fa  brfalse.s loc_A803
0xa7fc  ldloc.s  0xA
0xa7fe  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xa803  endfinally
0xa804  ldloc.s  4
0xa806  ldloc.s  7
0xa808  and
0xa809  ret
0xa80a  ldloc.s  7
0xa80c  ret
```
