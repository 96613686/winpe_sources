# I8xKeyboardSynchWritePort

- ea: `0x14000d8c0`
- end: `0x14000d8dc`
- name: `I8xKeyboardSynchWritePort`
- size: `28`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x1400059c0`

## pseudocode

```c
__int64 __fastcall I8xKeyboardSynchWritePort(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  LOBYTE(a4) = a2;
  LOBYTE(a2) = a3;
  LOBYTE(a3) = 1;
  return I8xPutBytePolled(0, a2, a3, a4);
}

```

## disassembly

```asm
0x14000d8c0  sub     rsp, 28h
0x14000d8c4  mov     al, r8b
0x14000d8c7  mov     r9b, dl
0x14000d8ca  mov     dl, al
0x14000d8cc  mov     r8b, 1
0x14000d8cf  xor     ecx, ecx
0x14000d8d1  call    I8xPutBytePolled
0x14000d8d6  add     rsp, 28h
0x14000d8da  retn
```
