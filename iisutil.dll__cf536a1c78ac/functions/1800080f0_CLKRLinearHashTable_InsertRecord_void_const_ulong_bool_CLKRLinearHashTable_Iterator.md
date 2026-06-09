# CLKRLinearHashTable::_InsertRecord(void const *,ulong,bool,CLKRLinearHashTable_Iterator *)

- ea: `0x1800080f0`
- end: `0x180008466`
- name: `?_InsertRecord@CLKRLinearHashTable@@AEAA?AW4LK_RETCODE@@PEBXK_NPEAVCLKRLinearHashTable_Iterator@@@Z`
- size: `886`
- prototype: ``
- caller_count: `3`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18001b860`
- `0x18001b980`
- `0x18001ba20`

## callees

- `0x180007e60`
- `0x1800080f0`
- `0x180008d30`
- `0x180008de0`
- `0x180008f60`
- `0x18002f010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180008141`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180008360`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180008141`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180008360`

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
0x1800080f0  mov     [rsp+arg_8], rbx
0x1800080f5  mov     [rsp+arg_18], r9b
0x1800080fa  push    rbp
0x1800080fb  push    rsi
0x1800080fc  push    rdi
0x1800080fd  push    r12
0x1800080ff  push    r13
0x180008101  push    r14
0x180008103  push    r15
0x180008105  sub     rsp, 30h
0x180008109  mov     eax, [rcx+1Ch]
0x18000810c  mov     r14d, r8d
0x18000810f  mov     r13, rdx
0x180008112  mov     rdi, rcx
0x180008115  test    eax, eax
0x180008117  jnz     short loc_180008141
0x180008119  mov     r10d, [rcx+18h]
0x18000811d  test    r10w, r10w
0x180008121  jnz     short loc_180008141
0x180008123  lea     ecx, [r10+10000h]
0x18000812a  mov     eax, r10d
0x18000812d  or      ecx, 0FFFFh
0x180008133  lock cmpxchg [rdi+18h], ecx
0x180008138  cmp     r10d, eax
0x18000813b  jz      loc_180008360
0x180008141  call    cs:__imp_GetCurrentThreadId
0x180008148  nop     dword ptr [rax+rax+00h]
0x18000814d  mov     ecx, [rdi+1Ch]
0x180008150  and     eax, 0FFFFFFFCh
0x180008153  and     ecx, 0FFFFFFFCh
0x180008156  cmp     ecx, eax
0x180008158  jz      loc_180008422
0x18000815e  lea     rcx, [rdi+18h]; this
0x180008162  call    ?_WriteLockSpin@CReaderWriterLock3@@AEAAXXZ; CReaderWriterLock3::_WriteLockSpin(void)
0x180008167  mov     ebp, r14d
0x18000816a  and     ebp, [rdi+58h]
0x18000816d  cmp     ebp, [rdi+60h]
0x180008170  jnb     short loc_180008178
0x180008172  mov     ebp, [rdi+5Ch]
0x180008175  and     ebp, r14d
0x180008178  mov     ecx, [rdi+44h]
0x18000817b  mov     edx, [rdi+4Ch]
0x18000817e  mov     r8d, ebp
0x180008181  shr     r8, cl
0x180008184  mov     rcx, [rdi+68h]
0x180008188  mov     eax, ebp
0x18000818a  and     rdx, rax
0x18000818d  shl     rdx, 6
0x180008191  mov     rbx, [rcx+r8*8]
0x180008195  add     rbx, rdx
0x180008198  mov     edx, [rbx]
0x18000819a  test    dx, dx
0x18000819d  jnz     short loc_1800081B5
0x18000819f  lea     ecx, [rdx+10000h]
0x1800081a5  mov     eax, edx
0x1800081a7  or      ecx, 0FFFFh
0x1800081ad  lock cmpxchg [rbx], ecx
0x1800081b1  cmp     edx, eax
0x1800081b3  jz      short loc_1800081D5
0x1800081b5  mov     edx, [rbx]
0x1800081b7  mov     eax, edx
0x1800081b9  lea     ecx, [rdx+10000h]
0x1800081bf  lock cmpxchg [rbx], ecx
0x1800081c3  cmp     edx, eax
0x1800081c5  jnz     loc_18000837A
0x1800081cb  mov     dl, 1; bool
0x1800081cd  mov     rcx, rbx; this
0x1800081d0  call    ?_LockSpin@CReaderWriterLock2@@AEAAX_N@Z; CReaderWriterLock2::_LockSpin(bool)
0x1800081d5  mov     eax, [rdi+1Ch]
0x1800081d8  dec     eax
0x1800081da  test    al, 3
0x1800081dc  jz      loc_180008339
0x1800081e2  xchg    eax, [rdi+1Ch]
0x1800081e5  mov     rax, [rdi+20h]
0x1800081e9  xor     r12d, r12d
0x1800081ec  mov     rcx, r13
0x1800081ef  mov     [rsp+68h+arg_10], r12b
0x1800081f7  mov     [rsp+68h+arg_0], 0FFFFFFFFh
0x1800081ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008204  mov     [rsp+68h+var_48], rax
0x180008209  lea     rsi, [rbx+8]
0x18000820d  xor     r15d, r15d
0x180008210  cmp     r15d, 4
0x180008214  jge     loc_18000830D
0x18000821a  movsxd  rcx, r15d
0x18000821d  mov     eax, [rsi+rcx*4]
0x180008220  cmp     eax, 1E3603Bh
0x180008225  jz      short loc_180008272
0x180008227  cmp     r14d, eax
0x18000822a  jnz     loc_180008395
0x180008230  mov     rcx, [rsi+rcx*8+18h]
0x180008235  cmp     r13, rcx
0x180008238  jz      short loc_18000825C
0x18000823a  mov     rax, [rdi+20h]
0x18000823e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008243  mov     rcx, [rsp+68h+var_48]
0x180008248  mov     rdx, rax
0x18000824b  mov     rax, [rdi+30h]
0x18000824f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008254  test    al, al
0x180008256  jz      loc_180008395
0x18000825c  cmp     [rsp+68h+arg_18], 0
0x180008264  jz      loc_180008381
0x18000826a  mov     [rsp+68h+arg_10], 1
0x180008272  mov     [rsp+68h+arg_0], r15d
0x180008277  test    rsi, rsi
0x18000827a  jz      loc_18000831D
0x180008280  xor     eax, eax
0x180008282  mov     r15d, eax
0x180008285  mov     edx, 1
0x18000828a  mov     rax, [rdi+38h]
0x18000828e  mov     rcx, r13
0x180008291  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008296  cmp     [rsp+68h+arg_10], 0
0x18000829e  movsxd  r12, [rsp+68h+arg_0]
0x1800082a3  jz      loc_18000838C
0x1800082a9  mov     rcx, [rsi+r12*8+18h]
0x1800082ae  mov     edx, 0FFFFFFFFh
0x1800082b3  mov     rax, [rdi+38h]
0x1800082b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800082bc  mov     eax, 3
0x1800082c1  mov     [rsi+r12*4], r14d
0x1800082c5  mov     rcx, r12
0x1800082c8  add     rax, rcx
0x1800082cb  mov     [rsi+rax*8], r13
0x1800082cf  mov     edx, [rbx]
0x1800082d1  mov     eax, edx
0x1800082d3  lea     ecx, [rdx-10000h]
0x1800082d9  and     ecx, 0FFFF0000h
0x1800082df  lock cmpxchg [rbx], ecx
0x1800082e3  cmp     edx, eax
0x1800082e5  jz      short loc_1800082EB
0x1800082e7  pause
0x1800082e9  jmp     short loc_1800082CF
0x1800082eb  test    r15d, r15d
0x1800082ee  jz      loc_1800083DC
0x1800082f4  mov     rbx, [rsp+68h+arg_8]
0x1800082f9  mov     eax, r15d
0x1800082fc  add     rsp, 30h
0x180008300  pop     r15
0x180008302  pop     r14
0x180008304  pop     r13
0x180008306  pop     r12
0x180008308  pop     rdi
0x180008309  pop     rsi
0x18000830a  pop     rbp
0x18000830b  retn
0x18000830d  mov     r12, rsi
0x180008310  mov     rsi, [rsi+10h]
0x180008314  test    rsi, rsi
0x180008317  jnz     loc_18000820D
0x18000831d  mov     rcx, cs:?sm_palloc@CNodeClump@@1PEAVALLOC_CACHE_HANDLER@@EA; this
0x180008324  call    ?Alloc@ALLOC_CACHE_HANDLER@@QEAAPEAXXZ; ALLOC_CACHE_HANDLER::Alloc(void)
0x180008329  mov     rsi, rax
0x18000832c  test    rax, rax
0x18000832f  jnz     short loc_18000839D
0x180008331  mov     r15d, 0FFFFFF9Eh
0x180008337  jmp     short loc_1800082CF
0x180008339  xor     eax, eax
0x18000833b  xchg    eax, [rdi+1Ch]
0x18000833e  mov     edx, [rdi+18h]
0x180008341  mov     eax, edx
0x180008343  lea     ecx, [rdx-10000h]
0x180008349  and     ecx, 0FFFF0000h
0x18000834f  lock cmpxchg [rdi+18h], ecx
0x180008354  cmp     edx, eax
0x180008356  jz      loc_1800081E5
0x18000835c  pause
0x18000835e  jmp     short loc_18000833E
0x180008360  call    cs:__imp_GetCurrentThreadId
0x180008367  nop     dword ptr [rax+rax+00h]
0x18000836c  and     eax, 0FFFFFFFCh
0x18000836f  or      eax, 1
0x180008372  xchg    eax, [rdi+1Ch]
0x180008375  jmp     loc_180008167
0x18000837a  pause
0x18000837c  jmp     loc_1800081B5
0x180008381  mov     r15d, 1
0x180008387  jmp     loc_1800082CF
0x18000838c  lock inc dword ptr [rdi+78h]
0x180008390  jmp     loc_1800082BC
0x180008395  inc     r15d
0x180008398  jmp     loc_180008210
0x18000839d  xor     eax, eax
0x18000839f  mov     [rsi+10h], rax
0x1800083a3  mov     dword ptr [rsi+0Ch], 1E3603Bh
0x1800083aa  mov     [rsi+30h], rax
0x1800083ae  mov     dword ptr [rsi+8], 1E3603Bh
0x1800083b5  mov     [rsi+28h], rax
0x1800083b9  mov     dword ptr [rsi+4], 1E3603Bh
0x1800083c0  mov     [rsi+20h], rax
0x1800083c4  mov     dword ptr [rsi], 1E3603Bh
0x1800083ca  mov     [rsi+18h], rax
0x1800083ce  mov     [r12+10h], rsi
0x1800083d3  mov     [rsp+68h+arg_0], eax
0x1800083d7  jmp     loc_180008282
0x1800083dc  mov     rax, [rsp+68h+arg_20]
0x1800083e4  test    rax, rax
0x1800083e7  jz      short loc_180008430
0x1800083e9  movsxd  rcx, [rsp+68h+arg_0]
0x1800083ee  mov     [rax], rdi
0x1800083f1  mov     [rax+8], rsi
0x1800083f5  mov     [rax+10h], ebp
0x1800083f8  mov     [rax+14h], cx
0x1800083fc  cmp     cx, 0FFFFh
0x180008400  jz      loc_1800082F4
0x180008406  mov     rax, [rdi+38h]
0x18000840a  mov     edx, 1
0x18000840f  movsx   rcx, cx
0x180008413  mov     rcx, [rsi+rcx*8+18h]
0x180008418  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000841d  jmp     loc_1800082F4
0x180008422  lock inc dword ptr [rdi+1Ch]
0x180008426  jmp     loc_180008167
0x180008430  mov     eax, [rdi+78h]
0x180008433  xorps   xmm0, xmm0
0x180008436  xorps   xmm1, xmm1
0x180008439  cvtsi2sd xmm1, rax
0x18000843e  mov     eax, [rdi+7Ch]
0x180008441  cvtsi2sd xmm0, rax
0x180008446  mulsd   xmm0, qword ptr [rdi+50h]
0x18000844b  comisd  xmm1, xmm0
0x18000844f  jbe     loc_1800082F4
0x180008455  mov     rcx, rdi
0x180008458  call    ?_Expand@CLKRLinearHashTable@@AEAA?AW4LK_RETCODE@@XZ; CLKRLinearHashTable::_Expand(void)
0x18000845d  test    eax, eax
0x18000845f  jz      short loc_180008430
0x180008461  jmp     loc_1800082F4
```
