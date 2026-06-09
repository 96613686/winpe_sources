# NtfsCommonVolumeOpen

- ea: `0x1401a0dd0`
- end: `0x1401a1daf`
- name: `NtfsCommonVolumeOpen`
- size: `4063`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `2`
- callee_count: `32`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x140015d10`
- `0x1401a1dc0`

## callees

- `0x140007ea0`
- `0x1400082b0`
- `0x14000c1d0`
- `0x14000c290`
- `0x14000d1e0`
- `0x140010be0`
- `0x140012e70`
- `0x14001c2e0`
- `0x14001e810`
- `0x140020de0`
- `0x14003c34c`
- `0x14003e734`
- `0x140044708`
- `0x14004480c`
- `0x14004f03c`
- `0x140059250`
- `0x1400596c0`
- `0x1400b454c`
- `0x1400dfe70`
- `0x14013af10`
- `0x140140380`
- `0x1401841d0`
- `0x140184e80`
- `0x140185c00`
- `0x14019ca80`
- `0x1401a0dd0`
- `0x1401aab20`
- `0x1401d2c34`
- `0x1401f1d30`
- `0x1402058c0`
- `0x140230888`
- `0x1402329dc`

## import_xrefs

- `ntoskrnl!FsRtlNotifyVolumeEvent` at `0x1401a0fee`
- `ntoskrnl!FsRtlNotifyVolumeEvent` at `0x1401a1c28`
- `ntoskrnl!FsRtlNotifyVolumeEvent` at `0x1402acdd2`
- `ntoskrnl!FsRtlNotifyVolumeEvent` at `0x1401a0fee`
- `ntoskrnl!FsRtlNotifyVolumeEvent` at `0x1401a1c28`
- `ntoskrnl!FsRtlNotifyVolumeEvent` at `0x1402acdd2`
- `ntoskrnl!FsRtlAreVolumeStartupApplicationsComplete` at `0x1401a122e`
- `ntoskrnl!FsRtlAreVolumeStartupApplicationsComplete` at `0x1401a122e`
- `ntoskrnl!CcWaitForCurrentLazyWriterActivity` at `0x1401a153f`
- `ntoskrnl!CcWaitForCurrentLazyWriterActivity` at `0x1401a153f`
- `ntoskrnl!ObGetObjectSecurity` at `0x1401a1a53`
- `ntoskrnl!ObGetObjectSecurity` at `0x1401a1a53`
- `ntoskrnl!ObReleaseObjectSecurity` at `0x1401a1ab1`
- `ntoskrnl!ObReleaseObjectSecurity` at `0x1401a1ab1`
- `ntoskrnl!KeWaitForSingleObject` at `0x1401a0fda`
- `ntoskrnl!KeWaitForSingleObject` at `0x1401a0fda`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401a1863`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401a1863`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1401a1849`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1401a1849`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401a1bfc`
- `ntoskrnl!ExReleaseResourceLite` at `0x1402acd95`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401a1bfc`
- `ntoskrnl!ExReleaseResourceLite` at `0x1402acd95`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x1401a103b`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x1401a103b`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsGetLogFileInformation` at `0x1401a131d`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsGetLogFileInformation` at `0x1401a131d`

## pseudocode

```c
__int64 __fastcall NtfsCommonVolumeOpen(__int64 a1, __int64 a2)
{
  BOOL v2; // edi
  __int64 v4; // rsi
  __int64 v5; // r13
  PFILE_OBJECT v6; // rbx
  int v7; // r9d
  int LogFileInformation; // edi
  unsigned __int8 v9; // r15
  unsigned int v10; // r8d
  __int64 v11; // r8
  __int64 v12; // rcx
  __int64 v13; // rax
  __int64 v14; // r8
  __int64 v15; // rcx
  _DWORD *v16; // rbx
  int v17; // r9d
  __int64 v18; // rdx
  unsigned int v19; // eax
  unsigned int v20; // r8d
  int v21; // eax
  int v22; // ebx
  __int64 v23; // rax
  __int64 v24; // rax
  FILE_OBJECT *v25; // rdi
  __int64 v26; // r10
  unsigned int v27; // eax
  unsigned __int16 v28; // cx
  __int64 v29; // rcx
  int v30; // eax
  int v31; // edx
  int v32; // r8d
  bool v33; // cl
  __int64 v34; // rdx
  __int64 v35; // r8
  int v36; // r9d
  __int64 v37; // rdx
  unsigned int v38; // eax
  int v39; // eax
  int v40; // edx
  int v41; // r8d
  __int64 v42; // r10
  unsigned int v43; // eax
  PFILE_OBJECT v44; // rdi
  PWSTR Buffer; // rbx
  __int64 v46; // rcx
  __int64 v47; // r13
  __int64 v48; // rbx
  __int64 v49; // r8
  __int64 v50; // rcx
  char v51; // r13
  BOOL v52; // ecx
  IRP *v53; // rax
  PLARGE_INTEGER Timeout; // [rsp+20h] [rbp-1D8h]
  PLARGE_INTEGER Timeouta; // [rsp+20h] [rbp-1D8h]
  __int64 v57; // [rsp+30h] [rbp-1C8h]
  __int64 v58; // [rsp+40h] [rbp-1B8h]
  char v59; // [rsp+82h] [rbp-176h]
  char v60; // [rsp+83h] [rbp-175h]
  unsigned __int8 MemoryAllocated; // [rsp+84h] [rbp-174h] BYREF
  char v62; // [rsp+85h] [rbp-173h]
  char v63; // [rsp+86h] [rbp-172h]
  char v64; // [rsp+87h] [rbp-171h]
  int v65; // [rsp+88h] [rbp-170h]
  char v66; // [rsp+8Ch] [rbp-16Ch]
  PFILE_OBJECT FileObject; // [rsp+90h] [rbp-168h]
  BOOL v68; // [rsp+98h] [rbp-160h]
  __int64 v69; // [rsp+A0h] [rbp-158h] BYREF
  _QWORD *v70; // [rsp+A8h] [rbp-150h]
  char v71; // [rsp+B0h] [rbp-148h]
  int v72; // [rsp+B4h] [rbp-144h]
  IRP *v73; // [rsp+B8h] [rbp-140h]
  __int64 v74; // [rsp+C0h] [rbp-138h]
  ULONG pcbInfoBuffer; // [rsp+C8h] [rbp-130h] BYREF
  __int64 v76; // [rsp+D0h] [rbp-128h]
  int v77; // [rsp+D8h] [rbp-120h]
  unsigned int v78; // [rsp+DCh] [rbp-11Ch]
  unsigned int v79; // [rsp+E0h] [rbp-118h]
  ACCESS_MASK v80; // [rsp+E4h] [rbp-114h] BYREF
  PSECURITY_DESCRIPTOR SecurityDescriptor[2]; // [rsp+E8h] [rbp-110h] BYREF
  __int16 v82; // [rsp+F8h] [rbp-100h]
  __int64 v83; // [rsp+100h] [rbp-F8h]
  unsigned __int16 v84; // [rsp+108h] [rbp-F0h]
  __int64 v85; // [rsp+110h] [rbp-E8h]
  __int16 v86; // [rsp+118h] [rbp-E0h]
  __int64 v87; // [rsp+120h] [rbp-D8h]
  __int16 v88; // [rsp+128h] [rbp-D0h]
  __int64 v89; // [rsp+130h] [rbp-C8h]
  CLFS_INFORMATION pinfoBuffer; // [rsp+140h] [rbp-B8h] BYREF

  v73 = (IRP *)a2;
  v76 = a1;
  v65 = -1073741823;
  v4 = 0;
  v74 = 0;
  v70 = 0;
  v69 = 0;
  v59 = 0;
  v60 = 0;
  v62 = 0;
  v66 = 0;
  v63 = 0;
  LOBYTE(v2) = 0;
  v68 = v2;
  MemoryAllocated = 0;
  v64 = 0;
  v5 = *(_QWORD *)(a2 + 184);
  v6 = *(PFILE_OBJECT *)(v5 + 48);
  FileObject = v6;
  SecurityDescriptor[1] = v6;
  *(_DWORD *)(a1 + 504) = 26;
  v7 = *(unsigned __int8 *)(v5 + 19);
  if ( ((v7 - 1) & 0xFFFFFFFD) != 0 )
  {
    if ( (*(_DWORD *)(a1 + 16) & 0x100000) == 0
      && (Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits & 0x20) != 0 )
    {
      McTemplateU0pd_EtwWriteTransfer(a1, (const EVENT_DESCRIPTOR *)create_c5645, (__int64)KeGetCurrentThread(), v7);
    }
    LogFileInformation = -1073741790;
    if ( NtfsStatusDebugFlags )
      NtfsStatusTraceAndDebugInternal(0, 0xC0000022, 0xA1615u);
    v65 = -1073741790;
    v9 = 1;
    goto LABEL_148;
  }
  v9 = 1;
  if ( (*(_DWORD *)(v5 + 16) & 1) != 0 )
  {
    LogFileInformation = -1073741811;
    if ( !NtfsStatusDebugFlags )
    {
LABEL_12:
      v65 = LogFileInformation;
      goto LABEL_148;
    }
    v10 = 661023;
LABEL_11:
    NtfsStatusTraceAndDebugInternal(0, LogFileInformation, v10);
    goto LABEL_12;
  }
  if ( TxfGetTransactionFromFileObject(*(_QWORD *)(v5 + 48), 0) )
  {
    LogFileInformation = -1072103334;
    if ( !NtfsStatusDebugFlags )
      goto LABEL_12;
    v10 = 661040;
    goto LABEL_11;
  }
  v12 = *(_QWORD *)(a1 + 104);
  if ( (*(_DWORD *)(v12 + 6436) & 2) != 0 )
  {
    v13 = *(_QWORD *)(v12 + 6248);
    if ( v13 )
    {
      if ( (*(_DWORD *)(v13 + 136) & 0x4000) != 0 && (*(_DWORD *)(a1 + 436) & 0x100000) == 0 )
        TxfParkRequest(a1, *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(a1 + 104) + 6248LL) + 24LL) + 1280LL, 0);
    }
  }
  v4 = *(_QWORD *)(a1 + 104);
  v74 = v4;
  if ( (*(_BYTE *)(v5 + 26) & 6) != 0 )
  {
    LOBYTE(v11) = 1;
    NtfsAcquireSharedVcb(a1, v4, v11);
  }
  else
  {
    KeWaitForSingleObject((PVOID)(v4 + 6632), Executive, 0, 0, 0);
    FsRtlNotifyVolumeEvent(v6, 3u);
    v63 = 1;
    NtfsFspCloseInternal(0, v4, 1, 0, 0);
    if ( (*(_DWORD *)(v4 + 6436) & 2) != 0 )
    {
      v15 = *(_QWORD *)(v4 + 6248);
      if ( v15 )
      {
        ExAcquireResourceSharedLite((PERESOURCE)(*(_QWORD *)(v15 + 24) + 912LL), 1u);
        v62 = 1;
      }
    }
    LOBYTE(v14) = 1;
    NtfsAcquireExclusiveVcb(a1, v4, v14);
    *(_BYTE *)(v4 + 5521) = 1;
    v64 = 1;
  }
  v59 = 1;
  v16 = (_DWORD *)(v4 + 4);
  v17 = *(_DWORD *)(v4 + 4);
  if ( (v17 & 0x802) != 0 )
  {
    if ( (*(_DWORD *)(a1 + 16) & 0x100000) == 0
      && (Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits & 0x20) != 0 )
    {
      v18 = *(_QWORD *)(v4 + 248);
      v19 = *(unsigned __int16 *)(v18 + 6);
      if ( v19 > 0x40 || (v19 & 1) != 0 )
        v19 = 0;
      v68 = v19;
      v82 = v19;
      v83 = v18 + 32;
      LODWORD(Timeout) = *(unsigned __int16 *)(v4 + 7872) >> 1;
      McTemplateU0ppwwd_EtwWriteTransfer(
        (unsigned int)Timeout,
        (const EVENT_DESCRIPTOR *)create_c5763,
        KeGetCurrentThread(),
        v4,
        Timeout,
        *(_QWORD *)(v4 + 7880),
        (unsigned __int16)v19 >> 1,
        v18 + 32,
        v17);
    }
    LogFileInformation = -1073741790;
    if ( !NtfsStatusDebugFlags )
      goto LABEL_36;
    v20 = 661134;
    goto LABEL_35;
  }
  if ( !(unsigned __int8)NtfsPingVolume(a1, v4, 0) || (*v16 & 1) == 0 )
  {
    *(_DWORD *)(a1 + 4) |= 0x200000u;
    NtfsRaiseStatusInternal(a1, -1073741608, 0, 0, 661165);
  }
  v70 = *(_QWORD **)(*(_QWORD *)(v4 + 192) + 184LL);
  NtfsAcquireExclusiveFcb(a1, (__int64)v70, 0, 0);
  NtfsAccessCheck(
    a1,
    0,
    v70,
    0,
    (__int64)v73,
    *(_DWORD *)(v73->Tail.Overlay.CurrentStackLocation->Parameters.WMI.ProviderId + 16),
    0,
    0,
    0);
  NtfsReleaseFcbEx(a1, (__int64)v70, 0);
  v60 = 0;
  v21 = *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(v5 + 8) + 8LL) + 20LL);
  if ( (*(_BYTE *)(v5 + 26) & 6) != 0 )
  {
    if ( (v21 & 7) != 0 )
      v68 = (*v16 & 0x2000000) == 0;
    goto LABEL_124;
  }
  if ( (v21 & 6) != 0 )
  {
    MemoryAllocated = 1;
    v71 = 1;
    if ( FsRtlAreVolumeStartupApplicationsComplete() )
      *(_WORD *)(v5 + 26) &= ~1u;
  }
  if ( (*(_BYTE *)(v5 + 26) & 1) == 0 )
  {
    v22 = 0;
    v72 = 0;
    v23 = *(_QWORD *)(v4 + 168);
    if ( v23 )
    {
      v22 = *(_DWORD *)(v23 + 208);
      v72 = v22;
    }
    if ( v62
      && (_InterlockedCompareExchange((volatile signed __int32 *)(*(_QWORD *)(v4 + 6248) + 132LL), 4, 4) == 2
       || _InterlockedCompareExchange((volatile signed __int32 *)(*(_QWORD *)(v4 + 6248) + 132LL), 4, 4) == 1) )
    {
      v24 = *(_QWORD *)(v4 + 6248);
      if ( *(_QWORD *)(v24 + 72) )
        v72 = ++v22;
      v25 = *(FILE_OBJECT **)(v24 + 496);
      if ( v25 )
      {
        memset(&pinfoBuffer, 0, sizeof(pinfoBuffer));
        pcbInfoBuffer = 120;
        LogFileInformation = ClfsGetLogFileInformation(v25, &pinfoBuffer, &pcbInfoBuffer);
        v65 = LogFileInformation;
        if ( LogFileInformation < 0 )
        {
          if ( NtfsStatusDebugFlags
            && (unsigned int)LogFileInformation < 0xFFFFFFED
            && LogFileInformation != -1073741802
            && (unsigned int)(LogFileInformation + 2147483643) > 1
            && LogFileInformation != -1073741807
            && LogFileInformation != -1073741608 )
          {
            NtfsStatusTraceAndDebugInternal(0, LogFileInformation, 0xA1718u);
          }
          goto LABEL_147;
        }
        v22 += pinfoBuffer.TotalContainers + 1;
        v72 = v22;
      }
    }
    if ( *(_DWORD *)(v4 + 256) != v22 )
    {
      if ( (*(_DWORD *)(a1 + 16) & 0x100000) == 0
        && (Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits & 0x8000) != 0 )
      {
        v26 = *(_QWORD *)(v4 + 248);
        v27 = *(unsigned __int16 *)(v26 + 6);
        if ( v27 > 0x40 || (v27 & 1) != 0 )
        {
          v28 = 0;
          v77 = 0;
        }
        else
        {
          v28 = *(_WORD *)(v26 + 6);
          v77 = v28;
        }
        v84 = v28;
        v85 = v26 + 32;
        v29 = v28 >> 1;
        LODWORD(v58) = *(unsigned __int16 *)(v5 + 26);
        LODWORD(v57) = v29;
        LODWORD(Timeouta) = *(unsigned __int16 *)(v4 + 7872) >> 1;
        McTemplateU0ppwwddd_EtwWriteTransfer(
          v29,
          (const EVENT_DESCRIPTOR *)create_c5927,
          KeGetCurrentThread(),
          v4,
          Timeouta,
          *(_QWORD *)(v4 + 7880),
          v57,
          v26 + 32,
          v58,
          *(_DWORD *)(v4 + 256),
          v22);
      }
      LogFileInformation = -1073741757;
      if ( !NtfsStatusDebugFlags )
        goto LABEL_36;
      v20 = 661300;
      goto LABEL_35;
    }
  }
  v30 = NtfsFlushVolume(a1);
  LogFileInformation = v30;
  v65 = v30;
  if ( v30 == -1073741797 || v30 == -1073741774 || v30 == -1073741566 )
  {
    LogFileInformation = 0;
    v65 = 0;
  }
  v31 = *(_DWORD *)(v4 + 260);
  v32 = *(_DWORD *)(v4 + 268);
  if ( (*(_BYTE *)(v5 + 26) & 1) != 0 )
    v33 = *(_DWORD *)(v4 + 264) != v31 - v32;
  else
    v33 = v31 != v32;
  if ( v33 )
  {
    if ( LogFileInformation < 0 )
      goto LABEL_100;
    NtfsCheckpointCurrentTransaction(a1);
    *(_DWORD *)(a1 + 4) &= ~0x2000u;
    while ( 1 )
    {
      v34 = *(_QWORD *)(a1 + 152);
      if ( v34 == a1 + 152 )
        break;
      NtfsReleaseFcbWithPaging(a1, v34 - 80);
    }
    NtfsReleaseVcb(a1, v4);
    CcWaitForCurrentLazyWriterActivity();
    LOBYTE(v35) = 1;
    NtfsAcquireExclusiveVcb(a1, v4, v35);
    v59 = 1;
    v36 = *(_DWORD *)(v4 + 4);
    if ( (v36 & 0x802) != 0 )
    {
      if ( (!a1 || (*(_DWORD *)(a1 + 16) & 0x100000) == 0)
        && (Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits & 0x20) != 0 )
      {
        v37 = *(_QWORD *)(v4 + 248);
        v38 = *(unsigned __int16 *)(v37 + 6);
        if ( v38 > 0x40 || (v38 & 1) != 0 )
          v38 = 0;
        v78 = v38;
        v86 = v38;
        v87 = v37 + 32;
        LODWORD(v58) = v36;
        LODWORD(v57) = (unsigned __int16)v38 >> 1;
        LODWORD(Timeouta) = *(unsigned __int16 *)(v4 + 7872) >> 1;
        McTemplateU0ppwwd_EtwWriteTransfer(
          (unsigned int)Timeouta,
          (const EVENT_DESCRIPTOR *)create_c6033,
          KeGetCurrentThread(),
          v4,
          Timeouta,
          *(_QWORD *)(v4 + 7880),
          v57,
          v37 + 32,
          v58);
      }
      LogFileInformation = -1073741790;
      if ( !NtfsStatusDebugFlags )
        goto LABEL_36;
      v20 = 661404;
      goto LABEL_35;
    }
    v39 = NtfsFlushVolume(a1);
    LogFileInformation = v39;
    v65 = v39;
    if ( v39 == -1073741797 || v39 == -1073741774 || v39 == -1073741566 )
    {
      LogFileInformation = 0;
      v65 = 0;
    }
    NtfsWakeAndWaitForRepairThreadToTerminate(v4);
    v33 = 0;
    v40 = *(_DWORD *)(v4 + 260);
    v41 = *(_DWORD *)(v4 + 268);
    if ( (*(_BYTE *)(v5 + 26) & 1) != 0 )
    {
      if ( *(_DWORD *)(v4 + 264) != v40 - v41 )
      {
        v33 = 1;
        if ( NtfsTrackVolumeOpenSharingViolation )
LABEL_99:
          __int2c();
      }
    }
    else if ( v40 != v41 )
    {
      v33 = 1;
      if ( NtfsTrackVolumeOpenSharingViolation )
        goto LABEL_99;
    }
LABEL_100:
    if ( v33 )
    {
      if ( LogFileInformation < 0 )
        goto LABEL_147;
      if ( (!a1 || (*(_DWORD *)(a1 + 16) & 0x100000) == 0)
        && (Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits & 0x8000) != 0 )
      {
        v42 = *(_QWORD *)(v4 + 248);
        v43 = *(unsigned __int16 *)(v42 + 6);
        if ( v43 > 0x40 || (v43 & 1) != 0 )
          v43 = 0;
        v79 = v43;
        v88 = v43;
        v89 = v42 + 32;
        LODWORD(v58) = *(unsigned __int16 *)(v5 + 26);
        LODWORD(v57) = (unsigned __int16)v43 >> 1;
        LODWORD(Timeouta) = *(unsigned __int16 *)(v4 + 7872) >> 1;
        McTemplateU0ppwwdddd_EtwWriteTransfer(
          *(unsigned __int16 *)(v5 + 26),
          (const EVENT_DESCRIPTOR *)create_c6122,
          KeGetCurrentThread(),
          v4,
          Timeouta,
          *(_QWORD *)(v4 + 7880),
          v57,
          v42 + 32,
          v58,
          *(_DWORD *)(v4 + 264),
          *(_DWORD *)(v4 + 260),
          *(_DWORD *)(v4 + 268));
      }
      LogFileInformation = -1073741757;
      if ( !NtfsStatusDebugFlags )
      {
LABEL_36:
        v65 = LogFileInformation;
LABEL_147:
        v6 = FileObject;
        goto LABEL_148;
      }
      v20 = 661497;
LABEL_35:
      NtfsStatusTraceAndDebugInternal(0, LogFileInformation, v20);
      goto LABEL_36;
    }
  }
  if ( LogFileInformation < 0 )
  {
    if ( LogFileInformation != -1073741797 && LogFileInformation != -1073741774 && LogFileInformation != -1073741566 )
      goto LABEL_147;
    v65 = 0;
  }
  if ( MemoryAllocated )
    v66 = 1;
