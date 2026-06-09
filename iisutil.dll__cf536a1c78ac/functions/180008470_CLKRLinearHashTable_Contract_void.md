# CLKRLinearHashTable::_Contract(void)

- ea: `0x180008470`
- end: `0x180008d23`
- name: `?_Contract@CLKRLinearHashTable@@AEAA?AW4LK_RETCODE@@XZ`
- size: `2227`
- prototype: ``
- caller_count: `3`
- callee_count: `15`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x18000b020`
- `0x18000b310`
- `0x1800172c0`

## callees

- `0x180007e60`
- `0x180008470`
- `0x180008d30`
- `0x180008de0`
- `0x180008f20`
- `0x1800093dc`
- `0x180009520`
- `0x180009c10`
- `0x18000c180`
- `0x18000c200`
- `0x180016bfc`
- `0x180019230`
- `0x180019270`
- `0x18001abfc`
- `0x18002e560`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800084b4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180008711`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800089a0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800084b4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180008711`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800089a0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800089e9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800089e9`
- `api-ms-win-core-interlocked-l1-1-0!QueryDepthSList` at `0x1800089c4`
- `api-ms-win-core-interlocked-l1-1-0!QueryDepthSList` at `0x1800089c4`
- `api-ms-win-core-interlocked-l1-1-0!InterlockedPushEntrySList` at `0x180008aff`
- `api-ms-win-core-interlocked-l1-1-0!InterlockedPushEntrySList` at `0x180008aff`

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
0x180008470  push    rbp
0x180008472  push    r15
0x180008474  sub     rsp, 78h
0x180008478  mov     rax, cs:__security_cookie
0x18000847f  xor     rax, rsp
0x180008482  mov     [rsp+88h+var_30], rax
0x180008487  mov     eax, [rcx+1Ch]
0x18000848a  mov     rbp, rcx
0x18000848d  test    eax, eax
0x18000848f  jnz     short loc_1800084B4
0x180008491  mov     edx, [rcx+18h]
0x180008494  test    dx, dx
0x180008497  jnz     short loc_1800084B4
0x180008499  lea     ecx, [rdx+10000h]
0x18000849f  mov     eax, edx
0x1800084a1  or      ecx, 0FFFFh
0x1800084a7  lock cmpxchg [rbp+18h], ecx
0x1800084ac  cmp     edx, eax
0x1800084ae  jz      loc_180008711
0x1800084b4  call    cs:__imp_GetCurrentThreadId
0x1800084bb  nop     dword ptr [rax+rax+00h]
0x1800084c0  mov     ecx, [rbp+1Ch]
0x1800084c3  and     eax, 0FFFFFFFCh
0x1800084c6  and     ecx, 0FFFFFFFCh
0x1800084c9  cmp     ecx, eax
0x1800084cb  jz      loc_180008B10
0x1800084d1  lea     rcx, [rbp+18h]; this
0x1800084d5  call    ?_WriteLockSpin@CReaderWriterLock3@@AEAAXXZ; CReaderWriterLock3::_WriteLockSpin(void)
0x1800084da  mov     edx, [rbp+7Ch]
0x1800084dd  cmp     edx, [rbp+48h]
0x1800084e0  jbe     loc_180008C3A
0x1800084e6  mov     eax, [rbp+60h]
0x1800084e9  mov     [rsp+88h+arg_8], rbx
0x1800084f1  mov     [rsp+88h+arg_10], rsi
0x1800084f9  mov     [rsp+88h+arg_18], rdi
0x180008501  mov     [rsp+88h+var_18], r12
0x180008506  mov     [rsp+88h+var_20], r13
0x18000850b  test    eax, eax
0x18000850d  jz      loc_180008685
0x180008513  dec     eax
0x180008515  mov     ecx, [rbp+44h]
0x180008518  mov     [rbp+60h], eax
0x18000851b  lea     eax, [rdx-1]
0x18000851e  mov     r8d, eax
0x180008521  shr     r8, cl
0x180008524  mov     rcx, [rbp+68h]
0x180008528  mov     edx, eax
0x18000852a  mov     eax, [rbp+4Ch]
0x18000852d  and     rdx, rax
0x180008530  mov     rsi, [rcx+r8*8]
0x180008534  shl     rdx, 6
0x180008538  add     rsi, rdx
0x18000853b  mov     edx, [rsi]
0x18000853d  test    dx, dx
0x180008540  jnz     short loc_180008558
0x180008542  lea     ecx, [rdx+10000h]
0x180008548  mov     eax, edx
0x18000854a  or      ecx, 0FFFFh
0x180008550  lock cmpxchg [rsi], ecx
0x180008554  cmp     edx, eax
0x180008556  jz      short loc_180008578
0x180008558  mov     edx, [rsi]
0x18000855a  mov     eax, edx
0x18000855c  lea     ecx, [rdx+10000h]
0x180008562  lock cmpxchg [rsi], ecx
0x180008566  cmp     edx, eax
0x180008568  jnz     loc_180008677
0x18000856e  mov     dl, 1; bool
0x180008570  mov     rcx, rsi; this
0x180008573  call    ?_LockSpin@CReaderWriterLock2@@AEAAX_N@Z; CReaderWriterLock2::_LockSpin(bool)
0x180008578  dec     dword ptr [rbp+7Ch]
0x18000857b  mov     r8d, [rbp+60h]
0x18000857f  mov     ecx, [rbp+44h]
0x180008582  mov     edx, r8d
0x180008585  mov     eax, [rbp+4Ch]
0x180008588  shr     rdx, cl
0x18000858b  and     r8, rax
0x18000858e  mov     rcx, [rbp+68h]
0x180008592  shl     r8, 6
0x180008596  mov     rdi, [rcx+rdx*8]
0x18000859a  add     rdi, r8
0x18000859d  mov     edx, [rdi]
0x18000859f  test    dx, dx
0x1800085a2  jnz     short loc_1800085BA
0x1800085a4  lea     ecx, [rdx+10000h]
0x1800085aa  mov     eax, edx
0x1800085ac  or      ecx, 0FFFFh
0x1800085b2  lock cmpxchg [rdi], ecx
0x1800085b6  cmp     edx, eax
0x1800085b8  jz      short loc_1800085DA
0x1800085ba  mov     edx, [rdi]
0x1800085bc  mov     eax, edx
0x1800085be  lea     ecx, [rdx+10000h]
0x1800085c4  lock cmpxchg [rdi], ecx
0x1800085c8  cmp     edx, eax
0x1800085ca  jnz     loc_18000867E
0x1800085d0  mov     dl, 1; bool
0x1800085d2  mov     rcx, rdi; this
0x1800085d5  call    ?_LockSpin@CReaderWriterLock2@@AEAAX_N@Z; CReaderWriterLock2::_LockSpin(bool)
0x1800085da  xor     r10d, r10d
0x1800085dd  lea     rbx, [rsi+8]
0x1800085e1  mov     r13d, r10d
0x1800085e4  mov     rdx, rbx
0x1800085e7  test    rbx, rbx
0x1800085ea  jnz     loc_180008A42
0x1800085f0  lea     r12, [rdi+8]
0x1800085f4  mov     rdx, r12
0x1800085f7  test    r12, r12
0x1800085fa  jnz     loc_180008A90
0x180008600  mov     [rsp+88h+var_28], r14
0x180008605  test    r13d, r13d
0x180008608  jle     loc_18000872B
0x18000860e  mov     rcx, cs:?sm_palloc@CNodeClump@@1PEAVALLOC_CACHE_HANDLER@@EA; this
0x180008615  call    ?Alloc@ALLOC_CACHE_HANDLER@@QEAAPEAXXZ; ALLOC_CACHE_HANDLER::Alloc(void)
0x18000861a  mov     r14, rax
0x18000861d  test    rax, rax
0x180008620  jnz     loc_180008948
0x180008626  mov     ecx, [rbp+70h]
0x180008629  mov     eax, 1
0x18000862e  inc     dword ptr [rbp+60h]
0x180008631  shl     eax, cl
0x180008633  cmp     [rbp+60h], eax
0x180008636  jnz     short loc_180008658
0x180008638  lea     eax, [rcx+1]
0x18000863b  mov     dword ptr [rbp+60h], 0
0x180008642  mov     [rbp+70h], eax
0x180008645  mov     eax, [rbp+58h]
0x180008648  add     eax, eax
0x18000864a  or      eax, 1
0x18000864d  mov     [rbp+58h], eax
0x180008650  add     eax, eax
0x180008652  or      eax, 1
0x180008655  mov     [rbp+5Ch], eax
0x180008658  inc     dword ptr [rbp+7Ch]
0x18000865b  mov     edx, [rsi]
0x18000865d  mov     eax, edx
0x18000865f  lea     ecx, [rdx-10000h]
0x180008665  and     ecx, 0FFFF0000h
0x18000866b  lock cmpxchg [rsi], ecx
0x18000866f  cmp     edx, eax
0x180008671  jz      short loc_18000869F
0x180008673  pause
0x180008675  jmp     short loc_18000865B
0x180008677  pause
0x180008679  jmp     loc_180008558
0x18000867e  pause
0x180008680  jmp     loc_1800085BA
0x180008685  dec     dword ptr [rbp+70h]
0x180008688  mov     eax, 1
0x18000868d  mov     ecx, [rbp+70h]
0x180008690  shr     dword ptr [rbp+58h], 1
0x180008693  shl     eax, cl
0x180008695  dec     eax
0x180008697  shr     dword ptr [rbp+5Ch], 1
0x18000869a  jmp     loc_180008515
0x18000869f  mov     edx, [rdi]
0x1800086a1  mov     eax, edx
0x1800086a3  lea     ecx, [rdx-10000h]
0x1800086a9  and     ecx, 0FFFF0000h
0x1800086af  lock cmpxchg [rdi], ecx
0x1800086b3  cmp     edx, eax
0x1800086b5  jz      short loc_1800086BB
0x1800086b7  pause
0x1800086b9  jmp     short loc_18000869F
0x1800086bb  mov     eax, [rbp+1Ch]
0x1800086be  dec     eax
0x1800086c0  test    al, 3
0x1800086c2  jz      loc_180008AD2
0x1800086c8  xchg    eax, [rbp+1Ch]
0x1800086cb  mov     eax, 0FFFFFF9Eh
0x1800086d0  jmp     short loc_1800086D4
0x1800086d2  xor     eax, eax
0x1800086d4  mov     r14, [rsp+88h+var_28]
0x1800086d9  mov     r12, [rsp+88h+var_18]
0x1800086de  mov     rdi, [rsp+88h+arg_18]
0x1800086e6  mov     rsi, [rsp+88h+arg_10]
0x1800086ee  mov     rbx, [rsp+88h+arg_8]
0x1800086f6  mov     r13, [rsp+88h+var_20]
0x1800086fb  mov     rcx, [rsp+88h+var_30]
0x180008700  xor     rcx, rsp; StackCookie
0x180008703  call    __security_check_cookie
0x180008708  add     rsp, 78h
0x18000870c  pop     r15
0x18000870e  pop     rbp
0x18000870f  retn
0x180008711  call    cs:__imp_GetCurrentThreadId
0x180008718  nop     dword ptr [rax+rax+00h]
0x18000871d  and     eax, 0FFFFFFFCh
0x180008720  or      eax, 1
0x180008723  xchg    eax, [rbp+1Ch]
0x180008726  jmp     loc_1800084DA
0x18000872b  mov     r14, r10
0x18000872e  movups  xmm0, xmmword ptr [rbx]
0x180008731  movups  [rsp+88h+var_68], xmm0
0x180008736  movups  xmm1, xmmword ptr [rbx+10h]
0x18000873a  movups  [rsp+88h+var_58], xmm1
0x18000873f  movups  xmm0, xmmword ptr [rbx+20h]
0x180008743  movups  [rsp+88h+var_48], xmm0
0x180008748  movsd   xmm1, qword ptr [rbx+30h]
0x18000874d  movsd   [rsp+88h+var_38], xmm1
0x180008753  mov     [rbx+10h], r10
0x180008757  mov     dword ptr [rbx+0Ch], 1E3603Bh
0x18000875e  mov     [rbx+30h], r10
0x180008762  mov     dword ptr [rbx+8], 1E3603Bh
0x180008769  mov     [rbx+28h], r10
0x18000876d  mov     dword ptr [rbx+4], 1E3603Bh
0x180008774  mov     [rbx+20h], r10
0x180008778  mov     dword ptr [rbx], 1E3603Bh
0x18000877e  mov     [rbx+18h], r10
0x180008782  mov     edx, [rsi]
0x180008784  mov     eax, edx
0x180008786  lea     ecx, [rdx-10000h]
0x18000878c  and     ecx, 0FFFF0000h
0x180008792  lock cmpxchg [rsi], ecx
0x180008796  cmp     edx, eax
0x180008798  jz      short loc_18000879E
0x18000879a  pause
0x18000879c  jmp     short loc_180008782
0x18000879e  mov     eax, [rbp+7Ch]
0x1800087a1  test    [rbp+4Ch], eax
0x1800087a4  jnz     short loc_1800087DC
0x1800087a6  mov     ecx, [rbp+44h]
0x1800087a9  mov     edx, eax
0x1800087ab  mov     rax, [rbp+68h]
0x1800087af  shr     rdx, cl
0x1800087b2  mov     ecx, [rbp+40h]
0x1800087b5  mov     rbx, [rax+rdx*8]
0x1800087b9  cmp     ecx, 1
0x1800087bc  jnz     loc_180008C4D
0x1800087c2  test    rbx, rbx
0x1800087c5  jnz     loc_180008B26
0x1800087cb  mov     edx, [rbp+7Ch]
0x1800087ce  mov     ecx, [rbp+44h]
0x1800087d1  mov     rax, [rbp+68h]
0x1800087d5  shr     rdx, cl
0x1800087d8  mov     [rax+rdx*8], r10
0x1800087dc  mov     esi, [rbp+74h]
0x1800087df  mov     eax, esi
0x1800087e1  imul    eax, [rbp+48h]
0x1800087e5  shr     eax, 1
0x1800087e7  cmp     [rbp+7Ch], eax
0x1800087ea  ja      short loc_180008824
0x1800087ec  cmp     esi, 8
0x1800087ef  jbe     short loc_180008824
0x1800087f1  shr     esi, 1
0x1800087f3  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1800087fa  mov     ebx, esi
0x1800087fc  mov     eax, 8
0x180008801  mul     rbx
0x180008804  cmovb   rax, rcx
0x180008808  add     rax, 8
0x18000880c  cmovb   rax, rcx
0x180008810  mov     rcx, rax; Size
0x180008813  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180008818  test    rax, rax
0x18000881b  jnz     loc_180008B9F
0x180008821  xor     r10d, r10d
0x180008824  mov     eax, [rbp+1Ch]
0x180008827  dec     eax
0x180008829  test    al, 3
0x18000882b  jz      loc_180008920
0x180008831  xchg    eax, [rbp+1Ch]
0x180008834  lea     r9, [rsp+88h+var_68]
0x180008839  mov     rcx, [r12+10h]
0x18000883e  test    rcx, rcx
0x180008841  jnz     loc_1800088F8
0x180008847  cmp     dword ptr [r12], 1E3603Bh
0x18000884f  mov     edx, r10d
0x180008852  jz      short loc_18000888A
0x180008854  cmp     dword ptr [r12+4], 1E3603Bh
0x18000885d  mov     edx, 1
0x180008862  jz      short loc_18000888A
0x180008864  cmp     dword ptr [r12+8], 1E3603Bh
0x18000886d  mov     edx, 2
0x180008872  jz      short loc_18000888A
0x180008874  cmp     dword ptr [r12+0Ch], 1E3603Bh
0x18000887d  mov     edx, 3
0x180008882  mov     eax, 4
0x180008887  cmovnz  edx, eax
0x18000888a  mov     r8, r10
0x18000888d  cmp     dword ptr [r9+r8*4], 1E3603Bh
0x180008895  jnz     loc_180008C91
0x18000889b  inc     r8
0x18000889e  cmp     r8, 4
0x1800088a2  jnz     short loc_18000888D
0x1800088a4  mov     rax, r9
0x1800088a7  lea     rcx, [r9+10h]
0x1800088ab  mov     r9, [r9+10h]
0x1800088af  lea     r8, [rsp+88h+var_68]
0x1800088b4  cmp     rax, r8
0x1800088b7  jnz     loc_180008D18
0x1800088bd  test    r9, r9
0x1800088c0  jnz     short loc_18000888A
0x1800088c2  test    r14, r14
0x1800088c5  jz      short loc_1800088D8
0x1800088c7  mov     rcx, r14; ListEntry
0x1800088ca  mov     r14, [r14+10h]
0x1800088ce  call    ??3CNodeClump@@SAXPEAX@Z; CNodeClump::operator delete(void *)
0x1800088d3  test    r14, r14
0x1800088d6  jnz     short loc_1800088C7
  ... truncated ...
```
