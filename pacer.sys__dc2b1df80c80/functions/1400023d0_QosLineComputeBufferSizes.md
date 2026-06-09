# QosLineComputeBufferSizes

- ea: `0x1400023d0`
- end: `0x14000247e`
- name: `QosLineComputeBufferSizes`
- size: `174`
- prototype: `__int64(void)`
- caller_count: `5`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140001d40`
- `0x140001fec`
- `0x1400020f0`
- `0x1400039d8`
- `0x140003ab0`

## callees

- `0x1400023d0`

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
0x1400023d0  mov     r10, [rcx+8]
0x1400023d4  xor     r8d, r8d
0x1400023d7  mov     r9, rcx
0x1400023da  cmp     r10, 0FFFFFFFFFFFFFFFFh
0x1400023de  jz      loc_140002479
0x1400023e4  mov     ecx, [rcx+74h]
0x1400023e7  mov     rax, 431BDE82D7B634DBh
0x1400023f1  imul    rcx, r10
0x1400023f5  mul     rcx
0x1400023f8  mov     r11, rdx
0x1400023fb  shr     r11, 12h
0x1400023ff  cmp     r10, 8000000h
0x140002406  ja      short loc_140002460
0x140002408  mov     ecx, 32h ; '2'
0x14000240d  cmp     dword ptr [r9+68h], 0Ah
0x140002412  ja      short loc_140002474
0x140002414  mov     r8d, ecx
0x140002417  mov     rax, 47AE147AE147AE15h
0x140002421  imul    r8, r11
0x140002425  mul     r8
0x140002428  sub     r8, rdx
0x14000242b  shr     r8, 1
0x14000242e  add     r8, rdx
0x140002431  shr     r8, 6
0x140002435  mov     ecx, [r9+6Ch]
0x140002439  mov     eax, r11d
0x14000243c  imul    rcx, rax
0x140002440  mov     [r9+0CCh], eax
0x140002447  mov     eax, 0FFFFFFFFh
0x14000244c  add     rcx, rcx
0x14000244f  mov     [r9+78h], r8d
0x140002453  cmp     rcx, rax
0x140002456  cmovnb  rcx, rax
0x14000245a  mov     [r9+7Ch], ecx
0x14000245e  retn
0x140002460  cmp     r10, 0C80000h
0x140002467  jbe     short loc_140002408
0x140002469  mov     ecx, 17h
0x14000246e  lea     r8d, [rcx-0Bh]
0x140002472  jmp     short loc_14000240D
0x140002474  add     ecx, r8d
0x140002477  jmp     short loc_140002414
0x140002479  mov     r11, r8
0x14000247c  jmp     short loc_140002435
```
