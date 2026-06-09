# I8xInternalDeviceControl

- ea: `0x140007090`
- end: `0x140007b02`
- name: `I8xInternalDeviceControl`
- size: `2674`
- prototype: `__int64 __fastcall(PDEVICE_OBJECT DeviceObject, PIRP Irp)`
- caller_count: `0`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x140004530`
- `0x140005140`
- `0x140007090`
- `0x140007b10`
- `0x1400098f0`
- `0x14000db80`

## import_xrefs

- `ntoskrnl!IoStartPacket` at `0x140007af1`
- `ntoskrnl!IoStartPacket` at `0x140007af1`
- `ntoskrnl!ExAllocatePool2` at `0x140007478`
- `ntoskrnl!ExAllocatePool2` at `0x140007735`
- `ntoskrnl!ExAllocatePool2` at `0x140007478`
- `ntoskrnl!ExAllocatePool2` at `0x140007735`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400074e2`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400074e2`
- `ntoskrnl!IofCompleteRequest` at `0x14000740e`
- `ntoskrnl!IofCompleteRequest` at `0x14000740e`
- `ntoskrnl!IoGetAttachedDeviceReference` at `0x14000748f`
- `ntoskrnl!IoGetAttachedDeviceReference` at `0x140007750`
- `ntoskrnl!IoGetAttachedDeviceReference` at `0x14000748f`
- `ntoskrnl!IoGetAttachedDeviceReference` at `0x140007750`
- `ntoskrnl!ObfDereferenceObject` at `0x1400074d1`
- `ntoskrnl!ObfDereferenceObject` at `0x1400074d1`
- `ntoskrnl!IoAcquireRemoveLockEx` at `0x140007abb`
- `ntoskrnl!IoAcquireRemoveLockEx` at `0x140007abb`

## pseudocode

```c
__int64 __fastcall I8xInternalDeviceControl(PDEVICE_OBJECT DeviceObject, PIRP Irp, __int64 a3, __int64 a4)
{
  char *DeviceExtension; // rdi
  PIRP v5; // rbx
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rsi
  unsigned int LowPart; // eax
  unsigned int v9; // eax
  unsigned int v10; // eax
  unsigned int v11; // eax
  __int64 v12; // rax
  ULONG v13; // edi
  unsigned int v14; // edi
  struct _IRP *v15; // rcx
  ULONG_PTR v16; // rax
  __int16 v17; // ax
  struct _IRP *v18; // rcx
  USHORT v19; // ax
  struct _IRP *v20; // rcx
  USHORT v21; // ax
  struct _IRP *v22; // rax
  __int128 v23; // xmm1
  int v24; // r9d
  int v25; // r9d
  int v26; // edx
  _QWORD *Pool2; // rsi
  PDEVICE_OBJECT v29; // rax
  ULONG v30; // r9d
  struct _DEVICE_OBJECT *v31; // rdi
  ULONG v32; // edx
  unsigned int v33; // eax
  unsigned int v34; // eax
  _QWORD *v35; // rcx
  __int64 v36; // rax
  __int64 v37; // rax
  int v38; // r9d
  int v39; // r9d
  int v40; // r8d
  PDEVICE_OBJECT AttachedDeviceReference; // rax
  struct _IRP *v42; // rcx
  int v43; // eax
  unsigned int v44; // eax
  unsigned int v45; // eax
  _QWORD *p_NamedPipeType; // rcx
  __int64 v47; // rax
  struct _IRP *v48; // rcx
  USHORT Size; // ax
  unsigned __int16 v50; // ax
  struct _IRP *MasterIrp; // r8
  unsigned __int16 v52; // cx
  __int16 v53; // cx
  __int16 v54; // cx
  NTSTATUS v55; // eax

  DeviceExtension = (char *)DeviceObject->DeviceExtension;
  v5 = Irp;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      (_DWORD)Irp,
      11,
      31,
      (__int64)WPP_69ad5fa20b14395ecb5f7e203cce2975_Traceguids);
  CurrentStackLocation = v5->Tail.Overlay.CurrentStackLocation;
  v5->IoStatus.Information = 0;
  LowPart = CurrentStackLocation->Parameters.Read.ByteOffset.LowPart;
  if ( LowPart == 720904 )
  {
    if ( !*((_QWORD *)DeviceExtension + 1) )
    {
      v14 = -1073741661;
      goto LABEL_53;
    }
    if ( *((_DWORD *)DeviceExtension + 20) != 1 )
    {
      v14 = -1073741101;
      goto LABEL_53;
    }
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_SF_(
        WPP_GLOBAL_Control->DeviceExtension,
        (_DWORD)Irp,
        10,
        49,
        (__int64)WPP_69ad5fa20b14395ecb5f7e203cce2975_Traceguids);
    if ( CurrentStackLocation->Parameters.Create.Options < 4 )
      goto LABEL_52;
    MasterIrp = v5->AssociatedIrp.MasterIrp;
    LODWORD(Irp) = MasterIrp->Size;
    if ( ((unsigned int)Irp & 0xFFFFFFF0) != 0 )
      goto LABEL_52;
    v52 = *((_WORD *)DeviceExtension + 344);
    if ( (_BYTE)v52 == 7 )
    {
      v53 = HIBYTE(v52);
      if ( (unsigned __int8)(v53 + 127) <= 1u )
      {
        if ( ((unsigned __int8)Irp & 8) != 0 )
        {
          LOWORD(Irp) = (unsigned __int16)Irp | 2;
          MasterIrp->Size = (unsigned __int16)Irp;
          v5->AssociatedIrp.MasterIrp->Size &= ~8u;
          goto LABEL_164;
        }
        v54 = -3;
LABEL_163:
        LOWORD(Irp) = v54 & (unsigned __int16)Irp;
        MasterIrp->Size = (unsigned __int16)Irp;
        goto LABEL_164;
      }
      if ( (_BYTE)v53 == 1 )
        goto LABEL_164;
    }
    if ( ((unsigned __int8)Irp & 8) == 0 )
      goto LABEL_164;
    v54 = -9;
    goto LABEL_163;
  }
  if ( LowPart == 720900 )
  {
    if ( !*((_QWORD *)DeviceExtension + 1) )
    {
      v14 = -1073741661;
      goto LABEL_53;
    }
    if ( *((_DWORD *)DeviceExtension + 20) != 1 )
    {
      v14 = -1073741101;
      goto LABEL_53;
    }
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_SF_(
        WPP_GLOBAL_Control->DeviceExtension,
        (_DWORD)Irp,
        10,
        51,
        (__int64)WPP_69ad5fa20b14395ecb5f7e203cce2975_Traceguids);
    if ( CurrentStackLocation->Parameters.Create.Options >= 6 )
    {
      v48 = v5->AssociatedIrp.MasterIrp;
      Size = v48->Size;
      if ( Size >= *((_WORD *)DeviceExtension + 353) && Size <= *((_WORD *)DeviceExtension + 356) )
      {
        v50 = *(&v48->Size + 1);
        if ( v50 >= *((_WORD *)DeviceExtension + 354) && v50 <= *((_WORD *)DeviceExtension + 357) )
          goto LABEL_164;
      }
    }
LABEL_144:
    v14 = -1073741811;
    goto LABEL_145;
  }
  if ( LowPart > 0xB3FCB )
  {
    if ( LowPart > 0xF0403 )
    {
      v44 = LowPart - 999363;
      if ( !v44 )
      {
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          WPP_RECORDER_SF_(
            WPP_GLOBAL_Control->DeviceExtension,
            (_DWORD)Irp,
            12,
            44,
            (__int64)WPP_69ad5fa20b14395ecb5f7e203cce2975_Traceguids);
        if ( CurrentStackLocation->Parameters.Create.Options >= 0x28 )
        {
          p_NamedPipeType = &CurrentStackLocation->Parameters.CreatePipe.Parameters->NamedPipeType;
          *((_QWORD *)DeviceExtension + 134) = *p_NamedPipeType;
          v47 = p_NamedPipeType[1];
          if ( v47 )
            *((_QWORD *)DeviceExtension + 133) = v47;
          v14 = 0;
          goto LABEL_145;
        }
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          v25 = 45;
          goto LABEL_51;
        }
        goto LABEL_52;
      }
      v45 = v44 - 4;
      if ( !v45 )
        goto LABEL_65;
      if ( v45 == 8 )
        goto LABEL_61;
    }
    else
    {
      switch ( LowPart )
      {
        case 0xF0403u:
          if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
            goto LABEL_80;
          v38 = 43;
          goto LABEL_79;
        case 0xB3FCFu:
          goto LABEL_61;
        case 0xF0000u:
          if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
            WPP_RECORDER_SF_(
              WPP_GLOBAL_Control->DeviceExtension,
              (_DWORD)Irp,
              10,
              53,
              (__int64)WPP_69ad5fa20b14395ecb5f7e203cce2975_Traceguids);
          if ( CurrentStackLocation->Parameters.Read.Length < 0xC )
          {
            v14 = -1073741789;
            goto LABEL_53;
          }
          v42 = v5->AssociatedIrp.MasterIrp;
          *(_QWORD *)&v42->Type = *((_QWORD *)DeviceExtension + 73);
          v43 = *((_DWORD *)DeviceExtension + 148);
          v14 = 0;
          LODWORD(v42->MdlAddress) = v43;
          v5->IoStatus.Information = 12;
          goto LABEL_145;
        case 0xF0203u:
          if ( (**(_DWORD **)&WPP_MAIN_CB.Queue.Wcb.NumberOfChannels & 2) != 0 )
          {
            if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
              WPP_RECORDER_SF_(
                WPP_GLOBAL_Control->DeviceExtension,
                (_DWORD)Irp,
                1,
                39,
                (__int64)WPP_69ad5fa20b14395ecb5f7e203cce2975_Traceguids);
            **(_DWORD **)&WPP_MAIN_CB.Queue.Wcb.NumberOfChannels |= 0x20u;
          }
          _InterlockedIncrement((volatile signed __int32 *)(&WPP_MAIN_CB.AlignmentRequirement + 1));
          DeviceExtension[565] = 0;
          **(_DWORD **)&WPP_MAIN_CB.Queue.Wcb.NumberOfChannels |= 2u;
          if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
            WPP_RECORDER_SF_(
              WPP_GLOBAL_Control->DeviceExtension,
              (_DWORD)Irp,
              12,
              40,
              (__int64)WPP_69ad5fa20b14395ecb5f7e203cce2975_Traceguids);
          if ( *((_QWORD *)DeviceExtension + 55) )
          {
            if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
              goto LABEL_47;
            v24 = 41;
            goto LABEL_46;
          }
          if ( CurrentStackLocation->Parameters.Create.Options < 0x10 )
          {
            if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
              goto LABEL_52;
            v25 = 42;
            goto LABEL_51;
          }
          *((_OWORD *)DeviceExtension + 27) = *(_OWORD *)&CurrentStackLocation->Parameters.CreatePipe.Parameters->NamedPipeType;
          Pool2 = (_QWORD *)ExAllocatePool2(256, 40, 842281016, a4);
          if ( Pool2 )
          {
            AttachedDeviceReference = IoGetAttachedDeviceReference(*(PDEVICE_OBJECT *)DeviceExtension);
            Pool2[4] = DeviceObject;
            v30 = 40;
            v31 = AttachedDeviceReference;
            v32 = 999363;
            Pool2[3] = I8xQueueCurrentMouseInput;
            Pool2[2] = I8xMouseIsrWritePort;
            goto LABEL_60;
          }
LABEL_61:
          v14 = 0;
          v5->IoStatus.Status = 0;
          goto LABEL_54;
      }
    }
