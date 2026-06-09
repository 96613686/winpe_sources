# __cpu_features_init

- ea: `0x140003d10`
- end: `0x140003da9`
- name: `__cpu_features_init`
- size: `153`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x140004380`

## callees

- `0x140003d10`

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
0x140003d10  push    rbx
0x140003d12  sub     rsp, 10h
0x140003d16  xor     eax, eax
0x140003d18  xor     ecx, ecx
0x140003d1a  cpuid
0x140003d1c  mov     r9d, eax
0x140003d1f  xor     ecx, ecx
0x140003d21  mov     eax, 1
0x140003d26  cpuid
0x140003d28  mov     edx, ecx
0x140003d2a  and     edx, 100000h
0x140003d30  mov     eax, edx
0x140003d32  neg     eax
0x140003d34  sbb     r8b, r8b
0x140003d37  and     r8b, 8
0x140003d3b  test    edx, edx
0x140003d3d  jz      short loc_140003D63
0x140003d3f  bt      ecx, 1Bh
0x140003d43  jnb     short loc_140003D63
0x140003d45  bt      ecx, 1Ch
0x140003d49  jnb     short loc_140003D63
0x140003d4b  xor     ecx, ecx
0x140003d4d  xgetbv
0x140003d50  shl     rdx, 20h
0x140003d54  or      rdx, rax
0x140003d57  and     dl, 6
0x140003d5a  cmp     dl, 6
0x140003d5d  jnz     short loc_140003D63
0x140003d5f  or      r8b, 4
0x140003d63  mov     eax, 7
0x140003d68  cmp     r9d, eax
0x140003d6b  jl      short loc_140003D95
0x140003d6d  xor     ecx, ecx
0x140003d6f  cpuid
0x140003d71  mov     al, r8b
0x140003d74  or      al, 2
0x140003d76  movzx   ecx, al
0x140003d79  bt      ebx, 9
0x140003d7d  movzx   eax, r8b
0x140003d81  cmovnb  ecx, eax
0x140003d84  mov     r8b, cl
0x140003d87  test    bl, 20h
0x140003d8a  jz      short loc_140003D95
0x140003d8c  test    cl, 4
0x140003d8f  jz      short loc_140003D95
0x140003d91  or      r8b, 10h
0x140003d95  or      r8b, 1
0x140003d99  mov     cs:__isa_info, r8b
0x140003da0  xor     eax, eax
0x140003da2  add     rsp, 10h
0x140003da6  pop     rbx
0x140003da7  retn
```
