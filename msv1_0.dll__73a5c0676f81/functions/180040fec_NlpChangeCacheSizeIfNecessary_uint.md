# NlpChangeCacheSizeIfNecessary(uint)

- ea: `0x180040fec`
- end: `0x18004159d`
- name: `?NlpChangeCacheSizeIfNecessary@@YAJI@Z`
- size: `1457`
- prototype: `__int64 __fastcall(unsigned int)`
- caller_count: `2`
- callee_count: `9`
- tags: ``

## callers

- `0x1800425d0`
- `0x180043180`

## callees

- `0x180030844`
- `0x180040fec`
- `0x180041ec8`
- `0x180042fa0`
- `0x180043270`
- `0x1800432c8`
- `0x180044e50`
- `0x18005029c`
- `0x18006d010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800413c3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800413e6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800413c3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800413e6`

## pseudocode

```c
__int64 __fastcall NlpChangeCacheSizeIfNecessary(unsigned int a1)
{
  __int64 v2; // rbx
  int v4; // r12d
  struct _NLP_CTE *v5; // r15
  unsigned int v6; // edx
  struct _NLP_CTE *v7; // r8
  __int64 v8; // rcx
  struct _LIST_ENTRY *v9; // rdx
  __int128 **v10; // r8
  __int128 *v11; // rcx
  struct _LIST_ENTRY *v12; // rdx
  _QWORD *v13; // r8
  _QWORD *v14; // rcx
  unsigned int k; // r14d
  _QWORD *v16; // rdx
  char *v17; // rcx
  NTSTATUS NewCacheEntry; // r12d
  _QWORD *v19; // rax
  _QWORD *v20; // r13
  __int64 v21; // r8
  __int128 *v22; // rdx
  char *v23; // rcx
  struct _LIST_ENTRY *Flink; // r12
  __int64 v25; // r14
  __int64 v26; // r9
  char *v27; // r12
  __int64 v28; // rax
  char **v29; // rcx
  char **v30; // rax
  void **v31; // rcx
  void **v32; // rcx
  unsigned int j; // r14d
  int v34; // eax
  unsigned int v35; // r14d
  __int64 v36; // rax
  __int64 v37; // rax
  struct _NLP_CTE *v38; // rcx
  __int128 v39; // [rsp+20h] [rbp-20h] BYREF
  __int128 v40; // [rsp+30h] [rbp-10h] BYREF
  int v41; // [rsp+80h] [rbp+40h]
  char *v42; // [rsp+88h] [rbp+48h]
  int i; // [rsp+88h] [rbp+48h]
  __int64 v44; // [rsp+90h] [rbp+50h]

  v40 = 0;
  v39 = 0;
  if ( !a1 )
    MsvpReportDisabledCache();
  v2 = 50;
  if ( a1 <= 0x32 )
    v2 = a1;
  if ( HIDWORD(NlpCacheControl) == (_DWORD)v2 )
    return 0;
  v4 = HIDWORD(NlpCacheControl) < (unsigned int)v2 ? HIDWORD(NlpCacheControl) : 0;
  v41 = v4;
  v5 = (struct _NLP_CTE *)((__int64 (__fastcall *)(__int64))qword_180088390)(32LL * (unsigned int)v2);
  if ( !v5 )
    goto LABEL_8;
  if ( (unsigned int)v2 <= HIDWORD(NlpCacheControl) )
  {
    if ( (_DWORD)v2 )
    {
      v19 = (_QWORD *)((__int64 (__fastcall *)(__int64))qword_180088390)(40 * v2);
      v20 = v19;
      if ( !v19 )
      {
        ((void (__fastcall *)(struct _NLP_CTE *))qword_180088398)(NlpCteTable);
LABEL_8:
        HIDWORD(NlpCacheControl) = v4;
        return 3221225495LL;
      }
      memset_0(v19, 0, 40 * v2);
      LODWORD(v21) = 0;
      *((_QWORD *)&v40 + 1) = &v40;
      *(_QWORD *)&v40 = &v40;
      *(_QWORD *)&v39 = &v39;
      v22 = &v39;
      for ( *((_QWORD *)&v39 + 1) = &v39; ; v22 = (__int128 *)*((_QWORD *)&v39 + 1) )
      {
        if ( *(__int128 **)v22 != &v39 )
          goto LABEL_74;
        v23 = (char *)v5 + 32 * (unsigned int)v21;
        *(_QWORD *)v23 = &v39;
        *((_QWORD *)v23 + 1) = v22;
        *(_QWORD *)v22 = v23;
        *((_QWORD *)&v39 + 1) = v23;
        *((_DWORD *)v23 + 6) = v21;
        v21 = (unsigned int)(v21 + 1);
        v23[28] = 0;
        if ( (unsigned int)v21 >= (unsigned int)v2 )
          break;
      }
      Flink = NlpActiveCtes.Flink;
      v25 = 0;
      while ( Flink != &NlpActiveCtes && (unsigned int)v25 < (unsigned int)v2 )
      {
        v42 = (char *)&v20[5 * v25];
        if ( (int)NlpReadCacheEntryByIndex(
                    (unsigned int)Flink[1].Blink,
                    (struct _LOGON_CACHE_ENTRY **)v42,
                    (unsigned int *)v42 + 2) >= 0 )
        {
          v25 = (unsigned int)(v25 + 1);
          v42[32] = 1;
        }
        Flink = Flink->Flink;
      }
      v26 = 0;
      for ( i = 0; (unsigned int)v26 < (unsigned int)v25; i = v26 )
      {
        v44 = 5 * v26;
        v27 = (char *)v5 + 32 * (unsigned int)v26;
        *((_DWORD *)v27 + 4) = *(_DWORD *)(v20[5 * v26] + 32LL);
        *((_DWORD *)v27 + 5) = *(_DWORD *)(v20[5 * v26] + 36LL);
        if ( NlpWriteCacheEntry(v26, (struct _LOGON_CACHE_ENTRY *)v20[5 * v26], v20[5 * v26 + 1]) >= 0 )
        {
          v27[28] = 1;
          v28 = *(_QWORD *)v27;
          if ( *(char **)(*(_QWORD *)v27 + 8LL) != v27 )
            goto LABEL_74;
          v29 = (char **)*((_QWORD *)v27 + 1);
          if ( *v29 != v27 )
            goto LABEL_74;
          *v29 = (char *)v28;
          *(_QWORD *)(v28 + 8) = v29;
          v30 = (char **)*((_QWORD *)&v40 + 1);
          if ( **((__int128 ***)&v40 + 1) != &v40 )
            goto LABEL_74;
          *((_QWORD *)v27 + 1) = *((_QWORD *)&v40 + 1);
          *(_QWORD *)v27 = &v40;
          *v30 = v27;
          *((_QWORD *)&v40 + 1) = v27;
        }
        if ( v20[v44] )
          ((void (*)(void))qword_180088398)();
        v31 = (void **)v20[v44 + 2];
        if ( v31 )
        {
          memset_0(v31[1], 0, *(unsigned int *)v31);
          LocalFree((HLOCAL)v20[v44 + 2]);
        }
        v32 = (void **)v20[v44 + 3];
        if ( v32 )
        {
          memset_0(v32[1], 0, *(unsigned int *)v32);
          LocalFree((HLOCAL)v20[v44 + 3]);
        }
        v26 = (unsigned int)(i + 1);
      }
      ((void (__fastcall *)(_QWORD *, __int128 *, __int64))qword_180088398)(v20, v22, v21);
      while ( (unsigned int)v25 < (unsigned int)v2 )
      {
        NlpMakeNewCacheEntry(v25);
        LODWORD(v25) = v25 + 1;
      }
      v4 = v41;
    }
    else
    {
      qword_1800870E0 = (__int64)&NlpInactiveCtes;
      qword_1800870F0 = (__int64)&NlpActiveCtes;
      NlpActiveCtes.Flink = &NlpActiveCtes;
      NlpInactiveCtes.Flink = &NlpInactiveCtes;
    }
    for ( j = v2; j < HIDWORD(NlpCacheControl); ++j )
      NlpEliminateCacheEntry(j);
  }
  else
  {
    v6 = 0;
    if ( HIDWORD(NlpCacheControl) )
    {
      v7 = NlpCteTable;
      do
      {
        v8 = 32LL * v6;
        *(_DWORD *)((char *)v5 + v8 + 24) = v6++;
        *(_QWORD *)((char *)v5 + v8 + 16) = *(_QWORD *)((char *)v7 + v8 + 16);
      }
      while ( v6 < HIDWORD(NlpCacheControl) );
    }
    v9 = NlpActiveCtes.Flink;
    v10 = (__int128 **)&v40;
    *((_QWORD *)&v40 + 1) = &v40;
    *(_QWORD *)&v40 = &v40;
    if ( NlpActiveCtes.Flink != &NlpActiveCtes )
    {
      while ( *v10 == &v40 )
      {
        v11 = (__int128 *)((char *)v5 + 32 * LODWORD(v9[1].Blink));
        *(_QWORD *)v11 = &v40;
        *((_QWORD *)v11 + 1) = v10;
        *v10 = v11;
        *((_QWORD *)&v40 + 1) = v11;
        *((_BYTE *)v5 + 32 * LODWORD(v9[1].Blink) + 28) = 1;
        v9 = v9->Flink;
        if ( v9 == &NlpActiveCtes )
          goto LABEL_17;
        v10 = (__int128 **)*((_QWORD *)&v40 + 1);
      }
LABEL_74:
      __fastfail(3u);
    }
LABEL_17:
    v12 = NlpInactiveCtes.Flink;
    *((_QWORD *)&v39 + 1) = &v39;
    *(_QWORD *)&v39 = &v39;
    while ( v12 != &NlpInactiveCtes )
    {
      v13 = (_QWORD *)*((_QWORD *)&v39 + 1);
      if ( **((__int128 ***)&v39 + 1) != &v39 )
        goto LABEL_74;
      v14 = (_QWORD *)((char *)v5 + 32 * LODWORD(v12[1].Blink));
      *v14 = &v39;
      v14[1] = v13;
      *v13 = v14;
      *((_QWORD *)&v39 + 1) = v14;
      *((_BYTE *)v5 + 32 * LODWORD(v12[1].Blink) + 28) = 0;
      v12 = v12->Flink;
    }
    for ( k = HIDWORD(NlpCacheControl); k < (unsigned int)v2; ++k )
    {
      v16 = (_QWORD *)*((_QWORD *)&v39 + 1);
      if ( **((__int128 ***)&v39 + 1) != &v39 )
        goto LABEL_74;
      v17 = (char *)v5 + 32 * k;
      *(_QWORD *)v17 = &v39;
      *((_QWORD *)v17 + 1) = v16;
      *v16 = v17;
      *((_QWORD *)&v39 + 1) = v17;
      v17[28] = 0;
      *((_DWORD *)v17 + 6) = k;
      NewCacheEntry = NlpMakeNewCacheEntry(k);
      if ( NewCacheEntry < 0 )
      {
        ((void (__fastcall *)(struct _NLP_CTE *))qword_180088398)(v5);
        return (unsigned int)NewCacheEntry;
      }
    }
    v4 = v41;
  }
  HIDWORD(NlpCacheControl) = v2;
  v34 = NlpWriteCacheControl();
  v35 = v34;
  if ( !(_DWORD)v2 )
    goto LABEL_65;
  if ( v34 >= 0 )
  {
    if ( *(__int128 **)(v40 + 8) != &v40 )
      goto LABEL_74;
    NlpActiveCtes.Flink = (struct _LIST_ENTRY *)v40;
    qword_1800870F0 = (__int64)&v40;
    *(_QWORD *)(v40 + 8) = &NlpActiveCtes;
    *(_QWORD *)&v40 = &NlpActiveCtes;
    if ( (__int128 *)qword_1800870F0 != &v40 )
      goto LABEL_74;
    v36 = *((_QWORD *)&v40 + 1);
    if ( **((__int128 ***)&v40 + 1) != &v40 )
      goto LABEL_74;
    **((_QWORD **)&v40 + 1) = &NlpActiveCtes;
    qword_1800870F0 = v36;
    if ( *(__int128 **)(v39 + 8) != &v39 )
      goto LABEL_74;
    NlpInactiveCtes.Flink = (struct _LIST_ENTRY *)v39;
    qword_1800870E0 = (__int64)&v39;
    *(_QWORD *)(v39 + 8) = &NlpInactiveCtes;
    *(_QWORD *)&v39 = &NlpInactiveCtes;
    if ( (__int128 *)qword_1800870E0 != &v39 )
      goto LABEL_74;
    v37 = *((_QWORD *)&v39 + 1);
    if ( **((__int128 ***)&v39 + 1) != &v39 )
      goto LABEL_74;
    v38 = NlpCteTable;
    **((_QWORD **)&v39 + 1) = &NlpInactiveCtes;
    qword_1800870E0 = v37;
    ((void (__fastcall *)(struct _NLP_CTE *))qword_180088398)(v38);
    NlpCteTable = v5;
  }
  else
  {
    ((void (__fastcall *)(struct _NLP_CTE *))qword_180088398)(v5);
    HIDWORD(NlpCacheControl) = v4;
    if ( !v4 )
    {
LABEL_65:
      NlpInactiveCtes.Flink = &NlpInactiveCtes;
      qword_1800870E0 = (__int64)&NlpInactiveCtes;
      NlpActiveCtes.Flink = &NlpActiveCtes;
      qword_1800870F0 = (__int64)&NlpActiveCtes;
    }
  }
  return v35;
}

```

