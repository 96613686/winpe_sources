# CertPropHandleReaderAction

- ea: `0x18000f230`
- end: `0x18000f238`
- name: `CertPropHandleReaderAction`
- size: `8`
- prototype: `void __fastcall(PTP_CALLBACK_INSTANCE Instance, char *Context, PTP_WAIT Wait, TP_WAIT_RESULT WaitResult)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18000f240`

## pseudocode

```c
void __fastcall CertPropHandleReaderAction(
        PTP_CALLBACK_INSTANCE Instance,
        char *Context,
        PTP_WAIT Wait,
        TP_WAIT_RESULT WaitResult)
{
  CertPropHandleReaderActionInternal(Context);
}

```

## disassembly

```asm
0x18000f230  mov     rcx, rdx; pv
0x18000f233  jmp     CertPropHandleReaderActionInternal
```
