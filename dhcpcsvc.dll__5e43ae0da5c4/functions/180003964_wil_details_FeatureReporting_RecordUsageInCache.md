# wil_details_FeatureReporting_RecordUsageInCache

- ea: `0x180003964`
- end: `0x180003adf`
- name: `wil_details_FeatureReporting_RecordUsageInCache`
- size: `379`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800038f8`

## callees

- `0x180003964`
- `0x1800106e0`
- `0x1800107b0`

## pseudocode

```c
int *__fastcall wil_details_FeatureReporting_RecordUsageInCache(
        __int64 a1,
        volatile signed __int32 *a2,
        unsigned int a3,
        int a4)
{
  int *v6; // r9
  unsigned int v7; // ebx
  unsigned __int32 v8; // eax
  BOOL v9; // edx
  unsigned __int32 v10; // ett
  int v11; // ecx
  unsigned int v12; // r8d
  unsigned int v13; // r8d
  unsigned int v14; // r8d
  signed __int32 v15; // edx
  int v16; // r10d
  signed __int32 v17; // ebx
  signed __int32 v18; // eax

  v6 = (int *)a1;
  *(_OWORD *)a1 = 0;
  *(_QWORD *)(a1 + 16) = 0;
  switch ( a3 )
  {
    case 0u:
      goto LABEL_35;
    case 1u:
LABEL_34:
      wil_details_FeatureReporting_IncrementOpportunityInCache(a2, a3);
      return v6;
    case 2u:
    case 3u:
      goto LABEL_17;
    case 4u:
LABEL_35:
      wil_details_FeatureReporting_IncrementUsageInCache(a2, a3);
      return v6;
    case 5u:
      goto LABEL_34;
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
  v15 = *a2;
  v16 = 1;
  while ( 1 )
  {
    v17 = v15 | v11 | 1;
    v6[4] = (v15 | v11) == v15;
    if ( (v15 | v11) == v15 )
      v17 = v15 | v11;
    v18 = _InterlockedCompareExchange(a2, v17, v15);
    if ( v15 == v18 )
      break;
    v15 = v18;
  }
  if ( (v17 & 1) == 0 || (v15 & 1) != 0 )
    v16 = 0;
  *v6 = v16;
  return v6;
}

```

## disassembly

```asm
0x180003964  mov     [rsp+arg_0], rbx
0x180003969  mov     [rsp+arg_8], rsi
0x18000396e  push    rdi
0x18000396f  sub     rsp, 20h
0x180003973  xor     eax, eax
0x180003975  xorps   xmm0, xmm0
0x180003978  mov     esi, r9d
0x18000397b  mov     r11, rdx
0x18000397e  mov     r9, rcx
0x180003981  mov     r10d, r8d
0x180003984  movups  xmmword ptr [rcx], xmm0
0x180003987  mov     [rcx+10h], rax
0x18000398b  test    r8d, r8d
0x18000398e  jz      loc_180003AC1
0x180003994  sub     r10d, 1
0x180003998  jz      loc_180003AB4
0x18000399e  sub     r10d, 1
0x1800039a2  jz      loc_180003A3B
0x1800039a8  sub     r10d, 1
0x1800039ac  jz      loc_180003A3B
0x1800039b2  sub     r10d, 1
0x1800039b6  jz      loc_180003AC1
0x1800039bc  sub     r10d, 1
0x1800039c0  jz      loc_180003AB4
0x1800039c6  sub     r10d, 1
0x1800039ca  jz      short loc_180003A3B
0x1800039cc  cmp     r10d, 1
0x1800039d0  jz      short loc_180003A3B
0x1800039d2  lea     ebx, [r8-140h]
0x1800039d9  lea     r10d, [rax+1]
0x1800039dd  cmp     ebx, 40h ; '@'
0x1800039e0  jge     short loc_180003A2A
0x1800039e2  mov     eax, [rdx+4]
0x1800039e5  lea     ecx, [r10+0Fh]
0x1800039e9  mov     edi, ebx
0x1800039eb  shl     edi, 5
0x1800039ee  test    cl, al
0x1800039f0  jz      short loc_180003A03
0x1800039f2  mov     edx, eax
0x1800039f4  shr     edx, 5
0x1800039f7  and     edx, 3Fh
0x1800039fa  cmp     edx, ebx
0x1800039fc  jnz     short loc_180003A03
0x1800039fe  mov     edx, r10d
0x180003a01  jmp     short loc_180003A05
0x180003a03  xor     edx, edx
0x180003a05  mov     [r9+10h], edx
0x180003a09  mov     edx, edi
0x180003a0b  xor     edx, eax
0x180003a0d  and     edx, 7E0h
0x180003a13  xor     edx, eax
0x180003a15  or      edx, ecx
0x180003a17  lock cmpxchg [r11+4], edx
0x180003a1d  jnz     short loc_1800039EE
0x180003a1f  cmp     dword ptr [r9+10h], 0
0x180003a24  jnz     loc_180003ACC
0x180003a2a  mov     [r9+8], r8d
0x180003a2e  mov     [r9+4], r10d
0x180003a32  mov     [r9+0Ch], esi
0x180003a36  jmp     loc_180003ACC
0x180003a3b  xor     ecx, ecx
0x180003a3d  sub     r8d, 2
0x180003a41  jz      short loc_180003A69
0x180003a43  sub     r8d, 1
0x180003a47  jz      short loc_180003A62
0x180003a49  sub     r8d, 3
0x180003a4d  jz      short loc_180003A5B
0x180003a4f  cmp     r8d, 1
0x180003a53  jnz     short loc_180003A6E
0x180003a55  lea     ecx, [r8+0Fh]
0x180003a59  jmp     short loc_180003A6E
0x180003a5b  mov     ecx, 4
0x180003a60  jmp     short loc_180003A6E
0x180003a62  mov     ecx, 8
0x180003a67  jmp     short loc_180003A6E
0x180003a69  mov     ecx, 2
0x180003a6e  mov     edx, [rdx]
0x180003a70  mov     r10d, 1
0x180003a76  xor     eax, eax
0x180003a78  mov     r8d, ecx
0x180003a7b  or      r8d, edx
0x180003a7e  cmp     r8d, edx
0x180003a81  mov     ebx, r8d
0x180003a84  setz    al
0x180003a87  or      ebx, r10d
0x180003a8a  cmp     r8d, edx
0x180003a8d  mov     [r9+10h], eax
0x180003a91  mov     eax, edx
0x180003a93  cmovz   ebx, r8d
0x180003a97  lock cmpxchg [r11], ebx
0x180003a9c  jz      short loc_180003AA2
0x180003a9e  mov     edx, eax
0x180003aa0  jmp     short loc_180003A76
0x180003aa2  test    r10b, bl
0x180003aa5  jz      short loc_180003AAC
0x180003aa7  test    r10b, dl
0x180003aaa  jz      short loc_180003AAF
0x180003aac  xor     r10d, r10d
0x180003aaf  mov     [r9], r10d
0x180003ab2  jmp     short loc_180003ACC
0x180003ab4  mov     edx, r8d
0x180003ab7  mov     rcx, r11
0x180003aba  call    wil_details_FeatureReporting_IncrementOpportunityInCache
0x180003abf  jmp     short loc_180003ACC
0x180003ac1  mov     edx, r8d
0x180003ac4  mov     rcx, r11
0x180003ac7  call    wil_details_FeatureReporting_IncrementUsageInCache
0x180003acc  mov     rbx, [rsp+28h+arg_0]
0x180003ad1  mov     rax, r9
0x180003ad4  mov     rsi, [rsp+28h+arg_8]
0x180003ad9  add     rsp, 20h
0x180003add  pop     rdi
0x180003ade  retn
```
