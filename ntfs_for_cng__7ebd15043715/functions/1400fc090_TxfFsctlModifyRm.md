# TxfFsctlModifyRm

- ea: `0x1400fc090`
- end: `0x1400fd4e3`
- name: `TxfFsctlModifyRm`
- size: `5203`
- prototype: `__int64 __fastcall(unsigned __int64, unsigned __int64, unsigned int, int *)`
- caller_count: `1`
- callee_count: `21`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x1402491a8`

## callees

- `0x140007ea0`
- `0x140008740`
- `0x14000cb00`
- `0x14000d1e0`
- `0x140010be0`
- `0x1400291f0`
- `0x140029d80`
- `0x14004088c`
- `0x140051fb0`
- `0x140052f24`
- `0x1400542f0`
- `0x140059250`
- `0x1400f9d48`
- `0x1400fa698`
- `0x1400fc090`
- `0x14010d148`
- `0x14013ad80`
- `0x140140380`
- `0x140188ce4`
- `0x1401913d4`
- `0x14020b5f4`

## import_xrefs

- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1400fc28a`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1400fd200`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1400fc28a`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1400fd200`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400fd262`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400fd27f`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400fd3ee`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400fd466`
- `ntoskrnl!ExReleaseResourceLite` at `0x1402c4610`
- `ntoskrnl!ExReleaseResourceLite` at `0x1402c4688`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400fd262`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400fd27f`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400fd3ee`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400fd466`
- `ntoskrnl!ExReleaseResourceLite` at `0x1402c4610`
- `ntoskrnl!ExReleaseResourceLite` at `0x1402c4688`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x1400fd188`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x1400fd188`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsMgmtSetLogFileSizeAsClient` at `0x1400fcdad`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsMgmtSetLogFileSizeAsClient` at `0x1400fcdad`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsMgmtRemovePolicy` at `0x1400fcca3`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsMgmtRemovePolicy` at `0x1400fcca3`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsMgmtInstallPolicy` at `0x1400fc747`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsMgmtInstallPolicy` at `0x1400fc833`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsMgmtInstallPolicy` at `0x1400fc918`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsMgmtInstallPolicy` at `0x1400fc9f8`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsMgmtInstallPolicy` at `0x1400fcb06`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsMgmtInstallPolicy` at `0x1400fcc08`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsMgmtInstallPolicy` at `0x1400fc747`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsMgmtInstallPolicy` at `0x1400fc833`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsMgmtInstallPolicy` at `0x1400fc918`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsMgmtInstallPolicy` at `0x1400fc9f8`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsMgmtInstallPolicy` at `0x1400fcb06`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsMgmtInstallPolicy` at `0x1400fcc08`

## pseudocode

```c
__int64 __fastcall TxfFsctlModifyRm(unsigned __int64 a1, unsigned __int64 a2, unsigned int a3, int *a4)
{
  int v6; // r13d
  int v7; // edx
  __int64 v8; // r15
  unsigned int v9; // r8d
  signed int NewRMGuid; // ebx
  __int64 v11; // rax
  unsigned int v12; // r8d
  int v13; // eax
  int v14; // ecx
  int v15; // r8d
  int v16; // r12d
  __int64 v17; // r8
  __int64 v18; // r8
  int *v19; // r13
  __int64 v20; // rcx
  unsigned int v21; // eax
  unsigned int v22; // r8d
  int v23; // eax
  int v24; // ecx
  unsigned int v25; // eax
  unsigned __int64 v26; // r13
  __int64 v27; // r12
  int v28; // edx
  int v29; // ecx
  int v30; // ecx
  int *v31; // rdx
  int v32; // r12d
  int v33; // eax
  int v34; // eax
  int v35; // eax
  __int64 v36; // r10
  __int64 v37; // r8
  bool v38; // r13
  int v39; // eax
  unsigned int v40; // eax
  __int64 v41; // r12
  __int64 v42; // rax
  __int64 v43; // r13
  int v44; // eax
  int v45; // eax
  unsigned int v46; // eax
  int CompletionRoutine; // [rsp+20h] [rbp-158h]
  CLFS_LSN *plsn1; // [rsp+38h] [rbp-140h]
  bool v50; // [rsp+90h] [rbp-E8h]
  char v51[3]; // [rsp+91h] [rbp-E7h] BYREF
  signed int v52; // [rsp+94h] [rbp-E4h]
  char v53; // [rsp+98h] [rbp-E0h]
  char v54; // [rsp+99h] [rbp-DFh]
  char v55; // [rsp+9Ah] [rbp-DEh]
  char v56; // [rsp+9Bh] [rbp-DDh] BYREF
  int v57; // [rsp+9Ch] [rbp-DCh] BYREF
  int v58; // [rsp+A0h] [rbp-D8h] BYREF
  int v59; // [rsp+A4h] [rbp-D4h] BYREF
  __int16 v60; // [rsp+A8h] [rbp-D0h] BYREF
  int v61; // [rsp+ACh] [rbp-CCh]
  int *v62; // [rsp+B0h] [rbp-C8h] BYREF
  int *v63; // [rsp+B8h] [rbp-C0h]
  __int64 v64; // [rsp+C0h] [rbp-B8h] BYREF
  unsigned __int64 NewSizeInContainers; // [rsp+C8h] [rbp-B0h] BYREF
  _QWORD v66[2]; // [rsp+D0h] [rbp-A8h] BYREF
  __int64 v67; // [rsp+E0h] [rbp-98h]
  __int64 v68; // [rsp+E8h] [rbp-90h]
  __int64 v69; // [rsp+F0h] [rbp-88h] BYREF
  int v70; // [rsp+F8h] [rbp-80h]
  int v71; // [rsp+FCh] [rbp-7Ch]
  int *v72; // [rsp+100h] [rbp-78h]
  unsigned __int64 ResultingSizeInContainers; // [rsp+108h] [rbp-70h] BYREF
  _CLFS_MGMT_POLICY Policy; // [rsp+110h] [rbp-68h] BYREF
  __int128 v75; // [rsp+128h] [rbp-50h] BYREF

  v62 = a4;
  NewSizeInContainers = a2;
  v72 = a4;
  v66[1] = a1;
  *(_QWORD *)&v75 = a2;
  v63 = a4;
  memset(&Policy, 0, sizeof(Policy));
  v69 = 0;
  v66[0] = 0;
  v51 = 0;
  v6 = 0;
  LODWORD(v64) = 0;
  v57 = 0;
  if ( !a4 || a3 < 0x28 )
  {
    if ( NtfsStatusDebugFlags )
    {
      v9 = 2687828;
      goto LABEL_239;
    }
    return (unsigned int)-1073741811;
  }
  v7 = *a4;
  if ( (*a4 & 0xFFFC0200) != 0 || !v7 )
  {
    if ( NtfsStatusDebugFlags )
    {
      v9 = 2687838;
      goto LABEL_239;
    }
    return (unsigned int)-1073741811;
  }
  if ( (v7 & 0x84) == 0x84
    || (*a4 & 0x108) == 0x108
    || (*a4 & 0x30) == 48
    || (*a4 & 0xC00) == 3072
    || (v7 & 0x4000) != 0 && (v7 & 0x8000) != 0
    || (v7 & 0x10000) != 0 && (v7 & 0x20000) != 0 )
  {
    if ( NtfsStatusDebugFlags )
    {
      v9 = 2687863;
      goto LABEL_239;
    }
    return (unsigned int)-1073741811;
  }
  v8 = *(_QWORD *)(a2 + 320);
  v68 = v8;
  if ( ((v7 & 0x4000) != 0 || (v7 & 0x8000) != 0) && v8 != *(_QWORD *)(*(_QWORD *)(v8 + 16) + 6248LL) )
  {
    if ( NtfsStatusDebugFlags )
    {
      v9 = 2687874;
LABEL_239:
      NewRMGuid = -1073741811;
      NtfsStatusTraceAndDebugInternal(0, 0xC000000D, v9);
      return (unsigned int)NewRMGuid;
    }
    return (unsigned int)-1073741811;
  }
  ResultingSizeInContainers = a1;
  NewRMGuid = 0;
  v52 = 0;
  v67 = v8;
  v53 = 0;
  v50 = 0;
  v55 = 0;
  v54 = 0;
  if ( (v7 & 0x10000) != 0 || (v7 & 0x20000) != 0 )
  {
    v11 = *(_QWORD *)(v8 + 16);
    if ( v8 == *(_QWORD *)(v11 + 6248) && (*(_DWORD *)(*(_QWORD *)(*(_QWORD *)(v11 + 248) + 16LL) + 48LL) & 0x100) != 0 )
    {
      if ( NtfsStatusDebugFlags )
      {
        v9 = 2687887;
        goto LABEL_239;
      }
      return (unsigned int)-1073741811;
    }
  }
  ExAcquireResourceExclusiveLite((PERESOURCE)(*(_QWORD *)(v8 + 24) + 912LL), 1u);
  if ( _InterlockedCompareExchange((volatile signed __int32 *)(v8 + 132), 4, 4) == 2 )
  {
LABEL_30:
    if ( (*(_DWORD *)(*(_QWORD *)(NewSizeInContainers + 96) + 4LL) & 0x2000000) != 0 )
    {
      NewRMGuid = -1073741662;
      if ( !NtfsStatusDebugFlags )
        goto LABEL_28;
      v12 = 2687928;
      goto LABEL_27;
    }
    v13 = *v62;
    v14 = 0;
    if ( (*v62 & 0x4000) != 0 )
      v14 = 0x200000;
    v59 = v14;
    v70 = v14;
    v15 = 0;
    if ( (v13 & 0x8000) != 0 )
      v15 = 0x200000;
    v58 = v15;
    v71 = v15;
    if ( (v13 & 0x10000) != 0 )
    {
      v6 = 4;
      LODWORD(v64) = 4;
      v16 = 8;
      v57 = 8;
    }
    else
    {
      v16 = v57;
    }
    if ( (v13 & 0x20000) != 0 )
    {
      v6 |= 8u;
      LODWORD(v64) = v6;
      v16 |= 4u;
      v57 = v16;
    }
    if ( v14 || v15 )
    {
      NtfsAcquireExclusiveFcb(a1, NewSizeInContainers, 0, 0);
      TxfUpdateTxfDataAttributeMembers(a1, NewSizeInContainers, CompletionRoutine, v59, v58, 0, 0, 0, 0, 0, 0);
      if ( v54 || !v6 && !v16 )
      {
        NtfsCheckpointCurrentTransaction(a1);
        *(_DWORD *)(a1 + 4) |= 0x400u;
        NtfsCleanupIrpContext(a1, 0, v17);
        NewRMGuid = 0;
        v52 = 0;
      }
      *(_DWORD *)(*(_QWORD *)(a1 + 144) + 24LL) = 0;
    }
    if ( v54 )
      goto LABEL_221;
    if ( v6 || v57 )
    {
      NtfsAcquireExclusiveScbEx(a1, *(_QWORD *)(v8 + 288), 0);
      TxfUpdateTopsMetadataStream(a1, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, (__int64)&v64, (__int64)&v57);
      NtfsCheckpointCurrentTransaction(a1);
      *(_DWORD *)(a1 + 4) |= 0x400u;
      NtfsCleanupIrpContext(a1, 0, v18);
      NewRMGuid = 0;
      v52 = 0;
      *(_DWORD *)(*(_QWORD *)(a1 + 144) + 24LL) = 0;
    }
    v19 = v62;
    if ( (*v62 & 2) != 0 )
    {
      v75 = *(_OWORD *)(v8 + 672);
      NewRMGuid = TxfCreateNewRMGuid(a1, v8);
      v52 = NewRMGuid;
      if ( NewRMGuid < 0 )
        goto LABEL_221;
      if ( (!a1 || (*(_DWORD *)(a1 + 16) & 0x100000) == 0)
        && (Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits & 0x8000000) != 0 )
      {
        McTemplateU0spjj_EtwWriteTransfer(
          v20,
          (const EVENT_DESCRIPTOR *)txfctrl_c1120,
          "TxfFsctlModifyRm",
          v8,
          &v75,
          v8 + 672);
      }
    }
    if ( (*v19 & 4) != 0 )
    {
      v21 = v63[1];
      if ( v21 < 2 )
      {
        NewRMGuid = -1073741811;
        if ( !NtfsStatusDebugFlags )
          goto LABEL_28;
        v12 = 2688119;
        goto LABEL_27;
      }
      Policy.Version = 1;
      Policy.LengthInBytes = 24;
      *(_QWORD *)&Policy.PolicyFlags = 1;
      Policy.PolicyParameters.NewContainerSuffix.NextContainerSuffix = v21;
      NtfsPurgeFileRecordCache(a1);
      *(_DWORD *)(a1 + 4) |= 0x200u;
      NewRMGuid = ClfsMgmtInstallPolicy(*(PLOG_FILE_OBJECT *)(v8 + 496), &Policy, 0x18u);
      v52 = NewRMGuid;
      *(_DWORD *)(a1 + 4) &= ~0x200u;
      if ( NewRMGuid < 0 )
      {
        if ( !NtfsStatusDebugFlags
          || (unsigned int)NewRMGuid >= 0xFFFFFFED
          || NewRMGuid == -1073741802
          || NewRMGuid == -1073741807
          || (unsigned int)(NewRMGuid + 2147483643) <= 1
          || NewRMGuid == -1073741608 )
        {
          goto LABEL_221;
        }
        v22 = 2688145;
        goto LABEL_71;
      }
    }
    if ( (*v19 & 0x80u) != 0 )
    {
      Policy.Version = 1;
      Policy.LengthInBytes = 24;
      Policy.PolicyType = ClfsMgmtPolicyMaximumSize;
      Policy.PolicyParameters.NewContainerSuffix.NextContainerSuffix = 0xFFFFFFFFLL;
      Policy.PolicyFlags = 1;
      NtfsPurgeFileRecordCache(a1);
      *(_DWORD *)(a1 + 4) |= 0x200u;
      NewRMGuid = ClfsMgmtInstallPolicy(*(PLOG_FILE_OBJECT *)(v8 + 496), &Policy, 0x18u);
      v52 = NewRMGuid;
      *(_DWORD *)(a1 + 4) &= ~0x200u;
      if ( NewRMGuid < 0 )
      {
        if ( !NtfsStatusDebugFlags
          || (unsigned int)NewRMGuid >= 0xFFFFFFED
          || NewRMGuid == -1073741802
          || NewRMGuid == -1073741807
          || (unsigned int)(NewRMGuid + 2147483643) <= 1
          || NewRMGuid == -1073741608 )
        {
          goto LABEL_221;
        }
        v22 = 2688174;
        goto LABEL_71;
      }
    }
    if ( (*v19 & 8) != 0 )
    {
      Policy.PolicyFlags = 0;
      Policy.PolicyParameters.NewContainerSuffix.NextContainerSuffix = 0;
      Policy.Version = 1;
      Policy.LengthInBytes = 24;
      Policy.PolicyType = ClfsMgmtPolicyMinimumSize;
      Policy.PolicyParameters.MaximumSize.Containers = v63[2];
      Policy.PolicyFlags = 1;
      NtfsPurgeFileRecordCache(a1);
      *(_DWORD *)(a1 + 4) |= 0x200u;
      NewRMGuid = ClfsMgmtInstallPolicy(*(PLOG_FILE_OBJECT *)(v8 + 496), &Policy, 0x18u);
      v52 = NewRMGuid;
      *(_DWORD *)(a1 + 4) &= ~0x200u;
      if ( NewRMGuid < 0 )
      {
        if ( !NtfsStatusDebugFlags
          || (unsigned int)NewRMGuid >= 0xFFFFFFED
          || NewRMGuid == -1073741802
          || NewRMGuid == -1073741807
          || (unsigned int)(NewRMGuid + 2147483643) <= 1
          || NewRMGuid == -1073741608 )
        {
          goto LABEL_221;
        }
        v22 = 2688207;
        goto LABEL_71;
      }
    }
    if ( (*v19 & 0x100) != 0 )
    {
      Policy.Version = 1;
      Policy.LengthInBytes = 24;
      Policy.PolicyType = ClfsMgmtPolicyMinimumSize;
      Policy.PolicyParameters.NewContainerSuffix.NextContainerSuffix = 0xFFFFFFFFLL;
      Policy.PolicyFlags = 1;
      NtfsPurgeFileRecordCache(a1);
      *(_DWORD *)(a1 + 4) |= 0x200u;
      NewRMGuid = ClfsMgmtInstallPolicy(*(PLOG_FILE_OBJECT *)(v8 + 496), &Policy, 0x18u);
      v52 = NewRMGuid;
      *(_DWORD *)(a1 + 4) &= ~0x200u;
      if ( NewRMGuid < 0 )
      {
        if ( !NtfsStatusDebugFlags
          || (unsigned int)NewRMGuid >= 0xFFFFFFED
          || NewRMGuid == -1073741802
          || NewRMGuid == -1073741807
          || (unsigned int)(NewRMGuid + 2147483643) <= 1
          || NewRMGuid == -1073741608 )
        {
          goto LABEL_221;
        }
        v22 = 2688236;
        goto LABEL_71;
      }
    }
    v23 = *v19 & 0x20;
    v24 = *v19 & 0x10;
    if ( v24 || v23 )
    {
      Policy.PolicyFlags = 0;
      Policy.PolicyParameters.NewContainerSuffix.NextContainerSuffix = 0;
      Policy.Version = 1;
      Policy.LengthInBytes = 24;
      Policy.PolicyType = ClfsMgmtPolicyGrowthRate;
      if ( v24 )
      {
        Policy.PolicyParameters.MaximumSize.Containers = v63[4];
      }
      else if ( v23 )
      {
        Policy.PolicyParameters.GrowthRate.RelativeGrowthPercentage = v63[4];
      }
      Policy.PolicyFlags = 1;
      NtfsPurgeFileRecordCache(a1);
      *(_DWORD *)(a1 + 4) |= 0x200u;
      NewRMGuid = ClfsMgmtInstallPolicy(*(PLOG_FILE_OBJECT *)(v8 + 496), &Policy, 0x18u);
      v52 = NewRMGuid;
      *(_DWORD *)(a1 + 4) &= ~0x200u;
      if ( NewRMGuid < 0 )
      {
        if ( !NtfsStatusDebugFlags
          || (unsigned int)NewRMGuid >= 0xFFFFFFED
          || NewRMGuid == -1073741802
          || NewRMGuid == -1073741807
          || (unsigned int)(NewRMGuid + 2147483643) <= 1
          || NewRMGuid == -1073741608 )
        {
          goto LABEL_221;
        }
        v22 = 2688275;
        goto LABEL_71;
      }
    }
    if ( (*v19 & 0x40) != 0 )
    {
      v25 = v63[5];
      v26 = ResultingSizeInContainers;
      if ( v25 )
      {
        Policy.Version = 1;
        Policy.LengthInBytes = 24;
        Policy.PolicyType = ClfsMgmtPolicyAutoShrink;
        Policy.PolicyParameters.NewContainerSuffix.NextContainerSuffix = v25;
        Policy.PolicyFlags = 1;
        NtfsPurgeFileRecordCache(a1);
        *(_DWORD *)(v26 + 4) |= 0x200u;
        v27 = v67;
        NewRMGuid = ClfsMgmtInstallPolicy(*(PLOG_FILE_OBJECT *)(v67 + 496), &Policy, 0x18u);
        v52 = NewRMGuid;
        *(_DWORD *)(v26 + 4) &= ~0x200u;
        if ( NewRMGuid < 0 )
        {
          if ( !NtfsStatusDebugFlags
            || (unsigned int)NewRMGuid >= 0xFFFFFFED
            || NewRMGuid == -1073741802
            || NewRMGuid == -1073741807
            || (unsigned int)(NewRMGuid + 2147483643) <= 1
            || NewRMGuid == -1073741608 )
          {
            goto LABEL_221;
          }
          v22 = 2688306;
          goto LABEL_71;
        }
      }
      else
      {
        NtfsPurgeFileRecordCache(a1);
        *(_DWORD *)(v26 + 4) |= 0x200u;
        v27 = v67;
        NewRMGuid = ClfsMgmtRemovePolicy(*(PLOG_FILE_OBJECT *)(v67 + 496), ClfsMgmtPolicyAutoShrink);
        v52 = NewRMGuid;
        *(_DWORD *)(v26 + 4) &= ~0x200u;
        if ( NewRMGuid < 0 )
        {
          if ( !NtfsStatusDebugFlags
            || (unsigned int)NewRMGuid >= 0xFFFFFFED
            || NewRMGuid == -1073741802
            || NewRMGuid == -1073741807
            || (unsigned int)(NewRMGuid + 2147483643) <= 1
            || NewRMGuid == -1073741608 )
          {
            goto LABEL_221;
          }
          v22 = 2688325;
LABEL_71:
          NtfsStatusTraceAndDebugInternal(0, NewRMGuid, v22);
          goto LABEL_221;
        }
      }
      v19 = v62;
    }
    else
    {
      v27 = v67;
    }
    v28 = *v19;
    v29 = *v19 & 0x800;
    if ( (*v19 & 0x400) != 0 || v29 )
    {
      NewSizeInContainers = 0;
      ResultingSizeInContainers = 0;
      NewSizeInContainers = (unsigned int)v63[3];
      if ( (v28 & 0x1000) != 0 && v29 )
        NewSizeInContainers = 0;
      NtfsPurgeFileRecordCache(a1);
      *(_DWORD *)(a1 + 4) |= 0x200u;
      NewRMGuid = ClfsMgmtSetLogFileSizeAsClient(
                    *(PLOG_FILE_OBJECT *)(v8 + 496),
                    *(PCLFS_MGMT_CLIENT *)(v8 + 560),
                    &NewSizeInContainers,
                    &ResultingSizeInContainers,
                    0,
                    0);
      v52 = NewRMGuid;
      *(_DWORD *)(a1 + 4) &= ~0x200u;
      if ( NtfsStatusDebugFlags
        && NewRMGuid
        && NewRMGuid != 294
        && (unsigned int)(NewRMGuid - 298) > 1
        && (unsigned int)NewRMGuid < 0xFFFFFFED
        && NewRMGuid != -1073741608
        && NewRMGuid != -1073741802
        && NewRMGuid != -1073741807
        && (unsigned int)(NewRMGuid + 2147483643) > 1
        && NewRMGuid != 259 )
      {
        NtfsStatusTraceAndDebugInternal(0, NewRMGuid, 0x290565u);
      }
    }
    v30 = *v19;
    if ( (*v19 & 1) != 0 )
    {
      if ( v8 == *(_QWORD *)(*(_QWORD *)(v8 + 16) + 6248LL) )
      {
        NewRMGuid = -1073741811;
        if ( !NtfsStatusDebugFlags )
          goto LABEL_28;
        v12 = 2688370;
        goto LABEL_27;
      }
      v31 = v63;
      if ( (unsigned __int16)(*((_WORD *)v63 + 16) - 1) > 1u )
      {
        NewRMGuid = -1073741811;
        if ( !NtfsStatusDebugFlags )
          goto LABEL_28;
        v12 = 2688377;
        goto LABEL_27;
      }
    }
    else
    {
      v31 = v63;
    }
    if ( (v30 & 0x2000) != 0 )
    {
      v32 = 0;
      v61 = 0;
      v59 = 0;
      v58 = 0;
      LODWORD(v62) = 0;
      v60 = 0;
      if ( (v30 & 0x84) != 0 )
      {
        v32 = 4;
        v61 = 4;
        v33 = v31[1];
        v59 = v33;
        if ( (v30 & 0x80u) != 0 )
          v33 = 0;
        v59 = v33;
      }
      if ( (v30 & 0x108) != 0 )
      {
        v32 |= 8u;
        v61 = v32;
        v34 = v31[2];
        v58 = v34;
        if ( (v30 & 0x100) != 0 )
          v34 = 0;
        v58 = v34;
      }
      if ( (v30 & 0x30) != 0 )
      {
        v32 |= 0x10u;
        v61 = v32;
        v35 = v31[4];
        LODWORD(v62) = v35;
        if ( (v30 & 0x20) != 0 )
          LODWORD(v62) = v35 | 0x80000000;
      }
      if ( (v30 & 0x40) != 0 && (unsigned int)v31[5] <= 0x64 )
      {
        v32 |= 0x40u;
        v61 = v32;
        v60 = *((_WORD *)v31 + 10);
      }
      if ( NewRMGuid == -1073741432 )
        NtfsCheckpointForLogFileFull(a1);
      NtfsAcquireExclusiveScbEx(a1, *(_QWORD *)(v8 + 288), 0);
      if ( (*v19 & 1) != 0 )
        v36 = (__int64)(v63 + 8);
      else
        v36 = 0;
      TxfUpdateTopsMetadataStream(
        a1,
        0,
        0,
        0,
        0,
        0,
        0,
        (unsigned __int64)&v59 & -(__int64)((v32 & 4) != 0),
        (unsigned __int64)&v58 & -(__int64)((v32 & 8) != 0),
        (unsigned __int64)&v62 & -(__int64)((v32 & 0x10) != 0),
        (unsigned __int64)&v60 & -(__int64)((v32 & 0x40) != 0),
        v36,
        0,
        0);
      NtfsCheckpointCurrentTransaction(a1);
      *(_DWORD *)(a1 + 4) |= 0x400u;
      NtfsCleanupIrpContext(a1, 0, v37);
      NewRMGuid = 0;
      v52 = 0;
      *(_DWORD *)(*(_QWORD *)(a1 + 144) + 24LL) = 0;
      v27 = v67;
    }
    if ( (*v19 & 1) == 0 )
      goto LABEL_221;
    v38 = *((_WORD *)v63 + 16) == 2;
    v50 = v38;
    if ( *((_WORD *)v63 + 16) != 2 )
      goto LABEL_184;
    if ( v8 != *(_QWORD *)(*(_QWORD *)(v8 + 16) + 6248LL) && (*(_DWORD *)(v8 + 128) & 0x10) != 0 )
    {
LABEL_185:
      NewRMGuid = 0;
LABEL_186:
      v52 = NewRMGuid;
      goto LABEL_222;
    }
    if ( *((_WORD *)v63 + 16) != 2 )
    {
LABEL_184:
      if ( v8 == *(_QWORD *)(*(_QWORD *)(v8 + 16) + 6248LL) || (*(_DWORD *)(v8 + 128) & 0x10) == 0 )
        goto LABEL_185;
    }
    v39 = *(_DWORD *)(v27 + 128);
    if ( *((_WORD *)v63 + 16) == 2 )
      v40 = v39 | 0x10;
    else
      v40 = v39 & 0xFFFFFFEF;
    *(_DWORD *)(v27 + 128) = v40;
    v55 = 1;
    while ( 1 )
    {
      if ( !v51 )
      {
        ExAcquireResourceSharedLite(*(PERESOURCE *)(v8 + 160), 1u);
        v51 = 1;
      }
      if ( v69 )
      {
        if ( v53 )
        {
          v66[0] = v69;
          v53 = 0;
        }
        v42 = *(_QWORD *)(v69 + 104);
        v41 = v42;
        v69 = v42;
        v43 = v42;
      }
      else
      {
        v41 = *(_QWORD *)(v8 + 152);
        v69 = v41;
        v42 = v41;
        v43 = v41;
      }
      if ( !v42 )
        goto LABEL_221;
      ExAcquireResourceExclusiveLite((PERESOURCE)(*(_QWORD *)(v43 + 24) + 80LL), 1u);
      ++*(_DWORD *)(v43 + 4);
      v53 = 1;
      if ( (*(_DWORD *)(v43 + 16) & 0x20000) == 0
        || (v56 = 1, TxfWaitForEnlistmentCompletion(0, v41, &v56, v8 + 144, &v51), v56) )
      {
        ExReleaseResourceLite((PERESOURCE)(*(_QWORD *)(v43 + 24) + 80LL));
      }
      if ( v51 )
      {
        ExReleaseResourceLite(*(PERESOURCE *)(v8 + 160));
        v51 = 0;
      }
      if ( v66[0] )
        TxfDereferenceTransaction(v66, 0);
      if ( *(_QWORD *)(v43 + 232) )
      {
        v38 = v50;
        v44 = TxfTransSwitchLoggingMode(v41, v50);
        v52 = v44;
        if ( (unsigned int)(v44 + 1072103403) > 1 && v44 != -1073741431 && v44 < 0 )
        {
          if ( (!a1 || (*(_DWORD *)(a1 + 16) & 0x100000) == 0)
            && (Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits & 0x8000000) != 0 )
          {
            LODWORD(plsn1) = v44;
            McTemplateU0spjpjd_EtwWriteTransfer(
              v8 + 672,
              (const EVENT_DESCRIPTOR *)txfctrl_c1700,
              "TxfFsctlModifyRm",
              v8,
              v8 + 672,
              v41,
              v41 + 256,
              plsn1);
          }
          NewRMGuid = TxfTryAbortTransaction(a1, v8, (_QWORD *)v41, 0, 0);
          v52 = NewRMGuid;
          if ( NewRMGuid < 0 )
          {
            if ( (*(_DWORD *)(v41 + 16) & 1) != 0 )
            {
              NewRMGuid = -1073741670;
              if ( NtfsStatusDebugFlags )
                NtfsStatusTraceAndDebugInternal(0, 0xC000009A, 0x2906BEu);
              goto LABEL_186;
            }
            NewRMGuid = TxfTryAbortTransaction(a1, v8, (_QWORD *)v41, 0, 0);
            v52 = NewRMGuid;
          }
          if ( (unsigned int)(NewRMGuid + 1072103403) > 1 )
            goto LABEL_222;
        }
        NewRMGuid = 0;
        v52 = 0;
      }
    }
  }
  if ( (*v62 & 0xFFFF3FFF) == 0 )
  {
    v54 = 1;
    goto LABEL_30;
  }
  NewRMGuid = -1072103419;
  if ( NtfsStatusDebugFlags )
  {
    v12 = 2687910;
LABEL_27:
    NtfsStatusTraceAndDebugInternal(0, NewRMGuid, v12);
  }
LABEL_28:
  v52 = NewRMGuid;
LABEL_221:
  v38 = v50;
LABEL_222:
  if ( v51 )
    ExReleaseResourceLite(*(PERESOURCE *)(v8 + 160));
  if ( v66[0] )
    TxfDereferenceTransaction(v66, 0);
  if ( v53 )
    TxfDereferenceTransaction(&v69, 0);
  if ( v55 && NewRMGuid < 0 )
  {
    v45 = *(_DWORD *)(v67 + 128);
    if ( v38 )
      v46 = v45 & 0xFFFFFFEF;
    else
      v46 = v45 | 0x10;
    *(_DWORD *)(v67 + 128) = v46;
  }
  ExReleaseResourceLite((PERESOURCE)(*(_QWORD *)(v8 + 24) + 912LL));
  return (unsigned int)NewRMGuid;
}

