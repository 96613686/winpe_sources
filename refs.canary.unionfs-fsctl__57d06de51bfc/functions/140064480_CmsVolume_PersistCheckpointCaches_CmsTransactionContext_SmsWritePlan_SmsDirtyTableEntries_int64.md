# CmsVolume::PersistCheckpointCaches(CmsTransactionContext *,SmsWritePlan *,SmsDirtyTableEntries *,__int64)

- ea: `0x140064480`
- end: `0x1400651fc`
- name: `?PersistCheckpointCaches@CmsVolume@@QEAAJPEAVCmsTransactionContext@@PEAUSmsWritePlan@@PEAUSmsDirtyTableEntries@@_J@Z`
- size: `3452`
- prototype: `__int64 __usercall@<rax>(CmsVolume *__hidden this@<rcx>, struct CmsTransactionContext *@<rdx>, struct SmsWritePlan *@<r8>, struct SmsDirtyTableEntries *@<r9>, __int64)`
- caller_count: `1`
- callee_count: `30`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x14013ff9c`

## callees

- `0x140012b30`
- `0x14001d3d0`
- `0x14001db90`
- `0x14003234c`
- `0x140032b20`
- `0x1400340e0`
- `0x140034ab0`
- `0x140062df0`
- `0x1400635c8`
- `0x1400638a0`
- `0x140064250`
- `0x140064480`
- `0x140065210`
- `0x140065410`
- `0x140065bdc`
- `0x140065c34`
- `0x14006f5c0`
- `0x1400a3840`
- `0x1400ad490`
- `0x1400ade40`
- `0x1400c5f44`
- `0x1400c6748`
- `0x1400c7a44`
- `0x1400c9534`
- `0x1400cd944`
- `0x1400ceb48`
- `0x140129164`
- `0x14013b3dc`
- `0x14013c174`
- `0x14013c634`

## import_xrefs

- `ntoskrnl!KdDebuggerEnabled` at `0x140065096`
- `ntoskrnl!KdDebuggerEnabled` at `0x1400650ac`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140064f94`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140064f94`
- `ntoskrnl!ExAllocatePool2` at `0x14006493f`
- `ntoskrnl!ExAllocatePool2` at `0x14006493f`
- `ntoskrnl!ExAcquireAutoExpandPushLockShared` at `0x140064900`
- `ntoskrnl!ExAcquireAutoExpandPushLockShared` at `0x140064900`
- `ntoskrnl!ExReleaseAutoExpandPushLockShared` at `0x1400649cc`
- `ntoskrnl!ExReleaseAutoExpandPushLockShared` at `0x140064fec`
- `ntoskrnl!ExReleaseAutoExpandPushLockShared` at `0x1400649cc`
- `ntoskrnl!ExReleaseAutoExpandPushLockShared` at `0x140064fec`
- `ntoskrnl!ExAcquireAutoExpandPushLockExclusive` at `0x1401f6078`
- `ntoskrnl!ExAcquireAutoExpandPushLockExclusive` at `0x1401f6078`
- `ntoskrnl!ExReleaseAutoExpandPushLockExclusive` at `0x1401f609f`
- `ntoskrnl!ExReleaseAutoExpandPushLockExclusive` at `0x1401f609f`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x140064e43`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x140064e43`
- `ntoskrnl!RtlInitStrongEnumerationHashTable` at `0x140064961`
- `ntoskrnl!RtlInitStrongEnumerationHashTable` at `0x140064961`
- `ntoskrnl!RtlStronglyEnumerateEntryHashTable` at `0x140064975`
- `ntoskrnl!RtlStronglyEnumerateEntryHashTable` at `0x14006499f`
- `ntoskrnl!RtlStronglyEnumerateEntryHashTable` at `0x140064975`
- `ntoskrnl!RtlStronglyEnumerateEntryHashTable` at `0x14006499f`
- `ntoskrnl!RtlEndStrongEnumerationHashTable` at `0x1400649b8`
- `ntoskrnl!RtlEndStrongEnumerationHashTable` at `0x1400649b8`
- `ntoskrnl!ExReleasePushLockEx` at `0x140064f4d`
- `ntoskrnl!ExReleasePushLockEx` at `0x140064fb7`
- `ntoskrnl!ExReleasePushLockEx` at `0x140064f4d`
- `ntoskrnl!ExReleasePushLockEx` at `0x140064fb7`
- `ntoskrnl!ExFreePoolWithTag` at `0x140064a14`
- `ntoskrnl!ExFreePoolWithTag` at `0x140064a14`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140064ede`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140064ede`

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
  unsigned int v35; // r15d
  unsigned __int64 v36; // rax
  __int64 Pool2; // r14
  __int64 v38; // rdi
  __int64 j; // rax
  void *v40; // rcx
  struct SmsWritePlan *v41; // rdi
  int v42; // ebx
  __int64 v43; // rcx
  int v44; // eax
  __int64 v45; // rbx
  __int64 v46; // rbx
  CmsVolume *v47; // rcx
  __int64 v48; // rdi
  __int64 v49; // rbx
  CmsBPlusTable *v50; // rcx
  unsigned __int8 v51; // r8
  CmsVolume *v52; // rdx
  _QWORD *v53; // rax
  _QWORD *v54; // rcx
  unsigned __int8 v55; // cl
  CmsVolume *v56; // rcx
  union _SLIST_HEADER *v57; // rbx
  PSLIST_ENTRY v58; // rax
  PSLIST_ENTRY v59; // rsi
  struct _SLIST_ENTRY *Next; // r14
  unsigned int v61; // edx
  __int64 v62; // rax
  struct SmsHashEntryLite **v63; // rdi
  struct SmsHashEntryLite *v64; // rbx
  struct SmsHashEntryLite *v65; // rcx
  int v66; // r14d
  struct SmsHashEntryLite *v67; // rax
  __int64 v68; // rdx
  __int64 v69; // r8
  __int64 v70; // r9
  CmsVolume *v71; // rcx
  int v72; // eax
  __int64 GlobalTablesGeneration; // rax
  unsigned __int8 v74; // [rsp+28h] [rbp-E0h]
  void (__usercall *v75)(struct CmsTransactionContext *@<rcx>, struct CmsHashTable *@<rdx>, unsigned int@<r8d>, unsigned int@<r9d>, struct CmsAllocator *, struct SmsWritePlan *); // [rsp+48h] [rbp-C0h] BYREF
  _QWORD v76[3]; // [rsp+50h] [rbp-B8h] BYREF
  __int16 v77; // [rsp+68h] [rbp-A0h]
  char v78; // [rsp+6Ah] [rbp-9Eh]
  unsigned __int8 v79; // [rsp+6Bh] [rbp-9Dh]
  unsigned __int8 v80; // [rsp+6Ch] [rbp-9Ch]
  CmsVolume *v81; // [rsp+70h] [rbp-98h]
  __int64 v82; // [rsp+78h] [rbp-90h]
  __int64 v83; // [rsp+80h] [rbp-88h]
  __int64 v84; // [rsp+88h] [rbp-80h]
  __int64 v85; // [rsp+90h] [rbp-78h]
  __int64 v86; // [rsp+98h] [rbp-70h]
  __int64 v87; // [rsp+A0h] [rbp-68h]
  _QWORD v88[2]; // [rsp+A8h] [rbp-60h] BYREF
  _QWORD v89[2]; // [rsp+B8h] [rbp-50h] BYREF
  int v90; // [rsp+C8h] [rbp-40h]
  int v91; // [rsp+D0h] [rbp-38h]
  unsigned int v92; // [rsp+D4h] [rbp-34h]
  __int64 v93; // [rsp+D8h] [rbp-30h]
  __int64 v94; // [rsp+E0h] [rbp-28h] BYREF
  __int128 v95; // [rsp+E8h] [rbp-20h]
  __int128 v96; // [rsp+F8h] [rbp-10h]
  struct SmsWritePlan *v98; // [rsp+158h] [rbp+50h] BYREF

  v98 = a3;
  v6 = (CmsTransactionContext *)a2;
  if ( (*((_DWORD *)a3 + 264) & 1) != 0 )
  {
    v83 = *(_QWORD *)(**((_QWORD **)this + 416) + 40LL);
    v8 = *(__int64 **)(*((_QWORD *)this + 418) + 8LL);
    if ( !v8 || (v9 = *v8) == 0 || !*(_QWORD *)(v9 + 72) || !*(_QWORD *)(v9 + 40) )
      v9 = 0;
    v10 = *((_QWORD *)this + 426);
    v85 = *(_QWORD *)(v9 + 40);
    v84 = *(_QWORD *)(*(_QWORD *)(*((_QWORD *)this + 421) + 8LL) + 40LL);
    v11 = *(_QWORD *)(*((_QWORD *)this + 417) + 16LL);
    v86 = *(_QWORD *)(*(_QWORD *)(v11 + 32) + 40LL);
    v12 = *(_QWORD *)(*(_QWORD *)(v11 + 40) + 40LL);
    v75 = CmsBPlusTable::MoveSmallAllocatorPagesToWillFreeRanges;
    v87 = v12;
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
        CmsTransactionContext::Abort(v6, v68, v69);
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
    v17 = (CmsVolumeContainer *)*((_QWORD *)this + 417);
    if ( *((_BYTE *)v17 + 281) )
    {
      CmsVolumeContainer::PersistContainerCache(v17, v6, 0);
      CmsTransactionContext::Commit(v6, 0, 0, 0);
    }
    if ( *((_BYTE *)this + 3457) )
    {
      if ( (*((_DWORD *)this + 865) & 0x20000000) == 0 )
      {
        v18 = (CmsBlockRefcount *)*((unsigned int *)v98 + 264);
        if ( ((unsigned __int8)v18 & 2) == 0 || ((unsigned __int8)v18 & 1) != 0 )
        {
          v19 = *((_QWORD *)v98 + 1) + 192LL;
          v20 = (_QWORD *)v19;
          while ( 1 )
          {
            v21 = v20[73];
            v22 = v20 - 24;
            v20 = (_QWORD *)*v20;
            if ( v21 )
            {
              _InterlockedAdd64((volatile signed __int64 *)this + 477, -v21);
              ExAcquireAutoExpandPushLockExclusive((char *)this + 3960, 2);
              CmsVolume::RemoveReservationForGlobalStreamReserve(this, v22[97]);
              ExReleaseAutoExpandPushLockExclusive((char *)this + 3960, 2);
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
              || (v18 = (CmsBlockRefcount *)*((_QWORD *)this + 418)) != 0
              && (IntegrityStateTable = CmsIntegrityState::GetIntegrityStateTable(v18), v30 == IntegrityStateTable) )
            {
              if ( v22[102] )
              {
                CmsAllocator::MergeIntoProcessedDeleteQueue(
                  *((CmsAllocator **)this + (((unsigned int)v23 >> 3) & 7) + 410),
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
    v24 = (CmsAllocator *)*((_QWORD *)this + 416);
    v25 = *((_BYTE *)v24 + 492) == 3;
    v26 = *(_QWORD *)(*(_QWORD *)v24 + 72LL);
    v89[0] = v24;
    v90 = 0;
    v89[1] = *((_QWORD *)v98 + 153);
    if ( v25 )
    {
      v70 = *(_QWORD *)(v26 + 840);
      if ( v70 > 0 )
      {
        CmsAllocator::AdjustAllocatorSummary(v24, 0, 0, -v70, 0);
        *(_QWORD *)(v26 + 840) = 0;
      }
    }
    updated = CmsContainerRangeMap::ParallelForEachBucket(
                (CmsContainerRangeMap *)(v26 + 784),
                v6,
                (int (*)(struct CmsTransactionCore *, struct CmsContainerRangeMap *, struct _SmsContainerRangeMapListHead *, struct _SmsQuickIndex *, void *))CmsAllocator::ProcessDeleteQueueEntryParallel,
                v89,
                v74);
    if ( updated < 0 )
      goto LABEL_42;
    updated = v90;
    if ( v90 < 0 )
      goto LABEL_42;
    CmsTransactionContext::Commit(v6, 0, 0, 0);
    updated = CmsAllocator::PersistFilteredView(*((CmsAllocator **)this + 416), v6);
    if ( updated < 0 )
      goto LABEL_42;
    CmsTransactionContext::Commit(v6, 0, 0, 0);
    _InterlockedOr((volatile signed __int32 *)this + 865, 0x800u);
    updated = 0;
    v31 = *((_QWORD *)this + 421);
    if ( *(_DWORD *)(v31 + 16) == 2 )
    {
LABEL_95:
      v57 = (union _SLIST_HEADER *)(v31 + 80);
      while ( 1 )
      {
        v58 = ExpInterlockedPopEntrySList(v57);
        if ( !v58 )
          break;
        v58->Next = 0;
        v59 = v58 - 2;
        _InterlockedAnd16((volatile signed __int16 *)&v58[1].Next + 1, 0xFFFDu);
        _InterlockedDecrement((volatile signed __int32 *)(v31 + 64));
        if ( (WORD1(v58[1].Next) & 4) != 0 )
          _InterlockedDecrement((volatile signed __int32 *)(v31 + 68));
        if ( (WORD1(v59[3].Next) & 4) != 0 )
        {
          updated = CmsBlockRefcount::PersistCacheEntry(
                      (CmsBlockRefcount *)v31,
                      v6,
                      (struct CmsRefcountCacheEntry *)v59);
          if ( updated < 0 )
          {
            if ( CmsRefcountCacheEntry::AddForProcessing((CmsRefcountCacheEntry *)v59, v57) )
              _InterlockedIncrement((volatile signed __int32 *)(v31 + 64));
            if ( (WORD1(v59[3].Next) & 4) != 0 )
              _InterlockedIncrement((volatile signed __int32 *)(v31 + 68));
            CmsRefcountCacheEntry::Release(v59);
            break;
          }
        }
        else if ( (WORD1(v59[3].Next) & 8) != 0 )
        {
          v93 = 0;
          Next = v59[1].Next;
          v91 = 0;
          v61 = ((69069 * (_DWORD)Next + 1) & 0xFFFF0000
               | (unsigned __int64)((unsigned int)(1103515245 * (_DWORD)Next + 12345) >> 16))
              % *(unsigned int *)(v31 + 40);
          v62 = *(_QWORD *)(v31 + 32);
          v92 = v61;
          v63 = (struct SmsHashEntryLite **)(v62 + 24LL * v61);
          ExAcquirePushLockExclusiveEx(v63 + 2, 0);
          if ( v63[1] )
          {
            v64 = *v63;
            while ( *((struct _SLIST_ENTRY **)v64 + 2) != Next )
            {
              v64 = *(struct SmsHashEntryLite **)v64;
              if ( v64 == *v63 )
                goto LABEL_117;
            }
            if ( v64 )
            {
              if ( CmsRefcountCacheEntry::CanBeDeleted(v64) )
              {
                v65 = (struct SmsHashEntryLite *)*((_QWORD *)v64 + 1);
                v66 = 0;
                v67 = *(struct SmsHashEntryLite **)v64;
                *(_QWORD *)v65 = *(_QWORD *)v64;
                *((_QWORD *)v67 + 1) = v65;
                if ( *v63 == v64 )
                  *v63 = v67;
                if ( v65 == v64 )
                  *v63 = 0;
                v63[1] = (struct SmsHashEntryLite *)((char *)v63[1] - 1);
                _InterlockedDecrement((volatile signed __int32 *)(v31 + 44));
              }
              else
              {
                v66 = -1073741772;
              }
              ExReleasePushLockEx(v63 + 2, 0);
              if ( v66 >= 0 )
              {
                _InterlockedAnd16((volatile signed __int16 *)&v59[3].Next + 1, 0xFFF7u);
                CmsRefcountCacheEntry::Release(v59);
              }
            }
          }
          else
          {
LABEL_117:
            ExReleasePushLockEx(v63 + 2, 0);
          }
          v6 = (CmsTransactionContext *)a2;
        }
        v57 = (union _SLIST_HEADER *)(v31 + 80);
        if ( _InterlockedExchangeAdd16((volatile signed __int16 *)&v59[3], 0xFFFFu) == 1 )
        {
          CmsRefcountCacheEntry::~CmsRefcountCacheEntry((CmsRefcountCacheEntry *)v59);
          ExFreeToNPagedLookasideList(&CmsRefcountCacheEntry::EntriesLookasideList, v59);
          goto LABEL_95;
        }
      }
      if ( v6 )
        CmsBPlusTable::OptimizeTree(*(CmsBPlusTable **)(v31 + 8), v6);
      if ( updated < 0 )
        goto LABEL_42;
    }
    CmsTransactionContext::Commit(v6, 0, 0, 0);
    v32 = *((_QWORD *)this + 418);
    if ( v32 && *(_BYTE *)(v32 + 16) )
    {
      updated = CmsAllocator::PersistFilteredView(*(CmsAllocator **)(v32 + 8), v6);
      if ( updated < 0 )
        goto LABEL_42;
      CmsTransactionContext::Commit(v6, 0, 0, 0);
    }
    v33 = *((_QWORD *)this + 417);
    if ( (*(_BYTE *)(v33 + 768) & 2) != 0 )
    {
      v48 = *(_QWORD *)(v33 + 16);
      v49 = 0;
      v77 = 0;
      v78 = 0;
      LODWORD(v82) = 0;
      do
      {
        v50 = *(CmsBPlusTable **)(v48 + 8 * v49 + 32);
        if ( v50 && !CmsBPlusTable::EnterTree(v50, (struct CmsTransactionContext *)a2) )
          break;
        v49 = (unsigned int)(v49 + 1);
      }
      while ( (unsigned int)v49 < 2 );
      if ( (*(_DWORD *)a2 & 0x200000) != 0 && (_BYTE)KdDebuggerEnabled )
        __debugbreak();
      v51 = *((_BYTE *)a2 + 131);
      v52 = *a2;
      LODWORD(v82) = (unsigned __int16)++*((_WORD *)a2 + 106);
      v76[0] = a2[18];
      v53 = (_QWORD *)((char *)a2[52] + 8);
      v78 = 0;
      v54 = (_QWORD *)*v53;
      v25 = *v53 == 0;
      v81 = v52;
      v79 = v51;
      if ( v25 )
        v54 = v53;
      HIBYTE(v77) = 0;
      v76[2] = a2[25];
      v76[1] = v54;
      v55 = *((_BYTE *)a2 + 132);
      *a2 = (CmsVolume *)((unsigned __int64)v52 & 0xFFFFEFFFFFFFFFFFuLL);
      v80 = v55;
      while ( 1 )
      {
        if ( v51 >= 0xDu )
          goto LABEL_88;
        if ( !a2[v51 + 70] )
          break;
        ++v51;
      }
      *((_BYTE *)a2 + 131) = v51;
LABEL_88:
      while ( v55 < 0xDu )
      {
        if ( !a2[v55 + 53] )
        {
          *((_BYTE *)a2 + 132) = v55;
          break;
        }
        ++v55;
      }
      if ( *((_BYTE *)a2 + 131) < *((_BYTE *)a2 + 130) && (_BYTE)KdDebuggerEnabled )
        __debugbreak();
      *((_BYTE *)a2 + 130) = *((_BYTE *)a2 + 131);
      v88[0] = v33 + 80;
      v88[1] = 200;
      updated = CmsFailoverBPlusTable::InvokeTableMethodInternal(
                  v48,
                  CmsFailoverBPlusTable::EmsPerformOnBoth,
                  a2,
                  CmsFailoverBPlusTable::InvokeTableMethod__CmsFailoverBPlusTable::UpdateDataWithRoot_::_2_::_lambda_1____::_2_::_lambda_1_::_lambda_invoker_cdecl_,
                  v88,
                  0,
                  0);
      v6 = (CmsTransactionContext *)a2;
      v56 = a2[1];
      if ( updated < 0 )
      {
        CmsVolume::AbortTopLevelAction(v56, (struct CmsTransactionContext *)a2, (struct _SmsTopLevelAction *)v76);
LABEL_65:
        v40 = *(void **)(v33 + 520);
        if ( v40 )
          ExFreePoolWithTag(v40, 0);
        *(_QWORD *)(v33 + 520) = 0;
        *(_DWORD *)(v33 + 528) = 0;
        if ( updated < 0 )
          goto LABEL_42;
        CmsTransactionContext::Commit(v6, 0, 0, 0);
        *(_BYTE *)(*((_QWORD *)this + 417) + 768LL) |= 0x20u;
        v41 = v98;
        if ( (*((_DWORD *)v98 + 264) & 1) != 0 )
        {
          v42 = 0;
          v43 = *((_QWORD *)v98 + 1) + 192LL;
          do
          {
            v42 += *(_DWORD *)(v43 + 180);
            v43 = *(_QWORD *)v43;
          }
          while ( v43 != *((_QWORD *)v98 + 1) + 192LL );
          v44 = *((_DWORD *)v98 + 262);
          if ( v42 > v44 )
          {
            updated = CmsLookasides::SatisfyReservation(20, (unsigned int)(v42 - v44));
            if ( updated < 0 )
              goto LABEL_42;
            updated = CmsLookasides::SatisfyReservation(21, (unsigned int)(v42 - *((_DWORD *)v41 + 263)));
            if ( updated < 0 )
            {
              _InterlockedAdd((volatile signed __int32 *)(qword_1402624A0 + 92), *((_DWORD *)v41 + 262) - v42);
              goto LABEL_42;
            }
            *((_DWORD *)v41 + 262) = v42;
            *((_DWORD *)v41 + 263) = v42;
          }
        }
        CmsBPlusTable::ParallelTuPageTableWork<void (*&)(CmsTransactionContext *,CmsHashTable *,unsigned long,unsigned long,CmsAllocator *,SmsWritePlan *),CmsAllocator * &,SmsWritePlan * &>(
          (__int64)a2,
          v83 + 16,
          (__int64)&v75,
          (__int64)this + 3320,
          (__int64)&v98);
        CmsBPlusTable::ParallelTuPageTableWork<void (*&)(CmsTransactionContext *,CmsHashTable *,unsigned long,unsigned long,CmsAllocator *,SmsWritePlan *),CmsAllocator * &,SmsWritePlan * &>(
          (__int64)a2,
          v84 + 16,
          (__int64)&v75,
          (__int64)this + 3320,
          (__int64)&v98);
        CmsBPlusTable::ParallelTuPageTableWork<void (*&)(CmsTransactionContext *,CmsHashTable *,unsigned long,unsigned long,CmsAllocator *,SmsWritePlan *),CmsAllocator * &,SmsWritePlan * &>(
          (__int64)a2,
          v85 + 16,
          (__int64)&v75,
          (__int64)this + 3320,
          (__int64)&v98);
        CmsBPlusTable::ParallelTuPageTableWork<void (*&)(CmsTransactionContext *,CmsHashTable *,unsigned long,unsigned long,CmsAllocator *,SmsWritePlan *),CmsAllocator * &,SmsWritePlan * &>(
          (__int64)a2,
          v86 + 16,
          (__int64)&v75,
          (__int64)this + 3312,
          (__int64)&v98);
        CmsBPlusTable::ParallelTuPageTableWork<void (*&)(CmsTransactionContext *,CmsHashTable *,unsigned long,unsigned long,CmsAllocator *,SmsWritePlan *),CmsAllocator * &,SmsWritePlan * &>(
          (__int64)a2,
          v87 + 16,
          (__int64)&v75,
          (__int64)this + 3312,
          (__int64)&v98);
        v45 = *((_QWORD *)this + 415);
        CmsContainerRangeMap::Merge(
          (CmsContainerRangeMap *)(*(_QWORD *)(*(_QWORD *)v45 + 72LL) + 784LL),
          *((struct CmsContainerRangeMap **)v98 + 155));
        *(_QWORD *)(*(_QWORD *)(*(_QWORD *)v45 + 72LL) + 840LL) = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)v45 + 72LL) + 840LL);
        v46 = *((_QWORD *)this + 414);
        CmsContainerRangeMap::Merge(
          (CmsContainerRangeMap *)(*(_QWORD *)(*(_QWORD *)v46 + 72LL) + 784LL),
          *((struct CmsContainerRangeMap **)v98 + 156));
        v47 = *(CmsVolume **)(*(_QWORD *)v46 + 72LL);
        *((_QWORD *)v47 + 105) = *((_QWORD *)v47 + 105);
        *((_QWORD *)v98 + 159) = 0;
        *((_QWORD *)v98 + 158) = 0;
        updated = CmsVolume::PersistSmallAllocator(
                    v47,
                    (struct CmsTransactionContext *)a2,
                    *((struct CmsAllocator **)this + 415),
                    v98,
                    *((struct SmsCheckpointContext **)v98 + 153));
        if ( updated >= 0 )
        {
          CmsTransactionContext::Commit((CmsTransactionContext *)a2, 0, 0, 0);
          v72 = CmsVolume::PersistSmallAllocator(
                  v71,
                  (struct CmsTransactionContext *)a2,
                  *((struct CmsAllocator **)this + 414),
                  v98,
                  *((struct SmsCheckpointContext **)v98 + 153));
          updated = v72;
          if ( v72 >= 0 )
          {
            CmsTransactionContext::Commit((CmsTransactionContext *)a2, 0, 0, 0);
            GlobalTablesGeneration = CmsVolume::GetGlobalTablesGeneration(this);
            if ( a5 == GlobalTablesGeneration )
              return (unsigned int)updated;
            updated = -1073741823;
          }
        }
LABEL_42:
        *(_BYTE *)(*((_QWORD *)this + 417) + 768LL) &= ~0x20u;
        _InterlockedAnd((volatile signed __int32 *)this + 865, 0xFFFFF7FF);
        return (unsigned int)updated;
      }
      CmsVolume::FoldTopLevelAction(v56, (struct CmsTransactionContext *)a2, (struct _SmsTopLevelAction *)v76);
      *(_BYTE *)(v33 + 768) &= ~2u;
      CmsTransactionContext::Commit((CmsTransactionContext *)a2, 0, 0, 0);
    }
    *(_BYTE *)(v33 + 768) |= 0x20u;
    *(_BYTE *)(v33 + 281) = 0;
    v94 = 0;
    v95 = 0;
    v96 = 0;
    v34 = ExAcquireAutoExpandPushLockShared(v33 + 56, 2);
    v35 = *(_DWORD *)(*(_QWORD *)(v33 + 48) + 20LL);
    v36 = (unsigned __int64)v35 << 6;
    if ( !is_mul_ok(8LL * v35, 8u) )
      v36 = -1;
    Pool2 = ExAllocatePool2(66, v36, 1766871885);
    if ( Pool2 )
    {
      v38 = 0;
      RtlInitStrongEnumerationHashTable(*(_QWORD *)(v33 + 48), &v94);
      for ( j = RtlStronglyEnumerateEntryHashTable(*(_QWORD *)(v33 + 48), &v94);
            j;
            j = RtlStronglyEnumerateEntryHashTable(*(_QWORD *)(v33 + 48), &v94) )
      {
        *(_QWORD *)(Pool2 + 8 * v38) = j;
        v38 = (unsigned int)(v38 + 1);
      }
      RtlEndStrongEnumerationHashTable(*(_QWORD *)(v33 + 48), &v94);
      ExReleaseAutoExpandPushLockShared(v34, 2);
      v6 = (CmsTransactionContext *)a2;
      *(_QWORD *)(v33 + 520) = Pool2;
      *(_DWORD *)(v33 + 528) = v35;
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
      ExReleaseAutoExpandPushLockShared(v34, 2);
      updated = -1073741670;
    }
    goto LABEL_65;
  }
  return 0;
}

```

