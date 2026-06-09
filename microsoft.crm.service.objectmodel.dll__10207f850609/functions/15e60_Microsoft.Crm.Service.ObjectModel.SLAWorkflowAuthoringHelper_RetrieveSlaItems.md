# Microsoft.Crm.Service.ObjectModel.SLAWorkflowAuthoringHelper::RetrieveSlaItems

- ea: `0x15e60`
- end: `0x15f0a`
- name: `Microsoft.Crm.Service.ObjectModel.SLAWorkflowAuthoringHelper::RetrieveSlaItems`
- size: `170`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x15700`

## string_xrefs

- `0x15ee2`: `applicablewhenxml`

## pseudocode

```c

```

## disassembly

```asm
0x15e60  ldarg.2
0x15e61  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression::.ctor(string)
0x15e66  stloc.0
0x15e67  ldloc.0
0x15e68  ldstr    aSla// "sla"
0x15e6d  ldstr    aSlaid// "slaid"
0x15e72  ldstr    aSlaid// "slaid"
0x15e77  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.LinkEntity [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression::AddLink(string, string, string)
0x15e7c  pop
0x15e7d  ldloc.0
0x15e7e  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.FilterExpression [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression::get_Criteria()
0x15e83  ldstr    aSlaid// "slaid"
0x15e88  ldc.i4.0
0x15e89  ldarg.1
0x15e8a  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionExpression::.ctor(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0x15e8f  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.FilterExpression::AddCondition(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionExpression)
0x15e94  ldloc.0
0x15e95  ldstr    aRelatedfield// "relatedfield"
0x15e9a  ldc.i4.0
0x15e9b  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression::AddOrder(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.OrderType)
0x15ea0  ldloc.0
0x15ea1  ldstr    aSequencenumber// "sequencenumber"
0x15ea6  ldc.i4.0
0x15ea7  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression::AddOrder(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.OrderType)
0x15eac  ldloc.0
0x15ead  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ColumnSet [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression::get_ColumnSet()
0x15eb2  ldc.i4.8
0x15eb3  newarr   [mscorlib]System.String
0x15eb8  dup
0x15eb9  ldc.i4.0
0x15eba  ldstr    aName// "name"
0x15ebf  stelem.ref
0x15ec0  dup
0x15ec1  ldc.i4.1
0x15ec2  ldstr    aWorkflowid// "workflowid"
0x15ec7  stelem.ref
0x15ec8  dup
0x15ec9  ldc.i4.2
0x15eca  ldstr    aRelatedfield// "relatedfield"
0x15ecf  stelem.ref
0x15ed0  dup
0x15ed1  ldc.i4.3
0x15ed2  ldstr    aSequencenumber// "sequencenumber"
0x15ed7  stelem.ref
0x15ed8  dup
0x15ed9  ldc.i4.4
0x15eda  ldstr    aSlaitemid// "slaitemid"
0x15edf  stelem.ref
0x15ee0  dup
0x15ee1  ldc.i4.5
0x15ee2  ldstr    aApplicablewhen// "applicablewhenxml"
0x15ee7  stelem.ref
0x15ee8  dup
0x15ee9  ldc.i4.6
0x15eea  ldstr    aFailureafter// "failureafter"
0x15eef  stelem.ref
0x15ef0  dup
0x15ef1  ldc.i4.7
0x15ef2  ldstr    aWarnafter// "warnafter"
0x15ef7  stelem.ref
0x15ef8  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ColumnSet::AddColumns(string[])
0x15efd  ldarg.0
0x15efe  call     instance class [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.ISdkCommand [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.WorkflowLibrary.WorkflowAuthoringBase::get_SdkCommand()
0x15f03  ldloc.0
0x15f04  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityCollection [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.ISdkCommand::RetrieveMultiple(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression)
0x15f09  ret
```
