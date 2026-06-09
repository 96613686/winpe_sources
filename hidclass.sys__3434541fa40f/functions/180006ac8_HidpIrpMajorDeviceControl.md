# HidpIrpMajorDeviceControl

- ea: `0x180006ac8`
- end: `0x18000840f`
- name: `HidpIrpMajorDeviceControl`
- size: `6471`
- prototype: ``
- caller_count: `1`
- callee_count: `32`
- tags: `reparse_path, broker_com_uri`

## callers

- `0x180004c00`

## callees

- `0x180003900`
- `0x1800039c0`
- `0x180003b70`
- `0x180003f40`
- `0x1800043a0`
- `0x180006ac8`
- `0x180008420`
- `0x1800085d8`
- `0x180008650`
- `0x180008760`
- `0x180008850`
- `0x180008a80`
- `0x180009ef8`
- `0x180009fdc`
- `0x18000c250`
- `0x18000df80`
- `0x18000ee70`
- `0x18001215c`
- `0x1800127d0`
- `0x1800129a4`
- `0x180013860`
- `0x180017024`
- `0x1800180b4`
- `0x18001b744`
- `0x18001eb28`
- `0x18001f044`
- `0x18001f2ac`
- `0x18001f5fc`
- `0x180023834`
- `0x180023924`
- `0x180024d30`
- `0x180025f64`

## import_xrefs

- `ntoskrnl!ProbeForWrite` at `0x180006d4f`
- `ntoskrnl!ProbeForWrite` at `0x180006d4f`
- `ntoskrnl!IoGetDeviceProperty` at `0x180007133`
- `ntoskrnl!IoGetDeviceProperty` at `0x180007133`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x180007162`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x180007162`
- `ntoskrnl!IofCompleteRequest` at `0x180006e59`
- `ntoskrnl!IofCompleteRequest` at `0x180006e59`
- `ntoskrnl!KeReleaseSpinLock` at `0x1800070b9`
- `ntoskrnl!KeReleaseSpinLock` at `0x180007175`
- `ntoskrnl!KeReleaseSpinLock` at `0x1800070b9`
- `ntoskrnl!KeReleaseSpinLock` at `0x180007175`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x18000708d`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x180007c01`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x18000708d`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x180007c01`
- `HIDPARSE!HidP_SysPowerCaps` at `0x18000790e`
- `HIDPARSE!HidP_SysPowerCaps` at `0x18000790e`

## string_xrefs

- `0x180006e05`: `Access Violation`
- `0x180007b13`: `Secure open not enabled`
- `0x180007dcd`: `Secure open not enabled`

## pseudocode