```

## disassembly

```asm
0x1400fc090  mov     r11, rsp
0x1400fc093  push    rbx
0x1400fc094  push    rsi
0x1400fc095  push    rdi
0x1400fc096  push    r12
0x1400fc098  push    r13
0x1400fc09a  push    r14
0x1400fc09c  push    r15
0x1400fc09e  sub     rsp, 140h
0x1400fc0a5  mov     rax, cs:__security_cookie
0x1400fc0ac  xor     rax, rsp
0x1400fc0af  mov     [rsp+178h+var_40], rax
0x1400fc0b7  mov     [rsp+178h+var_C8], r9
0x1400fc0bf  mov     r10, rdx
0x1400fc0c2  mov     [rsp+178h+NewSizeInContainers], rdx
0x1400fc0ca  mov     rsi, rcx
0x1400fc0cd  mov     [rsp+178h+var_78], r9
0x1400fc0d5  mov     [rsp+178h+var_A0], rcx
0x1400fc0dd  mov     qword ptr [rsp+178h+var_50], rdx
0x1400fc0e5  mov     [rsp+178h+var_C0], r9
0x1400fc0ed  xorps   xmm0, xmm0
0x1400fc0f0  xor     eax, eax
0x1400fc0f2  movups  xmmword ptr [r11-68h], xmm0
0x1400fc0f7  mov     [r11-58h], rax
0x1400fc0fb  xor     edi, edi
0x1400fc0fd  mov     [r11-88h], rdi
0x1400fc104  mov     [r11-0A8h], rdi
0x1400fc10b  mov     [rsp+178h+var_E7], dil
0x1400fc113  mov     r13d, edi
0x1400fc116  mov     dword ptr [rsp+178h+var_B8], edi
0x1400fc11d  mov     dword ptr [rsp+178h+var_DC], edi
0x1400fc124  test    r9, r9
0x1400fc127  jz      loc_1400FD4A6
0x1400fc12d  cmp     r8d, 28h ; '('
0x1400fc131  jb      loc_1400FD4A6
0x1400fc137  mov     edx, [r9]
0x1400fc13a  test    edx, 0FFFC0200h
0x1400fc140  jnz     loc_1400FD486
0x1400fc146  test    edx, edx
0x1400fc148  jz      loc_1400FD486
0x1400fc14e  mov     eax, edx
0x1400fc150  and     eax, 84h
0x1400fc155  cmp     al, 84h
0x1400fc157  jz      loc_1400FD474
0x1400fc15d  mov     eax, edx
0x1400fc15f  and     eax, 108h
0x1400fc164  cmp     eax, 108h
0x1400fc169  jz      loc_1400FD474
0x1400fc16f  mov     eax, edx
0x1400fc171  mov     ecx, 0C00h
0x1400fc176  and     eax, ecx
0x1400fc178  cmp     eax, ecx
0x1400fc17a  setz    cl
0x1400fc17d  mov     eax, edx
0x1400fc17f  and     eax, 30h
0x1400fc182  cmp     al, 30h ; '0'
0x1400fc184  setz    al
0x1400fc187  or      cl, al
0x1400fc189  jnz     loc_1400FD474
0x1400fc18f  mov     eax, edx
0x1400fc191  and     eax, 4000h
0x1400fc196  mov     r12d, 8000h
0x1400fc19c  jz      short loc_1400FC1A7
0x1400fc19e  test    r12d, edx
0x1400fc1a1  jnz     loc_1400FD474
0x1400fc1a7  mov     ecx, edx
0x1400fc1a9  and     ecx, 10000h
0x1400fc1af  jz      short loc_1400FC1BB
0x1400fc1b1  bt      edx, 11h
0x1400fc1b5  jb      loc_1400FD474
0x1400fc1bb  mov     r15, [r10+140h]
0x1400fc1c2  mov     [rsp+178h+var_90], r15
0x1400fc1ca  test    eax, eax
0x1400fc1cc  jnz     short loc_1400FC1D3
0x1400fc1ce  test    r12d, edx
0x1400fc1d1  jz      short loc_1400FC1F9
0x1400fc1d3  mov     rax, [r15+10h]
0x1400fc1d7  cmp     r15, [rax+1868h]
0x1400fc1de  jz      short loc_1400FC1F9
0x1400fc1e0  mov     al, cs:NtfsStatusDebugFlags
0x1400fc1e6  test    al, al
0x1400fc1e8  jz      loc_1400FD4B8
0x1400fc1ee  mov     r8d, 290382h
0x1400fc1f4  jmp     loc_1400FD496
0x1400fc1f9  mov     [rsp+178h+ResultingSizeInContainers], rsi
0x1400fc201  mov     ebx, edi
0x1400fc203  mov     [rsp+178h+var_E4], ebx
0x1400fc20a  mov     [rsp+178h+var_98], r15
0x1400fc212  mov     [rsp+178h+var_E0], dil
0x1400fc21a  mov     [rsp+178h+var_E8], dil
0x1400fc222  mov     [rsp+178h+var_DE], dil
0x1400fc22a  mov     [rsp+178h+var_DF], dil
0x1400fc232  test    ecx, ecx
0x1400fc234  jnz     short loc_1400FC23C
0x1400fc236  bt      edx, 11h
0x1400fc23a  jnb     short loc_1400FC276
0x1400fc23c  mov     rax, [r15+10h]
0x1400fc240  cmp     r15, [rax+1868h]
0x1400fc247  jnz     short loc_1400FC276
0x1400fc249  mov     rax, [rax+0F8h]
0x1400fc250  mov     rcx, [rax+10h]
0x1400fc254  test    dword ptr [rcx+30h], 100h
0x1400fc25b  jz      short loc_1400FC276
0x1400fc25d  mov     al, cs:NtfsStatusDebugFlags
0x1400fc263  test    al, al
0x1400fc265  jz      loc_1400FD4B8
0x1400fc26b  mov     r8d, 29038Fh
0x1400fc271  jmp     loc_1400FD496
0x1400fc276  mov     rcx, [r15+18h]
0x1400fc27a  add     rcx, 390h; Resource
0x1400fc281  mov     r14d, 1
0x1400fc287  mov     dl, r14b; Wait
0x1400fc28a  call    cs:__imp_ExAcquireResourceExclusiveLite
0x1400fc291  nop     dword ptr [rax+rax+00h]
0x1400fc296  lea     r9d, [r14+3]
0x1400fc29a  mov     eax, r9d
0x1400fc29d  lock cmpxchg [r15+84h], r9d
0x1400fc2a6  lea     r10d, [r14+1]
0x1400fc2aa  mov     rdx, [rsp+178h+var_C8]
0x1400fc2b2  cmp     eax, r10d
0x1400fc2b5  jz      short loc_1400FC2F1
0x1400fc2b7  test    dword ptr [rdx], 0FFFF3FFFh
0x1400fc2bd  jz      short loc_1400FC2E9
0x1400fc2bf  mov     al, cs:NtfsStatusDebugFlags
0x1400fc2c5  mov     ebx, 0C0190005h
0x1400fc2ca  test    al, al
0x1400fc2cc  jz      short loc_1400FC2DD
0x1400fc2ce  mov     r8d, 2903A6h
0x1400fc2d4  mov     edx, ebx
0x1400fc2d6  xor     ecx, ecx
0x1400fc2d8  call    NtfsStatusTraceAndDebugInternal
0x1400fc2dd  mov     [rsp+178h+var_E4], ebx
0x1400fc2e4  jmp     loc_1400FD3D5
0x1400fc2e9  mov     [rsp+178h+var_DF], r14b
0x1400fc2f1  mov     rax, [rsp+178h+NewSizeInContainers]
0x1400fc2f9  mov     rax, [rax+60h]
0x1400fc2fd  test    dword ptr [rax+4], 2000000h
0x1400fc304  jz      short loc_1400FC31D
0x1400fc306  mov     al, cs:NtfsStatusDebugFlags
0x1400fc30c  mov     ebx, 0C00000A2h
0x1400fc311  test    al, al
0x1400fc313  jz      short loc_1400FC2DD
0x1400fc315  mov     r8d, 2903B8h
0x1400fc31b  jmp     short loc_1400FC2D4
0x1400fc31d  mov     eax, [rdx]
0x1400fc31f  bt      eax, 0Eh
0x1400fc323  mov     ecx, edi
0x1400fc325  mov     edx, 200000h
0x1400fc32a  cmovb   ecx, edx
0x1400fc32d  mov     [rsp+178h+var_D4], ecx
0x1400fc334  mov     [rsp+178h+var_80], ecx
0x1400fc33b  test    r12d, eax
0x1400fc33e  mov     r8d, edi
0x1400fc341  cmovnz  r8d, edx
0x1400fc345  mov     dword ptr [rsp+178h+var_DC+4], r8d
0x1400fc34d  mov     [rsp+178h+var_7C], r8d
0x1400fc355  bt      eax, 10h
0x1400fc359  jnb     short loc_1400FC376
0x1400fc35b  mov     r13d, r9d
0x1400fc35e  mov     dword ptr [rsp+178h+var_B8], r9d
0x1400fc366  mov     r12d, 8
0x1400fc36c  mov     dword ptr [rsp+178h+var_DC], r12d
0x1400fc374  jmp     short loc_1400FC37E
0x1400fc376  mov     r12d, dword ptr [rsp+178h+var_DC]
0x1400fc37e  bt      eax, 11h
0x1400fc382  jnb     short loc_1400FC39B
0x1400fc384  or      r13d, 8
0x1400fc388  mov     dword ptr [rsp+178h+var_B8], r13d
0x1400fc390  or      r12d, r9d
0x1400fc393  mov     dword ptr [rsp+178h+var_DC], r12d
0x1400fc39b  test    ecx, ecx
0x1400fc39d  jnz     short loc_1400FC3A8
0x1400fc39f  test    r8d, r8d
0x1400fc3a2  jz      loc_1400FC4EC
0x1400fc3a8  cmp     ebx, 0C0000188h
0x1400fc3ae  jnz     short loc_1400FC3B8
0x1400fc3b0  mov     rcx, rsi
0x1400fc3b3  call    NtfsCheckpointForLogFileFull
0x1400fc3b8  xor     r9d, r9d
0x1400fc3bb  xor     r8d, r8d
0x1400fc3be  mov     rdx, [rsp+178h+NewSizeInContainers]
0x1400fc3c6  mov     rcx, rsi
0x1400fc3c9  call    NtfsAcquireExclusiveFcb
0x1400fc3ce  mov     [rsp+178h+var_118], rdi; __int64
0x1400fc3d3  mov     [rsp+178h+var_120], rdi; __int64
0x1400fc3d8  mov     [rsp+178h+var_128], rdi; __int64
0x1400fc3dd  mov     [rsp+178h+var_130], rdi; __int64
0x1400fc3e2  mov     [rsp+178h+var_138], rdi; __int64
0x1400fc3e7  mov     [rsp+178h+plsn1], rdi; __int64
0x1400fc3ec  mov     eax, dword ptr [rsp+178h+var_DC+4]
0x1400fc3f3  mov     dword ptr [rsp+178h+var_148], eax; int
0x1400fc3f7  mov     eax, [rsp+178h+var_D4]
0x1400fc3fe  mov     dword ptr [rsp+178h+CompletionRoutineData], eax; int
0x1400fc402  mov     rdx, [rsp+178h+NewSizeInContainers]; int
0x1400fc40a  mov     rcx, rsi; int
0x1400fc40d  call    TxfUpdateTxfDataAttributeMembers
0x1400fc412  cmp     [rsp+178h+var_DF], dil
0x1400fc41a  jnz     short loc_1400FC426
0x1400fc41c  test    r13d, r13d
0x1400fc41f  jnz     short loc_1400FC446
0x1400fc421  test    r12d, r12d
0x1400fc424  jnz     short loc_1400FC446
0x1400fc426  mov     rcx, rsi
0x1400fc429  call    NtfsCheckpointCurrentTransaction
0x1400fc42e  bts     dword ptr [rsi+4], 0Ah
0x1400fc433  xor     edx, edx
0x1400fc435  mov     rcx, rsi
0x1400fc438  call    NtfsCleanupIrpContext
0x1400fc43d  mov     ebx, edi
0x1400fc43f  mov     [rsp+178h+var_E4], ebx
0x1400fc446  mov     r10d, 2
0x1400fc44c  jmp     short loc_1400FC4C2
0x1400fc44e  mov     r8d, eax
0x1400fc451  xor     edx, edx
0x1400fc453  mov     rsi, [rsp+178h+var_A0]
0x1400fc45b  mov     rcx, rsi
0x1400fc45e  call    NtfsProcessException
0x1400fc463  mov     ebx, eax
0x1400fc465  mov     [rsp+178h+var_E4], eax
0x1400fc46c  xor     edi, edi
0x1400fc46e  lea     r14d, [rdi+1]
0x1400fc472  lea     r10d, [rdi+2]
0x1400fc476  mov     r15, [rsp+178h+var_90]
0x1400fc47e  mov     eax, [rsp+178h+var_80]
0x1400fc485  mov     [rsp+178h+var_D4], eax
0x1400fc48c  mov     eax, [rsp+178h+var_7C]
0x1400fc493  mov     dword ptr [rsp+178h+var_DC+4], eax
0x1400fc49a  mov     r13d, dword ptr [rsp+178h+var_B8]
0x1400fc4a2  mov     rax, qword ptr [rsp+178h+var_50]
0x1400fc4aa  mov     [rsp+178h+NewSizeInContainers], rax
0x1400fc4b2  mov     rdx, [rsp+178h+var_78]
0x1400fc4ba  mov     [rsp+178h+var_C8], rdx
0x1400fc4c2  mov     rax, [rsi+90h]
0x1400fc4c9  mov     [rax+18h], edi
0x1400fc4cc  cmp     ebx, 0C0000188h
0x1400fc4d2  mov     r12d, dword ptr [rsp+178h+var_DC]
0x1400fc4da  jz      loc_1400FC3A8
0x1400fc4e0  cmp     ebx, 0C00000D8h
0x1400fc4e6  jz      loc_1400FC3A8
0x1400fc4ec  cmp     [rsp+178h+var_DF], dil
0x1400fc4f4  jnz     loc_1400FD3D5
0x1400fc4fa  test    ebx, ebx
0x1400fc4fc  js      loc_1400FD3D5
0x1400fc502  test    r13d, r13d
0x1400fc505  jnz     short loc_1400FC515
0x1400fc507  cmp     dword ptr [rsp+178h+var_DC], r13d
0x1400fc50f  jz      loc_1400FC62A
0x1400fc515  cmp     ebx, 0C0000188h
0x1400fc51b  jnz     short loc_1400FC525
0x1400fc51d  mov     rcx, rsi
0x1400fc520  call    NtfsCheckpointForLogFileFull
0x1400fc525  xor     r8d, r8d
0x1400fc528  mov     rdx, [r15+120h]
0x1400fc52f  mov     rcx, rsi
0x1400fc532  call    NtfsAcquireExclusiveScbEx
0x1400fc537  lea     rax, [rsp+178h+var_DC]
0x1400fc53f  mov     [rsp+178h+var_F8], rax; __int64
0x1400fc547  lea     rax, [rsp+178h+var_B8]
0x1400fc54f  mov     [rsp+178h+var_100], rax; __int64
0x1400fc554  mov     [rsp+178h+var_108], rdi; __int64
0x1400fc559  mov     [rsp+178h+var_110], rdi; __int64
0x1400fc55e  mov     [rsp+178h+var_118], rdi; __int64
0x1400fc563  mov     [rsp+178h+var_120], rdi; __int64
0x1400fc568  mov     [rsp+178h+var_128], rdi; __int64
0x1400fc56d  mov     [rsp+178h+var_130], rdi; __int64
0x1400fc572  mov     [rsp+178h+var_138], rdi; __int64
0x1400fc577  mov     [rsp+178h+plsn1], rdi; plsn1
0x1400fc57c  mov     [rsp+178h+var_148], rdi; __int64
0x1400fc581  mov     [rsp+178h+CompletionRoutineData], rdi; __int64
0x1400fc586  mov     [rsp+178h+CompletionRoutine], rdi; __int64
0x1400fc58b  xor     r9d, r9d
0x1400fc58e  xor     r8d, r8d
0x1400fc591  mov     rdx, [r15+120h]
0x1400fc598  mov     rcx, rsi; int
0x1400fc59b  call    TxfUpdateTopsMetadataStream
0x1400fc5a0  mov     rcx, rsi
0x1400fc5a3  call    NtfsCheckpointCurrentTransaction
0x1400fc5a8  bts     dword ptr [rsi+4], 0Ah
0x1400fc5ad  xor     edx, edx
0x1400fc5af  mov     rcx, rsi
0x1400fc5b2  call    NtfsCleanupIrpContext
0x1400fc5b7  mov     ebx, edi
0x1400fc5b9  mov     [rsp+178h+var_E4], ebx
0x1400fc5c0  mov     r10d, 2
0x1400fc5c6  jmp     short loc_1400FC608
0x1400fc5c8  mov     r8d, eax
0x1400fc5cb  xor     edx, edx
0x1400fc5cd  mov     rsi, [rsp+178h+var_A0]
0x1400fc5d5  mov     rcx, rsi
0x1400fc5d8  call    NtfsProcessException
0x1400fc5dd  mov     ebx, eax
0x1400fc5df  mov     [rsp+178h+var_E4], eax
0x1400fc5e6  xor     edi, edi
0x1400fc5e8  lea     r14d, [rdi+1]
0x1400fc5ec  lea     r10d, [rdi+2]
0x1400fc5f0  mov     r15, [rsp+178h+var_90]
0x1400fc5f8  mov     rdx, [rsp+178h+var_78]
0x1400fc600  mov     [rsp+178h+var_C8], rdx
0x1400fc608  mov     rax, [rsi+90h]
0x1400fc60f  mov     [rax+18h], edi
  ... truncated ...
```
