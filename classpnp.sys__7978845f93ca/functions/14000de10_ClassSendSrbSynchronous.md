# ClassSendSrbSynchronous

- ea: `0x14000de10`
- end: `0x14000eed5`
- name: `ClassSendSrbSynchronous`
- size: `4293`
- prototype: `NTSTATUS __stdcall(PDEVICE_OBJECT DeviceObject, PSCSI_REQUEST_BLOCK Srb, PVOID BufferAddress, ULONG BufferLength, BOOLEAN WriteToDevice)`
- caller_count: `27`
- callee_count: `15`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x14000c094`
- `0x14000c524`
- `0x14000cf50`
- `0x14000d3e0`
- `0x14001522c`
- `0x140017010`
- `0x1400173a0`
- `0x1400196ec`
- `0x1400239bc`
- `0x140024550`
- `0x140024c58`
- `0x14002b008`
- `0x14002ccdc`
- `0x14002cf20`
- `0x14002e3f0`
- `0x14002e99c`
- `0x14002ec78`
- `0x14002ee64`
- `0x14002f0dc`
- `0x14002fdd8`
- `0x140030604`
- `0x140031d6c`
- `0x1400320dc`
- `0x140032444`
- `0x140036640`
- `0x14005d5d0`
- `0x14005e53c`

## callees

- `0x1400073d4`
- `0x140008360`
- `0x14000de10`
- `0x140015120`
- `0x14001f450`
- `0x14001fbf4`
- `0x14001feac`
- `0x140020070`
- `0x140027b2c`
- `0x140038784`
- `0x140038b84`
- `0x140039044`
- `0x140039818`
- `0x140039aa0`
- `0x14003e430`

## import_xrefs

- `ntoskrnl!IoFreeIrp` at `0x14000e622`
- `ntoskrnl!IoFreeIrp` at `0x14000eb55`
- `ntoskrnl!IoFreeIrp` at `0x14000e622`
- `ntoskrnl!IoFreeIrp` at `0x14000eb55`
- `ntoskrnl!IoAllocateMdl` at `0x14000e472`
- `ntoskrnl!IoAllocateMdl` at `0x14000e472`
- `ntoskrnl!ExAllocatePool2` at `0x14000df12`
- `ntoskrnl!ExAllocatePool2` at `0x14000df12`
- `ntoskrnl!IoFreeMdl` at `0x14000e613`
- `ntoskrnl!IoFreeMdl` at `0x14000e613`
- `ntoskrnl!IoAllocateIrp` at `0x14000e0cc`
- `ntoskrnl!IoAllocateIrp` at `0x14000e0cc`
- `ntoskrnl!IofCallDriver` at `0x14000e175`
- `ntoskrnl!IofCallDriver` at `0x14000e175`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000e210`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000e6d4`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000ecb4`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000ed31`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000e210`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000e6d4`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000ecb4`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000ed31`
- `ntoskrnl!KeInitializeEvent` at `0x14000e0b3`
- `ntoskrnl!KeInitializeEvent` at `0x14000e0b3`
- `ntoskrnl!KeWaitForSingleObject` at `0x14000e1a1`
- `ntoskrnl!KeWaitForSingleObject` at `0x14000e1a1`
- `ntoskrnl!KeDelayExecutionThread` at `0x14000eeb0`
- `ntoskrnl!KeDelayExecutionThread` at `0x14000eeb0`
- `ntoskrnl!MmProbeAndLockPages` at `0x14000e4ac`
- `ntoskrnl!MmProbeAndLockPages` at `0x14000e4ac`
- `ntoskrnl!IoGetActivityIdThread` at `0x14003f96e`
- `ntoskrnl!IoGetActivityIdThread` at `0x14003f96e`

## pseudocode

```c
NTSTATUS __stdcall ClassSendSrbSynchronous(
        PDEVICE_OBJECT DeviceObject,
        PSCSI_REQUEST_BLOCK Srb,
        PVOID BufferAddress,
        ULONG BufferLength,
        BOOLEAN WriteToDevice)
{
  PVOID v5; // r15
  struct _FUNCTIONAL_DEVICE_EXTENSION *DeviceExtension; // r12
  _CLASS_PRIVATE_FDO_DATA *PrivateFdoData; // r13
  unsigned __int8 *Cdb; // rdi
  unsigned int SrbExtension; // r10d
  __int64 v11; // r9
  char v12; // r11
  __int64 v13; // rcx
  unsigned __int64 DataTransferLength; // rdx
  __int64 v15; // r8
  int v16; // ecx
  unsigned __int8 *Pool2; // rax
  unsigned __int8 *v18; // r14
  char v19; // r10
  __int64 v20; // r8
  __int64 v21; // rcx
  unsigned __int64 v22; // rdx
  int v23; // r11d
  char v24; // r9
  __int64 v25; // r10
  __int64 v26; // rcx
  unsigned __int64 v27; // rdx
  __int64 v28; // r8
  int v29; // ecx
  bool v30; // zf
  __int64 v31; // rsi
  __int64 v32; // rax
  int v33; // edx
  int v34; // r8d
  int v35; // r9d
  int v36; // edx
  unsigned int SrbFlags; // ecx
  unsigned __int8 Function; // al
  PIRP v39; // rax
  IRP *v40; // rdi
  _IO_STACK_LOCATION *CurrentStackLocation; // rax
  _IO_STACK_LOCATION *v42; // rax
  bool v43; // zf
  bool v44; // zf
  __int64 v45; // r9
  unsigned __int8 v46; // cl
  int v47; // eax
  char v48; // dl
  unsigned int v49; // r10d
  __int64 v50; // rcx
  unsigned __int64 v51; // r8
  __int64 v52; // r9
  int v53; // ecx
  char v54; // r9
  unsigned int v55; // r8d
  __int64 v56; // rcx
  unsigned __int64 v57; // rdx
  int v58; // r11d
  char v60; // r11
  unsigned int v61; // r10d
  __int64 v62; // rcx
  unsigned __int64 v63; // rdx
  int v64; // r8d
  int v65; // ecx
  struct _MDL *Mdl; // rcx
  __int64 v67; // rax
  int v68; // ecx
  int v69; // ecx
  int v70; // r11d
  int v71; // r11d
  int v72; // r8d
  int v73; // r13d
  __int64 v74; // r8
  char v75; // dl
  unsigned int v76; // eax
  int v77; // ecx
  int v78; // eax
  char v79; // al
  _SENSE_DATA *SenseInfoBuffer; // rdx
  unsigned int v81; // esi
  unsigned int v82; // r11d
  char v83; // r10
  __int64 v84; // rcx
  unsigned __int64 v85; // r8
  char *v86; // rdi
  int v87; // r9d
  int v88; // r9d
  int v89; // ecx
  char v90; // dl
  unsigned int v91; // r8d
  char v92; // dl
  unsigned int v93; // r8d
  __int64 v94; // rcx
  unsigned __int64 v95; // r9
  __int64 v96; // r10
  int v97; // ecx
  int v98; // ecx
  PDEVICE_OBJECT v99; // rcx
  __int64 v100; // rdx
  int v101; // ecx
  char v102; // dl
  unsigned int v103; // r8d
  char v104; // dl
  unsigned int v105; // r8d
  __int64 v106; // rcx
  unsigned __int64 v107; // r9
  __int64 v108; // r10
  int v109; // ecx
  int v110; // ecx
  int v111; // ecx
  char v112; // r11
  unsigned __int8 SenseInfoBufferLength; // r9
  unsigned __int8 *v114; // rcx
  unsigned __int8 *v115; // rax
  unsigned int v116; // eax
  unsigned int QosTimeoutValueInSeconds; // eax
  __int64 v118; // rcx
  unsigned __int64 v119; // r9
  __int64 v120; // r10
  int v121; // ecx
  __int64 v122; // rcx
  unsigned __int64 v123; // r9
  __int64 v124; // r10
  int v125; // ecx
  unsigned int v126; // esi
  __int64 v127; // rdi
  __int64 v128; // rcx
  unsigned __int64 v129; // rdx
  __int64 v130; // r10
  int v131; // ecx
  __int64 v132; // rax
  char SrbStatus; // r12
  _DEVICE_OBJECT *AttachedDevice; // r13
  __int64 AdditionalSenseCodeQualifierStr; // r15
  __int64 AdditionalSenseCodeStr; // r14
  __int64 SenseCodeStr; // rdi
  __int64 SrbStatusStr; // rsi
  __int64 ScsiOpStr; // rax
  int v140; // edx
  int v141; // r8d
  __int64 ActivityIdThread; // rax
  _CLASS_PRIVATE_FDO_DATA **v143; // rcx
  NTSTATUS v144; // [rsp+60h] [rbp-C8h] BYREF
  ULONG Length; // [rsp+64h] [rbp-C4h]
  int QosMaxNumberOfTimeoutRetries; // [rsp+68h] [rbp-C0h]
  PIRP Irp; // [rsp+70h] [rbp-B8h] BYREF
  int v148; // [rsp+78h] [rbp-B0h]
  int v149; // [rsp+7Ch] [rbp-ACh]
  int v150; // [rsp+80h] [rbp-A8h]
  int v151; // [rsp+84h] [rbp-A4h]
  PVOID P; // [rsp+88h] [rbp-A0h]
  PDEVICE_OBJECT v153; // [rsp+90h] [rbp-98h]
  PSCSI_REQUEST_BLOCK v154; // [rsp+98h] [rbp-90h]
  PVOID v155; // [rsp+A0h] [rbp-88h]
  struct _FUNCTIONAL_DEVICE_EXTENSION *v156; // [rsp+A8h] [rbp-80h]
  __int128 v157; // [rsp+B0h] [rbp-78h] BYREF
  struct _KEVENT Event; // [rsp+C0h] [rbp-68h] BYREF
  _CLASS_PRIVATE_FDO_DATA *v159; // [rsp+D8h] [rbp-50h] BYREF
  int v160; // [rsp+E0h] [rbp-48h]
  int v161; // [rsp+E4h] [rbp-44h]

  Length = BufferLength;
  v5 = BufferAddress;
  v155 = BufferAddress;
  v153 = DeviceObject;
  DeviceExtension = (struct _FUNCTIONAL_DEVICE_EXTENSION *)DeviceObject->DeviceExtension;
  v156 = DeviceExtension;
  PrivateFdoData = DeviceExtension->PrivateFdoData;
  v159 = PrivateFdoData;
  v157 = 0;
  memset(&Event, 0, sizeof(Event));
  v144 = 0;
  QosMaxNumberOfTimeoutRetries = 4;
  if ( Srb->Function == 40 )
  {
    Cdb = 0;
    if ( !Srb->TimeOutValue )
    {
      SrbExtension = (unsigned int)Srb->SrbExtension;
      if ( SrbExtension )
      {
        v11 = 0;
        v12 = 0;
        while ( 1 )
        {
          v13 = *((unsigned int *)&Srb[1].SenseInfoBuffer + v11);
          if ( (unsigned int)v13 >= 0x80 )
          {
            DataTransferLength = Srb->DataTransferLength;
            if ( (unsigned int)v13 < (unsigned int)DataTransferLength )
              break;
          }
LABEL_120:
          v11 = (unsigned int)(v11 + 1);
          if ( (unsigned int)v11 >= SrbExtension )
            goto LABEL_10;
        }
        v15 = (unsigned int)v13;
        v16 = *(_DWORD *)((char *)&Srb->Length + v13);
        if ( v16 == 64 )
        {
          if ( v15 + 40 <= DataTransferLength )
          {
            v12 = 1;
            if ( *(&Srb->CdbLength + v15) )
LABEL_123:
              Cdb = (unsigned __int8 *)&Srb->DataBuffer + v15;
          }
        }
        else
        {
          v65 = v16 - 65;
          if ( v65 )
          {
            if ( v65 == 1 && v15 + 40 <= DataTransferLength )
            {
              v12 = 1;
              if ( *(unsigned int *)((char *)&Srb->SrbFlags + v15) )
                Cdb = (unsigned __int8 *)&Srb->SenseInfoBuffer + v15;
            }
          }
          else if ( v15 + 56 <= DataTransferLength )
          {
            v12 = 1;
            if ( *(&Srb->CdbLength + v15) )
              goto LABEL_123;
          }
        }
        if ( v12 )
          goto LABEL_10;
        goto LABEL_120;
      }
    }
  }
  else
  {
    Srb->Length = 88;
    Srb->Function = 0;
    Cdb = Srb->Cdb;
  }
LABEL_10:
  if ( PrivateFdoData->QOSModeEnabled && Cdb && (unsigned __int8)ClasspQosSupportedCommand(*Cdb) )
  {
    if ( (PrivateFdoData->FdoDataFlags.AsUlong & 0x20) != 0 )
    {
      QosTimeoutValueInSeconds = PrivateFdoData->QosTimeoutValueInSeconds;
      if ( Srb->Function == 40 )
        LODWORD(Srb->NextSrb) = QosTimeoutValueInSeconds;
      else
        Srb->TimeOutValue = QosTimeoutValueInSeconds;
    }
    QosMaxNumberOfTimeoutRetries = PrivateFdoData->QosMaxNumberOfTimeoutRetries;
  }
  Pool2 = (unsigned __int8 *)ExAllocatePool2(72, 18, 927163219);
  v18 = Pool2;
  P = Pool2;
  if ( !Pool2 )
  {
    v99 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      v100 = 71;
LABEL_332:
      WPP_SF_(v99->AttachedDevice, v100, WPP_9ee7907f5c473329e20561a6f3486187_Traceguids);
    }
    return -1073741670;
  }
  v154 = Srb;
  v148 = 4;
  if ( Srb->Function == 40 )
  {
    if ( !Srb->TimeOutValue )
    {
      v19 = 0;
      v20 = 0;
      if ( LODWORD(Srb->SrbExtension) )
      {
        while ( 1 )
        {
          v21 = *((unsigned int *)&Srb[1].SenseInfoBuffer + v20);
          if ( (unsigned int)v21 >= 0x80 )
          {
            v22 = Srb->DataTransferLength;
            if ( (unsigned int)v21 < (unsigned int)v22 )
              break;
          }
LABEL_21:
          v20 = (unsigned int)(v20 + 1);
          if ( (unsigned int)v20 >= LODWORD(Srb->SrbExtension) )
            goto LABEL_24;
        }
        v23 = *(_DWORD *)((char *)&Srb->Length + v21);
        if ( v23 == 64 )
        {
LABEL_18:
          if ( v21 + 40 > v22 )
            goto LABEL_20;
          goto LABEL_19;
        }
        v70 = v23 - 65;
        if ( v70 )
        {
          if ( v70 == 1 )
            goto LABEL_18;
        }
        else if ( v21 + 56 <= v22 )
        {
LABEL_19:
          v19 = 1;
          *(&Srb->QueueAction + v21) = 18;
        }
LABEL_20:
        if ( v19 )
          goto LABEL_24;
        goto LABEL_21;
      }
    }
  }
  else
  {
    Srb->SenseInfoBufferLength = 18;
  }
