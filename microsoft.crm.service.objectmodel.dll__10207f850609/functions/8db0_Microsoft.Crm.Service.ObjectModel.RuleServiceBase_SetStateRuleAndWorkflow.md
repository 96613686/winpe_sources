# Microsoft.Crm.Service.ObjectModel.RuleServiceBase::SetStateRuleAndWorkflow

- ea: `0x8db0`
- end: `0x8e8d`
- name: `Microsoft.Crm.Service.ObjectModel.RuleServiceBase::SetStateRuleAndWorkflow`
- size: `221`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x8bb0`

## callees

- `0x8db0`
- `0x8e90`
- `0x8ed0`
- `0xb430`

## pseudocode

```c

```

## disassembly

```asm
0x8db0  newobj   instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.WorkflowService::.ctor()
0x8db5  stloc.0
0x8db6  ldarg.s  5
0x8db8  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x8dbd  newobj   instance void [Microsoft.Crm.Entities]Microsoft.Crm.Entities.WorkflowEntity::.ctor(valuetype [mscorlib]System.Guid)
0x8dc2  stloc.1
0x8dc3  ldarg.2
0x8dc4  ldc.i4.1
0x8dc5  bne.un.s loc_8E1E
0x8dc7  ldarg.s  4
0x8dc9  ldstr    aStatecode// "statecode"
0x8dce  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x8dd3  unbox.any [mscorlib]System.Int32
0x8dd8  ldc.i4.1
0x8dd9  bne.un.s loc_8DEC
0x8ddb  ldc.i4   0x8004F852
0x8de0  ldc.i4.0
0x8de1  newarr   [mscorlib]System.Object
0x8de6  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(int32, object[])
0x8deb  throw
0x8dec  ldstr    aIncident_0// "incident"
0x8df1  ldarg.1
0x8df2  ldarg.s  5
0x8df4  ldc.i4.2
0x8df5  call     class [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.IWorkflowAuthorService Microsoft.Crm.Service.ObjectModel.WorkflowAuthorServiceFactory::Create(string entityName, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker moniker, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context, valuetype [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.WorkflowAuthorType type)
0x8dfa  callvirt instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.IWorkflowAuthorService::AuthorWorkflow()
0x8dff  ldarg.1
0x8e00  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker::get_EntityMetadata()
0x8e05  ldarg.s  5
0x8e07  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x8e0c  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.EntityClassFactory::CreateInstance(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata, valuetype [mscorlib]System.Guid)
0x8e11  starg.s  4
0x8e13  ldarg.0
0x8e14  ldarg.1
0x8e15  ldarg.s  5
0x8e17  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity Microsoft.Crm.Service.ObjectModel.RuleServiceBase::RetrieveConvertRuleRecord(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker moniker, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x8e1c  starg.s  4
0x8e1e  leave.s  loc_8E2B
0x8e20  callvirt instance string [mscorlib]System.Exception::get_Message()
0x8e25  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string)
0x8e2a  throw
0x8e2b  ldarg.s  5
0x8e2d  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.CrmTransaction [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_Transaction()
0x8e32  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmTransaction::StartTransaction()
0x8e37  ldarg.0
0x8e38  ldarg.1
0x8e39  ldarg.2
0x8e3a  ldarg.3
0x8e3b  ldarg.s  4
0x8e3d  ldarg.s  5
0x8e3f  call     instance bool [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::InternalSetState(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker, int32, int32, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x8e44  stloc.2
0x8e45  ldc.i4.1
0x8e46  stloc.3
0x8e47  ldarg.s  4
0x8e49  ldstr    aWorkflowid// "workflowid"
0x8e4e  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x8e53  stloc.s  4
0x8e55  ldloc.s  4
0x8e57  brfalse.s loc_8E6D
0x8e59  ldarg.0
0x8e5a  ldarg.2
0x8e5b  ldarg.s  5
0x8e5d  ldloc.2
0x8e5e  ldloc.1
0x8e5f  ldloc.s  4
0x8e61  unbox.any [mscorlib]System.Guid
0x8e66  ldloc.0
0x8e67  callvirt instance bool Microsoft.Crm.Service.ObjectModel.RuleServiceBase::SetStateWorkflow(int32 newState, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context, bool isConvertRuleStateChanged, class [Microsoft.Crm.Entities]Microsoft.Crm.Entities.WorkflowEntity workflowEntity, valuetype [mscorlib]System.Guid workflowId, class [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.WorkflowService workflowService)
0x8e6c  stloc.3
0x8e6d  ldloc.3
0x8e6e  brfalse.s loc_8E7E
0x8e70  ldarg.s  5
0x8e72  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.CrmTransaction [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_Transaction()
0x8e77  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmTransaction::CommitTransaction()
0x8e7c  br.s     loc_8E8B
0x8e7e  ldarg.s  5
0x8e80  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.CrmTransaction [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_Transaction()
0x8e85  ldc.i4.1
0x8e86  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmTransaction::RollbackTransaction(bool)
0x8e8b  ldloc.3
0x8e8c  ret
```
