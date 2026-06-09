# NtfsCleanupIrpContext

- ea: `0x140008740`
- end: `0x140009708`
- name: `NtfsCleanupIrpContext`
- size: `4040`
- prototype: ``
- caller_count: `68`
- callee_count: `17`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x140006670`
- `0x1400082b0`
- `0x1400085e0`
- `0x140009c80`
- `0x14000a000`
- `0x14000a0f0`
- `0x14000a760`
- `0x140012480`
- `0x140029d80`
- `0x140034a70`
- `0x140052bf0`
- `0x1400b96a0`
- `0x1400ba87c`
- `0x1400bb020`
- `0x1400bbf04`
- `0x1400cab50`
- `0x1400cb8c4`
- `0x1400dc2c0`
- `0x1400dec60`
- `0x1400df650`
- `0x1400e6a6c`
- `0x1400ec79c`
- `0x1400f758c`
- `0x1400fa6e8`
- `0x1400fc0e0`
- `0x14010c820`
- `0x14010d198`
- `0x140133f80`
- `0x140181bb0`
- `0x1401826e0`
- `0x14018f418`
- `0x140190bd0`
- `0x1401aa72c`
- `0x1401ac2f0`
- `0x1401bbd80`
- `0x1401bd410`
- `0x1401bd990`
- `0x1401cf490`
- `0x1401d1fac`
- `0x1401d437c`
- `0x1401d5148`
- `0x1401d6998`
- `0x1401d8390`
- `0x1401e9550`
- `0x1401f3be0`
- `0x1401f4270`
- `0x1401f50d8`
- `0x1401fc650`
- `0x1401fcd40`
- `0x14020a774`

## callees

- `0x1400054e8`
- `0x140008740`
- `0x14000e220`
- `0x14000ea70`
- `0x140021c30`
- `0x14004062c`
- `0x140040d48`
- `0x14004161c`
- `0x1400416d4`
- `0x14004fad8`
- `0x1400592c0`
- `0x140059740`
- `0x140176eb0`
- `0x1401aac80`
- `0x1401e76f0`
- `0x1401e7820`
- `0x14025125c`

## import_xrefs

- `ntoskrnl!ExQueueWorkItem` at `0x1400095ac`
- `ntoskrnl!ExQueueWorkItem` at `0x1400095ac`
- `ntoskrnl!IoSetTopLevelIrp` at `0x140009603`
- `ntoskrnl!IoSetTopLevelIrp` at `0x140009603`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400094e4`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400094e4`
- `ntoskrnl!KeReleaseSpinLock` at `0x140009543`
- `ntoskrnl!KeReleaseSpinLock` at `0x140009543`
- `ntoskrnl!MmUnmapLockedPages` at `0x14000938b`
- `ntoskrnl!MmUnmapLockedPages` at `0x14000938b`
- `ntoskrnl!IoFreeMdl` at `0x14000939a`
- `ntoskrnl!IoFreeMdl` at `0x14000939a`
- `ntoskrnl!ExReleaseRundownProtection` at `0x14000934f`
- `ntoskrnl!ExReleaseRundownProtection` at `0x14000934f`
- `ntoskrnl!SeReleaseSubjectContext` at `0x140009431`
- `ntoskrnl!SeReleaseSubjectContext` at `0x140009431`
- `ntoskrnl!FsRtlReleaseEofLock` at `0x140008dfd`
- `ntoskrnl!FsRtlReleaseEofLock` at `0x140008dfd`
- `ntoskrnl!FsRtlReleaseHeaderMutex` at `0x140008a75`
- `ntoskrnl!FsRtlReleaseHeaderMutex` at `0x140008c9c`
- `ntoskrnl!FsRtlReleaseHeaderMutex` at `0x140008fbf`
- `ntoskrnl!FsRtlReleaseHeaderMutex` at `0x1400091a2`
- `ntoskrnl!FsRtlReleaseHeaderMutex` at `0x140008a75`
- `ntoskrnl!FsRtlReleaseHeaderMutex` at `0x140008c9c`
- `ntoskrnl!FsRtlReleaseHeaderMutex` at `0x140008fbf`
- `ntoskrnl!FsRtlReleaseHeaderMutex` at `0x1400091a2`
- `ntoskrnl!FsRtlAcquireHeaderMutex` at `0x140008a4b`
- `ntoskrnl!FsRtlAcquireHeaderMutex` at `0x140008c72`
- `ntoskrnl!FsRtlAcquireHeaderMutex` at `0x140008f95`
- `ntoskrnl!FsRtlAcquireHeaderMutex` at `0x140009178`
- `ntoskrnl!FsRtlAcquireHeaderMutex` at `0x140008a4b`
- `ntoskrnl!FsRtlAcquireHeaderMutex` at `0x140008c72`
- `ntoskrnl!FsRtlAcquireHeaderMutex` at `0x140008f95`
- `ntoskrnl!FsRtlAcquireHeaderMutex` at `0x140009178`
- `ntoskrnl!ExIsResourceAcquiredSharedLite` at `0x140008933`
- `ntoskrnl!ExIsResourceAcquiredSharedLite` at `0x140008b58`
- `ntoskrnl!ExIsResourceAcquiredSharedLite` at `0x140008933`
- `ntoskrnl!ExIsResourceAcquiredSharedLite` at `0x140008b58`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x140008823`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x140008ab0`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x140008cd7`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x140008ffa`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x1400091de`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x1400093ce`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x140009417`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14000966c`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x140008823`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x140008ab0`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x140008cd7`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x140008ffa`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x1400091de`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x1400093ce`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x140009417`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14000966c`
- `ntoskrnl!FsRtlUninitializeBaseMcb` at `0x1400087f2`
- `ntoskrnl!FsRtlUninitializeBaseMcb` at `0x140008809`
- `ntoskrnl!FsRtlUninitializeBaseMcb` at `0x1400087f2`
- `ntoskrnl!FsRtlUninitializeBaseMcb` at `0x140008809`
- `ntoskrnl!ExFreePoolWithTag` at `0x140008d49`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000921c`
- `ntoskrnl!ExFreePoolWithTag` at `0x140009306`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400093b4`
- `ntoskrnl!ExFreePoolWithTag` at `0x140009446`
- `ntoskrnl!ExFreePoolWithTag` at `0x140008d49`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000921c`
- `ntoskrnl!ExFreePoolWithTag` at `0x140009306`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400093b4`
- `ntoskrnl!ExFreePoolWithTag` at `0x140009446`
- `ntoskrnl!CcUnpinData` at `0x14000886b`
- `ntoskrnl!CcUnpinData` at `0x14000886b`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400088b2`
- `ntoskrnl!ExReleaseResourceLite` at `0x140008ae8`
- `ntoskrnl!ExReleaseResourceLite` at `0x140008d1b`
- `ntoskrnl!ExReleaseResourceLite` at `0x140008dae`
- `ntoskrnl!ExReleaseResourceLite` at `0x140009042`
- `ntoskrnl!ExReleaseResourceLite` at `0x14000905e`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400088b2`
- `ntoskrnl!ExReleaseResourceLite` at `0x140008ae8`
- `ntoskrnl!ExReleaseResourceLite` at `0x140008d1b`
- `ntoskrnl!ExReleaseResourceLite` at `0x140008dae`
- `ntoskrnl!ExReleaseResourceLite` at `0x140009042`
- `ntoskrnl!ExReleaseResourceLite` at `0x14000905e`
- `ntoskrnl!IoGetTopLevelIrp` at `0x14000928a`
- `ntoskrnl!IoGetTopLevelIrp` at `0x1400095e5`
- `ntoskrnl!IoGetTopLevelIrp` at `0x14000928a`
- `ntoskrnl!IoGetTopLevelIrp` at `0x1400095e5`
- `ntoskrnl!ExIsResourceAcquiredExclusiveLite` at `0x140008917`
- `ntoskrnl!ExIsResourceAcquiredExclusiveLite` at `0x140008b39`
- `ntoskrnl!ExIsResourceAcquiredExclusiveLite` at `0x140008917`
- `ntoskrnl!ExIsResourceAcquiredExclusiveLite` at `0x140008b39`

## pseudocode

```c
void __fastcall NtfsCleanupIrpContext(__int64 a1, unsigned int a2, __int64 a3)
{
  _QWORD *v3; // rax
  __int64 **v5; // r14
  _QWORD **v6; // r12
  __int64 v7; // r9
  int i; // eax
  unsigned int v9; // eax
  void *v10; // rcx
  __int64 v11; // rcx
  int v12; // eax
  __int64 v13; // rbp
  __int64 v14; // r8
  _QWORD *v15; // rax
  _QWORD *v16; // rdi
  _QWORD *v17; // rsi
  _QWORD *v18; // rbx
  _QWORD *v19; // rax
  __int64 v20; // rcx
  __int64 v21; // rdx
  _QWORD *v22; // rcx
  _QWORD *v23; // rax
  struct _ERESOURCE *v24; // rcx
  _QWORD *v25; // r14
  int v26; // r15d
  __int64 v27; // rcx
  __int64 v28; // r8
  _QWORD *v29; // rax
  _QWORD *v30; // rdi
  __int64 v31; // rbp
  _QWORD *v32; // rsi
  _QWORD *v33; // rbx
  _QWORD *v34; // rax
  __int64 v35; // rcx
  __int64 v36; // rdx
  _QWORD *v37; // rcx
  _QWORD *v38; // rax
  __int64 v39; // rcx
  struct _ERESOURCE *v40; // rcx
  void *v41; // rcx
  __int64 v42; // rsi
  __int64 j; // rdi
  __int64 v44; // rbx
  __int64 v45; // rcx
  __int64 *v46; // rax
  __int64 v47; // rdx
  __int64 *v48; // rbp
  __int64 **v49; // rcx
  _QWORD *v50; // rax
  _QWORD *v51; // rdi
  _QWORD *v52; // rsi
  _QWORD *v53; // rbx
  _QWORD *v54; // rax
  __int64 v55; // rcx
  __int64 v56; // rcx
  _QWORD *v57; // rcx
  _QWORD *v58; // rax
  _QWORD *v59; // rax
  _QWORD *v60; // rbx
  _QWORD *v61; // rsi
  _QWORD *v62; // rdi
  _QWORD *v63; // rax
  _DWORD *v64; // rcx
  __int64 v65; // rcx
  _QWORD *v66; // rcx
  _QWORD *v67; // rax
  int v68; // edx
  _QWORD *v69; // rcx
  __int64 v70; // rcx
  volatile signed __int32 *v71; // rcx
  int v72; // edx
  int v73; // eax
  void *v74; // rcx
  struct _SECURITY_SUBJECT_CONTEXT *v75; // rcx
  __int64 v76; // rdi
  _QWORD *v77; // rbx
  __int64 v78; // rcx
  void *v79; // rcx
  __int64 v80; // r8
  __int64 v81; // rax
  __int64 v82; // rdi
  __int64 v83; // rax
  _QWORD *v84; // rcx
  char v85; // si
  __int64 v86; // rbx
  KIRQL v87; // cl
  _QWORD *v88; // r8
  __int64 v89; // rcx
  PIRP TopLevelIrp; // rax
  bool v91; // zf
  IRP *MasterIrp; // rcx
  unsigned int v93; // ecx
  __int64 v94; // r9
  __int64 v95; // rax
  unsigned int v96; // eax
  __int64 v97; // rdx
  int v98; // eax
  _BYTE v99[4]; // [rsp+30h] [rbp-78h] BYREF
  unsigned int v100; // [rsp+34h] [rbp-74h]
  __int128 v101; // [rsp+38h] [rbp-70h] BYREF
  __int64 v102; // [rsp+48h] [rbp-60h]

  v100 = a2;
  v3 = (_QWORD *)(a1 + 168);
  v5 = (__int64 **)(a1 + 152);
  v6 = (_QWORD **)(a1 + 280);
  while ( 2 )
  {
    v99[0] = 0;
    if ( (_QWORD *)*v3 != v3 )
    {
      NtfsUpdateScbSnapshots(a1);
      NtfsDeallocateRecordsComplete(a1);
    }
    if ( *(_QWORD *)(a1 + 520) >= 2u )
      *(_QWORD *)(a1 + 520) = 0;
    *(_DWORD *)(a1 + 28) = 0;
    v7 = *(_QWORD *)(a1 + 192);
    if ( v7 )
    {
      NtfsReleaseDelayedAllocation(a1, 0, 0x7FFFFFFFFFFFFFFFLL);
      FsRtlUninitializeBaseMcb(*(PBASE_MCB *)(a1 + 192));
      FsRtlUninitializeBaseMcb((PBASE_MCB)(*(_QWORD *)(a1 + 192) + 40LL));
      ExFreeToLookasideListEx(&NtfsDelayedAllocationLookasideList, *(PVOID *)(a1 + 192));
      *(_QWORD *)(a1 + 192) = 0;
    }
    for ( i = *(_DWORD *)(a1 + 296); i; i = *(_DWORD *)(a1 + 296) )
    {
      v9 = i - 1;
      *(_DWORD *)(a1 + 296) = v9;
      v10 = *(void **)(a1 + 16LL * v9 + 312);
      if ( v10 )
      {
        CcUnpinData(v10);
        *(_QWORD *)(a1 + 16LL * *(unsigned int *)(a1 + 296) + 312) = 0;
      }
    }
    v11 = *(_QWORD *)(a1 + 104);
    if ( v11 && (*(_DWORD *)(a1 + 4) & 0x20000) != 0 )
    {
      ExReleaseResourceLite((PERESOURCE)(v11 + 10688));
      *(_DWORD *)(a1 + 4) &= ~0x20000u;
    }
    v12 = *(unsigned __int16 *)(a1 + 34);
    if ( !(_WORD)v12 )
      goto LABEL_100;
    if ( v12 != 1 )
    {
      v25 = *(_QWORD **)(a1 + 40);
      v26 = *(unsigned __int16 *)(a1 + 34);
      while ( 1 )
      {
        v27 = *v25;
        if ( *v25 )
          break;
LABEL_95:
        ++v25;
        if ( !--v26 )
        {
          v41 = *(void **)(a1 + 40);
          if ( *(_BYTE *)(a1 + 32) == 18 )
          {
            memset(v41, 0, 8LL * *(unsigned __int16 *)(a1 + 34));
          }
          else
          {
            ExFreePoolWithTag(v41, 0);
            *(_QWORD *)(a1 + 40) = 0;
            *(_WORD *)(a1 + 34) = 0;
          }
          v5 = (__int64 **)(a1 + 152);
          goto LABEL_100;
        }
      }
      if ( *(_WORD *)v27 == 1805 )
      {
        NtfsReleaseQuotaControl(a1, *v25);
LABEL_94:
        *v25 = 0;
        goto LABEL_95;
      }
      if ( !ExIsResourceAcquiredExclusiveLite((PERESOURCE)(*(_QWORD *)(v27 + 104) + 64LL)) )
        goto LABEL_89;
      if ( ExIsResourceAcquiredSharedLite((PERESOURCE)(*(_QWORD *)(*v25 + 104LL) + 64LL)) != 1 )
        goto LABEL_89;
      v29 = *v6;
      if ( *v6 == v6 )
        goto LABEL_89;
      while ( 1 )
      {
        v30 = v29 - 1;
        if ( *((_WORD *)v29 - 4) == 1831 )
          break;
        v29 = (_QWORD *)*v29;
        if ( v29 == v6 )
          goto LABEL_89;
      }
      v31 = *v25;
      if ( v29 == (_QWORD *)8 )
      {
LABEL_89:
        v39 = *v25;
        if ( *(_WORD *)*v25 == 1794 )
          v40 = (struct _ERESOURCE *)(*(_QWORD *)(v39 + 104) + 64LL);
        else
          v40 = *(struct _ERESOURCE **)(v39 + 8);
        ExReleaseResourceLite(v40);
        goto LABEL_94;
      }
      while ( 1 )
      {
        v32 = 0;
        v33 = v30 + 1;
        if ( *v6 != v6 )
        {
          v34 = (_QWORD *)*v33;
          if ( (_QWORD **)*v33 != v6 )
          {
            while ( *((_WORD *)v34 - 4) != 1831 )
            {
              v34 = (_QWORD *)*v34;
              if ( v34 == v6 )
                goto LABEL_72;
            }
            v32 = v34 - 1;
          }
        }
LABEL_72:
        v35 = v30[10];
        if ( !v35 )
          goto LABEL_84;
        if ( !v31 || *(_QWORD *)(v35 + 184) == v31 )
          break;
LABEL_88:
        v30 = v32;
        if ( !v32 )
          goto LABEL_89;
      }
      if ( (*(_DWORD *)(v35 + 200) & 0x2000) != 0 || (*(_DWORD *)(v35 + 512) & 0x4040) != 0 )
      {
        if ( *(_DWORD *)(v35 + 256) == 256 && (*(_DWORD *)(v35 + 512) & 0x40) != 0 )
          *(_DWORD *)(v35 + 256) = 0;
        v36 = v30[10];
        if ( (*(_DWORD *)(v36 + 200) & 0x2000) != 0 || (*(_DWORD *)(v36 + 512) & 0x4000) != 0 )
        {
          ClearFlagInterlocked(v36 + 200, 0x2000);
          *(_DWORD *)(v30[10] + 512LL) &= ~0x4000u;
        }
      }
      FsRtlAcquireHeaderMutex(v30[10] + 120LL, v30[10] + 160LL, v28);
      *(_QWORD *)(v30[10] + 496LL) = 0;
      FsRtlReleaseHeaderMutex(v30[10] + 120LL, v30[10] + 160LL);
LABEL_84:
      v37 = (_QWORD *)*v33;
      if ( *(_QWORD **)(*v33 + 8LL) != v33 || (v38 = (_QWORD *)v30[2], (_QWORD *)*v38 != v33) )
        __fastfail(3u);
      *v38 = v37;
      v37[1] = v38;
      if ( v30 != (_QWORD *)(a1 + 552) )
        ExFreeToLookasideListEx(&NtfsScbSnapshotLookasideList, v30);
      goto LABEL_88;
    }
    v13 = *(_QWORD *)(a1 + 40);
    if ( v13 )
    {
      if ( *(_WORD *)v13 == 1805 )
      {
        NtfsReleaseQuotaControl(a1, *(_QWORD *)(a1 + 40));
        *(_QWORD *)(a1 + 40) = 0;
        *(_WORD *)(a1 + 34) = 0;
        goto LABEL_100;
      }
      if ( ExIsResourceAcquiredExclusiveLite((PERESOURCE)(*(_QWORD *)(v13 + 104) + 64LL)) )
      {
        if ( ExIsResourceAcquiredSharedLite((PERESOURCE)(*(_QWORD *)(v13 + 104) + 64LL)) == 1 )
        {
          v15 = *v6;
          if ( *v6 != v6 )
          {
            while ( 1 )
            {
              v16 = v15 - 1;
              if ( *((_WORD *)v15 - 4) == 1831 )
                break;
              v15 = (_QWORD *)*v15;
              if ( v15 == v6 )
                goto LABEL_49;
            }
            if ( v15 != (_QWORD *)8 )
            {
              while ( 1 )
              {
                v17 = 0;
                v18 = v16 + 1;
                if ( *v6 != v6 )
                {
                  v19 = (_QWORD *)*v18;
                  if ( (_QWORD **)*v18 != v6 )
                  {
                    while ( *((_WORD *)v19 - 4) != 1831 )
                    {
                      v19 = (_QWORD *)*v19;
                      if ( v19 == v6 )
                        goto LABEL_33;
                    }
                    v17 = v19 - 1;
                  }
                }
LABEL_33:
                v20 = v16[10];
                if ( !v20 )
                  goto LABEL_44;
                if ( *(_QWORD *)(v20 + 184) == v13 )
                  break;
LABEL_48:
                v16 = v17;
                if ( !v17 )
                  goto LABEL_49;
              }
              if ( (*(_DWORD *)(v20 + 200) & 0x2000) != 0 || (*(_DWORD *)(v20 + 512) & 0x4040) != 0 )
              {
                if ( *(_DWORD *)(v20 + 256) == 256 && (*(_DWORD *)(v20 + 512) & 0x40) != 0 )
                  *(_DWORD *)(v20 + 256) = 0;
                v21 = v16[10];
                if ( (*(_DWORD *)(v21 + 200) & 0x2000) != 0 || (*(_DWORD *)(v21 + 512) & 0x4000) != 0 )
                {
                  ClearFlagInterlocked(v21 + 200, 0x2000);
                  *(_DWORD *)(v16[10] + 512LL) &= ~0x4000u;
                }
              }
              FsRtlAcquireHeaderMutex(v16[10] + 120LL, v16[10] + 160LL, v14);
              *(_QWORD *)(v16[10] + 496LL) = 0;
              FsRtlReleaseHeaderMutex(v16[10] + 120LL, v16[10] + 160LL);
LABEL_44:
              v22 = (_QWORD *)*v18;
              if ( *(_QWORD **)(*v18 + 8LL) != v18 || (v23 = (_QWORD *)v16[2], (_QWORD *)*v23 != v18) )
                __fastfail(3u);
              *v23 = v22;
              v22[1] = v23;
              if ( v16 != (_QWORD *)(a1 + 552) )
                ExFreeToLookasideListEx(&NtfsScbSnapshotLookasideList, v16);
              goto LABEL_48;
            }
          }
        }
      }
LABEL_49:
      if ( *(_WORD *)v13 == 1794 )
        v24 = (struct _ERESOURCE *)(*(_QWORD *)(v13 + 104) + 64LL);
      else
        v24 = *(struct _ERESOURCE **)(v13 + 8);
      ExReleaseResourceLite(v24);
    }
    *(_QWORD *)(a1 + 40) = 0;
    *(_WORD *)(a1 + 34) = 0;
LABEL_100:
    v42 = *(_QWORD *)(a1 + 64);
    for ( j = 0; j != 2; ++j )
    {
      v44 = *(_QWORD *)(a1 + 8 * j + 48);
      if ( v44 )
      {
        v45 = *(_QWORD *)(a1 + 8 * j + 48);
        if ( *(_WORD *)v44 != 1794 )
          v45 = *(_QWORD *)(v44 + 184);
        ExReleaseResourceLite(*(PERESOURCE *)(v45 + 112));
        if ( *(_QWORD *)(a1 + 48) == v44 )
          *(_QWORD *)(a1 + 48) = 0;
        if ( *(_QWORD *)(a1 + 56) == v44 )
          *(_QWORD *)(a1 + 56) = 0;
      }
    }
    if ( v42 )
    {
      *(_QWORD *)(a1 + 64) = 0;
      FsRtlReleaseEofLock(v42 + 120, v42 + 160);
      *(_QWORD *)(a1 + 64) = 0;
    }
    if ( *(_QWORD *)(a1 + 80) )
    {
      NtfsReleaseRangeInternal(a1 + 72);
      *(_QWORD *)(a1 + 80) = 0;
    }
    *(_DWORD *)(a1 + 4) &= ~0x2000u;
    while ( 1 )
    {
      v46 = *v5;
      if ( *v5 == (__int64 *)v5 )
        break;
      v47 = *v46;
      v48 = v46 - 10;
      if ( *v46 )
      {
        if ( *((_WORD *)v48 + 16) != 1 )
          goto LABEL_152;
        if ( !*(_DWORD *)(a1 + 28) )
        {
          if ( *(__int64 **)(v47 + 8) != v46 || (v49 = (__int64 **)v46[1], *v49 != v46) )
            __fastfail(3u);
          *v49 = (__int64 *)v47;
          *(_QWORD *)(v47 + 8) = v49;
          *v46 = 0;
          v50 = *v6;
          if ( *v6 != v6 )
          {
            while ( 1 )
            {
              v51 = v50 - 1;
              if ( *((_WORD *)v50 - 4) == 1831 )
                break;
              v50 = (_QWORD *)*v50;
              if ( v50 == v6 )
                goto LABEL_150;
            }
            if ( v50 != (_QWORD *)8 )
            {
              while ( 1 )
              {
                v52 = 0;
                v53 = v51 + 1;
                if ( *v6 != v6 )
                {
                  v54 = (_QWORD *)*v53;
                  if ( (_QWORD **)*v53 != v6 )
                  {
                    while ( *((_WORD *)v54 - 4) != 1831 )
                    {
                      v54 = (_QWORD *)*v54;
                      if ( v54 == v6 )
                        goto LABEL_132;
                    }
                    v52 = v54 - 1;
                  }
                }
LABEL_132:
                v55 = v51[10];
                if ( !v55 )
                  goto LABEL_145;
                if ( *(__int64 **)(v55 + 184) == v48 )
                  break;
LABEL_149:
                v51 = v52;
                if ( !v52 )
                  goto LABEL_150;
              }
              if ( (*(_DWORD *)(v55 + 200) & 0x2000) != 0 || (*(_DWORD *)(v55 + 512) & 0x4040) != 0 )
              {
                if ( *(_DWORD *)(v55 + 256) == 256 && (*(_DWORD *)(v55 + 512) & 0x40) != 0 )
                  *(_DWORD *)(v55 + 256) = 0;
                v56 = v51[10];
                if ( (*(_DWORD *)(v56 + 200) & 0x2000) != 0 || (*(_DWORD *)(v56 + 512) & 0x4000) != 0 )
                {
                  if ( (*(_DWORD *)(v56 + 200) & 0x2000) != 0 )
                    _InterlockedAnd((volatile signed __int32 *)(v56 + 200), 0xFFFFDFFF);
                  *(_DWORD *)(v51[10] + 512LL) &= ~0x4000u;
                }
              }
              FsRtlAcquireHeaderMutex(v51[10] + 120LL, v51[10] + 160LL, a3);
              *(_QWORD *)(v51[10] + 496LL) = 0;
              FsRtlReleaseHeaderMutex(v51[10] + 120LL, v51[10] + 160LL);
LABEL_145:
              v57 = (_QWORD *)*v53;
              if ( *(_QWORD **)(*v53 + 8LL) != v53 || (v58 = (_QWORD *)v51[2], (_QWORD *)*v58 != v53) )
                __fastfail(3u);
              *v58 = v57;
              v57[1] = v58;
              if ( v51 != (_QWORD *)(a1 + 552) )
                ExFreeToLookasideListEx(&NtfsScbSnapshotLookasideList, v51);
              goto LABEL_149;
            }
          }
LABEL_150:
          if ( *((int *)v48 + 44) < 0 )
            *(_DWORD *)(a1 + 436) &= ~0x8000u;
LABEL_152:
          --*((_WORD *)v48 + 16);
          goto LABEL_153;
        }
      }
      else
      {
LABEL_153:
        if ( *(_WORD *)v48 == 1794 )
          ExReleaseResourceLite((PERESOURCE)(v48[13] + 64));
        else
          ExReleaseResourceLite((PERESOURCE)v48[1]);
      }
    }
    v59 = *v6;
    if ( *v6 != v6 )
    {
      while ( 1 )
      {
        v60 = v59 - 1;
        if ( *((_WORD *)v59 - 4) == 1831 )
          break;
        v59 = (_QWORD *)*v59;
        if ( v59 == v6 )
          goto LABEL_185;
      }
      if ( v59 != (_QWORD *)8 )
      {
        do
        {
          v61 = 0;
          v62 = v60 + 1;
          if ( *v6 != v6 )
          {
            v63 = (_QWORD *)*v62;
            if ( (_QWORD **)*v62 != v6 )
            {
              while ( *((_WORD *)v63 - 4) != 1831 )
              {
                v63 = (_QWORD *)*v63;
                if ( v63 == v6 )
                  goto LABEL_168;
              }
              v61 = v63 - 1;
            }
          }
LABEL_168:
          v64 = (_DWORD *)v60[10];
          if ( v64 )
          {
            if ( (v64[50] & 0x2000) != 0 || (v64[128] & 0x4040) != 0 )
            {
              if ( v64[64] == 256 && (v64[128] & 0x40) != 0 )
                v64[64] = 0;
              v65 = v60[10];
              if ( (*(_DWORD *)(v65 + 200) & 0x2000) != 0 || (*(_DWORD *)(v65 + 512) & 0x4000) != 0 )
              {
                if ( (*(_DWORD *)(v65 + 200) & 0x2000) != 0 )
                  _InterlockedAnd((volatile signed __int32 *)(v65 + 200), 0xFFFFDFFF);
                *(_DWORD *)(v60[10] + 512LL) &= ~0x4000u;
              }
            }
            FsRtlAcquireHeaderMutex(v60[10] + 120LL, v60[10] + 160LL, a3);
            *(_QWORD *)(v60[10] + 496LL) = 0;
            FsRtlReleaseHeaderMutex(v60[10] + 120LL, v60[10] + 160LL);
          }
          v66 = (_QWORD *)*v62;
          if ( *(_QWORD **)(*v62 + 8LL) != v62 || (v67 = (_QWORD *)v60[2], (_QWORD *)*v67 != v62) )
            __fastfail(3u);
          *v67 = v66;
          v66[1] = v67;
          if ( v60 != (_QWORD *)(a1 + 552) )
            ExFreeToLookasideListEx(&NtfsScbSnapshotLookasideList, v60);
          v60 = v61;
        }
        while ( v61 );
      }
    }
LABEL_185:
    v68 = *(_DWORD *)(a1 + 4);
    if ( (v68 & 0x400) == 0 )
    {
      v69 = *(_QWORD **)(a1 + 232);
      if ( v69 )
      {
        do
        {
          *(_QWORD *)(a1 + 232) = *v69;
          ExFreePoolWithTag(v69, 0);
          v69 = *(_QWORD **)(a1 + 232);
        }
        while ( v69 );
        v68 = *(_DWORD *)(a1 + 4);
      }
    }
    if ( (*(_DWORD *)(a1 + 376) & 1) != 0 || (*(_DWORD *)(a1 + 16) & 0x3000LL) != 0 )
    {
      NtfsProcessAttachedCorruptions(a1, v99);
      v68 = *(_DWORD *)(a1 + 4);
      if ( v99[0] )
      {
        v3 = (_QWORD *)(a1 + 168);
        continue;
      }
    }
    break;
  }
  if ( *(_QWORD *)(a1 + 384) )
  {
    if ( (v68 & 0x400) == 0 )
    {
      if ( IoGetTopLevelIrp() )
      {
        if ( (unsigned __int8)NtfsRepairIsTopLevelRequest(a1) )
        {
          v70 = *(_QWORD *)(a1 + 384);
          if ( (v70 & 2) != 0 )
          {
            v71 = (volatile signed __int32 *)(v70 & 0xFFFFFFFFFFFFFFFCuLL);
            if ( !_InterlockedCompareExchange(v71 + 5, 0, 1) )
              NtfsFreeRepairItem((PVOID)v71);
            *(_QWORD *)(a1 + 384) = 0;
          }
        }
      }
    }
  }
  v72 = *(_DWORD *)(a1 + 4);
  if ( (v72 & 0x400) != 0 || (v73 = *(_DWORD *)(a1 + 12), (v73 & 0x10000) != 0) )
  {
    *(_DWORD *)(a1 + 436) = *(_DWORD *)(a1 + 432) | *(_DWORD *)(a1 + 436) & 0xFFFDBF49;
    if ( (v72 & 0x40000) != 0 )
    {
      v97 = v72 & 0xFFFBFBFF;
    }
    else
    {
      a3 = v100;
      v96 = v72 & 0xDE6B4000;
      v97 = v72 & 0xDE6B4008;
      v7 = 4294967292LL;
      if ( v100 )
        v97 = v96;
      v98 = -2;
      if ( !v100 )
        v98 = -4;
      *(_DWORD *)(a1 + 8) &= v98;
    }
    *(_DWORD *)(a1 + 4) = v97;
    *(_QWORD *)(a1 + 16) &= ~4uLL;
    NtfsMarkUnusedContextPreTrimProcessing(a1, v97, a3, v7);
    *(_QWORD *)(a1 + 184) = 0;
    *(_DWORD *)(a1 + 24) = 0;
  }
  else
  {
    v74 = *(void **)(a1 + 488);
    if ( v74 )
    {
      ExFreePoolWithTag(v74, 0);
      v73 = *(_DWORD *)(a1 + 12);
      *(_QWORD *)(a1 + 488) = 0;
    }
    v75 = *(struct _SECURITY_SUBJECT_CONTEXT **)(a1 + 208);
    if ( v75 )
    {
      if ( (v73 & 0x80000010) != 0 )
      {
        if ( ((__int64)v75->ClientToken & 0x1000) != 0 )
          ExReleaseRundownProtection((PEX_RUNDOWN_REF)(*(_QWORD *)(*(_QWORD *)(a1 + 104) + 11784LL) + 32LL));
        v76 = *(_QWORD *)(a1 + 208);
        v77 = *(_QWORD **)(v76 + 32);
        if ( v77 )
        {
          v78 = *v77;
          if ( *v77 )
          {
            if ( (*(_BYTE *)(v78 + 10) & 1) != 0 )
            {
              *(_QWORD *)(v78 + 32) = v77[1];
              MmUnmapLockedPages(*(PVOID *)(*v77 + 24LL), (PMDL)*v77);
            }
            IoFreeMdl((PMDL)*v77);
            *v77 = 0;
          }
          v79 = (void *)v77[1];
          if ( v79 )
          {
            ExFreePoolWithTag(v79, 0);
            v77[1] = 0;
          }
          ExFreeToLookasideListEx(&NtfsAlignedMdlContextLookasideList, v77);
          *(_QWORD *)(v76 + 32) = 0;
        }
        if ( (*(_DWORD *)(a1 + 12) & 0x10) != 0 )
        {
          v80 = *(_QWORD *)(a1 + 208);
          v81 = *(unsigned int *)(v80 - 8);
          if ( (unsigned int)v81 >= NtfsNumberProcessors )
            v81 = (unsigned int)v81 % NtfsNumberProcessors;
          ExFreeToLookasideListEx((PLOOKASIDE_LIST_EX)(NtfsIoContextLookasideList + 96 * v81), (PVOID)(v80 - 8));
        }
        *(_DWORD *)(a1 + 12) &= 0x7FFFFFEFu;
      }
      else if ( (v73 & 0x20) != 0 )
      {
        SeReleaseSubjectContext(v75);
        ExFreePoolWithTag(*(PVOID *)(a1 + 208), 0);
        *(_DWORD *)(a1 + 12) &= ~0x20u;
      }
      *(_QWORD *)(a1 + 208) = 0;
    }
    v82 = a1 + 464;
    v102 = 0;
    v83 = *(_QWORD *)(a1 + 464);
    v101 = 0;
    if ( v83 != a1 + 464 )
    {
      v84 = *(_QWORD **)(v83 + 48);
      v85 = 0;
      v86 = *(_QWORD *)(v83 + 16);
      if ( v84 )
      {
        *((_QWORD *)&v101 + 1) = *v84;
        v102 = v84[1];
        *(_QWORD *)&v101 = (char *)&v101 + 8;
      }
      else
      {
        *(_QWORD *)&v101 = 0;
      }
      if ( (*(_DWORD *)(a1 + 16) & 0x100000) == 0
        && (Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits & 0x200000) != 0 )
      {
        McTemplateU0pp_EtwWriteTransfer(v84, delnotify_c1457, v86, a1);
      }
      v87 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v86 + 1752));
      if ( !*(_BYTE *)(v86 + 1808) )
      {
        v85 = 1;
        *(_BYTE *)(v86 + 1808) = 1;
      }
      v88 = *(_QWORD **)(v86 + 1768);
      *v88 = *(_QWORD *)v82;
      *(_QWORD *)(v86 + 1768) = *(_QWORD *)(a1 + 472);
      **(_QWORD **)(a1 + 472) = v86 + 1760;
      *(_QWORD *)(*(_QWORD *)v82 + 8LL) = v88;
      KeReleaseSpinLock((PKSPIN_LOCK)(v86 + 1752), v87);
      *(_QWORD *)(a1 + 472) = a1 + 464;
      *(_QWORD *)v82 = v82;
      if ( (Microsoft_Windows_NtfsEnableBits & 0x8000000) != 0 )
        McTemplateK0pq_EtwWriteTransfer(v89, WORKITEM_QUEUE, v101);
      if ( v85 )
      {
        if ( (*(_DWORD *)(a1 + 16) & 0x100000) == 0
          && (Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits & 0x40) != 0 )
        {
          McTemplateU0p_EtwWriteTransfer(v89, delnotify_c1503, v86);
        }
        ExQueueWorkItem((PWORK_QUEUE_ITEM)(v86 + 1776), DelayedWorkQueue);
      }
      if ( (*(_DWORD *)(a1 + 16) & 0x100000LL) == 0
        && (Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits & 0x200000) != 0 )
      {
        McTemplateU0p_EtwWriteTransfer(v89, delnotify_c1512, v86);
      }
    }
    if ( (*(_DWORD *)(a1 + 12) & 0x100000) != 0 )
    {
      TopLevelIrp = IoGetTopLevelIrp();
      v91 = LOBYTE(TopLevelIrp->Size) == 0;
      TopLevelIrp->ThreadListEntry.Flink = 0;
      if ( v91 )
      {
        MasterIrp = TopLevelIrp->AssociatedIrp.MasterIrp;
        *(_DWORD *)(&TopLevelIrp->Size + 1) = 0;
        IoSetTopLevelIrp(MasterIrp);
      }
      *(_DWORD *)(a1 + 12) &= ~0x100000u;
    }
    if ( *(_QWORD *)(a1 + 480) )
      NtfsUninitializeIrpContextExtension(a1);
    if ( (*(_DWORD *)(a1 + 12) & 0x80000) != 0 )
    {
      v93 = NtfsNumberProcessors;
      v94 = NtfsIrpContextLookasideList;
      *(_QWORD *)(a1 + 496) = 22;
      v95 = *(unsigned int *)(a1 - 8);
      if ( (unsigned int)v95 >= v93 )
        v95 = (unsigned int)v95 % v93;
      ExFreeToLookasideListEx((PLOOKASIDE_LIST_EX)(v94 + 96 * v95), (PVOID)(a1 - 8));
    }
  }
}

