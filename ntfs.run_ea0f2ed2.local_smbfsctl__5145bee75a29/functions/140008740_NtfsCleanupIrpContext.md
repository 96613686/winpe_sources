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
- `0x140052b80`
- `0x1400b96a0`
- `0x1400ba87c`
- `0x1400bb020`
- `0x1400bbf04`
- `0x1400cab50`
- `0x1400cb8c4`
- `0x1400dc2c0`
- `0x1400dec60`
- `0x1400df650`
- `0x1400e6a1c`
- `0x1400ec74c`
- `0x1400f753c`
- `0x1400fa698`
- `0x1400fc090`
- `0x14010c7d0`
- `0x14010d148`
- `0x140133f30`
- `0x140181b60`
- `0x140182690`
- `0x14018f3c8`
- `0x140190b80`
- `0x1401aa6dc`
- `0x1401ac2a0`
- `0x1401bbd30`
- `0x1401bd3c0`
- `0x1401bd940`
- `0x1401cf440`
- `0x1401d1f5c`
- `0x1401d432c`
- `0x1401d50f8`
- `0x1401d6948`
- `0x1401d8340`
- `0x1401e9500`
- `0x1401f3b90`
- `0x1401f4220`
- `0x1401f5088`
- `0x1401fc600`
- `0x1401fccf0`
- `0x14020a724`

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
- `0x14004fa68`
- `0x140059250`
- `0x1400596c0`
- `0x140176e60`
- `0x1401aac30`
- `0x1401e76a0`
- `0x1401e77d0`
- `0x14025120c`

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
  _QWORD *v14; // rax
  _QWORD *v15; // rdi
  _QWORD *v16; // rsi
  _QWORD *v17; // rbx
  _QWORD *v18; // rax
  __int64 v19; // rcx
  __int64 v20; // rdx
  _QWORD *v21; // rcx
  _QWORD *v22; // rax
  struct _ERESOURCE *v23; // rcx
  _QWORD *v24; // r14
  int v25; // r15d
  __int64 v26; // rcx
  _QWORD *v27; // rax
  _QWORD *v28; // rdi
  __int64 v29; // rbp
  _QWORD *v30; // rsi
  _QWORD *v31; // rbx
  _QWORD *v32; // rax
  __int64 v33; // rcx
  __int64 v34; // rdx
  _QWORD *v35; // rcx
  _QWORD *v36; // rax
  __int64 v37; // rcx
  struct _ERESOURCE *v38; // rcx
  void *v39; // rcx
  __int64 v40; // rsi
  __int64 j; // rdi
  __int64 v42; // rbx
  __int64 v43; // rcx
  __int64 *v44; // rax
  __int64 v45; // rdx
  __int64 *v46; // rbp
  __int64 **v47; // rcx
  _QWORD *v48; // rax
  _QWORD *v49; // rdi
  _QWORD *v50; // rsi
  _QWORD *v51; // rbx
  _QWORD *v52; // rax
  __int64 v53; // rcx
  __int64 v54; // rcx
  _QWORD *v55; // rcx
  _QWORD *v56; // rax
  _QWORD *v57; // rax
  _QWORD *v58; // rbx
  _QWORD *v59; // rsi
  _QWORD *v60; // rdi
  _QWORD *v61; // rax
  _DWORD *v62; // rcx
  __int64 v63; // rcx
  _QWORD *v64; // rcx
  _QWORD *v65; // rax
  int v66; // edx
  _QWORD *v67; // rcx
  __int64 v68; // rcx
  volatile signed __int32 *v69; // rcx
  int v70; // edx
  int v71; // eax
  void *v72; // rcx
  struct _SECURITY_SUBJECT_CONTEXT *v73; // rcx
  __int64 v74; // rdi
  _QWORD *v75; // rbx
  __int64 v76; // rcx
  void *v77; // rcx
  __int64 v78; // r8
  __int64 v79; // rax
  __int64 v80; // rdi
  __int64 v81; // rax
  _QWORD *v82; // rcx
  char v83; // si
  __int64 v84; // rbx
  KIRQL v85; // cl
  _QWORD *v86; // r8
  __int64 v87; // rcx
  PIRP TopLevelIrp; // rax
  bool v89; // zf
  IRP *MasterIrp; // rcx
  unsigned int v91; // ecx
  __int64 v92; // r9
  __int64 v93; // rax
  unsigned int v94; // eax
  __int64 v95; // rdx
  int v96; // eax
  _BYTE v97[4]; // [rsp+30h] [rbp-78h] BYREF
  unsigned int v98; // [rsp+34h] [rbp-74h]
  __int128 v99; // [rsp+38h] [rbp-70h] BYREF
  __int64 v100; // [rsp+48h] [rbp-60h]

  v98 = a2;
  v3 = (_QWORD *)(a1 + 168);
  v5 = (__int64 **)(a1 + 152);
  v6 = (_QWORD **)(a1 + 280);
  while ( 2 )
  {
    v97[0] = 0;
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
      v24 = *(_QWORD **)(a1 + 40);
      v25 = *(unsigned __int16 *)(a1 + 34);
      while ( 1 )
      {
        v26 = *v24;
        if ( *v24 )
          break;
LABEL_95:
        ++v24;
        if ( !--v25 )
        {
          v39 = *(void **)(a1 + 40);
          if ( *(_BYTE *)(a1 + 32) == 18 )
          {
            memset(v39, 0, 8LL * *(unsigned __int16 *)(a1 + 34));
          }
          else
          {
            ExFreePoolWithTag(v39, 0);
            *(_QWORD *)(a1 + 40) = 0;
            *(_WORD *)(a1 + 34) = 0;
          }
          v5 = (__int64 **)(a1 + 152);
          goto LABEL_100;
        }
      }
      if ( *(_WORD *)v26 == 1805 )
      {
        NtfsReleaseQuotaControl(a1, *v24);
LABEL_94:
        *v24 = 0;
        goto LABEL_95;
      }
      if ( !ExIsResourceAcquiredExclusiveLite((PERESOURCE)(*(_QWORD *)(v26 + 104) + 64LL)) )
        goto LABEL_89;
      if ( ExIsResourceAcquiredSharedLite((PERESOURCE)(*(_QWORD *)(*v24 + 104LL) + 64LL)) != 1 )
        goto LABEL_89;
      v27 = *v6;
      if ( *v6 == v6 )
        goto LABEL_89;
      while ( 1 )
      {
        v28 = v27 - 1;
        if ( *((_WORD *)v27 - 4) == 1831 )
          break;
        v27 = (_QWORD *)*v27;
        if ( v27 == v6 )
          goto LABEL_89;
      }
      v29 = *v24;
      if ( v27 == (_QWORD *)8 )
      {
LABEL_89:
        v37 = *v24;
        if ( *(_WORD *)*v24 == 1794 )
          v38 = (struct _ERESOURCE *)(*(_QWORD *)(v37 + 104) + 64LL);
        else
          v38 = *(struct _ERESOURCE **)(v37 + 8);
        ExReleaseResourceLite(v38);
        goto LABEL_94;
      }
      while ( 1 )
      {
        v30 = 0;
        v31 = v28 + 1;
        if ( *v6 != v6 )
        {
          v32 = (_QWORD *)*v31;
          if ( (_QWORD **)*v31 != v6 )
          {
            while ( *((_WORD *)v32 - 4) != 1831 )
            {
              v32 = (_QWORD *)*v32;
              if ( v32 == v6 )
                goto LABEL_72;
            }
            v30 = v32 - 1;
          }
        }
LABEL_72:
        v33 = v28[10];
        if ( !v33 )
          goto LABEL_84;
        if ( !v29 || *(_QWORD *)(v33 + 184) == v29 )
          break;
LABEL_88:
        v28 = v30;
        if ( !v30 )
          goto LABEL_89;
      }
      if ( (*(_DWORD *)(v33 + 200) & 0x2000) != 0 || (*(_DWORD *)(v33 + 512) & 0x4040) != 0 )
      {
        if ( *(_DWORD *)(v33 + 256) == 256 && (*(_DWORD *)(v33 + 512) & 0x40) != 0 )
          *(_DWORD *)(v33 + 256) = 0;
        v34 = v28[10];
        if ( (*(_DWORD *)(v34 + 200) & 0x2000) != 0 || (*(_DWORD *)(v34 + 512) & 0x4000) != 0 )
        {
          ClearFlagInterlocked(v34 + 200, 0x2000);
          *(_DWORD *)(v28[10] + 512LL) &= ~0x4000u;
        }
      }
      FsRtlAcquireHeaderMutex(v28[10] + 120LL, v28[10] + 160LL);
      *(_QWORD *)(v28[10] + 496LL) = 0;
      FsRtlReleaseHeaderMutex(v28[10] + 120LL, v28[10] + 160LL);
LABEL_84:
      v35 = (_QWORD *)*v31;
      if ( *(_QWORD **)(*v31 + 8LL) != v31 || (v36 = (_QWORD *)v28[2], (_QWORD *)*v36 != v31) )
        __fastfail(3u);
      *v36 = v35;
      v35[1] = v36;
      if ( v28 != (_QWORD *)(a1 + 552) )
        ExFreeToLookasideListEx(&NtfsScbSnapshotLookasideList, v28);
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
          v14 = *v6;
          if ( *v6 != v6 )
          {
            while ( 1 )
            {
              v15 = v14 - 1;
              if ( *((_WORD *)v14 - 4) == 1831 )
                break;
              v14 = (_QWORD *)*v14;
              if ( v14 == v6 )
                goto LABEL_49;
            }
            if ( v14 != (_QWORD *)8 )
            {
              while ( 1 )
              {
                v16 = 0;
                v17 = v15 + 1;
                if ( *v6 != v6 )
                {
                  v18 = (_QWORD *)*v17;
                  if ( (_QWORD **)*v17 != v6 )
                  {
                    while ( *((_WORD *)v18 - 4) != 1831 )
                    {
                      v18 = (_QWORD *)*v18;
                      if ( v18 == v6 )
                        goto LABEL_33;
                    }
                    v16 = v18 - 1;
                  }
                }
LABEL_33:
                v19 = v15[10];
                if ( !v19 )
                  goto LABEL_44;
                if ( *(_QWORD *)(v19 + 184) == v13 )
                  break;
LABEL_48:
                v15 = v16;
                if ( !v16 )
                  goto LABEL_49;
              }
              if ( (*(_DWORD *)(v19 + 200) & 0x2000) != 0 || (*(_DWORD *)(v19 + 512) & 0x4040) != 0 )
              {
                if ( *(_DWORD *)(v19 + 256) == 256 && (*(_DWORD *)(v19 + 512) & 0x40) != 0 )
                  *(_DWORD *)(v19 + 256) = 0;
                v20 = v15[10];
                if ( (*(_DWORD *)(v20 + 200) & 0x2000) != 0 || (*(_DWORD *)(v20 + 512) & 0x4000) != 0 )
                {
                  ClearFlagInterlocked(v20 + 200, 0x2000);
                  *(_DWORD *)(v15[10] + 512LL) &= ~0x4000u;
                }
              }
              FsRtlAcquireHeaderMutex(v15[10] + 120LL, v15[10] + 160LL);
              *(_QWORD *)(v15[10] + 496LL) = 0;
              FsRtlReleaseHeaderMutex(v15[10] + 120LL, v15[10] + 160LL);
LABEL_44:
              v21 = (_QWORD *)*v17;
              if ( *(_QWORD **)(*v17 + 8LL) != v17 || (v22 = (_QWORD *)v15[2], (_QWORD *)*v22 != v17) )
                __fastfail(3u);
              *v22 = v21;
              v21[1] = v22;
              if ( v15 != (_QWORD *)(a1 + 552) )
                ExFreeToLookasideListEx(&NtfsScbSnapshotLookasideList, v15);
              goto LABEL_48;
            }
          }
        }
      }
