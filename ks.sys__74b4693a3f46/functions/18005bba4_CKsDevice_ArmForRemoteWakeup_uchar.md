# CKsDevice::ArmForRemoteWakeup(uchar)

- ea: `0x18005bba4`
- end: `0x18005c139`
- name: `?ArmForRemoteWakeup@CKsDevice@@AEAAJE@Z`
- size: `1429`
- prototype: `__int64 __fastcall(CKsDevice *__hidden this, unsigned __int8)`
- caller_count: `3`
- callee_count: `9`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18003b6a0`
- `0x18005b470`
- `0x18005c140`

## callees

- `0x18000b7bc`
- `0x18000c4c8`
- `0x18000c630`
- `0x180013a88`
- `0x180019b80`
- `0x180019c60`
- `0x180019fc0`
- `0x18003b158`
- `0x18005bba4`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x18005bc62`
- `ntoskrnl!KeEnterCriticalRegion` at `0x18005bc62`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x18005c0d6`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x18005c0d6`
- `ntoskrnl!IoAcquireRemoveLockEx` at `0x18005bce4`
- `ntoskrnl!IoAcquireRemoveLockEx` at `0x18005bce4`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x18005bf37`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x18005bf37`
- `ntoskrnl!IoCancelIrp` at `0x18005c033`
- `ntoskrnl!IoCancelIrp` at `0x18005c033`
- `ntoskrnl!PoRequestPowerIrp` at `0x18005beb9`
- `ntoskrnl!PoRequestPowerIrp` at `0x18005beb9`
- `ntoskrnl!KeSetEvent` at `0x18005bed7`
- `ntoskrnl!KeSetEvent` at `0x18005bed7`
- `ntoskrnl!KeClearEvent` at `0x18005be27`
- `ntoskrnl!KeClearEvent` at `0x18005be27`

## pseudocode