## disassembly

```asm
0x180040fec  mov     [rsp-38h+arg_18], rbx
0x180040ff1  push    rbp
0x180040ff2  push    rsi
0x180040ff3  push    rdi
0x180040ff4  push    r12
0x180040ff6  push    r13
0x180040ff8  push    r14
0x180040ffa  push    r15
0x180040ffc  mov     rbp, rsp
0x180040fff  sub     rsp, 40h
0x180041003  xorps   xmm0, xmm0
0x180041006  xorps   xmm1, xmm1
0x180041009  mov     edi, ecx
0x18004100b  movups  [rbp+var_10], xmm0
0x18004100f  movups  [rbp+var_20], xmm1
0x180041013  test    ecx, ecx
0x180041015  jnz     short loc_18004101C
0x180041017  call    MsvpReportDisabledCache
0x18004101c  mov     eax, dword ptr cs:NlpCacheControl+4
0x180041022  mov     ebx, 32h ; '2'
0x180041027  cmp     edi, ebx
0x180041029  cmovbe  ebx, edi
0x18004102c  cmp     eax, ebx
0x18004102e  jnz     short loc_180041037
0x180041030  xor     eax, eax
0x180041032  jmp     loc_1800414BF
0x180041037  sbb     r12d, r12d
0x18004103a  mov     ecx, ebx
0x18004103c  and     r12d, eax
0x18004103f  shl     rcx, 5
0x180041043  mov     rax, cs:qword_180088390
0x18004104a  mov     [rbp+arg_0], r12d
0x18004104e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041053  mov     r15, rax
0x180041056  test    rax, rax
0x180041059  jnz     short loc_18004106C
0x18004105b  mov     dword ptr cs:NlpCacheControl+4, r12d
0x180041062  mov     eax, 0C0000017h
0x180041067  jmp     loc_1800414BF
0x18004106c  mov     eax, dword ptr cs:NlpCacheControl+4
0x180041072  cmp     ebx, eax
0x180041074  jbe     loc_1800411DF
0x18004107a  xor     edx, edx
0x18004107c  test    eax, eax
0x18004107e  jz      short loc_1800410A6
0x180041080  mov     r8, cs:?NlpCteTable@@3PEAU_NLP_CTE@@EA; _NLP_CTE * NlpCteTable
0x180041087  mov     ecx, edx
0x180041089  shl     rcx, 5
0x18004108d  mov     [r15+rcx+18h], edx
0x180041092  inc     edx
0x180041094  mov     rax, [r8+rcx+10h]
0x180041099  mov     [r15+rcx+10h], rax
0x18004109e  cmp     edx, dword ptr cs:NlpCacheControl+4
0x1800410a4  jb      short loc_180041087
0x1800410a6  mov     rdx, cs:?NlpActiveCtes@@3U_LIST_ENTRY@@A; _LIST_ENTRY NlpActiveCtes
0x1800410ad  lea     rdi, ?NlpActiveCtes@@3U_LIST_ENTRY@@A; _LIST_ENTRY NlpActiveCtes
0x1800410b4  lea     r8, [rbp+var_10]
0x1800410b8  mov     qword ptr [rbp+var_10+8], r8
0x1800410bc  lea     rax, [rbp+var_10]
0x1800410c0  mov     qword ptr [rbp+var_10], rax
0x1800410c4  cmp     rdx, rdi
0x1800410c7  jz      short loc_18004110D
0x1800410c9  lea     rax, [rbp+var_10]
0x1800410cd  cmp     [r8], rax
0x1800410d0  jnz     loc_180041596
0x1800410d6  mov     ecx, [rdx+18h]
0x1800410d9  lea     rax, [rbp+var_10]
0x1800410dd  shl     rcx, 5
0x1800410e1  add     rcx, r15
0x1800410e4  mov     [rcx], rax
0x1800410e7  mov     [rcx+8], r8
0x1800410eb  mov     [r8], rcx
0x1800410ee  mov     qword ptr [rbp+var_10+8], rcx
0x1800410f2  mov     eax, [rdx+18h]
0x1800410f5  shl     rax, 5
0x1800410f9  mov     byte ptr [rax+r15+1Ch], 1
0x1800410ff  mov     rdx, [rdx]
0x180041102  cmp     rdx, rdi
0x180041105  jz      short loc_18004110D
0x180041107  mov     r8, qword ptr [rbp+var_10+8]
0x18004110b  jmp     short loc_1800410C9
0x18004110d  mov     rdx, cs:?NlpInactiveCtes@@3U_LIST_ENTRY@@A; _LIST_ENTRY NlpInactiveCtes
0x180041114  lea     rax, [rbp+var_20]
0x180041118  mov     qword ptr [rbp+var_20+8], rax
0x18004111c  lea     rsi, ?NlpInactiveCtes@@3U_LIST_ENTRY@@A; _LIST_ENTRY NlpInactiveCtes
0x180041123  lea     rax, [rbp+var_20]
0x180041127  mov     qword ptr [rbp+var_20], rax
0x18004112b  jmp     short loc_18004116A
0x18004112d  mov     r8, qword ptr [rbp+var_20+8]
0x180041131  lea     rax, [rbp+var_20]
0x180041135  cmp     [r8], rax
0x180041138  jnz     loc_180041596
0x18004113e  mov     ecx, [rdx+18h]
0x180041141  lea     rax, [rbp+var_20]
0x180041145  shl     rcx, 5
0x180041149  add     rcx, r15
0x18004114c  mov     [rcx], rax
0x18004114f  mov     [rcx+8], r8
0x180041153  mov     [r8], rcx
0x180041156  mov     qword ptr [rbp+var_20+8], rcx
0x18004115a  mov     eax, [rdx+18h]
0x18004115d  shl     rax, 5
0x180041161  mov     byte ptr [rax+r15+1Ch], 0
0x180041167  mov     rdx, [rdx]
0x18004116a  cmp     rdx, rsi
0x18004116d  jnz     short loc_18004112D
0x18004116f  mov     r14d, dword ptr cs:NlpCacheControl+4
0x180041176  cmp     r14d, ebx
0x180041179  jnb     loc_18004146B
0x18004117f  mov     rdx, qword ptr [rbp+var_20+8]
0x180041183  lea     rax, [rbp+var_20]
0x180041187  cmp     [rdx], rax
0x18004118a  jnz     loc_180041596
0x180041190  lea     rax, [rbp+var_20]
0x180041194  mov     ecx, r14d
0x180041197  shl     rcx, 5
0x18004119b  add     rcx, r15
0x18004119e  mov     [rcx], rax
0x1800411a1  mov     [rcx+8], rdx
0x1800411a5  mov     [rdx], rcx
0x1800411a8  mov     qword ptr [rbp+var_20+8], rcx
0x1800411ac  mov     byte ptr [rcx+1Ch], 0
0x1800411b0  mov     [rcx+18h], r14d
0x1800411b4  mov     ecx, r14d; unsigned int
0x1800411b7  call    NlpMakeNewCacheEntry
0x1800411bc  mov     r12d, eax
0x1800411bf  test    eax, eax
0x1800411c1  js      short loc_1800411C8
0x1800411c3  inc     r14d
0x1800411c6  jmp     short loc_180041176
0x1800411c8  mov     rax, cs:qword_180088398
0x1800411cf  mov     rcx, r15
0x1800411d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800411d7  mov     eax, r12d
0x1800411da  jmp     loc_1800414BF
0x1800411df  lea     rsi, ?NlpInactiveCtes@@3U_LIST_ENTRY@@A; _LIST_ENTRY NlpInactiveCtes
0x1800411e6  test    ebx, ebx
0x1800411e8  jz      loc_180041427
0x1800411ee  mov     rax, cs:qword_180088390
0x1800411f5  lea     rdi, [rbx+rbx*4]
0x1800411f9  shl     rdi, 3
0x1800411fd  mov     rcx, rdi
0x180041200  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041205  mov     r13, rax
0x180041208  test    rax, rax
0x18004120b  jnz     short loc_180041225
0x18004120d  mov     rcx, cs:?NlpCteTable@@3PEAU_NLP_CTE@@EA; _NLP_CTE * NlpCteTable
0x180041214  mov     rax, cs:qword_180088398
0x18004121b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041220  jmp     loc_18004105B
0x180041225  mov     r8, rdi; Size
0x180041228  xor     edx, edx; Val
0x18004122a  mov     rcx, r13; void *
0x18004122d  call    memset_0
0x180041232  lea     rax, [rbp+var_10]
0x180041236  xor     r8d, r8d
0x180041239  mov     qword ptr [rbp+var_10+8], rax
0x18004123d  lea     rax, [rbp+var_10]
0x180041241  mov     qword ptr [rbp+var_10], rax
0x180041245  lea     rax, [rbp+var_20]
0x180041249  mov     qword ptr [rbp+var_20], rax
0x18004124d  lea     rdx, [rbp+var_20]
0x180041251  mov     qword ptr [rbp+var_20+8], rdx
0x180041255  test    ebx, ebx
0x180041257  jz      short loc_180041298
0x180041259  lea     rax, [rbp+var_20]
0x18004125d  cmp     [rdx], rax
0x180041260  jnz     loc_180041596
0x180041266  mov     ecx, r8d
0x180041269  lea     rax, [rbp+var_20]
0x18004126d  shl     rcx, 5
0x180041271  add     rcx, r15
0x180041274  mov     [rcx], rax
0x180041277  mov     [rcx+8], rdx
0x18004127b  mov     [rdx], rcx
0x18004127e  mov     qword ptr [rbp+var_20+8], rcx
0x180041282  mov     [rcx+18h], r8d
0x180041286  inc     r8d
0x180041289  mov     byte ptr [rcx+1Ch], 0
0x18004128d  cmp     r8d, ebx
0x180041290  jnb     short loc_180041298
0x180041292  mov     rdx, qword ptr [rbp+var_20+8]
0x180041296  jmp     short loc_180041259
0x180041298  mov     r12, cs:?NlpActiveCtes@@3U_LIST_ENTRY@@A; _LIST_ENTRY NlpActiveCtes
0x18004129f  lea     rdi, ?NlpActiveCtes@@3U_LIST_ENTRY@@A; _LIST_ENTRY NlpActiveCtes
0x1800412a6  xor     r14d, r14d
0x1800412a9  jmp     short loc_1800412E7
0x1800412ab  cmp     r14d, ebx
0x1800412ae  jnb     short loc_1800412EC
0x1800412b0  lea     rcx, [r14+r14*4]
0x1800412b4  lea     rax, ds:0[rcx*8]
0x1800412bc  mov     ecx, [r12+18h]; unsigned int
0x1800412c1  add     rax, r13
0x1800412c4  mov     rdx, rax; struct _LOGON_CACHE_ENTRY **
0x1800412c7  mov     [rbp+arg_8], rax
0x1800412cb  lea     r8, [rax+8]; unsigned int *
0x1800412cf  call    ?NlpReadCacheEntryByIndex@@YAJKPEAPEAU_LOGON_CACHE_ENTRY@@PEAK@Z; NlpReadCacheEntryByIndex(ulong,_LOGON_CACHE_ENTRY * *,ulong *)
0x1800412d4  test    eax, eax
0x1800412d6  js      short loc_1800412E3
0x1800412d8  mov     rax, [rbp+arg_8]
0x1800412dc  inc     r14d
0x1800412df  mov     byte ptr [rax+20h], 1
0x1800412e3  mov     r12, [r12]
0x1800412e7  cmp     r12, rdi
0x1800412ea  jnz     short loc_1800412AB
0x1800412ec  xor     r9d, r9d
0x1800412ef  mov     dword ptr [rbp+arg_8], r9d
0x1800412f3  test    r14d, r14d
0x1800412f6  jz      loc_180041400
0x1800412fc  lea     rdx, [r9+r9*4]
0x180041300  mov     r12d, r9d
0x180041303  mov     rax, [r13+rdx*8+0]
0x180041308  mov     [rbp+arg_10], rdx
0x18004130c  shl     r12, 5
0x180041310  add     r12, r15
0x180041313  mov     ecx, [rax+20h]
0x180041316  mov     [r12+10h], ecx
0x18004131b  mov     rax, [r13+rdx*8+0]
0x180041320  mov     ecx, [rax+24h]
0x180041323  mov     [r12+14h], ecx
0x180041328  mov     ecx, r9d; unsigned int
0x18004132b  mov     r8d, [r13+rdx*8+8]; unsigned int
0x180041330  mov     rdx, [r13+rdx*8+0]; struct _LOGON_CACHE_ENTRY *
0x180041335  call    ?NlpWriteCacheEntry@@YAJKPEAU_LOGON_CACHE_ENTRY@@K@Z; NlpWriteCacheEntry(ulong,_LOGON_CACHE_ENTRY *,ulong)
0x18004133a  test    eax, eax
0x18004133c  js      short loc_18004138C
0x18004133e  mov     byte ptr [r12+1Ch], 1
0x180041344  mov     rax, [r12]
0x180041348  cmp     [rax+8], r12
0x18004134c  jnz     loc_180041596
0x180041352  mov     rcx, [r12+8]
0x180041357  cmp     [rcx], r12
0x18004135a  jnz     loc_180041596
0x180041360  mov     [rcx], rax
0x180041363  mov     [rax+8], rcx
0x180041367  lea     rcx, [rbp+var_10]
0x18004136b  mov     rax, qword ptr [rbp+var_10+8]
0x18004136f  cmp     [rax], rcx
0x180041372  jnz     loc_180041596
0x180041378  mov     [r12+8], rax
0x18004137d  lea     rcx, [rbp+var_10]
0x180041381  mov     [r12], rcx
0x180041385  mov     [rax], r12
0x180041388  mov     qword ptr [rbp+var_10+8], r12
0x18004138c  mov     r12, [rbp+arg_10]
0x180041390  mov     rcx, [r13+r12*8+0]
0x180041395  test    rcx, rcx
0x180041398  jz      short loc_1800413A6
0x18004139a  mov     rax, cs:qword_180088398
0x1800413a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800413a6  mov     rcx, [r13+r12*8+10h]
0x1800413ab  test    rcx, rcx
0x1800413ae  jz      short loc_1800413C9
0x1800413b0  mov     r8d, [rcx]; Size
0x1800413b3  xor     edx, edx; Val
0x1800413b5  mov     rcx, [rcx+8]; void *
0x1800413b9  call    memset_0
0x1800413be  mov     rcx, [r13+r12*8+10h]; hMem
0x1800413c3  call    cs:__imp_LocalFree
0x1800413c9  mov     rcx, [r13+r12*8+18h]
0x1800413ce  test    rcx, rcx
0x1800413d1  jz      short loc_1800413EC
0x1800413d3  mov     r8d, [rcx]; Size
0x1800413d6  xor     edx, edx; Val
0x1800413d8  mov     rcx, [rcx+8]; void *
0x1800413dc  call    memset_0
0x1800413e1  mov     rcx, [r13+r12*8+18h]; hMem
0x1800413e6  call    cs:__imp_LocalFree
0x1800413ec  mov     r9d, dword ptr [rbp+arg_8]
0x1800413f0  inc     r9d
0x1800413f3  mov     dword ptr [rbp+arg_8], r9d
0x1800413f7  cmp     r9d, r14d
0x1800413fa  jb      loc_1800412FC
0x180041400  mov     rax, cs:qword_180088398
0x180041407  mov     rcx, r13
0x18004140a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004140f  jmp     short loc_18004141C
0x180041411  mov     ecx, r14d; unsigned int
0x180041414  call    NlpMakeNewCacheEntry
0x180041419  inc     r14d
0x18004141c  cmp     r14d, ebx
0x18004141f  jb      short loc_180041411
0x180041421  mov     r12d, [rbp+arg_0]
0x180041425  jmp     short loc_18004144A
0x180041427  lea     rdi, ?NlpActiveCtes@@3U_LIST_ENTRY@@A; _LIST_ENTRY NlpActiveCtes
0x18004142e  mov     cs:qword_1800870E0, rsi
0x180041435  mov     cs:qword_1800870F0, rdi
0x18004143c  mov     cs:?NlpActiveCtes@@3U_LIST_ENTRY@@A, rdi; _LIST_ENTRY NlpActiveCtes
0x180041443  mov     cs:?NlpInactiveCtes@@3U_LIST_ENTRY@@A, rsi; _LIST_ENTRY NlpInactiveCtes
0x18004144a  cmp     ebx, dword ptr cs:NlpCacheControl+4
0x180041450  mov     r14d, ebx
0x180041453  jnb     short loc_18004146F
0x180041455  mov     ecx, r14d; unsigned int
0x180041458  call    ?NlpEliminateCacheEntry@@YAJK@Z; NlpEliminateCacheEntry(ulong)
0x18004145d  inc     r14d
0x180041460  cmp     r14d, dword ptr cs:NlpCacheControl+4
0x180041467  jb      short loc_180041455
0x180041469  jmp     short loc_18004146F
0x18004146b  mov     r12d, [rbp+arg_0]
0x18004146f  mov     dword ptr cs:NlpCacheControl+4, ebx
  ... truncated ...
```
