# Microsoft.Crm.Workflow.Services.ChildInteractiveWorkflowActivityService::ValidateWorkflowAndGetActiveWorkflowId

- ea: `0x16120`
- end: `0x16274`
- name: `Microsoft.Crm.Workflow.Services.ChildInteractiveWorkflowActivityService::ValidateWorkflowAndGetActiveWorkflowId`
- size: `340`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x2e9a0`

## callees

- `0x8e70`
- `0x8ed0`
- `0x13fb0`
- `0x14150`
- `0x14360`
- `0x14770`
- `0x16120`

## pseudocode

```c

```

## disassembly

```asm
0x16120  ldstr    aWorkflow// "workflow"
0x16125  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression::.ctor(string)
0x1612a  stloc.0
0x1612b  ldloc.0
0x1612c  ldc.i4.2
0x1612d  newarr   [mscorlib]System.String
0x16132  dup
0x16133  ldc.i4.0
0x16134  ldstr    aActiveworkflow// "activeworkflowid"
0x16139  stelem.ref
0x1613a  dup
0x1613b  ldc.i4.1
0x1613c  ldstr    aInputparameter// "inputparameters"
0x16141  stelem.ref
0x16142  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ColumnSet::.ctor(string[])
0x16147  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression::set_ColumnSet(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ColumnSet)
0x1614c  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.FilterExpression::.ctor()
0x16151  stloc.1
0x16152  ldloc.0
0x16153  ldloc.1
0x16154  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression::set_Criteria(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.FilterExpression)
0x16159  ldloc.1
0x1615a  ldstr    aSubprocess// "subprocess"
0x1615f  ldc.i4.0
0x16160  ldc.i4.1
0x16161  newarr   [mscorlib]System.Object
0x16166  dup
0x16167  ldc.i4.0
0x16168  ldc.i4.1
0x16169  box      [mscorlib]System.Boolean
0x1616e  stelem.ref
0x1616f  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object[])
0x16174  ldloc.1
0x16175  ldstr    aWorkflowid// "workflowid"
0x1617a  ldc.i4.0
0x1617b  ldc.i4.1
0x1617c  newarr   [mscorlib]System.Object
0x16181  dup
0x16182  ldc.i4.0
0x16183  ldarg.2
0x16184  box      [mscorlib]System.Guid
0x16189  stelem.ref
0x1618a  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object[])
0x1618f  ldloc.1
0x16190  ldstr    aType// "type"
0x16195  ldc.i4.0
0x16196  ldc.i4.1
0x16197  newarr   [mscorlib]System.Object
0x1619c  dup
0x1619d  ldc.i4.0
0x1619e  ldc.i4.1
0x1619f  box      [mscorlib]System.Int32
0x161a4  stelem.ref
0x161a5  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object[])
0x161aa  ldloc.1
0x161ab  ldstr    aStatecode// "statecode"
0x161b0  ldc.i4.0
0x161b1  ldc.i4.1
0x161b2  newarr   [mscorlib]System.Object
0x161b7  dup
0x161b8  ldc.i4.0
0x161b9  ldc.i4.1
0x161ba  box      [mscorlib]System.Int32
0x161bf  stelem.ref
0x161c0  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object[])
0x161c5  ldloc.1
0x161c6  ldstr    aActiveworkflow// "activeworkflowid"
0x161cb  ldc.i4.s 0xD
0x161cd  ldc.i4.0
0x161ce  newarr   [mscorlib]System.Object
0x161d3  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object[])
0x161d8  ldloc.1
0x161d9  ldstr    aCategory// "category"
0x161de  ldc.i4.0
0x161df  ldc.i4.1
0x161e0  newarr   [mscorlib]System.Object
0x161e5  dup
0x161e6  ldc.i4.0
0x161e7  ldc.i4.1
0x161e8  box      [mscorlib]System.Int32
0x161ed  stelem.ref
0x161ee  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object[])
0x161f3  ldarg.1
0x161f4  ldloc.0
0x161f5  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationService::RetrieveMultiple(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryBase)
0x161fa  stloc.2
0x161fb  ldloc.2
0x161fc  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity> [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityCollection::get_Entities()
0x16201  callvirt instance int32 class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::get_Count()
0x16206  ldc.i4.1
0x16207  beq.s    loc_1621A
0x16209  ldc.i4   0x8004502F
0x1620e  ldc.i4.0
0x1620f  newarr   [mscorlib]System.Object
0x16214  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(int32, object[])
0x16219  throw
0x1621a  ldloc.2
0x1621b  ldc.i4.0
0x1621c  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityCollection::get_Item(int32)
0x16221  ldstr    aInputparameter// "inputparameters"
0x16226  callvirt instance object [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Item(string)
0x1622b  castclass [mscorlib]System.String
0x16230  call     class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Type> Microsoft.Crm.Workflow.Services.InputArgumentValidator::BuildInputParameterDictionary(string childInputParametersXml)
0x16235  stloc.3
0x16236  ldarg.3
0x16237  ldloc.3
0x16238  call     void Microsoft.Crm.Workflow.Services.InputArgumentValidator::VerifyAndFilterInputParametersSupplied(class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> inputArguments, class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Type> childParameters)
0x1623d  ldarg.0
0x1623e  call     instance class Microsoft.Crm.Workflow.ICommonWorkflowContext Microsoft.Crm.Workflow.Services.ActivityServiceBase::get_WorkflowContext()
0x16243  newobj   instance void Microsoft.Crm.Workflow.WorkflowUserContext::.ctor(class Microsoft.Crm.Workflow.ICommonWorkflowContext workflowContext)
0x16248  call     instance class [mscorlib]System.Globalization.CultureInfo Microsoft.Crm.Workflow.WorkflowUserContext::get_CultureInfo()
0x1624d  stloc.s  4
0x1624f  ldarg.3
0x16250  ldloc.3
0x16251  ldloc.s  4
0x16253  call     void Microsoft.Crm.Workflow.Services.InputArgumentValidator::FixInputParametersType(class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> inputArguments, class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Type> childParameters, class [mscorlib]System.Globalization.CultureInfo culture)
0x16258  ldloc.2
0x16259  ldc.i4.0
0x1625a  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityCollection::get_Item(int32)
0x1625f  ldstr    aActiveworkflow// "activeworkflowid"
0x16264  callvirt instance object [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Item(string)
0x16269  castclass [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference
0x1626e  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference::get_Id()
0x16273  ret
```