```

## disassembly

```asm
0x140008740  push    rbx
0x140008742  push    rbp
0x140008743  push    rsi
0x140008744  push    rdi
0x140008745  push    r12
0x140008747  push    r13
0x140008749  push    r14
0x14000874b  push    r15
0x14000874d  sub     rsp, 68h
0x140008751  mov     rax, cs:__security_cookie
0x140008758  xor     rax, rsp
0x14000875b  mov     [rsp+0A8h+var_58], rax
0x140008760  mov     [rsp+0A8h+var_74], edx
0x140008764  lea     rax, [rcx+0A8h]
0x14000876b  mov     r13, rcx
0x14000876e  lea     r14, [rcx+98h]
0x140008775  lea     r12, [rcx+118h]
0x14000877c  mov     r15d, 727h
0x140008782  mov     ebx, 70Dh
0x140008787  mov     rcx, 7FFFFFFFFFFFFFFFh
0x140008791  mov     [rsp+0A8h+var_78], 0
0x140008796  cmp     [rax], rax
0x140008799  jz      short loc_1400087B5
0x14000879b  mov     rcx, r13
0x14000879e  call    NtfsUpdateScbSnapshots
0x1400087a3  mov     rcx, r13
0x1400087a6  call    NtfsDeallocateRecordsComplete
0x1400087ab  mov     rcx, 7FFFFFFFFFFFFFFFh
0x1400087b5  cmp     qword ptr [r13+208h], 2
0x1400087bd  jb      short loc_1400087CA
0x1400087bf  mov     qword ptr [r13+208h], 0
0x1400087ca  mov     dword ptr [r13+1Ch], 0
0x1400087d2  mov     r9, [r13+0C0h]
0x1400087d9  test    r9, r9
0x1400087dc  jz      short loc_14000883A
0x1400087de  mov     r8, rcx
0x1400087e1  xor     edx, edx
0x1400087e3  mov     rcx, r13
0x1400087e6  call    NtfsReleaseDelayedAllocation
0x1400087eb  mov     rcx, [r13+0C0h]; Mcb
0x1400087f2  call    cs:__imp_FsRtlUninitializeBaseMcb
0x1400087f9  nop     dword ptr [rax+rax+00h]
0x1400087fe  mov     rcx, [r13+0C0h]
0x140008805  add     rcx, 28h ; '('; Mcb
0x140008809  call    cs:__imp_FsRtlUninitializeBaseMcb
0x140008810  nop     dword ptr [rax+rax+00h]
0x140008815  mov     rdx, [r13+0C0h]; Entry
0x14000881c  lea     rcx, NtfsDelayedAllocationLookasideList; Lookaside
0x140008823  call    cs:__imp_ExFreeToLookasideListEx
0x14000882a  nop     dword ptr [rax+rax+00h]
0x14000882f  mov     qword ptr [r13+0C0h], 0
0x14000883a  mov     eax, [r13+128h]
0x140008841  test    eax, eax
0x140008843  jz      short loc_140008898
0x140008845  nop     word ptr [rax+rax+00000000h]
0x140008850  dec     eax
0x140008852  mov     ecx, eax
0x140008854  add     rcx, rcx
0x140008857  mov     [r13+128h], eax
0x14000885e  mov     rcx, [r13+rcx*8+138h]; Bcb
0x140008866  test    rcx, rcx
0x140008869  jz      short loc_14000888D
0x14000886b  call    cs:__imp_CcUnpinData
0x140008872  nop     dword ptr [rax+rax+00h]
0x140008877  mov     eax, [r13+128h]
0x14000887e  add     rax, rax
0x140008881  mov     qword ptr [r13+rax*8+138h], 0
0x14000888d  mov     eax, [r13+128h]
0x140008894  test    eax, eax
0x140008896  jnz     short loc_140008850
0x140008898  mov     rcx, [r13+68h]
0x14000889c  test    rcx, rcx
0x14000889f  jz      short loc_1400088C6
0x1400088a1  test    dword ptr [r13+4], 20000h
0x1400088a9  jz      short loc_1400088C6
0x1400088ab  add     rcx, 29C0h; Resource
0x1400088b2  call    cs:__imp_ExReleaseResourceLite
0x1400088b9  nop     dword ptr [rax+rax+00h]
0x1400088be  and     dword ptr [r13+4], 0FFFDFFFFh
0x1400088c6  movzx   eax, word ptr [r13+22h]
0x1400088cb  test    ax, ax
0x1400088ce  jz      loc_140008D7B
0x1400088d4  cmp     eax, 1
0x1400088d7  jnz     loc_140008B08
0x1400088dd  mov     rbp, [r13+28h]
0x1400088e1  test    rbp, rbp
0x1400088e4  jz      loc_140008AF4
0x1400088ea  cmp     [rbp+0], bx
0x1400088ee  jnz     short loc_14000890F
0x1400088f0  mov     rdx, rbp
0x1400088f3  mov     rcx, r13
0x1400088f6  call    NtfsReleaseQuotaControl
0x1400088fb  xor     eax, eax
0x1400088fd  mov     qword ptr [r13+28h], 0
0x140008905  mov     [r13+22h], ax
0x14000890a  jmp     loc_140008D7B
0x14000890f  mov     rcx, [rbp+68h]
0x140008913  add     rcx, 40h ; '@'; Resource
0x140008917  call    cs:__imp_ExIsResourceAcquiredExclusiveLite
0x14000891e  nop     dword ptr [rax+rax+00h]
0x140008923  test    al, al
0x140008925  jz      loc_140008AC8
0x14000892b  mov     rcx, [rbp+68h]
0x14000892f  add     rcx, 40h ; '@'; Resource
0x140008933  call    cs:__imp_ExIsResourceAcquiredSharedLite
0x14000893a  nop     dword ptr [rax+rax+00h]
0x14000893f  cmp     eax, 1
0x140008942  jnz     loc_140008AC8
0x140008948  mov     rax, [r12]
0x14000894c  cmp     rax, r12
0x14000894f  jz      loc_140008AC8
0x140008955  cmp     [rax-8], r15w
0x14000895a  lea     rdi, [rax-8]
0x14000895e  jz      short loc_14000896D
0x140008960  mov     rax, [rax]
0x140008963  cmp     rax, r12
0x140008966  jnz     short loc_140008955
0x140008968  jmp     loc_140008AC8
0x14000896d  test    rdi, rdi
0x140008970  jz      loc_140008AC8
0x140008976  nop     word ptr [rax+rax+00000000h]
0x140008980  xor     esi, esi
0x140008982  lea     rbx, [rdi+8]
0x140008986  cmp     [r12], r12
0x14000898a  jz      short loc_1400089A9
0x14000898c  mov     rax, [rbx]
0x14000898f  cmp     rax, r12
0x140008992  jz      short loc_1400089A9
0x140008994  cmp     [rax-8], r15w
0x140008999  jz      short loc_1400089A5
0x14000899b  mov     rax, [rax]
0x14000899e  cmp     rax, r12
0x1400089a1  jnz     short loc_140008994
0x1400089a3  jmp     short loc_1400089A9
0x1400089a5  lea     rsi, [rax-8]
0x1400089a9  mov     rcx, [rdi+50h]
0x1400089ad  test    rcx, rcx
0x1400089b0  jz      loc_140008A81
0x1400089b6  cmp     [rcx+0B8h], rbp
0x1400089bd  jnz     loc_140008ABC
0x1400089c3  test    dword ptr [rcx+0C8h], 2000h
0x1400089cd  jnz     short loc_1400089DB
0x1400089cf  test    dword ptr [rcx+200h], 4040h
0x1400089d9  jz      short loc_140008A3C
0x1400089db  cmp     dword ptr [rcx+100h], 100h
0x1400089e5  jnz     short loc_1400089FB
0x1400089e7  mov     eax, [rcx+200h]
0x1400089ed  test    al, 40h
0x1400089ef  jz      short loc_1400089FB
0x1400089f1  mov     dword ptr [rcx+100h], 0
0x1400089fb  mov     rdx, [rdi+50h]
0x1400089ff  lea     rcx, [rdx+0C8h]
0x140008a06  test    dword ptr [rcx], 2000h
0x140008a0c  jnz     short loc_140008A1A
0x140008a0e  test    dword ptr [rdx+200h], 4000h
0x140008a18  jz      short loc_140008A3C
0x140008a1a  mov     edx, 2000h
0x140008a1f  call    ClearFlagInterlocked
0x140008a24  mov     rcx, [rdi+50h]
0x140008a28  mov     edx, [rcx+200h]
0x140008a2e  mov     rax, [rdi+50h]
0x140008a32  btr     edx, 0Eh
0x140008a36  mov     [rax+200h], edx
0x140008a3c  mov     rcx, [rdi+50h]
0x140008a40  lea     rdx, [rcx+0A0h]
0x140008a47  add     rcx, 78h ; 'x'
0x140008a4b  call    cs:__imp_FsRtlAcquireHeaderMutex
0x140008a52  nop     dword ptr [rax+rax+00h]
0x140008a57  mov     rax, [rdi+50h]
0x140008a5b  mov     qword ptr [rax+1F0h], 0
0x140008a66  mov     rcx, [rdi+50h]
0x140008a6a  lea     rdx, [rcx+0A0h]
0x140008a71  add     rcx, 78h ; 'x'
0x140008a75  call    cs:__imp_FsRtlReleaseHeaderMutex
0x140008a7c  nop     dword ptr [rax+rax+00h]
0x140008a81  mov     rcx, [rbx]
0x140008a84  cmp     [rcx+8], rbx
0x140008a88  jnz     short loc_140008ADD
0x140008a8a  mov     rax, [rbx+8]
0x140008a8e  cmp     [rax], rbx
0x140008a91  jnz     short loc_140008ADD
0x140008a93  mov     [rax], rcx
0x140008a96  mov     [rcx+8], rax
0x140008a9a  lea     rax, [r13+228h]
0x140008aa1  cmp     rdi, rax
0x140008aa4  jz      short loc_140008ABC
0x140008aa6  mov     rdx, rdi; Entry
0x140008aa9  lea     rcx, NtfsScbSnapshotLookasideList; Lookaside
0x140008ab0  call    cs:__imp_ExFreeToLookasideListEx
0x140008ab7  nop     dword ptr [rax+rax+00h]
0x140008abc  mov     rdi, rsi
0x140008abf  test    rsi, rsi
0x140008ac2  jnz     loc_140008980
0x140008ac8  mov     eax, 702h
0x140008acd  cmp     ax, [rbp+0]
0x140008ad1  jnz     short loc_140008AE4
0x140008ad3  mov     rcx, [rbp+68h]
0x140008ad7  add     rcx, 40h ; '@'
0x140008adb  jmp     short loc_140008AE8
0x140008add  mov     ecx, 3
0x140008ae2  int     29h; Win8: RtlFailFast(ecx)
0x140008ae4  mov     rcx, [rbp+8]; Resource
0x140008ae8  call    cs:__imp_ExReleaseResourceLite
0x140008aef  nop     dword ptr [rax+rax+00h]
0x140008af4  xor     eax, eax
0x140008af6  mov     qword ptr [r13+28h], 0
0x140008afe  mov     [r13+22h], ax
0x140008b03  jmp     loc_140008D7B
0x140008b08  mov     r14, [r13+28h]
0x140008b0c  mov     r15d, eax
0x140008b0f  nop
0x140008b10  mov     rcx, [r14]
0x140008b13  test    rcx, rcx
0x140008b16  jz      loc_140008D2E
0x140008b1c  cmp     [rcx], bx
0x140008b1f  jnz     short loc_140008B31
0x140008b21  mov     rdx, rcx
0x140008b24  mov     rcx, r13
0x140008b27  call    NtfsReleaseQuotaControl
0x140008b2c  jmp     loc_140008D27
0x140008b31  mov     rcx, [rcx+68h]
0x140008b35  add     rcx, 40h ; '@'; Resource
0x140008b39  call    cs:__imp_ExIsResourceAcquiredExclusiveLite
0x140008b40  nop     dword ptr [rax+rax+00h]
0x140008b45  test    al, al
0x140008b47  jz      loc_140008CF9
0x140008b4d  mov     rax, [r14]
0x140008b50  mov     rcx, [rax+68h]
0x140008b54  add     rcx, 40h ; '@'; Resource
0x140008b58  call    cs:__imp_ExIsResourceAcquiredSharedLite
0x140008b5f  nop     dword ptr [rax+rax+00h]
0x140008b64  cmp     eax, 1
0x140008b67  jnz     loc_140008CF9
0x140008b6d  mov     rax, [r12]
0x140008b71  cmp     rax, r12
0x140008b74  jz      loc_140008CF9
0x140008b7a  mov     edx, 727h
0x140008b7f  nop
0x140008b80  cmp     [rax-8], dx
0x140008b84  lea     rdi, [rax-8]
0x140008b88  jz      short loc_140008B97
0x140008b8a  mov     rax, [rax]
0x140008b8d  cmp     rax, r12
0x140008b90  jnz     short loc_140008B80
0x140008b92  jmp     loc_140008CF9
0x140008b97  mov     rbp, [r14]
0x140008b9a  test    rdi, rdi
0x140008b9d  jz      loc_140008CF9
0x140008ba3  xor     esi, esi
0x140008ba5  lea     rbx, [rdi+8]
0x140008ba9  cmp     [r12], r12
0x140008bad  jz      short loc_140008BCB
0x140008baf  mov     rax, [rbx]
0x140008bb2  cmp     rax, r12
0x140008bb5  jz      short loc_140008BCB
0x140008bb7  cmp     [rax-8], dx
0x140008bbb  jz      short loc_140008BC7
0x140008bbd  mov     rax, [rax]
0x140008bc0  cmp     rax, r12
0x140008bc3  jnz     short loc_140008BB7
0x140008bc5  jmp     short loc_140008BCB
0x140008bc7  lea     rsi, [rax-8]
0x140008bcb  mov     rcx, [rdi+50h]
0x140008bcf  test    rcx, rcx
0x140008bd2  jz      loc_140008CA8
0x140008bd8  test    rbp, rbp
0x140008bdb  jz      short loc_140008BEA
0x140008bdd  cmp     [rcx+0B8h], rbp
0x140008be4  jnz     loc_140008CE3
0x140008bea  test    dword ptr [rcx+0C8h], 2000h
0x140008bf4  jnz     short loc_140008C02
0x140008bf6  test    dword ptr [rcx+200h], 4040h
0x140008c00  jz      short loc_140008C63
0x140008c02  cmp     dword ptr [rcx+100h], 100h
0x140008c0c  jnz     short loc_140008C22
0x140008c0e  mov     eax, [rcx+200h]
0x140008c14  test    al, 40h
0x140008c16  jz      short loc_140008C22
0x140008c18  mov     dword ptr [rcx+100h], 0
0x140008c22  mov     rdx, [rdi+50h]
0x140008c26  lea     rcx, [rdx+0C8h]
0x140008c2d  test    dword ptr [rcx], 2000h
0x140008c33  jnz     short loc_140008C41
0x140008c35  test    dword ptr [rdx+200h], 4000h
0x140008c3f  jz      short loc_140008C63
0x140008c41  mov     edx, 2000h
0x140008c46  call    ClearFlagInterlocked
0x140008c4b  mov     rcx, [rdi+50h]
0x140008c4f  mov     edx, [rcx+200h]
0x140008c55  mov     rax, [rdi+50h]
0x140008c59  btr     edx, 0Eh
0x140008c5d  mov     [rax+200h], edx
0x140008c63  mov     rcx, [rdi+50h]
0x140008c67  lea     rdx, [rcx+0A0h]
0x140008c6e  add     rcx, 78h ; 'x'
0x140008c72  call    cs:__imp_FsRtlAcquireHeaderMutex
0x140008c79  nop     dword ptr [rax+rax+00h]
0x140008c7e  mov     rax, [rdi+50h]
0x140008c82  mov     qword ptr [rax+1F0h], 0
0x140008c8d  mov     rcx, [rdi+50h]
  ... truncated ...
```
