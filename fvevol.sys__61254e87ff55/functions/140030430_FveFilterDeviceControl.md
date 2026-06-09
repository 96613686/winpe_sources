# FveFilterDeviceControl

- ea: `0x140030430`
- end: `0x14003106a`
- name: `FveFilterDeviceControl`
- size: `3130`
- prototype: ``
- caller_count: `0`
- callee_count: `37`
- tags: `broker_com_uri`

## callees

- `0x140001008`
- `0x1400010ac`
- `0x140008348`
- `0x140008c00`
- `0x140008e80`
- `0x140008f04`
- `0x140009cb4`
- `0x14000a210`
- `0x14000afb4`
- `0x14000bc14`
- `0x14000f190`
- `0x140022bf0`
- `0x140024a64`
- `0x1400251b4`
- `0x140025b9c`
- `0x140028b28`
- `0x14002d490`
- `0x14002dbe0`
- `0x14002f334`
- `0x140030430`
- `0x140031690`
- `0x14006b298`
- `0x140089928`
- `0x140089d7c`
- `0x14008a0a4`
- `0x14008a3d4`
- `0x14008ae78`
- `0x14008b2f0`
- `0x14008cc90`
- `0x14009d280`
- `0x1400dce00`
- `0x1400dd144`
- `0x1400e62f8`
- `0x1400e64b4`
- `0x1400e6a80`
- `0x1400e7934`
- `0x1400e9584`

## import_xrefs

- `ntoskrnl!IoForwardIrpSynchronously` at `0x14003061b`
- `ntoskrnl!IoForwardIrpSynchronously` at `0x1400309ef`
- `ntoskrnl!IoForwardIrpSynchronously` at `0x140030b25`
- `ntoskrnl!IoForwardIrpSynchronously` at `0x140030ca7`
- `ntoskrnl!IoForwardIrpSynchronously` at `0x14003061b`
- `ntoskrnl!IoForwardIrpSynchronously` at `0x1400309ef`
- `ntoskrnl!IoForwardIrpSynchronously` at `0x140030b25`
- `ntoskrnl!IoForwardIrpSynchronously` at `0x140030ca7`
- `ntoskrnl!IofCompleteRequest` at `0x140031030`
- `ntoskrnl!IofCompleteRequest` at `0x140031030`
- `ntoskrnl!IoAllocateWorkItem` at `0x140030cc6`
- `ntoskrnl!IoAllocateWorkItem` at `0x140030cc6`
- `ntoskrnl!IoQueueWorkItemEx` at `0x140030ce8`
- `ntoskrnl!IoQueueWorkItemEx` at `0x140030ce8`
- `ntoskrnl!ExFreePoolWithTag` at `0x140030c09`
- `ntoskrnl!ExFreePoolWithTag` at `0x140030c2d`
- `ntoskrnl!ExFreePoolWithTag` at `0x140030fdf`
- `ntoskrnl!ExFreePoolWithTag` at `0x140030c09`
- `ntoskrnl!ExFreePoolWithTag` at `0x140030c2d`
- `ntoskrnl!ExFreePoolWithTag` at `0x140030fdf`
- `ntoskrnl!ExAllocatePool2` at `0x1400304ac`
- `ntoskrnl!ExAllocatePool2` at `0x1400304ac`

## pseudocode