LABEL_24:
  if ( Srb->Function == 40 )
  {
    if ( !Srb->TimeOutValue )
    {
      v24 = 0;
      v25 = 0;
      if ( LODWORD(Srb->SrbExtension) )
      {
        while ( 1 )
        {
          v26 = *((unsigned int *)&Srb[1].SenseInfoBuffer + v25);
          if ( (unsigned int)v26 >= 0x80 )
          {
            v27 = Srb->DataTransferLength;
            if ( (unsigned int)v26 < (unsigned int)v27 )
              break;
          }
LABEL_34:
          v25 = (unsigned int)(v25 + 1);
          if ( (unsigned int)v25 >= LODWORD(Srb->SrbExtension) )
            goto LABEL_37;
        }
        v28 = (unsigned int)v26;
        v29 = *(_DWORD *)((char *)&Srb->Length + v26);
        if ( v29 == 64 )
        {
          if ( v28 + 40 > v27 )
            goto LABEL_33;
          goto LABEL_31;
        }
        v68 = v29 - 65;
        if ( v68 )
        {
          if ( v68 == 1 && v28 + 40 <= v27 )
          {
            *(void **)((char *)&Srb->DataBuffer + v28) = Pool2;
            goto LABEL_32;
          }
        }
        else if ( v28 + 56 <= v27 )
        {
LABEL_31:
          *(_QWORD *)((char *)&Srb->DataTransferLength + v28) = Pool2;
LABEL_32:
          v24 = 1;
        }
LABEL_33:
        if ( v24 )
          goto LABEL_37;
        goto LABEL_34;
      }
    }
  }
  else
  {
    Srb->SenseInfoBuffer = Pool2;
  }