LABEL_116:
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      goto LABEL_85;
    v39 = 56;
    v40 = 13;
    goto LABEL_84;
  }
  if ( LowPart == 737227 )
  {
    if ( DeviceExtension[565] )
    {
      v14 = -1073741637;
      goto LABEL_145;
    }
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
LABEL_85:
      v14 = -1073741808;
      goto LABEL_53;
    }
    v39 = 55;
    v40 = 1;
LABEL_84:
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      (_DWORD)Irp,
      v40,
      v39,
      (__int64)WPP_69ad5fa20b14395ecb5f7e203cce2975_Traceguids);
    goto LABEL_85;
  }
  if ( LowPart <= 0xB0203 )
  {
    if ( LowPart != 721411 )
    {
      v9 = LowPart - 720896;
      if ( !v9 )
      {
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          WPP_RECORDER_SF_(
            WPP_GLOBAL_Control->DeviceExtension,
            (_DWORD)Irp,
            10,
            46,
            (__int64)WPP_69ad5fa20b14395ecb5f7e203cce2975_Traceguids);
        if ( CurrentStackLocation->Parameters.Read.Length < 0x1C )
        {
          v14 = -1073741789;
          goto LABEL_53;
        }
        v22 = v5->AssociatedIrp.MasterIrp;
        *(_OWORD *)&v22->Type = *((_OWORD *)DeviceExtension + 43);
        v23 = *(_OWORD *)(DeviceExtension + 700);
        v14 = 0;
        *(_OWORD *)((char *)&v22->MdlAddress + 4) = v23;
        v5->IoStatus.Information = 28;
        goto LABEL_145;
      }
      v10 = v9 - 32;
      if ( !v10 )
      {
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          WPP_RECORDER_SF_(
            WPP_GLOBAL_Control->DeviceExtension,
            (_DWORD)Irp,
            10,
            50,
            (__int64)WPP_69ad5fa20b14395ecb5f7e203cce2975_Traceguids);
        if ( CurrentStackLocation->Parameters.Read.Length < 6 )
        {
          v14 = -1073741789;
          goto LABEL_53;
        }
        v20 = v5->AssociatedIrp.MasterIrp;
        *(_DWORD *)&v20->Type = *((_DWORD *)DeviceExtension + 181);
        v21 = *((_WORD *)DeviceExtension + 364);
        v14 = 0;
        *(&v20->Size + 1) = v21;
        v5->IoStatus.Information = 6;
        goto LABEL_145;
      }
      v11 = v10 - 32;
      if ( !v11 )
      {
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          WPP_RECORDER_SF_(
            WPP_GLOBAL_Control->DeviceExtension,
            (_DWORD)Irp,
            10,
            48,
            (__int64)WPP_69ad5fa20b14395ecb5f7e203cce2975_Traceguids);
        if ( CurrentStackLocation->Parameters.Read.Length < 4 )
        {
          v14 = -1073741789;
          goto LABEL_53;
        }
        *(_DWORD *)v5->AssociatedIrp.MasterIrp = *(_DWORD *)(DeviceExtension + 730);
        v17 = *((_WORD *)DeviceExtension + 344);
        if ( (_BYTE)v17 == 7 && (HIBYTE(v17) == 0x81 || HIBYTE(v17) == 0x82) )
        {
          v18 = v5->AssociatedIrp.MasterIrp;
          v19 = v18->Size;
          if ( (v19 & 2) != 0 )
          {
            v18->Size = v19 | 8;
            v5->AssociatedIrp.MasterIrp->Size &= ~2u;
          }
        }
        v5->IoStatus.Information = 4;
        v14 = 0;
LABEL_145:
        v5->IoStatus.Status = v14;
        goto LABEL_54;
      }
      if ( v11 == 64 )
      {
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          WPP_RECORDER_SF_(
            WPP_GLOBAL_Control->DeviceExtension,
            (_DWORD)Irp,
            10,
            47,
            (__int64)WPP_69ad5fa20b14395ecb5f7e203cce2975_Traceguids);
        v12 = *((unsigned __int16 *)DeviceExtension + 347);
        v13 = 4 * v12 + 2;
        if ( CurrentStackLocation->Parameters.Read.Length < v13 )
        {
          v14 = -1073741789;
LABEL_53:
          v5->IoStatus.Status = v14;
LABEL_54:
          IofCompleteRequest(v5, 0);
          goto LABEL_55;
        }
        v15 = v5->AssociatedIrp.MasterIrp;
        v15->Type = v12;
        memmove(&v15->Size, qword_140010288, 4 * v12);
        v16 = v13;
        v14 = 0;
        v5->IoStatus.Information = v16;
        goto LABEL_145;
      }
      goto LABEL_116;
    }
    if ( (**(_DWORD **)&WPP_MAIN_CB.Queue.Wcb.NumberOfChannels & 1) != 0 )
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        WPP_RECORDER_SF_(
          WPP_GLOBAL_Control->DeviceExtension,
          (_DWORD)Irp,
          1,
          32,
          (__int64)WPP_69ad5fa20b14395ecb5f7e203cce2975_Traceguids);
      **(_DWORD **)&WPP_MAIN_CB.Queue.Wcb.NumberOfChannels |= 0x10u;
    }
    _InterlockedIncrement((volatile signed __int32 *)&WPP_MAIN_CB.AlignmentRequirement);
    DeviceExtension[565] = 1;
    **(_DWORD **)&WPP_MAIN_CB.Queue.Wcb.NumberOfChannels |= 1u;
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_SF_(
        WPP_GLOBAL_Control->DeviceExtension,
        (_DWORD)Irp,
        12,
        33,
        (__int64)WPP_69ad5fa20b14395ecb5f7e203cce2975_Traceguids);
    if ( *((_QWORD *)DeviceExtension + 55) )
    {
      if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
LABEL_47:
        v14 = -1073741757;
        goto LABEL_53;
      }
      v24 = 34;
