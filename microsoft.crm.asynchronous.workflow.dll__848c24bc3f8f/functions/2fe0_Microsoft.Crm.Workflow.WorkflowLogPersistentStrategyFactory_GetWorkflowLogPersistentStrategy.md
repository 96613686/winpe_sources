# Microsoft.Crm.Workflow.WorkflowLogPersistentStrategyFactory::GetWorkflowLogPersistentStrategy

- ea: `0x2fe0`
- end: `0x3010`
- name: `Microsoft.Crm.Workflow.WorkflowLogPersistentStrategyFactory::GetWorkflowLogPersistentStrategy`
- size: `48`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1900`

## callees

- `0x2e90`
- `0x2f70`
- `0x2fe0`

## string_xrefs

- `0x2fe5`: `WorkflowLogCacheStrategy`

## pseudocode

```c

```

## disassembly

```asm
0x2fe0  call     class [Microsoft.Crm.Core]Microsoft.Crm.IDeploymentInfoProvider [Microsoft.Crm.Core]Microsoft.Crm.DeploymentInfoProvider::get_Instance()
0x2fe5  ldstr    aWorkflowlogcac// "WorkflowLogCacheStrategy"
0x2fea  callvirt T0x2B000003
0x2fef  stloc.0
0x2ff0  ldloca.s 0
0x2ff2  call     instance bool valuetype [mscorlib]System.Nullable`1<bool>::get_HasValue()
0x2ff7  brfalse.s loc_3002
0x2ff9  ldloca.s 0
0x2ffb  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<bool>::get_Value()
0x3000  brfalse.s loc_3009
0x3002  ldarg.0
0x3003  newobj   instance void Microsoft.Crm.Workflow.WorkflowLogCachePersistentStrategy::.ctor(class Microsoft.Crm.Workflow.WorkflowContext context)
0x3008  ret
0x3009  ldarg.0
0x300a  newobj   instance void Microsoft.Crm.Workflow.WorkflowLogSdkPersistentStrategy::.ctor(class Microsoft.Crm.Workflow.WorkflowContext context)
0x300f  ret
```
