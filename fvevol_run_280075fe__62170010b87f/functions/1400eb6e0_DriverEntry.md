# DriverEntry

- ea: `0x1400eb6e0`
- end: `0x1400ebb67`
- name: `DriverEntry`
- size: `1159`
- prototype: `NTSTATUS __stdcall(_DRIVER_OBJECT *DriverObject, PUNICODE_STRING RegistryPath)`
- caller_count: `1`
- callee_count: `32`
- tags: `registry_config, loader_planting, installer_update`

## callers

- `0x1400eb010`

## callees

- `0x140008288`
- `0x140009bf4`
- `0x14000b870`
- `0x14000da84`
- `0x14001645c`
- `0x1400165dc`
- `0x140021d00`
- `0x1400516f4`
- `0x14006f658`
- `0x14007243c`
- `0x1400724e8`
- `0x14007251c`
- `0x1400725a0`
- `0x140072634`
- `0x140072a1c`
- `0x14007afc4`
- `0x140084cf0`
- `0x140084e30`
- `0x14008d6d8`
- `0x14009e318`
- `0x1400b3254`
- `0x1400b5bc0`
- `0x1400cbcb4`
- `0x1400eb078`
- `0x1400eb67c`
- `0x1400eb6e0`
- `0x1400ebb70`
- `0x1400ec564`
- `0x1400ec70c`
- `0x1400ecee4`
- `0x1400ed688`
- `0x1400edb74`

## import_xrefs

- `ntoskrnl!KeInitializeSpinLock` at `0x1400eb973`
- `ntoskrnl!KeInitializeSpinLock` at `0x1400eb973`
- `ntoskrnl!IoRegisterPlugPlayNotification` at `0x1400eba63`
- `ntoskrnl!IoRegisterPlugPlayNotification` at `0x1400eba63`
- `ntoskrnl!IoAllocateDriverObjectExtension` at `0x1400eb791`
- `ntoskrnl!IoAllocateDriverObjectExtension` at `0x1400eb791`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400ebae7`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400ebae7`
- `ntoskrnl!ExAllocatePool2` at `0x1400eb8a4`
- `ntoskrnl!ExAllocatePool2` at `0x1400eb8a4`
- `ntoskrnl!IoRegisterBootDriverReinitialization` at `0x1400eb884`
- `ntoskrnl!IoRegisterBootDriverReinitialization` at `0x1400eb884`

## pseudocode

