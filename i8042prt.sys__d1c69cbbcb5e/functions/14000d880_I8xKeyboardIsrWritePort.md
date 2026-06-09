# I8xKeyboardIsrWritePort

- ea: `0x14000d880`
- end: `0x14000d891`
- name: `I8xKeyboardIsrWritePort`
- size: `17`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x140001130`

## pseudocode

```c
void __fastcall __noreturn I8xKeyboardIsrWritePort(__int64 a1, __int64 a2)
{
  I8xPutByteAsynchronous(0, a2);
}

```

## disassembly

```asm
0x14000d880  sub     rsp, 28h
0x14000d884  xor     ecx, ecx
0x14000d886  call    I8xPutByteAsynchronous
0x14000d88b  add     rsp, 28h
0x14000d88f  retn
```
