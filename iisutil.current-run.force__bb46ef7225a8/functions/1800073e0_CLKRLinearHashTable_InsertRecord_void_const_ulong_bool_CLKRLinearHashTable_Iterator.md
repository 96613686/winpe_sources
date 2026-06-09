# CLKRLinearHashTable::_InsertRecord(void const *,ulong,bool,CLKRLinearHashTable_Iterator *)

- ea: `0x1800073e0`
- end: `0x180007746`
- name: `?_InsertRecord@CLKRLinearHashTable@@AEAA?AW4LK_RETCODE@@PEBXK_NPEAVCLKRLinearHashTable_Iterator@@@Z`
- size: `870`
- prototype: ``
- caller_count: `3`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18001a990`
- `0x18001aab0`
- `0x18001ab50`

## callees

- `0x180007180`
- `0x1800073e0`
- `0x180008000`
- `0x1800080a0`
- `0x180008220`
- `0x18002d010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180007431`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180007649`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180007431`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180007649`

## pseudocode

```c
__int64 __fastcall CLKRLinearHashTable::_InsertRecord(__int64 a1, __int64 a2, int a3, char a4, __int64 a5)
{
  signed __int32 v8; // r10d
  unsigned int v9; // ebp
  volatile signed __int32 *v10; // rbx
  signed __int32 v11; // edx
  signed __int32 v12; // edx
  _QWORD *v13; // r12
  _QWORD *v14; // rsi
  int i; // r15d
  int v16; // eax
  __int64 v17; // rax
  unsigned int v18; // r15d
  signed __int32 v19; // edx
  signed __int32 v21; // edx
  __int64 v22; // [rsp+20h] [rbp-48h]
  int v23; // [rsp+70h] [rbp+8h]
  char v24; // [rsp+80h] [rbp+18h]

  if ( *(_DWORD *)(a1 + 28)
    || (v8 = *(_DWORD *)(a1 + 24), (_WORD)v8)
    || v8 != _InterlockedCompareExchange((volatile signed __int32 *)(a1 + 24), (v8 + 0x10000) | 0xFFFF, v8) )
  {
    if ( (*(_DWORD *)(a1 + 28) & 0xFFFFFFFC) == (GetCurrentThreadId() & 0xFFFFFFFC) )
      _InterlockedIncrement((volatile signed __int32 *)(a1 + 28));
    else
      CReaderWriterLock3::_WriteLockSpin((CReaderWriterLock3 *)(a1 + 24));
  }
  else
  {
    _InterlockedExchange((volatile __int32 *)(a1 + 28), GetCurrentThreadId() & 0xFFFFFFFC | 1);
  }
  v9 = *(_DWORD *)(a1 + 88) & a3;
  if ( v9 < *(_DWORD *)(a1 + 96) )
    v9 = a3 & *(_DWORD *)(a1 + 92);
  v10 = (volatile signed __int32 *)(((unsigned __int64)(v9 & *(_DWORD *)(a1 + 76)) << 6)
                                  + *(_QWORD *)(*(_QWORD *)(a1 + 104)
                                              + 8 * ((unsigned __int64)v9 >> *(_DWORD *)(a1 + 68))));
  if ( (unsigned __int16)*v10 || (v11 = *v10, v11 != _InterlockedCompareExchange(v10, (v11 + 0x10000) | 0xFFFF, v11)) )
  {
    while ( 1 )
    {
      v12 = *v10;
      if ( v12 == _InterlockedCompareExchange(v10, v12 + 0x10000, v12) )
        break;
      _mm_pause();
    }
    CReaderWriterLock2::_LockSpin((CReaderWriterLock2 *)v10, 1);
  }
  if ( ((*(_BYTE *)(a1 + 28) - 1) & 3) != 0 )
  {
    _InterlockedExchange((volatile __int32 *)(a1 + 28), *(_DWORD *)(a1 + 28) - 1);
  }
  else
  {
    _InterlockedExchange((volatile __int32 *)(a1 + 28), 0);
    while ( 1 )
    {
      v21 = *(_DWORD *)(a1 + 24);
      if ( v21 == _InterlockedCompareExchange((volatile signed __int32 *)(a1 + 24), (v21 - 0x10000) & 0xFFFF0000, v21) )
        break;
      _mm_pause();
    }
  }
  v13 = 0;
  v24 = 0;
  LOWORD(v23) = -1;
  v22 = (*(__int64 (__fastcall **)(__int64))(a1 + 32))(a2);
  v14 = v10 + 2;
LABEL_15:
  for ( i = 0; ; ++i )
  {
    if ( i >= 4 )
    {
      v13 = v14;
      v14 = (_QWORD *)v14[2];
      if ( v14 )
        goto LABEL_15;
      goto LABEL_32;
    }
    v16 = *((_DWORD *)v14 + i);
    if ( v16 == 31678523 )
      break;
    if ( a3 == v16 )
    {
      if ( a2 == v14[i + 3]
        || (v17 = (*(__int64 (**)(void))(a1 + 32))(),
            (*(unsigned __int8 (__fastcall **)(__int64, __int64))(a1 + 48))(v22, v17)) )
      {
        if ( !a4 )
        {
          v18 = 1;
          goto LABEL_27;
        }
        v24 = 1;
        break;
      }
    }
  }
  v23 = i;
  if ( v14 )
    goto LABEL_24;
LABEL_32:
  v14 = ALLOC_CACHE_HANDLER::Alloc(CNodeClump::sm_palloc);
  if ( !v14 )
  {
    v18 = -98;
    goto LABEL_27;
  }
  v14[2] = 0;
  *((_DWORD *)v14 + 3) = 31678523;
  v14[6] = 0;
  *((_DWORD *)v14 + 2) = 31678523;
  v14[5] = 0;
  *((_DWORD *)v14 + 1) = 31678523;
  v14[4] = 0;
  *(_DWORD *)v14 = 31678523;
  v14[3] = 0;
  v13[2] = v14;
  v23 = 0;
LABEL_24:
  v18 = 0;
  (*(void (__fastcall **)(__int64, __int64))(a1 + 56))(a2, 1);
  if ( v24 )
    (*(void (__fastcall **)(_QWORD, __int64))(a1 + 56))(v14[v23 + 3], 0xFFFFFFFFLL);
  else
    _InterlockedIncrement((volatile signed __int32 *)(a1 + 120));
  *((_DWORD *)v14 + v23) = a3;
  v14[v23 + 3] = a2;
LABEL_27:
  while ( 1 )
  {
    v19 = *v10;
    if ( v19 == _InterlockedCompareExchange(v10, (v19 - 0x10000) & 0xFFFF0000, v19) )
      break;
    _mm_pause();
  }
  if ( !v18 )
  {
    if ( a5 )
    {
      *(_QWORD *)a5 = a1;
      *(_QWORD *)(a5 + 8) = v14;
      *(_DWORD *)(a5 + 16) = v9;
      *(_WORD *)(a5 + 20) = v23;
      if ( (_WORD)v23 != 0xFFFF )
        (*(void (__fastcall **)(_QWORD, __int64))(a1 + 56))(v14[(__int16)v23 + 3], 1);
    }
    else
    {
      while ( (double)*(int *)(a1 + 120) > (double)*(int *)(a1 + 124) * *(double *)(a1 + 80)
           && !(unsigned int)CLKRLinearHashTable::_Expand(a1) )
        ;
    }
  }
  return v18;
}

```

