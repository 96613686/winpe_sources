# vdbeCommit

- ea: `0x140094688`
- end: `0x140094c1c`
- name: `vdbeCommit`
- size: `1428`
- prototype: ``
- caller_count: `1`
- callee_count: `17`
- tags: `file_ops, broker_com_uri`

## callers

- `0x14007ae24`

## callees

- `0x140020730`
- `0x1400212cc`
- `0x14003e1e8`
- `0x14004d3d0`
- `0x14004d470`
- `0x140053e3c`
- `0x140062bfc`
- `0x140063aac`
- `0x140063c0c`
- `0x14007f2b8`
- `0x14008ac90`
- `0x14008b740`
- `0x14008bf00`
- `0x14008ccd0`
- `0x140092d90`
- `0x140094688`
- `0x1400a8010`

## string_xrefs

- `0x140094965`: `MJ delete: %s`

## pseudocode

```c
__int64 __fastcall vdbeCommit(__int64 *a1, __int64 a2)
{
  __int64 v2; // r15
  unsigned int v3; // ebx
  int v4; // r13d
  int v5; // r12d
  int v7; // esi
  __int64 v9; // rcx
  __int64 v10; // r14
  __int64 (__fastcall *v11)(_QWORD); // rax
  int v12; // r14d
  __int64 v13; // rbp
  __int64 v14; // rsi
  __int64 v15; // rcx
  __int64 (__fastcall *v17)(__int64); // rax
  const char *v19; // r9
  __int64 *v20; // rax
  __int64 v21; // rcx
  char v22; // r8
  int *v23; // rdx
  int i; // esi
  __int64 v25; // rax
  __int64 v26; // r14
  __int64 v27; // r13
  int v28; // esi
  __int64 v29; // rsi
  __int64 v30; // rax
  int v31; // r15d
  const char *v32; // rbp
  void (__fastcall *v33)(__int64, const char *, _QWORD); // rax
  __int64 v34; // rdx
  __int64 v35; // rsi
  int v36; // r15d
  __int64 v37; // rax
  __int64 v38; // rax
  __int64 v39; // r8
  __int64 v40; // rax
  int k; // r15d
  void (__fastcall *v42)(__int64, const char *, _QWORD); // rax
  __int64 v43; // rcx
  __int64 (__fastcall *v44)(__int64, const char *, __int64); // rax
  int m; // esi
  __int64 v46; // rcx
  __int64 v47; // rcx
  int v48; // esi
  __int64 v49; // rcx
  __int64 j; // [rsp+70h] [rbp+8h] BYREF
  int v51; // [rsp+80h] [rbp+18h] BYREF
  __int64 v52; // [rsp+88h] [rbp+20h] BYREF

  v2 = a1[73];
  v3 = 0;
  v4 = 0;
  a1[73] = 0;
  v5 = 0;
  v7 = 0;
  do
  {
    if ( v7 >= *((_DWORD *)a1 + 137) )
      break;
    v9 = *(_QWORD *)(v2 + 8LL * v7);
    v10 = *(_QWORD *)(v9 + 16);
    if ( v10 )
    {
      v11 = *(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)v10 + 120LL);
      if ( v11 )
      {
        v3 = v11(*(_QWORD *)(v9 + 16));
        sqlite3VtabImportErrmsg(a2, v10);
      }
    }
    ++v7;
  }
  while ( !v3 );
  v12 = 0;
  a1[73] = v2;
  if ( v3 )
    return v3;
  while ( v12 < *((_DWORD *)a1 + 10) )
  {
    v13 = 32LL * v12;
    v14 = *(_QWORD *)(a1[4] + v13 + 8);
    if ( v14 && *(_BYTE *)(v14 + 16) == 2 )
    {
      v5 = 1;
      if ( *(_BYTE *)(v14 + 17) )
      {
        ++*(_DWORD *)(v14 + 20);
        if ( !*(_BYTE *)(v14 + 18) )
          btreeLockCarefully(v14);
      }
      v15 = **(_QWORD **)(v14 + 8);
      if ( *(_BYTE *)(a1[4] + v13 + 16) != 1
        && *((_BYTE *)&qword_1400B22C0 + *(unsigned __int8 *)(v15 + 9))
        && !*(_BYTE *)(v15 + 16)
        && !*(_BYTE *)(v15 + 20) )
      {
        ++v4;
      }
      v3 = *(_DWORD *)(v15 + 48);
      if ( !v3 && !*(_QWORD *)(v15 + 296) )
        v3 = pager_wait_on_lock(v15, 4);
      if ( *(_BYTE *)(v14 + 17) )
      {
        if ( (*(_DWORD *)(v14 + 20))-- == 1 )
          unlockBtreeMutex(v14);
      }
    }
    ++v12;
    if ( v3 )
      return v3;
  }
  if ( v5 )
  {
    v17 = (__int64 (__fastcall *)(__int64))a1[36];
    if ( v17 )
    {
      v3 = v17(a1[35]);
      if ( v3 )
        return 531;
    }
  }
  v19 = (const char *)&dword_1400B1D54;
  v20 = *(__int64 **)(*(_QWORD *)(a1[4] + 8) + 8LL);
  v21 = *v20;
  v22 = *(_BYTE *)(*v20 + 19);
  if ( v22 || *(char **)v21 == byte_1400C5000 )
  {
    v23 = &dword_1400B1D54;
  }
  else
  {
    v23 = *(int **)(v21 + 216);
    if ( !v23 )
    {
LABEL_34:
      for ( i = 0; !v3 && i < *((_DWORD *)a1 + 10); ++i )
      {
        v47 = *(_QWORD *)(32LL * i + a1[4] + 8);
        if ( v47 )
          v3 = sqlite3BtreeCommitPhaseOne(v47, 0);
      }
      v48 = 0;
      while ( !v3 )
      {
        if ( v48 >= *((_DWORD *)a1 + 10) )
          goto LABEL_97;
        v49 = *(_QWORD *)(32LL * v48 + a1[4] + 8);
        if ( v49 )
          v3 = sqlite3BtreeCommitPhaseTwo(v49, 0);
        ++v48;
      }
      return v3;
    }
  }
  v25 = -1;
  do
    ++v25;
  while ( *((_BYTE *)v23 + v25) );
  if ( (v25 & 0x3FFFFFFF) == 0 || v4 <= 1 )
    goto LABEL_34;
  v26 = *a1;
  LODWORD(v27) = 0;
  if ( !v22 && *(char **)v21 != byte_1400C5000 )
    v19 = *(const char **)(v21 + 216);
  v52 = 0;
  v51 = 0;
  if ( v19 )
  {
    v29 = -1;
    do
      ++v29;
    while ( v19[v29] );
    v28 = v29 & 0x3FFFFFFF;
  }
  else
  {
    v28 = 0;
  }
  v30 = sqlite3MPrintf(a1, "%.4c%s%.16c", 0, v19, 0);
  if ( !v30 )
    return 7;
  v31 = 0;
  v32 = (const char *)(v30 + 4);
  while ( 1 )
  {
    LODWORD(j) = 0;
    if ( !v31 )
      goto LABEL_55;
    if ( v31 > 100 )
      break;
    if ( v31 == 1 )
      sqlite3_log(13, "MJ collide: %s", v32);
LABEL_55:
    sqlite3_randomness(4, &j);
    sqlite3_snprintf(13, &v32[v28], "-mj%06X9%02X", (unsigned int)j >> 8, (unsigned __int8)j);
    v3 = (*(__int64 (__fastcall **)(__int64, const char *, _QWORD, int *))(v26 + 56))(v26, v32, 0, &v51);
    if ( v3 )
      goto LABEL_78;
    if ( !v51 )
      goto LABEL_60;
    ++v31;
  }
  sqlite3_log(13, "MJ delete: %s", v32);
  v33 = *(void (__fastcall **)(__int64, const char *, _QWORD))(v26 + 48);
  if ( v33 )
    v33(v26, v32, 0);
LABEL_60:
  v3 = sqlite3OsOpenMalloc(v26, (_DWORD)v32, (unsigned int)&v52, 16406, 0);
  if ( v3 )
    goto LABEL_78;
  v34 = 0;
  v35 = v52;
  v36 = 0;
  for ( j = 0; v36 < *((_DWORD *)a1 + 10); ++v36 )
  {
    v37 = *(_QWORD *)(32LL * v36 + a1[4] + 8);
    if ( v37 )
    {
      if ( *(_BYTE *)(v37 + 16) == 2 )
      {
        v38 = *(_QWORD *)(v37 + 8);
        v27 = *(_QWORD *)(*(_QWORD *)v38 + 224LL);
        if ( v27 )
        {
          v39 = -1;
          do
            ++v39;
          while ( *(_BYTE *)(v39 + v27) );
          v3 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, __int64))(*(_QWORD *)v35 + 24LL))(
                 v35,
                 *(_QWORD *)(*(_QWORD *)v38 + 224LL),
                 ((unsigned int)v39 & 0x3FFFFFFF) + 1,
                 v34);
          v40 = -1;
          do
            ++v40;
          while ( *(_BYTE *)(v40 + v27) );
          LODWORD(v27) = 0;
          if ( v3 )
            goto LABEL_76;
          v34 = (v40 & 0x3FFFFFFF) + j + 1;
          j = v34;
        }
      }
    }
  }
  if ( !*(_QWORD *)v35 || ((*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v35 + 96LL))(v35) & 0x400) == 0 )
  {
    v3 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v35 + 40LL))(v35, 2);
    if ( v3 )
    {
LABEL_76:
      sqlite3OsClose(v35);
      sqlite3_free(v35);
      v42 = *(void (__fastcall **)(__int64, const char *, _QWORD))(v26 + 48);
      if ( v42 )
        v42(v26, v32, 0);
      goto LABEL_78;
    }
  }
  for ( k = v27; !v3 && k < *((_DWORD *)a1 + 10); ++k )
  {
    v43 = *(_QWORD *)(32LL * k + a1[4] + 8);
    if ( v43 )
      v3 = sqlite3BtreeCommitPhaseOne(v43, v32);
  }
  sqlite3OsClose(v35);
  sqlite3_free(v35);
  if ( v3 )
  {
LABEL_78:
    sqlite3DbFreeNN(a1);
    return v3;
  }
  v44 = *(__int64 (__fastcall **)(__int64, const char *, __int64))(v26 + 48);
  if ( v44 )
    v3 = v44(v26, v32, 1);
  else
    v3 = v27;
  sqlite3DbFreeNN(a1);
  if ( !v3 )
  {
    v3 = v27;
    if ( qword_1400C9140 )
      qword_1400C9140();
    for ( m = v27; m < *((_DWORD *)a1 + 10); ++m )
    {
      v46 = *(_QWORD *)(32LL * m + a1[4] + 8);
      if ( v46 )
        sqlite3BtreeCommitPhaseTwo(v46, 1);
    }
    if ( qword_1400C9148 )
      qword_1400C9148();
LABEL_97:
    callFinaliser(a1, 128);
  }
  return v3;
}

```