```c
NTSTATUS __stdcall DriverEntry(_DRIVER_OBJECT *DriverObject, PUNICODE_STRING RegistryPath)
{
  char v2; // r12
  char v3; // r14
  char v4; // r15
  NTSTATUS inited; // edi
  _QWORD *v8; // rdi
  void *v9; // rcx
  __int64 v10; // rcx
  __int64 v11; // rcx
  _QWORD *v12; // rdi
  __int64 v13; // rcx
  __int64 v14; // rcx
  int v15; // eax
  void *v16; // rcx
  PVOID DriverObjectExtension; // [rsp+70h] [rbp+30h] BYREF

  DriverObjectExtension = 0;
  v2 = 0;
  WPP_MAIN_CB.DriverObject = (struct _DRIVER_OBJECT *)WPP_ThisDir_CTLGUID_FveCtlGuid;
  v3 = 0;
  *(_QWORD *)&WPP_MAIN_CB.Type = 0;
  v4 = 0;
  WPP_MAIN_CB.NextDevice = 0;
  WPP_MAIN_CB.CurrentIrp = 0;
  WPP_MAIN_CB.Timer = (PIO_TIMER)1;
  WppLoadTracingSupport();
  WPP_MAIN_CB.CurrentIrp = 0;
  WppInitKm();
  wil_InitializeFeatureStaging();
  TraceLoggingRegisterEx_EtwRegister_EtwSetInformation(&dword_140045040);
  TlgRegisterAggregateProvider();
  g_DrvObj = (__int64)DriverObject;
  inited = IoAllocateDriverObjectExtension(DriverObject, DriverObject, 0x2958u, &DriverObjectExtension);
  if ( inited < 0 )
    goto LABEL_23;
  g_DrvExt = (__int64)DriverObjectExtension;
  inited = FveInitDriverExtension((char *)DriverObjectExtension, (__int64)DriverObject, RegistryPath);
  if ( inited < 0 )
    goto LABEL_23;
  inited = FveInitPerfCounters(DriverObjectExtension);
  if ( inited < 0 )
    goto LABEL_23;
  memset64(DriverObject->MajorFunction, (unsigned __int64)&FveFilterSkip, 0x1Cu);
  v2 = 1;
  DriverObject->MajorFunction[0] = (PDRIVER_DISPATCH)&FveFilterCreate;
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
LABEL_23:
    ReleaseKeyRing(DriverObject);
    if ( v4 )
      FveEventLogCleanup(DriverObjectExtension);
    TraceLoggingUnregister_EtwUnregister(&dword_140045040);
    TlgUnregisterAggregateProvider();
    if ( DriverObjectExtension )
    {
      v16 = (void *)*((_QWORD *)DriverObjectExtension + 9);
      if ( v16 )
      {
        ExFreePoolWithTag(v16, 0x30455646u);
        *((_QWORD *)DriverObjectExtension + 9) = 0;
      }
    }
    memset(DriverObject->MajorFunction, 0, sizeof(DriverObject->MajorFunction));
    DriverObject->DriverExtension->AddDevice = 0;
    DriverObject->DriverUnload = 0;
    if ( v2 )
      FveCleanupPerfCounters();
    FveCleanupDriverExtension(DriverObjectExtension);
    if ( v3 )
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
  if ( (unsigned int)Feature_SteelixInlineNvmeCryptoEngine__private_IsEnabledDeviceUsageNoInline(v10)
    || (unsigned int)Feature_BitLockerEphemeralVolumeSupport__private_IsEnabledDeviceUsageNoInline(v11) )
  {
    *(_QWORD *)(*((_QWORD *)DriverObjectExtension + 9) + 32LL) = FveRandomDataCallback;
  }
  KeInitializeSpinLock((PKSPIN_LOCK)DriverObjectExtension + 10);
  inited = FveLibInitEx(*((_QWORD *)DriverObjectExtension + 9), DriverObjectExtension);
  if ( inited < 0 )
    goto LABEL_23;
  v3 = 1;
  inited = FveEventLogInit(DriverObjectExtension);
  if ( inited < 0 )
    goto LABEL_23;
  v12 = DriverObjectExtension;
  v4 = 1;
  FveLockInitialize((char *)DriverObjectExtension + 136);
  v12[16] = 0;
  FveWorkerPreInit(DriverObjectExtension);
  inited = GetKeyRing(DriverObject);
  if ( inited < 0 )
    goto LABEL_23;
  FvePreAllocateKeyRingMemory(DriverObjectExtension);
  inited = FveReadWriteDriverInit((__int64)DriverObjectExtension);
  if ( inited < 0 )
    goto LABEL_23;
  FveInitWnfSubscriptions(DriverObjectExtension);
  if ( (unsigned int)Feature_SteelixInlineNvmeCryptoEngine__private_IsEnabledDeviceUsageNoInline(v13) )
  {
    v15 = (*((_DWORD *)DriverObjectExtension + 2420) & 0x20000) != 0
        ? SimGetIceKeyManInterfaceV1((char *)DriverObjectExtension + 10320)
        : IoRegisterPlugPlayNotification(
            EventCategoryDeviceInterfaceChange,
            1u,
            &GUID_DEVINTERFACE_STORAGE_ICE_KEY_MANAGEMENT,
            DriverObject,
            FveRegisterIceKeyManagementInterfaceCallback,
            DriverObjectExtension,
            (PVOID *)DriverObjectExtension + 1291);
    inited = v15;
    if ( v15 < 0 )
      goto LABEL_23;
  }
  if ( (unsigned int)Feature_BitLockerEphemeralVolumeSupport__private_IsEnabledDeviceUsageNoInline(v14) )
  {
    inited = FveLoadDrvProtections(DriverObjectExtension);
    if ( inited < 0 )
      goto LABEL_23;
  }
  if ( (unsigned int)Feature_BitLockerHwAccelCryptoSupport__private_IsEnabledDeviceUsageNoInline() )
    inited = FveHwAccelInitialize((__int64)DriverObjectExtension);
  if ( inited < 0 )
    goto LABEL_23;
  return inited;
}

```