LABEL_37:
  v30 = Srb->Function == 40;
  if ( Srb->Function == 40 )
    *(_QWORD *)&Srb->InternalStatus = v5;
  else
    Srb->DataBuffer = v5;
  v31 = 24;
  v32 = 24;
  if ( !v30 )
    v32 = 12;
  v33 = *(_DWORD *)((char *)&Srb->Length + v32);
  v34 = v33 & 0x8000;
  v150 = v34;
  v35 = v33 & 0x1000;
  v151 = v35;
  v36 = v33 & 0xC0;
  v149 = v36;
  while ( 1 )
  {
    SrbFlags = DeviceExtension->SrbFlags;
    Function = Srb->Function;
    if ( Function == 40 )
      LODWORD(Srb->DataBuffer) = SrbFlags;
    else
      Srb->SrbFlags = SrbFlags;
    if ( v5 )
    {
      if ( WriteToDevice )
      {
        if ( Function == 40 )
          LODWORD(Srb->DataBuffer) |= 0x80u;
        else
          Srb->SrbFlags |= 0x80u;
      }
      else if ( Function == 40 )
      {
        LODWORD(Srb->DataBuffer) |= 0x40u;
      }
      else
      {
        Srb->SrbFlags |= 0x40u;
      }
      if ( Function == 40 )
        LODWORD(Srb->DataBuffer) |= v36;
      else
        Srb->SrbFlags |= v36;
    }
    if ( v34 )
    {
      if ( Function == 40 )
        LODWORD(Srb->DataBuffer) |= 0x8000u;
      else
        Srb->SrbFlags |= 0x8000u;
    }
    if ( v35 )
    {
      if ( Function == 40 )
        LODWORD(Srb->DataBuffer) |= 0x1000u;
      else
        Srb->SrbFlags |= 0x1000u;
    }
    if ( Function == 40 )
      HIWORD(Srb->SenseInfoBuffer) = 32;
    else
      Srb->QueueAction = 32;
    if ( Function == 40 )
      LODWORD(Srb->DataBuffer) |= 0x108u;
    else
      Srb->SrbFlags |= 0x108u;
    KeInitializeEvent(&Event, NotificationEvent, 0);
    v39 = IoAllocateIrp(DeviceExtension->CommonExtension.LowerDeviceObject->StackSize + 1, 0);
    v40 = v39;
    Irp = v39;
    if ( !v39 )
    {
      ExFreePoolWithTag(v18, 0);
      if ( Srb->Function == 40 )
      {
        if ( !Srb->TimeOutValue )
        {
          v90 = 0;
          v91 = 0;
          if ( LODWORD(Srb->SrbExtension) )
          {
            while ( 1 )
            {
              v118 = *((unsigned int *)&Srb[1].SenseInfoBuffer + v91);
              if ( (unsigned int)v118 >= 0x80 )
              {
                v119 = Srb->DataTransferLength;
                if ( (unsigned int)v118 < (unsigned int)v119 )
                  break;
              }
LABEL_207:
              if ( ++v91 >= LODWORD(Srb->SrbExtension) )
                goto LABEL_210;
            }
            v120 = (unsigned int)v118;
            v121 = *(_DWORD *)((char *)&Srb->Length + v118);
            if ( v121 == 64 )
            {
              if ( v120 + 40 <= v119 )
                goto LABEL_297;
            }
            else
            {
              v89 = v121 - 65;
              if ( v89 )
              {
                if ( v89 == 1 && v120 + 40 <= v119 )
                {
                  *(void **)((char *)&Srb->DataBuffer + v120) = 0;
LABEL_204:
                  v90 = 1;
                }
              }
              else if ( v120 + 56 <= v119 )
              {
LABEL_297:
                *(_QWORD *)((char *)&Srb->DataTransferLength + v120) = 0;
                goto LABEL_204;
              }
            }
            if ( v90 )
              goto LABEL_210;
            goto LABEL_207;
          }
        }
      }
      else
      {
        Srb->SenseInfoBuffer = 0;
      }
LABEL_210:
      if ( Srb->Function == 40 )
      {
        if ( !Srb->TimeOutValue )
        {
          v92 = 0;
          v93 = 0;
          if ( LODWORD(Srb->SrbExtension) )
          {
            while ( 1 )
            {
              v94 = *((unsigned int *)&Srb[1].SenseInfoBuffer + v93);
              if ( (unsigned int)v94 >= 0x80 )
              {
                v95 = Srb->DataTransferLength;
                if ( (unsigned int)v94 < (unsigned int)v95 )
                  break;
              }
LABEL_221:
              if ( ++v93 >= LODWORD(Srb->SrbExtension) )
                goto LABEL_222;
            }
            v96 = (unsigned int)v94;
            v97 = *(_DWORD *)((char *)&Srb->Length + v94);
            if ( v97 == 64 )
            {
              if ( v96 + 40 > v95 )
                goto LABEL_220;
            }
            else
            {
              v98 = v97 - 65;
              if ( v98 )
              {
                if ( v98 == 1 && v96 + 40 <= v95 )
                  goto LABEL_219;
LABEL_220:
                if ( v92 )
                  goto LABEL_222;
                goto LABEL_221;
              }
              if ( v96 + 56 > v95 )
                goto LABEL_220;
            }
LABEL_219:
            v92 = 1;
            *(&Srb->QueueAction + v96) = 0;
            goto LABEL_220;
          }
        }
      }
      else
      {
        Srb->SenseInfoBufferLength = 0;
      }
LABEL_222:
      v99 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        v100 = 72;
        goto LABEL_332;
      }
      return -1073741670;
    }
    CurrentStackLocation = v39->Tail.Overlay.CurrentStackLocation;
    CurrentStackLocation[-1].MajorFunction = 15;
    CurrentStackLocation[-1].Parameters.WMI.ProviderId = (unsigned __int64)Srb;
    v42 = v40->Tail.Overlay.CurrentStackLocation;
    v42[-1].CompletionRoutine = (int (__fastcall *)(_DEVICE_OBJECT *, _IRP *, void *))&ClasspSendSynchronousCompletion;
    v42[-1].Context = Srb;
    v42[-1].Control = -32;
    v40->UserIosb = (_IO_STATUS_BLOCK *)&v157;
    v40->UserEvent = &Event;
    if ( !v5 )
      goto LABEL_53;
    Mdl = IoAllocateMdl(v5, Length, 0, 0, v40);
    v40->MdlAddress = Mdl;
    if ( !Mdl )
    {
      ExFreePoolWithTag(v18, 0);
      if ( Srb->Function == 40 )
      {
        if ( !Srb->TimeOutValue )
        {
          v102 = 0;
          v103 = 0;
          if ( LODWORD(Srb->SrbExtension) )
          {
            while ( 1 )
            {
              v122 = *((unsigned int *)&Srb[1].SenseInfoBuffer + v103);
              if ( (unsigned int)v122 >= 0x80 )
              {
                v123 = Srb->DataTransferLength;
                if ( (unsigned int)v122 < (unsigned int)v123 )
                  break;
              }
LABEL_238:
              if ( ++v103 >= LODWORD(Srb->SrbExtension) )
                goto LABEL_241;
            }
            v124 = (unsigned int)v122;
            v125 = *(_DWORD *)((char *)&Srb->Length + v122);
            if ( v125 == 64 )
            {
              if ( v124 + 40 <= v123 )
              {
LABEL_305:
                *(_QWORD *)((char *)&Srb->DataTransferLength + v124) = 0;
LABEL_235:
                v102 = 1;
              }
            }
            else
            {
              v101 = v125 - 65;
              if ( v101 )
              {
                if ( v101 == 1 && v124 + 40 <= v123 )
                {
                  *(void **)((char *)&Srb->DataBuffer + v124) = 0;
                  goto LABEL_235;
                }
              }
              else if ( v124 + 56 <= v123 )
              {
                goto LABEL_305;
              }
            }
            if ( v102 )
              goto LABEL_241;
            goto LABEL_238;
          }
        }
      }
      else
      {
        Srb->SenseInfoBuffer = 0;
      }
LABEL_241:
      if ( Srb->Function == 40 )
      {
        if ( !Srb->TimeOutValue )
        {
          v104 = 0;
          v105 = 0;
          if ( LODWORD(Srb->SrbExtension) )
          {
            while ( 1 )
            {
              v106 = *((unsigned int *)&Srb[1].SenseInfoBuffer + v105);
              if ( (unsigned int)v106 >= 0x80 )
              {
                v107 = Srb->DataTransferLength;
                if ( (unsigned int)v106 < (unsigned int)v107 )
                  break;
              }
LABEL_252:
              if ( ++v105 >= LODWORD(Srb->SrbExtension) )
                goto LABEL_253;
            }
            v108 = (unsigned int)v106;
            v109 = *(_DWORD *)((char *)&Srb->Length + v106);
            if ( v109 == 64 )
            {
              if ( v108 + 40 <= v107 )
                goto LABEL_250;
            }
            else
            {
              v110 = v109 - 65;
              if ( v110 )
              {
                if ( v110 == 1 && v108 + 40 <= v107 )
                {
LABEL_250:
                  v104 = 1;
                  *(&Srb->QueueAction + v108) = 0;
                }
              }
              else if ( v108 + 56 <= v107 )
              {
                goto LABEL_250;
              }
            }
            if ( v104 )
              goto LABEL_253;
            goto LABEL_252;
          }
        }
      }
      else
      {
        Srb->SenseInfoBufferLength = 0;
      }
LABEL_253:
      IoFreeIrp(v40);
      v99 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        v100 = 73;
        goto LABEL_332;
      }
      return -1073741670;
    }
    v67 = 24;
    if ( Srb->Function != 40 )
      v67 = 12;
    MmProbeAndLockPages(Mdl, 0, (LOCK_OPERATION)((*(_DWORD *)((char *)&Srb->Length + v67) >> 6) & 1));