LABEL_46:
      WPP_RECORDER_SF_(
        WPP_GLOBAL_Control->DeviceExtension,
        (_DWORD)Irp,
        13,
        v24,
        (__int64)WPP_69ad5fa20b14395ecb5f7e203cce2975_Traceguids);
      goto LABEL_47;
    }
    if ( CurrentStackLocation->Parameters.Create.Options < 0x10 )
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        v25 = 35;
LABEL_51:
        WPP_RECORDER_SF_(
          WPP_GLOBAL_Control->DeviceExtension,
          (_DWORD)Irp,
          13,
          v25,
          (__int64)WPP_69ad5fa20b14395ecb5f7e203cce2975_Traceguids);
        goto LABEL_52;
      }
      goto LABEL_52;
    }
    *((_OWORD *)DeviceExtension + 27) = *(_OWORD *)&CurrentStackLocation->Parameters.CreatePipe.Parameters->NamedPipeType;
    Pool2 = (_QWORD *)ExAllocatePool2(256, 48, 842281016, a4);
    if ( Pool2 )
    {
      v29 = IoGetAttachedDeviceReference(*(PDEVICE_OBJECT *)DeviceExtension);
      Pool2[5] = DeviceObject;
      v30 = 48;
      v31 = v29;
      v32 = 737219;
      Pool2[4] = I8xQueueCurrentKeyboardInput;
      Pool2[3] = I8xKeyboardIsrWritePort;
LABEL_60:
      I8xSendIoctl(v31, v32, Pool2, v30);
      ObfDereferenceObject(v31);
      ExFreePoolWithTag(Pool2, 0);
      goto LABEL_61;
    }
    goto LABEL_61;
  }
  v33 = LowPart - 721923;
  if ( !v33 )
  {
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
LABEL_80:
      v14 = -1073741822;
      goto LABEL_53;
    }
    v38 = 36;
