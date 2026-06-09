# __cpu_features_init

- ea: `0x140002470`
- end: `0x140002509`
- name: `__cpu_features_init`
- size: `153`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x140002b00`

## callees

- `0x140002470`

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
0x140002470  push    rbx
0x140002472  sub     rsp, 10h
0x140002476  xor     eax, eax
0x140002478  xor     ecx, ecx
0x14000247a  cpuid
0x14000247c  mov     r9d, eax
0x14000247f  xor     ecx, ecx
0x140002481  mov     eax, 1
0x140002486  cpuid
0x140002488  mov     edx, ecx
0x14000248a  and     edx, 100000h
0x140002490  mov     eax, edx
0x140002492  neg     eax
0x140002494  sbb     r8b, r8b
0x140002497  and     r8b, 8
0x14000249b  test    edx, edx
0x14000249d  jz      short loc_1400024C3
0x14000249f  bt      ecx, 1Bh
0x1400024a3  jnb     short loc_1400024C3
0x1400024a5  bt      ecx, 1Ch
0x1400024a9  jnb     short loc_1400024C3
0x1400024ab  xor     ecx, ecx
0x1400024ad  xgetbv
0x1400024b0  shl     rdx, 20h
0x1400024b4  or      rdx, rax
0x1400024b7  and     dl, 6
0x1400024ba  cmp     dl, 6
0x1400024bd  jnz     short loc_1400024C3
0x1400024bf  or      r8b, 4
0x1400024c3  mov     eax, 7
0x1400024c8  cmp     r9d, eax
0x1400024cb  jl      short loc_1400024F5
0x1400024cd  xor     ecx, ecx
0x1400024cf  cpuid
0x1400024d1  mov     al, r8b
0x1400024d4  or      al, 2
0x1400024d6  movzx   ecx, al
0x1400024d9  bt      ebx, 9
0x1400024dd  movzx   eax, r8b
0x1400024e1  cmovnb  ecx, eax
0x1400024e4  mov     r8b, cl
0x1400024e7  test    bl, 20h
0x1400024ea  jz      short loc_1400024F5
0x1400024ec  test    cl, 4
0x1400024ef  jz      short loc_1400024F5
0x1400024f1  or      r8b, 10h
0x1400024f5  or      r8b, 1
0x1400024f9  mov     cs:__isa_info, r8b
0x140002500  xor     eax, eax
0x140002502  add     rsp, 10h
0x140002506  pop     rbx
0x140002507  retn
```
