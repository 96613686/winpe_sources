# Microsoft.Crm.Workflow.AsyncWorkflowSaveInstanceStateCommand::get_Id

- ea: `0x27f0`
- end: `0x2813`
- name: `Microsoft.Crm.Workflow.AsyncWorkflowSaveInstanceStateCommand::get_Id`
- size: `35`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## pseudocode

```c

```

## disassembly

```asm
0x27f0  ldstr    aWorkflowstate_0// "WorkflowState_"
0x27f5  ldarg.0
0x27f6  ldfld    class [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.ICommonWorkflowContext Microsoft.Crm.Workflow.AsyncWorkflowSaveInstanceStateCommand::_context
0x27fb  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext::get_OperationId()
0x2800  stloc.0
0x2801  ldloca.s 0
0x2803  ldstr    aB// "B"
0x2808  call     instance string [mscorlib]System.Guid::ToString(string)
0x280d  call     string [mscorlib]System.String::Concat(string, string)
0x2812  ret
```
