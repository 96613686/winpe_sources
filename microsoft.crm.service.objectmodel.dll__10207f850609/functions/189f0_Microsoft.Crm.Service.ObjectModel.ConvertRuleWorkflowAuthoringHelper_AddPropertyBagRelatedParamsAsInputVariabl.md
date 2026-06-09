# Microsoft.Crm.Service.ObjectModel.ConvertRuleWorkflowAuthoringHelper::AddPropertyBagRelatedParamsAsInputVariable

- ea: `0x189f0`
- end: `0x18ab7`
- name: `Microsoft.Crm.Service.ObjectModel.ConvertRuleWorkflowAuthoringHelper::AddPropertyBagRelatedParamsAsInputVariable`
- size: `199`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x17e90`
- `0x18880`

## callees

- `0x189f0`
- `0x18ac0`

## pseudocode

```c

```

## disassembly

```asm
0x189f0  ldstr    aChannelpropert_2// "channelproperty"
0x189f5  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression::.ctor(string)
0x189fa  stloc.0
0x189fb  ldloc.0
0x189fc  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.FilterExpression [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression::get_Criteria()
0x18a01  ldstr    aRegardingobjec// "regardingobjectid"
0x18a06  ldc.i4.0
0x18a07  ldc.i4.1
0x18a08  newarr   [mscorlib]System.Object
0x18a0d  dup
0x18a0e  ldc.i4.0
0x18a0f  ldarg.1
0x18a10  stelem.ref
0x18a11  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object[])
0x18a16  ldloc.0
0x18a17  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ColumnSet [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression::get_ColumnSet()
0x18a1c  ldc.i4.1
0x18a1d  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ColumnSet::set_AllColumns(bool)
0x18a22  ldloc.0
0x18a23  ldstr    aName// "name"
0x18a28  ldc.i4.1
0x18a29  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression::AddOrder(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.OrderType)
0x18a2e  ldloc.0
0x18a2f  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x18a34  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ApplicationEntityCollection [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.DataSource::RetrieveMultiple(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x18a39  stloc.1
0x18a3a  ldloc.1
0x18a3b  callvirt instance int32 class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity>::get_Count()
0x18a40  ldc.i4.1
0x18a41  bge.s    loc_18A44
0x18a43  ret
0x18a44  ldarg.0
0x18a45  call     void Microsoft.Crm.Service.ObjectModel.ConvertRuleWorkflowAuthoringHelper::RemoveExistingWorkflowVariables(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep workflowStep)
0x18a4a  ldc.i4.0
0x18a4b  stloc.s  6
0x18a4d  br.s     loc_18AAC
0x18a4f  ldloc.1
0x18a50  ldloc.s  6
0x18a52  callvirt instance var<u1> class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity>::get_Item(!!T0)
0x18a57  ldstr    aDatatype// "datatype"
0x18a5c  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0x18a61  unbox.any [mscorlib]System.Int32
0x18a66  ldloca.s 3
0x18a68  ldloca.s 4
0x18a6a  ldloca.s 5
0x18a6c  call     void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.Any2AnyUtilities::GetDefaultDataForVariable(int32, object&, class [mscorlib]System.Type&, valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.WorkflowAttributeType&)
0x18a71  ldloc.1
0x18a72  ldloc.s  6
0x18a74  callvirt instance var<u1> class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity>::get_Item(!!T0)
0x18a79  ldstr    aName// "name"
0x18a7e  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0x18a83  callvirt instance string [mscorlib]System.Object::ToString()
0x18a88  ldloc.s  5
0x18a8a  ldc.i4.1
0x18a8b  call     string [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep::ConstructIdentifierName(string, valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.WorkflowAttributeType, bool)
0x18a90  stloc.2
0x18a91  ldarg.0
0x18a92  ldloc.2
0x18a93  ldc.i4.1
0x18a94  callvirt instance bool [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep::ContainsVariable(string, bool)
0x18a99  brtrue.s loc_18AA6
0x18a9b  ldarg.0
0x18a9c  ldloc.2
0x18a9d  ldloc.s  4
0x18a9f  ldloc.3
0x18aa0  ldc.i4.1
0x18aa1  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep::AddVariable(string, class [mscorlib]System.Type, object, bool)
0x18aa6  ldloc.s  6
0x18aa8  ldc.i4.1
0x18aa9  add
0x18aaa  stloc.s  6
0x18aac  ldloc.s  6
0x18aae  ldloc.1
0x18aaf  callvirt instance int32 class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity>::get_Count()
0x18ab4  blt.s    loc_18A4F
0x18ab6  ret
```