```c
__int64 __fastcall HidpIrpMajorDeviceControl(__int64 a1, IRP *a2)
{
  IRP *v2; // r13
  _UNKNOWN **v3; // r9
  char v4; // r12
  _IO_STACK_LOCATION *CurrentStackLocation; // rbx
  unsigned int LowPart; // esi
  __int64 v7; // r15
  __int64 v8; // r14
  NTSTATUS v9; // eax
  int v10; // edx
  int v11; // r8d
  NTSTATUS CollectionDescriptor; // esi
  _IRP *v13; // r8
  __int64 v14; // rcx
  const char *v15; // r8
  __int64 v16; // rdx
  bool v17; // al
  char v18; // r15
  volatile void *UserBuffer; // rcx
  unsigned int Length; // eax
  int v22; // edx
  __int64 v23; // rax
  __int64 v24; // rsi
  NTSTATUS SetReport; // eax
  KSPIN_LOCK *v26; // rbx
  KIRQL v27; // al
  __int64 v28; // rdx
  __int64 v29; // rcx
  __int64 v30; // r8
  __int64 v31; // r9
  __int64 v32; // rdx
  struct _DEVICE_OBJECT *v33; // rsi
  ULONG v34; // ebx
  _MDL *v35; // rcx
  PVOID MappedSystemVa; // rax
  __int64 v37; // rdx
  __int64 v38; // rcx
  __int64 v39; // r8
  __int64 v40; // r9
  __int64 v41; // r8
  _IO_STACK_LOCATION *v42; // rcx
  __int64 v43; // rcx
  _IO_STACK_LOCATION *v44; // rcx
  NTSTATUS DeviceString; // eax
  __int64 v46; // r8
  __int64 v47; // rax
  _IRP *v48; // rcx
  int v49; // eax
  _IRP *v50; // rax
  _BYTE *v51; // rdx
  unsigned int v52; // eax
  _IRP *v53; // rcx
  _DWORD *v54; // rdx
  int v55; // ecx
  _DWORD *v56; // rax
  __int64 v57; // rax
  __int64 HidclassCollection; // rax
  _MDL *MdlAddress; // rcx
  _BYTE *v60; // rbx
  __int64 v61; // rax
  int v62; // edx
  KSPIN_LOCK *v63; // r15
  KIRQL v64; // cl
  int v65; // edx
  __int64 v66; // rbx
  __int64 v67; // rax
  int v68; // edx
  __int64 v69; // r9
  _IRP *v70; // rcx
  int v71; // ecx
  _IO_STACK_LOCATION *v72; // rdx
  _FILE_OBJECT *FileObject; // rdx
  void *FsContext; // rsi
  const char *v75; // r8
  __int64 v76; // rdx
  __int64 v77; // rcx
  _IRP *v78; // rax
  char Type; // bl
  char v80; // r10
  _UNKNOWN **v81; // r9
  char v82; // r11
  __int64 v83; // rcx
  __int64 v84; // rdx
  const char *v85; // r8
  int v86; // r8d
  PDEVICE_OBJECT v87; // r10
  bool v88; // r11
  _IRP *v89; // rax
  __int64 v90; // r8
  _IRP *MasterIrp; // rax
  char v92; // al
  __int64 v93; // rdx
  unsigned int ResultLength; // [rsp+20h] [rbp-C8h]
  ULONG Priority; // [rsp+28h] [rbp-C0h]
  char *v96; // [rsp+30h] [rbp-B8h]
  int v97; // [rsp+38h] [rbp-B0h]
  __int64 v98; // [rsp+40h] [rbp-A8h]
  int v99; // [rsp+60h] [rbp-88h]
  char v100; // [rsp+80h] [rbp-68h] BYREF
  char v101; // [rsp+81h] [rbp-67h] BYREF
  char v102; // [rsp+82h] [rbp-66h]
  char v103; // [rsp+83h] [rbp-65h]
  unsigned int v104; // [rsp+84h] [rbp-64h]
  __int64 v105; // [rsp+88h] [rbp-60h]
  NTSTATUS v106; // [rsp+90h] [rbp-58h]
  unsigned int v107; // [rsp+94h] [rbp-54h]
  __int64 v108; // [rsp+98h] [rbp-50h]
  __int64 v109; // [rsp+A0h] [rbp-48h]
  __int64 OutputBuffer; // [rsp+F0h] [rbp+8h] BYREF
  __int64 v111; // [rsp+F8h] [rbp+10h]
  char v112; // [rsp+100h] [rbp+18h]
  char v113; // [rsp+108h] [rbp+20h] BYREF

  v111 = (__int64)a2;
  OutputBuffer = a1;
  v2 = a2;
  v3 = (_UNKNOWN **)a1;
  v4 = 1;
  v112 = 1;
  v100 = 0;
  v113 = 0;
  CurrentStackLocation = a2->Tail.Overlay.CurrentStackLocation;
  LowPart = CurrentStackLocation->Parameters.Read.ByteOffset.LowPart;
  v104 = LowPart;
  v107 = LowPart;
  v102 = *(_BYTE *)(a1 + 24);
  v103 = v102;
  v101 = 0;
  v7 = a1 + 32;
  if ( !v102 )
  {
    CollectionDescriptor = -1073741585;
    v8 = a1 + 32;
    v105 = 0;
    v15 = "Ioctl sent to FDO";
    v14 = a1 + 32;
LABEL_347:
    v16 = v104;
    goto LABEL_29;
  }
  v105 = a1 + 32;
  v108 = a1 + 32;
  v8 = *(_QWORD *)(a1 + 96) + 32LL;
  v109 = v8;
  if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    || (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) == 0
    || (LOBYTE(a2) = 1, BYTE1(WPP_GLOBAL_Control->Timer) < 4u) )
  {
    LOBYTE(a2) = 0;
  }
  if ( (_BYTE)a2 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    WPP_RECORDER_AND_TRACE_SF_qdqqcL(
      WPP_GLOBAL_Control->AttachedDevice,
      (_DWORD)a2,
      WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED,
      *(_QWORD *)(v8 + 672));
    v3 = (_UNKNOWN **)OutputBuffer;
  }
  if ( !*(_DWORD *)(v8 + 1720) || *(_DWORD *)(v7 + 4) != 3 )
  {
    CollectionDescriptor = -1073741667;
    v15 = "Device not started";
    v14 = v8;
    goto LABEL_347;
  }
  v2->IoStatus.Information = 0;
  switch ( LowPart )
  {
    case 0xB0193u:
      UserBuffer = v2->UserBuffer;
      if ( UserBuffer )
      {
        Length = CurrentStackLocation->Parameters.Read.Length;
        LODWORD(OutputBuffer) = Length;
        if ( v2->RequestorMode )
          ProbeForWrite(UserBuffer, Length, 1u);
        LOBYTE(ResultLength) = v2->RequestorMode;
        CollectionDescriptor = HidpGetCollectionDescriptor(
                                 v8,
                                 *(unsigned int *)(v105 + 8),
                                 v2->UserBuffer,
                                 &OutputBuffer);
        v106 = CollectionDescriptor;
        v2->IoStatus.Information = (unsigned int)OutputBuffer;
        goto LABEL_41;
      }
      CollectionDescriptor = -1073741306;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) == 0
        || (LOBYTE(a2) = 1, BYTE1(WPP_GLOBAL_Control->Timer) < 3u) )
      {
        LOBYTE(a2) = 0;
      }
      if ( (_BYTE)a2 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        WPP_RECORDER_AND_TRACE_SF_qdqL(
          WPP_GLOBAL_Control->AttachedDevice,
          (_DWORD)a2,
          WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED,
          *(_QWORD *)(v8 + 672),
          3,
          4,
          45,
          (__int64)WPP_09551ba6d0fe3383c1d3f23d6d3d8f25_Traceguids,
          *(_QWORD *)(*(_QWORD *)(v7 + 64) + 32LL),
          *(_DWORD *)(v7 + 8),
          *(_QWORD *)(v7 + 48),
          6);
      v85 = "Invalid buffer";
      v84 = 721299;
      v83 = v8;
      goto LABEL_296;
    case 0xB01ACu:
      v112 = 1;
      if ( CurrentStackLocation->Parameters.Create.Options == 1 )
      {
        MasterIrp = v2->AssociatedIrp.MasterIrp;
        if ( MasterIrp )
        {
          *(_BYTE *)(v7 + 258) = MasterIrp->Type;
          if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            || (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) == 0
            || (LOBYTE(a2) = 1, BYTE1(WPP_GLOBAL_Control->Timer) < 4u) )
          {
            LOBYTE(a2) = 0;
          }
          if ( (_BYTE)a2 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
            WPP_RECORDER_AND_TRACE_SF_qdqc(
              WPP_GLOBAL_Control->AttachedDevice,
              (_DWORD)a2,
              WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED,
              *(_QWORD *)(v8 + 672));
          goto LABEL_106;
        }
        v75 = "Null Buffer";
      }
      else
      {
        v75 = "Input size incorrect";
      }
      v76 = 721324;
      goto LABEL_271;
    case 0xB01B0u:
      v112 = 1;
      if ( CurrentStackLocation->Parameters.Create.Options == 4 )
      {
        v89 = v2->AssociatedIrp.MasterIrp;
        if ( v89 )
        {
          v90 = *(unsigned int *)&v89->Type;
          v77 = v8;
          if ( (unsigned int)v90 <= 0x186A0 )
          {
            HidpFdoNotifyPdoIdleTimeout(v8, v7, v90, v3);
            goto LABEL_106;
          }
          v75 = "Timeout too long";
          v76 = 721328;
LABEL_273:
          TraceLoggingIrpIoctlFailed(v77, v76, v75, v3);
          CollectionDescriptor = -1073741811;
          goto LABEL_30;
        }
        v75 = "Null Buffer";
      }
      else
      {
        v75 = "Input size incorrect";
      }
      v76 = 721328;
LABEL_271:
      v77 = v8;
      goto LABEL_273;
    case 0xB0233u:
      v83 = v8;
      if ( CurrentStackLocation->Parameters.Create.Options )
      {
        v84 = 721459;
        goto LABEL_293;
      }
      v9 = HidpFdoEnqueuePdoDeviceResetNotification(v8, v7, v2, &v100);
LABEL_320:
      CollectionDescriptor = v9;
      goto LABEL_321;
    case 0xB025Bu:
      if ( _InterlockedIncrement((volatile signed __int32 *)(v7 + 264)) > 0 )
      {
        HidpFdoAcquirePoFxPowerReferenceWithTag(v8, 0x10u);
        goto LABEL_106;
      }
      v86 = -1073741436;
      CollectionDescriptor = -1073741436;
      v87 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) == 0
        || (LOBYTE(a2) = 1, BYTE1(WPP_GLOBAL_Control->Timer) < 2u) )
      {
        LOBYTE(a2) = 0;
      }
      v88 = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      if ( !(_BYTE)a2 && WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        goto LABEL_30;
      LOWORD(v96) = 42;
      goto LABEL_308;
    case 0xB025Fu:
      if ( _InterlockedDecrement((volatile signed __int32 *)(v7 + 264)) >= 0 )
      {
        HidpFdoReleasePoFxPowerReferenceWithTag(v8, 16);
        goto LABEL_106;
      }
      v86 = -1073741436;
      CollectionDescriptor = -1073741436;
      v87 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) == 0
        || (LOBYTE(a2) = 1, BYTE1(WPP_GLOBAL_Control->Timer) < 2u) )
      {
        LOBYTE(a2) = 0;
      }
      v88 = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      if ( !(_BYTE)a2 && WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        goto LABEL_30;
      LOWORD(v96) = 43;
LABEL_308:
      LOBYTE(v86) = v88;
      WPP_RECORDER_AND_TRACE_SF_qdqqcLdl(v87->AttachedDevice, (_DWORD)a2, v86, *(_QWORD *)(v8 + 672));
      goto LABEL_30;
    case 0xB0267u:
      v83 = v8;
      if ( CurrentStackLocation->Parameters.Create.Options )
      {
        v84 = 721511;
LABEL_293:
        v85 = "Invalid input length";
        CollectionDescriptor = -1073741808;
LABEL_296:
        TraceLoggingIrpIoctlFailed(v83, v84, v85, v3);
        goto LABEL_41;
      }
      v9 = HidpFdoEnqueuePdoDevicePresenceNotification(v8, v7, v2, v3);
      goto LABEL_320;
    case 0xB0268u:
      v112 = 1;
      FileObject = CurrentStackLocation->FileObject;
      if ( !FileObject || (FsContext = FileObject->FsContext) == 0 )
      {
        CollectionDescriptor = -1073741727;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          || (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) == 0
          || (v82 = 1, BYTE1(WPP_GLOBAL_Control->Timer) < 2u) )
        {
          v82 = 0;
        }
        if ( v82 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          v99 = (int)CurrentStackLocation->FileObject;
          LOBYTE(FileObject) = v82;
          WPP_RECORDER_AND_TRACE_SF_qdqqqqd(
            WPP_GLOBAL_Control->AttachedDevice,
            (_DWORD)FileObject,
            WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED,
            *(_QWORD *)(v8 + 672));
        }
        goto LABEL_30;
      }
      if ( CurrentStackLocation->Parameters.Create.Options == 1 )
      {
        v78 = v2->AssociatedIrp.MasterIrp;
        if ( v78 )
        {
          Type = v78->Type;
          if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            || (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) == 0
            || (v80 = 1, BYTE1(WPP_GLOBAL_Control->Timer) < 4u) )
          {
            v80 = 0;
          }
          v81 = &WPP_RECORDER_INITIALIZED;
          if ( v80 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          {
            v99 = (int)FileObject;
            LOBYTE(FileObject) = v80;
            WPP_RECORDER_AND_TRACE_SF_qdqcqq(
              WPP_GLOBAL_Control->AttachedDevice,
              (_DWORD)FileObject,
              WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED,
              *(_QWORD *)(v8 + 672));
          }
          LOBYTE(v81) = Type;
          HidpFdoNotifyPdoClientInputSuppression(v8, v7, FsContext, v81);
          goto LABEL_106;
        }
        v75 = "Null Buffer";
      }
      else
      {
        v75 = "Input size incorrect";
      }
      v76 = 721512;
      goto LABEL_271;
  }
  v9 = HidpFdoStopIdleForIo(v3, v2, &v101);
  CollectionDescriptor = v9;
  if ( v9 )
  {
LABEL_321:
    v17 = v9 != 259;
LABEL_68:
    v112 = v17;
    goto LABEL_31;
  }
  if ( v104 > 0xB01BE )
  {
    if ( v104 == 721346 )
    {
      v46 = 16;
      goto LABEL_96;
    }
    if ( v104 == 721378 )
    {
      v70 = v2->AssociatedIrp.MasterIrp;
      if ( !v70 || CurrentStackLocation->Parameters.Create.Options < 4 )
      {
        CollectionDescriptor = -1073741811;
        v15 = "Invalid buffer";
        v16 = 721378;
        goto LABEL_56;
      }
      v71 = *(_DWORD *)&v70->Type;
      v72 = v2->Tail.Overlay.CurrentStackLocation;
      v72[-1].MajorFunction = 15;
      v72[-1].Parameters.Read.ByteOffset.LowPart = 721378;
      v72[-1].Parameters.Read.Length = v72->Parameters.Read.Length;
      v72[-1].Parameters.CreatePipe.Parameters = (_NAMED_PIPE_CREATE_PARAMETERS *)(unsigned int)(v71 + 67698688);
    }
    else
    {
      if ( v104 != 721382 )
      {
        if ( v104 != 721419 )
        {
          if ( v104 != 721423 )
          {
            if ( v104 != 721507 )
            {
              if ( v104 == 2703680 )
              {
                HidclassCollection = GetHidclassCollection(v8, *(unsigned int *)(v7 + 8));
                if ( HidclassCollection )
                {
                  if ( CurrentStackLocation->Parameters.Read.Length >= 4 )
                  {
                    LODWORD(OutputBuffer) = 0;
                    CollectionDescriptor = HidP_SysPowerCaps(
                                             *(PHIDP_PREPARSED_DATA *)(HidclassCollection + 304),
                                             (PULONG)&OutputBuffer);
                    if ( CollectionDescriptor >= 0 )
                    {
                      *(_DWORD *)v2->AssociatedIrp.MasterIrp = OutputBuffer;
                      v2->IoStatus.Information = 4;
                    }
                    goto LABEL_30;
                  }
                  CollectionDescriptor = -1073741306;
                  v2->IoStatus.Information = 4;
                  v15 = "Invalid Buffer";
                }
                else
                {
                  CollectionDescriptor = -1073741667;
                  v15 = "Cannot find collection";
                }
                v16 = 2703680;
              }
              else
              {
                if ( v104 != 2703684 )
                  goto LABEL_147;
                v57 = GetHidclassCollection(v8, *(unsigned int *)(v7 + 8));
                if ( v57 )
                {
                  CollectionDescriptor = QueuePowerEventIrp(v57, v2);
                  if ( CollectionDescriptor != 259 )
                    goto LABEL_30;
                  v112 = 0;
                  HidpFdoResumeIdleForIo(v8, v2);
                  v17 = 0;
LABEL_31:
                  if ( !v17 )
                  {
LABEL_32:
                    v18 = v112;
                    goto LABEL_33;
                  }
LABEL_42:
                  v2->IoStatus.Status = CollectionDescriptor;
                  IofCompleteRequest(v2, 0);
                  if ( v101 )
                    HidpFdoResumeIdleForIo(v8, v2);
                  goto LABEL_32;
                }
                CollectionDescriptor = -1073741667;
                v15 = "Cannot find collection";
                v16 = 2703684;
              }
              goto LABEL_56;
            }
            MdlAddress = v2->MdlAddress;
            if ( MdlAddress
              && (char *)MdlAddress->StartVa + MdlAddress->ByteOffset == (char *)CurrentStackLocation->Parameters.CreatePipe.Parameters )
            {
              v96 = &v113;
              LOBYTE(Priority) = *(_BYTE *)(v8 + 1976);
              ResultLength = CurrentStackLocation->Parameters.Create.Options;
              SetReport = HidpWriteReport(v8, v7, v2);
              goto LABEL_66;
            }
            CollectionDescriptor = -1073741808;
            if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              || (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) == 0
              || (LOBYTE(v10) = 1, BYTE1(WPP_GLOBAL_Control->Timer) < 2u) )
            {
              LOBYTE(v10) = 0;
            }
            if ( (_BYTE)v10 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
            {
              v99 = -1073741808;
              LOBYTE(v11) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
              WPP_RECORDER_AND_TRACE_SF_qdqqd(
                WPP_GLOBAL_Control->AttachedDevice,
                v10,
                v11,
                *(_QWORD *)(v8 + 672),
                2,
                4,
                57,
                (__int64)WPP_09551ba6d0fe3383c1d3f23d6d3d8f25_Traceguids,
                *(_QWORD *)(*(_QWORD *)(v7 + 64) + 32LL),
                *(_DWORD *)(v7 + 8),
                *(_QWORD *)(v7 + 48),
                (char)v2);
            }
LABEL_41:
            v112 = 1;
            goto LABEL_42;
          }
          v60 = CurrentStackLocation->FileObject->FsContext;
          if ( !v60 )
          {
            CollectionDescriptor = -1073741727;
            if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              || (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) == 0
              || (LOBYTE(v10) = 1, BYTE1(WPP_GLOBAL_Control->Timer) < 3u) )
            {
              LOBYTE(v10) = 0;
            }
            v3 = &WPP_RECORDER_INITIALIZED;
            if ( (_BYTE)v10 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
              WPP_RECORDER_AND_TRACE_SF_qdqL(
                WPP_GLOBAL_Control->AttachedDevice,
                v10,
                WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED,
                *(_QWORD *)(v8 + 672),
                3,
                4,
                55,
                (__int64)WPP_09551ba6d0fe3383c1d3f23d6d3d8f25_Traceguids,
                *(_QWORD *)(*(_QWORD *)(v7 + 64) + 32LL),
                *(_DWORD *)(v7 + 8),
                *(_QWORD *)(v7 + 48),
                97);
            v15 = "FsContext NULL";
            goto LABEL_223;
          }
          v61 = GetHidclassCollection(v8, *(unsigned int *)(v7 + 8));
          OutputBuffer = v61;
          if ( !v61 )
          {
            CollectionDescriptor = -1073741823;
            if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              || (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) == 0
              || (LOBYTE(v62) = 1, BYTE1(WPP_GLOBAL_Control->Timer) < 3u) )
            {
              LOBYTE(v62) = 0;
            }
            v3 = &WPP_RECORDER_INITIALIZED;
            if ( (_BYTE)v62 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
              WPP_RECORDER_AND_TRACE_SF_qdqL(
                WPP_GLOBAL_Control->AttachedDevice,
                v62,
                WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED,
                *(_QWORD *)(v8 + 672),
                3,
                4,
                56,
                (__int64)WPP_09551ba6d0fe3383c1d3f23d6d3d8f25_Traceguids,
                *(_QWORD *)(*(_QWORD *)(v7 + 64) + 32LL),
                *(_DWORD *)(v7 + 8),
                *(_QWORD *)(v7 + 48),
                1);
            v15 = "Cannot find collection";
            goto LABEL_223;
          }
          if ( !v60[118] )
          {
            CollectionDescriptor = -1073741727;
            v15 = "Secure open not enabled";
LABEL_223:
            v16 = 721423;
            goto LABEL_56;
          }
          v63 = (KSPIN_LOCK *)(v61 + 344);
          v64 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v61 + 344));
          v65 = *((_DWORD *)v60 + 30);
          if ( v65 )
          {
            *((_DWORD *)v60 + 30) = v65 - 1;
            --*(_DWORD *)(OutputBuffer + 336);
          }
          KeReleaseSpinLock(v63, v64);
          if ( !(unsigned int)Feature_HCTI01__private_IsEnabledDeviceUsageNoInline(v38, v37, v39, v40) )
            goto LABEL_30;
          v32 = 0;
LABEL_72:
          TlgAggrSecureReadIoctl(v8, v32);
          goto LABEL_30;
        }
        v66 = (__int64)CurrentStackLocation->FileObject->FsContext;
        OutputBuffer = v66;
        if ( v66 )
        {
          v67 = GetHidclassCollection(v8, *(unsigned int *)(v7 + 8));
          v111 = v67;
          if ( v67 )
          {
            if ( !*(_BYTE *)(v66 + 118) )
            {
              TraceLoggingIrpIoctlFailed(v8, 721419, "Secure open not enabled", v69);
              CollectionDescriptor = -1073741727;
              goto LABEL_30;
            }
            v26 = (KSPIN_LOCK *)(v67 + 344);
            v27 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v67 + 344));
            ++*(_DWORD *)(OutputBuffer + 120);
            ++*(_DWORD *)(v111 + 336);
            KeReleaseSpinLock(v26, v27);
            if ( !(unsigned int)Feature_HCTI01__private_IsEnabledDeviceUsageNoInline(v29, v28, v30, v31) )
              goto LABEL_30;
            LOBYTE(v32) = 1;
            goto LABEL_72;
          }
          CollectionDescriptor = -1073741823;
          if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            || (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) == 0
            || (LOBYTE(v68) = 1, BYTE1(WPP_GLOBAL_Control->Timer) < 3u) )
          {
            LOBYTE(v68) = 0;
          }
          v3 = &WPP_RECORDER_INITIALIZED;
          if ( (_BYTE)v68 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
            WPP_RECORDER_AND_TRACE_SF_qdqL(
              WPP_GLOBAL_Control->AttachedDevice,
              v68,
              WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED,
              *(_QWORD *)(v8 + 672),
              3,
              4,
              54,
              (__int64)WPP_09551ba6d0fe3383c1d3f23d6d3d8f25_Traceguids,
              *(_QWORD *)(*(_QWORD *)(v7 + 64) + 32LL),
              *(_DWORD *)(v7 + 8),
              *(_QWORD *)(v7 + 48),
              1);
          v15 = "Cannot find collection";
        }
        else
        {
          CollectionDescriptor = -1073741727;
          if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            || (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) == 0
            || (LOBYTE(v10) = 1, BYTE1(WPP_GLOBAL_Control->Timer) < 3u) )
          {
            LOBYTE(v10) = 0;
          }
          v3 = &WPP_RECORDER_INITIALIZED;
          if ( (_BYTE)v10 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
            WPP_RECORDER_AND_TRACE_SF_qdqL(
              WPP_GLOBAL_Control->AttachedDevice,
              v10,
              WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED,
              *(_QWORD *)(v8 + 672),
              3,
              4,
              53,
              (__int64)WPP_09551ba6d0fe3383c1d3f23d6d3d8f25_Traceguids,
              *(_QWORD *)(*(_QWORD *)(v7 + 64) + 32LL),
              *(_DWORD *)(v7 + 8),
              *(_QWORD *)(v7 + 48),
              97);
          v15 = "FsContext NULL";
        }
        v16 = 721419;
        goto LABEL_56;
      }
      v44 = v2->Tail.Overlay.CurrentStackLocation;
      v44[-1].MajorFunction = 15;
      v44[-1].Parameters.Read.ByteOffset.LowPart = 721382;
      v44[-1].Parameters.Read.Length = v44->Parameters.Read.Length;
    }
    v43 = *(_QWORD *)v8;
    goto LABEL_94;
  }
  if ( v104 == 721342 )
  {
    v46 = 15;
LABEL_96:
    DeviceString = HidpGetDeviceString(v8, v2, v46);
    goto LABEL_97;
  }
  if ( v104 > 0xB019C )
  {
    if ( v104 != 721310 )
    {
      if ( v104 != 721312 )
      {
        if ( v104 != 721314 )
        {
          if ( v104 != 721316 )
          {
            if ( v104 != 721318 )
            {
              if ( v104 == 721320 )
              {
                v13 = v2->AssociatedIrp.MasterIrp;
                v14 = v8;
                if ( !v13 )
                {
                  CollectionDescriptor = -1073741811;
                  v15 = "Invalid buffer";
                  v16 = 721320;
LABEL_29:
                  TraceLoggingIrpIoctlFailed(v14, v16, v15, v3);
                  goto LABEL_30;
                }
                LODWORD(OutputBuffer) = CurrentStackLocation->Parameters.Read.Length;
                CollectionDescriptor = HidpGetCollectionInformation(v8, *(unsigned int *)(v7 + 8), v13, &OutputBuffer);
LABEL_51:
                v2->IoStatus.Information = (unsigned int)OutputBuffer;
                goto LABEL_30;
              }
              if ( v104 != 721338 )
              {
LABEL_147:
                if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                  || (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) == 0
                  || (LOBYTE(v10) = 1, BYTE1(WPP_GLOBAL_Control->Timer) < 3u) )
                {
                  LOBYTE(v10) = 0;
                }
                if ( (_BYTE)v10 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
                  WPP_RECORDER_AND_TRACE_SF_qdqL(
                    WPP_GLOBAL_Control->AttachedDevice,
                    v10,
                    WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED,
                    *(_QWORD *)(v8 + 672),
                    3,
                    4,
                    58,
                    (__int64)WPP_09551ba6d0fe3383c1d3f23d6d3d8f25_Traceguids,
                    *(_QWORD *)(*(_QWORD *)(v7 + 64) + 32LL),
                    *(_DWORD *)(v7 + 8),
                    *(_QWORD *)(v7 + 48),
                    v104);
                CollectionDescriptor = -1073741808;
                goto LABEL_30;
              }
              v46 = 14;
              goto LABEL_96;
            }
            goto LABEL_65;
          }
          v53 = v2->AssociatedIrp.MasterIrp;
          if ( v53 && CurrentStackLocation->Parameters.Create.Options >= 4 )
          {
            v54 = CurrentStackLocation->FileObject->FsContext;
            if ( !v54 )
            {
              CollectionDescriptor = -1073741727;
              if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                || (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) == 0
                || (LOBYTE(v54) = 1, BYTE1(WPP_GLOBAL_Control->Timer) < 3u) )
              {
                LOBYTE(v54) = 0;
              }
              v3 = &WPP_RECORDER_INITIALIZED;
              if ( (_BYTE)v54 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
                WPP_RECORDER_AND_TRACE_SF_qdqL(
                  WPP_GLOBAL_Control->AttachedDevice,
                  (_DWORD)v54,
                  WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED,
                  *(_QWORD *)(v8 + 672),
                  3,
                  4,
                  52,
                  (__int64)WPP_09551ba6d0fe3383c1d3f23d6d3d8f25_Traceguids,
                  *(_QWORD *)(*(_QWORD *)(v7 + 64) + 32LL),
                  *(_DWORD *)(v7 + 8),
                  *(_QWORD *)(v7 + 48),
                  97);
              v15 = "FsContext NULL";
              goto LABEL_167;
            }
            v55 = *(_DWORD *)&v53->Type;
            if ( (unsigned int)(v55 - 2) <= 0x1FE )
            {
              v54[23] = v55;
              goto LABEL_106;
            }
            CollectionDescriptor = -1073741811;
            v15 = "Invalid input report queue size";
          }
          else
          {
            CollectionDescriptor = -1073741811;
            v15 = "Invalid buffer";
          }
LABEL_167:
          v16 = 721316;
          goto LABEL_56;
        }
        goto LABEL_65;
      }
      v48 = v2->AssociatedIrp.MasterIrp;
      if ( !v48 || CurrentStackLocation->Parameters.Read.Length < 4 )
      {
        CollectionDescriptor = -1073741811;
        v15 = "Invalid buffer";
        v16 = 721312;
        goto LABEL_56;
      }
      v56 = CurrentStackLocation->FileObject->FsContext;
      if ( !v56 )
      {
        CollectionDescriptor = -1073741727;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          || (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) == 0
          || (LOBYTE(v10) = 1, BYTE1(WPP_GLOBAL_Control->Timer) < 3u) )
        {
          LOBYTE(v10) = 0;
        }
        if ( (_BYTE)v10 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          WPP_RECORDER_AND_TRACE_SF_qdqL(
            WPP_GLOBAL_Control->AttachedDevice,
            v10,
            WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED,
            *(_QWORD *)(v8 + 672),
            3,
            4,
            51,
            (__int64)WPP_09551ba6d0fe3383c1d3f23d6d3d8f25_Traceguids,
            *(_QWORD *)(*(_QWORD *)(v7 + 64) + 32LL),
            *(_DWORD *)(v7 + 8),
            *(_QWORD *)(v7 + 48),
            97);
        goto LABEL_30;
      }
      v49 = v56[23];
      goto LABEL_104;
    }
    v33 = **(struct _DEVICE_OBJECT ***)(v7 + 64);
    v34 = CurrentStackLocation->Parameters.Read.Length;
    v35 = v2->MdlAddress;
    MappedSystemVa = 0;
    if ( v35 )
    {
      if ( (v35->MdlFlags & 5) != 0 )
        MappedSystemVa = v35->MappedSystemVa;
      else
        MappedSystemVa = MmMapLockedPagesSpecifyCache(v35, 0, MmCached, 0, 0, 0x40000010u);
    }
    if ( !MappedSystemVa || !v34 )
    {
      CollectionDescriptor = -1073741592;
      goto LABEL_30;
    }
    LODWORD(OutputBuffer) = 0;
    CollectionDescriptor = IoGetDeviceProperty(
                             v33,
                             DevicePropertyHardwareID,
                             v34,
                             MappedSystemVa,
                             (PULONG)&OutputBuffer);
    if ( CollectionDescriptor >= 0 )
      goto LABEL_51;
LABEL_30:
    v17 = 1;
    goto LABEL_31;
  }
  switch ( v104 )
  {
    case 0xB019Cu:
      v23 = GetHidclassCollection(v8, *(unsigned int *)(v7 + 8));
      v24 = v23;
      if ( v23 && *(_BYTE *)(v23 + 292) )
      {
        v50 = v2->AssociatedIrp.MasterIrp;
        if ( v50 && CurrentStackLocation->Parameters.Create.Options >= 4 )
        {
          v51 = CurrentStackLocation->FileObject->FsContext;
          if ( v51 )
          {
            v52 = *(_DWORD *)&v50->Type;
            if ( v52 )
            {
              if ( v52 > 0x2710 )
                v52 = 10000;
              *(_DWORD *)(v24 + 80) = v52;
              v51[117] = 0;
              StopPollingLoop(v24, 0);
              StartPollingLoop(v8, v24, 0);
            }
            else
            {
              v51[117] = 1;
            }
            goto LABEL_106;
          }
          CollectionDescriptor = -1073741727;
          if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            || (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) == 0
            || (LOBYTE(v51) = 1, BYTE1(WPP_GLOBAL_Control->Timer) < 3u) )
          {
            LOBYTE(v51) = 0;
          }
          v3 = &WPP_RECORDER_INITIALIZED;
          if ( (_BYTE)v51 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
            WPP_RECORDER_AND_TRACE_SF_qdqL(
              WPP_GLOBAL_Control->AttachedDevice,
              (_DWORD)v51,
              WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED,
              *(_QWORD *)(v8 + 672),
              3,
              4,
              50,
              (__int64)WPP_09551ba6d0fe3383c1d3f23d6d3d8f25_Traceguids,
              *(_QWORD *)(*(_QWORD *)(v7 + 64) + 32LL),
              *(_DWORD *)(v7 + 8),
              *(_QWORD *)(v7 + 48),
              97);
          v15 = "FsContext NULL";
        }
        else
        {
          CollectionDescriptor = -1073741306;
          v15 = "Invalid buffer size";
        }
      }
      else
      {
        CollectionDescriptor = -1073741808;
        v15 = "Cannot find collection for poll";
      }
      v16 = 721308;
      goto LABEL_56;
    case 0xB0190u:
      goto LABEL_359;
    case 0xB0191u:
    case 0xB0192u:
      goto LABEL_65;
    case 0xB0194u:
LABEL_359:
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) == 0
        || (LOBYTE(v10) = 1, BYTE1(WPP_GLOBAL_Control->Timer) < 3u) )
      {
        LOBYTE(v10) = 0;
      }
      if ( (_BYTE)v10 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        WPP_RECORDER_AND_TRACE_SF_qdqL(
          WPP_GLOBAL_Control->AttachedDevice,
          v10,
          WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED,
          *(_QWORD *)(v8 + 672),
          3,
          4,
          48,
          (__int64)WPP_09551ba6d0fe3383c1d3f23d6d3d8f25_Traceguids,
          *(_QWORD *)(*(_QWORD *)(v7 + 64) + 32LL),
          *(_DWORD *)(v7 + 8),
          *(_QWORD *)(v7 + 48),
          v104);
      CollectionDescriptor = -1073741822;
      goto LABEL_30;
    case 0xB0195u:
LABEL_65:
      SetReport = HidpGetSetReport(OutputBuffer, v2, CurrentStackLocation->Parameters.Read.ByteOffset.LowPart, &v113);
LABEL_66:
      CollectionDescriptor = SetReport;
      if ( !v113 )
      {
        v112 = 1;
        goto LABEL_42;
      }
      v17 = 0;
      goto LABEL_68;
    case 0xB0197u:
      if ( !CurrentStackLocation->FileObject->FsContext )
      {
        CollectionDescriptor = -1073741727;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          || (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) == 0
          || (LOBYTE(v10) = 1, BYTE1(WPP_GLOBAL_Control->Timer) < 3u) )
        {
          LOBYTE(v10) = 0;
        }
        v3 = &WPP_RECORDER_INITIALIZED;
        if ( (_BYTE)v10 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          WPP_RECORDER_AND_TRACE_SF_qdqL(
            WPP_GLOBAL_Control->AttachedDevice,
            v10,
            WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED,
            *(_QWORD *)(v8 + 672),
            3,
            4,
            49,
            (__int64)WPP_09551ba6d0fe3383c1d3f23d6d3d8f25_Traceguids,
            *(_QWORD *)(*(_QWORD *)(v7 + 64) + 32LL),
            *(_DWORD *)(v7 + 8),
            *(_QWORD *)(v7 + 48),
            97);
        v15 = "FsContext NULL";
        v16 = 721303;
        goto LABEL_56;
      }
      HidpFlushReportQueue();
LABEL_106:
      CollectionDescriptor = 0;
      goto LABEL_30;
    case 0xB0198u:
      v47 = GetHidclassCollection(v8, *(unsigned int *)(v7 + 8));
      if ( v47 && *(_BYTE *)(v47 + 292) )
      {
        v48 = v2->AssociatedIrp.MasterIrp;
        if ( v48 && CurrentStackLocation->Parameters.Read.Length >= 4 )
        {
          v49 = *(_DWORD *)(v47 + 80);
LABEL_104:
          *(_DWORD *)&v48->Type = v49;
          v2->IoStatus.Information = 4;
          goto LABEL_106;
        }
        CollectionDescriptor = -1073741306;
        v15 = "Invalid buffer size";
      }
      else
      {
        CollectionDescriptor = -1073741808;
        v15 = "Cannot find collection for poll";
      }
      v16 = 721304;
LABEL_56:
      v14 = v8;
      goto LABEL_29;
  }
  if ( v104 != 721306 )
    goto LABEL_147;
  v41 = *(_QWORD *)(OutputBuffer + 96);
  v42 = v2->Tail.Overlay.CurrentStackLocation;
  v42[-1].MajorFunction = 15;
  v42[-1].Parameters.Read.ByteOffset.LowPart = 721306;
  v42[-1].Parameters.Read.Length = v42->Parameters.Read.Length;
  v43 = *(_QWORD *)(v41 + 32);
LABEL_94:
  DeviceString = HidpCallDriverAsynchronous(v43, v2);
LABEL_97:
  CollectionDescriptor = DeviceString;
  v18 = 0;
LABEL_33:
  if ( v102 )
  {
    if ( v18 )
    {
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) == 0
        || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
      {
        v4 = 0;
      }
      if ( v4 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        v22 = v105;
        LOBYTE(v22) = v4;
        WPP_RECORDER_AND_TRACE_SF_qdqqcLdd(
          WPP_GLOBAL_Control->AttachedDevice,
          v22,
          WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED,
          *(_QWORD *)(v8 + 672),
          ResultLength,
          Priority,
          (_DWORD)v96,
          v97,
          *(_QWORD *)(*(_QWORD *)(v105 + 64) + 32LL),
          *(_DWORD *)(v105 + 8),
          *(_QWORD *)(v105 + 48),
          (char)v2,
          v99,
          v104,
          CollectionDescriptor,
          v100);
      }
    }
    else
    {
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) == 0
        || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
      {
        v4 = 0;
      }
      if ( v4 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        v92 = CollectionDescriptor;
        if ( v100 )
          v92 = 3;
        v93 = *(_QWORD *)(v105 + 64);
        v98 = *(_QWORD *)(v93 + 32);
        LOBYTE(v93) = v4;
        WPP_RECORDER_AND_TRACE_SF_qdqqcLd(
          WPP_GLOBAL_Control->AttachedDevice,
          v93,
          WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED,
          *(_QWORD *)(v8 + 672),
          ResultLength,
          Priority,
          (_DWORD)v96,
          v97,
          v98,
          *(_DWORD *)(v105 + 8),
          *(_QWORD *)(v105 + 48),
          (char)v2,
          v99,
          v104,
          v92);
      }
    }
  }
  if ( v100 )
    return 259;
  return (unsigned int)CollectionDescriptor;
}

```

