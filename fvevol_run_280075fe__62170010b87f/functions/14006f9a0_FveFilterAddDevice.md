# FveFilterAddDevice

- ea: `0x14006f9a0`
- end: `0x14006fe20`
- name: `FveFilterAddDevice`
- size: `1152`
- prototype: `__int64 __fastcall(PDRIVER_OBJECT DriverObject, PDEVICE_OBJECT TargetDevice)`
- caller_count: `0`
- callee_count: `16`
- tags: `authz_impersonation, loader_planting, service_task`

## callees

- `0x140008dc0`
- `0x140008e44`
- `0x14000a150`
- `0x14000b3ac`
- `0x14000b62c`
- `0x140021d00`
- `0x14002345c`
- `0x140026aec`
- `0x14002c140`
- `0x140050dec`
- `0x140061eb0`
- `0x14006f9a0`
- `0x140070b40`
- `0x140085180`
- `0x1400b5bc0`
- `0x1400e62e8`

## import_xrefs

- `ntoskrnl!KeInitializeEvent` at `0x14006fbea`
- `ntoskrnl!KeInitializeEvent` at `0x14006fbea`
- `ntoskrnl!KeInitializeSpinLock` at `0x14006fbbf`
- `ntoskrnl!KeInitializeSpinLock` at `0x14006fbbf`
- `ntoskrnl!MmIsThisAnNtAsSystem` at `0x14006fb2c`
- `ntoskrnl!MmIsThisAnNtAsSystem` at `0x14006fb2c`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x14006fd5c`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x14006fd5c`
- `ntoskrnl!ExFreeCacheAwareRundownProtection` at `0x14006fdaa`
- `ntoskrnl!ExFreeCacheAwareRundownProtection` at `0x14006fdaa`
- `ntoskrnl!IoDeleteDevice` at `0x14006fdbe`
- `ntoskrnl!IoDeleteDevice` at `0x14006fdbe`
- `ntoskrnl!ExSizeOfRundownProtectionCacheAware` at `0x14006fa13`
- `ntoskrnl!ExSizeOfRundownProtectionCacheAware` at `0x14006fa13`
- `ntoskrnl!IoCreateDevice` at `0x14006faad`
- `ntoskrnl!IoCreateDevice` at `0x14006faad`
- `ntoskrnl!ExInitializeRundownProtection` at `0x14006fc3d`
- `ntoskrnl!ExInitializeRundownProtection` at `0x14006fc3d`
- `ntoskrnl!ExInitializeRundownProtectionCacheAware` at `0x14006fc5a`
- `ntoskrnl!ExInitializeRundownProtectionCacheAware` at `0x14006fc5a`
- `ntoskrnl!IoAttachDeviceToDeviceStack` at `0x14006fc6d`
- `ntoskrnl!IoAttachDeviceToDeviceStack` at `0x14006fc6d`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006fd75`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006fd95`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006fd75`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006fd95`
- `ntoskrnl!IoGetDriverObjectExtension` at `0x14006fa04`
- `ntoskrnl!IoGetDriverObjectExtension` at `0x14006fa04`

## pseudocode

