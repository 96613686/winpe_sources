# CLKRLinearHashTable::_Contract(void)

- ea: `0x180007750`
- end: `0x180007fed`
- name: `?_Contract@CLKRLinearHashTable@@AEAA?AW4LK_RETCODE@@XZ`
- size: `2205`
- prototype: ``
- caller_count: `3`
- callee_count: `15`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x18000a110`
- `0x18000a9d0`
- `0x180016690`

## callees

- `0x180007180`
- `0x180007750`
- `0x180008000`
- `0x1800080a0`
- `0x1800081e0`
- `0x18000869c`
- `0x1800087d0`
- `0x180008eb0`
- `0x18000b250`
- `0x18000b2d0`
- `0x180016034`
- `0x1800183f8`
- `0x180018438`
- `0x180019d6c`
- `0x18002c4c0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180007794`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800079ea`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180007c73`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180007794`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800079ea`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180007c73`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007cb0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007cb0`
- `api-ms-win-core-interlocked-l1-1-0!QueryDepthSList` at `0x180007c91`
- `api-ms-win-core-interlocked-l1-1-0!QueryDepthSList` at `0x180007c91`
- `api-ms-win-core-interlocked-l1-1-0!InterlockedPushEntrySList` at `0x180007dcf`
- `api-ms-win-core-interlocked-l1-1-0!InterlockedPushEntrySList` at `0x180007dcf`

## pseudocode

```c
__int64 __fastcall CLKRLinearHashTable::_Contract(__int64 a1)
{
  signed __int32 v2; // edx
  unsigned int v3; // edx
  int v4; // eax
  int v5; // eax
  int v6; // ecx
  unsigned __int64 v7; // rsi
  signed __int32 v8; // edx
  signed __int32 v9; // edx
  volatile signed __int32 *v10; // rdi
  signed __int32 v11; // edx
  signed __int32 v12; // edx
  _OWORD *v13; // rbx
  int v14; // r13d
  unsigned __int64 v15; // rdx
  struct _SLIST_ENTRY *Next; // r12
  volatile signed __int32 *v17; // rdx
  struct _SLIST_ENTRY *v18; // rax
  struct _SLIST_ENTRY *v19; // r14
  int v20; // ecx
  int v21; // eax
  signed __int32 v22; // edx
  int v23; // ecx
  signed __int32 v24; // edx
  signed __int32 v26; // edx
  unsigned int v27; // eax
  unsigned __int64 v28; // rdx
  __int64 v29; // rax
  unsigned __int64 v30; // rdx
  int v31; // ecx
  void *v32; // rbx
  unsigned int v33; // esi
  unsigned int v34; // esi
  __int64 v35; // rax
  bool v36; // cf
  size_t v37; // rax
  _QWORD *v38; // rax
  _OWORD *v39; // r9
  int m; // edx
  __int64 k; // r8
  struct _SLIST_ENTRY *v42; // rax
  struct _SLIST_ENTRY **v43; // rcx
  struct _SLIST_ENTRY *v44; // rcx
  signed __int32 v45; // ecx
  unsigned int v46; // edx
  signed __int32 v47; // edx
  struct _SLIST_ENTRY *v48; // rax
  ALLOC_CACHE_HANDLER *v49; // r13
  _QWORD *v50; // rbx
  union _SLIST_HEADER *v51; // rbx
  int v52; // eax
  int v53; // ecx
  int v54; // eax
  int v55; // ecx
  signed __int32 v56; // edx
  ALLOC_CACHE_HANDLER *v57; // rcx
  unsigned int j; // r8d
  __int64 v59; // rcx
  char *v60; // rcx
  char *v61; // rbx
  _QWORD *v62; // r12
  unsigned int i; // r8d
  __int64 v64; // rax
  struct _SLIST_ENTRY *v65; // rdx
  struct _SLIST_ENTRY *v66; // rax
  struct _SLIST_ENTRY *v67; // rcx
  _OWORD v68[3]; // [rsp+20h] [rbp-68h] BYREF
  __int64 v69; // [rsp+50h] [rbp-38h]

  if ( *(_DWORD *)(a1 + 28)
    || (v2 = *(_DWORD *)(a1 + 24), (_WORD)v2)
    || v2 != _InterlockedCompareExchange((volatile signed __int32 *)(a1 + 24), (v2 + 0x10000) | 0xFFFF, v2) )
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
  v3 = *(_DWORD *)(a1 + 124);
  if ( v3 <= *(_DWORD *)(a1 + 72) )
  {
    CReaderWriterLock3::WriteUnlock((CReaderWriterLock3 *)(a1 + 24));
    return 4294967198LL;
  }
  v4 = *(_DWORD *)(a1 + 96);
  if ( v4 )
  {
    v5 = v4 - 1;
  }
  else
  {
    v23 = --*(_DWORD *)(a1 + 112);
    *(_DWORD *)(a1 + 88) >>= 1;
    v5 = (1 << v23) - 1;
    *(_DWORD *)(a1 + 92) >>= 1;
  }
  v6 = *(_DWORD *)(a1 + 68);
  *(_DWORD *)(a1 + 96) = v5;
  v7 = ((unsigned __int64)(*(_DWORD *)(a1 + 76) & (v3 - 1)) << 6)
     + *(_QWORD *)(*(_QWORD *)(a1 + 104) + 8 * ((unsigned __int64)(v3 - 1) >> v6));
  if ( (unsigned __int16)*(_DWORD *)v7
    || (v8 = *(_DWORD *)v7, v8 != _InterlockedCompareExchange(
                                    (volatile signed __int32 *)v7,
                                    (v8 + 0x10000) | 0xFFFF,
                                    v8)) )
  {
    while ( 1 )
    {
      v9 = *(_DWORD *)v7;
      if ( v9 == _InterlockedCompareExchange((volatile signed __int32 *)v7, v9 + 0x10000, v9) )
        break;
      _mm_pause();
    }
    CReaderWriterLock2::_LockSpin((CReaderWriterLock2 *)v7, 1);
  }
  --*(_DWORD *)(a1 + 124);
  v10 = (volatile signed __int32 *)(((unsigned __int64)(unsigned int)(*(_DWORD *)(a1 + 76) & *(_DWORD *)(a1 + 96)) << 6)
                                  + *(_QWORD *)(*(_QWORD *)(a1 + 104)
                                              + 8
                                              * ((unsigned __int64)*(unsigned int *)(a1 + 96) >> *(_DWORD *)(a1 + 68))));
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
  v13 = (_OWORD *)(v7 + 8);
  v14 = 0;
  v15 = v7 + 8;
  if ( v7 != -8 )
  {
    do
    {
      v52 = v14 + 1;
      if ( *(_DWORD *)v15 == 31678523 )
        v52 = v14;
      v53 = v52 + 1;
      if ( *(_DWORD *)(v15 + 4) == 31678523 )
        v53 = v52;
      v14 = v53 + 1;
      if ( *(_DWORD *)(v15 + 8) == 31678523 )
        v14 = v53;
      if ( *(_DWORD *)(v15 + 12) != 31678523 )
        ++v14;
      v15 = *(_QWORD *)(v15 + 16);
    }
    while ( v15 );
  }
  Next = (struct _SLIST_ENTRY *)(v10 + 2);
  v17 = v10 + 2;
  if ( v10 != (volatile signed __int32 *)-8LL )
  {
    do
    {
      v54 = v14 - 1;
      if ( *v17 != 31678523 )
        v54 = v14;
      v55 = v54 - 1;
      if ( *((_DWORD *)v17 + 1) != 31678523 )
        v55 = v54;
      v14 = v55 - 1;
      if ( *((_DWORD *)v17 + 2) != 31678523 )
        v14 = v55;
      if ( *((_DWORD *)v17 + 3) == 31678523 )
        --v14;
      v17 = (volatile signed __int32 *)*((_QWORD *)v17 + 2);
    }
    while ( v17 );
  }
  if ( v14 <= 0 )
  {
    v19 = 0;
  }
  else
  {
    v18 = (struct _SLIST_ENTRY *)ALLOC_CACHE_HANDLER::Alloc(CNodeClump::sm_palloc);
    v19 = v18;
    if ( !v18 )
      goto LABEL_21;
    v18[1].Next = 0;
    *((_DWORD *)&v18->Next + 3) = 31678523;
    v18[3].Next = 0;
    *((_DWORD *)&v18->Next + 2) = 31678523;
    *((_QWORD *)&v18[2].Next + 1) = 0;
    HIDWORD(v18->Next) = 31678523;
    v18[2].Next = 0;
    LODWORD(v18->Next) = 31678523;
    *((_QWORD *)&v18[1].Next + 1) = 0;
    if ( v14 > 4 )
    {
      v48 = (struct _SLIST_ENTRY *)ALLOC_CACHE_HANDLER::Alloc(CNodeClump::sm_palloc);
      if ( !v48 )
      {
        v49 = CNodeClump::sm_palloc;
        v50 = (_QWORD *)*((_QWORD *)CNodeClump::sm_palloc + 3);
        v51 = (union _SLIST_HEADER *)(v50[1] * ((unsigned __int64)GetCurrentThreadId() % v50[2]) + *v50);
        if ( QueryDepthSList(v51) < *((int *)v49 + 3) )
        {
          InterlockedPushEntrySList(v51, v19);
        }
        else
        {
          HeapFree(ALLOC_CACHE_HANDLER::sm_hHeap, 0, v19);
          _InterlockedDecrement((volatile signed __int32 *)v49 + 16);
        }
        _InterlockedIncrement((volatile signed __int32 *)v49 + 48);
LABEL_21:
        v20 = *(_DWORD *)(a1 + 112);
        if ( ++*(_DWORD *)(a1 + 96) == 1 << v20 )
        {
          *(_DWORD *)(a1 + 96) = 0;
          *(_DWORD *)(a1 + 112) = v20 + 1;
          v21 = (2 * *(_DWORD *)(a1 + 88)) | 1;
          *(_DWORD *)(a1 + 88) = v21;
          *(_DWORD *)(a1 + 92) = (2 * v21) | 1;
        }
        ++*(_DWORD *)(a1 + 124);
        while ( 1 )
        {
          v22 = *(_DWORD *)v7;
          if ( v22 == _InterlockedCompareExchange((volatile signed __int32 *)v7, (v22 - 0x10000) & 0xFFFF0000, v22) )
            break;
          _mm_pause();
        }
        while ( 1 )
        {
          v24 = *v10;
          if ( v24 == _InterlockedCompareExchange(v10, (v24 - 0x10000) & 0xFFFF0000, v24) )
            break;
          _mm_pause();
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
            v56 = *(_DWORD *)(a1 + 24);
            if ( v56 == _InterlockedCompareExchange(
                          (volatile signed __int32 *)(a1 + 24),
                          (v56 - 0x10000) & 0xFFFF0000,
                          v56) )
              break;
            _mm_pause();
          }
        }
        return 4294967198LL;
      }
      v48[1].Next = 0;
      *((_DWORD *)&v48->Next + 3) = 31678523;
      v48[3].Next = 0;
      *((_DWORD *)&v48->Next + 2) = 31678523;
      *((_QWORD *)&v48[2].Next + 1) = 0;
      HIDWORD(v48->Next) = 31678523;
      v48[2].Next = 0;
      LODWORD(v48->Next) = 31678523;
      *((_QWORD *)&v48[1].Next + 1) = 0;
      v19[1].Next = v48;
    }
  }
  v68[0] = *v13;
  v68[1] = *(_OWORD *)(v7 + 24);
  v68[2] = *(_OWORD *)(v7 + 40);
  v69 = *(_QWORD *)(v7 + 56);
  *(_QWORD *)(v7 + 24) = 0;
  *(_DWORD *)(v7 + 20) = 31678523;
  *(_QWORD *)(v7 + 56) = 0;
  *(_DWORD *)(v7 + 16) = 31678523;
  *(_QWORD *)(v7 + 48) = 0;
  *(_DWORD *)(v7 + 12) = 31678523;
  *(_QWORD *)(v7 + 40) = 0;
  *(_DWORD *)v13 = 31678523;
  *(_QWORD *)(v7 + 32) = 0;
  while ( 1 )
  {
    v26 = *(_DWORD *)v7;
    if ( v26 == _InterlockedCompareExchange((volatile signed __int32 *)v7, (v26 - 0x10000) & 0xFFFF0000, v26) )
      break;
    _mm_pause();
  }
  v27 = *(_DWORD *)(a1 + 124);
  if ( (v27 & *(_DWORD *)(a1 + 76)) == 0 )
  {
    v28 = v27;
    v29 = *(_QWORD *)(a1 + 104);
    v30 = v28 >> *(_DWORD *)(a1 + 68);
    v31 = *(_DWORD *)(a1 + 64);
    v32 = *(void **)(v29 + 8 * v30);
    if ( v31 == 1 )
    {
      if ( !v32 )
      {
LABEL_43:
        *(_QWORD *)(*(_QWORD *)(a1 + 104) + 8 * ((unsigned __int64)*(unsigned int *)(a1 + 124) >> *(_DWORD *)(a1 + 68))) = 0;
        goto LABEL_44;
      }
      CSmallSegment::~CSmallSegment(*(CSmallSegment **)(v29 + 8 * v30));
      v57 = CSmallSegment::sm_palloc;
    }
    else if ( v31 == 3 )
    {
      if ( !v32 )
        goto LABEL_43;
      CLargeSegment::~CLargeSegment(*(CLargeSegment **)(v29 + 8 * v30));
      v57 = CLargeSegment::sm_palloc;
    }
    else
    {
      if ( !v32 )
        goto LABEL_43;
      CMediumSegment::~CMediumSegment(*(CMediumSegment **)(v29 + 8 * v30));
      v57 = CMediumSegment::sm_palloc;
    }
    ALLOC_CACHE_HANDLER::Free(v57, v32);
    goto LABEL_43;
  }
