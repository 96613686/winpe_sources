# wil_details_FeatureReporting_RecordUsageInCache

- ea: `0x1400028ec`
- end: `0x140002a69`
- name: `wil_details_FeatureReporting_RecordUsageInCache`
- size: `381`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x140002af8`

## callees

- `0x140002740`
- `0x140002810`
- `0x1400028ec`

## pseudocode

```c
_DWORD *__fastcall wil_details_FeatureReporting_RecordUsageInCache(
        __int64 a1,
        volatile signed __int32 *a2,
        unsigned int a3,
        int a4)
{
  _DWORD *v6; // r9
  unsigned int v7; // r10d
  unsigned __int32 v8; // eax
  BOOL v9; // edx
  unsigned __int32 v10; // ett
  int v11; // ecx
  unsigned int v12; // r8d
  unsigned int v13; // r8d
  unsigned int v14; // r8d
  signed __int32 i; // edx
  signed __int32 v16; // r10d
  signed __int32 v17; // eax

  v6 = (_DWORD *)a1;
  *(_OWORD *)a1 = 0;
  *(_QWORD *)(a1 + 16) = 0;
  switch ( a3 )
  {
    case 0u:
      goto LABEL_32;
    case 1u:
LABEL_31:
      wil_details_FeatureReporting_IncrementOpportunityInCache(a2, a3);
      return v6;
    case 2u:
    case 3u:
      goto LABEL_17;
    case 4u:
LABEL_32:
      wil_details_FeatureReporting_IncrementUsageInCache(a2, a3);
      return v6;
    case 5u:
      goto LABEL_31;
  }
  if ( a3 - 6 >= 2 )
  {
    v7 = a3 - 320;
    if ( (int)(a3 - 320) >= 64 )
      goto LABEL_16;
    v8 = *((_DWORD *)a2 + 1);
    do
    {
      v9 = (v8 & 0x10) != 0 && ((v8 >> 5) & 0x3F) == v7;
      *(_DWORD *)(a1 + 16) = v9;
      v10 = v8;
      v8 = _InterlockedCompareExchange(
             a2 + 1,
             v8 ^ ((unsigned __int16)v8 ^ (unsigned __int16)(32 * v7)) & 0x7E0 | 0x10,
             v8);
    }
    while ( v10 != v8 );
    if ( !*(_DWORD *)(a1 + 16) )
    {
LABEL_16:
      *(_DWORD *)(a1 + 8) = a3;
      *(_DWORD *)(a1 + 4) = 1;
      *(_DWORD *)(a1 + 12) = a4;
    }
    return v6;
  }
LABEL_17:
  v11 = 0;
  v12 = a3 - 2;
  if ( v12 )
  {
    v13 = v12 - 1;
    if ( v13 )
    {
      v14 = v13 - 3;
      if ( v14 )
      {
        if ( v14 == 1 )
          v11 = 16;
      }
      else
      {
        v11 = 4;
      }
    }
    else
    {
      v11 = 8;
    }
  }
  else
  {
    v11 = 2;
  }
  for ( i = *a2; ; i = v17 )
  {
    v16 = i | v11 | 1;
    v6[4] = (i | v11) == i;
    if ( (i | v11) == i )
      v16 = i | v11;
    v17 = _InterlockedCompareExchange(a2, v16, i);
    if ( i == v17 )
      break;
  }
  *v6 = (v16 & 1) != 0 && (i & 1) == 0;
  return v6;
}

