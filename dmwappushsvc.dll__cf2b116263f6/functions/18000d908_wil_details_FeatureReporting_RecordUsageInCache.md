# wil_details_FeatureReporting_RecordUsageInCache

- ea: `0x18000d908`
- end: `0x18000da7e`
- name: `wil_details_FeatureReporting_RecordUsageInCache`
- size: `374`
- prototype: `__int64 __fastcall(__int64, volatile signed __int32 *, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000ae24`

## callees

- `0x18000d75c`
- `0x18000d82c`
- `0x18000d908`

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
      wil_details_FeatureReporting_IncrementOpportunityInCache(a2, a3, a3, (_DWORD *)a1);
      return a1;
    case 2:
    case 3:
      goto LABEL_17;
    case 4:
LABEL_32:
      wil_details_FeatureReporting_IncrementUsageInCache(a2, a3, a3, (_DWORD *)a1);
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
0x18000d908  push    rbx
0x18000d90a  sub     rsp, 20h
0x18000d90e  xor     eax, eax
0x18000d910  xorps   xmm0, xmm0
0x18000d913  mov     r10, rdx
0x18000d916  mov     rbx, rcx
0x18000d919  mov     r9d, r8d
0x18000d91c  movups  xmmword ptr [rcx], xmm0
0x18000d91f  mov     [rcx+10h], rax
0x18000d923  test    r8d, r8d
0x18000d926  jz      loc_18000DA67
0x18000d92c  sub     r9d, 1
0x18000d930  jz      loc_18000DA57
0x18000d936  sub     r9d, 1
0x18000d93a  jz      loc_18000D9DB
0x18000d940  sub     r9d, 1
0x18000d944  jz      loc_18000D9DB
0x18000d94a  sub     r9d, 1
0x18000d94e  jz      loc_18000DA67
0x18000d954  sub     r9d, 1
0x18000d958  jz      loc_18000DA57
0x18000d95e  sub     r9d, 1
0x18000d962  jz      short loc_18000D9DB
0x18000d964  cmp     r9d, 1
0x18000d968  jz      short loc_18000D9DB
0x18000d96a  lea     r9d, [r8-140h]
0x18000d971  cmp     r9d, 40h ; '@'
0x18000d975  jge     short loc_18000D9C4
0x18000d977  mov     eax, [rdx+4]
0x18000d97a  mov     r11d, r9d
0x18000d97d  shl     r11d, 5
0x18000d981  mov     ecx, 10h
0x18000d986  test    cl, al
0x18000d988  jz      short loc_18000D99E
0x18000d98a  mov     edx, eax
0x18000d98c  shr     edx, 5
0x18000d98f  and     edx, 3Fh
0x18000d992  cmp     edx, r9d
0x18000d995  jnz     short loc_18000D99E
0x18000d997  mov     edx, 1
0x18000d99c  jmp     short loc_18000D9A0
0x18000d99e  xor     edx, edx
0x18000d9a0  mov     [rbx+10h], edx
0x18000d9a3  mov     edx, r11d
0x18000d9a6  xor     edx, eax
0x18000d9a8  and     edx, 7E0h
0x18000d9ae  xor     edx, eax
0x18000d9b0  or      edx, ecx
0x18000d9b2  lock cmpxchg [r10+4], edx
0x18000d9b8  jnz     short loc_18000D986
0x18000d9ba  cmp     dword ptr [rbx+10h], 0
0x18000d9be  jnz     loc_18000DA75
0x18000d9c4  mov     [rbx+8], r8d
0x18000d9c8  mov     dword ptr [rbx+4], 1
0x18000d9cf  mov     dword ptr [rbx+0Ch], 0
0x18000d9d6  jmp     loc_18000DA75
0x18000d9db  xor     ecx, ecx
0x18000d9dd  sub     r8d, 2
0x18000d9e1  jz      short loc_18000DA09
0x18000d9e3  sub     r8d, 1
0x18000d9e7  jz      short loc_18000DA02
0x18000d9e9  sub     r8d, 3
0x18000d9ed  jz      short loc_18000D9FB
0x18000d9ef  cmp     r8d, 1
0x18000d9f3  jnz     short loc_18000DA0E
0x18000d9f5  lea     ecx, [r8+0Fh]
0x18000d9f9  jmp     short loc_18000DA0E
0x18000d9fb  mov     ecx, 4
0x18000da00  jmp     short loc_18000DA0E
0x18000da02  mov     ecx, 8
0x18000da07  jmp     short loc_18000DA0E
0x18000da09  mov     ecx, 2
0x18000da0e  mov     edx, [rdx]
0x18000da10  xor     eax, eax
0x18000da12  mov     r8d, ecx
0x18000da15  or      r8d, edx
0x18000da18  cmp     r8d, edx
0x18000da1b  mov     r9d, r8d
0x18000da1e  setz    al
0x18000da21  or      r9d, 1
0x18000da25  cmp     r8d, edx
0x18000da28  mov     [rbx+10h], eax
0x18000da2b  mov     eax, edx
0x18000da2d  cmovz   r9d, r8d
0x18000da31  lock cmpxchg [r10], r9d
0x18000da36  jz      short loc_18000DA3C
0x18000da38  mov     edx, eax
0x18000da3a  jmp     short loc_18000DA10
0x18000da3c  test    r9b, 1
0x18000da40  setnz   cl
0x18000da43  test    dl, 1
0x18000da46  setz    al
0x18000da49  test    al, cl
0x18000da4b  mov     eax, 0
0x18000da50  setnz   al
0x18000da53  mov     [rbx], eax
0x18000da55  jmp     short loc_18000DA75
0x18000da57  mov     r9, rbx
0x18000da5a  mov     edx, r8d
0x18000da5d  mov     rcx, r10
0x18000da60  call    wil_details_FeatureReporting_IncrementOpportunityInCache
0x18000da65  jmp     short loc_18000DA75
0x18000da67  mov     r9, rbx
0x18000da6a  mov     edx, r8d
0x18000da6d  mov     rcx, r10
0x18000da70  call    wil_details_FeatureReporting_IncrementUsageInCache
0x18000da75  mov     rax, rbx
0x18000da78  add     rsp, 20h
0x18000da7c  pop     rbx
0x18000da7d  retn
```