LABEL_49:
      if ( *(_WORD *)v13 == 1794 )
        v23 = (struct _ERESOURCE *)(*(_QWORD *)(v13 + 104) + 64LL);
      else
        v23 = *(struct _ERESOURCE **)(v13 + 8);
      ExReleaseResourceLite(v23);
    }
    *(_QWORD *)(a1 + 40) = 0;
    *(_WORD *)(a1 + 34) = 0;
LABEL_100:
    v40 = *(_QWORD *)(a1 + 64);
    for ( j = 0; j != 2; ++j )
    {
      v42 = *(_QWORD *)(a1 + 8 * j + 48);
      if ( v42 )
      {
        v43 = *(_QWORD *)(a1 + 8 * j + 48);
        if ( *(_WORD *)v42 != 1794 )
          v43 = *(_QWORD *)(v42 + 184);
        ExReleaseResourceLite(*(PERESOURCE *)(v43 + 112));
        if ( *(_QWORD *)(a1 + 48) == v42 )
          *(_QWORD *)(a1 + 48) = 0;
        if ( *(_QWORD *)(a1 + 56) == v42 )
          *(_QWORD *)(a1 + 56) = 0;
      }
    }
    if ( v40 )
    {
      *(_QWORD *)(a1 + 64) = 0;
      FsRtlReleaseEofLock(v40 + 120, v40 + 160);
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
      v44 = *v5;
      if ( *v5 == (__int64 *)v5 )
        break;
      v45 = *v44;
      v46 = v44 - 10;
      if ( *v44 )
      {
        if ( *((_WORD *)v46 + 16) != 1 )
          goto LABEL_152;
        if ( !*(_DWORD *)(a1 + 28) )
        {
          if ( *(__int64 **)(v45 + 8) != v44 || (v47 = (__int64 **)v44[1], *v47 != v44) )
            __fastfail(3u);
          *v47 = (__int64 *)v45;
          *(_QWORD *)(v45 + 8) = v47;
          *v44 = 0;
          v48 = *v6;
          if ( *v6 != v6 )
          {
            while ( 1 )
            {
              v49 = v48 - 1;
              if ( *((_WORD *)v48 - 4) == 1831 )
                break;
              v48 = (_QWORD *)*v48;
              if ( v48 == v6 )
                goto LABEL_150;
            }
            if ( v48 != (_QWORD *)8 )
            {
              while ( 1 )
              {
                v50 = 0;
                v51 = v49 + 1;
                if ( *v6 != v6 )
                {
                  v52 = (_QWORD *)*v51;
                  if ( (_QWORD **)*v51 != v6 )
                  {
                    while ( *((_WORD *)v52 - 4) != 1831 )
                    {
                      v52 = (_QWORD *)*v52;
                      if ( v52 == v6 )
                        goto LABEL_132;
                    }
                    v50 = v52 - 1;
                  }
                }
LABEL_132:
                v53 = v49[10];
                if ( !v53 )
                  goto LABEL_145;
                if ( *(__int64 **)(v53 + 184) == v46 )
                  break;
LABEL_149:
                v49 = v50;
                if ( !v50 )
                  goto LABEL_150;
              }
              if ( (*(_DWORD *)(v53 + 200) & 0x2000) != 0 || (*(_DWORD *)(v53 + 512) & 0x4040) != 0 )
              {
                if ( *(_DWORD *)(v53 + 256) == 256 && (*(_DWORD *)(v53 + 512) & 0x40) != 0 )
                  *(_DWORD *)(v53 + 256) = 0;
                v54 = v49[10];
                if ( (*(_DWORD *)(v54 + 200) & 0x2000) != 0 || (*(_DWORD *)(v54 + 512) & 0x4000) != 0 )
                {
                  if ( (*(_DWORD *)(v54 + 200) & 0x2000) != 0 )
                    _InterlockedAnd((volatile signed __int32 *)(v54 + 200), 0xFFFFDFFF);
                  *(_DWORD *)(v49[10] + 512LL) &= ~0x4000u;
                }
              }
              FsRtlAcquireHeaderMutex(v49[10] + 120LL, v49[10] + 160LL);
              *(_QWORD *)(v49[10] + 496LL) = 0;
              FsRtlReleaseHeaderMutex(v49[10] + 120LL, v49[10] + 160LL);
LABEL_145:
              v55 = (_QWORD *)*v51;
              if ( *(_QWORD **)(*v51 + 8LL) != v51 || (v56 = (_QWORD *)v49[2], (_QWORD *)*v56 != v51) )
                __fastfail(3u);
              *v56 = v55;
              v55[1] = v56;
              if ( v49 != (_QWORD *)(a1 + 552) )
                ExFreeToLookasideListEx(&NtfsScbSnapshotLookasideList, v49);
              goto LABEL_149;
            }
          }
LABEL_150:
          if ( *((int *)v46 + 44) < 0 )
            *(_DWORD *)(a1 + 436) &= ~0x8000u;
LABEL_152:
          --*((_WORD *)v46 + 16);
          goto LABEL_153;
        }
      }
      else
      {
LABEL_153:
        if ( *(_WORD *)v46 == 1794 )
          ExReleaseResourceLite((PERESOURCE)(v46[13] + 64));
        else
          ExReleaseResourceLite((PERESOURCE)v46[1]);
      }
    }
    v57 = *v6;
    if ( *v6 != v6 )
    {
      while ( 1 )
      {
        v58 = v57 - 1;
        if ( *((_WORD *)v57 - 4) == 1831 )
          break;
        v57 = (_QWORD *)*v57;
        if ( v57 == v6 )
          goto LABEL_185;
      }
      if ( v57 != (_QWORD *)8 )
      {
        do
        {
          v59 = 0;
          v60 = v58 + 1;
          if ( *v6 != v6 )
          {
            v61 = (_QWORD *)*v60;
            if ( (_QWORD **)*v60 != v6 )
            {
              while ( *((_WORD *)v61 - 4) != 1831 )
              {
                v61 = (_QWORD *)*v61;
                if ( v61 == v6 )
                  goto LABEL_168;
              }
              v59 = v61 - 1;
            }
          }
LABEL_168:
          v62 = (_DWORD *)v58[10];
          if ( v62 )
          {
            if ( (v62[50] & 0x2000) != 0 || (v62[128] & 0x4040) != 0 )
            {
              if ( v62[64] == 256 && (v62[128] & 0x40) != 0 )
                v62[64] = 0;
              v63 = v58[10];
              if ( (*(_DWORD *)(v63 + 200) & 0x2000) != 0 || (*(_DWORD *)(v63 + 512) & 0x4000) != 0 )
              {
                if ( (*(_DWORD *)(v63 + 200) & 0x2000) != 0 )
                  _InterlockedAnd((volatile signed __int32 *)(v63 + 200), 0xFFFFDFFF);
                *(_DWORD *)(v58[10] + 512LL) &= ~0x4000u;
              }
            }
            FsRtlAcquireHeaderMutex(v58[10] + 120LL, v58[10] + 160LL);
            *(_QWORD *)(v58[10] + 496LL) = 0;
            FsRtlReleaseHeaderMutex(v58[10] + 120LL, v58[10] + 160LL);
          }
          v64 = (_QWORD *)*v60;
          if ( *(_QWORD **)(*v60 + 8LL) != v60 || (v65 = (_QWORD *)v58[2], (_QWORD *)*v65 != v60) )
            __fastfail(3u);
          *v65 = v64;
          v64[1] = v65;
          if ( v58 != (_QWORD *)(a1 + 552) )
            ExFreeToLookasideListEx(&NtfsScbSnapshotLookasideList, v58);
          v58 = v59;
        }
        while ( v59 );
      }
    }
