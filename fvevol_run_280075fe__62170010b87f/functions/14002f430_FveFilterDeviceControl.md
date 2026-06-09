# FveFilterDeviceControl

- ea: `0x14002f430`
- end: `0x140030063`
- name: `FveFilterDeviceControl`
- size: `3123`
- prototype: ``
- caller_count: `0`
- callee_count: `37`
- tags: `broker_com_uri`

## callees

- `0x140001008`
- `0x1400010ac`
- `0x140008288`
- `0x140008b40`
- `0x140008dc0`
- `0x140008e44`
- `0x140009bf4`
- `0x14000a150`
- `0x14000aef4`
- `0x14000ba88`
- `0x14000efa8`
- `0x1400218c0`
- `0x140023a64`
- `0x1400241b4`
- `0x140024b9c`
- `0x140027b28`
- `0x14002c490`
- `0x14002cbe0`
- `0x14002e334`
- `0x14002f430`
- `0x140030690`
- `0x140069208`
- `0x140087888`
- `0x140087cdc`
- `0x140088004`
- `0x140088334`
- `0x140088dd8`
- `0x140089250`
- `0x14008abf0`
- `0x14009b1c0`
- `0x1400da590`
- `0x1400da8d4`
- `0x1400e39d8`
- `0x1400e3ec8`
- `0x1400e6cd4`
- `0x1400e9050`
- `0x1400e9244`

## import_xrefs

- `ntoskrnl!IoForwardIrpSynchronously` at `0x14002f61b`
- `ntoskrnl!IoForwardIrpSynchronously` at `0x14002f9e8`
- `ntoskrnl!IoForwardIrpSynchronously` at `0x14002fb1e`
- `ntoskrnl!IoForwardIrpSynchronously` at `0x14002fca0`
- `ntoskrnl!IoForwardIrpSynchronously` at `0x14002f61b`
- `ntoskrnl!IoForwardIrpSynchronously` at `0x14002f9e8`
- `ntoskrnl!IoForwardIrpSynchronously` at `0x14002fb1e`
- `ntoskrnl!IoForwardIrpSynchronously` at `0x14002fca0`
- `ntoskrnl!IofCompleteRequest` at `0x140030029`
- `ntoskrnl!IofCompleteRequest` at `0x140030029`
- `ntoskrnl!IoAllocateWorkItem` at `0x14002fcbf`
- `ntoskrnl!IoAllocateWorkItem` at `0x14002fcbf`
- `ntoskrnl!IoQueueWorkItemEx` at `0x14002fce1`
- `ntoskrnl!IoQueueWorkItemEx` at `0x14002fce1`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002fc02`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002fc26`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002ffd8`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002fc02`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002fc26`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002ffd8`
- `ntoskrnl!ExAllocatePool2` at `0x14002f4ac`
- `ntoskrnl!ExAllocatePool2` at `0x14002f4ac`

## pseudocode

