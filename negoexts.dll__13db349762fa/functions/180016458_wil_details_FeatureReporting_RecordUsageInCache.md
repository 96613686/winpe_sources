# wil_details_FeatureReporting_RecordUsageInCache

- ea: `0x180016458`
- end: `0x1800165ce`
- name: `wil_details_FeatureReporting_RecordUsageInCache`
- size: `374`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180013ab4`

## callees

- `0x1800162ac`
- `0x18001637c`
- `0x180016458`

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
0x180016458  push    rbx
0x18001645a  sub     rsp, 20h
0x18001645e  xor     eax, eax
0x180016460  xorps   xmm0, xmm0
0x180016463  mov     r10, rdx
0x180016466  mov     rbx, rcx
0x180016469  mov     r9d, r8d
0x18001646c  movups  xmmword ptr [rcx], xmm0
0x18001646f  mov     [rcx+10h], rax
0x180016473  test    r8d, r8d
0x180016476  jz      loc_1800165B7
0x18001647c  sub     r9d, 1
0x180016480  jz      loc_1800165A7
0x180016486  sub     r9d, 1
0x18001648a  jz      loc_18001652B
0x180016490  sub     r9d, 1
0x180016494  jz      loc_18001652B
0x18001649a  sub     r9d, 1
0x18001649e  jz      loc_1800165B7
0x1800164a4  sub     r9d, 1
0x1800164a8  jz      loc_1800165A7
0x1800164ae  sub     r9d, 1
0x1800164b2  jz      short loc_18001652B
0x1800164b4  cmp     r9d, 1
0x1800164b8  jz      short loc_18001652B
0x1800164ba  lea     r9d, [r8-140h]
0x1800164c1  cmp     r9d, 40h ; '@'
0x1800164c5  jge     short loc_180016514
0x1800164c7  mov     eax, [rdx+4]
0x1800164ca  mov     r11d, r9d
0x1800164cd  shl     r11d, 5
0x1800164d1  mov     ecx, 10h
0x1800164d6  test    cl, al
0x1800164d8  jz      short loc_1800164EE
0x1800164da  mov     edx, eax
0x1800164dc  shr     edx, 5
0x1800164df  and     edx, 3Fh
0x1800164e2  cmp     edx, r9d
0x1800164e5  jnz     short loc_1800164EE
0x1800164e7  mov     edx, 1
0x1800164ec  jmp     short loc_1800164F0
0x1800164ee  xor     edx, edx
0x1800164f0  mov     [rbx+10h], edx
0x1800164f3  mov     edx, r11d
0x1800164f6  xor     edx, eax
0x1800164f8  and     edx, 7E0h
0x1800164fe  xor     edx, eax
0x180016500  or      edx, ecx
0x180016502  lock cmpxchg [r10+4], edx
0x180016508  jnz     short loc_1800164D6
0x18001650a  cmp     dword ptr [rbx+10h], 0
0x18001650e  jnz     loc_1800165C5
0x180016514  mov     [rbx+8], r8d
0x180016518  mov     dword ptr [rbx+4], 1
0x18001651f  mov     dword ptr [rbx+0Ch], 0
0x180016526  jmp     loc_1800165C5
0x18001652b  xor     ecx, ecx
0x18001652d  sub     r8d, 2
0x180016531  jz      short loc_180016559
0x180016533  sub     r8d, 1
0x180016537  jz      short loc_180016552
0x180016539  sub     r8d, 3
0x18001653d  jz      short loc_18001654B
0x18001653f  cmp     r8d, 1
0x180016543  jnz     short loc_18001655E
0x180016545  lea     ecx, [r8+0Fh]
0x180016549  jmp     short loc_18001655E
0x18001654b  mov     ecx, 4
0x180016550  jmp     short loc_18001655E
0x180016552  mov     ecx, 8
0x180016557  jmp     short loc_18001655E
0x180016559  mov     ecx, 2
0x18001655e  mov     edx, [rdx]
0x180016560  xor     eax, eax
0x180016562  mov     r8d, ecx
0x180016565  or      r8d, edx
0x180016568  cmp     r8d, edx
0x18001656b  mov     r9d, r8d
0x18001656e  setz    al
0x180016571  or      r9d, 1
0x180016575  cmp     r8d, edx
0x180016578  mov     [rbx+10h], eax
0x18001657b  mov     eax, edx
0x18001657d  cmovz   r9d, r8d
0x180016581  lock cmpxchg [r10], r9d
0x180016586  jz      short loc_18001658C
0x180016588  mov     edx, eax
0x18001658a  jmp     short loc_180016560
0x18001658c  test    r9b, 1
0x180016590  setnz   cl
0x180016593  test    dl, 1
0x180016596  setz    al
0x180016599  test    al, cl
0x18001659b  mov     eax, 0
0x1800165a0  setnz   al
0x1800165a3  mov     [rbx], eax
0x1800165a5  jmp     short loc_1800165C5
0x1800165a7  mov     r9, rbx
0x1800165aa  mov     edx, r8d
0x1800165ad  mov     rcx, r10
0x1800165b0  call    wil_details_FeatureReporting_IncrementOpportunityInCache
0x1800165b5  jmp     short loc_1800165C5
0x1800165b7  mov     r9, rbx
0x1800165ba  mov     edx, r8d
0x1800165bd  mov     rcx, r10
0x1800165c0  call    wil_details_FeatureReporting_IncrementUsageInCache
0x1800165c5  mov     rax, rbx
0x1800165c8  add     rsp, 20h
0x1800165cc  pop     rbx
0x1800165cd  retn
```