LABEL_79:
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      (_DWORD)Irp,
      12,
      v38,
      (__int64)WPP_69ad5fa20b14395ecb5f7e203cce2975_Traceguids);
    goto LABEL_80;
  }
  v34 = v33 - 15296;
  if ( !v34 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_SF_(
        WPP_GLOBAL_Control->DeviceExtension,
        (_DWORD)Irp,
        12,
        37,
        (__int64)WPP_69ad5fa20b14395ecb5f7e203cce2975_Traceguids);
    if ( CurrentStackLocation->Parameters.Create.Options >= 0x30 )
    {
      v35 = &CurrentStackLocation->Parameters.CreatePipe.Parameters->NamedPipeType;
      *((_QWORD *)DeviceExtension + 117) = *v35;
      v36 = v35[1];
      if ( v36 )
        *((_QWORD *)DeviceExtension + 115) = v36;
      v37 = v35[2];
      if ( v37 )
        *((_QWORD *)DeviceExtension + 116) = v37;
      v14 = 0;
      goto LABEL_145;
    }
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v25 = 38;
      goto LABEL_51;
    }
LABEL_52:
    v14 = -1073741811;
    goto LABEL_53;
  }
  if ( v34 != 4 )
    goto LABEL_116;
LABEL_65:
  if ( !*((_QWORD *)DeviceExtension + 1) )
  {
    v14 = -1073741661;
    goto LABEL_53;
  }
  if ( *((_DWORD *)DeviceExtension + 20) != 1 )
  {
    v14 = -1073741101;
    goto LABEL_53;
  }
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      (_DWORD)Irp,
      10,
      54,
      (__int64)WPP_69ad5fa20b14395ecb5f7e203cce2975_Traceguids);
  if ( !CurrentStackLocation->Parameters.Create.Options || !CurrentStackLocation->Parameters.CreatePipe.Parameters )
    goto LABEL_144;