LABEL_124:
  v44 = FileObject;
  Buffer = FileObject->FileName.Buffer;
  FileObject->FileName.Buffer = (PWSTR)ExAllocatePoolWithTag((POOL_TYPE)(PoolType | 0x10), 0x10u, 0x4346744Eu);
  if ( Buffer )
    ExFreePoolWithTag(Buffer, 0);
  v6 = v44;
  *(_OWORD *)v44->FileName.Buffer = *(_OWORD *)L"\\$Volume";
  *(_DWORD *)&v44->FileName.Length = 1048592;
  v44->Flags &= ~0x40u;
  v44->Flags |= 8u;
  NtfsAcquireExclusiveFcb(a1, (__int64)v70, 0, 0);
  v60 = 1;
  LogFileInformation = NtfsOpenAttribute(
                         a1,
                         v5,
                         v4,
                         0,
                         (__int64)v70,
                         2,
                         &NtfsEmptyString,
                         128,
                         *((_DWORD *)v70 + 5) == 0 ? 2 : 0,
                         4,
                         0,
                         2,
                         0,
                         (__int64 *)(v4 + 192),
                         0,
                         &v69);
  v65 = LogFileInformation;
  if ( LogFileInformation >= 0 )
  {
    if ( (*(_BYTE *)(v5 + 26) & 7) == 1
      && (*(_DWORD *)(*(_QWORD *)(*(_QWORD *)(v5 + 8) + 8LL) + 20LL) & 1) != 0
      && (*(_DWORD *)(v4 + 4) & 0x2000000) == 0 )
    {
      _InterlockedAdd((volatile signed __int32 *)(v4 + 272), 1u);
      SetFlagInterlocked((unsigned int *)(v69 + 8), 0x80000u);
    }
    v46 = *(_QWORD *)(*(_QWORD *)(v5 + 8) + 8LL);
    if ( (*(_BYTE *)(v46 + 20) & 3) == 3 || NtfsCanAdministerVolume(v46, (__int64)v73, (__int64)v70, 0, 0) )
    {
      *(_WORD *)(v69 + 104) |= 0x200u;
      v47 = (__int64)v73;
    }
    else
    {
      v48 = *(_QWORD *)(*(_QWORD *)(v5 + 8) + 8LL);
      v47 = (__int64)v73;
      LOBYTE(v49) = NtfsEffectiveMode((__int64)v73);
      if ( (unsigned __int8)NtfsPrivilegeCheck(28, v48 + 32, v49) )
      {
        *(_WORD *)(v69 + 104) |= 0x200u;
      }
      else
      {
        MemoryAllocated = 0;
        SecurityDescriptor[0] = 0;
        v80 = 3;
        if ( !ObGetObjectSecurity(*(PVOID *)(*(_QWORD *)(v4 + 248) + 16LL), SecurityDescriptor, &MemoryAllocated)
          && SecurityDescriptor[0] )
        {
          if ( NtfsCanAdministerVolume(v50, v47, (__int64)v70, SecurityDescriptor[0], &v80) )
            *(_WORD *)(v69 + 104) |= 0x200u;
          ObReleaseObjectSecurity(SecurityDescriptor[0], MemoryAllocated);
        }
      }
    }
    if ( v68 )
      SetFlagInterlocked((unsigned int *)(v69 + 4), 0x200u);
    SetFlagInterlocked((unsigned int *)(v69 + 8), 0x800u);
    if ( v66 )
    {
      SetFlagInterlocked((unsigned int *)(v4 + 4), 2u);
      v6 = FileObject;
      *(_QWORD *)(v4 + 1472) = FileObject;
      v63 = 0;
    }
    else
    {
      v6 = FileObject;
    }
    *(_QWORD *)(v47 + 56) = 1;
  }