LABEL_53:
    v43 = Srb->Function == 40;
    if ( Srb->Function == 40 )
      HIDWORD(Srb->SrbExtension) = Length;
    else
      Srb->DataTransferLength = Length;
    if ( v43 )
    {
      if ( Srb->TimeOutValue )
        goto LABEL_57;
      v60 = 0;
      v61 = 0;
      if ( !LODWORD(Srb->SrbExtension) )
        goto LABEL_57;
      while ( 1 )
      {
        v62 = *((unsigned int *)&Srb[1].SenseInfoBuffer + v61);
        if ( (unsigned int)v62 >= 0x80 )
        {
          v63 = Srb->DataTransferLength;
          if ( (unsigned int)v62 < (unsigned int)v63 )
            break;
        }
LABEL_105:
        if ( ++v61 >= LODWORD(Srb->SrbExtension) )
          goto LABEL_57;
      }
      v64 = *(_DWORD *)((char *)&Srb->Length + v62);
      if ( v64 == 64 )
      {
LABEL_102:
        if ( v62 + 40 > v63 )
          goto LABEL_104;
        goto LABEL_103;
      }
      v72 = v64 - 65;
      if ( v72 )
      {
        if ( v72 == 1 )
          goto LABEL_102;
      }
      else if ( v62 + 56 <= v63 )
      {
LABEL_103:
        v60 = 1;
        *(&Srb->QueueTag + v62) = 0;
      }
LABEL_104:
      if ( v60 )
        goto LABEL_57;
      goto LABEL_105;
    }
    Srb->ScsiStatus = 0;
