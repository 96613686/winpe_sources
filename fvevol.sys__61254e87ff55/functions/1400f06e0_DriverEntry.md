# DriverEntry

- ea: `0x1400f06e0`
- end: `0x1400f0b57`
- name: `DriverEntry`
- size: `1143`
- prototype: `NTSTATUS __stdcall(_DRIVER_OBJECT *DriverObject, PUNICODE_STRING RegistryPath)`
- caller_count: `1`
- callee_count: `31`
- tags: `registry_config, loader_planting, installer_update`

## callers

- `0x1400f0010`

## callees

- `0x140008348`
- `0x140009cb4`
- `0x14000dc6c`
- `0x140016e14`
- `0x140016f94`
- `0x1400221ec`
- `0x140023040`
- `0x1400536f4`
- `0x1400716e8`
- `0x14007441c`
- `0x1400744c8`
- `0x1400744fc`
- `0x140074580`
- `0x140074614`
- `0x1400749fc`
- `0x14007d068`
- `0x140086d90`
- `0x140086ed0`
- `0x14008f788`
- `0x14009f258`
- `0x1400b44e4`
- `0x1400b6ebc`
- `0x1400f0078`
- `0x1400f067c`
- `0x1400f06e0`
- `0x1400f0b60`
- `0x1400f1554`
- `0x1400f16fc`
- `0x1400f1f50`
- `0x1400f26f4`
- `0x1400f2be0`

## import_xrefs

- `ntoskrnl!KeInitializeSpinLock` at `0x1400f097b`
- `ntoskrnl!KeInitializeSpinLock` at `0x1400f097b`
- `ntoskrnl!IoRegisterPlugPlayNotification` at `0x1400f0a6b`
- `ntoskrnl!IoRegisterPlugPlayNotification` at `0x1400f0a6b`
- `ntoskrnl!IoRegisterBootDriverReinitialization` at `0x1400f0889`
- `ntoskrnl!IoRegisterBootDriverReinitialization` at `0x1400f0889`
- `ntoskrnl!IoAllocateDriverObjectExtension` at `0x1400f0796`
- `ntoskrnl!IoAllocateDriverObjectExtension` at `0x1400f0796`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400f0ad7`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400f0ad7`
- `ntoskrnl!ExAllocatePool2` at `0x1400f08ac`
- `ntoskrnl!ExAllocatePool2` at `0x1400f08ac`

## pseudocode

