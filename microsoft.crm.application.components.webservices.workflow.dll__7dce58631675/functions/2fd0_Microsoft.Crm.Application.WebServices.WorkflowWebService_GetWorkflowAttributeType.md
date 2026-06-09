# Microsoft.Crm.Application.WebServices.WorkflowWebService::GetWorkflowAttributeType

- ea: `0x2fd0`
- end: `0x300b`
- name: `Microsoft.Crm.Application.WebServices.WorkflowWebService::GetWorkflowAttributeType`
- size: `59`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x2d30`
- `0x3010`

## callees

- `0x2fd0`

## pseudocode

```c

```

## disassembly

```asm
0x2fd0  ldarg.1
0x2fd1  switch   loc_2FF0, loc_2FF3, loc_2FF5, loc_2FF9, loc_2FF9, loc_2FF7
0x2fee  br.s     loc_2FFB
0x2ff0  ldc.i4.s 0xE
0x2ff2  ret
0x2ff3  ldc.i4.5
0x2ff4  ret
0x2ff5  ldc.i4.4
0x2ff6  ret
0x2ff7  ldc.i4.6
0x2ff8  ret
0x2ff9  ldc.i4.2
0x2ffa  ret
0x2ffb  ldstr    aUnsupportedVar// "Unsupported variable type"
0x3000  ldstr    aType// "type"
0x3005  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmArgumentException::.ctor(string, string)
0x300a  throw
```
