# ndisDevicePowerOn(void *)

- ea: `0x140180470`
- end: `0x1401811e8`
- name: `?ndisDevicePowerOn@@YAXPEAX@Z`
- size: `3448`
- prototype: `void __fastcall(void *)`
- caller_count: `0`
- callee_count: `47`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x1400075e0`
- `0x140009320`
- `0x1400095d0`
- `0x14000aab0`
- `0x140010d20`
- `0x1400110b0`
- `0x140011190`
- `0x1400114b0`
- `0x14003d6e0`
- `0x14003f590`
- `0x1400400d0`
- `0x1400416b0`
- `0x140041ae0`
- `0x140041bc0`
- `0x140041e40`
- `0x1400452c0`
- `0x140053280`
- `0x140055b00`
- `0x140057ac0`
- `0x14005a760`
- `0x14005b0e0`
- `0x140063390`
- `0x14006ddc0`
- `0x140073330`
- `0x140075220`
- `0x140080b80`
- `0x140088a2c`
- `0x140088dd0`
- `0x14008b110`
- `0x14008c71c`
- `0x1400ab248`
- `0x1400eb380`
- `0x1400eb7c0`
- `0x14013df20`
- `0x1401531e4`
- `0x14015bf10`
- `0x14015dae0`
- `0x14015ddf0`
- `0x14015dec0`
- `0x14015e6f0`
- `0x14015ed60`
- `0x14016a100`
- `0x14016b210`
- `0x14016d870`
- `0x14017a7a8`
- `0x14017e700`
- `0x140180470`

## import_xrefs

- `ntoskrnl!KeLowerIrql` at `0x140180f77`
- `ntoskrnl!KeLowerIrql` at `0x140180f77`
- `ntoskrnl!PoSetPowerState` at `0x14018061f`
- `ntoskrnl!PoSetPowerState` at `0x140180c57`
- `ntoskrnl!PoSetPowerState` at `0x14018061f`
- `ntoskrnl!PoSetPowerState` at `0x140180c57`
- `ntoskrnl!IofCompleteRequest` at `0x140180646`
- `ntoskrnl!IofCompleteRequest` at `0x1401806dc`
- `ntoskrnl!IofCompleteRequest` at `0x140180cfb`
- `ntoskrnl!IofCompleteRequest` at `0x140180646`
- `ntoskrnl!IofCompleteRequest` at `0x1401806dc`
- `ntoskrnl!IofCompleteRequest` at `0x140180cfb`
- `ntoskrnl!KeReleaseSpinLock` at `0x1401808cf`
- `ntoskrnl!KeReleaseSpinLock` at `0x140180977`
- `ntoskrnl!KeReleaseSpinLock` at `0x1401809b2`
- `ntoskrnl!KeReleaseSpinLock` at `0x140180b36`
- `ntoskrnl!KeReleaseSpinLock` at `0x140180cd2`
- `ntoskrnl!KeReleaseSpinLock` at `0x140180e48`
- `ntoskrnl!KeReleaseSpinLock` at `0x1401808cf`
- `ntoskrnl!KeReleaseSpinLock` at `0x140180977`
- `ntoskrnl!KeReleaseSpinLock` at `0x1401809b2`
- `ntoskrnl!KeReleaseSpinLock` at `0x140180b36`
- `ntoskrnl!KeReleaseSpinLock` at `0x140180cd2`
- `ntoskrnl!KeReleaseSpinLock` at `0x140180e48`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140180e9b`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140180e9b`
- `HAL!KeStallExecutionProcessor` at `0x140180e59`
- `HAL!KeStallExecutionProcessor` at `0x140180e59`

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
    if ( (byte_140121001 & 8) != 0 )
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
    if ( (byte_140121001 & 8) != 0 )
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
        if ( (byte_140121003 & 2) != 0 )
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
            if ( (unsigned __int8)byte_140122AD3 >= 4u )
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
    if ( (byte_140121001 & 8) != 0 )
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
  if ( (byte_140121001 & 8) != 0 )
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
0x140180470  push    rbp
0x140180472  push    rbx
0x140180473  push    rdi
0x140180474  push    r12
0x140180476  push    r13
0x140180478  lea     rbp, [rsp-0B0h]
0x140180480  sub     rsp, 1B0h
0x140180487  mov     rax, cs:__security_cookie
0x14018048e  xor     rax, rsp
0x140180491  mov     [rbp+0D0h+var_28], rax
0x140180498  mov     rdi, rcx
0x14018049b  lea     rbx, [rcx-1508h]
0x1401804a2  xor     r13d, r13d
0x1401804a5  lea     rcx, [rbp+0D0h+StatusIndication]; void *
0x1401804a9  xor     edx, edx; Val
0x1401804ab  mov     [rsp+1D0h+var_178], r13d
0x1401804b0  mov     r8d, 70h ; 'p'; Size
0x1401804b6  mov     [rsp+1D0h+var_180], r13b
0x1401804bb  call    memset
0x1401804c0  xor     eax, eax
0x1401804c2  xorps   xmm0, xmm0
0x1401804c5  mov     [rbp+0D0h+var_60], rax
0x1401804c9  mov     [rbp+0D0h+var_58], eax
0x1401804cc  movups  [rbp+0D0h+var_50], xmm0
0x1401804d3  mov     [rbp+0D0h+var_30], rax
0x1401804da  movups  [rbp+0D0h+var_40], xmm0
0x1401804e1  lea     r12, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x1401804e8  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x1401804ef  lea     rax, WPP_dc968d99198e32e9263b7dc94e457b33_Traceguids
0x1401804f6  jz      short loc_140180520
0x1401804f8  mov     rcx, cs:WPP_GLOBAL_Control
0x1401804ff  mov     r9d, 43h ; 'C'; int
0x140180505  mov     qword ptr [rsp+1D0h+var_1A8], rbx; char
0x14018050a  mov     r8d, 0Eh; int
0x140180510  mov     dl, 4; int
0x140180512  mov     [rsp+1D0h+var_1B0], rax; struct _GUID *
0x140180517  mov     rcx, [rcx+40h]; int
0x14018051b  call    WPP_RECORDER_SF_q
0x140180520  mov     [rsp+1D0h+arg_8], rsi
0x140180528  lea     rcx, ?ndisPkgs@@3PAU_PKG_REF@@A; struct _PKG_REF *
0x14018052f  mov     [rsp+1D0h+arg_10], r14
0x140180537  mov     [rsp+1D0h+arg_18], r15
0x14018053f  call    ?ndisReferencePackage@@YAXPEAU_PKG_REF@@@Z; ndisReferencePackage(_PKG_REF *)
0x140180544  mov     edx, 80h; unsigned int
0x140180549  mov     rcx, rbx; struct _NDIS_MINIPORT_BLOCK *
0x14018054c  call    ?MINIPORT_TEST_FLAG@@YAEPEBU_NDIS_MINIPORT_BLOCK@@K@Z; MINIPORT_TEST_FLAG(_NDIS_MINIPORT_BLOCK const *,ulong)
0x140180551  test    al, al
0x140180553  jnz     short loc_14018056A
0x140180555  mov     rsi, [rdi+20h]
0x140180559  mov     rax, [rsi+0B8h]
0x140180560  mov     r15d, [rsi+30h]
0x140180564  mov     r14d, [rax+18h]
0x140180568  jmp     short loc_140180576
0x14018056a  mov     rsi, r13
0x14018056d  mov     r15d, r13d
0x140180570  mov     r14d, 1
0x140180576  mov     [rdi+20h], r13
0x14018057a  cmp     dword ptr [rbx+5F0h], 1
0x140180581  jz      loc_140180657
0x140180587  call    ?MINIPORT_TEST_FLAG@@YAEPEBU_NDIS_MINIPORT_BLOCK@@K@Z; MINIPORT_TEST_FLAG(_NDIS_MINIPORT_BLOCK const *,ulong)
0x14018058c  cmp     cs:WPP_RECORDER_INITIALIZED, r12; __annotation("TMF:",
0x140180593  jz      short loc_1401805C4
0x140180595  mov     rcx, cs:WPP_GLOBAL_Control
0x14018059c  lea     rax, WPP_dc968d99198e32e9263b7dc94e457b33_Traceguids
0x1401805a3  mov     r9d, 44h ; 'D'; int
0x1401805a9  mov     qword ptr [rsp+1D0h+var_1A8], rbx; char
0x1401805ae  mov     r8d, 0Eh; int
0x1401805b4  mov     [rsp+1D0h+var_1B0], rax; struct _GUID *
0x1401805b9  mov     dl, 4; int
0x1401805bb  mov     rcx, [rcx+40h]; int
0x1401805bf  call    WPP_RECORDER_SF_q
0x1401805c4  test    cs:byte_140121001, 8
0x1401805cb  jz      short loc_140180601
0x1401805cd  mov     rax, [rbx+0FB8h]
0x1401805d4  lea     r8, [rbx+0FA8h]
0x1401805db  mov     dword ptr [rsp+1D0h+var_1A0], 10001h
0x1401805e3  lea     rdx, PowerOnMiniportNotStarted
0x1401805ea  mov     qword ptr [rsp+1D0h+var_1A8], rax
0x1401805ef  mov     r9, r8
0x1401805f2  mov     eax, [rbx+0FD8h]
0x1401805f8  mov     dword ptr [rsp+1D0h+var_1B0], eax
0x1401805fc  call    McTemplateK0jqxd_EtwWriteTransfer
0x140180601  mov     rax, [rsi+0B8h]
0x140180608  mov     edx, 1; Type
0x14018060d  mov     rcx, [rbx+0EF0h]; DeviceObject
0x140180614  mov     r8d, [rax+18h]; State
0x140180618  mov     [rbx+0F1Ch], r8d
0x14018061f  call    cs:__imp_PoSetPowerState
0x140180626  nop     dword ptr [rax+rax+00h]
0x14018062b  lea     rcx, [rbx+1478h]
0x140180632  call    ?Release@?$KNeutralLock@W4NDIS_MINIPORT_POLICY_OWNER@@@Rtl@@QEAAXW4NDIS_MINIPORT_POLICY_OWNER@@@Z; Rtl::KNeutralLock<NDIS_MINIPORT_POLICY_OWNER>::Release(NDIS_MINIPORT_POLICY_OWNER)
0x140180637  xor     edx, edx; int
0x140180639  mov     rcx, rbx; struct _NDIS_MINIPORT_BLOCK *
0x14018063c  call    ?ndisScheduleD0CompleteSignalWorkItem@@YAXPEAU_NDIS_MINIPORT_BLOCK@@J@Z; ndisScheduleD0CompleteSignalWorkItem(_NDIS_MINIPORT_BLOCK *,long)
0x140180641  xor     edx, edx; PriorityBoost
0x140180643  mov     rcx, rsi; Irp
0x140180646  call    cs:__imp_IofCompleteRequest
0x14018064d  nop     dword ptr [rax+rax+00h]
0x140180652  jmp     loc_14018119B
0x140180657  mov     eax, [rbx+7Ch]
0x14018065a  test    al, 10h
0x14018065c  jz      loc_14018074E
0x140180662  cmp     cs:WPP_RECORDER_INITIALIZED, r12; __annotation("TMF:",
0x140180669  lea     rdi, WPP_dc968d99198e32e9263b7dc94e457b33_Traceguids
0x140180670  jz      short loc_14018069A
0x140180672  mov     rcx, cs:WPP_GLOBAL_Control
0x140180679  mov     r9d, 45h ; 'E'; int
0x14018067f  mov     qword ptr [rsp+1D0h+var_1A8], rbx; char
0x140180684  mov     r8d, 0Eh; int
0x14018068a  mov     dl, 4; int
0x14018068c  mov     [rsp+1D0h+var_1B0], rdi; struct _GUID *
0x140180691  mov     rcx, [rcx+40h]; int
0x140180695  call    WPP_RECORDER_SF_q
0x14018069a  test    cs:byte_140121001, 8
0x1401806a1  jz      short loc_1401806D7
0x1401806a3  mov     rax, [rbx+0FB8h]
0x1401806aa  lea     r8, [rbx+0FA8h]
0x1401806b1  mov     dword ptr [rsp+1D0h+var_1A0], 10001h
0x1401806b9  lea     rdx, PowerOnMiniportRemoved
0x1401806c0  mov     qword ptr [rsp+1D0h+var_1A8], rax
0x1401806c5  mov     r9, r8
0x1401806c8  mov     eax, [rbx+0FD8h]
0x1401806ce  mov     dword ptr [rsp+1D0h+var_1B0], eax
0x1401806d2  call    McTemplateK0jqxd_EtwWriteTransfer
0x1401806d7  xor     edx, edx; PriorityBoost
0x1401806d9  mov     rcx, rsi; Irp
0x1401806dc  call    cs:__imp_IofCompleteRequest
0x1401806e3  nop     dword ptr [rax+rax+00h]
0x1401806e8  lea     rcx, [rbx+1478h]
0x1401806ef  call    ?Release@?$KNeutralLock@W4NDIS_MINIPORT_POLICY_OWNER@@@Rtl@@QEAAXW4NDIS_MINIPORT_POLICY_OWNER@@@Z; Rtl::KNeutralLock<NDIS_MINIPORT_POLICY_OWNER>::Release(NDIS_MINIPORT_POLICY_OWNER)
0x1401806f4  xor     edx, edx; int
0x1401806f6  mov     rcx, rbx; struct _NDIS_MINIPORT_BLOCK *
0x1401806f9  call    ?ndisSignalD0RequestComplete@@YAXPEAU_NDIS_MINIPORT_BLOCK@@J@Z; ndisSignalD0RequestComplete(_NDIS_MINIPORT_BLOCK *,long)
0x1401806fe  mov     dl, 0Ch; enum _NDIS_MP_REFTAG
0x140180700  mov     rcx, rbx; struct _NDIS_MINIPORT_BLOCK *
0x140180703  call    ?ndisDereferenceMiniport@@YAXPEAU_NDIS_MINIPORT_BLOCK@@W4_NDIS_MP_REFTAG@@@Z; ndisDereferenceMiniport(_NDIS_MINIPORT_BLOCK *,_NDIS_MP_REFTAG)
0x140180708  lea     rcx, ?ndisPkgs@@3PAU_PKG_REF@@A; struct _PKG_REF *
0x14018070f  call    ?ndisDereferencePackage@@YAXPEAU_PKG_REF@@@Z; ndisDereferencePackage(_PKG_REF *)
0x140180714  cmp     cs:WPP_RECORDER_INITIALIZED, r12; __annotation("TMF:",
0x14018071b  jz      loc_1401811B1
0x140180721  mov     rcx, cs:WPP_GLOBAL_Control
0x140180728  mov     r9d, 46h ; 'F'; int
0x14018072e  mov     qword ptr [rsp+1D0h+var_1A8], rbx; char
0x140180733  mov     r8d, 0Eh; int
0x140180739  mov     dl, 4; int
0x14018073b  mov     [rsp+1D0h+var_1B0], rdi; struct _GUID *
0x140180740  mov     rcx, [rcx+40h]; int
0x140180744  call    WPP_RECORDER_SF_q
0x140180749  jmp     loc_1401811B1
0x14018074e  xor     dil, dil
0x140180751  mov     [rsp+1D0h+var_17C], r13d
0x140180756  xor     r12b, r12b
0x140180759  mov     [rsp+1D0h+var_17F], dil
0x14018075e  test    r15d, r15d
0x140180761  jns     short loc_1401807B0
0x140180763  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14018076a  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140180771  jz      loc_140180CE1
0x140180777  mov     rcx, cs:WPP_GLOBAL_Control
0x14018077e  lea     rax, WPP_dc968d99198e32e9263b7dc94e457b33_Traceguids
0x140180785  mov     dword ptr [rsp+1D0h+var_1A0], r15d; char
0x14018078a  mov     r9d, 47h ; 'G'; int
0x140180790  mov     qword ptr [rsp+1D0h+var_1A8], rbx; char
0x140180795  mov     r8d, 0Eh; int
0x14018079b  mov     dl, 4; int
0x14018079d  mov     [rsp+1D0h+var_1B0], rax; struct _GUID *
0x1401807a2  mov     rcx, [rcx+40h]; int
0x1401807a6  call    WPP_RECORDER_SF_qL
0x1401807ab  jmp     loc_140180CE1
0x1401807b0  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x1401807b7  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1401807be  jz      short loc_1401807F6
0x1401807c0  mov     rcx, cs:WPP_GLOBAL_Control
0x1401807c7  lea     rax, WPP_dc968d99198e32e9263b7dc94e457b33_Traceguids
0x1401807ce  mov     r9d, 48h ; 'H'; int
0x1401807d4  mov     qword ptr [rsp+1D0h+var_1A8], rbx; char
0x1401807d9  mov     r8d, 0Eh; int
0x1401807df  mov     [rsp+1D0h+var_1B0], rax; struct _GUID *
0x1401807e4  mov     dl, 4; int
0x1401807e6  mov     rcx, [rcx+40h]; int
0x1401807ea  call    WPP_RECORDER_SF_q
0x1401807ef  lea     rax, WPP_RECORDER_INITIALIZED
0x1401807f6  cmp     dword ptr [rbx+0F1Ch], 1
0x1401807fd  jz      loc_140180C80
0x140180803  cmp     cs:WPP_RECORDER_INITIALIZED, rax; __annotation("TMF:",
0x14018080a  lea     rdi, WPP_dc968d99198e32e9263b7dc94e457b33_Traceguids
0x140180811  jz      short loc_14018083B
0x140180813  mov     rcx, cs:WPP_GLOBAL_Control
0x14018081a  mov     r9d, 49h ; 'I'; int
0x140180820  mov     qword ptr [rsp+1D0h+var_1A8], rbx; char
0x140180825  mov     r8d, 0Eh; int
0x14018082b  mov     dl, 4; int
0x14018082d  mov     [rsp+1D0h+var_1B0], rdi; struct _GUID *
0x140180832  mov     rcx, [rcx+40h]; int
0x140180836  call    WPP_RECORDER_SF_q
0x14018083b  test    cs:byte_140121001, 8
0x140180842  jz      short loc_140180878
0x140180844  mov     rax, [rbx+0FB8h]
0x14018084b  lea     r8, [rbx+0FA8h]
0x140180852  mov     dword ptr [rsp+1D0h+var_1A0], 10002h
0x14018085a  lea     rdx, MiniportPoweringUp
0x140180861  mov     qword ptr [rsp+1D0h+var_1A8], rax
0x140180866  mov     r9, r8
0x140180869  mov     eax, [rbx+0FD8h]
0x14018086f  mov     dword ptr [rsp+1D0h+var_1B0], eax
0x140180873  call    McTemplateK0jqxd_EtwWriteTransfer
0x140180878  mov     edx, [rbx+7Ch]
0x14018087b  test    dl, 20h
0x14018087e  jz      loc_1401809C0
0x140180884  cmp     cs:?ndisAoAcCapable@@3EA, r12b; uchar ndisAoAcCapable
0x14018088b  jnz     short loc_140180896
0x14018088d  cmp     cs:?ndisAoAcTest@@3EA, r12b; uchar ndisAoAcTest
0x140180894  jz      short loc_1401808DE
0x140180896  cmp     byte ptr [rbx+20h], 6
0x14018089a  ja      short loc_1401808A4
0x14018089c  jnz     short loc_1401808DE
0x14018089e  cmp     byte ptr [rbx+21h], 1Eh
0x1401808a2  jb      short loc_1401808DE
0x1401808a4  lea     rdx, [rsp+1D0h+var_180]; unsigned __int8 *
0x1401808a9  mov     rcx, rbx; struct _NDIS_MINIPORT_BLOCK *
0x1401808ac  call    ?NDIS_ACQUIRE_MINIPORT_SPIN_LOCK@@YAXPEAU_NDIS_MINIPORT_BLOCK@@PEAE@Z; NDIS_ACQUIRE_MINIPORT_SPIN_LOCK(_NDIS_MINIPORT_BLOCK *,uchar *)
0x1401808b1  mov     dl, 4; unsigned __int8
0x1401808b3  mov     rcx, rbx; struct _NDIS_MINIPORT_BLOCK *
0x1401808b6  call    ?ndisMRestoreOpenHandlers@@YAXPEAU_NDIS_MINIPORT_BLOCK@@E@Z; ndisMRestoreOpenHandlers(_NDIS_MINIPORT_BLOCK *,uchar)
0x1401808bb  movzx   edx, [rsp+1D0h+var_180]; NewIrql
0x1401808c0  lea     rcx, [rbx+60h]; SpinLock
0x1401808c4  mov     qword ptr [rbx+208h], 0
0x1401808cf  call    cs:__imp_KeReleaseSpinLock
0x1401808d6  nop     dword ptr [rax+rax+00h]
0x1401808db  mov     r13b, 1
0x1401808de  mov     r9b, 1; unsigned __int8
0x1401808e1  mov     r8d, 0FD010101h; unsigned int
0x1401808e7  mov     edx, r14d; enum _DEVICE_POWER_STATE
0x1401808ea  mov     rcx, rbx; struct _NDIS_MINIPORT_BLOCK *
0x1401808ed  call    ?ndisQuerySetMiniportDeviceState@@YAHPEAU_NDIS_MINIPORT_BLOCK@@W4_DEVICE_POWER_STATE@@KE@Z; ndisQuerySetMiniportDeviceState(_NDIS_MINIPORT_BLOCK *,_DEVICE_POWER_STATE,ulong,uchar)
0x1401808f2  mov     edi, eax
0x1401808f4  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x1401808fb  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140180902  jz      short loc_14018093A
0x140180904  mov     rcx, cs:WPP_GLOBAL_Control
0x14018090b  lea     rax, WPP_dc968d99198e32e9263b7dc94e457b33_Traceguids
0x140180912  mov     dword ptr [rsp+1D0h+var_198], edi; char
0x140180916  mov     r9d, 4Ah ; 'J'; int
0x14018091c  mov     dword ptr [rsp+1D0h+var_1A0], r14d; char
0x140180921  mov     r8d, 0Eh; int
0x140180927  mov     qword ptr [rsp+1D0h+var_1A8], rbx; char
0x14018092c  mov     rcx, [rcx+40h]; int
0x140180930  mov     [rsp+1D0h+var_1B0], rax; struct _GUID *
0x140180935  call    WPP_RECORDER_SF_qLL
0x14018093a  test    edi, edi
0x14018093c  jnz     short loc_140180947
0x14018093e  mov     [rbx+0F1Ch], r14d
0x140180945  jmp     short loc_140180986
0x140180947  test    r13b, r13b
0x14018094a  jz      short loc_140180986
0x14018094c  lea     rdx, [rsp+1D0h+var_180]; unsigned __int8 *
0x140180951  mov     rcx, rbx; struct _NDIS_MINIPORT_BLOCK *
0x140180954  call    ?NDIS_ACQUIRE_MINIPORT_SPIN_LOCK@@YAXPEAU_NDIS_MINIPORT_BLOCK@@PEAE@Z; NDIS_ACQUIRE_MINIPORT_SPIN_LOCK(_NDIS_MINIPORT_BLOCK *,uchar *)
0x140180959  mov     dl, 4; unsigned __int8
0x14018095b  mov     rcx, rbx; struct _NDIS_MINIPORT_BLOCK *
0x14018095e  call    ?ndisMSwapOpenHandlers@@YAXPEAU_NDIS_MINIPORT_BLOCK@@E@Z; ndisMSwapOpenHandlers(_NDIS_MINIPORT_BLOCK *,uchar)
0x140180963  movzx   edx, [rsp+1D0h+var_180]; NewIrql
0x140180968  lea     rcx, [rbx+60h]; SpinLock
0x14018096c  mov     qword ptr [rbx+208h], 0
0x140180977  call    cs:__imp_KeReleaseSpinLock
0x14018097e  nop     dword ptr [rax+rax+00h]
0x140180983  xor     r13b, r13b
0x140180986  lea     rdx, [rsp+1D0h+var_180]; unsigned __int8 *
0x14018098b  mov     rcx, rbx; struct _NDIS_MINIPORT_BLOCK *
0x14018098e  call    ?NDIS_ACQUIRE_MINIPORT_SPIN_LOCK@@YAXPEAU_NDIS_MINIPORT_BLOCK@@PEAE@Z; NDIS_ACQUIRE_MINIPORT_SPIN_LOCK(_NDIS_MINIPORT_BLOCK *,uchar *)
0x140180993  mov     rcx, rbx; struct _NDIS_MINIPORT_BLOCK *
0x140180996  call    ?ndisSetWakeUpTimer@@YAEPEAU_NDIS_MINIPORT_BLOCK@@@Z; ndisSetWakeUpTimer(_NDIS_MINIPORT_BLOCK *)
0x14018099b  movzx   edx, [rsp+1D0h+var_180]; NewIrql
0x1401809a0  lea     r12, [rbx+60h]
0x1401809a4  mov     rcx, r12; SpinLock
0x1401809a7  mov     qword ptr [rbx+208h], 0
0x1401809b2  call    cs:__imp_KeReleaseSpinLock
0x1401809b9  nop     dword ptr [rax+rax+00h]
0x1401809be  jmp     short loc_1401809F1
0x1401809c0  mov     rax, [rbx+0EB0h]
0x1401809c7  xor     ecx, ecx
0x1401809c9  movzx   eax, word ptr [rax+1Ah]
0x1401809cd  bt      ax, cx
0x1401809d1  setnb   cl
0x1401809d4  bt      edx, 0Eh
0x1401809d8  setb    al
0x1401809db  test    al, cl
0x1401809dd  jz      loc_140180ACE
0x1401809e3  mov     rcx, rbx; struct _NDIS_MINIPORT_BLOCK *
0x1401809e6  call    ?ndisPmInitializeMiniport@@_Y2PAGENPNP@@AHPEAU_NDIS_MINIPORT_BLOCK@@@Z; ndisPmInitializeMiniport(_NDIS_MINIPORT_BLOCK *)
0x1401809eb  mov     edi, eax
0x1401809ed  lea     r12, [rbx+60h]
0x1401809f1  test    edi, edi
0x1401809f3  jnz     short loc_140180A01
0x1401809f5  lea     rdi, WPP_dc968d99198e32e9263b7dc94e457b33_Traceguids
0x1401809fc  jmp     loc_140180AD2
0x140180a01  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140180a08  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140180a0f  jz      short loc_140180A44
0x140180a11  mov     rcx, cs:WPP_GLOBAL_Control
  ... truncated ...
```