```c
__int64 __fastcall FveFilterDeviceControl(__int64 a1, IRP *a2)
{
  __int64 v2; // rbx
  int Status; // edi
  unsigned int LowPart; // ebp
  __int64 v8; // rdx
  __int64 v9; // rcx
  void *Pool2; // r12
  bool v11; // r14
  __int64 v12; // rdx
  __int64 v13; // r8
  __int64 v14; // r8
  int v15; // eax
  bool v16; // zf
  int v17; // eax
  PDEVICE_OBJECT v18; // rcx
  __int64 v19; // rdx
  __int64 v20; // r9
  int v21; // eax
  __int64 v22; // r8
  int CdoPath; // eax
  __int64 v24; // rdx
  __int64 v25; // r8
  __int64 v26; // rdx
  __int64 v27; // rcx
  void *v28; // rcx
  void *v29; // rcx
  struct _IO_WORKITEM *WorkItem; // rax
  int v31; // [rsp+40h] [rbp-98h] BYREF
  __int64 v32; // [rsp+48h] [rbp-90h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v33; // [rsp+50h] [rbp-88h] BYREF
  __int64 *v34; // [rsp+70h] [rbp-68h]
  __int64 v35; // [rsp+78h] [rbp-60h]
  int *v36; // [rsp+80h] [rbp-58h]
  __int64 v37; // [rsp+88h] [rbp-50h]

  v2 = *(_QWORD *)(a1 + 64);
  if ( !*(_QWORD *)v2 )
  {
    Status = -1073741808;
    a2->IoStatus.Information = 0;
    a2->IoStatus.Status = -1073741808;
LABEL_194:
    IofCompleteRequest(a2, 0);
    return (unsigned int)Status;
  }
  if ( *(_QWORD *)(*(_QWORD *)(v2 + 8) + 8LL) == a1 )
    return BlCdoFilterIoctl();
  LowPart = a2->Tail.Overlay.CurrentStackLocation->Parameters.Read.ByteOffset.LowPart;
  a2->IoStatus.Information = 0;
  Pool2 = (void *)ExAllocatePool2(64, 144, 809850438);
  if ( !Pool2 )
  {
    Status = -1073741670;
    goto LABEL_189;
  }
  v11 = 1;
  if ( (unsigned int)Feature_BitLockerEphemeralVolumeSupport__private_IsEnabledDeviceUsageNoInline(v9, v8)
    && (*(_BYTE *)(v2 + 4419) & 8) != 0
    && (LowPart & 0xFFFF0000) == 0x45560000
    && LowPart != 1163268227
    && LowPart != 1163268232
    && LowPart != 1163268268
    && LowPart != 1163268296
    && LowPart != 1163268308
    && LowPart != 1163284627
    && LowPart != 1163317383
    && LowPart != 1163317408 )
  {
    Status = -1071579039;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_Dd(
        WPP_GLOBAL_Control->AttachedDevice,
        59,
        WPP_aaa266bfceb734b8e3c20e313abc0333_Traceguids,
        3223388257LL,
        LowPart);
    }
    goto LABEL_188;
  }
  if ( LowPart > 0x2D4800 )
  {
    if ( LowPart <= 0x455610D4 )
    {
      if ( LowPart == 1163268308 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
        {
          WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 60, WPP_aaa266bfceb734b8e3c20e313abc0333_Traceguids, v2);
        }
        CdoPath = IoctlFveGetCdoPath(v2, a2);
        goto LABEL_150;
      }
      if ( LowPart == 2987012 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
        {
          WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 75, WPP_aaa266bfceb734b8e3c20e313abc0333_Traceguids, v2);
        }
        v21 = FveManageDataSetAttributes(a1, a2);
        goto LABEL_127;
      }
      if ( LowPart != 5685256 )
      {
        switch ( LowPart )
        {
          case 0x56C00Cu:
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
              && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
            {
              WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 68, WPP_aaa266bfceb734b8e3c20e313abc0333_Traceguids, v2);
            }
            LOBYTE(v12) = 1;
            FveFsOffline(v2, v12);
            LOBYTE(v25) = 1;
            FvepAcquireDevFveLock(v2, Pool2, v25);
            FveRundownAllReadsAndWrites(v2);
            SetFveState(v2, 0x4000, 0, 0, 23);
            *(_DWORD *)(v2 + 836) = 1;
            FveResumeAllReadsAndWrites(v2);
            FveCleanup((PVOID)v2);
            if ( (unsigned int)Feature_SteelixInlineNvmeCryptoEngine__private_IsEnabledDeviceUsageNoInline(v27, v26) )
            {
              v28 = *(void **)(v2 + 4736);
              if ( v28 )
              {
                ExFreePoolWithTag(v28, 0x30455646u);
                *(_QWORD *)(v2 + 4736) = 0;
              }
            }
            v29 = *(void **)(v2 + 4744);
            if ( v29 )
            {
              ExFreePoolWithTag(v29, 0x30455646u);
              *(_QWORD *)(v2 + 4744) = 0;
            }
            *(_DWORD *)(v2 + 852) &= 0x3FFFFFFFu;
            FvepReleaseDevFveLock(Pool2);
            goto LABEL_126;
          case 0x56C05Cu:
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
              && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
            {
              WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 72, WPP_aaa266bfceb734b8e3c20e313abc0333_Traceguids, v2);
            }
            IoForwardIrpSynchronously(*(PDEVICE_OBJECT *)(v2 + 112), a2);
            Status = a2->IoStatus.Status;
            if ( Status >= 0 )
            {
              FveConvStop((PVOID)v2);
              LOBYTE(v24) = 1;
              FveWipeStop(v2, v24);
            }
            goto LABEL_188;
          case 0x7780000u:
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
              && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
            {
              WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 77, WPP_aaa266bfceb734b8e3c20e313abc0333_Traceguids, v2);
            }
            Status = FveQueueDelayedAutoWorkItem(v2, FveFilterCsvSetTargetPathWorker, a2, 1, FveFailIrpOnRemoval, a2, 0);
            v11 = Status != 259;
            goto LABEL_188;
        }
LABEL_155:
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
        {
          WPP_SF_Dq(WPP_GLOBAL_Control->AttachedDevice, v12, v13, LowPart, v2);
        }
LABEL_126:
        v21 = FveFilterSkip(a1, a2);
LABEL_127:
        Status = v21;
        v11 = 0;
        goto LABEL_188;
      }
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
      {
        WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 65, WPP_aaa266bfceb734b8e3c20e313abc0333_Traceguids, v2);
      }
      IoForwardIrpSynchronously(*(PDEVICE_OBJECT *)(v2 + 112), a2);
      Status = a2->IoStatus.Status;
      if ( Status < 0 )
        goto LABEL_188;
      Feature_BitLocker_DeferredDiscoveryOnVolumeOnline__private_IsEnabledPreCheck();
      WorkItem = IoAllocateWorkItem(*(PDEVICE_OBJECT *)v2);
      if ( WorkItem )
      {
        IoQueueWorkItemEx(
          WorkItem,
          FveDiscoverVolumeWorkerOnIoctlVolumeOnline,
          CustomPriorityWorkQueue|BackgroundWorkQueue|0x8,
          0);
        goto LABEL_188;
      }
      v18 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) == 0
        || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
      {
        goto LABEL_188;
      }
      v19 = 66;
      v20 = 3221225626LL;
LABEL_139:
      WPP_SF_d(v18->AttachedDevice, v19, WPP_aaa266bfceb734b8e3c20e313abc0333_Traceguids, v20);
      goto LABEL_188;
    }
    if ( LowPart == 1163268312 )
    {
      if ( !a2->RequestorMode )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
        {
          WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 78, WPP_aaa266bfceb734b8e3c20e313abc0333_Traceguids, v2);
        }
        _InterlockedAdd((volatile signed __int32 *)(v2 + 4732), 1u);
        a2->IoStatus.Information = 0;
        Status = FveReadWriteDeviceInit(v2);
        if ( Status >= 0 )
          FveLockDriver(v2);
        goto LABEL_188;
      }
    }
    else
    {
      if ( LowPart != 1163268316 )
      {
        if ( LowPart == 1163317443 )
        {
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
          {
            WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 61, WPP_aaa266bfceb734b8e3c20e313abc0333_Traceguids, v2);
          }
          CdoPath = IoctlFveRegisterContext(v2, a2);
        }
        else
        {
          if ( LowPart != 1163317447 )
            goto LABEL_155;
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
          {
            WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 62, WPP_aaa266bfceb734b8e3c20e313abc0333_Traceguids, v2);
          }
          CdoPath = IoctlFveUnregisterContext(v2, a2);
        }
        goto LABEL_150;
      }
      if ( !a2->RequestorMode )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
        {
          WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 79, WPP_aaa266bfceb734b8e3c20e313abc0333_Traceguids, v2);
        }
        if ( _InterlockedDecrement((volatile signed __int32 *)(v2 + 4732)) < 0
          && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        {
          WPP_SF_qd(
            WPP_GLOBAL_Control->AttachedDevice,
            80,
            WPP_aaa266bfceb734b8e3c20e313abc0333_Traceguids,
            v2,
            *(_DWORD *)(v2 + 4732));
        }
        a2->IoStatus.Information = 0;
        FveReadWriteDeviceCleanup(v2, 0);
        Status = 0;
        goto LABEL_188;
      }
    }
    Status = -1073741790;
    goto LABEL_188;
  }
  if ( LowPart == 2967552 )
  {
LABEL_89:
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
    {
      WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 64, WPP_aaa266bfceb734b8e3c20e313abc0333_Traceguids, v2);
    }
    IoForwardIrpSynchronously(*(PDEVICE_OBJECT *)(v2 + 112), a2);
    Status = a2->IoStatus.Status;
    if ( Status != -2147483626 )
    {
      v16 = Status == -1073741805;
LABEL_96:
      if ( !v16 )
        goto LABEL_188;
      goto LABEL_97;
    }
    *(_BYTE *)(v2 + 832) = 1;
LABEL_97:
    FveDiscoverVolume((PVOID)v2);
    goto LABEL_188;
  }
  if ( LowPart > 0x74004 )
  {
    if ( LowPart == 475228 )
    {
LABEL_84:
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
      {
        WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 73, WPP_aaa266bfceb734b8e3c20e313abc0333_Traceguids, v2);
      }
      CdoPath = IoctlDiskQuery(a1, a2);
      goto LABEL_150;
    }
    if ( LowPart != 477184 )
    {
      if ( LowPart == 508004 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
        {
          WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 74, WPP_aaa266bfceb734b8e3c20e313abc0333_Traceguids, v2);
        }
        Status = -1073741808;
        goto LABEL_188;
      }
      if ( LowPart != 2951168 )
      {
        if ( LowPart != 2951360 )
          goto LABEL_155;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
        {
          WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 81, WPP_aaa266bfceb734b8e3c20e313abc0333_Traceguids, v2);
        }
        CdoPath = IoctlStorageManageBypassIo(v2, a2);
LABEL_150:
        Status = CdoPath;
        goto LABEL_188;
      }
    }
    goto LABEL_89;
  }
  switch ( LowPart )
  {
    case 0x74004u:
      goto LABEL_84;
    case 0x70000u:
      goto LABEL_31;
    case 0x70014u:
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
      {
        WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 76, WPP_aaa266bfceb734b8e3c20e313abc0333_Traceguids, v2);
      }
      v21 = FveDiskVerify(a1, a2);
      goto LABEL_127;
    case 0x70024u:
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
      {
        WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 69, WPP_aaa266bfceb734b8e3c20e313abc0333_Traceguids, v2);
      }
      LOBYTE(v13) = 1;
      FvepAcquireDevFveLock(v2, Pool2, v13);
      v17 = FveDiscoverVolume((PVOID)v2);
      Status = v17;
      if ( (unsigned int)(*(_DWORD *)(v2 + 836) - 2) > 2 && v17 >= 0 )
      {
        Status = *(_DWORD *)(v2 + 816);
        if ( Status >= 0 )
        {
          Status = *(_DWORD *)(v2 + 812);
          if ( Status >= 0 )
            Status = -1073741823;
        }
      }
      FvepReleaseDevFveLock(Pool2);
      if ( Status >= 0 )
      {
        if ( (*(_DWORD *)(v2 + 852) & 8) != 0 )
        {
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
          {
            WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 71, WPP_aaa266bfceb734b8e3c20e313abc0333_Traceguids);
          }
          Status = -1073741662;
          if ( (unsigned int)dword_140046040 > 4 && (unsigned __int8)tlgKeywordOn(&dword_140046040, 0x400000000000LL) )
          {
            v32 = *(unsigned int *)(v2 + 852);
            v35 = 8;
            v34 = &v32;
            v31 = -1073741662;
            v36 = &v31;
            v37 = 4;
            tlgWriteTransfer_EtwWriteTransfer(
              (__int64)&dword_140046040,
              (unsigned __int8 *)&word_14003D6FE,
              0,
              0,
              4u,
              &v33);
          }
          goto LABEL_188;
        }
        goto LABEL_126;
      }
      v18 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) == 0
        || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
      {
        goto LABEL_188;
      }
      v19 = 70;
      v20 = (unsigned int)Status;
      goto LABEL_139;
    case 0x70048u:
      goto LABEL_84;
  }
  if ( LowPart != 458912 )
    goto LABEL_155;
LABEL_31:
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 63, WPP_aaa266bfceb734b8e3c20e313abc0333_Traceguids, v2);
  }
  IoForwardIrpSynchronously(*(PDEVICE_OBJECT *)(v2 + 112), a2);
  Status = a2->IoStatus.Status;
  if ( Status >= 0 )
  {
    v15 = *(_DWORD *)(v2 + 836);
    if ( v15 != 8 )
    {
      v16 = v15 == 1;
      goto LABEL_96;
    }
    goto LABEL_97;
  }
  if ( Status == -1073741805 )
  {
    LOBYTE(v14) = 1;
    FvepAcquireDevFveLock(v2, Pool2, v14);
    if ( *(_QWORD *)(v2 + 1048) )
    {
      FveRundownAllReadsAndWrites(v2);
      SetFveState(v2, 0x8000, 0, 0, 58);
      *(_QWORD *)(v2 + 1048) = 0;
      *(_DWORD *)(v2 + 836) = 1;
      FveResumeAllReadsAndWrites(v2);
      LOBYTE(v22) = 1;
      FveTestDevStateChange(v2, 58, v22);
    }
    FvepReleaseDevFveLock(Pool2);
  }
LABEL_188:
  ExFreePoolWithTag(Pool2, 0x30455646u);
  if ( v11 )
  {
LABEL_189:
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
    {
      WPP_SF_d(
        WPP_GLOBAL_Control->AttachedDevice,
        83,
        WPP_aaa266bfceb734b8e3c20e313abc0333_Traceguids,
        (unsigned int)Status);
    }
    a2->IoStatus.Status = Status;
    goto LABEL_194;
  }
  return (unsigned int)Status;
}

```

