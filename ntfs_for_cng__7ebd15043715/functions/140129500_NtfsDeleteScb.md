# NtfsDeleteScb

- ea: `0x140129500`
- end: `0x140129fa1`
- name: `NtfsDeleteScb`
- size: `2721`
- prototype: `void __fastcall(__int64, __int64 *)`
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
void __fastcall NtfsDeleteScb(__int64 a1, __int64 *a2)
{
  __int64 v4; // rcx
  __int64 v5; // rax
  __int64 v6; // r8
  _QWORD *v7; // rdx
  __int64 v8; // rsi
  struct _ERESOURCE *v9; // r14
  __int16 v10; // bp
  __int64 v11; // rcx
  LARGE_MCB *v12; // rcx
  FILE_LOCK *v13; // rcx
  void *v14; // rcx
  __int64 v15; // rcx
  __int64 v16; // rax
  __int64 v17; // rcx
  __int64 v18; // rcx
  void *v19; // rdx
  __int64 v20; // rcx
  _DWORD *v21; // rdx
  __int64 v22; // rcx
  _QWORD *v23; // rsi
  int v24; // eax
  __int64 **v25; // r14
  __int64 v26; // rcx
  __int16 *v27; // rdx
  __int16 v28; // cx
  _WORD *v29; // r14
  _QWORD *v30; // r15
  _QWORD *v31; // rdx
  _WORD *v32; // r12
  _WORD *v33; // r13
  _QWORD *v34; // rax
  __int64 v35; // r15
  __int64 v36; // rax
  __int64 v37; // rdx
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
  PNOTIFY_SYNC *v48; // rcx
  _QWORD *i; // rcx
  __int64 v50; // rax
  __int64 v51; // rdi
  __int64 v52; // rax
  __int64 v53; // rcx
  __int64 v54; // rdx
  signed __int64 v55; // r8
  signed __int64 v56; // rax
  bool v57; // zf
  __int64 v58; // rtt
  signed __int64 v59; // rax
  __int64 v60; // rtt
  __int64 v61; // r13
  _QWORD *v62; // rax
  __int64 *v63; // rdi
  __int64 v64; // rax
  __int64 **v65; // rcx
  void *v66; // rcx
  void *v67; // rcx
  _QWORD *v68; // rdx
  _QWORD *v69; // rax
  _QWORD *v70; // rdx
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
  v5 = *a2 + 168;
  v6 = *(_QWORD *)v5;
  if ( *(_QWORD *)(*(_QWORD *)v5 + 8LL) != v5 )
    goto LABEL_83;
  v7 = *(_QWORD **)(*a2 + 176);
  if ( *v7 != v5 )
    goto LABEL_83;
  v8 = *(_QWORD *)(v4 + 184);
  v9 = *(struct _ERESOURCE **)(v8 + 96);
  *v7 = v6;
  *(_QWORD *)(v6 + 8) = v7;
  *(_QWORD *)(*a2 + 176) = MmBadPointer;
  *(_QWORD *)(*a2 + 168) = *(_QWORD *)(*a2 + 176);
  v10 = *(_WORD *)*a2;
  if ( *(_DWORD *)(*a2 + 256) == 176 && (*(_DWORD *)(v8 + 176) & 0x10000000) != 0 )
  {
    v68 = 0;
    v69 = (_QWORD *)(v8 + 64);
    while ( 1 )
    {
      v70 = (_QWORD *)(v68 ? v68[21] : *v69);
      if ( v70 == v69 )
        break;
      v68 = v70 - 21;
      if ( !v68 )
        break;
      if ( *((_DWORD *)v68 + 64) == 160 )
      {
        v71 = v68[74];
        *(_OWORD *)(v68 + 75) = 0;
        *(_OWORD *)(v68 + 77) = 0;
        v68[79] = 0;
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
  v11 = *(_QWORD *)(*a2 + 288);
  if ( v11 && *(_DWORD *)(v11 + 4) )
  {
    ExAcquireResourceSharedLite(v9 + 8, 1u);
    Flink = v9[10].SystemResourcesList.Flink;
    v73 = *(unsigned int *)(*(_QWORD *)(*a2 + 288) + 4LL);
    if ( (BYTE6(Flink->Flink) & 1) != 0 )
      v74 = (char *)&Flink[1].Blink + (unsigned int)LOWORD(Flink->Flink) * ((_DWORD)v73 - 1);
    else
      v74 = (char *)Flink + v73;
    *(_QWORD *)(*((_QWORD *)v74 + 4) + 24LL) = 0;
    if ( *(_QWORD *)(*a2 + 272) )
      *(_BYTE *)(*((_QWORD *)v74 + 4) + 20LL) = 1;
    *(_QWORD *)(*a2 + 272) = 0;
    ExReleaseResourceLite(v9 + 8);
  }
  NtfsUninitializeNtfsMcb(*a2 + 400);
  v12 = (LARGE_MCB *)*a2;
  if ( v10 == 1798 )
  {
    FsRtlUninitializeLargeMcb(v12 + 20);
    FsRtlUninitializeLargeMcb((PLARGE_MCB)(*a2 + 672));
  }
  else
  {
    FsRtlUninitializeOplock(&v12[2].BaseMcb.Mapping);
    if ( v10 == 1797 )
    {
      v13 = *(FILE_LOCK **)(*a2 + 584);
      if ( v13 )
        FsRtlFreeFileLock(v13);
      v14 = *(void **)(*a2 + 624);
      if ( v14 )
      {
        ExFreePoolWithTag(v14, 0);
        *(_QWORD *)(*a2 + 624) = 0;
      }
    }
    else
    {
      while ( 1 )
      {
        v29 = (_WORD *)*a2;
        v30 = (_QWORD *)(*a2 + 640);
        v31 = (_QWORD *)*v30;
        if ( (_QWORD *)*v30 == v30 )
          break;
        v80 = v31 - 1;
        NtfsFullDeleteLcb(0, v31[2], &v80);
      }
      if ( *((_QWORD *)v29 + 83) )
      {
        v32 = v29 + 80;
        v33 = v29 + 60;
        FsRtlAcquireHeaderMutex(v29 + 60, v29 + 80);
        if ( (_QWORD *)*v30 != v30 )
        {
          v61 = *v30 - 8LL;
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
              ClearFlagInterlocked((unsigned int *)(v61 + 4), 32);
            }
            v62 = *(_QWORD **)(v61 + 8);
            v61 = (__int64)(v62 - 1);
          }
          while ( v62 != v30 );
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
                v37 = *(unsigned int *)(v35 + 184);
                LODWORD(v80) = *(_DWORD *)(v35 + 184);
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
      v48 = (PNOTIFY_SYNC *)(*a2 + 768);
      if ( *v48 )
        FsRtlNotifyUninitializeSync(v48);
      ExAcquireFastMutex((PFAST_MUTEX)(*(_QWORD *)(v8 + 104) + 8LL));
      for ( i = *(_QWORD **)(v8 + 48); i != (_QWORD *)(v8 + 48); i = (_QWORD *)*i )
        i[10] = 0;
      ExReleaseFastMutex((PFAST_MUTEX)(*(_QWORD *)(v8 + 104) + 8LL));
    }
  }
  NtfsDeleteEncryptionContext(*a2);
  v15 = *(_QWORD *)(*a2 + 496);
  if ( v15 )
    *(_QWORD *)(v15 + 80) = 0;
  v16 = NtfsAddStructToRollbackList(a1, 1830, *a2, 0);
  if ( v16 )
    NtfsProcessRollbackStruct(a1, v16, 16);
  v17 = *(_QWORD *)(a1 + 144);
  if ( a1 != v17 )
  {
    v75 = NtfsAddStructToRollbackList(v17, 1830, *a2, 0);
    if ( v75 )
      NtfsProcessRollbackStruct(*(_QWORD *)(a1 + 144), v75, 16);
  }
  if ( (*(_BYTE *)(*a2 + 6) & 2) != 0 )
    FsRtlTeardownPerStreamContexts((PFSRTL_ADVANCED_FCB_HEADER)*a2);
  v18 = *(_QWORD *)(*a2 + 96);
  if ( v18 )
    ExCleanupAutoExpandPushLock(v18);
  v19 = *(void **)(*a2 + 48);
  if ( v19 != (void *)(*(_QWORD *)(*(_QWORD *)(*a2 + 184) + 104LL) + 8LL) && v19 )
    ExFreeToLookasideListEx(&NtfsFastMutexNonpagedLookasideList, v19);
  v20 = *(_QWORD *)(*a2 + 288);
  if ( v20 )
  {
    FsLibUninitializeRangeLock((_QWORD **)(v20 + 48));
    v21 = *(_DWORD **)(*a2 + 288);
    if ( (v21[17] & 1) != 0 )
      *(_WORD *)v21 = 0;
    else
      ExFreeToLookasideListEx(&NtfsScbNonpagedLookasideList, v21);
  }
  NtfsFreeScbAttributeName(*(wchar_t **)(*a2 + 272));
  if ( (*(_DWORD *)(*a2 + 512) & 0x8000) != 0 )
    ExFreePoolWithTag(*(PVOID *)(*a2 + 688), 0);
  v22 = *(_QWORD *)(*a2 + 528);
  if ( v22 )
  {
    ExAcquireResourceExclusiveLite(*(PERESOURCE *)(*(_QWORD *)(v22 + 64) + 136LL), 1u);
    TxfDereferenceTxfScb(*(PVOID *)(*a2 + 528));
  }
  v23 = (_QWORD *)*a2;
  v24 = *(_DWORD *)(*a2 + 512);
  if ( (v24 & 0x10) != 0 || v10 == 1798 )
    goto LABEL_121;
  if ( v10 != 1797 )
    goto LABEL_37;
  v25 = (__int64 **)v23[77];
  if ( !v25 )
    goto LABEL_37;
  v26 = v23[72];
  if ( v26 && (v24 & 0x2000) != 0 )
  {
    v50 = v23[24];
    v51 = (v26 + *(unsigned int *)(v50 + 480)) >> *(_BYTE *)(v50 + 488);
    KeAcquireGuardedMutex((PKGUARDED_MUTEX)(v50 + 720));
    *(_QWORD *)(v23[24] + 328LL) -= v51;
    v52 = v23[24];
    v53 = *(_QWORD *)(v52 + 328);
    if ( v53 < *(_QWORD *)(v52 + 8312) )
      *(_QWORD *)(v52 + 8312) = v53;
    v54 = v23[24];
    v55 = *(_QWORD *)(v54 + 304) - *(_QWORD *)(v54 + 6368) - (*(__int64 *)(v54 + 328) >> 8) - *(_QWORD *)(v54 + 328);
    if ( v55 <= 0 )
      v55 = 0;
    do
    {
      v56 = *(_QWORD *)(v54 + 8344);
      if ( v55 >= v56 )
        break;
      v58 = *(_QWORD *)(v54 + 8344);
      v57 = v58 == _InterlockedCompareExchange64((volatile signed __int64 *)(v54 + 8344), v55, v56);
      v54 = v23[24];
    }
    while ( !v57 );
    do
    {
      v59 = *(_QWORD *)(v54 + 8352);
      if ( v55 <= v59 )
        break;
      v60 = *(_QWORD *)(v54 + 8352);
      v57 = v60 == _InterlockedCompareExchange64((volatile signed __int64 *)(v54 + 8352), v55, v59);
      v54 = v23[24];
    }
    while ( !v57 );
    KeReleaseGuardedMutex((PKGUARDED_MUTEX)(v54 + 720));
  }
  v23[72] = 0;
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
  v23[77] = 0;
LABEL_37:
  v27 = (__int16 *)*a2;
  if ( *a2 == *(_QWORD *)(*a2 + 184) + 368LL )
  {
    *v27 = 0;
    goto LABEL_40;
  }
  v28 = *v27;
  *v27 = 0;
  if ( v28 != 1797 )
  {
LABEL_121:
    ExFreePoolWithTag((PVOID)*a2, 0);
    goto LABEL_40;
  }
  ExFreeToLookasideListEx(&NtfsScbDataLookasideList, (PVOID)*a2);
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