## disassembly

```asm
0x140094688  mov     [rsp+arg_8], rbx
0x14009468d  push    rbp
0x14009468e  push    rsi
0x14009468f  push    rdi
0x140094690  push    r12
0x140094692  push    r13
0x140094694  push    r14
0x140094696  push    r15
0x140094698  sub     rsp, 30h
0x14009469c  mov     r15, [rcx+248h]
0x1400946a3  xor     ebx, ebx
0x1400946a5  xor     r13d, r13d
0x1400946a8  mov     [rcx+248h], rbx
0x1400946af  xor     r12d, r12d
0x1400946b2  mov     rbp, rdx
0x1400946b5  xor     esi, esi
0x1400946b7  mov     rdi, rcx
0x1400946ba  cmp     esi, [rdi+224h]
0x1400946c0  jge     short loc_1400946F9
0x1400946c2  movsxd  rax, esi
0x1400946c5  mov     rcx, [r15+rax*8]
0x1400946c9  mov     r14, [rcx+10h]
0x1400946cd  test    r14, r14
0x1400946d0  jz      short loc_1400946F3
0x1400946d2  mov     rax, [r14]
0x1400946d5  mov     rax, [rax+78h]
0x1400946d9  test    rax, rax
0x1400946dc  jz      short loc_1400946F3
0x1400946de  mov     rcx, r14
0x1400946e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400946e6  mov     rdx, r14
0x1400946e9  mov     rcx, rbp
0x1400946ec  mov     ebx, eax
0x1400946ee  call    sqlite3VtabImportErrmsg
0x1400946f3  inc     esi
0x1400946f5  test    ebx, ebx
0x1400946f7  jz      short loc_1400946BA
0x1400946f9  xor     r14d, r14d
0x1400946fc  mov     [rdi+248h], r15
0x140094703  test    ebx, ebx
0x140094705  jnz     loc_140094BAD
0x14009470b  or      r15, 0FFFFFFFFFFFFFFFFh
0x14009470f  cmp     r14d, [rdi+28h]
0x140094713  jge     loc_1400947C6
0x140094719  mov     rax, [rdi+20h]
0x14009471d  movsxd  rbp, r14d
0x140094720  shl     rbp, 5
0x140094724  mov     rsi, [rax+rbp+8]
0x140094729  test    rsi, rsi
0x14009472c  jz      loc_1400947B6
0x140094732  cmp     byte ptr [rsi+10h], 2
0x140094736  jnz     short loc_1400947B6
0x140094738  cmp     byte ptr [rsi+11h], 0
0x14009473c  mov     r12d, 1
0x140094742  jz      short loc_140094755
0x140094744  inc     dword ptr [rsi+14h]
0x140094747  cmp     byte ptr [rsi+12h], 0
0x14009474b  jnz     short loc_140094755
0x14009474d  mov     rcx, rsi
0x140094750  call    btreeLockCarefully
0x140094755  mov     rax, [rsi+8]
0x140094759  mov     rcx, [rax]
0x14009475c  mov     rax, [rdi+20h]
0x140094760  cmp     [rax+rbp+10h], r12b
0x140094765  jz      short loc_140094787
0x140094767  movzx   eax, byte ptr [rcx+9]
0x14009476b  lea     rdx, qword_1400B22C0
0x140094772  cmp     byte ptr [rax+rdx], 0
0x140094776  jz      short loc_140094787
0x140094778  cmp     byte ptr [rcx+10h], 0
0x14009477c  jnz     short loc_140094787
0x14009477e  cmp     byte ptr [rcx+14h], 0
0x140094782  jnz     short loc_140094787
0x140094784  inc     r13d
0x140094787  mov     ebx, [rcx+30h]
0x14009478a  test    ebx, ebx
0x14009478c  jnz     short loc_1400947A2
0x14009478e  cmp     qword ptr [rcx+128h], 0
0x140094796  jnz     short loc_1400947A2
0x140094798  lea     edx, [rbx+4]
0x14009479b  call    pager_wait_on_lock
0x1400947a0  mov     ebx, eax
0x1400947a2  cmp     byte ptr [rsi+11h], 0
0x1400947a6  jz      short loc_1400947B6
0x1400947a8  add     [rsi+14h], r15d
0x1400947ac  jnz     short loc_1400947B6
0x1400947ae  mov     rcx, rsi
0x1400947b1  call    unlockBtreeMutex
0x1400947b6  inc     r14d
0x1400947b9  test    ebx, ebx
0x1400947bb  jz      loc_14009470F
0x1400947c1  jmp     loc_140094BAD
0x1400947c6  test    ebx, ebx
0x1400947c8  jnz     loc_140094BAD
0x1400947ce  test    r12d, r12d
0x1400947d1  jz      short loc_1400947FB
0x1400947d3  mov     rax, [rdi+120h]
0x1400947da  test    rax, rax
0x1400947dd  jz      short loc_1400947FB
0x1400947df  mov     rcx, [rdi+118h]
0x1400947e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400947eb  mov     ebx, eax
0x1400947ed  test    eax, eax
0x1400947ef  jz      short loc_1400947FB
0x1400947f1  mov     eax, 213h
0x1400947f6  jmp     loc_140094BAF
0x1400947fb  mov     rax, [rdi+20h]
0x1400947ff  lea     r9, dword_1400B1D54
0x140094806  lea     r10, byte_1400C5000
0x14009480d  mov     rcx, [rax+8]
0x140094811  mov     rax, [rcx+8]
0x140094815  mov     rcx, [rax]
0x140094818  mov     r8b, [rcx+13h]
0x14009481c  test    r8b, r8b
0x14009481f  jnz     short loc_140094839
0x140094821  cmp     [rcx], r10
0x140094824  jz      short loc_140094839
0x140094826  mov     rdx, [rcx+0D8h]
0x14009482d  test    rdx, rdx
0x140094830  jnz     short loc_14009483C
0x140094832  xor     esi, esi
0x140094834  jmp     loc_140094BE9
0x140094839  mov     rdx, r9
0x14009483c  mov     rax, r15
0x14009483f  inc     rax
0x140094842  cmp     byte ptr [rdx+rax], 0
0x140094846  jnz     short loc_14009483F
0x140094848  and     eax, 3FFFFFFFh
0x14009484d  jz      short loc_140094832
0x14009484f  cmp     r13d, 1
0x140094853  jle     short loc_140094832
0x140094855  mov     r14, [rdi]
0x140094858  xor     r13d, r13d
0x14009485b  test    r8b, r8b
0x14009485e  jnz     short loc_14009486C
0x140094860  cmp     [rcx], r10
0x140094863  jz      short loc_14009486C
0x140094865  mov     r9, [rcx+0D8h]
0x14009486c  mov     [rsp+68h+arg_18], r13
0x140094874  mov     [rsp+68h+arg_10], r13d
0x14009487c  test    r9, r9
0x14009487f  jnz     short loc_140094886
0x140094881  mov     esi, r13d
0x140094884  jmp     short loc_140094898
0x140094886  mov     rsi, r15
0x140094889  inc     rsi
0x14009488c  cmp     [r9+rsi], r13b
0x140094890  jnz     short loc_140094889
0x140094892  and     esi, 3FFFFFFFh
0x140094898  xor     r8d, r8d
0x14009489b  mov     [rsp+68h+var_48], r13
0x1400948a0  lea     rdx, a4cS16c; "%.4c%s%.16c"
0x1400948a7  mov     rcx, rdi
0x1400948aa  call    sqlite3MPrintf
0x1400948af  mov     rbp, rax
0x1400948b2  test    rax, rax
0x1400948b5  jnz     short loc_1400948BF
0x1400948b7  lea     eax, [rbp+7]
0x1400948ba  jmp     loc_140094BAF
0x1400948bf  mov     r12, rbp
0x1400948c2  mov     r15d, r13d
0x1400948c5  add     rbp, 4
0x1400948c9  mov     dword ptr [rsp+68h+arg_0], r13d
0x1400948ce  test    r15d, r15d
0x1400948d1  jz      short loc_1400948F6
0x1400948d3  cmp     r15d, 64h ; 'd'
0x1400948d7  jg      loc_140094962
0x1400948dd  cmp     r15d, 1
0x1400948e1  jnz     short loc_1400948F6
0x1400948e3  mov     r8, rbp
0x1400948e6  lea     rdx, aMjCollideS; "MJ collide: %s"
0x1400948ed  lea     ecx, [r15+0Ch]
0x1400948f1  call    sqlite3_log
0x1400948f6  lea     rdx, [rsp+68h+arg_0]
0x1400948fb  mov     ecx, 4
0x140094900  call    sqlite3_randomness
0x140094905  mov     r9d, dword ptr [rsp+68h+arg_0]
0x14009490a  lea     r8, aMj06x902x; "-mj%06X9%02X"
0x140094911  movzx   eax, r9b
0x140094915  mov     ecx, 0Dh
0x14009491a  mov     edx, esi
0x14009491c  shr     r9d, 8
0x140094920  add     rdx, rbp
0x140094923  mov     dword ptr [rsp+68h+var_48], eax
0x140094927  call    sqlite3_snprintf
0x14009492c  mov     rax, [r14+38h]
0x140094930  lea     r9, [rsp+68h+arg_10]
0x140094938  xor     r8d, r8d
0x14009493b  mov     rdx, rbp
0x14009493e  mov     rcx, r14
0x140094941  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140094946  mov     ebx, eax
0x140094948  test    eax, eax
0x14009494a  jnz     loc_140094ACE
0x140094950  cmp     [rsp+68h+arg_10], r13d
0x140094958  jz      short loc_140094995
0x14009495a  inc     r15d
0x14009495d  jmp     loc_1400948C9
0x140094962  mov     r8, rbp
0x140094965  lea     rdx, aMjDeleteS; "MJ delete: %s"
0x14009496c  mov     ecx, 0Dh
0x140094971  call    sqlite3_log
0x140094976  mov     rax, [r14+30h]
0x14009497a  test    rax, rax
0x14009497d  jz      short loc_14009498D
0x14009497f  xor     r8d, r8d
0x140094982  mov     rdx, rbp
0x140094985  mov     rcx, r14
0x140094988  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14009498d  test    ebx, ebx
0x14009498f  jnz     loc_140094ACE
0x140094995  mov     r9d, 4016h
0x14009499b  mov     [rsp+68h+var_48], r13
0x1400949a0  lea     r8, [rsp+68h+arg_18]
0x1400949a8  mov     rdx, rbp
0x1400949ab  mov     rcx, r14
0x1400949ae  call    sqlite3OsOpenMalloc
0x1400949b3  mov     ebx, eax
0x1400949b5  test    eax, eax
0x1400949b7  jnz     loc_140094ACE
0x1400949bd  mov     rdx, r13
0x1400949c0  mov     rsi, [rsp+68h+arg_18]
0x1400949c8  mov     r15d, r13d
0x1400949cb  mov     [rsp+68h+arg_0], rdx
0x1400949d0  cmp     [rdi+28h], r13d
0x1400949d4  jle     loc_140094A6E
0x1400949da  mov     rax, [rdi+20h]
0x1400949de  movsxd  rcx, r15d
0x1400949e1  shl     rcx, 5
0x1400949e5  mov     rax, [rcx+rax+8]
0x1400949ea  test    rax, rax
0x1400949ed  jz      short loc_140094A61
0x1400949ef  cmp     byte ptr [rax+10h], 2
0x1400949f3  jnz     short loc_140094A61
0x1400949f5  mov     rax, [rax+8]
0x1400949f9  mov     rcx, [rax]
0x1400949fc  mov     r13, [rcx+0E0h]
0x140094a03  test    r13, r13
0x140094a06  jz      short loc_140094A61
0x140094a08  or      r8, 0FFFFFFFFFFFFFFFFh
0x140094a0c  inc     r8
0x140094a0f  cmp     byte ptr [r8+r13], 0
0x140094a14  jnz     short loc_140094A0C
0x140094a16  mov     rax, [rsi]
0x140094a19  and     r8d, 3FFFFFFFh
0x140094a20  mov     r9, rdx
0x140094a23  inc     r8d
0x140094a26  mov     rdx, r13
0x140094a29  mov     rcx, rsi
0x140094a2c  mov     rax, [rax+18h]
0x140094a30  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140094a35  mov     ebx, eax
0x140094a37  or      rax, 0FFFFFFFFFFFFFFFFh
0x140094a3b  inc     rax
0x140094a3e  cmp     byte ptr [rax+r13], 0
0x140094a43  jnz     short loc_140094A3B
0x140094a45  xor     r13d, r13d
0x140094a48  test    ebx, ebx
0x140094a4a  jnz     short loc_140094AA7
0x140094a4c  mov     rdx, [rsp+68h+arg_0]
0x140094a51  and     eax, 3FFFFFFFh
0x140094a56  inc     rdx
0x140094a59  add     rdx, rax
0x140094a5c  mov     [rsp+68h+arg_0], rdx
0x140094a61  inc     r15d
0x140094a64  cmp     r15d, [rdi+28h]
0x140094a68  jl      loc_1400949DA
0x140094a6e  mov     rax, [rsi]
0x140094a71  test    rax, rax
0x140094a74  jz      short loc_140094A88
0x140094a76  mov     rax, [rax+60h]
0x140094a7a  mov     rcx, rsi
0x140094a7d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140094a82  bt      eax, 0Ah
0x140094a86  jb      short loc_140094AA2
0x140094a88  mov     rax, [rsi]
0x140094a8b  mov     edx, 2
0x140094a90  mov     rcx, rsi
0x140094a93  mov     rax, [rax+28h]
0x140094a97  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140094a9c  mov     ebx, eax
0x140094a9e  test    eax, eax
0x140094aa0  jnz     short loc_140094AA7
0x140094aa2  mov     r15d, r13d
0x140094aa5  jmp     short loc_140094B06
0x140094aa7  mov     rcx, rsi
0x140094aaa  call    sqlite3OsClose
0x140094aaf  mov     rcx, rsi
0x140094ab2  call    sqlite3_free
0x140094ab7  mov     rax, [r14+30h]
0x140094abb  test    rax, rax
0x140094abe  jz      short loc_140094ACE
0x140094ac0  xor     r8d, r8d
0x140094ac3  mov     rdx, rbp
0x140094ac6  mov     rcx, r14
0x140094ac9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140094ace  mov     rdx, r12
0x140094ad1  mov     rcx, rdi
0x140094ad4  call    sqlite3DbFreeNN
0x140094ad9  jmp     loc_140094BAD
  ... truncated ...
```