```c
__int64 __fastcall FveFilterDeviceControl(__int64 a1, IRP *a2)
{
  __int64 v2; // rbx
  int Status; // edi
  unsigned int LowPart; // ebp
  __int64 v8; // rcx
  void *Pool2; // r12
  bool v10; // r14
  __int64 v11; // rdx
  __int64 v12; // r8
  __int64 v13; // r8
  int v14; // eax
  bool v15; // zf
  int v16; // eax
  PDEVICE_OBJECT v17; // rcx
  __int64 v18; // rdx
  __int64 v19; // r9
  __int64 v20; // rcx
  int v21; // eax
  __int64 v22; // r8
  int CdoPath; // eax
  __int64 v24; // rdx
  __int64 v25; // r8
  __int64 v26; // rcx
  void *v27; // rcx
  void *v28; // rcx
  struct _IO_WORKITEM *WorkItem; // rax
  int v30; // [rsp+40h] [rbp-98h] BYREF
  __int64 v31; // [rsp+48h] [rbp-90h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v32; // [rsp+50h] [rbp-88h] BYREF
  __int64 *v33; // [rsp+70h] [rbp-68h]
  __int64 v34; // [rsp+78h] [rbp-60h]
  int *v35; // [rsp+80h] [rbp-58h]
  __int64 v36; // [rsp+88h] [rbp-50h]

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
  v10 = 1;
  if ( (unsigned int)Feature_BitLockerEphemeralVolumeSupport__private_IsEnabledDeviceUsageNoInline(v8)
    && (*(_BYTE *)(v2 + 4403) & 8) != 0
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
        WPP_b4b9d8ac9d1830ce077ccb64ddccb5ed_Traceguids,
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
          WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 60, WPP_b4b9d8ac9d1830ce077ccb64ddccb5ed_Traceguids, v2);
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
          WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 75, WPP_b4b9d8ac9d1830ce077ccb64ddccb5ed_Traceguids, v2);
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
              WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 68, WPP_b4b9d8ac9d1830ce077ccb64ddccb5ed_Traceguids, v2);
            }
            LOBYTE(v11) = 1;
            FveFsOffline(v2, v11);
            LOBYTE(v25) = 1;
            FvepAcquireDevFveLock(v2, Pool2, v25);
            FveRundownAllReadsAndWrites(v2);
            SetFveState(v2, 0x4000, 0, 0, 23);
            *(_DWORD *)(v2 + 836) = 1;
            FveResumeAllReadsAndWrites(v2);
            FveCleanup((PVOID)v2);
            if ( (unsigned int)Feature_SteelixInlineNvmeCryptoEngine__private_IsEnabledDeviceUsageNoInline(v26) )
            {
              v27 = *(void **)(v2 + 4720);
              if ( v27 )
              {
                ExFreePoolWithTag(v27, 0x30455646u);
                *(_QWORD *)(v2 + 4720) = 0;
              }
            }
            v28 = *(void **)(v2 + 4728);
            if ( v28 )
            {
              ExFreePoolWithTag(v28, 0x30455646u);
              *(_QWORD *)(v2 + 4728) = 0;
            }
            *(_DWORD *)(v2 + 852) &= 0x3FFFFFFFu;
            FvepReleaseDevFveLock(Pool2);
            goto LABEL_126;
          case 0x56C05Cu:
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
              && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
            {
              WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 72, WPP_b4b9d8ac9d1830ce077ccb64ddccb5ed_Traceguids, v2);
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
              WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 77, WPP_b4b9d8ac9d1830ce077ccb64ddccb5ed_Traceguids, v2);
            }
            Status = FveQueueDelayedAutoWorkItem(v2, FveFilterCsvSetTargetPathWorker, a2, 1, FveFailIrpOnRemoval, a2, 0);
            v10 = Status != 259;
            goto LABEL_188;
        }
LABEL_155:
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
        {
          WPP_SF_Dq(WPP_GLOBAL_Control->AttachedDevice, v11, v12, LowPart, v2);
        }
LABEL_126:
        v21 = FveFilterSkip(a1, a2);
LABEL_127:
        Status = v21;
        v10 = 0;
        goto LABEL_188;
      }
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
      {
        WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 65, WPP_b4b9d8ac9d1830ce077ccb64ddccb5ed_Traceguids, v2);
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
      v17 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) == 0
        || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
      {
        goto LABEL_188;
      }
      v18 = 66;
      v19 = 3221225626LL;
LABEL_139:
      WPP_SF_d(v17->AttachedDevice, v18, WPP_b4b9d8ac9d1830ce077ccb64ddccb5ed_Traceguids, v19);
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
          WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 78, WPP_b4b9d8ac9d1830ce077ccb64ddccb5ed_Traceguids, v2);
        }
        _InterlockedAdd((volatile signed __int32 *)(v2 + 4716), 1u);
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
            WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 61, WPP_b4b9d8ac9d1830ce077ccb64ddccb5ed_Traceguids, v2);
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
            WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 62, WPP_b4b9d8ac9d1830ce077ccb64ddccb5ed_Traceguids, v2);
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
          WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 79, WPP_b4b9d8ac9d1830ce077ccb64ddccb5ed_Traceguids, v2);
        }
        if ( _InterlockedDecrement((volatile signed __int32 *)(v2 + 4716)) < 0
          && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        {
          WPP_SF_qd(
            WPP_GLOBAL_Control->AttachedDevice,
            80,
            WPP_b4b9d8ac9d1830ce077ccb64ddccb5ed_Traceguids,
            v2,
            *(_DWORD *)(v2 + 4716));
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
      WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 64, WPP_b4b9d8ac9d1830ce077ccb64ddccb5ed_Traceguids, v2);
    }
    IoForwardIrpSynchronously(*(PDEVICE_OBJECT *)(v2 + 112), a2);
    Status = a2->IoStatus.Status;
    if ( Status != -2147483626 )
    {
      v15 = Status == -1073741805;
LABEL_96:
      if ( !v15 )
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
        WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 73, WPP_b4b9d8ac9d1830ce077ccb64ddccb5ed_Traceguids, v2);
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
          WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 74, WPP_b4b9d8ac9d1830ce077ccb64ddccb5ed_Traceguids, v2);
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
          WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 81, WPP_b4b9d8ac9d1830ce077ccb64ddccb5ed_Traceguids, v2);
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
        WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 76, WPP_b4b9d8ac9d1830ce077ccb64ddccb5ed_Traceguids, v2);
      }
      v21 = FveDiskVerify(a1, a2);
      goto LABEL_127;
    case 0x70024u:
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
      {
        WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 69, WPP_b4b9d8ac9d1830ce077ccb64ddccb5ed_Traceguids, v2);
      }
      LOBYTE(v12) = 1;
      FvepAcquireDevFveLock(v2, Pool2, v12);
      v16 = FveDiscoverVolume((PVOID)v2);
      Status = v16;
      if ( (unsigned int)(*(_DWORD *)(v2 + 836) - 2) > 2 && v16 >= 0 )
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
            WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 71, WPP_b4b9d8ac9d1830ce077ccb64ddccb5ed_Traceguids);
          }
          Status = -1073741662;
          if ( (unsigned int)dword_140045040 > 4 && (unsigned __int8)tlgKeywordOn(&dword_140045040, 0x400000000000LL) )
          {
            v31 = *(unsigned int *)(v2 + 852);
            v34 = 8;
            v33 = &v31;
            v30 = -1073741662;
            v35 = &v30;
            v36 = 4;
            tlgWriteTransfer_EtwWriteTransfer(v20, (unsigned __int8 *)&word_14003C67E, 0, 0, 4u, &v32);
          }
          goto LABEL_188;
        }
        goto LABEL_126;
      }
      v17 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) == 0
        || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
      {
        goto LABEL_188;
      }
      v18 = 70;
      v19 = (unsigned int)Status;
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
    WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 63, WPP_b4b9d8ac9d1830ce077ccb64ddccb5ed_Traceguids, v2);
  }
  IoForwardIrpSynchronously(*(PDEVICE_OBJECT *)(v2 + 112), a2);
  Status = a2->IoStatus.Status;
  if ( Status >= 0 )
  {
    v14 = *(_DWORD *)(v2 + 836);
    if ( v14 != 8 )
    {
      v15 = v14 == 1;
      goto LABEL_96;
    }
    goto LABEL_97;
  }
  if ( Status == -1073741805 )
  {
    LOBYTE(v13) = 1;
    FvepAcquireDevFveLock(v2, Pool2, v13);
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
  if ( v10 )
  {
LABEL_189:
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
    {
      WPP_SF_d(
        WPP_GLOBAL_Control->AttachedDevice,
        83,
        WPP_b4b9d8ac9d1830ce077ccb64ddccb5ed_Traceguids,
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
0x14002f430  mov     [rsp+arg_10], rbx
0x14002f435  push    rbp
0x14002f436  push    rsi
0x14002f437  push    rdi
0x14002f438  push    r12
0x14002f43a  push    r13
0x14002f43c  push    r14
0x14002f43e  push    r15
0x14002f440  sub     rsp, 0A0h
0x14002f447  mov     rax, cs:__security_cookie
0x14002f44e  xor     rax, rsp
0x14002f451  mov     [rsp+0D8h+var_48], rax
0x14002f459  mov     rbx, [rcx+40h]
0x14002f45d  xor     r13d, r13d
0x14002f460  mov     rsi, rdx
0x14002f463  mov     r15, rcx
0x14002f466  cmp     [rbx], r13
0x14002f469  jnz     short loc_14002F47C
0x14002f46b  mov     edi, 0C0000010h
0x14002f470  mov     [rdx+38h], r13
0x14002f474  mov     [rdx+30h], edi
0x14002f477  jmp     loc_140030024
0x14002f47c  mov     rax, [rbx+8]
0x14002f480  cmp     [rax+8], r15
0x14002f484  jnz     short loc_14002F490
0x14002f486  call    BlCdoFilterIoctl
0x14002f48b  jmp     loc_140030037
0x14002f490  mov     rax, [rdx+0B8h]
0x14002f497  mov     r8d, 30455646h
0x14002f49d  mov     ebp, [rax+18h]
0x14002f4a0  mov     [rdx+38h], r13
0x14002f4a4  mov     edx, 90h
0x14002f4a9  lea     ecx, [rdx-50h]
0x14002f4ac  call    cs:__imp_ExAllocatePool2
0x14002f4b3  nop     dword ptr [rax+rax+00h]
0x14002f4b8  mov     r12, rax
0x14002f4bb  mov     edi, 10h
0x14002f4c0  lea     rax, WPP_GLOBAL_Control
0x14002f4c7  test    r12, r12
0x14002f4ca  jnz     short loc_14002F4D6
0x14002f4cc  mov     edi, 0C000009Ah
0x14002f4d1  jmp     loc_14002FFF0
0x14002f4d6  mov     r14d, 1
0x14002f4dc  call    Feature_BitLockerEphemeralVolumeSupport__private_IsEnabledDeviceUsageNoInline
0x14002f4e1  test    eax, eax
0x14002f4e3  jz      loc_14002F589
0x14002f4e9  test    byte ptr [rbx+1133h], 8
0x14002f4f0  jz      loc_14002F589
0x14002f4f6  mov     eax, ebp
0x14002f4f8  and     eax, 0FFFF0000h
0x14002f4fd  cmp     eax, 45560000h
0x14002f502  jnz     loc_14002F589
0x14002f508  mov     eax, ebp
0x14002f50a  sub     eax, 45561083h
0x14002f50f  jz      short loc_14002F589
0x14002f511  sub     eax, 5
0x14002f514  jz      short loc_14002F589
0x14002f516  sub     eax, 24h ; '$'
0x14002f519  jz      short loc_14002F589
0x14002f51b  sub     eax, 1Ch
0x14002f51e  jz      short loc_14002F589
0x14002f520  sub     eax, 0Ch
0x14002f523  jz      short loc_14002F589
0x14002f525  sub     eax, 3FBFh
0x14002f52a  jz      short loc_14002F589
0x14002f52c  sub     eax, 7FF4h
0x14002f531  jz      short loc_14002F589
0x14002f533  cmp     eax, 19h
0x14002f536  jz      short loc_14002F589
0x14002f538  mov     edi, 0C0210061h
0x14002f53d  mov     rcx, cs:WPP_GLOBAL_Control
0x14002f544  lea     rax, WPP_GLOBAL_Control
0x14002f54b  cmp     rcx, rax
0x14002f54e  jz      loc_14002FFD0
0x14002f554  mov     eax, [rcx+2Ch]
0x14002f557  test    al, 10h
0x14002f559  jz      loc_14002FFD0
0x14002f55f  cmp     byte ptr [rcx+29h], 2
0x14002f563  jb      loc_14002FFD0
0x14002f569  mov     rcx, [rcx+18h]
0x14002f56d  lea     edx, [r14+3Ah]
0x14002f571  mov     r9d, edi
0x14002f574  mov     dword ptr [rsp+0D8h+var_B8], ebp
0x14002f578  lea     r8, WPP_b4b9d8ac9d1830ce077ccb64ddccb5ed_Traceguids
0x14002f57f  call    WPP_SF_Dd
0x14002f584  jmp     loc_14002FFD0
0x14002f589  mov     eax, 2D4800h
0x14002f58e  cmp     ebp, eax
0x14002f590  ja      loc_14002FA26
0x14002f596  jz      loc_14002F9A8
0x14002f59c  mov     eax, 74004h
0x14002f5a1  cmp     ebp, eax
0x14002f5a3  ja      loc_14002F89B
0x14002f5a9  jz      loc_14002F95F
0x14002f5af  mov     eax, ebp
0x14002f5b1  sub     eax, 70000h
0x14002f5b6  jz      short loc_14002F5DB
0x14002f5b8  sub     eax, 14h
0x14002f5bb  jz      loc_14002F7DB
0x14002f5c1  sub     eax, edi
0x14002f5c3  jz      loc_14002F649
0x14002f5c9  sub     eax, 24h ; '$'
0x14002f5cc  jz      loc_14002F95F
0x14002f5d2  cmp     eax, 58h ; 'X'
0x14002f5d5  jnz     loc_14002FDF1
0x14002f5db  mov     rcx, cs:WPP_GLOBAL_Control
0x14002f5e2  lea     rax, WPP_GLOBAL_Control
0x14002f5e9  cmp     rcx, rax
0x14002f5ec  jz      short loc_14002F614
0x14002f5ee  mov     eax, [rcx+2Ch]
0x14002f5f1  test    dil, al
0x14002f5f4  jz      short loc_14002F614
0x14002f5f6  cmp     byte ptr [rcx+29h], 5
0x14002f5fa  jb      short loc_14002F614
0x14002f5fc  mov     rcx, [rcx+18h]
0x14002f600  lea     r8, WPP_b4b9d8ac9d1830ce077ccb64ddccb5ed_Traceguids
0x14002f607  mov     edx, 3Fh ; '?'
0x14002f60c  mov     r9, rbx
0x14002f60f  call    WPP_SF_q
0x14002f614  mov     rcx, [rbx+70h]; DeviceObject
0x14002f618  mov     rdx, rsi; Irp
0x14002f61b  call    cs:__imp_IoForwardIrpSynchronously
0x14002f622  nop     dword ptr [rax+rax+00h]
0x14002f627  mov     edi, [rsi+30h]
0x14002f62a  test    edi, edi
0x14002f62c  js      loc_14002F824
0x14002f632  mov     eax, [rbx+344h]
0x14002f638  cmp     eax, 8
0x14002f63b  jz      loc_14002FA14
0x14002f641  cmp     eax, r14d
0x14002f644  jmp     loc_14002FA0E
0x14002f649  mov     rcx, cs:WPP_GLOBAL_Control
0x14002f650  lea     rbp, WPP_GLOBAL_Control
0x14002f657  cmp     rcx, rbp
0x14002f65a  jz      short loc_14002F682
0x14002f65c  mov     eax, [rcx+2Ch]
0x14002f65f  test    dil, al
0x14002f662  jz      short loc_14002F682
0x14002f664  cmp     byte ptr [rcx+29h], 5
0x14002f668  jb      short loc_14002F682
0x14002f66a  mov     rcx, [rcx+18h]
0x14002f66e  lea     r8, WPP_b4b9d8ac9d1830ce077ccb64ddccb5ed_Traceguids
0x14002f675  mov     edx, 45h ; 'E'
0x14002f67a  mov     r9, rbx
0x14002f67d  call    WPP_SF_q
0x14002f682  mov     r8b, r14b
0x14002f685  mov     rdx, r12
0x14002f688  mov     rcx, rbx
0x14002f68b  call    FvepAcquireDevFveLock
0x14002f690  xor     r8d, r8d
0x14002f693  xor     edx, edx
0x14002f695  mov     rcx, rbx; Context
0x14002f698  call    FveDiscoverVolume
0x14002f69d  mov     ecx, [rbx+344h]
0x14002f6a3  mov     edi, eax
0x14002f6a5  sub     ecx, 2
0x14002f6a8  cmp     ecx, 2
0x14002f6ab  jbe     short loc_14002F6CB
0x14002f6ad  test    eax, eax
0x14002f6af  js      short loc_14002F6CB
0x14002f6b1  mov     edi, [rbx+330h]
0x14002f6b7  test    edi, edi
0x14002f6b9  js      short loc_14002F6CB
0x14002f6bb  mov     edi, [rbx+32Ch]
0x14002f6c1  mov     eax, 0C0000001h
0x14002f6c6  test    edi, edi
0x14002f6c8  cmovns  edi, eax
0x14002f6cb  mov     rcx, r12
0x14002f6ce  call    FvepReleaseDevFveLock
0x14002f6d3  test    edi, edi
0x14002f6d5  jns     short loc_14002F709
0x14002f6d7  mov     rcx, cs:WPP_GLOBAL_Control
0x14002f6de  cmp     rcx, rbp
0x14002f6e1  jz      loc_14002FFD0
0x14002f6e7  mov     eax, [rcx+2Ch]
0x14002f6ea  test    al, 10h
0x14002f6ec  jz      loc_14002FFD0
0x14002f6f2  cmp     byte ptr [rcx+29h], 2
0x14002f6f6  jb      loc_14002FFD0
0x14002f6fc  mov     edx, 46h ; 'F'
0x14002f701  mov     r9d, edi
0x14002f704  jmp     loc_14002FD22
0x14002f709  mov     eax, [rbx+354h]
0x14002f70f  test    al, 8
0x14002f711  jz      loc_14002FC4B
0x14002f717  mov     rcx, cs:WPP_GLOBAL_Control
0x14002f71e  cmp     rcx, rbp
0x14002f721  jz      short loc_14002F745
0x14002f723  mov     eax, [rcx+2Ch]
0x14002f726  test    al, 10h
0x14002f728  jz      short loc_14002F745
0x14002f72a  cmp     byte ptr [rcx+29h], 5
0x14002f72e  jb      short loc_14002F745
0x14002f730  mov     rcx, [rcx+18h]
0x14002f734  lea     r8, WPP_b4b9d8ac9d1830ce077ccb64ddccb5ed_Traceguids
0x14002f73b  mov     edx, 47h ; 'G'
0x14002f740  call    WPP_SF_
0x14002f745  mov     eax, cs:dword_140045040
0x14002f74b  mov     edi, 0C00000A2h
0x14002f750  cmp     eax, 4
0x14002f753  jbe     loc_14002FFD0
0x14002f759  mov     rdx, 400000000000h
0x14002f763  lea     rcx, dword_140045040
0x14002f76a  call    _tlgKeywordOn
0x14002f76f  test    al, al
0x14002f771  jz      loc_14002FFD0
0x14002f777  mov     eax, [rbx+354h]
0x14002f77d  lea     rdx, word_14003C67E
0x14002f784  mov     [rsp+0D8h+var_90], rax
0x14002f789  xor     r9d, r9d
0x14002f78c  lea     rax, [rsp+0D8h+var_90]
0x14002f791  mov     [rsp+0D8h+var_60], 8
0x14002f79a  mov     [rsp+0D8h+var_68], rax
0x14002f79f  xor     r8d, r8d
0x14002f7a2  lea     rax, [rsp+0D8h+var_98]
0x14002f7a7  mov     [rsp+0D8h+var_98], edi
0x14002f7ab  mov     [rsp+0D8h+var_58], rax
0x14002f7b3  lea     rax, [rsp+0D8h+var_88]
0x14002f7b8  mov     [rsp+0D8h+var_B0], rax
0x14002f7bd  mov     dword ptr [rsp+0D8h+var_B8], 4
0x14002f7c5  mov     [rsp+0D8h+var_50], 4
0x14002f7d1  call    _tlgWriteTransfer_EtwWriteTransfer
0x14002f7d6  jmp     loc_14002FFD0
0x14002f7db  mov     rcx, cs:WPP_GLOBAL_Control
0x14002f7e2  lea     rax, WPP_GLOBAL_Control
0x14002f7e9  cmp     rcx, rax
0x14002f7ec  jz      short loc_14002F814
0x14002f7ee  mov     eax, [rcx+2Ch]
0x14002f7f1  test    dil, al
0x14002f7f4  jz      short loc_14002F814
0x14002f7f6  cmp     byte ptr [rcx+29h], 5
0x14002f7fa  jb      short loc_14002F814
0x14002f7fc  mov     rcx, [rcx+18h]
0x14002f800  lea     r8, WPP_b4b9d8ac9d1830ce077ccb64ddccb5ed_Traceguids
0x14002f807  mov     edx, 4Ch ; 'L'
0x14002f80c  mov     r9, rbx
0x14002f80f  call    WPP_SF_q
0x14002f814  mov     rdx, rsi
0x14002f817  mov     rcx, r15
0x14002f81a  call    FveDiskVerify
0x14002f81f  jmp     loc_14002FC56
0x14002f824  cmp     edi, 0C0000013h
0x14002f82a  jnz     loc_14002FFD0
0x14002f830  mov     r8b, r14b
0x14002f833  mov     rdx, r12
0x14002f836  mov     rcx, rbx
0x14002f839  call    FvepAcquireDevFveLock
0x14002f83e  cmp     [rbx+418h], r13
0x14002f845  jbe     short loc_14002F88E
0x14002f847  mov     rcx, rbx
0x14002f84a  call    FveRundownAllReadsAndWrites
0x14002f84f  mov     ebp, 3Ah ; ':'
0x14002f854  xor     r9d, r9d
0x14002f857  xor     r8d, r8d
0x14002f85a  mov     dword ptr [rsp+0D8h+var_B8], ebp
0x14002f85e  mov     edx, 8000h
0x14002f863  mov     rcx, rbx
0x14002f866  call    SetFveState
0x14002f86b  mov     rcx, rbx
0x14002f86e  mov     [rbx+418h], r13
0x14002f875  mov     [rbx+344h], r14d
0x14002f87c  call    FveResumeAllReadsAndWrites
0x14002f881  mov     r8b, r14b
0x14002f884  mov     edx, ebp
0x14002f886  mov     rcx, rbx
0x14002f889  call    FveTestDevStateChange
0x14002f88e  mov     rcx, r12
0x14002f891  call    FvepReleaseDevFveLock
0x14002f896  jmp     loc_14002FFD0
0x14002f89b  cmp     ebp, 7405Ch
0x14002f8a1  jz      loc_14002F95F
0x14002f8a7  cmp     ebp, 74800h
0x14002f8ad  jz      loc_14002F9A8
0x14002f8b3  cmp     ebp, 7C064h
0x14002f8b9  jz      short loc_14002F91C
0x14002f8bb  cmp     ebp, 2D0800h
0x14002f8c1  jz      loc_14002F9A8
0x14002f8c7  cmp     ebp, 2D08C0h
0x14002f8cd  jnz     loc_14002FDF1
0x14002f8d3  mov     rcx, cs:WPP_GLOBAL_Control
0x14002f8da  lea     rax, WPP_GLOBAL_Control
0x14002f8e1  cmp     rcx, rax
0x14002f8e4  jz      short loc_14002F90C
0x14002f8e6  mov     eax, [rcx+2Ch]
0x14002f8e9  test    dil, al
0x14002f8ec  jz      short loc_14002F90C
0x14002f8ee  cmp     byte ptr [rcx+29h], 5
0x14002f8f2  jb      short loc_14002F90C
0x14002f8f4  mov     rcx, [rcx+18h]
0x14002f8f8  lea     r8, WPP_b4b9d8ac9d1830ce077ccb64ddccb5ed_Traceguids
0x14002f8ff  mov     edx, 51h ; 'Q'
0x14002f904  mov     r9, rbx
0x14002f907  call    WPP_SF_q
0x14002f90c  mov     rdx, rsi
0x14002f90f  mov     rcx, rbx
0x14002f912  call    IoctlStorageManageBypassIo
0x14002f917  jmp     loc_14002FDC4
0x14002f91c  mov     rcx, cs:WPP_GLOBAL_Control
0x14002f923  lea     rax, WPP_GLOBAL_Control
0x14002f92a  cmp     rcx, rax
  ... truncated ...
```
