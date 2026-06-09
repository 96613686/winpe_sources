# wil_details_FeatureReporting_RecordUsageInCache

- ea: `0x1800183b0`
- end: `0x18001852c`
- name: `wil_details_FeatureReporting_RecordUsageInCache`
- size: `380`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800185bc`

## callees

- `0x180018204`
- `0x1800182d4`
- `0x1800183b0`

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
0x1800183b0  mov     [rsp+arg_0], rbx
0x1800183b5  push    rdi
0x1800183b6  sub     rsp, 20h
0x1800183ba  xor     eax, eax
0x1800183bc  xorps   xmm0, xmm0
0x1800183bf  mov     edi, r9d
0x1800183c2  mov     r11, rdx
0x1800183c5  mov     r9, rcx
0x1800183c8  mov     r10d, r8d
0x1800183cb  movups  xmmword ptr [rcx], xmm0
0x1800183ce  mov     [rcx+10h], rax
0x1800183d2  test    r8d, r8d
0x1800183d5  jz      loc_180018513
0x1800183db  sub     r10d, 1
0x1800183df  jz      loc_180018506
0x1800183e5  sub     r10d, 1
0x1800183e9  jz      loc_180018488
0x1800183ef  sub     r10d, 1
0x1800183f3  jz      loc_180018488
0x1800183f9  sub     r10d, 1
0x1800183fd  jz      loc_180018513
0x180018403  sub     r10d, 1
0x180018407  jz      loc_180018506
0x18001840d  sub     r10d, 1
0x180018411  jz      short loc_180018488
0x180018413  cmp     r10d, 1
0x180018417  jz      short loc_180018488
0x180018419  lea     r10d, [r8-140h]
0x180018420  cmp     r10d, 40h ; '@'
0x180018424  jge     short loc_180018473
0x180018426  mov     eax, [rdx+4]
0x180018429  mov     ebx, r10d
0x18001842c  shl     ebx, 5
0x18001842f  mov     ecx, 10h
0x180018434  test    cl, al
0x180018436  jz      short loc_18001844C
0x180018438  mov     edx, eax
0x18001843a  shr     edx, 5
0x18001843d  and     edx, 3Fh
0x180018440  cmp     edx, r10d
0x180018443  jnz     short loc_18001844C
0x180018445  mov     edx, 1
0x18001844a  jmp     short loc_18001844E
0x18001844c  xor     edx, edx
0x18001844e  mov     [r9+10h], edx
0x180018452  mov     edx, ebx
0x180018454  xor     edx, eax
0x180018456  and     edx, 7E0h
0x18001845c  xor     edx, eax
0x18001845e  or      edx, ecx
0x180018460  lock cmpxchg [r11+4], edx
0x180018466  jnz     short loc_180018434
0x180018468  cmp     dword ptr [r9+10h], 0
0x18001846d  jnz     loc_18001851E
0x180018473  mov     [r9+8], r8d
0x180018477  mov     dword ptr [r9+4], 1
0x18001847f  mov     [r9+0Ch], edi
0x180018483  jmp     loc_18001851E
0x180018488  xor     ecx, ecx
0x18001848a  sub     r8d, 2
0x18001848e  jz      short loc_1800184B6
0x180018490  sub     r8d, 1
0x180018494  jz      short loc_1800184AF
0x180018496  sub     r8d, 3
0x18001849a  jz      short loc_1800184A8
0x18001849c  cmp     r8d, 1
0x1800184a0  jnz     short loc_1800184BB
0x1800184a2  lea     ecx, [r8+0Fh]
0x1800184a6  jmp     short loc_1800184BB
0x1800184a8  mov     ecx, 4
0x1800184ad  jmp     short loc_1800184BB
0x1800184af  mov     ecx, 8
0x1800184b4  jmp     short loc_1800184BB
0x1800184b6  mov     ecx, 2
0x1800184bb  mov     edx, [rdx]
0x1800184bd  xor     eax, eax
0x1800184bf  mov     r8d, ecx
0x1800184c2  or      r8d, edx
0x1800184c5  cmp     r8d, edx
0x1800184c8  mov     r10d, r8d
0x1800184cb  setz    al
0x1800184ce  or      r10d, 1
0x1800184d2  cmp     r8d, edx
0x1800184d5  mov     [r9+10h], eax
0x1800184d9  mov     eax, edx
0x1800184db  cmovz   r10d, r8d
0x1800184df  lock cmpxchg [r11], r10d
0x1800184e4  jz      short loc_1800184EA
0x1800184e6  mov     edx, eax
0x1800184e8  jmp     short loc_1800184BD
0x1800184ea  test    r10b, 1
0x1800184ee  setnz   cl
0x1800184f1  test    dl, 1
0x1800184f4  setz    al
0x1800184f7  test    al, cl
0x1800184f9  mov     eax, 0
0x1800184fe  setnz   al
0x180018501  mov     [r9], eax
0x180018504  jmp     short loc_18001851E
0x180018506  mov     edx, r8d
0x180018509  mov     rcx, r11
0x18001850c  call    wil_details_FeatureReporting_IncrementOpportunityInCache
0x180018511  jmp     short loc_18001851E
0x180018513  mov     edx, r8d
0x180018516  mov     rcx, r11
0x180018519  call    wil_details_FeatureReporting_IncrementUsageInCache
0x18001851e  mov     rbx, [rsp+28h+arg_0]
0x180018523  mov     rax, r9
0x180018526  add     rsp, 20h
0x18001852a  pop     rdi
0x18001852b  retn
```
