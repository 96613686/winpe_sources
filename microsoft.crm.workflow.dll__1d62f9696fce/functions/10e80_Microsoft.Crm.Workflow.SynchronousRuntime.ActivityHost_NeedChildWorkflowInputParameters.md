# Microsoft.Crm.Workflow.SynchronousRuntime.ActivityHost::NeedChildWorkflowInputParameters

- ea: `0x10e80`
- end: `0x10ec5`
- name: `Microsoft.Crm.Workflow.SynchronousRuntime.ActivityHost::NeedChildWorkflowInputParameters`
- size: `69`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x10c20`

## callees

- `0xd9d0`
- `0xd9f0`
- `0xda40`
- `0x10e80`
- `0x11470`

## string_xrefs

- `0x10e97`: `WorkflowStateXml is not expected when staring interactive child workflow first time.`

## pseudocode

```c

```

## disassembly

```asm
0x10e80  ldarg.1
0x10e81  isinst   Microsoft.Crm.Workflow.SynchronousRuntime.IInteractiveWorkflowContext
0x10e86  stloc.0
0x10e87  ldloc.0
0x10e88  callvirt instance class Microsoft.Crm.Workflow.InteractiveWorkflowInputContext Microsoft.Crm.Workflow.SynchronousRuntime.IInteractiveWorkflowContext::get_InteractiveWorkflowInputContext()
0x10e8d  callvirt instance string Microsoft.Crm.Workflow.InteractiveWorkflowContext::get_WorkflowStateXml()
0x10e92  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x10e97  ldstr    aWorkflowstatex_1// "WorkflowStateXml is not expected when s"...
0x10e9c  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::Assert(bool, string)
0x10ea1  ldloc.0
0x10ea2  callvirt instance class Microsoft.Crm.Workflow.InteractiveWorkflowInputContext Microsoft.Crm.Workflow.SynchronousRuntime.IInteractiveWorkflowContext::get_InteractiveWorkflowInputContext()
0x10ea7  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Workflow.SynchronousWorkflowCommonContext::get_OriginatingWorkflowInstanceId()
0x10eac  stloc.1
0x10ead  ldloca.s 1
0x10eaf  ldloc.0
0x10eb0  callvirt instance class Microsoft.Crm.Workflow.InteractiveWorkflowInputContext Microsoft.Crm.Workflow.SynchronousRuntime.IInteractiveWorkflowContext::get_InteractiveWorkflowInputContext()
0x10eb5  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Workflow.SynchronousWorkflowCommonContext::get_WorkflowInstanceId()
0x10eba  call     instance bool [mscorlib]System.Guid::Equals(valuetype [mscorlib]System.Guid)
0x10ebf  brtrue.s loc_10EC3
0x10ec1  ldc.i4.1
0x10ec2  ret
0x10ec3  ldc.i4.0
0x10ec4  ret
```
