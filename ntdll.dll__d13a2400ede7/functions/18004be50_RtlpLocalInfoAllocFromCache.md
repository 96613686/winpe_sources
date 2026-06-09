# RtlpLocalInfoAllocFromCache

- ea: `0x18004be50`
- end: `0x18004ca7e`
- name: `RtlpLocalInfoAllocFromCache`
- size: `3118`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800444ac`

## callees

- `0x18004bbf0`
- `0x18004bc90`
- `0x18004be50`
- `0x18004cbd0`
- `0x18004cd20`
- `0x18004cdb4`
- `0x18004ceb8`
- `0x18006f0d0`
- `0x18011d208`
- `0x180162850`
- `0x180162890`
- `0x180162900`

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
0x18004be50  mov     [rsp+arg_18], rbx
0x18004be55  mov     [rsp+arg_8], edx
0x18004be59  mov     [rsp+arg_0], rcx
0x18004be5e  push    rbp
0x18004be5f  push    rsi
0x18004be60  push    rdi
0x18004be61  push    r12
0x18004be63  push    r13
0x18004be65  push    r14
0x18004be67  push    r15
0x18004be69  sub     rsp, 30h
0x18004be6d  mov     r15, rcx
0x18004be70  lea     rbp, cs:180000000h
0x18004be77  mov     esi, 64h ; 'd'
0x18004be7c  mov     r10d, 8000h
0x18004be82  mov     rbx, [r15+8]
0x18004be86  test    rbx, rbx
0x18004be89  jz      loc_18004C298
0x18004be8f  mov     ecx, [rbx+20h]
0x18004be92  xor     r15d, r15d
0x18004be95  mov     r13, [rsp+68h+arg_0]
0x18004be9a  shr     ecx, 10h
0x18004be9d  mov     rax, [r13+0]
0x18004bea1  mov     r14, [rax+18h]
0x18004bea5  test    cx, cx
0x18004bea8  js      loc_18004C64B
0x18004beae  xor     r9d, r9d
0x18004beb1  cmp     word ptr ds:7FFE036Ah, 1
0x18004beba  cmova   r9d, esi
0x18004bebe  xor     edx, edx
0x18004bec0  cmp     edx, r9d
0x18004bec3  ja      loc_18004C4BF
0x18004bec9  mov     r8d, [rbx+20h]
0x18004becd  mov     eax, r8d
0x18004bed0  shr     eax, 10h
0x18004bed3  test    r10w, ax
0x18004bed7  jnz     short loc_18004BEFA
0x18004bed9  test    r8w, r8w
0x18004bedd  jz      loc_18004C27E
0x18004bee3  mov     ecx, r8d
0x18004bee6  mov     eax, r8d
0x18004bee9  or      ecx, 80000000h
0x18004beef  lock cmpxchg [rbx+20h], ecx
0x18004bef4  jz      loc_18004C116
0x18004befa  inc     edx
0x18004befc  jmp     short loc_18004BEC0
0x18004befe  lea     rax, [r15+0ACh]
0x18004bf05  xor     edi, edi
0x18004bf07  movzx   ecx, word ptr [rax]
0x18004bf0a  xor     r14d, r14d
0x18004bf0d  mov     rax, [r13+18h]
0x18004bf11  xor     ebx, ebx
0x18004bf13  xor     r15d, r15d
0x18004bf16  mov     rbp, [rax+rcx*8+4A8h]
0x18004bf1e  add     rbp, 90h
0x18004bf25  mov     rcx, rbp; ListHead
0x18004bf28  call    RtlpInterlockedPopEntrySList
0x18004bf2d  mov     rsi, rax
0x18004bf30  test    rax, rax
0x18004bf33  jnz     loc_18004CA74
0x18004bf39  test    rdi, rdi
0x18004bf3c  jz      loc_18004C644
0x18004bf42  mov     r15, [rsp+68h+arg_0]
0x18004bf47  mov     r12d, [rsp+68h+arg_8]
0x18004bf4c  lea     rbp, cs:180000000h
0x18004bf53  mov     [rdi+2Bh], r12b
0x18004bf57  nop     word ptr [rax+rax+00000000h]
0x18004bf60  mov     eax, [rdi+2Ch]
0x18004bf63  mov     esi, 64h ; 'd'
0x18004bf68  mov     r10d, 8000h
0x18004bf6e  test    eax, eax
0x18004bf70  jz      loc_18004BE82
0x18004bf76  test    al, 6
0x18004bf78  jnz     loc_18004BE82
0x18004bf7e  mov     ecx, eax
0x18004bf80  or      ecx, 6
0x18004bf83  lock cmpxchg [rdi+2Ch], ecx
0x18004bf88  jnz     short loc_18004BF60
0x18004bf8a  mov     r8, [rdi]
0x18004bf8d  cmp     r8, r15
0x18004bf90  jnz     loc_18004C7E2
0x18004bf96  mov     rax, gs:60h
0x18004bf9f  mov     rcx, [rax+90h]
0x18004bfa6  test    rcx, rcx
0x18004bfa9  jnz     loc_18004C95B
0x18004bfaf  mov     ecx, 7FFE0380h
0x18004bfb4  cmp     byte ptr [rcx], 0
0x18004bfb7  jnz     loc_18004C980
0x18004bfbd  xchg    rdi, [r15+8]
0x18004bfc1  mov     r10d, 8000h
0x18004bfc7  test    rdi, rdi
0x18004bfca  jz      loc_18004BE82
0x18004bfd0  prefetchw byte ptr [rdi+2Ch]
0x18004bfd4  mov     eax, [rdi+2Ch]
0x18004bfd7  mov     ecx, eax
0x18004bfd9  and     ecx, 0FFFFFFF9h
0x18004bfdc  lock cmpxchg [rdi+2Ch], ecx
0x18004bfe1  jnz     short loc_18004BFD7
0x18004bfe3  cmp     eax, 6
0x18004bfe6  jz      loc_18004C940
0x18004bfec  movzx   eax, word ptr [rdi+20h]
0x18004bff0  test    ax, ax
0x18004bff3  jz      loc_18004BE82
0x18004bff9  test    byte ptr cs:RtlpLowFragHeapGlobalFlags, 4
0x18004c000  jz      loc_18004C712
0x18004c006  xor     dl, dl
0x18004c008  mov     rax, gs:60h
0x18004c011  mov     rcx, [rax+90h]
0x18004c018  test    rcx, rcx
0x18004c01b  jnz     loc_18004C798
0x18004c021  mov     ecx, 7FFE038Ah
0x18004c026  cmp     byte ptr [rcx], 0
0x18004c029  jnz     loc_18004C76F
0x18004c02f  mov     rax, gs:60h
0x18004c038  mov     rcx, [rax+90h]
0x18004c03f  test    rcx, rcx
0x18004c042  jnz     loc_18004C7BD
0x18004c048  mov     ecx, 7FFE0380h
0x18004c04d  cmp     byte ptr [rcx], 0
0x18004c050  jnz     loc_18004C759
0x18004c056  test    dl, dl
0x18004c058  jnz     loc_18004BE82
0x18004c05e  xchg    ax, ax
0x18004c060  mov     eax, [rdi+2Ch]
0x18004c063  mov     esi, 64h ; 'd'
0x18004c068  mov     r10d, 8000h
0x18004c06e  test    eax, eax
0x18004c070  jz      loc_18004BE82
0x18004c076  test    al, 2
0x18004c078  jnz     loc_18004BE82
0x18004c07e  mov     ecx, eax
0x18004c080  or      ecx, 2
0x18004c083  lock cmpxchg [rdi+2Ch], ecx
0x18004c088  jnz     short loc_18004C060
0x18004c08a  mov     r9, [rdi]
0x18004c08d  xor     r8d, r8d
0x18004c090  cmp     r8d, 10h
0x18004c094  jnb     loc_18004C8F2
0x18004c09a  movzx   eax, word ptr [r9+0AEh]
0x18004c0a2  add     eax, r8d
0x18004c0a5  and     eax, 0Fh
0x18004c0a8  mov     rdx, [r9+rax*8+10h]
0x18004c0ad  lea     rcx, [r9+rax*8]
0x18004c0b1  test    rdx, rdx
0x18004c0b4  jz      loc_18004C8D1
0x18004c0ba  mov     eax, [rdx+2Ch]
0x18004c0bd  test    al, 1
0x18004c0bf  jnz     loc_18004C8EA
0x18004c0c5  mov     rax, rdx
0x18004c0c8  lock cmpxchg [rcx+10h], rdi
0x18004c0ce  jnz     loc_18004C8EA
0x18004c0d4  prefetchw byte ptr [rdx+2Ch]
0x18004c0d8  mov     eax, [rdx+2Ch]
0x18004c0db  mov     ecx, eax
0x18004c0dd  and     ecx, 0FFFFFFFDh
0x18004c0e0  lock cmpxchg [rdx+2Ch], ecx
0x18004c0e5  jnz     short loc_18004C0DB
0x18004c0e7  mov     esi, 64h ; 'd'
0x18004c0ec  mov     r10d, 8000h
0x18004c0f2  cmp     eax, 2
0x18004c0f5  jnz     loc_18004BE82
0x18004c0fb  mov     rax, [rdx]
0x18004c0fe  mov     rcx, [rax]
0x18004c101  mov     qword ptr [rdx], 0
0x18004c108  add     rdx, 30h ; '0'
0x18004c10c  call    RtlpInterlockedPushEntrySList
0x18004c111  jmp     loc_18004BE7C
0x18004c116  cmp     r8d, 0FFFFFFFFh
0x18004c11a  jz      loc_18004C27E
0x18004c120  mov     rsi, [rbx+8]
0x18004c124  test    rsi, rsi
0x18004c127  jz      loc_18004C5BE
0x18004c12d  cmp     [rbx], r13
0x18004c130  jnz     loc_18004C5BE
0x18004c136  test    r8w, r8w
0x18004c13a  jz      loc_18004C5BE
0x18004c140  mov     r9, gs:30h
0x18004c149  movzx   eax, word ptr [r13+0ACh]
0x18004c151  movzx   r11d, byte ptr [r9+246h]
0x18004c159  movzx   r10d, byte ptr [rax+rbp+17DA40h]
0x18004c162  cmp     r11b, [r9+247h]
0x18004c169  jz      loc_18004C4CF
0x18004c16f  movzx   ecx, r11b
0x18004c173  inc     cl
0x18004c175  mov     [r9+246h], cl
0x18004c17c  movzx   r11d, byte ptr [r11+rbp+1CB560h]
0x18004c185  mov     rdx, [rsi+20h]
0x18004c189  mov     rdi, [rsi+28h]
0x18004c18d  cmp     rdx, 40h ; '@'
0x18004c191  jnb     loc_18004C3FF
0x18004c197  mov     r9, rdi
0x18004c19a  cmp     rdx, r10
0x18004c19d  jnb     short loc_18004C1A2
0x18004c19f  mov     r10d, edx
0x18004c1a2  imul    r11d, r10d
0x18004c1a6  shr     r11d, 8
0x18004c1aa  cmp     r10d, 40h ; '@'
0x18004c1ae  jnb     loc_18004C44E
0x18004c1b4  mov     rax, [r9]
0x18004c1b7  mov     ecx, r10d
0x18004c1ba  not     rax
0x18004c1bd  tzcnt   rdx, rax
0x18004c1c2  mov     eax, 1
0x18004c1c7  add     r11d, edx
0x18004c1ca  shl     rax, cl
0x18004c1cd  movzx   ecx, dl
0x18004c1d0  dec     rax
0x18004c1d3  shl     rax, cl
0x18004c1d6  mov     rdx, [r9]
0x18004c1d9  not     rax
0x18004c1dc  or      rax, rdx
0x18004c1df  mov     ecx, r11d
0x18004c1e2  ror     rax, cl
0x18004c1e5  not     rax
0x18004c1e8  tzcnt   rax, rax
0x18004c1ed  add     eax, r11d
0x18004c1f0  and     eax, 3Fh
0x18004c1f3  mov     ecx, eax
0x18004c1f5  bts     rdx, rcx
0x18004c1f9  movzx   ecx, r8w
0x18004c1fd  mov     [r9], rdx
0x18004c200  dec     ecx
0x18004c202  sub     r9, [rsi+28h]
0x18004c206  sar     r9, 3
0x18004c20a  shl     r9d, 6
0x18004c20e  add     r9d, eax
0x18004c211  movzx   r8d, si
0x18004c215  mov     eax, r9d
0x18004c218  shl     eax, 10h
0x18004c21b  or      ecx, eax
0x18004c21d  movzx   eax, r14w
0x18004c221  xor     r8, rax
0x18004c224  mov     [rbx+20h], ecx
0x18004c227  mov     ecx, dword ptr cs:RtlpLFHKey
0x18004c22d  mov     edx, [rsi+18h]
0x18004c230  movzx   eax, cx
0x18004c233  xor     r8, rax
0x18004c236  movzx   eax, dx
0x18004c239  xor     r8, rax
0x18004c23c  mov     eax, esi
0x18004c23e  xor     eax, r14d
0x18004c241  add     r8, rsi
0x18004c244  xor     ecx, eax
0x18004c246  xor     ecx, edx
0x18004c248  shr     ecx, 10h
0x18004c24b  imul    ecx, r9d
0x18004c24f  add     r8, rcx
0x18004c252  test    byte ptr [r8+0Fh], 3Fh
0x18004c257  jz      short loc_18004C281
0x18004c259  mov     rax, [r13+0]
0x18004c25d  xor     r9d, r9d
0x18004c260  mov     ecx, 0Fh
0x18004c265  mov     rdx, [rax+18h]
0x18004c269  xor     eax, eax
0x18004c26b  mov     [rsp+68h+var_40], rax
0x18004c270  mov     [rsp+68h+var_48], rax
0x18004c275  mov     rdx, [rdx+18h]
0x18004c279  call    RtlpLogHeapFailure
0x18004c27e  xor     r8d, r8d
0x18004c281  test    r15d, r15d
0x18004c284  jnz     loc_18004C6E2
0x18004c28a  test    r8, r8
0x18004c28d  jnz     loc_18004C4A3
0x18004c293  mov     r15, [rsp+68h+arg_0]
0x18004c298  mov     r13, [r15]
0x18004c29b  mov     [rsp+68h+arg_10], r13
0x18004c2a3  xor     edi, edi
0x18004c2a5  xor     esi, esi
0x18004c2a7  lea     r13, cs:180000000h
0x18004c2ae  xor     ebp, ebp
0x18004c2b0  xor     ebx, ebx
0x18004c2b2  mov     rdx, [r15+rbx*8+10h]
0x18004c2b7  lea     r8, [r15+rbx*8]
0x18004c2bb  test    rdx, rdx
0x18004c2be  jz      short loc_18004C2CF
0x18004c2c0  movzx   eax, word ptr [rdx+20h]
0x18004c2c4  mov     r9d, eax
0x18004c2c7  cmp     eax, ebp
0x18004c2c9  ja      loc_18004C389
0x18004c2cf  inc     rbx
0x18004c2d2  cmp     rbx, 10h
0x18004c2d6  jnz     short loc_18004C2B2
0x18004c2d8  mov     r13, [rsp+68h+arg_10]
0x18004c2e0  test    rsi, rsi
0x18004c2e3  jz      loc_18004BEFE
0x18004c2e9  movzx   ecx, word ptr [r15+0ACh]
0x18004c2f1  mov     rax, [r13+18h]
0x18004c2f5  mov     rbp, [rax+rcx*8+4A8h]
0x18004c2fd  add     rbp, 90h
0x18004c304  mov     rcx, rbp; ListHead
0x18004c307  call    RtlpInterlockedPopEntrySList
0x18004c30c  mov     rbx, rax
0x18004c30f  test    rax, rax
0x18004c312  jnz     loc_18004C56D
0x18004c318  mov     rax, rdi
0x18004c31b  lock cmpxchg [rsi], rbx
0x18004c320  jnz     loc_18004C5A4
0x18004c326  test    rbx, rbx
0x18004c329  jnz     short loc_18004C342
0x18004c32b  sub     rsi, r15
  ... truncated ...
```