## disassembly

```asm
0x1400eb6e0  mov     [rsp-28h+arg_8], rbx
0x1400eb6e5  mov     [rsp-28h+arg_10], rsi
0x1400eb6ea  push    rbp
0x1400eb6eb  push    rdi
0x1400eb6ec  push    r12
0x1400eb6ee  push    r14
0x1400eb6f0  push    r15
0x1400eb6f2  mov     rbp, rsp
0x1400eb6f5  sub     rsp, 40h
0x1400eb6f9  lea     rax, WPP_ThisDir_CTLGUID_FveCtlGuid
0x1400eb700  mov     [rbp+DriverObjectExtension], 0
0x1400eb708  xor     r12b, r12b
0x1400eb70b  mov     cs:WPP_MAIN_CB.DriverObject, rax
0x1400eb712  xor     r14b, r14b
0x1400eb715  mov     qword ptr cs:WPP_MAIN_CB.Type, 0
0x1400eb720  xor     r15b, r15b
0x1400eb723  mov     cs:WPP_MAIN_CB.NextDevice, 0
0x1400eb72e  mov     rsi, rdx
0x1400eb731  mov     cs:WPP_MAIN_CB.CurrentIrp, 0
0x1400eb73c  mov     rbx, rcx
0x1400eb73f  mov     cs:WPP_MAIN_CB.Timer, 1
0x1400eb74a  call    WppLoadTracingSupport
0x1400eb74f  mov     cs:WPP_MAIN_CB.CurrentIrp, 0
0x1400eb75a  call    WppInitKm
0x1400eb75f  call    wil_InitializeFeatureStaging
0x1400eb764  xor     r8d, r8d
0x1400eb767  lea     rcx, dword_140045040; CallbackContext
0x1400eb76e  xor     edx, edx
0x1400eb770  call    TraceLoggingRegisterEx_EtwRegister_EtwSetInformation
0x1400eb775  call    TlgRegisterAggregateProvider
0x1400eb77a  lea     r9, [rbp+DriverObjectExtension]; DriverObjectExtension
0x1400eb77e  mov     cs:g_DrvObj, rbx
0x1400eb785  mov     r8d, 2958h; DriverObjectExtensionSize
0x1400eb78b  mov     rdx, rbx; ClientIdentificationAddress
0x1400eb78e  mov     rcx, rbx; DriverObject
0x1400eb791  call    cs:__imp_IoAllocateDriverObjectExtension
0x1400eb798  nop     dword ptr [rax+rax+00h]
0x1400eb79d  mov     edi, eax
0x1400eb79f  test    eax, eax
0x1400eb7a1  js      loc_1400EBAA9
0x1400eb7a7  mov     rcx, [rbp+DriverObjectExtension]; CallbackContext
0x1400eb7ab  mov     r8, rsi
0x1400eb7ae  mov     rdx, rbx
0x1400eb7b1  mov     cs:g_DrvExt, rcx
0x1400eb7b8  call    FveInitDriverExtension
0x1400eb7bd  mov     edi, eax
0x1400eb7bf  test    eax, eax
0x1400eb7c1  js      loc_1400EBAA9
0x1400eb7c7  mov     rcx, [rbp+DriverObjectExtension]
0x1400eb7cb  call    FveInitPerfCounters
0x1400eb7d0  mov     edi, eax
0x1400eb7d2  test    eax, eax
0x1400eb7d4  js      loc_1400EBAA9
0x1400eb7da  lea     rax, FveFilterSkip
0x1400eb7e1  mov     ecx, 1Ch
0x1400eb7e6  lea     rdi, [rbx+70h]
0x1400eb7ea  xor     r8d, r8d; Context
0x1400eb7ed  rep stosq
0x1400eb7f0  lea     rax, FveFilterCreate
0x1400eb7f7  mov     r12b, 1
0x1400eb7fa  mov     [rbx+70h], rax
0x1400eb7fe  lea     rcx, FveFilterAddDevice
0x1400eb805  lea     rax, FveFilterClose
0x1400eb80c  mov     [rbx+80h], rax
0x1400eb813  lea     rdx, ReInitialize; DriverReinitializationRoutine
0x1400eb81a  lea     rax, FveFilterCleanup
0x1400eb821  mov     [rbx+100h], rax
0x1400eb828  lea     rax, FveFilterRundownRead
0x1400eb82f  mov     [rbx+88h], rax
0x1400eb836  lea     rax, FveFilterRundownWrite
0x1400eb83d  mov     [rbx+90h], rax
0x1400eb844  lea     rax, FveFilterDeviceControl
0x1400eb84b  mov     [rbx+0E0h], rax
0x1400eb852  lea     rax, FveFilterPower
0x1400eb859  mov     [rbx+120h], rax
0x1400eb860  lea     rax, FveFilterPnp
0x1400eb867  mov     [rbx+148h], rax
0x1400eb86e  mov     rax, [rbx+30h]
0x1400eb872  mov     [rax+8], rcx
0x1400eb876  lea     rax, FveFilterUnload
0x1400eb87d  mov     rcx, rbx; DriverObject
0x1400eb880  mov     [rbx+68h], rax
0x1400eb884  call    cs:__imp_IoRegisterBootDriverReinitialization
0x1400eb88b  nop     dword ptr [rax+rax+00h]
0x1400eb890  mov     rdi, [rbp+DriverObjectExtension]
0x1400eb894  mov     esi, 78h ; 'x'
0x1400eb899  mov     r8d, 30455646h
0x1400eb89f  mov     edx, esi
0x1400eb8a1  lea     ecx, [rsi-38h]
0x1400eb8a4  call    cs:__imp_ExAllocatePool2
0x1400eb8ab  nop     dword ptr [rax+rax+00h]
0x1400eb8b0  mov     [rdi+48h], rax
0x1400eb8b4  mov     rax, [rbp+DriverObjectExtension]
0x1400eb8b8  mov     rcx, [rax+48h]; void *
0x1400eb8bc  test    rcx, rcx
0x1400eb8bf  jnz     short loc_1400EB8CB
0x1400eb8c1  mov     edi, 0C000009Ah
0x1400eb8c6  jmp     loc_1400EBAA9
0x1400eb8cb  mov     r8, rsi; Size
0x1400eb8ce  xor     edx, edx; Val
0x1400eb8d0  call    memset
0x1400eb8d5  mov     rax, [rbp+DriverObjectExtension]
0x1400eb8d9  mov     rcx, [rax+48h]
0x1400eb8dd  lea     rax, FveAllocCallback
0x1400eb8e4  mov     [rcx], rax
0x1400eb8e7  mov     rax, [rbp+DriverObjectExtension]
0x1400eb8eb  mov     rcx, [rax+48h]
0x1400eb8ef  lea     rax, FveFreeCallback
0x1400eb8f6  mov     [rcx+8], rax
0x1400eb8fa  mov     rax, [rbp+DriverObjectExtension]
0x1400eb8fe  mov     rcx, [rax+48h]
0x1400eb902  lea     rax, FveGetTimeCallback
0x1400eb909  mov     [rcx+30h], rax
0x1400eb90d  mov     rax, [rbp+DriverObjectExtension]
0x1400eb911  mov     rcx, [rax+48h]
0x1400eb915  lea     rax, FveGlobalLockAcquireCallback
0x1400eb91c  mov     [rcx+38h], rax
0x1400eb920  mov     rax, [rbp+DriverObjectExtension]
0x1400eb924  mov     rcx, [rax+48h]
0x1400eb928  lea     rax, FveGlobalLockReleaseCallback
0x1400eb92f  mov     [rcx+40h], rax
0x1400eb933  mov     rax, [rbp+DriverObjectExtension]
0x1400eb937  mov     rcx, [rax+48h]
0x1400eb93b  lea     rax, FveLibCryptoPerfEventCallback
0x1400eb942  mov     [rcx+48h], rax
0x1400eb946  call    Feature_SteelixInlineNvmeCryptoEngine__private_IsEnabledDeviceUsageNoInline
0x1400eb94b  test    eax, eax
0x1400eb94d  jnz     short loc_1400EB958
0x1400eb94f  call    Feature_BitLockerEphemeralVolumeSupport__private_IsEnabledDeviceUsageNoInline
0x1400eb954  test    eax, eax
0x1400eb956  jz      short loc_1400EB96B
0x1400eb958  mov     rax, [rbp+DriverObjectExtension]
0x1400eb95c  mov     rcx, [rax+48h]
0x1400eb960  lea     rax, FveRandomDataCallback
0x1400eb967  mov     [rcx+20h], rax
0x1400eb96b  mov     rcx, [rbp+DriverObjectExtension]
0x1400eb96f  add     rcx, 50h ; 'P'; SpinLock
0x1400eb973  call    cs:__imp_KeInitializeSpinLock
0x1400eb97a  nop     dword ptr [rax+rax+00h]
0x1400eb97f  mov     rcx, [rbp+DriverObjectExtension]
0x1400eb983  mov     rdx, rcx
0x1400eb986  mov     rcx, [rcx+48h]
0x1400eb98a  call    FveLibInitEx
0x1400eb98f  mov     edi, eax
0x1400eb991  test    eax, eax
0x1400eb993  js      loc_1400EBAA9
0x1400eb999  mov     rcx, [rbp+DriverObjectExtension]
0x1400eb99d  mov     r14b, r12b
0x1400eb9a0  call    FveEventLogInit
0x1400eb9a5  mov     edi, eax
0x1400eb9a7  test    eax, eax
0x1400eb9a9  js      loc_1400EBAA9
0x1400eb9af  mov     rdi, [rbp+DriverObjectExtension]
0x1400eb9b3  mov     r15b, r12b
0x1400eb9b6  lea     rcx, [rdi+88h]
0x1400eb9bd  call    FveLockInitialize
0x1400eb9c2  mov     qword ptr [rdi+80h], 0
0x1400eb9cd  mov     rcx, [rbp+DriverObjectExtension]
0x1400eb9d1  call    FveWorkerPreInit
0x1400eb9d6  mov     rcx, rbx; ClientIdentificationAddress
0x1400eb9d9  call    GetKeyRing
0x1400eb9de  mov     edi, eax
0x1400eb9e0  test    eax, eax
0x1400eb9e2  js      loc_1400EBAA9
0x1400eb9e8  mov     rcx, [rbp+DriverObjectExtension]
0x1400eb9ec  call    FvePreAllocateKeyRingMemory
0x1400eb9f1  mov     rcx, [rbp+DriverObjectExtension]
0x1400eb9f5  call    FveReadWriteDriverInit
0x1400eb9fa  mov     edi, eax
0x1400eb9fc  test    eax, eax
0x1400eb9fe  js      loc_1400EBAA9
0x1400eba04  mov     rcx, [rbp+DriverObjectExtension]
0x1400eba08  call    FveInitWnfSubscriptions
0x1400eba0d  call    Feature_SteelixInlineNvmeCryptoEngine__private_IsEnabledDeviceUsageNoInline
0x1400eba12  test    eax, eax
0x1400eba14  jz      short loc_1400EBA75
0x1400eba16  mov     rcx, [rbp+DriverObjectExtension]
0x1400eba1a  test    dword ptr [rcx+25D0h], 20000h
0x1400eba24  jz      short loc_1400EBA34
0x1400eba26  add     rcx, 2850h
0x1400eba2d  call    SimGetIceKeyManInterfaceV1
0x1400eba32  jmp     short loc_1400EBA6F
0x1400eba34  lea     rax, [rcx+2858h]
0x1400eba3b  mov     edx, 1; EventCategoryFlags
0x1400eba40  mov     [rsp+40h+NotificationEntry], rax; NotificationEntry
0x1400eba45  lea     r8, GUID_DEVINTERFACE_STORAGE_ICE_KEY_MANAGEMENT; EventCategoryData
0x1400eba4c  mov     [rsp+40h+Context], rcx; Context
0x1400eba51  lea     rax, FveRegisterIceKeyManagementInterfaceCallback
0x1400eba58  mov     r9, rbx; DriverObject
0x1400eba5b  mov     [rsp+40h+CallbackRoutine], rax; CallbackRoutine
0x1400eba60  lea     ecx, [rdx+1]; EventCategory
0x1400eba63  call    cs:__imp_IoRegisterPlugPlayNotification
0x1400eba6a  nop     dword ptr [rax+rax+00h]
0x1400eba6f  mov     edi, eax
0x1400eba71  test    eax, eax
0x1400eba73  js      short loc_1400EBAA9
0x1400eba75  call    Feature_BitLockerEphemeralVolumeSupport__private_IsEnabledDeviceUsageNoInline
0x1400eba7a  test    eax, eax
0x1400eba7c  jz      short loc_1400EBA8D
0x1400eba7e  mov     rcx, [rbp+DriverObjectExtension]
0x1400eba82  call    FveLoadDrvProtections
0x1400eba87  mov     edi, eax
0x1400eba89  test    eax, eax
0x1400eba8b  js      short loc_1400EBAA9
0x1400eba8d  call    Feature_BitLockerHwAccelCryptoSupport__private_IsEnabledDeviceUsageNoInline
0x1400eba92  test    eax, eax
0x1400eba94  jz      short loc_1400EBAA1
0x1400eba96  mov     rcx, [rbp+DriverObjectExtension]
0x1400eba9a  call    FveHwAccelInitialize
0x1400eba9f  mov     edi, eax
0x1400ebaa1  test    edi, edi
0x1400ebaa3  jns     loc_1400EBB4B
0x1400ebaa9  mov     rcx, rbx; ClientIdentificationAddress
0x1400ebaac  call    ReleaseKeyRing
0x1400ebab1  test    r15b, r15b
0x1400ebab4  jz      short loc_1400EBABF
0x1400ebab6  mov     rcx, [rbp+DriverObjectExtension]
0x1400ebaba  call    FveEventLogCleanup
0x1400ebabf  lea     rcx, dword_140045040
0x1400ebac6  call    TraceLoggingUnregister_EtwUnregister
0x1400ebacb  call    TlgUnregisterAggregateProvider
0x1400ebad0  mov     rax, [rbp+DriverObjectExtension]
0x1400ebad4  test    rax, rax
0x1400ebad7  jz      short loc_1400EBAFF
0x1400ebad9  mov     rcx, [rax+48h]; P
0x1400ebadd  test    rcx, rcx
0x1400ebae0  jz      short loc_1400EBAFF
0x1400ebae2  mov     edx, 30455646h; Tag
0x1400ebae7  call    cs:__imp_ExFreePoolWithTag
0x1400ebaee  nop     dword ptr [rax+rax+00h]
0x1400ebaf3  mov     rax, [rbp+DriverObjectExtension]
0x1400ebaf7  mov     qword ptr [rax+48h], 0
0x1400ebaff  lea     rcx, [rbx+70h]; void *
0x1400ebb03  xor     edx, edx; Val
0x1400ebb05  mov     r8d, 0E0h; Size
0x1400ebb0b  call    memset
0x1400ebb10  mov     rax, [rbx+30h]
0x1400ebb14  mov     qword ptr [rax+8], 0
0x1400ebb1c  mov     qword ptr [rbx+68h], 0
0x1400ebb24  test    r12b, r12b
0x1400ebb27  jz      short loc_1400EBB2E
0x1400ebb29  call    FveCleanupPerfCounters
0x1400ebb2e  mov     rcx, [rbp+DriverObjectExtension]; void *
0x1400ebb32  call    FveCleanupDriverExtension
0x1400ebb37  test    r14b, r14b
0x1400ebb3a  jz      short loc_1400EBB41
0x1400ebb3c  call    FveLibCleanup
0x1400ebb41  call    wil_UninitializeFeatureStaging
0x1400ebb46  call    WppCleanupKm
0x1400ebb4b  lea     r11, [rsp+40h+var_s0]
0x1400ebb50  mov     eax, edi
0x1400ebb52  mov     rbx, [r11+38h]
0x1400ebb56  mov     rsi, [r11+40h]
0x1400ebb5a  mov     rsp, r11
0x1400ebb5d  pop     r15
0x1400ebb5f  pop     r14
0x1400ebb61  pop     r12
0x1400ebb63  pop     rdi
0x1400ebb64  pop     rbp
0x1400ebb65  retn
```
