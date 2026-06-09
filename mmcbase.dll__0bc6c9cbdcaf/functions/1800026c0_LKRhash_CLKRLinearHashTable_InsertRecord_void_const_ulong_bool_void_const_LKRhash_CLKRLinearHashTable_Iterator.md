# LKRhash::CLKRLinearHashTable::_InsertRecord(void const *,ulong,bool,void const * *,LKRhash::CLKRLinearHashTable_Iterator *)

- ea: `0x1800026c0`
- end: `0x1800029bf`
- name: `?_InsertRecord@CLKRLinearHashTable@LKRhash@@AEAA?AW4LK_RETCODE@2@PEBXK_NPEAPEBXPEAVCLKRLinearHashTable_Iterator@2@@Z`
- size: `767`
- prototype: ``
- caller_count: `3`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180001420`
- `0x180001c00`
- `0x180002640`

## callees

- `0x1800026c0`
- `0x1800037e0`
- `0x180006404`
- `0x180019624`
- `0x180019a34`
- `0x18001a07c`
- `0x18001d010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180002715`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180002971`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180002715`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180002971`

## pseudocode

```c
__int64 __fastcall LKRhash::CLKRLinearHashTable::_InsertRecord(__int64 a1, __int64 a2, int a3)
{
  signed __int32 v6; // r8d
  unsigned int v7; // eax
  volatile signed __int32 *v8; // rbx
  signed __int32 v9; // edx
  __int32 v10; // ecx
  struct LKRhash::CNodeClump *v11; // r15
  __int64 v12; // r12
  struct LKRhash::CNodeClump *v13; // rdi
  int i; // esi
  int v15; // eax
  unsigned int v16; // r15d
  bool j; // zf
  signed __int32 v18; // edx
  __int64 v20; // rax
  struct LKRhash::CNodeClump *NodeClump; // rax
  signed __int32 v22; // edx
  signed __int32 v23; // edx

  if ( *(_BYTE *)(a1 + 153) )
  {
    if ( *(_DWORD *)(a1 + 28)
      || (v6 = *(_DWORD *)(a1 + 24), (_WORD)v6)
      || v6 != _InterlockedCompareExchange((volatile signed __int32 *)(a1 + 24), (v6 + 0x10000) | 0xFFFF, v6) )
    {
      if ( (*(_DWORD *)(a1 + 28) & 0xFFFFFFFC) == (GetCurrentThreadId() & 0xFFFFFFFC) )
        _InterlockedExchange((volatile __int32 *)(a1 + 28), *(_DWORD *)(a1 + 28) + 1);
      else
        CReaderWriterLock3::_WriteLockSpin((CReaderWriterLock3 *)(a1 + 24));
    }
    else
    {
      _InterlockedExchange((volatile __int32 *)(a1 + 28), GetCurrentThreadId() & 0xFFFFFFFC | 1);
    }
  }
  if ( *(_DWORD *)(a1 + 20) )
  {
    LKRhash::CLKRLinearHashTable::WriteUnlock((LKRhash::CLKRLinearHashTable *)a1);
    return *(unsigned int *)(a1 + 20);
  }
  v7 = *(_DWORD *)(a1 + 88) & a3;
  if ( v7 < *(_DWORD *)(a1 + 96) )
    v7 = a3 & *(_DWORD *)(a1 + 92);
  v8 = (volatile signed __int32 *)(((unsigned __int64)(v7 & *(_DWORD *)(a1 + 76)) << 6)
                                 + *(_QWORD *)(*(_QWORD *)(a1 + 104) + 8
                                                                     * ((unsigned __int64)v7 >> *(_DWORD *)(a1 + 68))));
  if ( *(_BYTE *)(a1 + 153) )
  {
    if ( (unsigned __int16)*v8 || (v9 = *v8, v9 != _InterlockedCompareExchange(v8, (v9 + 0x10000) | 0xFFFF, v9)) )
    {
      do
        v22 = *v8;
      while ( v22 != _InterlockedCompareExchange(v8, v22 + 0x10000, v22) );
      CReaderWriterLock2::_LockSpin((CReaderWriterLock2 *)v8, 1);
    }
    if ( *(_BYTE *)(a1 + 153) )
    {
      v10 = 0;
      if ( ((*(_BYTE *)(a1 + 28) - 1) & 3) != 0 )
        v10 = *(_DWORD *)(a1 + 28) - 1;
      _InterlockedExchange((volatile __int32 *)(a1 + 28), v10);
      if ( !v10 )
      {
        _m_prefetchw((const void *)(a1 + 24));
        do
          v23 = *(_DWORD *)(a1 + 24);
        while ( v23 != _InterlockedCompareExchange(
                         (volatile signed __int32 *)(a1 + 24),
                         (v23 - 0x10000) & 0xFFFF0000,
                         v23) );
      }
    }
  }
  v11 = 0;
  v12 = (*(__int64 (__fastcall **)(__int64))(a1 + 32))(a2);
  v13 = (struct LKRhash::CNodeClump *)(v8 + 2);
LABEL_17:
  for ( i = 0; ; ++i )
  {
    if ( i >= 4 )
    {
      v11 = v13;
      v13 = (struct LKRhash::CNodeClump *)*((_QWORD *)v13 + 2);
      if ( !v13 )
        goto LABEL_35;
      goto LABEL_17;
    }
    v15 = *((_DWORD *)v13 + i);
    if ( v15 == 31678523 )
    {
      if ( !v13 )
      {
LABEL_35:
        NodeClump = LKRhash::CLKRLinearHashTable::_AllocateNodeClump((LKRhash::CLKRLinearHashTable *)a1);
        v13 = NodeClump;
        if ( !NodeClump )
        {
          v16 = -98;
          goto LABEL_22;
        }
        *((_QWORD *)v11 + 2) = NodeClump;
        i = 0;
      }
      v16 = 0;
      (*(void (__fastcall **)(__int64, __int64))(a1 + 56))(a2, 1);
      _InterlockedIncrement((volatile signed __int32 *)(a1 + 120));
      *((_DWORD *)v13 + i) = a3;
      *((_QWORD *)v13 + i + 3) = a2;
      goto LABEL_22;
    }
    if ( a3 == v15 )
    {
      v20 = (*(__int64 (__fastcall **)(_QWORD))(a1 + 32))(*((_QWORD *)v13 + i + 3));
      if ( (*(unsigned __int8 (__fastcall **)(__int64, __int64))(a1 + 48))(v12, v20) )
        break;
    }
  }
  v16 = 1;
LABEL_22:
  for ( j = *(_BYTE *)(a1 + 153) == 0; !j; j = v18 == _InterlockedCompareExchange(v8, (v18 - 0x10000) & 0xFFFF0000, v18) )
    v18 = *v8;
  if ( !v16 )
  {
    while ( (double)*(int *)(a1 + 120) > (double)*(int *)(a1 + 124) * *(double *)(a1 + 80)
         && !(unsigned int)LKRhash::CLKRLinearHashTable::_Expand(a1) )
      ;
  }
  return v16;
}

```

