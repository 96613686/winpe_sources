# wil_details_FeatureReporting_IncrementOpportunityInCache

- ea: `0x140002930`
- end: `0x1400029fa`
- name: `wil_details_FeatureReporting_IncrementOpportunityInCache`
- size: `202`
- prototype: `__int64 __fastcall(volatile signed __int32 *, int, __int64, _DWORD *)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140002adc`

## callees

- `0x140002930`

## pseudocode

```c
__int64 __fastcall wil_details_FeatureReporting_IncrementOpportunityInCache(
        volatile signed __int32 *a1,
        int a2,
        __int64 a3,
        _DWORD *a4)
{
  signed __int32 v4; // r8d
  int *v5; // r10
  BOOL v8; // ebx
  unsigned int v9; // eax
  int v10; // ecx
  int v11; // edx
  unsigned int v12; // ecx
  unsigned int v13; // edx
  __int64 result; // rax

  v4 = *a1;
  v5 = a4 + 2;
  v8 = a2 == 5;
  while ( 1 )
  {
    a4[1] = 0;
    v9 = v4 | 1;
    if ( (((v4 | 1u) >> 22) & 1) != v8 )
    {
      if ( ((v9 >> 15) & 0x7F) != 0 )
      {
        a4[1] = (v9 >> 15) & 0x7F;
        v10 = 5;
        v5 = a4 + 2;
        if ( a2 != 1 )
          v10 = 1;
        v9 = v4 & 0xFFC07FFE | 1;
        *v5 = v10;
      }
      v11 = 0;
      if ( a2 == 5 )
        v11 = 0x400000;
      v9 = v9 & 0xFFBFFFFF | v11;
    }
    v12 = (v9 >> 15) & 0x7F;
    v13 = v12 + 1;
    if ( v12 + 1 > 0x7F || v13 < v12 )
    {
      v13 = 1;
      *v5 = a2;
      a4[1] = v12;
    }
    else
    {
      v5 = a4 + 2;
    }
    result = (unsigned int)_InterlockedCompareExchange(a1, v9 ^ (v9 ^ (v13 << 15)) & 0x3F8000, v4);
    if ( v4 == (_DWORD)result )
      break;
    v4 = result;
  }
  a4[4] = 0;
  *a4 = (v4 & 1) == 0;
  return result;
}

```

## disassembly

```asm
0x140002930  push    rbx
0x140002932  push    rsi
0x140002933  push    rdi
0x140002934  mov     r8d, [rcx]
0x140002937  lea     r10, [r9+8]
0x14000293b  xor     ebx, ebx
0x14000293d  mov     r11d, edx
0x140002940  cmp     edx, 5
0x140002943  mov     rdi, rcx
0x140002946  mov     esi, 1
0x14000294b  setz    bl
0x14000294e  mov     eax, r8d
0x140002951  mov     dword ptr [r9+4], 0
0x140002959  or      eax, esi
0x14000295b  mov     ecx, eax
0x14000295d  shr     ecx, 16h
0x140002960  and     ecx, esi
0x140002962  cmp     ecx, ebx
0x140002964  jz      short loc_1400029A3
0x140002966  mov     edx, eax
0x140002968  shr     edx, 0Fh
0x14000296b  and     edx, 7Fh
0x14000296e  jbe     short loc_14000298B
0x140002970  cmp     r11d, esi
0x140002973  mov     [r9+4], edx
0x140002977  mov     ecx, 5
0x14000297c  lea     r10, [r9+8]
0x140002980  cmovnz  ecx, esi
0x140002983  and     eax, 0FFC07FFFh
0x140002988  mov     [r10], ecx
0x14000298b  xor     edx, edx
0x14000298d  mov     ecx, 400000h
0x140002992  cmp     r11d, 5
0x140002996  cmovz   edx, ecx
0x140002999  mov     ecx, eax
0x14000299b  btr     ecx, 16h
0x14000299f  mov     eax, edx
0x1400029a1  or      eax, ecx
0x1400029a3  mov     ecx, eax
0x1400029a5  shr     ecx, 0Fh
0x1400029a8  and     ecx, 7Fh
0x1400029ab  lea     edx, [rcx+1]
0x1400029ae  cmp     edx, 7Fh
0x1400029b1  ja      short loc_1400029BD
0x1400029b3  cmp     edx, ecx
0x1400029b5  jb      short loc_1400029BD
0x1400029b7  lea     r10, [r9+8]
0x1400029bb  jmp     short loc_1400029C6
0x1400029bd  mov     edx, esi
0x1400029bf  mov     [r10], r11d
0x1400029c2  mov     [r9+4], ecx
0x1400029c6  shl     edx, 0Fh
0x1400029c9  xor     edx, eax
0x1400029cb  and     edx, 3F8000h
0x1400029d1  xor     edx, eax
0x1400029d3  mov     eax, r8d
0x1400029d6  lock cmpxchg [rdi], edx
0x1400029da  jz      short loc_1400029E4
0x1400029dc  mov     r8d, eax
0x1400029df  jmp     loc_14000294E
0x1400029e4  not     r8d
0x1400029e7  mov     dword ptr [r9+10h], 0
0x1400029ef  and     r8d, esi
0x1400029f2  mov     [r9], r8d
0x1400029f5  pop     rdi
0x1400029f6  pop     rsi
0x1400029f7  pop     rbx
0x1400029f8  retn
```
