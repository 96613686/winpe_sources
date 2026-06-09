# Microsoft.Crm.Asynchronous.ServiceOperationExecutionEngine::ExecuteOperation

- ea: `0xe5d0`
- end: `0xe5d7`
- name: `Microsoft.Crm.Asynchronous.ServiceOperationExecutionEngine::ExecuteOperation`
- size: `7`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x6ee0`
- `0xd2e0`
- `0xe500`

## callees

- `0x15810`

## pseudocode

```c

```

## disassembly

```asm
0xe5d0  ldarg.1
0xe5d1  callvirt instance void Microsoft.Crm.Asynchronous.Operations.IServiceOperation::Execute()
0xe5d6  ret
```
