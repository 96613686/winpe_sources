# Microsoft.Crm.Asynchronous.ImportOperation::HasJobBeenAbortedOrPaused

- ea: `0xbcb0`
- end: `0xbcd2`
- name: `Microsoft.Crm.Asynchronous.ImportOperation::HasJobBeenAbortedOrPaused`
- size: `34`
- prototype: ``
- caller_count: `13`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0xd7f0`
- `0xe550`
- `0x10b00`
- `0x14cb0`
- `0x156f0`
- `0x16f30`
- `0x17420`
- `0x17750`
- `0x19b90`
- `0x1b1e0`
- `0x1c080`
- `0x1c180`
- `0x1c630`

## callees

- `0xbcb0`

## pseudocode

```c

```

## disassembly

```asm
0xbcb0  ldarg.0
0xbcb1  ldfld    class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEvent Microsoft.Crm.Asynchronous.ImportOperation::_asyncEvent
0xbcb6  callvirt instance valuetype [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncHandlerEarlyExitRequest [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEventBase::QueryForEarlyExitRequest()
0xbcbb  stloc.0
0xbcbc  ldloc.0
0xbcbd  ldc.i4.2
0xbcbe  bne.un.s loc_BCC6
0xbcc0  newobj   instance void [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncCanceledResult::.ctor()
0xbcc5  ret
0xbcc6  ldloc.0
0xbcc7  ldc.i4.1
0xbcc8  bne.un.s loc_BCD0
0xbcca  newobj   instance void [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncPausedResult::.ctor()
0xbccf  ret
0xbcd0  ldnull
0xbcd1  ret
```
