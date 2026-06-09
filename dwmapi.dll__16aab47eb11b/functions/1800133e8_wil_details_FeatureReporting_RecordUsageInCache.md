# wil_details_FeatureReporting_RecordUsageInCache

- ea: `0x1800133e8`
- end: `0x18001355e`
- name: `wil_details_FeatureReporting_RecordUsageInCache`
- size: `374`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180012308`

## callees

- `0x18001323c`
- `0x18001330c`
- `0x1800133e8`

## pseudocode

```c
__int64 __fastcall wil_details_FeatureReporting_RecordUsageInCache(__int64 a1, volatile signed __int32 *a2, __int64 a3)
{
  int v5; // r9d
  unsigned __int32 v6; // eax
  BOOL v7; // edx
  unsigned __int32 v8; // ett
  int v9; // ecx
  int v10; // r8d
  int v11; // r8d
  int v12; // r8d
  signed __int32 i; // edx
  signed __int32 v14; // r9d
  signed __int32 v15; // eax

  *(_OWORD *)a1 = 0;
  *(_QWORD *)(a1 + 16) = 0;
  switch ( (_DWORD)a3 )
  {
    case 0:
      goto LABEL_32;
    case 1:
LABEL_31:
      wil_details_FeatureReporting_IncrementOpportunityInCache(a2, (unsigned int)a3, a3, a1);
      return a1;
    case 2:
    case 3:
      goto LABEL_17;
    case 4:
LABEL_32:
      wil_details_FeatureReporting_IncrementUsageInCache(a2, (unsigned int)a3, a3, a1);
      return a1;
    case 5:
      goto LABEL_31;
  }
  if ( (unsigned int)(a3 - 6) >= 2 )
  {
    v5 = a3 - 320;
    if ( (int)a3 - 320 >= 64 )
      goto LABEL_16;
    v6 = *((_DWORD *)a2 + 1);
    do
    {
      v7 = (v6 & 0x10) != 0 && ((v6 >> 5) & 0x3F) == v5;
      *(_DWORD *)(a1 + 16) = v7;
      v8 = v6;
      v6 = _InterlockedCompareExchange(
             a2 + 1,
             v6 ^ ((unsigned __int16)v6 ^ (unsigned __int16)(32 * v5)) & 0x7E0 | 0x10,
             v6);
    }
    while ( v8 != v6 );
    if ( !*(_DWORD *)(a1 + 16) )
    {
LABEL_16:
      *(_DWORD *)(a1 + 8) = a3;
      *(_DWORD *)(a1 + 4) = 1;
      *(_DWORD *)(a1 + 12) = 0;
    }
    return a1;
  }
LABEL_17:
  v9 = 0;
  v10 = a3 - 2;
  if ( v10 )
  {
    v11 = v10 - 1;
    if ( v11 )
    {
      v12 = v11 - 3;
      if ( v12 )
      {
        if ( v12 == 1 )
          v9 = 16;
      }
      else
      {
        v9 = 4;
      }
    }
    else
    {
      v9 = 8;
    }
  }
  else
  {
    v9 = 2;
  }
  for ( i = *a2; ; i = v15 )
  {
    v14 = i | v9 | 1;
    *(_DWORD *)(a1 + 16) = (i | v9) == i;
    if ( (i | v9) == i )
      v14 = i | v9;
    v15 = _InterlockedCompareExchange(a2, v14, i);
    if ( i == v15 )
      break;
  }
  *(_DWORD *)a1 = (v14 & 1) != 0 && (i & 1) == 0;
  return a1;
}