LABEL_57:
    Srb->SrbStatus = 0;
    v44 = Srb->Function == 40;
    if ( Srb->Function == 40 )
      Srb[1].DataBuffer = 0;
    else
      Srb->NextSrb = 0;
    if ( v44 )
      *(_QWORD *)&Srb->Cdb[8] = v40;
    else
      Srb->OriginalRequest = v40;
    v144 = IofCallDriver(DeviceExtension->CommonExtension.LowerDeviceObject, v40);
    if ( v144 == 259 )
    {
      KeWaitForSingleObject(&Event, Executive, 0, 0, 0);
      v144 = v157;
    }
    if ( Srb->Function == 40 )
      *(_QWORD *)&Srb->Cdb[8] = 0;
    else
      Srb->OriginalRequest = 0;
    if ( (Srb->SrbStatus & 0x3F) == 1 )
    {
      v159->LoggedTURFailureSinceLastIO = 0;
      v144 = 0;
      goto LABEL_67;
    }
    Irp = 0;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      SrbStatus = Srb->SrbStatus;
      AttachedDevice = WPP_GLOBAL_Control->AttachedDevice;
      AdditionalSenseCodeQualifierStr = DbgGetAdditionalSenseCodeQualifierStr(Srb);
      AdditionalSenseCodeStr = DbgGetAdditionalSenseCodeStr(Srb);
      SenseCodeStr = DbgGetSenseCodeStr(Srb);
      SrbStatusStr = DbgGetSrbStatusStr(Srb);
      ScsiOpStr = DbgGetScsiOpStr();
      WPP_SF_qssDDsss(
        (_DWORD)AttachedDevice,
        v140,
        v141,
        (_DWORD)Srb,
        ScsiOpStr,
        SrbStatusStr,
        SrbStatus,
        v144,
        SenseCodeStr,
        AdditionalSenseCodeStr,
        AdditionalSenseCodeQualifierStr);
      v18 = (unsigned __int8 *)P;
      v31 = 24;
      v5 = v155;
      DeviceExtension = v156;
    }
    v73 = v148;
    LOBYTE(v45) = 15;
    if ( !(unsigned __int8)InterpretSenseInfoWithoutHistory(v153, 0, Srb, v45, 0, 4 - v148, &v144, &Irp) )
      break;
    v75 = 0;
    LOBYTE(v74) = 0;
    if ( v144 != -1073741661 )
      goto LABEL_171;
    SenseInfoBufferLength = 0;
    if ( Srb->Function == 40 )
    {
      if ( !Srb->TimeOutValue )
      {
        v126 = (unsigned int)Srb->SrbExtension;
        if ( v126 )
        {
          v127 = 0;
          v112 = 0;
          while ( 1 )
          {
            v128 = *((unsigned int *)&Srb[1].SenseInfoBuffer + v127);
            if ( (unsigned int)v128 >= 0x80 )
            {
              v129 = Srb->DataTransferLength;
              if ( (unsigned int)v128 < (unsigned int)v129 )
                break;
            }
LABEL_324:
            v127 = (unsigned int)(v127 + 1);
            if ( (unsigned int)v127 >= v126 )
              goto LABEL_267;
          }
          v130 = (unsigned int)v128;
          v131 = *(_DWORD *)((char *)&Srb->Length + v128);
          if ( v131 == 64 )
          {
            if ( v130 + 40 <= v129 )
              goto LABEL_265;
          }
          else
          {
            v111 = v131 - 65;
            if ( v111 )
            {
              if ( v111 == 1 && v130 + 40 <= v129 )
                goto LABEL_265;
            }
            else if ( v130 + 56 <= v129 )
            {
LABEL_265:
              v112 = 1;
              SenseInfoBufferLength = *(&Srb->QueueAction + v130);
            }
          }
          if ( v112 )
            goto LABEL_267;
          goto LABEL_324;
        }
LABEL_267:
        v31 = 24;
      }
    }
    else
    {
      SenseInfoBufferLength = Srb->SenseInfoBufferLength;
    }
    v75 = 0;
    if ( SenseInfoBufferLength )
    {
      v114 = &v18[SenseInfoBufferLength];
      v115 = v18 + 8;
      if ( (unsigned __int8)((*v18 & 0x7F) - 114) <= 1u )
      {
        if ( v115 > v114 )
          goto LABEL_171;
        v74 = v18[2];
        goto LABEL_272;
      }
      if ( v115 <= v114 )
      {
        v116 = SenseInfoBufferLength;
        if ( (unsigned int)v18[7] + 8 <= SenseInfoBufferLength )
          v116 = v18[7] + 8;
        if ( v18 + 13 > &v18[v116] )
        {
LABEL_272:
          v75 = 1;
          goto LABEL_171;
        }
        v74 = v18[12];
        v75 = 1;
      }
    }
LABEL_171:
    if ( v75 && (_BYTE)v74 == 4 || (Srb->SrbStatus & 0x3F) == 0xA )
    {
      v132 = (__int64)Irp;
      if ( (__int64)Irp < 20000000 )
        v132 = 20000000;
      Irp = (PIRP)-v132;
      KeDelayExecutionThread(0, 0, (PLARGE_INTEGER)&Irp);
    }
    v76 = Srb->SrbStatus;
    if ( (unsigned __int8)v76 <= 0xEu )
    {
      v77 = 18948;
      if ( _bittest(&v77, v76) )
      {
        if ( QosMaxNumberOfTimeoutRetries )
          --QosMaxNumberOfTimeoutRetries;
        else
          v73 = 0;
      }
    }
    v78 = v73--;
    v148 = v73;
    if ( !v78 )
      break;
    v79 = PORT_ALLOCATED_SENSE_EX(DeviceExtension, Srb, v74);
    v36 = v149;
    v34 = v150;
    v35 = v151;
    if ( v79 )
    {
      FREE_PORT_ALLOCATED_SENSE_BUFFER_EX(DeviceExtension);
      v36 = v149;
      v34 = v150;
      v35 = v151;
    }
  }
  if ( ClassPnPETWEnabled )
  {
    v159 = 0;
    v160 = 0;
    v161 = 0x1000000;
    ActivityIdThread = IoGetActivityIdThread();
    v143 = &v159;
    if ( ActivityIdThread )
      LODWORD(v143) = ActivityIdThread;
    ClasspWriteSrbErrorResultEvent((_DWORD)v143, (_DWORD)v153, v157, (_DWORD)Srb, 4 - v73);
  }