## disassembly

```asm
0x180006ac8  mov     r11, rsp
0x180006acb  mov     [r11+10h], rdx
0x180006acf  mov     [r11+8], rcx
0x180006ad3  push    rbx
0x180006ad4  push    rsi
0x180006ad5  push    rdi
0x180006ad6  push    r12
0x180006ad8  push    r13
0x180006ada  push    r14
0x180006adc  push    r15
0x180006ade  sub     rsp, 0B0h
0x180006ae5  mov     r13, rdx
0x180006ae8  mov     r9, rcx
0x180006aeb  mov     r12d, 1
0x180006af1  mov     [rsp+0E8h+arg_10], r12b
0x180006af9  xor     edi, edi
0x180006afb  mov     [r11-68h], dil
0x180006aff  mov     [r11+20h], dil
0x180006b03  mov     rbx, [rdx+0B8h]
0x180006b0a  mov     esi, [rbx+18h]
0x180006b0d  mov     [rsp+0E8h+var_64], esi
0x180006b14  mov     [rsp+0E8h+var_54], esi
0x180006b1b  mov     al, [rcx+18h]
0x180006b1e  mov     [rsp+0E8h+var_66], al
0x180006b25  mov     [rsp+0E8h+var_65], al
0x180006b2c  mov     [r11-67h], dil
0x180006b30  lea     r15, [rcx+20h]
0x180006b34  test    al, al
0x180006b36  jz      loc_180007195
0x180006b3c  mov     rax, r15
0x180006b3f  mov     [rsp+0E8h+var_60], rax
0x180006b47  mov     [rsp+0E8h+var_50], rax
0x180006b4f  mov     r14, [r15+40h]
0x180006b53  add     r14, 20h ; ' '
0x180006b57  mov     [rsp+0E8h+var_48], r14
0x180006b5f  lea     r11, WPP_GLOBAL_Control
0x180006b66  mov     rcx, cs:WPP_GLOBAL_Control
0x180006b6d  cmp     rcx, r11
0x180006b70  jz      short loc_180006B7D
0x180006b72  mov     eax, [rcx+2Ch]
0x180006b75  test    al, 8
0x180006b77  jnz     loc_1800071B4
0x180006b7d  mov     dl, dil
0x180006b80  lea     r10, WPP_RECORDER_INITIALIZED
0x180006b87  cmp     cs:WPP_RECORDER_INITIALIZED, r10
0x180006b8e  setnz   r8b
0x180006b92  test    dl, dl
0x180006b94  jz      loc_1800071C6
0x180006b9a  mov     dword ptr [rsp+0E8h+var_80], esi
0x180006b9e  mov     [rsp+0E8h+var_90], r13
0x180006ba3  mov     rax, [r15+30h]
0x180006ba7  mov     [rsp+0E8h+var_98], rax
0x180006bac  mov     eax, [r15+8]
0x180006bb0  mov     [rsp+0E8h+var_A0], eax
0x180006bb4  mov     rax, [r14]
0x180006bb7  mov     [rsp+0E8h+var_A8], rax
0x180006bbc  mov     r9, [r14+2A0h]
0x180006bc3  mov     rcx, [rcx+18h]
0x180006bc7  call    WPP_RECORDER_AND_TRACE_SF_qdqqcL
0x180006bcc  mov     r9, [rsp+0E8h+OutputBuffer]
0x180006bd4  lea     r11, WPP_GLOBAL_Control
0x180006bdb  lea     r10, WPP_RECORDER_INITIALIZED
0x180006be2  cmp     [r14+6B8h], edi
0x180006be9  jz      loc_18000833F
0x180006bef  cmp     dword ptr [r15+4], 3
0x180006bf4  jnz     loc_18000833F
0x180006bfa  mov     [r13+38h], rdi
0x180006bfe  mov     eax, esi
0x180006c00  sub     eax, 0B0193h
0x180006c05  jz      loc_180006D2D
0x180006c0b  sub     eax, 19h
0x180006c0e  jz      loc_180008282
0x180006c14  sub     eax, 4
0x180006c17  jz      loc_180008231
0x180006c1d  sub     eax, 83h
0x180006c22  jz      loc_180008201
0x180006c28  sub     eax, 28h ; '('
0x180006c2b  jz      loc_180008188
0x180006c31  sub     eax, 4
0x180006c34  jz      loc_18000808A
0x180006c3a  sub     eax, 8
0x180006c3d  jz      loc_180007FE9
0x180006c43  cmp     eax, r12d
0x180006c46  jz      loc_180007E44
0x180006c4c  lea     r8, [rsp+0E8h+var_67]
0x180006c54  mov     rdx, r13
0x180006c57  mov     rcx, r9
0x180006c5a  call    HidpFdoStopIdleForIo
0x180006c5f  mov     esi, eax
0x180006c61  test    eax, eax
0x180006c63  jnz     loc_180008222
0x180006c69  mov     eax, 0B01BEh
0x180006c6e  mov     r10d, [rsp+0E8h+var_64]
0x180006c76  cmp     r10d, eax
0x180006c79  ja      loc_180007834
0x180006c7f  jz      loc_180007829
0x180006c85  mov     eax, 0B019Ch
0x180006c8a  cmp     r10d, eax
0x180006c8d  jbe     loc_180006FC3
0x180006c93  mov     eax, r10d
0x180006c96  sub     eax, 0B019Eh
0x180006c9b  jz      loc_1800070E2
0x180006ca1  sub     eax, 2
0x180006ca4  jz      loc_18000773C
0x180006caa  sub     eax, 2
0x180006cad  jz      loc_18000703A
0x180006cb3  sub     eax, 2
0x180006cb6  jz      loc_180007637
0x180006cbc  sub     eax, 2
0x180006cbf  jz      loc_18000703A
0x180006cc5  sub     eax, 2
0x180006cc8  jnz     loc_180007590
0x180006cce  mov     r8, [r13+18h]
0x180006cd2  mov     rcx, r14
0x180006cd5  test    r8, r8
0x180006cd8  jnz     loc_180006F96
0x180006cde  mov     esi, 0C000000Dh
0x180006ce3  lea     r8, aInvalidBuffer_0; "Invalid buffer"
0x180006cea  mov     edx, 0B01A8h
0x180006cef  call    TraceLoggingIrpIoctlFailed
0x180006cf4  mov     ebx, 103h
0x180006cf9  mov     al, r12b
0x180006cfc  test    al, al
0x180006cfe  jnz     loc_180006E50
0x180006d04  mov     r15b, [rsp+0E8h+arg_10]
0x180006d0c  cmp     [rsp+0E8h+var_66], dil
0x180006d14  jnz     loc_180006EF6
0x180006d1a  cmp     [rsp+0E8h+var_68], dil
0x180006d22  cmovnz  esi, ebx
0x180006d25  mov     eax, esi
0x180006d27  jmp     loc_1800083FC
0x180006d2d  mov     rcx, [r13+70h]; Address
0x180006d31  test    rcx, rcx
0x180006d34  jz      loc_1800082FA
0x180006d3a  mov     eax, [rbx+8]
0x180006d3d  mov     dword ptr [rsp+0E8h+OutputBuffer], eax
0x180006d44  cmp     [r13+40h], dil
0x180006d48  jz      short loc_180006D5B
0x180006d4a  mov     edx, eax; Length
0x180006d4c  mov     r8d, r12d; Alignment
0x180006d4f  call    cs:__imp_ProbeForWrite
0x180006d56  nop     dword ptr [rax+rax+00h]
0x180006d5b  mov     al, [r13+40h]
0x180006d5f  mov     byte ptr [rsp+0E8h+ResultLength], al
0x180006d63  lea     r9, [rsp+0E8h+OutputBuffer]
0x180006d6b  mov     r8, [r13+70h]
0x180006d6f  mov     rdx, [rsp+0E8h+var_60]
0x180006d77  mov     edx, [rdx+8]
0x180006d7a  mov     rcx, r14
0x180006d7d  call    HidpGetCollectionDescriptor
0x180006d82  mov     esi, eax
0x180006d84  mov     [rsp+0E8h+var_58], eax
0x180006d8b  mov     eax, dword ptr [rsp+0E8h+OutputBuffer]
0x180006d92  mov     [r13+38h], rax
0x180006d96  jmp     loc_180006E43
0x180006d9b  mov     esi, eax
0x180006d9d  mov     [rsp+0E8h+var_58], eax
0x180006da4  lea     rax, WPP_GLOBAL_Control
0x180006dab  mov     rcx, cs:WPP_GLOBAL_Control
0x180006db2  cmp     rcx, rax
0x180006db5  jz      short loc_180006DC8
0x180006db7  mov     eax, [rcx+2Ch]
0x180006dba  test    al, 8
0x180006dbc  jz      short loc_180006DC8
0x180006dbe  cmp     byte ptr [rcx+29h], 3
0x180006dc2  jb      short loc_180006DC8
0x180006dc4  mov     dl, 1
0x180006dc6  jmp     short loc_180006DCA
0x180006dc8  xor     dl, dl
0x180006dca  lea     r8, WPP_RECORDER_INITIALIZED
0x180006dd1  cmp     cs:WPP_RECORDER_INITIALIZED, r8
0x180006dd8  setnz   r8b
0x180006ddc  test    dl, dl
0x180006dde  jnz     loc_180006E83
0x180006de4  test    r8b, r8b
0x180006de7  jnz     loc_180006E83
0x180006ded  mov     rdx, [rsp+0E8h+var_50]
0x180006df5  mov     [rsp+0E8h+var_60], rdx
0x180006dfd  mov     r14, [rsp+0E8h+var_48]
0x180006e05  lea     r8, aAccessViolatio; "Access Violation"
0x180006e0c  mov     edx, 0B0193h
0x180006e11  mov     rcx, r14
0x180006e14  call    TraceLoggingIrpIoctlFailed
0x180006e19  xor     edi, edi
0x180006e1b  lea     r12d, [rdi+1]
0x180006e1f  mov     r13, [rsp+0E8h+arg_8]
0x180006e27  mov     eax, [rsp+0E8h+var_54]
0x180006e2e  mov     [rsp+0E8h+var_64], eax
0x180006e35  mov     al, [rsp+0E8h+var_65]
0x180006e3c  mov     [rsp+0E8h+var_66], al
0x180006e43  mov     [rsp+0E8h+arg_10], r12b
0x180006e4b  mov     ebx, 103h
0x180006e50  mov     [r13+30h], esi
0x180006e54  xor     edx, edx; PriorityBoost
0x180006e56  mov     rcx, r13; Irp
0x180006e59  call    cs:__imp_IofCompleteRequest
0x180006e60  nop     dword ptr [rax+rax+00h]
0x180006e65  cmp     [rsp+0E8h+var_67], dil
0x180006e6d  jz      loc_180006D04
0x180006e73  mov     rdx, r13
0x180006e76  mov     rcx, r14
0x180006e79  call    HidpFdoResumeIdleForIo
0x180006e7e  jmp     loc_180006D04
0x180006e83  mov     rbx, [rsp+0E8h+var_50]
0x180006e8b  mov     [rsp+0E8h+var_60], rbx
0x180006e93  mov     r9, [rbx+40h]
0x180006e97  mov     r10d, 2Ch ; ','
0x180006e9d  mov     dword ptr [rsp+0E8h+var_90], esi
0x180006ea1  mov     rax, [rbx+30h]
0x180006ea5  mov     [rsp+0E8h+var_98], rax
0x180006eaa  mov     eax, [rbx+8]
0x180006ead  mov     [rsp+0E8h+var_A0], eax
0x180006eb1  mov     rax, [r9+20h]
0x180006eb5  mov     [rsp+0E8h+var_A8], rax
0x180006eba  lea     rax, WPP_09551ba6d0fe3383c1d3f23d6d3d8f25_Traceguids
0x180006ec1  mov     [rsp+0E8h+var_B0], rax
0x180006ec6  mov     word ptr [rsp+0E8h+var_B8], r10w
0x180006ecc  mov     [rsp+0E8h+Priority], 4
0x180006ed4  mov     byte ptr [rsp+0E8h+ResultLength], 3
0x180006ed9  mov     r14, [rsp+0E8h+var_48]
0x180006ee1  mov     r9, [r14+2A0h]
0x180006ee8  mov     rcx, [rcx+18h]
0x180006eec  call    WPP_RECORDER_AND_TRACE_SF_qdqL
0x180006ef1  jmp     loc_180006E05
0x180006ef6  test    r15b, r15b
0x180006ef9  jz      loc_18000835A
0x180006eff  mov     rcx, cs:WPP_GLOBAL_Control
0x180006f06  lea     rax, WPP_GLOBAL_Control
0x180006f0d  cmp     rcx, rax
0x180006f10  jnz     loc_180006FF6
0x180006f16  mov     r12b, dil
0x180006f19  lea     rdx, WPP_RECORDER_INITIALIZED
0x180006f20  cmp     cs:WPP_RECORDER_INITIALIZED, rdx
0x180006f27  setnz   r8b
0x180006f2b  test    r12b, r12b
0x180006f2e  jnz     short loc_180006F39
0x180006f30  test    r8b, r8b
0x180006f33  jz      loc_180006D1A
0x180006f39  movzx   eax, [rsp+0E8h+var_68]
0x180006f41  mov     rdx, [rsp+0E8h+var_60]
0x180006f49  mov     r10, [rdx+40h]
0x180006f4d  mov     [rsp+0E8h+var_70], eax
0x180006f51  mov     [rsp+0E8h+var_78], esi
0x180006f55  mov     eax, [rsp+0E8h+var_64]
0x180006f5c  mov     dword ptr [rsp+0E8h+var_80], eax
0x180006f60  mov     [rsp+0E8h+var_90], r13
0x180006f65  mov     rax, [rdx+30h]
0x180006f69  mov     [rsp+0E8h+var_98], rax
0x180006f6e  mov     eax, [rdx+8]
0x180006f71  mov     [rsp+0E8h+var_A0], eax
0x180006f75  mov     rax, [r10+20h]
0x180006f79  mov     [rsp+0E8h+var_A8], rax
0x180006f7e  mov     r9, [r14+2A0h]
0x180006f85  mov     dl, r12b
0x180006f88  mov     rcx, [rcx+18h]
0x180006f8c  call    WPP_RECORDER_AND_TRACE_SF_qdqqcLdd
0x180006f91  jmp     loc_180006D1A
0x180006f96  mov     eax, [rbx+8]
0x180006f99  mov     dword ptr [rsp+0E8h+OutputBuffer], eax
0x180006fa0  lea     r9, [rsp+0E8h+OutputBuffer]
0x180006fa8  mov     edx, [r15+8]
0x180006fac  call    HidpGetCollectionInformation
0x180006fb1  mov     esi, eax
0x180006fb3  mov     eax, dword ptr [rsp+0E8h+OutputBuffer]
0x180006fba  mov     [r13+38h], rax
0x180006fbe  jmp     loc_180006CF4
0x180006fc3  jnz     short loc_180007010
0x180006fc5  mov     edx, [r15+8]
0x180006fc9  mov     rcx, r14
0x180006fcc  call    GetHidclassCollection
0x180006fd1  mov     rsi, rax
0x180006fd4  test    rax, rax
0x180006fd7  jnz     loc_18000745B
0x180006fdd  mov     esi, 0C0000010h
0x180006fe2  lea     r8, aCannotFindColl; "Cannot find collection for poll"
0x180006fe9  mov     edx, 0B019Ch
0x180006fee  mov     rcx, r14
0x180006ff1  jmp     loc_180006CEF
0x180006ff6  mov     eax, [rcx+2Ch]
0x180006ff9  test    al, 8
0x180006ffb  jz      loc_180006F16
0x180007001  cmp     byte ptr [rcx+29h], 4
0x180007005  jnb     loc_180006F19
0x18000700b  jmp     loc_180006F16
0x180007010  mov     eax, r10d
0x180007013  sub     eax, 0B0190h
0x180007018  jz      loc_1800073BD
0x18000701e  sub     eax, r12d
0x180007021  jz      short loc_18000703A
0x180007023  sub     eax, r12d
0x180007026  jz      short loc_18000703A
0x180007028  sub     eax, 2
0x18000702b  jz      loc_1800073BD
0x180007031  sub     eax, r12d
0x180007034  jnz     loc_1800071D4
0x18000703a  lea     r9, [rsp+0E8h+arg_18]
0x180007042  mov     r8d, [rbx+18h]
0x180007046  mov     rdx, r13
0x180007049  mov     rcx, [rsp+0E8h+OutputBuffer]
0x180007051  call    HidpGetSetReport
  ... truncated ...
```
