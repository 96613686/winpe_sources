# ClassDispatchPnp

- ea: `0x14005fe50`
- end: `0x140061415`
- name: `ClassDispatchPnp`
- size: `5573`
- prototype: `__int64 __fastcall(PDEVICE_OBJECT DeviceObject, PIRP Irp)`
- caller_count: `0`
- callee_count: `29`
- tags: `file_ops, registry_config, loader_planting, installer_update, broker_com_uri`

## callees

- `0x140001008`
- `0x1400010f8`
- `0x140005190`
- `0x1400134a0`
- `0x1400157d0`
- `0x1400175e0`
- `0x140018018`
- `0x14001feac`
- `0x14002249c`
- `0x140022668`
- `0x1400231f0`
- `0x140025074`
- `0x140026690`
- `0x14002675c`
- `0x140026804`
- `0x140027870`
- `0x1400278d4`
- `0x14002794c`
- `0x140027a84`
- `0x1400317e0`
- `0x14003e430`
- `0x14003e470`
- `0x1400569e4`
- `0x14005792c`
- `0x1400579b4`
- `0x140058974`
- `0x14005bef0`
- `0x14005e53c`
- `0x14005fe50`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x140060bb2`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140060bb2`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400610bd`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400610bd`
- `ntoskrnl!KeSetEvent` at `0x140060c0e`
- `ntoskrnl!KeSetEvent` at `0x140060c0e`
- `ntoskrnl!ExAllocatePool2` at `0x140060dab`
- `ntoskrnl!ExAllocatePool2` at `0x140061255`
- `ntoskrnl!ExAllocatePool2` at `0x140060dab`
- `ntoskrnl!ExAllocatePool2` at `0x140061255`
- `ntoskrnl!IofCallDriver` at `0x1400604e4`
- `ntoskrnl!IofCallDriver` at `0x140060747`
- `ntoskrnl!IofCallDriver` at `0x14006135c`
- `ntoskrnl!IofCallDriver` at `0x1400604e4`
- `ntoskrnl!IofCallDriver` at `0x140060747`
- `ntoskrnl!IofCallDriver` at `0x14006135c`
- `ntoskrnl!ExFreePoolWithTag` at `0x140060e68`
- `ntoskrnl!ExFreePoolWithTag` at `0x140060f00`
- `ntoskrnl!ExFreePoolWithTag` at `0x140060e68`
- `ntoskrnl!ExFreePoolWithTag` at `0x140060f00`
- `ntoskrnl!KeInitializeEvent` at `0x140060e1a`
- `ntoskrnl!KeInitializeEvent` at `0x140060e1a`
- `ntoskrnl!KeWaitForSingleObject` at `0x140060bd9`
- `ntoskrnl!KeWaitForSingleObject` at `0x140060bd9`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140060c1a`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140060c1a`
- `ntoskrnl!ExWaitForRundownProtectionReleaseCacheAware` at `0x140060edd`
- `ntoskrnl!ExWaitForRundownProtectionReleaseCacheAware` at `0x140060edd`
- `ntoskrnl!KdDebuggerNotPresent` at `0x140060d8c`
- `ntoskrnl!ExReleaseFastMutex` at `0x140060f6e`
- `ntoskrnl!ExReleaseFastMutex` at `0x140060f6e`
- `ntoskrnl!IoClearActivityIdThread` at `0x140060207`
- `ntoskrnl!IoClearActivityIdThread` at `0x1400602fa`
- `ntoskrnl!IoClearActivityIdThread` at `0x14006045f`
- `ntoskrnl!IoClearActivityIdThread` at `0x140060207`
- `ntoskrnl!IoClearActivityIdThread` at `0x1400602fa`
- `ntoskrnl!IoClearActivityIdThread` at `0x14006045f`
- `ntoskrnl!IoGetActivityIdIrp` at `0x14005ffa8`
- `ntoskrnl!IoGetActivityIdIrp` at `0x14005ffa8`
- `ntoskrnl!IoGetDriverObjectExtension` at `0x14005feab`
- `ntoskrnl!IoGetDriverObjectExtension` at `0x14005feab`
- `ntoskrnl!ExAllocateCacheAwareRundownProtection` at `0x140060e37`
- `ntoskrnl!ExAllocateCacheAwareRundownProtection` at `0x140060e37`
- `ntoskrnl!ObfReferenceObject` at `0x140061278`
- `ntoskrnl!ObfReferenceObject` at `0x140061278`
- `ntoskrnl!ExAcquireFastMutex` at `0x140060ec3`
- `ntoskrnl!ExAcquireFastMutex` at `0x140060ec3`
- `ntoskrnl!IoPropagateActivityIdToThread` at `0x1400601a7`
- `ntoskrnl!IoPropagateActivityIdToThread` at `0x140060230`
- `ntoskrnl!IoPropagateActivityIdToThread` at `0x1400603d4`
- `ntoskrnl!IoPropagateActivityIdToThread` at `0x1400601a7`
- `ntoskrnl!IoPropagateActivityIdToThread` at `0x140060230`
- `ntoskrnl!IoPropagateActivityIdToThread` at `0x1400603d4`
- `ntoskrnl!ExFreeCacheAwareRundownProtection` at `0x140060f46`
- `ntoskrnl!ExFreeCacheAwareRundownProtection` at `0x140060f46`

## string_xrefs

- `0x140060090`: `REMOVE`
- `0x1400602bd`: `REMOVE`

## pseudocode