```c
NTSTATUS __stdcall DriverEntry(_DRIVER_OBJECT *DriverObject, PUNICODE_STRING RegistryPath)
{
  char v4; // r12
  char v5; // si
  char v6; // r14
  NTSTATUS inited; // edi
  _QWORD *v8; // rdi
  void *v9; // rcx
  __int64 v10; // rcx
  __int64 v11; // rdx
  __int64 v12; // rdx
  __int64 v13; // rcx
  _QWORD *v14; // rdi
  __int64 v15; // rdx
  __int64 v16; // rcx
  __int64 v17; // rdx
  __int64 v18; // rcx
  int v19; // eax
  void *v20; // rcx
  PVOID DriverObjectExtension; // [rsp+70h] [rbp+30h] BYREF

  DriverObjectExtension = 0;
  v4 = 0;
  v5 = 0;
  v6 = 0;
  InitializeTelemetryAssertsKMByDriverObject();
  *(_QWORD *)&WPP_MAIN_CB.Type = 0;
  WPP_MAIN_CB.DriverObject = (struct _DRIVER_OBJECT *)WPP_ThisDir_CTLGUID_FveCtlGuid;
  WPP_MAIN_CB.NextDevice = 0;
  WPP_MAIN_CB.CurrentIrp = 0;
  WPP_MAIN_CB.Timer = (PIO_TIMER)1;
  WppLoadTracingSupport();
  WPP_MAIN_CB.CurrentIrp = 0;
  WppInitKm();
  wil_InitializeFeatureStaging();
  TraceLoggingRegisterEx_EtwRegister_EtwSetInformation(&dword_140046040);
  TlgRegisterAggregateProvider();
  g_DrvObj = (__int64)DriverObject;
  inited = IoAllocateDriverObjectExtension(DriverObject, DriverObject, 0x2A60u, &DriverObjectExtension);
  if ( inited < 0 )
    goto LABEL_21;
  g_DrvExt = (__int64)DriverObjectExtension;
  inited = FveInitDriverExtension((char *)DriverObjectExtension, (__int64)DriverObject, RegistryPath);
  if ( inited < 0 )
    goto LABEL_21;
  inited = FveInitPerfCounters(DriverObjectExtension);
  if ( inited < 0 )
    goto LABEL_21;
  memset64(DriverObject->MajorFunction, (unsigned __int64)FveFilterSkip, 0x1Cu);
  v4 = 1;
  DriverObject->MajorFunction[0] = (PDRIVER_DISPATCH)FveFilterCreate;
  DriverObject->MajorFunction[2] = (PDRIVER_DISPATCH)&FveFilterClose;
  DriverObject->MajorFunction[18] = (PDRIVER_DISPATCH)&FveFilterCleanup;
  DriverObject->MajorFunction[3] = (PDRIVER_DISPATCH)FveFilterRundownRead;
  DriverObject->MajorFunction[4] = (PDRIVER_DISPATCH)FveFilterRundownWrite;
  DriverObject->MajorFunction[14] = (PDRIVER_DISPATCH)&FveFilterDeviceControl;
  DriverObject->MajorFunction[22] = (PDRIVER_DISPATCH)&FveFilterPower;
  DriverObject->MajorFunction[27] = (PDRIVER_DISPATCH)FveFilterPnp;
  DriverObject->DriverExtension->AddDevice = (PDRIVER_ADD_DEVICE)FveFilterAddDevice;
  DriverObject->DriverUnload = (PDRIVER_UNLOAD)FveFilterUnload;
  IoRegisterBootDriverReinitialization(DriverObject, ReInitialize, 0);
  v8 = DriverObjectExtension;
  v8[9] = ExAllocatePool2(64, 120, 809850438);
  v9 = (void *)*((_QWORD *)DriverObjectExtension + 9);
  if ( !v9 )
  {
    inited = -1073741670;
LABEL_21:
    ReleaseKeyRing(DriverObject);
    if ( v6 )
      FveEventLogCleanup(DriverObjectExtension);
    TraceLoggingUnregister_EtwUnregister(&dword_140046040);
    TlgUnregisterAggregateProvider();
    if ( DriverObjectExtension )
    {
      v20 = (void *)*((_QWORD *)DriverObjectExtension + 9);
      if ( v20 )
      {
        ExFreePoolWithTag(v20, 0x30455646u);
        *((_QWORD *)DriverObjectExtension + 9) = 0;
      }
    }
    memset(DriverObject->MajorFunction, 0, sizeof(DriverObject->MajorFunction));
    DriverObject->DriverExtension->AddDevice = 0;
    DriverObject->DriverUnload = 0;
    if ( v4 )
      FveCleanupPerfCounters();
    FveCleanupDriverExtension(DriverObjectExtension);
    if ( v5 )
      FveLibCleanup();
    wil_UninitializeFeatureStaging();
    WppCleanupKm();
    return inited;
  }
  memset(v9, 0, 0x78u);
  **((_QWORD **)DriverObjectExtension + 9) = FveAllocCallback;
  *(_QWORD *)(*((_QWORD *)DriverObjectExtension + 9) + 8LL) = FveFreeCallback;
  *(_QWORD *)(*((_QWORD *)DriverObjectExtension + 9) + 48LL) = FveGetTimeCallback;
  *(_QWORD *)(*((_QWORD *)DriverObjectExtension + 9) + 56LL) = FveGlobalLockAcquireCallback;
  *(_QWORD *)(*((_QWORD *)DriverObjectExtension + 9) + 64LL) = FveGlobalLockReleaseCallback;
  v10 = *((_QWORD *)DriverObjectExtension + 9);
  *(_QWORD *)(v10 + 72) = FveLibCryptoPerfEventCallback;
  if ( (unsigned int)Feature_SteelixInlineNvmeCryptoEngine__private_IsEnabledDeviceUsageNoInline(v10, v11)
    || (unsigned int)Feature_BitLockerEphemeralVolumeSupport__private_IsEnabledDeviceUsageNoInline(v13, v12) )
  {
    *(_QWORD *)(*((_QWORD *)DriverObjectExtension + 9) + 32LL) = FveRandomDataCallback;
  }
  KeInitializeSpinLock((PKSPIN_LOCK)DriverObjectExtension + 10);
  inited = FveLibInitEx(*((_QWORD *)DriverObjectExtension + 9), DriverObjectExtension);
  if ( inited < 0 )
    goto LABEL_21;
  v5 = 1;
  inited = FveEventLogInit(DriverObjectExtension);
  if ( inited < 0 )
    goto LABEL_21;
  v14 = DriverObjectExtension;
  v6 = 1;
  FveLockInitialize((char *)DriverObjectExtension + 136);
  v14[16] = 0;
  FveWorkerPreInit(DriverObjectExtension);
  inited = GetKeyRing(DriverObject);
  if ( inited < 0 )
    goto LABEL_21;
  FvePreAllocateKeyRingMemory(DriverObjectExtension);
  inited = FveReadWriteDriverInit((__int64)DriverObjectExtension);
  if ( inited < 0 )
    goto LABEL_21;
  FveInitWnfSubscriptions(DriverObjectExtension);
  if ( (unsigned int)Feature_SteelixInlineNvmeCryptoEngine__private_IsEnabledDeviceUsageNoInline(v16, v15) )
  {
    v19 = (*((_DWORD *)DriverObjectExtension + 2482) & 0x20000) != 0
        ? SimGetIceKeyManInterfaceV1((char *)DriverObjectExtension + 10568)
        : IoRegisterPlugPlayNotification(
            EventCategoryDeviceInterfaceChange,
            1u,
            &GUID_DEVINTERFACE_STORAGE_ICE_KEY_MANAGEMENT,
            DriverObject,
            FveRegisterIceKeyManagementInterfaceCallback,
            DriverObjectExtension,
            (PVOID *)DriverObjectExtension + 1322);
    inited = v19;
    if ( v19 < 0 )
      goto LABEL_21;
  }
  if ( (unsigned int)Feature_BitLockerEphemeralVolumeSupport__private_IsEnabledDeviceUsageNoInline(v18, v17) )
    inited = FveLoadDrvProtections(DriverObjectExtension);
  if ( inited < 0 )
    goto LABEL_21;
  return inited;
}

```

