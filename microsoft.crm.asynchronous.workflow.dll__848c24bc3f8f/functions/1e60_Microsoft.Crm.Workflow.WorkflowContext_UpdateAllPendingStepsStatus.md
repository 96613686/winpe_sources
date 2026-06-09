# Microsoft.Crm.Workflow.WorkflowContext::UpdateAllPendingStepsStatus

- ea: `0x1e60`
- end: `0x1f30`
- name: `Microsoft.Crm.Workflow.WorkflowContext::UpdateAllPendingStepsStatus`
- size: `208`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callees

- `0x1e60`
- `0x28a0`

## pseudocode

```c

```

## disassembly

```asm
0x1e60  ldarg.0
0x1e61  ldfld    class Microsoft.Crm.Workflow.IWorkflowLogPersistentStrategy Microsoft.Crm.Workflow.WorkflowContext::_workflowLogPersistentStrategy
0x1e66  callvirt instance void Microsoft.Crm.Workflow.IWorkflowLogPersistentStrategy::Flush()
0x1e6b  ldarg.0
0x1e6c  ldc.i4.1
0x1e6d  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationService [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.WorkflowContextBase::CreateSdkService(bool)
0x1e72  stloc.0
0x1e73  ldc.i4   0x199
0x1e78  stloc.s  4
0x1e7a  ldloca.s 4
0x1e7c  constrained. [Microsoft.Crm.Sdk.Reserved]Microsoft.Crm.Extensibility.EntityName
0x1e82  callvirt instance string [mscorlib]System.Object::ToString()
0x1e87  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression::.ctor(string)
0x1e8c  stloc.1
0x1e8d  ldstr    aStatus// "status"
0x1e92  ldc.i4.8
0x1e93  ldc.i4.2
0x1e94  newarr   [mscorlib]System.Object
0x1e99  dup
0x1e9a  ldc.i4.0
0x1e9b  ldc.i4.1
0x1e9c  box      [mscorlib]System.Int32
0x1ea1  stelem.ref
0x1ea2  dup
0x1ea3  ldc.i4.1
0x1ea4  ldc.i4.5
0x1ea5  box      [mscorlib]System.Int32
0x1eaa  stelem.ref
0x1eab  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionExpression::.ctor(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object[])
0x1eb0  stloc.2
0x1eb1  ldstr    aAsyncoperation_1// "asyncoperationid"
0x1eb6  ldc.i4.0
0x1eb7  ldarg.0
0x1eb8  call     instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.WorkflowContextBase::get_OperationId()
0x1ebd  box      [mscorlib]System.Guid
0x1ec2  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionExpression::.ctor(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0x1ec7  stloc.3
0x1ec8  ldloc.1
0x1ec9  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.FilterExpression [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression::get_Criteria()
0x1ece  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionExpression> [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.FilterExpression::get_Conditions()
0x1ed3  ldloc.2
0x1ed4  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionExpression>::Add(var<u1>)
0x1ed9  ldloc.1
0x1eda  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.FilterExpression [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression::get_Criteria()
0x1edf  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionExpression> [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.FilterExpression::get_Conditions()
0x1ee4  ldloc.3
0x1ee5  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionExpression>::Add(var<u1>)
0x1eea  ldloc.0
0x1eeb  ldloc.1
0x1eec  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationService::RetrieveMultiple(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryBase)
0x1ef1  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity> [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityCollection::get_Entities()
0x1ef6  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::GetEnumerator()
0x1efb  stloc.s  5
0x1efd  br.s     loc_1F18
0x1eff  ldloc.s  5
0x1f01  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::get_Current()
0x1f06  stloc.s  6
0x1f08  ldarg.0
0x1f09  ldloc.s  6
0x1f0b  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Id()
0x1f10  ldarg.2
0x1f11  ldarg.1
0x1f12  ldarg.3
0x1f13  callvirt instance void [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.WorkflowContextBase::UpdateWorkflowLog(valuetype [mscorlib]System.Guid, int32, string, int32)
0x1f18  ldloc.s  5
0x1f1a  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x1f1f  brtrue.s loc_1EFF
0x1f21  leave.s  loc_1F2F
0x1f23  ldloc.s  5
0x1f25  brfalse.s loc_1F2E
0x1f27  ldloc.s  5
0x1f29  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1f2e  endfinally
0x1f2f  ret
```