LABEL_148:
  NtfsCleanupTransaction(a1, LogFileInformation, 0);
  if ( !LogFileInformation )
  {
    v6->FileName.Buffer = 0;
    *(_DWORD *)&v6->FileName.Length = 0;
    SetFlagInterlocked((unsigned int *)(v69 + 4), 0x4000u);
  }
  if ( v60 )
    NtfsReleaseFcbEx(a1, (__int64)v70, 0);
  v51 = v59;
  if ( v64 && LogFileInformation < 0 )
  {
    if ( !v59 )
      v51 = NtfsAcquireExclusiveVcb(a1, v4, 0);
    NtfsUpdateDeleteNotificationVolumeSetting(a1, v4);
  }
  if ( v51 )
    NtfsReleaseVcb(a1, v4);
  if ( v62 )
    ExReleaseResourceLite((PERESOURCE)(*(_QWORD *)(*(_QWORD *)(v4 + 6248) + 24LL) + 912LL));
  if ( v63 )
  {
    NtfsPurgeFileRecordCache(a1);
    if ( (*(_DWORD *)(v4 + 4) & 1) != 0 )
      FsRtlNotifyVolumeEvent(v6, 4u);
  }
  if ( (*(_DWORD *)(a1 + 12) & 2) != 0 )
  {
    if ( NtfsStatusDebugFlags
      && LogFileInformation
      && LogFileInformation != 294
      && (unsigned int)(LogFileInformation - 298) > 1
      && (unsigned int)LogFileInformation < 0xFFFFFFED
      && LogFileInformation != -1073741802
      && (unsigned int)(LogFileInformation + 2147483643) > 1
      && LogFileInformation != -1073741807
      && LogFileInformation != 259
      && LogFileInformation != -1073741608 )
    {
      NtfsStatusTraceAndDebugInternal(a1, LogFileInformation, 0xA1934u);
    }
    v52 = LogFileInformation >= 0;
    v53 = 0;
  }
  else
  {
    if ( NtfsStatusDebugFlags
      && LogFileInformation
      && LogFileInformation != 294
      && (unsigned int)(LogFileInformation - 298) > 1
      && (unsigned int)LogFileInformation < 0xFFFFFFED
      && LogFileInformation != -1073741802
      && (unsigned int)(LogFileInformation + 2147483643) > 1
      && LogFileInformation != -1073741807
      && LogFileInformation != 259
      && LogFileInformation != -1073741608 )
    {
      NtfsStatusTraceAndDebugInternal(a1, LogFileInformation, 0xA1936u);
    }
    v52 = LogFileInformation >= 0;
    v9 = v73 != 0;
    v53 = v73;
  }
  NtfsExtendedCompleteRequestInternal(a1, v53, LogFileInformation, v9, v52);
  return (unsigned int)LogFileInformation;
}

