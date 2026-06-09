# NtfsDeleteScb

- ea: `0x140129550`
- end: `0x140129ff1`
- name: `NtfsDeleteScb`
- size: `2721`
- prototype: ``
- caller_count: `7`
- callee_count: `12`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x1400cf580`
- `0x1400e9dc0`
- `0x140128a10`
- `0x140128da0`
- `0x14012a140`
- `0x140194cb8`
- `0x1401ff4b0`

## callees

- `0x14000ea70`
- `0x1400132a8`
- `0x140025c10`
- `0x140027f70`
- `0x140028680`
- `0x14004a4ac`
- `0x140129550`
- `0x14012a000`
- `0x14012bbd0`
- `0x140140b00`
- `0x1401db1b4`
- `0x1401e3280`

## import_xrefs

- `ntoskrnl!MmBadPointer` at `0x140129593`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140129967`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140129967`
- `ntoskrnl!FsRtlUninitializeLargeMcb` at `0x140129e3c`
- `ntoskrnl!FsRtlUninitializeLargeMcb` at `0x140129e52`
- `ntoskrnl!FsRtlUninitializeLargeMcb` at `0x140129e3c`
- `ntoskrnl!FsRtlUninitializeLargeMcb` at `0x140129e52`
- `ntoskrnl!ExCleanupAutoExpandPushLock` at `0x1401296ca`
- `ntoskrnl!ExCleanupAutoExpandPushLock` at `0x1401296ca`
- `ntoskrnl!FsRtlNotifyUninitializeSync` at `0x140129a9a`
- `ntoskrnl!FsRtlNotifyUninitializeSync` at `0x140129a9a`
- `ntoskrnl!FsRtlUninitializeOplock` at `0x14012961e`
- `ntoskrnl!FsRtlUninitializeOplock` at `0x14012961e`
- `ntoskrnl!FsRtlFreeFileLock` at `0x140129643`
- `ntoskrnl!FsRtlFreeFileLock` at `0x140129643`
- `ntoskrnl!FsRtlTeardownPerStreamContexts` at `0x1401296b2`
- `ntoskrnl!FsRtlTeardownPerStreamContexts` at `0x1401296b2`
- `ntoskrnl!FsRtlReleaseHeaderMutex` at `0x140129a49`
- `ntoskrnl!FsRtlReleaseHeaderMutex` at `0x140129a49`
- `ntoskrnl!FsRtlAcquireHeaderMutex` at `0x14012986c`
- `ntoskrnl!FsRtlAcquireHeaderMutex` at `0x14012986c`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x140129906`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x140129906`
- `ntoskrnl!ExReleasePushLockEx` at `0x1401299ef`
- `ntoskrnl!ExReleasePushLockEx` at `0x140129a02`
- `ntoskrnl!ExReleasePushLockEx` at `0x1401299ef`
- `ntoskrnl!ExReleasePushLockEx` at `0x140129a02`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x140129729`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14012980d`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x140129d7a`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x140129729`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14012980d`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x140129d7a`
- `ntoskrnl!KeReleaseGuardedMutex` at `0x140129bf6`
- `ntoskrnl!KeReleaseGuardedMutex` at `0x140129bf6`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401297bd`
- `ntoskrnl!ExFreePoolWithTag` at `0x140129a76`
- `ntoskrnl!ExFreePoolWithTag` at `0x140129b0f`
- `ntoskrnl!ExFreePoolWithTag` at `0x140129c21`
- `ntoskrnl!ExFreePoolWithTag` at `0x140129cd3`
- `ntoskrnl!ExFreePoolWithTag` at `0x140129e68`
- `ntoskrnl!ExFreePoolWithTag` at `0x140129f16`
- `ntoskrnl!ExFreePoolWithTag` at `0x140129fba`
- `ntoskrnl!ExFreePoolWithTag` at `0x140129fcd`
- `ntoskrnl!ExFreePoolWithTag` at `0x140129fe0`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401297bd`
- `ntoskrnl!ExFreePoolWithTag` at `0x140129a76`
- `ntoskrnl!ExFreePoolWithTag` at `0x140129b0f`
- `ntoskrnl!ExFreePoolWithTag` at `0x140129c21`
- `ntoskrnl!ExFreePoolWithTag` at `0x140129cd3`
- `ntoskrnl!ExFreePoolWithTag` at `0x140129e68`
- `ntoskrnl!ExFreePoolWithTag` at `0x140129f16`
- `ntoskrnl!ExFreePoolWithTag` at `0x140129fba`
- `ntoskrnl!ExFreePoolWithTag` at `0x140129fcd`
- `ntoskrnl!ExFreePoolWithTag` at `0x140129fe0`
- `ntoskrnl!KeAcquireGuardedMutex` at `0x140129b4b`
- `ntoskrnl!KeAcquireGuardedMutex` at `0x140129b4b`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140129ef2`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140129ef2`
- `ntoskrnl!ExReleaseResourceLite` at `0x140129df0`
- `ntoskrnl!ExReleaseResourceLite` at `0x140129df0`
- `ntoskrnl!ExAcquireFastMutex` at `0x140129aae`
- `ntoskrnl!ExAcquireFastMutex` at `0x140129aae`
- `ntoskrnl!ExReleaseFastMutex` at `0x140129adb`
- `ntoskrnl!ExReleaseFastMutex` at `0x140129adb`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x140129d94`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x140129d94`

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
  __int64 v13; // r8
  FILE_LOCK *v14; // rcx
  PERESOURCE v15; // rcx
  struct _LIST_ENTRY *v16; // rcx
  __int64 v17; // rax
  __int64 v18; // rcx
  struct _LIST_ENTRY **FastMutex; // rdx
  LARGE_INTEGER v20; // rcx
  _DWORD *v21; // rdx
  __int64 v22; // rcx
  PFSRTL_ADVANCED_FCB_HEADER v23; // rsi
  int PushLock; // eax
  __int64 **v25; // r14
  PFAST_MUTEX v26; // rcx
  PFSRTL_ADVANCED_FCB_HEADER v27; // rdx
  CSHORT v28; // cx
  _WORD *v29; // r14
  LARGE_INTEGER *p_AllocationSize; // r15
  _QWORD *QuadPart; // rdx
  _WORD *v32; // r12
  _WORD *v33; // r13
  _QWORD *v34; // rax
  __int64 v35; // r15
  __int64 v36; // rax
  int v37; // edx
  __int64 v38; // r8
  unsigned __int64 v39; // rax
  _QWORD *v40; // r9
  __int64 v41; // r8
  _QWORD *v42; // rcx
  _QWORD *v43; // r12
  unsigned int v44; // edx
  int v45; // eax
  __int64 v46; // r8
  void *v47; // rcx
  PNOTIFY_SYNC *p_Blink; // rcx
  OWNER_ENTRY *i; // rcx
  PERESOURCE PagingIoResource; // rax
  __int64 v51; // rdi
  PERESOURCE v52; // rax
  POWNER_ENTRY OwnerTable; // rcx
  PERESOURCE v54; // rdx
  signed __int64 v55; // r8
  signed __int64 v56; // rax
  bool v57; // zf
  __int64 v58; // rtt
  signed __int64 SharedWaiters; // rax
  PVOID v60; // rtt
  __int64 v61; // r13
  LARGE_INTEGER *v62; // rax
  __int64 *v63; // rdi
  __int64 v64; // rax
  __int64 **v65; // rcx
  void *v66; // rcx
  void *v67; // rcx
  ULONG *v68; // rdx
  ULONG *p_ActiveEntries; // rax
  ULONG *v70; // rdx
  __int64 v71; // r8
  struct _LIST_ENTRY *Flink; // rdx
  __int64 v73; // r8
  char *v74; // rcx
  __int64 v75; // rax
  __int64 v76; // rcx
  _QWORD *v77; // [rsp+40h] [rbp-58h]
  _DWORD *v78; // [rsp+48h] [rbp-50h]
  __int64 v79; // [rsp+58h] [rbp-40h]
  _QWORD *v80; // [rsp+A8h] [rbp+10h] BYREF
  unsigned int v81; // [rsp+B0h] [rbp+18h]
  __int64 v82; // [rsp+B8h] [rbp+20h]

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
    v68 = 0;
    p_ActiveEntries = &Resource->ActiveEntries;
    while ( 1 )
    {
      v70 = v68 ? (ULONG *)*((_QWORD *)v68 + 21) : *(ULONG **)p_ActiveEntries;
      if ( v70 == p_ActiveEntries )
        break;
      v68 = v70 - 42;
      if ( !v68 )
        break;
      if ( v68[64] == 160 )
      {
        v71 = *((_QWORD *)v68 + 74);
        *(_OWORD *)(v68 + 150) = 0;
        *(_OWORD *)(v68 + 154) = 0;
        *((_QWORD *)v68 + 79) = 0;
        if ( v71 )
        {
          v76 = 712;
          if ( *(_QWORD *)(*(_QWORD *)(v71 + 192) + 48LL) != v71 )
            v76 = 742;
          *(_BYTE *)(v76 + v71) = 0;
        }
        *((_BYTE *)v68 + 742) = 0;
        break;
      }
    }
  }
  AllocationSize = (*a2)[3].AllocationSize;
  if ( AllocationSize.QuadPart && *(_DWORD *)(AllocationSize.QuadPart + 4) )
  {
    ExAcquireResourceSharedLite(SpinLock + 8, 1u);
    Flink = SpinLock[10].SystemResourcesList.Flink;
    v73 = *(unsigned int *)((*a2)[3].AllocationSize.QuadPart + 4);
    if ( (BYTE6(Flink->Flink) & 1) != 0 )
      v74 = (char *)&Flink[1].Blink + (unsigned int)LOWORD(Flink->Flink) * ((_DWORD)v73 - 1);
    else
      v74 = (char *)Flink + v73;
    *(_QWORD *)(*((_QWORD *)v74 + 4) + 24LL) = 0;
    if ( (*a2)[3].Resource )
      *(_BYTE *)(*((_QWORD *)v74 + 4) + 20LL) = 1;
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
      v14 = (FILE_LOCK *)(*a2)[6].FilterContexts.Flink;
      if ( v14 )
        FsRtlFreeFileLock(v14);
      v15 = (*a2)[7].Resource;
      if ( v15 )
      {
        ExFreePoolWithTag(v15, 0);
        (*a2)[7].Resource = 0;
      }
    }
    else
    {
      while ( 1 )
      {
        v29 = *a2;
        p_AllocationSize = &(*a2)[7].AllocationSize;
        QuadPart = (_QWORD *)p_AllocationSize->QuadPart;
        if ( (LARGE_INTEGER *)p_AllocationSize->QuadPart == p_AllocationSize )
          break;
        v80 = QuadPart - 1;
        NtfsFullDeleteLcb(0, QuadPart[2], &v80);
      }
      if ( *((_QWORD *)v29 + 83) )
      {
        v32 = v29 + 80;
        v33 = v29 + 60;
        FsRtlAcquireHeaderMutex(v29 + 60, v29 + 80, v13);
        if ( (LARGE_INTEGER *)p_AllocationSize->QuadPart != p_AllocationSize )
        {
          v61 = p_AllocationSize->QuadPart - 8;
          do
          {
            if ( (*(_DWORD *)(v61 + 4) & 0x20) != 0 )
            {
              NtfsRemoveHashEntry(
                a1,
                *(_QWORD *)(*(_QWORD *)(v61 + 48) + 96LL) + 4968LL,
                *(unsigned int *)(v61 + 184),
                v61);
              *(_DWORD *)(v61 + 184) = 0;
              ClearFlagInterlocked(v61 + 4, 32);
            }
            v62 = *(LARGE_INTEGER **)(v61 + 8);
            v61 = (__int64)&v62[-1];
          }
          while ( v62 != p_AllocationSize );
          v33 = v29 + 60;
        }
        if ( *v29 != 1796 )
        {
          v34 = (_QWORD *)(*((_QWORD *)v29 + 23) + 48LL);
          if ( (_QWORD *)*v34 != v34 )
          {
            v35 = *v34 - 56LL;
            do
            {
              if ( (*(_DWORD *)(v35 + 4) & 0x20) != 0 )
              {
                v36 = *(_QWORD *)(v35 + 48);
                v37 = *(_DWORD *)(v35 + 184);
                LODWORD(v80) = v37;
                v38 = *(_QWORD *)(v36 + 96) + 4968LL;
                v78 = (_DWORD *)v38;
                if ( (!a1 || (*(_DWORD *)(a1 + 16) & 0x100000) == 0)
                  && (Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits & 0x80000000LL) != 0 )
                {
                  McTemplateU0pdpw_EtwWriteTransfer(
                    *(unsigned __int16 *)(v35 + 72) >> 1,
                    v37,
                    v38,
                    v37,
                    v35,
                    *(_WORD *)(v35 + 72) >> 1,
                    *(_QWORD *)(v35 + 80));
                  v38 = (__int64)v78;
                }
                v79 = v38 + 16;
                ExAcquirePushLockSharedEx(v38 + 16, 0);
                v39 = (unsigned int)v80 & (*v78 - 1);
                if ( (unsigned int)v39 < v78[1] )
                  v39 = (unsigned int)v80 & (2 * *v78 - 1);
                v82 = 16 * (v39 & 0x3FF);
                v77 = &v78[2 * (v39 >> 10) + 6];
                ExAcquirePushLockExclusiveEx(*v77 + 8LL + v82, 0);
                v40 = v77;
                v41 = v82;
                v42 = *(_QWORD **)(v82 + *v77);
                if ( v42 )
                {
                  v43 = (_QWORD *)(v82 + *v77);
                  v44 = 0;
                  v45 = (int)v80;
                  v81 = 0;
                  do
                  {
                    if ( *((_DWORD *)v42 + 4) == v45 && v42[1] == v35 )
                    {
                      *v43 = *v42;
                      ExFreePoolWithTag(v42, 0);
                      v45 = (int)v80;
                      v44 = v81;
                    }
                    else
                    {
                      ++v44;
                      v43 = v42;
                      v81 = v44;
                    }
                    v42 = (_QWORD *)*v43;
                  }
                  while ( *v43 );
                  v32 = v29 + 80;
                  if ( v44 <= 5 || v78[2] )
                  {
                    v40 = v77;
                    v41 = v82;
                  }
                  else
                  {
                    v41 = v82;
                    v40 = v77;
                    if ( *v78 < 0x8000u )
                      v78[2] = 1;
                  }
                }
                ExReleasePushLockEx(v41 + 8 + *v40, 0);
                ExReleasePushLockEx(v79, 0);
                *(_DWORD *)(v35 + 184) = 0;
                if ( (*(_DWORD *)(v35 + 4) & 0x20) != 0 )
                  _InterlockedAnd((volatile signed __int32 *)(v35 + 4), 0xFFFFFFDF);
              }
              v46 = *(_QWORD *)(v35 + 56);
              v35 = v46 - 56;
            }
            while ( v46 != *((_QWORD *)v29 + 23) + 48LL );
          }
        }
        FsRtlReleaseHeaderMutex(v33, v32);
        v47 = (void *)*((_QWORD *)v29 + 83);
        *((_QWORD *)v29 + 83) = 0;
        *((_DWORD *)v29 + 164) = 0;
        *((_DWORD *)v29 + 168) = 0;
        ExFreePoolWithTag(v47, 0);
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
  NtfsDeleteEncryptionContext(*a2);
  v16 = (*a2)[5].FilterContexts.Flink;
  if ( v16 )
    v16[5].Flink = 0;
  v17 = NtfsAddStructToRollbackList(a1, 1830, *a2, 0);
  if ( v17 )
    NtfsProcessRollbackStruct(a1, v17, 16);
  v18 = *(_QWORD *)(a1 + 144);
  if ( a1 != v18 )
  {
    v75 = NtfsAddStructToRollbackList(v18, 1830, *a2, 0);
    if ( v75 )
      NtfsProcessRollbackStruct(*(_QWORD *)(a1 + 144), v75, 16);
  }
  if ( ((*a2)->Flags2 & 2) != 0 )
    FsRtlTeardownPerStreamContexts(*a2);
  if ( (*a2)[1].Resource )
    ExCleanupAutoExpandPushLock();
  FastMutex = (struct _LIST_ENTRY **)(*a2)->FastMutex;
  if ( FastMutex != &(*a2)[2].Resource[1].SystemResourcesList.Flink->Blink && FastMutex )
    ExFreeToLookasideListEx(&NtfsFastMutexNonpagedLookasideList, FastMutex);
  v20 = (*a2)[3].AllocationSize;
  if ( v20.QuadPart )
  {
    FsLibUninitializeRangeLock(v20.QuadPart + 48);
    v21 = (_DWORD *)(*a2)[3].AllocationSize.QuadPart;
    if ( (v21[17] & 1) != 0 )
      *(_WORD *)v21 = 0;
    else
      ExFreeToLookasideListEx(&NtfsScbNonpagedLookasideList, v21);
  }
  NtfsFreeScbAttributeName((*a2)[3].Resource);
  if ( ((*a2)[5].PushLock & 0x8000) != 0 )
    ExFreePoolWithTag((PVOID)(*a2)[7].PushLock, 0);
  v22 = *(_QWORD *)&(*a2)[6].NodeTypeCode;
  if ( v22 )
  {
    ExAcquireResourceExclusiveLite(*(PERESOURCE *)(*(_QWORD *)(v22 + 64) + 136LL), 1u);
    TxfDereferenceTxfScb(*(PVOID *)&(*a2)[6].NodeTypeCode);
  }
  v23 = *a2;
  PushLock = (*a2)[5].PushLock;
  if ( (PushLock & 0x10) != 0 || NodeTypeCode == 1798 )
    goto LABEL_121;
  if ( NodeTypeCode != 1797 )
    goto LABEL_37;
  v25 = *(__int64 ***)&v23[7].NodeTypeCode;
  if ( !v25 )
    goto LABEL_37;
  v26 = v23[6].FastMutex;
  if ( v26 && (PushLock & 0x2000) != 0 )
  {
    PagingIoResource = v23[2].PagingIoResource;
    v51 = ((__int64)v26 + PagingIoResource[4].ActiveEntries) >> LOBYTE(PagingIoResource[4].NumberOfSharedWaiters);
    KeAcquireGuardedMutex((PKGUARDED_MUTEX)&PagingIoResource[6].SpinLock);
    v23[2].PagingIoResource[3].OwnerTable = (POWNER_ENTRY)((char *)v23[2].PagingIoResource[3].OwnerTable - v51);
    v52 = v23[2].PagingIoResource;
    OwnerTable = v52[3].OwnerTable;
    if ( (__int64)OwnerTable < (signed __int64)v52[79].SpinLock )
      v52[79].SpinLock = (KSPIN_LOCK)OwnerTable;
    v54 = v23[2].PagingIoResource;
    v55 = v54[2].SpinLock
        - *(_QWORD *)&v54[61].ActiveCount
        - ((__int64)v54[3].OwnerTable >> 8)
        - (unsigned __int64)v54[3].OwnerTable;
    if ( v55 <= 0 )
      v55 = 0;
    do
    {
      v56 = *(_QWORD *)&v54[80].ActiveCount;
      if ( v55 >= v56 )
        break;
      v58 = *(_QWORD *)&v54[80].ActiveCount;
      v57 = v58 == _InterlockedCompareExchange64((volatile signed __int64 *)&v54[80].ActiveCount, v55, v56);
      v54 = v23[2].PagingIoResource;
    }
    while ( !v57 );
    do
    {
      SharedWaiters = (signed __int64)v54[80].SharedWaiters;
      if ( v55 <= SharedWaiters )
        break;
      v60 = v54[80].SharedWaiters;
      v57 = v60 == (PVOID)_InterlockedCompareExchange64(
                            (volatile signed __int64 *)&v54[80].SharedWaiters,
                            v55,
                            SharedWaiters);
      v54 = v23[2].PagingIoResource;
    }
    while ( !v57 );
    KeReleaseGuardedMutex((PKGUARDED_MUTEX)&v54[6].SpinLock);
  }
  v23[6].FastMutex = 0;
  if ( *v25 )
  {
    while ( 1 )
    {
      v63 = *v25;
      v64 = **v25;
      if ( *(__int64 **)(v64 + 8) != *v25 )
        break;
      v65 = (__int64 **)v63[1];
      if ( *v65 != v63 )
        break;
      *v65 = (__int64 *)v64;
      *(_QWORD *)(v64 + 8) = v65;
      v66 = (void *)v63[3];
      if ( v66 )
        ExFreePoolWithTag(v66, 0);
      v67 = (void *)v63[4];
      if ( v67 )
        ExFreePoolWithTag(v67, 0);
      ExFreePoolWithTag(v63, 0);
      if ( v63 == (__int64 *)v25 )
        goto LABEL_36;
    }
LABEL_83:
    __fastfail(3u);
  }
  ExFreePoolWithTag(v25, 0);
LABEL_36:
  *(_QWORD *)&v23[7].NodeTypeCode = 0;
LABEL_37:
  v27 = *a2;
  if ( *a2 == (PFSRTL_ADVANCED_FCB_HEADER)&(*a2)[2].Resource[3].OwnerEntry.0 )
  {
    v27->NodeTypeCode = 0;
    goto LABEL_40;
  }
  v28 = v27->NodeTypeCode;
  v27->NodeTypeCode = 0;
  if ( v28 != 1797 )
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
0x140129550  push    rbx
0x140129552  push    rbp
0x140129553  push    rsi
0x140129554  push    rdi
0x140129555  push    r12
0x140129557  push    r14
0x140129559  push    r15
0x14012955b  sub     rsp, 60h
0x14012955f  mov     rdi, rcx
0x140129562  mov     rbx, rdx
0x140129565  mov     rcx, [rdx]
0x140129568  lea     rax, [rcx+0A8h]
0x14012956f  mov     r8, [rax]
0x140129572  cmp     [r8+8], rax
0x140129576  jnz     loc_140129C07
0x14012957c  mov     rdx, [rax+8]
0x140129580  cmp     [rdx], rax
0x140129583  jnz     loc_140129C07
0x140129589  mov     rsi, [rcx+0B8h]
0x140129590  xor     r12d, r12d
0x140129593  mov     rax, cs:MmBadPointer
0x14012959a  mov     r14, [rsi+60h]
0x14012959e  mov     [rdx], r8
0x1401295a1  mov     [r8+8], rdx
0x1401295a5  mov     rcx, [rax]
0x1401295a8  mov     rdx, [rbx]
0x1401295ab  mov     [rdx+0B0h], rcx
0x1401295b2  mov     rcx, [rbx]
0x1401295b5  mov     rax, [rcx+0B0h]
0x1401295bc  mov     [rcx+0A8h], rax
0x1401295c3  mov     rax, [rbx]
0x1401295c6  cmp     dword ptr [rax+100h], 0B0h
0x1401295d0  movzx   ebp, word ptr [rax]
0x1401295d3  jz      loc_140129CEA
0x1401295d9  mov     rax, [rbx]
0x1401295dc  mov     rcx, [rax+120h]
0x1401295e3  test    rcx, rcx
0x1401295e6  jz      short loc_1401295F2
0x1401295e8  cmp     [rcx+4], r12d
0x1401295ec  jnz     loc_140129D8B
0x1401295f2  mov     rcx, [rbx]
0x1401295f5  add     rcx, 190h
0x1401295fc  call    NtfsUninitializeNtfsMcb
0x140129601  mov     rcx, [rbx]
0x140129604  mov     r15d, 706h
0x14012960a  mov     r14d, 705h
0x140129610  cmp     bp, r15w
0x140129614  jz      loc_140129E35
0x14012961a  add     rcx, 58h ; 'X'; Oplock
0x14012961e  call    cs:__imp_FsRtlUninitializeOplock
0x140129625  nop     dword ptr [rax+rax+00h]
0x14012962a  cmp     bp, r14w
0x14012962e  jnz     loc_140129830
0x140129634  mov     rax, [rbx]
0x140129637  mov     rcx, [rax+248h]; FileLock
0x14012963e  test    rcx, rcx
0x140129641  jz      short loc_14012964F
0x140129643  call    cs:__imp_FsRtlFreeFileLock
0x14012964a  nop     dword ptr [rax+rax+00h]
0x14012964f  mov     rax, [rbx]
0x140129652  mov     rcx, [rax+270h]; P
0x140129659  test    rcx, rcx
0x14012965c  jnz     loc_140129F14
0x140129662  mov     rcx, [rbx]
0x140129665  call    NtfsDeleteEncryptionContext
0x14012966a  mov     rax, [rbx]
0x14012966d  mov     rcx, [rax+1F0h]
0x140129674  test    rcx, rcx
0x140129677  jz      short loc_14012967D
0x140129679  mov     [rcx+50h], r12
0x14012967d  mov     r8, [rbx]
0x140129680  mov     edx, 726h
0x140129685  xor     r9d, r9d
0x140129688  mov     rcx, rdi
0x14012968b  call    NtfsAddStructToRollbackList
0x140129690  test    rax, rax
0x140129693  jnz     loc_140129F9B
0x140129699  mov     rcx, [rdi+90h]
0x1401296a0  cmp     rdi, rcx
0x1401296a3  jnz     loc_140129E8F
0x1401296a9  mov     rcx, [rbx]; AdvancedHeader
0x1401296ac  test    byte ptr [rcx+6], 2
0x1401296b0  jz      short loc_1401296BE
0x1401296b2  call    cs:__imp_FsRtlTeardownPerStreamContexts
0x1401296b9  nop     dword ptr [rax+rax+00h]
0x1401296be  mov     rax, [rbx]
0x1401296c1  mov     rcx, [rax+60h]
0x1401296c5  test    rcx, rcx
0x1401296c8  jz      short loc_1401296D6
0x1401296ca  call    cs:__imp_ExCleanupAutoExpandPushLock
0x1401296d1  nop     dword ptr [rax+rax+00h]
0x1401296d6  mov     rax, [rbx]
0x1401296d9  mov     rdx, [rax+30h]; Entry
0x1401296dd  mov     rax, [rax+0B8h]
0x1401296e4  mov     rcx, [rax+68h]
0x1401296e8  add     rcx, 8
0x1401296ec  cmp     rdx, rcx
0x1401296ef  jnz     loc_140129D6A
0x1401296f5  mov     rax, [rbx]
0x1401296f8  mov     rcx, [rax+120h]
0x1401296ff  test    rcx, rcx
0x140129702  jz      short loc_140129735
0x140129704  add     rcx, 30h ; '0'
0x140129708  call    FsLibUninitializeRangeLock
0x14012970d  mov     rax, [rbx]
0x140129710  mov     rdx, [rax+120h]; Entry
0x140129717  mov     eax, [rdx+44h]
0x14012971a  test    al, 1
0x14012971c  jnz     loc_140129AF8
0x140129722  lea     rcx, NtfsScbNonpagedLookasideList; Lookaside
0x140129729  call    cs:__imp_ExFreeToLookasideListEx
0x140129730  nop     dword ptr [rax+rax+00h]
0x140129735  mov     rcx, [rbx]
0x140129738  mov     rcx, [rcx+110h]
0x14012973f  call    NtfsFreeScbAttributeName
0x140129744  mov     rcx, [rbx]
0x140129747  test    dword ptr [rcx+200h], 8000h
0x140129751  jnz     loc_140129FB1
0x140129757  mov     rax, [rbx]
0x14012975a  mov     rcx, [rax+210h]
0x140129761  test    rcx, rcx
0x140129764  jnz     loc_140129EE5
0x14012976a  mov     rsi, [rbx]
0x14012976d  mov     eax, [rsi+200h]
0x140129773  test    al, 10h
0x140129775  jnz     loc_140129B0A
0x14012977b  cmp     bp, r15w
0x14012977f  jz      loc_140129B0A
0x140129785  cmp     bp, r14w
0x140129789  jnz     short loc_1401297D6
0x14012978b  mov     r14, [rsi+268h]
0x140129792  test    r14, r14
0x140129795  jz      short loc_1401297D0
0x140129797  mov     rcx, [rsi+240h]
0x14012979e  test    rcx, rcx
0x1401297a1  jnz     loc_140129B20
0x1401297a7  mov     [rsi+240h], r12
0x1401297ae  cmp     qword ptr [r14], 0
0x1401297b2  jnz     loc_140129C90
0x1401297b8  xor     edx, edx; Tag
0x1401297ba  mov     rcx, r14; P
0x1401297bd  call    cs:__imp_ExFreePoolWithTag
0x1401297c4  nop     dword ptr [rax+rax+00h]
0x1401297c9  mov     [rsi+268h], r12
0x1401297d0  mov     r14d, 705h
0x1401297d6  mov     rdx, [rbx]
0x1401297d9  mov     rax, [rdx+0B8h]
0x1401297e0  add     rax, 170h
0x1401297e6  cmp     rdx, rax
0x1401297e9  jz      loc_140129B01
0x1401297ef  movzx   ecx, word ptr [rdx]
0x1401297f2  mov     [rdx], r12w
0x1401297f6  mov     rax, [rbx]
0x1401297f9  cmp     cx, r14w
0x1401297fd  jnz     loc_140129E63
0x140129803  mov     rdx, rax; Entry
0x140129806  lea     rcx, NtfsScbDataLookasideList; Lookaside
0x14012980d  call    cs:__imp_ExFreeToLookasideListEx
0x140129814  nop     dword ptr [rax+rax+00h]
0x140129819  mov     [rbx], r12
0x14012981c  add     rsp, 60h
0x140129820  pop     r15
0x140129822  pop     r14
0x140129824  pop     r12
0x140129826  pop     rdi
0x140129827  pop     rsi
0x140129828  pop     rbp
0x140129829  pop     rbx
0x14012982a  retn
0x140129830  mov     r14, [rbx]
0x140129833  lea     r15, [r14+280h]
0x14012983a  mov     rdx, [r15]
0x14012983d  cmp     rdx, r15
0x140129840  jnz     loc_140129C40
0x140129846  cmp     [r14+298h], r12
0x14012984d  jz      loc_140129A8A
0x140129853  mov     [rsp+98h+arg_0], r13
0x14012985b  lea     r12, [r14+0A0h]
0x140129862  lea     r13, [r14+78h]
0x140129866  mov     rdx, r12
0x140129869  mov     rcx, r13
0x14012986c  call    cs:__imp_FsRtlAcquireHeaderMutex
0x140129873  nop     dword ptr [rax+rax+00h]
0x140129878  mov     rax, [r15]
0x14012987b  cmp     rax, r15
0x14012987e  jnz     loc_140129C64
0x140129884  mov     eax, 704h
0x140129889  cmp     [r14], ax
0x14012988d  jz      loc_140129A43
0x140129893  mov     rax, [r14+0B8h]
0x14012989a  add     rax, 30h ; '0'
0x14012989e  mov     r15, [rax]
0x1401298a1  cmp     r15, rax
0x1401298a4  jz      loc_140129A43
0x1401298aa  add     r15, 0FFFFFFFFFFFFFFC8h
0x1401298ae  mov     eax, [r15+4]
0x1401298b2  test    al, 20h
0x1401298b4  jz      loc_140129A27
0x1401298ba  mov     rax, [r15+30h]
0x1401298be  mov     edx, [r15+0B8h]
0x1401298c5  mov     dword ptr [rsp+98h+arg_8], edx
0x1401298cc  mov     r8, [rax+60h]
0x1401298d0  add     r8, 1368h
0x1401298d7  mov     [rsp+98h+var_50], r8
0x1401298dc  test    rdi, rdi
0x1401298df  jz      short loc_1401298EB
0x1401298e1  mov     eax, [rdi+10h]
0x1401298e4  bt      rax, 14h
0x1401298e9  jb      short loc_1401298F8
0x1401298eb  cmp     byte ptr cs:Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits+3, 0
0x1401298f2  jl      loc_140129F70
0x1401298f8  lea     rax, [r8+10h]
0x1401298fc  xor     edx, edx
0x1401298fe  mov     rcx, rax
0x140129901  mov     [rsp+98h+var_40], rax
0x140129906  call    cs:__imp_ExAcquirePushLockSharedEx
0x14012990d  nop     dword ptr [rax+rax+00h]
0x140129912  mov     r8, [rsp+98h+var_50]
0x140129917  mov     ecx, dword ptr [rsp+98h+arg_8]
0x14012991e  mov     edx, [r8]
0x140129921  lea     eax, [rdx-1]
0x140129924  and     eax, ecx
0x140129926  cmp     eax, [r8+4]
0x14012992a  jnb     short loc_140129935
0x14012992c  lea     eax, ds:0FFFFFFFFFFFFFFFFh[rdx*2]
0x140129933  and     eax, ecx
0x140129935  mov     rcx, rax
0x140129938  add     r8, 18h
0x14012993c  shr     rax, 0Ah
0x140129940  and     ecx, 3FFh
0x140129946  shl     rcx, 4
0x14012994a  xor     edx, edx
0x14012994c  mov     [rsp+98h+arg_18], rcx
0x140129954  lea     rax, [r8+rax*8]
0x140129958  mov     [rsp+98h+var_58], rax
0x14012995d  mov     rax, [rax]
0x140129960  add     rax, 8
0x140129964  add     rcx, rax
0x140129967  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x14012996e  nop     dword ptr [rax+rax+00h]
0x140129973  mov     r9, [rsp+98h+var_58]
0x140129978  mov     r8, [rsp+98h+arg_18]
0x140129980  mov     rcx, [r9]
0x140129983  add     rcx, r8
0x140129986  mov     [rsp+98h+var_48], rcx
0x14012998b  mov     rcx, [rcx]; P
0x14012998e  test    rcx, rcx
0x140129991  jz      short loc_1401299E3
0x140129993  mov     r12, [rsp+98h+var_48]
0x140129998  xor     edx, edx
0x14012999a  mov     eax, dword ptr [rsp+98h+arg_8]
0x1401299a1  mov     [rsp+98h+arg_10], edx
0x1401299a8  cmp     [rcx+10h], eax
0x1401299ab  jz      loc_140129C0E
0x1401299b1  inc     edx
0x1401299b3  mov     r12, rcx
0x1401299b6  mov     [rsp+98h+arg_10], edx
0x1401299bd  mov     rcx, [r12]
0x1401299c1  test    rcx, rcx
0x1401299c4  jnz     short loc_1401299A8
0x1401299c6  lea     r12, [r14+0A0h]
0x1401299cd  cmp     edx, 5
0x1401299d0  ja      loc_140129E01
0x1401299d6  mov     r9, [rsp+98h+var_58]
0x1401299db  mov     r8, [rsp+98h+arg_18]
0x1401299e3  mov     rcx, [r9]
0x1401299e6  add     r8, 8
0x1401299ea  add     rcx, r8
0x1401299ed  xor     edx, edx
0x1401299ef  call    cs:__imp_ExReleasePushLockEx
0x1401299f6  nop     dword ptr [rax+rax+00h]
0x1401299fb  mov     rcx, [rsp+98h+var_40]
0x140129a00  xor     edx, edx
0x140129a02  call    cs:__imp_ExReleasePushLockEx
0x140129a09  nop     dword ptr [rax+rax+00h]
0x140129a0e  mov     dword ptr [r15+0B8h], 0
0x140129a19  mov     eax, [r15+4]
0x140129a1d  test    al, 20h
0x140129a1f  jz      short loc_140129A27
0x140129a21  lock and dword ptr [r15+4], 0FFFFFFDFh
0x140129a27  mov     r8, [r15+38h]
0x140129a2b  mov     rax, [r14+0B8h]
0x140129a32  add     rax, 30h ; '0'
0x140129a36  lea     r15, [r8-38h]
0x140129a3a  cmp     r8, rax
0x140129a3d  jnz     loc_1401298AE
0x140129a43  mov     rdx, r12
0x140129a46  mov     rcx, r13
0x140129a49  call    cs:__imp_FsRtlReleaseHeaderMutex
0x140129a50  nop     dword ptr [rax+rax+00h]
0x140129a55  mov     rcx, [r14+298h]; P
0x140129a5c  xor     r12d, r12d
0x140129a5f  xor     edx, edx; Tag
0x140129a61  mov     [r14+298h], r12
0x140129a68  mov     [r14+290h], r12d
0x140129a6f  mov     [r14+2A0h], r12d
0x140129a76  call    cs:__imp_ExFreePoolWithTag
0x140129a7d  nop     dword ptr [rax+rax+00h]
0x140129a82  mov     r13, [rsp+98h+arg_0]
0x140129a8a  mov     rcx, [rbx]
  ... truncated ...
```
