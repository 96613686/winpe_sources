# match_est

- ea: `0x180005df0`
- end: `0x180005e51`
- name: `match_est`
- size: `97`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180002da0`

## callees

- `0x180005df0`

## pseudocode

```c
__int64 __fastcall match_est(__int64 a1, int a2, unsigned int a3)
{
  unsigned int v3; // r9d

  v3 = a3;
  if ( a3 >= 0x100 )
    v3 = (a3 >> 7) + 256;
  return *(unsigned __int8 *)(*((unsigned __int8 *)&qword_18000AC20[31] + a2 + 5) + a1 + 555397)
       + *(unsigned __int8 *)(*((unsigned __int8 *)g_DistLookup + v3) + a1 + 555620)
       + *((unsigned __int8 *)&g_ExtraLengthBits + *((unsigned __int8 *)&qword_18000AC20[31] + a2 + 5))
       + (unsigned int)(unsigned __int8)g_ExtraDistanceBits[*((unsigned __int8 *)g_DistLookup + v3)];
}

```

## disassembly

```asm
0x180005df0  mov     r10, rcx
0x180005df3  movsxd  rax, edx
0x180005df6  mov     ecx, 100h
0x180005dfb  lea     r11, cs:180000000h
0x180005e02  mov     r9d, r8d
0x180005e05  cmp     r8d, ecx
0x180005e08  jb      short loc_180005E11
0x180005e0a  shr     r9d, 7
0x180005e0e  add     r9d, ecx
0x180005e11  movzx   r8d, byte ptr [rax+r11+0AD1Dh]
0x180005e1a  mov     eax, r9d
0x180005e1d  movzx   ecx, byte ptr [r8+r11+7940h]
0x180005e26  movzx   edx, byte ptr [rax+r11+0AB20h]
0x180005e2f  movzx   eax, byte ptr [rdx+r11+7920h]
0x180005e38  add     eax, ecx
0x180005e3a  movzx   ecx, byte ptr [rdx+r10+87A64h]
0x180005e43  add     eax, ecx
0x180005e45  movzx   ecx, byte ptr [r8+r10+87985h]
0x180005e4e  add     eax, ecx
0x180005e50  retn
```
