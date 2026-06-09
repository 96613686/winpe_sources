# NtfsDeleteScb

- ea: `0x140129500`
- end: `0x140129fa1`
- name: `NtfsDeleteScb`
- size: `2721`
- prototype: ``
- caller_count: `7`
- callee_count: `12`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x1400cf580`
- `0x1400e9d70`
- `0x1401289c0`
- `0x140128d50`
- `0x14012a0f0`
- `0x140194c68`
- `0x1401ff460`

## callees

- `0x14000ea70`
- `0x1400132a8`
- `0x140025c10`
- `0x140027f70`
- `0x140028680`
- `0x14004a43c`
- `0x140129500`
- `0x140129fb0`
- `0x14012bb80`
- `0x140140ab0`
- `0x1401db164`
- `0x1401e3230`

## import_xrefs

- `ntoskrnl!MmBadPointer` at `0x140129543`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140129917`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140129917`
- `ntoskrnl!FsRtlUninitializeLargeMcb` at `0x140129dec`
- `ntoskrnl!FsRtlUninitializeLargeMcb` at `0x140129e02`
- `ntoskrnl!FsRtlUninitializeLargeMcb` at `0x140129dec`
- `ntoskrnl!FsRtlUninitializeLargeMcb` at `0x140129e02`
- `ntoskrnl!ExCleanupAutoExpandPushLock` at `0x14012967a`
- `ntoskrnl!ExCleanupAutoExpandPushLock` at `0x14012967a`
- `ntoskrnl!FsRtlNotifyUninitializeSync` at `0x140129a4a`
- `ntoskrnl!FsRtlNotifyUninitializeSync` at `0x140129a4a`
- `ntoskrnl!FsRtlUninitializeOplock` at `0x1401295ce`
- `ntoskrnl!FsRtlUninitializeOplock` at `0x1401295ce`
- `ntoskrnl!FsRtlFreeFileLock` at `0x1401295f3`
- `ntoskrnl!FsRtlFreeFileLock` at `0x1401295f3`
- `ntoskrnl!FsRtlTeardownPerStreamContexts` at `0x140129662`
- `ntoskrnl!FsRtlTeardownPerStreamContexts` at `0x140129662`
- `ntoskrnl!FsRtlReleaseHeaderMutex` at `0x1401299f9`
- `ntoskrnl!FsRtlReleaseHeaderMutex` at `0x1401299f9`
- `ntoskrnl!FsRtlAcquireHeaderMutex` at `0x14012981c`
- `ntoskrnl!FsRtlAcquireHeaderMutex` at `0x14012981c`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x1401298b6`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x1401298b6`
- `ntoskrnl!ExReleasePushLockEx` at `0x14012999f`
- `ntoskrnl!ExReleasePushLockEx` at `0x1401299b2`
- `ntoskrnl!ExReleasePushLockEx` at `0x14012999f`
- `ntoskrnl!ExReleasePushLockEx` at `0x1401299b2`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x1401296d9`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x1401297bd`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x140129d2a`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x1401296d9`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x1401297bd`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x140129d2a`
- `ntoskrnl!KeReleaseGuardedMutex` at `0x140129ba6`
- `ntoskrnl!KeReleaseGuardedMutex` at `0x140129ba6`
- `ntoskrnl!ExFreePoolWithTag` at `0x14012976d`
- `ntoskrnl!ExFreePoolWithTag` at `0x140129a26`
- `ntoskrnl!ExFreePoolWithTag` at `0x140129abf`
- `ntoskrnl!ExFreePoolWithTag` at `0x140129bd1`
- `ntoskrnl!ExFreePoolWithTag` at `0x140129c83`
- `ntoskrnl!ExFreePoolWithTag` at `0x140129e18`
- `ntoskrnl!ExFreePoolWithTag` at `0x140129ec6`
- `ntoskrnl!ExFreePoolWithTag` at `0x140129f6a`
- `ntoskrnl!ExFreePoolWithTag` at `0x140129f7d`
- `ntoskrnl!ExFreePoolWithTag` at `0x140129f90`
- `ntoskrnl!ExFreePoolWithTag` at `0x14012976d`
- `ntoskrnl!ExFreePoolWithTag` at `0x140129a26`
- `ntoskrnl!ExFreePoolWithTag` at `0x140129abf`
- `ntoskrnl!ExFreePoolWithTag` at `0x140129bd1`
- `ntoskrnl!ExFreePoolWithTag` at `0x140129c83`
- `ntoskrnl!ExFreePoolWithTag` at `0x140129e18`
- `ntoskrnl!ExFreePoolWithTag` at `0x140129ec6`
- `ntoskrnl!ExFreePoolWithTag` at `0x140129f6a`
- `ntoskrnl!ExFreePoolWithTag` at `0x140129f7d`
- `ntoskrnl!ExFreePoolWithTag` at `0x140129f90`
- `ntoskrnl!KeAcquireGuardedMutex` at `0x140129afb`
- `ntoskrnl!KeAcquireGuardedMutex` at `0x140129afb`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140129ea2`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140129ea2`
- `ntoskrnl!ExReleaseResourceLite` at `0x140129da0`
- `ntoskrnl!ExReleaseResourceLite` at `0x140129da0`
- `ntoskrnl!ExAcquireFastMutex` at `0x140129a5e`
- `ntoskrnl!ExAcquireFastMutex` at `0x140129a5e`
- `ntoskrnl!ExReleaseFastMutex` at `0x140129a8b`
- `ntoskrnl!ExReleaseFastMutex` at `0x140129a8b`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x140129d44`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x140129d44`

## pseudocode

```c
void __fastcall NtfsDeleteScb(__int64 a1, PFSRTL_ADVANCED_FCB_HEADER *a2)
{
  PFSRTL_ADVANCED_FCB_HEADER v4; // rcx
  __int64 p_FileContextSupportPointer; // rax
  __int64 v6; // r8
  _QWORD *v7; // rdx
  PERESOURCE Resource; // rsi
  struct _ERESOURCE *SpinLock; // r14
  CSHORT NodeTypeCode; // bp
  LARGE_INTEGER AllocationSize; // rcx
  LARGE_MCB *v12; // rcx
  __int64 v13; // rdx
  __int64 v14; // r8
  FILE_LOCK *v15; // rcx
  PERESOURCE v16; // rcx
  struct _LIST_ENTRY *v17; // rcx
  __int64 v18; // rax
  __int64 v19; // rcx
  struct _LIST_ENTRY **FastMutex; // rdx
  LARGE_INTEGER v21; // rcx
  _DWORD *v22; // rdx
  __int64 v23; // rcx
  PFSRTL_ADVANCED_FCB_HEADER v24; // rsi
  int PushLock; // eax
  __int64 **v26; // r14
  PFAST_MUTEX v27; // rcx
  PFSRTL_ADVANCED_FCB_HEADER v28; // rdx
  CSHORT v29; // cx
  _WORD *v30; // r14
  LARGE_INTEGER *p_AllocationSize; // r15
  _QWORD *QuadPart; // rdx
  _WORD *v33; // r12
  _WORD *v34; // r13
  _QWORD *v35; // rax
  __int64 v36; // r15
  __int64 v37; // rax
  int v38; // edx
  __int64 v39; // r8
  unsigned __int64 v40; // rax
  _QWORD *v41; // r9
  __int64 v42; // r8
  _QWORD *v43; // rcx
  _QWORD *v44; // r12
  unsigned int v45; // edx
  int v46; // eax
  __int64 v47; // r8
  void *v48; // rcx
  PNOTIFY_SYNC *p_Blink; // rcx
  OWNER_ENTRY *i; // rcx
  PERESOURCE PagingIoResource; // rax
  __int64 v52; // rdi
  PERESOURCE v53; // rax
  POWNER_ENTRY OwnerTable; // rcx
  PERESOURCE v55; // rdx
  signed __int64 v56; // r8
  signed __int64 v57; // rax
  bool v58; // zf
  __int64 v59; // rtt
  signed __int64 SharedWaiters; // rax
  PVOID v61; // rtt
  __int64 v62; // r13
  LARGE_INTEGER *v63; // rax
  __int64 *v64; // rdi
  __int64 v65; // rax
  __int64 **v66; // rcx
  void *v67; // rcx
  void *v68; // rcx
  ULONG *v69; // rdx
  ULONG *p_ActiveEntries; // rax
  ULONG *v71; // rdx
  __int64 v72; // r8
  struct _LIST_ENTRY *Flink; // rdx
  __int64 v74; // r8
  char *v75; // rcx
  __int64 v76; // rax
  __int64 v77; // rcx
  _QWORD *v78; // [rsp+40h] [rbp-58h]
  _DWORD *v79; // [rsp+48h] [rbp-50h]
  __int64 v80; // [rsp+58h] [rbp-40h]
  _QWORD *v81; // [rsp+A8h] [rbp+10h] BYREF
  unsigned int v82; // [rsp+B0h] [rbp+18h]
  __int64 v83; // [rsp+B8h] [rbp+20h]

  v4 = *a2;
  p_FileContextSupportPointer = (__int64)&(*a2)[1].FileContextSupportPointer;
  v6 = *(_QWORD *)p_FileContextSupportPointer;
  if ( *(_QWORD *)(*(_QWORD *)p_FileContextSupportPointer + 8LL) != p_FileContextSupportPointer )
    goto LABEL_83;
  v7 = *(_QWORD **)&(*a2)[2].NodeTypeCode;
  if ( *v7 != p_FileContextSupportPointer )
    goto LABEL_83;
  Resource = v4[2].Resource;
  SpinLock = (struct _ERESOURCE *)Resource->SpinLock;
  *v7 = v6;
  *(_QWORD *)(v6 + 8) = v7;
  *(_QWORD *)&(*a2)[2].NodeTypeCode = MmBadPointer;
  (*a2)[1].FileContextSupportPointer = *(PVOID **)&(*a2)[2].NodeTypeCode;
  NodeTypeCode = (*a2)->NodeTypeCode;
  if ( LODWORD((*a2)[2].FileContextSupportPointer) == 176 && (Resource[1].NumberOfSharedWaiters & 0x10000000) != 0 )
  {
    v69 = 0;
    p_ActiveEntries = &Resource->ActiveEntries;
    while ( 1 )
    {
      v71 = v69 ? (ULONG *)*((_QWORD *)v69 + 21) : *(ULONG **)p_ActiveEntries;
      if ( v71 == p_ActiveEntries )
        break;
      v69 = v71 - 42;
      if ( !v69 )
        break;
      if ( v69[64] == 160 )
      {
        v72 = *((_QWORD *)v69 + 74);
        *(_OWORD *)(v69 + 150) = 0;
        *(_OWORD *)(v69 + 154) = 0;
        *((_QWORD *)v69 + 79) = 0;
        if ( v72 )
        {
          v77 = 712;
          if ( *(_QWORD *)(*(_QWORD *)(v72 + 192) + 48LL) != v72 )
            v77 = 742;
          *(_BYTE *)(v77 + v72) = 0;
        }
        *((_BYTE *)v69 + 742) = 0;
        break;
      }
    }
  }
  AllocationSize = (*a2)[3].AllocationSize;
  if ( AllocationSize.QuadPart && *(_DWORD *)(AllocationSize.QuadPart + 4) )
  {
    ExAcquireResourceSharedLite(SpinLock + 8, 1u);
    Flink = SpinLock[10].SystemResourcesList.Flink;
    v74 = *(unsigned int *)((*a2)[3].AllocationSize.QuadPart + 4);
    if ( (BYTE6(Flink->Flink) & 1) != 0 )
      v75 = (char *)&Flink[1].Blink + (unsigned int)LOWORD(Flink->Flink) * ((_DWORD)v74 - 1);
    else
      v75 = (char *)Flink + v74;
    *(_QWORD *)(*((_QWORD *)v75 + 4) + 24LL) = 0;
    if ( (*a2)[3].Resource )
      *(_BYTE *)(*((_QWORD *)v75 + 4) + 20LL) = 1;
    (*a2)[3].Resource = 0;
    ExReleaseResourceLite(SpinLock + 8);
  }
  NtfsUninitializeNtfsMcb(&(*a2)[4].FastMutex);
  v12 = (LARGE_MCB *)*a2;
  if ( NodeTypeCode == 1798 )
  {
    FsRtlUninitializeLargeMcb(v12 + 20);
    FsRtlUninitializeLargeMcb((PLARGE_MCB)&(*a2)[7].FilterContexts);
  }
  else
  {
    FsRtlUninitializeOplock(&v12[2].BaseMcb.Mapping);
    if ( NodeTypeCode == 1797 )
    {
      v15 = (FILE_LOCK *)(*a2)[6].FilterContexts.Flink;
      if ( v15 )
        FsRtlFreeFileLock(v15);
      v16 = (*a2)[7].Resource;
      if ( v16 )
      {
        ExFreePoolWithTag(v16, 0);
        (*a2)[7].Resource = 0;
      }
    }
    else
    {
      while ( 1 )
      {
        v30 = *a2;
        p_AllocationSize = &(*a2)[7].AllocationSize;
        QuadPart = (_QWORD *)p_AllocationSize->QuadPart;
        if ( (LARGE_INTEGER *)p_AllocationSize->QuadPart == p_AllocationSize )
          break;
        v81 = QuadPart - 1;
        NtfsFullDeleteLcb(0, QuadPart[2], &v81);
      }
      if ( *((_QWORD *)v30 + 83) )
      {
        v33 = v30 + 80;
        v34 = v30 + 60;
        FsRtlAcquireHeaderMutex(v30 + 60, v30 + 80);
        if ( (LARGE_INTEGER *)p_AllocationSize->QuadPart != p_AllocationSize )
        {
          v62 = p_AllocationSize->QuadPart - 8;
          do
          {
            if ( (*(_DWORD *)(v62 + 4) & 0x20) != 0 )
            {
              NtfsRemoveHashEntry(
                a1,
                *(_QWORD *)(*(_QWORD *)(v62 + 48) + 96LL) + 4968LL,
                *(unsigned int *)(v62 + 184),
                v62);
              *(_DWORD *)(v62 + 184) = 0;
              ClearFlagInterlocked(v62 + 4, 32);
            }
            v63 = *(LARGE_INTEGER **)(v62 + 8);
            v62 = (__int64)&v63[-1];
          }
          while ( v63 != p_AllocationSize );
          v34 = v30 + 60;
        }
        if ( *v30 != 1796 )
        {
          v35 = (_QWORD *)(*((_QWORD *)v30 + 23) + 48LL);
          if ( (_QWORD *)*v35 != v35 )
          {
            v36 = *v35 - 56LL;
            do
            {
              if ( (*(_DWORD *)(v36 + 4) & 0x20) != 0 )
              {
                v37 = *(_QWORD *)(v36 + 48);
                v38 = *(_DWORD *)(v36 + 184);
                LODWORD(v81) = v38;
                v39 = *(_QWORD *)(v37 + 96) + 4968LL;
                v79 = (_DWORD *)v39;
                if ( (!a1 || (*(_DWORD *)(a1 + 16) & 0x100000) == 0)
                  && (Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits & 0x80000000LL) != 0 )
                {
                  McTemplateU0pdpw_EtwWriteTransfer(
                    *(unsigned __int16 *)(v36 + 72) >> 1,
                    v38,
                    v39,
                    v38,
                    v36,
                    *(_WORD *)(v36 + 72) >> 1,
                    *(_QWORD *)(v36 + 80));
                  v39 = (__int64)v79;
                }
                v80 = v39 + 16;
                ExAcquirePushLockSharedEx(v39 + 16, 0);
                v40 = (unsigned int)v81 & (*v79 - 1);
                if ( (unsigned int)v40 < v79[1] )
                  v40 = (unsigned int)v81 & (2 * *v79 - 1);
                v83 = 16 * (v40 & 0x3FF);
                v78 = &v79[2 * (v40 >> 10) + 6];
                ExAcquirePushLockExclusiveEx(*v78 + 8LL + v83, 0);
                v41 = v78;
                v42 = v83;
                v43 = *(_QWORD **)(v83 + *v78);
                if ( v43 )
                {
                  v44 = (_QWORD *)(v83 + *v78);
                  v45 = 0;
                  v46 = (int)v81;
                  v82 = 0;
                  do
                  {
                    if ( *((_DWORD *)v43 + 4) == v46 && v43[1] == v36 )
                    {
                      *v44 = *v43;
                      ExFreePoolWithTag(v43, 0);
                      v46 = (int)v81;
                      v45 = v82;
                    }
                    else
                    {
                      ++v45;
                      v44 = v43;
                      v82 = v45;
                    }
                    v43 = (_QWORD *)*v44;
                  }
                  while ( *v44 );
                  v33 = v30 + 80;
                  if ( v45 <= 5 || v79[2] )
                  {
                    v41 = v78;
                    v42 = v83;
                  }
                  else
                  {
                    v42 = v83;
                    v41 = v78;
                    if ( *v79 < 0x8000u )
                      v79[2] = 1;
                  }
                }
                ExReleasePushLockEx(v42 + 8 + *v41, 0);
                ExReleasePushLockEx(v80, 0);
                *(_DWORD *)(v36 + 184) = 0;
                if ( (*(_DWORD *)(v36 + 4) & 0x20) != 0 )
                  _InterlockedAnd((volatile signed __int32 *)(v36 + 4), 0xFFFFFFDF);
              }
              v47 = *(_QWORD *)(v36 + 56);
              v36 = v47 - 56;
            }
            while ( v47 != *((_QWORD *)v30 + 23) + 48LL );
          }
        }
        FsRtlReleaseHeaderMutex(v34, v33);
        v48 = (void *)*((_QWORD *)v30 + 83);
        *((_QWORD *)v30 + 83) = 0;
        *((_DWORD *)v30 + 164) = 0;
        *((_DWORD *)v30 + 168) = 0;
        ExFreePoolWithTag(v48, 0);
      }
      p_Blink = (PNOTIFY_SYNC *)&(*a2)[8].FilterContexts.Blink;
      if ( *p_Blink )
        FsRtlNotifyUninitializeSync(p_Blink);
      ExAcquireFastMutex((PFAST_MUTEX)&Resource[1].SystemResourcesList.Flink->Blink);
      for ( i = (OWNER_ENTRY *)Resource->OwnerEntry.OwnerThread;
            i != &Resource->OwnerEntry;
            i = (OWNER_ENTRY *)i->OwnerThread )
      {
        i[5].OwnerThread = 0;
      }
      ExReleaseFastMutex((PFAST_MUTEX)&Resource[1].SystemResourcesList.Flink->Blink);
    }
  }
  NtfsDeleteEncryptionContext(*a2, v13, v14);
  v17 = (*a2)[5].FilterContexts.Flink;
  if ( v17 )
    v17[5].Flink = 0;
  v18 = NtfsAddStructToRollbackList(a1, 1830, *a2, 0);
  if ( v18 )
    NtfsProcessRollbackStruct(a1, v18, 16);
  v19 = *(_QWORD *)(a1 + 144);
  if ( a1 != v19 )
  {
    v76 = NtfsAddStructToRollbackList(v19, 1830, *a2, 0);
    if ( v76 )
      NtfsProcessRollbackStruct(*(_QWORD *)(a1 + 144), v76, 16);
  }
  if ( ((*a2)->Flags2 & 2) != 0 )
    FsRtlTeardownPerStreamContexts(*a2);
  if ( (*a2)[1].Resource )
    ExCleanupAutoExpandPushLock();
  FastMutex = (struct _LIST_ENTRY **)(*a2)->FastMutex;
  if ( FastMutex != &(*a2)[2].Resource[1].SystemResourcesList.Flink->Blink && FastMutex )
    ExFreeToLookasideListEx(&NtfsFastMutexNonpagedLookasideList, FastMutex);
  v21 = (*a2)[3].AllocationSize;
  if ( v21.QuadPart )
  {
    FsLibUninitializeRangeLock(v21.QuadPart + 48);
    v22 = (_DWORD *)(*a2)[3].AllocationSize.QuadPart;
    if ( (v22[17] & 1) != 0 )
      *(_WORD *)v22 = 0;
    else
      ExFreeToLookasideListEx(&NtfsScbNonpagedLookasideList, v22);
  }
  NtfsFreeScbAttributeName((*a2)[3].Resource);
  if ( ((*a2)[5].PushLock & 0x8000) != 0 )
    ExFreePoolWithTag((PVOID)(*a2)[7].PushLock, 0);
  v23 = *(_QWORD *)&(*a2)[6].NodeTypeCode;
  if ( v23 )
  {
    ExAcquireResourceExclusiveLite(*(PERESOURCE *)(*(_QWORD *)(v23 + 64) + 136LL), 1u);
    TxfDereferenceTxfScb(*(PVOID *)&(*a2)[6].NodeTypeCode);
  }
  v24 = *a2;
  PushLock = (*a2)[5].PushLock;
  if ( (PushLock & 0x10) != 0 || NodeTypeCode == 1798 )
    goto LABEL_121;
  if ( NodeTypeCode != 1797 )
    goto LABEL_37;
  v26 = *(__int64 ***)&v24[7].NodeTypeCode;
  if ( !v26 )
    goto LABEL_37;
  v27 = v24[6].FastMutex;
  if ( v27 && (PushLock & 0x2000) != 0 )
  {
    PagingIoResource = v24[2].PagingIoResource;
    v52 = ((__int64)v27 + PagingIoResource[4].ActiveEntries) >> LOBYTE(PagingIoResource[4].NumberOfSharedWaiters);
    KeAcquireGuardedMutex((PKGUARDED_MUTEX)&PagingIoResource[6].SpinLock);
    v24[2].PagingIoResource[3].OwnerTable = (POWNER_ENTRY)((char *)v24[2].PagingIoResource[3].OwnerTable - v52);
    v53 = v24[2].PagingIoResource;
    OwnerTable = v53[3].OwnerTable;
    if ( (__int64)OwnerTable < (signed __int64)v53[79].SpinLock )
      v53[79].SpinLock = (KSPIN_LOCK)OwnerTable;
    v55 = v24[2].PagingIoResource;
    v56 = v55[2].SpinLock
        - *(_QWORD *)&v55[61].ActiveCount
        - ((__int64)v55[3].OwnerTable >> 8)
        - (unsigned __int64)v55[3].OwnerTable;
    if ( v56 <= 0 )
      v56 = 0;
    do
    {
      v57 = *(_QWORD *)&v55[80].ActiveCount;
      if ( v56 >= v57 )
        break;
      v59 = *(_QWORD *)&v55[80].ActiveCount;
      v58 = v59 == _InterlockedCompareExchange64((volatile signed __int64 *)&v55[80].ActiveCount, v56, v57);
      v55 = v24[2].PagingIoResource;
    }
    while ( !v58 );
    do
    {
      SharedWaiters = (signed __int64)v55[80].SharedWaiters;
      if ( v56 <= SharedWaiters )
        break;
      v61 = v55[80].SharedWaiters;
      v58 = v61 == (PVOID)_InterlockedCompareExchange64(
                            (volatile signed __int64 *)&v55[80].SharedWaiters,
                            v56,
                            SharedWaiters);
      v55 = v24[2].PagingIoResource;
    }
    while ( !v58 );
    KeReleaseGuardedMutex((PKGUARDED_MUTEX)&v55[6].SpinLock);
  }
  v24[6].FastMutex = 0;
  if ( *v26 )
  {
    while ( 1 )
    {
      v64 = *v26;
      v65 = **v26;
      if ( *(__int64 **)(v65 + 8) != *v26 )
        break;
      v66 = (__int64 **)v64[1];
      if ( *v66 != v64 )
        break;
      *v66 = (__int64 *)v65;
      *(_QWORD *)(v65 + 8) = v66;
      v67 = (void *)v64[3];
      if ( v67 )
        ExFreePoolWithTag(v67, 0);
      v68 = (void *)v64[4];
      if ( v68 )
        ExFreePoolWithTag(v68, 0);
      ExFreePoolWithTag(v64, 0);
      if ( v64 == (__int64 *)v26 )
        goto LABEL_36;
    }
LABEL_83:
    __fastfail(3u);
  }
  ExFreePoolWithTag(v26, 0);
LABEL_36:
  *(_QWORD *)&v24[7].NodeTypeCode = 0;
LABEL_37:
  v28 = *a2;
  if ( *a2 == (PFSRTL_ADVANCED_FCB_HEADER)&(*a2)[2].Resource[3].OwnerEntry.0 )
  {
    v28->NodeTypeCode = 0;
    goto LABEL_40;
  }
  v29 = v28->NodeTypeCode;
  v28->NodeTypeCode = 0;
  if ( v29 != 1797 )
  {
LABEL_121:
    ExFreePoolWithTag(*a2, 0);
    goto LABEL_40;
  }
  ExFreeToLookasideListEx(&NtfsScbDataLookasideList, *a2);
LABEL_40:
  *a2 = 0;
}

