# Microsoft.Crm.Service.ObjectModel.SLAWorkflowAuthoringHelper::AuthorWorkflow_0

- ea: `0x15560`
- end: `0x156f2`
- name: `Microsoft.Crm.Service.ObjectModel.SLAWorkflowAuthoringHelper::AuthorWorkflow_0`
- size: `402`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x9310`
- `0x15550`

## callees

- `0x15560`
- `0x15700`

## pseudocode

```c

```

## disassembly

```asm
0x15560  ldc.i4.4
0x15561  newarr   [mscorlib]System.String
0x15566  dup
0x15567  ldc.i4.0
0x15568  ldstr    aName// "name"
0x1556d  stelem.ref
0x1556e  dup
0x1556f  ldc.i4.1
0x15570  ldstr    aApplicablefrom// "applicablefrom"
0x15575  stelem.ref
0x15576  dup
0x15577  ldc.i4.2
0x15578  ldstr    aOwnerid// "ownerid"
0x1557d  stelem.ref
0x1557e  dup
0x1557f  ldc.i4.3
0x15580  ldstr    aSlatype// "slatype"
0x15585  stelem.ref
0x15586  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ColumnSet::.ctor(string[])
0x1558b  stloc.0
0x1558c  ldarg.0
0x1558d  call     instance class [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.ISdkCommand [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.WorkflowLibrary.WorkflowAuthoringBase::get_SdkCommand()
0x15592  ldstr    aSla// "sla"
0x15597  ldarg.1
0x15598  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x1559d  ldloc.0
0x1559e  ldc.i4.0
0x1559f  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.ISdkCommand::Retrieve(string, valuetype [mscorlib]System.Guid, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ColumnSet, bool)
0x155a4  stloc.1
0x155a5  ldarg.0
0x155a6  ldloc.1
0x155a7  ldstr    aName// "name"
0x155ac  callvirt instance object [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Item(string)
0x155b1  callvirt instance string [mscorlib]System.Object::ToString()
0x155b6  call     instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.WorkflowLibrary.WorkflowAuthoringBase::set_WorkflowName(string)
0x155bb  ldarg.0
0x155bc  ldarg.2
0x155bd  call     instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.WorkflowLibrary.WorkflowAuthoringBase::set_PrimaryEntityName(string)
0x155c2  ldarg.0
0x155c3  ldc.i4.0
0x155c4  call     instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.WorkflowLibrary.WorkflowAuthoringBase::set_WorkflowCategory(int32)
0x155c9  ldarg.0
0x155ca  ldc.i4.1
0x155cb  call     instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.WorkflowLibrary.WorkflowAuthoringBase::set_IsSyncWorkflow(bool)
0x155d0  ldarg.0
0x155d1  call     instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.WorkflowLibrary.WorkflowAuthoringBase::CreateWorkflow()
0x155d6  stloc.2
0x155d7  ldloc.1
0x155d8  ldstr    aSlatype// "slatype"
0x155dd  callvirt instance bool [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::Contains(string)
0x155e2  brfalse  loc_156C7
0x155e7  ldloc.1
0x155e8  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributeCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Attributes()
0x155ed  ldstr    aSlatype// "slatype"
0x155f2  callvirt instance var<u1> class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::get_Item(void)
0x155f7  castclass [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OptionSetValue
0x155fc  callvirt instance int32 [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OptionSetValue::get_Value()
0x15601  ldc.i4.1
0x15602  bne.un   loc_156C7
0x15607  ldarg.0
0x15608  ldc.i4.1
0x15609  stfld    bool Microsoft.Crm.Service.ObjectModel.SLAWorkflowAuthoringHelper::useSLAKPI
0x1560e  ldstr    aInvokechildwfs// "invokechildwfs"
0x15613  ldtoken  [mscorlib]System.Int32
0x15618  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1561d  ldc.i4.1
0x1561e  call     string [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep::ConstructIdentifierName(string, class [mscorlib]System.Type, bool)
0x15623  stloc.3
0x15624  ldloc.2
0x15625  ldloc.3
0x15626  ldtoken  [mscorlib]System.Int32
0x1562b  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x15630  ldc.i4.1
0x15631  box      [mscorlib]System.Int32
0x15636  ldc.i4.1
0x15637  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep::AddVariable(string, class [mscorlib]System.Type, object, bool)
0x1563c  ldstr    aOnholdtime// "onholdtime"
0x15641  ldtoken  [mscorlib]System.Int32
0x15646  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1564b  ldc.i4.1
0x1564c  call     string [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep::ConstructIdentifierName(string, class [mscorlib]System.Type, bool)
0x15651  stloc.s  4
0x15653  ldloc.2
0x15654  ldloc.s  4
0x15656  ldtoken  [mscorlib]System.Int32
0x1565b  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x15660  ldc.i4.0
0x15661  box      [mscorlib]System.Int32
0x15666  ldc.i4.1
0x15667  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep::AddVariable(string, class [mscorlib]System.Type, object, bool)
0x1566c  ldstr    aStatus// "status"
0x15671  ldtoken  [mscorlib]System.Int32
0x15676  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1567b  ldc.i4.1
0x1567c  call     string [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep::ConstructIdentifierName(string, class [mscorlib]System.Type, bool)
0x15681  stloc.s  5
0x15683  ldloc.2
0x15684  ldloc.s  5
0x15686  ldtoken  [mscorlib]System.Int32
0x1568b  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x15690  ldc.i4.0
0x15691  box      [mscorlib]System.Int32
0x15696  ldc.i4.1
0x15697  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep::AddVariable(string, class [mscorlib]System.Type, object, bool)
0x1569c  ldarg.0
0x1569d  ldloc.2
0x1569e  ldloc.1
0x1569f  ldarg.1
0x156a0  ldarg.2
0x156a1  ldstr    aSlaitem_0// "slaitem"
0x156a6  ldarg.3
0x156a7  ldarg.0
0x156a8  ldftn    instance class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase Microsoft.Crm.Service.ObjectModel.SlaWorkflowForKPIHelper::AddUpdateEntityStepForSLAKPI(string stepId, string applicableFrom, string relatedKPI, class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep workflowStep, string stepDescription, int32 failureAfter, int32 warnAfter)
0x156ae  newobj   instance void class [mscorlib]System.Func`8<string, string, string, class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep, string, int32, int32, class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase>::.ctor(object, native int)
0x156b3  ldarg.0
0x156b4  ldftn    instance class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase Microsoft.Crm.Service.ObjectModel.SlaWorkflowForKPIHelper::SetRelatedKPIForSLAKPI(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep workflowStep, string applicableFrom, int32 failureAfter)
0x156ba  newobj   instance void class [mscorlib]System.Func`4<class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep, string, int32, class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase>::.ctor(object, native int)
0x156bf  ldarg.s  4
0x156c1  call     instance string Microsoft.Crm.Service.ObjectModel.SLAWorkflowAuthoringHelper::AuthorWorkflow(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep workflowStep, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity parentEntity, string entityId, string primaryEntityName, string childEntityName, class [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.IWorkflowErrorVisitorContext workflowErrorVisitorContext, class [mscorlib]System.Func`8<string, string, string, class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep, string, int32, int32, class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase> addUpdateEntityStepMethod, class [mscorlib]System.Func`4<class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep, string, int32, class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase> setRelatedKPIMethod, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext executionContext)
0x156c6  ret
0x156c7  ldarg.0
0x156c8  ldloc.2
0x156c9  ldloc.1
0x156ca  ldarg.1
0x156cb  ldarg.2
0x156cc  ldstr    aSlaitem_0// "slaitem"
0x156d1  ldarg.3
0x156d2  ldarg.0
0x156d3  ldftn    instance class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase Microsoft.Crm.Service.ObjectModel.SLAWorkflowAuthoringHelper::AddUpdateEntityStep(string stepid, string _applicableFrom, string relatedKpi, class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep workflowStep, string stepDescription, int32 _failureAfter, int32 warnAfter)
0x156d9  newobj   instance void class [mscorlib]System.Func`8<string, string, string, class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep, string, int32, int32, class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase>::.ctor(object, native int)
0x156de  ldarg.0
0x156df  ldftn    instance class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase Microsoft.Crm.Service.ObjectModel.SLAWorkflowAuthoringHelper::SetRelatedKpi(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep workflowStep, string _applicableFrom, int32 _failureAfter)
0x156e5  newobj   instance void class [mscorlib]System.Func`4<class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep, string, int32, class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase>::.ctor(object, native int)
0x156ea  ldarg.s  4
0x156ec  call     instance string Microsoft.Crm.Service.ObjectModel.SLAWorkflowAuthoringHelper::AuthorWorkflow(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep workflowStep, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity parentEntity, string entityId, string primaryEntityName, string childEntityName, class [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.IWorkflowErrorVisitorContext workflowErrorVisitorContext, class [mscorlib]System.Func`8<string, string, string, class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep, string, int32, int32, class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase> addUpdateEntityStepMethod, class [mscorlib]System.Func`4<class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep, string, int32, class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase> setRelatedKPIMethod, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext executionContext)
0x156f1  ret
```
