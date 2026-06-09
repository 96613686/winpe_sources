# ndisDevicePowerDown(void *)

- ea: `0x140179ea0`
- end: `0x14017a62a`
- name: `?ndisDevicePowerDown@@YAXPEAX@Z`
- size: `1930`
- prototype: `void __fastcall(void *)`
- caller_count: `0`
- callee_count: `35`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callees

- `0x1400075e0`
- `0x140009320`
- `0x1400095d0`
- `0x14000aab0`
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
- `0x140053280`
- `0x140055b00`
- `0x14005b0e0`
- `0x140063390`
- `0x14006ddc0`
- `0x140080b80`
- `0x140088a2c`
- `0x1400eb380`
- `0x1400eb7c0`
- `0x14013df20`
- `0x1401531e4`
- `0x14015bf10`
- `0x14015dae0`
- `0x14015dec0`
- `0x14015e6f0`
- `0x14015ed60`
- `0x14016a100`
- `0x14016b210`
- `0x14016d870`
- `0x140179ea0`
- `0x14017a7a8`

## import_xrefs

- `ntoskrnl!PoSetPowerState` at `0x14017a4c1`
- `ntoskrnl!PoSetPowerState` at `0x14017a4c1`
- `ntoskrnl!IofCompleteRequest` at `0x14017a5b8`
- `ntoskrnl!IofCompleteRequest` at `0x14017a5b8`
- `ntoskrnl!KeReleaseSpinLock` at `0x14017a1ea`
- `ntoskrnl!KeReleaseSpinLock` at `0x14017a484`
- `ntoskrnl!KeReleaseSpinLock` at `0x14017a1ea`
- `ntoskrnl!KeReleaseSpinLock` at `0x14017a484`

## pseudocode

