# sub_2BC5E6E

- ea: `0x2bc5e6e`
- end: `0x2bc5e86`
- name: `sub_2BC5E6E`
- size: `24`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: ``

## pseudocode

```c
char __fastcall sub_2BC5E6E(
        __int64 a1,
        __int64 a2,
        char a3,
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

  LOBYTE(v21) = *a4 | (unsigned __int8)v21;
  *a4 += (_BYTE)a4;
  LOBYTE(v21) = *v21 | (unsigned __int8)v21;
  *a4 += (_BYTE)v21;
  *a4 ^= 0x10u;
  __outbyte(1u, (unsigned __int8)v21);
  *v22 += a3;
  LOBYTE(v21) = *v21 | (unsigned __int8)v21;
  return (char)v21;
}

```

## disassembly

```asm
0x2bc5e6e  or      al, [rcx]
0x2bc5e70  add     [rcx], cl
0x2bc5e72  or      al, [rax]
0x2bc5e74  enter   78h, 0
0x2bc5e78  add     [rcx], al
0x2bc5e7a  xor     byte ptr [rcx], 10h
0x2bc5e7d  out     1, al; DMA controller, 8237A-5.
0x2bc5e7f  add     [rbx], dl
0x2bc5e81  or      al, [rax]
0x2bc5e83  retn    78h ; 'x'
```
