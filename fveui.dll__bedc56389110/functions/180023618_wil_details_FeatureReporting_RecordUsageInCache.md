# wil_details_FeatureReporting_RecordUsageInCache

- ea: `0x180023618`
- end: `0x18002378e`
- name: `wil_details_FeatureReporting_RecordUsageInCache`
- size: `374`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180018968`

## callees

- `0x18002346c`
- `0x18002353c`
- `0x180023618`

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
0x180023618  push    rbx
0x18002361a  sub     rsp, 20h
0x18002361e  xor     eax, eax
0x180023620  xorps   xmm0, xmm0
0x180023623  mov     r10, rdx
0x180023626  mov     rbx, rcx
0x180023629  mov     r9d, r8d
0x18002362c  movups  xmmword ptr [rcx], xmm0
0x18002362f  mov     [rcx+10h], rax
0x180023633  test    r8d, r8d
0x180023636  jz      loc_180023777
0x18002363c  sub     r9d, 1
0x180023640  jz      loc_180023767
0x180023646  sub     r9d, 1
0x18002364a  jz      loc_1800236EB
0x180023650  sub     r9d, 1
0x180023654  jz      loc_1800236EB
0x18002365a  sub     r9d, 1
0x18002365e  jz      loc_180023777
0x180023664  sub     r9d, 1
0x180023668  jz      loc_180023767
0x18002366e  sub     r9d, 1
0x180023672  jz      short loc_1800236EB
0x180023674  cmp     r9d, 1
0x180023678  jz      short loc_1800236EB
0x18002367a  lea     r9d, [r8-140h]
0x180023681  cmp     r9d, 40h ; '@'
0x180023685  jge     short loc_1800236D4
0x180023687  mov     eax, [rdx+4]
0x18002368a  mov     r11d, r9d
0x18002368d  shl     r11d, 5
0x180023691  mov     ecx, 10h
0x180023696  test    cl, al
0x180023698  jz      short loc_1800236AE
0x18002369a  mov     edx, eax
0x18002369c  shr     edx, 5
0x18002369f  and     edx, 3Fh
0x1800236a2  cmp     edx, r9d
0x1800236a5  jnz     short loc_1800236AE
0x1800236a7  mov     edx, 1
0x1800236ac  jmp     short loc_1800236B0
0x1800236ae  xor     edx, edx
0x1800236b0  mov     [rbx+10h], edx
0x1800236b3  mov     edx, r11d
0x1800236b6  xor     edx, eax
0x1800236b8  and     edx, 7E0h
0x1800236be  xor     edx, eax
0x1800236c0  or      edx, ecx
0x1800236c2  lock cmpxchg [r10+4], edx
0x1800236c8  jnz     short loc_180023696
0x1800236ca  cmp     dword ptr [rbx+10h], 0
0x1800236ce  jnz     loc_180023785
0x1800236d4  mov     [rbx+8], r8d
0x1800236d8  mov     dword ptr [rbx+4], 1
0x1800236df  mov     dword ptr [rbx+0Ch], 0
0x1800236e6  jmp     loc_180023785
0x1800236eb  xor     ecx, ecx
0x1800236ed  sub     r8d, 2
0x1800236f1  jz      short loc_180023719
0x1800236f3  sub     r8d, 1
0x1800236f7  jz      short loc_180023712
0x1800236f9  sub     r8d, 3
0x1800236fd  jz      short loc_18002370B
0x1800236ff  cmp     r8d, 1
0x180023703  jnz     short loc_18002371E
0x180023705  lea     ecx, [r8+0Fh]
0x180023709  jmp     short loc_18002371E
0x18002370b  mov     ecx, 4
0x180023710  jmp     short loc_18002371E
0x180023712  mov     ecx, 8
0x180023717  jmp     short loc_18002371E
0x180023719  mov     ecx, 2
0x18002371e  mov     edx, [rdx]
0x180023720  xor     eax, eax
0x180023722  mov     r8d, ecx
0x180023725  or      r8d, edx
0x180023728  cmp     r8d, edx
0x18002372b  mov     r9d, r8d
0x18002372e  setz    al
0x180023731  or      r9d, 1
0x180023735  cmp     r8d, edx
0x180023738  mov     [rbx+10h], eax
0x18002373b  mov     eax, edx
0x18002373d  cmovz   r9d, r8d
0x180023741  lock cmpxchg [r10], r9d
0x180023746  jz      short loc_18002374C
0x180023748  mov     edx, eax
0x18002374a  jmp     short loc_180023720
0x18002374c  test    r9b, 1
0x180023750  setnz   cl
0x180023753  test    dl, 1
0x180023756  setz    al
0x180023759  test    al, cl
0x18002375b  mov     eax, 0
0x180023760  setnz   al
0x180023763  mov     [rbx], eax
0x180023765  jmp     short loc_180023785
0x180023767  mov     r9, rbx
0x18002376a  mov     edx, r8d
0x18002376d  mov     rcx, r10
0x180023770  call    wil_details_FeatureReporting_IncrementOpportunityInCache
0x180023775  jmp     short loc_180023785
0x180023777  mov     r9, rbx
0x18002377a  mov     edx, r8d
0x18002377d  mov     rcx, r10
0x180023780  call    wil_details_FeatureReporting_IncrementUsageInCache
0x180023785  mov     rax, rbx
0x180023788  add     rsp, 20h
0x18002378c  pop     rbx
0x18002378d  retn
```
