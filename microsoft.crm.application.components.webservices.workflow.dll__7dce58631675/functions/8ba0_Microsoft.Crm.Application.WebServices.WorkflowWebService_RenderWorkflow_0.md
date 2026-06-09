# Microsoft.Crm.Application.WebServices.WorkflowWebService::RenderWorkflow_0

- ea: `0x8ba0`
- end: `0x8bbd`
- name: `Microsoft.Crm.Application.WebServices.WorkflowWebService::RenderWorkflow_0`
- size: `29`
- prototype: ``
- caller_count: `22`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x2030`
- `0x2250`
- `0x4a50`
- `0x4ab0`
- `0x4b20`
- `0x4cf0`
- `0x4d60`
- `0x4dd0`
- `0x4fd0`
- `0x5040`
- `0x50b0`
- `0x5290`
- `0x5300`
- `0x5370`
- `0x5690`
- `0x5700`
- `0x5770`
- `0x5a50`
- `0x5ac0`
- `0x5b30`
- `0x71b0`
- `0x8b90`

## callees

- `0x8ba0`
- `0x8bd0`

## pseudocode

```c

```

## disassembly

```asm
0x8ba0  ldarg.0
0x8ba1  ldarg.1
0x8ba2  ldc.i4.1
0x8ba3  ldarg.2
0x8ba4  dup
0x8ba5  brtrue.s loc_8BAD
0x8ba7  pop
0x8ba8  ldstr    asc_A26A// ""
0x8bad  ldarg.3
0x8bae  dup
0x8baf  brtrue.s loc_8BB7
0x8bb1  pop
0x8bb2  ldstr    asc_A26A// ""
0x8bb7  call     instance string Microsoft.Crm.Application.WebServices.WorkflowWebService::RenderWorkflow(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep workflowStep, bool bSave, string parentStepId, string rendererTypeCode)
0x8bbc  ret
```
