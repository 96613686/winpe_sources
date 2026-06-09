# LKRhash::CLKRLinearHashTable::_Contract(void)

- ea: `0x180002d60`
- end: `0x1800037d6`
- name: `?_Contract@CLKRLinearHashTable@LKRhash@@AEAA?AW4LK_RETCODE@2@XZ`
- size: `2678`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x1800029d0`
- `0x180019de8`

## callees

- `0x180002d60`
- `0x1800037e0`
- `0x180005780`
- `0x180006404`
- `0x1800065c4`
- `0x180007b30`
- `0x180019624`
- `0x180019a34`
- `0x18001a284`
- `0x18001b550`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180002db6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800035b3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180002db6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800035b3`

## pseudocode

```c
__int64 __fastcall LKRhash::CLKRLinearHashTable::_Contract(__int64 a1)
{
  signed __int32 v2; // edx
  unsigned int v3; // r9d
  int v4; // ebx
  unsigned int v5; // ebx
  int v6; // ecx
  unsigned int v7; // r9d
  unsigned int v8; // r11d
  __int64 v9; // r10
  __int64 v10; // rdi
  __int64 v11; // rdi
  volatile signed __int32 *v12; // rbx
  signed __int32 v13; // edx
  signed __int32 v14; // edx
  _OWORD *v15; // rsi
  int v16; // ebp
  __int64 v17; // rdx
  int v18; // eax
  int v19; // ecx
  int v20; // eax
  struct LKRhash::CNodeClump *v21; // r14
  volatile signed __int32 *v22; // rdx
  int v23; // eax
  int v24; // ecx
  int v25; // eax
  struct LKRhash::CNodeClump *NodeClump; // r15
  bool i; // zf
  signed __int32 v28; // edx
  unsigned __int64 v29; // rax
  unsigned int v30; // edi
  __int32 v31; // ecx
  _OWORD *v32; // rdx
  unsigned int m; // ecx
  struct LKRhash::CNodeClump *v34; // rax
  struct LKRhash::CNodeClump **v35; // r8
  bool n; // zf
  signed __int32 v37; // ecx
  signed __int32 v39; // edx
  signed __int32 v40; // edx
  unsigned int v41; // edi
  struct LKRhash::CDirEntry *SegmentDirectory; // rsi
  unsigned int j; // r8d
  __int64 v44; // rcx
  unsigned int k; // edx
  __int64 v46; // rcx
  int v47; // ecx
  signed __int32 v48; // edx
  int v49; // ecx
  signed __int32 v50; // edx
  signed __int32 v51; // edx
  __int32 v52; // ecx
  signed __int32 v53; // edx
  struct LKRhash::CNodeClump **v54; // r8
  struct LKRhash::CNodeClump **v55; // r8
  struct LKRhash::CNodeClump **v56; // r8
  struct LKRhash::CNodeClump **v57; // r8
  struct LKRhash::CNodeClump *v58; // rax
  int v59; // eax
  _QWORD *v60; // rax
  struct LKRhash::CNodeClump *v61; // rcx
  _QWORD *v62; // rax
  struct LKRhash::CNodeClump *v63; // rcx
  _QWORD *v64; // rax
  struct LKRhash::CNodeClump *v65; // rcx
  _QWORD *v66; // rax
  struct LKRhash::CNodeClump *v67; // rcx
  struct LKRhash::CNodeClump *v68; // rdx
  _OWORD v69[3]; // [rsp+20h] [rbp-68h] BYREF
  __int64 v70; // [rsp+50h] [rbp-38h]

  if ( *(_BYTE *)(a1 + 153) )
  {
    if ( *(_DWORD *)(a1 + 28)
      || (v2 = *(_DWORD *)(a1 + 24), (_WORD)v2)
      || v2 != _InterlockedCompareExchange((volatile signed __int32 *)(a1 + 24), (v2 + 0x10000) | 0xFFFF, v2) )
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
  v3 = *(_DWORD *)(a1 + 124);
  if ( v3 <= *(_DWORD *)(a1 + 72) )
  {
    LKRhash::CLKRLinearHashTable::WriteUnlock((LKRhash::CLKRLinearHashTable *)a1);
    return 4294967198LL;
  }
  v4 = *(_DWORD *)(a1 + 96);
  if ( v4 )
  {
    v5 = v4 - 1;
  }
  else
  {
    v47 = --*(_DWORD *)(a1 + 112);
    *(_DWORD *)(a1 + 88) >>= 1;
    v5 = (1 << v47) - 1;
    *(_DWORD *)(a1 + 92) >>= 1;
  }
  v6 = *(_DWORD *)(a1 + 68);
  v7 = v3 - 1;
  v8 = *(_DWORD *)(a1 + 76);
  v9 = *(_QWORD *)(a1 + 104);
  *(_DWORD *)(a1 + 96) = v5;
  v10 = *(_QWORD *)(v9 + 8 * ((unsigned __int64)v7 >> v6));
  *(_DWORD *)(a1 + 124) = v7;
  v11 = ((unsigned __int64)(v7 & v8) << 6) + v10;
  v12 = (volatile signed __int32 *)(((unsigned __int64)(v8 & v5) << 6)
                                  + *(_QWORD *)(v9 + 8 * ((unsigned __int64)v5 >> v6)));
  if ( *(_BYTE *)(a1 + 153) )
  {
    if ( (unsigned __int16)*v12 || (v13 = *v12, v13 != _InterlockedCompareExchange(v12, (v13 + 0x10000) | 0xFFFF, v13)) )
    {
      do
        v39 = *v12;
      while ( v39 != _InterlockedCompareExchange(v12, v39 + 0x10000, v39) );
      CReaderWriterLock2::_LockSpin((CReaderWriterLock2 *)v12, 1);
    }
    if ( *(_BYTE *)(a1 + 153) )
    {
      if ( (unsigned __int16)*(_DWORD *)v11
        || (v14 = *(_DWORD *)v11,
            v14 != _InterlockedCompareExchange((volatile signed __int32 *)v11, (v14 + 0x10000) | 0xFFFF, v14)) )
      {
        do
          v40 = *(_DWORD *)v11;
        while ( v40 != _InterlockedCompareExchange((volatile signed __int32 *)v11, v40 + 0x10000, v40) );
        CReaderWriterLock2::_LockSpin((CReaderWriterLock2 *)v11, 1);
      }
    }
  }
  v15 = (_OWORD *)(v11 + 8);
  v16 = 0;
  v17 = v11 + 8;
  if ( v11 != -8 )
  {
    do
    {
      v18 = v16 + 1;
      if ( *(_DWORD *)v17 == 31678523 )
        v18 = v16;
      v19 = v18 + 1;
      if ( *(_DWORD *)(v17 + 4) == 31678523 )
        v19 = v18;
      v20 = v19 + 1;
      if ( *(_DWORD *)(v17 + 8) == 31678523 )
        v20 = v19;
      i = *(_DWORD *)(v17 + 12) == 31678523;
      v17 = *(_QWORD *)(v17 + 16);
      v16 = v20 + 1;
      if ( i )
        v16 = v20;
    }
    while ( v17 );
  }
  v21 = (struct LKRhash::CNodeClump *)(v12 + 2);
  v22 = v12 + 2;
  if ( v12 != (volatile signed __int32 *)-8LL )
  {
    do
    {
      v23 = v16 - 1;
      if ( *v22 != 31678523 )
        v23 = v16;
      v24 = v23 - 1;
      if ( *((_DWORD *)v22 + 1) != 31678523 )
        v24 = v23;
      v25 = v24 - 1;
      if ( *((_DWORD *)v22 + 2) != 31678523 )
        v25 = v24;
      i = *((_DWORD *)v22 + 3) == 31678523;
      v22 = (volatile signed __int32 *)*((_QWORD *)v22 + 2);
      v16 = v25 - 1;
      if ( !i )
        v16 = v25;
    }
    while ( v22 );
  }
  NodeClump = 0;
  if ( v16 <= 0 )
    goto LABEL_36;
  NodeClump = LKRhash::CLKRLinearHashTable::_AllocateNodeClump((LKRhash::CLKRLinearHashTable *)a1);
  if ( NodeClump )
  {
    if ( v16 > 4 )
    {
      v58 = LKRhash::CLKRLinearHashTable::_AllocateNodeClump((LKRhash::CLKRLinearHashTable *)a1);
      if ( !v58 )
      {
        LKRhash::CLKRLinearHashTable::_FreeNodeClump((LKRhash::CLKRLinearHashTable *)a1, NodeClump);
        goto LABEL_121;
      }
      *((_QWORD *)NodeClump + 2) = v58;
    }
LABEL_36:
    v69[0] = *v15;
    v69[1] = *(_OWORD *)(v11 + 24);
    v69[2] = *(_OWORD *)(v11 + 40);
    v70 = *(_QWORD *)(v11 + 56);
    *(_QWORD *)(v11 + 24) = 0;
    *(_DWORD *)(v11 + 20) = 31678523;
    *(_QWORD *)(v11 + 56) = 0;
    *(_DWORD *)(v11 + 16) = 31678523;
    *(_QWORD *)(v11 + 48) = 0;
    *(_DWORD *)(v11 + 12) = 31678523;
    *(_QWORD *)(v11 + 40) = 0;
    *(_DWORD *)v15 = 31678523;
    *(_QWORD *)(v11 + 32) = 0;
    for ( i = *(_BYTE *)(a1 + 153) == 0;
          !i;
          i = v28 == _InterlockedCompareExchange((volatile signed __int32 *)v11, (v28 - 0x10000) & 0xFFFF0000, v28) )
    {
      v28 = *(_DWORD *)v11;
    }
    v29 = *(unsigned int *)(a1 + 124);
    if ( ((unsigned int)v29 & *(_DWORD *)(a1 + 76)) == 0 )
    {
      LKRhash::CLKRLinearHashTable::_FreeSegment(
        (LKRhash::CLKRLinearHashTable *)a1,
        *(struct LKRhash::CSegment **)(*(_QWORD *)(a1 + 104) + 8 * (v29 >> *(_DWORD *)(a1 + 68))));
      *(_QWORD *)(*(_QWORD *)(a1 + 104) + 8 * ((unsigned __int64)*(unsigned int *)(a1 + 124) >> *(_DWORD *)(a1 + 68))) = 0;
    }
    v30 = *(_DWORD *)(a1 + 116);
    if ( v30 > 8 && *(_DWORD *)(a1 + 124) <= (unsigned int)(*(_DWORD *)(a1 + 72) * *(_DWORD *)(a1 + 116)) >> 1 )
    {
      v41 = v30 >> 1;
      SegmentDirectory = LKRhash::CLKRLinearHashTable::_AllocateSegmentDirectory(
                           (LKRhash::CLKRLinearHashTable *)a1,
                           v41);
      if ( SegmentDirectory )
      {
        for ( j = 0; j < v41; *((_QWORD *)SegmentDirectory + v44) = *(_QWORD *)(8 * v44 + *(_QWORD *)(a1 + 104)) )
          v44 = j++;
        for ( k = 0; k < *(_DWORD *)(a1 + 116); *(_QWORD *)(*(_QWORD *)(a1 + 104) + 8 * v46) = 0 )
          v46 = k++;
        LKRhash::CLKRLinearHashTable::_FreeSegmentDirectory((LKRhash::CLKRLinearHashTable *)a1);
        *(_QWORD *)(a1 + 104) = SegmentDirectory;
        *(_DWORD *)(a1 + 116) = v41;
      }
    }
    if ( *(_BYTE *)(a1 + 153) )
    {
      v31 = 0;
      if ( ((*(_BYTE *)(a1 + 28) - 1) & 3) != 0 )
        v31 = *(_DWORD *)(a1 + 28) - 1;
      _InterlockedExchange((volatile __int32 *)(a1 + 28), v31);
      if ( !v31 )
      {
        _m_prefetchw((const void *)(a1 + 24));
        do
          v48 = *(_DWORD *)(a1 + 24);
        while ( v48 != _InterlockedCompareExchange(
                         (volatile signed __int32 *)(a1 + 24),
                         (v48 - 0x10000) & 0xFFFF0000,
                         v48) );
      }
    }
    v32 = v69;
    while ( *((_QWORD *)v21 + 2)
         && *(_DWORD *)v21 != 31678523
         && *((_DWORD *)v21 + 1) != 31678523
         && *((_DWORD *)v21 + 2) != 31678523
         && *((_DWORD *)v21 + 3) != 31678523 )
      v21 = (struct LKRhash::CNodeClump *)*((_QWORD *)v21 + 2);
    m = 0;
    if ( *(_DWORD *)v21 != 31678523 )
    {
      m = 1;
      if ( *((_DWORD *)v21 + 1) != 31678523 )
      {
        m = 2;
        if ( *((_DWORD *)v21 + 2) != 31678523 )
        {
          m = 3;
          if ( *((_DWORD *)v21 + 3) != 31678523 )
            m = 4;
        }
      }
    }
    while ( 1 )
    {
      if ( *(_DWORD *)v32 != 31678523 )
      {
        if ( m == 4 )
        {
          while ( 1 )
          {
            v54 = (struct LKRhash::CNodeClump **)((char *)v21 + 16);
            v21 = (struct LKRhash::CNodeClump *)*((_QWORD *)v21 + 2);
            if ( !v21 )
              break;
            for ( m = 0; (int)m < 4; ++m )
            {
              if ( *((_DWORD *)v21 + (int)m) == 31678523 )
                goto LABEL_90;
            }
          }
          v21 = NodeClump;
          v60 = (_QWORD *)((char *)NodeClump + 16);
          v61 = NodeClump;
          NodeClump = (struct LKRhash::CNodeClump *)*((_QWORD *)NodeClump + 2);
          *v60 = 0;
          *((_DWORD *)v21 + 3) = 31678523;
          *((_QWORD *)v21 + 6) = 0;
          *((_DWORD *)v21 + 2) = 31678523;
          *((_QWORD *)v21 + 5) = 0;
          *((_DWORD *)v21 + 1) = 31678523;
          *((_QWORD *)v21 + 4) = 0;
          *(_DWORD *)v61 = 31678523;
          m = 0;
          *((_QWORD *)v21 + 3) = 0;
          *v54 = v21;
        }
        else
        {
LABEL_90:
          if ( m > 3 )
            goto LABEL_54;
        }
        if ( !v21 || *((_QWORD *)v21 + m + 3) || *((_DWORD *)v21 + m) != 31678523 )
          goto LABEL_54;
        *((_DWORD *)v21 + m) = *(_DWORD *)v32;
        *((_QWORD *)v21 + m + 3) = *((_QWORD *)v32 + 3);
        *(_DWORD *)v32 = 31678523;
        *((_QWORD *)v32 + 3) = 0;
        do
          ++m;
        while ( m != 4 && *((_DWORD *)v21 + (int)m) != 31678523 );
      }
      if ( *((_DWORD *)v32 + 1) != 31678523 )
      {
        if ( m == 4 )
        {
          while ( 1 )
          {
            v55 = (struct LKRhash::CNodeClump **)((char *)v21 + 16);
            v21 = (struct LKRhash::CNodeClump *)*((_QWORD *)v21 + 2);
            if ( !v21 )
              break;
            for ( m = 0; (int)m < 4; ++m )
            {
              if ( *((_DWORD *)v21 + (int)m) == 31678523 )
                goto LABEL_99;
            }
          }
          v21 = NodeClump;
          v62 = (_QWORD *)((char *)NodeClump + 16);
          v63 = NodeClump;
          NodeClump = (struct LKRhash::CNodeClump *)*((_QWORD *)NodeClump + 2);
          *v62 = 0;
          *((_DWORD *)v21 + 3) = 31678523;
          *((_QWORD *)v21 + 6) = 0;
          *((_DWORD *)v21 + 2) = 31678523;
          *((_QWORD *)v21 + 5) = 0;
          *((_DWORD *)v21 + 1) = 31678523;
          *((_QWORD *)v21 + 4) = 0;
          *(_DWORD *)v63 = 31678523;
          m = 0;
          *((_QWORD *)v21 + 3) = 0;
          *v55 = v21;
        }
        else
        {
LABEL_99:
          if ( m > 3 )
            goto LABEL_54;
        }
        if ( !v21 || *((_QWORD *)v21 + m + 3) || *((_DWORD *)v21 + m) != 31678523 )
          goto LABEL_54;
        *((_DWORD *)v21 + m) = *((_DWORD *)v32 + 1);
        *((_QWORD *)v21 + m + 3) = *((_QWORD *)v32 + 4);
        *((_DWORD *)v32 + 1) = 31678523;
        *((_QWORD *)v32 + 4) = 0;
        do
          ++m;
        while ( m != 4 && *((_DWORD *)v21 + (int)m) != 31678523 );
      }
      if ( *((_DWORD *)v32 + 2) != 31678523 )
      {
        if ( m == 4 )
        {
          while ( 1 )
          {
            v56 = (struct LKRhash::CNodeClump **)((char *)v21 + 16);
            v21 = (struct LKRhash::CNodeClump *)*((_QWORD *)v21 + 2);
            if ( !v21 )
              break;
            for ( m = 0; (int)m < 4; ++m )
            {
              if ( *((_DWORD *)v21 + (int)m) == 31678523 )
                goto LABEL_72;
            }
          }
          v21 = NodeClump;
          v64 = (_QWORD *)((char *)NodeClump + 16);
          v65 = NodeClump;
          NodeClump = (struct LKRhash::CNodeClump *)*((_QWORD *)NodeClump + 2);
          *v64 = 0;
          *((_DWORD *)v21 + 3) = 31678523;
          *((_QWORD *)v21 + 6) = 0;
          *((_DWORD *)v21 + 2) = 31678523;
          *((_QWORD *)v21 + 5) = 0;
          *((_DWORD *)v21 + 1) = 31678523;
          *((_QWORD *)v21 + 4) = 0;
          *(_DWORD *)v65 = 31678523;
          m = 0;
          *((_QWORD *)v21 + 3) = 0;
          *v56 = v21;
        }
        else
        {
LABEL_72:
          if ( m > 3 )
            goto LABEL_54;
        }
        if ( !v21 || *((_QWORD *)v21 + m + 3) || *((_DWORD *)v21 + m) != 31678523 )
          goto LABEL_54;
        *((_DWORD *)v21 + m) = *((_DWORD *)v32 + 2);
        *((_QWORD *)v21 + m + 3) = *((_QWORD *)v32 + 5);
        *((_DWORD *)v32 + 2) = 31678523;
        *((_QWORD *)v32 + 5) = 0;
        do
          ++m;
        while ( m != 4 && *((_DWORD *)v21 + (int)m) != 31678523 );
      }
      if ( *((_DWORD *)v32 + 3) != 31678523 )
      {
        if ( m == 4 )
        {
          while ( 1 )
          {
            v57 = (struct LKRhash::CNodeClump **)((char *)v21 + 16);
            v21 = (struct LKRhash::CNodeClump *)*((_QWORD *)v21 + 2);
            if ( !v21 )
              break;
            for ( m = 0; (int)m < 4; ++m )
            {
              if ( *((_DWORD *)v21 + (int)m) == 31678523 )
                goto LABEL_81;
            }
          }
          v21 = NodeClump;
          v66 = (_QWORD *)((char *)NodeClump + 16);
          v67 = NodeClump;
          NodeClump = (struct LKRhash::CNodeClump *)*((_QWORD *)NodeClump + 2);
          *v66 = 0;
          *((_DWORD *)v21 + 3) = 31678523;
          *((_QWORD *)v21 + 6) = 0;
          *((_DWORD *)v21 + 2) = 31678523;
          *((_QWORD *)v21 + 5) = 0;
          *((_DWORD *)v21 + 1) = 31678523;
          *((_QWORD *)v21 + 4) = 0;
          *(_DWORD *)v67 = 31678523;
          m = 0;
          *((_QWORD *)v21 + 3) = 0;
          *v57 = v21;
LABEL_82:
          if ( v21 && !*((_QWORD *)v21 + m + 3) && *((_DWORD *)v21 + m) == 31678523 )
          {
            *((_DWORD *)v21 + m) = *((_DWORD *)v32 + 3);
            *((_QWORD *)v21 + m + 3) = *((_QWORD *)v32 + 6);
            *((_DWORD *)v32 + 3) = 31678523;
            *((_QWORD *)v32 + 6) = 0;
            do
              ++m;
            while ( m != 4 && *((_DWORD *)v21 + (int)m) != 31678523 );
          }
          goto LABEL_54;
        }
LABEL_81:
        if ( m <= 3 )
          goto LABEL_82;
      }
LABEL_54:
      v34 = (struct LKRhash::CNodeClump *)v32;
      v35 = (struct LKRhash::CNodeClump **)(v32 + 1);
      v32 = (_OWORD *)*((_QWORD *)v32 + 2);
      if ( v34 != (struct LKRhash::CNodeClump *)v69 )
      {
        *v35 = NodeClump;
        NodeClump = v34;
      }
      if ( !v32 )
      {
        while ( NodeClump )
        {
          v68 = NodeClump;
          NodeClump = (struct LKRhash::CNodeClump *)*((_QWORD *)NodeClump + 2);
          LKRhash::CLKRLinearHashTable::_FreeNodeClump((LKRhash::CLKRLinearHashTable *)a1, v68);
        }
        for ( n = *(_BYTE *)(a1 + 153) == 0;
              !n;
              n = v37 == _InterlockedCompareExchange(v12, (v37 - 0x10000) & 0xFFFF0000, v37) )
        {
          v37 = *v12;
        }
        return 0;
      }
    }
  }
LABEL_121:
  v49 = *(_DWORD *)(a1 + 112);
  if ( ++*(_DWORD *)(a1 + 96) == 1 << v49 )
  {
    *(_DWORD *)(a1 + 96) = 0;
    *(_DWORD *)(a1 + 112) = v49 + 1;
    v59 = (2 * *(_DWORD *)(a1 + 88)) | 1;
    *(_DWORD *)(a1 + 88) = v59;
    *(_DWORD *)(a1 + 92) = (2 * v59) | 1;
  }
  ++*(_DWORD *)(a1 + 124);
  if ( *(_BYTE *)(a1 + 153) )
  {
    do
      v50 = *(_DWORD *)v11;
    while ( v50 != _InterlockedCompareExchange((volatile signed __int32 *)v11, (v50 - 0x10000) & 0xFFFF0000, v50) );
    if ( *(_BYTE *)(a1 + 153) )
    {
      do
        v51 = *v12;
      while ( v51 != _InterlockedCompareExchange(v12, (v51 - 0x10000) & 0xFFFF0000, v51) );
      if ( *(_BYTE *)(a1 + 153) )
      {
        v52 = 0;
        if ( ((*(_BYTE *)(a1 + 28) - 1) & 3) != 0 )
          v52 = *(_DWORD *)(a1 + 28) - 1;
        _InterlockedExchange((volatile __int32 *)(a1 + 28), v52);
        if ( !v52 )
        {
          _m_prefetchw((const void *)(a1 + 24));
          do
            v53 = *(_DWORD *)(a1 + 24);
          while ( v53 != _InterlockedCompareExchange(
                           (volatile signed __int32 *)(a1 + 24),
                           (v53 - 0x10000) & 0xFFFF0000,
                           v53) );
        }
      }
    }
  }
  return 4294967198LL;
}

```