```

## disassembly

```asm
0x1400028ec  mov     [rsp+arg_0], rbx
0x1400028f1  push    rdi
0x1400028f2  sub     rsp, 20h
0x1400028f6  xor     eax, eax
0x1400028f8  xorps   xmm0, xmm0
0x1400028fb  mov     edi, r9d
0x1400028fe  mov     r11, rdx
0x140002901  mov     r9, rcx
0x140002904  mov     r10d, r8d
0x140002907  movups  xmmword ptr [rcx], xmm0
0x14000290a  mov     [rcx+10h], rax
0x14000290e  test    r8d, r8d
0x140002911  jz      loc_140002A4F
0x140002917  sub     r10d, 1
0x14000291b  jz      loc_140002A42
0x140002921  sub     r10d, 1
0x140002925  jz      loc_1400029C4
0x14000292b  sub     r10d, 1
0x14000292f  jz      loc_1400029C4
0x140002935  sub     r10d, 1
0x140002939  jz      loc_140002A4F
0x14000293f  sub     r10d, 1
0x140002943  jz      loc_140002A42
0x140002949  sub     r10d, 1
0x14000294d  jz      short loc_1400029C4
0x14000294f  cmp     r10d, 1
0x140002953  jz      short loc_1400029C4
0x140002955  lea     r10d, [r8-140h]
0x14000295c  cmp     r10d, 40h ; '@'
0x140002960  jge     short loc_1400029AF
0x140002962  mov     eax, [rdx+4]
0x140002965  mov     ebx, r10d
0x140002968  shl     ebx, 5
0x14000296b  mov     ecx, 10h
0x140002970  test    cl, al
0x140002972  jz      short loc_140002988
0x140002974  mov     edx, eax
0x140002976  shr     edx, 5
0x140002979  and     edx, 3Fh
0x14000297c  cmp     edx, r10d
0x14000297f  jnz     short loc_140002988
0x140002981  mov     edx, 1
0x140002986  jmp     short loc_14000298A
0x140002988  xor     edx, edx
0x14000298a  mov     [r9+10h], edx
0x14000298e  mov     edx, ebx
0x140002990  xor     edx, eax
0x140002992  and     edx, 7E0h
0x140002998  xor     edx, eax
0x14000299a  or      edx, ecx
0x14000299c  lock cmpxchg [r11+4], edx
0x1400029a2  jnz     short loc_140002970
0x1400029a4  cmp     dword ptr [r9+10h], 0
0x1400029a9  jnz     loc_140002A5A
0x1400029af  mov     [r9+8], r8d
0x1400029b3  mov     dword ptr [r9+4], 1
0x1400029bb  mov     [r9+0Ch], edi
0x1400029bf  jmp     loc_140002A5A
0x1400029c4  xor     ecx, ecx
0x1400029c6  sub     r8d, 2
0x1400029ca  jz      short loc_1400029F2
0x1400029cc  sub     r8d, 1
0x1400029d0  jz      short loc_1400029EB
0x1400029d2  sub     r8d, 3
0x1400029d6  jz      short loc_1400029E4
0x1400029d8  cmp     r8d, 1
0x1400029dc  jnz     short loc_1400029F7
0x1400029de  lea     ecx, [r8+0Fh]
0x1400029e2  jmp     short loc_1400029F7
0x1400029e4  mov     ecx, 4
0x1400029e9  jmp     short loc_1400029F7
0x1400029eb  mov     ecx, 8
0x1400029f0  jmp     short loc_1400029F7
0x1400029f2  mov     ecx, 2
0x1400029f7  mov     edx, [rdx]
0x1400029f9  xor     eax, eax
0x1400029fb  mov     r8d, ecx
0x1400029fe  or      r8d, edx
0x140002a01  cmp     r8d, edx
0x140002a04  mov     r10d, r8d
0x140002a07  setz    al
0x140002a0a  or      r10d, 1
0x140002a0e  cmp     r8d, edx
0x140002a11  mov     [r9+10h], eax
0x140002a15  mov     eax, edx
0x140002a17  cmovz   r10d, r8d
0x140002a1b  lock cmpxchg [r11], r10d
0x140002a20  jz      short loc_140002A26
0x140002a22  mov     edx, eax
0x140002a24  jmp     short loc_1400029F9
0x140002a26  test    r10b, 1
0x140002a2a  setnz   cl
0x140002a2d  test    dl, 1
0x140002a30  setz    al
0x140002a33  test    al, cl
0x140002a35  mov     eax, 0
0x140002a3a  setnz   al
0x140002a3d  mov     [r9], eax
0x140002a40  jmp     short loc_140002A5A
0x140002a42  mov     edx, r8d
0x140002a45  mov     rcx, r11
0x140002a48  call    wil_details_FeatureReporting_IncrementOpportunityInCache
0x140002a4d  jmp     short loc_140002A5A
0x140002a4f  mov     edx, r8d
0x140002a52  mov     rcx, r11
0x140002a55  call    wil_details_FeatureReporting_IncrementUsageInCache
0x140002a5a  mov     rbx, [rsp+28h+arg_0]
0x140002a5f  mov     rax, r9
0x140002a62  add     rsp, 20h
0x140002a66  pop     rdi
0x140002a67  retn
```