LABEL_44:
  v33 = *(_DWORD *)(a1 + 116);
  if ( *(_DWORD *)(a1 + 124) <= (*(_DWORD *)(a1 + 72) * v33) >> 1 && v33 > 8 )
  {
    v34 = v33 >> 1;
    v35 = 8LL * v34;
    if ( !is_mul_ok(v34, 8u) )
      v35 = -1;
    v36 = __CFADD__(v35, 8);
    v37 = v35 + 8;
    if ( v36 )
      v37 = -1;
    v38 = operator new(v37);
    if ( v38 )
    {
      v62 = v38 + 1;
      *v38 = v34;
      `vector constructor iterator'(v38 + 1, 8u, v34, (void *(*)(void *))CDirEntry::CDirEntry);
      if ( v62 )
      {
        for ( i = 0; i < v34; v62[v64] = *(_QWORD *)(8 * v64 + *(_QWORD *)(a1 + 104)) )
          v64 = i++;
        for ( j = 0; j < *(_DWORD *)(a1 + 116); *(_QWORD *)(*(_QWORD *)(a1 + 104) + 8 * v59) = 0 )
          v59 = j++;
        v60 = *(char **)(a1 + 104);
        if ( v60 )
        {
          v61 = v60 - 8;
          `vector destructor iterator'(v60, 8u, *((_QWORD *)v60 - 1), (void (*)(void *))CDirEntry::~CDirEntry);
          operator delete(v61);
        }
        *(_QWORD *)(a1 + 104) = v62;
        *(_DWORD *)(a1 + 116) = v34;
      }
      Next = (struct _SLIST_ENTRY *)(v10 + 2);
    }
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
      v47 = *(_DWORD *)(a1 + 24);
      if ( v47 == _InterlockedCompareExchange((volatile signed __int32 *)(a1 + 24), (v47 - 0x10000) & 0xFFFF0000, v47) )
        break;
      _mm_pause();
    }
  }
  v39 = v68;
