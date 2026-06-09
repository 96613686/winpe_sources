# ndisDevicePowerOn(void *)

- ea: `0x14017a4a0`
- end: `0x14017b218`
- name: `?ndisDevicePowerOn@@YAXPEAX@Z`
- size: `3448`
- prototype: `void __fastcall(void *)`
- caller_count: `0`
- callee_count: `47`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x140012a70`
- `0x140015280`
- `0x140015530`
- `0x140016a10`
- `0x14001cc80`
- `0x14001cf50`
- `0x14001d030`
- `0x14001d350`
- `0x1400388e0`
- `0x140039d00`
- `0x14003a720`
- `0x14003cde0`
- `0x14003d920`
- `0x14003ef00`
- `0x14003f330`
- `0x1400423f0`
- `0x14004e050`
- `0x140050410`
- `0x1400527c0`
- `0x140055f20`
- `0x1400568a0`
- `0x14005edf0`
- `0x140068220`
- `0x14006d9b0`
- `0x14006f2e0`
- `0x14007b4e0`
- `0x1400837ac`
- `0x140083b50`
- `0x140085e90`
- `0x14008742c`
- `0x1400a5e08`
- `0x1400e6160`
- `0x1400e65c0`
- `0x140136f20`
- `0x14014c244`
- `0x140154f70`
- `0x140156b40`
- `0x140156e50`
- `0x140156f20`
- `0x140157750`
- `0x140157dc0`
- `0x140163170`
- `0x140164280`
- `0x1401669d0`
- `0x1401747a8`
- `0x140178730`
- `0x14017a4a0`

## import_xrefs

- `ntoskrnl!KeLowerIrql` at `0x14017afa7`
- `ntoskrnl!KeLowerIrql` at `0x14017afa7`
- `ntoskrnl!PoSetPowerState` at `0x14017a64f`
- `ntoskrnl!PoSetPowerState` at `0x14017ac87`
- `ntoskrnl!PoSetPowerState` at `0x14017a64f`
- `ntoskrnl!PoSetPowerState` at `0x14017ac87`
- `ntoskrnl!IofCompleteRequest` at `0x14017a676`
- `ntoskrnl!IofCompleteRequest` at `0x14017a70c`
- `ntoskrnl!IofCompleteRequest` at `0x14017ad2b`
- `ntoskrnl!IofCompleteRequest` at `0x14017a676`
- `ntoskrnl!IofCompleteRequest` at `0x14017a70c`
- `ntoskrnl!IofCompleteRequest` at `0x14017ad2b`
- `ntoskrnl!KeReleaseSpinLock` at `0x14017a8ff`
- `ntoskrnl!KeReleaseSpinLock` at `0x14017a9a7`
- `ntoskrnl!KeReleaseSpinLock` at `0x14017a9e2`
- `ntoskrnl!KeReleaseSpinLock` at `0x14017ab66`
- `ntoskrnl!KeReleaseSpinLock` at `0x14017ad02`
- `ntoskrnl!KeReleaseSpinLock` at `0x14017ae78`
- `ntoskrnl!KeReleaseSpinLock` at `0x14017a8ff`
- `ntoskrnl!KeReleaseSpinLock` at `0x14017a9a7`
- `ntoskrnl!KeReleaseSpinLock` at `0x14017a9e2`
- `ntoskrnl!KeReleaseSpinLock` at `0x14017ab66`
- `ntoskrnl!KeReleaseSpinLock` at `0x14017ad02`
- `ntoskrnl!KeReleaseSpinLock` at `0x14017ae78`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x14017aecb`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x14017aecb`
- `HAL!KeStallExecutionProcessor` at `0x14017ae89`
- `HAL!KeStallExecutionProcessor` at `0x14017ae89`

## pseudocode

```c
void __fastcall ndisDevicePowerOn(_QWORD *a1)
{
  char *v2; // rbx
  int v3; // r13d
  int v4; // edx
  unsigned int v5; // edx
  const struct _NDIS_MINIPORT_BLOCK *v6; // rcx
  IRP *v7; // rsi
  int Status; // r15d
  enum _DEVICE_POWER_STATE DeviceState; // r14d
  int v10; // edx
  __int64 v11; // rcx
  struct _DEVICE_OBJECT *v12; // rcx
  POWER_STATE v13; // r8d
  int v14; // edx
  char v15; // di
  char v16; // r12
  KIRQL v17; // dl
  int v18; // edx
  int SetMiniportDeviceState; // edi
  KIRQL v20; // dl
  KIRQL v21; // dl
  KSPIN_LOCK *v22; // r12
  int v23; // edx
  struct _NDIS_MINIPORT_BLOCK *v24; // rcx
  __int64 v25; // rax
  int v26; // edx
  unsigned __int8 v27; // al
  KIRQL v28; // dl
  enum _NDIS_DEVICE_PNP_EVENT v29; // edx
  unsigned int v30; // r9d
  signed __int32 v31; // eax
  signed __int32 v32; // ett
  __int64 v33; // rcx
  struct _NDIS_MINIPORT_BLOCK *v34; // rcx
  KIRQL v35; // dl
  int v36; // edx
  int v37; // ecx
  unsigned __int8 v38; // al
  struct _NDIS_MINIPORT_BLOCK *v39; // rcx
  struct _NDIS_MINIPORT_BLOCK *v40; // rcx
  KIRQL v41; // dl
  KIRQL v42; // cl
  struct _NDIS_MINIPORT_BLOCK *v43; // rcx
  int v44; // edx
  int v45; // eax
  int v46; // edx
  __int64 v47; // rcx
  unsigned __int8 v48; // [rsp+50h] [rbp-B0h] BYREF
  char v49; // [rsp+51h] [rbp-AFh]
  int v50; // [rsp+54h] [rbp-ACh]
  BOOL v51; // [rsp+58h] [rbp-A8h] BYREF
  char v52[160]; // [rsp+60h] [rbp-A0h] BYREF
  struct _NDIS_STATUS_INDICATION StatusIndication; // [rsp+100h] [rbp+0h] BYREF
  _QWORD v54[2]; // [rsp+170h] [rbp+70h] BYREF
  __int128 v55; // [rsp+180h] [rbp+80h] BYREF
  __int128 v56; // [rsp+190h] [rbp+90h]
  __int64 v57; // [rsp+1A0h] [rbp+A0h]

  v2 = (char *)(a1 - 673);
  v3 = 0;
  v51 = 0;
  v48 = 0;
  memset(&StatusIndication, 0, sizeof(StatusIndication));
  memset(v54, 0, 12);
  v55 = 0;
  v57 = 0;
  v56 = 0;
  if ( *(enum Ndis::ReadBindingsOptions::Flags **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v4) = 4;
    WPP_RECORDER_SF_q(
      *((_QWORD *)WPP_GLOBAL_Control + 8),
      v4,
      14,
      67,
      (struct _GUID *)&WPP_dc968d99198e32e9263b7dc94e457b33_Traceguids,
      (char)v2);
  }
  ndisReferencePackage((struct _PKG_REF *)&ndisPkgs);
  if ( MINIPORT_TEST_FLAG((const struct _NDIS_MINIPORT_BLOCK *)v2, 0x80u) )
  {
    v7 = 0;
    Status = 0;
    DeviceState = PowerDeviceD0;
  }
  else
  {
    v7 = (IRP *)a1[4];
    Status = v7->IoStatus.Status;
    DeviceState = v7->Tail.Overlay.CurrentStackLocation->Parameters.Power.State.DeviceState;
  }
  a1[4] = 0;
  if ( *((_DWORD *)v2 + 380) != 1 )
  {
    MINIPORT_TEST_FLAG(v6, v5);
    if ( *(enum Ndis::ReadBindingsOptions::Flags **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v10) = 4;
      WPP_RECORDER_SF_q(
        *((_QWORD *)WPP_GLOBAL_Control + 8),
        v10,
        14,
        68,
        (struct _GUID *)&WPP_dc968d99198e32e9263b7dc94e457b33_Traceguids,
        (char)v2);
    }
    if ( (byte_14011B001 & 8) != 0 )
      McTemplateK0jqxd_EtwWriteTransfer(
        v11,
        PowerOnMiniportNotStarted,
        v2 + 4008,
        v2 + 4008,
        *((_DWORD *)v2 + 1014),
        *((_QWORD *)v2 + 503),
        65537);
    v12 = (struct _DEVICE_OBJECT *)*((_QWORD *)v2 + 478);
    v13.SystemState = (_SYSTEM_POWER_STATE)v7->Tail.Overlay.CurrentStackLocation->Parameters.Power.State;
    *((POWER_STATE *)v2 + 967) = v13;
    PoSetPowerState(v12, DevicePowerState, v13);
    Rtl::KNeutralLock<enum NDIS_MINIPORT_POLICY_OWNER>::Release(v2 + 5240);
    ndisScheduleD0CompleteSignalWorkItem((struct _NDIS_MINIPORT_BLOCK *)v2, 0);
    IofCompleteRequest(v7, 0);
LABEL_115:
    ndisDereferenceMiniport((struct _NDIS_MINIPORT_BLOCK *)v2, MPREF_PM_DEVPOWERUP);
    ndisDereferencePackage((struct _PKG_REF *)&ndisPkgs);
    return;
  }
  if ( (*((_DWORD *)v2 + 31) & 0x10) == 0 )
  {
    v15 = 0;
    v50 = 0;
    v16 = 0;
    v49 = 0;
    if ( Status < 0 )
    {
      if ( *(enum Ndis::ReadBindingsOptions::Flags **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v5) = 4;
        WPP_RECORDER_SF_qL(
          *((_QWORD *)WPP_GLOBAL_Control + 8),
          v5,
          14,
          71,
          (struct _GUID *)&WPP_dc968d99198e32e9263b7dc94e457b33_Traceguids,
          (char)v2,
          Status);
      }
      goto LABEL_79;
    }
    if ( *(enum Ndis::ReadBindingsOptions::Flags **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v5) = 4;
      WPP_RECORDER_SF_q(
        *((_QWORD *)WPP_GLOBAL_Control + 8),
        v5,
        14,
        72,
        (struct _GUID *)&WPP_dc968d99198e32e9263b7dc94e457b33_Traceguids,
        (char)v2);
    }
    if ( *((_DWORD *)v2 + 967) == 1 )
    {
      MINIPORT_TEST_FLAG((const struct _NDIS_MINIPORT_BLOCK *)v2, 0x80u);
      if ( ndisIsMiniportStarted(v34) && *((_DWORD *)v2 + 380) == 1 )
      {
        NdisSetEvent((PNDIS_EVENT)(v2 + 3728));
        NDIS_ACQUIRE_MINIPORT_SPIN_LOCK((struct _NDIS_MINIPORT_BLOCK *)v2, &v48);
        ndisMRestoreOpenHandlers((struct _NDIS_MINIPORT_BLOCK *)v2, 4u);
        v35 = v48;
        *((_QWORD *)v2 + 65) = 0;
        KeReleaseSpinLock((PKSPIN_LOCK)v2 + 12, v35);
        v15 = 1;
      }
      goto LABEL_79;
    }
    if ( *(enum Ndis::ReadBindingsOptions::Flags **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v5) = 4;
      WPP_RECORDER_SF_q(
        *((_QWORD *)WPP_GLOBAL_Control + 8),
        v5,
        14,
        73,
        (struct _GUID *)&WPP_dc968d99198e32e9263b7dc94e457b33_Traceguids,
        (char)v2);
    }
    if ( (byte_14011B001 & 8) != 0 )
      McTemplateK0jqxd_EtwWriteTransfer(
        v6,
        MiniportPoweringUp,
        v2 + 4008,
        v2 + 4008,
        *((_DWORD *)v2 + 1014),
        *((_QWORD *)v2 + 503),
        65538);
    if ( (*((_DWORD *)v2 + 31) & 0x20) != 0 )
    {
      if ( (ndisAoAcCapable || ndisAoAcTest)
        && ((unsigned __int8)v2[32] > 6u || v2[32] == 6 && (unsigned __int8)v2[33] >= 0x1Eu) )
      {
        NDIS_ACQUIRE_MINIPORT_SPIN_LOCK((struct _NDIS_MINIPORT_BLOCK *)v2, &v48);
        ndisMRestoreOpenHandlers((struct _NDIS_MINIPORT_BLOCK *)v2, 4u);
        v17 = v48;
        *((_QWORD *)v2 + 65) = 0;
        KeReleaseSpinLock((PKSPIN_LOCK)v2 + 12, v17);
        LOBYTE(v3) = 1;
      }
      SetMiniportDeviceState = ndisQuerySetMiniportDeviceState(
                                 (struct _NDIS_MINIPORT_BLOCK *)v2,
                                 DeviceState,
                                 0xFD010101,
                                 1u);
      if ( *(enum Ndis::ReadBindingsOptions::Flags **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
        WPP_RECORDER_SF_qLL(
          *((_QWORD *)WPP_GLOBAL_Control + 8),
          v18,
          14,
          74,
          (struct _GUID *)&WPP_dc968d99198e32e9263b7dc94e457b33_Traceguids,
          (char)v2,
          DeviceState,
          SetMiniportDeviceState);
      if ( SetMiniportDeviceState )
      {
        if ( (_BYTE)v3 )
        {
          NDIS_ACQUIRE_MINIPORT_SPIN_LOCK((struct _NDIS_MINIPORT_BLOCK *)v2, &v48);
          ndisMSwapOpenHandlers((struct _NDIS_MINIPORT_BLOCK *)v2, 4u);
          v20 = v48;
          *((_QWORD *)v2 + 65) = 0;
          KeReleaseSpinLock((PKSPIN_LOCK)v2 + 12, v20);
          LOBYTE(v3) = 0;
        }
      }
      else
      {
        *((_DWORD *)v2 + 967) = DeviceState;
      }
      NDIS_ACQUIRE_MINIPORT_SPIN_LOCK((struct _NDIS_MINIPORT_BLOCK *)v2, &v48);
      ndisSetWakeUpTimer((struct _NDIS_MINIPORT_BLOCK *)v2);
      v21 = v48;
      v22 = (KSPIN_LOCK *)(v2 + 96);
      *((_QWORD *)v2 + 65) = 0;
      KeReleaseSpinLock((PKSPIN_LOCK)v2 + 12, v21);
    }
    else
    {
      if ( (*(_WORD *)(*((_QWORD *)v2 + 470) + 26LL) & 1) != 0 || (*((_DWORD *)v2 + 31) & 0x4000) == 0 )
      {
        v22 = (KSPIN_LOCK *)(v2 + 96);
        goto LABEL_57;
      }
      SetMiniportDeviceState = ndisPmInitializeMiniport((struct _NDIS_MINIPORT_BLOCK *)v2);
      v22 = (KSPIN_LOCK *)(v2 + 96);
    }
    if ( SetMiniportDeviceState )
    {
      if ( *(enum Ndis::ReadBindingsOptions::Flags **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v23) = 2;
        WPP_RECORDER_SF_qL(
          *((_QWORD *)WPP_GLOBAL_Control + 8),
          v23,
          14,
          76,
          (struct _GUID *)&WPP_dc968d99198e32e9263b7dc94e457b33_Traceguids,
          (char)v2,
          SetMiniportDeviceState);
      }
      if ( MINIPORT_TEST_FLAG((const struct _NDIS_MINIPORT_BLOCK *)v2, 0x80u) )
        Status = -1073741823;
      else
        v7->IoStatus.Status = -1073741823;
      *((_QWORD *)v2 + 508) = 2;
      if ( ndisMReferenceIfBlock(v24, MPIFREF_DEVPOWERUPFAIL) )
      {
        v25 = *((_QWORD *)v2 + 505);
        if ( *(_DWORD *)(v25 + 1112) == 2 )
        {
          v3 = v50;
        }
        else
        {
          *(_DWORD *)(v25 + 1112) = 2;
          *(_DWORD *)(*((_QWORD *)v2 + 505) + 1116LL) = 0;
          ndisNsiSyncMiniportOperStatusNotification((struct _NDIS_MINIPORT_BLOCK *)v2);
          v3 = 1;
        }
        ndisMDereferenceIfBlock((struct _NDIS_MINIPORT_BLOCK *)v2, MPIFREF_DEVPOWERUPFAIL);
      }
      else
      {
        v3 = v50;
      }
      v16 = 0;
LABEL_75:
      v15 = v16;
LABEL_79:
      if ( !MINIPORT_TEST_FLAG((const struct _NDIS_MINIPORT_BLOCK *)v2, 0x80u) )
      {
        Status = v7->IoStatus.Status;
        IofCompleteRequest(v7, 0);
      }
      if ( Status < 0 )
      {
        if ( *(enum Ndis::ReadBindingsOptions::Flags **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
        {
          LOBYTE(v36) = 2;
          WPP_RECORDER_SF_qL(
            *((_QWORD *)WPP_GLOBAL_Control + 8),
            v36,
            14,
            77,
            (struct _GUID *)&WPP_dc968d99198e32e9263b7dc94e457b33_Traceguids,
            (char)v2,
            Status);
        }
        if ( (byte_14011B003 & 2) != 0 )
          McTemplateK0jqxddq_EtwWriteTransfer(
            v37,
            (unsigned int)DevicePowerOnFailed,
            (_DWORD)v2 + 4008,
            (_DWORD)v2 + 4008,
            *((_DWORD *)v2 + 1014),
            *((_QWORD *)v2 + 503),
            Status,
            1,
            0);
        ndisMiniportFatalError((struct _NDIS_MINIPORT_BLOCK *)v2, NdisMEventErr_FailedPowerD0);
      }
      if ( *((int *)v2 + 468) < 0 )
        ndisReturnQueuedLowPowerNbls((struct _NDIS_MINIPORT_BLOCK *)v2, 0);
      Rtl::KNeutralLock<enum NDIS_MINIPORT_POLICY_OWNER>::Release(v2 + 5240);
      if ( v15 )
      {
        v38 = MINIPORT_TEST_FLAG((const struct _NDIS_MINIPORT_BLOCK *)v2, 0x80u);
        ndisIssueNetEventSetPowerEvent(v39, DeviceState, v38 == 0);
        ndisNotifyDevicePowerStateChange((struct _NDIS_MINIPORT_BLOCK *)v2, (enum _NDIS_DEVICE_POWER_STATE)DeviceState);
        if ( (*((_DWORD *)v2 + 31) & 0x10000000) != 0
          && MINIPORT_TEST_FLAG((const struct _NDIS_MINIPORT_BLOCK *)v2, 0x20000000u) )
        {
          NDIS_ACQUIRE_MINIPORT_SPIN_LOCK(v40, &v48);
          while ( v2[89] )
          {
            v41 = v48;
            *((_QWORD *)v2 + 65) = 0;
            KeReleaseSpinLock((PKSPIN_LOCK)v2 + 12, v41);
            KeStallExecutionProcessor(1u);
            NDIS_ACQUIRE_MINIPORT_SPIN_LOCK((struct _NDIS_MINIPORT_BLOCK *)v2, &v48);
          }
          v2[89] = 1;
          *((_QWORD *)v2 + 233) = KeGetCurrentThread();
          *((_QWORD *)v2 + 65) = 0;
          KeReleaseSpinLockFromDpcLevel((PKSPIN_LOCK)v2 + 12);
          MINIPORT_CLEAR_FLAG((struct _NDIS_MINIPORT_BLOCK *)v2, 0x20000000u);
          *((_QWORD *)&v55 + 1) = *((unsigned int *)v2 + 87);
          v56 = *(_OWORD *)(v2 + 2760);
          v57 = *(_QWORD *)(v2 + 812);
          *(_QWORD *)&v55 = 0x100280180LL;
          memset(&StatusIndication, 0, sizeof(StatusIndication));
          StatusIndication.Header = (_NDIS_OBJECT_HEADER)7340440;
          StatusIndication.StatusBuffer = &v55;
          StatusIndication.SourceHandle = v2;
          StatusIndication.StatusCode = 1073807383;
          StatusIndication.StatusBufferSize = 40;
          StatusIndication.Flags = 8;
          NdisMIndicateStatusEx(v2, &StatusIndication);
          v42 = v48;
          v2[89] = 0;
          *((_QWORD *)v2 + 233) = 0;
          if ( v42 != 2 )
            KeLowerIrql(v42);
        }
        if ( !MINIPORT_TEST_FLAG((const struct _NDIS_MINIPORT_BLOCK *)v2, 0x20000000u) && v16 )
          ndisSetMediaDisconnectTimer(v43);
      }
      ndisSignalD0RequestComplete((struct _NDIS_MINIPORT_BLOCK *)v2, Status);
      ndisMSetMiniportReadyForBinding((struct _NDIS_MINIPORT_BLOCK *)v2, 1, Reason_MiniportLowPower, RunAsynchronous);
      if ( v49 )
      {
        v45 = *((_DWORD *)v2 + 671);
        if ( (v45 & 0x100) != 0 )
        {
          *((_DWORD *)v2 + 671) = v45 & 0xFFFFFEFF;
          Ndis::BindEngine::BeginPolicyUpdates((Ndis::BindEngine *)(v2 + 5120));
          if ( Ndis::BindState::SetPause((Ndis::BindState *)(v2 + 5048), DatapathRunning, PauseReason_LowPower) )
          {
            memset(v52, 0, sizeof(v52));
            if ( (unsigned __int8)byte_14011CAD3 >= 4u )
            {
              ndisGetBindLinkNameForTracing((struct _NDIS_MINIPORT_BLOCK *)v2, (struct NDIS_PNPTRACE_LOCALS *)v52);
              if ( *(enum Ndis::ReadBindingsOptions::Flags **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
                WPP_RECORDER_SF_Zq(
                  *((_QWORD *)WPP_GLOBAL_Control + 8),
                  v46,
                  28,
                  78,
                  (struct _GUID *)&WPP_dc968d99198e32e9263b7dc94e457b33_Traceguids,
                  *(__int64 *)&v52[8],
                  v52[0]);
            }
          }
          Ndis::BindEngine::EndPolicyUpdates((Ndis::BindEngine *)(v2 + 5120));
          Ndis::BindEngine::ApplyBindChanges((Ndis::BindEngine *)(v2 + 5120), RunSynchronous, 1);
        }
      }
      if ( (!ndisAoAcCapable && !ndisAoAcTest || v3)
        && ndisIsMiniportStarted((struct _NDIS_MINIPORT_BLOCK *)v2)
        && *((_DWORD *)v2 + 380) == 1
        && ndisMReferenceIfBlock((struct _NDIS_MINIPORT_BLOCK *)v2, MPIFREF_DEVPOWERUP) )
      {
        v47 = *((_QWORD *)v2 + 505);
        *(_QWORD *)((char *)v54 + 4) = 0;
        LODWORD(v54[0]) = 786816;
        HIDWORD(v54[0]) = *(_DWORD *)(v47 + 1112);
        LODWORD(v54[1]) = *(_DWORD *)(v47 + 1116);
        memset(&StatusIndication, 0, sizeof(StatusIndication));
        StatusIndication.Header = (_NDIS_OBJECT_HEADER)7340440;
        StatusIndication.StatusBuffer = v54;
        StatusIndication.SourceHandle = v2;
        StatusIndication.StatusCode = 1073807395;
        StatusIndication.StatusBufferSize = 12;
        NdisMIndicateStatusEx(v2, &StatusIndication);
        ndisMDereferenceIfBlock((struct _NDIS_MINIPORT_BLOCK *)v2, MPIFREF_DEVPOWERUP);
      }
      if ( *(enum Ndis::ReadBindingsOptions::Flags **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v44) = 4;
        WPP_RECORDER_SF_q(
          *((_QWORD *)WPP_GLOBAL_Control + 8),
          v44,
          14,
          79,
          (struct _GUID *)&WPP_dc968d99198e32e9263b7dc94e457b33_Traceguids,
          (char)v2);
      }
      goto LABEL_115;
    }
LABEL_57:
    v49 = 1;
    if ( ndisIsMiniportStarted((struct _NDIS_MINIPORT_BLOCK *)v2) )
    {
      NdisSetEvent((PNDIS_EVENT)(v2 + 3728));
      NDIS_ACQUIRE_MINIPORT_SPIN_LOCK((struct _NDIS_MINIPORT_BLOCK *)v2, &v48);
      if ( !(_BYTE)v3 )
        ndisMRestoreOpenHandlers((struct _NDIS_MINIPORT_BLOCK *)v2, 4u);
      v27 = ndisIfSetInterfaceState((struct _NDIS_MINIPORT_BLOCK *)v2, 1u, v48);
      v28 = v48;
      v3 = v27;
      *((_QWORD *)v2 + 65) = 0;
      KeReleaseSpinLock(v22, v28);
      _m_prefetchw(v2 + 4424);
      v31 = *((_DWORD *)v2 + 1106);
      do
      {
        v32 = v31;
        v31 = _InterlockedCompareExchange((volatile signed __int32 *)v2 + 1106, v31, v31);
      }
      while ( v32 != v31 );
      if ( (v31 & 0x10) != 0 )
      {
        ndisSetDeviceInterfaceState((struct _NDIS_MINIPORT_BLOCK *)v2, 1u);
        _InterlockedAnd((volatile signed __int32 *)v2 + 1106, 0xFFFFFFEF);
      }
      v16 = 1;
      v51 = (_BYTE)ndisAcOnLine == 1;
      ndisNotifyMiniports((struct _NDIS_MINIPORT_BLOCK *)v2, v29, &v51, v30);
      if ( (unsigned __int8)v2[32] < 6u )
        ndisQueryMediaStatus((struct _NDIS_MINIPORT_BLOCK *)v2);
    }
    else
    {
      v3 = v50;
      v16 = 0;
    }
    *((_DWORD *)v2 + 967) = DeviceState;
    if ( *(enum Ndis::ReadBindingsOptions::Flags **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v26) = 4;
      WPP_RECORDER_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 8),
        v26,
        14,
        75,
        (struct _GUID *)&WPP_dc968d99198e32e9263b7dc94e457b33_Traceguids,
        (char)v2,
        DeviceState);
    }
    NDIS_COUNT_POWER_TRANSITION((struct _NDIS_MINIPORT_BLOCK *)v2, (enum _NDIS_DEVICE_POWER_STATE)DeviceState);
    if ( (byte_14011B001 & 8) != 0 )
      McTemplateK0jqxqq_EtwWriteTransfer(
        v33,
        DevicePowerStateChange,
        v2 + 4008,
        v2 + 4008,
        *((_DWORD *)v2 + 1014),
        *((_QWORD *)v2 + 503),
        1,
        DeviceState);
    if ( !MINIPORT_TEST_FLAG((const struct _NDIS_MINIPORT_BLOCK *)v2, 0x80u) )
      PoSetPowerState(*((PDEVICE_OBJECT *)v2 + 478), DevicePowerState, (POWER_STATE)DeviceState);
    goto LABEL_75;
  }
  if ( *(enum Ndis::ReadBindingsOptions::Flags **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v5) = 4;
    WPP_RECORDER_SF_q(
      *((_QWORD *)WPP_GLOBAL_Control + 8),
      v5,
      14,
      69,
      (struct _GUID *)&WPP_dc968d99198e32e9263b7dc94e457b33_Traceguids,
      (char)v2);
  }
  if ( (byte_14011B001 & 8) != 0 )
    McTemplateK0jqxd_EtwWriteTransfer(
      v6,
      PowerOnMiniportRemoved,
      v2 + 4008,
      v2 + 4008,
      *((_DWORD *)v2 + 1014),
      *((_QWORD *)v2 + 503),
      65537);
  IofCompleteRequest(v7, 0);
  Rtl::KNeutralLock<enum NDIS_MINIPORT_POLICY_OWNER>::Release(v2 + 5240);
  ndisSignalD0RequestComplete((struct _NDIS_MINIPORT_BLOCK *)v2, 0);
  ndisDereferenceMiniport((struct _NDIS_MINIPORT_BLOCK *)v2, MPREF_PM_DEVPOWERUP);
  ndisDereferencePackage((struct _PKG_REF *)&ndisPkgs);
  if ( *(enum Ndis::ReadBindingsOptions::Flags **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v14) = 4;
    WPP_RECORDER_SF_q(
      *((_QWORD *)WPP_GLOBAL_Control + 8),
      v14,
      14,
      70,
      (struct _GUID *)&WPP_dc968d99198e32e9263b7dc94e457b33_Traceguids,
      (char)v2);
  }
}

```

## disassembly

```asm
0x14017a4a0  push    rbp
0x14017a4a2  push    rbx
0x14017a4a3  push    rdi
0x14017a4a4  push    r12
0x14017a4a6  push    r13
0x14017a4a8  lea     rbp, [rsp-0B0h]
0x14017a4b0  sub     rsp, 1B0h
0x14017a4b7  mov     rax, cs:__security_cookie
0x14017a4be  xor     rax, rsp
0x14017a4c1  mov     [rbp+0D0h+var_28], rax
0x14017a4c8  mov     rdi, rcx
0x14017a4cb  lea     rbx, [rcx-1508h]
0x14017a4d2  xor     r13d, r13d
0x14017a4d5  lea     rcx, [rbp+0D0h+StatusIndication]; void *
0x14017a4d9  xor     edx, edx; Val
0x14017a4db  mov     [rsp+1D0h+var_178], r13d
0x14017a4e0  mov     r8d, 70h ; 'p'; Size
0x14017a4e6  mov     [rsp+1D0h+var_180], r13b
0x14017a4eb  call    memset
0x14017a4f0  xor     eax, eax
0x14017a4f2  xorps   xmm0, xmm0
0x14017a4f5  mov     [rbp+0D0h+var_60], rax
0x14017a4f9  mov     [rbp+0D0h+var_58], eax
0x14017a4fc  movups  [rbp+0D0h+var_50], xmm0
0x14017a503  mov     [rbp+0D0h+var_30], rax
0x14017a50a  movups  [rbp+0D0h+var_40], xmm0
0x14017a511  lea     r12, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14017a518  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x14017a51f  lea     rax, WPP_dc968d99198e32e9263b7dc94e457b33_Traceguids
0x14017a526  jz      short loc_14017A550
0x14017a528  mov     rcx, cs:WPP_GLOBAL_Control
0x14017a52f  mov     r9d, 43h ; 'C'; int
0x14017a535  mov     qword ptr [rsp+1D0h+var_1A8], rbx; char
0x14017a53a  mov     r8d, 0Eh; int
0x14017a540  mov     dl, 4; int
0x14017a542  mov     [rsp+1D0h+var_1B0], rax; struct _GUID *
0x14017a547  mov     rcx, [rcx+40h]; int
0x14017a54b  call    WPP_RECORDER_SF_q
0x14017a550  mov     [rsp+1D0h+arg_8], rsi
0x14017a558  lea     rcx, ?ndisPkgs@@3PAU_PKG_REF@@A; struct _PKG_REF *
0x14017a55f  mov     [rsp+1D0h+arg_10], r14
0x14017a567  mov     [rsp+1D0h+arg_18], r15
0x14017a56f  call    ?ndisReferencePackage@@YAXPEAU_PKG_REF@@@Z; ndisReferencePackage(_PKG_REF *)
0x14017a574  mov     edx, 80h; unsigned int
0x14017a579  mov     rcx, rbx; struct _NDIS_MINIPORT_BLOCK *
0x14017a57c  call    ?MINIPORT_TEST_FLAG@@YAEPEBU_NDIS_MINIPORT_BLOCK@@K@Z; MINIPORT_TEST_FLAG(_NDIS_MINIPORT_BLOCK const *,ulong)
0x14017a581  test    al, al
0x14017a583  jnz     short loc_14017A59A
0x14017a585  mov     rsi, [rdi+20h]
0x14017a589  mov     rax, [rsi+0B8h]
0x14017a590  mov     r15d, [rsi+30h]
0x14017a594  mov     r14d, [rax+18h]
0x14017a598  jmp     short loc_14017A5A6
0x14017a59a  mov     rsi, r13
0x14017a59d  mov     r15d, r13d
0x14017a5a0  mov     r14d, 1
0x14017a5a6  mov     [rdi+20h], r13
0x14017a5aa  cmp     dword ptr [rbx+5F0h], 1
0x14017a5b1  jz      loc_14017A687
0x14017a5b7  call    ?MINIPORT_TEST_FLAG@@YAEPEBU_NDIS_MINIPORT_BLOCK@@K@Z; MINIPORT_TEST_FLAG(_NDIS_MINIPORT_BLOCK const *,ulong)
0x14017a5bc  cmp     cs:WPP_RECORDER_INITIALIZED, r12; __annotation("TMF:",
0x14017a5c3  jz      short loc_14017A5F4
0x14017a5c5  mov     rcx, cs:WPP_GLOBAL_Control
0x14017a5cc  lea     rax, WPP_dc968d99198e32e9263b7dc94e457b33_Traceguids
0x14017a5d3  mov     r9d, 44h ; 'D'; int
0x14017a5d9  mov     qword ptr [rsp+1D0h+var_1A8], rbx; char
0x14017a5de  mov     r8d, 0Eh; int
0x14017a5e4  mov     [rsp+1D0h+var_1B0], rax; struct _GUID *
0x14017a5e9  mov     dl, 4; int
0x14017a5eb  mov     rcx, [rcx+40h]; int
0x14017a5ef  call    WPP_RECORDER_SF_q
0x14017a5f4  test    cs:byte_14011B001, 8
0x14017a5fb  jz      short loc_14017A631
0x14017a5fd  mov     rax, [rbx+0FB8h]
0x14017a604  lea     r8, [rbx+0FA8h]
0x14017a60b  mov     dword ptr [rsp+1D0h+var_1A0], 10001h
0x14017a613  lea     rdx, PowerOnMiniportNotStarted
0x14017a61a  mov     qword ptr [rsp+1D0h+var_1A8], rax
0x14017a61f  mov     r9, r8
0x14017a622  mov     eax, [rbx+0FD8h]
0x14017a628  mov     dword ptr [rsp+1D0h+var_1B0], eax
0x14017a62c  call    McTemplateK0jqxd_EtwWriteTransfer
0x14017a631  mov     rax, [rsi+0B8h]
0x14017a638  mov     edx, 1; Type
0x14017a63d  mov     rcx, [rbx+0EF0h]; DeviceObject
0x14017a644  mov     r8d, [rax+18h]; State
0x14017a648  mov     [rbx+0F1Ch], r8d
0x14017a64f  call    cs:__imp_PoSetPowerState
0x14017a656  nop     dword ptr [rax+rax+00h]
0x14017a65b  lea     rcx, [rbx+1478h]
0x14017a662  call    ?Release@?$KNeutralLock@W4NDIS_MINIPORT_POLICY_OWNER@@@Rtl@@QEAAXW4NDIS_MINIPORT_POLICY_OWNER@@@Z; Rtl::KNeutralLock<NDIS_MINIPORT_POLICY_OWNER>::Release(NDIS_MINIPORT_POLICY_OWNER)
0x14017a667  xor     edx, edx; int
0x14017a669  mov     rcx, rbx; struct _NDIS_MINIPORT_BLOCK *
0x14017a66c  call    ?ndisScheduleD0CompleteSignalWorkItem@@YAXPEAU_NDIS_MINIPORT_BLOCK@@J@Z; ndisScheduleD0CompleteSignalWorkItem(_NDIS_MINIPORT_BLOCK *,long)
0x14017a671  xor     edx, edx; PriorityBoost
0x14017a673  mov     rcx, rsi; Irp
0x14017a676  call    cs:__imp_IofCompleteRequest
0x14017a67d  nop     dword ptr [rax+rax+00h]
0x14017a682  jmp     loc_14017B1CB
0x14017a687  mov     eax, [rbx+7Ch]
0x14017a68a  test    al, 10h
0x14017a68c  jz      loc_14017A77E
0x14017a692  cmp     cs:WPP_RECORDER_INITIALIZED, r12; __annotation("TMF:",
0x14017a699  lea     rdi, WPP_dc968d99198e32e9263b7dc94e457b33_Traceguids
0x14017a6a0  jz      short loc_14017A6CA
0x14017a6a2  mov     rcx, cs:WPP_GLOBAL_Control
0x14017a6a9  mov     r9d, 45h ; 'E'; int
0x14017a6af  mov     qword ptr [rsp+1D0h+var_1A8], rbx; char
0x14017a6b4  mov     r8d, 0Eh; int
0x14017a6ba  mov     dl, 4; int
0x14017a6bc  mov     [rsp+1D0h+var_1B0], rdi; struct _GUID *
0x14017a6c1  mov     rcx, [rcx+40h]; int
0x14017a6c5  call    WPP_RECORDER_SF_q
0x14017a6ca  test    cs:byte_14011B001, 8
0x14017a6d1  jz      short loc_14017A707
0x14017a6d3  mov     rax, [rbx+0FB8h]
0x14017a6da  lea     r8, [rbx+0FA8h]
0x14017a6e1  mov     dword ptr [rsp+1D0h+var_1A0], 10001h
0x14017a6e9  lea     rdx, PowerOnMiniportRemoved
0x14017a6f0  mov     qword ptr [rsp+1D0h+var_1A8], rax
0x14017a6f5  mov     r9, r8
0x14017a6f8  mov     eax, [rbx+0FD8h]
0x14017a6fe  mov     dword ptr [rsp+1D0h+var_1B0], eax
0x14017a702  call    McTemplateK0jqxd_EtwWriteTransfer
0x14017a707  xor     edx, edx; PriorityBoost
0x14017a709  mov     rcx, rsi; Irp
0x14017a70c  call    cs:__imp_IofCompleteRequest
0x14017a713  nop     dword ptr [rax+rax+00h]
0x14017a718  lea     rcx, [rbx+1478h]
0x14017a71f  call    ?Release@?$KNeutralLock@W4NDIS_MINIPORT_POLICY_OWNER@@@Rtl@@QEAAXW4NDIS_MINIPORT_POLICY_OWNER@@@Z; Rtl::KNeutralLock<NDIS_MINIPORT_POLICY_OWNER>::Release(NDIS_MINIPORT_POLICY_OWNER)
0x14017a724  xor     edx, edx; int
0x14017a726  mov     rcx, rbx; struct _NDIS_MINIPORT_BLOCK *
0x14017a729  call    ?ndisSignalD0RequestComplete@@YAXPEAU_NDIS_MINIPORT_BLOCK@@J@Z; ndisSignalD0RequestComplete(_NDIS_MINIPORT_BLOCK *,long)
0x14017a72e  mov     dl, 0Ch; enum _NDIS_MP_REFTAG
0x14017a730  mov     rcx, rbx; struct _NDIS_MINIPORT_BLOCK *
0x14017a733  call    ?ndisDereferenceMiniport@@YAXPEAU_NDIS_MINIPORT_BLOCK@@W4_NDIS_MP_REFTAG@@@Z; ndisDereferenceMiniport(_NDIS_MINIPORT_BLOCK *,_NDIS_MP_REFTAG)
0x14017a738  lea     rcx, ?ndisPkgs@@3PAU_PKG_REF@@A; struct _PKG_REF *
0x14017a73f  call    ?ndisDereferencePackage@@YAXPEAU_PKG_REF@@@Z; ndisDereferencePackage(_PKG_REF *)
0x14017a744  cmp     cs:WPP_RECORDER_INITIALIZED, r12; __annotation("TMF:",
0x14017a74b  jz      loc_14017B1E1
0x14017a751  mov     rcx, cs:WPP_GLOBAL_Control
0x14017a758  mov     r9d, 46h ; 'F'; int
0x14017a75e  mov     qword ptr [rsp+1D0h+var_1A8], rbx; char
0x14017a763  mov     r8d, 0Eh; int
0x14017a769  mov     dl, 4; int
0x14017a76b  mov     [rsp+1D0h+var_1B0], rdi; struct _GUID *
0x14017a770  mov     rcx, [rcx+40h]; int
0x14017a774  call    WPP_RECORDER_SF_q
0x14017a779  jmp     loc_14017B1E1
0x14017a77e  xor     dil, dil
0x14017a781  mov     [rsp+1D0h+var_17C], r13d
0x14017a786  xor     r12b, r12b
0x14017a789  mov     [rsp+1D0h+var_17F], dil
0x14017a78e  test    r15d, r15d
0x14017a791  jns     short loc_14017A7E0
0x14017a793  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14017a79a  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14017a7a1  jz      loc_14017AD11
0x14017a7a7  mov     rcx, cs:WPP_GLOBAL_Control
0x14017a7ae  lea     rax, WPP_dc968d99198e32e9263b7dc94e457b33_Traceguids
0x14017a7b5  mov     dword ptr [rsp+1D0h+var_1A0], r15d; char
0x14017a7ba  mov     r9d, 47h ; 'G'; int
0x14017a7c0  mov     qword ptr [rsp+1D0h+var_1A8], rbx; char
0x14017a7c5  mov     r8d, 0Eh; int
0x14017a7cb  mov     dl, 4; int
0x14017a7cd  mov     [rsp+1D0h+var_1B0], rax; struct _GUID *
0x14017a7d2  mov     rcx, [rcx+40h]; int
0x14017a7d6  call    WPP_RECORDER_SF_qL
0x14017a7db  jmp     loc_14017AD11
0x14017a7e0  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14017a7e7  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14017a7ee  jz      short loc_14017A826
0x14017a7f0  mov     rcx, cs:WPP_GLOBAL_Control
0x14017a7f7  lea     rax, WPP_dc968d99198e32e9263b7dc94e457b33_Traceguids
0x14017a7fe  mov     r9d, 48h ; 'H'; int
0x14017a804  mov     qword ptr [rsp+1D0h+var_1A8], rbx; char
0x14017a809  mov     r8d, 0Eh; int
0x14017a80f  mov     [rsp+1D0h+var_1B0], rax; struct _GUID *
0x14017a814  mov     dl, 4; int
0x14017a816  mov     rcx, [rcx+40h]; int
0x14017a81a  call    WPP_RECORDER_SF_q
0x14017a81f  lea     rax, WPP_RECORDER_INITIALIZED
0x14017a826  cmp     dword ptr [rbx+0F1Ch], 1
0x14017a82d  jz      loc_14017ACB0
0x14017a833  cmp     cs:WPP_RECORDER_INITIALIZED, rax; __annotation("TMF:",
0x14017a83a  lea     rdi, WPP_dc968d99198e32e9263b7dc94e457b33_Traceguids
0x14017a841  jz      short loc_14017A86B
0x14017a843  mov     rcx, cs:WPP_GLOBAL_Control
0x14017a84a  mov     r9d, 49h ; 'I'; int
0x14017a850  mov     qword ptr [rsp+1D0h+var_1A8], rbx; char
0x14017a855  mov     r8d, 0Eh; int
0x14017a85b  mov     dl, 4; int
0x14017a85d  mov     [rsp+1D0h+var_1B0], rdi; struct _GUID *
0x14017a862  mov     rcx, [rcx+40h]; int
0x14017a866  call    WPP_RECORDER_SF_q
0x14017a86b  test    cs:byte_14011B001, 8
0x14017a872  jz      short loc_14017A8A8
0x14017a874  mov     rax, [rbx+0FB8h]
0x14017a87b  lea     r8, [rbx+0FA8h]
0x14017a882  mov     dword ptr [rsp+1D0h+var_1A0], 10002h
0x14017a88a  lea     rdx, MiniportPoweringUp
0x14017a891  mov     qword ptr [rsp+1D0h+var_1A8], rax
0x14017a896  mov     r9, r8
0x14017a899  mov     eax, [rbx+0FD8h]
0x14017a89f  mov     dword ptr [rsp+1D0h+var_1B0], eax
0x14017a8a3  call    McTemplateK0jqxd_EtwWriteTransfer
0x14017a8a8  mov     edx, [rbx+7Ch]
0x14017a8ab  test    dl, 20h
0x14017a8ae  jz      loc_14017A9F0
0x14017a8b4  cmp     cs:?ndisAoAcCapable@@3EA, r12b; uchar ndisAoAcCapable
0x14017a8bb  jnz     short loc_14017A8C6
0x14017a8bd  cmp     cs:?ndisAoAcTest@@3EA, r12b; uchar ndisAoAcTest
0x14017a8c4  jz      short loc_14017A90E
0x14017a8c6  cmp     byte ptr [rbx+20h], 6
0x14017a8ca  ja      short loc_14017A8D4
0x14017a8cc  jnz     short loc_14017A90E
0x14017a8ce  cmp     byte ptr [rbx+21h], 1Eh
0x14017a8d2  jb      short loc_14017A90E
0x14017a8d4  lea     rdx, [rsp+1D0h+var_180]; unsigned __int8 *
0x14017a8d9  mov     rcx, rbx; struct _NDIS_MINIPORT_BLOCK *
0x14017a8dc  call    ?NDIS_ACQUIRE_MINIPORT_SPIN_LOCK@@YAXPEAU_NDIS_MINIPORT_BLOCK@@PEAE@Z; NDIS_ACQUIRE_MINIPORT_SPIN_LOCK(_NDIS_MINIPORT_BLOCK *,uchar *)
0x14017a8e1  mov     dl, 4; unsigned __int8
0x14017a8e3  mov     rcx, rbx; struct _NDIS_MINIPORT_BLOCK *
0x14017a8e6  call    ?ndisMRestoreOpenHandlers@@YAXPEAU_NDIS_MINIPORT_BLOCK@@E@Z; ndisMRestoreOpenHandlers(_NDIS_MINIPORT_BLOCK *,uchar)
0x14017a8eb  movzx   edx, [rsp+1D0h+var_180]; NewIrql
0x14017a8f0  lea     rcx, [rbx+60h]; SpinLock
0x14017a8f4  mov     qword ptr [rbx+208h], 0
0x14017a8ff  call    cs:__imp_KeReleaseSpinLock
0x14017a906  nop     dword ptr [rax+rax+00h]
0x14017a90b  mov     r13b, 1
0x14017a90e  mov     r9b, 1; unsigned __int8
0x14017a911  mov     r8d, 0FD010101h; unsigned int
0x14017a917  mov     edx, r14d; enum _DEVICE_POWER_STATE
0x14017a91a  mov     rcx, rbx; struct _NDIS_MINIPORT_BLOCK *
0x14017a91d  call    ?ndisQuerySetMiniportDeviceState@@YAHPEAU_NDIS_MINIPORT_BLOCK@@W4_DEVICE_POWER_STATE@@KE@Z; ndisQuerySetMiniportDeviceState(_NDIS_MINIPORT_BLOCK *,_DEVICE_POWER_STATE,ulong,uchar)
0x14017a922  mov     edi, eax
0x14017a924  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14017a92b  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14017a932  jz      short loc_14017A96A
0x14017a934  mov     rcx, cs:WPP_GLOBAL_Control
0x14017a93b  lea     rax, WPP_dc968d99198e32e9263b7dc94e457b33_Traceguids
0x14017a942  mov     dword ptr [rsp+1D0h+var_198], edi; char
0x14017a946  mov     r9d, 4Ah ; 'J'; int
0x14017a94c  mov     dword ptr [rsp+1D0h+var_1A0], r14d; char
0x14017a951  mov     r8d, 0Eh; int
0x14017a957  mov     qword ptr [rsp+1D0h+var_1A8], rbx; char
0x14017a95c  mov     rcx, [rcx+40h]; int
0x14017a960  mov     [rsp+1D0h+var_1B0], rax; struct _GUID *
0x14017a965  call    WPP_RECORDER_SF_qLL
0x14017a96a  test    edi, edi
0x14017a96c  jnz     short loc_14017A977
0x14017a96e  mov     [rbx+0F1Ch], r14d
0x14017a975  jmp     short loc_14017A9B6
0x14017a977  test    r13b, r13b
0x14017a97a  jz      short loc_14017A9B6
0x14017a97c  lea     rdx, [rsp+1D0h+var_180]; unsigned __int8 *
0x14017a981  mov     rcx, rbx; struct _NDIS_MINIPORT_BLOCK *
0x14017a984  call    ?NDIS_ACQUIRE_MINIPORT_SPIN_LOCK@@YAXPEAU_NDIS_MINIPORT_BLOCK@@PEAE@Z; NDIS_ACQUIRE_MINIPORT_SPIN_LOCK(_NDIS_MINIPORT_BLOCK *,uchar *)
0x14017a989  mov     dl, 4; unsigned __int8
0x14017a98b  mov     rcx, rbx; struct _NDIS_MINIPORT_BLOCK *
0x14017a98e  call    ?ndisMSwapOpenHandlers@@YAXPEAU_NDIS_MINIPORT_BLOCK@@E@Z; ndisMSwapOpenHandlers(_NDIS_MINIPORT_BLOCK *,uchar)
0x14017a993  movzx   edx, [rsp+1D0h+var_180]; NewIrql
0x14017a998  lea     rcx, [rbx+60h]; SpinLock
0x14017a99c  mov     qword ptr [rbx+208h], 0
0x14017a9a7  call    cs:__imp_KeReleaseSpinLock
0x14017a9ae  nop     dword ptr [rax+rax+00h]
0x14017a9b3  xor     r13b, r13b
0x14017a9b6  lea     rdx, [rsp+1D0h+var_180]; unsigned __int8 *
0x14017a9bb  mov     rcx, rbx; struct _NDIS_MINIPORT_BLOCK *
0x14017a9be  call    ?NDIS_ACQUIRE_MINIPORT_SPIN_LOCK@@YAXPEAU_NDIS_MINIPORT_BLOCK@@PEAE@Z; NDIS_ACQUIRE_MINIPORT_SPIN_LOCK(_NDIS_MINIPORT_BLOCK *,uchar *)
0x14017a9c3  mov     rcx, rbx; struct _NDIS_MINIPORT_BLOCK *
0x14017a9c6  call    ?ndisSetWakeUpTimer@@YAEPEAU_NDIS_MINIPORT_BLOCK@@@Z; ndisSetWakeUpTimer(_NDIS_MINIPORT_BLOCK *)
0x14017a9cb  movzx   edx, [rsp+1D0h+var_180]; NewIrql
0x14017a9d0  lea     r12, [rbx+60h]
0x14017a9d4  mov     rcx, r12; SpinLock
0x14017a9d7  mov     qword ptr [rbx+208h], 0
0x14017a9e2  call    cs:__imp_KeReleaseSpinLock
0x14017a9e9  nop     dword ptr [rax+rax+00h]
0x14017a9ee  jmp     short loc_14017AA21
0x14017a9f0  mov     rax, [rbx+0EB0h]
0x14017a9f7  xor     ecx, ecx
0x14017a9f9  movzx   eax, word ptr [rax+1Ah]
0x14017a9fd  bt      ax, cx
0x14017aa01  setnb   cl
0x14017aa04  bt      edx, 0Eh
0x14017aa08  setb    al
0x14017aa0b  test    al, cl
0x14017aa0d  jz      loc_14017AAFE
0x14017aa13  mov     rcx, rbx; struct _NDIS_MINIPORT_BLOCK *
0x14017aa16  call    ?ndisPmInitializeMiniport@@_Y2PAGENPNP@@AHPEAU_NDIS_MINIPORT_BLOCK@@@Z; ndisPmInitializeMiniport(_NDIS_MINIPORT_BLOCK *)
0x14017aa1b  mov     edi, eax
0x14017aa1d  lea     r12, [rbx+60h]
0x14017aa21  test    edi, edi
0x14017aa23  jnz     short loc_14017AA31
0x14017aa25  lea     rdi, WPP_dc968d99198e32e9263b7dc94e457b33_Traceguids
0x14017aa2c  jmp     loc_14017AB02
0x14017aa31  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14017aa38  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14017aa3f  jz      short loc_14017AA74
0x14017aa41  mov     rcx, cs:WPP_GLOBAL_Control
  ... truncated ...
```
