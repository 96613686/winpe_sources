# Microsoft.Crm.Common.Application.Platform.WorkflowLibrary.ProfileRuleWorkflowAuthoringHelper::GetDefaultChannelAccessProfile

- ea: `0x5420`
- end: `0x548c`
- name: `Microsoft.Crm.Common.Application.Platform.WorkflowLibrary.ProfileRuleWorkflowAuthoringHelper::GetDefaultChannelAccessProfile`
- size: `108`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x52f0`

## callees

- `0x5420`

## string_xrefs

- `0x5450`: `channelaccessprofileid`
- `0x5420`: `channelaccessprofile`

## pseudocode

```c

```

## disassembly

```asm
0x5420  ldstr    aChannelaccessp_2// "channelaccessprofile"
0x5425  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression::.ctor(string)
0x542a  stloc.0
0x542b  ldloc.0
0x542c  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.FilterExpression [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression::get_Criteria()
0x5431  ldstr    aIsguestprofile// "isguestprofile"
0x5436  ldc.i4.0
0x5437  ldc.i4.1
0x5438  box      [mscorlib]System.Boolean
0x543d  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionExpression::.ctor(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0x5442  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.FilterExpression::AddCondition(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionExpression)
0x5447  ldloc.0
0x5448  ldc.i4.2
0x5449  newarr   [mscorlib]System.String
0x544e  dup
0x544f  ldc.i4.0
0x5450  ldstr    aChannelaccessp_1// "channelaccessprofileid"
0x5455  stelem.ref
0x5456  dup
0x5457  ldc.i4.1
0x5458  ldstr    aName// "name"
0x545d  stelem.ref
0x545e  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ColumnSet::.ctor(string[])
0x5463  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression::set_ColumnSet(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ColumnSet)
0x5468  ldarg.0
0x5469  call     instance class [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.ISdkCommand [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.WorkflowLibrary.WorkflowAuthoringBase::get_SdkCommand()
0x546e  ldloc.0
0x546f  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityCollection [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.ISdkCommand::RetrieveMultiple(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression)
0x5474  stloc.1
0x5475  ldloc.1
0x5476  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity> [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityCollection::get_Entities()
0x547b  callvirt instance int32 class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::get_Count()
0x5480  brtrue.s loc_5484
0x5482  ldnull
0x5483  ret
0x5484  ldloc.1
0x5485  ldc.i4.0
0x5486  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityCollection::get_Item(int32)
0x548b  ret
```
