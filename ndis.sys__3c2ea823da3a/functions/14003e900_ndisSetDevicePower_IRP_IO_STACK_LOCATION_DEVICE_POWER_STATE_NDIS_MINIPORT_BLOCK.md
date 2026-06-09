# ndisSetDevicePower(_IRP *,_IO_STACK_LOCATION *,_DEVICE_POWER_STATE,_NDIS_MINIPORT_BLOCK *)

- ea: `0x14003e900`
- end: `0x14003eef7`
- name: `?ndisSetDevicePower@@YAJPEAU_IRP@@PEAU_IO_STACK_LOCATION@@W4_DEVICE_POWER_STATE@@PEAU_NDIS_MINIPORT_BLOCK@@@Z`
- size: `1527`
- prototype: `__int64 __fastcall(PIRP Irp, struct _IO_STACK_LOCATION *, enum _DEVICE_POWER_STATE, struct _NDIS_MINIPORT_BLOCK *)`
- caller_count: `1`
- callee_count: `18`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14005ae50`

## callees

- `0x140012a70`
- `0x14001cf50`
- `0x14003a720`
- `0x14003cde0`
- `0x14003e900`
- `0x14003ef00`
- `0x14003f280`
- `0x14003f330`
- `0x140043030`
- `0x14007b4e0`
- `0x140082e00`
- `0x140083440`
- `0x140138e90`
- `0x140157750`
- `0x1401661c0`
- `0x1401669d0`
- `0x140169300`
- `0x14017ef50`

## import_xrefs

- `ntoskrnl!IofCallDriver` at `0x14003ead6`
- `ntoskrnl!IofCallDriver` at `0x14003eb6e`
- `ntoskrnl!IofCallDriver` at `0x14003ec00`
- `ntoskrnl!IofCallDriver` at `0x14003ead6`
- `ntoskrnl!IofCallDriver` at `0x14003eb6e`
- `ntoskrnl!IofCallDriver` at `0x14003ec00`
- `ntoskrnl!KeQueryUnbiasedInterruptTime` at `0x14003eb12`
- `ntoskrnl!KeQueryUnbiasedInterruptTime` at `0x14003eb12`
- `ntoskrnl!IofCompleteRequest` at `0x14003ed0e`
- `ntoskrnl!IofCompleteRequest` at `0x14003ed74`
- `ntoskrnl!IofCompleteRequest` at `0x14003ed0e`
- `ntoskrnl!IofCompleteRequest` at `0x14003ed74`
- `ntoskrnl!KeClearEvent` at `0x14003ec26`
- `ntoskrnl!KeClearEvent` at `0x14003ec26`
- `ntoskrnl!KeReleaseSpinLock` at `0x14003ec6b`
- `ntoskrnl!KeReleaseSpinLock` at `0x14003ed8a`
- `ntoskrnl!KeReleaseSpinLock` at `0x14003edf3`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400eac38`
- `ntoskrnl!KeReleaseSpinLock` at `0x14003ec6b`
- `ntoskrnl!KeReleaseSpinLock` at `0x14003ed8a`
- `ntoskrnl!KeReleaseSpinLock` at `0x14003edf3`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400eac38`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14003ec44`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14003edcb`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14003ec44`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14003edcb`

## pseudocode

```c
NTSTATUS __fastcall ndisSetDevicePower(
        PIRP Irp,
        struct _IO_STACK_LOCATION *a2,
        enum _NDIS_DEVICE_POWER_STATE a3,
        struct _NDIS_MINIPORT_BLOCK *a4)
{
  struct _IO_STACK_LOCATION *v6; // rbp
  struct _NDIS_SELECTIVE_SUSPEND *v8; // r14
  int v9; // edx
  __int64 v10; // rcx
  int SetMiniportDeviceState; // eax
  int v12; // ecx
  int v13; // ebp
  _IO_STACK_LOCATION *v14; // rax
  _IO_STACK_LOCATION *v15; // rax
  struct _NDIS_SELECTIVE_SUSPEND *SelectiveSuspend; // rdi
  _IO_STACK_LOCATION *CurrentStackLocation; // rax
  _IO_STACK_LOCATION *v19; // rax
  KIRQL v20; // al
  struct _IO_STACK_LOCATION *v21; // rdx
  unsigned int InterlockedFlags; // eax
  unsigned int v23; // ett
  KIRQL v24; // al

