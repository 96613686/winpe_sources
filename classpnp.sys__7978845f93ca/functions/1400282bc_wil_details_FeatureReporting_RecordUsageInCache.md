# wil_details_FeatureReporting_RecordUsageInCache

- ea: `0x1400282bc`
- end: `0x140028439`
- name: `wil_details_FeatureReporting_RecordUsageInCache`
- size: `381`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1400284bc`

## callees

- `0x140028110`
- `0x1400281e0`
- `0x1400282bc`

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
0x1400282bc  mov     [rsp+arg_0], rbx
0x1400282c1  push    rdi
0x1400282c2  sub     rsp, 20h
0x1400282c6  xor     eax, eax
0x1400282c8  xorps   xmm0, xmm0
0x1400282cb  mov     edi, r9d
0x1400282ce  mov     r11, rdx
0x1400282d1  mov     r9, rcx
0x1400282d4  mov     r10d, r8d
0x1400282d7  movups  xmmword ptr [rcx], xmm0
0x1400282da  mov     [rcx+10h], rax
0x1400282de  test    r8d, r8d
0x1400282e1  jz      loc_14002841F
0x1400282e7  sub     r10d, 1
0x1400282eb  jz      loc_140028412
0x1400282f1  sub     r10d, 1
0x1400282f5  jz      loc_140028394
0x1400282fb  sub     r10d, 1
0x1400282ff  jz      loc_140028394
0x140028305  sub     r10d, 1
0x140028309  jz      loc_14002841F
0x14002830f  sub     r10d, 1
0x140028313  jz      loc_140028412
0x140028319  sub     r10d, 1
0x14002831d  jz      short loc_140028394
0x14002831f  cmp     r10d, 1
0x140028323  jz      short loc_140028394
0x140028325  lea     r10d, [r8-140h]
0x14002832c  cmp     r10d, 40h ; '@'
0x140028330  jge     short loc_14002837F
0x140028332  mov     eax, [rdx+4]
0x140028335  mov     ebx, r10d
0x140028338  shl     ebx, 5
0x14002833b  mov     ecx, 10h
0x140028340  test    cl, al
0x140028342  jz      short loc_140028358
0x140028344  mov     edx, eax
0x140028346  shr     edx, 5
0x140028349  and     edx, 3Fh
0x14002834c  cmp     edx, r10d
0x14002834f  jnz     short loc_140028358
0x140028351  mov     edx, 1
0x140028356  jmp     short loc_14002835A
0x140028358  xor     edx, edx
0x14002835a  mov     [r9+10h], edx
0x14002835e  mov     edx, ebx
0x140028360  xor     edx, eax
0x140028362  and     edx, 7E0h
0x140028368  xor     edx, eax
0x14002836a  or      edx, ecx
0x14002836c  lock cmpxchg [r11+4], edx
0x140028372  jnz     short loc_140028340
0x140028374  cmp     dword ptr [r9+10h], 0
0x140028379  jnz     loc_14002842A
0x14002837f  mov     [r9+8], r8d
0x140028383  mov     dword ptr [r9+4], 1
0x14002838b  mov     [r9+0Ch], edi
0x14002838f  jmp     loc_14002842A
0x140028394  xor     ecx, ecx
0x140028396  sub     r8d, 2
0x14002839a  jz      short loc_1400283C2
0x14002839c  sub     r8d, 1
0x1400283a0  jz      short loc_1400283BB
0x1400283a2  sub     r8d, 3
0x1400283a6  jz      short loc_1400283B4
0x1400283a8  cmp     r8d, 1
0x1400283ac  jnz     short loc_1400283C7
0x1400283ae  lea     ecx, [r8+0Fh]
0x1400283b2  jmp     short loc_1400283C7
0x1400283b4  mov     ecx, 4
0x1400283b9  jmp     short loc_1400283C7
0x1400283bb  mov     ecx, 8
0x1400283c0  jmp     short loc_1400283C7
0x1400283c2  mov     ecx, 2
0x1400283c7  mov     edx, [rdx]
0x1400283c9  xor     eax, eax
0x1400283cb  mov     r8d, ecx
0x1400283ce  or      r8d, edx
0x1400283d1  cmp     r8d, edx
0x1400283d4  mov     r10d, r8d
0x1400283d7  setz    al
0x1400283da  or      r10d, 1
0x1400283de  cmp     r8d, edx
0x1400283e1  mov     [r9+10h], eax
0x1400283e5  mov     eax, edx
0x1400283e7  cmovz   r10d, r8d
0x1400283eb  lock cmpxchg [r11], r10d
0x1400283f0  jz      short loc_1400283F6
0x1400283f2  mov     edx, eax
0x1400283f4  jmp     short loc_1400283C9
0x1400283f6  test    r10b, 1
0x1400283fa  setnz   cl
0x1400283fd  test    dl, 1
0x140028400  setz    al
0x140028403  test    al, cl
0x140028405  mov     eax, 0
0x14002840a  setnz   al
0x14002840d  mov     [r9], eax
0x140028410  jmp     short loc_14002842A
0x140028412  mov     edx, r8d
0x140028415  mov     rcx, r11
0x140028418  call    wil_details_FeatureReporting_IncrementOpportunityInCache
0x14002841d  jmp     short loc_14002842A
0x14002841f  mov     edx, r8d
0x140028422  mov     rcx, r11
0x140028425  call    wil_details_FeatureReporting_IncrementUsageInCache
0x14002842a  mov     rbx, [rsp+28h+arg_0]
0x14002842f  mov     rax, r9
0x140028432  add     rsp, 20h
0x140028436  pop     rdi
0x140028437  retn
```
