# sub_2F2FA91

- ea: `0x2f2fa91`
- end: `0x2f2faa3`
- name: `sub_2F2FA91`
- size: `18`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: ``

## pseudocode

```c
char __fastcall sub_2F2FA91(
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

  *a4 += (_BYTE)v21;
  __outdword(1u, (unsigned int)v21);
  *v22 += a3;
  return *v21 | (unsigned __int8)v21;
}

```

## disassembly

```asm
0x2f2fa91  enter   78h, 0
0x2f2fa95  add     [rcx], al
0x2f2fa97  cmp     byte ptr [rcx], 7
0x2f2fa9a  out     1, eax; DMA controller, 8237A-5.
0x2f2fa9c  add     [rbx], dl
0x2f2fa9e  or      al, [rax]
0x2f2faa0  retn    78h ; 'x'
```