## disassembly

```asm
0x180002d60  push    rbx
0x180002d62  push    r13
0x180002d64  sub     rsp, 78h
0x180002d68  mov     rax, cs:__security_cookie
0x180002d6f  xor     rax, rsp
0x180002d72  mov     [rsp+88h+var_30], rax
0x180002d77  cmp     byte ptr [rcx+99h], 0
0x180002d7e  mov     r13, rcx
0x180002d81  jz      short loc_180002DC6
0x180002d83  mov     eax, [rcx+1Ch]
0x180002d86  test    eax, eax
0x180002d88  jnz     loc_1800035B3
0x180002d8e  mov     edx, [rcx+18h]
0x180002d91  test    dx, dx
0x180002d94  jnz     loc_1800035B3
0x180002d9a  lea     ecx, [rdx+10000h]
0x180002da0  mov     eax, edx
0x180002da2  or      ecx, 0FFFFh
0x180002da8  lock cmpxchg [r13+18h], ecx
0x180002dae  cmp     edx, eax
0x180002db0  jnz     loc_1800035B3
0x180002db6  call    cs:__imp_GetCurrentThreadId
0x180002dbc  and     eax, 0FFFFFFFCh
0x180002dbf  or      eax, 1
0x180002dc2  xchg    eax, [r13+1Ch]
0x180002dc6  mov     r9d, [r13+7Ch]
0x180002dca  cmp     r9d, [r13+48h]
0x180002dce  jbe     loc_1800035E4
0x180002dd4  mov     ebx, [r13+60h]
0x180002dd8  mov     [rsp+88h+arg_8], rbp
0x180002de0  mov     [rsp+88h+arg_10], rsi
0x180002de8  mov     [rsp+88h+arg_18], rdi
0x180002df0  mov     [rsp+88h+var_18], r12
0x180002df5  mov     r12d, 1
0x180002dfb  mov     [rsp+88h+var_20], r14
0x180002e00  mov     [rsp+88h+var_28], r15
0x180002e05  test    ebx, ebx
0x180002e07  jz      loc_1800033D5
0x180002e0d  dec     ebx
0x180002e0f  mov     ecx, [r13+44h]
0x180002e13  dec     r9d
0x180002e16  mov     r11d, [r13+4Ch]
0x180002e1a  mov     r10, [r13+68h]
0x180002e1e  mov     edx, r11d
0x180002e21  mov     [r13+60h], ebx
0x180002e25  mov     eax, r9d
0x180002e28  and     rdx, rax
0x180002e2b  mov     r8d, r9d
0x180002e2e  shr     r8, cl
0x180002e31  mov     eax, ebx
0x180002e33  shr     rax, cl
0x180002e36  mov     ecx, ebx
0x180002e38  mov     rdi, [r10+r8*8]
0x180002e3c  and     rcx, r11
0x180002e3f  shl     rcx, 6
0x180002e43  shl     rdx, 6
0x180002e47  mov     [r13+7Ch], r9d
0x180002e4b  add     rdi, rdx
0x180002e4e  mov     rbx, [r10+rax*8]
0x180002e52  add     rbx, rcx
0x180002e55  cmp     byte ptr [r13+99h], 0
0x180002e5d  jz      short loc_180002EB3
0x180002e5f  mov     edx, [rbx]
0x180002e61  test    dx, dx
0x180002e64  jnz     loc_1800030F9
0x180002e6a  lea     ecx, [rdx+10000h]
0x180002e70  mov     eax, edx
0x180002e72  or      ecx, 0FFFFh
0x180002e78  lock cmpxchg [rbx], ecx
0x180002e7c  cmp     edx, eax
0x180002e7e  jnz     loc_1800030F9
0x180002e84  cmp     byte ptr [r13+99h], 0
0x180002e8c  jz      short loc_180002EB3
0x180002e8e  mov     edx, [rdi]
0x180002e90  test    dx, dx
0x180002e93  jnz     loc_18000311C
0x180002e99  lea     ecx, [rdx+10000h]
0x180002e9f  mov     eax, edx
0x180002ea1  or      ecx, 0FFFFh
0x180002ea7  lock cmpxchg [rdi], ecx
0x180002eab  cmp     edx, eax
0x180002ead  jnz     loc_18000311C
0x180002eb3  lea     rsi, [rdi+8]
0x180002eb7  xor     ebp, ebp
0x180002eb9  mov     rdx, rsi
0x180002ebc  test    rsi, rsi
0x180002ebf  jz      short loc_180002EFD
0x180002ec1  cmp     dword ptr [rdx], 1E3603Bh
0x180002ec7  lea     eax, [rbp+1]
0x180002eca  cmovz   eax, ebp
0x180002ecd  cmp     dword ptr [rdx+4], 1E3603Bh
0x180002ed4  lea     ecx, [rax+1]
0x180002ed7  cmovz   ecx, eax
0x180002eda  cmp     dword ptr [rdx+8], 1E3603Bh
0x180002ee1  lea     eax, [rcx+1]
0x180002ee4  cmovz   eax, ecx
0x180002ee7  cmp     dword ptr [rdx+0Ch], 1E3603Bh
0x180002eee  mov     rdx, [rdx+10h]
0x180002ef2  lea     ebp, [rax+1]
0x180002ef5  cmovz   ebp, eax
0x180002ef8  test    rdx, rdx
0x180002efb  jnz     short loc_180002EC1
0x180002efd  lea     r14, [rbx+8]
0x180002f01  mov     rdx, r14
0x180002f04  test    r14, r14
0x180002f07  jz      short loc_180002F45
0x180002f09  cmp     dword ptr [rdx], 1E3603Bh
0x180002f0f  lea     eax, [rbp-1]
0x180002f12  cmovnz  eax, ebp
0x180002f15  cmp     dword ptr [rdx+4], 1E3603Bh
0x180002f1c  lea     ecx, [rax-1]
0x180002f1f  cmovnz  ecx, eax
0x180002f22  cmp     dword ptr [rdx+8], 1E3603Bh
0x180002f29  lea     eax, [rcx-1]
0x180002f2c  cmovnz  eax, ecx
0x180002f2f  cmp     dword ptr [rdx+0Ch], 1E3603Bh
0x180002f36  mov     rdx, [rdx+10h]
0x180002f3a  lea     ebp, [rax-1]
0x180002f3d  cmovnz  ebp, eax
0x180002f40  test    rdx, rdx
0x180002f43  jnz     short loc_180002F09
0x180002f45  xor     r15d, r15d
0x180002f48  test    ebp, ebp
0x180002f4a  jg      loc_1800035F6
0x180002f50  movups  xmm0, xmmword ptr [rsi]
0x180002f53  xor     ebp, ebp
0x180002f55  movups  [rsp+88h+var_68], xmm0
0x180002f5a  movups  xmm1, xmmword ptr [rsi+10h]
0x180002f5e  movups  [rsp+88h+var_58], xmm1
0x180002f63  movups  xmm0, xmmword ptr [rsi+20h]
0x180002f67  movups  [rsp+88h+var_48], xmm0
0x180002f6c  movsd   xmm1, qword ptr [rsi+30h]
0x180002f71  movsd   [rsp+88h+var_38], xmm1
0x180002f77  mov     [rsi+10h], rbp
0x180002f7b  mov     dword ptr [rsi+0Ch], 1E3603Bh
0x180002f82  mov     [rsi+30h], rbp
0x180002f86  mov     dword ptr [rsi+8], 1E3603Bh
0x180002f8d  mov     [rsi+28h], rbp
0x180002f91  mov     dword ptr [rsi+4], 1E3603Bh
0x180002f98  mov     [rsi+20h], rbp
0x180002f9c  mov     dword ptr [rsi], 1E3603Bh
0x180002fa2  mov     [rsi+18h], rbp
0x180002fa6  cmp     [r13+99h], bpl
0x180002fad  jz      short loc_180002FC7
0x180002faf  mov     edx, [rdi]
0x180002fb1  mov     eax, edx
0x180002fb3  lea     ecx, [rdx-10000h]
0x180002fb9  and     ecx, 0FFFF0000h
0x180002fbf  lock cmpxchg [rdi], ecx
0x180002fc3  cmp     edx, eax
0x180002fc5  jmp     short loc_180002FAD
0x180002fc7  mov     eax, [r13+7Ch]
0x180002fcb  test    [r13+4Ch], eax
0x180002fcf  jz      loc_180003663
0x180002fd5  mov     edi, [r13+74h]
0x180002fd9  mov     eax, edi
0x180002fdb  imul    eax, [r13+48h]
0x180002fe0  shr     eax, 1
0x180002fe2  cmp     edi, 8
0x180002fe5  ja      loc_18000335E
0x180002feb  cmp     [r13+99h], bpl
0x180002ff2  jz      short loc_18000300F
0x180002ff4  mov     eax, [r13+1Ch]
0x180002ff8  mov     ecx, ebp
0x180002ffa  dec     eax
0x180002ffc  test    al, 3
0x180002ffe  cmovnz  ecx, eax
0x180003001  mov     eax, ecx
0x180003003  xchg    eax, [r13+1Ch]
0x180003007  test    ecx, ecx
0x180003009  jz      loc_180003421
0x18000300f  lea     rdx, [rsp+88h+var_68]
0x180003014  mov     rax, [r14+10h]
0x180003018  test    rax, rax
0x18000301b  jnz     loc_18000313F
0x180003021  cmp     dword ptr [r14], 1E3603Bh
0x180003028  mov     ecx, ebp
0x18000302a  jz      short loc_180003040
0x18000302c  cmp     dword ptr [r14+4], 1E3603Bh
0x180003034  mov     ecx, r12d
0x180003037  jnz     loc_1800033F1
0x18000303d  nop     dword ptr [rax]
0x180003040  cmp     dword ptr [rdx], 1E3603Bh
0x180003046  jnz     loc_18000326E
0x18000304c  cmp     dword ptr [rdx+4], 1E3603Bh
0x180003053  jnz     loc_1800032E1
0x180003059  cmp     dword ptr [rdx+8], 1E3603Bh
0x180003060  jnz     loc_18000317E
0x180003066  cmp     dword ptr [rdx+0Ch], 1E3603Bh
0x18000306d  jnz     loc_1800031F3
0x180003073  mov     rax, rdx
0x180003076  lea     r8, [rdx+10h]
0x18000307a  mov     rdx, [rdx+10h]
0x18000307e  lea     r9, [rsp+88h+var_68]
0x180003083  cmp     rax, r9
0x180003086  jnz     loc_1800037B2
0x18000308c  test    rdx, rdx
0x18000308f  jnz     short loc_180003040
0x180003091  test    r15, r15
0x180003094  jnz     loc_1800037BD
0x18000309a  cmp     [r13+99h], bpl
0x1800030a1  jz      short loc_1800030BB
0x1800030a3  mov     ecx, [rbx]
0x1800030a5  mov     eax, ecx
0x1800030a7  lea     edx, [rcx-10000h]
0x1800030ad  and     edx, 0FFFF0000h
0x1800030b3  lock cmpxchg [rbx], edx
0x1800030b7  cmp     ecx, eax
0x1800030b9  jmp     short loc_1800030A1
0x1800030bb  xor     eax, eax
0x1800030bd  mov     r14, [rsp+88h+var_20]
0x1800030c2  mov     r12, [rsp+88h+var_18]
0x1800030c7  mov     rdi, [rsp+88h+arg_18]
0x1800030cf  mov     rsi, [rsp+88h+arg_10]
0x1800030d7  mov     rbp, [rsp+88h+arg_8]
0x1800030df  mov     r15, [rsp+88h+var_28]
0x1800030e4  mov     rcx, [rsp+88h+var_30]
0x1800030e9  xor     rcx, rsp; StackCookie
0x1800030ec  call    __security_check_cookie
0x1800030f1  add     rsp, 78h
0x1800030f5  pop     r13
0x1800030f7  pop     rbx
0x1800030f8  retn
0x1800030f9  mov     edx, [rbx]
0x1800030fb  mov     eax, edx
0x1800030fd  lea     ecx, [rdx+10000h]
0x180003103  lock cmpxchg [rbx], ecx
0x180003107  cmp     edx, eax
0x180003109  jnz     short loc_1800030F9
0x18000310b  movzx   edx, r12b; bool
0x18000310f  mov     rcx, rbx; this
0x180003112  call    ?_LockSpin@CReaderWriterLock2@@AEAAX_N@Z; CReaderWriterLock2::_LockSpin(bool)
0x180003117  jmp     loc_180002E84
0x18000311c  mov     edx, [rdi]
0x18000311e  mov     eax, edx
0x180003120  lea     ecx, [rdx+10000h]
0x180003126  lock cmpxchg [rdi], ecx
0x18000312a  cmp     edx, eax
0x18000312c  jnz     short loc_18000311C
0x18000312e  movzx   edx, r12b; bool
0x180003132  mov     rcx, rdi; this
0x180003135  call    ?_LockSpin@CReaderWriterLock2@@AEAAX_N@Z; CReaderWriterLock2::_LockSpin(bool)
0x18000313a  jmp     loc_180002EB3
0x18000313f  cmp     dword ptr [r14], 1E3603Bh
0x180003146  jz      loc_180003021
0x18000314c  cmp     dword ptr [r14+4], 1E3603Bh
0x180003154  jz      loc_180003021
0x18000315a  cmp     dword ptr [r14+8], 1E3603Bh
0x180003162  jz      loc_180003021
0x180003168  cmp     dword ptr [r14+0Ch], 1E3603Bh
0x180003170  jz      loc_180003021
0x180003176  mov     r14, rax
0x180003179  jmp     loc_180003014
0x18000317e  cmp     ecx, 4
0x180003181  jz      loc_180003559
0x180003187  cmp     ecx, 3
0x18000318a  ja      loc_180003073
0x180003190  test    r14, r14
0x180003193  jz      loc_180003073
0x180003199  mov     eax, ecx
0x18000319b  cmp     [r14+rax*8+18h], rbp
0x1800031a0  lea     r8, [r14+rax*8]
0x1800031a4  jnz     loc_180003073
0x1800031aa  cmp     dword ptr [r14+rax*4], 1E3603Bh
0x1800031b2  lea     r9, [r14+rax*4]
0x1800031b6  jnz     loc_180003073
0x1800031bc  mov     eax, [rdx+8]
0x1800031bf  mov     [r9], eax
0x1800031c2  mov     rax, [rdx+28h]
0x1800031c6  mov     [r8+18h], rax
0x1800031ca  mov     dword ptr [rdx+8], 1E3603Bh
0x1800031d1  mov     [rdx+28h], rbp
0x1800031d5  inc     ecx
0x1800031d7  cmp     ecx, 4
0x1800031da  jz      loc_180003066
0x1800031e0  movsxd  rax, ecx
0x1800031e3  cmp     dword ptr [r14+rax*4], 1E3603Bh
0x1800031eb  jz      loc_180003066
0x1800031f1  jmp     short loc_1800031D5
0x1800031f3  cmp     ecx, 4
0x1800031f6  jz      loc_180003586
0x1800031fc  cmp     ecx, 3
0x1800031ff  ja      loc_180003073
0x180003205  test    r14, r14
0x180003208  jz      loc_180003073
0x18000320e  mov     eax, ecx
0x180003210  cmp     [r14+rax*8+18h], rbp
0x180003215  lea     r8, [r14+rax*8]
0x180003219  jnz     loc_180003073
0x18000321f  cmp     dword ptr [r14+rax*4], 1E3603Bh
0x180003227  lea     r9, [r14+rax*4]
0x18000322b  jnz     loc_180003073
0x180003231  mov     eax, [rdx+0Ch]
0x180003234  mov     [r9], eax
0x180003237  mov     rax, [rdx+30h]
0x18000323b  mov     [r8+18h], rax
0x18000323f  mov     dword ptr [rdx+0Ch], 1E3603Bh
0x180003246  mov     [rdx+30h], rbp
0x18000324a  nop     word ptr [rax+rax+00h]
0x180003250  inc     ecx
  ... truncated ...
```
