# Microsoft.Crm.Asynchronous.BulkDeleteOperation::HasJobBeenAbortedOrPaused

- ea: `0x2a70`
- end: `0x2a8d`
- name: `Microsoft.Crm.Asynchronous.BulkDeleteOperation::HasJobBeenAbortedOrPaused`
- size: `29`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x2660`

## callees

- `0x2a70`

## pseudocode

```c

```

## disassembly

```asm
0x2a70  ldarg.1
0x2a71  callvirt instance valuetype [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncHandlerEarlyExitRequest [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEventBase::QueryForEarlyExitRequest()
0x2a76  stloc.0
0x2a77  ldloc.0
0x2a78  ldc.i4.2
0x2a79  bne.un.s loc_2A81
0x2a7b  newobj   instance void [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncCanceledResult::.ctor()
0x2a80  ret
0x2a81  ldloc.0
0x2a82  ldc.i4.1
0x2a83  bne.un.s loc_2A8B
0x2a85  newobj   instance void [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncPausedResult::.ctor()
0x2a8a  ret
0x2a8b  ldnull
0x2a8c  ret
```