```

## disassembly

```asm
0x1401a0dd0  mov     r11, rsp
0x1401a0dd3  mov     [r11+18h], rbx
0x1401a0dd7  mov     [r11+20h], rsi
0x1401a0ddb  push    rdi
0x1401a0ddc  push    r12
0x1401a0dde  push    r13
0x1401a0de0  push    r14
0x1401a0de2  push    r15
0x1401a0de4  sub     rsp, 1D0h
0x1401a0deb  mov     rax, cs:__security_cookie
0x1401a0df2  xor     rax, rsp
0x1401a0df5  mov     [rsp+1F8h+var_38], rax
0x1401a0dfd  mov     [rsp+1F8h+var_140], rdx
0x1401a0e05  mov     r14, rcx
0x1401a0e08  mov     [rsp+1F8h+var_128], rcx
0x1401a0e10  mov     [rsp+1F8h+var_170], 0C0000001h
0x1401a0e1b  xor     r12d, r12d
0x1401a0e1e  mov     esi, r12d
0x1401a0e21  mov     [r11-138h], r12
0x1401a0e28  mov     [r11-150h], r12
0x1401a0e2f  mov     [r11-158h], r12
0x1401a0e36  mov     al, r12b
0x1401a0e39  mov     [rsp+1F8h+var_176], al
0x1401a0e40  mov     [rsp+1F8h+var_178], al
0x1401a0e47  mov     [r11-175h], r12b
0x1401a0e4e  mov     [r11-173h], r12b
0x1401a0e55  mov     [r11-16Ch], r12b
0x1401a0e5c  mov     [r11-172h], r12b
0x1401a0e63  mov     dil, r12b
0x1401a0e66  mov     [rsp+1F8h+var_160], edi
0x1401a0e6d  mov     [r11-174h], r12b
0x1401a0e74  mov     [r11-171h], r12b
0x1401a0e7b  mov     r13, [rdx+0B8h]
0x1401a0e82  mov     rbx, [r13+30h]
0x1401a0e86  mov     [rsp+1F8h+FileObject], rbx
0x1401a0e8e  mov     [rsp+1F8h+var_108], rbx
0x1401a0e96  mov     dword ptr [rcx+1F8h], 1Ah
0x1401a0ea0  movzx   r9d, byte ptr [r13+13h]
0x1401a0ea5  lea     eax, [r9-1]
0x1401a0ea9  test    eax, 0FFFFFFFDh
0x1401a0eae  jz      short loc_1401A0F0A
0x1401a0eb0  mov     eax, [rcx+10h]
0x1401a0eb3  bt      rax, 14h
0x1401a0eb8  jb      short loc_1401A0EDA
0x1401a0eba  mov     rax, cs:Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits
0x1401a0ec1  test    al, 20h
0x1401a0ec3  jz      short loc_1401A0EDA
0x1401a0ec5  mov     r8, gs:188h
0x1401a0ece  lea     rdx, create_c5645
0x1401a0ed5  call    McTemplateU0pd_EtwWriteTransfer
0x1401a0eda  mov     al, cs:NtfsStatusDebugFlags
0x1401a0ee0  mov     edi, 0C0000022h
0x1401a0ee5  test    al, al
0x1401a0ee7  jz      short loc_1401A0EF8
0x1401a0ee9  mov     r8d, 0A1615h
0x1401a0eef  mov     edx, edi
0x1401a0ef1  xor     ecx, ecx
0x1401a0ef3  call    NtfsStatusTraceAndDebugInternal
0x1401a0ef8  mov     [rsp+1F8h+var_170], edi
0x1401a0eff  mov     r15d, 1
0x1401a0f05  jmp     loc_1401A1B3E
0x1401a0f0a  mov     eax, [r13+10h]
0x1401a0f0e  mov     r15d, 1
0x1401a0f14  test    r15b, al
0x1401a0f17  jz      short loc_1401A0F43
0x1401a0f19  mov     al, cs:NtfsStatusDebugFlags
0x1401a0f1f  mov     edi, 0C000000Dh
0x1401a0f24  test    al, al
0x1401a0f26  jz      short loc_1401A0F37
0x1401a0f28  mov     r8d, 0A161Fh
0x1401a0f2e  mov     edx, edi
0x1401a0f30  xor     ecx, ecx
0x1401a0f32  call    NtfsStatusTraceAndDebugInternal
0x1401a0f37  mov     [rsp+1F8h+var_170], edi
0x1401a0f3e  jmp     loc_1401A1B3E
0x1401a0f43  xor     edx, edx
0x1401a0f45  mov     rcx, [r13+30h]
0x1401a0f49  call    TxfGetTransactionFromFileObject
0x1401a0f4e  test    rax, rax
0x1401a0f51  jz      short loc_1401A0F6A
0x1401a0f53  mov     al, cs:NtfsStatusDebugFlags
0x1401a0f59  mov     edi, 0C019005Ah
0x1401a0f5e  test    al, al
0x1401a0f60  jz      short loc_1401A0F37
0x1401a0f62  mov     r8d, 0A1630h
0x1401a0f68  jmp     short loc_1401A0F2E
0x1401a0f6a  mov     rcx, [r14+68h]
0x1401a0f6e  mov     eax, [rcx+1924h]
0x1401a0f74  test    al, 2
0x1401a0f76  jz      short loc_1401A0FA5
0x1401a0f78  mov     rax, [rcx+1868h]
0x1401a0f7f  test    rax, rax
0x1401a0f82  jz      short loc_1401A0FA5
0x1401a0f84  mov     eax, [rax+88h]
0x1401a0f8a  mov     r12d, 100000h
0x1401a0f90  bt      eax, 0Eh
0x1401a0f94  jnb     short loc_1401A0FAB
0x1401a0f96  test    [r14+1B4h], r12d
0x1401a0f9d  jz      loc_1401A1D8C
0x1401a0fa3  jmp     short loc_1401A0FAB
0x1401a0fa5  mov     r12d, 100000h
0x1401a0fab  mov     rsi, [r14+68h]
0x1401a0faf  mov     [rsp+1F8h+var_138], rsi
0x1401a0fb7  test    byte ptr [r13+1Ah], 6
0x1401a0fbc  jnz     loc_1401A106E
0x1401a0fc2  lea     rcx, [rsi+19E8h]; Object
0x1401a0fc9  mov     [rsp+1F8h+Timeout], 0; Timeout
0x1401a0fd2  xor     r9d, r9d; Alertable
0x1401a0fd5  xor     r8d, r8d; WaitMode
0x1401a0fd8  xor     edx, edx; WaitReason
0x1401a0fda  call    cs:__imp_KeWaitForSingleObject
0x1401a0fe1  nop     dword ptr [rax+rax+00h]
0x1401a0fe6  mov     edx, 3; EventCode
0x1401a0feb  mov     rcx, rbx; FileObject
0x1401a0fee  call    cs:__imp_FsRtlNotifyVolumeEvent
0x1401a0ff5  nop     dword ptr [rax+rax+00h]
0x1401a0ffa  mov     [rsp+1F8h+var_172], r15b
0x1401a1002  mov     byte ptr [rsp+1F8h+Timeout], 0
0x1401a1007  xor     r9d, r9d
0x1401a100a  mov     r8b, r15b
0x1401a100d  mov     rdx, rsi
0x1401a1010  xor     ecx, ecx
0x1401a1012  call    NtfsFspCloseInternal
0x1401a1017  mov     eax, [rsi+1924h]
0x1401a101d  test    al, 2
0x1401a101f  jz      short loc_1401A104F
0x1401a1021  mov     rcx, [rsi+1868h]
0x1401a1028  test    rcx, rcx
0x1401a102b  jz      short loc_1401A104F
0x1401a102d  mov     rcx, [rcx+18h]
0x1401a1031  add     rcx, 390h; Resource
0x1401a1038  mov     dl, r15b; Wait
0x1401a103b  call    cs:__imp_ExAcquireResourceSharedLite
0x1401a1042  nop     dword ptr [rax+rax+00h]
0x1401a1047  mov     [rsp+1F8h+var_173], r15b
0x1401a104f  mov     r8b, r15b
0x1401a1052  mov     rdx, rsi
0x1401a1055  mov     rcx, r14
0x1401a1058  call    NtfsAcquireExclusiveVcb
0x1401a105d  mov     [rsi+1591h], r15b
0x1401a1064  mov     [rsp+1F8h+var_171], r15b
0x1401a106c  jmp     short loc_1401A107C
0x1401a106e  mov     r8b, r15b
0x1401a1071  mov     rdx, rsi
0x1401a1074  mov     rcx, r14
0x1401a1077  call    NtfsAcquireSharedVcb
0x1401a107c  mov     al, r15b
0x1401a107f  mov     [rsp+1F8h+var_176], al
0x1401a1086  mov     [rsp+1F8h+var_178], al
0x1401a108d  lea     rbx, [rsi+4]
0x1401a1091  mov     r9d, [rbx]
0x1401a1094  test    r9d, 802h
0x1401a109b  jz      loc_1401A1159
0x1401a10a1  mov     eax, [r14+10h]
0x1401a10a5  test    r12, rax
0x1401a10a8  jnz     loc_1401A112F
0x1401a10ae  mov     rax, cs:Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits
0x1401a10b5  test    al, 20h
0x1401a10b7  jz      short loc_1401A112F
0x1401a10b9  mov     rdx, [rsi+0F8h]
0x1401a10c0  movzx   eax, word ptr [rdx+6]
0x1401a10c4  cmp     eax, 40h ; '@'
0x1401a10c7  ja      short loc_1401A10CE
0x1401a10c9  test    r15b, al
0x1401a10cc  jz      short loc_1401A10D0
0x1401a10ce  xor     eax, eax
0x1401a10d0  mov     [rsp+1F8h+var_160], eax
0x1401a10d7  mov     [rsp+1F8h+var_100], ax
0x1401a10df  add     rdx, 20h ; ' '
0x1401a10e3  mov     [rsp+1F8h+var_F8], rdx
0x1401a10eb  mov     r8, gs:188h
0x1401a10f4  movzx   eax, ax
0x1401a10f7  shr     eax, 1
0x1401a10f9  movzx   ecx, word ptr [rsi+1EC0h]
0x1401a1100  shr     ecx, 1
0x1401a1102  mov     dword ptr [rsp+1F8h+var_1B8], r9d
0x1401a1107  mov     [rsp+1F8h+var_1C0], rdx
0x1401a110c  mov     dword ptr [rsp+1F8h+var_1C8], eax
0x1401a1110  mov     rax, [rsi+1EC8h]
0x1401a1117  mov     [rsp+1F8h+var_1D0], rax
0x1401a111c  mov     dword ptr [rsp+1F8h+Timeout], ecx
0x1401a1120  mov     r9, rsi
0x1401a1123  lea     rdx, create_c5763
0x1401a112a  call    McTemplateU0ppwwd_EtwWriteTransfer
0x1401a112f  mov     al, cs:NtfsStatusDebugFlags
0x1401a1135  mov     edi, 0C0000022h
0x1401a113a  test    al, al
0x1401a113c  jz      short loc_1401A114D
0x1401a113e  mov     r8d, 0A168Eh
0x1401a1144  mov     edx, edi
0x1401a1146  xor     ecx, ecx
0x1401a1148  call    NtfsStatusTraceAndDebugInternal
0x1401a114d  mov     [rsp+1F8h+var_170], edi
0x1401a1154  jmp     loc_1401A1B36
0x1401a1159  xor     r8d, r8d
0x1401a115c  mov     rdx, rsi
0x1401a115f  mov     rcx, r14
0x1401a1162  call    NtfsPingVolume
0x1401a1167  test    al, al
0x1401a1169  jz      loc_1401A1D64
0x1401a116f  mov     eax, [rbx]
0x1401a1171  test    r15b, al
0x1401a1174  jz      loc_1401A1D64
0x1401a117a  mov     rax, [rsi+0C0h]
0x1401a1181  mov     rax, [rax+0B8h]
0x1401a1188  mov     [rsp+1F8h+var_150], rax
0x1401a1190  xor     r9d, r9d
0x1401a1193  xor     r8d, r8d
0x1401a1196  mov     rdx, rax
0x1401a1199  mov     rcx, r14
0x1401a119c  call    NtfsAcquireExclusiveFcb
0x1401a11a1  mov     [rsp+1F8h+var_175], r15b
0x1401a11a9  mov     rcx, [rsp+1F8h+var_140]
0x1401a11b1  mov     rax, [rcx+0B8h]
0x1401a11b8  mov     rax, [rax+8]
0x1401a11bc  xor     edx, edx
0x1401a11be  mov     byte ptr [rsp+1F8h+var_1B8], dl
0x1401a11c2  mov     byte ptr [rsp+1F8h+var_1C0], dl
0x1401a11c6  mov     byte ptr [rsp+1F8h+var_1C8], dl
0x1401a11ca  mov     eax, [rax+10h]
0x1401a11cd  mov     dword ptr [rsp+1F8h+var_1D0], eax
0x1401a11d1  mov     [rsp+1F8h+Timeout], rcx
0x1401a11d6  xor     r9d, r9d
0x1401a11d9  mov     r8, [rsp+1F8h+var_150]
0x1401a11e1  mov     rcx, r14
0x1401a11e4  call    NtfsAccessCheck
0x1401a11e9  xor     r8d, r8d
0x1401a11ec  mov     rdx, [rsp+1F8h+var_150]
0x1401a11f4  mov     rcx, r14
0x1401a11f7  call    NtfsReleaseFcbEx
0x1401a11fc  mov     [rsp+1F8h+var_175], 0
0x1401a1204  mov     rax, [r13+8]
0x1401a1208  mov     rcx, [rax+8]
0x1401a120c  mov     eax, [rcx+14h]
0x1401a120f  test    byte ptr [r13+1Ah], 6
0x1401a1214  jnz     loc_1401A1809
0x1401a121a  test    al, 6
0x1401a121c  jz      short loc_1401A1248
0x1401a121e  mov     [rsp+1F8h+MemoryAllocated], r15b
0x1401a1226  mov     [rsp+1F8h+var_148], r15b
0x1401a122e  call    cs:__imp_FsRtlAreVolumeStartupApplicationsComplete
0x1401a1235  nop     dword ptr [rax+rax+00h]
0x1401a123a  test    al, al
0x1401a123c  jz      short loc_1401A1248
0x1401a123e  mov     eax, 0FFFEh
0x1401a1243  and     [r13+1Ah], ax
0x1401a1248  test    [r13+1Ah], r15b
0x1401a124c  jnz     loc_1401A1484
0x1401a1252  xor     ebx, ebx
0x1401a1254  mov     [rsp+1F8h+var_144], ebx
0x1401a125b  mov     rax, [rsi+0A8h]
0x1401a1262  test    rax, rax
0x1401a1265  jz      short loc_1401A1274
0x1401a1267  mov     ebx, [rax+0D0h]
0x1401a126d  mov     [rsp+1F8h+var_144], ebx
0x1401a1274  cmp     [rsp+1F8h+var_173], 0
0x1401a127c  jz      loc_1401A13A6
0x1401a1282  mov     rcx, [rsi+1868h]
0x1401a1289  mov     edx, 4
0x1401a128e  mov     r8d, 84h
0x1401a1294  mov     eax, edx
0x1401a1296  lock cmpxchg [rcx+r8], edx
0x1401a129c  cmp     eax, 2
0x1401a129f  jz      short loc_1401A12B9
0x1401a12a1  mov     rcx, [rsi+1868h]
0x1401a12a8  mov     eax, edx
0x1401a12aa  lock cmpxchg [rcx+r8], edx
0x1401a12b0  cmp     eax, r15d
0x1401a12b3  jnz     loc_1401A13A6
0x1401a12b9  mov     rax, [rsi+1868h]
0x1401a12c0  cmp     qword ptr [rax+48h], 0
0x1401a12c5  jz      short loc_1401A12D1
0x1401a12c7  add     ebx, r15d
0x1401a12ca  mov     [rsp+1F8h+var_144], ebx
0x1401a12d1  mov     rdi, [rax+1F0h]
0x1401a12d8  test    rdi, rdi
0x1401a12db  jz      loc_1401A13A6
0x1401a12e1  xor     edx, edx; Val
0x1401a12e3  lea     r8d, [rdx+78h]; Size
0x1401a12e7  lea     rcx, [rsp+1F8h+pinfoBuffer]; void *
0x1401a12ef  call    memset
0x1401a12f4  mov     [rsp+1F8h+pcbInfoBuffer], 0
0x1401a12ff  mov     [rsp+1F8h+pcbInfoBuffer], 78h ; 'x'
0x1401a130a  lea     r8, [rsp+1F8h+pcbInfoBuffer]; pcbInfoBuffer
0x1401a1312  lea     rdx, [rsp+1F8h+pinfoBuffer]; pinfoBuffer
0x1401a131a  mov     rcx, rdi; plfoLog
0x1401a131d  call    cs:__imp_ClfsGetLogFileInformation
0x1401a1324  nop     dword ptr [rax+rax+00h]
0x1401a1329  mov     edi, eax
0x1401a132b  mov     [rsp+1F8h+var_170], eax
0x1401a1332  test    eax, eax
0x1401a1334  jns     short loc_1401A1394
0x1401a1336  mov     al, cs:NtfsStatusDebugFlags
0x1401a133c  test    al, al
0x1401a133e  jz      loc_1401A1B36
0x1401a1344  cmp     edi, 0FFFFFFEDh
0x1401a1347  jnb     loc_1401A1B36
0x1401a134d  cmp     edi, 0C0000016h
0x1401a1353  jz      loc_1401A1B36
0x1401a1359  lea     eax, [rdi+7FFFFFFBh]
  ... truncated ...
```
