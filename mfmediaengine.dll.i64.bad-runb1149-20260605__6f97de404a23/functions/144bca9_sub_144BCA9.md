# sub_144BCA9

- ea: `0x144bca9`
- end: `0x144bcbd`
- name: `sub_144BCA9`
- size: `20`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: ``

## pseudocode

```c
char __fastcall sub_144BCA9(
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

  LOBYTE(v21) = *v21 | (unsigned __int8)v21;
  *a4 += (_BYTE)v21;
  *a3 += 44;
  __outbyte(1u, (unsigned __int8)v21);
  *v22 += (_BYTE)a3;
  LOBYTE(v21) = *v21 | (unsigned __int8)v21;
  return (char)v21;
}

```

## disassembly

```asm
0x144bca9  or      al, [rax]
0x144bcab  enter   78h, 0
0x144bcaf  add     [rcx], al
0x144bcb1  add     byte ptr [rdx], 2Ch ; ','
0x144bcb4  out     1, al; DMA controller, 8237A-5.
0x144bcb6  add     [rbx], dl
0x144bcb8  or      al, [rax]
0x144bcba  retn    78h ; 'x'
```
