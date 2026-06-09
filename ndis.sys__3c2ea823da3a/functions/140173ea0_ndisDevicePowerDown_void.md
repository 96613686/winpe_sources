# ndisDevicePowerDown(void *)

- ea: `0x140173ea0`
- end: `0x14017462a`
- name: `?ndisDevicePowerDown@@YAXPEAX@Z`
- size: `1930`
- prototype: `void __fastcall(void *)`
- caller_count: `0`
- callee_count: `35`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callees

- `0x140012a70`
- `0x140015280`
- `0x140015530`
- `0x140016a10`
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
- `0x14004e050`
- `0x140050410`
- `0x1400568a0`
- `0x14005edf0`
- `0x140068220`
- `0x14007b4e0`
- `0x1400837ac`
- `0x1400e6160`
- `0x1400e65c0`
- `0x140136f20`
- `0x14014c244`
- `0x140154f70`
- `0x140156b40`
- `0x140156f20`
- `0x140157750`
- `0x140157dc0`
- `0x140163170`
- `0x140164280`
- `0x1401669d0`
- `0x140173ea0`
- `0x1401747a8`

## import_xrefs

- `ntoskrnl!PoSetPowerState` at `0x1401744c1`
- `ntoskrnl!PoSetPowerState` at `0x1401744c1`
- `ntoskrnl!IofCompleteRequest` at `0x1401745b8`
- `ntoskrnl!IofCompleteRequest` at `0x1401745b8`
- `ntoskrnl!KeReleaseSpinLock` at `0x1401741ea`
- `ntoskrnl!KeReleaseSpinLock` at `0x140174484`
- `ntoskrnl!KeReleaseSpinLock` at `0x1401741ea`
- `ntoskrnl!KeReleaseSpinLock` at `0x140174484`

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
    if ( (byte_14011B001 & 8) != 0 )
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
  if ( (byte_14011B001 & 8) != 0 )
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
    if ( (byte_14011B002 & 0x40) != 0 )
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
      if ( (unsigned __int8)byte_14011CAD3 >= 4u )
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
  if ( (byte_14011B003 & 4) != 0 )
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
0x140173ea0  push    rbp
0x140173ea2  push    rbx
0x140173ea3  push    rsi
0x140173ea4  push    rdi
0x140173ea5  push    r12
0x140173ea7  push    r13
0x140173ea9  push    r14
0x140173eab  push    r15
0x140173ead  lea     rbp, [rsp-98h]
0x140173eb5  sub     rsp, 198h
0x140173ebc  mov     rax, cs:__security_cookie
0x140173ec3  xor     rax, rsp
0x140173ec6  mov     [rbp+0D0h+var_50], rax
0x140173ecd  xor     r13d, r13d
0x140173ed0  mov     [rsp+1D0h+NewIrql], 0
0x140173ed5  mov     rsi, rcx
0x140173ed8  mov     [rsp+1D0h+var_17C], r13d
0x140173edd  lea     rbx, [rcx-1530h]
0x140173ee4  xor     edx, edx; Val
0x140173ee6  lea     rcx, [rbp+0D0h+StatusIndication]; void *
0x140173eea  lea     r8d, [r13+70h]; Size
0x140173eee  call    memset
0x140173ef3  xor     eax, eax
0x140173ef5  mov     [rbp+0D0h+var_60], rax
0x140173ef9  mov     [rbp+0D0h+var_58], eax
0x140173efc  lea     r12, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140173f03  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x140173f0a  lea     rax, WPP_dc968d99198e32e9263b7dc94e457b33_Traceguids
0x140173f11  jz      short loc_140173F37
0x140173f13  mov     rcx, cs:WPP_GLOBAL_Control
0x140173f1a  lea     r9d, [r13+52h]; int
0x140173f1e  mov     qword ptr [rsp+1D0h+var_1A8], rbx; char
0x140173f23  lea     r8d, [r13+0Eh]; int
0x140173f27  mov     dl, 4; int
0x140173f29  mov     [rsp+1D0h+var_1B0], rax; struct _GUID *
0x140173f2e  mov     rcx, [rcx+40h]; int
0x140173f32  call    WPP_RECORDER_SF_q
0x140173f37  lea     rcx, ?ndisPkgs@@3PAU_PKG_REF@@A; struct _PKG_REF *
0x140173f3e  call    ?ndisReferencePackage@@YAXPEAU_PKG_REF@@@Z; ndisReferencePackage(_PKG_REF *)
0x140173f43  mov     edx, 80h; unsigned int
0x140173f48  mov     rcx, rbx; struct _NDIS_MINIPORT_BLOCK *
0x140173f4b  call    ?MINIPORT_TEST_FLAG@@YAEPEBU_NDIS_MINIPORT_BLOCK@@K@Z; MINIPORT_TEST_FLAG(_NDIS_MINIPORT_BLOCK const *,ulong)
0x140173f50  test    al, al
0x140173f52  jnz     loc_140174364
0x140173f58  mov     rdi, [rsi+20h]
0x140173f5c  mov     rax, [rdi+0B8h]
0x140173f63  mov     r14d, [rdi+30h]
0x140173f67  mov     r15d, [rax+18h]
0x140173f6b  mov     [rsi+20h], r13
0x140173f6f  test    r14d, r14d
0x140173f72  jns     loc_140174371
0x140173f78  call    ?ndisIsMiniportStarted@@YAEPEAU_NDIS_MINIPORT_BLOCK@@@Z; ndisIsMiniportStarted(_NDIS_MINIPORT_BLOCK *)
0x140173f7d  test    al, al
0x140173f7f  jz      loc_14017455E
0x140173f85  lea     r13, [rbx+5F0h]
0x140173f8c  mov     esi, 1
0x140173f91  cmp     [r13+0], esi
0x140173f95  jnz     loc_14017455E
0x140173f9b  lea     edx, [rsi+7Fh]; unsigned int
0x140173f9e  mov     rcx, rbx; struct _NDIS_MINIPORT_BLOCK *
0x140173fa1  call    ?MINIPORT_TEST_FLAG@@YAEPEBU_NDIS_MINIPORT_BLOCK@@K@Z; MINIPORT_TEST_FLAG(_NDIS_MINIPORT_BLOCK const *,ulong)
0x140173fa6  test    al, al
0x140173fa8  jz      short loc_140173FAC
0x140173faa  int     2Ch; NT_ASSERT("0")
0x140173fac  cmp     cs:WPP_RECORDER_INITIALIZED, r12; __annotation("TMF:",
0x140173fb3  lea     r15, WPP_dc968d99198e32e9263b7dc94e457b33_Traceguids
0x140173fba  jz      short loc_140173FE9
0x140173fbc  mov     rcx, cs:WPP_GLOBAL_Control
0x140173fc3  mov     r9d, 54h ; 'T'; int
0x140173fc9  mov     eax, [rdi+30h]
0x140173fcc  mov     dl, 2; int
0x140173fce  mov     dword ptr [rsp+1D0h+var_1A0], eax; char
0x140173fd2  mov     qword ptr [rsp+1D0h+var_1A8], rbx; char
0x140173fd7  mov     rcx, [rcx+40h]; int
0x140173fdb  lea     r8d, [r9-46h]; int
0x140173fdf  mov     [rsp+1D0h+var_1B0], r15; struct _GUID *
0x140173fe4  call    WPP_RECORDER_SF_qL
0x140173fe9  mov     r12d, [rbx+0F1Ch]
0x140173ff0  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140173ff7  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140173ffe  jz      short loc_14017402B
0x140174000  mov     rcx, cs:WPP_GLOBAL_Control
0x140174007  mov     r9d, 55h ; 'U'; int
0x14017400d  mov     dword ptr [rsp+1D0h+var_1A0], r12d; char
0x140174012  mov     dl, 4; int
0x140174014  mov     qword ptr [rsp+1D0h+var_1A8], rbx; char
0x140174019  mov     [rsp+1D0h+var_1B0], r15; struct _GUID *
0x14017401e  mov     rcx, [rcx+40h]; int
0x140174022  lea     r8d, [r9-47h]; int
0x140174026  call    WPP_RECORDER_SF_qD
0x14017402b  mov     edx, [rbx+0F1Ch]; enum _NDIS_DEVICE_POWER_STATE
0x140174031  mov     rcx, rbx; struct _NDIS_MINIPORT_BLOCK *
0x140174034  call    ?NDIS_COUNT_POWER_TRANSITION@@YAXPEAU_NDIS_MINIPORT_BLOCK@@W4_NDIS_DEVICE_POWER_STATE@@@Z; NDIS_COUNT_POWER_TRANSITION(_NDIS_MINIPORT_BLOCK *,_NDIS_DEVICE_POWER_STATE)
0x140174039  test    cs:byte_14011B001, 8
0x140174040  jz      short loc_14017407C
0x140174042  mov     eax, [rbx+0F1Ch]
0x140174048  lea     r8, [rbx+0FA8h]
0x14017404f  mov     dword ptr [rsp+1D0h+var_198], eax
0x140174053  lea     rdx, DevicePowerStateChange
0x14017405a  mov     rax, [rbx+0FB8h]
0x140174061  mov     r9, r8
0x140174064  mov     dword ptr [rsp+1D0h+var_1A0], esi
0x140174068  mov     qword ptr [rsp+1D0h+var_1A8], rax
0x14017406d  mov     eax, [rbx+0FD8h]
0x140174073  mov     dword ptr [rsp+1D0h+var_1B0], eax
0x140174077  call    McTemplateK0jqxqq_EtwWriteTransfer
0x14017407c  mov     eax, [rbx+7Ch]
0x14017407f  mov     rcx, rbx; struct _NDIS_MINIPORT_BLOCK *
0x140174082  test    al, 20h
0x140174084  jz      short loc_1401740E1
0x140174086  mov     r9b, sil; unsigned __int8
0x140174089  mov     r8d, 0FD010101h; unsigned int
0x14017408f  mov     edx, r12d; enum _DEVICE_POWER_STATE
0x140174092  call    ?ndisQuerySetMiniportDeviceState@@YAHPEAU_NDIS_MINIPORT_BLOCK@@W4_DEVICE_POWER_STATE@@KE@Z; ndisQuerySetMiniportDeviceState(_NDIS_MINIPORT_BLOCK *,_DEVICE_POWER_STATE,ulong,uchar)
0x140174097  mov     r15d, eax
0x14017409a  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x1401740a1  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1401740a8  jz      short loc_1401740E9
0x1401740aa  mov     rcx, cs:WPP_GLOBAL_Control
0x1401740b1  lea     rax, WPP_dc968d99198e32e9263b7dc94e457b33_Traceguids
0x1401740b8  mov     dword ptr [rsp+1D0h+var_198], r15d; char
0x1401740bd  mov     r9d, 56h ; 'V'; int
0x1401740c3  mov     dword ptr [rsp+1D0h+var_1A0], r12d; char
0x1401740c8  mov     qword ptr [rsp+1D0h+var_1A8], rbx; char
0x1401740cd  mov     rcx, [rcx+40h]; int
0x1401740d1  lea     r8d, [r9-48h]; int
0x1401740d5  mov     [rsp+1D0h+var_1B0], rax; struct _GUID *
0x1401740da  call    WPP_RECORDER_SF_qLL
0x1401740df  jmp     short loc_1401740E9
0x1401740e1  call    ?ndisPmInitializeMiniport@@_Y2PAGENPNP@@AHPEAU_NDIS_MINIPORT_BLOCK@@@Z; ndisPmInitializeMiniport(_NDIS_MINIPORT_BLOCK *)
0x1401740e6  mov     r15d, eax
0x1401740e9  lea     rcx, [rbx+1478h]
0x1401740f0  call    ?Release@?$KNeutralLock@W4NDIS_MINIPORT_POLICY_OWNER@@@Rtl@@QEAAXW4NDIS_MINIPORT_POLICY_OWNER@@@Z; Rtl::KNeutralLock<NDIS_MINIPORT_POLICY_OWNER>::Release(NDIS_MINIPORT_POLICY_OWNER)
0x1401740f5  test    r15d, r15d
0x1401740f8  jnz     loc_140174244
0x1401740fe  lea     r15, [rbx+1400h]
0x140174105  mov     rcx, r15; this
0x140174108  call    ?BeginPolicyUpdates@BindEngine@Ndis@@QEAAXXZ; Ndis::BindEngine::BeginPolicyUpdates(void)
0x14017410d  lea     rcx, [rbx+13B8h]; this
0x140174114  mov     r8d, 2; enum NDIS_PAUSE_REASON
0x14017411a  mov     edx, esi; enum PAUSE_OR_RESTART
0x14017411c  call    ?SetPause@BindState@Ndis@@QEAA_NW4PAUSE_OR_RESTART@@W4NDIS_PAUSE_REASON@@@Z; Ndis::BindState::SetPause(PAUSE_OR_RESTART,NDIS_PAUSE_REASON)
0x140174121  test    al, al
0x140174123  jz      short loc_140174197
0x140174125  xor     edx, edx; Val
0x140174127  lea     rcx, [rsp+1D0h+var_170]; void *
0x14017412c  mov     r8d, 0A0h; Size
0x140174132  call    memset
0x140174137  cmp     cs:byte_14011CAD3, 4
0x14017413e  jb      short loc_140174197
0x140174140  lea     rdx, [rsp+1D0h+var_170]; struct NDIS_PNPTRACE_LOCALS *
0x140174145  mov     rcx, rbx; struct _NDIS_MINIPORT_BLOCK *
0x140174148  call    ?ndisGetBindLinkNameForTracing@@YAXPEAU_NDIS_MINIPORT_BLOCK@@PEAUNDIS_PNPTRACE_LOCALS@@@Z; ndisGetBindLinkNameForTracing(_NDIS_MINIPORT_BLOCK *,NDIS_PNPTRACE_LOCALS *)
0x14017414d  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140174154  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14017415b  jz      short loc_140174197
0x14017415d  mov     rax, qword ptr [rsp+1D0h+var_170]
0x140174162  mov     r9d, 57h ; 'W'; int
0x140174168  mov     rcx, cs:WPP_GLOBAL_Control
0x14017416f  mov     qword ptr [rsp+1D0h+var_1A0], rax; char
0x140174174  mov     rax, [rsp+1D0h+var_168]
0x140174179  mov     qword ptr [rsp+1D0h+var_1A8], rax; __int64
0x14017417e  lea     r8d, [r9-3Bh]; int
0x140174182  mov     rcx, [rcx+40h]; int
0x140174186  lea     rax, WPP_dc968d99198e32e9263b7dc94e457b33_Traceguids
0x14017418d  mov     [rsp+1D0h+var_1B0], rax; struct _GUID *
0x140174192  call    WPP_RECORDER_SF_Zq
0x140174197  mov     rcx, r15; this
0x14017419a  call    ?EndPolicyUpdates@BindEngine@Ndis@@QEAAXXZ; Ndis::BindEngine::EndPolicyUpdates(void)
0x14017419f  xor     r8d, r8d; bool
0x1401741a2  xor     edx, edx; enum CallRunMode
0x1401741a4  mov     rcx, r15; this
0x1401741a7  call    ?ApplyBindChanges@BindEngine@Ndis@@QEAAXW4CallRunMode@@_N@Z; Ndis::BindEngine::ApplyBindChanges(CallRunMode,bool)
0x1401741ac  lea     rdx, [rsp+1D0h+NewIrql]; unsigned __int8 *
0x1401741b1  mov     rcx, rbx; struct _NDIS_MINIPORT_BLOCK *
0x1401741b4  call    ?NDIS_ACQUIRE_MINIPORT_SPIN_LOCK@@YAXPEAU_NDIS_MINIPORT_BLOCK@@PEAE@Z; NDIS_ACQUIRE_MINIPORT_SPIN_LOCK(_NDIS_MINIPORT_BLOCK *,uchar *)
0x1401741b9  mov     dl, 4; unsigned __int8
0x1401741bb  mov     rcx, rbx; struct _NDIS_MINIPORT_BLOCK *
0x1401741be  call    ?ndisMRestoreOpenHandlers@@YAXPEAU_NDIS_MINIPORT_BLOCK@@E@Z; ndisMRestoreOpenHandlers(_NDIS_MINIPORT_BLOCK *,uchar)
0x1401741c3  mov     r8b, [rsp+1D0h+NewIrql]; unsigned __int8
0x1401741c8  mov     dl, sil; unsigned __int8
0x1401741cb  mov     rcx, rbx; struct _NDIS_MINIPORT_BLOCK *
0x1401741ce  call    ?ndisIfSetInterfaceState@@YAEPEAU_NDIS_MINIPORT_BLOCK@@EE@Z; ndisIfSetInterfaceState(_NDIS_MINIPORT_BLOCK *,uchar,uchar)
0x1401741d3  mov     dl, [rsp+1D0h+NewIrql]; NewIrql
0x1401741d7  lea     rcx, [rbx+60h]; SpinLock
0x1401741db  movzx   r15d, al
0x1401741df  mov     qword ptr [rbx+208h], 0
0x1401741ea  call    cs:__imp_KeReleaseSpinLock
0x1401741f1  nop     dword ptr [rax+rax+00h]
0x1401741f6  prefetchw byte ptr [rbx+1148h]
0x1401741fd  mov     eax, [rbx+1148h]
0x140174203  mov     ecx, eax
0x140174205  lock cmpxchg [rbx+1148h], ecx
0x14017420d  jnz     short loc_140174203
0x14017420f  test    al, 10h
0x140174211  jz      short loc_140174226
0x140174213  mov     dl, sil; unsigned __int8
0x140174216  mov     rcx, rbx; struct _NDIS_MINIPORT_BLOCK *
0x140174219  call    ?ndisSetDeviceInterfaceState@@YAXPEAU_NDIS_MINIPORT_BLOCK@@E@Z; ndisSetDeviceInterfaceState(_NDIS_MINIPORT_BLOCK *,uchar)
0x14017421e  lock and dword ptr [rbx+1148h], 0FFFFFFEFh
0x140174226  mov     edx, r12d; enum _NDIS_DEVICE_POWER_STATE
0x140174229  mov     rcx, rbx; struct _NDIS_MINIPORT_BLOCK *
0x14017422c  call    ?ndisNotifyDevicePowerStateChange@@YAXPEAU_NDIS_MINIPORT_BLOCK@@W4_NDIS_DEVICE_POWER_STATE@@@Z; ndisNotifyDevicePowerStateChange(_NDIS_MINIPORT_BLOCK *,_NDIS_DEVICE_POWER_STATE)
0x140174231  mov     r8b, sil; unsigned __int8
0x140174234  mov     edx, r12d; enum _DEVICE_POWER_STATE
0x140174237  mov     rcx, rbx; struct _NDIS_MINIPORT_BLOCK *
0x14017423a  call    ?ndisIssueNetEventSetPowerEvent@@YAXPEAU_NDIS_MINIPORT_BLOCK@@W4_DEVICE_POWER_STATE@@E@Z; ndisIssueNetEventSetPowerEvent(_NDIS_MINIPORT_BLOCK *,_DEVICE_POWER_STATE,uchar)
0x14017423f  jmp     loc_1401744D9
0x140174244  lea     r12, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14017424b  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x140174252  jz      short loc_140174281
0x140174254  mov     rcx, cs:WPP_GLOBAL_Control
0x14017425b  lea     rax, WPP_dc968d99198e32e9263b7dc94e457b33_Traceguids
0x140174262  mov     r9d, 58h ; 'X'; int
0x140174268  mov     qword ptr [rsp+1D0h+var_1A8], rbx; char
0x14017426d  mov     dl, 4; int
0x14017426f  mov     [rsp+1D0h+var_1B0], rax; struct _GUID *
0x140174274  mov     rcx, [rcx+40h]; int
0x140174278  lea     r8d, [r9-4Ah]; int
0x14017427c  call    WPP_RECORDER_SF_q
0x140174281  test    cs:byte_14011B002, 40h
0x140174288  jz      short loc_1401742CB
0x14017428a  mov     rax, [rbx+0FB8h]
0x140174291  lea     r8, [rbx+0FA8h]
0x140174298  mov     [rsp+1D0h+var_190], 0
0x1401742a0  lea     rdx, PowerDownFailedCannotReinitialize
0x1401742a7  mov     dword ptr [rsp+1D0h+var_198], 10001h
0x1401742af  mov     r9, r8
0x1401742b2  mov     dword ptr [rsp+1D0h+var_1A0], r15d
0x1401742b7  mov     qword ptr [rsp+1D0h+var_1A8], rax
0x1401742bc  mov     eax, [rbx+0FD8h]
0x1401742c2  mov     dword ptr [rsp+1D0h+var_1B0], eax
0x1401742c6  call    McTemplateK0jqxddq_EtwWriteTransfer
0x1401742cb  mov     dl, 0Fh; enum _NDIS_MPIF_REFTAG
0x1401742cd  mov     rcx, rbx; struct _NDIS_MINIPORT_BLOCK *
0x1401742d0  call    ?ndisMReferenceIfBlock@@YAPEAU_NDIS_IF_BLOCK@@PEAU_NDIS_MINIPORT_BLOCK@@W4_NDIS_MPIF_REFTAG@@@Z; ndisMReferenceIfBlock(_NDIS_MINIPORT_BLOCK *,_NDIS_MPIF_REFTAG)
0x1401742d5  test    rax, rax
0x1401742d8  jz      short loc_14017432A
0x1401742da  mov     rax, [rbx+0FC8h]
0x1401742e1  mov     ecx, 2
0x1401742e6  mov     [rbx+0FE0h], rcx
0x1401742ed  cmp     [rax+458h], ecx
0x1401742f3  jz      short loc_140174319
0x1401742f5  mov     [rax+458h], ecx
0x1401742fb  mov     rcx, rbx; struct _NDIS_MINIPORT_BLOCK *
0x1401742fe  mov     rax, [rbx+0FC8h]
0x140174305  mov     dword ptr [rax+45Ch], 0
0x14017430f  call    ?ndisNsiSyncMiniportOperStatusNotification@@YAXPEAU_NDIS_MINIPORT_BLOCK@@@Z; ndisNsiSyncMiniportOperStatusNotification(_NDIS_MINIPORT_BLOCK *)
0x140174314  mov     r15d, esi
0x140174317  jmp     short loc_14017431E
0x140174319  mov     r15d, [rsp+1D0h+var_17C]
0x14017431e  mov     dl, 0Fh; enum _NDIS_MPIF_REFTAG
0x140174320  mov     rcx, rbx; struct _NDIS_MINIPORT_BLOCK *
0x140174323  call    ?ndisMDereferenceIfBlock@@YAXPEAU_NDIS_MINIPORT_BLOCK@@W4_NDIS_MPIF_REFTAG@@@Z; ndisMDereferenceIfBlock(_NDIS_MINIPORT_BLOCK *,_NDIS_MPIF_REFTAG)
0x140174328  jmp     short loc_14017432F
0x14017432a  mov     r15d, [rsp+1D0h+var_17C]
0x14017432f  mov     edx, 4Bh ; 'K'; enum _NDIS_MINIPORT_EVENT
0x140174334  mov     rcx, rbx; struct _NDIS_MINIPORT_BLOCK *
0x140174337  call    ?ndisMiniportFatalError@@YAXPEAU_NDIS_MINIPORT_BLOCK@@W4_NDIS_MINIPORT_EVENT@@@Z; ndisMiniportFatalError(_NDIS_MINIPORT_BLOCK *,_NDIS_MINIPORT_EVENT)
0x14017433c  mov     edx, 80h; unsigned int
0x140174341  mov     rcx, rbx; struct _NDIS_MINIPORT_BLOCK *
0x140174344  call    ?MINIPORT_TEST_FLAG@@YAEPEBU_NDIS_MINIPORT_BLOCK@@K@Z; MINIPORT_TEST_FLAG(_NDIS_MINIPORT_BLOCK const *,ulong)
0x140174349  test    al, al
0x14017434b  jnz     short loc_140174359
0x14017434d  mov     dword ptr [rdi+30h], 0C0000001h
0x140174354  jmp     loc_1401744E0
0x140174359  mov     r14d, 0C0000001h
0x14017435f  jmp     loc_1401744E0
0x140174364  xor     edi, edi
0x140174366  xor     r14d, r14d
0x140174369  mov     [rsi+20h], rdi
0x14017436d  lea     r15d, [rdi+4]
0x140174371  cmp     cs:WPP_RECORDER_INITIALIZED, r12; __annotation("TMF:",
0x140174378  jz      short loc_1401743AC
0x14017437a  mov     rcx, cs:WPP_GLOBAL_Control
0x140174381  lea     rax, WPP_dc968d99198e32e9263b7dc94e457b33_Traceguids
0x140174388  mov     r9d, 53h ; 'S'; int
0x14017438e  mov     dword ptr [rsp+1D0h+var_1A0], r15d; char
0x140174393  mov     qword ptr [rsp+1D0h+var_1A8], rbx; char
0x140174398  mov     dl, 4; int
0x14017439a  mov     [rsp+1D0h+var_1B0], rax; struct _GUID *
0x14017439f  mov     rcx, [rcx+40h]; int
0x1401743a3  lea     r8d, [r9-45h]; int
0x1401743a7  call    WPP_RECORDER_SF_qD
0x1401743ac  mov     edx, r15d; enum _NDIS_DEVICE_POWER_STATE
0x1401743af  mov     rcx, rbx; struct _NDIS_MINIPORT_BLOCK *
0x1401743b2  call    ?NDIS_COUNT_POWER_TRANSITION@@YAXPEAU_NDIS_MINIPORT_BLOCK@@W4_NDIS_DEVICE_POWER_STATE@@@Z; NDIS_COUNT_POWER_TRANSITION(_NDIS_MINIPORT_BLOCK *,_NDIS_DEVICE_POWER_STATE)
0x1401743b7  test    cs:byte_14011B001, 8
0x1401743be  mov     esi, 1
0x1401743c3  jz      short loc_1401743FA
0x1401743c5  mov     rax, [rbx+0FB8h]
0x1401743cc  lea     r8, [rbx+0FA8h]
0x1401743d3  mov     dword ptr [rsp+1D0h+var_198], r15d
0x1401743d8  lea     rdx, DevicePowerStateChange
0x1401743df  mov     dword ptr [rsp+1D0h+var_1A0], esi
0x1401743e3  mov     r9, r8
0x1401743e6  mov     qword ptr [rsp+1D0h+var_1A8], rax
0x1401743eb  mov     eax, [rbx+0FD8h]
0x1401743f1  mov     dword ptr [rsp+1D0h+var_1B0], eax
0x1401743f5  call    McTemplateK0jqxqq_EtwWriteTransfer
  ... truncated ...
```
