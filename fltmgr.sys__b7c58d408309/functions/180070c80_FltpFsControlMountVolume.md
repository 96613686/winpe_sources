# FltpFsControlMountVolume

- ea: `0x180070c80`
- end: `0x180071363`
- name: `FltpFsControlMountVolume`
- size: `1763`
- prototype: `__int64 __fastcall(unsigned __int64, IRP *)`
- caller_count: `1`
- callee_count: `22`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18006ee20`

## callees

- `0x180003380`
- `0x1800044e0`
- `0x180009f20`
- `0x18000a340`
- `0x180016f40`
- `0x18001c160`
- `0x18001cd80`
- `0x18001f6a0`
- `0x180023870`
- `0x1800552c0`
- `0x180067030`
- `0x180067a50`
- `0x180067b00`
- `0x180067be0`
- `0x1800682b0`
- `0x180068420`
- `0x180068650`
- `0x1800688d0`
- `0x18006f2d0`
- `0x18006f640`
- `0x180070c80`
- `0x1800767a0`

## import_xrefs

- `ntoskrnl!ExReleaseFastMutex` at `0x1800710b2`
- `ntoskrnl!ExReleaseFastMutex` at `0x1800710b2`
- `ntoskrnl!ExAcquireFastMutex` at `0x180071033`
- `ntoskrnl!ExAcquireFastMutex` at `0x180071033`
- `ntoskrnl!ExFreePoolWithTag` at `0x180071324`
- `ntoskrnl!ExFreePoolWithTag` at `0x180071324`
- `ntoskrnl!KeInitializeEvent` at `0x180070ec6`
- `ntoskrnl!KeInitializeEvent` at `0x180070ec6`
- `ntoskrnl!ObfDereferenceObject` at `0x1800710c6`
- `ntoskrnl!ObfDereferenceObject` at `0x1800710c6`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x180070ce4`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x180070ce4`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x18007133f`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x18007133f`
- `ntoskrnl!IoGetStackLimits` at `0x180071197`
- `ntoskrnl!IoGetStackLimits` at `0x180071204`
- `ntoskrnl!IoGetStackLimits` at `0x180071197`
- `ntoskrnl!IoGetStackLimits` at `0x180071204`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x18007130c`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x18007130c`

## pseudocode

```c
__int64 __fastcall FltpFsControlMountVolume(unsigned __int64 a1, IRP *a2)
{
  __int64 v2; // r12
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rax
  struct _DEVICE_OBJECT *v4; // r14
  ULONG_PTR v5; // r13
  PIO_SECURITY_CONTEXT SecurityContext; // rcx
  void *v7; // rdi
  char *v8; // rax
  __int64 v9; // r15
  int ObjectName; // ebx
  __int64 v11; // rdi
  PIRP v12; // rbx
  ULONG_PTR v13; // rdx
  unsigned __int64 v14; // rax
  struct _IO_STACK_LOCATION *v15; // rax
  struct _IO_STACK_LOCATION *v16; // rax
  NTSTATUS v17; // eax
  PIRP v18; // r12
  NTSTATUS Status; // r12d
  int v20; // edx
  ULONG Flags; // r14d
  struct _IRP *MasterIrp; // rcx
  int v23; // r8d
  unsigned int v24; // r14d
  __int64 FsDeviceObjectAfterMount; // rax
  __int64 v26; // rdx
  __int64 v27; // r8
  int UniqueIdentifierForObject; // eax
  __int64 v29; // r8
  int v30; // eax
  __int64 v32; // [rsp+28h] [rbp-51h]
  __int64 v33; // [rsp+50h] [rbp-29h]
  struct _DEVICE_OBJECT *Object; // [rsp+58h] [rbp-21h]
  __int64 v35; // [rsp+60h] [rbp-19h]
  unsigned __int64 HighLimit; // [rsp+68h] [rbp-11h] BYREF
  unsigned __int64 v37; // [rsp+70h] [rbp-9h] BYREF
  struct _KEVENT Event; // [rsp+78h] [rbp-1h] BYREF
  unsigned __int64 LowLimit; // [rsp+E0h] [rbp+67h] BYREF
  PIRP Irp; // [rsp+E8h] [rbp+6Fh]
  ULONG_PTR BugCheckParameter3; // [rsp+F0h] [rbp+77h] BYREF
  PDEVICE_OBJECT SourceDevice; // [rsp+F8h] [rbp+7Fh] BYREF

  Irp = a2;
  LowLimit = a1;
  v2 = *(_QWORD *)(a1 + 64);
  CurrentStackLocation = a2->Tail.Overlay.CurrentStackLocation;
  v4 = 0;
  memset(&Event, 0, sizeof(Event));
  v5 = 0;
  v33 = *(_QWORD *)(v2 + 16);
  SecurityContext = CurrentStackLocation->Parameters.Create.SecurityContext;
  SourceDevice = 0;
  BugCheckParameter3 = 0;
  v7 = *(void **)&SecurityContext->DesiredAccess;
  v35 = (__int64)v7;
  v8 = (char *)ExAllocateFromNPagedLookasideList(&stru_18003EDC0);
  v9 = (__int64)v8;
  if ( v8 )
  {
    *((_DWORD *)v8 + 4) = 0;
    *(_QWORD *)(v8 + 20) = 254;
    *(_OWORD *)v8 = 0;
    *((_WORD *)v8 + 1) = 254;
    *((_QWORD *)v8 + 1) = v8 + 28;
    ObjectName = FltpGetObjectName(v7, (__int64)v8);
    if ( (int)FltpDbgStatus(ObjectName) < 0 )
    {
      FltpLogEventWithObjectID(&FLTMGR_VOLUME_ATTACH_FAILED, ObjectName, 0, (unsigned __int16 *)&UnknownName, 0);
      goto LABEL_61;
    }
    ObjectName = FltpCreateVolumeDeviceObject(
                   LowLimit,
                   (__int64)v7,
                   v9,
                   v2 + 48,
                   v2 + 64,
                   *(_QWORD *)(v2 + 16),
                   &SourceDevice);
    if ( (int)FltpDbgStatus(ObjectName) < 0 )
    {
      FltpLogEventWithObjectID(&FLTMGR_VOLUME_ATTACH_FAILED, ObjectName, 0, (unsigned __int16 *)v9, 0);
      v4 = SourceDevice;
      goto LABEL_61;
    }
    v4 = SourceDevice;
    v11 = *((_QWORD *)SourceDevice->DeviceExtension + 10);
    FltpLinkVolume(v11, 1);
    ObjectName = FltpAllocateIrpCtrl((int)v4, 2, 0, (int)&BugCheckParameter3);
    if ( (int)FltpDbgStatus(ObjectName) < 0 )
    {
      FltpLogEventWithObjectID(&FLTMGR_VOLUME_ATTACH_FAILED, ObjectName, 0, (unsigned __int16 *)v9, 0);
      v5 = BugCheckParameter3;
      goto LABEL_61;
    }
    v5 = BugCheckParameter3;
    v12 = Irp;
    v13 = BugCheckParameter3;
    *(_BYTE *)(*(_QWORD *)(BugCheckParameter3 + 248) + 4LL) = -19;
    v14 = LowLimit;
    *(_BYTE *)(v13 + 12) = -19;
    *(_DWORD *)(*(_QWORD *)(v13 + 248) + 24LL) = *(_DWORD *)(v14 + 72);
    *(_DWORD *)(v13 + 256) = v12->IoStatus.Status;
    *(_QWORD *)(v13 + 264) = v12->IoStatus.Information;
    LODWORD(BugCheckParameter3) = FltpPerformPreMountCallbacks(v11, v13);
    if ( (int)FltpDbgStatus(BugCheckParameter3) < 0 || (_DWORD)BugCheckParameter3 == 1835009 )
    {
      ObjectName = *(_DWORD *)(v5 + 256);
      if ( (int)FltpDbgStatus(ObjectName) < 0 && ObjectName != -1073741489 )
        FltpLogEventWithObjectID(&FLTMGR_VOLUME_ATTACH_FAILED, ObjectName, 0, (unsigned __int16 *)v9, 0);
      goto LABEL_61;
    }
    KeInitializeEvent(&Event, NotificationEvent, 0);
    v15 = v12->Tail.Overlay.CurrentStackLocation;
    *(_OWORD *)&v15[-1].MajorFunction = *(_OWORD *)&v15->MajorFunction;
    *(_OWORD *)&v15[-1].Parameters.NotifyDirectoryEx.CompletionFilter = *(_OWORD *)&v15->Parameters.NotifyDirectoryEx.CompletionFilter;
    *(_OWORD *)(&v15[-1].Parameters.SetQuota + 6) = *(_OWORD *)(&v15->Parameters.SetQuota + 6);
    v15[-1].FileObject = v15->FileObject;
    v15[-1].Control = 0;
    v16 = v12->Tail.Overlay.CurrentStackLocation;
    v16[-1].CompletionRoutine = (PIO_COMPLETION_ROUTINE)FltpFsControlCompletion;
    v16[-1].Context = &Event;
    v16[-1].Control = -32;
    v17 = FltpCallDriver(*(PDEVICE_OBJECT *)(v2 + 8), v12);
    v18 = Irp;
    ObjectName = v17;
    if ( v17 == 259 )
      FltpCancellableWaitForIo(&Event, Irp);
    Status = v18->IoStatus.Status;
    if ( Status < 0 )
    {
      ObjectName = Status;
    }
    else
    {
      Object = (struct _DEVICE_OBJECT *)FltpGetFsDeviceObjectAfterMount(v35);
      if ( Object )
      {
        v20 = 0;
        Flags = 0;
        LODWORD(BugCheckParameter3) = 0;
        MasterIrp = Irp->AssociatedIrp.MasterIrp;
        if ( !MasterIrp || Irp->IoStatus.Information < 0x2C )
          goto LABEL_31;
        v23 = *(_DWORD *)(&MasterIrp->Size + 1);
        if ( (v23 & 0x2000) != 0 )
        {
          if ( ((__int64)MasterIrp->MdlAddress & 0x2000) != 0 )
            v20 = 4096;
          LODWORD(BugCheckParameter3) = v20;
        }
        if ( (v23 & 0x4000) != 0 && ((__int64)MasterIrp->MdlAddress & 0x4000) != 0 )
        {
          v20 |= 0x2000u;
          LODWORD(BugCheckParameter3) = v20;
        }
        *(_OWORD *)(v11 + 2136) = *(_OWORD *)((char *)&MasterIrp->MdlAddress + 4);
        *(_OWORD *)(v11 + 2152) = *(_OWORD *)((char *)&MasterIrp->AssociatedIrp.SystemBuffer + 4);
        if ( v20 != 12288
          || (FltpInitVolumeAttachPolicy(v11), *(_QWORD *)(v11 + 2184))
          || *(_QWORD *)(v11 + 2208)
          || *(_QWORD *)(v11 + 2232)
          || *(_DWORD *)(v11 + 2240) )
        {
LABEL_31:
          if ( ObjectName >= 0 )
          {
            ExAcquireFastMutex((PFAST_MUTEX)(v33 + 624));
            if ( FltpIsAttachedToDevice(v33, Object) )
            {
              ObjectName = -1071906790;
            }
            else
            {
              ObjectName = FltpAttachDeviceObject(Object, SourceDevice);
              if ( (int)FltpDbgStatus(ObjectName) < 0 && ObjectName != -1071906805 )
                FltpLogEventWithObjectID(&FLTMGR_VOLUME_ATTACH_FAILED, ObjectName, 0, (unsigned __int16 *)v9, 0);
            }
            ExReleaseFastMutex((PFAST_MUTEX)(v33 + 624));
            Flags = Object->Flags;
          }
        }
        else
        {
          ObjectName = -1073740577;
          FltpTelemetryVolumeMountFailure(v11);
        }
        ObfDereferenceObject(Object);
        if ( ObjectName >= 0 )
        {
          v24 = BugCheckParameter3 | ((Flags & 0x10000000 | 0x40000) >> 17);
          if ( (*(_DWORD *)(v11 + 56) & v24) != v24 )
            _InterlockedOr((volatile signed __int32 *)(v11 + 56), v24);
LABEL_45:
          if ( (int)FltpDbgStatus(ObjectName) < 0 )
          {
LABEL_57:
            FltpPerformPostMountCallbacks(v11, v5);
            v4 = SourceDevice;
            goto LABEL_62;
          }
          if ( (unsigned int)dword_18003DAA8 > 5 )
          {
            HighLimit = 0;
            LowLimit = 0;
            IoGetStackLimits(&LowLimit, &HighLimit);
            if ( (unsigned __int64)&HighLimit - LowLimit >= 0x200 )
            {
              UniqueIdentifierForObject = FltpGetUniqueIdentifierForObject((char *)v11);
              if ( (int)FltpDbgStatus(UniqueIdentifierForObject) >= 0 )
                goto LABEL_51;
            }
            else
            {
              _InterlockedIncrement(&dword_18003FFB0);
            }
          }
          _InterlockedIncrement(&dword_18003FFB4);
LABEL_51:
          if ( (unsigned int)dword_18003DAA8 > 5 )
          {
            v37 = 0;
            LowLimit = 0;
            IoGetStackLimits(&LowLimit, &v37);
            if ( (unsigned __int64)&v37 - LowLimit < 0x200 )
            {
              _InterlockedIncrement(&dword_18003FFB0);
              FltpPerformPostMountCallbacks(v11, v5);
              v4 = SourceDevice;
              goto LABEL_62;
            }
            if ( *(_DWORD *)(v11 + 60) != 1 )
            {
              FltpTelemetryVolumeAttach(v11);
              FltpPerformPostMountCallbacks(v11, v5);
              v4 = SourceDevice;
              goto LABEL_62;
            }
            _InterlockedIncrement(&dword_18003FFB8);
          }
          goto LABEL_57;
        }
        v4 = SourceDevice;
      }
      else
      {
        ObjectName = -1073741202;
      }
    }
    *(_DWORD *)(v5 + 256) = ObjectName;
    *(_QWORD *)(v5 + 264) = 0;
    if ( (Microsoft_Windows_FltMgrTrace_20460e0498193c4b075e7d2a13c945f3EnableBits & 8) != 0 )
    {
      FsDeviceObjectAfterMount = FltpGetFsDeviceObjectAfterMount(v35);
      LODWORD(v32) = *(unsigned __int16 *)(v11 + 112) >> 1;
      McTemplateU0sppwdpp_EtwWriteTransfer(
        (unsigned int)v32,
        v26,
        v27,
        v4,
        v11,
        v32,
        *(_QWORD *)(v11 + 120),
        ObjectName,
        FsDeviceObjectAfterMount,
        LowLimit);
    }
    goto LABEL_45;
  }
  ObjectName = -1073741670;
  FltpLogEventWithObjectID(&FLTMGR_VOLUME_ATTACH_FAILED, -1073741670, 0, (unsigned __int16 *)&UnknownName, 0);
LABEL_61:
  Status = ObjectName;
LABEL_62:
  FltpCompleteRequest(Irp, Status);
  if ( v5 )
    FltpFreeIrpCtrl(v5, 0);
  if ( ObjectName < 0 && v4 )
    FltpCleanupDeviceObject(v4, 8, v29);
  if ( v9 )
  {
    v30 = *(_DWORD *)(v9 + 16);
    if ( (v30 & 1) != 0 )
    {
      if ( (v30 & 2) != 0 )
      {
        ExFreeToPagedLookasideList(&stru_18003F440, *(PVOID *)(v9 + 8));
        *(_DWORD *)(v9 + 16) &= ~2u;
      }
      else
      {
        ExFreePoolWithTag(*(PVOID *)(v9 + 8), 0x346E4D46u);
      }
      *(_DWORD *)(v9 + 16) &= ~1u;
    }
    ExFreeToNPagedLookasideList(&stru_18003EDC0, (PVOID)v9);
  }
  return (unsigned int)Status;
}

