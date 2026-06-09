# Microsoft.Crm.Service.ObjectModel.ConvertRuleService::SetStateRuleAndWorkflow

- ea: `0x5680`
- end: `0x579d`
- name: `Microsoft.Crm.Service.ObjectModel.ConvertRuleService::SetStateRuleAndWorkflow`
- size: `285`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x52b0`

## callees

- `0x5680`
- `0x5dc0`
- `0x5e20`
- `0x8bb0`
- `0x8e90`
- `0xb430`

## pseudocode

```c

```

## disassembly

```asm
0x5680  newobj   instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.WorkflowService::.ctor()
0x5685  stloc.0
0x5686  ldarg.s  5
0x5688  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x568d  newobj   instance void [Microsoft.Crm.Entities]Microsoft.Crm.Entities.WorkflowEntity::.ctor(valuetype [mscorlib]System.Guid)
0x5692  stloc.1
0x5693  ldc.i4.0
0x5694  stloc.2
0x5695  ldarg.0
0x5696  ldarg.1
0x5697  ldarg.2
0x5698  ldarg.3
0x5699  ldarg.s  4
0x569b  ldarg.s  5
0x569d  call     instance bool Microsoft.Crm.Service.ObjectModel.RuleServiceBase::InternalSetState(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker moniker, int32 newState, int32 newStatusCode, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity originalEntity, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x56a2  stloc.3
0x56a3  ldarg.0
0x56a4  ldarg.1
0x56a5  ldarg.s  5
0x56a7  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity Microsoft.Crm.Service.ObjectModel.ConvertRuleService::RetrieveConvertRuleRecord(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker moniker, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x56ac  starg.s  4
0x56ae  ldarg.s  4
0x56b0  castclass [Microsoft.Crm.Service.Entities]Microsoft.Crm.Service.Entities.ConvertRule
0x56b5  ldstr    aWorkflowid// "workflowid"
0x56ba  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x56bf  stloc.s  4
0x56c1  ldc.i4.1
0x56c2  stloc.s  5
0x56c4  ldloc.s  4
0x56c6  brfalse.s loc_56DD
0x56c8  ldarg.0
0x56c9  ldarg.2
0x56ca  ldarg.s  5
0x56cc  ldloc.3
0x56cd  ldloc.1
0x56ce  ldloc.s  4
0x56d0  unbox.any [mscorlib]System.Guid
0x56d5  ldloc.0
0x56d6  callvirt instance bool Microsoft.Crm.Service.ObjectModel.RuleServiceBase::SetStateWorkflow(int32 newState, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context, bool isConvertRuleStateChanged, class [Microsoft.Crm.Entities]Microsoft.Crm.Entities.WorkflowEntity workflowEntity, valuetype [mscorlib]System.Guid workflowId, class [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.WorkflowService workflowService)
0x56db  stloc.s  5
0x56dd  ldarg.0
0x56de  ldarg.1
0x56df  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker::get_Id()
0x56e4  ldarg.s  5
0x56e6  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection Microsoft.Crm.Service.ObjectModel.ConvertRuleService::RetrieveConvertRuleItemWorkflows(valuetype [mscorlib]System.Guid convertRuleId, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x56eb  stloc.s  6
0x56ed  ldloc.s  5
0x56ef  brfalse  loc_579A
0x56f4  ldloc.s  6
0x56f6  callvirt instance int32 [mscorlib]System.Collections.CollectionBase::get_Count()
0x56fb  ldc.i4.0
0x56fc  ble      loc_579A
0x5701  ldnull
0x5702  stloc.s  7
0x5704  ldarg.2
0x5705  brtrue.s loc_5717
0x5707  ldstr    aIncident_0// "incident"
0x570c  ldarg.1
0x570d  ldarg.s  5
0x570f  ldc.i4.2
0x5710  call     class [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.IWorkflowAuthorService Microsoft.Crm.Service.ObjectModel.WorkflowAuthorServiceFactory::Create(string entityName, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker moniker, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context, valuetype [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.WorkflowAuthorType type)
0x5715  stloc.s  7
0x5717  ldloc.s  6
0x5719  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.CollectionBase::GetEnumerator()
0x571e  stloc.s  8
0x5720  br.s     loc_5765
0x5722  ldloc.s  8
0x5724  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x5729  castclass [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity
0x572e  stloc.s  9
0x5730  ldloc.s  9
0x5732  ldstr    aWorkflowid// "workflowid"
0x5737  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::IsAttributeNull(string)
0x573c  brtrue.s loc_5765
0x573e  ldloc.s  9
0x5740  ldstr    aWorkflowid// "workflowid"
0x5745  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x574a  unbox.any [mscorlib]System.Guid
0x574f  stloc.s  0xA
0x5751  ldarg.0
0x5752  ldarg.2
0x5753  ldarg.s  5
0x5755  ldloc.3
0x5756  ldloc.1
0x5757  ldloc.s  0xA
0x5759  ldloc.0
0x575a  callvirt instance bool Microsoft.Crm.Service.ObjectModel.RuleServiceBase::SetStateWorkflow(int32 newState, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context, bool isConvertRuleStateChanged, class [Microsoft.Crm.Entities]Microsoft.Crm.Entities.WorkflowEntity workflowEntity, valuetype [mscorlib]System.Guid workflowId, class [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.WorkflowService workflowService)
0x575f  stloc.2
0x5760  ldloc.2
0x5761  brtrue.s loc_5765
0x5763  leave.s  loc_5785
0x5765  ldloc.s  8
0x5767  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x576c  brtrue.s loc_5722
0x576e  leave.s  loc_5785
0x5770  ldloc.s  8
0x5772  isinst   [mscorlib]System.IDisposable
0x5777  stloc.s  0xB
0x5779  ldloc.s  0xB
0x577b  brfalse.s loc_5784
0x577d  ldloc.s  0xB
0x577f  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x5784  endfinally
0x5785  ldarg.2
0x5786  brtrue.s loc_5795
0x5788  ldloc.s  7
0x578a  brfalse.s loc_5795
0x578c  ldloc.s  7
0x578e  ldloc.s  6
0x5790  callvirt instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.IWorkflowAuthorService::RemoveStepsonDeactivate(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection)
0x5795  ldloc.2
0x5796  ldloc.s  5
0x5798  and
0x5799  ret
0x579a  ldloc.s  5
0x579c  ret
```
