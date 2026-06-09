# Microsoft.Crm.Asynchronous.ParallelTasksExecutionEngine::StopOperation

- ea: `0xd310`
- end: `0xd31b`
- name: `Microsoft.Crm.Asynchronous.ParallelTasksExecutionEngine::StopOperation`
- size: `11`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## string_xrefs

- `0xd310`: `Parallel tasks cannot be stopped, only cancelled.`

## pseudocode

```c

```

## disassembly

```asm
0xd310  ldstr    aParallelTasksC// "Parallel tasks cannot be stopped, only "...
0xd315  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0xd31a  throw
```
