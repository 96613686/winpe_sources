# sub_2C3BE69

- ea: `0x2c3be69`
- end: `0x2c3be7b`
- name: `sub_2C3BE69`
- size: `18`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: ``

## pseudocode

```c
char __fastcall sub_2C3BE69(
        __int64 a1,
        __int64 a2,
        _BYTE *a3,
        _BYTE *a4,
        __int64 a5,
        __int64 a6,
        __int64 a7,
        __int64 a8,
        __int64 a9,
        __int64 a10,
        __int64 a11,
        __int64 a12,
        __int64 a13,
        __int64 a14,
        __int64 a15,
        __int64 a16,
        __int64 a17,
        __int64 a18,
        __int64 a19,
        __int64 a20,
        __int64 a21)
{
  _BYTE *v21; // rax
  _BYTE *v22; // rbx

  *a4 += (_BYTE)v21;
  *a3 ^= 0x1Fu;
  __outbyte(1u, (unsigned __int8)v21);
  *v22 += (_BYTE)a3;
  return *v21 | (unsigned __int8)v21;
}

```

## disassembly

```asm
0x2c3be69  enter   78h, 0
0x2c3be6d  add     [rcx], al
0x2c3be6f  xor     byte ptr [rdx], 1Fh
0x2c3be72  out     1, al; DMA controller, 8237A-5.
0x2c3be74  add     [rbx], dl
0x2c3be76  or      al, [rax]
0x2c3be78  retn    78h ; 'x'
```