## disassembly

```asm
0x1400f06e0  mov     [rsp-28h+arg_8], rbx
0x1400f06e5  mov     [rsp-28h+arg_10], rsi
0x1400f06ea  push    rbp
0x1400f06eb  push    rdi
0x1400f06ec  push    r12
0x1400f06ee  push    r14
0x1400f06f0  push    r15
0x1400f06f2  mov     rbp, rsp
0x1400f06f5  sub     rsp, 40h
0x1400f06f9  mov     r15, rdx
0x1400f06fc  mov     [rbp+DriverObjectExtension], 0
0x1400f0704  mov     rbx, rcx
0x1400f0707  xor     r12b, r12b
0x1400f070a  xor     sil, sil
0x1400f070d  xor     r14b, r14b
0x1400f0710  call    InitializeTelemetryAssertsKMByDriverObject
0x1400f0715  lea     rax, WPP_ThisDir_CTLGUID_FveCtlGuid
0x1400f071c  mov     qword ptr cs:WPP_MAIN_CB.Type, 0
0x1400f0727  mov     cs:WPP_MAIN_CB.DriverObject, rax
0x1400f072e  mov     cs:WPP_MAIN_CB.NextDevice, 0
0x1400f0739  mov     cs:WPP_MAIN_CB.CurrentIrp, 0
0x1400f0744  mov     cs:WPP_MAIN_CB.Timer, 1
0x1400f074f  call    WppLoadTracingSupport
0x1400f0754  mov     cs:WPP_MAIN_CB.CurrentIrp, 0
0x1400f075f  call    WppInitKm
0x1400f0764  call    wil_InitializeFeatureStaging
0x1400f0769  xor     r8d, r8d
0x1400f076c  lea     rcx, dword_140046040; CallbackContext
0x1400f0773  xor     edx, edx
0x1400f0775  call    TraceLoggingRegisterEx_EtwRegister_EtwSetInformation
0x1400f077a  call    TlgRegisterAggregateProvider
0x1400f077f  lea     r9, [rbp+DriverObjectExtension]; DriverObjectExtension
0x1400f0783  mov     cs:g_DrvObj, rbx
0x1400f078a  mov     r8d, 2A60h; DriverObjectExtensionSize
0x1400f0790  mov     rdx, rbx; ClientIdentificationAddress
0x1400f0793  mov     rcx, rbx; DriverObject
0x1400f0796  call    cs:__imp_IoAllocateDriverObjectExtension
0x1400f079d  nop     dword ptr [rax+rax+00h]
0x1400f07a2  mov     edi, eax
0x1400f07a4  test    eax, eax
0x1400f07a6  js      loc_1400F0A99
0x1400f07ac  mov     rcx, [rbp+DriverObjectExtension]; CallbackContext
0x1400f07b0  mov     r8, r15
0x1400f07b3  mov     rdx, rbx
0x1400f07b6  mov     cs:g_DrvExt, rcx
0x1400f07bd  call    FveInitDriverExtension
0x1400f07c2  mov     edi, eax
0x1400f07c4  test    eax, eax
0x1400f07c6  js      loc_1400F0A99
0x1400f07cc  mov     rcx, [rbp+DriverObjectExtension]
0x1400f07d0  call    FveInitPerfCounters
0x1400f07d5  mov     edi, eax
0x1400f07d7  test    eax, eax
0x1400f07d9  js      loc_1400F0A99
0x1400f07df  lea     rax, FveFilterSkip
0x1400f07e6  mov     ecx, 1Ch
0x1400f07eb  lea     rdi, [rbx+70h]
0x1400f07ef  xor     r8d, r8d; Context
0x1400f07f2  rep stosq
0x1400f07f5  lea     rax, FveFilterCreate
0x1400f07fc  mov     r12b, 1
0x1400f07ff  mov     [rbx+70h], rax
0x1400f0803  lea     rcx, FveFilterAddDevice
0x1400f080a  lea     rax, FveFilterClose
0x1400f0811  mov     [rbx+80h], rax
0x1400f0818  lea     rdx, ReInitialize; DriverReinitializationRoutine
0x1400f081f  lea     rax, FveFilterCleanup
0x1400f0826  mov     [rbx+100h], rax
0x1400f082d  lea     rax, FveFilterRundownRead
0x1400f0834  mov     [rbx+88h], rax
0x1400f083b  lea     rax, FveFilterRundownWrite
0x1400f0842  mov     [rbx+90h], rax
0x1400f0849  lea     rax, FveFilterDeviceControl
0x1400f0850  mov     [rbx+0E0h], rax
0x1400f0857  lea     rax, FveFilterPower
0x1400f085e  mov     [rbx+120h], rax
0x1400f0865  lea     rax, FveFilterPnp
0x1400f086c  mov     [rbx+148h], rax
0x1400f0873  mov     rax, [rbx+30h]
0x1400f0877  mov     [rax+8], rcx
0x1400f087b  lea     rax, FveFilterUnload
0x1400f0882  mov     rcx, rbx; DriverObject
0x1400f0885  mov     [rbx+68h], rax
0x1400f0889  call    cs:__imp_IoRegisterBootDriverReinitialization
0x1400f0890  nop     dword ptr [rax+rax+00h]
0x1400f0895  mov     rdi, [rbp+DriverObjectExtension]
0x1400f0899  mov     r15d, 78h ; 'x'
0x1400f089f  mov     r8d, 30455646h
0x1400f08a5  mov     edx, r15d
0x1400f08a8  lea     ecx, [r15-38h]
0x1400f08ac  call    cs:__imp_ExAllocatePool2
0x1400f08b3  nop     dword ptr [rax+rax+00h]
0x1400f08b8  mov     [rdi+48h], rax
0x1400f08bc  mov     rax, [rbp+DriverObjectExtension]
0x1400f08c0  mov     rcx, [rax+48h]; void *
0x1400f08c4  test    rcx, rcx
0x1400f08c7  jnz     short loc_1400F08D3
0x1400f08c9  mov     edi, 0C000009Ah
0x1400f08ce  jmp     loc_1400F0A99
0x1400f08d3  mov     r8, r15; Size
0x1400f08d6  xor     edx, edx; Val
0x1400f08d8  call    memset
0x1400f08dd  mov     rax, [rbp+DriverObjectExtension]
0x1400f08e1  mov     rcx, [rax+48h]
0x1400f08e5  lea     rax, FveAllocCallback
0x1400f08ec  mov     [rcx], rax
0x1400f08ef  mov     rax, [rbp+DriverObjectExtension]
0x1400f08f3  mov     rcx, [rax+48h]
0x1400f08f7  lea     rax, FveFreeCallback
0x1400f08fe  mov     [rcx+8], rax
0x1400f0902  mov     rax, [rbp+DriverObjectExtension]
0x1400f0906  mov     rcx, [rax+48h]
0x1400f090a  lea     rax, FveGetTimeCallback
0x1400f0911  mov     [rcx+30h], rax
0x1400f0915  mov     rax, [rbp+DriverObjectExtension]
0x1400f0919  mov     rcx, [rax+48h]
0x1400f091d  lea     rax, FveGlobalLockAcquireCallback
0x1400f0924  mov     [rcx+38h], rax
0x1400f0928  mov     rax, [rbp+DriverObjectExtension]
0x1400f092c  mov     rcx, [rax+48h]
0x1400f0930  lea     rax, FveGlobalLockReleaseCallback
0x1400f0937  mov     [rcx+40h], rax
0x1400f093b  mov     rax, [rbp+DriverObjectExtension]
0x1400f093f  mov     rcx, [rax+48h]
0x1400f0943  lea     rax, FveLibCryptoPerfEventCallback
0x1400f094a  mov     [rcx+48h], rax
0x1400f094e  call    Feature_SteelixInlineNvmeCryptoEngine__private_IsEnabledDeviceUsageNoInline
0x1400f0953  test    eax, eax
0x1400f0955  jnz     short loc_1400F0960
0x1400f0957  call    Feature_BitLockerEphemeralVolumeSupport__private_IsEnabledDeviceUsageNoInline
0x1400f095c  test    eax, eax
0x1400f095e  jz      short loc_1400F0973
0x1400f0960  mov     rax, [rbp+DriverObjectExtension]
0x1400f0964  mov     rcx, [rax+48h]
0x1400f0968  lea     rax, FveRandomDataCallback
0x1400f096f  mov     [rcx+20h], rax
0x1400f0973  mov     rcx, [rbp+DriverObjectExtension]
0x1400f0977  add     rcx, 50h ; 'P'; SpinLock
0x1400f097b  call    cs:__imp_KeInitializeSpinLock
0x1400f0982  nop     dword ptr [rax+rax+00h]
0x1400f0987  mov     rcx, [rbp+DriverObjectExtension]
0x1400f098b  mov     rdx, rcx
0x1400f098e  mov     rcx, [rcx+48h]
0x1400f0992  call    FveLibInitEx
0x1400f0997  mov     edi, eax
0x1400f0999  test    eax, eax
0x1400f099b  js      loc_1400F0A99
0x1400f09a1  mov     rcx, [rbp+DriverObjectExtension]
0x1400f09a5  mov     sil, r12b
0x1400f09a8  call    FveEventLogInit
0x1400f09ad  mov     edi, eax
0x1400f09af  test    eax, eax
0x1400f09b1  js      loc_1400F0A99
0x1400f09b7  mov     rdi, [rbp+DriverObjectExtension]
0x1400f09bb  mov     r14b, r12b
0x1400f09be  lea     rcx, [rdi+88h]
0x1400f09c5  call    FveLockInitialize
0x1400f09ca  mov     qword ptr [rdi+80h], 0
0x1400f09d5  mov     rcx, [rbp+DriverObjectExtension]
0x1400f09d9  call    FveWorkerPreInit
0x1400f09de  mov     rcx, rbx; ClientIdentificationAddress
0x1400f09e1  call    GetKeyRing
0x1400f09e6  mov     edi, eax
0x1400f09e8  test    eax, eax
0x1400f09ea  js      loc_1400F0A99
0x1400f09f0  mov     rcx, [rbp+DriverObjectExtension]
0x1400f09f4  call    FvePreAllocateKeyRingMemory
0x1400f09f9  mov     rcx, [rbp+DriverObjectExtension]
0x1400f09fd  call    FveReadWriteDriverInit
0x1400f0a02  mov     edi, eax
0x1400f0a04  test    eax, eax
0x1400f0a06  js      loc_1400F0A99
0x1400f0a0c  mov     rcx, [rbp+DriverObjectExtension]
0x1400f0a10  call    FveInitWnfSubscriptions
0x1400f0a15  call    Feature_SteelixInlineNvmeCryptoEngine__private_IsEnabledDeviceUsageNoInline
0x1400f0a1a  test    eax, eax
0x1400f0a1c  jz      short loc_1400F0A7D
0x1400f0a1e  mov     rcx, [rbp+DriverObjectExtension]
0x1400f0a22  test    dword ptr [rcx+26C8h], 20000h
0x1400f0a2c  jz      short loc_1400F0A3C
0x1400f0a2e  add     rcx, 2948h
0x1400f0a35  call    SimGetIceKeyManInterfaceV1
0x1400f0a3a  jmp     short loc_1400F0A77
0x1400f0a3c  lea     rax, [rcx+2950h]
0x1400f0a43  mov     edx, 1; EventCategoryFlags
0x1400f0a48  mov     [rsp+40h+NotificationEntry], rax; NotificationEntry
0x1400f0a4d  lea     r8, GUID_DEVINTERFACE_STORAGE_ICE_KEY_MANAGEMENT; EventCategoryData
0x1400f0a54  mov     [rsp+40h+Context], rcx; Context
0x1400f0a59  lea     rax, FveRegisterIceKeyManagementInterfaceCallback
0x1400f0a60  mov     r9, rbx; DriverObject
0x1400f0a63  mov     [rsp+40h+CallbackRoutine], rax; CallbackRoutine
0x1400f0a68  lea     ecx, [rdx+1]; EventCategory
0x1400f0a6b  call    cs:__imp_IoRegisterPlugPlayNotification
0x1400f0a72  nop     dword ptr [rax+rax+00h]
0x1400f0a77  mov     edi, eax
0x1400f0a79  test    eax, eax
0x1400f0a7b  js      short loc_1400F0A99
0x1400f0a7d  call    Feature_BitLockerEphemeralVolumeSupport__private_IsEnabledDeviceUsageNoInline
0x1400f0a82  test    eax, eax
0x1400f0a84  jz      short loc_1400F0A91
0x1400f0a86  mov     rcx, [rbp+DriverObjectExtension]
0x1400f0a8a  call    FveLoadDrvProtections
0x1400f0a8f  mov     edi, eax
0x1400f0a91  test    edi, edi
0x1400f0a93  jns     loc_1400F0B3B
0x1400f0a99  mov     rcx, rbx; ClientIdentificationAddress
0x1400f0a9c  call    ReleaseKeyRing
0x1400f0aa1  test    r14b, r14b
0x1400f0aa4  jz      short loc_1400F0AAF
0x1400f0aa6  mov     rcx, [rbp+DriverObjectExtension]
0x1400f0aaa  call    FveEventLogCleanup
0x1400f0aaf  lea     rcx, dword_140046040
0x1400f0ab6  call    TraceLoggingUnregister_EtwUnregister
0x1400f0abb  call    TlgUnregisterAggregateProvider
0x1400f0ac0  mov     rax, [rbp+DriverObjectExtension]
0x1400f0ac4  test    rax, rax
0x1400f0ac7  jz      short loc_1400F0AEF
0x1400f0ac9  mov     rcx, [rax+48h]; P
0x1400f0acd  test    rcx, rcx
0x1400f0ad0  jz      short loc_1400F0AEF
0x1400f0ad2  mov     edx, 30455646h; Tag
0x1400f0ad7  call    cs:__imp_ExFreePoolWithTag
0x1400f0ade  nop     dword ptr [rax+rax+00h]
0x1400f0ae3  mov     rax, [rbp+DriverObjectExtension]
0x1400f0ae7  mov     qword ptr [rax+48h], 0
0x1400f0aef  lea     rcx, [rbx+70h]; void *
0x1400f0af3  xor     edx, edx; Val
0x1400f0af5  mov     r8d, 0E0h; Size
0x1400f0afb  call    memset
0x1400f0b00  mov     rax, [rbx+30h]
0x1400f0b04  mov     qword ptr [rax+8], 0
0x1400f0b0c  mov     qword ptr [rbx+68h], 0
0x1400f0b14  test    r12b, r12b
0x1400f0b17  jz      short loc_1400F0B1E
0x1400f0b19  call    FveCleanupPerfCounters
0x1400f0b1e  mov     rcx, [rbp+DriverObjectExtension]; void *
0x1400f0b22  call    FveCleanupDriverExtension
0x1400f0b27  test    sil, sil
0x1400f0b2a  jz      short loc_1400F0B31
0x1400f0b2c  call    FveLibCleanup
0x1400f0b31  call    wil_UninitializeFeatureStaging
0x1400f0b36  call    WppCleanupKm
0x1400f0b3b  lea     r11, [rsp+40h+var_s0]
0x1400f0b40  mov     eax, edi
0x1400f0b42  mov     rbx, [r11+38h]
0x1400f0b46  mov     rsi, [r11+40h]
0x1400f0b4a  mov     rsp, r11
0x1400f0b4d  pop     r15
0x1400f0b4f  pop     r14
0x1400f0b51  pop     r12
0x1400f0b53  pop     rdi
0x1400f0b54  pop     rbp
0x1400f0b55  retn
```