```c
__int64 __fastcall ClassDispatchPnp(PDEVICE_OBJECT DeviceObject, PIRP Irp)
{
  struct _COMMON_DEVICE_EXTENSION *DeviceExtension; // r14
  _IO_STACK_LOCATION *CurrentStackLocation; // r13
  int Status; // esi
  struct _DRIVER_OBJECT *DriverObject; // rcx
  char v8; // bl
  char v9; // r12
  char v10; // bl
  const char *v11; // rcx
  int v12; // edx
  __int64 v13; // r8
  __int64 v14; // r9
  unsigned int MinorFunction; // ecx
  __int64 v16; // rdx
  const char *v17; // r8
  const char *v18; // r12
  const char *v19; // rax
  const char *v20; // rax
  __int64 v21; // rdx
  char v22; // r12
  char v23; // bl
  int v24; // eax
  int v25; // r8d
  __int64 v26; // rcx
  NTSTATUS started; // eax
  char v28; // si
  NTSTATUS v29; // eax
  NTSTATUS v30; // ecx
  unsigned __int8 v31; // al
  bool v32; // zf
  _IO_STACK_LOCATION *v33; // rax
  int v34; // ecx
  __int64 v35; // rcx
  char v36; // r13
  _QWORD *v37; // rdx
  int v38; // ecx
  __int64 v39; // rax
  __int64 v40; // rcx
  wchar_t *v41; // rax
  UCHAR v42; // r13
  _LARGE_INTEGER v43; // rax
  __int128 *v44; // r8
  int v45; // ecx
  __int64 v46; // r8
  int v47; // r9d
  _IO_STACK_LOCATION *v48; // rax
  unsigned int Options; // ebx
  unsigned int v50; // ebx
  unsigned int v51; // ebx
  unsigned int v52; // ebx
  unsigned int v53; // ebx
  int FdoRelations; // eax
  _BYTE *v55; // rbx
  int v56; // ecx
  int v57; // r8d
  int v58; // r9d
  _LARGE_INTEGER PartitionLength; // rax
  PDEVICE_OBJECT v60; // rcx
  __int64 v61; // rdx
  __int64 v62; // r9
  struct _KEVENT *p_PathCountEvent; // rcx
  __int64 v64; // r9
  unsigned int PagingPathCount; // eax
  wchar_t *v66; // rax
  wchar_t *v67; // rcx
  wchar_t *v68; // rbx
  wchar_t *v69; // rcx
  void *v70; // rcx
  wchar_t *v71; // rcx
  void *v72; // rcx
  wchar_t *Buffer; // rax
  unsigned int v74; // r12d
  _IO_SECURITY_CONTEXT *SecurityContext; // r13
  __int64 v76; // r12
  unsigned int Length; // r13d
  ULONG_PTR Pool2; // rax
  int *Information; // rax
  int v80; // ecx
  _IO_STACK_LOCATION *v81; // rax
  char v83; // [rsp+40h] [rbp-79h] BYREF
  char v84; // [rsp+41h] [rbp-78h]
  char v85; // [rsp+42h] [rbp-77h]
  char v86; // [rsp+43h] [rbp-76h]
  UCHAR RemoveType[8]; // [rsp+48h] [rbp-71h] BYREF
  unsigned int v88; // [rsp+50h] [rbp-69h] BYREF
  _QWORD *DriverObjectExtension; // [rsp+58h] [rbp-61h]
  __int128 v90; // [rsp+60h] [rbp-59h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+70h] [rbp-49h] BYREF
  __int128 v92; // [rsp+80h] [rbp-39h] BYREF
  __int64 v93[4]; // [rsp+90h] [rbp-29h] BYREF
  __int64 v94; // [rsp+B0h] [rbp-9h]
  __int64 v95; // [rsp+B8h] [rbp-1h]
  char *v96; // [rsp+C0h] [rbp+7h]
  __int64 v97; // [rsp+C8h] [rbp+Fh]

  DeviceExtension = (struct _COMMON_DEVICE_EXTENSION *)DeviceObject->DeviceExtension;
  CurrentStackLocation = Irp->Tail.Overlay.CurrentStackLocation;
  Status = Irp->IoStatus.Status;
  DriverObject = DeviceObject->DriverObject;
  v8 = *((_BYTE *)DeviceExtension + 104);
  v88 = 2;
  v90 = 0;
  DriverObjectExtension = IoGetDriverObjectExtension(DriverObject, ClassInitialize);
  if ( !DriverObjectExtension )
  {
    Status = -1073741595;
    goto LABEL_327;
  }
  v86 = 0;
  v83 = 0;
  v85 = 0;
  v9 = 1;
  v10 = v8 & 1;
  v84 = v10;
  ClassAcquireRemoveLockEx(DeviceObject, Irp, "minkernel\\storage\\classpnp\\class.c", 0x561u);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
  {
    if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      v11 = "fdo";
      if ( !v10 )
        v11 = "pdo";
      WPP_SF_qqDsq(
        WPP_GLOBAL_Control->AttachedDevice,
        (_DWORD)WPP_GLOBAL_Control,
        (unsigned int)"pdo",
        (_DWORD)DeviceObject,
        (char)Irp,
        CurrentStackLocation->MinorFunction,
        (__int64)v11,
        (char)DeviceObject);
    }
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_qqDD(
        WPP_GLOBAL_Control->AttachedDevice,
        20,
        WPP_GLOBAL_Control,
        DeviceObject,
        Irp,
        DeviceExtension->PreviousState,
        DeviceExtension->CurrentState);
    }
  }
  if ( (int)IoGetActivityIdIrp(Irp, &v90) < 0 )
  {
    LOBYTE(v13) = v83;
    LOBYTE(v14) = v83;
  }
  else
  {
    LOBYTE(v13) = ClassPnPETWEnabled;
    LOBYTE(v14) = 1;
    v85 = 1;
    v83 = ClassPnPETWEnabled;
    if ( ClassPnPETWEnabled )
    {
      MinorFunction = CurrentStackLocation->MinorFunction;
      if ( (unsigned __int8)MinorFunction > 0x16u || (v12 = 4718720, !_bittest(&v12, MinorFunction)) )
      {
        if ( (BYTE2(WPP_MAIN_CB.Queue.Wcb.CurrentIrp) & 0x10) != 0 )
        {
          McTemplateK0qpddp_EtwWriteTransfer(
            MinorFunction,
            v12,
            (unsigned int)&v90,
            HIDWORD(DeviceExtension[1].RemoveTrackingSpinlock),
            (char)Irp,
            MinorFunction,
            0,
            (char)DeviceObject);
          LOBYTE(v13) = v83;
          LOBYTE(v14) = 1;
        }
      }
    }
  }
  v16 = CurrentStackLocation->MinorFunction;
  *(_DWORD *)RemoveType = v16;
  if ( (unsigned int)v16 <= 6 )
  {
    switch ( (_DWORD)v16 )
    {
      case 6:
        goto LABEL_79;
      case 0:
        v88 = 3;
        if ( v84 && (Status = ClassForwardIrpSynchronous(DeviceExtension, Irp), Status < 0) )
        {
          v26 = 4;
          v88 = 4;
        }
        else
        {
          started = ClassPnpStartDevice(DeviceObject, &v88);
          Irp->IoStatus.Status = started;
          Status = started;
          if ( started >= 0 )
            goto LABEL_324;
          v26 = v88;
        }
        if ( !BootCompleted )
        {
          ClasspLogBootError(v26, (unsigned int)Status);
          goto LABEL_327;
        }
        goto LABEL_324;
      case 1:
LABEL_26:
        DestinationString = 0;
        *(_QWORD *)RemoveType = &DestinationString;
        v17 = "REMOVE";
        v18 = "STOP";
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
        {
          v19 = "STOP";
          if ( (_BYTE)v16 != 5 )
            v19 = "REMOVE";
          WPP_SF_qqs(
            WPP_GLOBAL_Control->AttachedDevice,
            21,
            (unsigned int)"REMOVE",
            (_DWORD)DeviceObject,
            (char)Irp,
            (__int64)v19);
        }
        if ( DeviceExtension->PagingPathCount )
        {
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
          {
            WPP_SF_qq(
              WPP_GLOBAL_Control->AttachedDevice,
              22,
              WPP_9ee7907f5c473329e20561a6f3486187_Traceguids,
              DeviceObject,
              Irp);
          }
          Status = -2147483631;
          goto LABEL_327;
        }
        if ( v85 )
          IoPropagateActivityIdToThread(Irp, &v90, RemoveType);
        LOBYTE(v16) = CurrentStackLocation->MinorFunction;
        v23 = v84;
        if ( (_BYTE)v16 == 5 )
          v24 = (*(__int64 (__fastcall **)(PDEVICE_OBJECT, __int64, const char *, __int64))((char *)DriverObjectExtension
                                                                                          + (-(__int64)(v84 != 0)
                                                                                           & 0xFFFFFFFFFFFFFF58uLL)
                                                                                          + 272))(
                  DeviceObject,
                  v16,
                  v17,
                  v14);
        else
          v24 = (*(__int64 (__fastcall **)(PDEVICE_OBJECT, __int64, const char *, __int64))((char *)DriverObjectExtension
                                                                                          + (-(__int64)(v84 != 0)
                                                                                           & 0xFFFFFFFFFFFFFF58uLL)
                                                                                          + 280))(
                  DeviceObject,
                  v16,
                  v17,
                  v14);
        Status = v24;
        if ( v24 >= 0 )
        {
          DeviceExtension->PreviousState = DeviceExtension->CurrentState;
          DeviceExtension->CurrentState = CurrentStackLocation->MinorFunction;
          if ( v23 )
          {
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
              && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
            {
              if ( CurrentStackLocation->MinorFunction != 5 )
                v18 = "REMOVE";
              WPP_SF_qqs(WPP_GLOBAL_Control->AttachedDevice, 23, v25, (_DWORD)DeviceObject, (char)Irp, (__int64)v18);
            }
            Status = ClassForwardIrpSynchronous(DeviceExtension, Irp);
          }
        }
        if ( v85 )
          IoClearActivityIdThread(*(_QWORD *)RemoveType);
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
        {
          WPP_SF_qqD(
            WPP_GLOBAL_Control->AttachedDevice,
            24,
            WPP_9ee7907f5c473329e20561a6f3486187_Traceguids,
            DeviceObject,
            Irp,
            Status);
          goto LABEL_327;
        }
        goto LABEL_324;
    }
    if ( (_DWORD)v16 != 2 )
    {
      if ( (_DWORD)v16 != 3 )
      {
        if ( (_DWORD)v16 == 4 )
        {
          DestinationString = 0;
          *(_QWORD *)RemoveType = &DestinationString;
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
          {
            v20 = "fdo";
            if ( !v84 )
              v20 = "pdo";
            WPP_SF_qqs(WPP_GLOBAL_Control->AttachedDevice, 25, v13, (_DWORD)DeviceObject, (char)Irp, (__int64)v20);
          }
          ClasspDisableTimer(DeviceExtension);
          v22 = v85;
          if ( v85 )
            IoPropagateActivityIdToThread(Irp, &v90, RemoveType);
          LOBYTE(v21) = 4;
          Status = (*(__int64 (__fastcall **)(PDEVICE_OBJECT, __int64))((char *)DriverObjectExtension
                                                                      + (-(__int64)(v84 != 0) & 0xFFFFFFFFFFFFFF58uLL)
                                                                      + 272))(
                     DeviceObject,
                     v21);
          if ( v84 )
            Status = ClassForwardIrpSynchronous(DeviceExtension, Irp);
          if ( Status >= 0 )
          {
            DeviceExtension->CurrentState = CurrentStackLocation->MinorFunction;
            DeviceExtension->PreviousState = -1;
          }
          if ( v22 )
          {
            IoClearActivityIdThread(*(_QWORD *)RemoveType);
LABEL_327:
            Irp->IoStatus.Status = Status;
            goto LABEL_328;
          }
          goto LABEL_324;
        }
        goto LABEL_26;
      }
LABEL_79:
      *(_QWORD *)&DestinationString.Length = &v92;
      v92 = 0;
      if ( (_BYTE)v14 )
        IoPropagateActivityIdToThread(Irp, &v90, &DestinationString);
      v28 = v84;
      if ( CurrentStackLocation->MinorFunction == 6 )
        v29 = (*(__int64 (__fastcall **)(PDEVICE_OBJECT))((char *)DriverObjectExtension
                                                        + (-(__int64)(v84 != 0) & 0xFFFFFFFFFFFFFF58uLL)
                                                        + 272))(DeviceObject);
      else
        v29 = (*(__int64 (__fastcall **)(PDEVICE_OBJECT))((char *)DriverObjectExtension
                                                        + (-(__int64)(v84 != 0) & 0xFFFFFFFFFFFFFF58uLL)
                                                        + 280))(DeviceObject);
      v30 = v29;
      *(_DWORD *)RemoveType = v29;
      Irp->IoStatus.Status = v29;
      v31 = CurrentStackLocation->MinorFunction;
      if ( v31 == 6 )
      {
        v32 = DeviceExtension->CurrentState == 5;
      }
      else
      {
        if ( v31 != 3 )
        {
LABEL_90:
          if ( v85 )
          {
            IoClearActivityIdThread(*(_QWORD *)&DestinationString.Length);
            v30 = *(_DWORD *)RemoveType;
          }
          if ( !v28 )
          {
            Status = 0;
            Irp->IoStatus.Status = 0;
            goto LABEL_328;
          }
          if ( v83 && (BYTE2(WPP_MAIN_CB.Queue.Wcb.CurrentIrp) & 0x10) != 0 )
            McTemplateK0qpd_EtwWriteTransfer(
              v30,
              (unsigned int)EventPnpRequestComplete,
              (unsigned int)&v90,
              HIDWORD(DeviceExtension[1].RemoveTrackingSpinlock),
              (char)Irp,
              v30);
          goto LABEL_96;
        }
        v32 = DeviceExtension->CurrentState == 1;
      }
      if ( v32 )
      {
        DeviceExtension->CurrentState = DeviceExtension->PreviousState;
        DeviceExtension->PreviousState = -1;
      }
      goto LABEL_90;
    }
    goto LABEL_110;
  }
  v34 = v16 - 7;
  if ( (_DWORD)v16 == 7 )
  {
    Length = CurrentStackLocation->Parameters.Read.Length;
    if ( (_BYTE)v13 && (BYTE2(WPP_MAIN_CB.Queue.Wcb.CurrentIrp) & 0x10) != 0 )
      McTemplateK0qpddp_EtwWriteTransfer(
        v34,
        7,
        (unsigned int)&v90,
        HIDWORD(DeviceExtension[1].RemoveTrackingSpinlock),
        (char)Irp,
        7,
        Length,
        (char)DeviceObject);
    if ( v84 )
    {
      if ( Length
        || (v34 = (int)DriverObjectExtension, !DriverObjectExtension[46])
        || (FdoRelations = ClassPnpQueryFdoRelations(DeviceObject, Irp, v13, v14),
            Status = FdoRelations,
            FdoRelations >= 0) )
      {
        if ( v83 )
        {
          if ( Length )
          {
            if ( (BYTE2(WPP_MAIN_CB.Queue.Wcb.CurrentIrp) & 0x10) != 0 )
              McTemplateK0qpd_EtwWriteTransfer(
                v34,
                (unsigned int)EventPnpRequestComplete,
                (unsigned int)&v90,
                HIDWORD(DeviceExtension[1].RemoveTrackingSpinlock),
                (char)Irp,
                Status);
          }
          else if ( (BYTE2(WPP_MAIN_CB.Queue.Wcb.CurrentIrp) & 0x20) != 0 )
          {
            Information = (int *)Irp->IoStatus.Information;
            if ( Information )
              v80 = *Information;
            else
              v80 = 0;
            McTemplateK0qpqd_EtwWriteTransfer(
              v80,
              v16,
              (unsigned int)&v90,
              HIDWORD(DeviceExtension[1].RemoveTrackingSpinlock),
              (char)Irp,
              v80,
              Status);
          }
        }
        v81 = Irp->Tail.Overlay.CurrentStackLocation;
        *(_OWORD *)&v81[-1].MajorFunction = *(_OWORD *)&v81->MajorFunction;
        *(_OWORD *)&v81[-1].Parameters.NotifyDirectoryEx.CompletionFilter = *(_OWORD *)&v81->Parameters.NotifyDirectoryEx.CompletionFilter;
        *(_OWORD *)(&v81[-1].Parameters.SetQuota + 6) = *(_OWORD *)(&v81->Parameters.SetQuota + 6);
        v81[-1].FileObject = v81->FileObject;
        v81[-1].Control = 0;
        ClassReleaseRemoveLock(DeviceObject, Irp);
        Status = IofCallDriver(DeviceExtension->LowerDeviceObject, Irp);
        v9 = 0;
LABEL_323:
        if ( !v9 )
          goto LABEL_97;
LABEL_324:
        v32 = v86 == 0;
        Irp->IoStatus.Status = Status;
        if ( !v32 )
        {
LABEL_329:
          ClassCompleteRequest(DeviceObject, Irp, 0);
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
          {
            WPP_SF_qqDD(
              WPP_GLOBAL_Control->AttachedDevice,
              41,
              DeviceExtension->PreviousState,
              DeviceObject,
              Irp,
              DeviceExtension->PreviousState,
              DeviceExtension->CurrentState);
          }
          return (unsigned int)Status;
        }
LABEL_328:
        ClassReleaseRemoveLock(DeviceObject, Irp);
        goto LABEL_329;
      }
LABEL_149:
      Irp->IoStatus.Status = FdoRelations;
      goto LABEL_328;
    }
    if ( Length == 4 )
    {
      Status = -1073741670;
      Pool2 = ExAllocatePool2(256, 16, 843277139);
      if ( Pool2 )
      {
        Irp->IoStatus.Information = Pool2;
        *(_DWORD *)Pool2 = 1;
        *(_QWORD *)(Pool2 + 8) = DeviceObject;
        ObfReferenceObject(DeviceObject);
        Status = 0;
        goto LABEL_327;
      }
      goto LABEL_324;
    }
LABEL_284:
    Status = Irp->IoStatus.Status;
    goto LABEL_327;
  }
  if ( (_DWORD)v16 == 9 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_qq(
        WPP_GLOBAL_Control->AttachedDevice,
        39,
        WPP_9ee7907f5c473329e20561a6f3486187_Traceguids,
        DeviceObject,
        Irp);
    }
    if ( !v84 )
    {
      Status = ClassQueryPnpCapabilities(DeviceObject, CurrentStackLocation->Parameters.WMI.ProviderId, v13, v14);
      Irp->IoStatus.Status = Status;
      goto LABEL_328;
    }
    SecurityContext = CurrentStackLocation->Parameters.Create.SecurityContext;
    v76 = *((_QWORD *)DeviceObject->DeviceExtension + 143);
    Status = ClassForwardIrpSynchronous(DeviceExtension, Irp);
    if ( Status >= 0 && v76 && *(_BYTE *)(v76 + 1335) )
    {
      if ( (HIDWORD(SecurityContext->SecurityQos) & 0x200) != 0
        && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      {
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 40, WPP_9ee7907f5c473329e20561a6f3486187_Traceguids);
      }
      HIDWORD(SecurityContext->SecurityQos) &= ~0x200u;
      goto LABEL_327;
    }
    goto LABEL_324;
  }
  LODWORD(v35) = v16 - 19;
  if ( (_DWORD)v16 == 19 )
  {
    v74 = CurrentStackLocation->Parameters.Read.Length;
    DestinationString = 0;
    if ( (_BYTE)v13 && (BYTE2(WPP_MAIN_CB.Queue.Wcb.CurrentIrp) & 0x10) != 0 )
    {
      McTemplateK0qpddp_EtwWriteTransfer(
        0,
        v16,
        (unsigned int)&v90,
        HIDWORD(DeviceExtension[1].RemoveTrackingSpinlock),
        (char)Irp,
        19,
        v74,
        (char)DeviceObject);
      LOBYTE(v13) = v83;
    }
    if ( v84 )
      goto LABEL_275;
    RtlInitUnicodeString(&DestinationString, 0);
    Status = ClassGetPdoId(DeviceObject, v74, &DestinationString);
    if ( Status != -1073741822 )
    {
      Irp->IoStatus.Status = Status;
      if ( Status < 0 )
        Irp->IoStatus.Information = 0;
      else
        Irp->IoStatus.Information = (ULONG_PTR)DestinationString.Buffer;
      goto LABEL_328;
    }
    goto LABEL_284;
  }
  LODWORD(v35) = v16 - 20;
  if ( (_DWORD)v16 == 20 )
  {
    if ( !v84 )
      goto LABEL_324;
    Buffer = DeviceExtension[2].DeviceName.Buffer;
    if ( Buffer )
      *((_BYTE *)Buffer + 718) = 1;
    goto LABEL_275;
  }
  v35 = (unsigned int)(v16 - 22);
  if ( (_DWORD)v16 == 22 )
  {
    Options = CurrentStackLocation->Parameters.Create.Options;
    if ( (_BYTE)v13 && (BYTE2(WPP_MAIN_CB.Queue.Wcb.CurrentIrp) & 0x10) != 0 )
      McTemplateK0qpddp_EtwWriteTransfer(
        0,
        v16,
        (unsigned int)&v90,
        HIDWORD(DeviceExtension[1].RemoveTrackingSpinlock),
        (char)Irp,
        22,
        Options,
        (char)DeviceObject);
    v50 = Options - 1;
    if ( !v50 )
    {
      if ( CurrentStackLocation->Parameters.SetLock.Lock && DeviceExtension->CurrentState )
      {
        Status = -1073741661;
      }
      else
      {
        KeEnterCriticalRegion();
        KeWaitForSingleObject(&DeviceExtension->PathCountEvent, Executive, 0, 0, 0);
        if ( (*((_BYTE *)DeviceExtension + 104) & 1) != 0
          && (LOBYTE(v62) = CurrentStackLocation->Parameters.SetLock.Lock,
              Status = ClasspEjectionControl(DeviceObject, Irp, 2, v62),
              Status < 0) )
        {
          p_PathCountEvent = &DeviceExtension->PathCountEvent;
        }
        else
        {
          v32 = CurrentStackLocation->Parameters.SetLock.Lock == 0;
          v83 = 0;
          if ( v32 && DeviceExtension->PagingPathCount == 1 )
          {
            if ( (DeviceObject->Flags & 0x4000) != 0 )
            {
              if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
                && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
              {
                WPP_SF_qq(
                  WPP_GLOBAL_Control->AttachedDevice,
                  27,
                  WPP_9ee7907f5c473329e20561a6f3486187_Traceguids,
                  DeviceObject,
                  Irp);
              }
            }
            else if ( !DeviceExtension->HibernationPathCount && !DeviceExtension->DumpPathCount )
            {
              if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
                && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
              {
                WPP_SF_qq(
                  WPP_GLOBAL_Control->AttachedDevice,
                  28,
                  WPP_9ee7907f5c473329e20561a6f3486187_Traceguids,
                  DeviceObject,
                  Irp);
              }
              DeviceObject->Flags |= 0x2000u;
              v83 = 1;
            }
          }
          Status = ClassForwardIrpSynchronous(DeviceExtension, Irp);
          if ( Status < 0 )
          {
            if ( v83 == 1 )
            {
              if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
                && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
              {
                WPP_SF_qq(
                  WPP_GLOBAL_Control->AttachedDevice,
                  30,
                  WPP_9ee7907f5c473329e20561a6f3486187_Traceguids,
                  DeviceObject,
                  Irp);
              }
              DeviceObject->Flags &= ~0x2000u;
            }
            if ( (*((_BYTE *)DeviceExtension + 104) & 1) != 0 )
            {
              LOBYTE(v64) = CurrentStackLocation->Parameters.SetLock.Lock == 0;
              ClasspEjectionControl(DeviceObject, Irp, 2, v64);
            }
          }
          else
          {
            if ( CurrentStackLocation->Parameters.SetLock.Lock )
              _InterlockedAdd((volatile signed __int32 *)&DeviceExtension->PagingPathCount, 1u);
            else
              _InterlockedDecrement((volatile signed __int32 *)&DeviceExtension->PagingPathCount);
            if ( CurrentStackLocation->Parameters.SetLock.Lock )
            {
              PagingPathCount = DeviceExtension->PagingPathCount;
              if ( PagingPathCount == 1 )
              {
                if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                  && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
                  && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
                {
                  WPP_SF_qq(
                    WPP_GLOBAL_Control->AttachedDevice,
                    29,
                    WPP_9ee7907f5c473329e20561a6f3486187_Traceguids,
                    DeviceObject,
                    Irp);
                }
                DeviceObject->Flags &= ~0x2000u;
                if ( (*((_BYTE *)DeviceExtension + 104) & 1) != 0
                  && !ClassRegDisablePagefileCRC
                  && !(_BYTE)KdDebuggerNotPresent )
                {
                  *((_QWORD *)DeviceExtension[2].DeviceName.Buffer + 84) = ExAllocatePool2(64, 0x40000, 1129341779);
                  v66 = DeviceExtension[2].DeviceName.Buffer;
                  if ( *((_QWORD *)v66 + 84) )
                  {
                    *((_DWORD *)v66 + 206) = 0;
                    *((_DWORD *)DeviceExtension[2].DeviceName.Buffer + 205) = 0x2000;
                    v67 = DeviceExtension[2].DeviceName.Buffer;
                    *((_DWORD *)v67 + 190) = 1;
                    *((_QWORD *)v67 + 96) = 0;
                    *((_DWORD *)v67 + 194) = 0;
                    KeInitializeEvent((PRKEVENT)(v67 + 392), SynchronizationEvent, 0);
                    v68 = DeviceExtension[2].DeviceName.Buffer;
                    *((_QWORD *)v68 + 94) = ExAllocateCacheAwareRundownProtection(NonPagedPoolNx, 0x43506353u);
                    v69 = DeviceExtension[2].DeviceName.Buffer;
                    if ( !*((_QWORD *)v69 + 94) )
                    {
                      v70 = (void *)*((_QWORD *)v69 + 84);
                      if ( v70 )
                      {
                        ExFreePoolWithTag(v70, 0);
                        *((_QWORD *)DeviceExtension[2].DeviceName.Buffer + 84) = 0;
                      }
                    }
                  }
                  *((_QWORD *)DeviceExtension[2].DeviceName.Buffer + 92) = 0;
                }
              }
              else if ( !PagingPathCount && (*((_BYTE *)DeviceExtension + 104) & 1) != 0 )
              {
                v71 = DeviceExtension[2].DeviceName.Buffer;
                if ( *((_QWORD *)v71 + 84) )
                {
                  ExAcquireFastMutex((PFAST_MUTEX)(v71 + 380));
                  ExWaitForRundownProtectionReleaseCacheAware(*((PEX_RUNDOWN_REF_CACHE_AWARE *)DeviceExtension[2].DeviceName.Buffer
                                                              + 94));
                  v72 = (void *)*((_QWORD *)DeviceExtension[2].DeviceName.Buffer + 84);
                  if ( v72 )
                  {
                    ExFreePoolWithTag(v72, 0);
                    *((_QWORD *)DeviceExtension[2].DeviceName.Buffer + 84) = 0;
                  }
                  *((_DWORD *)DeviceExtension[2].DeviceName.Buffer + 206) = 0;
                  *((_DWORD *)DeviceExtension[2].DeviceName.Buffer + 205) = 0x2000;
                  ExFreeCacheAwareRundownProtection(*((PEX_RUNDOWN_REF_CACHE_AWARE *)DeviceExtension[2].DeviceName.Buffer
                                                    + 94));
                  *((_QWORD *)DeviceExtension[2].DeviceName.Buffer + 94) = 0;
                  ExReleaseFastMutex((PFAST_MUTEX)(DeviceExtension[2].DeviceName.Buffer + 380));
                }
              }
            }
          }
          p_PathCountEvent = &DeviceExtension->PathCountEvent;
        }
        KeSetEvent(p_PathCountEvent, 0, 0);
        KeLeaveCriticalRegion();
      }
      goto LABEL_327;
    }
    v51 = v50 - 1;
    if ( v51 )
    {
      v52 = v51 - 1;
      if ( v52 )
      {
        v53 = v52 - 1;
        if ( v53 )
        {
          if ( v53 != 3
            || !(unsigned int)Feature_SteelixInlineNvmeCryptoEngine__private_IsEnabledDeviceUsageNoInline(
                                v35,
                                v16,
                                v13,
                                v14) )
          {
            Status = -1073741811;
            goto LABEL_327;
          }
        }
        else if ( v84 )
        {
          v55 = (_BYTE *)*((_QWORD *)DeviceObject->DeviceExtension + 143);
          if ( v55 )
          {
            v55[717] = 1;
            if ( (unsigned int)dword_14004D060 > 5 && (unsigned __int8)tlgKeywordOn(v35, 0x400000000000LL, v13) )
            {
              PartitionLength = DeviceExtension[2].PartitionLength;
              v95 = 16;
              v94 = PartitionLength.QuadPart + 4;
              tlgWriteTransfer_EtwWriteTransfer(v56, (int)&byte_1400487B7, v57, v58, 3u, (__int64)v93);
            }
            if ( v55[1334] )
            {
              v55[1334] = 0;
              v55[1332] = 0;
              ClassSetDeviceParameter(
                (PFUNCTIONAL_DEVICE_EXTENSION)DeviceObject->DeviceExtension,
                (PWSTR)L"Classpnp",
                (PWSTR)L"UserRemovalPolicy",
                2u);
            }
          }
        }
        FdoRelations = ClassForwardIrpSynchronous(DeviceExtension, Irp);
        Status = FdoRelations;
        goto LABEL_149;
      }
      v32 = CurrentStackLocation->Parameters.SetLock.Lock == 0;
      v83 = 0;
      if ( v32 && DeviceExtension->DumpPathCount == 1 )
      {
        if ( (DeviceObject->Flags & 0x4000) != 0 )
        {
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
          {
            WPP_SF_qq(
              WPP_GLOBAL_Control->AttachedDevice,
              35,
              WPP_9ee7907f5c473329e20561a6f3486187_Traceguids,
              DeviceObject,
              Irp);
          }
        }
        else if ( !DeviceExtension->PagingPathCount && !DeviceExtension->HibernationPathCount )
        {
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
          {
            WPP_SF_qq(
              WPP_GLOBAL_Control->AttachedDevice,
              36,
              WPP_9ee7907f5c473329e20561a6f3486187_Traceguids,
              DeviceObject,
              Irp);
          }
          DeviceObject->Flags |= 0x2000u;
          v83 = 1;
        }
      }
      Status = ClassForwardIrpSynchronous(DeviceExtension, Irp);
      if ( Status >= 0 )
      {
        if ( CurrentStackLocation->Parameters.SetLock.Lock )
          _InterlockedAdd((volatile signed __int32 *)&DeviceExtension->DumpPathCount, 1u);
        else
          _InterlockedDecrement((volatile signed __int32 *)&DeviceExtension->DumpPathCount);
        if ( !CurrentStackLocation->Parameters.SetLock.Lock || DeviceExtension->DumpPathCount != 1 )
          goto LABEL_324;
        v60 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
        {
          v61 = 38;
          goto LABEL_178;
        }
      }
      else
      {
        if ( v83 != 1 )
          goto LABEL_324;
        v60 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
        {
          v61 = 37;
LABEL_178:
          WPP_SF_qq(v60->AttachedDevice, v61, WPP_9ee7907f5c473329e20561a6f3486187_Traceguids, DeviceObject, Irp);
        }
      }
    }
    else
    {
      v32 = CurrentStackLocation->Parameters.SetLock.Lock == 0;
      v83 = 0;
      if ( v32 && DeviceExtension->HibernationPathCount == 1 )
      {
        if ( (DeviceObject->Flags & 0x4000) != 0 )
        {
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
          {
            WPP_SF_qq(
              WPP_GLOBAL_Control->AttachedDevice,
              31,
              WPP_9ee7907f5c473329e20561a6f3486187_Traceguids,
              DeviceObject,
              Irp);
          }
        }
        else if ( !DeviceExtension->PagingPathCount && !DeviceExtension->DumpPathCount )
        {
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
          {
            WPP_SF_qq(
              WPP_GLOBAL_Control->AttachedDevice,
              32,
              WPP_9ee7907f5c473329e20561a6f3486187_Traceguids,
              DeviceObject,
              Irp);
          }
          DeviceObject->Flags |= 0x2000u;
          v83 = 1;
        }
      }
      Status = ClassForwardIrpSynchronous(DeviceExtension, Irp);
      if ( Status >= 0 )
      {
        if ( CurrentStackLocation->Parameters.SetLock.Lock )
          _InterlockedAdd((volatile signed __int32 *)&DeviceExtension->HibernationPathCount, 1u);
        else
          _InterlockedDecrement((volatile signed __int32 *)&DeviceExtension->HibernationPathCount);
        if ( !CurrentStackLocation->Parameters.SetLock.Lock || DeviceExtension->HibernationPathCount != 1 )
          goto LABEL_324;
        v60 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
        {
          v61 = 34;
          goto LABEL_178;
        }
      }
      else
      {
        if ( v83 != 1 )
          goto LABEL_324;
        v60 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
        {
          v61 = 33;
          goto LABEL_178;
        }
      }
    }
    DeviceObject->Flags &= ~0x2000u;
    goto LABEL_327;
  }
  if ( (_DWORD)v16 == 23 )
  {
LABEL_110:
    v36 = v84;
    if ( v84 )
    {
      if ( (_BYTE)v16 == 23 && (*((_BYTE *)DeviceExtension + 104) & 2) != 0 )
      {
        v37 = DeviceObject->DeviceExtension;
        v38 = *(_DWORD *)(v37[65] + 28LL);
        if ( v38 != 15 )
        {
          v39 = v37[143];
          if ( !*(_BYTE *)(v39 + 1332) && (!*(_BYTE *)(v39 + 1334) || v38 != 7 && v38 != 4) )
            ClasspLogSystemEventWithDeviceNumber(DeviceObject, 2147745949LL, v13, v14);
        }
      }
    }
    if ( DeviceExtension->PagingPathCount
      && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
    {
      WPP_SF_qq(
        WPP_GLOBAL_Control->AttachedDevice,
        26,
        WPP_9ee7907f5c473329e20561a6f3486187_Traceguids,
        DeviceObject,
        Irp);
    }
    ClassReleaseRemoveLock(DeviceObject, Irp);
    v86 = 1;
    DeviceExtension->IsRemoved = 1;
    ClasspDisableTimer(DeviceExtension);
    if ( v36 )
    {
      v41 = DeviceExtension[2].DeviceName.Buffer;
      if ( v41 )
        *((_BYTE *)v41 + 718) = 0;
      if ( v83 && (BYTE2(WPP_MAIN_CB.Queue.Wcb.CurrentIrp) & 0x10) != 0 )
        McTemplateK0qpd_EtwWriteTransfer(
          v40,
          (unsigned int)EventPnpRequestComplete,
          (unsigned int)&v90,
          HIDWORD(DeviceExtension[1].RemoveTrackingSpinlock),
          (char)Irp,
          Status);
      v42 = RemoveType[0];
      if ( RemoveType[0] == 2 )
      {
        v43 = DeviceExtension[2].PartitionLength;
        v92 = 0;
        v44 = (__int128 *)(v43.QuadPart + 4);
        if ( !v43.QuadPart )
          v44 = &v92;
        if ( (unsigned int)dword_14004D060 > 5 && (unsigned __int8)tlgKeywordOn(v40, 0x400000000000LL, v44) )
        {
          v32 = DeviceExtension->CurrentState == 23;
          v96 = &v83;
          v94 = v46;
          v83 = v32;
          v95 = 16;
          v97 = 1;
          tlgWriteTransfer_EtwWriteTransfer(v45, (int)&byte_140048809, v46, v47, 4u, (__int64)v93);
        }
      }
      v48 = Irp->Tail.Overlay.CurrentStackLocation;
      *(_OWORD *)&v48[-1].MajorFunction = *(_OWORD *)&v48->MajorFunction;
      *(_OWORD *)&v48[-1].Parameters.NotifyDirectoryEx.CompletionFilter = *(_OWORD *)&v48->Parameters.NotifyDirectoryEx.CompletionFilter;
      *(_OWORD *)(&v48[-1].Parameters.SetQuota + 6) = *(_OWORD *)(&v48->Parameters.SetQuota + 6);
      v48[-1].FileObject = v48->FileObject;
      v48[-1].Control = 0;
      Status = IofCallDriver(DeviceExtension->LowerDeviceObject, Irp);
      v9 = 0;
    }
    else
    {
      v42 = RemoveType[0];
      Status = 0;
    }
    DeviceExtension->PreviousState = DeviceExtension->CurrentState;
    DeviceExtension->CurrentState = v42;
    ClassRemoveDevice(DeviceObject, v42);
    goto LABEL_323;
  }
  if ( !v84 )
    goto LABEL_324;
LABEL_275:
  if ( (_BYTE)v13 && (BYTE2(WPP_MAIN_CB.Queue.Wcb.CurrentIrp) & 0x10) != 0 )
    McTemplateK0qpd_EtwWriteTransfer(
      v35,
      (unsigned int)EventPnpRequestComplete,
      (unsigned int)&v90,
      HIDWORD(DeviceExtension[1].RemoveTrackingSpinlock),
      (char)Irp,
      Status);
LABEL_96:
  v33 = Irp->Tail.Overlay.CurrentStackLocation;
  *(_OWORD *)&v33[-1].MajorFunction = *(_OWORD *)&v33->MajorFunction;
  *(_OWORD *)&v33[-1].Parameters.NotifyDirectoryEx.CompletionFilter = *(_OWORD *)&v33->Parameters.NotifyDirectoryEx.CompletionFilter;
  *(_OWORD *)(&v33[-1].Parameters.SetQuota + 6) = *(_OWORD *)(&v33->Parameters.SetQuota + 6);
  v33[-1].FileObject = v33->FileObject;
  v33[-1].Control = 0;
  ClassReleaseRemoveLock(DeviceObject, Irp);
  Status = IofCallDriver(DeviceExtension->LowerDeviceObject, Irp);
LABEL_97:
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_qq(
      WPP_GLOBAL_Control->AttachedDevice,
      42,
      WPP_9ee7907f5c473329e20561a6f3486187_Traceguids,
      DeviceObject,
      Irp);
  }
  return (unsigned int)Status;
}

```

