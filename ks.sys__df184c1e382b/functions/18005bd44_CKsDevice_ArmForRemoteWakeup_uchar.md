# CKsDevice::ArmForRemoteWakeup(uchar)

- ea: `0x18005bd44`
- end: `0x18005c2d9`
- name: `?ArmForRemoteWakeup@CKsDevice@@AEAAJE@Z`
- size: `1429`
- prototype: `__int64 __fastcall(CKsDevice *this, char)`
- caller_count: `3`
- callee_count: `9`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18003b690`
- `0x18005b610`
- `0x18005c2e0`

## callees

- `0x18000b7bc`
- `0x18000c4c8`
- `0x18000c630`
- `0x180013a88`
- `0x180019bd0`
- `0x180019cb0`
- `0x18001a000`
- `0x18003b148`
- `0x18005bd44`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x18005be02`
- `ntoskrnl!KeEnterCriticalRegion` at `0x18005be02`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x18005c276`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x18005c276`
- `ntoskrnl!KeClearEvent` at `0x18005bfc7`
- `ntoskrnl!KeClearEvent` at `0x18005bfc7`
- `ntoskrnl!IoAcquireRemoveLockEx` at `0x18005be84`
- `ntoskrnl!IoAcquireRemoveLockEx` at `0x18005be84`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x18005c0d7`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x18005c0d7`
- `ntoskrnl!IoCancelIrp` at `0x18005c1d3`
- `ntoskrnl!IoCancelIrp` at `0x18005c1d3`
- `ntoskrnl!PoRequestPowerIrp` at `0x18005c059`
- `ntoskrnl!PoRequestPowerIrp` at `0x18005c059`
- `ntoskrnl!KeSetEvent` at `0x18005c077`
- `ntoskrnl!KeSetEvent` at `0x18005c077`

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
    if ( CKsDevice::GetDeviceCapabilities(this, &v25) >= 0 )
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
0x18005bd44  push    rbx
0x18005bd46  push    rbp
0x18005bd47  push    rsi
0x18005bd48  push    rdi
0x18005bd49  push    r12
0x18005bd4b  push    r13
0x18005bd4d  push    r14
0x18005bd4f  push    r15
0x18005bd51  sub     rsp, 98h
0x18005bd58  mov     rax, cs:__security_cookie
0x18005bd5f  xor     rax, rsp
0x18005bd62  mov     [rsp+0D8h+var_58], rax
0x18005bd6a  mov     rdi, rcx
0x18005bd6d  mov     sil, dl
0x18005bd70  mov     rcx, [rcx+0E0h]; struct _DEVICE_OBJECT *
0x18005bd77  call    ?GetDeviceHeaderEx@CKsDevice@@SAPEAU_KSDEVICE_HEADER_EX@@PEAU_DEVICE_OBJECT@@@Z; CKsDevice::GetDeviceHeaderEx(_DEVICE_OBJECT *)
0x18005bd7c  mov     r14, rax
0x18005bd7f  xor     r15d, r15d
0x18005bd82  lea     r12, WPP_RECORDER_INITIALIZED
0x18005bd89  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x18005bd90  lea     rbp, WPP_50288c75019938eedd86f8b19427641e_Traceguids
0x18005bd97  lea     r13d, [r15+1]
0x18005bd9b  jz      short loc_18005BDC2
0x18005bd9d  mov     rcx, cs:WPP_GLOBAL_Control
0x18005bda4  cmp     [rcx+48h], r15w
0x18005bda9  jz      short loc_18005BDC2
0x18005bdab  mov     rcx, [rcx+40h]
0x18005bdaf  lea     r9d, [r15+49h]
0x18005bdb3  mov     r8d, r13d
0x18005bdb6  mov     qword ptr [rsp+0D8h+RemlockSize], rbp
0x18005bdbb  mov     dl, 5
0x18005bdbd  call    WPP_RECORDER_SF_
0x18005bdc2  cmp     [rdi+3D0h], r15b
0x18005bdc9  jnz     short loc_18005BE02
0x18005bdcb  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x18005bdd2  jz      short loc_18005BDFB
0x18005bdd4  mov     rcx, cs:WPP_GLOBAL_Control
0x18005bddb  cmp     [rcx+48h], r15w
0x18005bde0  jz      short loc_18005BDFB
0x18005bde2  mov     rcx, [rcx+40h]
0x18005bde6  mov     r9d, 4Ah ; 'J'
0x18005bdec  mov     r8d, r13d
0x18005bdef  mov     qword ptr [rsp+0D8h+RemlockSize], rbp
0x18005bdf4  mov     dl, 5
0x18005bdf6  call    WPP_RECORDER_SF_
0x18005bdfb  xor     eax, eax
0x18005bdfd  jmp     loc_18005C2B4
0x18005be02  call    cs:__imp_KeEnterCriticalRegion
0x18005be09  nop     dword ptr [rax+rax+00h]
0x18005be0e  mov     rax, [rdi]
0x18005be11  mov     rcx, rdi
0x18005be14  mov     rax, [rax+28h]
0x18005be18  call    _guard_dispatch_icall
0x18005be1d  cmp     [rdi+0F8h], r15b
0x18005be24  jnz     short loc_18005BE68
0x18005be26  mov     ebx, 0C0000001h
0x18005be2b  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x18005be32  jz      loc_18005C267
0x18005be38  mov     rcx, cs:WPP_GLOBAL_Control
0x18005be3f  cmp     [rcx+48h], r15w
0x18005be44  jz      loc_18005C267
0x18005be4a  mov     rcx, [rcx+40h]
0x18005be4e  mov     r9d, 4Bh ; 'K'
0x18005be54  mov     r8d, r13d
0x18005be57  mov     qword ptr [rsp+0D8h+RemlockSize], rbp
0x18005be5c  mov     dl, 5
0x18005be5e  call    WPP_RECORDER_SF_
0x18005be63  jmp     loc_18005C267
0x18005be68  mov     r9d, r13d; Line
0x18005be6b  mov     [rsp+0D8h+RemlockSize], 20h ; ' '; RemlockSize
0x18005be73  lea     r8, File; File
0x18005be7a  mov     rcx, r14; RemoveLock
0x18005be7d  lea     rdx, ?FinalCompleteWaitWake@CKsDevice@@CAXPEAU_DEVICE_OBJECT@@ET_POWER_STATE@@PEAV1@PEAU_IO_STATUS_BLOCK@@@Z; Tag
0x18005be84  call    cs:__imp_IoAcquireRemoveLockEx
0x18005be8b  nop     dword ptr [rax+rax+00h]
0x18005be90  mov     ebx, eax
0x18005be92  test    eax, eax
0x18005be94  jnz     loc_18005C233
0x18005be9a  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x18005bea1  jz      short loc_18005BEC8
0x18005bea3  mov     rcx, cs:WPP_GLOBAL_Control
0x18005beaa  cmp     [rcx+48h], r15w
0x18005beaf  jz      short loc_18005BEC8
0x18005beb1  mov     rcx, [rcx+40h]
0x18005beb5  lea     r9d, [rax+4Ch]
0x18005beb9  mov     r8d, r13d
0x18005bebc  mov     qword ptr [rsp+0D8h+RemlockSize], rbp
0x18005bec1  mov     dl, 5
0x18005bec3  call    WPP_RECORDER_SF_
0x18005bec8  neg     sil
0x18005becb  sbb     esi, esi
0x18005becd  and     esi, 4
0x18005bed0  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x18005bed7  jz      short loc_18005BF00
0x18005bed9  mov     rcx, cs:WPP_GLOBAL_Control
0x18005bee0  cmp     [rcx+48h], r15w
0x18005bee5  jz      short loc_18005BF00
0x18005bee7  mov     rcx, [rcx+40h]
0x18005beeb  mov     r9d, 4Dh ; 'M'
0x18005bef1  mov     r8d, r13d
0x18005bef4  mov     qword ptr [rsp+0D8h+RemlockSize], rbp
0x18005bef9  mov     dl, 5
0x18005befb  call    WPP_RECORDER_SF_
0x18005bf00  mov     ecx, 2
0x18005bf05  mov     eax, esi
0x18005bf07  lock cmpxchg [rdi+3D4h], ecx
0x18005bf0f  mov     ebp, eax
0x18005bf11  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x18005bf18  jz      short loc_18005BF54
0x18005bf1a  mov     rax, cs:WPP_GLOBAL_Control
0x18005bf21  cmp     [rax+48h], r15w
0x18005bf26  jz      short loc_18005BF54
0x18005bf28  lea     r9d, [rcx+4Ch]
0x18005bf2c  mov     r8d, r13d
0x18005bf2f  mov     ecx, [rdi+3D4h]
0x18005bf35  mov     dl, 5
0x18005bf37  mov     [rsp+0D8h+var_A8], ecx
0x18005bf3b  lea     rcx, WPP_50288c75019938eedd86f8b19427641e_Traceguids
0x18005bf42  mov     dword ptr [rsp+0D8h+Irp], ebp
0x18005bf46  mov     qword ptr [rsp+0D8h+RemlockSize], rcx
0x18005bf4b  mov     rcx, [rax+40h]
0x18005bf4f  call    WPP_RECORDER_SF_DD
0x18005bf54  cmp     ebp, esi
0x18005bf56  jz      short loc_18005BFA9
0x18005bf58  mov     ebx, 0C0000001h
0x18005bf5d  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x18005bf64  jz      loc_18005C0C0
0x18005bf6a  mov     rcx, cs:WPP_GLOBAL_Control
0x18005bf71  cmp     [rcx+48h], r15w
0x18005bf76  jz      loc_18005C0C0
0x18005bf7c  mov     rcx, [rcx+40h]
0x18005bf80  mov     r9d, 4Fh ; 'O'
0x18005bf86  mov     [rsp+0D8h+var_A8], esi
0x18005bf8a  mov     r8d, r13d
0x18005bf8d  mov     dword ptr [rsp+0D8h+Irp], ebp
0x18005bf91  mov     dl, 5
0x18005bf93  lea     rbp, WPP_50288c75019938eedd86f8b19427641e_Traceguids
0x18005bf9a  mov     qword ptr [rsp+0D8h+RemlockSize], rbp
0x18005bf9f  call    WPP_RECORDER_SF_DD
0x18005bfa4  jmp     loc_18005C0C7
0x18005bfa9  mov     ebx, 40h ; '@'
0x18005bfae  lea     rcx, [rsp+0D8h+var_98]; void *
0x18005bfb3  mov     r8d, ebx; Size
0x18005bfb6  xor     edx, edx; Val
0x18005bfb8  call    memset
0x18005bfbd  lea     rbp, [rdi+3F8h]
0x18005bfc4  mov     rcx, rbp; Event
0x18005bfc7  call    cs:__imp_KeClearEvent
0x18005bfce  nop     dword ptr [rax+rax+00h]
0x18005bfd3  mov     r8d, ebx; Size
0x18005bfd6  lea     rcx, [rsp+0D8h+var_98]; void *
0x18005bfdb  xor     edx, edx; Val
0x18005bfdd  call    memset
0x18005bfe2  lea     rdx, [rsp+0D8h+var_98]; struct _DEVICE_CAPABILITIES *
0x18005bfe7  mov     [rsp+0D8h+var_98.Size], bx
0x18005bfec  mov     rcx, rdi; this
0x18005bfef  call    ?GetDeviceCapabilities@CKsDevice@@AEAAJPEAU_DEVICE_CAPABILITIES@@@Z; CKsDevice::GetDeviceCapabilities(_DEVICE_CAPABILITIES *)
0x18005bff4  test    eax, eax
0x18005bff6  mov     ebx, r15d
0x18005bff9  cmovns  ebx, [rsp+0D8h+var_98.SystemWake]
0x18005bffe  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x18005c005  jz      short loc_18005C035
0x18005c007  mov     rcx, cs:WPP_GLOBAL_Control
0x18005c00e  cmp     [rcx+48h], r15w
0x18005c013  jz      short loc_18005C035
0x18005c015  mov     rcx, [rcx+40h]
0x18005c019  lea     rax, WPP_50288c75019938eedd86f8b19427641e_Traceguids
0x18005c020  mov     r9d, 50h ; 'P'
0x18005c026  mov     qword ptr [rsp+0D8h+RemlockSize], rax
0x18005c02b  mov     r8d, r13d
0x18005c02e  mov     dl, 5
0x18005c030  call    WPP_RECORDER_SF_
0x18005c035  mov     rcx, [rdi+0E8h]; DeviceObject
0x18005c03c  lea     rsi, [rdi+3C8h]
0x18005c043  mov     [rsp+0D8h+Irp], rsi; Irp
0x18005c048  lea     r9, ?FinalCompleteWaitWake@CKsDevice@@CAXPEAU_DEVICE_OBJECT@@ET_POWER_STATE@@PEAV1@PEAU_IO_STATUS_BLOCK@@@Z; CompletionFunction
0x18005c04f  mov     r8d, ebx; PowerState
0x18005c052  mov     qword ptr [rsp+0D8h+RemlockSize], rdi; Context
0x18005c057  xor     edx, edx; MinorFunction
0x18005c059  call    cs:__imp_PoRequestPowerIrp
0x18005c060  nop     dword ptr [rax+rax+00h]
0x18005c065  mov     ebx, eax
0x18005c067  test    eax, eax
0x18005c069  jns     loc_18005C11A
0x18005c06f  xor     r8d, r8d; Wait
0x18005c072  xor     edx, edx; Increment
0x18005c074  mov     rcx, rbp; Event
0x18005c077  call    cs:__imp_KeSetEvent
0x18005c07e  nop     dword ptr [rax+rax+00h]
0x18005c083  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x18005c08a  jz      short loc_18005C0C0
0x18005c08c  mov     rcx, cs:WPP_GLOBAL_Control
0x18005c093  lea     rbp, WPP_50288c75019938eedd86f8b19427641e_Traceguids
0x18005c09a  cmp     [rcx+48h], r15w
0x18005c09f  jz      short loc_18005C0C7
0x18005c0a1  mov     rcx, [rcx+40h]
0x18005c0a5  mov     r9d, 51h ; 'Q'
0x18005c0ab  mov     dword ptr [rsp+0D8h+Irp], ebx
0x18005c0af  mov     r8d, r13d
0x18005c0b2  mov     dl, 5
0x18005c0b4  mov     qword ptr [rsp+0D8h+RemlockSize], rbp
0x18005c0b9  call    WPP_RECORDER_SF_D
0x18005c0be  jmp     short loc_18005C0C7
0x18005c0c0  lea     rbp, WPP_50288c75019938eedd86f8b19427641e_Traceguids
0x18005c0c7  mov     r8d, 20h ; ' '; RemlockSize
0x18005c0cd  lea     rdx, ?FinalCompleteWaitWake@CKsDevice@@CAXPEAU_DEVICE_OBJECT@@ET_POWER_STATE@@PEAV1@PEAU_IO_STATUS_BLOCK@@@Z; Tag
0x18005c0d4  mov     rcx, r14; RemoveLock
0x18005c0d7  call    cs:__imp_IoReleaseRemoveLockEx
0x18005c0de  nop     dword ptr [rax+rax+00h]
0x18005c0e3  mov     eax, r15d
0x18005c0e6  xchg    eax, [rdi+3D4h]
0x18005c0ec  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x18005c0f3  jz      loc_18005C267
0x18005c0f9  mov     rcx, cs:WPP_GLOBAL_Control
0x18005c100  cmp     [rcx+48h], r15w
0x18005c105  jz      loc_18005C267
0x18005c10b  mov     r9d, 57h ; 'W'
0x18005c111  mov     dword ptr [rsp+0D8h+Irp], ebx
0x18005c115  jmp     loc_18005C254
0x18005c11a  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x18005c121  lea     rbp, WPP_50288c75019938eedd86f8b19427641e_Traceguids
0x18005c128  jz      short loc_18005C151
0x18005c12a  mov     rcx, cs:WPP_GLOBAL_Control
0x18005c131  cmp     [rcx+48h], r15w
0x18005c136  jz      short loc_18005C151
0x18005c138  mov     rcx, [rcx+40h]
0x18005c13c  mov     r9d, 52h ; 'R'
0x18005c142  mov     r8d, r13d
0x18005c145  mov     qword ptr [rsp+0D8h+RemlockSize], rbp
0x18005c14a  mov     dl, 5
0x18005c14c  call    WPP_RECORDER_SF_
0x18005c151  mov     ecx, 3
0x18005c156  lea     eax, [rcx-1]
0x18005c159  lock cmpxchg [rdi+3D4h], ecx
0x18005c161  mov     ebx, eax
0x18005c163  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x18005c16a  jz      short loc_18005C193
0x18005c16c  mov     rcx, cs:WPP_GLOBAL_Control
0x18005c173  cmp     [rcx+48h], r15w
0x18005c178  jz      short loc_18005C193
0x18005c17a  mov     rcx, [rcx+40h]
0x18005c17e  mov     r9d, 53h ; 'S'
0x18005c184  mov     r8d, r13d
0x18005c187  mov     qword ptr [rsp+0D8h+RemlockSize], rbp
0x18005c18c  mov     dl, 5
0x18005c18e  call    WPP_RECORDER_SF_
0x18005c193  cmp     ebx, 2
0x18005c196  jz      short loc_18005C1FE
0x18005c198  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x18005c19f  jz      short loc_18005C1C8
0x18005c1a1  mov     rcx, cs:WPP_GLOBAL_Control
0x18005c1a8  cmp     [rcx+48h], r15w
0x18005c1ad  jz      short loc_18005C1C8
0x18005c1af  mov     rcx, [rcx+40h]
0x18005c1b3  mov     r9d, 54h ; 'T'
0x18005c1b9  mov     r8d, r13d
0x18005c1bc  mov     qword ptr [rsp+0D8h+RemlockSize], rbp
0x18005c1c1  mov     dl, 5
0x18005c1c3  call    WPP_RECORDER_SF_
0x18005c1c8  mov     rcx, r15
0x18005c1cb  xchg    rcx, [rsi]; Irp
0x18005c1ce  test    rcx, rcx
0x18005c1d1  jz      short loc_18005C22E
0x18005c1d3  call    cs:__imp_IoCancelIrp
0x18005c1da  nop     dword ptr [rax+rax+00h]
0x18005c1df  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x18005c1e6  jz      short loc_18005C22E
0x18005c1e8  mov     rcx, cs:WPP_GLOBAL_Control
0x18005c1ef  cmp     [rcx+48h], r15w
0x18005c1f4  jz      short loc_18005C22E
0x18005c1f6  mov     r9d, 55h ; 'U'
0x18005c1fc  jmp     short loc_18005C21B
0x18005c1fe  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x18005c205  jz      short loc_18005C22E
0x18005c207  mov     rcx, cs:WPP_GLOBAL_Control
0x18005c20e  cmp     [rcx+48h], r15w
0x18005c213  jz      short loc_18005C22E
0x18005c215  mov     r9d, 56h ; 'V'
0x18005c21b  mov     rcx, [rcx+40h]
0x18005c21f  mov     r8d, r13d
0x18005c222  mov     dl, 5
0x18005c224  mov     qword ptr [rsp+0D8h+RemlockSize], rbp
0x18005c229  call    WPP_RECORDER_SF_
0x18005c22e  mov     ebx, r15d
0x18005c231  jmp     short loc_18005C267
0x18005c233  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x18005c23a  jz      short loc_18005C267
0x18005c23c  mov     rcx, cs:WPP_GLOBAL_Control
0x18005c243  cmp     [rcx+48h], r15w
0x18005c248  jz      short loc_18005C267
0x18005c24a  mov     r9d, 58h ; 'X'
0x18005c250  mov     dword ptr [rsp+0D8h+Irp], eax
0x18005c254  mov     rcx, [rcx+40h]
0x18005c258  mov     r8d, r13d
0x18005c25b  mov     dl, 5
0x18005c25d  mov     qword ptr [rsp+0D8h+RemlockSize], rbp
0x18005c262  call    WPP_RECORDER_SF_D
0x18005c267  mov     rax, [rdi]
0x18005c26a  mov     rcx, rdi
0x18005c26d  mov     rax, [rax+30h]
  ... truncated ...
```