```c
__int64 __fastcall FveFilterAddDevice(PDRIVER_OBJECT DriverObject, PDEVICE_OBJECT TargetDevice)
{
  _QWORD *DeviceExtension; // rbx
  PVOID DriverObjectExtension; // r15
  unsigned __int64 v6; // rsi
  unsigned __int64 v7; // rdx
  NTSTATUS DcbVol; // edi
  BOOLEAN IsThisAnNtAsSystem; // al
  __int64 v10; // r8
  __int64 v11; // rdx
  PDEVICE_OBJECT v12; // rax
  __int64 v13; // rax
  struct _NPAGED_LOOKASIDE_LIST *v14; // rcx
  struct _EX_RUNDOWN_REF_CACHE_AWARE *v15; // rcx
  signed __int32 v17[8]; // [rsp+0h] [rbp-40h] BYREF
  PDEVICE_OBJECT SourceDevice; // [rsp+80h] [rbp+40h] BYREF
  __int64 v19; // [rsp+88h] [rbp+48h]

  SourceDevice = 0;
  DeviceExtension = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 154, WPP_b4b9d8ac9d1830ce077ccb64ddccb5ed_Traceguids);
  }
  DriverObjectExtension = IoGetDriverObjectExtension(DriverObject, DriverObject);
  v6 = ExSizeOfRundownProtectionCacheAware();
  v19 = *((unsigned int *)&WPP_MAIN_CB.Reserved + 2);
  if ( (*(_BYTE *)(&WPP_MAIN_CB.Reserved + 1) & 0x10) == 0 )
  {
    LODWORD(v19) = *((_DWORD *)&WPP_MAIN_CB.Reserved + 2) | 1;
    wil_details_FeatureReporting_ReportUsageToService(
      &Feature_BitLocker_Scalable_Remove_Lock__private_descriptor,
      v19,
      3);
    wil_details_FeatureStateCache_TryEnableDeviceUsageFastPath(
      v19,
      3,
      &Feature_BitLocker_Scalable_Remove_Lock__private_descriptor);
  }
  v7 = v6 + 5200;
  if ( v6 + 5200 < v6 || v7 > 0xFFFFFFFF )
  {
    DcbVol = -1073741670;
LABEL_25:
    if ( SourceDevice )
    {
      FveDisconnectVol(DeviceExtension);
      FveQueueCleanup(DeviceExtension);
      v13 = DeviceExtension[292];
      if ( v13 )
      {
        v14 = *(struct _NPAGED_LOOKASIDE_LIST **)(v13 + 8);
        if ( v14 )
        {
          ExDeleteNPagedLookasideList(v14);
          ExFreePoolWithTag(*(PVOID *)(DeviceExtension[292] + 8LL), 0x30455646u);
          *(_QWORD *)(DeviceExtension[292] + 8LL) = 0;
        }
        ExFreePoolWithTag((PVOID)DeviceExtension[292], 0x30455646u);
      }
      v15 = (struct _EX_RUNDOWN_REF_CACHE_AWARE *)DeviceExtension[13];
      if ( v15 )
      {
        ExFreeCacheAwareRundownProtection(v15);
        DeviceExtension[13] = 0;
      }
      IoDeleteDevice(SourceDevice);
      SourceDevice = 0;
    }
    goto LABEL_33;
  }
  DcbVol = IoCreateDevice(DriverObject, v7, 0, 0x22u, 0x100u, 0, &SourceDevice);
  if ( DcbVol < 0 )
    goto LABEL_25;
  DeviceExtension = SourceDevice->DeviceExtension;
  memset(DeviceExtension, 0, 0x1450u);
  *((_BYTE *)DeviceExtension + 1476) = 1;
  v19 = (unsigned int)Feature_BitLocker_Priority_From_Current_Thread__private_featureState;
  if ( (Feature_BitLocker_Priority_From_Current_Thread__private_featureState & 0x10) == 0 )
  {
    LODWORD(v19) = Feature_BitLocker_Priority_From_Current_Thread__private_featureState | 1;
    wil_details_FeatureReporting_ReportUsageToService(
      Feature_BitLocker_Priority_From_Current_Thread__private_descriptor,
      v19,
      3);
    wil_details_FeatureStateCache_TryEnableDeviceUsageFastPath(
      v19,
      3,
      Feature_BitLocker_Priority_From_Current_Thread__private_descriptor);
  }
  IsThisAnNtAsSystem = MmIsThisAnNtAsSystem();
  LOBYTE(v10) = 1;
  *((_BYTE *)DeviceExtension + 1477) = IsThisAnNtAsSystem != 0;
  DcbVol = FveInitializeRemoveLock(DeviceExtension + 7, DeviceExtension, v10);
  if ( DcbVol < 0 )
    goto LABEL_25;
  *DeviceExtension = SourceDevice;
  DeviceExtension[1] = DriverObjectExtension;
  DeviceExtension[589] = 0;
  DcbVol = FveQueueInit(DeviceExtension);
  if ( DcbVol < 0 )
    goto LABEL_25;
  v11 = TargetDevice->Flags >> 8;
  LOBYTE(v11) = BYTE1(TargetDevice->Flags) & 1;
  DcbVol = FveInit(DeviceExtension, v11);
  if ( DcbVol < 0 )
    goto LABEL_25;
  DeviceExtension[570] = DeviceExtension + 569;
  DeviceExtension[569] = DeviceExtension + 569;
  DeviceExtension[572] = DeviceExtension + 571;
  DeviceExtension[571] = DeviceExtension + 571;
  KeInitializeSpinLock(DeviceExtension + 573);
  DeviceExtension[574] = 0;
  FveLockInitialize(DeviceExtension + 575);
  KeInitializeEvent((PRKEVENT)(DeviceExtension + 586), NotificationEvent, 0);
  DeviceExtension[15] = TargetDevice;
  DcbVol = FveResolveDeviceType(DeviceExtension);
  if ( DcbVol < 0 )
    goto LABEL_25;
  DcbVol = FveCreateDcbVol(DeviceExtension);
  if ( DcbVol < 0 )
    goto LABEL_25;
  *((_DWORD *)DeviceExtension + 368) = 0;
  DeviceExtension[185] = 0;
  *((_DWORD *)DeviceExtension + 372) = 5;
  ExInitializeRundownProtection((PEX_RUNDOWN_REF)DeviceExtension + 181);
  DeviceExtension[183] = DeviceExtension + 650;
  ExInitializeRundownProtectionCacheAware((PEX_RUNDOWN_REF_CACHE_AWARE)(DeviceExtension + 650), v6);
  v12 = IoAttachDeviceToDeviceStack(SourceDevice, TargetDevice);
  DeviceExtension[14] = v12;
  if ( !v12 )
  {
    DcbVol = -1073741810;
    goto LABEL_25;
  }
  SourceDevice->DeviceType = v12->DeviceType;
  SourceDevice->Flags |= 0x10u;
  SourceDevice->Flags |= *(_DWORD *)(DeviceExtension[14] + 48LL) & 0x6000;
  SourceDevice->Characteristics |= *(_DWORD *)(DeviceExtension[14] + 52LL) & 0x5010F;
  FvePerfTraceDevPtr(DeviceExtension, FVE_PERF_VOLUME_CREATE, TargetDevice);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 155, WPP_b4b9d8ac9d1830ce077ccb64ddccb5ed_Traceguids, DeviceExtension);
  }
  _InterlockedOr(v17, 0);
  SourceDevice->Flags &= ~0x80u;
LABEL_33:
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_d(
      WPP_GLOBAL_Control->AttachedDevice,
      156,
      WPP_b4b9d8ac9d1830ce077ccb64ddccb5ed_Traceguids,
      (unsigned int)DcbVol);
  }
  return (unsigned int)DcbVol;
}

```