```

## disassembly

```asm
0x140129500  push    rbx
0x140129502  push    rbp
0x140129503  push    rsi
0x140129504  push    rdi
0x140129505  push    r12
0x140129507  push    r14
0x140129509  push    r15
0x14012950b  sub     rsp, 60h
0x14012950f  mov     rdi, rcx
0x140129512  mov     rbx, rdx
0x140129515  mov     rcx, [rdx]
0x140129518  lea     rax, [rcx+0A8h]
0x14012951f  mov     r8, [rax]
0x140129522  cmp     [r8+8], rax
0x140129526  jnz     loc_140129BB7
0x14012952c  mov     rdx, [rax+8]
0x140129530  cmp     [rdx], rax
0x140129533  jnz     loc_140129BB7
0x140129539  mov     rsi, [rcx+0B8h]
0x140129540  xor     r12d, r12d
0x140129543  mov     rax, cs:MmBadPointer
0x14012954a  mov     r14, [rsi+60h]
0x14012954e  mov     [rdx], r8
0x140129551  mov     [r8+8], rdx
0x140129555  mov     rcx, [rax]
0x140129558  mov     rdx, [rbx]
0x14012955b  mov     [rdx+0B0h], rcx
0x140129562  mov     rcx, [rbx]
0x140129565  mov     rax, [rcx+0B0h]
0x14012956c  mov     [rcx+0A8h], rax
0x140129573  mov     rax, [rbx]
0x140129576  cmp     dword ptr [rax+100h], 0B0h
0x140129580  movzx   ebp, word ptr [rax]
0x140129583  jz      loc_140129C9A
0x140129589  mov     rax, [rbx]
0x14012958c  mov     rcx, [rax+120h]
0x140129593  test    rcx, rcx
0x140129596  jz      short loc_1401295A2
0x140129598  cmp     [rcx+4], r12d
0x14012959c  jnz     loc_140129D3B
0x1401295a2  mov     rcx, [rbx]
0x1401295a5  add     rcx, 190h
0x1401295ac  call    NtfsUninitializeNtfsMcb
0x1401295b1  mov     rcx, [rbx]
0x1401295b4  mov     r15d, 706h
0x1401295ba  mov     r14d, 705h
0x1401295c0  cmp     bp, r15w
0x1401295c4  jz      loc_140129DE5
0x1401295ca  add     rcx, 58h ; 'X'; Oplock
0x1401295ce  call    cs:__imp_FsRtlUninitializeOplock
0x1401295d5  nop     dword ptr [rax+rax+00h]
0x1401295da  cmp     bp, r14w
0x1401295de  jnz     loc_1401297E0
0x1401295e4  mov     rax, [rbx]
0x1401295e7  mov     rcx, [rax+248h]; FileLock
0x1401295ee  test    rcx, rcx
0x1401295f1  jz      short loc_1401295FF
0x1401295f3  call    cs:__imp_FsRtlFreeFileLock
0x1401295fa  nop     dword ptr [rax+rax+00h]
0x1401295ff  mov     rax, [rbx]
0x140129602  mov     rcx, [rax+270h]; P
0x140129609  test    rcx, rcx
0x14012960c  jnz     loc_140129EC4
0x140129612  mov     rcx, [rbx]
0x140129615  call    NtfsDeleteEncryptionContext
0x14012961a  mov     rax, [rbx]
0x14012961d  mov     rcx, [rax+1F0h]
0x140129624  test    rcx, rcx
0x140129627  jz      short loc_14012962D
0x140129629  mov     [rcx+50h], r12
0x14012962d  mov     r8, [rbx]
0x140129630  mov     edx, 726h
0x140129635  xor     r9d, r9d
0x140129638  mov     rcx, rdi
0x14012963b  call    NtfsAddStructToRollbackList
0x140129640  test    rax, rax
0x140129643  jnz     loc_140129F4B
0x140129649  mov     rcx, [rdi+90h]
0x140129650  cmp     rdi, rcx
0x140129653  jnz     loc_140129E3F
0x140129659  mov     rcx, [rbx]; AdvancedHeader
0x14012965c  test    byte ptr [rcx+6], 2
0x140129660  jz      short loc_14012966E
0x140129662  call    cs:__imp_FsRtlTeardownPerStreamContexts
0x140129669  nop     dword ptr [rax+rax+00h]
0x14012966e  mov     rax, [rbx]
0x140129671  mov     rcx, [rax+60h]
0x140129675  test    rcx, rcx
0x140129678  jz      short loc_140129686
0x14012967a  call    cs:__imp_ExCleanupAutoExpandPushLock
0x140129681  nop     dword ptr [rax+rax+00h]
0x140129686  mov     rax, [rbx]
0x140129689  mov     rdx, [rax+30h]; Entry
0x14012968d  mov     rax, [rax+0B8h]
0x140129694  mov     rcx, [rax+68h]
0x140129698  add     rcx, 8
0x14012969c  cmp     rdx, rcx
0x14012969f  jnz     loc_140129D1A
0x1401296a5  mov     rax, [rbx]
0x1401296a8  mov     rcx, [rax+120h]
0x1401296af  test    rcx, rcx
0x1401296b2  jz      short loc_1401296E5
0x1401296b4  add     rcx, 30h ; '0'
0x1401296b8  call    FsLibUninitializeRangeLock
0x1401296bd  mov     rax, [rbx]
0x1401296c0  mov     rdx, [rax+120h]; Entry
0x1401296c7  mov     eax, [rdx+44h]
0x1401296ca  test    al, 1
0x1401296cc  jnz     loc_140129AA8
0x1401296d2  lea     rcx, NtfsScbNonpagedLookasideList; Lookaside
0x1401296d9  call    cs:__imp_ExFreeToLookasideListEx
0x1401296e0  nop     dword ptr [rax+rax+00h]
0x1401296e5  mov     rcx, [rbx]
0x1401296e8  mov     rcx, [rcx+110h]
0x1401296ef  call    NtfsFreeScbAttributeName
0x1401296f4  mov     rcx, [rbx]
0x1401296f7  test    dword ptr [rcx+200h], 8000h
0x140129701  jnz     loc_140129F61
0x140129707  mov     rax, [rbx]
0x14012970a  mov     rcx, [rax+210h]
0x140129711  test    rcx, rcx
0x140129714  jnz     loc_140129E95
0x14012971a  mov     rsi, [rbx]
0x14012971d  mov     eax, [rsi+200h]
0x140129723  test    al, 10h
0x140129725  jnz     loc_140129ABA
0x14012972b  cmp     bp, r15w
0x14012972f  jz      loc_140129ABA
0x140129735  cmp     bp, r14w
0x140129739  jnz     short loc_140129786
0x14012973b  mov     r14, [rsi+268h]
0x140129742  test    r14, r14
0x140129745  jz      short loc_140129780
0x140129747  mov     rcx, [rsi+240h]
0x14012974e  test    rcx, rcx
0x140129751  jnz     loc_140129AD0
0x140129757  mov     [rsi+240h], r12
0x14012975e  cmp     qword ptr [r14], 0
0x140129762  jnz     loc_140129C40
0x140129768  xor     edx, edx; Tag
0x14012976a  mov     rcx, r14; P
0x14012976d  call    cs:__imp_ExFreePoolWithTag
0x140129774  nop     dword ptr [rax+rax+00h]
0x140129779  mov     [rsi+268h], r12
0x140129780  mov     r14d, 705h
0x140129786  mov     rdx, [rbx]
0x140129789  mov     rax, [rdx+0B8h]
0x140129790  add     rax, 170h
0x140129796  cmp     rdx, rax
0x140129799  jz      loc_140129AB1
0x14012979f  movzx   ecx, word ptr [rdx]
0x1401297a2  mov     [rdx], r12w
0x1401297a6  mov     rax, [rbx]
0x1401297a9  cmp     cx, r14w
0x1401297ad  jnz     loc_140129E13
0x1401297b3  mov     rdx, rax; Entry
0x1401297b6  lea     rcx, NtfsScbDataLookasideList; Lookaside
0x1401297bd  call    cs:__imp_ExFreeToLookasideListEx
0x1401297c4  nop     dword ptr [rax+rax+00h]
0x1401297c9  mov     [rbx], r12
0x1401297cc  add     rsp, 60h
0x1401297d0  pop     r15
0x1401297d2  pop     r14
0x1401297d4  pop     r12
0x1401297d6  pop     rdi
0x1401297d7  pop     rsi
0x1401297d8  pop     rbp
0x1401297d9  pop     rbx
0x1401297da  retn
0x1401297e0  mov     r14, [rbx]
0x1401297e3  lea     r15, [r14+280h]
0x1401297ea  mov     rdx, [r15]
0x1401297ed  cmp     rdx, r15
0x1401297f0  jnz     loc_140129BF0
0x1401297f6  cmp     [r14+298h], r12
0x1401297fd  jz      loc_140129A3A
0x140129803  mov     [rsp+98h+arg_0], r13
0x14012980b  lea     r12, [r14+0A0h]
0x140129812  lea     r13, [r14+78h]
0x140129816  mov     rdx, r12
0x140129819  mov     rcx, r13
0x14012981c  call    cs:__imp_FsRtlAcquireHeaderMutex
0x140129823  nop     dword ptr [rax+rax+00h]
0x140129828  mov     rax, [r15]
0x14012982b  cmp     rax, r15
0x14012982e  jnz     loc_140129C14
0x140129834  mov     eax, 704h
0x140129839  cmp     [r14], ax
0x14012983d  jz      loc_1401299F3
0x140129843  mov     rax, [r14+0B8h]
0x14012984a  add     rax, 30h ; '0'
0x14012984e  mov     r15, [rax]
0x140129851  cmp     r15, rax
0x140129854  jz      loc_1401299F3
0x14012985a  add     r15, 0FFFFFFFFFFFFFFC8h
0x14012985e  mov     eax, [r15+4]
0x140129862  test    al, 20h
0x140129864  jz      loc_1401299D7
0x14012986a  mov     rax, [r15+30h]
0x14012986e  mov     edx, [r15+0B8h]
0x140129875  mov     dword ptr [rsp+98h+arg_8], edx
0x14012987c  mov     r8, [rax+60h]
0x140129880  add     r8, 1368h
0x140129887  mov     [rsp+98h+var_50], r8
0x14012988c  test    rdi, rdi
0x14012988f  jz      short loc_14012989B
0x140129891  mov     eax, [rdi+10h]
0x140129894  bt      rax, 14h
0x140129899  jb      short loc_1401298A8
0x14012989b  cmp     byte ptr cs:Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits+3, 0
0x1401298a2  jl      loc_140129F20
0x1401298a8  lea     rax, [r8+10h]
0x1401298ac  xor     edx, edx
0x1401298ae  mov     rcx, rax
0x1401298b1  mov     [rsp+98h+var_40], rax
0x1401298b6  call    cs:__imp_ExAcquirePushLockSharedEx
0x1401298bd  nop     dword ptr [rax+rax+00h]
0x1401298c2  mov     r8, [rsp+98h+var_50]
0x1401298c7  mov     ecx, dword ptr [rsp+98h+arg_8]
0x1401298ce  mov     edx, [r8]
0x1401298d1  lea     eax, [rdx-1]
0x1401298d4  and     eax, ecx
0x1401298d6  cmp     eax, [r8+4]
0x1401298da  jnb     short loc_1401298E5
0x1401298dc  lea     eax, ds:0FFFFFFFFFFFFFFFFh[rdx*2]
0x1401298e3  and     eax, ecx
0x1401298e5  mov     rcx, rax
0x1401298e8  add     r8, 18h
0x1401298ec  shr     rax, 0Ah
0x1401298f0  and     ecx, 3FFh
0x1401298f6  shl     rcx, 4
0x1401298fa  xor     edx, edx
0x1401298fc  mov     [rsp+98h+arg_18], rcx
0x140129904  lea     rax, [r8+rax*8]
0x140129908  mov     [rsp+98h+var_58], rax
0x14012990d  mov     rax, [rax]
0x140129910  add     rax, 8
0x140129914  add     rcx, rax
0x140129917  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x14012991e  nop     dword ptr [rax+rax+00h]
0x140129923  mov     r9, [rsp+98h+var_58]
0x140129928  mov     r8, [rsp+98h+arg_18]
0x140129930  mov     rcx, [r9]
0x140129933  add     rcx, r8
0x140129936  mov     [rsp+98h+var_48], rcx
0x14012993b  mov     rcx, [rcx]; P
0x14012993e  test    rcx, rcx
0x140129941  jz      short loc_140129993
0x140129943  mov     r12, [rsp+98h+var_48]
0x140129948  xor     edx, edx
0x14012994a  mov     eax, dword ptr [rsp+98h+arg_8]
0x140129951  mov     [rsp+98h+arg_10], edx
0x140129958  cmp     [rcx+10h], eax
0x14012995b  jz      loc_140129BBE
0x140129961  inc     edx
0x140129963  mov     r12, rcx
0x140129966  mov     [rsp+98h+arg_10], edx
0x14012996d  mov     rcx, [r12]
0x140129971  test    rcx, rcx
0x140129974  jnz     short loc_140129958
0x140129976  lea     r12, [r14+0A0h]
0x14012997d  cmp     edx, 5
0x140129980  ja      loc_140129DB1
0x140129986  mov     r9, [rsp+98h+var_58]
0x14012998b  mov     r8, [rsp+98h+arg_18]
0x140129993  mov     rcx, [r9]
0x140129996  add     r8, 8
0x14012999a  add     rcx, r8
0x14012999d  xor     edx, edx
0x14012999f  call    cs:__imp_ExReleasePushLockEx
0x1401299a6  nop     dword ptr [rax+rax+00h]
0x1401299ab  mov     rcx, [rsp+98h+var_40]
0x1401299b0  xor     edx, edx
0x1401299b2  call    cs:__imp_ExReleasePushLockEx
0x1401299b9  nop     dword ptr [rax+rax+00h]
0x1401299be  mov     dword ptr [r15+0B8h], 0
0x1401299c9  mov     eax, [r15+4]
0x1401299cd  test    al, 20h
0x1401299cf  jz      short loc_1401299D7
0x1401299d1  lock and dword ptr [r15+4], 0FFFFFFDFh
0x1401299d7  mov     r8, [r15+38h]
0x1401299db  mov     rax, [r14+0B8h]
0x1401299e2  add     rax, 30h ; '0'
0x1401299e6  lea     r15, [r8-38h]
0x1401299ea  cmp     r8, rax
0x1401299ed  jnz     loc_14012985E
0x1401299f3  mov     rdx, r12
0x1401299f6  mov     rcx, r13
0x1401299f9  call    cs:__imp_FsRtlReleaseHeaderMutex
0x140129a00  nop     dword ptr [rax+rax+00h]
0x140129a05  mov     rcx, [r14+298h]; P
0x140129a0c  xor     r12d, r12d
0x140129a0f  xor     edx, edx; Tag
0x140129a11  mov     [r14+298h], r12
0x140129a18  mov     [r14+290h], r12d
0x140129a1f  mov     [r14+2A0h], r12d
0x140129a26  call    cs:__imp_ExFreePoolWithTag
0x140129a2d  nop     dword ptr [rax+rax+00h]
0x140129a32  mov     r13, [rsp+98h+arg_0]
0x140129a3a  mov     rcx, [rbx]
  ... truncated ...
```