```c
__int64 __fastcall CKsDevice::ArmForRemoteWakeup(CKsDevice *this, char a2)
{
  int v4; // edx
  struct _KSDEVICE_HEADER_EX *DeviceHeader; // r14
  int v7; // edx
  NTSTATUS v8; // ebx
  NTSTATUS v9; // eax
  int v10; // edx
  int v11; // esi
  signed __int32 v12; // ebp
  int v13; // edx
  SYSTEM_POWER_STATE SystemWake; // ebx
  int v15; // edx
  int v16; // edx
  PDEVICE_OBJECT v17; // rcx
  int v18; // r9d
  signed __int32 v19; // ebx
  IRP *v20; // rcx
  PDEVICE_OBJECT v21; // rcx
  int v22; // r9d
  int v23; // edx
  PIRP *Irp; // [rsp+28h] [rbp-B0h]
  struct _DEVICE_CAPABILITIES v25; // [rsp+40h] [rbp-98h] BYREF

  DeviceHeader = CKsDevice::GetDeviceHeaderEx(this->m_Ext.Public.FunctionalDeviceObject);
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
  {
    LOBYTE(v4) = 5;
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      v4,
      1,
      73,
      (__int64)WPP_50288c75019938eedd86f8b19427641e_Traceguids);
  }
  if ( !this->m_RemoteWakeup )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      if ( LOWORD(WPP_GLOBAL_Control->DeviceType) )
      {
        LOBYTE(v4) = 5;
        WPP_RECORDER_SF_(
          WPP_GLOBAL_Control->DeviceExtension,
          v4,
          1,
          74,
          (__int64)WPP_50288c75019938eedd86f8b19427641e_Traceguids);
      }
    }
    return 0;
  }
  KeEnterCriticalRegion();
  this->AcquireDevice(this);
  if ( !this->m_Ext.Public.Started )
  {
    v8 = -1073741823;
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
    {
      LOBYTE(v7) = 5;
      WPP_RECORDER_SF_(
        WPP_GLOBAL_Control->DeviceExtension,
        v7,
        1,
        75,
        (__int64)WPP_50288c75019938eedd86f8b19427641e_Traceguids);
    }
    goto LABEL_62;
  }
  v9 = IoAcquireRemoveLockEx(&DeviceHeader->RemoveLock, CKsDevice::FinalCompleteWaitWake, File, 1u, 0x20u);
  v8 = v9;
  if ( !v9 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
    {
      LOBYTE(v10) = 5;
      WPP_RECORDER_SF_(
        WPP_GLOBAL_Control->DeviceExtension,
        v10,
        1,
        76,
        (__int64)WPP_50288c75019938eedd86f8b19427641e_Traceguids);
    }
    v11 = a2 != 0 ? 4 : 0;
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
    {
      LOBYTE(v10) = 5;
      WPP_RECORDER_SF_(
        WPP_GLOBAL_Control->DeviceExtension,
        v10,
        1,
        77,
        (__int64)WPP_50288c75019938eedd86f8b19427641e_Traceguids);
    }
    v12 = _InterlockedCompareExchange((volatile signed __int32 *)&this->m_WakeState, 2, v11);
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
    {
      LOBYTE(v10) = 5;
      WPP_RECORDER_SF_DD(
        WPP_GLOBAL_Control->DeviceExtension,
        v10,
        1,
        78,
        (__int64)WPP_50288c75019938eedd86f8b19427641e_Traceguids,
        v12,
        this->m_WakeState);
    }
    if ( v12 != v11 )
    {
      v8 = -1073741823;
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
      {
        LOBYTE(v10) = 5;
        WPP_RECORDER_SF_DD(
          WPP_GLOBAL_Control->DeviceExtension,
          v10,
          1,
          79,
          (__int64)WPP_50288c75019938eedd86f8b19427641e_Traceguids,
          v12,
          v11);
      }
LABEL_36:
      IoReleaseRemoveLockEx(&DeviceHeader->RemoveLock, CKsDevice::FinalCompleteWaitWake, 0x20u);
      _InterlockedExchange((volatile __int32 *)&this->m_WakeState, 0);
      if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        goto LABEL_62;
      v17 = WPP_GLOBAL_Control;
      if ( !LOWORD(WPP_GLOBAL_Control->DeviceType) )
        goto LABEL_62;
      v18 = 87;
      LODWORD(Irp) = v8;
      goto LABEL_61;
    }
    memset(&v25, 0, sizeof(v25));
    KeClearEvent(&this->m_WakeupCompletionSignal);
    memset(&v25, 0, sizeof(v25));
    v25.Size = 64;
    SystemWake = PowerSystemUnspecified;
    if ( (int)CKsDevice::GetDeviceCapabilities(this, &v25) >= 0 )
      SystemWake = v25.SystemWake;
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
    {
      LOBYTE(v13) = 5;
      WPP_RECORDER_SF_(
        WPP_GLOBAL_Control->DeviceExtension,
        v13,
        1,
        80,
        (__int64)WPP_50288c75019938eedd86f8b19427641e_Traceguids);
    }
    v8 = PoRequestPowerIrp(
           this->m_Ext.Public.PhysicalDeviceObject,
           0,
           (POWER_STATE)SystemWake,
           (PREQUEST_POWER_COMPLETE)CKsDevice::FinalCompleteWaitWake,
           this,
           &this->m_PendingWakeIrp);
    if ( v8 < 0 )
    {
      KeSetEvent(&this->m_WakeupCompletionSignal, 0, 0);
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
      {
        LODWORD(Irp) = v8;
        LOBYTE(v16) = 5;
        WPP_RECORDER_SF_D(
          WPP_GLOBAL_Control->DeviceExtension,
          v16,
          1,
          81,
          (__int64)WPP_50288c75019938eedd86f8b19427641e_Traceguids,
          Irp);
      }
      goto LABEL_36;
    }
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
    {
      LOBYTE(v15) = 5;
      WPP_RECORDER_SF_(
        WPP_GLOBAL_Control->DeviceExtension,
        v15,
        1,
        82,
        (__int64)WPP_50288c75019938eedd86f8b19427641e_Traceguids);
    }
    v19 = _InterlockedCompareExchange((volatile signed __int32 *)&this->m_WakeState, 3, 2);
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
    {
      LOBYTE(v15) = 5;
      WPP_RECORDER_SF_(
        WPP_GLOBAL_Control->DeviceExtension,
        v15,
        1,
        83,
        (__int64)WPP_50288c75019938eedd86f8b19427641e_Traceguids);
    }
    if ( v19 == 2 )
    {
      if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        goto LABEL_57;
      v21 = WPP_GLOBAL_Control;
      if ( !LOWORD(WPP_GLOBAL_Control->DeviceType) )
        goto LABEL_57;
      v22 = 86;
    }
    else
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
      {
        LOBYTE(v15) = 5;
        WPP_RECORDER_SF_(
          WPP_GLOBAL_Control->DeviceExtension,
          v15,
          1,
          84,
          (__int64)WPP_50288c75019938eedd86f8b19427641e_Traceguids);
      }
      v20 = (IRP *)_InterlockedExchange64((volatile __int64 *)&this->m_PendingWakeIrp, 0);
      if ( !v20 )
        goto LABEL_57;
      IoCancelIrp(v20);
      if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        goto LABEL_57;
      v21 = WPP_GLOBAL_Control;
      if ( !LOWORD(WPP_GLOBAL_Control->DeviceType) )
        goto LABEL_57;
      v22 = 85;
    }
    LOBYTE(v15) = 5;
    WPP_RECORDER_SF_(v21->DeviceExtension, v15, 1, v22, (__int64)WPP_50288c75019938eedd86f8b19427641e_Traceguids);
LABEL_57:
    v8 = 0;
    goto LABEL_62;
  }
  if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    goto LABEL_62;
  v17 = WPP_GLOBAL_Control;
  if ( !LOWORD(WPP_GLOBAL_Control->DeviceType) )
    goto LABEL_62;
  v18 = 88;
  LODWORD(Irp) = v9;
LABEL_61:
  LOBYTE(v10) = 5;
  WPP_RECORDER_SF_D(v17->DeviceExtension, v10, 1, v18, (__int64)WPP_50288c75019938eedd86f8b19427641e_Traceguids, Irp);
LABEL_62:
  this->ReleaseDevice(this);
  KeLeaveCriticalRegion();
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
  {
    LOBYTE(v23) = 5;
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      v23,
      1,
      89,
      (__int64)WPP_50288c75019938eedd86f8b19427641e_Traceguids);
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18005bba4  push    rbx
0x18005bba6  push    rbp
0x18005bba7  push    rsi
0x18005bba8  push    rdi
0x18005bba9  push    r12
0x18005bbab  push    r13
0x18005bbad  push    r14
0x18005bbaf  push    r15
0x18005bbb1  sub     rsp, 98h
0x18005bbb8  mov     rax, cs:__security_cookie
0x18005bbbf  xor     rax, rsp
0x18005bbc2  mov     [rsp+0D8h+var_58], rax
0x18005bbca  mov     rdi, rcx
0x18005bbcd  mov     sil, dl
0x18005bbd0  mov     rcx, [rcx+0E0h]; struct _DEVICE_OBJECT *
0x18005bbd7  call    ?GetDeviceHeaderEx@CKsDevice@@SAPEAU_KSDEVICE_HEADER_EX@@PEAU_DEVICE_OBJECT@@@Z; CKsDevice::GetDeviceHeaderEx(_DEVICE_OBJECT *)
0x18005bbdc  mov     r14, rax
0x18005bbdf  xor     r15d, r15d
0x18005bbe2  lea     r12, WPP_RECORDER_INITIALIZED
0x18005bbe9  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x18005bbf0  lea     rbp, WPP_50288c75019938eedd86f8b19427641e_Traceguids
0x18005bbf7  lea     r13d, [r15+1]
0x18005bbfb  jz      short loc_18005BC22
0x18005bbfd  mov     rcx, cs:WPP_GLOBAL_Control
0x18005bc04  cmp     [rcx+48h], r15w
0x18005bc09  jz      short loc_18005BC22
0x18005bc0b  mov     rcx, [rcx+40h]
0x18005bc0f  lea     r9d, [r15+49h]
0x18005bc13  mov     r8d, r13d
0x18005bc16  mov     qword ptr [rsp+0D8h+RemlockSize], rbp
0x18005bc1b  mov     dl, 5
0x18005bc1d  call    WPP_RECORDER_SF_
0x18005bc22  cmp     [rdi+3D0h], r15b
0x18005bc29  jnz     short loc_18005BC62
0x18005bc2b  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x18005bc32  jz      short loc_18005BC5B
0x18005bc34  mov     rcx, cs:WPP_GLOBAL_Control
0x18005bc3b  cmp     [rcx+48h], r15w
0x18005bc40  jz      short loc_18005BC5B
0x18005bc42  mov     rcx, [rcx+40h]
0x18005bc46  mov     r9d, 4Ah ; 'J'
0x18005bc4c  mov     r8d, r13d
0x18005bc4f  mov     qword ptr [rsp+0D8h+RemlockSize], rbp
0x18005bc54  mov     dl, 5
0x18005bc56  call    WPP_RECORDER_SF_
0x18005bc5b  xor     eax, eax
0x18005bc5d  jmp     loc_18005C114
0x18005bc62  call    cs:__imp_KeEnterCriticalRegion
0x18005bc69  nop     dword ptr [rax+rax+00h]
0x18005bc6e  mov     rax, [rdi]
0x18005bc71  mov     rcx, rdi
0x18005bc74  mov     rax, [rax+28h]
0x18005bc78  call    _guard_dispatch_icall
0x18005bc7d  cmp     [rdi+0F8h], r15b
0x18005bc84  jnz     short loc_18005BCC8
0x18005bc86  mov     ebx, 0C0000001h
0x18005bc8b  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x18005bc92  jz      loc_18005C0C7
0x18005bc98  mov     rcx, cs:WPP_GLOBAL_Control
0x18005bc9f  cmp     [rcx+48h], r15w
0x18005bca4  jz      loc_18005C0C7
0x18005bcaa  mov     rcx, [rcx+40h]
0x18005bcae  mov     r9d, 4Bh ; 'K'
0x18005bcb4  mov     r8d, r13d
0x18005bcb7  mov     qword ptr [rsp+0D8h+RemlockSize], rbp
0x18005bcbc  mov     dl, 5
0x18005bcbe  call    WPP_RECORDER_SF_
0x18005bcc3  jmp     loc_18005C0C7
0x18005bcc8  mov     r9d, r13d; Line
0x18005bccb  mov     [rsp+0D8h+RemlockSize], 20h ; ' '; RemlockSize
0x18005bcd3  lea     r8, File; File
0x18005bcda  mov     rcx, r14; RemoveLock
0x18005bcdd  lea     rdx, ?FinalCompleteWaitWake@CKsDevice@@CAXPEAU_DEVICE_OBJECT@@ET_POWER_STATE@@PEAV1@PEAU_IO_STATUS_BLOCK@@@Z; Tag
0x18005bce4  call    cs:__imp_IoAcquireRemoveLockEx
0x18005bceb  nop     dword ptr [rax+rax+00h]
0x18005bcf0  mov     ebx, eax
0x18005bcf2  test    eax, eax
0x18005bcf4  jnz     loc_18005C093
0x18005bcfa  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x18005bd01  jz      short loc_18005BD28
0x18005bd03  mov     rcx, cs:WPP_GLOBAL_Control
0x18005bd0a  cmp     [rcx+48h], r15w
0x18005bd0f  jz      short loc_18005BD28
0x18005bd11  mov     rcx, [rcx+40h]
0x18005bd15  lea     r9d, [rax+4Ch]
0x18005bd19  mov     r8d, r13d
0x18005bd1c  mov     qword ptr [rsp+0D8h+RemlockSize], rbp
0x18005bd21  mov     dl, 5
0x18005bd23  call    WPP_RECORDER_SF_
0x18005bd28  neg     sil
0x18005bd2b  sbb     esi, esi
0x18005bd2d  and     esi, 4
0x18005bd30  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x18005bd37  jz      short loc_18005BD60
0x18005bd39  mov     rcx, cs:WPP_GLOBAL_Control
0x18005bd40  cmp     [rcx+48h], r15w
0x18005bd45  jz      short loc_18005BD60
0x18005bd47  mov     rcx, [rcx+40h]
0x18005bd4b  mov     r9d, 4Dh ; 'M'
0x18005bd51  mov     r8d, r13d
0x18005bd54  mov     qword ptr [rsp+0D8h+RemlockSize], rbp
0x18005bd59  mov     dl, 5
0x18005bd5b  call    WPP_RECORDER_SF_
0x18005bd60  mov     ecx, 2
0x18005bd65  mov     eax, esi
0x18005bd67  lock cmpxchg [rdi+3D4h], ecx
0x18005bd6f  mov     ebp, eax
0x18005bd71  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x18005bd78  jz      short loc_18005BDB4
0x18005bd7a  mov     rax, cs:WPP_GLOBAL_Control
0x18005bd81  cmp     [rax+48h], r15w
0x18005bd86  jz      short loc_18005BDB4
0x18005bd88  lea     r9d, [rcx+4Ch]
0x18005bd8c  mov     r8d, r13d
0x18005bd8f  mov     ecx, [rdi+3D4h]
0x18005bd95  mov     dl, 5
0x18005bd97  mov     [rsp+0D8h+var_A8], ecx
0x18005bd9b  lea     rcx, WPP_50288c75019938eedd86f8b19427641e_Traceguids
0x18005bda2  mov     dword ptr [rsp+0D8h+Irp], ebp
0x18005bda6  mov     qword ptr [rsp+0D8h+RemlockSize], rcx
0x18005bdab  mov     rcx, [rax+40h]
0x18005bdaf  call    WPP_RECORDER_SF_DD
0x18005bdb4  cmp     ebp, esi
0x18005bdb6  jz      short loc_18005BE09
0x18005bdb8  mov     ebx, 0C0000001h
0x18005bdbd  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x18005bdc4  jz      loc_18005BF20
0x18005bdca  mov     rcx, cs:WPP_GLOBAL_Control
0x18005bdd1  cmp     [rcx+48h], r15w
0x18005bdd6  jz      loc_18005BF20
0x18005bddc  mov     rcx, [rcx+40h]
0x18005bde0  mov     r9d, 4Fh ; 'O'
0x18005bde6  mov     [rsp+0D8h+var_A8], esi
0x18005bdea  mov     r8d, r13d
0x18005bded  mov     dword ptr [rsp+0D8h+Irp], ebp
0x18005bdf1  mov     dl, 5
0x18005bdf3  lea     rbp, WPP_50288c75019938eedd86f8b19427641e_Traceguids
0x18005bdfa  mov     qword ptr [rsp+0D8h+RemlockSize], rbp
0x18005bdff  call    WPP_RECORDER_SF_DD
0x18005be04  jmp     loc_18005BF27
0x18005be09  mov     ebx, 40h ; '@'
0x18005be0e  lea     rcx, [rsp+0D8h+var_98]; void *
0x18005be13  mov     r8d, ebx; Size
0x18005be16  xor     edx, edx; Val
0x18005be18  call    memset
0x18005be1d  lea     rbp, [rdi+3F8h]
0x18005be24  mov     rcx, rbp; Event
0x18005be27  call    cs:__imp_KeClearEvent
0x18005be2e  nop     dword ptr [rax+rax+00h]
0x18005be33  mov     r8d, ebx; Size
0x18005be36  lea     rcx, [rsp+0D8h+var_98]; void *
0x18005be3b  xor     edx, edx; Val
0x18005be3d  call    memset
0x18005be42  lea     rdx, [rsp+0D8h+var_98]; struct _DEVICE_CAPABILITIES *
0x18005be47  mov     [rsp+0D8h+var_98.Size], bx
0x18005be4c  mov     rcx, rdi; this
0x18005be4f  call    ?GetDeviceCapabilities@CKsDevice@@AEAAJPEAU_DEVICE_CAPABILITIES@@@Z; CKsDevice::GetDeviceCapabilities(_DEVICE_CAPABILITIES *)
0x18005be54  test    eax, eax
0x18005be56  mov     ebx, r15d
0x18005be59  cmovns  ebx, [rsp+0D8h+var_98.SystemWake]
0x18005be5e  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x18005be65  jz      short loc_18005BE95
0x18005be67  mov     rcx, cs:WPP_GLOBAL_Control
0x18005be6e  cmp     [rcx+48h], r15w
0x18005be73  jz      short loc_18005BE95
0x18005be75  mov     rcx, [rcx+40h]
0x18005be79  lea     rax, WPP_50288c75019938eedd86f8b19427641e_Traceguids
0x18005be80  mov     r9d, 50h ; 'P'
0x18005be86  mov     qword ptr [rsp+0D8h+RemlockSize], rax
0x18005be8b  mov     r8d, r13d
0x18005be8e  mov     dl, 5
0x18005be90  call    WPP_RECORDER_SF_
0x18005be95  mov     rcx, [rdi+0E8h]; DeviceObject
0x18005be9c  lea     rsi, [rdi+3C8h]
0x18005bea3  mov     [rsp+0D8h+Irp], rsi; Irp
0x18005bea8  lea     r9, ?FinalCompleteWaitWake@CKsDevice@@CAXPEAU_DEVICE_OBJECT@@ET_POWER_STATE@@PEAV1@PEAU_IO_STATUS_BLOCK@@@Z; CompletionFunction
0x18005beaf  mov     r8d, ebx; PowerState
0x18005beb2  mov     qword ptr [rsp+0D8h+RemlockSize], rdi; Context
0x18005beb7  xor     edx, edx; MinorFunction
0x18005beb9  call    cs:__imp_PoRequestPowerIrp
0x18005bec0  nop     dword ptr [rax+rax+00h]
0x18005bec5  mov     ebx, eax
0x18005bec7  test    eax, eax
0x18005bec9  jns     loc_18005BF7A
0x18005becf  xor     r8d, r8d; Wait
0x18005bed2  xor     edx, edx; Increment
0x18005bed4  mov     rcx, rbp; Event
0x18005bed7  call    cs:__imp_KeSetEvent
0x18005bede  nop     dword ptr [rax+rax+00h]
0x18005bee3  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x18005beea  jz      short loc_18005BF20
0x18005beec  mov     rcx, cs:WPP_GLOBAL_Control
0x18005bef3  lea     rbp, WPP_50288c75019938eedd86f8b19427641e_Traceguids
0x18005befa  cmp     [rcx+48h], r15w
0x18005beff  jz      short loc_18005BF27
0x18005bf01  mov     rcx, [rcx+40h]
0x18005bf05  mov     r9d, 51h ; 'Q'
0x18005bf0b  mov     dword ptr [rsp+0D8h+Irp], ebx
0x18005bf0f  mov     r8d, r13d
0x18005bf12  mov     dl, 5
0x18005bf14  mov     qword ptr [rsp+0D8h+RemlockSize], rbp
0x18005bf19  call    WPP_RECORDER_SF_D
0x18005bf1e  jmp     short loc_18005BF27
0x18005bf20  lea     rbp, WPP_50288c75019938eedd86f8b19427641e_Traceguids
0x18005bf27  mov     r8d, 20h ; ' '; RemlockSize
0x18005bf2d  lea     rdx, ?FinalCompleteWaitWake@CKsDevice@@CAXPEAU_DEVICE_OBJECT@@ET_POWER_STATE@@PEAV1@PEAU_IO_STATUS_BLOCK@@@Z; Tag
0x18005bf34  mov     rcx, r14; RemoveLock
0x18005bf37  call    cs:__imp_IoReleaseRemoveLockEx
0x18005bf3e  nop     dword ptr [rax+rax+00h]
0x18005bf43  mov     eax, r15d
0x18005bf46  xchg    eax, [rdi+3D4h]
0x18005bf4c  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x18005bf53  jz      loc_18005C0C7
0x18005bf59  mov     rcx, cs:WPP_GLOBAL_Control
0x18005bf60  cmp     [rcx+48h], r15w
0x18005bf65  jz      loc_18005C0C7
0x18005bf6b  mov     r9d, 57h ; 'W'
0x18005bf71  mov     dword ptr [rsp+0D8h+Irp], ebx
0x18005bf75  jmp     loc_18005C0B4
0x18005bf7a  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x18005bf81  lea     rbp, WPP_50288c75019938eedd86f8b19427641e_Traceguids
0x18005bf88  jz      short loc_18005BFB1
0x18005bf8a  mov     rcx, cs:WPP_GLOBAL_Control
0x18005bf91  cmp     [rcx+48h], r15w
0x18005bf96  jz      short loc_18005BFB1
0x18005bf98  mov     rcx, [rcx+40h]
0x18005bf9c  mov     r9d, 52h ; 'R'
0x18005bfa2  mov     r8d, r13d
0x18005bfa5  mov     qword ptr [rsp+0D8h+RemlockSize], rbp
0x18005bfaa  mov     dl, 5
0x18005bfac  call    WPP_RECORDER_SF_
0x18005bfb1  mov     ecx, 3
0x18005bfb6  lea     eax, [rcx-1]
0x18005bfb9  lock cmpxchg [rdi+3D4h], ecx
0x18005bfc1  mov     ebx, eax
0x18005bfc3  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x18005bfca  jz      short loc_18005BFF3
0x18005bfcc  mov     rcx, cs:WPP_GLOBAL_Control
0x18005bfd3  cmp     [rcx+48h], r15w
0x18005bfd8  jz      short loc_18005BFF3
0x18005bfda  mov     rcx, [rcx+40h]
0x18005bfde  mov     r9d, 53h ; 'S'
0x18005bfe4  mov     r8d, r13d
0x18005bfe7  mov     qword ptr [rsp+0D8h+RemlockSize], rbp
0x18005bfec  mov     dl, 5
0x18005bfee  call    WPP_RECORDER_SF_
0x18005bff3  cmp     ebx, 2
0x18005bff6  jz      short loc_18005C05E
0x18005bff8  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x18005bfff  jz      short loc_18005C028
0x18005c001  mov     rcx, cs:WPP_GLOBAL_Control
0x18005c008  cmp     [rcx+48h], r15w
0x18005c00d  jz      short loc_18005C028
0x18005c00f  mov     rcx, [rcx+40h]
0x18005c013  mov     r9d, 54h ; 'T'
0x18005c019  mov     r8d, r13d
0x18005c01c  mov     qword ptr [rsp+0D8h+RemlockSize], rbp
0x18005c021  mov     dl, 5
0x18005c023  call    WPP_RECORDER_SF_
0x18005c028  mov     rcx, r15
0x18005c02b  xchg    rcx, [rsi]; Irp
0x18005c02e  test    rcx, rcx
0x18005c031  jz      short loc_18005C08E
0x18005c033  call    cs:__imp_IoCancelIrp
0x18005c03a  nop     dword ptr [rax+rax+00h]
0x18005c03f  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x18005c046  jz      short loc_18005C08E
0x18005c048  mov     rcx, cs:WPP_GLOBAL_Control
0x18005c04f  cmp     [rcx+48h], r15w
0x18005c054  jz      short loc_18005C08E
0x18005c056  mov     r9d, 55h ; 'U'
0x18005c05c  jmp     short loc_18005C07B
0x18005c05e  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x18005c065  jz      short loc_18005C08E
0x18005c067  mov     rcx, cs:WPP_GLOBAL_Control
0x18005c06e  cmp     [rcx+48h], r15w
0x18005c073  jz      short loc_18005C08E
0x18005c075  mov     r9d, 56h ; 'V'
0x18005c07b  mov     rcx, [rcx+40h]
0x18005c07f  mov     r8d, r13d
0x18005c082  mov     dl, 5
0x18005c084  mov     qword ptr [rsp+0D8h+RemlockSize], rbp
0x18005c089  call    WPP_RECORDER_SF_
0x18005c08e  mov     ebx, r15d
0x18005c091  jmp     short loc_18005C0C7
0x18005c093  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x18005c09a  jz      short loc_18005C0C7
0x18005c09c  mov     rcx, cs:WPP_GLOBAL_Control
0x18005c0a3  cmp     [rcx+48h], r15w
0x18005c0a8  jz      short loc_18005C0C7
0x18005c0aa  mov     r9d, 58h ; 'X'
0x18005c0b0  mov     dword ptr [rsp+0D8h+Irp], eax
0x18005c0b4  mov     rcx, [rcx+40h]
0x18005c0b8  mov     r8d, r13d
0x18005c0bb  mov     dl, 5
0x18005c0bd  mov     qword ptr [rsp+0D8h+RemlockSize], rbp
0x18005c0c2  call    WPP_RECORDER_SF_D
0x18005c0c7  mov     rax, [rdi]
0x18005c0ca  mov     rcx, rdi
0x18005c0cd  mov     rax, [rax+30h]
  ... truncated ...
```
