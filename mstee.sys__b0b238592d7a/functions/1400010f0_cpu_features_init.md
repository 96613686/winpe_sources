# __cpu_features_init

- ea: `0x1400010f0`
- end: `0x140001189`
- name: `__cpu_features_init`
- size: `153`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x140001780`

## callees

- `0x1400010f0`

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
0x1400010f0  push    rbx
0x1400010f2  sub     rsp, 10h
0x1400010f6  xor     eax, eax
0x1400010f8  xor     ecx, ecx
0x1400010fa  cpuid
0x1400010fc  mov     r9d, eax
0x1400010ff  xor     ecx, ecx
0x140001101  mov     eax, 1
0x140001106  cpuid
0x140001108  mov     edx, ecx
0x14000110a  and     edx, 100000h
0x140001110  mov     eax, edx
0x140001112  neg     eax
0x140001114  sbb     r8b, r8b
0x140001117  and     r8b, 8
0x14000111b  test    edx, edx
0x14000111d  jz      short loc_140001143
0x14000111f  bt      ecx, 1Bh
0x140001123  jnb     short loc_140001143
0x140001125  bt      ecx, 1Ch
0x140001129  jnb     short loc_140001143
0x14000112b  xor     ecx, ecx
0x14000112d  xgetbv
0x140001130  shl     rdx, 20h
0x140001134  or      rdx, rax
0x140001137  and     dl, 6
0x14000113a  cmp     dl, 6
0x14000113d  jnz     short loc_140001143
0x14000113f  or      r8b, 4
0x140001143  mov     eax, 7
0x140001148  cmp     r9d, eax
0x14000114b  jl      short loc_140001175
0x14000114d  xor     ecx, ecx
0x14000114f  cpuid
0x140001151  mov     al, r8b
0x140001154  or      al, 2
0x140001156  movzx   ecx, al
0x140001159  bt      ebx, 9
0x14000115d  movzx   eax, r8b
0x140001161  cmovnb  ecx, eax
0x140001164  mov     r8b, cl
0x140001167  test    bl, 20h
0x14000116a  jz      short loc_140001175
0x14000116c  test    cl, 4
0x14000116f  jz      short loc_140001175
0x140001171  or      r8b, 10h
0x140001175  or      r8b, 1
0x140001179  mov     cs:__isa_info, r8b
0x140001180  xor     eax, eax
0x140001182  add     rsp, 10h
0x140001186  pop     rbx
0x140001187  retn
```
