# sub_24EFB79

- ea: `0x24efb79`
- end: `0x24efb91`
- name: `sub_24EFB79`
- size: `24`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: ``

## pseudocode

```c
char __fastcall sub_24EFB79(
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
  *v22 &= 0x52u;
  __outbyte(1u, (unsigned __int8)v21);
  *v22 += a3;
  LOBYTE(v21) = *v21 | (unsigned __int8)v21;
  return (char)v21;
}

```

## disassembly

```asm
0x24efb79  or      al, [rcx]
0x24efb7b  add     [rcx], cl
0x24efb7d  or      al, [rax]
0x24efb7f  enter   78h, 0
0x24efb83  add     [rcx], al
0x24efb85  and     byte ptr [rbx], 52h
0x24efb88  out     1, al; DMA controller, 8237A-5.
0x24efb8a  add     [rbx], dl
0x24efb8c  or      al, [rax]
0x24efb8e  retn    78h ; 'x'
```
