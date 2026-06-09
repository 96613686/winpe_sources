# I8xKeyboardSynchReadPort

- ea: `0x14000d8a0`
- end: `0x14000d8b1`
- name: `I8xKeyboardSynchReadPort`
- size: `17`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x1400066d0`

## pseudocode

```c
__int64 __fastcall I8xKeyboardSynchReadPort(__int64 a1, __int64 a2)
{
  LOBYTE(a1) = 1;
  return I8xGetBytePolled(a1, a2);
}

```

## disassembly

```asm
0x14000d8a0  sub     rsp, 28h
0x14000d8a4  mov     cl, 1
0x14000d8a6  call    I8xGetBytePolled
0x14000d8ab  add     rsp, 28h
0x14000d8af  retn
```