## disassembly

```asm
0x1800026c0  push    rbx
0x1800026c2  push    rbp
0x1800026c3  push    r13
0x1800026c5  push    r14
0x1800026c7  sub     rsp, 28h
0x1800026cb  cmp     byte ptr [rcx+99h], 0
0x1800026d2  mov     ebp, r8d
0x1800026d5  mov     r14, rdx
0x1800026d8  mov     r13, rcx
0x1800026db  jz      short loc_180002725
0x1800026dd  mov     eax, [rcx+1Ch]
0x1800026e0  test    eax, eax
0x1800026e2  jnz     loc_180002971
0x1800026e8  mov     r8d, [rcx+18h]
0x1800026ec  test    r8w, r8w
0x1800026f0  jnz     loc_180002971
0x1800026f6  lea     ecx, [r8+10000h]
0x1800026fd  mov     eax, r8d
0x180002700  or      ecx, 0FFFFh
0x180002706  lock cmpxchg [r13+18h], ecx
0x18000270c  cmp     r8d, eax
0x18000270f  jnz     loc_180002971
0x180002715  call    cs:__imp_GetCurrentThreadId
0x18000271b  and     eax, 0FFFFFFFCh
0x18000271e  or      eax, 1
0x180002721  xchg    eax, [r13+1Ch]
0x180002725  cmp     dword ptr [r13+14h], 0
0x18000272a  jnz     loc_18000285B
0x180002730  mov     [rsp+48h+arg_0], rsi
0x180002735  mov     eax, ebp
0x180002737  and     eax, [r13+58h]
0x18000273b  mov     [rsp+48h+arg_8], rdi
0x180002740  mov     [rsp+48h+arg_10], r12
0x180002745  mov     [rsp+48h+var_28], r15
0x18000274a  cmp     eax, [r13+60h]
0x18000274e  jb      loc_1800029A2
0x180002754  mov     ecx, [r13+44h]
0x180002758  mov     edx, [r13+4Ch]
0x18000275c  and     rdx, rax
0x18000275f  mov     r8d, eax
0x180002762  shr     r8, cl
0x180002765  mov     rcx, [r13+68h]
0x180002769  shl     rdx, 6
0x18000276d  mov     rbx, [rcx+r8*8]
0x180002771  add     rbx, rdx
0x180002774  cmp     byte ptr [r13+99h], 0
0x18000277c  jz      short loc_1800027CB
0x18000277e  mov     edx, [rbx]
0x180002780  test    dx, dx
0x180002783  jnz     loc_180002929
0x180002789  lea     ecx, [rdx+10000h]
0x18000278f  mov     eax, edx
0x180002791  or      ecx, 0FFFFh
0x180002797  lock cmpxchg [rbx], ecx
0x18000279b  cmp     edx, eax
0x18000279d  jnz     loc_180002929
0x1800027a3  cmp     byte ptr [r13+99h], 0
0x1800027ab  jz      short loc_1800027CB
0x1800027ad  mov     eax, [r13+1Ch]
0x1800027b1  mov     ecx, 0
0x1800027b6  dec     eax
0x1800027b8  test    al, 3
0x1800027ba  cmovnz  ecx, eax
0x1800027bd  mov     eax, ecx
0x1800027bf  xchg    eax, [r13+1Ch]
0x1800027c3  test    ecx, ecx
0x1800027c5  jz      loc_18000294A
0x1800027cb  mov     rax, [r13+20h]
0x1800027cf  xor     r15d, r15d
0x1800027d2  mov     rcx, r14
0x1800027d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800027da  mov     r12, rax
0x1800027dd  lea     rdi, [rbx+8]
0x1800027e1  xor     esi, esi
0x1800027e3  cmp     esi, 4
0x1800027e6  jge     loc_1800028FA
0x1800027ec  movsxd  rcx, esi
0x1800027ef  mov     eax, [rdi+rcx*4]
0x1800027f2  cmp     eax, 1E3603Bh
0x1800027f7  jnz     loc_1800028C2
0x1800027fd  test    rdi, rdi
0x180002800  jz      loc_18000290A
0x180002806  mov     rax, [r13+38h]
0x18000280a  xor     r15d, r15d
0x18000280d  mov     edx, 1
0x180002812  mov     rcx, r14
0x180002815  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000281a  lock inc dword ptr [r13+78h]
0x18000281f  movsxd  rax, esi
0x180002822  mov     [rdi+rax*4], ebp
0x180002825  mov     [rdi+rax*8+18h], r14
0x18000282a  mov     r12, [rsp+48h+arg_10]
0x18000282f  mov     rdi, [rsp+48h+arg_8]
0x180002834  mov     rsi, [rsp+48h+arg_0]
0x180002839  cmp     byte ptr [r13+99h], 0
0x180002841  jz      short loc_180002872
0x180002843  mov     edx, [rbx]
0x180002845  mov     eax, edx
0x180002847  lea     ecx, [rdx-10000h]
0x18000284d  and     ecx, 0FFFF0000h
0x180002853  lock cmpxchg [rbx], ecx
0x180002857  cmp     edx, eax
0x180002859  jmp     short loc_180002841
0x18000285b  mov     rcx, r13; this
0x18000285e  call    ?WriteUnlock@CLKRLinearHashTable@LKRhash@@QEBAXXZ; LKRhash::CLKRLinearHashTable::WriteUnlock(void)
0x180002863  mov     eax, [r13+14h]
0x180002867  add     rsp, 28h
0x18000286b  pop     r14
0x18000286d  pop     r13
0x18000286f  pop     rbp
0x180002870  pop     rbx
0x180002871  retn
0x180002872  test    r15d, r15d
0x180002875  jz      short loc_180002890
0x180002877  mov     eax, r15d
0x18000287a  mov     r15, [rsp+48h+var_28]
0x18000287f  add     rsp, 28h
0x180002883  pop     r14
0x180002885  pop     r13
0x180002887  pop     rbp
0x180002888  pop     rbx
0x180002889  retn
0x180002890  mov     ecx, [r13+7Ch]
0x180002894  xorps   xmm0, xmm0
0x180002897  mov     eax, [r13+78h]
0x18000289b  xorps   xmm1, xmm1
0x18000289e  cvtsi2sd xmm0, rcx
0x1800028a3  cvtsi2sd xmm1, rax
0x1800028a8  mulsd   xmm0, qword ptr [r13+50h]
0x1800028ae  comisd  xmm1, xmm0
0x1800028b2  jbe     short loc_180002877
0x1800028b4  mov     rcx, r13
0x1800028b7  call    ?_Expand@CLKRLinearHashTable@LKRhash@@AEAA?AW4LK_RETCODE@2@XZ; LKRhash::CLKRLinearHashTable::_Expand(void)
0x1800028bc  test    eax, eax
0x1800028be  jz      short loc_180002890
0x1800028c0  jmp     short loc_180002877
0x1800028c2  cmp     ebp, eax
0x1800028c4  jnz     loc_1800029AD
0x1800028ca  mov     rcx, [rdi+rcx*8+18h]
0x1800028cf  mov     rax, [r13+20h]
0x1800028d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800028d8  mov     rdx, rax
0x1800028db  mov     rcx, r12
0x1800028de  mov     rax, [r13+30h]
0x1800028e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800028e7  test    al, al
0x1800028e9  jz      loc_1800029AD
0x1800028ef  mov     r15d, 1
0x1800028f5  jmp     loc_18000282A
0x1800028fa  mov     r15, rdi
0x1800028fd  mov     rdi, [rdi+10h]
0x180002901  test    rdi, rdi
0x180002904  jnz     loc_1800027E1
0x18000290a  mov     rcx, r13; this
0x18000290d  call    ?_AllocateNodeClump@CLKRLinearHashTable@LKRhash@@AEAAQEAVCNodeClump@2@XZ; LKRhash::CLKRLinearHashTable::_AllocateNodeClump(void)
0x180002912  mov     rdi, rax
0x180002915  test    rax, rax
0x180002918  jnz     loc_1800029B4
0x18000291e  mov     r15d, 0FFFFFF9Eh
0x180002924  jmp     loc_18000282A
0x180002929  mov     edx, [rbx]
0x18000292b  mov     eax, edx
0x18000292d  lea     ecx, [rdx+10000h]
0x180002933  lock cmpxchg [rbx], ecx
0x180002937  cmp     edx, eax
0x180002939  jnz     short loc_180002929
0x18000293b  mov     dl, 1; bool
0x18000293d  mov     rcx, rbx; this
0x180002940  call    ?_LockSpin@CReaderWriterLock2@@AEAAX_N@Z; CReaderWriterLock2::_LockSpin(bool)
0x180002945  jmp     loc_1800027A3
0x18000294a  prefetchw byte ptr [r13+18h]
0x18000294f  nop
0x180002950  mov     edx, [r13+18h]
0x180002954  mov     eax, edx
0x180002956  lea     ecx, [rdx-10000h]
0x18000295c  and     ecx, 0FFFF0000h
0x180002962  lock cmpxchg [r13+18h], ecx
0x180002968  cmp     edx, eax
0x18000296a  jnz     short loc_180002950
0x18000296c  jmp     loc_1800027CB
0x180002971  call    cs:__imp_GetCurrentThreadId
0x180002977  mov     ecx, [r13+1Ch]
0x18000297b  and     eax, 0FFFFFFFCh
0x18000297e  and     ecx, 0FFFFFFFCh
0x180002981  cmp     ecx, eax
0x180002983  jnz     short loc_180002994
0x180002985  mov     eax, [r13+1Ch]
0x180002989  inc     eax
0x18000298b  xchg    eax, [r13+1Ch]
0x18000298f  jmp     loc_180002725
0x180002994  lea     rcx, [r13+18h]; this
0x180002998  call    ?_WriteLockSpin@CReaderWriterLock3@@AEAAXXZ; CReaderWriterLock3::_WriteLockSpin(void)
0x18000299d  jmp     loc_180002725
0x1800029a2  mov     eax, [r13+5Ch]
0x1800029a6  and     eax, ebp
0x1800029a8  jmp     loc_180002754
0x1800029ad  inc     esi
0x1800029af  jmp     loc_1800027E3
0x1800029b4  mov     [r15+10h], rax
0x1800029b8  xor     esi, esi
0x1800029ba  jmp     loc_180002806
```
