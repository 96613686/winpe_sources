# CmsBlockRefcount::ProcessDeleteQueueEntry(CmsTransactionCore *,CmsContainerRangeMap *,_SmsContainerRangeMapListHead *,_SmsQuickIndex *,void *)

- ea: `0x1400c01a0`
- end: `0x1400c0cae`
- name: `?ProcessDeleteQueueEntry@CmsBlockRefcount@@CAJPEAVCmsTransactionCore@@PEAVCmsContainerRangeMap@@PEAU_SmsContainerRangeMapListHead@@PEAU_SmsQuickIndex@@PEAX@Z`
- size: `2830`
- prototype: `__int64 __usercall@<rax>(struct CmsTransactionCore *@<rcx>, struct CmsContainerRangeMap *@<rdx>, struct _SmsContainerRangeMapListHead *@<r8>, struct _SmsQuickIndex *@<r9>, void *)`
- caller_count: `0`
- callee_count: `16`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x14001dc94`
- `0x140023480`
- `0x140023ac0`
- `0x1400325d0`
- `0x140062510`
- `0x14006e320`
- `0x14009ac80`
- `0x1400a2ab0`
- `0x1400a3840`
- `0x1400c01a0`
- `0x1400c6748`
- `0x1400c8574`
- `0x1400f3ec8`
- `0x1400f5680`
- `0x14013b560`
- `0x1401e9e40`

## import_xrefs

- `ntoskrnl!KdDebuggerEnabled` at `0x1400c0b08`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400c049c`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400c04b2`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400c0a8c`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400c0aa2`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400c049c`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400c04b2`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400c0a8c`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400c0aa2`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x1400c0633`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x1400c0633`
- `ntoskrnl!ExAllocatePool2` at `0x1400c06b0`
- `ntoskrnl!ExAllocatePool2` at `0x1400c06b0`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x1400c05f9`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x1400c05f9`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x1400c0641`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x1400c0641`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x1400c067b`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x1400c067b`
- `ntoskrnl!ExReleasePushLockEx` at `0x1400c038d`
- `ntoskrnl!ExReleasePushLockEx` at `0x1400c046a`
- `ntoskrnl!ExReleasePushLockEx` at `0x1400c0548`
- `ntoskrnl!ExReleasePushLockEx` at `0x1400c08ac`
- `ntoskrnl!ExReleasePushLockEx` at `0x1400c0a5a`
- `ntoskrnl!ExReleasePushLockEx` at `0x1400c038d`
- `ntoskrnl!ExReleasePushLockEx` at `0x1400c046a`
- `ntoskrnl!ExReleasePushLockEx` at `0x1400c0548`
- `ntoskrnl!ExReleasePushLockEx` at `0x1400c08ac`
- `ntoskrnl!ExReleasePushLockEx` at `0x1400c0a5a`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1400c0370`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1400c088f`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1400c0370`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1400c088f`

## string_xrefs

- `0x1400c0ca1`: `Lookaside list allocation must be double quad aligned.`

## pseudocode

```c
__int64 __fastcall CmsBlockRefcount::ProcessDeleteQueueEntry(
        struct CmsTransactionCore *a1,
        struct CmsContainerRangeMap *a2,
        struct _SmsContainerRangeMapListHead *a3,
        struct _SmsQuickIndex *a4,
        volatile signed __int64 *a5)
{
  int v5; // r14d
  struct CmsTransactionCore *v6; // rbx
  __int64 v7; // rcx
  struct _SmsContainerRangeMapListHead *v8; // rsi
  struct _SmsContainerRangeMapListHead *v9; // r13
  unsigned __int8 v10; // al
  unsigned __int64 v11; // rdx
  char *v12; // rdi
  __int64 result; // rax
  __int64 v14; // rcx
  int NextRange; // r12d
  __int64 *v16; // r15
  bool v17; // zf
  signed __int64 *v18; // rcx
  char v19; // cl
  __int64 v20; // rax
  __int64 v21; // r15
  unsigned __int64 v22; // rsi
  unsigned __int64 v23; // r14
  __int64 v24; // rcx
  signed __int16 v25; // ax
  signed __int16 v26; // ax
  signed __int16 v27; // tt
  void *v28; // rdx
  signed __int64 *v29; // r15
  __int64 v30; // r14
  _WORD *v31; // r15
  unsigned __int64 v32; // r14
  unsigned __int64 v33; // rbx
  unsigned int *v34; // rsi
  struct _NPAGED_LOOKASIDE_LIST *v35; // rcx
  void *v36; // rax
  int v37; // ecx
  signed __int64 v38; // rbx
  unsigned __int64 v39; // rdx
  __int64 Pool2; // rax
  __int16 v41; // dx
  unsigned __int64 v42; // r10
  __int16 v43; // cx
  __int16 v44; // ax
  __int64 v45; // rax
  char *v46; // rsi
  struct CmsTransactionCore *v47; // rdx
  _BYTE *v48; // r14
  _DWORD *v49; // r15
  __int16 v50; // r10
  signed __int64 v51; // rax
  signed __int64 v52; // rax
  __int64 v53; // rsi
  __int64 v54; // r13
  unsigned __int64 v55; // r14
  unsigned __int64 v56; // r15
  unsigned __int64 v57; // rbx
  unsigned __int64 v58; // r10
  unsigned __int64 v59; // rsi
  volatile signed __int32 *v60; // r9
  __int64 v61; // rax
  __int64 v62; // r8
  signed __int16 v63; // ax
  signed __int16 v64; // tt
  __int16 v65; // bx
  __int16 v66; // ax
  __int64 *v67; // r15
  void *v68; // rdx
  unsigned __int64 v69; // r13
  signed __int64 v70; // rax
  signed __int64 v71; // r14
  __int64 v72; // rsi
  struct _SmsContainerRangeMapListHead *v73; // rbx
  int v74; // eax
  struct _SmsContainerRangeMapListHead *v75; // rsi
  signed __int64 v76; // rax
  signed __int64 v77; // rax
  unsigned __int8 v78[4]; // [rsp+40h] [rbp-A1h] BYREF
  unsigned __int16 v79[2]; // [rsp+44h] [rbp-9Dh] BYREF
  int v80; // [rsp+48h] [rbp-99h]
  struct _SmsContainerRangeMapListHead *v81; // [rsp+50h] [rbp-91h] BYREF
  __int16 v82; // [rsp+58h] [rbp-89h]
  unsigned __int64 v83; // [rsp+60h] [rbp-81h] BYREF
  unsigned __int64 v84; // [rsp+68h] [rbp-79h]
  PVOID Entry; // [rsp+70h] [rbp-71h] BYREF
  __int64 *v86; // [rsp+78h] [rbp-69h]
  unsigned __int64 v87; // [rsp+80h] [rbp-61h] BYREF
  __int64 v88; // [rsp+88h] [rbp-59h]
  __int64 v89; // [rsp+90h] [rbp-51h]
  signed __int64 *v90; // [rsp+98h] [rbp-49h]
  struct _SmsContainerRangeMapListHead *v91; // [rsp+A0h] [rbp-41h] BYREF
  unsigned __int64 v92; // [rsp+A8h] [rbp-39h]
  __int64 v93; // [rsp+B0h] [rbp-31h]
  CmsVolume *v94; // [rsp+B8h] [rbp-29h]
  signed __int64 *v95; // [rsp+C0h] [rbp-21h]
  _BYTE v96[24]; // [rsp+D0h] [rbp-11h] BYREF
  __int16 v97; // [rsp+E8h] [rbp+7h]
  char v98; // [rsp+EAh] [rbp+9h]
  int v99; // [rsp+F8h] [rbp+17h]

  v5 = 0;
  v6 = a1;
  v7 = *((_QWORD *)a1 + 1);
  v8 = a3;
  v94 = (CmsVolume *)v7;
  v91 = 0;
  v79[0] = 0;
  v9 = *(struct _SmsContainerRangeMapListHead **)(v7 + 3368);
  v97 = 0;
  v98 = 0;
  v99 = 0;
  v83 = 0;
  v84 = 0;
  v10 = *(_BYTE *)(v7 + 88);
  v81 = v9;
  v78[0] = 0;
  if ( v10 == 2 )
    v10 = (*(_DWORD *)(v7 + 64) != 12) + 1;
  v11 = *((_QWORD *)a3 + 2);
  v12 = 0;
  Entry = 0;
  v89 = *(_QWORD *)(v7 + 8LL * v10 + 3624);
  result = CmsContainerRangeMap::InitializeContainerRangeMapListHead(&v91, v11, 0, 0);
  NextRange = result;
  if ( (int)result < 0 )
    return result;
  v90 = 0;
  v80 = 0;
  CmsVolume::BeginTopLevelActionInternal(v14, v6, v96, 0, 0, 0);
  v16 = (__int64 *)*((_QWORD *)v8 + 3);
  v86 = v16;
  if ( !v16 )
  {
LABEL_144:
    v75 = v91;
    goto LABEL_145;
  }
  do
  {
    v17 = (*((_BYTE *)v16 + 14) & 1) == 0;
    v18 = v16;
    v95 = v16;
    if ( !v17 )
      goto LABEL_39;
    v19 = *((_BYTE *)a2 + 52);
    v93 = 0;
    v20 = *((unsigned __int16 *)v16 + 5);
    v92 = (*((_QWORD *)v8 + 2) << v19) | (unsigned __int16)v16[1] & (unsigned __int64)((1 << v19) - 1);
    v87 = v92;
    v88 = v20;
    if ( !v20 )
      goto LABEL_35;
    while ( 1 )
    {
      NextRange = CmsBlockRefcount::GetNextRange(
                    v9,
                    v6,
                    (const struct _RANGE *)&v87,
                    (struct _RANGE *)&v83,
                    v79,
                    v78,
                    0,
                    (struct CmsRefcountCacheEntry **)&Entry);
      if ( NextRange < 0 )
        goto LABEL_32;
      while ( !v79[0] && v78[0] )
      {
        v12 = (char *)Entry;
        v21 = *((_QWORD *)v6 + 1);
        v22 = v83 - *((_QWORD *)Entry + 2);
        v23 = v22 + v84;
        if ( !*((_QWORD *)Entry + 9) )
        {
          ExAcquirePushLockExclusiveEx((char *)Entry + 56, 0);
          NextRange = CmsRefcountCacheEntry::AllocateArray((CmsRefcountCacheEntry *)v12);
          ExReleasePushLockEx(v12 + 56, 0);
          if ( NextRange < 0 )
            goto LABEL_33;
        }
        for ( ; v22 < v23; ++v22 )
        {
          do
          {
            v24 = *((_QWORD *)v12 + 9);
            v25 = *(_WORD *)(v24 + 2 * v22);
          }
          while ( v25 < 0
               && v25 != _InterlockedCompareExchange16(
                           (volatile signed __int16 *)(v24 + 2 * v22),
                           v25 & 0x3FFF | 0x4000,
                           v25) );
        }
        if ( (v12[50] & 4) != 0 )
        {
          _InterlockedAnd16((volatile signed __int16 *)v12 + 25, 0xFFF7u);
        }
        else
        {
          _m_prefetchw(v12 + 50);
          v26 = *((_WORD *)v12 + 25);
          do
          {
            v27 = v26;
            v26 = _InterlockedCompareExchange16((volatile signed __int16 *)v12 + 25, v26 | 4, v26);
          }
          while ( v27 != v26 );
          _InterlockedAnd16((volatile signed __int16 *)v12 + 25, 0xFFF7u);
          if ( (v26 & 4) == 0 )
            _InterlockedIncrement((volatile signed __int32 *)v9 + 17);
        }
        if ( CmsRefcountCacheEntry::AddForProcessing((CmsRefcountCacheEntry *)v12, (union _SLIST_HEADER *)v9 + 5) )
          _InterlockedIncrement((volatile signed __int32 *)v9 + 16);
        if ( (*(_DWORD *)(*(_QWORD *)(v21 + 1712) + 120LL) & 0x100) != 0 )
          MsKmeLogOverwriteOrFree(*(struct _VCB *const *)(v21 + 48), (const struct _RANGE *)&v83);
        ExReleasePushLockEx(v12 + 56, 0);
        if ( _InterlockedExchangeAdd16((volatile signed __int16 *)v12 + 24, 0xFFFFu) == 1 && v12 )
        {
          v28 = (void *)*((_QWORD *)v12 + 9);
          if ( v28 )
            ExFreeToNPagedLookasideList(&CmsRefcountCacheEntry::ArraysLookasideList, v28);
          ExFreeToNPagedLookasideList(&CmsRefcountCacheEntry::EntriesLookasideList, v12);
        }
        v6 = a1;
        Entry = 0;
        NextRange = CmsBlockRefcount::GetNextRange(
                      v9,
                      a1,
                      (const struct _RANGE *)&v87,
                      (struct _RANGE *)&v83,
                      v79,
                      v78,
                      0,
                      (struct CmsRefcountCacheEntry **)&Entry);
        if ( NextRange < 0 )
          goto LABEL_32;
      }
      v12 = (char *)Entry;
      if ( v79[0] )
        break;
      v30 = v88;
      if ( v84 != v88 )
      {
        v31 = v86;
        if ( (*((_BYTE *)v86 + 12) & 4) != 0 )
        {
          if ( *(_WORD *)(v89 + 8) )
            v32 = (unsigned __int64)(unsigned int)(v84 << *((_DWORD *)v94 + 16)) >> ((unsigned __int8)*(_WORD *)(v89 + 20)
                                                                                   - *(_BYTE *)(v89 + 12));
          else
            LODWORD(v32) = 0;
        }
        else
        {
          LODWORD(v32) = 0;
        }
        v33 = (unsigned int)(v32 + 16);
        v34 = (unsigned int *)(qword_1402624B0 + 192LL * (KeGetCurrentProcessorNumberEx(0) % NumProcessors));
        if ( v33 > *v34 )
        {
          v34 = 0;
          v39 = v33 + 16;
        }
        else
        {
          if ( *((_BYTE *)v34 + 8) )
          {
            v35 = (struct _NPAGED_LOOKASIDE_LIST *)(v34 + 16);
            if ( *((_BYTE *)v34 + 9) )
              v36 = ExAllocateFromNPagedLookasideList(v35);
            else
              v36 = ExAllocateFromPagedLookasideList((PPAGED_LOOKASIDE_LIST)v35);
LABEL_57:
            v38 = (signed __int64)v36;
            if ( !v36 )
            {
              v39 = v34[1];
              goto LABEL_62;
            }
LABEL_64:
            *(_QWORD *)v38 = v34;
            v38 += 16LL;
LABEL_65:
            if ( !v38 )
            {
              NextRange = -1073741670;
LABEL_32:
              v12 = (char *)Entry;
              goto LABEL_33;
            }
            v41 = v84;
            NextRange = 0;
            v42 = v92;
            *(_WORD *)(v38 + 8) = v83 + v31[4] - v92;
            v43 = 0;
            *(_WORD *)(v38 + 14) = 0;
            *(_WORD *)(v38 + 10) = v41;
            if ( (_DWORD)v32 )
              v43 = 4;
            v44 = 0;
            if ( (_DWORD)v32 )
              v44 = 2;
            *(_WORD *)(v38 + 12) = v44 | v43;
            if ( (_DWORD)v32 )
            {
              v45 = v89;
              v46 = (char *)(v31 + 8);
              v47 = a1;
              v48 = (_BYTE *)(v89 + 20);
              v49 = (_DWORD *)(v89 + 12);
              if ( *(_WORD *)(v89 + 8) )
              {
                memmove(
                  (void *)(v38 + 16),
                  &v46[(unsigned __int64)(unsigned int)((v83 - v42) << *(_DWORD *)(*((_QWORD *)a1 + 1) + 64LL)) >> *v48 << *v49],
                  (unsigned __int64)(unsigned int)(v84 << *(_DWORD *)(*((_QWORD *)a1 + 1) + 64LL)) >> ((unsigned __int8)*(_WORD *)v48 - (unsigned __int8)*v49));
                v47 = a1;
                v45 = v89;
              }
              if ( *(_WORD *)(v45 + 8) )
              {
                v50 = *(_WORD *)v48;
                v30 = v88;
                memmove(
                  v46,
                  &v46[(unsigned __int64)(unsigned int)(v84 << *(_DWORD *)(*((_QWORD *)v47 + 1) + 64LL)) >> v50 << *v49],
                  (unsigned __int64)(unsigned int)((v88 - v84) << *(_DWORD *)(*((_QWORD *)v47 + 1) + 64LL)) >> ((unsigned __int8)v50 - (unsigned __int8)*v49));
                v31 = v86;
LABEL_77:
                v31[5] -= v84;
                v31[4] += v84;
                ++v80;
                _m_prefetchw((char *)a3 + 24);
                do
                {
                  v51 = *((_QWORD *)a3 + 3);
                  *(_QWORD *)v38 = v51;
                  v52 = _InterlockedCompareExchange64((volatile signed __int64 *)a3 + 3, v38, v51);
                }
                while ( v52 != *(_QWORD *)v38 );
                if ( !v52 )
                  *((_QWORD *)a3 + 4) = v38;
                if ( (*(_BYTE *)(v38 + 12) & 2) != 0 )
                  _InterlockedOr((volatile signed __int32 *)a3 + 11, 1u);
                _InterlockedIncrement((volatile signed __int32 *)a3 + 10);
                _InterlockedIncrement64((volatile signed __int64 *)a2 + 4);
                if ( !v90 )
                  v90 = (signed __int64 *)v38;
LABEL_110:
                v6 = a1;
                goto LABEL_111;
              }
              v31 = v86;
            }
            v30 = v88;
            goto LABEL_77;
          }
          if ( (int)*((_QWORD *)v34 + 11) > (int)HIDWORD(*((_QWORD *)v34 + 11)) )
          {
            v37 = _InterlockedDecrement((volatile signed __int32 *)v34 + 22);
            if ( v37 >= (int)v34[23] && v37 >= 0 )
            {
              v36 = ExpInterlockedPopEntrySList((PSLIST_HEADER)v34 + 4);
              goto LABEL_57;
            }
            _InterlockedIncrement((volatile signed __int32 *)v34 + 22);
          }
          v39 = v34[1];
        }
LABEL_62:
        Pool2 = ExAllocatePool2(66, v39, 1766871885);
        v38 = Pool2;
        if ( (Pool2 & 0xF) != 0 )
          MsUnsupportedOperationBugCheck("Lookaside list allocation must be double quad aligned.");
        if ( Pool2 )
          goto LABEL_64;
        goto LABEL_65;
      }
LABEL_111:
      if ( v12 )
      {
        ExReleasePushLockEx(v12 + 56, 0);
        if ( _InterlockedExchangeAdd16((volatile signed __int16 *)v12 + 24, 0xFFFFu) == 1 )
        {
          v68 = (void *)*((_QWORD *)v12 + 9);
          if ( v68 )
            ExFreeToNPagedLookasideList(&CmsRefcountCacheEntry::ArraysLookasideList, v68);
          ExFreeToNPagedLookasideList(&CmsRefcountCacheEntry::EntriesLookasideList, v12);
        }
        v12 = 0;
        Entry = 0;
      }
      v88 = v30 - v84;
      v92 += v84;
      v87 = v92;
      if ( v30 == v84 )
        goto LABEL_33;
    }
    NextRange = 0;
    v53 = *((_QWORD *)Entry + 2);
    v54 = *(_QWORD *)v9;
    v55 = v84;
    v56 = v83;
    if ( !*((_QWORD *)Entry + 9) )
    {
      ExAcquirePushLockExclusiveEx((char *)Entry + 56, 0);
      NextRange = CmsRefcountCacheEntry::AllocateArray((CmsRefcountCacheEntry *)v12);
      ExReleasePushLockEx(v12 + 56, 0);
      if ( NextRange < 0 )
      {
        v9 = v81;
LABEL_102:
        if ( NextRange < 0 )
          goto LABEL_33;
        v65 = v84;
        v30 = v88;
        if ( v84 == v88 )
        {
          v66 = *((_WORD *)v86 + 7);
          LOBYTE(v66) = v66 | 1;
          v82 = v66;
          *((_WORD *)v86 + 7) = v66;
        }
        else
        {
          v67 = v86;
          if ( (*((_BYTE *)v86 + 12) & 4) != 0 && *(_WORD *)(v89 + 8) )
          {
            memmove(
              v86 + 2,
              (char *)v86
            + ((unsigned __int64)(unsigned int)(v84 << *(_DWORD *)(*((_QWORD *)a1 + 1) + 64LL)) >> *(_WORD *)(v89 + 20) << *(_DWORD *)(v89 + 12))
            + 16,
              (unsigned __int64)(unsigned int)((v88 - v84) << *(_DWORD *)(*((_QWORD *)a1 + 1) + 64LL)) >> ((unsigned __int8)*(_WORD *)(v89 + 20) - (unsigned __int8)*(_DWORD *)(v89 + 12)));
            v65 = v84;
          }
          *((_WORD *)v67 + 5) -= v65;
          *((_WORD *)v67 + 4) += v84;
        }
        v93 += v84;
        goto LABEL_110;
      }
    }
    v57 = v56 - v53;
    v58 = v57;
    v59 = v55 + v56 - v53;
    if ( v57 >= v59 )
    {
LABEL_92:
      if ( (v12[50] & 4) != 0 )
      {
        _InterlockedAnd16((volatile signed __int16 *)v12 + 25, 0xFFF7u);
      }
      else
      {
        _m_prefetchw(v12 + 50);
        v63 = *((_WORD *)v12 + 25);
        do
        {
          v64 = v63;
          v63 = _InterlockedCompareExchange16((volatile signed __int16 *)v12 + 25, v63 | 4, v63);
        }
        while ( v64 != v63 );
        _InterlockedAnd16((volatile signed __int16 *)v12 + 25, 0xFFF7u);
        if ( (v63 & 4) == 0 )
        {
          v9 = v81;
          _InterlockedIncrement((volatile signed __int32 *)v81 + 17);
LABEL_95:
          if ( CmsRefcountCacheEntry::AddForProcessing((CmsRefcountCacheEntry *)v12, (union _SLIST_HEADER *)v9 + 5) )
            _InterlockedIncrement((volatile signed __int32 *)v9 + 16);
          goto LABEL_102;
        }
      }
      v9 = v81;
      goto LABEL_95;
    }
    v60 = (volatile signed __int32 *)(v12 + 64);
    while ( 1 )
    {
      v61 = *((_QWORD *)v12 + 9);
      v62 = *(__int16 *)(v61 + 2 * v58);
      if ( (v62 & 0x1FFF) == 0 )
        break;
      v60 = (volatile signed __int32 *)(v12 + 64);
      if ( (_WORD)v62 == _InterlockedCompareExchange16((volatile signed __int16 *)(v61 + 2 * v58), v62 - 1, v62) )
      {
        NextRange = 0;
        v60 = (volatile signed __int32 *)(v12 + 64);
        ++v58;
        _InterlockedDecrement((volatile signed __int32 *)v12 + 16);
        if ( v58 >= v59 )
          goto LABEL_92;
      }
    }
    while ( v58 > v57 )
    {
      --v58;
      _InterlockedIncrement16((volatile signed __int16 *)(*((_QWORD *)v12 + 9) + 2 * v58));
      _InterlockedIncrement(v60);
    }
    if ( (_BYTE)KdDebuggerEnabled )
      __debugbreak();
    MsKmeBlockRefCountUnderflowEventNotification(
      *(struct _VCB **)(v54 + 48),
      0x47400602C9uLL,
      v62,
      v58,
      v56,
      v55,
      v57,
      v59);
    NextRange = -1073741675;
LABEL_33:
    v9 = v81;
    v16 = v86;
    v8 = a3;
    v6 = a1;
    v5 = v80;
    if ( v93 )
      _InterlockedAdd64((volatile signed __int64 *)v94 + 477, -v93);
LABEL_35:
    if ( v12 )
    {
      ExReleasePushLockEx(v12 + 56, 0);
      CmsRefcountCacheEntry::Release(v12);
      v12 = 0;
      Entry = 0;
    }
    if ( NextRange < 0 )
    {
      v29 = v90;
      goto LABEL_126;
    }
    v18 = v95;
LABEL_39:
    v16 = (__int64 *)*v16;
    ++v5;
    v86 = v16;
    v80 = v5;
    v90 = v18;
  }
  while ( v16 );
  v29 = v18;
  v80 = v5;
LABEL_126:
  if ( v5 <= 0 )
    goto LABEL_144;
  v69 = v80;
  *((_DWORD *)v8 + 10) -= v80;
  v70 = *v29;
  v71 = *((_QWORD *)v8 + 3);
  *((_QWORD *)v8 + 3) = *v29;
  if ( !v70 )
    *((_QWORD *)v8 + 4) = 0;
  _InterlockedAdd64((volatile signed __int64 *)a2 + 4, -(int)v69);
  v72 = *((_QWORD *)v8 + 2);
  v81 = 0;
  if ( (int)CmsContainerRangeMap::InitializeMapIfRequired((CmsContainerRangeMap *)a5) < 0 )
    goto LABEL_144;
  if ( (int)CmsHashTableLite::PinInIndex<1>(a5, v72, &v81, 0) >= 0 )
  {
    v75 = v91;
    v73 = v81;
  }
  else
  {
    v73 = v91;
    v81 = v91;
    v74 = CmsHashTableLite::AddToIndex<1>(a5, v91, 0);
    if ( v74 == -1073741771 )
    {
      CmsLookasides::Free(v73);
      CmsHashTableLite::PinInIndex<1>(a5, v72, &v81, 0);
      v73 = v81;
      goto LABEL_133;
    }
    if ( v74 < 0 )
    {
      CmsLookasides::Free(v73);
      v75 = 0;
      goto LABEL_145;
    }
LABEL_133:
    v75 = 0;
  }
  if ( (*((_DWORD *)a3 + 11) & 1) != 0 )
    _InterlockedOr((volatile signed __int32 *)v73 + 11, 1u);
  _m_prefetchw((char *)v73 + 24);
  do
  {
    v76 = *((_QWORD *)v73 + 3);
    *v29 = v76;
    v77 = _InterlockedCompareExchange64((volatile signed __int64 *)v73 + 3, v71, v76);
  }
  while ( v77 != *v29 );
  if ( !v77 )
    *((_QWORD *)v73 + 4) = v29;
  _InterlockedAdd((volatile signed __int32 *)v73 + 10, v69);
  _InterlockedAdd64(a5 + 4, v69);
LABEL_145:
  CmsVolume::CommitTopLevelAction(v94, a1, (struct _SmsTopLevelAction *)v96, 0);
  if ( v75 )
    CmsLookasides::Free(v75);
  return (unsigned int)NextRange;
}