LABEL_185:
    v66 = *(_DWORD *)(a1 + 4);
    if ( (v66 & 0x400) == 0 )
    {
      v67 = *(_QWORD **)(a1 + 232);
      if ( v67 )
      {
        do
        {
          *(_QWORD *)(a1 + 232) = *v67;
          ExFreePoolWithTag(v67, 0);
          v67 = *(_QWORD **)(a1 + 232);
        }
        while ( v67 );
        v66 = *(_DWORD *)(a1 + 4);
      }
    }
    if ( (*(_DWORD *)(a1 + 376) & 1) != 0 || (*(_DWORD *)(a1 + 16) & 0x3000LL) != 0 )
    {
      NtfsProcessAttachedCorruptions(a1, v97);
      v66 = *(_DWORD *)(a1 + 4);
      if ( v97[0] )
      {
        v3 = (_QWORD *)(a1 + 168);
        continue;
      }
    }
    break;
  }
  if ( *(_QWORD *)(a1 + 384) )
  {
    if ( (v66 & 0x400) == 0 )
    {
      if ( IoGetTopLevelIrp() )
      {
        if ( (unsigned __int8)NtfsRepairIsTopLevelRequest(a1) )
        {
          v68 = *(_QWORD *)(a1 + 384);
          if ( (v68 & 2) != 0 )
          {
            v69 = (volatile signed __int32 *)(v68 & 0xFFFFFFFFFFFFFFFCuLL);
            if ( !_InterlockedCompareExchange(v69 + 5, 0, 1) )
              NtfsFreeRepairItem((PVOID)v69);
            *(_QWORD *)(a1 + 384) = 0;
          }
        }
      }
    }
  }
  v70 = *(_DWORD *)(a1 + 4);
  if ( (v70 & 0x400) != 0 || (v71 = *(_DWORD *)(a1 + 12), (v71 & 0x10000) != 0) )
  {
    *(_DWORD *)(a1 + 436) = *(_DWORD *)(a1 + 432) | *(_DWORD *)(a1 + 436) & 0xFFFDBF49;
    if ( (v70 & 0x40000) != 0 )
    {
      v95 = v70 & 0xFFFBFBFF;
    }
    else
    {
      a3 = v98;
      v94 = v70 & 0xDE6B4000;
      v95 = v70 & 0xDE6B4008;
      v7 = 4294967292LL;
      if ( v98 )
        v95 = v94;
      v96 = -2;
      if ( !v98 )
        v96 = -4;
      *(_DWORD *)(a1 + 8) &= v96;
    }
    *(_DWORD *)(a1 + 4) = v95;
    *(_QWORD *)(a1 + 16) &= ~4uLL;
    NtfsMarkUnusedContextPreTrimProcessing(a1, v95, a3, v7);
    *(_QWORD *)(a1 + 184) = 0;
    *(_DWORD *)(a1 + 24) = 0;
  }
  else
  {
    v72 = *(void **)(a1 + 488);
    if ( v72 )
    {
      ExFreePoolWithTag(v72, 0);
      v71 = *(_DWORD *)(a1 + 12);
      *(_QWORD *)(a1 + 488) = 0;
    }
    v73 = *(struct _SECURITY_SUBJECT_CONTEXT **)(a1 + 208);
    if ( v73 )
    {
      if ( (v71 & 0x80000010) != 0 )
      {
        if ( ((__int64)v73->ClientToken & 0x1000) != 0 )
          ExReleaseRundownProtection((PEX_RUNDOWN_REF)(*(_QWORD *)(*(_QWORD *)(a1 + 104) + 11784LL) + 32LL));
        v74 = *(_QWORD *)(a1 + 208);
        v75 = *(_QWORD **)(v74 + 32);
        if ( v75 )
        {
          v76 = *v75;
          if ( *v75 )
          {
            if ( (*(_BYTE *)(v76 + 10) & 1) != 0 )
            {
              *(_QWORD *)(v76 + 32) = v75[1];
              MmUnmapLockedPages(*(PVOID *)(*v75 + 24LL), (PMDL)*v75);
            }
            IoFreeMdl((PMDL)*v75);
            *v75 = 0;
          }
          v77 = (void *)v75[1];
          if ( v77 )
          {
            ExFreePoolWithTag(v77, 0);
            v75[1] = 0;
          }
          ExFreeToLookasideListEx(&NtfsAlignedMdlContextLookasideList, v75);
          *(_QWORD *)(v74 + 32) = 0;
        }
        if ( (*(_DWORD *)(a1 + 12) & 0x10) != 0 )
        {
          v78 = *(_QWORD *)(a1 + 208);
          v79 = *(unsigned int *)(v78 - 8);
          if ( (unsigned int)v79 >= NtfsNumberProcessors )
            v79 = (unsigned int)v79 % NtfsNumberProcessors;
          ExFreeToLookasideListEx((PLOOKASIDE_LIST_EX)(NtfsIoContextLookasideList + 96 * v79), (PVOID)(v78 - 8));
        }
        *(_DWORD *)(a1 + 12) &= 0x7FFFFFEFu;
      }
      else if ( (v71 & 0x20) != 0 )
      {
        SeReleaseSubjectContext(v73);
        ExFreePoolWithTag(*(PVOID *)(a1 + 208), 0);
        *(_DWORD *)(a1 + 12) &= ~0x20u;
      }
      *(_QWORD *)(a1 + 208) = 0;
    }
    v80 = a1 + 464;
    v100 = 0;
    v81 = *(_QWORD *)(a1 + 464);
    v99 = 0;
    if ( v81 != a1 + 464 )
    {
      v82 = *(_QWORD **)(v81 + 48);
      v83 = 0;
      v84 = *(_QWORD *)(v81 + 16);
      if ( v82 )
      {
        *((_QWORD *)&v99 + 1) = *v82;
        v100 = v82[1];
        *(_QWORD *)&v99 = (char *)&v99 + 8;
      }
      else
      {
        *(_QWORD *)&v99 = 0;
      }
      if ( (*(_DWORD *)(a1 + 16) & 0x100000) == 0
        && (Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits & 0x200000) != 0 )
      {
        McTemplateU0pp_EtwWriteTransfer(v82, delnotify_c1457, v84, a1);
      }
      v85 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v84 + 1752));
      if ( !*(_BYTE *)(v84 + 1808) )
      {
        v83 = 1;
        *(_BYTE *)(v84 + 1808) = 1;
      }
      v86 = *(_QWORD **)(v84 + 1768);
      *v86 = *(_QWORD *)v80;
      *(_QWORD *)(v84 + 1768) = *(_QWORD *)(a1 + 472);
      **(_QWORD **)(a1 + 472) = v84 + 1760;
      *(_QWORD *)(*(_QWORD *)v80 + 8LL) = v86;
      KeReleaseSpinLock((PKSPIN_LOCK)(v84 + 1752), v85);
      *(_QWORD *)(a1 + 472) = a1 + 464;
      *(_QWORD *)v80 = v80;
      if ( (Microsoft_Windows_NtfsEnableBits & 0x8000000) != 0 )
        McTemplateK0pq_EtwWriteTransfer(v87, WORKITEM_QUEUE, v99);
      if ( v83 )
      {
        if ( (*(_DWORD *)(a1 + 16) & 0x100000) == 0
          && (Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits & 0x40) != 0 )
        {
          McTemplateU0p_EtwWriteTransfer(v87, delnotify_c1503, v84);
        }
        ExQueueWorkItem((PWORK_QUEUE_ITEM)(v84 + 1776), DelayedWorkQueue);
      }
      if ( (*(_DWORD *)(a1 + 16) & 0x100000LL) == 0
        && (Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits & 0x200000) != 0 )
      {
        McTemplateU0p_EtwWriteTransfer(v87, delnotify_c1512, v84);
      }
    }
    if ( (*(_DWORD *)(a1 + 12) & 0x100000) != 0 )
    {
      TopLevelIrp = IoGetTopLevelIrp();
      v89 = LOBYTE(TopLevelIrp->Size) == 0;
      TopLevelIrp->ThreadListEntry.Flink = 0;
      if ( v89 )
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
      v91 = NtfsNumberProcessors;
      v92 = NtfsIrpContextLookasideList;
      *(_QWORD *)(a1 + 496) = 22;
      v93 = *(unsigned int *)(a1 - 8);
      if ( (unsigned int)v93 >= v91 )
        v93 = (unsigned int)v93 % v91;
      ExFreeToLookasideListEx((PLOOKASIDE_LIST_EX)(v92 + 96 * v93), (PVOID)(a1 - 8));
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