## disassembly

```asm
0x140064480  mov     r11, rsp
0x140064483  mov     [r11+18h], r8
0x140064487  mov     [r11+10h], rdx
0x14006448b  push    rbp
0x14006448c  push    rsi
0x14006448d  push    rdi
0x14006448e  push    r13
0x140064490  lea     rbp, [r11-38h]
0x140064494  sub     rsp, 118h
0x14006449b  mov     eax, [r8+420h]
0x1400644a2  mov     rsi, r9
0x1400644a5  mov     rdi, rdx
0x1400644a8  mov     r13, rcx
0x1400644ab  test    al, 1
0x1400644ad  jz      loc_1400647C0
0x1400644b3  mov     rax, [rcx+0D00h]
0x1400644ba  mov     [r11+8], rbx
0x1400644be  mov     [r11-28h], r12
0x1400644c2  mov     [r11-30h], r14
0x1400644c6  xor     r14d, r14d
0x1400644c9  mov     r8, [rax]
0x1400644cc  mov     rax, [r8+28h]
0x1400644d0  mov     [rsp+130h+var_B8], rax
0x1400644d5  mov     rax, [rcx+0D10h]
0x1400644dc  mov     rax, [rax+8]
0x1400644e0  test    rax, rax
0x1400644e3  jz      short loc_1400644F9
0x1400644e5  mov     rax, [rax]
0x1400644e8  test    rax, rax
0x1400644eb  jz      short loc_1400644F9
0x1400644ed  cmp     [rax+48h], r14
0x1400644f1  jz      short loc_1400644F9
0x1400644f3  cmp     [rax+28h], r14
0x1400644f7  jnz     short loc_1400644FC
0x1400644f9  mov     rax, r14
0x1400644fc  mov     rax, [rax+28h]
0x140064500  mov     rbx, [r13+0D50h]
0x140064507  mov     [rbp+30h+var_A8], rax
0x14006450b  mov     rax, [rcx+0D28h]
0x140064512  mov     [rsp+130h+var_30], r15
0x14006451a  mov     rcx, [rax+8]
0x14006451e  mov     rax, [rcx+28h]
0x140064522  mov     [rbp+30h+var_B0], rax
0x140064526  mov     rax, [r13+0D08h]
0x14006452d  mov     rcx, [rax+10h]
0x140064531  mov     rax, [rcx+20h]
0x140064535  mov     rax, [rax+28h]
0x140064539  mov     [rbp+30h+var_A0], rax
0x14006453d  mov     rax, [rcx+28h]
0x140064541  lea     rcx, ?MoveSmallAllocatorPagesToWillFreeRanges@CmsBPlusTable@@SAXPEAVCmsTransactionContext@@PEAVCmsHashTable@@KKPEAVCmsAllocator@@PEAUSmsWritePlan@@@Z; CmsBPlusTable::MoveSmallAllocatorPagesToWillFreeRanges(CmsTransactionContext *,CmsHashTable *,ulong,ulong,CmsAllocator *,SmsWritePlan *)
0x140064548  mov     rax, [rax+28h]
0x14006454c  mov     [rsp+130h+var_F0], rcx
0x140064551  mov     [rbp+30h+var_98], rax
0x140064555  cmp     [rbx+20h], r14b
0x140064559  jnz     loc_1400650C2
0x14006455f  xor     r9d, r9d; unsigned __int8
0x140064562  xor     r8d, r8d; struct _SmsLsn *
0x140064565  xor     edx, edx; unsigned __int8
0x140064567  mov     rcx, rdi; this
0x14006456a  call    ?Commit@CmsTransactionContext@@QEAAJEPEAU_SmsLsn@@E@Z; CmsTransactionContext::Commit(uchar,_SmsLsn *,uchar)
0x14006456f  mov     r8, 0FFFFFFFFFFFFFFFFh
0x140064576  test    rsi, rsi
0x140064579  jz      loc_14006462A
0x14006457f  test    rsi, rsi
0x140064582  jz      short loc_1400645AA
0x140064584  mov     ebx, r14d
0x140064587  cmp     ebx, 8
0x14006458a  jnb     loc_1400647C4
0x140064590  mov     eax, ebx
0x140064592  lea     rdi, [rax+rax*2]
0x140064596  shl     rdi, 5
0x14006459a  add     rdi, 8
0x14006459e  add     rdi, rsi
0x1400645a1  cmp     [rdi], r14
0x1400645a4  jnz     short loc_1400645B0
0x1400645a6  inc     ebx
0x1400645a8  jmp     short loc_140064587
0x1400645aa  mov     rdi, r14
0x1400645ad  mov     ebx, r8d
0x1400645b0  test    rdi, rdi
0x1400645b3  jz      short loc_140064626
0x1400645b5  mov     r12, [rbp+30h+arg_8]
0x1400645b9  nop     dword ptr [rax+00000000h]
0x1400645c0  mov     rcx, [rdi]; this
0x1400645c3  mov     rax, [rcx+48h]
0x1400645c7  mov     rdx, [rax+180h]
0x1400645ce  lea     rax, [rdx-1]
0x1400645d2  cmp     rax, 3
0x1400645d6  jbe     loc_140064810
0x1400645dc  cmp     rdx, 6
0x1400645e0  jz      loc_140064810
0x1400645e6  lea     eax, [rbx+rbx*2]
0x1400645e9  shl     eax, 5
0x1400645ec  add     eax, 8
0x1400645ef  cdqe
0x1400645f1  sub     rdi, rax
0x1400645f4  mov     rdx, rdi
0x1400645f7  test    rdx, rdx
0x1400645fa  jz      short loc_140064626
0x1400645fc  inc     ebx
0x1400645fe  xchg    ax, ax
0x140064600  cmp     ebx, 8
0x140064603  jnb     loc_1400647B5
0x140064609  lea     rdi, [rbx+rbx*2]
0x14006460d  shl     rdi, 5
0x140064611  add     rdi, 8
0x140064615  add     rdi, rdx
0x140064618  cmp     [rdi], r14
0x14006461b  jnz     short loc_140064621
0x14006461d  inc     ebx
0x14006461f  jmp     short loc_140064600
0x140064621  test    rdi, rdi
0x140064624  jnz     short loc_1400645C0
0x140064626  mov     rdi, [rbp+30h+arg_8]
0x14006462a  mov     rcx, [r13+0D08h]; this
0x140064631  cmp     [rcx+119h], r14b
0x140064638  jnz     loc_140065103
0x14006463e  cmp     [r13+0D81h], r14b
0x140064645  jz      loc_140064700
0x14006464b  test    dword ptr [r13+0D84h], 20000000h
0x140064656  jnz     loc_140064700
0x14006465c  mov     rax, [rbp+30h+arg_10]
0x140064660  mov     ecx, [rax+420h]; this
0x140064666  test    cl, 2
0x140064669  jnz     loc_14006506F
0x14006466f  mov     r14, [rax+8]
0x140064673  mov     r12, [rbp+30h+arg_8]
0x140064677  add     r14, 0C0h
0x14006467e  mov     rsi, r14
0x140064681  mov     rax, [rsi+248h]
0x140064688  lea     rdi, [rsi-0C0h]
0x14006468f  mov     rsi, [rsi]
0x140064692  test    rax, rax
0x140064695  jnz     loc_1401F605F
0x14006469b  cmp     qword ptr [rdi+2F0h], 0
0x1400646a3  jnz     loc_1400647CC
0x1400646a9  mov     r8, [rdi]
0x1400646ac  movzx   edx, byte ptr [r8+0Eh]; struct CmsTransactionContext *
0x1400646b1  test    dl, 7
0x1400646b4  jnz     loc_140064824
0x1400646ba  cmp     qword ptr [rdi+330h], 0
0x1400646c2  jz      short loc_1400646F4
0x1400646c4  mov     r9, [rdi+348h]; __int64
0x1400646cb  lea     r8, [rdi+310h]; struct CmsContainerRangeMap *
0x1400646d2  mov     eax, edx
0x1400646d4  shr     eax, 3
0x1400646d7  and     eax, 7
0x1400646da  dec     eax
0x1400646dc  mov     rcx, [r13+rax*8+0CD8h]; this
0x1400646e4  call    ?MergeIntoProcessedDeleteQueue@CmsAllocator@@QEAAXPEAVCmsTransactionContext@@PEAVCmsContainerRangeMap@@_J@Z; CmsAllocator::MergeIntoProcessedDeleteQueue(CmsTransactionContext *,CmsContainerRangeMap *,__int64)
0x1400646e9  mov     qword ptr [rdi+348h], 0
0x1400646f4  cmp     rsi, r14
0x1400646f7  jnz     short loc_140064681
0x1400646f9  mov     rdi, [rbp+30h+arg_8]
0x1400646fd  xor     r14d, r14d
0x140064700  xor     r9d, r9d; unsigned __int8
0x140064703  xor     r8d, r8d; struct _SmsLsn *
0x140064706  xor     edx, edx; unsigned __int8
0x140064708  mov     rcx, rdi; this
0x14006470b  call    ?Commit@CmsTransactionContext@@QEAAJEPEAU_SmsLsn@@E@Z; CmsTransactionContext::Commit(uchar,_SmsLsn *,uchar)
0x140064710  mov     r10, [r13+0D00h]
0x140064717  cmp     byte ptr [r10+1ECh], 3
0x14006471f  mov     rax, [r10]
0x140064722  mov     rbx, [rax+48h]
0x140064726  mov     rax, [rbp+30h+arg_10]
0x14006472a  mov     [rbp+30h+var_80], r10
0x14006472e  mov     [rbp+30h+var_70], r14d
0x140064732  mov     rcx, [rax+4C8h]
0x140064739  mov     [rbp+30h+var_78], rcx
0x14006473d  jz      loc_140065138
0x140064743  lea     r9, [rbp+30h+var_80]; void *
0x140064747  mov     rdx, rdi; struct CmsTransactionContext *
0x14006474a  lea     r8, ?ProcessDeleteQueueEntryParallel@CmsAllocator@@CAJPEAVCmsTransactionCore@@PEAVCmsContainerRangeMap@@PEAU_SmsContainerRangeMapListHead@@PEAU_SmsQuickIndex@@PEAX@Z; int (*)(struct CmsTransactionCore *, struct CmsContainerRangeMap *, struct _SmsContainerRangeMapListHead *, struct _SmsQuickIndex *, void *)
0x140064751  lea     rcx, [rbx+310h]; this
0x140064758  call    ?ParallelForEachBucket@CmsContainerRangeMap@@QEAAJPEAVCmsTransactionContext@@P6AJPEAVCmsTransactionCore@@PEAV1@PEAU_SmsContainerRangeMapListHead@@PEAU_SmsQuickIndex@@PEAX@Z5E@Z; CmsContainerRangeMap::ParallelForEachBucket(CmsTransactionContext *,long (*)(CmsTransactionCore *,CmsContainerRangeMap *,_SmsContainerRangeMapListHead *,_SmsQuickIndex *,void *),void *,uchar)
0x14006475d  mov     r12d, eax
0x140064760  test    eax, eax
0x140064762  jns     loc_140065169
0x140064768  mov     rax, [r13+0D08h]
0x14006476f  and     byte ptr [rax+300h], 0DFh
0x140064776  nop
0x140064777  lock and dword ptr [r13+0D84h], 0FFFFF7FFh
0x140064783  nop
0x140064784  mov     r15, [rsp+130h+var_30]
0x14006478c  mov     eax, r12d
0x14006478f  mov     r12, [rsp+110h]
0x140064797  mov     r14, [rsp+130h+var_28]
0x14006479f  mov     rbx, [rsp+130h+arg_0]
0x1400647a7  add     rsp, 118h
0x1400647ae  pop     r13
0x1400647b0  pop     rdi
0x1400647b1  pop     rsi
0x1400647b2  pop     rbp
0x1400647b3  retn
0x1400647b5  mov     rdx, [rdx]
0x1400647b8  mov     ebx, r8d
0x1400647bb  jmp     loc_1400645F7
0x1400647c0  xor     eax, eax
0x1400647c2  jmp     short loc_1400647A7
0x1400647c4  mov     rsi, [rsi]
0x1400647c7  jmp     loc_14006457F
0x1400647cc  mov     eax, [r12]
0x1400647d0  lea     r9, [rdi+310h]; struct CmsContainerRangeMap *
0x1400647d7  bt      rax, 0Ah
0x1400647dc  jb      loc_140065123
0x1400647e2  lea     r8, [rdi+2D0h]; struct CmsContainerRangeMap *
0x1400647e9  mov     rdx, r12; struct CmsTransactionContext *
0x1400647ec  call    ?ProcessDeleteQueue@CmsBlockRefcount@@QEAAJPEAVCmsTransactionContext@@PEAVCmsContainerRangeMap@@1@Z; CmsBlockRefcount::ProcessDeleteQueue(CmsTransactionContext *,CmsContainerRangeMap *,CmsContainerRangeMap *)
0x1400647f1  test    eax, eax
0x1400647f3  jns     loc_1401F60BB
0x1400647f9  mov     rcx, [rdi]
0x1400647fc  mov     r8d, 0Ch
0x140064802  mov     rdx, r12
0x140064805  call    ?EnqueueTreeUpdate@CmsBPlusTable@@QEAAJPEAVCmsTransactionContext@@W4_EMS_ENQUEUE_FLAGS@@@Z; CmsBPlusTable::EnqueueTreeUpdate(CmsTransactionContext *,_EMS_ENQUEUE_FLAGS)
0x14006480a  nop
0x14006480b  jmp     loc_1401F60C9
0x140064810  mov     rdx, r12; struct CmsTransactionContext *
0x140064813  call    ?OptimizeTree@CmsBPlusTable@@QEAAJPEAVCmsTransactionContext@@@Z; CmsBPlusTable::OptimizeTree(CmsTransactionContext *)
0x140064818  mov     r8, 0FFFFFFFFFFFFFFFFh
0x14006481f  jmp     loc_1400645E6
0x140064824  mov     rcx, [r13+0D10h]; this
0x14006482b  test    rcx, rcx
0x14006482e  jz      loc_1400646F4
0x140064834  call    ?GetIntegrityStateTable@CmsIntegrityState@@QEAAPEAVCmsBPlusTable@@XZ; CmsIntegrityState::GetIntegrityStateTable(void)
0x140064839  cmp     r8, rax
0x14006483c  jnz     loc_1400646F4
0x140064842  jmp     loc_1400646BA
0x140064847  xor     r9d, r9d; unsigned __int8
0x14006484a  xor     r8d, r8d; struct _SmsLsn *
0x14006484d  xor     edx, edx; unsigned __int8
0x14006484f  mov     rcx, rdi; this
0x140064852  call    ?Commit@CmsTransactionContext@@QEAAJEPEAU_SmsLsn@@E@Z; CmsTransactionContext::Commit(uchar,_SmsLsn *,uchar)
0x140064857  mov     rcx, [r13+0D00h]; this
0x14006485e  mov     rdx, rdi; struct CmsTransactionContext *
0x140064861  call    ?PersistFilteredView@CmsAllocator@@QEAAJPEAVCmsTransactionContext@@@Z; CmsAllocator::PersistFilteredView(CmsTransactionContext *)
0x140064866  mov     r12d, eax
0x140064869  test    eax, eax
0x14006486b  js      loc_140064768
0x140064871  xor     r9d, r9d; unsigned __int8
0x140064874  xor     r8d, r8d; struct _SmsLsn *
0x140064877  xor     edx, edx; unsigned __int8
0x140064879  mov     rcx, rdi; this
0x14006487c  call    ?Commit@CmsTransactionContext@@QEAAJEPEAU_SmsLsn@@E@Z; CmsTransactionContext::Commit(uchar,_SmsLsn *,uchar)
0x140064881  nop
0x140064882  lock or dword ptr [r13+0D84h], 800h
0x14006488e  nop
0x14006488f  mov     r12d, r14d
0x140064892  mov     r15, [r13+0D28h]
0x140064899  mov     eax, [r15+10h]
0x14006489d  cmp     eax, 2
0x1400648a0  jz      loc_140064E32
0x1400648a6  xor     r9d, r9d; unsigned __int8
0x1400648a9  xor     r8d, r8d; struct _SmsLsn *
0x1400648ac  xor     edx, edx; unsigned __int8
0x1400648ae  mov     rcx, rdi; this
0x1400648b1  call    ?Commit@CmsTransactionContext@@QEAAJEPEAU_SmsLsn@@E@Z; CmsTransactionContext::Commit(uchar,_SmsLsn *,uchar)
0x1400648b6  mov     rcx, [r13+0D10h]
0x1400648bd  test    rcx, rcx
0x1400648c0  jnz     loc_140064C1D
0x1400648c6  mov     rsi, [r13+0D08h]
0x1400648cd  test    byte ptr [rsi+300h], 2
0x1400648d4  jnz     loc_140064C78
0x1400648da  or      byte ptr [rsi+300h], 20h
0x1400648e1  lea     rcx, [rsi+38h]
0x1400648e5  xorps   xmm0, xmm0
0x1400648e8  mov     byte ptr [rsi+119h], 0
0x1400648ef  mov     edx, 2
0x1400648f4  mov     [rbp+30h+var_58], r14
0x1400648f8  movups  [rbp+30h+var_50], xmm0
0x1400648fc  movups  xmmword ptr [rbp-10h], xmm0
0x140064900  call    cs:__imp_ExAcquireAutoExpandPushLockShared
0x140064907  nop     dword ptr [rax+rax+00h]
0x14006490c  mov     rbx, rax
0x14006490f  mov     r8d, 6950534Dh
0x140064915  mov     rax, [rsi+30h]
0x140064919  mov     r15d, [rax+14h]
0x14006491d  mov     eax, 8
0x140064922  mov     ecx, r15d
0x140064925  shl     rcx, 3
0x140064929  mul     rcx
0x14006492c  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x140064933  cmovb   rax, rcx
0x140064937  mov     ecx, 42h ; 'B'
0x14006493c  mov     rdx, rax
0x14006493f  call    cs:__imp_ExAllocatePool2
0x140064946  nop     dword ptr [rax+rax+00h]
0x14006494b  mov     r14, rax
0x14006494e  test    rax, rax
0x140064951  jz      loc_140064FE4
0x140064957  mov     rcx, [rsi+30h]
0x14006495b  lea     rdx, [rbp+30h+var_58]
0x14006495f  xor     edi, edi
0x140064961  call    cs:__imp_RtlInitStrongEnumerationHashTable
0x140064968  nop     dword ptr [rax+rax+00h]
0x14006496d  mov     rcx, [rsi+30h]
0x140064971  lea     rdx, [rbp+30h+var_58]
0x140064975  call    cs:__imp_RtlStronglyEnumerateEntryHashTable
0x14006497c  nop     dword ptr [rax+rax+00h]
0x140064981  test    rax, rax
0x140064984  jz      short loc_1400649B0
  ... truncated ...
```
