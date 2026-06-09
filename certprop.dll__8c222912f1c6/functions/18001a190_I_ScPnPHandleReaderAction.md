# I_ScPnPHandleReaderAction

- ea: `0x18001a190`
- end: `0x18001a195`
- name: `I_ScPnPHandleReaderAction`
- size: `5`
- prototype: `void __fastcall(PTP_CALLBACK_INSTANCE Instance, PVOID Context, PTP_WAIT Wait, TP_WAIT_RESULT WaitResult)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180006a40`

## pseudocode

```c
// attributes: thunk
void __fastcall I_ScPnPHandleReaderAction(
        PTP_CALLBACK_INSTANCE Instance,
        PVOID Context,
        PTP_WAIT Wait,
        TP_WAIT_RESULT WaitResult)
{
  I_ScPnPHandleReaderActionInternal(Instance, Context, Wait, WaitResult);
}

```

## disassembly

```asm
0x18001a190  jmp     I_ScPnPHandleReaderActionInternal
```
