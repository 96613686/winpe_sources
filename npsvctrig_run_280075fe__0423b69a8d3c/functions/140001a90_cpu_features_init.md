# __cpu_features_init

- ea: `0x140001a90`
- end: `0x140001b29`
- name: `__cpu_features_init`
- size: `153`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x140002100`

## callees

- `0x140001a90`

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
0x140001a90  push    rbx
0x140001a92  sub     rsp, 10h
0x140001a96  xor     eax, eax
0x140001a98  xor     ecx, ecx
0x140001a9a  cpuid
0x140001a9c  mov     r9d, eax
0x140001a9f  xor     ecx, ecx
0x140001aa1  mov     eax, 1
0x140001aa6  cpuid
0x140001aa8  mov     edx, ecx
0x140001aaa  and     edx, 100000h
0x140001ab0  mov     eax, edx
0x140001ab2  neg     eax
0x140001ab4  sbb     r8b, r8b
0x140001ab7  and     r8b, 8
0x140001abb  test    edx, edx
0x140001abd  jz      short loc_140001AE3
0x140001abf  bt      ecx, 1Bh
0x140001ac3  jnb     short loc_140001AE3
0x140001ac5  bt      ecx, 1Ch
0x140001ac9  jnb     short loc_140001AE3
0x140001acb  xor     ecx, ecx
0x140001acd  xgetbv
0x140001ad0  shl     rdx, 20h
0x140001ad4  or      rdx, rax
0x140001ad7  and     dl, 6
0x140001ada  cmp     dl, 6
0x140001add  jnz     short loc_140001AE3
0x140001adf  or      r8b, 4
0x140001ae3  mov     eax, 7
0x140001ae8  cmp     r9d, eax
0x140001aeb  jl      short loc_140001B15
0x140001aed  xor     ecx, ecx
0x140001aef  cpuid
0x140001af1  mov     al, r8b
0x140001af4  or      al, 2
0x140001af6  movzx   ecx, al
0x140001af9  bt      ebx, 9
0x140001afd  movzx   eax, r8b
0x140001b01  cmovnb  ecx, eax
0x140001b04  mov     r8b, cl
0x140001b07  test    bl, 20h
0x140001b0a  jz      short loc_140001B15
0x140001b0c  test    cl, 4
0x140001b0f  jz      short loc_140001B15
0x140001b11  or      r8b, 10h
0x140001b15  or      r8b, 1
0x140001b19  mov     cs:__isa_info, r8b
0x140001b20  xor     eax, eax
0x140001b22  add     rsp, 10h
0x140001b26  pop     rbx
0x140001b27  retn
```