```

## disassembly

```asm
0x180070c80  mov     [rsp-8+Irp], rdx
0x180070c85  mov     [rsp-8+LowLimit], rcx
0x180070c8a  push    rbp
0x180070c8b  push    rbx
0x180070c8c  push    rsi
0x180070c8d  push    rdi
0x180070c8e  push    r12
0x180070c90  push    r13
0x180070c92  push    r14
0x180070c94  push    r15
0x180070c96  lea     rbp, [rsp-1Fh]
0x180070c9b  sub     rsp, 98h
0x180070ca2  mov     r12, [rcx+40h]
0x180070ca6  xorps   xmm0, xmm0
0x180070ca9  mov     rax, [rdx+0B8h]
0x180070cb0  xor     ecx, ecx
0x180070cb2  mov     [rbp+57h+Event.Header.WaitListHead.Blink], rcx
0x180070cb6  xor     r14d, r14d
0x180070cb9  movups  xmmword ptr [rbp+57h+Event.Header], xmm0
0x180070cbd  mov     rcx, [r12+10h]
0x180070cc2  xor     r13d, r13d
0x180070cc5  mov     [rbp+57h+var_80], rcx
0x180070cc9  mov     rcx, [rax+8]
0x180070ccd  mov     [rbp+57h+SourceDevice], r14
0x180070cd1  mov     [rbp+57h+BugCheckParameter3], r13
0x180070cd5  mov     rdi, [rcx+10h]
0x180070cd9  lea     rcx, stru_18003EDC0; Lookaside
0x180070ce0  mov     [rbp+57h+var_70], rdi
0x180070ce4  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x180070ceb  nop     dword ptr [rax+rax+00h]
0x180070cf0  mov     r15, rax
0x180070cf3  test    rax, rax
0x180070cf6  jnz     short loc_180070D0E
0x180070cf8  mov     ebx, 0C000009Ah
0x180070cfd  mov     [rsp+0D0h+var_B0], r13
0x180070d02  lea     r9, UnknownName
0x180070d09  jmp     loc_1800712A8
0x180070d0e  mov     [rax+10h], r13d
0x180070d12  xorps   xmm0, xmm0
0x180070d15  mov     qword ptr [rax+14h], 0FEh
0x180070d1d  mov     rdx, r15
0x180070d20  movups  xmmword ptr [r15], xmm0
0x180070d24  mov     eax, 0FEh
0x180070d29  mov     rcx, rdi; Object
0x180070d2c  mov     [r15+2], ax
0x180070d31  lea     rax, [r15+1Ch]
0x180070d35  mov     [r15+8], rax
0x180070d39  call    FltpGetObjectName
0x180070d3e  mov     r8d, 1C1Fh
0x180070d44  lea     rdx, aMinkernelFsFil_28; "minkernel\\fs\\filtermgr\\filter\\fltmg"...
0x180070d4b  xor     r9d, r9d
0x180070d4e  mov     ecx, eax
0x180070d50  mov     ebx, eax
0x180070d52  call    FltpDbgStatus
0x180070d57  test    eax, eax
0x180070d59  jns     short loc_180070D6C
0x180070d5b  mov     [rsp+0D0h+var_B0], r13
0x180070d60  lea     r9, UnknownName
0x180070d67  jmp     loc_1800712A8
0x180070d6c  lea     rax, [rbp+57h+SourceDevice]
0x180070d70  mov     r8, r15
0x180070d73  mov     [rsp+0D0h+var_A0], rax
0x180070d78  lea     rcx, [r12+40h]
0x180070d7d  mov     rax, [r12+10h]
0x180070d82  lea     r9, [r12+30h]
0x180070d87  mov     [rsp+0D0h+var_A8], rax
0x180070d8c  mov     rdx, rdi
0x180070d8f  mov     [rsp+0D0h+var_B0], rcx
0x180070d94  mov     rcx, [rbp+57h+LowLimit]
0x180070d98  call    FltpCreateVolumeDeviceObject
0x180070d9d  mov     r8d, 1C37h
0x180070da3  lea     rdx, aMinkernelFsFil_28; "minkernel\\fs\\filtermgr\\filter\\fltmg"...
0x180070daa  xor     r9d, r9d
0x180070dad  mov     ecx, eax
0x180070daf  mov     ebx, eax
0x180070db1  call    FltpDbgStatus
0x180070db6  test    eax, eax
0x180070db8  jns     short loc_180070DDC
0x180070dba  mov     r9, r15
0x180070dbd  mov     [rsp+0D0h+var_B0], r13; __int64
0x180070dc2  xor     r8d, r8d
0x180070dc5  lea     rcx, FLTMGR_VOLUME_ATTACH_FAILED; EventDescriptor
0x180070dcc  mov     edx, ebx
0x180070dce  call    FltpLogEventWithObjectID
0x180070dd3  mov     r14, [rbp+57h+SourceDevice]
0x180070dd7  jmp     loc_1800712B9
0x180070ddc  mov     r14, [rbp+57h+SourceDevice]
0x180070de0  mov     dl, 1
0x180070de2  mov     rax, [r14+40h]
0x180070de6  mov     rdi, [rax+50h]
0x180070dea  mov     rcx, rdi
0x180070ded  call    FltpLinkVolume
0x180070df2  lea     r9, [rbp+57h+BugCheckParameter3]
0x180070df6  xor     r8d, r8d
0x180070df9  mov     edx, 2
0x180070dfe  mov     rcx, r14
0x180070e01  call    FltpAllocateIrpCtrl
0x180070e06  mov     r8d, 1C61h
0x180070e0c  lea     rdx, aMinkernelFsFil_28; "minkernel\\fs\\filtermgr\\filter\\fltmg"...
0x180070e13  xor     r9d, r9d
0x180070e16  mov     ecx, eax
0x180070e18  mov     ebx, eax
0x180070e1a  call    FltpDbgStatus
0x180070e1f  test    eax, eax
0x180070e21  jns     short loc_180070E45
0x180070e23  mov     r9, r15
0x180070e26  mov     [rsp+0D0h+var_B0], r13; __int64
0x180070e2b  xor     r8d, r8d
0x180070e2e  lea     rcx, FLTMGR_VOLUME_ATTACH_FAILED; EventDescriptor
0x180070e35  mov     edx, ebx
0x180070e37  call    FltpLogEventWithObjectID
0x180070e3c  mov     r13, [rbp+57h+BugCheckParameter3]
0x180070e40  jmp     loc_1800712B9
0x180070e45  mov     r13, [rbp+57h+BugCheckParameter3]
0x180070e49  mov     rbx, [rbp+57h+Irp]
0x180070e4d  mov     rdx, r13
0x180070e50  mov     rax, [r13+0F8h]
0x180070e57  mov     byte ptr [rax+4], 0EDh
0x180070e5b  mov     rax, [rbp+57h+LowLimit]
0x180070e5f  mov     byte ptr [r13+0Ch], 0EDh
0x180070e64  mov     rcx, [r13+0F8h]
0x180070e6b  mov     eax, [rax+48h]
0x180070e6e  mov     [rcx+18h], eax
0x180070e71  mov     rcx, rdi
0x180070e74  mov     eax, [rbx+30h]
0x180070e77  mov     [r13+100h], eax
0x180070e7e  mov     rax, [rbx+38h]
0x180070e82  mov     [r13+108h], rax
0x180070e89  call    FltpPerformPreMountCallbacks
0x180070e8e  mov     r8d, 1C81h
0x180070e94  mov     dword ptr [rbp+57h+BugCheckParameter3], eax
0x180070e97  xor     r9d, r9d
0x180070e9a  lea     rdx, aMinkernelFsFil_28; "minkernel\\fs\\filtermgr\\filter\\fltmg"...
0x180070ea1  mov     ecx, eax
0x180070ea3  call    FltpDbgStatus
0x180070ea8  test    eax, eax
0x180070eaa  js      loc_180071272
0x180070eb0  cmp     dword ptr [rbp+57h+BugCheckParameter3], 1C0001h
0x180070eb7  jz      loc_180071272
0x180070ebd  xor     r8d, r8d; State
0x180070ec0  lea     rcx, [rbp+57h+Event]; Event
0x180070ec4  xor     edx, edx; Type
0x180070ec6  call    cs:__imp_KeInitializeEvent
0x180070ecd  nop     dword ptr [rax+rax+00h]
0x180070ed2  mov     rax, [rbx+0B8h]
0x180070ed9  lea     rcx, FltpFsControlCompletion
0x180070ee0  mov     rdx, rbx; Irp
0x180070ee3  movups  xmm0, xmmword ptr [rax]
0x180070ee6  movups  xmmword ptr [rax-48h], xmm0
0x180070eea  movups  xmm1, xmmword ptr [rax+10h]
0x180070eee  movups  xmmword ptr [rax-38h], xmm1
0x180070ef2  movups  xmm0, xmmword ptr [rax+20h]
0x180070ef6  movups  xmmword ptr [rax-28h], xmm0
0x180070efa  movsd   xmm1, qword ptr [rax+30h]
0x180070eff  movsd   qword ptr [rax-18h], xmm1
0x180070f04  mov     byte ptr [rax-45h], 0
0x180070f08  mov     rax, [rbx+0B8h]
0x180070f0f  mov     [rax-10h], rcx
0x180070f13  lea     rcx, [rbp+57h+Event]
0x180070f17  mov     [rax-8], rcx
0x180070f1b  mov     byte ptr [rax-45h], 0E0h
0x180070f1f  mov     rcx, [r12+8]; DeviceObject
0x180070f24  call    FltpCallDriver
0x180070f29  mov     r12, [rbp+57h+Irp]
0x180070f2d  mov     ebx, eax
0x180070f2f  cmp     eax, 103h
0x180070f34  jnz     short loc_180070F42
0x180070f36  mov     rdx, r12; Irp
0x180070f39  lea     rcx, [rbp+57h+Event]; Object
0x180070f3d  call    FltpCancellableWaitForIo
0x180070f42  mov     r12d, [r12+30h]
0x180070f47  test    r12d, r12d
0x180070f4a  js      loc_180071104
0x180070f50  mov     rcx, [rbp+57h+var_70]
0x180070f54  call    FltpGetFsDeviceObjectAfterMount
0x180070f59  mov     [rbp+57h+Object], rax
0x180070f5d  test    rax, rax
0x180070f60  jnz     short loc_180070F6C
0x180070f62  mov     ebx, 0C000026Eh
0x180070f67  jmp     loc_180071107
0x180070f6c  mov     rax, [rbp+57h+Irp]
0x180070f70  xor     edx, edx
0x180070f72  xor     r14d, r14d
0x180070f75  mov     dword ptr [rbp+57h+BugCheckParameter3], edx
0x180070f78  mov     rcx, [rax+18h]
0x180070f7c  test    rcx, rcx
0x180070f7f  jz      loc_180071020
0x180070f85  cmp     qword ptr [rax+38h], 2Ch ; ','
0x180070f8a  jb      loc_180071020
0x180070f90  mov     r8d, [rcx+4]
0x180070f94  bt      r8d, 0Dh
0x180070f99  jnb     short loc_180070FAD
0x180070f9b  test    dword ptr [rcx+8], 2000h
0x180070fa2  mov     eax, 1000h
0x180070fa7  cmovnz  edx, eax
0x180070faa  mov     dword ptr [rbp+57h+BugCheckParameter3], edx
0x180070fad  bt      r8d, 0Eh
0x180070fb2  jnb     short loc_180070FC4
0x180070fb4  test    dword ptr [rcx+8], 4000h
0x180070fbb  jz      short loc_180070FC4
0x180070fbd  bts     edx, 0Dh
0x180070fc1  mov     dword ptr [rbp+57h+BugCheckParameter3], edx
0x180070fc4  movups  xmm0, xmmword ptr [rcx+0Ch]
0x180070fc8  movups  xmmword ptr [rdi+858h], xmm0
0x180070fcf  movups  xmm0, xmmword ptr [rcx+1Ch]
0x180070fd3  movups  xmmword ptr [rdi+868h], xmm0
0x180070fda  cmp     edx, 3000h
0x180070fe0  jnz     short loc_180071020
0x180070fe2  mov     rcx, rdi
0x180070fe5  call    FltpInitVolumeAttachPolicy
0x180070fea  cmp     [rdi+888h], r14
0x180070ff1  jnz     short loc_180071020
0x180070ff3  cmp     [rdi+8A0h], r14
0x180070ffa  jnz     short loc_180071020
0x180070ffc  cmp     [rdi+8B8h], r14
0x180071003  jnz     short loc_180071020
0x180071005  cmp     [rdi+8C0h], r14d
0x18007100c  jnz     short loc_180071020
0x18007100e  mov     rcx, rdi
0x180071011  mov     ebx, 0C00004DFh
0x180071016  call    FltpTelemetryVolumeMountFailure
0x18007101b  jmp     loc_1800710C2
0x180071020  test    ebx, ebx
0x180071022  js      loc_1800710C2
0x180071028  mov     rbx, [rbp+57h+var_80]
0x18007102c  lea     rcx, [rbx+270h]; FastMutex
0x180071033  call    cs:__imp_ExAcquireFastMutex
0x18007103a  nop     dword ptr [rax+rax+00h]
0x18007103f  mov     r14, [rbp+57h+Object]
0x180071043  mov     rcx, rbx
0x180071046  mov     rdx, r14
0x180071049  call    FltpIsAttachedToDevice
0x18007104e  test    al, al
0x180071050  jnz     short loc_1800710A2
0x180071052  mov     rdx, [rbp+57h+SourceDevice]; SourceDevice
0x180071056  mov     rcx, r14; TargetDevice
0x180071059  call    FltpAttachDeviceObject
0x18007105e  mov     r8d, 1D2Ah
0x180071064  lea     rdx, aMinkernelFsFil_28; "minkernel\\fs\\filtermgr\\filter\\fltmg"...
0x18007106b  xor     r9d, r9d
0x18007106e  mov     ecx, eax
0x180071070  mov     ebx, eax
0x180071072  call    FltpDbgStatus
0x180071077  test    eax, eax
0x180071079  jns     short loc_1800710A7
0x18007107b  cmp     ebx, 0C01C000Bh
0x180071081  jz      short loc_1800710A7
0x180071083  mov     r9, r15
0x180071086  mov     [rsp+0D0h+var_B0], 0; __int64
0x18007108f  xor     r8d, r8d
0x180071092  lea     rcx, FLTMGR_VOLUME_ATTACH_FAILED; EventDescriptor
0x180071099  mov     edx, ebx
0x18007109b  call    FltpLogEventWithObjectID
0x1800710a0  jmp     short loc_1800710A7
0x1800710a2  mov     ebx, 0C01C001Ah
0x1800710a7  mov     rcx, [rbp+57h+var_80]
0x1800710ab  add     rcx, 270h; FastMutex
0x1800710b2  call    cs:__imp_ExReleaseFastMutex
0x1800710b9  nop     dword ptr [rax+rax+00h]
0x1800710be  mov     r14d, [r14+30h]
0x1800710c2  mov     rcx, [rbp+57h+Object]; Object
0x1800710c6  call    cs:__imp_ObfDereferenceObject
0x1800710cd  nop     dword ptr [rax+rax+00h]
0x1800710d2  test    ebx, ebx
0x1800710d4  js      short loc_1800710FE
0x1800710d6  mov     eax, [rdi+38h]
0x1800710d9  and     r14d, 10000000h
0x1800710e0  bts     r14d, 12h
0x1800710e5  shr     r14d, 11h
0x1800710e9  or      r14d, dword ptr [rbp+57h+BugCheckParameter3]
0x1800710ed  mov     ecx, r14d
0x1800710f0  and     ecx, eax
0x1800710f2  cmp     ecx, r14d
0x1800710f5  jz      short loc_18007115D
0x1800710f7  lock or [rdi+38h], r14d
0x1800710fc  jmp     short loc_18007115D
0x1800710fe  mov     r14, [rbp+57h+SourceDevice]
0x180071102  jmp     short loc_180071107
0x180071104  mov     ebx, r12d
0x180071107  mov     [r13+100h], ebx
0x18007110e  mov     qword ptr [r13+108h], 0
0x180071119  test    cs:Microsoft_Windows_FltMgrTrace_20460e0498193c4b075e7d2a13c945f3EnableBits, 8
0x180071120  jz      short loc_18007115D
0x180071122  mov     rcx, [rbp+57h+var_70]
0x180071126  call    FltpGetFsDeviceObjectAfterMount
0x18007112b  mov     r10, [rbp+57h+LowLimit]
0x18007112f  mov     r9, r14
0x180071132  movzx   ecx, word ptr [rdi+70h]
0x180071136  mov     [rsp+0D0h+var_88], r10
0x18007113b  mov     [rsp+0D0h+var_90], rax
0x180071140  mov     rax, [rdi+78h]
0x180071144  mov     [rsp+0D0h+var_98], ebx
0x180071148  mov     [rsp+0D0h+var_A0], rax
0x18007114d  shr     ecx, 1
0x18007114f  mov     dword ptr [rsp+0D0h+var_A8], ecx
0x180071153  mov     [rsp+0D0h+var_B0], rdi
0x180071158  call    McTemplateU0sppwdpp_EtwWriteTransfer
0x18007115d  mov     r8d, 1D84h
0x180071163  lea     rdx, aMinkernelFsFil_28; "minkernel\\fs\\filtermgr\\filter\\fltmg"...
0x18007116a  xor     r9d, r9d
  ... truncated ...
```