## disassembly

```asm
0x1800073e0  mov     [rsp+arg_8], rbx
0x1800073e5  mov     [rsp+arg_18], r9b
0x1800073ea  push    rbp
0x1800073eb  push    rsi
0x1800073ec  push    rdi
0x1800073ed  push    r12
0x1800073ef  push    r13
0x1800073f1  push    r14
0x1800073f3  push    r15
0x1800073f5  sub     rsp, 30h
0x1800073f9  mov     eax, [rcx+1Ch]
0x1800073fc  mov     r14d, r8d
0x1800073ff  mov     r13, rdx
0x180007402  mov     rdi, rcx
0x180007405  test    eax, eax
0x180007407  jnz     short loc_180007431
0x180007409  mov     r10d, [rcx+18h]
0x18000740d  test    r10w, r10w
0x180007411  jnz     short loc_180007431
0x180007413  lea     ecx, [r10+10000h]
0x18000741a  mov     eax, r10d
0x18000741d  or      ecx, 0FFFFh
0x180007423  lock cmpxchg [rdi+18h], ecx
0x180007428  cmp     r10d, eax
0x18000742b  jz      loc_180007649
0x180007431  call    cs:__imp_GetCurrentThreadId
0x180007437  mov     ecx, [rdi+1Ch]
0x18000743a  and     eax, 0FFFFFFFCh
0x18000743d  and     ecx, 0FFFFFFFCh
0x180007440  cmp     ecx, eax
0x180007442  jz      loc_180007705
0x180007448  lea     rcx, [rdi+18h]; this
0x18000744c  call    ?_WriteLockSpin@CReaderWriterLock3@@AEAAXXZ; CReaderWriterLock3::_WriteLockSpin(void)
0x180007451  mov     ebp, r14d
0x180007454  and     ebp, [rdi+58h]
0x180007457  cmp     ebp, [rdi+60h]
0x18000745a  jnb     short loc_180007462
0x18000745c  mov     ebp, [rdi+5Ch]
0x18000745f  and     ebp, r14d
0x180007462  mov     ecx, [rdi+44h]
0x180007465  mov     edx, [rdi+4Ch]
0x180007468  mov     r8d, ebp
0x18000746b  shr     r8, cl
0x18000746e  mov     rcx, [rdi+68h]
0x180007472  mov     eax, ebp
0x180007474  and     rdx, rax
0x180007477  shl     rdx, 6
0x18000747b  mov     rbx, [rcx+r8*8]
0x18000747f  add     rbx, rdx
0x180007482  mov     edx, [rbx]
0x180007484  test    dx, dx
0x180007487  jnz     short loc_18000749F
0x180007489  lea     ecx, [rdx+10000h]
0x18000748f  mov     eax, edx
0x180007491  or      ecx, 0FFFFh
0x180007497  lock cmpxchg [rbx], ecx
0x18000749b  cmp     edx, eax
0x18000749d  jz      short loc_1800074BF
0x18000749f  mov     edx, [rbx]
0x1800074a1  mov     eax, edx
0x1800074a3  lea     ecx, [rdx+10000h]
0x1800074a9  lock cmpxchg [rbx], ecx
0x1800074ad  cmp     edx, eax
0x1800074af  jnz     loc_18000765D
0x1800074b5  mov     dl, 1; bool
0x1800074b7  mov     rcx, rbx; this
0x1800074ba  call    ?_LockSpin@CReaderWriterLock2@@AEAAX_N@Z; CReaderWriterLock2::_LockSpin(bool)
0x1800074bf  mov     eax, [rdi+1Ch]
0x1800074c2  dec     eax
0x1800074c4  test    al, 3
0x1800074c6  jz      loc_180007622
0x1800074cc  xchg    eax, [rdi+1Ch]
0x1800074cf  mov     rax, [rdi+20h]
0x1800074d3  xor     r12d, r12d
0x1800074d6  mov     rcx, r13
0x1800074d9  mov     [rsp+68h+arg_10], r12b
0x1800074e1  mov     [rsp+68h+arg_0], 0FFFFFFFFh
0x1800074e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800074ee  mov     [rsp+68h+var_48], rax
0x1800074f3  lea     rsi, [rbx+8]
0x1800074f7  xor     r15d, r15d
0x1800074fa  cmp     r15d, 4
0x1800074fe  jge     loc_1800075F6
0x180007504  movsxd  rcx, r15d
0x180007507  mov     eax, [rsi+rcx*4]
0x18000750a  cmp     eax, 1E3603Bh
0x18000750f  jz      short loc_18000755C
0x180007511  cmp     r14d, eax
0x180007514  jnz     loc_180007678
0x18000751a  mov     rcx, [rsi+rcx*8+18h]
0x18000751f  cmp     r13, rcx
0x180007522  jz      short loc_180007546
0x180007524  mov     rax, [rdi+20h]
0x180007528  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000752d  mov     rcx, [rsp+68h+var_48]
0x180007532  mov     rdx, rax
0x180007535  mov     rax, [rdi+30h]
0x180007539  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000753e  test    al, al
0x180007540  jz      loc_180007678
0x180007546  cmp     [rsp+68h+arg_18], 0
0x18000754e  jz      loc_180007664
0x180007554  mov     [rsp+68h+arg_10], 1
0x18000755c  mov     [rsp+68h+arg_0], r15d
0x180007561  test    rsi, rsi
0x180007564  jz      loc_180007606
0x18000756a  xor     eax, eax
0x18000756c  mov     r15d, eax
0x18000756f  mov     edx, 1
0x180007574  mov     rax, [rdi+38h]
0x180007578  mov     rcx, r13
0x18000757b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007580  cmp     [rsp+68h+arg_10], 0
0x180007588  movsxd  r12, [rsp+68h+arg_0]
0x18000758d  jz      loc_18000766F
0x180007593  mov     rcx, [rsi+r12*8+18h]
0x180007598  mov     edx, 0FFFFFFFFh
0x18000759d  mov     rax, [rdi+38h]
0x1800075a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800075a6  mov     eax, 3
0x1800075ab  mov     [rsi+r12*4], r14d
0x1800075af  mov     rcx, r12
0x1800075b2  add     rax, rcx
0x1800075b5  mov     [rsi+rax*8], r13
0x1800075b9  mov     edx, [rbx]
0x1800075bb  mov     eax, edx
0x1800075bd  lea     ecx, [rdx-10000h]
0x1800075c3  and     ecx, 0FFFF0000h
0x1800075c9  lock cmpxchg [rbx], ecx
0x1800075cd  cmp     edx, eax
0x1800075cf  jz      short loc_1800075D5
0x1800075d1  pause
0x1800075d3  jmp     short loc_1800075B9
0x1800075d5  test    r15d, r15d
0x1800075d8  jz      loc_1800076BF
0x1800075de  mov     rbx, [rsp+68h+arg_8]
0x1800075e3  mov     eax, r15d
0x1800075e6  add     rsp, 30h
0x1800075ea  pop     r15
0x1800075ec  pop     r14
0x1800075ee  pop     r13
0x1800075f0  pop     r12
0x1800075f2  pop     rdi
0x1800075f3  pop     rsi
0x1800075f4  pop     rbp
0x1800075f5  retn
0x1800075f6  mov     r12, rsi
0x1800075f9  mov     rsi, [rsi+10h]
0x1800075fd  test    rsi, rsi
0x180007600  jnz     loc_1800074F7
0x180007606  mov     rcx, cs:?sm_palloc@CNodeClump@@1PEAVALLOC_CACHE_HANDLER@@EA; this
0x18000760d  call    ?Alloc@ALLOC_CACHE_HANDLER@@QEAAPEAXXZ; ALLOC_CACHE_HANDLER::Alloc(void)
0x180007612  mov     rsi, rax
0x180007615  test    rax, rax
0x180007618  jnz     short loc_180007680
0x18000761a  mov     r15d, 0FFFFFF9Eh
0x180007620  jmp     short loc_1800075B9
0x180007622  xor     eax, eax
0x180007624  xchg    eax, [rdi+1Ch]
0x180007627  mov     edx, [rdi+18h]
0x18000762a  mov     eax, edx
0x18000762c  lea     ecx, [rdx-10000h]
0x180007632  and     ecx, 0FFFF0000h
0x180007638  lock cmpxchg [rdi+18h], ecx
0x18000763d  cmp     edx, eax
0x18000763f  jz      loc_1800074CF
0x180007645  pause
0x180007647  jmp     short loc_180007627
0x180007649  call    cs:__imp_GetCurrentThreadId
0x18000764f  and     eax, 0FFFFFFFCh
0x180007652  or      eax, 1
0x180007655  xchg    eax, [rdi+1Ch]
0x180007658  jmp     loc_180007451
0x18000765d  pause
0x18000765f  jmp     loc_18000749F
0x180007664  mov     r15d, 1
0x18000766a  jmp     loc_1800075B9
0x18000766f  lock inc dword ptr [rdi+78h]
0x180007673  jmp     loc_1800075A6
0x180007678  inc     r15d
0x18000767b  jmp     loc_1800074FA
0x180007680  xor     eax, eax
0x180007682  mov     [rsi+10h], rax
0x180007686  mov     dword ptr [rsi+0Ch], 1E3603Bh
0x18000768d  mov     [rsi+30h], rax
0x180007691  mov     dword ptr [rsi+8], 1E3603Bh
0x180007698  mov     [rsi+28h], rax
0x18000769c  mov     dword ptr [rsi+4], 1E3603Bh
0x1800076a3  mov     [rsi+20h], rax
0x1800076a7  mov     dword ptr [rsi], 1E3603Bh
0x1800076ad  mov     [rsi+18h], rax
0x1800076b1  mov     [r12+10h], rsi
0x1800076b6  mov     [rsp+68h+arg_0], eax
0x1800076ba  jmp     loc_18000756C
0x1800076bf  mov     rax, [rsp+68h+arg_20]
0x1800076c7  test    rax, rax
0x1800076ca  jz      short loc_180007710
0x1800076cc  movsxd  rcx, [rsp+68h+arg_0]
0x1800076d1  mov     [rax], rdi
0x1800076d4  mov     [rax+8], rsi
0x1800076d8  mov     [rax+10h], ebp
0x1800076db  mov     [rax+14h], cx
0x1800076df  cmp     cx, 0FFFFh
0x1800076e3  jz      loc_1800075DE
0x1800076e9  mov     rax, [rdi+38h]
0x1800076ed  mov     edx, 1
0x1800076f2  movsx   rcx, cx
0x1800076f6  mov     rcx, [rsi+rcx*8+18h]
0x1800076fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007700  jmp     loc_1800075DE
0x180007705  lock inc dword ptr [rdi+1Ch]
0x180007709  jmp     loc_180007451
0x180007710  mov     eax, [rdi+78h]
0x180007713  xorps   xmm0, xmm0
0x180007716  xorps   xmm1, xmm1
0x180007719  cvtsi2sd xmm1, rax
0x18000771e  mov     eax, [rdi+7Ch]
0x180007721  cvtsi2sd xmm0, rax
0x180007726  mulsd   xmm0, qword ptr [rdi+50h]
0x18000772b  comisd  xmm1, xmm0
0x18000772f  jbe     loc_1800075DE
0x180007735  mov     rcx, rdi
0x180007738  call    ?_Expand@CLKRLinearHashTable@@AEAA?AW4LK_RETCODE@@XZ; CLKRLinearHashTable::_Expand(void)
0x18000773d  test    eax, eax
0x18000773f  jz      short loc_180007710
0x180007741  jmp     loc_1800075DE
```