```c
void __fastcall ndisDevicePowerDown(_QWORD *a1)
{
  int v1; // r13d
  char *v3; // rbx
  int v4; // edx
  int v5; // edx
  struct _NDIS_MINIPORT_BLOCK *v6; // rcx
  IRP *v7; // rdi
  int Status; // r14d
  enum _NDIS_DEVICE_POWER_STATE LowPart; // r15d
  __int64 v10; // rcx
  _DWORD *v11; // r13
  int v12; // edx
  enum _DEVICE_POWER_STATE v13; // r12d
  __int64 v14; // rcx
  int v15; // edx
  int SetMiniportDeviceState; // r15d
  int v17; // edx
  int v18; // ecx
  int v19; // edx
  unsigned __int8 v20; // al
  KIRQL v21; // dl
  int v22; // r15d
  signed __int32 v23; // eax
  signed __int32 v24; // ett
  __int64 v25; // rax
  __int64 v26; // rcx
  unsigned int v27; // eax
  __int64 v28; // rax
  __int64 v29; // rcx
  int v30; // eax
  KIRQL v31; // dl
  __int64 v32; // rcx
  int v33; // edx
  KIRQL NewIrql[4]; // [rsp+50h] [rbp-B0h] BYREF
  int v35; // [rsp+54h] [rbp-ACh]
  char v36[160]; // [rsp+60h] [rbp-A0h] BYREF
  struct _NDIS_STATUS_INDICATION StatusIndication; // [rsp+100h] [rbp+0h] BYREF
  _QWORD v38[2]; // [rsp+170h] [rbp+70h] BYREF

  v1 = 0;
  NewIrql[0] = 0;
  v35 = 0;
  v3 = (char *)(a1 - 678);
  memset(&StatusIndication, 0, sizeof(StatusIndication));
  memset(v38, 0, 12);
  if ( *(enum Ndis::ReadBindingsOptions::Flags **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v4) = 4;
    WPP_RECORDER_SF_q(
      *((_QWORD *)WPP_GLOBAL_Control + 8),
      v4,
      14,
      82,
      (struct _GUID *)&WPP_dc968d99198e32e9263b7dc94e457b33_Traceguids,
      (char)v3);
  }
  ndisReferencePackage((struct _PKG_REF *)&ndisPkgs);
  if ( MINIPORT_TEST_FLAG((const struct _NDIS_MINIPORT_BLOCK *)v3, 0x80u) )
  {
    v7 = 0;
    Status = 0;
    a1[4] = 0;
    LowPart = NdisDeviceStateD3;
    goto LABEL_43;
  }
  v7 = (IRP *)a1[4];
  Status = v7->IoStatus.Status;
  LowPart = v7->Tail.Overlay.CurrentStackLocation->Parameters.Read.ByteOffset.LowPart;
  a1[4] = 0;
  if ( Status >= 0 )
  {
LABEL_43:
    if ( *(enum Ndis::ReadBindingsOptions::Flags **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v5) = 4;
      WPP_RECORDER_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 8),
        v5,
        14,
        83,
        (struct _GUID *)&WPP_dc968d99198e32e9263b7dc94e457b33_Traceguids,
        (char)v3,
        LowPart);
    }
    NDIS_COUNT_POWER_TRANSITION((struct _NDIS_MINIPORT_BLOCK *)v3, LowPart);
    if ( (byte_140121001 & 8) != 0 )
      McTemplateK0jqxqq_EtwWriteTransfer(
        v26,
        DevicePowerStateChange,
        v3 + 4008,
        v3 + 4008,
        *((_DWORD *)v3 + 1014),
        *((_QWORD *)v3 + 503),
        1,
        LowPart);
    NDIS_ACQUIRE_MINIPORT_SPIN_LOCK((struct _NDIS_MINIPORT_BLOCK *)v3, NewIrql);
    v27 = *((_DWORD *)v3 + 1017) & 0xFEFFFFFF;
    *((_DWORD *)v3 + 1016) = 5;
    *((_DWORD *)v3 + 1017) = v27 | 8;
    if ( ndisMReferenceIfBlock((struct _NDIS_MINIPORT_BLOCK *)v3, MPIFREF_POWERDOWN) )
    {
      v28 = *((_QWORD *)v3 + 505);
      if ( *(_DWORD *)(v28 + 1112) != 5 )
      {
        *(_DWORD *)(v28 + 1112) = 5;
        v1 = 1;
        v29 = *((_QWORD *)v3 + 505);
        v30 = *((_DWORD *)v3 + 1017);
        v35 = 1;
        *(_DWORD *)(v29 + 1116) = v30;
      }
      ndisMDereferenceIfBlock((struct _NDIS_MINIPORT_BLOCK *)v3, MPIFREF_POWERDOWN);
    }
    v31 = NewIrql[0];
    *((_QWORD *)v3 + 65) = 0;
    KeReleaseSpinLock((PKSPIN_LOCK)v3 + 12, v31);
    if ( v1 )
      ndisNsiSyncMiniportOperStatusNotification((struct _NDIS_MINIPORT_BLOCK *)v3);
    *((_DWORD *)v3 + 967) = LowPart;
    if ( !MINIPORT_TEST_FLAG((const struct _NDIS_MINIPORT_BLOCK *)v3, 0x80u) )
      PoSetPowerState(*((PDEVICE_OBJECT *)v3 + 478), DevicePowerState, (POWER_STATE)LowPart);
    v22 = v35;
    v11 = v3 + 1520;
    goto LABEL_56;
  }
  if ( !ndisIsMiniportStarted(v6) )
    goto LABEL_60;
  v11 = v3 + 1520;
  if ( *((_DWORD *)v3 + 380) != 1 )
    goto LABEL_60;
  if ( MINIPORT_TEST_FLAG((const struct _NDIS_MINIPORT_BLOCK *)v3, 0x80u) )
    NT_ASSERT("0");
  if ( *(enum Ndis::ReadBindingsOptions::Flags **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v12) = 2;
    WPP_RECORDER_SF_qL(
      *((_QWORD *)WPP_GLOBAL_Control + 8),
      v12,
      14,
      84,
      (struct _GUID *)&WPP_dc968d99198e32e9263b7dc94e457b33_Traceguids,
      (char)v3,
      v7->IoStatus.Status);
  }
  v13 = *((_DWORD *)v3 + 967);
  if ( *(enum Ndis::ReadBindingsOptions::Flags **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v12) = 4;
    WPP_RECORDER_SF_qD(
      *((_QWORD *)WPP_GLOBAL_Control + 8),
      v12,
      14,
      85,
      (struct _GUID *)&WPP_dc968d99198e32e9263b7dc94e457b33_Traceguids,
      (char)v3,
      *((_DWORD *)v3 + 967));
  }
  NDIS_COUNT_POWER_TRANSITION((struct _NDIS_MINIPORT_BLOCK *)v3, *((enum _NDIS_DEVICE_POWER_STATE *)v3 + 967));
  if ( (byte_140121001 & 8) != 0 )
    McTemplateK0jqxqq_EtwWriteTransfer(
      v14,
      DevicePowerStateChange,
      v3 + 4008,
      v3 + 4008,
      *((_DWORD *)v3 + 1014),
      *((_QWORD *)v3 + 503),
      1,
      *((_DWORD *)v3 + 967));
  if ( (*((_DWORD *)v3 + 31) & 0x20) != 0 )
  {
    SetMiniportDeviceState = ndisQuerySetMiniportDeviceState((struct _NDIS_MINIPORT_BLOCK *)v3, v13, 0xFD010101, 1u);
    if ( *(enum Ndis::ReadBindingsOptions::Flags **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_SF_qLL(
        *((_QWORD *)WPP_GLOBAL_Control + 8),
        v15,
        14,
        86,
        (struct _GUID *)&WPP_dc968d99198e32e9263b7dc94e457b33_Traceguids,
        (char)v3,
        v13,
        SetMiniportDeviceState);
  }
  else
  {
    SetMiniportDeviceState = ndisPmInitializeMiniport((struct _NDIS_MINIPORT_BLOCK *)v3);
  }
  Rtl::KNeutralLock<enum NDIS_MINIPORT_POLICY_OWNER>::Release(v3 + 5240);
  if ( SetMiniportDeviceState )
  {
    if ( *(enum Ndis::ReadBindingsOptions::Flags **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v17) = 4;
      WPP_RECORDER_SF_q(
        *((_QWORD *)WPP_GLOBAL_Control + 8),
        v17,
        14,
        88,
        (struct _GUID *)&WPP_dc968d99198e32e9263b7dc94e457b33_Traceguids,
        (char)v3);
    }
    if ( (byte_140121002 & 0x40) != 0 )
      McTemplateK0jqxddq_EtwWriteTransfer(
        v18,
        (unsigned int)PowerDownFailedCannotReinitialize,
        (_DWORD)v3 + 4008,
        (_DWORD)v3 + 4008,
        *((_DWORD *)v3 + 1014),
        *((_QWORD *)v3 + 503),
        SetMiniportDeviceState,
        1,
        0);
    if ( ndisMReferenceIfBlock((struct _NDIS_MINIPORT_BLOCK *)v3, MPIFREF_POWERDOWNFAIL) )
    {
      v25 = *((_QWORD *)v3 + 505);
      *((_QWORD *)v3 + 508) = 2;
      if ( *(_DWORD *)(v25 + 1112) == 2 )
      {
        v22 = v35;
      }
      else
      {
        *(_DWORD *)(v25 + 1112) = 2;
        *(_DWORD *)(*((_QWORD *)v3 + 505) + 1116LL) = 0;
        ndisNsiSyncMiniportOperStatusNotification((struct _NDIS_MINIPORT_BLOCK *)v3);
        v22 = 1;
      }
      ndisMDereferenceIfBlock((struct _NDIS_MINIPORT_BLOCK *)v3, MPIFREF_POWERDOWNFAIL);
    }
    else
    {
      v22 = v35;
    }
    ndisMiniportFatalError((struct _NDIS_MINIPORT_BLOCK *)v3, NdisMEventErr_FailedPowerDx);
    if ( MINIPORT_TEST_FLAG((const struct _NDIS_MINIPORT_BLOCK *)v3, 0x80u) )
      Status = -1073741823;
    else
      v7->IoStatus.Status = -1073741823;
  }
  else
  {
    Ndis::BindEngine::BeginPolicyUpdates((Ndis::BindEngine *)(v3 + 5120));
    if ( Ndis::BindState::SetPause((Ndis::BindState *)(v3 + 5048), DatapathRunning, PauseReason_LowPower) )
    {
      memset(v36, 0, sizeof(v36));
      if ( (unsigned __int8)byte_140122AD3 >= 4u )
      {
        ndisGetBindLinkNameForTracing((struct _NDIS_MINIPORT_BLOCK *)v3, (struct NDIS_PNPTRACE_LOCALS *)v36);
        if ( *(enum Ndis::ReadBindingsOptions::Flags **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
          WPP_RECORDER_SF_Zq(
            *((_QWORD *)WPP_GLOBAL_Control + 8),
            v19,
            28,
            87,
            (struct _GUID *)&WPP_dc968d99198e32e9263b7dc94e457b33_Traceguids,
            *(__int64 *)&v36[8],
            v36[0]);
      }
    }
    Ndis::BindEngine::EndPolicyUpdates((Ndis::BindEngine *)(v3 + 5120));
    Ndis::BindEngine::ApplyBindChanges((Ndis::BindEngine *)(v3 + 5120), RunSynchronous, 0);
    NDIS_ACQUIRE_MINIPORT_SPIN_LOCK((struct _NDIS_MINIPORT_BLOCK *)v3, NewIrql);
    ndisMRestoreOpenHandlers((struct _NDIS_MINIPORT_BLOCK *)v3, 4u);
    v20 = ndisIfSetInterfaceState((struct _NDIS_MINIPORT_BLOCK *)v3, 1u, NewIrql[0]);
    v21 = NewIrql[0];
    v22 = v20;
    *((_QWORD *)v3 + 65) = 0;
    KeReleaseSpinLock((PKSPIN_LOCK)v3 + 12, v21);
    _m_prefetchw(v3 + 4424);
    v23 = *((_DWORD *)v3 + 1106);
    do
    {
      v24 = v23;
      v23 = _InterlockedCompareExchange((volatile signed __int32 *)v3 + 1106, v23, v23);
    }
    while ( v24 != v23 );
    if ( (v23 & 0x10) != 0 )
    {
      ndisSetDeviceInterfaceState((struct _NDIS_MINIPORT_BLOCK *)v3, 1u);
      _InterlockedAnd((volatile signed __int32 *)v3 + 1106, 0xFFFFFFEF);
    }
    ndisNotifyDevicePowerStateChange((struct _NDIS_MINIPORT_BLOCK *)v3, v13);
    ndisIssueNetEventSetPowerEvent((struct _NDIS_MINIPORT_BLOCK *)v3, v13, 1u);
  }
LABEL_56:
  if ( v22 && ndisIsMiniportStarted((struct _NDIS_MINIPORT_BLOCK *)v3) && *v11 == 1 )
  {
    v32 = *((_QWORD *)v3 + 505);
    *(_QWORD *)((char *)v38 + 4) = 0;
    LODWORD(v38[0]) = 786816;
    HIDWORD(v38[0]) = *(_DWORD *)(v32 + 1112);
    LODWORD(v38[1]) = *(_DWORD *)(v32 + 1116);
    memset(&StatusIndication, 0, sizeof(StatusIndication));
    StatusIndication.Header = (_NDIS_OBJECT_HEADER)7340440;
    StatusIndication.StatusBuffer = v38;
    StatusIndication.SourceHandle = v3;
    StatusIndication.StatusCode = 1073807395;
    StatusIndication.StatusBufferSize = 12;
    NdisMIndicateStatusEx(v3, &StatusIndication);
  }
LABEL_60:
  *((_DWORD *)v3 + 1116) = 65534;
  if ( (byte_140121003 & 4) != 0 )
    McTemplateK0jqxd_EtwWriteTransfer(
      v10,
      DevicePowerDownComplete,
      v3 + 4008,
      v3 + 4008,
      *((_DWORD *)v3 + 1014),
      *((_QWORD *)v3 + 503),
      Status);
  if ( !MINIPORT_TEST_FLAG((const struct _NDIS_MINIPORT_BLOCK *)v3, 0x80u) )
    IofCompleteRequest(v7, 0);
  if ( *(enum Ndis::ReadBindingsOptions::Flags **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v33) = 4;
    WPP_RECORDER_SF_q(
      *((_QWORD *)WPP_GLOBAL_Control + 8),
      v33,
      14,
      89,
      (struct _GUID *)&WPP_dc968d99198e32e9263b7dc94e457b33_Traceguids,
      (char)v3);
  }
  ndisDereferencePackage((struct _PKG_REF *)&ndisPkgs);
}

```

