# CmsVolume::PersistCheckpointCaches(CmsTransactionContext *,SmsWritePlan *,SmsDirtyTableEntries *,__int64)

- ea: `0x140030130`
- end: `0x140030eac`
- name: `?PersistCheckpointCaches@CmsVolume@@QEAAJPEAVCmsTransactionContext@@PEAUSmsWritePlan@@PEAUSmsDirtyTableEntries@@_J@Z`
- size: `3452`
- prototype: `__int64 __usercall@<rax>(CmsVolume *__hidden this@<rcx>, struct CmsTransactionContext *@<rdx>, struct SmsWritePlan *@<r8>, struct SmsDirtyTableEntries *@<r9>, __int64)`
- caller_count: `1`
- callee_count: `30`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x140147c6c`

## callees

- `0x140012c34`
- `0x1400130c0`
- `0x140014750`
- `0x1400147e0`
- `0x140018810`
- `0x14002e990`
- `0x14002eaa0`
- `0x14002f278`
- `0x14002f550`
- `0x14002ff00`
- `0x140030130`
- `0x140030ec0`
- `0x1400310e0`
- `0x1400318ac`
- `0x140031904`
- `0x14005c060`
- `0x14006ad20`
- `0x1400a889c`
- `0x1400a9214`
- `0x1400ae7a0`
- `0x1400ccdf4`
- `0x1400cd630`
- `0x1400ce3f4`
- `0x1400cfcb0`
- `0x1400d3348`
- `0x1400d4368`
- `0x140140f70`
- `0x140141dac`
- `0x140142358`
- `0x14014518c`

## import_xrefs

- `ntoskrnl!KdDebuggerEnabled` at `0x140030d46`
- `ntoskrnl!KdDebuggerEnabled` at `0x140030d5c`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140030c44`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140030c44`
- `ntoskrnl!ExAllocatePool2` at `0x1400305ef`
- `ntoskrnl!ExAllocatePool2` at `0x1400305ef`
- `ntoskrnl!ExAcquireAutoExpandPushLockShared` at `0x1400305b0`
- `ntoskrnl!ExAcquireAutoExpandPushLockShared` at `0x1400305b0`
- `ntoskrnl!ExReleaseAutoExpandPushLockShared` at `0x14003067c`
- `ntoskrnl!ExReleaseAutoExpandPushLockShared` at `0x140030c9c`
- `ntoskrnl!ExReleaseAutoExpandPushLockShared` at `0x14003067c`
- `ntoskrnl!ExReleaseAutoExpandPushLockShared` at `0x140030c9c`
- `ntoskrnl!ExAcquireAutoExpandPushLockExclusive` at `0x1401fb62c`
- `ntoskrnl!ExAcquireAutoExpandPushLockExclusive` at `0x1401fb62c`
- `ntoskrnl!ExReleaseAutoExpandPushLockExclusive` at `0x1401fb653`
- `ntoskrnl!ExReleaseAutoExpandPushLockExclusive` at `0x1401fb653`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x140030af3`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x140030af3`
- `ntoskrnl!RtlInitStrongEnumerationHashTable` at `0x140030611`
- `ntoskrnl!RtlInitStrongEnumerationHashTable` at `0x140030611`
- `ntoskrnl!RtlStronglyEnumerateEntryHashTable` at `0x140030625`
- `ntoskrnl!RtlStronglyEnumerateEntryHashTable` at `0x14003064f`
- `ntoskrnl!RtlStronglyEnumerateEntryHashTable` at `0x140030625`
- `ntoskrnl!RtlStronglyEnumerateEntryHashTable` at `0x14003064f`
- `ntoskrnl!RtlEndStrongEnumerationHashTable` at `0x140030668`
- `ntoskrnl!RtlEndStrongEnumerationHashTable` at `0x140030668`
- `ntoskrnl!ExReleasePushLockEx` at `0x140030bfd`
- `ntoskrnl!ExReleasePushLockEx` at `0x140030c67`
- `ntoskrnl!ExReleasePushLockEx` at `0x140030bfd`
- `ntoskrnl!ExReleasePushLockEx` at `0x140030c67`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400306c4`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400306c4`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140030b8e`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140030b8e`

## pseudocode

```c
__int64 __fastcall CmsVolume::PersistCheckpointCaches(
        CmsVolume *this,
        CmsVolume **a2,
        struct SmsWritePlan *a3,
        struct SmsDirtyTableEntries **a4,
        __int64 a5)
{
  CmsTransactionContext *v6; // rdi
  __int64 *v8; // rax
  __int64 v9; // rax
  __int64 v10; // rbx
  __int64 v11; // rcx
  __int64 v12; // rax
  __int64 i; // rbx
  CmsBPlusTable **v14; // rdi
  __int64 v15; // rdx
  CmsBPlusTable **v16; // rdx
  CmsVolumeContainer *v17; // rcx
  CmsBlockRefcount *v18; // rcx
  __int64 v19; // r14
  _QWORD *v20; // rsi
  __int64 v21; // rax
  _QWORD *v22; // rdi
  struct CmsTransactionContext *v23; // rdx
  CmsAllocator *v24; // r10
  bool v25; // zf
  __int64 v26; // rbx
  int updated; // r12d
  struct CmsBPlusTable *IntegrityStateTable; // rax
  struct CmsBPlusTable *v30; // r8
  __int64 v31; // r15
  __int64 v32; // rcx
  __int64 v33; // rsi
  __int64 v34; // rbx
  __int64 v35; // r9
  unsigned int v36; // r15d
  unsigned __int64 v37; // rax
  __int64 v38; // r8
  __int64 Pool2; // r14
  __int64 v40; // rdi
  __int64 j; // rax
  __int64 v42; // r8
  void *v43; // rcx
  struct SmsWritePlan *v44; // rdi
  int v45; // ebx
  __int64 v46; // rcx
  int v47; // eax
  __int64 v48; // rbx
  __int64 v49; // rbx
  CmsVolume *v50; // rcx
  __int64 v51; // rdi
  __int64 v52; // rbx
  CmsBPlusTable *v53; // rcx
  unsigned __int8 v54; // r8
  CmsVolume *v55; // rdx
  _QWORD *v56; // rax
  _QWORD *v57; // rcx
  unsigned __int8 v58; // cl
  CmsVolume *v59; // rcx
  union _SLIST_HEADER *v60; // rbx
  PSLIST_ENTRY v61; // rax
  PSLIST_ENTRY v62; // rsi
  struct _SLIST_ENTRY *Next; // r14
  unsigned int v64; // edx
  __int64 v65; // rax
  struct SmsHashEntryLite **v66; // rdi
  struct SmsHashEntryLite *v67; // rbx
  struct SmsHashEntryLite *v68; // rcx
  int v69; // r14d
  struct SmsHashEntryLite *v70; // rax
  __int64 v71; // rdx
  __int64 v72; // r8
  __int64 v73; // r9
  CmsVolume *v74; // rcx
  int v75; // eax
  __int64 GlobalTablesGeneration; // rax
  unsigned __int8 v77; // [rsp+28h] [rbp-E0h]
  void (__usercall *v78)(struct CmsTransactionContext *@<rcx>, struct CmsHashTable *@<rdx>, unsigned int@<r8d>, unsigned int@<r9d>, struct CmsAllocator *, struct SmsWritePlan *); // [rsp+48h] [rbp-C0h] BYREF
  _QWORD v79[3]; // [rsp+50h] [rbp-B8h] BYREF
  __int16 v80; // [rsp+68h] [rbp-A0h]
  char v81; // [rsp+6Ah] [rbp-9Eh]
  unsigned __int8 v82; // [rsp+6Bh] [rbp-9Dh]
  unsigned __int8 v83; // [rsp+6Ch] [rbp-9Ch]
  CmsVolume *v84; // [rsp+70h] [rbp-98h]
  __int64 v85; // [rsp+78h] [rbp-90h]
  __int64 v86; // [rsp+80h] [rbp-88h]
  __int64 v87; // [rsp+88h] [rbp-80h]
  __int64 v88; // [rsp+90h] [rbp-78h]
  __int64 v89; // [rsp+98h] [rbp-70h]
  __int64 v90; // [rsp+A0h] [rbp-68h]
  _QWORD v91[2]; // [rsp+A8h] [rbp-60h] BYREF
  _QWORD v92[2]; // [rsp+B8h] [rbp-50h] BYREF
  int v93; // [rsp+C8h] [rbp-40h]
  int v94; // [rsp+D0h] [rbp-38h]
  unsigned int v95; // [rsp+D4h] [rbp-34h]
  __int64 v96; // [rsp+D8h] [rbp-30h]
  __int64 v97; // [rsp+E0h] [rbp-28h] BYREF
  __int128 v98; // [rsp+E8h] [rbp-20h]
  __int128 v99; // [rsp+F8h] [rbp-10h]
  struct SmsWritePlan *v101; // [rsp+158h] [rbp+50h] BYREF

  v101 = a3;
  v6 = (CmsTransactionContext *)a2;
  if ( (*((_DWORD *)a3 + 264) & 1) != 0 )
  {
    v86 = *(_QWORD *)(**((_QWORD **)this + 408) + 40LL);
    v8 = *(__int64 **)(*((_QWORD *)this + 410) + 8LL);
    if ( !v8 || (v9 = *v8) == 0 || !*(_QWORD *)(v9 + 72) || !*(_QWORD *)(v9 + 40) )
      v9 = 0;
    v10 = *((_QWORD *)this + 418);
    v88 = *(_QWORD *)(v9 + 40);
    v87 = *(_QWORD *)(*(_QWORD *)(*((_QWORD *)this + 413) + 8LL) + 40LL);
    v11 = *(_QWORD *)(*((_QWORD *)this + 409) + 16LL);
    v89 = *(_QWORD *)(*(_QWORD *)(v11 + 32) + 40LL);
    v12 = *(_QWORD *)(*(_QWORD *)(v11 + 40) + 40LL);
    v78 = CmsBPlusTable::MoveSmallAllocatorPagesToWillFreeRanges;
    v90 = v12;
    if ( *(_BYTE *)(v10 + 32) )
    {
      updated = CmsFailoverBPlusTable::UpdateDataWithRoot(
                  *(CmsFailoverBPlusTable **)(v10 + 40),
                  (struct CmsTransactionContext *)a2,
                  (const void *)(v10 + 8),
                  0x18u,
                  0,
                  0);
      if ( updated < 0 )
      {
        CmsTransactionContext::Abort(v6, v71, v72);
        goto LABEL_42;
      }
      *(_BYTE *)(v10 + 32) = 0;
      CmsTransactionContext::Commit(v6, 0, 0, 0);
    }
    CmsTransactionContext::Commit(v6, 0, 0, 0);
    if ( a4 )
    {
      while ( a4 )
      {
        LODWORD(i) = 0;
        while ( (unsigned int)i < 8 )
        {
          v14 = &a4[12 * (unsigned int)i + 1];
          if ( *v14 )
            goto LABEL_15;
          LODWORD(i) = i + 1;
        }
        a4 = (struct SmsDirtyTableEntries **)*a4;
      }
      v14 = 0;
      LODWORD(i) = -1;
LABEL_15:
      if ( v14 )
      {
        while ( 2 )
        {
          v15 = *(_QWORD *)(*((_QWORD *)*v14 + 9) + 384LL);
          if ( (unsigned __int64)(v15 - 1) <= 3 || v15 == 6 )
            CmsBPlusTable::OptimizeTree(*v14, (struct CmsTransactionContext *)a2);
          v16 = &v14[-12 * (int)i - 1];
LABEL_19:
          if ( v16 )
          {
            for ( i = (unsigned int)(i + 1); ; i = (unsigned int)(i + 1) )
            {
              if ( (unsigned int)i >= 8 )
              {
                v16 = (CmsBPlusTable **)*v16;
                LODWORD(i) = -1;
                goto LABEL_19;
              }
              v14 = &v16[12 * i + 1];
              if ( *v14 )
                break;
            }
            if ( v14 )
              continue;
          }
          break;
        }
      }
      v6 = (CmsTransactionContext *)a2;
    }
    v17 = (CmsVolumeContainer *)*((_QWORD *)this + 409);
    if ( *((_BYTE *)v17 + 281) )
    {
      CmsVolumeContainer::PersistContainerCache(v17, v6, 0);
      CmsTransactionContext::Commit(v6, 0, 0, 0);
    }
    if ( *((_BYTE *)this + 3393) )
    {
      if ( (*((_DWORD *)this + 849) & 0x20000000) == 0 )
      {
        v18 = (CmsBlockRefcount *)*((unsigned int *)v101 + 264);
        if ( ((unsigned __int8)v18 & 2) == 0 || ((unsigned __int8)v18 & 1) != 0 )
        {
          v19 = *((_QWORD *)v101 + 1) + 192LL;
          v20 = (_QWORD *)v19;
          while ( 1 )
          {
            v21 = v20[73];
            v22 = v20 - 24;
            v20 = (_QWORD *)*v20;
            if ( v21 )
            {
              _InterlockedAdd64((volatile signed __int64 *)this + 468, -v21);
              ExAcquireAutoExpandPushLockExclusive((char *)this + 3856, 2);
              CmsVolume::RemoveReservationForGlobalStreamReserve(this, v22[97]);
              ExReleaseAutoExpandPushLockExclusive((char *)this + 3856, 2);
              v22[97] = 0;
            }
            if ( !v22[94] )
              goto LABEL_35;
            if ( (*(_DWORD *)a2 & 0x400LL) != 0 )
              break;
            if ( CmsBlockRefcount::ProcessDeleteQueue(
                   v18,
                   (struct CmsTransactionContext *)a2,
                   (struct CmsContainerRangeMap *)(v22 + 90),
                   (struct CmsContainerRangeMap *)(v22 + 98)) >= 0 )
              goto LABEL_150;
            CmsBPlusTable::EnqueueTreeUpdate(*v22, a2, 12);
LABEL_151:
            CmsTransactionContext::Commit((CmsTransactionContext *)a2, 0, 0, 0);
LABEL_35:
            v23 = (struct CmsTransactionContext *)*(unsigned __int8 *)(*v22 + 14LL);
            if ( ((unsigned __int8)v23 & 7) == 0
              || (v18 = (CmsBlockRefcount *)*((_QWORD *)this + 410)) != 0
              && (IntegrityStateTable = CmsIntegrityState::GetIntegrityStateTable(v18), v30 == IntegrityStateTable) )
            {
              if ( v22[102] )
              {
                CmsAllocator::MergeIntoProcessedDeleteQueue(
                  *((CmsAllocator **)this + (((unsigned int)v23 >> 3) & 7) + 402),
                  v23,
                  (struct CmsContainerRangeMap *)(v22 + 98),
                  v22[105]);
                v22[105] = 0;
              }
            }
            if ( v20 == (_QWORD *)v19 )
            {
              v6 = (CmsTransactionContext *)a2;
              goto LABEL_40;
            }
          }
          CmsContainerRangeMap::Merge((CmsContainerRangeMap *)(v22 + 98), (struct CmsContainerRangeMap *)(v22 + 90));
LABEL_150:
          CmsContainerRangeMap::DeleteAll((CmsContainerRangeMap *)(v22 + 90), 0);
          goto LABEL_151;
        }
      }
    }
LABEL_40:
    CmsTransactionContext::Commit(v6, 0, 0, 0);
    v24 = (CmsAllocator *)*((_QWORD *)this + 408);
    v25 = *((_BYTE *)v24 + 492) == 3;
    v26 = *(_QWORD *)(*(_QWORD *)v24 + 72LL);
    v92[0] = v24;
    v93 = 0;
    v92[1] = *((_QWORD *)v101 + 153);
    if ( v25 )
    {
      v73 = *(_QWORD *)(v26 + 840);
      if ( v73 > 0 )
      {
        CmsAllocator::AdjustAllocatorSummary(v24, 0, 0, -v73, 0);
        *(_QWORD *)(v26 + 840) = 0;
      }
    }
    updated = CmsContainerRangeMap::ParallelForEachBucket(
                (CmsContainerRangeMap *)(v26 + 784),
                v6,
                (int (*)(struct CmsTransactionCore *, struct CmsContainerRangeMap *, struct _SmsContainerRangeMapListHead *, struct _SmsQuickIndex *, void *))CmsAllocator::ProcessDeleteQueueEntryParallel,
                v92,
                v77);
    if ( updated < 0 )
      goto LABEL_42;
    updated = v93;
    if ( v93 < 0 )
      goto LABEL_42;
    CmsTransactionContext::Commit(v6, 0, 0, 0);
    updated = CmsAllocator::PersistFilteredView(*((CmsAllocator **)this + 408), v6);
    if ( updated < 0 )
      goto LABEL_42;
    CmsTransactionContext::Commit(v6, 0, 0, 0);
    _InterlockedOr((volatile signed __int32 *)this + 849, 0x800u);
    updated = 0;
    v31 = *((_QWORD *)this + 413);
    if ( *(_DWORD *)(v31 + 16) == 2 )
    {
LABEL_95:
      v60 = (union _SLIST_HEADER *)(v31 + 80);
      while ( 1 )
      {
        v61 = ExpInterlockedPopEntrySList(v60);
        if ( !v61 )
          break;
        v61->Next = 0;
        v62 = v61 - 2;
        _InterlockedAnd16((volatile signed __int16 *)&v61[1].Next + 1, 0xFFFDu);
        _InterlockedDecrement((volatile signed __int32 *)(v31 + 64));
        if ( (WORD1(v61[1].Next) & 4) != 0 )
          _InterlockedDecrement((volatile signed __int32 *)(v31 + 68));
        if ( (WORD1(v62[3].Next) & 4) != 0 )
        {
          updated = CmsBlockRefcount::PersistCacheEntry(
                      (CmsBlockRefcount *)v31,
                      v6,
                      (struct CmsRefcountCacheEntry *)v62);
          if ( updated < 0 )
          {
            if ( CmsRefcountCacheEntry::AddForProcessing((CmsRefcountCacheEntry *)v62, v60) )
              _InterlockedIncrement((volatile signed __int32 *)(v31 + 64));
            if ( (WORD1(v62[3].Next) & 4) != 0 )
              _InterlockedIncrement((volatile signed __int32 *)(v31 + 68));
            CmsRefcountCacheEntry::Release(v62);
            break;
          }
        }
        else if ( (WORD1(v62[3].Next) & 8) != 0 )
        {
          v96 = 0;
          Next = v62[1].Next;
          v94 = 0;
          v64 = ((69069 * (_DWORD)Next + 1) & 0xFFFF0000
               | (unsigned __int64)((unsigned int)(1103515245 * (_DWORD)Next + 12345) >> 16))
              % *(unsigned int *)(v31 + 40);
          v65 = *(_QWORD *)(v31 + 32);
          v95 = v64;
          v66 = (struct SmsHashEntryLite **)(v65 + 24LL * v64);
          ExAcquirePushLockExclusiveEx(v66 + 2, 0);
          if ( v66[1] )
          {
            v67 = *v66;
            while ( *((struct _SLIST_ENTRY **)v67 + 2) != Next )
            {
              v67 = *(struct SmsHashEntryLite **)v67;
              if ( v67 == *v66 )
                goto LABEL_117;
            }
            if ( v67 )
            {
              if ( CmsRefcountCacheEntry::CanBeDeleted(v67) )
              {
                v68 = (struct SmsHashEntryLite *)*((_QWORD *)v67 + 1);
                v69 = 0;
                v70 = *(struct SmsHashEntryLite **)v67;
                *(_QWORD *)v68 = *(_QWORD *)v67;
                *((_QWORD *)v70 + 1) = v68;
                if ( *v66 == v67 )
                  *v66 = v70;
                if ( v68 == v67 )
                  *v66 = 0;
                v66[1] = (struct SmsHashEntryLite *)((char *)v66[1] - 1);
                _InterlockedDecrement((volatile signed __int32 *)(v31 + 44));
              }
              else
              {
                v69 = -1073741772;
              }
              ExReleasePushLockEx(v66 + 2, 0);
              if ( v69 >= 0 )
              {
                _InterlockedAnd16((volatile signed __int16 *)&v62[3].Next + 1, 0xFFF7u);
                CmsRefcountCacheEntry::Release(v62);
              }
            }
          }
          else
          {
LABEL_117:
            ExReleasePushLockEx(v66 + 2, 0);
          }
          v6 = (CmsTransactionContext *)a2;
        }
        v60 = (union _SLIST_HEADER *)(v31 + 80);
        if ( _InterlockedExchangeAdd16((volatile signed __int16 *)&v62[3], 0xFFFFu) == 1 )
        {
          CmsRefcountCacheEntry::~CmsRefcountCacheEntry((CmsRefcountCacheEntry *)v62);
          ExFreeToNPagedLookasideList(&CmsRefcountCacheEntry::EntriesLookasideList, v62);
          goto LABEL_95;
        }
      }
      if ( v6 )
        CmsBPlusTable::OptimizeTree(*(CmsBPlusTable **)(v31 + 8), v6);
      if ( updated < 0 )
        goto LABEL_42;
    }
    CmsTransactionContext::Commit(v6, 0, 0, 0);
    v32 = *((_QWORD *)this + 410);
    if ( v32 && *(_BYTE *)(v32 + 16) )
    {
      updated = CmsAllocator::PersistFilteredView(*(CmsAllocator **)(v32 + 8), v6);
      if ( updated < 0 )
        goto LABEL_42;
      CmsTransactionContext::Commit(v6, 0, 0, 0);
    }
    v33 = *((_QWORD *)this + 409);
    if ( (*(_BYTE *)(v33 + 760) & 2) != 0 )
    {
      v51 = *(_QWORD *)(v33 + 16);
      v52 = 0;
      v80 = 0;
      v81 = 0;
      LODWORD(v85) = 0;
      do
      {
        v53 = *(CmsBPlusTable **)(v51 + 8 * v52 + 32);
        if ( v53 && !CmsBPlusTable::EnterTree(v53, (struct CmsTransactionContext *)a2) )
          break;
        v52 = (unsigned int)(v52 + 1);
      }
      while ( (unsigned int)v52 < 2 );
      if ( (*(_DWORD *)a2 & 0x200000) != 0 && (_BYTE)KdDebuggerEnabled )
        __debugbreak();
      v54 = *((_BYTE *)a2 + 131);
      v55 = *a2;
      LODWORD(v85) = (unsigned __int16)++*((_WORD *)a2 + 106);
      v79[0] = a2[18];
      v56 = (_QWORD *)((char *)a2[52] + 8);
      v81 = 0;
      v57 = (_QWORD *)*v56;
      v25 = *v56 == 0;
      v84 = v55;
      v82 = v54;
      if ( v25 )
        v57 = v56;
      HIBYTE(v80) = 0;
      v79[2] = a2[25];
      v79[1] = v57;
      v58 = *((_BYTE *)a2 + 132);
      *a2 = (CmsVolume *)((unsigned __int64)v55 & 0xFFFFEFFFFFFFFFFFuLL);
      v83 = v58;
      while ( 1 )
      {
        if ( v54 >= 0xDu )
          goto LABEL_88;
        if ( !a2[v54 + 70] )
          break;
        ++v54;
      }
      *((_BYTE *)a2 + 131) = v54;
LABEL_88:
      while ( v58 < 0xDu )
      {
        if ( !a2[v58 + 53] )
        {
          *((_BYTE *)a2 + 132) = v58;
          break;
        }
        ++v58;
      }
      if ( *((_BYTE *)a2 + 131) < *((_BYTE *)a2 + 130) && (_BYTE)KdDebuggerEnabled )
        __debugbreak();
      *((_BYTE *)a2 + 130) = *((_BYTE *)a2 + 131);
      v91[0] = v33 + 80;
      v91[1] = 200;
      updated = CmsFailoverBPlusTable::InvokeTableMethodInternal(
                  v51,
                  CmsFailoverBPlusTable::EmsPerformOnBoth,
                  a2,
                  CmsFailoverBPlusTable::InvokeTableMethod__CmsFailoverBPlusTable::UpdateDataWithRoot_::_2_::_lambda_1____::_2_::_lambda_1_::_lambda_invoker_cdecl_,
                  v91,
                  0,
                  0);
      v6 = (CmsTransactionContext *)a2;
      v59 = a2[1];
      if ( updated < 0 )
      {
        CmsVolume::AbortTopLevelAction(v59, (struct CmsTransactionContext *)a2, (struct _SmsTopLevelAction *)v79);
LABEL_65:
        v43 = *(void **)(v33 + 512);
        if ( v43 )
          ExFreePoolWithTag(v43, 0);
        *(_QWORD *)(v33 + 512) = 0;
        *(_DWORD *)(v33 + 520) = 0;
        if ( updated < 0 )
          goto LABEL_42;
        CmsTransactionContext::Commit(v6, 0, 0, 0);
        *(_BYTE *)(*((_QWORD *)this + 409) + 760LL) |= 0x20u;
        v44 = v101;
        if ( (*((_DWORD *)v101 + 264) & 1) != 0 )
        {
          v45 = 0;
          v46 = *((_QWORD *)v101 + 1) + 192LL;
          do
          {
            v45 += *(_DWORD *)(v46 + 180);
            v46 = *(_QWORD *)v46;
          }
          while ( v46 != *((_QWORD *)v101 + 1) + 192LL );
          v47 = *((_DWORD *)v101 + 262);
          if ( v45 > v47 )
          {
            updated = CmsLookasides::SatisfyReservation(20, (unsigned int)(v45 - v47));
            if ( updated < 0 )
              goto LABEL_42;
            updated = CmsLookasides::SatisfyReservation(21, (unsigned int)(v45 - *((_DWORD *)v44 + 263)));
            if ( updated < 0 )
            {
              _InterlockedAdd((volatile signed __int32 *)(qword_1402694A0 + 92), *((_DWORD *)v44 + 262) - v45);
              goto LABEL_42;
            }
            *((_DWORD *)v44 + 262) = v45;
            *((_DWORD *)v44 + 263) = v45;
          }
        }
        CmsBPlusTable::ParallelTuPageTableWork<void (*&)(CmsTransactionContext *,CmsHashTable *,unsigned long,unsigned long,CmsAllocator *,SmsWritePlan *),CmsAllocator * &,SmsWritePlan * &>(
          (__int64)a2,
          v86 + 16,
          (__int64)&v78,
          (__int64)this + 3256,
          (__int64)&v101);
        CmsBPlusTable::ParallelTuPageTableWork<void (*&)(CmsTransactionContext *,CmsHashTable *,unsigned long,unsigned long,CmsAllocator *,SmsWritePlan *),CmsAllocator * &,SmsWritePlan * &>(
          (__int64)a2,
          v87 + 16,
          (__int64)&v78,
          (__int64)this + 3256,
          (__int64)&v101);
        CmsBPlusTable::ParallelTuPageTableWork<void (*&)(CmsTransactionContext *,CmsHashTable *,unsigned long,unsigned long,CmsAllocator *,SmsWritePlan *),CmsAllocator * &,SmsWritePlan * &>(
          (__int64)a2,
          v88 + 16,
          (__int64)&v78,
          (__int64)this + 3256,
          (__int64)&v101);
        CmsBPlusTable::ParallelTuPageTableWork<void (*&)(CmsTransactionContext *,CmsHashTable *,unsigned long,unsigned long,CmsAllocator *,SmsWritePlan *),CmsAllocator * &,SmsWritePlan * &>(
          (__int64)a2,
          v89 + 16,
          (__int64)&v78,
          (__int64)this + 3248,
          (__int64)&v101);
        CmsBPlusTable::ParallelTuPageTableWork<void (*&)(CmsTransactionContext *,CmsHashTable *,unsigned long,unsigned long,CmsAllocator *,SmsWritePlan *),CmsAllocator * &,SmsWritePlan * &>(
          (__int64)a2,
          v90 + 16,
          (__int64)&v78,
          (__int64)this + 3248,
          (__int64)&v101);
        v48 = *((_QWORD *)this + 407);
        CmsContainerRangeMap::Merge(
          (CmsContainerRangeMap *)(*(_QWORD *)(*(_QWORD *)v48 + 72LL) + 784LL),
          *((struct CmsContainerRangeMap **)v101 + 155));
        *(_QWORD *)(*(_QWORD *)(*(_QWORD *)v48 + 72LL) + 840LL) = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)v48 + 72LL) + 840LL);
        v49 = *((_QWORD *)this + 406);
        CmsContainerRangeMap::Merge(
          (CmsContainerRangeMap *)(*(_QWORD *)(*(_QWORD *)v49 + 72LL) + 784LL),
          *((struct CmsContainerRangeMap **)v101 + 156));
        v50 = *(CmsVolume **)(*(_QWORD *)v49 + 72LL);
        *((_QWORD *)v50 + 105) = *((_QWORD *)v50 + 105);
        *((_QWORD *)v101 + 159) = 0;
        *((_QWORD *)v101 + 158) = 0;
        updated = CmsVolume::PersistSmallAllocator(
                    v50,
                    (struct CmsTransactionContext *)a2,
                    *((struct CmsAllocator **)this + 407),
                    v101,
                    *((struct SmsCheckpointContext **)v101 + 153));
        if ( updated >= 0 )
        {
          CmsTransactionContext::Commit((CmsTransactionContext *)a2, 0, 0, 0);
          v75 = CmsVolume::PersistSmallAllocator(
                  v74,
                  (struct CmsTransactionContext *)a2,
                  *((struct CmsAllocator **)this + 406),
                  v101,
                  *((struct SmsCheckpointContext **)v101 + 153));
          updated = v75;
          if ( v75 >= 0 )
          {
            CmsTransactionContext::Commit((CmsTransactionContext *)a2, 0, 0, 0);
            GlobalTablesGeneration = CmsVolume::GetGlobalTablesGeneration(this);
            if ( a5 == GlobalTablesGeneration )
              return (unsigned int)updated;
            updated = -1073741823;
          }
        }
LABEL_42:
        *(_BYTE *)(*((_QWORD *)this + 409) + 760LL) &= ~0x20u;
        _InterlockedAnd((volatile signed __int32 *)this + 849, 0xFFFFF7FF);
        return (unsigned int)updated;
      }
      CmsVolume::FoldTopLevelAction(v59, (struct CmsTransactionContext *)a2, (struct _SmsTopLevelAction *)v79);
      *(_BYTE *)(v33 + 760) &= ~2u;
      CmsTransactionContext::Commit((CmsTransactionContext *)a2, 0, 0, 0);
    }
    *(_BYTE *)(v33 + 760) |= 0x20u;
    *(_BYTE *)(v33 + 281) = 0;
    v97 = 0;
    v98 = 0;
    v99 = 0;
    v34 = ExAcquireAutoExpandPushLockShared(v33 + 56, 2);
    v36 = *(_DWORD *)(*(_QWORD *)(v33 + 48) + 20LL);
    v37 = (unsigned __int64)v36 << 6;
    if ( !is_mul_ok(8LL * v36, 8u) )
      v37 = -1;
    Pool2 = ExAllocatePool2(66, v37, 1766871885, v35);
    if ( Pool2 )
    {
      v40 = 0;
      RtlInitStrongEnumerationHashTable(*(_QWORD *)(v33 + 48), &v97);
      for ( j = RtlStronglyEnumerateEntryHashTable(*(_QWORD *)(v33 + 48), &v97);
            j;
            j = RtlStronglyEnumerateEntryHashTable(*(_QWORD *)(v33 + 48), &v97) )
      {
        *(_QWORD *)(Pool2 + 8 * v40) = j;
        v40 = (unsigned int)(v40 + 1);
      }
      RtlEndStrongEnumerationHashTable(*(_QWORD *)(v33 + 48), &v97);
      ExReleaseAutoExpandPushLockShared(v34, 2, v42);
      v6 = (CmsTransactionContext *)a2;
      *(_QWORD *)(v33 + 512) = Pool2;
      *(_DWORD *)(v33 + 520) = v36;
      updated = CmsVolumeContainer::PersistContainerCacheParallel(
                  (CmsVolumeContainer *)v33,
                  (struct CmsTransactionContext *)a2,
                  1u);
      if ( updated >= 0 )
      {
        CmsBPlusTable::OptimizeTree(
          *(CmsBPlusTable **)(*(_QWORD *)(v33 + 16) + 32LL),
          (struct CmsTransactionContext *)a2);
        CmsBPlusTable::OptimizeTree(
          *(CmsBPlusTable **)(*(_QWORD *)(v33 + 16) + 40LL),
          (struct CmsTransactionContext *)a2);
      }
    }
    else
    {
      ExReleaseAutoExpandPushLockShared(v34, 2, v38);
      updated = -1073741670;
    }
    goto LABEL_65;
  }
  return 0;
}

