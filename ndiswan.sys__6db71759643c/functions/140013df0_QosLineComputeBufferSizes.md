# QosLineComputeBufferSizes

- ea: `0x140013df0`
- end: `0x140013e97`
- name: `QosLineComputeBufferSizes`
- size: `167`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1400141c0`

## callees

- `0x140013df0`

## pseudocode

```c
__int64 __fastcall QosLineComputeBufferSizes(__int64 a1)
{
  unsigned __int64 v1; // r10
  unsigned __int64 v2; // r8
  unsigned __int64 v4; // r11
  unsigned int v5; // ecx
  unsigned __int64 v6; // rcx
  __int64 result; // rax
  unsigned __int64 v8; // rcx

  v1 = *(_QWORD *)(a1 + 8);
  LODWORD(v2) = 0;
  if ( v1 == -1 )
  {
    LODWORD(v4) = 0;
  }
  else
  {
    v4 = v1 * *(unsigned int *)(a1 + 116) / 0xF4240;
    if ( v1 > 0x8000000 )
    {
      v5 = 23;
      LODWORD(v2) = 12;
    }
    else
    {
      v5 = 50;
    }
    if ( *(_DWORD *)(a1 + 104) > 0xAu )
      v5 += v2;
    v2 = v4 * v5 / 0x64;
  }
  v6 = (unsigned int)v4 * (unsigned __int64)*(unsigned int *)(a1 + 108);
  *(_DWORD *)(a1 + 204) = v4;
  result = 0xFFFFFFFFLL;
  v8 = 2 * v6;
  *(_DWORD *)(a1 + 120) = v2;
  if ( v8 >= 0xFFFFFFFF )
    LODWORD(v8) = -1;
  *(_DWORD *)(a1 + 124) = v8;
  return result;
}

```

## disassembly

```asm
0x140013df0  mov     r10, [rcx+8]
0x140013df4  xor     r8d, r8d
0x140013df7  mov     r9, rcx
0x140013dfa  cmp     r10, 0FFFFFFFFFFFFFFFFh
0x140013dfe  jnz     short loc_140013E05
0x140013e00  mov     r11d, r8d
0x140013e03  jmp     short loc_140013E6D
0x140013e05  mov     ecx, [rcx+74h]
0x140013e08  mov     rax, 431BDE82D7B634DBh
0x140013e12  imul    rcx, r10
0x140013e16  mul     rcx
0x140013e19  mov     r11, rdx
0x140013e1c  shr     r11, 12h
0x140013e20  cmp     r10, 0C80000h
0x140013e27  jbe     short loc_140013E32
0x140013e29  cmp     r10, 8000000h
0x140013e30  ja      short loc_140013E39
0x140013e32  mov     ecx, 32h ; '2'
0x140013e37  jmp     short loc_140013E42
0x140013e39  mov     ecx, 17h
0x140013e3e  lea     r8d, [rcx-0Bh]
0x140013e42  cmp     dword ptr [r9+68h], 0Ah
0x140013e47  jbe     short loc_140013E4C
0x140013e49  add     ecx, r8d
0x140013e4c  mov     r8d, ecx
0x140013e4f  mov     rax, 47AE147AE147AE15h
0x140013e59  imul    r8, r11
0x140013e5d  mul     r8
0x140013e60  sub     r8, rdx
0x140013e63  shr     r8, 1
0x140013e66  add     r8, rdx
0x140013e69  shr     r8, 6
0x140013e6d  mov     ecx, [r9+6Ch]
0x140013e71  mov     eax, r11d
0x140013e74  imul    rcx, rax
0x140013e78  mov     [r9+0CCh], eax
0x140013e7f  mov     eax, 0FFFFFFFFh
0x140013e84  add     rcx, rcx
0x140013e87  mov     [r9+78h], r8d
0x140013e8b  cmp     rcx, rax
0x140013e8e  cmovnb  rcx, rax
0x140013e92  mov     [r9+7Ch], ecx
0x140013e96  retn
```