LABEL_54:
  if ( Next[1].Next )
  {
    v46 = 0;
    while ( *((_DWORD *)&Next->Next + v46) != 31678523 )
    {
      if ( (int)++v46 >= 4 )
      {
        if ( v46 != 4 )
          break;
        Next = Next[1].Next;
        goto LABEL_54;
      }
    }
  }
  m = 0;
  if ( LODWORD(Next->Next) != 31678523 )
  {
    m = 1;
    if ( HIDWORD(Next->Next) != 31678523 )
    {
      m = 2;
      if ( *((_DWORD *)&Next->Next + 2) != 31678523 )
      {
        m = 3;
        if ( *((_DWORD *)&Next->Next + 3) != 31678523 )
          m = 4;
      }
    }
  }
  do
  {
    for ( k = 0; k != 4; ++k )
    {
      if ( *((_DWORD *)v39 + k) != 31678523 )
      {
        if ( m == 4 )
        {
          while ( 1 )
          {
            v65 = Next + 1;
            Next = Next[1].Next;
            if ( !Next )
              break;
            for ( m = 0; m < 4; ++m )
            {
              if ( *((_DWORD *)&Next->Next + m) == 31678523 )
                goto LABEL_137;
            }
          }
          Next = v19;
          v66 = v19 + 1;
          v67 = v19;
          v19 = v19[1].Next;
          v66->Next = 0;
          *((_DWORD *)&Next->Next + 3) = 31678523;
          Next[3].Next = 0;
          *((_DWORD *)&Next->Next + 2) = 31678523;
          *((_QWORD *)&Next[2].Next + 1) = 0;
          HIDWORD(Next->Next) = 31678523;
          Next[2].Next = 0;
          LODWORD(v67->Next) = 31678523;
          *((_QWORD *)&Next[1].Next + 1) = 0;
          v65->Next = Next;
          m = 0;
        }
LABEL_137:
        *((_DWORD *)&Next->Next + m) = *((_DWORD *)v39 + k);
        *((_QWORD *)&Next[1].Next + m + 1) = *((_QWORD *)v39 + k + 3);
        *((_DWORD *)v39 + k) = 31678523;
        *((_QWORD *)v39 + k + 3) = 0;
        do
          ++m;
        while ( m != 4 && *((_DWORD *)&Next->Next + m) != 31678523 );
      }
    }
    v42 = (struct _SLIST_ENTRY *)v39;
    v43 = (struct _SLIST_ENTRY **)(v39 + 1);
    v39 = (_OWORD *)*((_QWORD *)v39 + 2);
    if ( v42 != (struct _SLIST_ENTRY *)v68 )
    {
      *v43 = v19;
      v19 = v42;
    }
  }
  while ( v39 );
  while ( v19 )
  {
    v44 = v19;
    v19 = v19[1].Next;
    CNodeClump::operator delete(v44);
  }
  while ( 1 )
  {
    v45 = *v10;
    if ( v45 == _InterlockedCompareExchange(v10, (v45 - 0x10000) & 0xFFFF0000, v45) )
      break;
    _mm_pause();
  }
  return 0;
}

