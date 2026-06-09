# sub_33DBD4

- ea: `0x33dbd4`
- end: `0x33dbfd`
- name: `sub_33DBD4`
- size: `41`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: ``

## pseudocode

```c
void __fastcall sub_33DBD4(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        char a4,
        __int64 a5,
        __int64 a6,
        __int64 a7,
        __int64 a8,
        __int64 a9,
        __int64 a10,
        __int64 a11)
{
  _BYTE *v11; // rax

  v11[65] += a4;
  *v11 |= (unsigned __int8)v11;
  __asm { retf    21h ; '!' }
}

```

## disassembly

```asm
0x33dbd4  add     [rax+41h], cl
0x33dbd7  push    r10
0x33dbda  push    rdx
0x33dbdb  push    r11
0x33dbdd  push    r13
0x33dbdf  push    rdx
0x33dbe0  push    r11
0x33dbe3  pop     rdi
0x33dbe4  push    rbp
0x33dbe5  push    r12
0x33dbef  push    r12
0x33dbf8  or      [rax], al
0x33dbfa  retf    21h ; '!'
```