  v6 = a2;
  if ( *(enum Ndis::ReadBindingsOptions::Flags **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_LqZ(
      *((_QWORD *)WPP_GLOBAL_Control + 8),
      (int)a2,
      a3,
      100,
      (struct _GUID *)&WPP_dc968d99198e32e9263b7dc94e457b33_Traceguids,
      a3,
      (char)a4,
      (__int64)a4->pAdapterInstanceName);
  if ( (byte_14011B001 & 8) != 0 )
    ((void (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD, _DWORD, _DWORD))McTemplateK0jqxqq_EtwWriteTransfer)(
      Irp,
      MiniportPowerDeviceState,
      &a4->InterfaceGuid,
      &a4->InterfaceGuid,
      a4->IfIndex,
      (_NET_LUID_LH)a4->NetLuid.Value,
      1,
      a3);
  if ( a3 != NdisDeviceStateD3 )
  {
    if ( a3 == NdisDeviceStateD0 )
    {
      if ( a4->AoAc )
        *((_QWORD *)a4->AoAc + 137) = KeQueryUnbiasedInterruptTime();
      _m_prefetchw(&a4->InterlockedFlags);
      if ( (_InterlockedAnd((volatile signed __int32 *)&a4->InterlockedFlags, 0xFFFFFFFD) & 2) != 0 )
      {
        SelectiveSuspend = a4->SelectiveSuspend;
        if ( SelectiveSuspend )
        {
          v20 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)a4->SelectiveSuspend);
          if ( (*((_DWORD *)SelectiveSuspend + 126) & 0x120) == 0x20 )
          {
            KeReleaseSpinLock((PKSPIN_LOCK)SelectiveSuspend, v20);
            return ndisSetPowerResume(Irp, v21, a4);
          }
          KeReleaseSpinLock((PKSPIN_LOCK)SelectiveSuspend, v20);
        }
        CurrentStackLocation = Irp->Tail.Overlay.CurrentStackLocation;
        *(_OWORD *)&CurrentStackLocation[-1].MajorFunction = *(_OWORD *)&CurrentStackLocation->MajorFunction;
        *(_OWORD *)&CurrentStackLocation[-1].Parameters.NotifyDirectoryEx.CompletionFilter = *(_OWORD *)&CurrentStackLocation->Parameters.NotifyDirectoryEx.CompletionFilter;
        *(_OWORD *)&CurrentStackLocation[-1].Parameters.ReadWriteConfig.Length = *(_OWORD *)&CurrentStackLocation->Parameters.ReadWriteConfig.Length;
        CurrentStackLocation[-1].FileObject = CurrentStackLocation->FileObject;
        CurrentStackLocation[-1].Control = 0;
        v19 = Irp->Tail.Overlay.CurrentStackLocation;
        v19[-1].CompletionRoutine = (int (__fastcall *)(_DEVICE_OBJECT *, _IRP *, void *))ndisSetDevicePowerOnComplete;
        v19[-1].Context = a4;
        v19[-1].Control = -32;
        if ( *(enum Ndis::ReadBindingsOptions::Flags **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
        {
          LOBYTE(a2) = 4;
          WPP_RECORDER_SF_q(
            *((_QWORD *)WPP_GLOBAL_Control + 8),
            (int)a2,
            14,
            101,
            (struct _GUID *)&WPP_dc968d99198e32e9263b7dc94e457b33_Traceguids,
            (char)a4);
        }
        Irp->Tail.Overlay.CurrentStackLocation->Control |= 1u;
        IofCallDriver(a4->NextDeviceObject, Irp);
        return 259;
      }
LABEL_25:
      _InterlockedOr((volatile signed __int32 *)&a4->InterlockedFlags, 8u);
      ++Irp->CurrentLocation;
      ++Irp->Tail.Overlay.CurrentStackLocation;
      Irp->IoStatus.Status = 0;
      return IofCallDriver(a4->NextDeviceObject, Irp);
    }
    if ( (unsigned int)(a3 - 2) >= 2 )
    {
      Irp->IoStatus.Status = -1073741811;
      IofCompleteRequest(Irp, 0);
      return -1073741811;
    }
  }
  _m_prefetchw(&a4->InterlockedFlags);
  if ( (_InterlockedAnd((volatile signed __int32 *)&a4->InterlockedFlags, 0xFFFFFFFB) & 4) == 0 )
    goto LABEL_25;
  v8 = a4->SelectiveSuspend;
  if ( v8 )
  {
    v24 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)a4->SelectiveSuspend);
    if ( (*((_DWORD *)v8 + 126) & 0x108) == 8 )
    {
      KeReleaseSpinLock((PKSPIN_LOCK)v8, v24);
      return ndisSetPowerSuspend(Irp, v6, a4);
    }
    KeReleaseSpinLock((PKSPIN_LOCK)v8, v24);
  }
  if ( !ndisIsMiniportStarted(a4) || a4->PnPDeviceState != NdisPnPDeviceStarted )
    goto LABEL_18;
  if ( (a4->PnPFlags & 0x800) == 0 )
  {
    KeClearEvent(&a4->OpenReadyEvent.Event);
    ndisPrepForLowPower(a4, a3);
  }
  if ( (a4->PnPFlags & 0x20) == 0 )
  {
    if ( (a4->DriverHandle->Flags & 1) == 0 )
    {
      if ( *(enum Ndis::ReadBindingsOptions::Flags **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v9) = 4;
        WPP_RECORDER_SF_q(
          *((_QWORD *)WPP_GLOBAL_Control + 8),
          v9,
          14,
          104,
          (struct _GUID *)&WPP_dc968d99198e32e9263b7dc94e457b33_Traceguids,
          (char)a4);
      }
      if ( (byte_14011B003 & 4) != 0 )
        ((void (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD, _DWORD))McTemplateK0jqxd_EtwWriteTransfer)(
          v10,
          PowerHaltMiniport,
          &a4->InterfaceGuid,
          &a4->InterfaceGuid,
          a4->IfIndex,
          (_NET_LUID_LH)a4->NetLuid.Value,
          65537);
      if ( (a4->PnPFlags & 0x100) == 0 )
      {
        Rtl::KNeutralLock<enum NDIS_MINIPORT_POLICY_OWNER>::Release(&a4->MiniportOwner);
        ndisPmHaltMiniport(a4);
        Rtl::KNeutralLock<enum NDIS_MINIPORT_POLICY_OWNER>::Acquire(&a4->MiniportOwner, 1);
      }
    }
    goto LABEL_18;
  }
  ndisCancelWakeUpDpcTimer(a4);
  ndisWaitForResetCompletion(a4);
  if ( (a4->PnPFlags & 0x800) != 0 )
  {
    ndisSetDeviceInterfaceState(a4, 0);
    _InterlockedOr((volatile signed __int32 *)&a4->InterlockedFlags, 0x10u);
  }
  SetMiniportDeviceState = ndisQuerySetMiniportDeviceState(a4, (enum _DEVICE_POWER_STATE)a3, 0xFD010101, 1u);
  v13 = SetMiniportDeviceState;
  if ( *(enum Ndis::ReadBindingsOptions::Flags **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_qLL(
      *((_QWORD *)WPP_GLOBAL_Control + 8),
      v9,
      14,
      102,
      (struct _GUID *)&WPP_dc968d99198e32e9263b7dc94e457b33_Traceguids,
      (char)a4,
      a3,
      SetMiniportDeviceState);
  if ( !v13 )
  {
LABEL_18:
    if ( *(enum Ndis::ReadBindingsOptions::Flags **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v9) = 4;
      WPP_RECORDER_SF_q(
        *((_QWORD *)WPP_GLOBAL_Control + 8),
        v9,
        14,
        105,
        (struct _GUID *)&WPP_dc968d99198e32e9263b7dc94e457b33_Traceguids,
        (char)a4);
    }
    v14 = Irp->Tail.Overlay.CurrentStackLocation;
    *(_OWORD *)&v14[-1].MajorFunction = *(_OWORD *)&v14->MajorFunction;
    *(_OWORD *)&v14[-1].Parameters.NotifyDirectoryEx.CompletionFilter = *(_OWORD *)&v14->Parameters.NotifyDirectoryEx.CompletionFilter;
    *(_OWORD *)&v14[-1].Parameters.ReadWriteConfig.Length = *(_OWORD *)&v14->Parameters.ReadWriteConfig.Length;
    v14[-1].FileObject = v14->FileObject;
    v14[-1].Control = 0;
    v15 = Irp->Tail.Overlay.CurrentStackLocation;
    v15[-1].CompletionRoutine = (int (__fastcall *)(_DEVICE_OBJECT *, _IRP *, void *))ndisSetDevicePowerDownComplete;
    v15[-1].Context = a4;
    v15[-1].Control = -32;
    Irp->Tail.Overlay.CurrentStackLocation->Control |= 1u;
    IofCallDriver(a4->NextDeviceObject, Irp);
    return 259;
  }
  if ( *(enum Ndis::ReadBindingsOptions::Flags **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v9) = 2;
    WPP_RECORDER_SF_q(
      *((_QWORD *)WPP_GLOBAL_Control + 8),
      v9,
      14,
      103,
      (struct _GUID *)&WPP_dc968d99198e32e9263b7dc94e457b33_Traceguids,
      (char)a4);
  }
  if ( (byte_14011B003 & 0x40) != 0 )
    McTemplateK0jqxddq_EtwWriteTransfer(
      v12,
      (unsigned int)PowerDownFailed,
      (_DWORD)a4 + 4008,
      (_DWORD)a4 + 4008,
      a4->IfIndex,
      a4->NetLuid.Value,
      v13,
      1,
      0);
  Rtl::KNeutralLock<enum NDIS_MINIPORT_POLICY_OWNER>::Release(&a4->MiniportOwner);
  _m_prefetchw(&a4->InterlockedFlags);
  InterlockedFlags = a4->InterlockedFlags;
  do
  {
    v23 = InterlockedFlags;
    InterlockedFlags = _InterlockedCompareExchange(
                         (volatile signed __int32 *)&a4->InterlockedFlags,
                         InterlockedFlags,
                         InterlockedFlags);
  }
  while ( v23 != InterlockedFlags );
  if ( (InterlockedFlags & 0x10) != 0 )
  {
    ndisSetDeviceInterfaceState(a4, 1u);
    _InterlockedAnd((volatile signed __int32 *)&a4->InterlockedFlags, 0xFFFFFFEF);
  }
  Irp->IoStatus.Status = v13;
  IofCompleteRequest(Irp, 0);
  return v13;
}

```

## disassembly

```asm
0x14003e900  push    rbx
0x14003e902  push    rbp
0x14003e903  push    rsi
0x14003e904  push    rdi
0x14003e905  push    r12
0x14003e907  push    r15
0x14003e909  sub     rsp, 58h
0x14003e90d  mov     rbx, r9
0x14003e910  mov     edi, r8d
0x14003e913  mov     rbp, rdx
0x14003e916  mov     rsi, rcx
0x14003e919  lea     r15, WPP_RECORDER_INITIALIZED
0x14003e920  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x14003e927  lea     r12, WPP_dc968d99198e32e9263b7dc94e457b33_Traceguids
0x14003e92e  jnz     loc_14003ED21
0x14003e934  test    cs:byte_14011B001, 8
0x14003e93b  jz      short loc_14003E975
0x14003e93d  mov     rax, [rbx+0FB8h]
0x14003e944  lea     r8, [rbx+0FA8h]
0x14003e94b  mov     dword ptr [rsp+88h+var_50], edi
0x14003e94f  lea     rdx, MiniportPowerDeviceState
0x14003e956  mov     dword ptr [rsp+88h+var_58], 1
0x14003e95e  mov     r9, r8
0x14003e961  mov     qword ptr [rsp+88h+var_60], rax
0x14003e966  mov     eax, [rbx+0FD8h]
0x14003e96c  mov     dword ptr [rsp+88h+var_68], eax
0x14003e970  call    McTemplateK0jqxqq_EtwWriteTransfer
0x14003e975  cmp     edi, 4
0x14003e978  jnz     loc_14003EAFD
0x14003e97e  prefetchw byte ptr [rbx+1148h]
0x14003e985  mov     eax, [rbx+1148h]
0x14003e98b  mov     ecx, eax
0x14003e98d  and     ecx, 0FFFFFFFBh
0x14003e990  lock cmpxchg [rbx+1148h], ecx
0x14003e998  jnz     short loc_14003E98B
0x14003e99a  test    al, 4
0x14003e99c  jz      loc_14003EB4C
0x14003e9a2  mov     [rsp+88h+arg_0], r14
0x14003e9aa  mov     r14, [rbx+1160h]
0x14003e9b1  test    r14, r14
0x14003e9b4  jnz     loc_14003EDC8
0x14003e9ba  mov     rcx, rbx; struct _NDIS_MINIPORT_BLOCK *
0x14003e9bd  call    ?ndisIsMiniportStarted@@YAEPEAU_NDIS_MINIPORT_BLOCK@@@Z; ndisIsMiniportStarted(_NDIS_MINIPORT_BLOCK *)
0x14003e9c2  test    al, al
0x14003e9c4  jz      loc_14003EA6E
0x14003e9ca  cmp     dword ptr [rbx+5F0h], 1
0x14003e9d1  jnz     loc_14003EA6E
0x14003e9d7  test    dword ptr [rbx+7Ch], 800h
0x14003e9de  jz      loc_14003EC1F
0x14003e9e4  mov     eax, [rbx+7Ch]
0x14003e9e7  test    al, 20h
0x14003e9e9  jz      loc_14003EC90
0x14003e9ef  mov     rcx, rbx; struct _NDIS_MINIPORT_BLOCK *
0x14003e9f2  call    ?ndisCancelWakeUpDpcTimer@@YAXPEAU_NDIS_MINIPORT_BLOCK@@@Z; ndisCancelWakeUpDpcTimer(_NDIS_MINIPORT_BLOCK *)
0x14003e9f7  mov     rcx, rbx; struct _NDIS_MINIPORT_BLOCK *
0x14003e9fa  call    ?ndisWaitForResetCompletion@@YAXPEAU_NDIS_MINIPORT_BLOCK@@@Z; ndisWaitForResetCompletion(_NDIS_MINIPORT_BLOCK *)
0x14003e9ff  test    dword ptr [rbx+7Ch], 800h
0x14003ea06  jz      short loc_14003EA1A
0x14003ea08  xor     edx, edx; unsigned __int8
0x14003ea0a  mov     rcx, rbx; struct _NDIS_MINIPORT_BLOCK *
0x14003ea0d  call    ?ndisSetDeviceInterfaceState@@YAXPEAU_NDIS_MINIPORT_BLOCK@@E@Z; ndisSetDeviceInterfaceState(_NDIS_MINIPORT_BLOCK *,uchar)
0x14003ea12  lock or dword ptr [rbx+1148h], 10h
0x14003ea1a  mov     r9b, 1; unsigned __int8
0x14003ea1d  mov     r8d, 0FD010101h; unsigned int
0x14003ea23  mov     edx, edi; enum _DEVICE_POWER_STATE
0x14003ea25  mov     rcx, rbx; struct _NDIS_MINIPORT_BLOCK *
0x14003ea28  call    ?ndisQuerySetMiniportDeviceState@@YAHPEAU_NDIS_MINIPORT_BLOCK@@W4_DEVICE_POWER_STATE@@KE@Z; ndisQuerySetMiniportDeviceState(_NDIS_MINIPORT_BLOCK *,_DEVICE_POWER_STATE,ulong,uchar)
0x14003ea2d  mov     ebp, eax
0x14003ea2f  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x14003ea36  jz      short loc_14003EA66
0x14003ea38  mov     rcx, cs:WPP_GLOBAL_Control
0x14003ea3f  mov     r9d, 66h ; 'f'; int
0x14003ea45  mov     dword ptr [rsp+88h+var_50], eax; char
0x14003ea49  mov     r8d, 0Eh; int
0x14003ea4f  mov     dword ptr [rsp+88h+var_58], edi; char
0x14003ea53  mov     qword ptr [rsp+88h+var_60], rbx; char
0x14003ea58  mov     rcx, [rcx+40h]; int
0x14003ea5c  mov     [rsp+88h+var_68], r12; struct _GUID *
0x14003ea61  call    WPP_RECORDER_SF_qLL
0x14003ea66  test    ebp, ebp
0x14003ea68  jnz     loc_14003EE12
0x14003ea6e  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x14003ea75  jnz     loc_14003EECA
0x14003ea7b  mov     rax, [rsi+0B8h]
0x14003ea82  lea     rcx, ?ndisSetDevicePowerDownComplete@@YAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@PEAX@Z; ndisSetDevicePowerDownComplete(_DEVICE_OBJECT *,_IRP *,void *)
0x14003ea89  mov     rdx, rsi; Irp
0x14003ea8c  movups  xmm0, xmmword ptr [rax]
0x14003ea8f  movups  xmmword ptr [rax-48h], xmm0
0x14003ea93  movups  xmm1, xmmword ptr [rax+10h]
0x14003ea97  movups  xmmword ptr [rax-38h], xmm1
0x14003ea9b  movups  xmm0, xmmword ptr [rax+20h]
0x14003ea9f  movups  xmmword ptr [rax-28h], xmm0
0x14003eaa3  movsd   xmm1, qword ptr [rax+30h]
0x14003eaa8  movsd   qword ptr [rax-18h], xmm1
0x14003eaad  mov     byte ptr [rax-45h], 0
0x14003eab1  mov     rax, [rsi+0B8h]
0x14003eab8  mov     [rax-10h], rcx
0x14003eabc  mov     [rax-8], rbx
0x14003eac0  mov     byte ptr [rax-45h], 0E0h
0x14003eac4  mov     rax, [rsi+0B8h]
0x14003eacb  or      byte ptr [rax+3], 1
0x14003eacf  mov     rcx, [rbx+0F00h]; DeviceObject
0x14003ead6  call    cs:__imp_IofCallDriver
0x14003eadd  nop     dword ptr [rax+rax+00h]
0x14003eae2  mov     eax, 103h
0x14003eae7  mov     r14, [rsp+88h+arg_0]
0x14003eaef  add     rsp, 58h
0x14003eaf3  pop     r15
0x14003eaf5  pop     r12
0x14003eaf7  pop     rdi
0x14003eaf8  pop     rsi
0x14003eaf9  pop     rbp
0x14003eafa  pop     rbx
0x14003eafb  retn
0x14003eafd  mov     ecx, edi
0x14003eaff  sub     ecx, 1
0x14003eb02  jnz     loc_14003ED56
0x14003eb08  cmp     qword ptr [rbx+1168h], 0
0x14003eb10  jz      short loc_14003EB2C
0x14003eb12  call    cs:__imp_KeQueryUnbiasedInterruptTime
0x14003eb19  nop     dword ptr [rax+rax+00h]
0x14003eb1e  mov     rcx, [rbx+1168h]
0x14003eb25  mov     [rcx+448h], rax
0x14003eb2c  prefetchw byte ptr [rbx+1148h]
0x14003eb33  mov     eax, [rbx+1148h]
0x14003eb39  mov     ecx, eax
0x14003eb3b  and     ecx, 0FFFFFFFDh
0x14003eb3e  lock cmpxchg [rbx+1148h], ecx
0x14003eb46  jnz     short loc_14003EB39
0x14003eb48  test    al, 2
0x14003eb4a  jnz     short loc_14003EB88
0x14003eb4c  lock or dword ptr [rbx+1148h], 8
0x14003eb54  inc     byte ptr [rsi+43h]
0x14003eb57  xor     eax, eax
0x14003eb59  add     qword ptr [rsi+0B8h], 48h ; 'H'
0x14003eb61  mov     rdx, rsi; Irp
0x14003eb64  mov     [rsi+30h], eax
0x14003eb67  mov     rcx, [rbx+0F00h]; DeviceObject
0x14003eb6e  call    cs:__imp_IofCallDriver
0x14003eb75  nop     dword ptr [rax+rax+00h]
0x14003eb7a  add     rsp, 58h
0x14003eb7e  pop     r15
0x14003eb80  pop     r12
0x14003eb82  pop     rdi
0x14003eb83  pop     rsi
0x14003eb84  pop     rbp
0x14003eb85  pop     rbx
0x14003eb86  retn
0x14003eb88  mov     rdi, [rbx+1160h]
0x14003eb8f  test    rdi, rdi
0x14003eb92  jnz     loc_14003EC41
0x14003eb98  mov     rax, [rsi+0B8h]
0x14003eb9f  lea     rcx, ?ndisSetDevicePowerOnComplete@@YAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@PEAX@Z; ndisSetDevicePowerOnComplete(_DEVICE_OBJECT *,_IRP *,void *)
0x14003eba6  movups  xmm0, xmmword ptr [rax]
0x14003eba9  movups  xmmword ptr [rax-48h], xmm0
0x14003ebad  movups  xmm1, xmmword ptr [rax+10h]
0x14003ebb1  movups  xmmword ptr [rax-38h], xmm1
0x14003ebb5  movups  xmm0, xmmword ptr [rax+20h]
0x14003ebb9  movups  xmmword ptr [rax-28h], xmm0
0x14003ebbd  movsd   xmm1, qword ptr [rax+30h]
0x14003ebc2  movsd   qword ptr [rax-18h], xmm1
0x14003ebc7  mov     byte ptr [rax-45h], 0
0x14003ebcb  mov     rax, [rsi+0B8h]
0x14003ebd2  mov     [rax-10h], rcx
0x14003ebd6  mov     [rax-8], rbx
0x14003ebda  mov     byte ptr [rax-45h], 0E0h
0x14003ebde  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x14003ebe5  jnz     loc_14003ED9B
0x14003ebeb  mov     rax, [rsi+0B8h]
0x14003ebf2  mov     rdx, rsi; Irp
0x14003ebf5  or      byte ptr [rax+3], 1
0x14003ebf9  mov     rcx, [rbx+0F00h]; DeviceObject
0x14003ec00  call    cs:__imp_IofCallDriver
0x14003ec07  nop     dword ptr [rax+rax+00h]
0x14003ec0c  mov     eax, 103h
0x14003ec11  add     rsp, 58h
0x14003ec15  pop     r15
0x14003ec17  pop     r12
0x14003ec19  pop     rdi
0x14003ec1a  pop     rsi
0x14003ec1b  pop     rbp
0x14003ec1c  pop     rbx
0x14003ec1d  retn
0x14003ec1f  lea     rcx, [rbx+0E90h]; Event
0x14003ec26  call    cs:__imp_KeClearEvent
0x14003ec2d  nop     dword ptr [rax+rax+00h]
0x14003ec32  mov     edx, edi; enum _NDIS_DEVICE_POWER_STATE
0x14003ec34  mov     rcx, rbx; struct _NDIS_MINIPORT_BLOCK *
0x14003ec37  call    ?ndisPrepForLowPower@@YAJPEAU_NDIS_MINIPORT_BLOCK@@W4_NDIS_DEVICE_POWER_STATE@@@Z; ndisPrepForLowPower(_NDIS_MINIPORT_BLOCK *,_NDIS_DEVICE_POWER_STATE)
0x14003ec3c  jmp     loc_14003E9E4
0x14003ec41  mov     rcx, rdi; SpinLock
0x14003ec44  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14003ec4b  nop     dword ptr [rax+rax+00h]
0x14003ec50  mov     edx, [rdi+1F8h]
0x14003ec56  mov     rcx, rdi; SpinLock
0x14003ec59  and     edx, 120h
0x14003ec5f  cmp     edx, 20h ; ' '
0x14003ec62  movzx   edx, al; NewIrql
0x14003ec65  jnz     loc_14003ED8A
0x14003ec6b  call    cs:__imp_KeReleaseSpinLock
0x14003ec72  nop     dword ptr [rax+rax+00h]
0x14003ec77  mov     r8, rbx; struct _NDIS_MINIPORT_BLOCK *
0x14003ec7a  mov     rcx, rsi; struct _IRP *
0x14003ec7d  call    ?ndisSetPowerResume@@YAJPEAU_IRP@@PEAU_IO_STACK_LOCATION@@PEAU_NDIS_MINIPORT_BLOCK@@@Z; ndisSetPowerResume(_IRP *,_IO_STACK_LOCATION *,_NDIS_MINIPORT_BLOCK *)
0x14003ec82  add     rsp, 58h
0x14003ec86  pop     r15
0x14003ec88  pop     r12
0x14003ec8a  pop     rdi
0x14003ec8b  pop     rsi
0x14003ec8c  pop     rbp
0x14003ec8d  pop     rbx
0x14003ec8e  retn
0x14003ec90  mov     rax, [rbx+0EB0h]
0x14003ec97  test    byte ptr [rax+1Ah], 1
0x14003ec9b  jnz     loc_14003EA6E
0x14003eca1  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x14003eca8  jnz     loc_14003EE64
0x14003ecae  test    cs:byte_14011B003, 4
0x14003ecb5  jnz     loc_14003EE91
0x14003ecbb  test    dword ptr [rbx+7Ch], 100h
0x14003ecc2  jnz     loc_14003EA6E
0x14003ecc8  lea     rcx, [rbx+1478h]
0x14003eccf  call    ?Release@?$KNeutralLock@W4NDIS_MINIPORT_POLICY_OWNER@@@Rtl@@QEAAXW4NDIS_MINIPORT_POLICY_OWNER@@@Z; Rtl::KNeutralLock<NDIS_MINIPORT_POLICY_OWNER>::Release(NDIS_MINIPORT_POLICY_OWNER)
0x14003ecd4  mov     rcx, rbx; struct _NDIS_MINIPORT_BLOCK *
0x14003ecd7  call    ?ndisPmHaltMiniport@@_Y2PAGENPNP@@AXPEAU_NDIS_MINIPORT_BLOCK@@@Z; ndisPmHaltMiniport(_NDIS_MINIPORT_BLOCK *)
0x14003ecdc  mov     edx, 1
0x14003ece1  lea     rcx, [rbx+1478h]
0x14003ece8  call    ?Acquire@?$KNeutralLock@W4NDIS_MINIPORT_POLICY_OWNER@@@Rtl@@QEAAXW4NDIS_MINIPORT_POLICY_OWNER@@@Z; Rtl::KNeutralLock<NDIS_MINIPORT_POLICY_OWNER>::Acquire(NDIS_MINIPORT_POLICY_OWNER)
0x14003eced  jmp     loc_14003EA6E
0x14003ecf2  mov     ecx, eax
0x14003ecf4  lock cmpxchg [rbx+1148h], ecx
0x14003ecfc  jnz     short loc_14003ECF2
0x14003ecfe  test    al, 10h
0x14003ed00  jnz     loc_14003EE4D
0x14003ed06  xor     edx, edx; PriorityBoost
0x14003ed08  mov     [rsi+30h], ebp
0x14003ed0b  mov     rcx, rsi; Irp
0x14003ed0e  call    cs:__imp_IofCompleteRequest
0x14003ed15  nop     dword ptr [rax+rax+00h]
0x14003ed1a  mov     eax, ebp
0x14003ed1c  jmp     loc_14003EAE7
0x14003ed21  mov     rcx, cs:WPP_GLOBAL_Control
0x14003ed28  mov     r9d, 64h ; 'd'; int
0x14003ed2e  mov     rax, [rbx+0F10h]
0x14003ed35  mov     qword ptr [rsp+88h+var_50], rax; __int64
0x14003ed3a  mov     qword ptr [rsp+88h+var_58], rbx; char
0x14003ed3f  mov     rcx, [rcx+40h]; int
0x14003ed43  mov     dword ptr [rsp+88h+var_60], edi; char
0x14003ed47  mov     [rsp+88h+var_68], r12; struct _GUID *
0x14003ed4c  call    WPP_RECORDER_SF_LqZ
0x14003ed51  jmp     loc_14003E934
0x14003ed56  sub     ecx, 1
0x14003ed59  jz      loc_14003E97E
0x14003ed5f  cmp     ecx, 1
0x14003ed62  jz      loc_14003E97E
0x14003ed68  xor     edx, edx; PriorityBoost
0x14003ed6a  mov     dword ptr [rsi+30h], 0C000000Dh
0x14003ed71  mov     rcx, rsi; Irp
0x14003ed74  call    cs:__imp_IofCompleteRequest
0x14003ed7b  nop     dword ptr [rax+rax+00h]
0x14003ed80  mov     eax, 0C000000Dh
0x14003ed85  jmp     loc_14003EAEF
0x14003ed8a  call    cs:__imp_KeReleaseSpinLock
0x14003ed91  nop     dword ptr [rax+rax+00h]
0x14003ed96  jmp     loc_14003EB98
0x14003ed9b  mov     rcx, cs:WPP_GLOBAL_Control
0x14003eda2  mov     r9d, 65h ; 'e'; int
0x14003eda8  mov     qword ptr [rsp+88h+var_60], rbx; char
0x14003edad  mov     r8d, 0Eh; int
0x14003edb3  mov     dl, 4; int
0x14003edb5  mov     [rsp+88h+var_68], r12; struct _GUID *
0x14003edba  mov     rcx, [rcx+40h]; int
0x14003edbe  call    WPP_RECORDER_SF_q
0x14003edc3  jmp     loc_14003EBEB
0x14003edc8  mov     rcx, r14; SpinLock
0x14003edcb  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14003edd2  nop     dword ptr [rax+rax+00h]
0x14003edd7  mov     edx, [r14+1F8h]
0x14003edde  mov     rcx, r14; SpinLock
0x14003ede1  and     edx, 108h
0x14003ede7  cmp     edx, 8
0x14003edea  movzx   edx, al; NewIrql
0x14003eded  jnz     loc_1400EAC38
0x14003edf3  call    cs:__imp_KeReleaseSpinLock
0x14003edfa  nop     dword ptr [rax+rax+00h]
0x14003edff  mov     r8, rbx; struct _NDIS_MINIPORT_BLOCK *
0x14003ee02  mov     rdx, rbp; struct _IO_STACK_LOCATION *
0x14003ee05  mov     rcx, rsi; Irp
0x14003ee08  call    ?ndisSetPowerSuspend@@YAJPEAU_IRP@@PEAU_IO_STACK_LOCATION@@PEAU_NDIS_MINIPORT_BLOCK@@@Z; ndisSetPowerSuspend(_IRP *,_IO_STACK_LOCATION *,_NDIS_MINIPORT_BLOCK *)
0x14003ee0d  jmp     loc_14003EAE7
0x14003ee12  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x14003ee19  jz      loc_1400EAC4A
0x14003ee1f  mov     rcx, cs:WPP_GLOBAL_Control
0x14003ee26  mov     r9d, 67h ; 'g'; int
0x14003ee2c  mov     qword ptr [rsp+88h+var_60], rbx; char
0x14003ee31  mov     r8d, 0Eh; int
0x14003ee37  mov     dl, 2; int
0x14003ee39  mov     [rsp+88h+var_68], r12; struct _GUID *
0x14003ee3e  mov     rcx, [rcx+40h]; int
0x14003ee42  call    WPP_RECORDER_SF_q
  ... truncated ...
```