```

## disassembly

```asm
0x180007750  push    rbp
0x180007752  push    r15
0x180007754  sub     rsp, 78h
0x180007758  mov     rax, cs:__security_cookie
0x18000775f  xor     rax, rsp
0x180007762  mov     [rsp+88h+var_30], rax
0x180007767  mov     eax, [rcx+1Ch]
0x18000776a  mov     rbp, rcx
0x18000776d  test    eax, eax
0x18000776f  jnz     short loc_180007794
0x180007771  mov     edx, [rcx+18h]
0x180007774  test    dx, dx
0x180007777  jnz     short loc_180007794
0x180007779  lea     ecx, [rdx+10000h]
0x18000777f  mov     eax, edx
0x180007781  or      ecx, 0FFFFh
0x180007787  lock cmpxchg [rbp+18h], ecx
0x18000778c  cmp     edx, eax
0x18000778e  jz      loc_1800079EA
0x180007794  call    cs:__imp_GetCurrentThreadId
0x18000779a  mov     ecx, [rbp+1Ch]
0x18000779d  and     eax, 0FFFFFFFCh
0x1800077a0  and     ecx, 0FFFFFFFCh
0x1800077a3  cmp     ecx, eax
0x1800077a5  jz      loc_180007DDA
0x1800077ab  lea     rcx, [rbp+18h]; this
0x1800077af  call    ?_WriteLockSpin@CReaderWriterLock3@@AEAAXXZ; CReaderWriterLock3::_WriteLockSpin(void)
0x1800077b4  mov     edx, [rbp+7Ch]
0x1800077b7  cmp     edx, [rbp+48h]
0x1800077ba  jbe     loc_180007F04
0x1800077c0  mov     eax, [rbp+60h]
0x1800077c3  mov     [rsp+88h+arg_8], rbx
0x1800077cb  mov     [rsp+88h+arg_10], rsi
0x1800077d3  mov     [rsp+88h+arg_18], rdi
0x1800077db  mov     [rsp+88h+var_18], r12
0x1800077e0  mov     [rsp+88h+var_20], r13
0x1800077e5  test    eax, eax
0x1800077e7  jz      loc_18000795F
0x1800077ed  dec     eax
0x1800077ef  mov     ecx, [rbp+44h]
0x1800077f2  mov     [rbp+60h], eax
0x1800077f5  lea     eax, [rdx-1]
0x1800077f8  mov     r8d, eax
0x1800077fb  shr     r8, cl
0x1800077fe  mov     rcx, [rbp+68h]
0x180007802  mov     edx, eax
0x180007804  mov     eax, [rbp+4Ch]
0x180007807  and     rdx, rax
0x18000780a  mov     rsi, [rcx+r8*8]
0x18000780e  shl     rdx, 6
0x180007812  add     rsi, rdx
0x180007815  mov     edx, [rsi]
0x180007817  test    dx, dx
0x18000781a  jnz     short loc_180007832
0x18000781c  lea     ecx, [rdx+10000h]
0x180007822  mov     eax, edx
0x180007824  or      ecx, 0FFFFh
0x18000782a  lock cmpxchg [rsi], ecx
0x18000782e  cmp     edx, eax
0x180007830  jz      short loc_180007852
0x180007832  mov     edx, [rsi]
0x180007834  mov     eax, edx
0x180007836  lea     ecx, [rdx+10000h]
0x18000783c  lock cmpxchg [rsi], ecx
0x180007840  cmp     edx, eax
0x180007842  jnz     loc_180007951
0x180007848  mov     dl, 1; bool
0x18000784a  mov     rcx, rsi; this
0x18000784d  call    ?_LockSpin@CReaderWriterLock2@@AEAAX_N@Z; CReaderWriterLock2::_LockSpin(bool)
0x180007852  dec     dword ptr [rbp+7Ch]
0x180007855  mov     r8d, [rbp+60h]
0x180007859  mov     ecx, [rbp+44h]
0x18000785c  mov     edx, r8d
0x18000785f  mov     eax, [rbp+4Ch]
0x180007862  shr     rdx, cl
0x180007865  and     r8, rax
0x180007868  mov     rcx, [rbp+68h]
0x18000786c  shl     r8, 6
0x180007870  mov     rdi, [rcx+rdx*8]
0x180007874  add     rdi, r8
0x180007877  mov     edx, [rdi]
0x180007879  test    dx, dx
0x18000787c  jnz     short loc_180007894
0x18000787e  lea     ecx, [rdx+10000h]
0x180007884  mov     eax, edx
0x180007886  or      ecx, 0FFFFh
0x18000788c  lock cmpxchg [rdi], ecx
0x180007890  cmp     edx, eax
0x180007892  jz      short loc_1800078B4
0x180007894  mov     edx, [rdi]
0x180007896  mov     eax, edx
0x180007898  lea     ecx, [rdx+10000h]
0x18000789e  lock cmpxchg [rdi], ecx
0x1800078a2  cmp     edx, eax
0x1800078a4  jnz     loc_180007958
0x1800078aa  mov     dl, 1; bool
0x1800078ac  mov     rcx, rdi; this
0x1800078af  call    ?_LockSpin@CReaderWriterLock2@@AEAAX_N@Z; CReaderWriterLock2::_LockSpin(bool)
0x1800078b4  xor     r10d, r10d
0x1800078b7  lea     rbx, [rsi+8]
0x1800078bb  mov     r13d, r10d
0x1800078be  mov     rdx, rbx
0x1800078c1  test    rbx, rbx
0x1800078c4  jnz     loc_180007D10
0x1800078ca  lea     r12, [rdi+8]
0x1800078ce  mov     rdx, r12
0x1800078d1  test    r12, r12
0x1800078d4  jnz     loc_180007D60
0x1800078da  mov     [rsp+88h+var_28], r14
0x1800078df  test    r13d, r13d
0x1800078e2  jle     loc_1800079FE
0x1800078e8  mov     rcx, cs:?sm_palloc@CNodeClump@@1PEAVALLOC_CACHE_HANDLER@@EA; this
0x1800078ef  call    ?Alloc@ALLOC_CACHE_HANDLER@@QEAAPEAXXZ; ALLOC_CACHE_HANDLER::Alloc(void)
0x1800078f4  mov     r14, rax
0x1800078f7  test    rax, rax
0x1800078fa  jnz     loc_180007C1B
0x180007900  mov     ecx, [rbp+70h]
0x180007903  mov     eax, 1
0x180007908  inc     dword ptr [rbp+60h]
0x18000790b  shl     eax, cl
0x18000790d  cmp     [rbp+60h], eax
0x180007910  jnz     short loc_180007932
0x180007912  lea     eax, [rcx+1]
0x180007915  mov     dword ptr [rbp+60h], 0
0x18000791c  mov     [rbp+70h], eax
0x18000791f  mov     eax, [rbp+58h]
0x180007922  add     eax, eax
0x180007924  or      eax, 1
0x180007927  mov     [rbp+58h], eax
0x18000792a  add     eax, eax
0x18000792c  or      eax, 1
0x18000792f  mov     [rbp+5Ch], eax
0x180007932  inc     dword ptr [rbp+7Ch]
0x180007935  mov     edx, [rsi]
0x180007937  mov     eax, edx
0x180007939  lea     ecx, [rdx-10000h]
0x18000793f  and     ecx, 0FFFF0000h
0x180007945  lock cmpxchg [rsi], ecx
0x180007949  cmp     edx, eax
0x18000794b  jz      short loc_180007979
0x18000794d  pause
0x18000794f  jmp     short loc_180007935
0x180007951  pause
0x180007953  jmp     loc_180007832
0x180007958  pause
0x18000795a  jmp     loc_180007894
0x18000795f  dec     dword ptr [rbp+70h]
0x180007962  mov     eax, 1
0x180007967  mov     ecx, [rbp+70h]
0x18000796a  shr     dword ptr [rbp+58h], 1
0x18000796d  shl     eax, cl
0x18000796f  dec     eax
0x180007971  shr     dword ptr [rbp+5Ch], 1
0x180007974  jmp     loc_1800077EF
0x180007979  mov     edx, [rdi]
0x18000797b  mov     eax, edx
0x18000797d  lea     ecx, [rdx-10000h]
0x180007983  and     ecx, 0FFFF0000h
0x180007989  lock cmpxchg [rdi], ecx
0x18000798d  cmp     edx, eax
0x18000798f  jz      short loc_180007995
0x180007991  pause
0x180007993  jmp     short loc_180007979
0x180007995  mov     eax, [rbp+1Ch]
0x180007998  dec     eax
0x18000799a  test    al, 3
0x18000799c  jz      loc_180007DA2
0x1800079a2  xchg    eax, [rbp+1Ch]
0x1800079a5  mov     eax, 0FFFFFF9Eh
0x1800079aa  jmp     short loc_1800079AE
0x1800079ac  xor     eax, eax
0x1800079ae  mov     r14, [rsp+88h+var_28]
0x1800079b3  mov     r12, [rsp+88h+var_18]
0x1800079b8  mov     rdi, [rsp+88h+arg_18]
0x1800079c0  mov     rsi, [rsp+88h+arg_10]
0x1800079c8  mov     rbx, [rsp+88h+arg_8]
0x1800079d0  mov     r13, [rsp+88h+var_20]
0x1800079d5  mov     rcx, [rsp+88h+var_30]
0x1800079da  xor     rcx, rsp; StackCookie
0x1800079dd  call    __security_check_cookie
0x1800079e2  add     rsp, 78h
0x1800079e6  pop     r15
0x1800079e8  pop     rbp
0x1800079e9  retn
0x1800079ea  call    cs:__imp_GetCurrentThreadId
0x1800079f0  and     eax, 0FFFFFFFCh
0x1800079f3  or      eax, 1
0x1800079f6  xchg    eax, [rbp+1Ch]
0x1800079f9  jmp     loc_1800077B4
0x1800079fe  mov     r14, r10
0x180007a01  movups  xmm0, xmmword ptr [rbx]
0x180007a04  movups  [rsp+88h+var_68], xmm0
0x180007a09  movups  xmm1, xmmword ptr [rbx+10h]
0x180007a0d  movups  [rsp+88h+var_58], xmm1
0x180007a12  movups  xmm0, xmmword ptr [rbx+20h]
0x180007a16  movups  [rsp+88h+var_48], xmm0
0x180007a1b  movsd   xmm1, qword ptr [rbx+30h]
0x180007a20  movsd   [rsp+88h+var_38], xmm1
0x180007a26  mov     [rbx+10h], r10
0x180007a2a  mov     dword ptr [rbx+0Ch], 1E3603Bh
0x180007a31  mov     [rbx+30h], r10
0x180007a35  mov     dword ptr [rbx+8], 1E3603Bh
0x180007a3c  mov     [rbx+28h], r10
0x180007a40  mov     dword ptr [rbx+4], 1E3603Bh
0x180007a47  mov     [rbx+20h], r10
0x180007a4b  mov     dword ptr [rbx], 1E3603Bh
0x180007a51  mov     [rbx+18h], r10
0x180007a55  mov     edx, [rsi]
0x180007a57  mov     eax, edx
0x180007a59  lea     ecx, [rdx-10000h]
0x180007a5f  and     ecx, 0FFFF0000h
0x180007a65  lock cmpxchg [rsi], ecx
0x180007a69  cmp     edx, eax
0x180007a6b  jz      short loc_180007A71
0x180007a6d  pause
0x180007a6f  jmp     short loc_180007A55
0x180007a71  mov     eax, [rbp+7Ch]
0x180007a74  test    [rbp+4Ch], eax
0x180007a77  jnz     short loc_180007AAF
0x180007a79  mov     ecx, [rbp+44h]
0x180007a7c  mov     edx, eax
0x180007a7e  mov     rax, [rbp+68h]
0x180007a82  shr     rdx, cl
0x180007a85  mov     ecx, [rbp+40h]
0x180007a88  mov     rbx, [rax+rdx*8]
0x180007a8c  cmp     ecx, 1
0x180007a8f  jnz     loc_180007F17
0x180007a95  test    rbx, rbx
0x180007a98  jnz     loc_180007DF0
0x180007a9e  mov     edx, [rbp+7Ch]
0x180007aa1  mov     ecx, [rbp+44h]
0x180007aa4  mov     rax, [rbp+68h]
0x180007aa8  shr     rdx, cl
0x180007aab  mov     [rax+rdx*8], r10
0x180007aaf  mov     esi, [rbp+74h]
0x180007ab2  mov     eax, esi
0x180007ab4  imul    eax, [rbp+48h]
0x180007ab8  shr     eax, 1
0x180007aba  cmp     [rbp+7Ch], eax
0x180007abd  ja      short loc_180007AF7
0x180007abf  cmp     esi, 8
0x180007ac2  jbe     short loc_180007AF7
0x180007ac4  shr     esi, 1
0x180007ac6  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180007acd  mov     ebx, esi
0x180007acf  mov     eax, 8
0x180007ad4  mul     rbx
0x180007ad7  cmovb   rax, rcx
0x180007adb  add     rax, 8
0x180007adf  cmovb   rax, rcx
0x180007ae3  mov     rcx, rax; Size
0x180007ae6  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180007aeb  test    rax, rax
0x180007aee  jnz     loc_180007E69
0x180007af4  xor     r10d, r10d
0x180007af7  mov     eax, [rbp+1Ch]
0x180007afa  dec     eax
0x180007afc  test    al, 3
0x180007afe  jz      loc_180007BF3
0x180007b04  xchg    eax, [rbp+1Ch]
0x180007b07  lea     r9, [rsp+88h+var_68]
0x180007b0c  mov     rcx, [r12+10h]
0x180007b11  test    rcx, rcx
0x180007b14  jnz     loc_180007BCB
0x180007b1a  cmp     dword ptr [r12], 1E3603Bh
0x180007b22  mov     edx, r10d
0x180007b25  jz      short loc_180007B5D
0x180007b27  cmp     dword ptr [r12+4], 1E3603Bh
0x180007b30  mov     edx, 1
0x180007b35  jz      short loc_180007B5D
0x180007b37  cmp     dword ptr [r12+8], 1E3603Bh
0x180007b40  mov     edx, 2
0x180007b45  jz      short loc_180007B5D
0x180007b47  cmp     dword ptr [r12+0Ch], 1E3603Bh
0x180007b50  mov     edx, 3
0x180007b55  mov     eax, 4
0x180007b5a  cmovnz  edx, eax
0x180007b5d  mov     r8, r10
0x180007b60  cmp     dword ptr [r9+r8*4], 1E3603Bh
0x180007b68  jnz     loc_180007F5B
0x180007b6e  inc     r8
0x180007b71  cmp     r8, 4
0x180007b75  jnz     short loc_180007B60
0x180007b77  mov     rax, r9
0x180007b7a  lea     rcx, [r9+10h]
0x180007b7e  mov     r9, [r9+10h]
0x180007b82  lea     r8, [rsp+88h+var_68]
0x180007b87  cmp     rax, r8
0x180007b8a  jnz     loc_180007FE2
0x180007b90  test    r9, r9
0x180007b93  jnz     short loc_180007B5D
0x180007b95  test    r14, r14
0x180007b98  jz      short loc_180007BAB
0x180007b9a  mov     rcx, r14; ListEntry
0x180007b9d  mov     r14, [r14+10h]
0x180007ba1  call    ??3CNodeClump@@SAXPEAX@Z; CNodeClump::operator delete(void *)
0x180007ba6  test    r14, r14
0x180007ba9  jnz     short loc_180007B9A
0x180007bab  mov     ecx, [rdi]
0x180007bad  mov     eax, ecx
  ... truncated ...
```
