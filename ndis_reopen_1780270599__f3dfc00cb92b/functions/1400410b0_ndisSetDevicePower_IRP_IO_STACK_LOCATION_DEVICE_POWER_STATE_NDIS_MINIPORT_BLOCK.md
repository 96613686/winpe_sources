# ndisSetDevicePower(_IRP *,_IO_STACK_LOCATION *,_DEVICE_POWER_STATE,_NDIS_MINIPORT_BLOCK *)

- ea: `0x1400410b0`
- end: `0x1400416a7`
- name: `?ndisSetDevicePower@@YAJPEAU_IRP@@PEAU_IO_STACK_LOCATION@@W4_DEVICE_POWER_STATE@@PEAU_NDIS_MINIPORT_BLOCK@@@Z`
- size: `1527`
- prototype: `__int64 __fastcall(PIRP Irp, struct _IO_STACK_LOCATION *, enum _DEVICE_POWER_STATE, struct _NDIS_MINIPORT_BLOCK *)`
- caller_count: `1`
- callee_count: `18`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14005f440`

## callees

- `0x1400110b0`
- `0x14003d6e0`
- `0x14003f590`
- `0x1400410b0`
- `0x1400416b0`
- `0x140041a30`
- `0x140041ae0`
- `0x140041bc0`
- `0x140045f10`
- `0x140080b80`
- `0x140088080`
- `0x1400886c0`
- `0x14013fe90`
- `0x14015e6f0`
- `0x140164e70`
- `0x14016d870`
- `0x1401701f0`
- `0x140185210`

## import_xrefs

- `ntoskrnl!IofCallDriver` at `0x140041286`
- `ntoskrnl!IofCallDriver` at `0x14004131e`
- `ntoskrnl!IofCallDriver` at `0x1400413b0`
- `ntoskrnl!IofCallDriver` at `0x140041286`
- `ntoskrnl!IofCallDriver` at `0x14004131e`
- `ntoskrnl!IofCallDriver` at `0x1400413b0`
- `ntoskrnl!KeQueryUnbiasedInterruptTime` at `0x1400412c2`
- `ntoskrnl!KeQueryUnbiasedInterruptTime` at `0x1400412c2`
- `ntoskrnl!IofCompleteRequest` at `0x1400414be`
- `ntoskrnl!IofCompleteRequest` at `0x140041524`
- `ntoskrnl!IofCompleteRequest` at `0x1400414be`
- `ntoskrnl!IofCompleteRequest` at `0x140041524`
- `ntoskrnl!KeClearEvent` at `0x1400413d6`
- `ntoskrnl!KeClearEvent` at `0x1400413d6`
- `ntoskrnl!KeReleaseSpinLock` at `0x14004141b`
- `ntoskrnl!KeReleaseSpinLock` at `0x14004153a`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400415a3`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400ef8f2`
- `ntoskrnl!KeReleaseSpinLock` at `0x14004141b`
- `ntoskrnl!KeReleaseSpinLock` at `0x14004153a`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400415a3`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400ef8f2`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400413f4`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14004157b`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400413f4`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14004157b`

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
  if ( (byte_140121001 & 8) != 0 )
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
      if ( (byte_140121003 & 4) != 0 )
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
  if ( (byte_140121003 & 0x40) != 0 )
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
0x1400410b0  push    rbx
0x1400410b2  push    rbp
0x1400410b3  push    rsi
0x1400410b4  push    rdi
0x1400410b5  push    r12
0x1400410b7  push    r15
0x1400410b9  sub     rsp, 58h
0x1400410bd  mov     rbx, r9
0x1400410c0  mov     edi, r8d
0x1400410c3  mov     rbp, rdx
0x1400410c6  mov     rsi, rcx
0x1400410c9  lea     r15, WPP_RECORDER_INITIALIZED
0x1400410d0  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x1400410d7  lea     r12, WPP_dc968d99198e32e9263b7dc94e457b33_Traceguids
0x1400410de  jnz     loc_1400414D1
0x1400410e4  test    cs:byte_140121001, 8
0x1400410eb  jz      short loc_140041125
0x1400410ed  mov     rax, [rbx+0FB8h]
0x1400410f4  lea     r8, [rbx+0FA8h]
0x1400410fb  mov     dword ptr [rsp+88h+var_50], edi
0x1400410ff  lea     rdx, MiniportPowerDeviceState
0x140041106  mov     dword ptr [rsp+88h+var_58], 1
0x14004110e  mov     r9, r8
0x140041111  mov     qword ptr [rsp+88h+var_60], rax
0x140041116  mov     eax, [rbx+0FD8h]
0x14004111c  mov     dword ptr [rsp+88h+var_68], eax
0x140041120  call    McTemplateK0jqxqq_EtwWriteTransfer
0x140041125  cmp     edi, 4
0x140041128  jnz     loc_1400412AD
0x14004112e  prefetchw byte ptr [rbx+1148h]
0x140041135  mov     eax, [rbx+1148h]
0x14004113b  mov     ecx, eax
0x14004113d  and     ecx, 0FFFFFFFBh
0x140041140  lock cmpxchg [rbx+1148h], ecx
0x140041148  jnz     short loc_14004113B
0x14004114a  test    al, 4
0x14004114c  jz      loc_1400412FC
0x140041152  mov     [rsp+88h+arg_0], r14
0x14004115a  mov     r14, [rbx+1160h]
0x140041161  test    r14, r14
0x140041164  jnz     loc_140041578
0x14004116a  mov     rcx, rbx; struct _NDIS_MINIPORT_BLOCK *
0x14004116d  call    ?ndisIsMiniportStarted@@YAEPEAU_NDIS_MINIPORT_BLOCK@@@Z; ndisIsMiniportStarted(_NDIS_MINIPORT_BLOCK *)
0x140041172  test    al, al
0x140041174  jz      loc_14004121E
0x14004117a  cmp     dword ptr [rbx+5F0h], 1
0x140041181  jnz     loc_14004121E
0x140041187  test    dword ptr [rbx+7Ch], 800h
0x14004118e  jz      loc_1400413CF
0x140041194  mov     eax, [rbx+7Ch]
0x140041197  test    al, 20h
0x140041199  jz      loc_140041440
0x14004119f  mov     rcx, rbx; struct _NDIS_MINIPORT_BLOCK *
0x1400411a2  call    ?ndisCancelWakeUpDpcTimer@@YAXPEAU_NDIS_MINIPORT_BLOCK@@@Z; ndisCancelWakeUpDpcTimer(_NDIS_MINIPORT_BLOCK *)
0x1400411a7  mov     rcx, rbx; struct _NDIS_MINIPORT_BLOCK *
0x1400411aa  call    ?ndisWaitForResetCompletion@@YAXPEAU_NDIS_MINIPORT_BLOCK@@@Z; ndisWaitForResetCompletion(_NDIS_MINIPORT_BLOCK *)
0x1400411af  test    dword ptr [rbx+7Ch], 800h
0x1400411b6  jz      short loc_1400411CA
0x1400411b8  xor     edx, edx; unsigned __int8
0x1400411ba  mov     rcx, rbx; struct _NDIS_MINIPORT_BLOCK *
0x1400411bd  call    ?ndisSetDeviceInterfaceState@@YAXPEAU_NDIS_MINIPORT_BLOCK@@E@Z; ndisSetDeviceInterfaceState(_NDIS_MINIPORT_BLOCK *,uchar)
0x1400411c2  lock or dword ptr [rbx+1148h], 10h
0x1400411ca  mov     r9b, 1; unsigned __int8
0x1400411cd  mov     r8d, 0FD010101h; unsigned int
0x1400411d3  mov     edx, edi; enum _DEVICE_POWER_STATE
0x1400411d5  mov     rcx, rbx; struct _NDIS_MINIPORT_BLOCK *
0x1400411d8  call    ?ndisQuerySetMiniportDeviceState@@YAHPEAU_NDIS_MINIPORT_BLOCK@@W4_DEVICE_POWER_STATE@@KE@Z; ndisQuerySetMiniportDeviceState(_NDIS_MINIPORT_BLOCK *,_DEVICE_POWER_STATE,ulong,uchar)
0x1400411dd  mov     ebp, eax
0x1400411df  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x1400411e6  jz      short loc_140041216
0x1400411e8  mov     rcx, cs:WPP_GLOBAL_Control
0x1400411ef  mov     r9d, 66h ; 'f'; int
0x1400411f5  mov     dword ptr [rsp+88h+var_50], eax; char
0x1400411f9  mov     r8d, 0Eh; int
0x1400411ff  mov     dword ptr [rsp+88h+var_58], edi; char
0x140041203  mov     qword ptr [rsp+88h+var_60], rbx; char
0x140041208  mov     rcx, [rcx+40h]; int
0x14004120c  mov     [rsp+88h+var_68], r12; struct _GUID *
0x140041211  call    WPP_RECORDER_SF_qLL
0x140041216  test    ebp, ebp
0x140041218  jnz     loc_1400415C2
0x14004121e  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x140041225  jnz     loc_14004167A
0x14004122b  mov     rax, [rsi+0B8h]
0x140041232  lea     rcx, ?ndisSetDevicePowerDownComplete@@YAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@PEAX@Z; ndisSetDevicePowerDownComplete(_DEVICE_OBJECT *,_IRP *,void *)
0x140041239  mov     rdx, rsi; Irp
0x14004123c  movups  xmm0, xmmword ptr [rax]
0x14004123f  movups  xmmword ptr [rax-48h], xmm0
0x140041243  movups  xmm1, xmmword ptr [rax+10h]
0x140041247  movups  xmmword ptr [rax-38h], xmm1
0x14004124b  movups  xmm0, xmmword ptr [rax+20h]
0x14004124f  movups  xmmword ptr [rax-28h], xmm0
0x140041253  movsd   xmm1, qword ptr [rax+30h]
0x140041258  movsd   qword ptr [rax-18h], xmm1
0x14004125d  mov     byte ptr [rax-45h], 0
0x140041261  mov     rax, [rsi+0B8h]
0x140041268  mov     [rax-10h], rcx
0x14004126c  mov     [rax-8], rbx
0x140041270  mov     byte ptr [rax-45h], 0E0h
0x140041274  mov     rax, [rsi+0B8h]
0x14004127b  or      byte ptr [rax+3], 1
0x14004127f  mov     rcx, [rbx+0F00h]; DeviceObject
0x140041286  call    cs:__imp_IofCallDriver
0x14004128d  nop     dword ptr [rax+rax+00h]
0x140041292  mov     eax, 103h
0x140041297  mov     r14, [rsp+88h+arg_0]
0x14004129f  add     rsp, 58h
0x1400412a3  pop     r15
0x1400412a5  pop     r12
0x1400412a7  pop     rdi
0x1400412a8  pop     rsi
0x1400412a9  pop     rbp
0x1400412aa  pop     rbx
0x1400412ab  retn
0x1400412ad  mov     ecx, edi
0x1400412af  sub     ecx, 1
0x1400412b2  jnz     loc_140041506
0x1400412b8  cmp     qword ptr [rbx+1168h], 0
0x1400412c0  jz      short loc_1400412DC
0x1400412c2  call    cs:__imp_KeQueryUnbiasedInterruptTime
0x1400412c9  nop     dword ptr [rax+rax+00h]
0x1400412ce  mov     rcx, [rbx+1168h]
0x1400412d5  mov     [rcx+448h], rax
0x1400412dc  prefetchw byte ptr [rbx+1148h]
0x1400412e3  mov     eax, [rbx+1148h]
0x1400412e9  mov     ecx, eax
0x1400412eb  and     ecx, 0FFFFFFFDh
0x1400412ee  lock cmpxchg [rbx+1148h], ecx
0x1400412f6  jnz     short loc_1400412E9
0x1400412f8  test    al, 2
0x1400412fa  jnz     short loc_140041338
0x1400412fc  lock or dword ptr [rbx+1148h], 8
0x140041304  inc     byte ptr [rsi+43h]
0x140041307  xor     eax, eax
0x140041309  add     qword ptr [rsi+0B8h], 48h ; 'H'
0x140041311  mov     rdx, rsi; Irp
0x140041314  mov     [rsi+30h], eax
0x140041317  mov     rcx, [rbx+0F00h]; DeviceObject
0x14004131e  call    cs:__imp_IofCallDriver
0x140041325  nop     dword ptr [rax+rax+00h]
0x14004132a  add     rsp, 58h
0x14004132e  pop     r15
0x140041330  pop     r12
0x140041332  pop     rdi
0x140041333  pop     rsi
0x140041334  pop     rbp
0x140041335  pop     rbx
0x140041336  retn
0x140041338  mov     rdi, [rbx+1160h]
0x14004133f  test    rdi, rdi
0x140041342  jnz     loc_1400413F1
0x140041348  mov     rax, [rsi+0B8h]
0x14004134f  lea     rcx, ?ndisSetDevicePowerOnComplete@@YAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@PEAX@Z; ndisSetDevicePowerOnComplete(_DEVICE_OBJECT *,_IRP *,void *)
0x140041356  movups  xmm0, xmmword ptr [rax]
0x140041359  movups  xmmword ptr [rax-48h], xmm0
0x14004135d  movups  xmm1, xmmword ptr [rax+10h]
0x140041361  movups  xmmword ptr [rax-38h], xmm1
0x140041365  movups  xmm0, xmmword ptr [rax+20h]
0x140041369  movups  xmmword ptr [rax-28h], xmm0
0x14004136d  movsd   xmm1, qword ptr [rax+30h]
0x140041372  movsd   qword ptr [rax-18h], xmm1
0x140041377  mov     byte ptr [rax-45h], 0
0x14004137b  mov     rax, [rsi+0B8h]
0x140041382  mov     [rax-10h], rcx
0x140041386  mov     [rax-8], rbx
0x14004138a  mov     byte ptr [rax-45h], 0E0h
0x14004138e  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x140041395  jnz     loc_14004154B
0x14004139b  mov     rax, [rsi+0B8h]
0x1400413a2  mov     rdx, rsi; Irp
0x1400413a5  or      byte ptr [rax+3], 1
0x1400413a9  mov     rcx, [rbx+0F00h]; DeviceObject
0x1400413b0  call    cs:__imp_IofCallDriver
0x1400413b7  nop     dword ptr [rax+rax+00h]
0x1400413bc  mov     eax, 103h
0x1400413c1  add     rsp, 58h
0x1400413c5  pop     r15
0x1400413c7  pop     r12
0x1400413c9  pop     rdi
0x1400413ca  pop     rsi
0x1400413cb  pop     rbp
0x1400413cc  pop     rbx
0x1400413cd  retn
0x1400413cf  lea     rcx, [rbx+0E90h]; Event
0x1400413d6  call    cs:__imp_KeClearEvent
0x1400413dd  nop     dword ptr [rax+rax+00h]
0x1400413e2  mov     edx, edi; enum _NDIS_DEVICE_POWER_STATE
0x1400413e4  mov     rcx, rbx; struct _NDIS_MINIPORT_BLOCK *
0x1400413e7  call    ?ndisPrepForLowPower@@YAJPEAU_NDIS_MINIPORT_BLOCK@@W4_NDIS_DEVICE_POWER_STATE@@@Z; ndisPrepForLowPower(_NDIS_MINIPORT_BLOCK *,_NDIS_DEVICE_POWER_STATE)
0x1400413ec  jmp     loc_140041194
0x1400413f1  mov     rcx, rdi; SpinLock
0x1400413f4  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400413fb  nop     dword ptr [rax+rax+00h]
0x140041400  mov     edx, [rdi+1F8h]
0x140041406  mov     rcx, rdi; SpinLock
0x140041409  and     edx, 120h
0x14004140f  cmp     edx, 20h ; ' '
0x140041412  movzx   edx, al; NewIrql
0x140041415  jnz     loc_14004153A
0x14004141b  call    cs:__imp_KeReleaseSpinLock
0x140041422  nop     dword ptr [rax+rax+00h]
0x140041427  mov     r8, rbx; struct _NDIS_MINIPORT_BLOCK *
0x14004142a  mov     rcx, rsi; struct _IRP *
0x14004142d  call    ?ndisSetPowerResume@@YAJPEAU_IRP@@PEAU_IO_STACK_LOCATION@@PEAU_NDIS_MINIPORT_BLOCK@@@Z; ndisSetPowerResume(_IRP *,_IO_STACK_LOCATION *,_NDIS_MINIPORT_BLOCK *)
0x140041432  add     rsp, 58h
0x140041436  pop     r15
0x140041438  pop     r12
0x14004143a  pop     rdi
0x14004143b  pop     rsi
0x14004143c  pop     rbp
0x14004143d  pop     rbx
0x14004143e  retn
0x140041440  mov     rax, [rbx+0EB0h]
0x140041447  test    byte ptr [rax+1Ah], 1
0x14004144b  jnz     loc_14004121E
0x140041451  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x140041458  jnz     loc_140041614
0x14004145e  test    cs:byte_140121003, 4
0x140041465  jnz     loc_140041641
0x14004146b  test    dword ptr [rbx+7Ch], 100h
0x140041472  jnz     loc_14004121E
0x140041478  lea     rcx, [rbx+1478h]
0x14004147f  call    ?Release@?$KNeutralLock@W4NDIS_MINIPORT_POLICY_OWNER@@@Rtl@@QEAAXW4NDIS_MINIPORT_POLICY_OWNER@@@Z; Rtl::KNeutralLock<NDIS_MINIPORT_POLICY_OWNER>::Release(NDIS_MINIPORT_POLICY_OWNER)
0x140041484  mov     rcx, rbx; struct _NDIS_MINIPORT_BLOCK *
0x140041487  call    ?ndisPmHaltMiniport@@_Y2PAGENPNP@@AXPEAU_NDIS_MINIPORT_BLOCK@@@Z; ndisPmHaltMiniport(_NDIS_MINIPORT_BLOCK *)
0x14004148c  mov     edx, 1
0x140041491  lea     rcx, [rbx+1478h]
0x140041498  call    ?Acquire@?$KNeutralLock@W4NDIS_MINIPORT_POLICY_OWNER@@@Rtl@@QEAAXW4NDIS_MINIPORT_POLICY_OWNER@@@Z; Rtl::KNeutralLock<NDIS_MINIPORT_POLICY_OWNER>::Acquire(NDIS_MINIPORT_POLICY_OWNER)
0x14004149d  jmp     loc_14004121E
0x1400414a2  mov     ecx, eax
0x1400414a4  lock cmpxchg [rbx+1148h], ecx
0x1400414ac  jnz     short loc_1400414A2
0x1400414ae  test    al, 10h
0x1400414b0  jnz     loc_1400415FD
0x1400414b6  xor     edx, edx; PriorityBoost
0x1400414b8  mov     [rsi+30h], ebp
0x1400414bb  mov     rcx, rsi; Irp
0x1400414be  call    cs:__imp_IofCompleteRequest
0x1400414c5  nop     dword ptr [rax+rax+00h]
0x1400414ca  mov     eax, ebp
0x1400414cc  jmp     loc_140041297
0x1400414d1  mov     rcx, cs:WPP_GLOBAL_Control
0x1400414d8  mov     r9d, 64h ; 'd'; int
0x1400414de  mov     rax, [rbx+0F10h]
0x1400414e5  mov     qword ptr [rsp+88h+var_50], rax; __int64
0x1400414ea  mov     qword ptr [rsp+88h+var_58], rbx; char
0x1400414ef  mov     rcx, [rcx+40h]; int
0x1400414f3  mov     dword ptr [rsp+88h+var_60], edi; char
0x1400414f7  mov     [rsp+88h+var_68], r12; struct _GUID *
0x1400414fc  call    WPP_RECORDER_SF_LqZ
0x140041501  jmp     loc_1400410E4
0x140041506  sub     ecx, 1
0x140041509  jz      loc_14004112E
0x14004150f  cmp     ecx, 1
0x140041512  jz      loc_14004112E
0x140041518  xor     edx, edx; PriorityBoost
0x14004151a  mov     dword ptr [rsi+30h], 0C000000Dh
0x140041521  mov     rcx, rsi; Irp
0x140041524  call    cs:__imp_IofCompleteRequest
0x14004152b  nop     dword ptr [rax+rax+00h]
0x140041530  mov     eax, 0C000000Dh
0x140041535  jmp     loc_14004129F
0x14004153a  call    cs:__imp_KeReleaseSpinLock
0x140041541  nop     dword ptr [rax+rax+00h]
0x140041546  jmp     loc_140041348
0x14004154b  mov     rcx, cs:WPP_GLOBAL_Control
0x140041552  mov     r9d, 65h ; 'e'; int
0x140041558  mov     qword ptr [rsp+88h+var_60], rbx; char
0x14004155d  mov     r8d, 0Eh; int
0x140041563  mov     dl, 4; int
0x140041565  mov     [rsp+88h+var_68], r12; struct _GUID *
0x14004156a  mov     rcx, [rcx+40h]; int
0x14004156e  call    WPP_RECORDER_SF_q
0x140041573  jmp     loc_14004139B
0x140041578  mov     rcx, r14; SpinLock
0x14004157b  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140041582  nop     dword ptr [rax+rax+00h]
0x140041587  mov     edx, [r14+1F8h]
0x14004158e  mov     rcx, r14; SpinLock
0x140041591  and     edx, 108h
0x140041597  cmp     edx, 8
0x14004159a  movzx   edx, al; NewIrql
0x14004159d  jnz     loc_1400EF8F2
0x1400415a3  call    cs:__imp_KeReleaseSpinLock
0x1400415aa  nop     dword ptr [rax+rax+00h]
0x1400415af  mov     r8, rbx; struct _NDIS_MINIPORT_BLOCK *
0x1400415b2  mov     rdx, rbp; struct _IO_STACK_LOCATION *
0x1400415b5  mov     rcx, rsi; Irp
0x1400415b8  call    ?ndisSetPowerSuspend@@YAJPEAU_IRP@@PEAU_IO_STACK_LOCATION@@PEAU_NDIS_MINIPORT_BLOCK@@@Z; ndisSetPowerSuspend(_IRP *,_IO_STACK_LOCATION *,_NDIS_MINIPORT_BLOCK *)
0x1400415bd  jmp     loc_140041297
0x1400415c2  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x1400415c9  jz      loc_1400EF904
0x1400415cf  mov     rcx, cs:WPP_GLOBAL_Control
0x1400415d6  mov     r9d, 67h ; 'g'; int
0x1400415dc  mov     qword ptr [rsp+88h+var_60], rbx; char
0x1400415e1  mov     r8d, 0Eh; int
0x1400415e7  mov     dl, 2; int
0x1400415e9  mov     [rsp+88h+var_68], r12; struct _GUID *
0x1400415ee  mov     rcx, [rcx+40h]; int
0x1400415f2  call    WPP_RECORDER_SF_q
  ... truncated ...
```
