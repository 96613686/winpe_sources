# Microsoft.Crm.Workflow.AsyncWorkflowInstanceState::.ctor

- ea: `0x2870`
- end: `0x288c`
- name: `Microsoft.Crm.Workflow.AsyncWorkflowInstanceState::.ctor`
- size: `28`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1900`

## callees

- `0x1f0`
- `0x2870`

## string_xrefs

- `0x2877`: `Total Workflow state writes`

## pseudocode

```c

```

## disassembly

```asm
0x2870  ldarg.0
0x2871  call     instance void [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.WorkflowInstanceStateBase::.ctor()
0x2876  ldarg.0
0x2877  ldstr    aTotalWorkflowS// "Total Workflow state writes"
0x287c  call     class [System]System.Diagnostics.PerformanceCounter Microsoft.Crm.Asynchronous.WorkflowPerformanceCounters::GetPerformanceCounter(string performanceCounterName)
0x2881  call     instance void [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.WorkflowInstanceStateBase::set_WorkflowSaveStateCounter(class [System]System.Diagnostics.PerformanceCounter)
0x2886  leave.s  loc_288B
0x2888  pop
0x2889  leave.s  loc_288B
0x288b  ret
```