## disassembly

```asm
0x14006f9a0  mov     [rsp-28h+arg_0], rbx
0x14006f9a5  mov     [rsp-28h+arg_8], rsi
0x14006f9aa  push    rbp
0x14006f9ab  push    rdi
0x14006f9ac  push    r12
0x14006f9ae  push    r14
0x14006f9b0  push    r15
0x14006f9b2  mov     rbp, rsp
0x14006f9b5  sub     rsp, 40h
0x14006f9b9  xor     r12d, r12d
0x14006f9bc  mov     r14, rdx
0x14006f9bf  mov     [rbp+SourceDevice], r12
0x14006f9c3  mov     ebx, r12d
0x14006f9c6  mov     rdi, rcx
0x14006f9c9  mov     rcx, cs:WPP_GLOBAL_Control
0x14006f9d0  lea     rax, WPP_GLOBAL_Control
0x14006f9d7  cmp     rcx, rax
0x14006f9da  jz      short loc_14006F9FE
0x14006f9dc  mov     eax, [rcx+2Ch]
0x14006f9df  test    al, 40h
0x14006f9e1  jz      short loc_14006F9FE
0x14006f9e3  cmp     byte ptr [rcx+29h], 5
0x14006f9e7  jb      short loc_14006F9FE
0x14006f9e9  mov     rcx, [rcx+18h]
0x14006f9ed  lea     r8, WPP_b4b9d8ac9d1830ce077ccb64ddccb5ed_Traceguids
0x14006f9f4  mov     edx, 9Ah
0x14006f9f9  call    WPP_SF_
0x14006f9fe  mov     rdx, rdi; ClientIdentificationAddress
0x14006fa01  mov     rcx, rdi; DriverObject
0x14006fa04  call    cs:__imp_IoGetDriverObjectExtension
0x14006fa0b  nop     dword ptr [rax+rax+00h]
0x14006fa10  mov     r15, rax
0x14006fa13  call    cs:__imp_ExSizeOfRundownProtectionCacheAware
0x14006fa1a  nop     dword ptr [rax+rax+00h]
0x14006fa1f  mov     rsi, rax
0x14006fa22  mov     edx, dword ptr cs:WPP_MAIN_CB+148h
0x14006fa28  mov     [rbp+arg_18], r12
0x14006fa2c  mov     dword ptr [rbp+arg_18], edx
0x14006fa2f  test    dl, 10h
0x14006fa32  jnz     short loc_14006FA6D
0x14006fa34  mov     rcx, [rbp+arg_18]
0x14006fa38  or      edx, 1
0x14006fa3b  mov     [rbp+arg_18], rcx
0x14006fa3f  mov     r8d, 3
0x14006fa45  mov     dword ptr [rbp+arg_18], edx
0x14006fa48  lea     rcx, Feature_BitLocker_Scalable_Remove_Lock__private_descriptor
0x14006fa4f  mov     rdx, [rbp+arg_18]
0x14006fa53  call    wil_details_FeatureReporting_ReportUsageToService
0x14006fa58  mov     rcx, [rbp+arg_18]
0x14006fa5c  lea     r8, Feature_BitLocker_Scalable_Remove_Lock__private_descriptor
0x14006fa63  mov     edx, 3
0x14006fa68  call    wil_details_FeatureStateCache_TryEnableDeviceUsageFastPath
0x14006fa6d  lea     rdx, [rsi+1450h]; DeviceExtensionSize
0x14006fa74  cmp     rdx, rsi
0x14006fa77  jb      loc_14006FD23
0x14006fa7d  mov     eax, 0FFFFFFFFh
0x14006fa82  cmp     rdx, rax
0x14006fa85  ja      loc_14006FD23
0x14006fa8b  lea     rax, [rbp+SourceDevice]
0x14006fa8f  mov     r9d, 22h ; '"'; DeviceType
0x14006fa95  mov     [rsp+40h+DeviceObject], rax; DeviceObject
0x14006fa9a  xor     r8d, r8d; DeviceName
0x14006fa9d  mov     [rsp+40h+Exclusive], r12b; Exclusive
0x14006faa2  mov     rcx, rdi; DriverObject
0x14006faa5  mov     [rsp+40h+DeviceCharacteristics], 100h; DeviceCharacteristics
0x14006faad  call    cs:__imp_IoCreateDevice
0x14006fab4  nop     dword ptr [rax+rax+00h]
0x14006fab9  mov     edi, eax
0x14006fabb  test    eax, eax
0x14006fabd  js      loc_14006FD28
0x14006fac3  mov     rax, [rbp+SourceDevice]
0x14006fac7  xor     edx, edx; Val
0x14006fac9  mov     r8d, 1450h; Size
0x14006facf  mov     rbx, [rax+40h]
0x14006fad3  mov     rcx, rbx; void *
0x14006fad6  call    memset
0x14006fadb  mov     byte ptr [rbx+5C4h], 1
0x14006fae2  mov     ecx, cs:Feature_BitLocker_Priority_From_Current_Thread__private_featureState
0x14006fae8  mov     [rbp+arg_18], r12
0x14006faec  mov     dword ptr [rbp+arg_18], ecx
0x14006faef  test    cl, 10h
0x14006faf2  jnz     short loc_14006FB2C
0x14006faf4  mov     rax, [rbp+arg_18]
0x14006faf8  or      ecx, 1
0x14006fafb  mov     [rbp+arg_18], rax
0x14006faff  mov     edi, 3
0x14006fb04  mov     dword ptr [rbp+arg_18], ecx
0x14006fb07  mov     r8d, edi
0x14006fb0a  mov     rdx, [rbp+arg_18]
0x14006fb0e  lea     rcx, Feature_BitLocker_Priority_From_Current_Thread__private_descriptor
0x14006fb15  call    wil_details_FeatureReporting_ReportUsageToService
0x14006fb1a  mov     rcx, [rbp+arg_18]
0x14006fb1e  lea     r8, Feature_BitLocker_Priority_From_Current_Thread__private_descriptor
0x14006fb25  mov     edx, edi
0x14006fb27  call    wil_details_FeatureStateCache_TryEnableDeviceUsageFastPath
0x14006fb2c  call    cs:__imp_MmIsThisAnNtAsSystem
0x14006fb33  nop     dword ptr [rax+rax+00h]
0x14006fb38  lea     rcx, [rbx+38h]
0x14006fb3c  mov     r8b, 1
0x14006fb3f  test    al, al
0x14006fb41  mov     rdx, rbx
0x14006fb44  setnz   al
0x14006fb47  mov     [rbx+5C5h], al
0x14006fb4d  call    FveInitializeRemoveLock
0x14006fb52  mov     edi, eax
0x14006fb54  test    eax, eax
0x14006fb56  js      loc_14006FD28
0x14006fb5c  mov     rax, [rbp+SourceDevice]
0x14006fb60  mov     rcx, rbx
0x14006fb63  mov     [rbx], rax
0x14006fb66  mov     [rbx+8], r15
0x14006fb6a  mov     [rbx+1268h], r12
0x14006fb71  call    FveQueueInit
0x14006fb76  mov     edi, eax
0x14006fb78  test    eax, eax
0x14006fb7a  js      loc_14006FD28
0x14006fb80  mov     edx, [r14+30h]
0x14006fb84  mov     rcx, rbx
0x14006fb87  shr     edx, 8
0x14006fb8a  and     dl, 1
0x14006fb8d  call    FveInit
0x14006fb92  mov     edi, eax
0x14006fb94  test    eax, eax
0x14006fb96  js      loc_14006FD28
0x14006fb9c  lea     rax, [rbx+11C8h]
0x14006fba3  mov     [rax+8], rax
0x14006fba7  lea     rcx, [rbx+11E8h]; SpinLock
0x14006fbae  mov     [rax], rax
0x14006fbb1  lea     rax, [rbx+11D8h]
0x14006fbb8  mov     [rax+8], rax
0x14006fbbc  mov     [rax], rax
0x14006fbbf  call    cs:__imp_KeInitializeSpinLock
0x14006fbc6  nop     dword ptr [rax+rax+00h]
0x14006fbcb  lea     rcx, [rbx+11F8h]
0x14006fbd2  mov     [rbx+11F0h], r12
0x14006fbd9  call    FveLockInitialize
0x14006fbde  lea     rcx, [rbx+1250h]; Event
0x14006fbe5  xor     r8d, r8d; State
0x14006fbe8  xor     edx, edx; Type
0x14006fbea  call    cs:__imp_KeInitializeEvent
0x14006fbf1  nop     dword ptr [rax+rax+00h]
0x14006fbf6  mov     rcx, rbx
0x14006fbf9  mov     [rbx+78h], r14
0x14006fbfd  call    FveResolveDeviceType
0x14006fc02  mov     edi, eax
0x14006fc04  test    eax, eax
0x14006fc06  js      loc_14006FD28
0x14006fc0c  mov     rcx, rbx
0x14006fc0f  call    FveCreateDcbVol
0x14006fc14  mov     edi, eax
0x14006fc16  test    eax, eax
0x14006fc18  js      loc_14006FD28
0x14006fc1e  lea     rcx, [rbx+5A8h]; RunRef
0x14006fc25  mov     [rbx+5C0h], r12d
0x14006fc2c  mov     [rbx+5C8h], r12
0x14006fc33  mov     dword ptr [rbx+5D0h], 5
0x14006fc3d  call    cs:__imp_ExInitializeRundownProtection
0x14006fc44  nop     dword ptr [rax+rax+00h]
0x14006fc49  lea     rcx, [rbx+1450h]; RunRefCacheAware
0x14006fc50  mov     rdx, rsi; RunRefSize
0x14006fc53  mov     [rbx+5B8h], rcx
0x14006fc5a  call    cs:__imp_ExInitializeRundownProtectionCacheAware
0x14006fc61  nop     dword ptr [rax+rax+00h]
0x14006fc66  mov     rcx, [rbp+SourceDevice]; SourceDevice
0x14006fc6a  mov     rdx, r14; TargetDevice
0x14006fc6d  call    cs:__imp_IoAttachDeviceToDeviceStack
0x14006fc74  nop     dword ptr [rax+rax+00h]
0x14006fc79  mov     [rbx+70h], rax
0x14006fc7d  test    rax, rax
0x14006fc80  jnz     short loc_14006FC8C
0x14006fc82  mov     edi, 0C000000Eh
0x14006fc87  jmp     loc_14006FD28
0x14006fc8c  mov     ecx, [rax+48h]
0x14006fc8f  mov     r8, r14
0x14006fc92  mov     rax, [rbp+SourceDevice]
0x14006fc96  mov     [rax+48h], ecx
0x14006fc99  mov     rax, [rbp+SourceDevice]
0x14006fc9d  or      dword ptr [rax+30h], 10h
0x14006fca1  mov     rax, [rbx+70h]
0x14006fca5  mov     rdx, [rbp+SourceDevice]
0x14006fca9  mov     ecx, [rax+30h]
0x14006fcac  and     ecx, 6000h
0x14006fcb2  or      [rdx+30h], ecx
0x14006fcb5  mov     rax, [rbx+70h]
0x14006fcb9  mov     rdx, [rbp+SourceDevice]
0x14006fcbd  mov     ecx, [rax+34h]
0x14006fcc0  and     ecx, 5010Fh
0x14006fcc6  or      [rdx+34h], ecx
0x14006fcc9  lea     rdx, FVE_PERF_VOLUME_CREATE
0x14006fcd0  mov     rcx, rbx
0x14006fcd3  call    FvePerfTraceDevPtr
0x14006fcd8  mov     rcx, cs:WPP_GLOBAL_Control
0x14006fcdf  lea     rsi, WPP_GLOBAL_Control
0x14006fce6  cmp     rcx, rsi
0x14006fce9  jz      short loc_14006FD10
0x14006fceb  mov     eax, [rcx+2Ch]
0x14006fcee  test    al, 40h
0x14006fcf0  jz      short loc_14006FD10
0x14006fcf2  cmp     byte ptr [rcx+29h], 4
0x14006fcf6  jb      short loc_14006FD10
0x14006fcf8  mov     rcx, [rcx+18h]
0x14006fcfc  lea     r8, WPP_b4b9d8ac9d1830ce077ccb64ddccb5ed_Traceguids
0x14006fd03  mov     edx, 9Bh
0x14006fd08  mov     r9, rbx
0x14006fd0b  call    WPP_SF_q
0x14006fd10  lock or [rsp+40h+var_40], r12d
0x14006fd15  mov     rax, [rbp+SourceDevice]
0x14006fd19  btr     dword ptr [rax+30h], 7
0x14006fd1e  jmp     loc_14006FDD5
0x14006fd23  mov     edi, 0C000009Ah
0x14006fd28  cmp     [rbp+SourceDevice], r12
0x14006fd2c  jz      loc_14006FDCE
0x14006fd32  mov     rcx, rbx
0x14006fd35  call    FveDisconnectVol
0x14006fd3a  mov     rcx, rbx
0x14006fd3d  call    FveQueueCleanup
0x14006fd42  mov     rax, [rbx+920h]
0x14006fd49  test    rax, rax
0x14006fd4c  jz      short loc_14006FDA1
0x14006fd4e  mov     rcx, [rax+8]; Lookaside
0x14006fd52  mov     esi, 30455646h
0x14006fd57  test    rcx, rcx
0x14006fd5a  jz      short loc_14006FD8C
0x14006fd5c  call    cs:__imp_ExDeleteNPagedLookasideList
0x14006fd63  nop     dword ptr [rax+rax+00h]
0x14006fd68  mov     rcx, [rbx+920h]
0x14006fd6f  mov     edx, esi; Tag
0x14006fd71  mov     rcx, [rcx+8]; P
0x14006fd75  call    cs:__imp_ExFreePoolWithTag
0x14006fd7c  nop     dword ptr [rax+rax+00h]
0x14006fd81  mov     rax, [rbx+920h]
0x14006fd88  mov     [rax+8], r12
0x14006fd8c  mov     rcx, [rbx+920h]; P
0x14006fd93  mov     edx, esi; Tag
0x14006fd95  call    cs:__imp_ExFreePoolWithTag
0x14006fd9c  nop     dword ptr [rax+rax+00h]
0x14006fda1  mov     rcx, [rbx+68h]; RunRefCacheAware
0x14006fda5  test    rcx, rcx
0x14006fda8  jz      short loc_14006FDBA
0x14006fdaa  call    cs:__imp_ExFreeCacheAwareRundownProtection
0x14006fdb1  nop     dword ptr [rax+rax+00h]
0x14006fdb6  mov     [rbx+68h], r12
0x14006fdba  mov     rcx, [rbp+SourceDevice]; DeviceObject
0x14006fdbe  call    cs:__imp_IoDeleteDevice
0x14006fdc5  nop     dword ptr [rax+rax+00h]
0x14006fdca  mov     [rbp+SourceDevice], r12
0x14006fdce  lea     rsi, WPP_GLOBAL_Control
0x14006fdd5  mov     rcx, cs:WPP_GLOBAL_Control
0x14006fddc  cmp     rcx, rsi
0x14006fddf  jz      short loc_14006FE06
0x14006fde1  mov     eax, [rcx+2Ch]
0x14006fde4  test    al, 40h
0x14006fde6  jz      short loc_14006FE06
0x14006fde8  cmp     byte ptr [rcx+29h], 5
0x14006fdec  jb      short loc_14006FE06
0x14006fdee  mov     rcx, [rcx+18h]
0x14006fdf2  lea     r8, WPP_b4b9d8ac9d1830ce077ccb64ddccb5ed_Traceguids
0x14006fdf9  mov     edx, 9Ch
0x14006fdfe  mov     r9d, edi
0x14006fe01  call    WPP_SF_d
0x14006fe06  mov     rbx, [rsp+40h+arg_0]
0x14006fe0b  mov     eax, edi
0x14006fe0d  mov     rsi, [rsp+40h+arg_8]
0x14006fe12  add     rsp, 40h
0x14006fe16  pop     r15
0x14006fe18  pop     r14
0x14006fe1a  pop     r12
0x14006fe1c  pop     rdi
0x14006fe1d  pop     rbp
0x14006fe1e  retn
```