```

## disassembly

```asm
0x140030130  mov     r11, rsp
0x140030133  mov     [r11+18h], r8
0x140030137  mov     [r11+10h], rdx
0x14003013b  push    rbp
0x14003013c  push    rsi
0x14003013d  push    rdi
0x14003013e  push    r13
0x140030140  lea     rbp, [r11-38h]
0x140030144  sub     rsp, 118h
0x14003014b  mov     eax, [r8+420h]
0x140030152  mov     rsi, r9
0x140030155  mov     rdi, rdx
0x140030158  mov     r13, rcx
0x14003015b  test    al, 1
0x14003015d  jz      loc_140030470
0x140030163  mov     rax, [rcx+0CC0h]
0x14003016a  mov     [r11+8], rbx
0x14003016e  mov     [r11-28h], r12
0x140030172  mov     [r11-30h], r14
0x140030176  xor     r14d, r14d
0x140030179  mov     r8, [rax]
0x14003017c  mov     rax, [r8+28h]
0x140030180  mov     [rsp+130h+var_B8], rax
0x140030185  mov     rax, [rcx+0CD0h]
0x14003018c  mov     rax, [rax+8]
0x140030190  test    rax, rax
0x140030193  jz      short loc_1400301A9
0x140030195  mov     rax, [rax]
0x140030198  test    rax, rax
0x14003019b  jz      short loc_1400301A9
0x14003019d  cmp     [rax+48h], r14
0x1400301a1  jz      short loc_1400301A9
0x1400301a3  cmp     [rax+28h], r14
0x1400301a7  jnz     short loc_1400301AC
0x1400301a9  mov     rax, r14
0x1400301ac  mov     rax, [rax+28h]
0x1400301b0  mov     rbx, [r13+0D10h]
0x1400301b7  mov     [rbp+30h+var_A8], rax
0x1400301bb  mov     rax, [rcx+0CE8h]
0x1400301c2  mov     [rsp+130h+var_30], r15
0x1400301ca  mov     rcx, [rax+8]
0x1400301ce  mov     rax, [rcx+28h]
0x1400301d2  mov     [rbp+30h+var_B0], rax
0x1400301d6  mov     rax, [r13+0CC8h]
0x1400301dd  mov     rcx, [rax+10h]
0x1400301e1  mov     rax, [rcx+20h]
0x1400301e5  mov     rax, [rax+28h]
0x1400301e9  mov     [rbp+30h+var_A0], rax
0x1400301ed  mov     rax, [rcx+28h]
0x1400301f1  lea     rcx, ?MoveSmallAllocatorPagesToWillFreeRanges@CmsBPlusTable@@SAXPEAVCmsTransactionContext@@PEAVCmsHashTable@@KKPEAVCmsAllocator@@PEAUSmsWritePlan@@@Z; CmsBPlusTable::MoveSmallAllocatorPagesToWillFreeRanges(CmsTransactionContext *,CmsHashTable *,ulong,ulong,CmsAllocator *,SmsWritePlan *)
0x1400301f8  mov     rax, [rax+28h]
0x1400301fc  mov     [rsp+130h+var_F0], rcx
0x140030201  mov     [rbp+30h+var_98], rax
0x140030205  cmp     [rbx+20h], r14b
0x140030209  jnz     loc_140030D72
0x14003020f  xor     r9d, r9d; unsigned __int8
0x140030212  xor     r8d, r8d; struct _SmsLsn *
0x140030215  xor     edx, edx; unsigned __int8
0x140030217  mov     rcx, rdi; this
0x14003021a  call    ?Commit@CmsTransactionContext@@QEAAJEPEAU_SmsLsn@@E@Z; CmsTransactionContext::Commit(uchar,_SmsLsn *,uchar)
0x14003021f  mov     r8, 0FFFFFFFFFFFFFFFFh
0x140030226  test    rsi, rsi
0x140030229  jz      loc_1400302DA
0x14003022f  test    rsi, rsi
0x140030232  jz      short loc_14003025A
0x140030234  mov     ebx, r14d
0x140030237  cmp     ebx, 8
0x14003023a  jnb     loc_140030474
0x140030240  mov     eax, ebx
0x140030242  lea     rdi, [rax+rax*2]
0x140030246  shl     rdi, 5
0x14003024a  add     rdi, 8
0x14003024e  add     rdi, rsi
0x140030251  cmp     [rdi], r14
0x140030254  jnz     short loc_140030260
0x140030256  inc     ebx
0x140030258  jmp     short loc_140030237
0x14003025a  mov     rdi, r14
0x14003025d  mov     ebx, r8d
0x140030260  test    rdi, rdi
0x140030263  jz      short loc_1400302D6
0x140030265  mov     r12, [rbp+30h+arg_8]
0x140030269  nop     dword ptr [rax+00000000h]
0x140030270  mov     rcx, [rdi]; this
0x140030273  mov     rax, [rcx+48h]
0x140030277  mov     rdx, [rax+180h]
0x14003027e  lea     rax, [rdx-1]
0x140030282  cmp     rax, 3
0x140030286  jbe     loc_1400304C0
0x14003028c  cmp     rdx, 6
0x140030290  jz      loc_1400304C0
0x140030296  lea     eax, [rbx+rbx*2]
0x140030299  shl     eax, 5
0x14003029c  add     eax, 8
0x14003029f  cdqe
0x1400302a1  sub     rdi, rax
0x1400302a4  mov     rdx, rdi
0x1400302a7  test    rdx, rdx
0x1400302aa  jz      short loc_1400302D6
0x1400302ac  inc     ebx
0x1400302ae  xchg    ax, ax
0x1400302b0  cmp     ebx, 8
0x1400302b3  jnb     loc_140030465
0x1400302b9  lea     rdi, [rbx+rbx*2]
0x1400302bd  shl     rdi, 5
0x1400302c1  add     rdi, 8
0x1400302c5  add     rdi, rdx
0x1400302c8  cmp     [rdi], r14
0x1400302cb  jnz     short loc_1400302D1
0x1400302cd  inc     ebx
0x1400302cf  jmp     short loc_1400302B0
0x1400302d1  test    rdi, rdi
0x1400302d4  jnz     short loc_140030270
0x1400302d6  mov     rdi, [rbp+30h+arg_8]
0x1400302da  mov     rcx, [r13+0CC8h]; this
0x1400302e1  cmp     [rcx+119h], r14b
0x1400302e8  jnz     loc_140030DB3
0x1400302ee  cmp     [r13+0D41h], r14b
0x1400302f5  jz      loc_1400303B0
0x1400302fb  test    dword ptr [r13+0D44h], 20000000h
0x140030306  jnz     loc_1400303B0
0x14003030c  mov     rax, [rbp+30h+arg_10]
0x140030310  mov     ecx, [rax+420h]; this
0x140030316  test    cl, 2
0x140030319  jnz     loc_140030D1F
0x14003031f  mov     r14, [rax+8]
0x140030323  mov     r12, [rbp+30h+arg_8]
0x140030327  add     r14, 0C0h
0x14003032e  mov     rsi, r14
0x140030331  mov     rax, [rsi+248h]
0x140030338  lea     rdi, [rsi-0C0h]
0x14003033f  mov     rsi, [rsi]
0x140030342  test    rax, rax
0x140030345  jnz     loc_1401FB613
0x14003034b  cmp     qword ptr [rdi+2F0h], 0
0x140030353  jnz     loc_14003047C
0x140030359  mov     r8, [rdi]
0x14003035c  movzx   edx, byte ptr [r8+0Eh]; struct CmsTransactionContext *
0x140030361  test    dl, 7
0x140030364  jnz     loc_1400304D4
0x14003036a  cmp     qword ptr [rdi+330h], 0
0x140030372  jz      short loc_1400303A4
0x140030374  mov     r9, [rdi+348h]; __int64
0x14003037b  lea     r8, [rdi+310h]; struct CmsContainerRangeMap *
0x140030382  mov     eax, edx
0x140030384  shr     eax, 3
0x140030387  and     eax, 7
0x14003038a  dec     eax
0x14003038c  mov     rcx, [r13+rax*8+0C98h]; this
0x140030394  call    ?MergeIntoProcessedDeleteQueue@CmsAllocator@@QEAAXPEAVCmsTransactionContext@@PEAVCmsContainerRangeMap@@_J@Z; CmsAllocator::MergeIntoProcessedDeleteQueue(CmsTransactionContext *,CmsContainerRangeMap *,__int64)
0x140030399  mov     qword ptr [rdi+348h], 0
0x1400303a4  cmp     rsi, r14
0x1400303a7  jnz     short loc_140030331
0x1400303a9  mov     rdi, [rbp+30h+arg_8]
0x1400303ad  xor     r14d, r14d
0x1400303b0  xor     r9d, r9d; unsigned __int8
0x1400303b3  xor     r8d, r8d; struct _SmsLsn *
0x1400303b6  xor     edx, edx; unsigned __int8
0x1400303b8  mov     rcx, rdi; this
0x1400303bb  call    ?Commit@CmsTransactionContext@@QEAAJEPEAU_SmsLsn@@E@Z; CmsTransactionContext::Commit(uchar,_SmsLsn *,uchar)
0x1400303c0  mov     r10, [r13+0CC0h]
0x1400303c7  cmp     byte ptr [r10+1ECh], 3
0x1400303cf  mov     rax, [r10]
0x1400303d2  mov     rbx, [rax+48h]
0x1400303d6  mov     rax, [rbp+30h+arg_10]
0x1400303da  mov     [rbp+30h+var_80], r10
0x1400303de  mov     [rbp+30h+var_70], r14d
0x1400303e2  mov     rcx, [rax+4C8h]
0x1400303e9  mov     [rbp+30h+var_78], rcx
0x1400303ed  jz      loc_140030DE8
0x1400303f3  lea     r9, [rbp+30h+var_80]; void *
0x1400303f7  mov     rdx, rdi; struct CmsTransactionContext *
0x1400303fa  lea     r8, ?ProcessDeleteQueueEntryParallel@CmsAllocator@@CAJPEAVCmsTransactionCore@@PEAVCmsContainerRangeMap@@PEAU_SmsContainerRangeMapListHead@@PEAU_SmsQuickIndex@@PEAX@Z; int (*)(struct CmsTransactionCore *, struct CmsContainerRangeMap *, struct _SmsContainerRangeMapListHead *, struct _SmsQuickIndex *, void *)
0x140030401  lea     rcx, [rbx+310h]; this
0x140030408  call    ?ParallelForEachBucket@CmsContainerRangeMap@@QEAAJPEAVCmsTransactionContext@@P6AJPEAVCmsTransactionCore@@PEAV1@PEAU_SmsContainerRangeMapListHead@@PEAU_SmsQuickIndex@@PEAX@Z5E@Z; CmsContainerRangeMap::ParallelForEachBucket(CmsTransactionContext *,long (*)(CmsTransactionCore *,CmsContainerRangeMap *,_SmsContainerRangeMapListHead *,_SmsQuickIndex *,void *),void *,uchar)
0x14003040d  mov     r12d, eax
0x140030410  test    eax, eax
0x140030412  jns     loc_140030E19
0x140030418  mov     rax, [r13+0CC8h]
0x14003041f  and     byte ptr [rax+2F8h], 0DFh
0x140030426  nop
0x140030427  lock and dword ptr [r13+0D44h], 0FFFFF7FFh
0x140030433  nop
0x140030434  mov     r15, [rsp+130h+var_30]
0x14003043c  mov     eax, r12d
0x14003043f  mov     r12, [rsp+110h]
0x140030447  mov     r14, [rsp+130h+var_28]
0x14003044f  mov     rbx, [rsp+130h+arg_0]
0x140030457  add     rsp, 118h
0x14003045e  pop     r13
0x140030460  pop     rdi
0x140030461  pop     rsi
0x140030462  pop     rbp
0x140030463  retn
0x140030465  mov     rdx, [rdx]
0x140030468  mov     ebx, r8d
0x14003046b  jmp     loc_1400302A7
0x140030470  xor     eax, eax
0x140030472  jmp     short loc_140030457
0x140030474  mov     rsi, [rsi]
0x140030477  jmp     loc_14003022F
0x14003047c  mov     eax, [r12]
0x140030480  lea     r9, [rdi+310h]; struct CmsContainerRangeMap *
0x140030487  bt      rax, 0Ah
0x14003048c  jb      loc_140030DD3
0x140030492  lea     r8, [rdi+2D0h]; struct CmsContainerRangeMap *
0x140030499  mov     rdx, r12; struct CmsTransactionContext *
0x14003049c  call    ?ProcessDeleteQueue@CmsBlockRefcount@@QEAAJPEAVCmsTransactionContext@@PEAVCmsContainerRangeMap@@1@Z; CmsBlockRefcount::ProcessDeleteQueue(CmsTransactionContext *,CmsContainerRangeMap *,CmsContainerRangeMap *)
0x1400304a1  test    eax, eax
0x1400304a3  jns     loc_1401FB66F
0x1400304a9  mov     rcx, [rdi]
0x1400304ac  mov     r8d, 0Ch
0x1400304b2  mov     rdx, r12
0x1400304b5  call    ?EnqueueTreeUpdate@CmsBPlusTable@@QEAAJPEAVCmsTransactionContext@@W4_EMS_ENQUEUE_FLAGS@@@Z; CmsBPlusTable::EnqueueTreeUpdate(CmsTransactionContext *,_EMS_ENQUEUE_FLAGS)
0x1400304ba  nop
0x1400304bb  jmp     loc_1401FB67D
0x1400304c0  mov     rdx, r12; struct CmsTransactionContext *
0x1400304c3  call    ?OptimizeTree@CmsBPlusTable@@QEAAJPEAVCmsTransactionContext@@@Z; CmsBPlusTable::OptimizeTree(CmsTransactionContext *)
0x1400304c8  mov     r8, 0FFFFFFFFFFFFFFFFh
0x1400304cf  jmp     loc_140030296
0x1400304d4  mov     rcx, [r13+0CD0h]; this
0x1400304db  test    rcx, rcx
0x1400304de  jz      loc_1400303A4
0x1400304e4  call    ?GetIntegrityStateTable@CmsIntegrityState@@QEAAPEAVCmsBPlusTable@@XZ; CmsIntegrityState::GetIntegrityStateTable(void)
0x1400304e9  cmp     r8, rax
0x1400304ec  jnz     loc_1400303A4
0x1400304f2  jmp     loc_14003036A
0x1400304f7  xor     r9d, r9d; unsigned __int8
0x1400304fa  xor     r8d, r8d; struct _SmsLsn *
0x1400304fd  xor     edx, edx; unsigned __int8
0x1400304ff  mov     rcx, rdi; this
0x140030502  call    ?Commit@CmsTransactionContext@@QEAAJEPEAU_SmsLsn@@E@Z; CmsTransactionContext::Commit(uchar,_SmsLsn *,uchar)
0x140030507  mov     rcx, [r13+0CC0h]; this
0x14003050e  mov     rdx, rdi; struct CmsTransactionContext *
0x140030511  call    ?PersistFilteredView@CmsAllocator@@QEAAJPEAVCmsTransactionContext@@@Z; CmsAllocator::PersistFilteredView(CmsTransactionContext *)
0x140030516  mov     r12d, eax
0x140030519  test    eax, eax
0x14003051b  js      loc_140030418
0x140030521  xor     r9d, r9d; unsigned __int8
0x140030524  xor     r8d, r8d; struct _SmsLsn *
0x140030527  xor     edx, edx; unsigned __int8
0x140030529  mov     rcx, rdi; this
0x14003052c  call    ?Commit@CmsTransactionContext@@QEAAJEPEAU_SmsLsn@@E@Z; CmsTransactionContext::Commit(uchar,_SmsLsn *,uchar)
0x140030531  nop
0x140030532  lock or dword ptr [r13+0D44h], 800h
0x14003053e  nop
0x14003053f  mov     r12d, r14d
0x140030542  mov     r15, [r13+0CE8h]
0x140030549  mov     eax, [r15+10h]
0x14003054d  cmp     eax, 2
0x140030550  jz      loc_140030AE2
0x140030556  xor     r9d, r9d; unsigned __int8
0x140030559  xor     r8d, r8d; struct _SmsLsn *
0x14003055c  xor     edx, edx; unsigned __int8
0x14003055e  mov     rcx, rdi; this
0x140030561  call    ?Commit@CmsTransactionContext@@QEAAJEPEAU_SmsLsn@@E@Z; CmsTransactionContext::Commit(uchar,_SmsLsn *,uchar)
0x140030566  mov     rcx, [r13+0CD0h]
0x14003056d  test    rcx, rcx
0x140030570  jnz     loc_1400308CD
0x140030576  mov     rsi, [r13+0CC8h]
0x14003057d  test    byte ptr [rsi+2F8h], 2
0x140030584  jnz     loc_140030928
0x14003058a  or      byte ptr [rsi+2F8h], 20h
0x140030591  lea     rcx, [rsi+38h]
0x140030595  xorps   xmm0, xmm0
0x140030598  mov     byte ptr [rsi+119h], 0
0x14003059f  mov     edx, 2
0x1400305a4  mov     [rbp+30h+var_58], r14
0x1400305a8  movups  [rbp+30h+var_50], xmm0
0x1400305ac  movups  xmmword ptr [rbp-10h], xmm0
0x1400305b0  call    cs:__imp_ExAcquireAutoExpandPushLockShared
0x1400305b7  nop     dword ptr [rax+rax+00h]
0x1400305bc  mov     rbx, rax
0x1400305bf  mov     r8d, 6950534Dh
0x1400305c5  mov     rax, [rsi+30h]
0x1400305c9  mov     r15d, [rax+14h]
0x1400305cd  mov     eax, 8
0x1400305d2  mov     ecx, r15d
0x1400305d5  shl     rcx, 3
0x1400305d9  mul     rcx
0x1400305dc  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1400305e3  cmovb   rax, rcx
0x1400305e7  mov     ecx, 42h ; 'B'
0x1400305ec  mov     rdx, rax
0x1400305ef  call    cs:__imp_ExAllocatePool2
0x1400305f6  nop     dword ptr [rax+rax+00h]
0x1400305fb  mov     r14, rax
0x1400305fe  test    rax, rax
0x140030601  jz      loc_140030C94
0x140030607  mov     rcx, [rsi+30h]
0x14003060b  lea     rdx, [rbp+30h+var_58]
0x14003060f  xor     edi, edi
0x140030611  call    cs:__imp_RtlInitStrongEnumerationHashTable
0x140030618  nop     dword ptr [rax+rax+00h]
0x14003061d  mov     rcx, [rsi+30h]
0x140030621  lea     rdx, [rbp+30h+var_58]
0x140030625  call    cs:__imp_RtlStronglyEnumerateEntryHashTable
0x14003062c  nop     dword ptr [rax+rax+00h]
0x140030631  test    rax, rax
0x140030634  jz      short loc_140030660
  ... truncated ...
```
