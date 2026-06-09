# Microsoft.Crm.Workflow.SynchronousRuntime.WorkflowDataAccess::UpdateWorkflowInstanceStage

- ea: `0x11d90`
- end: `0x11db5`
- name: `Microsoft.Crm.Workflow.SynchronousRuntime.WorkflowDataAccess::UpdateWorkflowInstanceStage`
- size: `37`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `installer_update, broker_com_uri`

## string_xrefs

- `0x11d97`: `Interactive Workflow {0} has moved to stage '{1}'.`

## pseudocode

```c

```

## disassembly

```asm
0x11d90  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x11d95  ldc.i4.s 0x1E
0x11d97  ldstr    aInteractiveWor_1// "Interactive Workflow {0} has moved to s"...
0x11d9c  ldc.i4.2
0x11d9d  newarr   [mscorlib]System.Object
0x11da2  dup
0x11da3  ldc.i4.0
0x11da4  ldarg.1
0x11da5  box      [mscorlib]System.Guid
0x11daa  stelem.ref
0x11dab  dup
0x11dac  ldc.i4.1
0x11dad  ldarg.2
0x11dae  stelem.ref
0x11daf  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x11db4  ret
```
