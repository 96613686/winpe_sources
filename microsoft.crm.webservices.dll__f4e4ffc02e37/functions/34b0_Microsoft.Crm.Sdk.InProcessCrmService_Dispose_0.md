# Microsoft.Crm.Sdk.InProcessCrmService::Dispose_0

- ea: `0x34b0`
- end: `0x34c3`
- name: `Microsoft.Crm.Sdk.InProcessCrmService::Dispose_0`
- size: `19`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x34a0`

## callees

- `0x34b0`

## pseudocode

```c

```

## disassembly

```asm
0x34b0  ldarg.0
0x34b1  ldfld    bool Microsoft.Crm.Sdk.InProcessCrmService::disposed
0x34b6  brfalse.s loc_34B9
0x34b8  ret
0x34b9  ldarg.1
0x34ba  pop
0x34bb  ldarg.0
0x34bc  ldc.i4.1
0x34bd  stfld    bool Microsoft.Crm.Sdk.InProcessCrmService::disposed
0x34c2  ret
```