## disassembly

```asm
0x140030430  mov     [rsp+arg_10], rbx
0x140030435  push    rbp
0x140030436  push    rsi
0x140030437  push    rdi
0x140030438  push    r12
0x14003043a  push    r13
0x14003043c  push    r14
0x14003043e  push    r15
0x140030440  sub     rsp, 0A0h
0x140030447  mov     rax, cs:__security_cookie
0x14003044e  xor     rax, rsp
0x140030451  mov     [rsp+0D8h+var_48], rax
0x140030459  mov     rbx, [rcx+40h]
0x14003045d  xor     r13d, r13d
0x140030460  mov     rsi, rdx
0x140030463  mov     r15, rcx
0x140030466  cmp     [rbx], r13
0x140030469  jnz     short loc_14003047C
0x14003046b  mov     edi, 0C0000010h
0x140030470  mov     [rdx+38h], r13
0x140030474  mov     [rdx+30h], edi
0x140030477  jmp     loc_14003102B
0x14003047c  mov     rax, [rbx+8]
0x140030480  cmp     [rax+8], r15
0x140030484  jnz     short loc_140030490
0x140030486  call    BlCdoFilterIoctl
0x14003048b  jmp     loc_14003103E
0x140030490  mov     rax, [rdx+0B8h]
0x140030497  mov     r8d, 30455646h
0x14003049d  mov     ebp, [rax+18h]
0x1400304a0  mov     [rdx+38h], r13
0x1400304a4  mov     edx, 90h
0x1400304a9  lea     ecx, [rdx-50h]
0x1400304ac  call    cs:__imp_ExAllocatePool2
0x1400304b3  nop     dword ptr [rax+rax+00h]
0x1400304b8  mov     r12, rax
0x1400304bb  mov     edi, 10h
0x1400304c0  lea     rax, WPP_GLOBAL_Control
0x1400304c7  test    r12, r12
0x1400304ca  jnz     short loc_1400304D6
0x1400304cc  mov     edi, 0C000009Ah
0x1400304d1  jmp     loc_140030FF7
0x1400304d6  mov     r14d, 1
0x1400304dc  call    Feature_BitLockerEphemeralVolumeSupport__private_IsEnabledDeviceUsageNoInline
0x1400304e1  test    eax, eax
0x1400304e3  jz      loc_140030589
0x1400304e9  test    byte ptr [rbx+1143h], 8
0x1400304f0  jz      loc_140030589
0x1400304f6  mov     eax, ebp
0x1400304f8  and     eax, 0FFFF0000h
0x1400304fd  cmp     eax, 45560000h
0x140030502  jnz     loc_140030589
0x140030508  mov     eax, ebp
0x14003050a  sub     eax, 45561083h
0x14003050f  jz      short loc_140030589
0x140030511  sub     eax, 5
0x140030514  jz      short loc_140030589
0x140030516  sub     eax, 24h ; '$'
0x140030519  jz      short loc_140030589
0x14003051b  sub     eax, 1Ch
0x14003051e  jz      short loc_140030589
0x140030520  sub     eax, 0Ch
0x140030523  jz      short loc_140030589
0x140030525  sub     eax, 3FBFh
0x14003052a  jz      short loc_140030589
0x14003052c  sub     eax, 7FF4h
0x140030531  jz      short loc_140030589
0x140030533  cmp     eax, 19h
0x140030536  jz      short loc_140030589
0x140030538  mov     edi, 0C0210061h
0x14003053d  mov     rcx, cs:WPP_GLOBAL_Control
0x140030544  lea     rax, WPP_GLOBAL_Control
0x14003054b  cmp     rcx, rax
0x14003054e  jz      loc_140030FD7
0x140030554  mov     eax, [rcx+2Ch]
0x140030557  test    al, 10h
0x140030559  jz      loc_140030FD7
0x14003055f  cmp     byte ptr [rcx+29h], 2
0x140030563  jb      loc_140030FD7
0x140030569  mov     rcx, [rcx+18h]
0x14003056d  lea     edx, [r14+3Ah]
0x140030571  mov     r9d, edi
0x140030574  mov     dword ptr [rsp+0D8h+var_B8], ebp
0x140030578  lea     r8, WPP_aaa266bfceb734b8e3c20e313abc0333_Traceguids
0x14003057f  call    WPP_SF_Dd
0x140030584  jmp     loc_140030FD7
0x140030589  mov     eax, 2D4800h
0x14003058e  cmp     ebp, eax
0x140030590  ja      loc_140030A2D
0x140030596  jz      loc_1400309AF
0x14003059c  mov     eax, 74004h
0x1400305a1  cmp     ebp, eax
0x1400305a3  ja      loc_1400308A2
0x1400305a9  jz      loc_140030966
0x1400305af  mov     eax, ebp
0x1400305b1  sub     eax, 70000h
0x1400305b6  jz      short loc_1400305DB
0x1400305b8  sub     eax, 14h
0x1400305bb  jz      loc_1400307E2
0x1400305c1  sub     eax, edi
0x1400305c3  jz      loc_140030649
0x1400305c9  sub     eax, 24h ; '$'
0x1400305cc  jz      loc_140030966
0x1400305d2  cmp     eax, 58h ; 'X'
0x1400305d5  jnz     loc_140030DF8
0x1400305db  mov     rcx, cs:WPP_GLOBAL_Control
0x1400305e2  lea     rax, WPP_GLOBAL_Control
0x1400305e9  cmp     rcx, rax
0x1400305ec  jz      short loc_140030614
0x1400305ee  mov     eax, [rcx+2Ch]
0x1400305f1  test    dil, al
0x1400305f4  jz      short loc_140030614
0x1400305f6  cmp     byte ptr [rcx+29h], 5
0x1400305fa  jb      short loc_140030614
0x1400305fc  mov     rcx, [rcx+18h]
0x140030600  lea     r8, WPP_aaa266bfceb734b8e3c20e313abc0333_Traceguids
0x140030607  mov     edx, 3Fh ; '?'
0x14003060c  mov     r9, rbx
0x14003060f  call    WPP_SF_q
0x140030614  mov     rcx, [rbx+70h]; DeviceObject
0x140030618  mov     rdx, rsi; Irp
0x14003061b  call    cs:__imp_IoForwardIrpSynchronously
0x140030622  nop     dword ptr [rax+rax+00h]
0x140030627  mov     edi, [rsi+30h]
0x14003062a  test    edi, edi
0x14003062c  js      loc_14003082B
0x140030632  mov     eax, [rbx+344h]
0x140030638  cmp     eax, 8
0x14003063b  jz      loc_140030A1B
0x140030641  cmp     eax, r14d
0x140030644  jmp     loc_140030A15
0x140030649  mov     rcx, cs:WPP_GLOBAL_Control
0x140030650  lea     rbp, WPP_GLOBAL_Control
0x140030657  cmp     rcx, rbp
0x14003065a  jz      short loc_140030682
0x14003065c  mov     eax, [rcx+2Ch]
0x14003065f  test    dil, al
0x140030662  jz      short loc_140030682
0x140030664  cmp     byte ptr [rcx+29h], 5
0x140030668  jb      short loc_140030682
0x14003066a  mov     rcx, [rcx+18h]
0x14003066e  lea     r8, WPP_aaa266bfceb734b8e3c20e313abc0333_Traceguids
0x140030675  mov     edx, 45h ; 'E'
0x14003067a  mov     r9, rbx
0x14003067d  call    WPP_SF_q
0x140030682  mov     r8b, r14b
0x140030685  mov     rdx, r12
0x140030688  mov     rcx, rbx
0x14003068b  call    FvepAcquireDevFveLock
0x140030690  xor     r8d, r8d
0x140030693  xor     edx, edx
0x140030695  mov     rcx, rbx; Context
0x140030698  call    FveDiscoverVolume
0x14003069d  mov     ecx, [rbx+344h]
0x1400306a3  mov     edi, eax
0x1400306a5  sub     ecx, 2
0x1400306a8  cmp     ecx, 2
0x1400306ab  jbe     short loc_1400306CB
0x1400306ad  test    eax, eax
0x1400306af  js      short loc_1400306CB
0x1400306b1  mov     edi, [rbx+330h]
0x1400306b7  test    edi, edi
0x1400306b9  js      short loc_1400306CB
0x1400306bb  mov     edi, [rbx+32Ch]
0x1400306c1  mov     eax, 0C0000001h
0x1400306c6  test    edi, edi
0x1400306c8  cmovns  edi, eax
0x1400306cb  mov     rcx, r12
0x1400306ce  call    FvepReleaseDevFveLock
0x1400306d3  test    edi, edi
0x1400306d5  jns     short loc_140030709
0x1400306d7  mov     rcx, cs:WPP_GLOBAL_Control
0x1400306de  cmp     rcx, rbp
0x1400306e1  jz      loc_140030FD7
0x1400306e7  mov     eax, [rcx+2Ch]
0x1400306ea  test    al, 10h
0x1400306ec  jz      loc_140030FD7
0x1400306f2  cmp     byte ptr [rcx+29h], 2
0x1400306f6  jb      loc_140030FD7
0x1400306fc  mov     edx, 46h ; 'F'
0x140030701  mov     r9d, edi
0x140030704  jmp     loc_140030D29
0x140030709  mov     eax, [rbx+354h]
0x14003070f  test    al, 8
0x140030711  jz      loc_140030C52
0x140030717  mov     rcx, cs:WPP_GLOBAL_Control
0x14003071e  cmp     rcx, rbp
0x140030721  jz      short loc_140030745
0x140030723  mov     eax, [rcx+2Ch]
0x140030726  test    al, 10h
0x140030728  jz      short loc_140030745
0x14003072a  cmp     byte ptr [rcx+29h], 5
0x14003072e  jb      short loc_140030745
0x140030730  mov     rcx, [rcx+18h]
0x140030734  lea     r8, WPP_aaa266bfceb734b8e3c20e313abc0333_Traceguids
0x14003073b  mov     edx, 47h ; 'G'
0x140030740  call    WPP_SF_
0x140030745  mov     eax, cs:dword_140046040
0x14003074b  mov     edi, 0C00000A2h
0x140030750  cmp     eax, 4
0x140030753  jbe     loc_140030FD7
0x140030759  mov     rdx, 400000000000h
0x140030763  lea     rcx, dword_140046040
0x14003076a  call    _tlgKeywordOn
0x14003076f  test    al, al
0x140030771  jz      loc_140030FD7
0x140030777  mov     eax, [rbx+354h]
0x14003077d  lea     rdx, word_14003D6FE
0x140030784  mov     [rsp+0D8h+var_90], rax
0x140030789  lea     rcx, dword_140046040
0x140030790  lea     rax, [rsp+0D8h+var_90]
0x140030795  mov     [rsp+0D8h+var_60], 8
0x14003079e  mov     [rsp+0D8h+var_68], rax
0x1400307a3  xor     r9d, r9d
0x1400307a6  lea     rax, [rsp+0D8h+var_98]
0x1400307ab  mov     [rsp+0D8h+var_98], edi
0x1400307af  mov     [rsp+0D8h+var_58], rax
0x1400307b7  xor     r8d, r8d
0x1400307ba  lea     rax, [rsp+0D8h+var_88]
0x1400307bf  mov     [rsp+0D8h+var_50], 4
0x1400307cb  mov     [rsp+0D8h+var_B0], rax
0x1400307d0  mov     dword ptr [rsp+0D8h+var_B8], 4
0x1400307d8  call    _tlgWriteTransfer_EtwWriteTransfer
0x1400307dd  jmp     loc_140030FD7
0x1400307e2  mov     rcx, cs:WPP_GLOBAL_Control
0x1400307e9  lea     rax, WPP_GLOBAL_Control
0x1400307f0  cmp     rcx, rax
0x1400307f3  jz      short loc_14003081B
0x1400307f5  mov     eax, [rcx+2Ch]
0x1400307f8  test    dil, al
0x1400307fb  jz      short loc_14003081B
0x1400307fd  cmp     byte ptr [rcx+29h], 5
0x140030801  jb      short loc_14003081B
0x140030803  mov     rcx, [rcx+18h]
0x140030807  lea     r8, WPP_aaa266bfceb734b8e3c20e313abc0333_Traceguids
0x14003080e  mov     edx, 4Ch ; 'L'
0x140030813  mov     r9, rbx
0x140030816  call    WPP_SF_q
0x14003081b  mov     rdx, rsi
0x14003081e  mov     rcx, r15
0x140030821  call    FveDiskVerify
0x140030826  jmp     loc_140030C5D
0x14003082b  cmp     edi, 0C0000013h
0x140030831  jnz     loc_140030FD7
0x140030837  mov     r8b, r14b
0x14003083a  mov     rdx, r12
0x14003083d  mov     rcx, rbx
0x140030840  call    FvepAcquireDevFveLock
0x140030845  cmp     [rbx+418h], r13
0x14003084c  jbe     short loc_140030895
0x14003084e  mov     rcx, rbx
0x140030851  call    FveRundownAllReadsAndWrites
0x140030856  mov     ebp, 3Ah ; ':'
0x14003085b  xor     r9d, r9d
0x14003085e  xor     r8d, r8d
0x140030861  mov     dword ptr [rsp+0D8h+var_B8], ebp
0x140030865  mov     edx, 8000h
0x14003086a  mov     rcx, rbx
0x14003086d  call    SetFveState
0x140030872  mov     rcx, rbx
0x140030875  mov     [rbx+418h], r13
0x14003087c  mov     [rbx+344h], r14d
0x140030883  call    FveResumeAllReadsAndWrites
0x140030888  mov     r8b, r14b
0x14003088b  mov     edx, ebp
0x14003088d  mov     rcx, rbx
0x140030890  call    FveTestDevStateChange
0x140030895  mov     rcx, r12
0x140030898  call    FvepReleaseDevFveLock
0x14003089d  jmp     loc_140030FD7
0x1400308a2  cmp     ebp, 7405Ch
0x1400308a8  jz      loc_140030966
0x1400308ae  cmp     ebp, 74800h
0x1400308b4  jz      loc_1400309AF
0x1400308ba  cmp     ebp, 7C064h
0x1400308c0  jz      short loc_140030923
0x1400308c2  cmp     ebp, 2D0800h
0x1400308c8  jz      loc_1400309AF
0x1400308ce  cmp     ebp, 2D08C0h
0x1400308d4  jnz     loc_140030DF8
0x1400308da  mov     rcx, cs:WPP_GLOBAL_Control
0x1400308e1  lea     rax, WPP_GLOBAL_Control
0x1400308e8  cmp     rcx, rax
0x1400308eb  jz      short loc_140030913
0x1400308ed  mov     eax, [rcx+2Ch]
0x1400308f0  test    dil, al
0x1400308f3  jz      short loc_140030913
0x1400308f5  cmp     byte ptr [rcx+29h], 5
0x1400308f9  jb      short loc_140030913
0x1400308fb  mov     rcx, [rcx+18h]
0x1400308ff  lea     r8, WPP_aaa266bfceb734b8e3c20e313abc0333_Traceguids
0x140030906  mov     edx, 51h ; 'Q'
0x14003090b  mov     r9, rbx
0x14003090e  call    WPP_SF_q
0x140030913  mov     rdx, rsi
0x140030916  mov     rcx, rbx
0x140030919  call    IoctlStorageManageBypassIo
0x14003091e  jmp     loc_140030DCB
0x140030923  mov     rcx, cs:WPP_GLOBAL_Control
0x14003092a  lea     rax, WPP_GLOBAL_Control
  ... truncated ...
```