```

## disassembly

```asm
0x1400c01a0  mov     [rsp-8+arg_10], r8
0x1400c01a5  mov     [rsp-8+arg_8], rdx
0x1400c01aa  mov     [rsp-8+arg_0], rcx
0x1400c01af  push    rbp
0x1400c01b0  push    rbx
0x1400c01b1  push    rsi
0x1400c01b2  push    rdi
0x1400c01b3  push    r12
0x1400c01b5  push    r13
0x1400c01b7  push    r14
0x1400c01b9  lea     rbp, [rsp-1Fh]
0x1400c01be  sub     rsp, 100h
0x1400c01c5  xor     r14d, r14d
0x1400c01c8  mov     rbx, rcx
0x1400c01cb  mov     rcx, [rcx+8]
0x1400c01cf  mov     rsi, r8
0x1400c01d2  mov     [rbp+4Fh+var_78], rcx
0x1400c01d6  mov     [rbp+4Fh+var_90], r14
0x1400c01da  mov     [rsp+130h+var_EC], r14w
0x1400c01e0  mov     r13, [rcx+0D28h]
0x1400c01e7  mov     [rbp+4Fh+var_48], r14w
0x1400c01ec  mov     [rbp+4Fh+var_46], r14b
0x1400c01f0  mov     [rbp+4Fh+var_38], r14d
0x1400c01f4  mov     [rsp+130h+var_D0], r14
0x1400c01f9  mov     [rbp+4Fh+var_C8], r14
0x1400c01fd  movzx   eax, byte ptr [rcx+58h]
0x1400c0201  mov     [rsp+130h+var_E0], r13
0x1400c0206  mov     [rsp+130h+var_F0], r14b
0x1400c020b  cmp     al, 2
0x1400c020d  jnz     short loc_1400C0218
0x1400c020f  cmp     dword ptr [rcx+40h], 0Ch
0x1400c0213  setnz   al
0x1400c0216  inc     al
0x1400c0218  mov     rdx, [rsi+10h]; unsigned __int64
0x1400c021c  xor     r9d, r9d; int *
0x1400c021f  movzx   eax, al
0x1400c0222  xor     r8d, r8d; unsigned __int8
0x1400c0225  mov     rdi, r14
0x1400c0228  mov     [rbp+4Fh+Entry], r14
0x1400c022c  mov     rcx, [rcx+rax*8+0E28h]
0x1400c0234  mov     [rbp+4Fh+var_A0], rcx
0x1400c0238  lea     rcx, [rbp+4Fh+var_90]; struct _SmsContainerRangeMapListHead **
0x1400c023c  call    ?InitializeContainerRangeMapListHead@CmsContainerRangeMap@@SAJPEAPEAU_SmsContainerRangeMapListHead@@_KEPEAJ@Z; CmsContainerRangeMap::InitializeContainerRangeMapListHead(_SmsContainerRangeMapListHead * *,unsigned __int64,uchar,long *)
0x1400c0241  mov     r12d, eax
0x1400c0244  test    eax, eax
0x1400c0246  js      loc_1400C0C8E
0x1400c024c  mov     byte ptr [rsp+130h+var_108], dil
0x1400c0251  lea     r8, [rbp+4Fh+var_60]
0x1400c0255  xor     r9d, r9d
0x1400c0258  mov     byte ptr [rsp+130h+var_110], dil
0x1400c025d  mov     rdx, rbx
0x1400c0260  mov     [rsp+130h+arg_18], r15
0x1400c0268  mov     [rbp+4Fh+var_98], r14
0x1400c026c  mov     [rsp+130h+var_E8], r14d
0x1400c0271  call    ?BeginTopLevelActionInternal@CmsVolume@@QEAAXPEAVCmsTransactionContext@@PEAU_SmsTopLevelAction@@EEW4FoldOnlyTla@@@Z; CmsVolume::BeginTopLevelActionInternal(CmsTransactionContext *,_SmsTopLevelAction *,uchar,uchar,FoldOnlyTla)
0x1400c0276  mov     r15, [rsi+18h]
0x1400c027a  mov     [rbp+4Fh+var_B8], r15
0x1400c027e  test    r15, r15
0x1400c0281  jz      loc_1400C0C5E
0x1400c0287  nop     word ptr [rax+rax+00000000h]
0x1400c0290  test    byte ptr [r15+0Eh], 1
0x1400c0295  mov     rcx, r15
0x1400c0298  mov     [rbp+4Fh+var_70], rcx
0x1400c029c  jnz     loc_1400C056F
0x1400c02a2  mov     rax, [rbp+4Fh+arg_8]
0x1400c02a6  movzx   ecx, byte ptr [rax+34h]
0x1400c02aa  xor     eax, eax
0x1400c02ac  mov     [rbp+4Fh+var_80], rax
0x1400c02b0  mov     eax, 1
0x1400c02b5  shl     eax, cl
0x1400c02b7  dec     eax
0x1400c02b9  movsxd  rdx, eax
0x1400c02bc  movzx   eax, word ptr [r15+8]
0x1400c02c1  and     rdx, rax
0x1400c02c4  mov     rax, [rsi+10h]
0x1400c02c8  shl     rax, cl
0x1400c02cb  or      rdx, rax
0x1400c02ce  movzx   eax, word ptr [r15+0Ah]
0x1400c02d3  mov     [rbp+4Fh+var_88], rdx
0x1400c02d7  mov     [rbp+4Fh+var_B0], rdx
0x1400c02db  mov     [rbp+4Fh+var_A8], rax
0x1400c02df  test    rax, rax
0x1400c02e2  jz      loc_1400C053D
0x1400c02e8  xor     esi, esi
0x1400c02ea  nop     word ptr [rax+rax+00h]
0x1400c02f0  lea     rax, [rbp+4Fh+Entry]
0x1400c02f4  mov     rdx, rbx; struct CmsTransactionContext *
0x1400c02f7  mov     [rsp+130h+var_F8], rax; struct CmsRefcountCacheEntry **
0x1400c02fc  lea     r9, [rsp+130h+var_D0]; struct _RANGE *
0x1400c0301  lea     rax, [rsp+130h+var_F0]
0x1400c0306  mov     [rsp+130h+var_100], rsi; unsigned __int8 *
0x1400c030b  mov     [rsp+130h+var_108], rax; unsigned __int8 *
0x1400c0310  lea     r8, [rbp+4Fh+var_B0]; struct _RANGE *
0x1400c0314  lea     rax, [rsp+130h+var_EC]
0x1400c0319  mov     rcx, r13; this
0x1400c031c  mov     [rsp+130h+var_110], rax; unsigned __int16 *
0x1400c0321  call    ?GetNextRange@CmsBlockRefcount@@QEAAJPEAVCmsTransactionContext@@PEBU_RANGE@@PEAU3@PEAGPEAE4PEAPEAVCmsRefcountCacheEntry@@@Z; CmsBlockRefcount::GetNextRange(CmsTransactionContext *,_RANGE const *,_RANGE *,ushort *,uchar *,uchar *,CmsRefcountCacheEntry * *)
0x1400c0326  mov     r12d, eax
0x1400c0329  test    eax, eax
0x1400c032b  js      loc_1400C0509
0x1400c0331  movzx   eax, [rsp+130h+var_EC]
0x1400c0336  test    ax, ax
0x1400c0339  jnz     loc_1400C0598
0x1400c033f  cmp     [rsp+130h+var_F0], al
0x1400c0343  jz      loc_1400C0598
0x1400c0349  mov     rdi, [rbp+4Fh+Entry]
0x1400c034d  xor     r12d, r12d
0x1400c0350  mov     rsi, [rsp+130h+var_D0]
0x1400c0355  mov     r14, [rbp+4Fh+var_C8]
0x1400c0359  mov     r15, [rbx+8]
0x1400c035d  sub     rsi, [rdi+10h]
0x1400c0361  add     r14, rsi
0x1400c0364  cmp     [rdi+48h], r12
0x1400c0368  jnz     short loc_1400C03A2
0x1400c036a  xor     edx, edx
0x1400c036c  lea     rcx, [rdi+38h]
0x1400c0370  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x1400c0377  nop     dword ptr [rax+rax+00h]
0x1400c037c  mov     rcx, rdi; this
0x1400c037f  call    ?AllocateArray@CmsRefcountCacheEntry@@QEAAJXZ; CmsRefcountCacheEntry::AllocateArray(void)
0x1400c0384  xor     edx, edx
0x1400c0386  lea     rcx, [rdi+38h]
0x1400c038a  mov     r12d, eax
0x1400c038d  call    cs:__imp_ExReleasePushLockEx
0x1400c0394  nop     dword ptr [rax+rax+00h]
0x1400c0399  test    r12d, r12d
0x1400c039c  js      loc_1400C050D
0x1400c03a2  cmp     rsi, r14
0x1400c03a5  jnb     short loc_1400C03E8
0x1400c03a7  nop     word ptr [rax+rax+00000000h]
0x1400c03b0  xor     r12d, r12d
0x1400c03b3  mov     r8d, 3FFFh
0x1400c03b9  mov     r9d, 4000h
0x1400c03bf  nop
0x1400c03c0  mov     rcx, [rdi+48h]
0x1400c03c4  movzx   eax, word ptr [rcx+rsi*2]
0x1400c03c8  test    ax, ax
0x1400c03cb  jns     short loc_1400C03E0
0x1400c03cd  movzx   edx, ax
0x1400c03d0  and     dx, r8w
0x1400c03d4  or      dx, r9w
0x1400c03d8  lock cmpxchg [rcx+rsi*2], dx
0x1400c03de  jnz     short loc_1400C03C0
0x1400c03e0  inc     rsi
0x1400c03e3  cmp     rsi, r14
0x1400c03e6  jb      short loc_1400C03B0
0x1400c03e8  test    byte ptr [rdi+32h], 4
0x1400c03ec  nop
0x1400c03ed  jz      short loc_1400C03F7
0x1400c03ef  lock and word ptr [rdi+32h], 0FFF7h
0x1400c03f5  jmp     short loc_1400C0425
0x1400c03f7  prefetchw byte ptr [rdi+32h]
0x1400c03fb  movzx   eax, word ptr [rdi+32h]
0x1400c03ff  nop
0x1400c0400  movzx   ecx, ax
0x1400c0403  or      cx, 4
0x1400c0407  lock cmpxchg [rdi+32h], cx
0x1400c040d  jnz     short loc_1400C0400
0x1400c040f  nop
0x1400c0410  nop
0x1400c0411  lock and word ptr [rdi+32h], 0FFF7h
0x1400c0417  nop
0x1400c0418  bt      ax, 2
0x1400c041d  jb      short loc_1400C0426
0x1400c041f  nop
0x1400c0420  lock inc dword ptr [r13+44h]
0x1400c0425  nop
0x1400c0426  lea     rdx, [r13+50h]; union _SLIST_HEADER *
0x1400c042a  mov     rcx, rdi; this
0x1400c042d  call    ?AddForProcessing@CmsRefcountCacheEntry@@QEAAEPEAT_SLIST_HEADER@@@Z; CmsRefcountCacheEntry::AddForProcessing(_SLIST_HEADER *)
0x1400c0432  test    al, al
0x1400c0434  jz      short loc_1400C043D
0x1400c0436  nop
0x1400c0437  lock inc dword ptr [r13+40h]
0x1400c043c  nop
0x1400c043d  mov     rax, [r15+6B0h]
0x1400c0444  test    dword ptr [rax+78h], 100h
0x1400c044b  jz      short loc_1400C045B
0x1400c044d  mov     rcx, [r15+30h]; struct _VCB *
0x1400c0451  lea     rdx, [rsp+130h+var_D0]; struct _RANGE *
0x1400c0456  call    ?MsKmeLogOverwriteOrFree@@YAXQEAU_VCB@@PEBU_RANGE@@@Z; MsKmeLogOverwriteOrFree(_VCB * const,_RANGE const *)
0x1400c045b  test    r12d, r12d
0x1400c045e  js      loc_1400C050D
0x1400c0464  lea     rcx, [rdi+38h]
0x1400c0468  xor     edx, edx
0x1400c046a  call    cs:__imp_ExReleasePushLockEx
0x1400c0471  nop     dword ptr [rax+rax+00h]
0x1400c0476  mov     eax, 0FFFFFFFFh
0x1400c047b  lock xadd [rdi+30h], ax
0x1400c0481  cmp     ax, 1
0x1400c0485  jnz     short loc_1400C04BE
0x1400c0487  test    rdi, rdi
0x1400c048a  jz      short loc_1400C04BE
0x1400c048c  mov     rdx, [rdi+48h]; Entry
0x1400c0490  test    rdx, rdx
0x1400c0493  jz      short loc_1400C04A8
0x1400c0495  lea     rcx, ?ArraysLookasideList@CmsRefcountCacheEntry@@0U_NPAGED_LOOKASIDE_LIST@@A; Lookaside
0x1400c049c  call    cs:__imp_ExFreeToNPagedLookasideList
0x1400c04a3  nop     dword ptr [rax+rax+00h]
0x1400c04a8  mov     rdx, rdi; Entry
0x1400c04ab  lea     rcx, ?EntriesLookasideList@CmsRefcountCacheEntry@@0U_NPAGED_LOOKASIDE_LIST@@A; Lookaside
0x1400c04b2  call    cs:__imp_ExFreeToNPagedLookasideList
0x1400c04b9  nop     dword ptr [rax+rax+00h]
0x1400c04be  mov     rbx, [rbp+4Fh+arg_0]
0x1400c04c2  lea     rax, [rbp+4Fh+Entry]
0x1400c04c6  mov     [rsp+130h+var_F8], rax; struct CmsRefcountCacheEntry **
0x1400c04cb  lea     r9, [rsp+130h+var_D0]; struct _RANGE *
0x1400c04d0  xor     esi, esi
0x1400c04d2  lea     rax, [rsp+130h+var_F0]
0x1400c04d7  mov     [rsp+130h+var_100], rsi; unsigned __int8 *
0x1400c04dc  lea     r8, [rbp+4Fh+var_B0]; struct _RANGE *
0x1400c04e0  mov     [rsp+130h+var_108], rax; unsigned __int8 *
0x1400c04e5  mov     rdx, rbx; struct CmsTransactionContext *
0x1400c04e8  lea     rax, [rsp+130h+var_EC]
0x1400c04ed  mov     [rbp+4Fh+Entry], rsi
0x1400c04f1  mov     rcx, r13; this
0x1400c04f4  mov     [rsp+130h+var_110], rax; unsigned __int16 *
0x1400c04f9  call    ?GetNextRange@CmsBlockRefcount@@QEAAJPEAVCmsTransactionContext@@PEBU_RANGE@@PEAU3@PEAGPEAE4PEAPEAVCmsRefcountCacheEntry@@@Z; CmsBlockRefcount::GetNextRange(CmsTransactionContext *,_RANGE const *,_RANGE *,ushort *,uchar *,uchar *,CmsRefcountCacheEntry * *)
0x1400c04fe  mov     r12d, eax
0x1400c0501  test    eax, eax
0x1400c0503  jns     loc_1400C0331
0x1400c0509  mov     rdi, [rbp+4Fh+Entry]
0x1400c050d  mov     rax, [rbp+4Fh+var_80]
0x1400c0511  mov     r13, [rsp+130h+var_E0]
0x1400c0516  mov     r15, [rbp+4Fh+var_B8]
0x1400c051a  mov     rsi, [rbp+4Fh+arg_10]
0x1400c051e  mov     rbx, [rbp+4Fh+arg_0]
0x1400c0522  mov     r14d, [rsp+130h+var_E8]
0x1400c0527  test    rax, rax
0x1400c052a  jz      short loc_1400C053D
0x1400c052c  mov     rcx, [rbp+4Fh+var_78]
0x1400c0530  nop
0x1400c0531  neg     rax
0x1400c0534  lock add [rcx+0EE8h], rax
0x1400c053c  nop
0x1400c053d  test    rdi, rdi
0x1400c0540  jz      short loc_1400C0562
0x1400c0542  lea     rcx, [rdi+38h]
0x1400c0546  xor     edx, edx
0x1400c0548  call    cs:__imp_ExReleasePushLockEx
0x1400c054f  nop     dword ptr [rax+rax+00h]
0x1400c0554  mov     rcx, rdi; Entry
0x1400c0557  call    ?Release@CmsRefcountCacheEntry@@QEAAXXZ; CmsRefcountCacheEntry::Release(void)
0x1400c055c  xor     edi, edi
0x1400c055e  mov     [rbp+4Fh+Entry], rdi
0x1400c0562  test    r12d, r12d
0x1400c0565  js      loc_1400C0B4A
0x1400c056b  mov     rcx, [rbp+4Fh+var_70]
0x1400c056f  mov     r15, [r15]
0x1400c0572  inc     r14d
0x1400c0575  mov     [rbp+4Fh+var_B8], r15
0x1400c0579  mov     [rsp+130h+var_E8], r14d
0x1400c057e  mov     [rbp+4Fh+var_98], rcx
0x1400c0582  test    r15, r15
0x1400c0585  jnz     loc_1400C0290
0x1400c058b  mov     r15, rcx
0x1400c058e  mov     [rsp+130h+var_E8], r14d
0x1400c0593  jmp     loc_1400C0B4E
0x1400c0598  mov     rdi, [rbp+4Fh+Entry]
0x1400c059c  test    ax, ax
0x1400c059f  jnz     loc_1400C086E
0x1400c05a5  mov     r14, [rbp+4Fh+var_A8]
0x1400c05a9  cmp     [rbp+4Fh+var_C8], r14
0x1400c05ad  jz      loc_1400C0A4F
0x1400c05b3  mov     r15, [rbp+4Fh+var_B8]
0x1400c05b7  test    byte ptr [r15+0Ch], 4
0x1400c05bc  jz      short loc_1400C05F0
0x1400c05be  mov     r14, [rbp+4Fh+var_A0]
0x1400c05c2  cmp     [r14+8], ax
0x1400c05c7  jnz     short loc_1400C05CE
0x1400c05c9  mov     r14, rsi
0x1400c05cc  jmp     short loc_1400C05F3
0x1400c05ce  movzx   edx, word ptr [r14+14h]
0x1400c05d3  sub     edx, [r14+0Ch]
0x1400c05d7  mov     rax, [rbp+4Fh+var_78]
0x1400c05db  mov     r14, [rbp+4Fh+var_C8]
0x1400c05df  mov     ecx, [rax+40h]
0x1400c05e2  shl     r14, cl
0x1400c05e5  movzx   ecx, dl
0x1400c05e8  mov     r14d, r14d
0x1400c05eb  shr     r14, cl
0x1400c05ee  jmp     short loc_1400C05F3
0x1400c05f0  mov     r14d, esi
0x1400c05f3  xor     ecx, ecx; ProcNumber
0x1400c05f5  lea     ebx, [r14+10h]
0x1400c05f9  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x1400c0600  nop     dword ptr [rax+rax+00h]
0x1400c0605  xor     edx, edx
0x1400c0607  div     cs:?NumProcessors@@3KA; ulong NumProcessors
0x1400c060d  lea     rsi, [rdx+rdx*2]
0x1400c0611  shl     rsi, 6
0x1400c0615  add     rsi, cs:qword_1402624B0
0x1400c061c  mov     eax, [rsi]
0x1400c061e  cmp     rbx, rax
0x1400c0621  ja      short loc_1400C069F
0x1400c0623  cmp     byte ptr [rsi+8], 0
0x1400c0627  jz      short loc_1400C064F
0x1400c0629  cmp     byte ptr [rsi+9], 0
0x1400c062d  lea     rcx, [rsi+40h]; Lookaside
0x1400c0631  jz      short loc_1400C0641
  ... truncated ...
```