LABEL_164:
  v5->IoStatus.Status = 259;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_qq(
      WPP_GLOBAL_Control->DeviceExtension,
      (_DWORD)Irp,
      10,
      57,
      (__int64)WPP_69ad5fa20b14395ecb5f7e203cce2975_Traceguids,
      (char)v5,
      (char)DeviceObject->DeviceExtension + 40);
  v55 = IoAcquireRemoveLockEx((PIO_REMOVE_LOCK)((char *)DeviceObject->DeviceExtension + 40), v5, File, 1u, 0x20u);
  v14 = v55;
  if ( v55 < 0 )
  {
    v5->IoStatus.Status = v55;
    goto LABEL_54;
  }
  v14 = 259;
  v5->Tail.Overlay.CurrentStackLocation->Control |= 1u;
  IoStartPacket(DeviceObject, v5, 0, 0);
LABEL_55:
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_D(
      WPP_GLOBAL_Control->DeviceExtension,
      v26,
      11,
      58,
      (__int64)WPP_69ad5fa20b14395ecb5f7e203cce2975_Traceguids,
      v14);
  return v14;
}

```

## disassembly

```asm
0x140007090  push    rbx
0x140007092  push    rbp
0x140007093  push    rsi
0x140007094  push    rdi
0x140007095  push    r12
0x140007097  push    r14
0x140007099  push    r15
0x14000709b  sub     rsp, 40h
0x14000709f  mov     rdi, [rcx+40h]
0x1400070a3  mov     rbx, rdx
0x1400070a6  mov     rbp, rcx
0x1400070a9  lea     r14, WPP_RECORDER_INITIALIZED
0x1400070b0  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x1400070b7  lea     r12, WPP_69ad5fa20b14395ecb5f7e203cce2975_Traceguids
0x1400070be  jz      short loc_1400070E1
0x1400070c0  mov     rcx, cs:WPP_GLOBAL_Control
0x1400070c7  mov     r9d, 1Fh
0x1400070cd  mov     r8d, 0Bh
0x1400070d3  mov     qword ptr [rsp+78h+RemlockSize], r12
0x1400070d8  mov     rcx, [rcx+40h]
0x1400070dc  call    WPP_RECORDER_SF_
0x1400070e1  mov     rsi, [rbx+0B8h]
0x1400070e8  xor     r15d, r15d
0x1400070eb  mov     [rbx+38h], r15
0x1400070ef  mov     eax, [rsi+18h]
0x1400070f2  cmp     eax, 0B0008h
0x1400070f7  jz      loc_14000799D
0x1400070fd  cmp     eax, 0B0004h
0x140007102  jz      loc_140007900
0x140007108  cmp     eax, 0B3FCBh
0x14000710d  ja      loc_140007622
0x140007113  jz      loc_1400075DB
0x140007119  cmp     eax, 0B0203h
0x14000711e  ja      loc_1400074FA
0x140007124  jz      loc_14000730F
0x14000712a  sub     eax, 0B0000h
0x14000712f  jz      loc_1400072AC
0x140007135  sub     eax, 20h ; ' '
0x140007138  jz      loc_14000724B
0x14000713e  sub     eax, 20h ; ' '
0x140007141  jz      short loc_1400071BF
0x140007143  cmp     eax, 40h ; '@'
0x140007146  jnz     loc_140007821
0x14000714c  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x140007153  jz      short loc_140007176
0x140007155  mov     rcx, cs:WPP_GLOBAL_Control
0x14000715c  mov     r9d, 2Fh ; '/'
0x140007162  mov     r8d, 0Ah
0x140007168  mov     qword ptr [rsp+78h+RemlockSize], r12
0x14000716d  mov     rcx, [rcx+40h]
0x140007171  call    WPP_RECORDER_SF_
0x140007176  movzx   eax, word ptr [rdi+2B6h]
0x14000717d  lea     edi, ds:2[rax*4]
0x140007184  cmp     [rsi+8], edi
0x140007187  jnb     short loc_140007193
0x140007189  mov     edi, 0C0000023h
0x14000718e  jmp     loc_140007406
0x140007193  mov     rcx, [rbx+18h]
0x140007197  lea     rdx, qword_140010288; Src
0x14000719e  mov     r8, rax
0x1400071a1  shl     r8, 2; Size
0x1400071a5  mov     [rcx], ax
0x1400071a8  add     rcx, 2; void *
0x1400071ac  call    memmove
0x1400071b1  mov     eax, edi
0x1400071b3  mov     edi, r15d
0x1400071b6  mov     [rbx+38h], rax
0x1400071ba  jmp     loc_140007989
0x1400071bf  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x1400071c6  jz      short loc_1400071E9
0x1400071c8  mov     rcx, cs:WPP_GLOBAL_Control
0x1400071cf  mov     r9d, 30h ; '0'
0x1400071d5  mov     r8d, 0Ah
0x1400071db  mov     qword ptr [rsp+78h+RemlockSize], r12
0x1400071e0  mov     rcx, [rcx+40h]
0x1400071e4  call    WPP_RECORDER_SF_
0x1400071e9  cmp     dword ptr [rsi+8], 4
0x1400071ed  jnb     short loc_1400071F9
0x1400071ef  mov     edi, 0C0000023h
0x1400071f4  jmp     loc_140007406
0x1400071f9  mov     eax, [rdi+2DAh]
0x1400071ff  mov     rcx, [rbx+18h]
0x140007203  mov     [rcx], eax
0x140007205  movzx   eax, word ptr [rdi+2B0h]
0x14000720c  cmp     al, 7
0x14000720e  jnz     short loc_14000723B
0x140007210  shr     ax, 8
0x140007214  add     al, 7Fh
0x140007216  cmp     al, 1
0x140007218  ja      short loc_14000723B
0x14000721a  mov     rcx, [rbx+18h]
0x14000721e  movzx   eax, word ptr [rcx+2]
0x140007222  test    al, 2
0x140007224  jz      short loc_14000723B
0x140007226  or      ax, 8
0x14000722a  mov     [rcx+2], ax
0x14000722e  mov     ecx, 0FFFDh
0x140007233  mov     rax, [rbx+18h]
0x140007237  and     [rax+2], cx
0x14000723b  mov     qword ptr [rbx+38h], 4
0x140007243  mov     edi, r15d
0x140007246  jmp     loc_140007989
0x14000724b  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x140007252  jz      short loc_140007275
0x140007254  mov     rcx, cs:WPP_GLOBAL_Control
0x14000725b  mov     r9d, 32h ; '2'
0x140007261  mov     r8d, 0Ah
0x140007267  mov     qword ptr [rsp+78h+RemlockSize], r12
0x14000726c  mov     rcx, [rcx+40h]
0x140007270  call    WPP_RECORDER_SF_
0x140007275  cmp     dword ptr [rsi+8], 6
0x140007279  jnb     short loc_140007285
0x14000727b  mov     edi, 0C0000023h
0x140007280  jmp     loc_140007406
0x140007285  mov     eax, [rdi+2D4h]
0x14000728b  mov     rcx, [rbx+18h]
0x14000728f  mov     [rcx], eax
0x140007291  movzx   eax, word ptr [rdi+2D8h]
0x140007298  mov     edi, r15d
0x14000729b  mov     [rcx+4], ax
0x14000729f  mov     qword ptr [rbx+38h], 6
0x1400072a7  jmp     loc_140007989
0x1400072ac  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x1400072b3  jz      short loc_1400072D6
0x1400072b5  mov     rcx, cs:WPP_GLOBAL_Control
0x1400072bc  mov     r9d, 2Eh ; '.'
0x1400072c2  mov     r8d, 0Ah
0x1400072c8  mov     qword ptr [rsp+78h+RemlockSize], r12
0x1400072cd  mov     rcx, [rcx+40h]
0x1400072d1  call    WPP_RECORDER_SF_
0x1400072d6  cmp     dword ptr [rsi+8], 1Ch
0x1400072da  jnb     short loc_1400072E6
0x1400072dc  mov     edi, 0C0000023h
0x1400072e1  jmp     loc_140007406
0x1400072e6  movups  xmm0, xmmword ptr [rdi+2B0h]
0x1400072ed  mov     rax, [rbx+18h]
0x1400072f1  movups  xmmword ptr [rax], xmm0
0x1400072f4  movups  xmm1, xmmword ptr [rdi+2BCh]
0x1400072fb  mov     edi, r15d
0x1400072fe  movups  xmmword ptr [rax+0Ch], xmm1
0x140007302  mov     qword ptr [rbx+38h], 1Ch
0x14000730a  jmp     loc_140007989
0x14000730f  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue+10h
0x140007316  mov     ecx, [rax]
0x140007318  test    cl, 1
0x14000731b  jz      short loc_140007351
0x14000731d  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x140007324  jz      short loc_140007347
0x140007326  mov     rcx, cs:WPP_GLOBAL_Control
0x14000732d  mov     r9d, 20h ; ' '
0x140007333  mov     r8d, 1
0x140007339  mov     qword ptr [rsp+78h+RemlockSize], r12
0x14000733e  mov     rcx, [rcx+40h]
0x140007342  call    WPP_RECORDER_SF_
0x140007347  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue+10h
0x14000734e  or      dword ptr [rax], 10h
0x140007351  lock inc cs:WPP_MAIN_CB.AlignmentRequirement
0x140007358  mov     byte ptr [rdi+235h], 1
0x14000735f  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue+10h
0x140007366  or      dword ptr [rax], 1
0x140007369  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x140007370  jz      short loc_140007393
0x140007372  mov     rcx, cs:WPP_GLOBAL_Control
0x140007379  mov     r9d, 21h ; '!'
0x14000737f  mov     r8d, 0Ch
0x140007385  mov     qword ptr [rsp+78h+RemlockSize], r12
0x14000738a  mov     rcx, [rcx+40h]
0x14000738e  call    WPP_RECORDER_SF_
0x140007393  cmp     [rdi+1B8h], r15
0x14000739a  jz      short loc_1400073CD
0x14000739c  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x1400073a3  jz      short loc_1400073C6
0x1400073a5  mov     r9d, 22h ; '"'
0x1400073ab  mov     rcx, cs:WPP_GLOBAL_Control
0x1400073b2  mov     r8d, 0Dh
0x1400073b8  mov     qword ptr [rsp+78h+RemlockSize], r12
0x1400073bd  mov     rcx, [rcx+40h]
0x1400073c1  call    WPP_RECORDER_SF_
0x1400073c6  mov     edi, 0C0000043h
0x1400073cb  jmp     short loc_140007406
0x1400073cd  cmp     dword ptr [rsi+10h], 10h
0x1400073d1  jnb     loc_14000745A
0x1400073d7  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x1400073de  jz      short loc_140007401
0x1400073e0  mov     r9d, 23h ; '#'
0x1400073e6  mov     rcx, cs:WPP_GLOBAL_Control
0x1400073ed  mov     r8d, 0Dh
0x1400073f3  mov     qword ptr [rsp+78h+RemlockSize], r12
0x1400073f8  mov     rcx, [rcx+40h]
0x1400073fc  call    WPP_RECORDER_SF_
0x140007401  mov     edi, 0C000000Dh
0x140007406  mov     [rbx+30h], edi
0x140007409  xor     edx, edx; PriorityBoost
0x14000740b  mov     rcx, rbx; Irp
0x14000740e  call    cs:__imp_IofCompleteRequest
0x140007415  nop     dword ptr [rax+rax+00h]
0x14000741a  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x140007421  jz      short loc_140007448
0x140007423  mov     rcx, cs:WPP_GLOBAL_Control
0x14000742a  mov     r9d, 3Ah ; ':'
0x140007430  mov     dword ptr [rsp+78h+var_50], edi
0x140007434  mov     r8d, 0Bh
0x14000743a  mov     qword ptr [rsp+78h+RemlockSize], r12
0x14000743f  mov     rcx, [rcx+40h]
0x140007443  call    WPP_RECORDER_SF_D
0x140007448  mov     eax, edi
0x14000744a  add     rsp, 40h
0x14000744e  pop     r15
0x140007450  pop     r14
0x140007452  pop     r12
0x140007454  pop     rdi
0x140007455  pop     rsi
0x140007456  pop     rbp
0x140007457  pop     rbx
0x140007458  retn
0x14000745a  mov     rax, [rsi+20h]
0x14000745e  mov     edx, 30h ; '0'
0x140007463  mov     ecx, 100h
0x140007468  mov     r8d, 32343038h
0x14000746e  movups  xmm0, xmmword ptr [rax]
0x140007471  movups  xmmword ptr [rdi+1B0h], xmm0
0x140007478  call    cs:__imp_ExAllocatePool2
0x14000747f  nop     dword ptr [rax+rax+00h]
0x140007484  mov     rsi, rax
0x140007487  test    rax, rax
0x14000748a  jz      short loc_1400074EE
0x14000748c  mov     rcx, [rdi]; DeviceObject
0x14000748f  call    cs:__imp_IoGetAttachedDeviceReference
0x140007496  nop     dword ptr [rax+rax+00h]
0x14000749b  mov     [rsi+28h], rbp
0x14000749f  mov     r9d, 30h ; '0'; InputBufferLength
0x1400074a5  mov     rdi, rax
0x1400074a8  mov     edx, 0B3FC3h; IoControlCode
0x1400074ad  lea     rax, I8xQueueCurrentKeyboardInput
0x1400074b4  mov     [rsi+20h], rax
0x1400074b8  lea     rax, I8xKeyboardIsrWritePort
0x1400074bf  mov     [rsi+18h], rax
0x1400074c3  mov     r8, rsi; InputBuffer
0x1400074c6  mov     rcx, rdi; DeviceObject
0x1400074c9  call    I8xSendIoctl
0x1400074ce  mov     rcx, rdi; Object
0x1400074d1  call    cs:__imp_ObfDereferenceObject
0x1400074d8  nop     dword ptr [rax+rax+00h]
0x1400074dd  xor     edx, edx; Tag
0x1400074df  mov     rcx, rsi; P
0x1400074e2  call    cs:__imp_ExFreePoolWithTag
0x1400074e9  nop     dword ptr [rax+rax+00h]
0x1400074ee  mov     edi, r15d
0x1400074f1  mov     [rbx+30h], r15d
0x1400074f5  jmp     loc_140007409
0x1400074fa  sub     eax, 0B0403h
0x1400074ff  jz      loc_1400075A7
0x140007505  sub     eax, 3BC0h
0x14000750a  jz      short loc_140007529
0x14000750c  cmp     eax, 4
0x14000750f  jnz     loc_140007821
0x140007515  cmp     [rdi+8], r15
0x140007519  jnz     loc_14000783F
0x14000751f  mov     edi, 0C00000A3h
0x140007524  jmp     loc_140007406
0x140007529  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x140007530  jz      short loc_140007553
0x140007532  mov     rcx, cs:WPP_GLOBAL_Control
0x140007539  mov     r9d, 25h ; '%'
0x14000753f  mov     r8d, 0Ch
0x140007545  mov     qword ptr [rsp+78h+RemlockSize], r12
0x14000754a  mov     rcx, [rcx+40h]
0x14000754e  call    WPP_RECORDER_SF_
0x140007553  cmp     dword ptr [rsi+10h], 30h ; '0'
0x140007557  jnb     short loc_140007571
0x140007559  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x140007560  jz      loc_140007401
0x140007566  mov     r9d, 26h ; '&'
0x14000756c  jmp     loc_1400073E6
0x140007571  mov     rcx, [rsi+20h]
0x140007575  mov     rax, [rcx]
0x140007578  mov     [rdi+3A8h], rax
0x14000757f  mov     rax, [rcx+8]
0x140007583  test    rax, rax
0x140007586  jz      short loc_14000758F
0x140007588  mov     [rdi+398h], rax
0x14000758f  mov     rax, [rcx+10h]
0x140007593  test    rax, rax
0x140007596  jz      short loc_14000759F
0x140007598  mov     [rdi+3A0h], rax
0x14000759f  mov     edi, r15d
0x1400075a2  jmp     loc_140007989
0x1400075a7  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x1400075ae  jz      short loc_1400075D1
0x1400075b0  mov     r9d, 24h ; '$'
0x1400075b6  mov     rcx, cs:WPP_GLOBAL_Control
0x1400075bd  mov     r8d, 0Ch
0x1400075c3  mov     qword ptr [rsp+78h+RemlockSize], r12
0x1400075c8  mov     rcx, [rcx+40h]
0x1400075cc  call    WPP_RECORDER_SF_
0x1400075d1  mov     edi, 0C0000002h
0x1400075d6  jmp     loc_140007406
0x1400075db  cmp     [rdi+235h], r15b
0x1400075e2  jnz     short loc_140007618
0x1400075e4  cmp     cs:WPP_RECORDER_INITIALIZED, r14
  ... truncated ...
```