LABEL_67:
  v46 = Srb->Function;
  if ( v46 != 40 )
    v31 = 12;
  v47 = *(_DWORD *)((char *)&Srb->Length + v31);
  if ( (v47 & 0x200000) == 0 || (v47 & 0x400) == 0 )
    goto LABEL_71;
  SenseInfoBuffer = 0;
  if ( v46 == 40 )
  {
    if ( !Srb->TimeOutValue )
    {
      v81 = (unsigned int)Srb->SrbExtension;
      if ( v81 )
      {
        v82 = 0;
        v83 = 0;
        while ( 1 )
        {
          v84 = *((unsigned int *)&Srb[1].SenseInfoBuffer + v82);
          if ( (unsigned int)v84 >= 0x80 )
          {
            v85 = Srb->DataTransferLength;
            if ( (unsigned int)v84 < (unsigned int)v85 )
              break;
          }
LABEL_195:
          if ( ++v82 >= v81 )
            goto LABEL_187;
        }
        v86 = (char *)Srb + v84;
        v87 = *(_DWORD *)((char *)&Srb->Length + v84);
        if ( v87 == 64 )
        {
          if ( v84 + 40 > v85 )
            goto LABEL_186;
          goto LABEL_198;
        }
        v88 = v87 - 65;
        if ( v88 )
        {
          if ( v88 == 1 && v84 + 40 <= v85 )
          {
            SenseInfoBuffer = (_SENSE_DATA *)*((_QWORD *)v86 + 3);
LABEL_194:
            v83 = 1;
          }
        }
        else if ( v84 + 56 <= v85 )
        {
LABEL_198:
          SenseInfoBuffer = (_SENSE_DATA *)*((_QWORD *)v86 + 2);
          goto LABEL_194;
        }
LABEL_186:
        if ( v83 )
          goto LABEL_187;
        goto LABEL_195;
      }
    }
  }
  else
  {
    SenseInfoBuffer = (_SENSE_DATA *)Srb->SenseInfoBuffer;
  }
LABEL_187:
  if ( SenseInfoBuffer != DeviceExtension->SenseData )
    FREE_PORT_ALLOCATED_SENSE_BUFFER_EX(DeviceExtension);
LABEL_71:
  ExFreePoolWithTag(v18, 0);
  if ( Srb->Function == 40 )
  {
    if ( !Srb->TimeOutValue )
    {
      v48 = 0;
      v49 = 0;
      if ( LODWORD(Srb->SrbExtension) )
      {
        while ( 1 )
        {
          v50 = *((unsigned int *)&Srb[1].SenseInfoBuffer + v49);
          if ( (unsigned int)v50 >= 0x80 )
          {
            v51 = Srb->DataTransferLength;
            if ( (unsigned int)v50 < (unsigned int)v51 )
              break;
          }
LABEL_81:
          if ( ++v49 >= LODWORD(Srb->SrbExtension) )
            goto LABEL_84;
        }
        v52 = (unsigned int)v50;
        v53 = *(_DWORD *)((char *)&Srb->Length + v50);
        if ( v53 == 64 )
        {
          if ( v52 + 40 > v51 )
            goto LABEL_80;
          goto LABEL_78;
        }
        v69 = v53 - 65;
        if ( v69 )
        {
          if ( v69 == 1 && v52 + 40 <= v51 )
          {
            *(void **)((char *)&Srb->DataBuffer + v52) = 0;
            goto LABEL_79;
          }
        }
        else if ( v52 + 56 <= v51 )
        {
LABEL_78:
          *(_QWORD *)((char *)&Srb->DataTransferLength + v52) = 0;
LABEL_79:
          v48 = 1;
        }
LABEL_80:
        if ( v48 )
          goto LABEL_84;
        goto LABEL_81;
      }
    }
  }
  else
  {
    Srb->SenseInfoBuffer = 0;
  }
LABEL_84:
  if ( Srb->Function == 40 )
  {
    if ( !Srb->TimeOutValue )
    {
      v54 = 0;
      v55 = 0;
      if ( LODWORD(Srb->SrbExtension) )
      {
        while ( 1 )
        {
          v56 = *((unsigned int *)&Srb[1].SenseInfoBuffer + v55);
          if ( (unsigned int)v56 >= 0x80 )
          {
            v57 = Srb->DataTransferLength;
            if ( (unsigned int)v56 < (unsigned int)v57 )
              break;
          }
LABEL_93:
          if ( ++v55 >= LODWORD(Srb->SrbExtension) )
            return v144;
        }
        v58 = *(_DWORD *)((char *)&Srb->Length + v56);
        if ( v58 == 64 )
        {
LABEL_90:
          if ( v56 + 40 > v57 )
            goto LABEL_92;
          goto LABEL_91;
        }
        v71 = v58 - 65;
        if ( v71 )
        {
          if ( v71 == 1 )
            goto LABEL_90;
        }
        else if ( v56 + 56 <= v57 )
        {
LABEL_91:
          v54 = 1;
          *(&Srb->QueueAction + v56) = 0;
        }
LABEL_92:
        if ( v54 )
          return v144;
        goto LABEL_93;
      }
    }
  }
  else
  {
    Srb->SenseInfoBufferLength = 0;
  }
  return v144;
}

