# HidpPdoPnp

- ea: `0x18003e5b0`
- end: `0x18003f2ac`
- name: `HidpPdoPnp`
- size: `3324`
- prototype: ``
- caller_count: `1`
- callee_count: `25`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x18003e58c`

## callees

- `0x1800097f8`
- `0x180009a78`
- `0x18000ff44`
- `0x180011738`
- `0x1800125c4`
- `0x180013860`
- `0x18001414c`
- `0x180016f50`
- `0x1800173fc`
- `0x180018bec`
- `0x180019464`
- `0x18001a1cc`
- `0x18001be48`
- `0x18001c8a0`
- `0x18001e8ec`
- `0x18001ef18`
- `0x18001f468`
- `0x180020038`
- `0x180022534`
- `0x180027c80`
- `0x18003da1c`
- `0x18003e5b0`
- `0x18003ff7c`
- `0x180041d94`
- `0x180042f24`

## import_xrefs

- `ntoskrnl!MmBadPointer` at `0x18003e7d4`
- `ntoskrnl!MmBadPointer` at `0x18003e853`
- `ntoskrnl!MmBadPointer` at `0x18003ea54`
- `ntoskrnl!ObfReferenceObject` at `0x18003ef8a`
- `ntoskrnl!ObfReferenceObject` at `0x18003ef8a`
- `ntoskrnl!IofCompleteRequest` at `0x18003e7a1`
- `ntoskrnl!IofCompleteRequest` at `0x18003eb00`
- `ntoskrnl!IofCompleteRequest` at `0x18003f1ad`
- `ntoskrnl!IofCompleteRequest` at `0x18003e7a1`
- `ntoskrnl!IofCompleteRequest` at `0x18003eb00`
- `ntoskrnl!IofCompleteRequest` at `0x18003f1ad`
- `ntoskrnl!ExAllocatePool2` at `0x18003ef72`
- `ntoskrnl!ExAllocatePool2` at `0x18003f161`
- `ntoskrnl!ExAllocatePool2` at `0x18003ef72`
- `ntoskrnl!ExAllocatePool2` at `0x18003f161`
- `ntoskrnl!PoDirectedDripsSetDeviceFlags` at `0x18003e6ed`
- `ntoskrnl!PoDirectedDripsSetDeviceFlags` at `0x18003e6ed`
- `HIDPARSE!HidP_GetCaps` at `0x18003f097`

## pseudocode

```c
__int64 __fastcall HidpPdoPnp(PDEVICE_OBJECT a1, IRP *a2)
{
  _IO_STACK_LOCATION *CurrentStackLocation; // rbp
  unsigned int *p_CurrentIrp; // rdi
  PDEVICE_OBJECT *v4; // r8
  __int64 v5; // r14
  IRP *v6; // rsi
  int MinorFunction; // r12d
  _QWORD *p_Type; // rbx
  $E18ADDA25AF0B5F6794A1D3AE4197A6C *v9; // rdx
  int v10; // edx
  int started; // ebx
  int v12; // r8d
  PVOID v13; // rax
  __int64 v14; // rdx
  __int64 v15; // r8
  void (__fastcall *v16)(_QWORD, __int64); // rax
  PDEVICE_OBJECT v17; // rcx
  unsigned int v18; // r11d
  PDEVICE_OBJECT v19; // rcx
  char *v20; // rdx
  __int64 v21; // rcx
  __int64 v22; // rax
  IRP *v23; // rcx
  char v24; // bl
  __int64 v25; // rdx
  __int64 v26; // r8
  int v27; // eax
  unsigned __int64 ProviderId; // rbp
  __int64 v29; // rbx
  int v30; // edx
  unsigned int v31; // ecx
  unsigned int v32; // edx
  bool v33; // r11
  __int64 Pool2; // rbx
  _IO_STACK_LOCATION *v35; // rcx
  _IO_SECURITY_CONTEXT *SecurityContext; // rdx
  _LARGE_INTEGER ByteOffset; // rax
  __int64 v38; // rcx
  _LARGE_INTEGER v39; // rdx
  __int64 v40; // r8
  _LARGE_INTEGER v41; // rax
  __int64 v42; // rax
  int v43; // edx
  int v44; // r8d
  int v46; // [rsp+20h] [rbp-B8h]
  int v47; // [rsp+28h] [rbp-B0h]
  int v48; // [rsp+30h] [rbp-A8h]
  int v49; // [rsp+38h] [rbp-A0h]
  _OWORD v50[5]; // [rsp+80h] [rbp-58h] BYREF

  CurrentStackLocation = a2->Tail.Overlay.CurrentStackLocation;
  p_CurrentIrp = (unsigned int *)&a1->CurrentIrp;
  v4 = &WPP_GLOBAL_Control;
  v5 = *(_QWORD *)&a1->Queue.Wcb.NumberOfChannels + 32LL;
  v6 = a2;
  MinorFunction = CurrentStackLocation->MinorFunction;
  p_Type = &a1->Type;
  switch ( CurrentStackLocation->MinorFunction )
  {
    case 0u:
    case 1u:
    case 2u:
    case 3u:
    case 4u:
    case 5u:
    case 6u:
    case 8u:
    case 9u:
    case 0x13u:
    case 0x14u:
    case 0x17u:
      a1 = WPP_GLOBAL_Control;
      LOBYTE(a2) = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
                && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u;
      if ( (_BYTE)a2 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v4) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
        WPP_RECORDER_AND_TRACE_SF_qdqqcc(
          WPP_GLOBAL_Control->AttachedDevice,
          (_DWORD)a2,
          (_DWORD)v4,
          *(_QWORD *)(v5 + 672),
          4,
          4,
          63,
          (__int64)WPP_09551ba6d0fe3383c1d3f23d6d3d8f25_Traceguids,
          *(_QWORD *)v5,
          p_CurrentIrp[2],
          *((_QWORD *)p_CurrentIrp + 6),
          (char)v6,
          27,
          CurrentStackLocation->MinorFunction);
      }
      v9 = &v6->Tail.Overlay.64;
      v4 = &WPP_GLOBAL_Control;
      break;
    default:
      v9 = &a2->Tail.Overlay.64;
      break;
  }
  switch ( MinorFunction )
  {
    case 0:
      started = HidpPdoStartDevice(v5, p_CurrentIrp, &WPP_GLOBAL_Control);
      if ( started < 0 )
        goto LABEL_176;
      v13 = (PVOID)*((_QWORD *)p_CurrentIrp + 15);
      if ( !v13 || v13 == MmBadPointer )
        goto LABEL_176;
      ((void (__fastcall *)(_QWORD, _QWORD))v13)(*((_QWORD *)p_CurrentIrp + 16), 0);
      goto LABEL_22;
    case 1:
    case 2:
    case 23:
      v18 = p_CurrentIrp[1];
      *p_CurrentIrp = v18;
      p_CurrentIrp[1] = 6;
      LOBYTE(v9) = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
                && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u;
      LOBYTE(v4) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      if ( (_BYTE)v9 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        WPP_RECORDER_AND_TRACE_SF_qdqLdd(
          WPP_GLOBAL_Control->AttachedDevice,
          (_DWORD)v9,
          (_DWORD)v4,
          *(_QWORD *)(v5 + 672),
          v46,
          v47,
          v48,
          v49,
          *(_QWORD *)(*((_QWORD *)p_CurrentIrp + 8) + 32LL),
          p_CurrentIrp[2],
          *((_QWORD *)p_CurrentIrp + 6),
          v18,
          *(_BYTE *)(v5 + 588),
          *((_BYTE *)p_CurrentIrp + 73));
      switch ( *p_CurrentIrp )
      {
        case 1u:
          if ( (unsigned int)Feature_HPPICNS__private_IsEnabledDeviceUsageNoInline(*p_CurrentIrp - 1, v9, v4)
            && (_BYTE)MinorFunction == 2 )
          {
            v19 = WPP_GLOBAL_Control;
            LOBYTE(v9) = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
                      && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u;
            LOBYTE(v4) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
            if ( (_BYTE)v9 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
              WPP_RECORDER_AND_TRACE_SF_qdq(
                WPP_GLOBAL_Control->AttachedDevice,
                (_DWORD)v9,
                (_DWORD)v4,
                *(_QWORD *)(v5 + 672),
                3,
                4,
                68,
                (__int64)WPP_09551ba6d0fe3383c1d3f23d6d3d8f25_Traceguids,
                *(_QWORD *)(*((_QWORD *)p_CurrentIrp + 8) + 32LL),
                p_CurrentIrp[2],
                *((_QWORD *)p_CurrentIrp + 6));
            goto LABEL_98;
          }
LABEL_59:
          if ( (unsigned int)Feature_HPPICNS__private_IsEnabledDeviceUsageNoInline(v19, v9, v4)
            && (_BYTE)MinorFunction == 2 )
          {
            goto LABEL_98;
          }
LABEL_61:
          v19 = WPP_GLOBAL_Control;
          LOBYTE(v9) = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
                    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u;
          LOBYTE(v4) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
          if ( (_BYTE)v9 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
            WPP_RECORDER_AND_TRACE_SF_qdqL(
              WPP_GLOBAL_Control->AttachedDevice,
              (_DWORD)v9,
              (_DWORD)v4,
              *(_QWORD *)(v5 + 672),
              2,
              4,
              69,
              (__int64)WPP_09551ba6d0fe3383c1d3f23d6d3d8f25_Traceguids,
              *(_QWORD *)(*((_QWORD *)p_CurrentIrp + 8) + 32LL),
              p_CurrentIrp[2],
              *((_QWORD *)p_CurrentIrp + 6),
              *p_CurrentIrp);
          goto LABEL_97;
        case 3u:
          HidpPdoUnregisterDeviceInterface(p_CurrentIrp, v9, v4);
          break;
        case 5u:
          break;
        default:
          v19 = (PDEVICE_OBJECT)(*p_CurrentIrp - 6);
          if ( *p_CurrentIrp == 6 )
            goto LABEL_97;
          if ( *p_CurrentIrp != 7 )
            goto LABEL_61;
          goto LABEL_59;
      }
      v50[0] = 0;
      CompleteAllPendingReadsForPdo(p_CurrentIrp, v9, v4);
      v20 = *(char **)(v5 + 152);
      if ( v20 && v20 != MmBadPointer )
        HidpFreePowerEventIrp(&v20[424 * p_CurrentIrp[3]]);
      *((_QWORD *)&v50[0] + 1) = v50;
      *(_QWORD *)&v50[0] = v50;
      DequeueAllPowerDelayedIrpsForPdo(p_CurrentIrp, v50);
      while ( 1 )
      {
        v21 = *(_QWORD *)&v50[0];
        if ( *(_OWORD **)&v50[0] == v50 )
          break;
        if ( *(_OWORD **)(*(_QWORD *)&v50[0] + 8LL) != v50
          || (v22 = **(_QWORD **)&v50[0], *(_QWORD *)(**(_QWORD **)&v50[0] + 8LL) != *(_QWORD *)&v50[0]) )
        {
          __fastfail(3u);
        }
        *(_QWORD *)&v50[0] = **(_QWORD **)&v50[0];
        *(_QWORD *)(v22 + 8) = v50;
        v23 = (IRP *)(v21 - 168);
        v23->IoStatus.Status = -1073741810;
        IofCompleteRequest(v23, 0);
      }
      HidpFdoCancelPdoDeviceResetNotifications(v5, p_CurrentIrp);
      HidpFdoCancelPdoDevicePresenceNotifications(v5, p_CurrentIrp);
      CheckAndRecoverFromStopS0IdleLeak(v5, p_CurrentIrp);
      v19 = WPP_GLOBAL_Control;
      LOBYTE(v9) = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
                && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u;
      LOBYTE(v4) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      if ( (_BYTE)v9 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        WPP_RECORDER_AND_TRACE_SF_qdqL(
          WPP_GLOBAL_Control->AttachedDevice,
          (_DWORD)v9,
          (_DWORD)v4,
          *(_QWORD *)(v5 + 672),
          4,
          4,
          67,
          (__int64)WPP_09551ba6d0fe3383c1d3f23d6d3d8f25_Traceguids,
          *(_QWORD *)(*((_QWORD *)p_CurrentIrp + 8) + 32LL),
          p_CurrentIrp[2],
          *((_QWORD *)p_CurrentIrp + 6),
          p_CurrentIrp[34]);
LABEL_97:
      if ( (_BYTE)MinorFunction != 2 )
        goto LABEL_21;
LABEL_98:
      if ( (unsigned int)Feature_HPPICNS__private_IsEnabledDeviceUsageNoInline(v19, v9, v4) )
      {
        v24 = *((_BYTE *)p_CurrentIrp + 73);
        HidpPdoRemoveDevice(v5, p_CurrentIrp);
        if ( !v24 )
        {
          if ( (unsigned __int8)AllCollectionPDOsInitialized(v5) )
          {
            LOBYTE(v25) = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                       && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
                       && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u;
            LOBYTE(v26) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
            if ( (_BYTE)v25 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
              WPP_RECORDER_AND_TRACE_SF_q(
                WPP_GLOBAL_Control->AttachedDevice,
                v25,
                v26,
                *(_QWORD *)(v5 + 672),
                4,
                4,
                70,
                (__int64)WPP_09551ba6d0fe3383c1d3f23d6d3d8f25_Traceguids,
                *(_QWORD *)v5);
            LOBYTE(v25) = 1;
            HidpFdoUpdatePdosInStableState(v5, v25, v26);
          }
          else
          {
            LOBYTE(v25) = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                       && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
                       && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u;
            if ( (_BYTE)v25 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
            {
              LOBYTE(v26) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
              WPP_RECORDER_AND_TRACE_SF_q(
                WPP_GLOBAL_Control->AttachedDevice,
                v25,
                v26,
                *(_QWORD *)(v5 + 672),
                3,
                4,
                71,
                (__int64)WPP_09551ba6d0fe3383c1d3f23d6d3d8f25_Traceguids,
                *(_QWORD *)v5);
            }
          }
        }
      }
      else
      {
        HidpPdoRemoveDevice(v5, p_CurrentIrp);
      }
      goto LABEL_21;
    case 3:
      if ( p_CurrentIrp[1] == 6 )
      {
        v27 = *p_CurrentIrp;
        p_CurrentIrp[1] = *p_CurrentIrp;
        if ( v27 == 3 )
          HidpPdoRegisterDeviceInterface(p_CurrentIrp, v9, &WPP_GLOBAL_Control);
      }
      goto LABEL_21;
    case 4:
      if ( !(unsigned int)Feature_HPPICNS__private_IsEnabledDeviceUsageNoInline(a1, v9, &WPP_GLOBAL_Control) )
      {
        if ( *p_CurrentIrp == 1 )
          goto LABEL_21;
        goto LABEL_32;
      }
      v15 = *p_CurrentIrp;
      if ( (_DWORD)v15 != 1 && (_DWORD)v15 != 7 )
      {
LABEL_32:
        HidpPdoUnregisterDeviceInterface(p_CurrentIrp, v14, v15);
        HidpFreePowerEventIrp(*(_QWORD *)(v5 + 152) + 424LL * p_CurrentIrp[3]);
        v16 = (void (__fastcall *)(_QWORD, __int64))*((_QWORD *)p_CurrentIrp + 15);
        p_CurrentIrp[1] = 5;
        if ( v16 && v16 != MmBadPointer )
          v16(*((_QWORD *)p_CurrentIrp + 16), 1);
        goto LABEL_21;
      }
      v17 = WPP_GLOBAL_Control;
      LOBYTE(v14) = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                 && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 8u)
                 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u;
      if ( (_BYTE)v14 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        WPP_RECORDER_AND_TRACE_SF_qdqLL(
          WPP_GLOBAL_Control->AttachedDevice,
          v14,
          WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED,
          *(_QWORD *)(v5 + 672),
          v46,
          v47,
          v48,
          v49,
          *(_QWORD *)(*((_QWORD *)p_CurrentIrp + 8) + 32LL),
          p_CurrentIrp[2],
          *((_QWORD *)p_CurrentIrp + 6),
          v15,
          p_CurrentIrp[1]);
      MicrosoftTelemetryAssertTriggeredArgsMsgKM(
        v17,
        (*p_CurrentIrp << 16) | (unsigned __int16)p_CurrentIrp[1],
        *(unsigned __int16 *)(v5 + 110) | (*(unsigned __int16 *)(v5 + 108) << 16),
        "Unexpected PDO prevState at PDO IRP_MN_STOP_DEVICE");
LABEL_21:
      started = 0;
LABEL_22:
      v6->IoStatus.Status = started;
      IofCompleteRequest(v6, 0);
      return (unsigned int)started;
    case 5:
      *p_CurrentIrp = p_CurrentIrp[1];
      p_CurrentIrp[1] = 4;
      goto LABEL_21;
    case 6:
      if ( p_CurrentIrp[1] == 4 )
        p_CurrentIrp[1] = *p_CurrentIrp;
      goto LABEL_21;
    case 7:
      if ( CurrentStackLocation->Parameters.Read.Length != 4 )
        goto LABEL_175;
      Pool2 = ExAllocatePool2(256, 16, 1130654024);
      if ( Pool2 )
      {
        ObfReferenceObject(*((PVOID *)p_CurrentIrp + 6));
        *(_QWORD *)(Pool2 + 8) = *((_QWORD *)p_CurrentIrp + 6);
        *(_DWORD *)Pool2 = 1;
        v6->IoStatus.Information = Pool2;
        goto LABEL_21;
      }
      started = -1073741670;
      goto LABEL_176;
    case 8:
      v35 = v6->Tail.Overlay.CurrentStackLocation;
      SecurityContext = v35->Parameters.Create.SecurityContext;
      if ( SecurityContext->SecurityQos == *(_SECURITY_QUALITY_OF_SERVICE **)&GUID_HID_INTERFACE_NOTIFY.Data1
        && SecurityContext->AccessState == *(_ACCESS_STATE **)GUID_HID_INTERFACE_NOTIFY.Data4 )
      {
        ByteOffset = v35->Parameters.Read.ByteOffset;
        if ( *(_WORD *)ByteOffset.QuadPart == 48 )
        {
          if ( *(_WORD *)(ByteOffset.QuadPart + 2) )
          {
            v38 = *(_QWORD *)(ByteOffset.QuadPart + 32);
            if ( v38 )
            {
              p_Type[19] = v38;
              p_Type[20] = *(_QWORD *)(ByteOffset.QuadPart + 40);
              started = 0;
              goto LABEL_176;
            }
          }
        }
        goto LABEL_175;
      }
      if ( SecurityContext->SecurityQos == *(_SECURITY_QUALITY_OF_SERVICE **)&GUID_HID_INTERFACE_HIDPARSE.Data1
        && SecurityContext->AccessState == *(_ACCESS_STATE **)GUID_HID_INTERFACE_HIDPARSE.Data4 )
      {
        v39 = v35->Parameters.Read.ByteOffset;
        if ( *(_WORD *)v39.QuadPart == 40 && *(_WORD *)(v39.QuadPart + 2) )
        {
          started = 0;
          *(_QWORD *)(v39.QuadPart + 32) = HidP_GetCaps;
          goto LABEL_176;
        }
        goto LABEL_175;
      }
      v40 = p_Type[12];
      if ( *(_BYTE *)(*(_QWORD *)(v40 + 40) + 296LL)
        || !*(_BYTE *)(v40 + 2010)
        || SecurityContext->SecurityQos != *(_SECURITY_QUALITY_OF_SERVICE **)&GUID_REENUMERATE_SELF_INTERFACE_STANDARD.Data1
        || SecurityContext->AccessState != *(_ACCESS_STATE **)GUID_REENUMERATE_SELF_INTERFACE_STANDARD.Data4 )
      {
LABEL_175:
        started = v6->IoStatus.Status;
        goto LABEL_176;
      }
      if ( v35->Parameters.QueryInterface.Size == 40 )
      {
        if ( v35->Parameters.QueryInterface.Version == 1 )
        {
          v41 = v35->Parameters.Read.ByteOffset;
          if ( v41.QuadPart )
          {
            *(_QWORD *)(v41.QuadPart + 8) = p_Type;
            *(_QWORD *)(v41.QuadPart + 16) = HidpPdoReenumerateSelfInterfaceDereference;
            started = 0;
            *(_DWORD *)v41.QuadPart = 65576;
            *(_QWORD *)(v41.QuadPart + 24) = HidpPdoReenumerateSelfInterfaceDereference;
            *(_QWORD *)(v41.QuadPart + 32) = HidpPdoReenumerateSelfInterfaceSurpriseRemoveAndReenumerateSelf;
          }
          else
          {
            started = -1073741811;
          }
        }
        else
        {
          started = -1073741811;
        }
      }
      else
      {
        started = -1073741811;
      }
LABEL_176:
      v6->IoStatus.Status = started;
      IofCompleteRequest(v6, 0);
      if ( (int)(started + 0x80000000) >= 0 && started != -1073741637 )
      {
        switch ( MinorFunction )
        {
          case 0:
          case 1:
          case 2:
          case 3:
          case 4:
          case 5:
          case 6:
          case 8:
          case 9:
          case 19:
          case 20:
          case 23:
            LOBYTE(v43) = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                       && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
                       && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u;
            if ( (_BYTE)v43 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
            {
              LOBYTE(v44) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
              WPP_RECORDER_AND_TRACE_SF_qdqqccd(
                WPP_GLOBAL_Control->AttachedDevice,
                v43,
                v44,
                *(_QWORD *)(v5 + 672),
                v46,
                4,
                72,
                (__int64)WPP_09551ba6d0fe3383c1d3f23d6d3d8f25_Traceguids,
                *(_QWORD *)(*((_QWORD *)p_CurrentIrp + 8) + 32LL),
                p_CurrentIrp[2],
                *((_QWORD *)p_CurrentIrp + 6),
                (char)v6,
                27,
                MinorFunction,
                started);
            }
            break;
          default:
            return (unsigned int)started;
        }
      }
      return (unsigned int)started;
    case 9:
      ProviderId = v9->CurrentStackLocation->Parameters.WMI.ProviderId;
      if ( ProviderId )
      {
        v29 = *((_QWORD *)p_CurrentIrp + 8);
        v30 = 0;
        *(_OWORD *)ProviderId = *(_OWORD *)(v29 + 328);
        *(_OWORD *)(ProviderId + 16) = *(_OWORD *)(v29 + 344);
        *(_OWORD *)(ProviderId + 32) = *(_OWORD *)(v29 + 360);
        *(_OWORD *)(ProviderId + 48) = *(_OWORD *)(v29 + 376);
        v31 = *(_DWORD *)(ProviderId + 4) & 0xFFFFFF03 | 0x80;
        *(_DWORD *)(ProviderId + 4) = v31;
        *(_DWORD *)(ProviderId + 8) = p_CurrentIrp[2];
        if ( !*((_BYTE *)p_CurrentIrp + 256) )
          v30 = 256;
        v32 = v31 & 0xFFFFFEFF | v30 | 0x200;
        *(_DWORD *)(ProviderId + 4) = v32;
        v33 = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
           && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
           && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u;
        LOBYTE(v4) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
                  && LOWORD(WPP_GLOBAL_Control->DeviceType);
        if ( v33 || (_BYTE)v4 )
          WPP_RECORDER_AND_TRACE_SF_qLLdddd(
            WPP_GLOBAL_Control->AttachedDevice,
            v33,
            (_DWORD)v4,
            *(_QWORD *)(v29 + 704),
            v46,
            v47,
            v48,
            v49,
            *(_QWORD *)(v29 + 32),
            *(_DWORD *)(ProviderId + 44),
            *(_DWORD *)(ProviderId + 48),
            (v32 & 0x400) != 0,
            (v32 & 0x800) != 0,
            (v32 & 0x1000) != 0,
            (v32 & 0x2000) != 0);
        started = 0;
        v6->IoStatus.Information = ProviderId;
      }
      else
      {
        started = -1073741438;
        v6->IoStatus.Information = 0;
      }
      goto LABEL_176;
    case 19:
      started = HidpQueryIdForClientPdo(p_Type, v6, &WPP_GLOBAL_Control);
      goto LABEL_176;
    case 20:
      if ( p_CurrentIrp[1] == 4 )
      {
        v6->IoStatus.Information |= 4u;
      }
      else if ( p_CurrentIrp[1] == 6 )
      {
        v6->IoStatus.Information |= 1u;
      }
      else if ( p_CurrentIrp[1] - 7 <= 1 )
      {
        v6->IoStatus.Information |= 8u;
      }
      goto LABEL_21;
    case 21:
      v42 = ExAllocatePool2(64, 24, 1130654024);
      if ( v42 )
      {
        *(_DWORD *)(v42 + 16) = 15;
        started = 0;
        *(GUID *)v42 = GUID_BUS_TYPE_HID;
        *(_DWORD *)(v42 + 20) = *(_DWORD *)(v5 + 512);
        v6->IoStatus.Information = v42;
      }
      else
      {
        started = -1073741670;
        v6->IoStatus.Information = 0;
      }
      goto LABEL_176;
    case 25:
      started = PoDirectedDripsSetDeviceFlags(*((_QWORD *)p_CurrentIrp + 6), 10);
      if ( started >= 0 )
        goto LABEL_22;
      LOBYTE(v10) = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                 && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 8u)
                 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u;
      if ( (_BYTE)v10 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v12) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
        WPP_RECORDER_AND_TRACE_SF_qdqL(
          WPP_GLOBAL_Control->AttachedDevice,
          v10,
          v12,
          *(_QWORD *)(v5 + 672),
          2,
          9,
          64,
          (__int64)WPP_09551ba6d0fe3383c1d3f23d6d3d8f25_Traceguids,
          *(_QWORD *)(*((_QWORD *)p_CurrentIrp + 8) + 32LL),
          p_CurrentIrp[2],
          *((_QWORD *)p_CurrentIrp + 6),
          started);
      }
      goto LABEL_21;
    default:
      goto LABEL_175;
  }
}

```

## disassembly

```asm
0x18003e5b0  push    rbx
0x18003e5b2  push    rbp
0x18003e5b3  push    rsi
0x18003e5b4  push    rdi
0x18003e5b5  push    r12
0x18003e5b7  push    r13
0x18003e5b9  push    r14
0x18003e5bb  push    r15
0x18003e5bd  sub     rsp, 98h
0x18003e5c4  mov     rbp, [rdx+0B8h]
0x18003e5cb  lea     rdi, [rcx+20h]
0x18003e5cf  mov     r14, [rdi+40h]
0x18003e5d3  lea     r8, WPP_GLOBAL_Control
0x18003e5da  add     r14, 20h ; ' '
0x18003e5de  lea     r10, WPP_RECORDER_INITIALIZED
0x18003e5e5  mov     rsi, rdx
0x18003e5e8  lea     r11, WPP_09551ba6d0fe3383c1d3f23d6d3d8f25_Traceguids
0x18003e5ef  movzx   r12d, byte ptr [rbp+1]
0x18003e5f4  lea     r13, cs:180000000h
0x18003e5fb  mov     rbx, rcx
0x18003e5fe  cmp     r12d, 17h; switch 24 cases
0x18003e602  ja      def_18003E61F; jumptable 000000018003E61F default case, cases 7,10-18,21,22
0x18003e608  movsxd  rax, r12d
0x18003e60b  movzx   eax, ds:(byte_18002C608 - 180000000h)[rax+r13]
0x18003e614  mov     ecx, ds:(jpt_18003E61F - 180000000h)[r13+rax*4]
0x18003e61c  add     rcx, r13
0x18003e61f  jmp     rcx; switch jump
0x18003e625  mov     rcx, cs:WPP_GLOBAL_Control; jumptable 000000018003E61F cases 0-6,8,9,19,20,23
0x18003e62c  cmp     rcx, r8
0x18003e62f  jz      short loc_18003E642
0x18003e631  mov     eax, [rcx+2Ch]
0x18003e634  test    al, 8
0x18003e636  jz      short loc_18003E642
0x18003e638  cmp     byte ptr [rcx+29h], 4
0x18003e63c  jb      short loc_18003E642
0x18003e63e  mov     dl, 1
0x18003e640  jmp     short loc_18003E644
0x18003e642  xor     dl, dl
0x18003e644  cmp     cs:WPP_RECORDER_INITIALIZED, r10
0x18003e64b  setnz   r8b
0x18003e64f  test    dl, dl
0x18003e651  jnz     short loc_18003E658
0x18003e653  test    r8b, r8b
0x18003e656  jz      short loc_18003E6AF
0x18003e658  mov     rax, [rdi+30h]
0x18003e65c  mov     r9, [r14+2A0h]
0x18003e663  mov     rcx, [rcx+18h]
0x18003e667  mov     byte ptr [rsp+0D8h+var_70], r12b
0x18003e66c  mov     byte ptr [rsp+0D8h+var_78], 1Bh
0x18003e671  mov     [rsp+0D8h+var_80], rsi
0x18003e676  mov     [rsp+0D8h+var_88], rax
0x18003e67b  mov     eax, [rdi+8]
0x18003e67e  mov     [rsp+0D8h+var_90], eax
0x18003e682  mov     rax, [r14]
0x18003e685  mov     [rsp+0D8h+var_98], rax
0x18003e68a  mov     [rsp+0D8h+var_A0], r11
0x18003e68f  mov     [rsp+0D8h+var_A8], 3Fh ; '?'
0x18003e696  mov     [rsp+0D8h+var_B0], 4
0x18003e69e  mov     [rsp+0D8h+var_B8], 4
0x18003e6a3  call    WPP_RECORDER_AND_TRACE_SF_qdqqcc
0x18003e6a8  lea     r10, WPP_RECORDER_INITIALIZED
0x18003e6af  lea     rdx, [rsi+0B8h]
0x18003e6b6  lea     r8, WPP_GLOBAL_Control
0x18003e6bd  jmp     short loc_18003E6D0
0x18003e6bf  add     rdx, 0B8h; jumptable 000000018003E61F default case, cases 7,10-18,21,22
0x18003e6c6  cmp     r12d, 19h; switch 26 cases
0x18003e6ca  ja      def_18003E6DE; jumptable 000000018003E6DE default case, cases 10-18,22,24
0x18003e6d0  movsxd  rax, r12d
0x18003e6d3  mov     ecx, ds:(jpt_18003E6DE - 180000000h)[r13+rax*4]
0x18003e6db  add     rcx, r13
0x18003e6de  jmp     rcx; switch jump
0x18003e6e4  mov     rcx, [rdi+30h]; jumptable 000000018003E6DE case 25
0x18003e6e8  mov     edx, 0Ah
0x18003e6ed  call    cs:__imp_PoDirectedDripsSetDeviceFlags
0x18003e6f4  nop     dword ptr [rax+rax+00h]
0x18003e6f9  mov     ebx, eax
0x18003e6fb  test    eax, eax
0x18003e6fd  jns     loc_18003E799
0x18003e703  mov     r10, cs:WPP_GLOBAL_Control
0x18003e70a  lea     rax, WPP_GLOBAL_Control
0x18003e711  cmp     r10, rax
0x18003e714  jz      short loc_18003E729
0x18003e716  bt      dword ptr [r10+2Ch], 8
0x18003e71c  jnb     short loc_18003E729
0x18003e71e  cmp     byte ptr [r10+29h], 2
0x18003e723  jb      short loc_18003E729
0x18003e725  mov     dl, 1
0x18003e727  jmp     short loc_18003E72B
0x18003e729  xor     dl, dl
0x18003e72b  lea     rax, WPP_RECORDER_INITIALIZED
0x18003e732  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x18003e739  setnz   r8b
0x18003e73d  test    dl, dl
0x18003e73f  jnz     short loc_18003E746
0x18003e741  test    r8b, r8b
0x18003e744  jz      short loc_18003E797
0x18003e746  mov     rax, [rdi+30h]
0x18003e74a  lea     r13, WPP_09551ba6d0fe3383c1d3f23d6d3d8f25_Traceguids
0x18003e751  mov     r9, [rdi+40h]
0x18003e755  mov     rcx, [r10+18h]
0x18003e759  mov     dword ptr [rsp+0D8h+var_80], ebx
0x18003e75d  mov     [rsp+0D8h+var_88], rax
0x18003e762  mov     eax, [rdi+8]
0x18003e765  mov     [rsp+0D8h+var_90], eax
0x18003e769  mov     rax, [r9+20h]
0x18003e76d  mov     r9, [r14+2A0h]
0x18003e774  mov     [rsp+0D8h+var_98], rax
0x18003e779  mov     [rsp+0D8h+var_A0], r13
0x18003e77e  mov     [rsp+0D8h+var_A8], 40h ; '@'
0x18003e785  mov     [rsp+0D8h+var_B0], 9
0x18003e78d  mov     [rsp+0D8h+var_B8], 2
0x18003e792  call    WPP_RECORDER_AND_TRACE_SF_qdqL
0x18003e797  xor     ebx, ebx
0x18003e799  xor     edx, edx; PriorityBoost
0x18003e79b  mov     [rsi+30h], ebx
0x18003e79e  mov     rcx, rsi; Irp
0x18003e7a1  call    cs:__imp_IofCompleteRequest
0x18003e7a8  nop     dword ptr [rax+rax+00h]
0x18003e7ad  jmp     def_18003F1F3; jumptable 000000018003F1F3 default case, cases 7,10-18,21,22
0x18003e7b2  mov     rdx, rdi; jumptable 000000018003E6DE case 0
0x18003e7b5  mov     rcx, r14
0x18003e7b8  call    HidpPdoStartDevice
0x18003e7bd  mov     ebx, eax
0x18003e7bf  test    eax, eax
0x18003e7c1  js      loc_18003F1A5
0x18003e7c7  mov     rax, [rdi+78h]
0x18003e7cb  test    rax, rax
0x18003e7ce  jz      loc_18003F1A5
0x18003e7d4  mov     rcx, cs:MmBadPointer
0x18003e7db  cmp     rax, [rcx]
0x18003e7de  jz      loc_18003F1A5
0x18003e7e4  mov     rcx, [rdi+80h]
0x18003e7eb  xor     edx, edx
0x18003e7ed  call    _guard_dispatch_icall
0x18003e7f2  jmp     short loc_18003E799
0x18003e7f4  mov     eax, [rdi+4]; jumptable 000000018003E6DE case 5
0x18003e7f7  mov     [rdi], eax
0x18003e7f9  mov     dword ptr [rdi+4], 4
0x18003e800  jmp     short loc_18003E797
0x18003e802  cmp     dword ptr [rdi+4], 4; jumptable 000000018003E6DE case 6
0x18003e806  jnz     short loc_18003E797
0x18003e808  mov     eax, [rdi]
0x18003e80a  mov     [rdi+4], eax
0x18003e80d  jmp     short loc_18003E797
0x18003e80f  call    Feature_HPPICNS__private_IsEnabledDeviceUsageNoInline; jumptable 000000018003E6DE case 4
0x18003e814  test    eax, eax
0x18003e816  jnz     short loc_18003E879
0x18003e818  cmp     dword ptr [rdi], 1
0x18003e81b  jz      loc_18003E797
0x18003e821  mov     rcx, rdi
0x18003e824  call    HidpPdoUnregisterDeviceInterface
0x18003e829  mov     eax, [rdi+0Ch]
0x18003e82c  imul    rcx, rax, 1A8h
0x18003e833  add     rcx, [r14+98h]
0x18003e83a  call    HidpFreePowerEventIrp
0x18003e83f  mov     rax, [rdi+78h]
0x18003e843  mov     dword ptr [rdi+4], 5
0x18003e84a  test    rax, rax
0x18003e84d  jz      loc_18003E797
0x18003e853  mov     rcx, cs:MmBadPointer
0x18003e85a  cmp     rax, [rcx]
0x18003e85d  jz      loc_18003E797
0x18003e863  mov     rcx, [rdi+80h]
0x18003e86a  mov     edx, 1
0x18003e86f  call    _guard_dispatch_icall
0x18003e874  jmp     loc_18003E797
0x18003e879  mov     r8d, [rdi]
0x18003e87c  cmp     r8d, 1
0x18003e880  jz      short loc_18003E888
0x18003e882  cmp     r8d, 7
0x18003e886  jnz     short loc_18003E821
0x18003e888  mov     rcx, cs:WPP_GLOBAL_Control
0x18003e88f  lea     rax, WPP_GLOBAL_Control
0x18003e896  cmp     rcx, rax
0x18003e899  jz      short loc_18003E8AC
0x18003e89b  bt      dword ptr [rcx+2Ch], 8
0x18003e8a0  jnb     short loc_18003E8AC
0x18003e8a2  cmp     byte ptr [rcx+29h], 2
0x18003e8a6  jb      short loc_18003E8AC
0x18003e8a8  mov     dl, 1
0x18003e8aa  jmp     short loc_18003E8AE
0x18003e8ac  xor     dl, dl
0x18003e8ae  lea     rax, WPP_RECORDER_INITIALIZED
0x18003e8b5  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x18003e8bc  setnz   r10b
0x18003e8c0  test    dl, dl
0x18003e8c2  jnz     short loc_18003E8C9
0x18003e8c4  test    r10b, r10b
0x18003e8c7  jz      short loc_18003E906
0x18003e8c9  mov     eax, [rdi+4]
0x18003e8cc  mov     r9, [rdi+40h]
0x18003e8d0  mov     rcx, [rcx+18h]
0x18003e8d4  mov     [rsp+0D8h+var_78], eax
0x18003e8d8  mov     rax, [rdi+30h]
0x18003e8dc  mov     dword ptr [rsp+0D8h+var_80], r8d
0x18003e8e1  movzx   r8d, r10b
0x18003e8e5  mov     [rsp+0D8h+var_88], rax
0x18003e8ea  mov     eax, [rdi+8]
0x18003e8ed  mov     [rsp+0D8h+var_90], eax
0x18003e8f1  mov     rax, [r9+20h]
0x18003e8f5  mov     r9, [r14+2A0h]
0x18003e8fc  mov     [rsp+0D8h+var_98], rax
0x18003e901  call    WPP_RECORDER_AND_TRACE_SF_qdqLL
0x18003e906  movzx   eax, word ptr [r14+6Eh]; __annotation("Debug", "TelemetryAssert", "FALSE", "Unexpected PDO prevState at PDO IRP_MN_STOP_DEVICE")
0x18003e90b  lea     r9, aUnexpectedPdoP; "Unexpected PDO prevState at PDO IRP_MN_"...
0x18003e912  movzx   r8d, word ptr [r14+6Ch]
0x18003e917  shl     r8d, 10h
0x18003e91b  or      r8d, eax
0x18003e91e  mov     eax, [rdi+4]
0x18003e921  movzx   edx, ax
0x18003e924  mov     eax, [rdi]
0x18003e926  shl     eax, 10h
0x18003e929  or      edx, eax
0x18003e92b  call    MicrosoftTelemetryAssertTriggeredArgsMsgKM
0x18003e930  jmp     loc_18003E797
0x18003e935  mov     r11d, [rdi+4]; jumptable 000000018003E6DE cases 1,2,23
0x18003e939  mov     [rdi], r11d
0x18003e93c  mov     dword ptr [rdi+4], 6
0x18003e943  mov     rcx, cs:WPP_GLOBAL_Control
0x18003e94a  lea     rbp, WPP_GLOBAL_Control
0x18003e951  cmp     rcx, rbp
0x18003e954  jz      short loc_18003E967
0x18003e956  mov     eax, [rcx+2Ch]
0x18003e959  test    al, 8
0x18003e95b  jz      short loc_18003E967
0x18003e95d  cmp     byte ptr [rcx+29h], 4
0x18003e961  jb      short loc_18003E967
0x18003e963  mov     dl, 1
0x18003e965  jmp     short loc_18003E969
0x18003e967  xor     dl, dl
0x18003e969  lea     r15, WPP_RECORDER_INITIALIZED
0x18003e970  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x18003e977  setnz   r8b
0x18003e97b  test    dl, dl
0x18003e97d  jnz     short loc_18003E984
0x18003e97f  test    r8b, r8b
0x18003e982  jz      short loc_18003E9CB
0x18003e984  movzx   eax, byte ptr [rdi+49h]
0x18003e988  movzx   r9d, byte ptr [r14+24Ch]
0x18003e990  mov     r10, [rdi+40h]
0x18003e994  mov     rcx, [rcx+18h]
0x18003e998  mov     [rsp+0D8h+var_70], eax
0x18003e99c  mov     rax, [rdi+30h]
0x18003e9a0  mov     [rsp+0D8h+var_78], r9d
0x18003e9a5  mov     r9, [r14+2A0h]
0x18003e9ac  mov     dword ptr [rsp+0D8h+var_80], r11d
0x18003e9b1  mov     [rsp+0D8h+var_88], rax
0x18003e9b6  mov     eax, [rdi+8]
0x18003e9b9  mov     [rsp+0D8h+var_90], eax
0x18003e9bd  mov     rax, [r10+20h]
0x18003e9c1  mov     [rsp+0D8h+var_98], rax
0x18003e9c6  call    WPP_RECORDER_AND_TRACE_SF_qdqLdd
0x18003e9cb  mov     ecx, [rdi]
0x18003e9cd  sub     ecx, 1
0x18003e9d0  jz      loc_18003EBC9
0x18003e9d6  sub     ecx, 2
0x18003e9d9  jz      short loc_18003EA2D
0x18003e9db  sub     ecx, 2
0x18003e9de  jz      short loc_18003EA35
0x18003e9e0  sub     ecx, 1
0x18003e9e3  jz      loc_18003ECD4
0x18003e9e9  cmp     ecx, 1
0x18003e9ec  jnz     short loc_18003EA01
0x18003e9ee  call    Feature_HPPICNS__private_IsEnabledDeviceUsageNoInline
0x18003e9f3  test    eax, eax
0x18003e9f5  jz      short loc_18003EA01
0x18003e9f7  cmp     r12b, 2
0x18003e9fb  jz      loc_18003ECE7
0x18003ea01  mov     rcx, cs:WPP_GLOBAL_Control
0x18003ea08  cmp     rcx, rbp
0x18003ea0b  jz      loc_18003EC69
0x18003ea11  mov     eax, [rcx+2Ch]
0x18003ea14  test    al, 8
0x18003ea16  jz      loc_18003EC69
0x18003ea1c  cmp     byte ptr [rcx+29h], 2
0x18003ea20  jb      loc_18003EC69
0x18003ea26  mov     dl, 1
0x18003ea28  jmp     loc_18003EC6B
0x18003ea2d  mov     rcx, rdi
0x18003ea30  call    HidpPdoUnregisterDeviceInterface
0x18003ea35  xorps   xmm0, xmm0
0x18003ea38  mov     rcx, rdi
0x18003ea3b  movups  [rsp+0D8h+var_58], xmm0
0x18003ea43  call    CompleteAllPendingReadsForPdo
0x18003ea48  mov     rdx, [r14+98h]
0x18003ea4f  test    rdx, rdx
0x18003ea52  jz      short loc_18003EA72
0x18003ea54  mov     rax, cs:MmBadPointer
0x18003ea5b  cmp     rdx, [rax]
0x18003ea5e  jz      short loc_18003EA72
0x18003ea60  mov     eax, [rdi+0Ch]
0x18003ea63  imul    rcx, rax, 1A8h
0x18003ea6a  add     rcx, rdx
0x18003ea6d  call    HidpFreePowerEventIrp
0x18003ea72  lea     rax, [rsp+0D8h+var_58]
0x18003ea7a  mov     rcx, rdi
0x18003ea7d  mov     qword ptr [rsp+0D8h+var_58+8], rax
0x18003ea85  lea     rdx, [rsp+0D8h+var_58]
0x18003ea8d  lea     rax, [rsp+0D8h+var_58]
0x18003ea95  mov     qword ptr [rsp+0D8h+var_58], rax
  ... truncated ...
```
