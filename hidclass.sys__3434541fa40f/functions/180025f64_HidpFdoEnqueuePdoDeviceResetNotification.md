# HidpFdoEnqueuePdoDeviceResetNotification

- ea: `0x180025f64`
- end: `0x1800268d0`
- name: `HidpFdoEnqueuePdoDeviceResetNotification`
- size: `2412`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x180006ac8`

## callees

- `0x18000a020`
- `0x18000cc90`
- `0x1800127d0`
- `0x180012d1c`
- `0x18001c8a0`
- `0x18001fba0`
- `0x180024b0c`
- `0x180025f64`
- `0x1800268d8`
- `0x1800269d8`

## import_xrefs

- `ntoskrnl!IoFreeIrp` at `0x1800266b8`
- `ntoskrnl!IoFreeIrp` at `0x1800266b8`
- `ntoskrnl!IoAllocateIrp` at `0x18002653e`
- `ntoskrnl!IoAllocateIrp` at `0x18002653e`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800266d2`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800266d2`
- `ntoskrnl!ExAllocatePool2` at `0x18002649a`
- `ntoskrnl!ExAllocatePool2` at `0x18002649a`
- `ntoskrnl!KeReleaseSpinLock` at `0x1800267e3`
- `ntoskrnl!KeReleaseSpinLock` at `0x1800268a6`
- `ntoskrnl!KeReleaseSpinLock` at `0x1800267e3`
- `ntoskrnl!KeReleaseSpinLock` at `0x1800268a6`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x180025f93`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x180025f93`
- `ntoskrnl!IoAcquireRemoveLockEx` at `0x18002661a`
- `ntoskrnl!IoAcquireRemoveLockEx` at `0x18002661a`

## pseudocode

```c
__int64 __fastcall HidpFdoEnqueuePdoDeviceResetNotification(_QWORD *a1, __int64 a2, __int64 a3, _BYTE *a4)
{
  char v8; // bl
  __int64 v9; // rdx
  __int64 v10; // r8
  NTSTATUS v11; // esi
  _QWORD *v12; // rdx
  int v13; // edx
  unsigned __int16 *CollectionDesc; // rsi
  int v15; // r8d
  int v16; // edx
  __int64 v17; // rcx
  int v18; // edx
  PDEVICE_OBJECT v19; // rcx
  __int64 v20; // rdx
  PIRP Irp; // rax
  __int64 v22; // rdx
  __int64 v23; // r8
  IRP *v24; // r13
  int v25; // edx
  int v26; // r8d
  __int64 v27; // rdx
  __int64 v28; // rax
  __int64 v29; // rdx
  _QWORD *v30; // rcx
  _IO_STACK_LOCATION *CurrentStackLocation; // rax
  _IO_STACK_LOCATION *v32; // rax
  int v33; // r8d
  int v34; // r9d
  __int64 v35; // rdx
  __int64 v36; // rax
  ULONG RemlockSize; // [rsp+20h] [rbp-A8h]
  char RemlockSizea; // [rsp+20h] [rbp-A8h]
  ULONG RemlockSizeb; // [rsp+20h] [rbp-A8h]
  int v41; // [rsp+28h] [rbp-A0h]
  __int16 v42; // [rsp+30h] [rbp-98h]
  int v43; // [rsp+38h] [rbp-90h]
  __int64 v44; // [rsp+40h] [rbp-88h]
  int v45; // [rsp+48h] [rbp-80h]
  __int64 v46; // [rsp+50h] [rbp-78h]
  char v47; // [rsp+58h] [rbp-70h]
  __int64 v48; // [rsp+60h] [rbp-68h]
  PVOID P; // [rsp+70h] [rbp-58h]
  IRP **Pa; // [rsp+70h] [rbp-58h]
  KSPIN_LOCK *SpinLock; // [rsp+78h] [rbp-50h]
  KIRQL NewIrql; // [rsp+D0h] [rbp+8h]

  SpinLock = a1 + 237;
  v8 = 1;
  NewIrql = KeAcquireSpinLockRaiseToDpc(a1 + 237);
  if ( *((_BYTE *)a1 + 1904) == 1 )
  {
    v11 = -1073741823;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || !_bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 9u)
      || BYTE1(WPP_GLOBAL_Control->Timer) < 3u )
    {
      v8 = 0;
    }
    LOBYTE(v10) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    if ( v8 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v9) = v8;
      WPP_RECORDER_AND_TRACE_SF_qdqqd(
        WPP_GLOBAL_Control->AttachedDevice,
        v9,
        v10,
        a1[84],
        3,
        10,
        17,
        (__int64)WPP_7dfbfdf723c8332f637dd0f8a651f634_Traceguids,
        *(_QWORD *)(*(_QWORD *)(a2 + 64) + 32LL),
        *(_DWORD *)(a2 + 8),
        *(_QWORD *)(a2 + 48),
        a3,
        -1073741823);
    }
    TraceLoggingDeviceResetNotificationFailed(a1, v9, v10);
    goto LABEL_115;
  }
  LOBYTE(v9) = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 9u)
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u;
  LOBYTE(v10) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
  if ( (_BYTE)v9 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_AND_TRACE_SF_qdqq(
      WPP_GLOBAL_Control->AttachedDevice,
      v9,
      v10,
      a1[84],
      4,
      10,
      18,
      (__int64)WPP_7dfbfdf723c8332f637dd0f8a651f634_Traceguids,
      *(_QWORD *)(*(_QWORD *)(a2 + 64) + 32LL),
      *(_DWORD *)(a2 + 8),
      *(_QWORD *)(a2 + 48),
      a3);
  *(_BYTE *)(*(_QWORD *)(a3 + 184) + 3LL) |= 1u;
  *a4 = 1;
  *(_QWORD *)(a3 + 120) = a2;
  v12 = (_QWORD *)a1[240];
  if ( (_QWORD *)*v12 != a1 + 239 )
    goto LABEL_117;
  *(_QWORD *)(a3 + 168) = a1 + 239;
  *(_QWORD *)(a3 + 176) = v12;
  *v12 = a3 + 168;
  a1[240] = a3 + 168;
  P = (PVOID)_InterlockedExchange64(
               (volatile __int64 *)(a3 + 104),
               (__int64)&HidpPdoDeviceResetNotificationCancelRoutine);
  if ( P )
  {
    CollectionDesc = (unsigned __int16 *)GetCollectionDesc(a1, *(unsigned int *)(a2 + 8), v10);
    LOBYTE(v13) = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
               && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 9u)
               && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u;
    if ( (_BYTE)v13 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v15) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      WPP_RECORDER_AND_TRACE_SF_qdqqq(
        WPP_GLOBAL_Control->AttachedDevice,
        v13,
        v15,
        a1[84],
        3,
        10,
        19,
        (__int64)WPP_7dfbfdf723c8332f637dd0f8a651f634_Traceguids,
        *(_QWORD *)(*(_QWORD *)(a2 + 64) + 32LL),
        *(_DWORD *)(a2 + 8),
        *(_QWORD *)(a2 + 48),
        a3,
        (char)P);
    }
    if ( CollectionDesc )
    {
      v16 = *CollectionDesc;
      v17 = CollectionDesc[1];
    }
    else
    {
      v16 = 0;
      v17 = 0;
    }
    MicrosoftTelemetryAssertTriggeredArgsMsgKM(
      v17,
      (unsigned int)v17 | (v16 << 16),
      *((unsigned __int16 *)a1 + 55) | (*((unsigned __int16 *)a1 + 54) << 16),
      "Received IOCTL_HID_DEVICERESET_NOTIFICATION with a cancel routine.");
    if ( !_InterlockedExchange64((volatile __int64 *)(a3 + 104), (__int64)P) )
    {
      v11 = 259;
      v19 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || !_bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 9u)
        || BYTE1(WPP_GLOBAL_Control->Timer) < 3u )
      {
        v8 = 0;
      }
      LOBYTE(v10) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      if ( !v8 && WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        goto LABEL_115;
      v20 = *(_QWORD *)(a2 + 64);
      LODWORD(v48) = 259;
      v47 = a3;
      v46 = *(_QWORD *)(a2 + 48);
      v45 = *(_DWORD *)(a2 + 8);
      v44 = *(_QWORD *)(v20 + 32);
      v42 = 20;
      RemlockSizea = 3;
      goto LABEL_39;
    }
    v11 = -1073741811;
    LOBYTE(v18) = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
               && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 9u)
               && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u;
    if ( (_BYTE)v18 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v10) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      WPP_RECORDER_AND_TRACE_SF_qdqqdq(
        WPP_GLOBAL_Control->AttachedDevice,
        v18,
        v10,
        a1[84],
        RemlockSize,
        v41,
        21,
        v43,
        *(_QWORD *)(*(_QWORD *)(a2 + 64) + 32LL),
        *(_DWORD *)(a2 + 8),
        *(_QWORD *)(a2 + 48),
        a3,
        13,
        (char)P);
    }
    goto LABEL_96;
  }
  if ( *(_BYTE *)(a3 + 68) )
  {
    if ( !_InterlockedExchange64((volatile __int64 *)(a3 + 104), 0) )
    {
      v11 = 259;
      v19 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || !_bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 9u)
        || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
      {
        v8 = 0;
      }
      LOBYTE(v10) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      if ( !v8 && WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        goto LABEL_115;
      v20 = *(_QWORD *)(a2 + 64);
      LODWORD(v48) = 259;
      v47 = a3;
      v46 = *(_QWORD *)(a2 + 48);
      v45 = *(_DWORD *)(a2 + 8);
      v44 = *(_QWORD *)(v20 + 32);
      v42 = 22;
      RemlockSizea = 4;
      goto LABEL_39;
    }
    v11 = -1073741536;
    LOBYTE(v12) = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
               && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 9u)
               && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u;
    if ( (_BYTE)v12 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v10) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      WPP_RECORDER_AND_TRACE_SF_qdqqd(
        WPP_GLOBAL_Control->AttachedDevice,
        (_DWORD)v12,
        v10,
        a1[84],
        4,
        10,
        23,
        (__int64)WPP_7dfbfdf723c8332f637dd0f8a651f634_Traceguids,
        *(_QWORD *)(*(_QWORD *)(a2 + 64) + 32LL),
        *(_DWORD *)(a2 + 8),
        *(_QWORD *)(a2 + 48),
        a3,
        -1073741536);
    }
