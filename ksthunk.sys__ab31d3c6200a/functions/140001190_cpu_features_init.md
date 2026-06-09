# __cpu_features_init

- ea: `0x140001190`
- end: `0x140001229`
- name: `__cpu_features_init`
- size: `153`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x140004700`

## callees

- `0x140001190`

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
0x140001190  push    rbx
0x140001192  sub     rsp, 10h
0x140001196  xor     eax, eax
0x140001198  xor     ecx, ecx
0x14000119a  cpuid
0x14000119c  mov     r9d, eax
0x14000119f  xor     ecx, ecx
0x1400011a1  mov     eax, 1
0x1400011a6  cpuid
0x1400011a8  mov     edx, ecx
0x1400011aa  and     edx, 100000h
0x1400011b0  mov     eax, edx
0x1400011b2  neg     eax
0x1400011b4  sbb     r8b, r8b
0x1400011b7  and     r8b, 8
0x1400011bb  test    edx, edx
0x1400011bd  jz      short loc_1400011E3
0x1400011bf  bt      ecx, 1Bh
0x1400011c3  jnb     short loc_1400011E3
0x1400011c5  bt      ecx, 1Ch
0x1400011c9  jnb     short loc_1400011E3
0x1400011cb  xor     ecx, ecx
0x1400011cd  xgetbv
0x1400011d0  shl     rdx, 20h
0x1400011d4  or      rdx, rax
0x1400011d7  and     dl, 6
0x1400011da  cmp     dl, 6
0x1400011dd  jnz     short loc_1400011E3
0x1400011df  or      r8b, 4
0x1400011e3  mov     eax, 7
0x1400011e8  cmp     r9d, eax
0x1400011eb  jl      short loc_140001215
0x1400011ed  xor     ecx, ecx
0x1400011ef  cpuid
0x1400011f1  mov     al, r8b
0x1400011f4  or      al, 2
0x1400011f6  movzx   ecx, al
0x1400011f9  bt      ebx, 9
0x1400011fd  movzx   eax, r8b
0x140001201  cmovnb  ecx, eax
0x140001204  mov     r8b, cl
0x140001207  test    bl, 20h
0x14000120a  jz      short loc_140001215
0x14000120c  test    cl, 4
0x14000120f  jz      short loc_140001215
0x140001211  or      r8b, 10h
0x140001215  or      r8b, 1
0x140001219  mov     cs:__isa_info, r8b
0x140001220  xor     eax, eax
0x140001222  add     rsp, 10h
0x140001226  pop     rbx
0x140001227  retn
```
