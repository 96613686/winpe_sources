# Microsoft.Crm.Workflow.Services.ActivityServiceBase::CreateLog_0

- ea: `0x14970`
- end: `0x149ba`
- name: `Microsoft.Crm.Workflow.Services.ActivityServiceBase::CreateLog_0`
- size: `74`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x14930`

## callees

- `0x6960`
- `0x6a60`
- `0x14770`
- `0x14970`

## string_xrefs

- `0x1499f`: `StepService: Created workflow log {0}.`

## pseudocode

```c

```

## disassembly

```asm
0x14970  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x14975  stloc.0
0x14976  ldarg.0
0x14977  call     instance class Microsoft.Crm.Workflow.ICommonWorkflowContext Microsoft.Crm.Workflow.Services.ActivityServiceBase::get_WorkflowContext()
0x1497c  callvirt instance bool Microsoft.Crm.Workflow.ICommonWorkflowContext::get_IsLoggingEnabled()
0x14981  brfalse.s loc_149B8
0x14983  ldarg.0
0x14984  call     instance class Microsoft.Crm.Workflow.ICommonWorkflowContext Microsoft.Crm.Workflow.Services.ActivityServiceBase::get_WorkflowContext()
0x14989  ldarg.1
0x1498a  ldarg.2
0x1498b  ldarg.3
0x1498c  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Workflow.ICommonWorkflowContext::CreateWorkflowLog(string activityName, string stepName, string description)
0x14991  stloc.0
0x14992  ldarg.0
0x14993  call     instance class Microsoft.Crm.Workflow.ICommonWorkflowContext Microsoft.Crm.Workflow.Services.ActivityServiceBase::get_WorkflowContext()
0x14998  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext::get_OrganizationId()
0x1499d  ldc.i4.s 0x1E
0x1499f  ldstr    aStepserviceCre// "StepService: Created workflow log {0}."
0x149a4  ldc.i4.1
0x149a5  newarr   [mscorlib]System.Object
0x149aa  dup
0x149ab  ldc.i4.0
0x149ac  ldloc.0
0x149ad  box      [mscorlib]System.Guid
0x149b2  stelem.ref
0x149b3  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x149b8  ldloc.0
0x149b9  ret
```
