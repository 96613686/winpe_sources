# Microsoft.Crm.Workflow.Services.ChildInteractiveWorkflowActivityService::ExecuteInternal

- ea: `0x16060`
- end: `0x1609f`
- name: `Microsoft.Crm.Workflow.Services.ChildInteractiveWorkflowActivityService::ExecuteInternal`
- size: `63`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x16040`

## callees

- `0x160a0`
- `0x2d000`
- `0x2d020`
- `0x2d040`
- `0x2d060`

## pseudocode

```c

```

## disassembly

```asm
0x16060  ldarg.2
0x16061  callvirt instance class [System.Activities]System.Activities.InArgument`1<string> Microsoft.Crm.Workflow.Activities.StartChildInteractiveWorkflow::get_EntityName()
0x16066  ldarg.1
0x16067  callvirt instance var<u1> class [System.Activities]System.Activities.InArgument`1<string>::Get(!!T0)
0x1606c  stloc.0
0x1606d  ldarg.2
0x1606e  callvirt instance class [System.Activities]System.Activities.InArgument`1<valuetype [mscorlib]System.Guid> Microsoft.Crm.Workflow.Activities.StartChildInteractiveWorkflow::get_EntityId()
0x16073  ldarg.1
0x16074  callvirt instance var<u1> class [System.Activities]System.Activities.InArgument`1<valuetype [mscorlib]System.Guid>::Get(!!T0)
0x16079  stloc.1
0x1607a  ldarg.2
0x1607b  callvirt instance class [System.Activities]System.Activities.InArgument`1<valuetype [mscorlib]System.Guid> Microsoft.Crm.Workflow.Activities.StartChildInteractiveWorkflow::get_WorkflowId()
0x16080  ldarg.1
0x16081  callvirt instance var<u1> class [System.Activities]System.Activities.InArgument`1<valuetype [mscorlib]System.Guid>::Get(!!T0)
0x16086  stloc.2
0x16087  ldarg.2
0x16088  callvirt instance class [System.Activities]System.Activities.InArgument`1<class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>> Microsoft.Crm.Workflow.Activities.StartChildInteractiveWorkflow::get_InputParameters()
0x1608d  ldarg.1
0x1608e  callvirt instance var<u1> class [System.Activities]System.Activities.InArgument`1<class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>>::Get(!!T0)
0x16093  stloc.3
0x16094  ldarg.0
0x16095  ldloc.0
0x16096  ldloc.1
0x16097  ldloc.2
0x16098  ldloc.3
0x16099  call     instance void Microsoft.Crm.Workflow.Services.ChildInteractiveWorkflowActivityService::StartChildInteractiveWorkflowInternal(string entityName, valuetype [mscorlib]System.Guid entityId, valuetype [mscorlib]System.Guid workflowDefinitionId, class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> inputArguments)
0x1609e  ret
```