## disassembly

```asm
0x140179ea0  push    rbp
0x140179ea2  push    rbx
0x140179ea3  push    rsi
0x140179ea4  push    rdi
0x140179ea5  push    r12
0x140179ea7  push    r13
0x140179ea9  push    r14
0x140179eab  push    r15
0x140179ead  lea     rbp, [rsp-98h]
0x140179eb5  sub     rsp, 198h
0x140179ebc  mov     rax, cs:__security_cookie
0x140179ec3  xor     rax, rsp
0x140179ec6  mov     [rbp+0D0h+var_50], rax
0x140179ecd  xor     r13d, r13d
0x140179ed0  mov     [rsp+1D0h+NewIrql], 0
0x140179ed5  mov     rsi, rcx
0x140179ed8  mov     [rsp+1D0h+var_17C], r13d
0x140179edd  lea     rbx, [rcx-1530h]
0x140179ee4  xor     edx, edx; Val
0x140179ee6  lea     rcx, [rbp+0D0h+StatusIndication]; void *
0x140179eea  lea     r8d, [r13+70h]; Size
0x140179eee  call    memset
0x140179ef3  xor     eax, eax
0x140179ef5  mov     [rbp+0D0h+var_60], rax
0x140179ef9  mov     [rbp+0D0h+var_58], eax
0x140179efc  lea     r12, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140179f03  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x140179f0a  lea     rax, WPP_dc968d99198e32e9263b7dc94e457b33_Traceguids
0x140179f11  jz      short loc_140179F37
0x140179f13  mov     rcx, cs:WPP_GLOBAL_Control
0x140179f1a  lea     r9d, [r13+52h]; int
0x140179f1e  mov     qword ptr [rsp+1D0h+var_1A8], rbx; char
0x140179f23  lea     r8d, [r13+0Eh]; int
0x140179f27  mov     dl, 4; int
0x140179f29  mov     [rsp+1D0h+var_1B0], rax; struct _GUID *
0x140179f2e  mov     rcx, [rcx+40h]; int
0x140179f32  call    WPP_RECORDER_SF_q
0x140179f37  lea     rcx, ?ndisPkgs@@3PAU_PKG_REF@@A; struct _PKG_REF *
0x140179f3e  call    ?ndisReferencePackage@@YAXPEAU_PKG_REF@@@Z; ndisReferencePackage(_PKG_REF *)
0x140179f43  mov     edx, 80h; unsigned int
0x140179f48  mov     rcx, rbx; struct _NDIS_MINIPORT_BLOCK *
0x140179f4b  call    ?MINIPORT_TEST_FLAG@@YAEPEBU_NDIS_MINIPORT_BLOCK@@K@Z; MINIPORT_TEST_FLAG(_NDIS_MINIPORT_BLOCK const *,ulong)
0x140179f50  test    al, al
0x140179f52  jnz     loc_14017A364
0x140179f58  mov     rdi, [rsi+20h]
0x140179f5c  mov     rax, [rdi+0B8h]
0x140179f63  mov     r14d, [rdi+30h]
0x140179f67  mov     r15d, [rax+18h]
0x140179f6b  mov     [rsi+20h], r13
0x140179f6f  test    r14d, r14d
0x140179f72  jns     loc_14017A371
0x140179f78  call    ?ndisIsMiniportStarted@@YAEPEAU_NDIS_MINIPORT_BLOCK@@@Z; ndisIsMiniportStarted(_NDIS_MINIPORT_BLOCK *)
0x140179f7d  test    al, al
0x140179f7f  jz      loc_14017A55E
0x140179f85  lea     r13, [rbx+5F0h]
0x140179f8c  mov     esi, 1
0x140179f91  cmp     [r13+0], esi
0x140179f95  jnz     loc_14017A55E
0x140179f9b  lea     edx, [rsi+7Fh]; unsigned int
0x140179f9e  mov     rcx, rbx; struct _NDIS_MINIPORT_BLOCK *
0x140179fa1  call    ?MINIPORT_TEST_FLAG@@YAEPEBU_NDIS_MINIPORT_BLOCK@@K@Z; MINIPORT_TEST_FLAG(_NDIS_MINIPORT_BLOCK const *,ulong)
0x140179fa6  test    al, al
0x140179fa8  jz      short loc_140179FAC
0x140179faa  int     2Ch; NT_ASSERT("0")
0x140179fac  cmp     cs:WPP_RECORDER_INITIALIZED, r12; __annotation("TMF:",
0x140179fb3  lea     r15, WPP_dc968d99198e32e9263b7dc94e457b33_Traceguids
0x140179fba  jz      short loc_140179FE9
0x140179fbc  mov     rcx, cs:WPP_GLOBAL_Control
0x140179fc3  mov     r9d, 54h ; 'T'; int
0x140179fc9  mov     eax, [rdi+30h]
0x140179fcc  mov     dl, 2; int
0x140179fce  mov     dword ptr [rsp+1D0h+var_1A0], eax; char
0x140179fd2  mov     qword ptr [rsp+1D0h+var_1A8], rbx; char
0x140179fd7  mov     rcx, [rcx+40h]; int
0x140179fdb  lea     r8d, [r9-46h]; int
0x140179fdf  mov     [rsp+1D0h+var_1B0], r15; struct _GUID *
0x140179fe4  call    WPP_RECORDER_SF_qL
0x140179fe9  mov     r12d, [rbx+0F1Ch]
0x140179ff0  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140179ff7  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140179ffe  jz      short loc_14017A02B
0x14017a000  mov     rcx, cs:WPP_GLOBAL_Control
0x14017a007  mov     r9d, 55h ; 'U'; int
0x14017a00d  mov     dword ptr [rsp+1D0h+var_1A0], r12d; char
0x14017a012  mov     dl, 4; int
0x14017a014  mov     qword ptr [rsp+1D0h+var_1A8], rbx; char
0x14017a019  mov     [rsp+1D0h+var_1B0], r15; struct _GUID *
0x14017a01e  mov     rcx, [rcx+40h]; int
0x14017a022  lea     r8d, [r9-47h]; int
0x14017a026  call    WPP_RECORDER_SF_qD
0x14017a02b  mov     edx, [rbx+0F1Ch]; enum _NDIS_DEVICE_POWER_STATE
0x14017a031  mov     rcx, rbx; struct _NDIS_MINIPORT_BLOCK *
0x14017a034  call    ?NDIS_COUNT_POWER_TRANSITION@@YAXPEAU_NDIS_MINIPORT_BLOCK@@W4_NDIS_DEVICE_POWER_STATE@@@Z; NDIS_COUNT_POWER_TRANSITION(_NDIS_MINIPORT_BLOCK *,_NDIS_DEVICE_POWER_STATE)
0x14017a039  test    cs:byte_140121001, 8
0x14017a040  jz      short loc_14017A07C
0x14017a042  mov     eax, [rbx+0F1Ch]
0x14017a048  lea     r8, [rbx+0FA8h]
0x14017a04f  mov     dword ptr [rsp+1D0h+var_198], eax
0x14017a053  lea     rdx, DevicePowerStateChange
0x14017a05a  mov     rax, [rbx+0FB8h]
0x14017a061  mov     r9, r8
0x14017a064  mov     dword ptr [rsp+1D0h+var_1A0], esi
0x14017a068  mov     qword ptr [rsp+1D0h+var_1A8], rax
0x14017a06d  mov     eax, [rbx+0FD8h]
0x14017a073  mov     dword ptr [rsp+1D0h+var_1B0], eax
0x14017a077  call    McTemplateK0jqxqq_EtwWriteTransfer
0x14017a07c  mov     eax, [rbx+7Ch]
0x14017a07f  mov     rcx, rbx; struct _NDIS_MINIPORT_BLOCK *
0x14017a082  test    al, 20h
0x14017a084  jz      short loc_14017A0E1
0x14017a086  mov     r9b, sil; unsigned __int8
0x14017a089  mov     r8d, 0FD010101h; unsigned int
0x14017a08f  mov     edx, r12d; enum _DEVICE_POWER_STATE
0x14017a092  call    ?ndisQuerySetMiniportDeviceState@@YAHPEAU_NDIS_MINIPORT_BLOCK@@W4_DEVICE_POWER_STATE@@KE@Z; ndisQuerySetMiniportDeviceState(_NDIS_MINIPORT_BLOCK *,_DEVICE_POWER_STATE,ulong,uchar)
0x14017a097  mov     r15d, eax
0x14017a09a  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14017a0a1  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14017a0a8  jz      short loc_14017A0E9
0x14017a0aa  mov     rcx, cs:WPP_GLOBAL_Control
0x14017a0b1  lea     rax, WPP_dc968d99198e32e9263b7dc94e457b33_Traceguids
0x14017a0b8  mov     dword ptr [rsp+1D0h+var_198], r15d; char
0x14017a0bd  mov     r9d, 56h ; 'V'; int
0x14017a0c3  mov     dword ptr [rsp+1D0h+var_1A0], r12d; char
0x14017a0c8  mov     qword ptr [rsp+1D0h+var_1A8], rbx; char
0x14017a0cd  mov     rcx, [rcx+40h]; int
0x14017a0d1  lea     r8d, [r9-48h]; int
0x14017a0d5  mov     [rsp+1D0h+var_1B0], rax; struct _GUID *
0x14017a0da  call    WPP_RECORDER_SF_qLL
0x14017a0df  jmp     short loc_14017A0E9
0x14017a0e1  call    ?ndisPmInitializeMiniport@@_Y2PAGENPNP@@AHPEAU_NDIS_MINIPORT_BLOCK@@@Z; ndisPmInitializeMiniport(_NDIS_MINIPORT_BLOCK *)
0x14017a0e6  mov     r15d, eax
0x14017a0e9  lea     rcx, [rbx+1478h]
0x14017a0f0  call    ?Release@?$KNeutralLock@W4NDIS_MINIPORT_POLICY_OWNER@@@Rtl@@QEAAXW4NDIS_MINIPORT_POLICY_OWNER@@@Z; Rtl::KNeutralLock<NDIS_MINIPORT_POLICY_OWNER>::Release(NDIS_MINIPORT_POLICY_OWNER)
0x14017a0f5  test    r15d, r15d
0x14017a0f8  jnz     loc_14017A244
0x14017a0fe  lea     r15, [rbx+1400h]
0x14017a105  mov     rcx, r15; this
0x14017a108  call    ?BeginPolicyUpdates@BindEngine@Ndis@@QEAAXXZ; Ndis::BindEngine::BeginPolicyUpdates(void)
0x14017a10d  lea     rcx, [rbx+13B8h]; this
0x14017a114  mov     r8d, 2; enum NDIS_PAUSE_REASON
0x14017a11a  mov     edx, esi; enum PAUSE_OR_RESTART
0x14017a11c  call    ?SetPause@BindState@Ndis@@QEAA_NW4PAUSE_OR_RESTART@@W4NDIS_PAUSE_REASON@@@Z; Ndis::BindState::SetPause(PAUSE_OR_RESTART,NDIS_PAUSE_REASON)
0x14017a121  test    al, al
0x14017a123  jz      short loc_14017A197
0x14017a125  xor     edx, edx; Val
0x14017a127  lea     rcx, [rsp+1D0h+var_170]; void *
0x14017a12c  mov     r8d, 0A0h; Size
0x14017a132  call    memset
0x14017a137  cmp     cs:byte_140122AD3, 4
0x14017a13e  jb      short loc_14017A197
0x14017a140  lea     rdx, [rsp+1D0h+var_170]; struct NDIS_PNPTRACE_LOCALS *
0x14017a145  mov     rcx, rbx; struct _NDIS_MINIPORT_BLOCK *
0x14017a148  call    ?ndisGetBindLinkNameForTracing@@YAXPEAU_NDIS_MINIPORT_BLOCK@@PEAUNDIS_PNPTRACE_LOCALS@@@Z; ndisGetBindLinkNameForTracing(_NDIS_MINIPORT_BLOCK *,NDIS_PNPTRACE_LOCALS *)
0x14017a14d  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14017a154  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14017a15b  jz      short loc_14017A197
0x14017a15d  mov     rax, qword ptr [rsp+1D0h+var_170]
0x14017a162  mov     r9d, 57h ; 'W'; int
0x14017a168  mov     rcx, cs:WPP_GLOBAL_Control
0x14017a16f  mov     qword ptr [rsp+1D0h+var_1A0], rax; char
0x14017a174  mov     rax, [rsp+1D0h+var_168]
0x14017a179  mov     qword ptr [rsp+1D0h+var_1A8], rax; __int64
0x14017a17e  lea     r8d, [r9-3Bh]; int
0x14017a182  mov     rcx, [rcx+40h]; int
0x14017a186  lea     rax, WPP_dc968d99198e32e9263b7dc94e457b33_Traceguids
0x14017a18d  mov     [rsp+1D0h+var_1B0], rax; struct _GUID *
0x14017a192  call    WPP_RECORDER_SF_Zq
0x14017a197  mov     rcx, r15; this
0x14017a19a  call    ?EndPolicyUpdates@BindEngine@Ndis@@QEAAXXZ; Ndis::BindEngine::EndPolicyUpdates(void)
0x14017a19f  xor     r8d, r8d; bool
0x14017a1a2  xor     edx, edx; enum CallRunMode
0x14017a1a4  mov     rcx, r15; this
0x14017a1a7  call    ?ApplyBindChanges@BindEngine@Ndis@@QEAAXW4CallRunMode@@_N@Z; Ndis::BindEngine::ApplyBindChanges(CallRunMode,bool)
0x14017a1ac  lea     rdx, [rsp+1D0h+NewIrql]; unsigned __int8 *
0x14017a1b1  mov     rcx, rbx; struct _NDIS_MINIPORT_BLOCK *
0x14017a1b4  call    ?NDIS_ACQUIRE_MINIPORT_SPIN_LOCK@@YAXPEAU_NDIS_MINIPORT_BLOCK@@PEAE@Z; NDIS_ACQUIRE_MINIPORT_SPIN_LOCK(_NDIS_MINIPORT_BLOCK *,uchar *)
0x14017a1b9  mov     dl, 4; unsigned __int8
0x14017a1bb  mov     rcx, rbx; struct _NDIS_MINIPORT_BLOCK *
0x14017a1be  call    ?ndisMRestoreOpenHandlers@@YAXPEAU_NDIS_MINIPORT_BLOCK@@E@Z; ndisMRestoreOpenHandlers(_NDIS_MINIPORT_BLOCK *,uchar)
0x14017a1c3  mov     r8b, [rsp+1D0h+NewIrql]; unsigned __int8
0x14017a1c8  mov     dl, sil; unsigned __int8
0x14017a1cb  mov     rcx, rbx; struct _NDIS_MINIPORT_BLOCK *
0x14017a1ce  call    ?ndisIfSetInterfaceState@@YAEPEAU_NDIS_MINIPORT_BLOCK@@EE@Z; ndisIfSetInterfaceState(_NDIS_MINIPORT_BLOCK *,uchar,uchar)
0x14017a1d3  mov     dl, [rsp+1D0h+NewIrql]; NewIrql
0x14017a1d7  lea     rcx, [rbx+60h]; SpinLock
0x14017a1db  movzx   r15d, al
0x14017a1df  mov     qword ptr [rbx+208h], 0
0x14017a1ea  call    cs:__imp_KeReleaseSpinLock
0x14017a1f1  nop     dword ptr [rax+rax+00h]
0x14017a1f6  prefetchw byte ptr [rbx+1148h]
0x14017a1fd  mov     eax, [rbx+1148h]
0x14017a203  mov     ecx, eax
0x14017a205  lock cmpxchg [rbx+1148h], ecx
0x14017a20d  jnz     short loc_14017A203
0x14017a20f  test    al, 10h
0x14017a211  jz      short loc_14017A226
0x14017a213  mov     dl, sil; unsigned __int8
0x14017a216  mov     rcx, rbx; struct _NDIS_MINIPORT_BLOCK *
0x14017a219  call    ?ndisSetDeviceInterfaceState@@YAXPEAU_NDIS_MINIPORT_BLOCK@@E@Z; ndisSetDeviceInterfaceState(_NDIS_MINIPORT_BLOCK *,uchar)
0x14017a21e  lock and dword ptr [rbx+1148h], 0FFFFFFEFh
0x14017a226  mov     edx, r12d; enum _NDIS_DEVICE_POWER_STATE
0x14017a229  mov     rcx, rbx; struct _NDIS_MINIPORT_BLOCK *
0x14017a22c  call    ?ndisNotifyDevicePowerStateChange@@YAXPEAU_NDIS_MINIPORT_BLOCK@@W4_NDIS_DEVICE_POWER_STATE@@@Z; ndisNotifyDevicePowerStateChange(_NDIS_MINIPORT_BLOCK *,_NDIS_DEVICE_POWER_STATE)
0x14017a231  mov     r8b, sil; unsigned __int8
0x14017a234  mov     edx, r12d; enum _DEVICE_POWER_STATE
0x14017a237  mov     rcx, rbx; struct _NDIS_MINIPORT_BLOCK *
0x14017a23a  call    ?ndisIssueNetEventSetPowerEvent@@YAXPEAU_NDIS_MINIPORT_BLOCK@@W4_DEVICE_POWER_STATE@@E@Z; ndisIssueNetEventSetPowerEvent(_NDIS_MINIPORT_BLOCK *,_DEVICE_POWER_STATE,uchar)
0x14017a23f  jmp     loc_14017A4D9
0x14017a244  lea     r12, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14017a24b  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x14017a252  jz      short loc_14017A281
0x14017a254  mov     rcx, cs:WPP_GLOBAL_Control
0x14017a25b  lea     rax, WPP_dc968d99198e32e9263b7dc94e457b33_Traceguids
0x14017a262  mov     r9d, 58h ; 'X'; int
0x14017a268  mov     qword ptr [rsp+1D0h+var_1A8], rbx; char
0x14017a26d  mov     dl, 4; int
0x14017a26f  mov     [rsp+1D0h+var_1B0], rax; struct _GUID *
0x14017a274  mov     rcx, [rcx+40h]; int
0x14017a278  lea     r8d, [r9-4Ah]; int
0x14017a27c  call    WPP_RECORDER_SF_q
0x14017a281  test    cs:byte_140121002, 40h
0x14017a288  jz      short loc_14017A2CB
0x14017a28a  mov     rax, [rbx+0FB8h]
0x14017a291  lea     r8, [rbx+0FA8h]
0x14017a298  mov     [rsp+1D0h+var_190], 0
0x14017a2a0  lea     rdx, PowerDownFailedCannotReinitialize
0x14017a2a7  mov     dword ptr [rsp+1D0h+var_198], 10001h
0x14017a2af  mov     r9, r8
0x14017a2b2  mov     dword ptr [rsp+1D0h+var_1A0], r15d
0x14017a2b7  mov     qword ptr [rsp+1D0h+var_1A8], rax
0x14017a2bc  mov     eax, [rbx+0FD8h]
0x14017a2c2  mov     dword ptr [rsp+1D0h+var_1B0], eax
0x14017a2c6  call    McTemplateK0jqxddq_EtwWriteTransfer
0x14017a2cb  mov     dl, 0Fh; enum _NDIS_MPIF_REFTAG
0x14017a2cd  mov     rcx, rbx; struct _NDIS_MINIPORT_BLOCK *
0x14017a2d0  call    ?ndisMReferenceIfBlock@@YAPEAU_NDIS_IF_BLOCK@@PEAU_NDIS_MINIPORT_BLOCK@@W4_NDIS_MPIF_REFTAG@@@Z; ndisMReferenceIfBlock(_NDIS_MINIPORT_BLOCK *,_NDIS_MPIF_REFTAG)
0x14017a2d5  test    rax, rax
0x14017a2d8  jz      short loc_14017A32A
0x14017a2da  mov     rax, [rbx+0FC8h]
0x14017a2e1  mov     ecx, 2
0x14017a2e6  mov     [rbx+0FE0h], rcx
0x14017a2ed  cmp     [rax+458h], ecx
0x14017a2f3  jz      short loc_14017A319
0x14017a2f5  mov     [rax+458h], ecx
0x14017a2fb  mov     rcx, rbx; struct _NDIS_MINIPORT_BLOCK *
0x14017a2fe  mov     rax, [rbx+0FC8h]
0x14017a305  mov     dword ptr [rax+45Ch], 0
0x14017a30f  call    ?ndisNsiSyncMiniportOperStatusNotification@@YAXPEAU_NDIS_MINIPORT_BLOCK@@@Z; ndisNsiSyncMiniportOperStatusNotification(_NDIS_MINIPORT_BLOCK *)
0x14017a314  mov     r15d, esi
0x14017a317  jmp     short loc_14017A31E
0x14017a319  mov     r15d, [rsp+1D0h+var_17C]
0x14017a31e  mov     dl, 0Fh; enum _NDIS_MPIF_REFTAG
0x14017a320  mov     rcx, rbx; struct _NDIS_MINIPORT_BLOCK *
0x14017a323  call    ?ndisMDereferenceIfBlock@@YAXPEAU_NDIS_MINIPORT_BLOCK@@W4_NDIS_MPIF_REFTAG@@@Z; ndisMDereferenceIfBlock(_NDIS_MINIPORT_BLOCK *,_NDIS_MPIF_REFTAG)
0x14017a328  jmp     short loc_14017A32F
0x14017a32a  mov     r15d, [rsp+1D0h+var_17C]
0x14017a32f  mov     edx, 4Bh ; 'K'; enum _NDIS_MINIPORT_EVENT
0x14017a334  mov     rcx, rbx; struct _NDIS_MINIPORT_BLOCK *
0x14017a337  call    ?ndisMiniportFatalError@@YAXPEAU_NDIS_MINIPORT_BLOCK@@W4_NDIS_MINIPORT_EVENT@@@Z; ndisMiniportFatalError(_NDIS_MINIPORT_BLOCK *,_NDIS_MINIPORT_EVENT)
0x14017a33c  mov     edx, 80h; unsigned int
0x14017a341  mov     rcx, rbx; struct _NDIS_MINIPORT_BLOCK *
0x14017a344  call    ?MINIPORT_TEST_FLAG@@YAEPEBU_NDIS_MINIPORT_BLOCK@@K@Z; MINIPORT_TEST_FLAG(_NDIS_MINIPORT_BLOCK const *,ulong)
0x14017a349  test    al, al
0x14017a34b  jnz     short loc_14017A359
0x14017a34d  mov     dword ptr [rdi+30h], 0C0000001h
0x14017a354  jmp     loc_14017A4E0
0x14017a359  mov     r14d, 0C0000001h
0x14017a35f  jmp     loc_14017A4E0
0x14017a364  xor     edi, edi
0x14017a366  xor     r14d, r14d
0x14017a369  mov     [rsi+20h], rdi
0x14017a36d  lea     r15d, [rdi+4]
0x14017a371  cmp     cs:WPP_RECORDER_INITIALIZED, r12; __annotation("TMF:",
0x14017a378  jz      short loc_14017A3AC
0x14017a37a  mov     rcx, cs:WPP_GLOBAL_Control
0x14017a381  lea     rax, WPP_dc968d99198e32e9263b7dc94e457b33_Traceguids
0x14017a388  mov     r9d, 53h ; 'S'; int
0x14017a38e  mov     dword ptr [rsp+1D0h+var_1A0], r15d; char
0x14017a393  mov     qword ptr [rsp+1D0h+var_1A8], rbx; char
0x14017a398  mov     dl, 4; int
0x14017a39a  mov     [rsp+1D0h+var_1B0], rax; struct _GUID *
0x14017a39f  mov     rcx, [rcx+40h]; int
0x14017a3a3  lea     r8d, [r9-45h]; int
0x14017a3a7  call    WPP_RECORDER_SF_qD
0x14017a3ac  mov     edx, r15d; enum _NDIS_DEVICE_POWER_STATE
0x14017a3af  mov     rcx, rbx; struct _NDIS_MINIPORT_BLOCK *
0x14017a3b2  call    ?NDIS_COUNT_POWER_TRANSITION@@YAXPEAU_NDIS_MINIPORT_BLOCK@@W4_NDIS_DEVICE_POWER_STATE@@@Z; NDIS_COUNT_POWER_TRANSITION(_NDIS_MINIPORT_BLOCK *,_NDIS_DEVICE_POWER_STATE)
0x14017a3b7  test    cs:byte_140121001, 8
0x14017a3be  mov     esi, 1
0x14017a3c3  jz      short loc_14017A3FA
0x14017a3c5  mov     rax, [rbx+0FB8h]
0x14017a3cc  lea     r8, [rbx+0FA8h]
0x14017a3d3  mov     dword ptr [rsp+1D0h+var_198], r15d
0x14017a3d8  lea     rdx, DevicePowerStateChange
0x14017a3df  mov     dword ptr [rsp+1D0h+var_1A0], esi
0x14017a3e3  mov     r9, r8
0x14017a3e6  mov     qword ptr [rsp+1D0h+var_1A8], rax
0x14017a3eb  mov     eax, [rbx+0FD8h]
0x14017a3f1  mov     dword ptr [rsp+1D0h+var_1B0], eax
0x14017a3f5  call    McTemplateK0jqxqq_EtwWriteTransfer
  ... truncated ...
```