## disassembly

```asm
0x14005fe50  mov     [rsp-8+arg_10], rbx
0x14005fe55  push    rbp
0x14005fe56  push    rsi
0x14005fe57  push    rdi
0x14005fe58  push    r12
0x14005fe5a  push    r13
0x14005fe5c  push    r14
0x14005fe5e  push    r15
0x14005fe60  lea     rbp, [rsp-27h]
0x14005fe65  sub     rsp, 0E0h
0x14005fe6c  mov     rax, cs:__security_cookie
0x14005fe73  xor     rax, rsp
0x14005fe76  mov     [rbp+57h+var_40], rax
0x14005fe7a  mov     r14, [rcx+40h]
0x14005fe7e  mov     rdi, rdx
0x14005fe81  mov     r13, [rdx+0B8h]
0x14005fe88  mov     r15, rcx
0x14005fe8b  mov     esi, [rdx+30h]
0x14005fe8e  xorps   xmm0, xmm0
0x14005fe91  mov     rcx, [rcx+8]; DriverObject
0x14005fe95  lea     rdx, ClassInitialize; ClientIdentificationAddress
0x14005fe9c  mov     bl, [r14+68h]
0x14005fea0  mov     [rbp+57h+var_C0], 2
0x14005fea7  movups  [rbp+57h+var_B0], xmm0
0x14005feab  call    cs:__imp_IoGetDriverObjectExtension
0x14005feb2  nop     dword ptr [rax+rax+00h]
0x14005feb7  mov     [rbp+57h+var_B8], rax
0x14005febb  lea     r12, WPP_GLOBAL_Control
0x14005fec2  test    rax, rax
0x14005fec5  jz      loc_140061388
0x14005fecb  xor     dl, dl
0x14005fecd  mov     [rbp+57h+var_CD], 0
0x14005fed1  mov     [rbp+57h+var_D0], dl
0x14005fed4  lea     r8, File; "minkernel\\storage\\classpnp\\class.c"
0x14005fedb  mov     [rbp+57h+var_CE], dl
0x14005fede  mov     r12d, 1
0x14005fee4  and     bl, r12b
0x14005fee7  mov     rdx, rdi; Tag
0x14005feea  mov     r9d, 561h; Line
0x14005fef0  mov     [rbp+57h+var_CF], bl
0x14005fef3  mov     rcx, r15; DeviceObject
0x14005fef6  call    ClassAcquireRemoveLockEx
0x14005fefb  mov     rdx, cs:WPP_GLOBAL_Control
0x14005ff02  lea     rax, WPP_GLOBAL_Control
0x14005ff09  lea     r8, aPdo; "pdo"
0x14005ff10  cmp     rdx, rax
0x14005ff13  jz      loc_14005FFA1
0x14005ff19  mov     eax, [rdx+2Ch]
0x14005ff1c  test    al, 2
0x14005ff1e  jz      short loc_14005FF57
0x14005ff20  cmp     byte ptr [rdx+29h], 4
0x14005ff24  jb      short loc_14005FF57
0x14005ff26  movzx   eax, byte ptr [r13+1]
0x14005ff2b  lea     rcx, aFdo; "fdo"
0x14005ff32  mov     [rsp+110h+var_D8], r15
0x14005ff37  test    bl, bl
0x14005ff39  mov     r9, r15
0x14005ff3c  cmovz   rcx, r8
0x14005ff40  mov     [rsp+110h+var_E0], rcx
0x14005ff45  mov     rcx, [rdx+18h]
0x14005ff49  mov     dword ptr [rsp+110h+var_E8], eax
0x14005ff4d  mov     [rsp+110h+Timeout], rdi
0x14005ff52  call    WPP_SF_qqDsq
0x14005ff57  mov     r8, cs:WPP_GLOBAL_Control
0x14005ff5e  lea     rax, WPP_GLOBAL_Control
0x14005ff65  cmp     r8, rax
0x14005ff68  jz      short loc_14005FFA1
0x14005ff6a  mov     eax, [r8+2Ch]
0x14005ff6e  test    al, 2
0x14005ff70  jz      short loc_14005FFA1
0x14005ff72  cmp     byte ptr [r8+29h], 4
0x14005ff77  jb      short loc_14005FFA1
0x14005ff79  movzx   ecx, byte ptr [r14+69h]
0x14005ff7e  mov     edx, 14h
0x14005ff83  movzx   eax, byte ptr [r14+6Ah]
0x14005ff88  mov     r9, r15
0x14005ff8b  mov     dword ptr [rsp+110h+var_E0], eax
0x14005ff8f  mov     dword ptr [rsp+110h+var_E8], ecx
0x14005ff93  mov     rcx, [r8+18h]
0x14005ff97  mov     [rsp+110h+Timeout], rdi
0x14005ff9c  call    WPP_SF_qqDD
0x14005ffa1  lea     rdx, [rbp+57h+var_B0]
0x14005ffa5  mov     rcx, rdi
0x14005ffa8  call    cs:__imp_IoGetActivityIdIrp
0x14005ffaf  nop     dword ptr [rax+rax+00h]
0x14005ffb4  test    eax, eax
0x14005ffb6  js      short loc_14006001B
0x14005ffb8  mov     r8b, cs:ClassPnPETWEnabled
0x14005ffbf  mov     r9b, r12b
0x14005ffc2  mov     [rbp+57h+var_CE], r12b
0x14005ffc6  mov     [rbp+57h+var_D0], r8b
0x14005ffca  test    r8b, r8b
0x14005ffcd  jz      short loc_140060022
0x14005ffcf  movzx   ecx, byte ptr [r13+1]
0x14005ffd4  cmp     cl, 16h
0x14005ffd7  ja      short loc_14005FFE3
0x14005ffd9  mov     edx, 480080h
0x14005ffde  bt      edx, ecx
0x14005ffe1  jb      short loc_140060022
0x14005ffe3  test    byte ptr cs:WPP_MAIN_CB.Queue+3Ah, 10h
0x14005ffea  jz      short loc_140060022
0x14005ffec  mov     r9d, [r14+24Ch]
0x14005fff3  lea     r8, [rbp+57h+var_B0]
0x14005fff7  mov     [rsp+110h+var_D8], r15
0x14005fffc  mov     dword ptr [rsp+110h+var_E0], 0
0x140060004  mov     dword ptr [rsp+110h+var_E8], ecx
0x140060008  mov     [rsp+110h+Timeout], rdi
0x14006000d  call    McTemplateK0qpddp_EtwWriteTransfer
0x140060012  mov     r8b, [rbp+57h+var_D0]
0x140060016  mov     r9b, r12b
0x140060019  jmp     short loc_140060022
0x14006001b  mov     r8b, [rbp+57h+var_D0]
0x14006001f  mov     r9b, r8b
0x140060022  movzx   edx, byte ptr [r13+1]
0x140060027  lea     rbx, WPP_9ee7907f5c473329e20561a6f3486187_Traceguids
0x14006002e  mov     dword ptr [rbp+57h+RemoveType], edx
0x140060031  cmp     edx, 6
0x140060034  ja      loc_14006054F
0x14006003a  jz      loc_1400603B5
0x140060040  mov     ecx, edx
0x140060042  test    edx, edx
0x140060044  jz      loc_140060358
0x14006004a  sub     ecx, r12d
0x14006004d  jz      short loc_140060073
0x14006004f  sub     ecx, r12d
0x140060052  jz      loc_140060592
0x140060058  sub     ecx, r12d
0x14006005b  jz      loc_1400603B5
0x140060061  sub     ecx, r12d
0x140060064  jz      loc_14006012A
0x14006006a  cmp     ecx, r12d
0x14006006d  jnz     loc_140060583
0x140060073  xorps   xmm0, xmm0
0x140060076  lea     rax, [rbp+57h+DestinationString]
0x14006007a  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x14006007e  mov     qword ptr [rbp+57h+RemoveType], rax
0x140060082  mov     rcx, cs:WPP_GLOBAL_Control
0x140060089  lea     rax, WPP_GLOBAL_Control
0x140060090  lea     r8, aRemove; "REMOVE"
0x140060097  lea     r12, aStop; "STOP"
0x14006009e  cmp     rcx, rax
0x1400600a1  jz      short loc_1400600D5
0x1400600a3  mov     eax, [rcx+2Ch]
0x1400600a6  test    al, 2
0x1400600a8  jz      short loc_1400600D5
0x1400600aa  cmp     byte ptr [rcx+29h], 4
0x1400600ae  jb      short loc_1400600D5
0x1400600b0  mov     rcx, [rcx+18h]
0x1400600b4  cmp     dl, 5
0x1400600b7  mov     rax, r12
0x1400600ba  mov     edx, 15h
0x1400600bf  cmovnz  rax, r8
0x1400600c3  mov     r9, r15
0x1400600c6  mov     [rsp+110h+var_E8], rax
0x1400600cb  mov     [rsp+110h+Timeout], rdi
0x1400600d0  call    WPP_SF_qqs
0x1400600d5  cmp     dword ptr [r14+0A8h], 0
0x1400600dd  jz      loc_14006021F
0x1400600e3  mov     rcx, cs:WPP_GLOBAL_Control
0x1400600ea  lea     r12, WPP_GLOBAL_Control
0x1400600f1  cmp     rcx, r12
0x1400600f4  jz      short loc_140060120
0x1400600f6  mov     eax, [rcx+2Ch]
0x1400600f9  test    al, 2
0x1400600fb  jz      short loc_140060120
0x1400600fd  cmp     byte ptr [rcx+29h], 3
0x140060101  jb      short loc_140060120
0x140060103  mov     rcx, [rcx+18h]
0x140060107  lea     r8, WPP_9ee7907f5c473329e20561a6f3486187_Traceguids
0x14006010e  mov     edx, 16h
0x140060113  mov     [rsp+110h+Timeout], rdi
0x140060118  mov     r9, r15
0x14006011b  call    WPP_SF_qq
0x140060120  mov     esi, 80000011h
0x140060125  jmp     loc_14006138D
0x14006012a  xorps   xmm0, xmm0
0x14006012d  lea     rax, [rbp+57h+DestinationString]
0x140060131  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x140060135  mov     qword ptr [rbp+57h+RemoveType], rax
0x140060139  mov     rcx, cs:WPP_GLOBAL_Control
0x140060140  lea     rax, WPP_GLOBAL_Control
0x140060147  mov     bl, [rbp+57h+var_CF]
0x14006014a  cmp     rcx, rax
0x14006014d  jz      short loc_14006018B
0x14006014f  mov     eax, [rcx+2Ch]
0x140060152  test    al, 2
0x140060154  jz      short loc_14006018B
0x140060156  cmp     byte ptr [rcx+29h], 4
0x14006015a  jb      short loc_14006018B
0x14006015c  mov     rcx, [rcx+18h]
0x140060160  lea     rdx, aPdo; "pdo"
0x140060167  test    bl, bl
0x140060169  lea     rax, aFdo; "fdo"
0x140060170  mov     r9, r15
0x140060173  cmovz   rax, rdx
0x140060177  mov     edx, 19h
0x14006017c  mov     [rsp+110h+var_E8], rax
0x140060181  mov     [rsp+110h+Timeout], rdi
0x140060186  call    WPP_SF_qqs
0x14006018b  mov     rcx, r14
0x14006018e  call    ClasspDisableTimer
0x140060193  mov     r12b, [rbp+57h+var_CE]
0x140060197  test    r12b, r12b
0x14006019a  jz      short loc_1400601B3
0x14006019c  lea     r8, [rbp+57h+RemoveType]
0x1400601a0  mov     rcx, rdi
0x1400601a3  lea     rdx, [rbp+57h+var_B0]
0x1400601a7  call    cs:__imp_IoPropagateActivityIdToThread
0x1400601ae  nop     dword ptr [rax+rax+00h]
0x1400601b3  mov     rcx, [rbp+57h+var_B8]
0x1400601b7  mov     al, bl
0x1400601b9  neg     al
0x1400601bb  mov     dl, 4
0x1400601bd  sbb     rax, rax
0x1400601c0  and     rax, 0FFFFFFFFFFFFFF58h
0x1400601c6  mov     rax, [rax+rcx+110h]
0x1400601ce  mov     rcx, r15
0x1400601d1  call    _guard_dispatch_icall
0x1400601d6  mov     esi, eax
0x1400601d8  test    bl, bl
0x1400601da  jz      short loc_1400601E9
0x1400601dc  mov     rdx, rdi; Irp
0x1400601df  mov     rcx, r14; CommonExtension
0x1400601e2  call    ClassForwardIrpSynchronous
0x1400601e7  mov     esi, eax
0x1400601e9  test    esi, esi
0x1400601eb  js      short loc_1400601FA
0x1400601ed  mov     al, [r13+1]
0x1400601f1  mov     [r14+6Ah], al
0x1400601f5  mov     byte ptr [r14+69h], 0FFh
0x1400601fa  test    r12b, r12b
0x1400601fd  jz      loc_140061376
0x140060203  mov     rcx, qword ptr [rbp+57h+RemoveType]
0x140060207  call    cs:__imp_IoClearActivityIdThread
0x14006020e  nop     dword ptr [rax+rax+00h]
0x140060213  lea     r12, WPP_GLOBAL_Control
0x14006021a  jmp     loc_14006138D
0x14006021f  cmp     [rbp+57h+var_CE], 0
0x140060223  jz      short loc_14006023C
0x140060225  lea     r8, [rbp+57h+RemoveType]
0x140060229  mov     rcx, rdi
0x14006022c  lea     rdx, [rbp+57h+var_B0]
0x140060230  call    cs:__imp_IoPropagateActivityIdToThread
0x140060237  nop     dword ptr [rax+rax+00h]
0x14006023c  mov     dl, [r13+1]
0x140060240  mov     bl, [rbp+57h+var_CF]
0x140060243  mov     rcx, [rbp+57h+var_B8]
0x140060247  mov     al, bl
0x140060249  cmp     dl, 5
0x14006024c  jnz     short loc_140060263
0x14006024e  neg     al
0x140060250  sbb     rax, rax
0x140060253  and     rax, 0FFFFFFFFFFFFFF58h
0x140060259  mov     rax, [rax+rcx+110h]
0x140060261  jmp     short loc_140060276
0x140060263  neg     al
0x140060265  sbb     rax, rax
0x140060268  and     rax, 0FFFFFFFFFFFFFF58h
0x14006026e  mov     rax, [rax+rcx+118h]
0x140060276  mov     rcx, r15
0x140060279  call    _guard_dispatch_icall
0x14006027e  mov     esi, eax
0x140060280  test    eax, eax
0x140060282  js      short loc_1400602F0
0x140060284  mov     al, [r14+6Ah]
0x140060288  mov     [r14+69h], al
0x14006028c  mov     al, [r13+1]
0x140060290  mov     [r14+6Ah], al
0x140060294  test    bl, bl
0x140060296  jz      short loc_1400602F0
0x140060298  mov     rcx, cs:WPP_GLOBAL_Control
0x14006029f  lea     rax, WPP_GLOBAL_Control
0x1400602a6  cmp     rcx, rax
0x1400602a9  jz      short loc_1400602E3
0x1400602ab  mov     eax, [rcx+2Ch]
0x1400602ae  test    al, 2
0x1400602b0  jz      short loc_1400602E3
0x1400602b2  cmp     byte ptr [rcx+29h], 4
0x1400602b6  jb      short loc_1400602E3
0x1400602b8  cmp     byte ptr [r13+1], 5
0x1400602bd  lea     rax, aRemove; "REMOVE"
0x1400602c4  mov     rcx, [rcx+18h]
0x1400602c8  mov     edx, 17h
0x1400602cd  cmovnz  r12, rax
0x1400602d1  mov     r9, r15
0x1400602d4  mov     [rsp+110h+var_E8], r12
0x1400602d9  mov     [rsp+110h+Timeout], rdi
0x1400602de  call    WPP_SF_qqs
0x1400602e3  mov     rdx, rdi; Irp
0x1400602e6  mov     rcx, r14; CommonExtension
0x1400602e9  call    ClassForwardIrpSynchronous
0x1400602ee  mov     esi, eax
0x1400602f0  cmp     [rbp+57h+var_CE], 0
0x1400602f4  jz      short loc_140060306
0x1400602f6  mov     rcx, qword ptr [rbp+57h+RemoveType]
0x1400602fa  call    cs:__imp_IoClearActivityIdThread
0x140060301  nop     dword ptr [rax+rax+00h]
0x140060306  mov     rcx, cs:WPP_GLOBAL_Control
0x14006030d  lea     r12, WPP_GLOBAL_Control
0x140060314  cmp     rcx, r12
  ... truncated ...
```
