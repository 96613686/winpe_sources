# Microsoft.Crm.Asynchronous.AsyncService::CreateEventLog

- ea: `0x1860`
- end: `0x1872`
- name: `Microsoft.Crm.Asynchronous.AsyncService::CreateEventLog`
- size: `18`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## callers

- `0xe20`

## pseudocode

```c

```

## disassembly

```asm
0x1860  newobj   instance void [System]System.Diagnostics.EventLog::.ctor()
0x1865  dup
0x1866  ldarg.0
0x1867  callvirt instance void [System]System.Diagnostics.EventLog::set_Source(string)
0x186c  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmEventLog::.ctor(class [System]System.Diagnostics.EventLog)
0x1871  ret
```
