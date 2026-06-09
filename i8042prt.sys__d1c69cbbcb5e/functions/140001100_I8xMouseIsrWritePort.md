# I8xMouseIsrWritePort

- ea: `0x140001100`
- end: `0x140001123`
- name: `I8xMouseIsrWritePort`
- size: `35`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x140001130`

## pseudocode

```c
__int64 __fastcall I8xMouseIsrWritePort(__int64 a1, __int64 a2)
{
  unsigned __int8 v2; // bl

  v2 = a2;
  LOBYTE(a1) = 1;
  LOBYTE(a2) = -44;
  I8xPutByteAsynchronous(a1, a2);
  return I8xPutByteAsynchronous(0, v2);
}

```

## disassembly

```asm
0x140001100  push    rbx
0x140001102  sub     rsp, 20h
0x140001106  movzx   ebx, dl
0x140001109  mov     cl, 1
0x14000110b  mov     dl, 0D4h
0x14000110d  call    I8xPutByteAsynchronous
0x140001112  movzx   edx, bl
0x140001115  xor     ecx, ecx
0x140001117  call    I8xPutByteAsynchronous
0x14000111c  add     rsp, 20h
0x140001120  pop     rbx
0x140001121  retn
```
