# RtlpLocalInfoAllocFromCache

- ea: `0x18003d5f0`
- end: `0x18003e21e`
- name: `RtlpLocalInfoAllocFromCache`
- size: `3118`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `service_task, broker_com_uri`

## callers

- `0x18003ee4c`

## callees

- `0x18003d390`
- `0x18003d430`
- `0x18003d5f0`
- `0x18003e370`
- `0x18003e4c0`
- `0x18003e554`
- `0x18003e658`
- `0x1800526f0`
- `0x18011c718`
- `0x180162040`
- `0x180162080`
- `0x1801620f0`

## pseudocode

```c
unsigned __int64 __fastcall RtlpLocalInfoAllocFromCache(unsigned __int16 *a1, char a2)
{
  unsigned __int16 *v2; // r15
  __int64 v3; // rbx
  int v4; // r15d
  __int64 v5; // r14
  unsigned int v6; // r9d
  unsigned int i; // edx
  signed __int32 v8; // r8d
  unsigned __int16 *v9; // rax
  volatile signed __int32 *v10; // rdi
  unsigned int v11; // r14d
  _SLIST_ENTRY *v12; // rbx
  struct _SLIST_ENTRY *v13; // r15
  union _SLIST_HEADER *v14; // rbp
  PSLIST_ENTRY v15; // rsi
  __int64 v16; // r9
  signed __int32 v17; // eax
  __int64 *v18; // r8
  _DWORD *v19; // rcx
  __int64 v20; // rcx
  char v21; // dl
  _DWORD *v22; // rcx
  __int64 v23; // rcx
  _DWORD *v24; // rcx
  __int64 v25; // rcx
  signed __int32 v26; // eax
  __int64 *v27; // r9
  unsigned int m; // r8d
  __int64 v29; // rax
  volatile signed __int32 *v30; // rdx
  __int64 *v31; // rcx
  __int64 v32; // rcx
  __int64 v33; // rsi
  struct _TEB *v34; // r9
  __int64 v35; // r11
  unsigned __int64 v36; // r10
  char v37; // cl
  int v38; // r11d
  unsigned __int64 v39; // rdx
  __int64 v40; // rdi
  _QWORD *v41; // r9
  unsigned int v42; // r11d
  __int64 v45; // rax
  int v48; // r9d
  unsigned __int64 v49; // r8
  volatile signed __int64 *v50; // rsi
  unsigned int v51; // ebp
  __int64 j; // rbx
  __int64 v53; // rdx
  union _SLIST_HEADER *v54; // rbp
  PSLIST_ENTRY v55; // rax
  _QWORD **v56; // rbx
  __int64 v57; // rcx
  char v58; // r10
  _DWORD *SharedData; // rcx
  __int64 v60; // rcx
  _DWORD *v61; // rcx
  __int64 v62; // rcx
  _QWORD *v63; // rbp
  unsigned int v64; // edx
  __int64 v65; // rax
  unsigned __int64 v67; // rax
  signed __int64 v68; // rcx
  unsigned __int64 v69; // rtt
  _QWORD *v70; // rax
  PSLIST_ENTRY v71; // r14
  __int64 v72; // rcx
  __int64 v73; // rdi
  __int64 v74; // rdx
  __int64 v75; // rcx
  __int64 v76; // r8
  __int64 v77; // r9
  char *v78; // rcx
  __int64 v79; // rax
  signed __int32 v80; // eax
  __int64 *v81; // r9
  unsigned int k; // r8d
  __int64 v83; // rax
  volatile signed __int32 *v84; // rdx
  __int64 *v85; // rcx
  __int64 v86; // rcx
  _QWORD **v87; // rdx
  PSLIST_ENTRY v88; // rax
  __int64 v89; // rcx
  __int64 v92; // [rsp+80h] [rbp+18h]

  v2 = a1;
LABEL_2:
  while ( 2 )
  {
    v3 = *((_QWORD *)v2 + 1);
    if ( v3 )
    {
      v4 = 0;
      v5 = *(_QWORD *)(*(_QWORD *)a1 + 24LL);
      if ( (HIWORD(*(_DWORD *)(v3 + 32)) & 0x8000u) != 0 )
      {
        v4 = 1;
        v73 = v5 + 4LL * a1[86];
        if ( (*(_BYTE *)(v73 + 679) & 1) == 0
          && (int)RtlpAffinitizeSegmentInfoForBucket(*(_QWORD *)(*(_QWORD *)a1 + 24LL), *(unsigned __int8 *)(v73 + 678)) >= 0 )
        {
          *(_BYTE *)(v73 + 679) |= 1u;
          v78 = (unsigned int)RtlGetCurrentServiceSessionId(v75, v74, v76, v77)
              ? (char *)NtCurrentPeb()->SharedData + 550
              : (char *)2147353472;
          if ( *v78 && (NtCurrentPeb()->TracingFlags & 1) != 0 )
            RtlpLogHeapAffinityManagerEnable(*(_QWORD *)(v5 + 24), *(unsigned __int8 *)(v73 + 678));
        }
      }
      v6 = 0;
      if ( MEMORY[0x7FFE036A] > 1u )
        v6 = 100;
      for ( i = 0; ; ++i )
      {
        if ( i > v6 )
          goto LABEL_59;
        v8 = *(_DWORD *)(v3 + 32);
        if ( (v8 & 0x80000000) == 0 )
        {
          if ( !(_WORD)v8 )
            goto LABEL_59;
          if ( v8 == _InterlockedCompareExchange((volatile signed __int32 *)(v3 + 32), v8 | 0x80000000, v8) )
            break;
        }
      }
      if ( v8 == -1 )
        goto LABEL_59;
      v33 = *(_QWORD *)(v3 + 8);
      if ( !v33 || *(unsigned __int16 **)v3 != a1 || !(_WORD)v8 )
      {
        *(_DWORD *)(v3 + 32) = v8;
        goto LABEL_59;
      }
      v34 = NtCurrentTeb();
      v35 = BYTE2(v34->HeapThreadData);
      v36 = *((unsigned __int8 *)RtlpSearchWidth + a1[86]);
      if ( (_BYTE)v35 == HIBYTE(v34->HeapThreadData) )
      {
        v67 = qword_1801C5F00;
        do
        {
          v68 = v67
              ^ (v67 >> 12)
              ^ ((v67 ^ (v67 >> 12)) << 25)
              ^ ((v67 ^ (v67 >> 12) ^ ((v67 ^ (v67 >> 12)) << 25)) >> 27);
          v69 = v67;
          v67 = _InterlockedCompareExchange64(&qword_1801C5F00, v68, v67);
        }
        while ( v69 != v67 );
        v37 = 29 * v68;
        HIBYTE(v34->HeapThreadData) = v37;
      }
      else
      {
        v37 = BYTE2(v34->HeapThreadData);
      }
      BYTE2(v34->HeapThreadData) = v37 + 1;
      v38 = *((unsigned __int8 *)RtlpLowFragHeapRandomData + v35);
      v39 = *(_QWORD *)(v33 + 32);
      v40 = *(_QWORD *)(v33 + 40);
      if ( v39 >= 0x40 )
      {
        v63 = (_QWORD *)(v40 + 8 * ((v39 - 1) >> 6));
        v41 = (_QWORD *)(v40 + 8 * ((unsigned __int64)(unsigned int)(v8 >> 16) >> 6));
        do
        {
          if ( *v41 != -1 )
            break;
          v70 = v41++;
          if ( v70 == v63 )
            v41 = *(_QWORD **)(v33 + 40);
        }
        while ( v41 != (_QWORD *)(v40 + 8 * ((unsigned __int64)(unsigned int)(v8 >> 16) >> 6)) );
        if ( v41 == v63 )
        {
          v64 = v39 & 0x3F;
          if ( v64 )
          {
            if ( v64 < v36 )
              LODWORD(v36) = *(_DWORD *)(v33 + 32) & 0x3F;
          }
        }
      }
      else
      {
        v41 = *(_QWORD **)(v33 + 40);
        if ( v39 < v36 )
          LODWORD(v36) = *(_QWORD *)(v33 + 32);
      }
      v42 = (unsigned int)(v36 * v38) >> 8;
      if ( (unsigned int)v36 >= 0x40 )
      {
        v45 = -1;
      }
      else
      {
        _RAX = ~*v41;
        __asm { tzcnt   rdx, rax }
        LOBYTE(v42) = _RDX + v42;
        v45 = ((1LL << v36) - 1) << _RDX;
      }
      _RAX = ~__ROR8__(*v41 | ~v45, v42);
      __asm { tzcnt   rax, rax }
      LODWORD(_RAX) = ((_BYTE)v42 + (_BYTE)_RAX) & 0x3F;
      *v41 |= 1LL << _RAX;
      v48 = _RAX + ((unsigned int)(((__int64)v41 - *(_QWORD *)(v33 + 40)) >> 3) << 6);
      *(_DWORD *)(v3 + 32) = (v48 << 16) | ((unsigned __int16)v8 - 1);
      v49 = v48 * ((*(_DWORD *)(v33 + 24) ^ (unsigned int)v5 ^ (unsigned int)v33 ^ (unsigned int)RtlpLFHKey) >> 16)
          + v33
          + ((unsigned __int16)*(_DWORD *)(v33 + 24)
           ^ (unsigned __int16)RtlpLFHKey
           ^ (unsigned __int16)v5
           ^ (unsigned __int64)(unsigned __int16)v33);
      if ( (*(_BYTE *)(v49 + 15) & 0x3F) != 0 )
      {
        RtlpLogHeapFailure(15, *(_QWORD *)(*(_QWORD *)(*(_QWORD *)a1 + 24LL) + 24LL), v49, 0, 0, 0);
LABEL_59:
        v49 = 0;
      }
      if ( v4 && HIDWORD(RtlpAffinityState) + 1 < (unsigned int)RtlpAffinityState )
        _InterlockedCompareExchange(
          (_DWORD *)&RtlpAffinityState + 1,
          2 * (HIDWORD(RtlpAffinityState) + 1) - 1,
          SHIDWORD(RtlpAffinityState));
      if ( v49 )
        return v49;
      v2 = a1;
    }
    v92 = *(_QWORD *)v2;
LABEL_64:
    v10 = 0;
    while ( 2 )
    {
      v50 = 0;
      v51 = 0;
      for ( j = 0; j != 16; ++j )
      {
        v53 = *(_QWORD *)&v2[4 * j + 8];
        if ( v53 && *(unsigned __int16 *)(v53 + 32) > v51 )
        {
          if ( (RtlpLowFragHeapGlobalFlags & 4) != 0
            || (v65 = v2[86], (unsigned int)v65 > 0x70)
            || *((_DWORD *)v2 + 40) < 16 * (unsigned int)(unsigned __int16)RtlpBucketSizeIndexReuseThreshold[v65]
            || (v58 = 1, (unsigned int)(*(_WORD *)(v53 + 40) >> 2) <= *(_WORD *)(v53 + 32)) )
          {
            v58 = 0;
          }
          SharedData = NtCurrentPeb()->SharedData;
          if ( SharedData && *SharedData )
            v60 = (__int64)NtCurrentPeb()->SharedData + 560;
          else
            v60 = 2147353482;
          if ( !*(_BYTE *)v60 )
          {
            v61 = NtCurrentPeb()->SharedData;
            if ( v61 && *v61 )
              v62 = (__int64)NtCurrentPeb()->SharedData + 550;
            else
              v62 = 2147353472;
            if ( !*(_BYTE *)v62 || (NtCurrentPeb()->TracingFlags & 1) == 0 )
            {
              if ( v58 )
                continue;
LABEL_87:
              v10 = *(volatile signed __int32 **)&v2[4 * j + 8];
              v50 = (volatile signed __int64 *)&v2[4 * j + 8];
              v51 = *(unsigned __int16 *)(v53 + 32);
              continue;
            }
          }
          if ( !v58 )
            goto LABEL_87;
          RtlpLogHeapReuseThresholdActivate(
            *(_QWORD *)(*(_QWORD *)(*(_QWORD *)v2 + 24LL) + 24LL),
            *(_QWORD *)(v53 + 8),
            v2[86],
            *(unsigned __int16 *)(v53 + 32));
        }
      }
      if ( v50 )
      {
        v54 = (union _SLIST_HEADER *)(*(_QWORD *)(*(_QWORD *)(v92 + 24) + 8LL * v2[86] + 1192) + 144LL);
        while ( 1 )
        {
          v55 = RtlpInterlockedPopEntrySList(v54);
          v56 = (_QWORD **)v55;
          if ( !v55 )
            break;
          v71 = v55;
          v56 = (_QWORD **)&v55[-3];
          if ( (*((_DWORD *)&v55[-1].Next + 3) & 1) != 0 )
          {
            if ( !(unsigned int)RtlpSetSegmentInfo(v56, v2) )
            {
              RtlpInterlockedPushEntrySList(v54, v71);
              v56 = 0;
            }
            break;
          }
          _m_prefetchw((char *)v56 + 44);
          if ( _InterlockedAnd((volatile signed __int32 *)v56 + 11, 0xFFFFFFFD) == 2 )
          {
            v72 = **v56;
            *v56 = 0;
            RtlpInterlockedPushEntrySList(v72, v55);
          }
        }
        if ( v10 != (volatile signed __int32 *)_InterlockedCompareExchange64(
                                                 v50,
                                                 (signed __int64)v56,
                                                 (signed __int64)v10) )
        {
          if ( v56 )
            RtlpInterlockedPushEntrySList(v54, v56 + 6);
          continue;
        }
        if ( !v56 )
          v2[87] = (unsigned __int8)(((char *)v50 - (char *)v2 - 16) >> 3);
        v9 = v2 + 86;
        if ( v10 )
        {
          _m_prefetchw((const void *)(v10 + 11));
          if ( _InterlockedAnd(v10 + 11, 0xFFFFFFFD) != 2 )
            goto LABEL_16;
          v57 = **(_QWORD **)v10;
          *(_QWORD *)v10 = 0;
          RtlpInterlockedPushEntrySList(v57, v10 + 12);
          goto LABEL_64;
        }
      }
      else
      {
        v9 = v2 + 86;
        v10 = 0;
      }
      break;
    }
    v11 = 0;
    v12 = 0;
    v13 = 0;
    v14 = (union _SLIST_HEADER *)(*(_QWORD *)(*(_QWORD *)(v92 + 24) + 8LL * *v9 + 1192) + 144LL);
    v15 = RtlpInterlockedPopEntrySList(v14);
    if ( !v15 )
      goto LABEL_14;
    while ( 2 )
    {
      v10 = (volatile signed __int32 *)&v15[-3];
      if ( (*((_DWORD *)&v15[-1].Next + 3) & 1) == 0 )
      {
        _m_prefetchw((const void *)(v10 + 11));
        if ( _InterlockedAnd(v10 + 11, 0xFFFFFFFD) != 2 )
          goto LABEL_179;
LABEL_182:
        v89 = **(_QWORD **)v10;
        *(_QWORD *)v10 = 0;
        RtlpInterlockedPushEntrySList(v89, v15);
        goto LABEL_179;
      }
      if ( !(unsigned int)RtlpSetSegmentInfo(&v15[-3], a1) )
      {
        v15->Next = v12;
        v88 = v15;
        v12 = v15;
        if ( v11 )
          v88 = v13;
        ++v11;
        v13 = v88;
        goto LABEL_179;
      }
      _m_prefetchw((const void *)(v10 + 11));
      if ( _InterlockedAnd(v10 + 11, 0xFFFFFFFD) == 2 )
        goto LABEL_182;
      if ( (unsigned __int8)RtlpIsSubSegmentReuseable(a1, &v15[-3]) )
        break;
LABEL_179:
      v10 = 0;
      v15 = RtlpInterlockedPopEntrySList(v14);
      if ( v15 )
        continue;
      break;
    }
    if ( v11 )
      InterlockedPushListSList(v14, v12, v13, v11);
LABEL_14:
    if ( v10 )
    {
      v2 = a1;
LABEL_16:
      *((_BYTE *)v10 + 43) = a2;
      do
      {
        v17 = *((_DWORD *)v10 + 11);
        if ( !v17 || (v17 & 6) != 0 )
          goto LABEL_2;
      }
      while ( v17 != _InterlockedCompareExchange(v10 + 11, v17 | 6, v17) );
      v18 = *(__int64 **)v10;
      if ( *(unsigned __int16 **)v10 != v2 )
      {
        _m_prefetchw((const void *)(v10 + 11));
        if ( _InterlockedAnd(v10 + 11, 0xFFFFFFF9) == 6 )
        {
LABEL_163:
          v87 = (_QWORD **)(v10 + 12);
          v86 = **(_QWORD **)v10;
          *(_QWORD *)v10 = 0;
          goto LABEL_164;
        }
        if ( !(unsigned __int8)RtlpIsSubSegmentReuseable(v18, v10) )
          continue;
        do
        {
          v80 = *((_DWORD *)v10 + 11);
          if ( !v80 || (v80 & 2) != 0 )
            goto LABEL_2;
        }
        while ( v80 != _InterlockedCompareExchange(v10 + 11, v80 | 2, v80) );
        v81 = *(__int64 **)v10;
        for ( k = 0; ; ++k )
        {
          if ( k >= 0x10 )
          {
LABEL_160:
            RtlpInterlockedPushEntrySList(
              *(_QWORD *)(*(_QWORD *)(**(_QWORD **)v10 + 24LL)
                        + 8LL * *(unsigned __int16 *)(*(_QWORD *)v10 + 172LL)
                        + 1192)
            + 144LL,
              v10 + 12);
            goto LABEL_2;
          }
          v83 = ((_BYTE)k + (unsigned __int8)*((_WORD *)v81 + 87)) & 0xF;
          v84 = (volatile signed __int32 *)v81[v83 + 2];
          v85 = &v81[v83];
          if ( v84 )
          {
            if ( (v84[11] & 1) == 0
              && v84 == (volatile signed __int32 *)_InterlockedCompareExchange64(
                                                     v85 + 2,
                                                     (signed __int64)v10,
                                                     (signed __int64)v84) )
            {
              _m_prefetchw((const void *)(v84 + 11));
              if ( _InterlockedAnd(v84 + 11, 0xFFFFFFFD) != 2 )
                goto LABEL_2;
              v86 = **(_QWORD **)v84;
              *(_QWORD *)v84 = 0;
              v87 = (_QWORD **)(v84 + 12);
LABEL_164:
              RtlpInterlockedPushEntrySList(v86, v87);
              goto LABEL_2;
            }
          }
          else if ( !_InterlockedCompareExchange64(v85 + 2, (signed __int64)v10, 0) )
          {
            goto LABEL_2;
          }
        }
      }
      v19 = NtCurrentPeb()->SharedData;
      if ( v19 && *v19 )
        v20 = (__int64)NtCurrentPeb()->SharedData + 550;
      else
        v20 = 2147353472;
      if ( *(_BYTE *)v20 && (NtCurrentPeb()->TracingFlags & 1) != 0 )
        RtlpLogHeapSubSegmentActivate(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)v2 + 24LL) + 24LL), *((_QWORD *)v10 + 1));
      v10 = (volatile signed __int32 *)_InterlockedExchange64((volatile __int64 *)v2 + 1, (__int64)v10);
      if ( v10 )
      {
        _m_prefetchw((const void *)(v10 + 11));
        if ( _InterlockedAnd(v10 + 11, 0xFFFFFFF9) == 6 )
          goto LABEL_163;
        if ( *((_WORD *)v10 + 16) )
        {
          if ( (RtlpLowFragHeapGlobalFlags & 4) != 0
            || (v79 = v2[86], (unsigned int)v79 > 0x70)
            || *((_DWORD *)v2 + 40) < 16 * (unsigned int)(unsigned __int16)RtlpBucketSizeIndexReuseThreshold[v79]
            || (v21 = 1, (unsigned int)(*((_WORD *)v10 + 20) >> 2) <= *((_WORD *)v10 + 16)) )
          {
            v21 = 0;
          }
          v22 = NtCurrentPeb()->SharedData;
          if ( v22 && *v22 )
            v23 = (__int64)NtCurrentPeb()->SharedData + 560;
          else
            v23 = 2147353482;
          if ( *(_BYTE *)v23
            || ((v24 = NtCurrentPeb()->SharedData) == 0 || !*v24
              ? (v25 = 2147353472)
              : (v25 = (__int64)NtCurrentPeb()->SharedData + 550),
                *(_BYTE *)v25 && (NtCurrentPeb()->TracingFlags & 1) != 0) )
          {
            if ( !v21 )
              goto LABEL_36;
            RtlpLogHeapReuseThresholdActivate(
              *(_QWORD *)(*(_QWORD *)(*(_QWORD *)v2 + 24LL) + 24LL),
              *((_QWORD *)v10 + 1),
              v2[86],
              v16);
          }
          else if ( !v21 )
          {
LABEL_36:
            while ( 1 )
            {
              v26 = *((_DWORD *)v10 + 11);
              if ( !v26 || (v26 & 2) != 0 )
                break;
              if ( v26 == _InterlockedCompareExchange(v10 + 11, v26 | 2, v26) )
              {
                v27 = *(__int64 **)v10;
                for ( m = 0; m < 0x10; ++m )
                {
                  v29 = ((_BYTE)m + (unsigned __int8)*((_WORD *)v27 + 87)) & 0xF;
                  v30 = (volatile signed __int32 *)v27[v29 + 2];
                  v31 = &v27[v29];
                  if ( v30 )
                  {
                    if ( (v30[11] & 1) == 0
                      && v30 == (volatile signed __int32 *)_InterlockedCompareExchange64(
                                                             v31 + 2,
                                                             (signed __int64)v10,
                                                             (signed __int64)v30) )
                    {
                      _m_prefetchw((const void *)(v30 + 11));
                      if ( _InterlockedAnd(v30 + 11, 0xFFFFFFFD) == 2 )
                      {
                        v32 = **(_QWORD **)v30;
                        *(_QWORD *)v30 = 0;
                        RtlpInterlockedPushEntrySList(v32, v30 + 12);
                      }
                      goto LABEL_2;
                    }
                  }
                  else if ( !_InterlockedCompareExchange64(v31 + 2, (signed __int64)v10, 0) )
                  {
                    goto LABEL_2;
                  }
                }
                goto LABEL_160;
              }
            }
          }
        }
      }
      continue;
    }
    return 0;
  }
}

```