```

## disassembly

```asm
0x1800133e8  push    rbx
0x1800133ea  sub     rsp, 20h
0x1800133ee  xor     eax, eax
0x1800133f0  xorps   xmm0, xmm0
0x1800133f3  mov     r10, rdx
0x1800133f6  mov     rbx, rcx
0x1800133f9  mov     r9d, r8d
0x1800133fc  movups  xmmword ptr [rcx], xmm0
0x1800133ff  mov     [rcx+10h], rax
0x180013403  test    r8d, r8d
0x180013406  jz      loc_180013547
0x18001340c  sub     r9d, 1
0x180013410  jz      loc_180013537
0x180013416  sub     r9d, 1
0x18001341a  jz      loc_1800134BB
0x180013420  sub     r9d, 1
0x180013424  jz      loc_1800134BB
0x18001342a  sub     r9d, 1
0x18001342e  jz      loc_180013547
0x180013434  sub     r9d, 1
0x180013438  jz      loc_180013537
0x18001343e  sub     r9d, 1
0x180013442  jz      short loc_1800134BB
0x180013444  cmp     r9d, 1
0x180013448  jz      short loc_1800134BB
0x18001344a  lea     r9d, [r8-140h]
0x180013451  cmp     r9d, 40h ; '@'
0x180013455  jge     short loc_1800134A4
0x180013457  mov     eax, [rdx+4]
0x18001345a  mov     r11d, r9d
0x18001345d  shl     r11d, 5
0x180013461  mov     ecx, 10h
0x180013466  test    cl, al
0x180013468  jz      short loc_18001347E
0x18001346a  mov     edx, eax
0x18001346c  shr     edx, 5
0x18001346f  and     edx, 3Fh
0x180013472  cmp     edx, r9d
0x180013475  jnz     short loc_18001347E
0x180013477  mov     edx, 1
0x18001347c  jmp     short loc_180013480
0x18001347e  xor     edx, edx
0x180013480  mov     [rbx+10h], edx
0x180013483  mov     edx, r11d
0x180013486  xor     edx, eax
0x180013488  and     edx, 7E0h
0x18001348e  xor     edx, eax
0x180013490  or      edx, ecx
0x180013492  lock cmpxchg [r10+4], edx
0x180013498  jnz     short loc_180013466
0x18001349a  cmp     dword ptr [rbx+10h], 0
0x18001349e  jnz     loc_180013555
0x1800134a4  mov     [rbx+8], r8d
0x1800134a8  mov     dword ptr [rbx+4], 1
0x1800134af  mov     dword ptr [rbx+0Ch], 0
0x1800134b6  jmp     loc_180013555
0x1800134bb  xor     ecx, ecx
0x1800134bd  sub     r8d, 2
0x1800134c1  jz      short loc_1800134E9
0x1800134c3  sub     r8d, 1
0x1800134c7  jz      short loc_1800134E2
0x1800134c9  sub     r8d, 3
0x1800134cd  jz      short loc_1800134DB
0x1800134cf  cmp     r8d, 1
0x1800134d3  jnz     short loc_1800134EE
0x1800134d5  lea     ecx, [r8+0Fh]
0x1800134d9  jmp     short loc_1800134EE
0x1800134db  mov     ecx, 4
0x1800134e0  jmp     short loc_1800134EE
0x1800134e2  mov     ecx, 8
0x1800134e7  jmp     short loc_1800134EE
0x1800134e9  mov     ecx, 2
0x1800134ee  mov     edx, [rdx]
0x1800134f0  xor     eax, eax
0x1800134f2  mov     r8d, ecx
0x1800134f5  or      r8d, edx
0x1800134f8  cmp     r8d, edx
0x1800134fb  mov     r9d, r8d
0x1800134fe  setz    al
0x180013501  or      r9d, 1
0x180013505  cmp     r8d, edx
0x180013508  mov     [rbx+10h], eax
0x18001350b  mov     eax, edx
0x18001350d  cmovz   r9d, r8d
0x180013511  lock cmpxchg [r10], r9d
0x180013516  jz      short loc_18001351C
0x180013518  mov     edx, eax
0x18001351a  jmp     short loc_1800134F0
0x18001351c  test    r9b, 1
0x180013520  setnz   cl
0x180013523  test    dl, 1
0x180013526  setz    al
0x180013529  test    al, cl
0x18001352b  mov     eax, 0
0x180013530  setnz   al
0x180013533  mov     [rbx], eax
0x180013535  jmp     short loc_180013555
0x180013537  mov     r9, rbx
0x18001353a  mov     edx, r8d
0x18001353d  mov     rcx, r10
0x180013540  call    wil_details_FeatureReporting_IncrementOpportunityInCache
0x180013545  jmp     short loc_180013555
0x180013547  mov     r9, rbx
0x18001354a  mov     edx, r8d
0x18001354d  mov     rcx, r10
0x180013550  call    wil_details_FeatureReporting_IncrementUsageInCache
0x180013555  mov     rax, rbx
0x180013558  add     rsp, 20h
0x18001355c  pop     rbx
0x18001355d  retn
```