LABEL_96:
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || !_bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 9u)
      || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
    {
      v8 = 0;
    }
    if ( v8 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v27 = *(_QWORD *)(a2 + 64);
      v28 = *(_QWORD *)(v27 + 32);
      LOBYTE(v27) = v8;
      LOBYTE(v10) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      WPP_RECORDER_AND_TRACE_SF_qdqq(
        WPP_GLOBAL_Control->AttachedDevice,
        v27,
        v10,
        a1[84],
        2,
        10,
        28,
        (__int64)WPP_7dfbfdf723c8332f637dd0f8a651f634_Traceguids,
        v28,
        *(_DWORD *)(a2 + 8),
        *(_QWORD *)(a2 + 48),
        a3);
    }
    v29 = *(_QWORD *)(a3 + 168);
    if ( *(_QWORD *)(v29 + 8) == a3 + 168 )
    {
      v30 = *(_QWORD **)(a3 + 176);
      if ( *v30 == a3 + 168 )
      {
        *v30 = v29;
        *(_QWORD *)(v29 + 8) = v30;
        goto LABEL_115;
      }
    }
LABEL_117:
    __fastfail(3u);
  }
  if ( *((_BYTE *)a1 + 1888) != 1 || a1[242] )
  {
    v11 = 259;
    goto LABEL_115;
  }
  Pa = (IRP **)ExAllocatePool2(64, 24, 1130654024);
  if ( !Pa )
  {
    v11 = 0;
    v19 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || !_bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 9u)
      || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
    {
      v8 = 0;
    }
    LOBYTE(v10) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    if ( !v8 && WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      goto LABEL_115;
    v20 = *(_QWORD *)(a2 + 64);
    LODWORD(v48) = 0;
    v47 = a3;
    v46 = *(_QWORD *)(a2 + 48);
    v45 = *(_DWORD *)(a2 + 8);
    v44 = *(_QWORD *)(v20 + 32);
    v42 = 24;
    RemlockSizea = 2;
LABEL_39:
    LOBYTE(v20) = v8;
    WPP_RECORDER_AND_TRACE_SF_qdqqd(
      v19->AttachedDevice,
      v20,
      v10,
      a1[84],
      RemlockSizea,
      10,
      v42,
      (__int64)WPP_7dfbfdf723c8332f637dd0f8a651f634_Traceguids,
      v44,
      v45,
      v46,
      v47,
      v48);
LABEL_115:
    KeReleaseSpinLock(SpinLock, NewIrql);
    return (unsigned int)v11;
  }
  Irp = IoAllocateIrp(*(_BYTE *)(*a1 + 76LL) - 1, 0);
  v24 = Irp;
  if ( !Irp )
  {
    v11 = -1073741670;
    LOBYTE(v22) = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
               && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 9u)
               && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u;
    LOBYTE(v23) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    if ( (_BYTE)v22 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_AND_TRACE_SF_qdqqd(
        WPP_GLOBAL_Control->AttachedDevice,
        v22,
        v23,
        a1[84],
        2,
        10,
        25,
        (__int64)WPP_7dfbfdf723c8332f637dd0f8a651f634_Traceguids,
        *(_QWORD *)(*(_QWORD *)(a2 + 64) + 32LL),
        *(_DWORD *)(a2 + 8),
        *(_QWORD *)(a2 + 48),
        a3,
        -1073741670);
    TraceLoggingIoAllocateIrpFailed((unsigned int)(*(char *)(*a1 + 76LL) - 1), v22, v23);
LABEL_95:
    ExFreePoolWithTag(Pa, 0);
    goto LABEL_96;
  }
  v11 = IoAcquireRemoveLockEx((PIO_REMOVE_LOCK)a1 + 20, Irp, File, 1u, 0x20u);
  if ( v11 < 0 )
  {
    LOBYTE(v25) = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
               && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 9u)
               && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u;
    if ( (_BYTE)v25 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v26) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      WPP_RECORDER_AND_TRACE_SF_qdqqdq(
        WPP_GLOBAL_Control->AttachedDevice,
        v25,
        v26,
        a1[84],
        RemlockSizeb,
        v41,
        26,
        v43,
        *(_QWORD *)(*(_QWORD *)(a2 + 64) + 32LL),
        *(_DWORD *)(a2 + 8),
        *(_QWORD *)(a2 + 48),
        a3,
        v11,
        a1[241]);
    }
    IoFreeIrp(v24);
    goto LABEL_95;
  }
  CurrentStackLocation = v24->Tail.Overlay.CurrentStackLocation;
  CurrentStackLocation[-1].MajorFunction = 15;
  CurrentStackLocation[-1].Parameters.Read.ByteOffset.LowPart = 721459;
  *Pa = v24;
  Pa[2] = (IRP *)a1;
  *((_DWORD *)Pa + 2) = 0;
  v32 = v24->Tail.Overlay.CurrentStackLocation;
  v32[-1].CompletionRoutine = (int (__fastcall *)(_DEVICE_OBJECT *, _IRP *, void *))HidpFdoDeviceResetNotificationCompletion;
  v32[-1].Context = Pa;
  v32[-1].Control = -32;
  a1[242] = Pa;
  KeReleaseSpinLock(a1 + 237, NewIrql);
  v34 = HidpCallDriver(*a1, v24);
  if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    || !_bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 9u)
    || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
  {
    v8 = 0;
  }
  if ( v8 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    v35 = *(_QWORD *)(a2 + 64);
    v36 = *(_QWORD *)(v35 + 32);
    LOBYTE(v35) = v8;
    LOBYTE(v33) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    WPP_RECORDER_AND_TRACE_SF_qdqqd(
      WPP_GLOBAL_Control->AttachedDevice,
      v35,
      v33,
      a1[84],
      4,
      10,
      27,
      (__int64)WPP_7dfbfdf723c8332f637dd0f8a651f634_Traceguids,
      v36,
      *(_DWORD *)(a2 + 8),
      *(_QWORD *)(a2 + 48),
      (char)v24,
      v34);
  }
  return 259;
}