## disassembly

```asm
0x18003d5f0  mov     [rsp+arg_18], rbx
0x18003d5f5  mov     [rsp+arg_8], edx
0x18003d5f9  mov     [rsp+arg_0], rcx
0x18003d5fe  push    rbp
0x18003d5ff  push    rsi
0x18003d600  push    rdi
0x18003d601  push    r12
0x18003d603  push    r13
0x18003d605  push    r14
0x18003d607  push    r15
0x18003d609  sub     rsp, 30h
0x18003d60d  mov     r15, rcx
0x18003d610  lea     rbp, cs:180000000h
0x18003d617  mov     esi, 64h ; 'd'
0x18003d61c  mov     r10d, 8000h
0x18003d622  mov     rbx, [r15+8]
0x18003d626  test    rbx, rbx
0x18003d629  jz      loc_18003DA38
0x18003d62f  mov     ecx, [rbx+20h]
0x18003d632  xor     r15d, r15d
0x18003d635  mov     r13, [rsp+68h+arg_0]
0x18003d63a  shr     ecx, 10h
0x18003d63d  mov     rax, [r13+0]
0x18003d641  mov     r14, [rax+18h]
0x18003d645  test    cx, cx
0x18003d648  js      loc_18003DDEB
0x18003d64e  xor     r9d, r9d
0x18003d651  cmp     word ptr ds:7FFE036Ah, 1
0x18003d65a  cmova   r9d, esi
0x18003d65e  xor     edx, edx
0x18003d660  cmp     edx, r9d
0x18003d663  ja      loc_18003DC5F
0x18003d669  mov     r8d, [rbx+20h]
0x18003d66d  mov     eax, r8d
0x18003d670  shr     eax, 10h
0x18003d673  test    r10w, ax
0x18003d677  jnz     short loc_18003D69A
0x18003d679  test    r8w, r8w
0x18003d67d  jz      loc_18003DA1E
0x18003d683  mov     ecx, r8d
0x18003d686  mov     eax, r8d
0x18003d689  or      ecx, 80000000h
0x18003d68f  lock cmpxchg [rbx+20h], ecx
0x18003d694  jz      loc_18003D8B6
0x18003d69a  inc     edx
0x18003d69c  jmp     short loc_18003D660
0x18003d69e  lea     rax, [r15+0ACh]
0x18003d6a5  xor     edi, edi
0x18003d6a7  movzx   ecx, word ptr [rax]
0x18003d6aa  xor     r14d, r14d
0x18003d6ad  mov     rax, [r13+18h]
0x18003d6b1  xor     ebx, ebx
0x18003d6b3  xor     r15d, r15d
0x18003d6b6  mov     rbp, [rax+rcx*8+4A8h]
0x18003d6be  add     rbp, 90h
0x18003d6c5  mov     rcx, rbp; ListHead
0x18003d6c8  call    RtlpInterlockedPopEntrySList
0x18003d6cd  mov     rsi, rax
0x18003d6d0  test    rax, rax
0x18003d6d3  jnz     loc_18003E214
0x18003d6d9  test    rdi, rdi
0x18003d6dc  jz      loc_18003DDE4
0x18003d6e2  mov     r15, [rsp+68h+arg_0]
0x18003d6e7  mov     r12d, [rsp+68h+arg_8]
0x18003d6ec  lea     rbp, cs:180000000h
0x18003d6f3  mov     [rdi+2Bh], r12b
0x18003d6f7  nop     word ptr [rax+rax+00000000h]
0x18003d700  mov     eax, [rdi+2Ch]
0x18003d703  mov     esi, 64h ; 'd'
0x18003d708  mov     r10d, 8000h
0x18003d70e  test    eax, eax
0x18003d710  jz      loc_18003D622
0x18003d716  test    al, 6
0x18003d718  jnz     loc_18003D622
0x18003d71e  mov     ecx, eax
0x18003d720  or      ecx, 6
0x18003d723  lock cmpxchg [rdi+2Ch], ecx
0x18003d728  jnz     short loc_18003D700
0x18003d72a  mov     r8, [rdi]
0x18003d72d  cmp     r8, r15
0x18003d730  jnz     loc_18003DF82
0x18003d736  mov     rax, gs:60h
0x18003d73f  mov     rcx, [rax+90h]
0x18003d746  test    rcx, rcx
0x18003d749  jnz     loc_18003E0FB
0x18003d74f  mov     ecx, 7FFE0380h
0x18003d754  cmp     byte ptr [rcx], 0
0x18003d757  jnz     loc_18003E120
0x18003d75d  xchg    rdi, [r15+8]
0x18003d761  mov     r10d, 8000h
0x18003d767  test    rdi, rdi
0x18003d76a  jz      loc_18003D622
0x18003d770  prefetchw byte ptr [rdi+2Ch]
0x18003d774  mov     eax, [rdi+2Ch]
0x18003d777  mov     ecx, eax
0x18003d779  and     ecx, 0FFFFFFF9h
0x18003d77c  lock cmpxchg [rdi+2Ch], ecx
0x18003d781  jnz     short loc_18003D777
0x18003d783  cmp     eax, 6
0x18003d786  jz      loc_18003E0E0
0x18003d78c  movzx   eax, word ptr [rdi+20h]
0x18003d790  test    ax, ax
0x18003d793  jz      loc_18003D622
0x18003d799  test    byte ptr cs:RtlpLowFragHeapGlobalFlags, 4
0x18003d7a0  jz      loc_18003DEB2
0x18003d7a6  xor     dl, dl
0x18003d7a8  mov     rax, gs:60h
0x18003d7b1  mov     rcx, [rax+90h]
0x18003d7b8  test    rcx, rcx
0x18003d7bb  jnz     loc_18003DF38
0x18003d7c1  mov     ecx, 7FFE038Ah
0x18003d7c6  cmp     byte ptr [rcx], 0
0x18003d7c9  jnz     loc_18003DF0F
0x18003d7cf  mov     rax, gs:60h
0x18003d7d8  mov     rcx, [rax+90h]
0x18003d7df  test    rcx, rcx
0x18003d7e2  jnz     loc_18003DF5D
0x18003d7e8  mov     ecx, 7FFE0380h
0x18003d7ed  cmp     byte ptr [rcx], 0
0x18003d7f0  jnz     loc_18003DEF9
0x18003d7f6  test    dl, dl
0x18003d7f8  jnz     loc_18003D622
0x18003d7fe  xchg    ax, ax
0x18003d800  mov     eax, [rdi+2Ch]
0x18003d803  mov     esi, 64h ; 'd'
0x18003d808  mov     r10d, 8000h
0x18003d80e  test    eax, eax
0x18003d810  jz      loc_18003D622
0x18003d816  test    al, 2
0x18003d818  jnz     loc_18003D622
0x18003d81e  mov     ecx, eax
0x18003d820  or      ecx, 2
0x18003d823  lock cmpxchg [rdi+2Ch], ecx
0x18003d828  jnz     short loc_18003D800
0x18003d82a  mov     r9, [rdi]
0x18003d82d  xor     r8d, r8d
0x18003d830  cmp     r8d, 10h
0x18003d834  jnb     loc_18003E092
0x18003d83a  movzx   eax, word ptr [r9+0AEh]
0x18003d842  add     eax, r8d
0x18003d845  and     eax, 0Fh
0x18003d848  mov     rdx, [r9+rax*8+10h]
0x18003d84d  lea     rcx, [r9+rax*8]
0x18003d851  test    rdx, rdx
0x18003d854  jz      loc_18003E071
0x18003d85a  mov     eax, [rdx+2Ch]
0x18003d85d  test    al, 1
0x18003d85f  jnz     loc_18003E08A
0x18003d865  mov     rax, rdx
0x18003d868  lock cmpxchg [rcx+10h], rdi
0x18003d86e  jnz     loc_18003E08A
0x18003d874  prefetchw byte ptr [rdx+2Ch]
0x18003d878  mov     eax, [rdx+2Ch]
0x18003d87b  mov     ecx, eax
0x18003d87d  and     ecx, 0FFFFFFFDh
0x18003d880  lock cmpxchg [rdx+2Ch], ecx
0x18003d885  jnz     short loc_18003D87B
0x18003d887  mov     esi, 64h ; 'd'
0x18003d88c  mov     r10d, 8000h
0x18003d892  cmp     eax, 2
0x18003d895  jnz     loc_18003D622
0x18003d89b  mov     rax, [rdx]
0x18003d89e  mov     rcx, [rax]
0x18003d8a1  mov     qword ptr [rdx], 0
0x18003d8a8  add     rdx, 30h ; '0'
0x18003d8ac  call    RtlpInterlockedPushEntrySList
0x18003d8b1  jmp     loc_18003D61C
0x18003d8b6  cmp     r8d, 0FFFFFFFFh
0x18003d8ba  jz      loc_18003DA1E
0x18003d8c0  mov     rsi, [rbx+8]
0x18003d8c4  test    rsi, rsi
0x18003d8c7  jz      loc_18003DD5E
0x18003d8cd  cmp     [rbx], r13
0x18003d8d0  jnz     loc_18003DD5E
0x18003d8d6  test    r8w, r8w
0x18003d8da  jz      loc_18003DD5E
0x18003d8e0  mov     r9, gs:30h
0x18003d8e9  movzx   eax, word ptr [r13+0ACh]
0x18003d8f1  movzx   r11d, byte ptr [r9+246h]
0x18003d8f9  movzx   r10d, byte ptr [rax+rbp+17D590h]
0x18003d902  cmp     r11b, [r9+247h]
0x18003d909  jz      loc_18003DC6F
0x18003d90f  movzx   ecx, r11b
0x18003d913  inc     cl
0x18003d915  mov     [r9+246h], cl
0x18003d91c  movzx   r11d, byte ptr [r11+rbp+1CB560h]
0x18003d925  mov     rdx, [rsi+20h]
0x18003d929  mov     rdi, [rsi+28h]
0x18003d92d  cmp     rdx, 40h ; '@'
0x18003d931  jnb     loc_18003DB9F
0x18003d937  mov     r9, rdi
0x18003d93a  cmp     rdx, r10
0x18003d93d  jnb     short loc_18003D942
0x18003d93f  mov     r10d, edx
0x18003d942  imul    r11d, r10d
0x18003d946  shr     r11d, 8
0x18003d94a  cmp     r10d, 40h ; '@'
0x18003d94e  jnb     loc_18003DBEE
0x18003d954  mov     rax, [r9]
0x18003d957  mov     ecx, r10d
0x18003d95a  not     rax
0x18003d95d  tzcnt   rdx, rax
0x18003d962  mov     eax, 1
0x18003d967  add     r11d, edx
0x18003d96a  shl     rax, cl
0x18003d96d  movzx   ecx, dl
0x18003d970  dec     rax
0x18003d973  shl     rax, cl
0x18003d976  mov     rdx, [r9]
0x18003d979  not     rax
0x18003d97c  or      rax, rdx
0x18003d97f  mov     ecx, r11d
0x18003d982  ror     rax, cl
0x18003d985  not     rax
0x18003d988  tzcnt   rax, rax
0x18003d98d  add     eax, r11d
0x18003d990  and     eax, 3Fh
0x18003d993  mov     ecx, eax
0x18003d995  bts     rdx, rcx
0x18003d999  movzx   ecx, r8w
0x18003d99d  mov     [r9], rdx
0x18003d9a0  dec     ecx
0x18003d9a2  sub     r9, [rsi+28h]
0x18003d9a6  sar     r9, 3
0x18003d9aa  shl     r9d, 6
0x18003d9ae  add     r9d, eax
0x18003d9b1  movzx   r8d, si
0x18003d9b5  mov     eax, r9d
0x18003d9b8  shl     eax, 10h
0x18003d9bb  or      ecx, eax
0x18003d9bd  movzx   eax, r14w
0x18003d9c1  xor     r8, rax
0x18003d9c4  mov     [rbx+20h], ecx
0x18003d9c7  mov     ecx, dword ptr cs:RtlpLFHKey
0x18003d9cd  mov     edx, [rsi+18h]
0x18003d9d0  movzx   eax, cx
0x18003d9d3  xor     r8, rax
0x18003d9d6  movzx   eax, dx
0x18003d9d9  xor     r8, rax
0x18003d9dc  mov     eax, esi
0x18003d9de  xor     eax, r14d
0x18003d9e1  add     r8, rsi
0x18003d9e4  xor     ecx, eax
0x18003d9e6  xor     ecx, edx
0x18003d9e8  shr     ecx, 10h
0x18003d9eb  imul    ecx, r9d
0x18003d9ef  add     r8, rcx
0x18003d9f2  test    byte ptr [r8+0Fh], 3Fh
0x18003d9f7  jz      short loc_18003DA21
0x18003d9f9  mov     rax, [r13+0]
0x18003d9fd  xor     r9d, r9d
0x18003da00  mov     ecx, 0Fh
0x18003da05  mov     rdx, [rax+18h]
0x18003da09  xor     eax, eax
0x18003da0b  mov     [rsp+68h+var_40], rax
0x18003da10  mov     [rsp+68h+var_48], rax
0x18003da15  mov     rdx, [rdx+18h]
0x18003da19  call    RtlpLogHeapFailure
0x18003da1e  xor     r8d, r8d
0x18003da21  test    r15d, r15d
0x18003da24  jnz     loc_18003DE82
0x18003da2a  test    r8, r8
0x18003da2d  jnz     loc_18003DC43
0x18003da33  mov     r15, [rsp+68h+arg_0]
0x18003da38  mov     r13, [r15]
0x18003da3b  mov     [rsp+68h+arg_10], r13
0x18003da43  xor     edi, edi
0x18003da45  xor     esi, esi
0x18003da47  lea     r13, cs:180000000h
0x18003da4e  xor     ebp, ebp
0x18003da50  xor     ebx, ebx
0x18003da52  mov     rdx, [r15+rbx*8+10h]
0x18003da57  lea     r8, [r15+rbx*8]
0x18003da5b  test    rdx, rdx
0x18003da5e  jz      short loc_18003DA6F
0x18003da60  movzx   eax, word ptr [rdx+20h]
0x18003da64  mov     r9d, eax
0x18003da67  cmp     eax, ebp
0x18003da69  ja      loc_18003DB29
0x18003da6f  inc     rbx
0x18003da72  cmp     rbx, 10h
0x18003da76  jnz     short loc_18003DA52
0x18003da78  mov     r13, [rsp+68h+arg_10]
0x18003da80  test    rsi, rsi
0x18003da83  jz      loc_18003D69E
0x18003da89  movzx   ecx, word ptr [r15+0ACh]
0x18003da91  mov     rax, [r13+18h]
0x18003da95  mov     rbp, [rax+rcx*8+4A8h]
0x18003da9d  add     rbp, 90h
0x18003daa4  mov     rcx, rbp; ListHead
0x18003daa7  call    RtlpInterlockedPopEntrySList
0x18003daac  mov     rbx, rax
0x18003daaf  test    rax, rax
0x18003dab2  jnz     loc_18003DD0D
0x18003dab8  mov     rax, rdi
0x18003dabb  lock cmpxchg [rsi], rbx
0x18003dac0  jnz     loc_18003DD44
0x18003dac6  test    rbx, rbx
0x18003dac9  jnz     short loc_18003DAE2
0x18003dacb  sub     rsi, r15
  ... truncated ...
```
