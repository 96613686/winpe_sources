# __cpu_features_init

- ea: `0x140004d20`
- end: `0x140004db9`
- name: `__cpu_features_init`
- size: `153`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x140005380`

## callees

- `0x140004d20`

## pseudocode

```c
__int64 _cpu_features_init()
{
  int v5; // r9d
  char v11; // r8
  char v17; // cl

  _RAX = 0;
  __asm { cpuid }
  v5 = _RAX;
  _RAX = 1;
  __asm { cpuid }
  v11 = (_RCX & 0x100000) != 0 ? 8 : 0;
  if ( (_RCX & 0x100000) != 0 && (_RCX & 0x8000000) != 0 && (_RCX & 0x10000000) != 0 )
    __asm { xgetbv }
  _RAX = 7;
  if ( v5 >= 7 )
  {
    __asm { cpuid }
    v17 = v11 | 2;
    if ( (_RBX & 0x200) == 0 )
      v17 = v11;
    v11 = v17;
    if ( (_RBX & 0x20) != 0 && (v17 & 4) != 0 )
      v11 = v17 | 0x10;
  }
  _isa_info = v11 | 1;
  return 0;
}

```

## disassembly

```asm
0x140004d20  push    rbx
0x140004d22  sub     rsp, 10h
0x140004d26  xor     eax, eax
0x140004d28  xor     ecx, ecx
0x140004d2a  cpuid
0x140004d2c  mov     r9d, eax
0x140004d2f  xor     ecx, ecx
0x140004d31  mov     eax, 1
0x140004d36  cpuid
0x140004d38  mov     edx, ecx
0x140004d3a  and     edx, 100000h
0x140004d40  mov     eax, edx
0x140004d42  neg     eax
0x140004d44  sbb     r8b, r8b
0x140004d47  and     r8b, 8
0x140004d4b  test    edx, edx
0x140004d4d  jz      short loc_140004D73
0x140004d4f  bt      ecx, 1Bh
0x140004d53  jnb     short loc_140004D73
0x140004d55  bt      ecx, 1Ch
0x140004d59  jnb     short loc_140004D73
0x140004d5b  xor     ecx, ecx
0x140004d5d  xgetbv
0x140004d60  shl     rdx, 20h
0x140004d64  or      rdx, rax
0x140004d67  and     dl, 6
0x140004d6a  cmp     dl, 6
0x140004d6d  jnz     short loc_140004D73
0x140004d6f  or      r8b, 4
0x140004d73  mov     eax, 7
0x140004d78  cmp     r9d, eax
0x140004d7b  jl      short loc_140004DA5
0x140004d7d  xor     ecx, ecx
0x140004d7f  cpuid
0x140004d81  mov     al, r8b
0x140004d84  or      al, 2
0x140004d86  movzx   ecx, al
0x140004d89  bt      ebx, 9
0x140004d8d  movzx   eax, r8b
0x140004d91  cmovnb  ecx, eax
0x140004d94  mov     r8b, cl
0x140004d97  test    bl, 20h
0x140004d9a  jz      short loc_140004DA5
0x140004d9c  test    cl, 4
0x140004d9f  jz      short loc_140004DA5
0x140004da1  or      r8b, 10h
0x140004da5  or      r8b, 1
0x140004da9  mov     cs:__isa_info, r8b
0x140004db0  xor     eax, eax
0x140004db2  add     rsp, 10h
0x140004db6  pop     rbx
0x140004db7  retn
```
