# __cpu_features_init

- ea: `0x180001ec0`
- end: `0x180001f59`
- name: `__cpu_features_init`
- size: `153`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180002640`

## callees

- `0x180001ec0`

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
0x180001ec0  push    rbx
0x180001ec2  sub     rsp, 10h
0x180001ec6  xor     eax, eax
0x180001ec8  xor     ecx, ecx
0x180001eca  cpuid
0x180001ecc  mov     r9d, eax
0x180001ecf  xor     ecx, ecx
0x180001ed1  mov     eax, 1
0x180001ed6  cpuid
0x180001ed8  mov     edx, ecx
0x180001eda  and     edx, 100000h
0x180001ee0  mov     eax, edx
0x180001ee2  neg     eax
0x180001ee4  sbb     r8b, r8b
0x180001ee7  and     r8b, 8
0x180001eeb  test    edx, edx
0x180001eed  jz      short loc_180001F13
0x180001eef  bt      ecx, 1Bh
0x180001ef3  jnb     short loc_180001F13
0x180001ef5  bt      ecx, 1Ch
0x180001ef9  jnb     short loc_180001F13
0x180001efb  xor     ecx, ecx
0x180001efd  xgetbv
0x180001f00  shl     rdx, 20h
0x180001f04  or      rdx, rax
0x180001f07  and     dl, 6
0x180001f0a  cmp     dl, 6
0x180001f0d  jnz     short loc_180001F13
0x180001f0f  or      r8b, 4
0x180001f13  mov     eax, 7
0x180001f18  cmp     r9d, eax
0x180001f1b  jl      short loc_180001F45
0x180001f1d  xor     ecx, ecx
0x180001f1f  cpuid
0x180001f21  mov     al, r8b
0x180001f24  or      al, 2
0x180001f26  movzx   ecx, al
0x180001f29  bt      ebx, 9
0x180001f2d  movzx   eax, r8b
0x180001f31  cmovnb  ecx, eax
0x180001f34  mov     r8b, cl
0x180001f37  test    bl, 20h
0x180001f3a  jz      short loc_180001F45
0x180001f3c  test    cl, 4
0x180001f3f  jz      short loc_180001F45
0x180001f41  or      r8b, 10h
0x180001f45  or      r8b, 1
0x180001f49  mov     cs:__isa_info, r8b
0x180001f50  xor     eax, eax
0x180001f52  add     rsp, 10h
0x180001f56  pop     rbx
0x180001f57  retn
```
