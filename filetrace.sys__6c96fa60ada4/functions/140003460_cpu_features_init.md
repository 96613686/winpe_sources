# __cpu_features_init

- ea: `0x140003460`
- end: `0x1400034f9`
- name: `__cpu_features_init`
- size: `153`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x140003ac0`

## callees

- `0x140003460`

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
  WmiRegistrationContext.DeviceQueue.Busy = v11 | 1;
  return 0;
}

```

## disassembly

```asm
0x140003460  push    rbx
0x140003462  sub     rsp, 10h
0x140003466  xor     eax, eax
0x140003468  xor     ecx, ecx
0x14000346a  cpuid
0x14000346c  mov     r9d, eax
0x14000346f  xor     ecx, ecx
0x140003471  mov     eax, 1
0x140003476  cpuid
0x140003478  mov     edx, ecx
0x14000347a  and     edx, 100000h
0x140003480  mov     eax, edx
0x140003482  neg     eax
0x140003484  sbb     r8b, r8b
0x140003487  and     r8b, 8
0x14000348b  test    edx, edx
0x14000348d  jz      short loc_1400034B3
0x14000348f  bt      ecx, 1Bh
0x140003493  jnb     short loc_1400034B3
0x140003495  bt      ecx, 1Ch
0x140003499  jnb     short loc_1400034B3
0x14000349b  xor     ecx, ecx
0x14000349d  xgetbv
0x1400034a0  shl     rdx, 20h
0x1400034a4  or      rdx, rax
0x1400034a7  and     dl, 6
0x1400034aa  cmp     dl, 6
0x1400034ad  jnz     short loc_1400034B3
0x1400034af  or      r8b, 4
0x1400034b3  mov     eax, 7
0x1400034b8  cmp     r9d, eax
0x1400034bb  jl      short loc_1400034E5
0x1400034bd  xor     ecx, ecx
0x1400034bf  cpuid
0x1400034c1  mov     al, r8b
0x1400034c4  or      al, 2
0x1400034c6  movzx   ecx, al
0x1400034c9  bt      ebx, 9
0x1400034cd  movzx   eax, r8b
0x1400034d1  cmovnb  ecx, eax
0x1400034d4  mov     r8b, cl
0x1400034d7  test    bl, 20h
0x1400034da  jz      short loc_1400034E5
0x1400034dc  test    cl, 4
0x1400034df  jz      short loc_1400034E5
0x1400034e1  or      r8b, 10h
0x1400034e5  or      r8b, 1
0x1400034e9  mov     byte ptr cs:WmiRegistrationContext.DeviceQueue.20h, r8b
0x1400034f0  xor     eax, eax
0x1400034f2  add     rsp, 10h
0x1400034f6  pop     rbx
0x1400034f7  retn
```