```

## disassembly

```asm
0x14000de10  mov     r11, rsp
0x14000de13  push    rbx
0x14000de14  push    rsi
0x14000de15  push    rdi
0x14000de16  push    r12
0x14000de18  push    r13
0x14000de1a  push    r14
0x14000de1c  push    r15
0x14000de1e  sub     rsp, 0F0h
0x14000de25  mov     rax, cs:__security_cookie
0x14000de2c  xor     rax, rsp
0x14000de2f  mov     [rsp+128h+var_40], rax
0x14000de37  mov     [rsp+128h+Length], r9d
0x14000de3c  mov     r15, r8
0x14000de3f  mov     [rsp+128h+var_88], r8
0x14000de47  mov     rbx, rdx
0x14000de4a  mov     [rsp+128h+var_98], rcx
0x14000de52  mov     r12, [rcx+40h]
0x14000de56  mov     [rsp+128h+var_80], r12
0x14000de5e  mov     r13, [r12+478h]
0x14000de66  mov     [rsp+128h+var_50], r13
0x14000de6e  xorps   xmm0, xmm0
0x14000de71  movups  xmmword ptr [r11-78h], xmm0
0x14000de76  xorps   xmm1, xmm1
0x14000de79  xor     eax, eax
0x14000de7b  movups  xmmword ptr [r11-68h], xmm1
0x14000de80  mov     [r11-58h], rax
0x14000de84  mov     [rsp+128h+var_C8], eax
0x14000de88  mov     esi, 4
0x14000de8d  mov     [rsp+128h+var_C0], esi
0x14000de91  movzx   eax, byte ptr [rdx+2]
0x14000de95  cmp     al, 28h ; '('
0x14000de97  jnz     loc_14000E99F
0x14000de9d  xor     edi, edi
0x14000de9f  cmp     [rdx+14h], edi
0x14000dea2  jnz     short loc_14000DEF4
0x14000dea4  mov     r10d, [rdx+38h]
0x14000dea8  test    r10d, r10d
0x14000deab  jz      short loc_14000DEF4
0x14000dead  xor     r9d, r9d
0x14000deb0  xor     r11b, r11b
0x14000deb3  mov     ecx, [rbx+r9*4+78h]
0x14000deb8  cmp     ecx, 80h
0x14000debe  jb      loc_14000E3F9
0x14000dec4  mov     edx, [rbx+10h]
0x14000dec7  cmp     ecx, edx
0x14000dec9  jnb     loc_14000E3F9
0x14000decf  mov     r8d, ecx
0x14000ded2  mov     ecx, [rcx+rbx]
0x14000ded5  cmp     ecx, 40h ; '@'
0x14000ded8  jnz     loc_14000E3BF
0x14000dede  lea     rcx, [r8+28h]
0x14000dee2  cmp     rcx, rdx
0x14000dee5  jbe     loc_14000E40A
0x14000deeb  test    r11b, r11b
0x14000deee  jz      loc_14000E3F9
0x14000def4  cmp     byte ptr [r13+0F4Bh], 0
0x14000defc  jnz     loc_14000EE12
0x14000df02  mov     edx, 12h
0x14000df07  mov     ecx, 48h ; 'H'
0x14000df0c  mov     r8d, 37436353h
0x14000df12  call    cs:__imp_ExAllocatePool2
0x14000df19  nop     dword ptr [rax+rax+00h]
0x14000df1e  mov     r14, rax
0x14000df21  mov     [rsp+128h+P], rax
0x14000df29  test    rax, rax
0x14000df2c  jz      loc_14000EE3F
0x14000df32  mov     [rsp+128h+var_90], rbx
0x14000df3a  mov     [rsp+128h+var_B0], esi
0x14000df3e  cmp     byte ptr [rbx+2], 28h ; '('
0x14000df42  jnz     short loc_14000DF9C
0x14000df44  cmp     dword ptr [rbx+14h], 0
0x14000df48  jnz     short loc_14000DFA0
0x14000df4a  xor     r10b, r10b
0x14000df4d  xor     r8d, r8d
0x14000df50  cmp     [rbx+38h], r8d
0x14000df54  jbe     short loc_14000DFA0
0x14000df56  mov     ecx, [rbx+r8*4+78h]
0x14000df5b  cmp     ecx, 80h
0x14000df61  jb      short loc_14000DF91
0x14000df63  mov     edx, [rbx+10h]
0x14000df66  cmp     ecx, edx
0x14000df68  jnb     short loc_14000DF91
0x14000df6a  lea     r9, [rcx+rbx]
0x14000df6e  mov     r11d, [r9]
0x14000df71  cmp     r11d, 40h ; '@'
0x14000df75  jnz     loc_14000E70E
0x14000df7b  add     rcx, 28h ; '('
0x14000df7f  cmp     rcx, rdx
0x14000df82  ja      short loc_14000DF8C
0x14000df84  mov     r10b, 1
0x14000df87  mov     byte ptr [r9+9], 12h
0x14000df8c  test    r10b, r10b
0x14000df8f  jnz     short loc_14000DFA0
0x14000df91  inc     r8d
0x14000df94  cmp     r8d, [rbx+38h]
0x14000df98  jnb     short loc_14000DFA0
0x14000df9a  jmp     short loc_14000DF56
0x14000df9c  mov     byte ptr [rbx+0Bh], 12h
0x14000dfa0  cmp     byte ptr [rbx+2], 28h ; '('
0x14000dfa4  jnz     short loc_14000DFFC
0x14000dfa6  cmp     dword ptr [rbx+14h], 0
0x14000dfaa  jnz     short loc_14000E000
0x14000dfac  xor     r9b, r9b
0x14000dfaf  xor     r10d, r10d
0x14000dfb2  cmp     [rbx+38h], r10d
0x14000dfb6  jbe     short loc_14000E000
0x14000dfb8  mov     ecx, [rbx+r10*4+78h]
0x14000dfbd  cmp     ecx, 80h
0x14000dfc3  jb      short loc_14000DFF1
0x14000dfc5  mov     edx, [rbx+10h]
0x14000dfc8  cmp     ecx, edx
0x14000dfca  jnb     short loc_14000DFF1
0x14000dfcc  mov     r8d, ecx
0x14000dfcf  mov     ecx, [rcx+rbx]
0x14000dfd2  cmp     ecx, 40h ; '@'
0x14000dfd5  jnz     loc_14000E671
0x14000dfdb  lea     rcx, [r8+28h]
0x14000dfdf  cmp     rcx, rdx
0x14000dfe2  ja      short loc_14000DFEC
0x14000dfe4  mov     [r8+rbx+10h], rax
0x14000dfe9  mov     r9b, 1
0x14000dfec  test    r9b, r9b
0x14000dfef  jnz     short loc_14000E000
0x14000dff1  inc     r10d
0x14000dff4  cmp     r10d, [rbx+38h]
0x14000dff8  jnb     short loc_14000E000
0x14000dffa  jmp     short loc_14000DFB8
0x14000dffc  mov     [rbx+20h], rax
0x14000e000  cmp     byte ptr [rbx+2], 28h ; '('
0x14000e004  jnz     loc_14000E394
0x14000e00a  mov     [rbx+40h], r15
0x14000e00e  mov     esi, 18h
0x14000e013  mov     eax, esi
0x14000e015  mov     edx, 0Ch
0x14000e01a  cmovnz  eax, edx
0x14000e01d  mov     edx, [rax+rbx]
0x14000e020  mov     r8d, edx
0x14000e023  and     r8d, 8000h
0x14000e02a  mov     [rsp+128h+var_A8], r8d
0x14000e032  mov     r9d, edx
0x14000e035  and     r9d, 1000h
0x14000e03c  mov     [rsp+128h+var_A4], r9d
0x14000e044  and     edx, 0C0h
0x14000e04a  mov     [rsp+128h+var_AC], edx
0x14000e04e  mov     r10d, 20h ; ' '
0x14000e054  lea     r13, WPP_GLOBAL_Control
0x14000e05b  mov     ecx, [r12+250h]
0x14000e063  movzx   eax, byte ptr [rbx+2]
0x14000e067  cmp     al, 28h ; '('
0x14000e069  jnz     loc_14000E3AF
0x14000e06f  mov     [rbx+18h], ecx
0x14000e072  test    r15, r15
0x14000e075  jnz     loc_14000E425
0x14000e07b  test    r8d, r8d
0x14000e07e  jnz     loc_14000EC77
0x14000e084  test    r9d, r9d
0x14000e087  jnz     loc_14000EC93
0x14000e08d  cmp     al, 28h ; '('
0x14000e08f  jz      loc_14000E37E
0x14000e095  mov     byte ptr [rbx+9], 20h ; ' '
0x14000e099  jnz     loc_14000E388
0x14000e09f  or      dword ptr [rbx+18h], 108h
0x14000e0a6  xor     r8d, r8d; State
0x14000e0a9  xor     edx, edx; Type
0x14000e0ab  lea     rcx, [rsp+128h+Event]; Event
0x14000e0b3  call    cs:__imp_KeInitializeEvent
0x14000e0ba  nop     dword ptr [rax+rax+00h]
0x14000e0bf  mov     rax, [r12+10h]
0x14000e0c4  movzx   ecx, byte ptr [rax+4Ch]
0x14000e0c8  inc     cl; StackSize
0x14000e0ca  xor     edx, edx; ChargeQuota
0x14000e0cc  call    cs:__imp_IoAllocateIrp
0x14000e0d3  nop     dword ptr [rax+rax+00h]
0x14000e0d8  mov     rdi, rax
0x14000e0db  mov     [rsp+128h+Irp], rax
0x14000e0e0  test    rax, rax
0x14000e0e3  jz      loc_14000ECAF
0x14000e0e9  mov     rax, [rax+0B8h]
0x14000e0f0  mov     byte ptr [rax-48h], 0Fh
0x14000e0f4  mov     [rax-40h], rbx
0x14000e0f8  mov     rax, [rdi+0B8h]
0x14000e0ff  lea     rcx, ClasspSendSynchronousCompletion
0x14000e106  mov     [rax-10h], rcx
0x14000e10a  mov     [rax-8], rbx
0x14000e10e  mov     byte ptr [rax-45h], 0E0h
0x14000e112  lea     rax, [rsp+128h+var_78]
0x14000e11a  mov     [rdi+48h], rax
0x14000e11e  lea     rax, [rsp+128h+Event]
0x14000e126  mov     [rdi+50h], rax
0x14000e12a  test    r15, r15
0x14000e12d  jnz     loc_14000E460
0x14000e133  mov     ecx, [rsp+128h+Length]
0x14000e137  cmp     byte ptr [rbx+2], 28h ; '('
0x14000e13b  jnz     loc_14000E3B7
0x14000e141  mov     [rbx+3Ch], ecx
0x14000e144  jz      loc_14000E309
0x14000e14a  mov     byte ptr [rbx+4], 0
0x14000e14e  xor     r13d, r13d
0x14000e151  mov     byte ptr [rbx+3], 0
0x14000e155  cmp     byte ptr [rbx+2], 28h ; '('
0x14000e159  jnz     loc_14000E375
0x14000e15f  mov     [rbx+70h], r13
0x14000e163  jnz     loc_14000E39D
0x14000e169  mov     [rbx+50h], rdi
0x14000e16d  mov     rdx, rdi; Irp
0x14000e170  mov     rcx, [r12+10h]; DeviceObject
0x14000e175  call    cs:__imp_IofCallDriver
0x14000e17c  nop     dword ptr [rax+rax+00h]
0x14000e181  mov     [rsp+128h+var_C8], eax
0x14000e185  cmp     eax, 103h
0x14000e18a  jnz     short loc_14000E1B8
0x14000e18c  mov     [rsp+128h+Timeout], r13; Timeout
0x14000e191  xor     r9d, r9d; Alertable
0x14000e194  xor     r8d, r8d; WaitMode
0x14000e197  xor     edx, edx; WaitReason
0x14000e199  lea     rcx, [rsp+128h+Event]; Object
0x14000e1a1  call    cs:__imp_KeWaitForSingleObject
0x14000e1a8  nop     dword ptr [rax+rax+00h]
0x14000e1ad  mov     eax, dword ptr [rsp+128h+var_78]
0x14000e1b4  mov     [rsp+128h+var_C8], eax
0x14000e1b8  cmp     byte ptr [rbx+2], 28h ; '('
0x14000e1bc  jnz     loc_14000E3A6
0x14000e1c2  mov     [rbx+50h], r13
0x14000e1c6  movzx   eax, byte ptr [rbx+3]
0x14000e1ca  and     al, 3Fh
0x14000e1cc  cmp     al, 1
0x14000e1ce  jnz     loc_14000E7E1
0x14000e1d4  mov     rax, [rsp+128h+var_50]
0x14000e1dc  mov     byte ptr [rax+295h], 0
0x14000e1e3  mov     [rsp+128h+var_C8], r13d
0x14000e1e8  movzx   ecx, byte ptr [rbx+2]
0x14000e1ec  cmp     cl, 28h ; '('
0x14000e1ef  mov     eax, 0Ch
0x14000e1f4  cmovnz  rsi, rax
0x14000e1f8  mov     eax, [rsi+rbx]
0x14000e1fb  bt      eax, 15h
0x14000e1ff  jnb     short loc_14000E20B
0x14000e201  bt      eax, 0Ah
0x14000e205  jb      loc_14000E8F6
0x14000e20b  xor     edx, edx; Tag
0x14000e20d  mov     rcx, r14; P
0x14000e210  call    cs:__imp_ExFreePoolWithTag
0x14000e217  nop     dword ptr [rax+rax+00h]
0x14000e21c  cmp     byte ptr [rbx+2], 28h ; '('
0x14000e220  jnz     short loc_14000E279
0x14000e222  cmp     dword ptr [rbx+14h], 0
0x14000e226  jnz     short loc_14000E27D
0x14000e228  xor     dl, dl
0x14000e22a  mov     r10d, r13d
0x14000e22d  cmp     dword ptr [rbx+38h], 0
0x14000e231  jbe     short loc_14000E27D
0x14000e233  mov     eax, r10d
0x14000e236  mov     ecx, [rbx+rax*4+78h]
0x14000e23a  cmp     ecx, 80h
0x14000e240  jb      short loc_14000E26E
0x14000e242  mov     r8d, [rbx+10h]
0x14000e246  cmp     ecx, r8d
0x14000e249  jnb     short loc_14000E26E
0x14000e24b  mov     r9d, ecx
0x14000e24e  mov     ecx, [rcx+rbx]
0x14000e251  cmp     ecx, 40h ; '@'
0x14000e254  jnz     loc_14000E6E5
0x14000e25a  lea     rcx, [r9+28h]
0x14000e25e  cmp     rcx, r8
0x14000e261  ja      short loc_14000E26A
0x14000e263  mov     [r9+rbx+10h], r13
0x14000e268  mov     dl, 1
0x14000e26a  test    dl, dl
0x14000e26c  jnz     short loc_14000E27D
0x14000e26e  inc     r10d
0x14000e271  cmp     r10d, [rbx+38h]
0x14000e275  jnb     short loc_14000E27D
0x14000e277  jmp     short loc_14000E233
0x14000e279  mov     [rbx+20h], r13
0x14000e27d  cmp     byte ptr [rbx+2], 28h ; '('
0x14000e281  jnz     short loc_14000E2DD
0x14000e283  cmp     dword ptr [rbx+14h], 0
0x14000e287  jnz     short loc_14000E2E1
0x14000e289  xor     r9b, r9b
0x14000e28c  mov     r8d, r13d
0x14000e28f  cmp     dword ptr [rbx+38h], 0
0x14000e293  jbe     short loc_14000E2E1
0x14000e295  mov     eax, r8d
0x14000e298  mov     ecx, [rbx+rax*4+78h]
0x14000e29c  cmp     ecx, 80h
0x14000e2a2  jb      short loc_14000E2D2
0x14000e2a4  mov     edx, [rbx+10h]
0x14000e2a7  cmp     ecx, edx
0x14000e2a9  jnb     short loc_14000E2D2
0x14000e2ab  lea     r10, [rcx+rbx]
0x14000e2af  mov     r11d, [r10]
0x14000e2b2  cmp     r11d, 40h ; '@'
0x14000e2b6  jnz     loc_14000E723
0x14000e2bc  add     rcx, 28h ; '('
0x14000e2c0  cmp     rcx, rdx
0x14000e2c3  ja      short loc_14000E2CD
0x14000e2c5  mov     r9b, 1
0x14000e2c8  mov     byte ptr [r10+9], 0
0x14000e2cd  test    r9b, r9b
  ... truncated ...
```