```

## disassembly

```asm
0x180025f64  push    rbx
0x180025f66  push    rbp
0x180025f67  push    rsi
0x180025f68  push    rdi
0x180025f69  push    r12
0x180025f6b  push    r13
0x180025f6d  push    r14
0x180025f6f  push    r15
0x180025f71  sub     rsp, 88h
0x180025f78  lea     rax, [rcx+768h]
0x180025f7f  mov     rdi, rcx
0x180025f82  mov     rcx, rax; SpinLock
0x180025f85  mov     [rsp+0C8h+SpinLock], rax
0x180025f8a  mov     rsi, r9
0x180025f8d  mov     r12, r8
0x180025f90  mov     rbp, rdx
0x180025f93  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x180025f9a  nop     dword ptr [rax+rax+00h]
0x180025f9f  mov     ebx, 1
0x180025fa4  mov     [rsp+0C8h+NewIrql], al
0x180025fab  cmp     [rdi+770h], bl
0x180025fb1  jnz     loc_18002605E
0x180025fb7  mov     esi, 0C0000001h
0x180025fbc  mov     rcx, cs:WPP_GLOBAL_Control
0x180025fc3  lea     r15, WPP_GLOBAL_Control
0x180025fca  cmp     rcx, r15
0x180025fcd  jz      short loc_180025FDC
0x180025fcf  bt      dword ptr [rcx+2Ch], 9
0x180025fd4  jnb     short loc_180025FDC
0x180025fd6  cmp     byte ptr [rcx+29h], 3
0x180025fda  jnb     short loc_180025FDE
0x180025fdc  xor     bl, bl
0x180025fde  lea     rax, WPP_RECORDER_INITIALIZED
0x180025fe5  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x180025fec  setnz   r8b
0x180025ff0  test    bl, bl
0x180025ff2  jnz     short loc_180025FF9
0x180025ff4  test    r8b, r8b
0x180025ff7  jz      short loc_180026051
0x180025ff9  mov     rax, [rbp+30h]
0x180025ffd  mov     dl, bl
0x180025fff  mov     r9, [rbp+40h]
0x180026003  mov     rcx, [rcx+18h]
0x180026007  mov     dword ptr [rsp+0C8h+var_68], esi
0x18002600b  mov     [rsp+0C8h+var_70], r12
0x180026010  mov     [rsp+0C8h+var_78], rax
0x180026015  mov     eax, [rbp+8]
0x180026018  mov     [rsp+0C8h+var_80], eax
0x18002601c  mov     rax, [r9+20h]
0x180026020  mov     r9, [rdi+2A0h]
0x180026027  mov     [rsp+0C8h+var_88], rax
0x18002602c  lea     rax, WPP_7dfbfdf723c8332f637dd0f8a651f634_Traceguids
0x180026033  mov     [rsp+0C8h+var_90], rax
0x180026038  mov     [rsp+0C8h+var_98], 11h
0x18002603f  mov     [rsp+0C8h+var_A0], 0Ah
0x180026047  mov     byte ptr [rsp+0C8h+RemlockSize], 3
0x18002604c  call    WPP_RECORDER_AND_TRACE_SF_qdqqd
0x180026051  mov     rcx, rdi
0x180026054  call    TraceLoggingDeviceResetNotificationFailed
0x180026059  jmp     loc_18002689A
0x18002605e  mov     rcx, cs:WPP_GLOBAL_Control
0x180026065  lea     r15, WPP_GLOBAL_Control
0x18002606c  cmp     rcx, r15
0x18002606f  jz      short loc_180026082
0x180026071  bt      dword ptr [rcx+2Ch], 9
0x180026076  jnb     short loc_180026082
0x180026078  cmp     byte ptr [rcx+29h], 4
0x18002607c  jb      short loc_180026082
0x18002607e  mov     dl, bl
0x180026080  jmp     short loc_180026084
0x180026082  xor     dl, dl
0x180026084  lea     r13, WPP_RECORDER_INITIALIZED
0x18002608b  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x180026092  lea     r10, WPP_7dfbfdf723c8332f637dd0f8a651f634_Traceguids
0x180026099  setnz   r8b
0x18002609d  test    dl, dl
0x18002609f  jnz     short loc_1800260A6
0x1800260a1  test    r8b, r8b
0x1800260a4  jz      short loc_1800260F8
0x1800260a6  mov     rax, [rbp+30h]
0x1800260aa  mov     r9, [rbp+40h]
0x1800260ae  mov     rcx, [rcx+18h]
0x1800260b2  mov     [rsp+0C8h+var_70], r12
0x1800260b7  mov     [rsp+0C8h+var_78], rax
0x1800260bc  mov     eax, [rbp+8]
0x1800260bf  mov     [rsp+0C8h+var_80], eax
0x1800260c3  mov     rax, [r9+20h]
0x1800260c7  mov     r9, [rdi+2A0h]
0x1800260ce  mov     [rsp+0C8h+var_88], rax
0x1800260d3  mov     [rsp+0C8h+var_90], r10
0x1800260d8  mov     [rsp+0C8h+var_98], 12h
0x1800260df  mov     [rsp+0C8h+var_A0], 0Ah
0x1800260e7  mov     byte ptr [rsp+0C8h+RemlockSize], 4
0x1800260ec  call    WPP_RECORDER_AND_TRACE_SF_qdqq
0x1800260f1  lea     r10, WPP_7dfbfdf723c8332f637dd0f8a651f634_Traceguids
0x1800260f8  mov     rax, [r12+0B8h]
0x180026100  lea     rcx, [rdi+778h]
0x180026107  or      [rax+3], bl
0x18002610a  mov     [rsi], bl
0x18002610c  mov     [r12+78h], rbp
0x180026111  mov     rdx, [rcx+8]
0x180026115  cmp     [rdx], rcx
0x180026118  jnz     loc_1800268C9
0x18002611e  lea     rax, [r12+0A8h]
0x180026126  mov     [rax], rcx
0x180026129  mov     [rax+8], rdx
0x18002612d  mov     [rdx], rax
0x180026130  mov     [rcx+8], rax
0x180026134  lea     rax, HidpPdoDeviceResetNotificationCancelRoutine
0x18002613b  xchg    rax, [r12+68h]
0x180026140  mov     [rsp+0C8h+P], rax
0x180026145  test    rax, rax
0x180026148  jz      loc_18002634E
0x18002614e  mov     edx, [rbp+8]
0x180026151  mov     rcx, rdi
0x180026154  call    GetCollectionDesc
0x180026159  mov     rsi, rax
0x18002615c  mov     r10, cs:WPP_GLOBAL_Control
0x180026163  cmp     r10, r15
0x180026166  jz      short loc_18002617B
0x180026168  bt      dword ptr [r10+2Ch], 9
0x18002616e  jnb     short loc_18002617B
0x180026170  cmp     byte ptr [r10+29h], 3
0x180026175  jb      short loc_18002617B
0x180026177  mov     dl, bl
0x180026179  jmp     short loc_18002617D
0x18002617b  xor     dl, dl
0x18002617d  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x180026184  setnz   r8b
0x180026188  test    dl, dl
0x18002618a  jnz     short loc_180026191
0x18002618c  test    r8b, r8b
0x18002618f  jz      short loc_1800261ED
0x180026191  mov     r9, [rbp+40h]
0x180026195  mov     rax, [rsp+0C8h+P]
0x18002619a  mov     rcx, [r10+18h]
0x18002619e  mov     [rsp+0C8h+var_68], rax
0x1800261a3  mov     rax, [rbp+30h]
0x1800261a7  mov     [rsp+0C8h+var_70], r12
0x1800261ac  mov     [rsp+0C8h+var_78], rax
0x1800261b1  mov     eax, [rbp+8]
0x1800261b4  mov     [rsp+0C8h+var_80], eax
0x1800261b8  mov     rax, [r9+20h]
0x1800261bc  mov     r9, [rdi+2A0h]
0x1800261c3  mov     [rsp+0C8h+var_88], rax
0x1800261c8  lea     rax, WPP_7dfbfdf723c8332f637dd0f8a651f634_Traceguids
0x1800261cf  mov     [rsp+0C8h+var_90], rax
0x1800261d4  mov     [rsp+0C8h+var_98], 13h
0x1800261db  mov     [rsp+0C8h+var_A0], 0Ah
0x1800261e3  mov     byte ptr [rsp+0C8h+RemlockSize], 3
0x1800261e8  call    WPP_RECORDER_AND_TRACE_SF_qdqqq
0x1800261ed  test    rsi, rsi; __annotation("Debug", "TelemetryAssert", "FALSE", "Received IOCTL_HID_DEVICERESET_NOTIFICATION with a cancel routine.")
0x1800261f0  jz      short loc_1800261FB
0x1800261f2  movzx   edx, word ptr [rsi]
0x1800261f5  movzx   ecx, word ptr [rsi+2]
0x1800261f9  jmp     short loc_1800261FF
0x1800261fb  xor     edx, edx
0x1800261fd  xor     ecx, ecx
0x1800261ff  movzx   r8d, word ptr [rdi+6Ch]
0x180026204  lea     r9, aReceivedIoctlH; "Received IOCTL_HID_DEVICERESET_NOTIFICA"...
0x18002620b  movzx   eax, word ptr [rdi+6Eh]
0x18002620f  shl     r8d, 10h
0x180026213  shl     edx, 10h
0x180026216  or      r8d, eax
0x180026219  or      edx, ecx
0x18002621b  call    MicrosoftTelemetryAssertTriggeredArgsMsgKM
0x180026220  mov     r10, [rsp+0C8h+P]
0x180026225  mov     rax, r10
0x180026228  xchg    rax, [r12+68h]
0x18002622d  test    rax, rax
0x180026230  jnz     loc_1800262CB
0x180026236  mov     esi, 103h
0x18002623b  mov     rcx, cs:WPP_GLOBAL_Control
0x180026242  cmp     rcx, r15
0x180026245  jz      short loc_180026254
0x180026247  bt      dword ptr [rcx+2Ch], 9
0x18002624c  jnb     short loc_180026254
0x18002624e  cmp     byte ptr [rcx+29h], 3
0x180026252  jnb     short loc_180026256
0x180026254  xor     bl, bl
0x180026256  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x18002625d  setnz   r8b
0x180026261  test    bl, bl
0x180026263  jnz     short loc_18002626E
0x180026265  test    r8b, r8b
0x180026268  jz      loc_18002689A
0x18002626e  mov     rax, [rbp+30h]
0x180026272  mov     rdx, [rbp+40h]
0x180026276  mov     dword ptr [rsp+0C8h+var_68], esi
0x18002627a  mov     [rsp+0C8h+var_70], r12
0x18002627f  mov     [rsp+0C8h+var_78], rax
0x180026284  mov     eax, [rbp+8]
0x180026287  mov     [rsp+0C8h+var_80], eax
0x18002628b  mov     rax, [rdx+20h]
0x18002628f  mov     [rsp+0C8h+var_88], rax
0x180026294  lea     rax, WPP_7dfbfdf723c8332f637dd0f8a651f634_Traceguids
0x18002629b  mov     [rsp+0C8h+var_90], rax
0x1800262a0  mov     [rsp+0C8h+var_98], 14h
0x1800262a7  mov     [rsp+0C8h+var_A0], 0Ah
0x1800262af  mov     byte ptr [rsp+0C8h+RemlockSize], 3
0x1800262b4  mov     r9, [rdi+2A0h]
0x1800262bb  mov     dl, bl
0x1800262bd  mov     rcx, [rcx+18h]
0x1800262c1  call    WPP_RECORDER_AND_TRACE_SF_qdqqd
0x1800262c6  jmp     loc_18002689A
0x1800262cb  mov     esi, 0C000000Dh
0x1800262d0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800262d7  cmp     rcx, r15
0x1800262da  jz      short loc_1800262ED
0x1800262dc  bt      dword ptr [rcx+2Ch], 9
0x1800262e1  jnb     short loc_1800262ED
0x1800262e3  cmp     byte ptr [rcx+29h], 3
0x1800262e7  jb      short loc_1800262ED
0x1800262e9  mov     dl, bl
0x1800262eb  jmp     short loc_1800262EF
0x1800262ed  xor     dl, dl
0x1800262ef  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x1800262f6  setnz   r8b
0x1800262fa  test    dl, dl
0x1800262fc  jnz     short loc_180026307
0x1800262fe  test    r8b, r8b
0x180026301  jz      loc_1800266DE
0x180026307  mov     rax, [rbp+30h]
0x18002630b  mov     r9, [rbp+40h]
0x18002630f  mov     rcx, [rcx+18h]
0x180026313  mov     [rsp+0C8h+var_60], r10
0x180026318  mov     dword ptr [rsp+0C8h+var_68], esi
0x18002631c  mov     [rsp+0C8h+var_70], r12
0x180026321  mov     [rsp+0C8h+var_78], rax
0x180026326  mov     eax, [rbp+8]
0x180026329  mov     [rsp+0C8h+var_80], eax
0x18002632d  mov     rax, [r9+20h]
0x180026331  mov     r9, [rdi+2A0h]
0x180026338  mov     [rsp+0C8h+var_88], rax
0x18002633d  mov     [rsp+0C8h+var_98], 15h
0x180026344  call    WPP_RECORDER_AND_TRACE_SF_qdqqdq
0x180026349  jmp     loc_1800266DE
0x18002634e  cmp     byte ptr [r12+44h], 0
0x180026354  jz      loc_180026472
0x18002635a  xor     eax, eax
0x18002635c  xchg    rax, [r12+68h]
0x180026361  test    rax, rax
0x180026364  jnz     short loc_1800263E2
0x180026366  mov     esi, 103h
0x18002636b  mov     rcx, cs:WPP_GLOBAL_Control
0x180026372  cmp     rcx, r15
0x180026375  jz      short loc_180026384
0x180026377  bt      dword ptr [rcx+2Ch], 9
0x18002637c  jnb     short loc_180026384
0x18002637e  cmp     byte ptr [rcx+29h], 4
0x180026382  jnb     short loc_180026386
0x180026384  xor     bl, bl
0x180026386  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x18002638d  setnz   r8b
0x180026391  test    bl, bl
0x180026393  jnz     short loc_18002639E
0x180026395  test    r8b, r8b
0x180026398  jz      loc_18002689A
0x18002639e  mov     rax, [rbp+30h]
0x1800263a2  mov     rdx, [rbp+40h]
0x1800263a6  mov     dword ptr [rsp+0C8h+var_68], esi
0x1800263aa  mov     [rsp+0C8h+var_70], r12
0x1800263af  mov     [rsp+0C8h+var_78], rax
0x1800263b4  mov     eax, [rbp+8]
0x1800263b7  mov     [rsp+0C8h+var_80], eax
0x1800263bb  mov     rax, [rdx+20h]
0x1800263bf  mov     [rsp+0C8h+var_88], rax
0x1800263c4  mov     [rsp+0C8h+var_90], r10
0x1800263c9  mov     [rsp+0C8h+var_98], 16h
0x1800263d0  mov     [rsp+0C8h+var_A0], 0Ah
0x1800263d8  mov     byte ptr [rsp+0C8h+RemlockSize], 4
0x1800263dd  jmp     loc_1800262B4
0x1800263e2  mov     esi, 0C0000120h
0x1800263e7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800263ee  cmp     rcx, r15
0x1800263f1  jz      short loc_180026404
0x1800263f3  bt      dword ptr [rcx+2Ch], 9
0x1800263f8  jnb     short loc_180026404
0x1800263fa  cmp     byte ptr [rcx+29h], 4
0x1800263fe  jb      short loc_180026404
0x180026400  mov     dl, bl
0x180026402  jmp     short loc_180026406
0x180026404  xor     dl, dl
0x180026406  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x18002640d  setnz   r8b
0x180026411  test    dl, dl
0x180026413  jnz     short loc_18002641E
0x180026415  test    r8b, r8b
0x180026418  jz      loc_1800266DE
0x18002641e  mov     rax, [rbp+30h]
0x180026422  mov     r9, [rbp+40h]
0x180026426  mov     rcx, [rcx+18h]
0x18002642a  mov     dword ptr [rsp+0C8h+var_68], esi
0x18002642e  mov     [rsp+0C8h+var_70], r12
0x180026433  mov     [rsp+0C8h+var_78], rax
0x180026438  mov     eax, [rbp+8]
0x18002643b  mov     [rsp+0C8h+var_80], eax
0x18002643f  mov     rax, [r9+20h]
0x180026443  mov     r9, [rdi+2A0h]
0x18002644a  mov     [rsp+0C8h+var_88], rax
  ... truncated ...
```
