# CLKRLinearHashTable::_Clear(bool)

- ea: `0x1800093e0`
- end: `0x1800096ee`
- name: `?_Clear@CLKRLinearHashTable@@AEAAX_N@Z`
- size: `782`
- prototype: `void __fastcall(CLKRLinearHashTable *__hidden this, bool)`
- caller_count: `3`
- callee_count: `10`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x180014450`
- `0x18001a0c0`
- `0x18001a110`

## callees

- `0x1800080a0`
- `0x1800087d0`
- `0x1800093e0`
- `0x180009700`
- `0x18000b250`
- `0x18000b2d0`
- `0x180016034`
- `0x180018438`
- `0x180019d6c`
- `0x18002d010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800094fe`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800094fe`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000953b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000953b`
- `api-ms-win-core-interlocked-l1-1-0!QueryDepthSList` at `0x18000951c`
- `api-ms-win-core-interlocked-l1-1-0!QueryDepthSList` at `0x18000951c`
- `api-ms-win-core-interlocked-l1-1-0!InterlockedPushEntrySList` at `0x180009688`
- `api-ms-win-core-interlocked-l1-1-0!InterlockedPushEntrySList` at `0x180009688`

## pseudocode

```c
void __fastcall CLKRLinearHashTable::_Clear(CLKRLinearHashTable *this, char a2)
{
  unsigned int v4; // r12d
  volatile signed __int32 *v5; // rsi
  signed __int32 v6; // edx
  signed __int32 v7; // edx
  struct _SLIST_ENTRY *Next; // r14
  struct _SLIST_ENTRY *v9; // rsi
  unsigned int v10; // edi
  __int64 v11; // r15
  struct _SLIST_ENTRY *v12; // rax
  struct _SLIST_ENTRY *v13; // r13
  ALLOC_CACHE_HANDLER *v14; // r15
  _QWORD *v15; // rdi
  union _SLIST_HEADER *v16; // rdi
  signed __int32 v17; // edx
  unsigned int v18; // eax
  unsigned int v19; // edi
  char *v20; // rcx
  unsigned int v21; // esi
  char *v22; // rdi
  __int64 v23; // rdx
  __int64 v24; // rax
  unsigned __int64 v25; // rdx
  int v26; // ecx
  struct _SLIST_ENTRY *v27; // r14
  ALLOC_CACHE_HANDLER *v28; // rcx
  volatile signed __int32 *v29; // [rsp+70h] [rbp+18h]

  if ( *((_DWORD *)this + 5) || a2 && !*((_DWORD *)this + 30) )
    return;
  v4 = 0;
  if ( *((_DWORD *)this + 31) )
  {
    do
    {
      v5 = (volatile signed __int32 *)(((unsigned __int64)(v4 & *((_DWORD *)this + 19)) << 6)
                                     + *(_QWORD *)(*((_QWORD *)this + 13)
                                                 + 8 * ((unsigned __int64)v4 >> *((_DWORD *)this + 17))));
      v29 = v5;
      if ( (unsigned __int16)*v5 || (v6 = *v5, v6 != _InterlockedCompareExchange(v5, (v6 + 0x10000) | 0xFFFF, v6)) )
      {
        while ( 1 )
        {
          v7 = *v5;
          if ( v7 == _InterlockedCompareExchange(v5, v7 + 0x10000, v7) )
            break;
          _mm_pause();
        }
        CReaderWriterLock2::_LockSpin((CReaderWriterLock2 *)v5, 1);
      }
      Next = (struct _SLIST_ENTRY *)(v5 + 2);
      if ( v5 != (volatile signed __int32 *)-8LL )
      {
        v9 = (struct _SLIST_ENTRY *)(v5 + 2);
        do
        {
          v10 = 0;
          do
          {
            v11 = v10;
            if ( *((_DWORD *)&Next->Next + v10) == 31678523 )
              break;
            (*((void (__fastcall **)(_QWORD, __int64))this + 7))(*((_QWORD *)&Next[1].Next + v10 + 1), 0xFFFFFFFFLL);
            *((_QWORD *)&Next[1].Next + ++v10) = 0;
            *((_DWORD *)&Next->Next + v11) = 31678523;
            --*((_DWORD *)this + 30);
          }
          while ( (int)v10 < 4 );
          v12 = Next + 1;
          v13 = Next;
          Next = Next[1].Next;
          v12->Next = 0;
          if ( v13 != v9 )
          {
            v14 = CNodeClump::sm_palloc;
            v15 = (_QWORD *)*((_QWORD *)CNodeClump::sm_palloc + 3);
            v16 = (union _SLIST_HEADER *)(v15[1] * ((unsigned __int64)GetCurrentThreadId() % v15[2]) + *v15);
            if ( QueryDepthSList(v16) < *((int *)v14 + 3) )
            {
              InterlockedPushEntrySList(v16, v13);
            }
            else
            {
              HeapFree(ALLOC_CACHE_HANDLER::sm_hHeap, 0, v13);
              _InterlockedDecrement((volatile signed __int32 *)v14 + 16);
            }
            _InterlockedIncrement((volatile signed __int32 *)v14 + 48);
          }
        }
        while ( Next );
        v5 = v29;
      }
      while ( 1 )
      {
        v17 = *v5;
        if ( v17 == _InterlockedCompareExchange(v5, (v17 - 0x10000) & 0xFFFF0000, v17) )
          break;
        _mm_pause();
      }
      v18 = *((_DWORD *)this + 31);
      ++v4;
    }
    while ( v4 < v18 );
    v19 = 0;
    if ( v18 )
    {
      while ( 1 )
      {
        v24 = *((_QWORD *)this + 13);
        v25 = (unsigned __int64)v19 >> *((_DWORD *)this + 17);
        v26 = *((_DWORD *)this + 16);
        v27 = *(struct _SLIST_ENTRY **)(v24 + 8 * v25);
        if ( v26 != 1 )
          break;
        if ( v27 )
        {
          CSmallSegment::~CSmallSegment(*(CSmallSegment **)(v24 + 8 * v25));
          v28 = CSmallSegment::sm_palloc;
LABEL_43:
          ALLOC_CACHE_HANDLER::Free(v28, v27);
        }
LABEL_36:
        *(_QWORD *)(*((_QWORD *)this + 13) + 8 * ((unsigned __int64)v19 >> *((_DWORD *)this + 17))) = 0;
        v19 += *((_DWORD *)this + 18);
        if ( v19 >= *((_DWORD *)this + 31) )
          goto LABEL_23;
      }
      if ( v26 == 3 )
      {
        if ( !v27 )
          goto LABEL_36;
        CLargeSegment::~CLargeSegment(*(CLargeSegment **)(v24 + 8 * v25));
        v28 = CLargeSegment::sm_palloc;
      }
      else
      {
        if ( !v27 )
          goto LABEL_36;
        CMediumSegment::~CMediumSegment(*(CMediumSegment **)(v24 + 8 * v25));
        v28 = CMediumSegment::sm_palloc;
      }
      goto LABEL_43;
    }
  }
LABEL_23:
  v20 = (char *)*((_QWORD *)this + 13);
  v21 = 8;
  if ( v20 )
  {
    v22 = v20 - 8;
    `vector destructor iterator'(v20, 8u, *((_QWORD *)v20 - 1), (void (*)(void *))CDirEntry::~CDirEntry);
    operator delete(v22);
  }
  *((_QWORD *)this + 13) = 0;
  *((_QWORD *)this + 14) = 0;
  *(_QWORD *)((char *)this + 92) = 3;
  *((_DWORD *)this + 31) = 0;
  *((_DWORD *)this + 22) = 1;
  if ( a2 )
  {
    v23 = *((unsigned int *)this + 16);
    if ( (_DWORD)v23 != 1 )
    {
      if ( (_DWORD)v23 == 2 )
      {
        v21 = 128;
      }
      else
      {
        v21 = 0;
        if ( (_DWORD)v23 == 3 )
          v21 = 2048;
      }
    }
    CLKRLinearHashTable::_SetSegVars(this, v23, v21);
  }
}

```

## disassembly

```asm
0x1800093e0  push    rbx
0x1800093e2  push    rbp
0x1800093e3  sub     rsp, 48h
0x1800093e7  cmp     dword ptr [rcx+14h], 0
0x1800093eb  movzx   ebp, dl
0x1800093ee  mov     rbx, rcx
0x1800093f1  jnz     loc_180009623
0x1800093f7  test    dl, dl
0x1800093f9  jnz     loc_180009693
0x1800093ff  mov     [rsp+58h+arg_8], rsi
0x180009404  mov     [rsp+58h+var_18], rdi
0x180009409  mov     [rsp+58h+var_20], r12
0x18000940e  mov     [rsp+58h+var_28], r13
0x180009413  xor     r13d, r13d
0x180009416  mov     r12d, r13d
0x180009419  cmp     [rcx+7Ch], r13d
0x18000941d  jbe     loc_1800095A2
0x180009423  mov     [rsp+58h+var_30], r14
0x180009428  mov     [rsp+58h+var_38], r15
0x18000942d  mov     ecx, [rbx+44h]
0x180009430  mov     edx, [rbx+4Ch]
0x180009433  mov     r8d, r12d
0x180009436  shr     r8, cl
0x180009439  mov     rcx, [rbx+68h]
0x18000943d  mov     eax, r12d
0x180009440  and     rdx, rax
0x180009443  shl     rdx, 6
0x180009447  mov     rsi, [rcx+r8*8]
0x18000944b  add     rsi, rdx
0x18000944e  mov     [rsp+58h+arg_10], rsi
0x180009453  mov     edx, [rsi]
0x180009455  test    dx, dx
0x180009458  jnz     short loc_180009470
0x18000945a  lea     ecx, [rdx+10000h]
0x180009460  mov     eax, edx
0x180009462  or      ecx, 0FFFFh
0x180009468  lock cmpxchg [rsi], ecx
0x18000946c  cmp     edx, eax
0x18000946e  jz      short loc_180009490
0x180009470  mov     edx, [rsi]
0x180009472  mov     eax, edx
0x180009474  lea     ecx, [rdx+10000h]
0x18000947a  lock cmpxchg [rsi], ecx
0x18000947e  cmp     edx, eax
0x180009480  jnz     loc_18000967B
0x180009486  mov     dl, 1; bool
0x180009488  mov     rcx, rsi; this
0x18000948b  call    ?_LockSpin@CReaderWriterLock2@@AEAAX_N@Z; CReaderWriterLock2::_LockSpin(bool)
0x180009490  lea     rax, [rsi+8]
0x180009494  mov     r14, rax
0x180009497  test    rax, rax
0x18000949a  jz      loc_180009562
0x1800094a0  mov     rsi, rax
0x1800094a3  mov     edi, r13d
0x1800094a6  mov     r15d, edi
0x1800094a9  cmp     dword ptr [r14+r15*4], 1E3603Bh
0x1800094b1  jz      short loc_1800094DD
0x1800094b3  mov     rcx, [r14+r15*8+18h]
0x1800094b8  mov     edx, 0FFFFFFFFh
0x1800094bd  mov     rax, [rbx+38h]
0x1800094c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800094c6  mov     [r14+r15*8+18h], r13
0x1800094cb  inc     edi
0x1800094cd  mov     dword ptr [r14+r15*4], 1E3603Bh
0x1800094d5  dec     dword ptr [rbx+78h]
0x1800094d8  cmp     edi, 4
0x1800094db  jl      short loc_1800094A6
0x1800094dd  lea     rax, [r14+10h]
0x1800094e1  mov     r13, r14
0x1800094e4  mov     r14, [rax]
0x1800094e7  mov     qword ptr [rax], 0
0x1800094ee  cmp     r13, rsi
0x1800094f1  jz      short loc_18000954E
0x1800094f3  mov     r15, cs:?sm_palloc@CNodeClump@@1PEAVALLOC_CACHE_HANDLER@@EA; ALLOC_CACHE_HANDLER * CNodeClump::sm_palloc
0x1800094fa  mov     rdi, [r15+18h]
0x1800094fe  call    cs:__imp_GetCurrentThreadId
0x180009504  mov     eax, eax
0x180009506  xor     edx, edx
0x180009508  div     qword ptr [rdi+10h]
0x18000950c  mov     ecx, edx
0x18000950e  imul    rcx, [rdi+8]
0x180009513  mov     rdi, [rdi]
0x180009516  add     rdi, rcx
0x180009519  mov     rcx, rdi; ListHead
0x18000951c  call    cs:__imp_QueryDepthSList
0x180009522  movzx   eax, ax
0x180009525  cmp     eax, [r15+0Ch]
0x180009529  jl      loc_180009682
0x18000952f  mov     rcx, cs:?sm_hHeap@ALLOC_CACHE_HANDLER@@0PEAXEA; hHeap
0x180009536  mov     r8, r13; lpMem
0x180009539  xor     edx, edx; dwFlags
0x18000953b  call    cs:__imp_HeapFree
0x180009541  lock dec dword ptr [r15+40h]
0x180009546  lock inc dword ptr [r15+0C0h]
0x18000954e  mov     r13d, 0
0x180009554  test    r14, r14
0x180009557  jnz     loc_1800094A3
0x18000955d  mov     rsi, [rsp+58h+arg_10]
0x180009562  mov     edx, [rsi]
0x180009564  mov     eax, edx
0x180009566  lea     ecx, [rdx-10000h]
0x18000956c  and     ecx, 0FFFF0000h
0x180009572  lock cmpxchg [rsi], ecx
0x180009576  cmp     edx, eax
0x180009578  jz      short loc_18000957E
0x18000957a  pause
0x18000957c  jmp     short loc_180009562
0x18000957e  mov     eax, [rbx+7Ch]
0x180009581  inc     r12d
0x180009584  cmp     r12d, eax
0x180009587  jb      loc_18000942D
0x18000958d  mov     r15, [rsp+58h+var_38]
0x180009592  mov     edi, r13d
0x180009595  test    eax, eax
0x180009597  jnz     loc_180009640
0x18000959d  mov     r14, [rsp+58h+var_30]
0x1800095a2  mov     rcx, [rbx+68h]; void *
0x1800095a6  mov     esi, 8
0x1800095ab  mov     r12, [rsp+58h+var_20]
0x1800095b0  test    rcx, rcx
0x1800095b3  jz      short loc_1800095D3
0x1800095b5  mov     r8, [rcx-8]; unsigned __int64
0x1800095b9  lea     rdi, [rcx-8]
0x1800095bd  lea     r9, ??1CDirEntry@@QEAA@XZ; void (*)(void *)
0x1800095c4  mov     edx, esi; unsigned __int64
0x1800095c6  call    ??_I@YAXPEAX_K1P6AX0@Z@Z; `vector destructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *))
0x1800095cb  mov     rcx, rdi; Block
0x1800095ce  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800095d3  mov     rdi, [rsp+58h+var_18]
0x1800095d8  mov     [rbx+68h], r13
0x1800095dc  mov     qword ptr [rbx+70h], 0
0x1800095e4  mov     qword ptr [rbx+5Ch], 3
0x1800095ec  mov     [rbx+7Ch], r13d
0x1800095f0  mov     dword ptr [rbx+58h], 1
0x1800095f7  test    bpl, bpl
0x1800095fa  jz      short loc_180009619
0x1800095fc  mov     edx, [rbx+40h]
0x1800095ff  cmp     edx, 1
0x180009602  jz      short loc_18000960E
0x180009604  cmp     edx, 2
0x180009607  jnz     short loc_18000962A
0x180009609  mov     esi, 80h
0x18000960e  mov     r8d, esi
0x180009611  mov     rcx, rbx
0x180009614  call    ?_SetSegVars@CLKRLinearHashTable@@AEAA?AW4LK_RETCODE@@W4LK_TABLESIZE@@K@Z; CLKRLinearHashTable::_SetSegVars(LK_TABLESIZE,ulong)
0x180009619  mov     rsi, [rsp+58h+arg_8]
0x18000961e  mov     r13, [rsp+58h+var_28]
0x180009623  add     rsp, 48h
0x180009627  pop     rbp
0x180009628  pop     rbx
0x180009629  retn
0x18000962a  cmp     edx, 3
0x18000962d  mov     esi, r13d
0x180009630  mov     ecx, 800h
0x180009635  cmovz   esi, ecx
0x180009638  jmp     short loc_18000960E
0x180009640  mov     ecx, [rbx+44h]
0x180009643  mov     rax, [rbx+68h]
0x180009647  mov     edx, edi
0x180009649  shr     rdx, cl
0x18000964c  mov     ecx, [rbx+40h]
0x18000964f  mov     esi, edi
0x180009651  mov     r14, [rax+rdx*8]
0x180009655  cmp     ecx, 1
0x180009658  jnz     short loc_1800096B8
0x18000965a  test    r14, r14
0x18000965d  jnz     short loc_18000969F
0x18000965f  mov     ecx, [rbx+44h]
0x180009662  mov     rax, [rbx+68h]
0x180009666  shr     rsi, cl
0x180009669  mov     [rax+rsi*8], r13
0x18000966d  add     edi, [rbx+48h]
0x180009670  cmp     edi, [rbx+7Ch]
0x180009673  jnb     loc_18000959D
0x180009679  jmp     short loc_180009640
0x18000967b  pause
0x18000967d  jmp     loc_180009470
0x180009682  mov     rdx, r13; ListEntry
0x180009685  mov     rcx, rdi; ListHead
0x180009688  call    cs:__imp_InterlockedPushEntrySList
0x18000968e  jmp     loc_180009546
0x180009693  cmp     dword ptr [rcx+78h], 0
0x180009697  jnz     loc_1800093FF
0x18000969d  jmp     short loc_180009623
0x18000969f  mov     rcx, r14; this
0x1800096a2  call    ??1CSmallSegment@@QEAA@XZ; CSmallSegment::~CSmallSegment(void)
0x1800096a7  mov     rcx, cs:?sm_palloc@CSmallSegment@@1PEAVALLOC_CACHE_HANDLER@@EA; this
0x1800096ae  mov     rdx, r14; void *
0x1800096b1  call    ?Free@ALLOC_CACHE_HANDLER@@QEAAHPEAX@Z; ALLOC_CACHE_HANDLER::Free(void *)
0x1800096b6  jmp     short loc_18000965F
0x1800096b8  sub     ecx, 2
0x1800096bb  jz      short loc_1800096D8
0x1800096bd  cmp     ecx, 1
0x1800096c0  jnz     short loc_1800096D8
0x1800096c2  test    r14, r14
0x1800096c5  jz      short loc_18000965F
0x1800096c7  mov     rcx, r14; this
0x1800096ca  call    ??1CLargeSegment@@QEAA@XZ; CLargeSegment::~CLargeSegment(void)
0x1800096cf  mov     rcx, cs:?sm_palloc@CLargeSegment@@1PEAVALLOC_CACHE_HANDLER@@EA; ALLOC_CACHE_HANDLER * CLargeSegment::sm_palloc
0x1800096d6  jmp     short loc_1800096AE
0x1800096d8  test    r14, r14
0x1800096db  jz      short loc_18000965F
0x1800096dd  mov     rcx, r14; this
0x1800096e0  call    ??1CMediumSegment@@QEAA@XZ; CMediumSegment::~CMediumSegment(void)
0x1800096e5  mov     rcx, cs:?sm_palloc@CMediumSegment@@1PEAVALLOC_CACHE_HANDLER@@EA; ALLOC_CACHE_HANDLER * CMediumSegment::sm_palloc
0x1800096ec  jmp     short loc_1800096AE
```
