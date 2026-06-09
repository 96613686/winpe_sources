# DriverEntry

- ea: `0x140090740`
- end: `0x140091415`
- name: `DriverEntry`
- size: `3285`
- prototype: `NTSTATUS __stdcall(_DRIVER_OBJECT *DriverObject, PUNICODE_STRING RegistryPath)`
- caller_count: `1`
- callee_count: `41`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x140090010`

## callees

- `0x140013018`
- `0x140015634`
- `0x140018930`
- `0x1400190ec`
- `0x14001b7a0`
- `0x14001b884`
- `0x14001bfac`
- `0x140020edc`
- `0x140020f2c`
- `0x140021030`
- `0x14002115c`
- `0x140022a0c`
- `0x140022b88`
- `0x14002310c`
- `0x14002f010`
- `0x14002f440`
- `0x140046e48`
- `0x140049150`
- `0x140049884`
- `0x140049924`
- `0x14004ece8`
- `0x14004ed6c`
- `0x14005015c`
- `0x14005027c`
- `0x140050480`
- `0x140052470`
- `0x140052520`
- `0x140052574`
- `0x140053300`
- `0x140053a9c`
- `0x140053e28`
- `0x14005402c`
- `0x140060314`
- `0x140090078`
- `0x1400901c0`
- `0x14009055c`
- `0x1400906ac`
- `0x140090740`
- `0x14009141c`
- `0x1400914f4`
- `0x14009156c`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x140090d18`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140090e79`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140090f55`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140090f86`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140091317`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140090d18`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140090e79`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140090f55`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140090f86`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140091317`
- `ntoskrnl!KeReleaseGuardedMutex` at `0x140091012`
- `ntoskrnl!KeReleaseGuardedMutex` at `0x140091012`
- `ntoskrnl!ExFreePoolWithTag` at `0x14009120b`
- `ntoskrnl!ExFreePoolWithTag` at `0x14009120b`
- `ntoskrnl!KeAcquireGuardedMutex` at `0x140090fe5`
- `ntoskrnl!KeAcquireGuardedMutex` at `0x140090fe5`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140090d34`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140090e9a`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140090f6c`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140090f9d`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14009133b`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140090d34`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140090e9a`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140090f6c`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140090f9d`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14009133b`
- `ntoskrnl!KeBugCheckEx` at `0x1400912e2`
- `ntoskrnl!KeBugCheckEx` at `0x1400912e2`
- `ntoskrnl!KeInitializeGuardedMutex` at `0x140090fc5`
- `ntoskrnl!KeInitializeGuardedMutex` at `0x140090fc5`
- `ntoskrnl!ExDeleteResourceLite` at `0x1400912b1`
- `ntoskrnl!ExDeleteResourceLite` at `0x14009130b`
- `ntoskrnl!ExDeleteResourceLite` at `0x140091355`
- `ntoskrnl!ExDeleteResourceLite` at `0x1400912b1`
- `ntoskrnl!ExDeleteResourceLite` at `0x14009130b`
- `ntoskrnl!ExDeleteResourceLite` at `0x140091355`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x1400911e9`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x1400911e9`
- `ntoskrnl!ExInitializePagedLookasideList` at `0x1400909e8`
- `ntoskrnl!ExInitializePagedLookasideList` at `0x1400909e8`
- `ntoskrnl!ExDeletePagedLookasideList` at `0x1400911cf`
- `ntoskrnl!ExDeletePagedLookasideList` at `0x1400911cf`
- `ntoskrnl!ExFreePool` at `0x1400909bd`
- `ntoskrnl!ExFreePool` at `0x140090a00`
- `ntoskrnl!IoRegisterShutdownNotification` at `0x140091071`
- `ntoskrnl!IoRegisterShutdownNotification` at `0x140091071`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x140090a2e`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x140090a2e`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1400909c8`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140090a0e`
- `ntoskrnl!DbgPrint` at `0x1400913e1`
- `ntoskrnl!DbgPrint` at `0x1400913e1`
- `ntoskrnl!SeExports` at `0x140090978`
- `ntoskrnl!ExInitializeResourceLite` at `0x14009092e`
- `ntoskrnl!ExInitializeResourceLite` at `0x140090954`
- `ntoskrnl!ExInitializeResourceLite` at `0x140090aa8`
- `ntoskrnl!ExInitializeResourceLite` at `0x14009092e`
- `ntoskrnl!ExInitializeResourceLite` at `0x140090954`
- `ntoskrnl!ExInitializeResourceLite` at `0x140090aa8`
- `rdbss!RxGetRDBSSProcess` at `0x140090b81`
- `rdbss!RxGetRDBSSProcess` at `0x140090b81`
- `rdbss!RxStartMinirdr` at `0x140091124`
- `rdbss!RxStartMinirdr` at `0x140091124`
- `rdbss!RxUnregisterMinirdr` at `0x140091368`
- `rdbss!RxUnregisterMinirdr` at `0x140091368`
- `rdbss!RxRegisterMinirdr` at `0x1400908e4`
- `rdbss!RxRegisterMinirdr` at `0x1400908e4`
- `rdbss!RxRegisterLogicalMinirdr` at `0x140090ebb`
- `rdbss!RxRegisterLogicalMinirdr` at `0x140090ebb`
- `rdbss!RxDereferenceAndDeleteRxContext_Real` at `0x140091135`
- `rdbss!RxDereferenceAndDeleteRxContext_Real` at `0x140091135`
- `rdbss!RxCreateRxContext` at `0x1400910f6`
- `rdbss!RxCreateRxContext` at `0x1400910f6`

## pseudocode

```c
NTSTATUS __stdcall DriverEntry(_DRIVER_OBJECT *DriverObject, PUNICODE_STRING RegistryPath)
{
  CscLicensingQueryDWord(L"Microsoft-Windows-OfflineFiles-Core-FeatureEnabled");
  if ( CscRegistryMonitorBranchCachePolicyEnable )
  {
    CscRegistryMonitorDeleteInstance(CscRegistryMonitorBranchCachePolicyEnable);
    CscRegistryMonitorBranchCachePolicyEnable = 0;
  }
  if ( CscRegistryMonitorBranchCacheManualEnable )
  {
    CscRegistryMonitorDeleteInstance(CscRegistryMonitorBranchCacheManualEnable);
    CscRegistryMonitorBranchCacheManualEnable = 0;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 )
    WPP_SF_Dd(WPP_GLOBAL_Control->AttachedDevice, 12, WPP_0148477061aa3f6f7a18a21d9bb78afb_Traceguids, 3221226090LL, 0);
  DbgPrint("CSC driver entry failed, status = 0x%x (EE %d)\n", -1073741206, 0);
  WppCleanupKm();
  return -1073741206;
}

```

## disassembly

```asm
0x140090740  push    rbp
0x140090742  push    rbx
0x140090743  push    rsi
0x140090744  push    rdi
0x140090745  push    r12
0x140090747  push    r13
0x140090749  push    r14
0x14009074b  push    r15
0x14009074d  lea     rbp, [rsp-1Fh]
0x140090752  sub     rsp, 0F8h
0x140090759  mov     rax, cs:__security_cookie
0x140090760  xor     rax, rsp
0x140090763  mov     [rbp+57h+var_50], rax
0x140090767  xor     edi, edi
0x140090769  lea     rdx, [rsp+130h+var_E8+4]
0x14009076e  xorps   xmm0, xmm0
0x140090771  mov     dword ptr [rsp+130h+var_DC], edi
0x140090775  or      eax, 0FFFFFFFFh
0x140090778  mov     dword ptr [rsp+130h+var_DC+4], edi
0x14009077c  mov     [rbp+57h+var_AC], eax
0x14009077f  mov     r13, rcx
0x140090782  mov     [rbp+57h+var_B0], eax
0x140090785  lea     rcx, aMicrosoftWindo; "Microsoft-Windows-OfflineFiles-Core-Fea"...
0x14009078c  xor     eax, eax
0x14009078e  mov     [rbp+57h+var_B4], edi
0x140090791  xorps   xmm1, xmm1
0x140090794  mov     [rbp+57h+var_58], eax
0x140090797  movups  xmmword ptr [rbp+57h+StringIn.Length], xmm0
0x14009079b  mov     dword ptr [rbp+57h+var_DC+8], edi
0x14009079e  mov     r12d, edi
0x1400907a1  movups  [rbp+57h+var_98], xmm1
0x1400907a5  mov     dword ptr [rbp+57h+var_DC+0Ch], edi
0x1400907a8  movups  [rbp+57h+var_88], xmm0
0x1400907ac  mov     dword ptr [rbp+57h+var_CC], edi
0x1400907af  mov     dword ptr [rbp+57h+var_CC+4], edi
0x1400907b2  mov     dword ptr [rbp+57h+var_CC+0Ch], edi
0x1400907b5  mov     dword ptr [rbp+57h+var_CC+8], edi
0x1400907b8  mov     [rsp+130h+var_E0], edi
0x1400907bc  mov     [rbp+57h+var_BC], edi
0x1400907bf  mov     [rbp+57h+var_B8], edi
0x1400907c2  movups  [rbp+57h+var_78], xmm0
0x1400907c6  mov     [rsp+130h+var_EF], dil
0x1400907cb  movups  [rbp+57h+var_68], xmm0
0x1400907cf  mov     byte ptr [rsp+130h+var_E8], dil
0x1400907d4  mov     word ptr [rsp+130h+var_EC], di
0x1400907d9  mov     dword ptr [rsp+130h+var_E8+4], edi
0x1400907dd  call    CscLicensingQueryDWord
0x1400907e2  lea     esi, [rdi+1]
0x1400907e5  test    eax, eax
0x1400907e7  js      loc_140091170
0x1400907ed  cmp     dword ptr [rsp+130h+var_E8+4], esi
0x1400907f1  jnz     loc_140091170
0x1400907f7  call    CscIsOSSetupRunning
0x1400907fc  test    al, al
0x1400907fe  jz      short loc_14009080F
0x140090800  mov     ebx, 0C00000A3h
0x140090805  mov     esi, 126h
0x14009080a  jmp     loc_140091177
0x14009080f  lea     rax, WPP_ThisDir_CTLGUID_MupLog
0x140090816  mov     qword ptr cs:WPP_MAIN_CB.Type, rdi
0x14009081d  mov     cs:WPP_MAIN_CB.DriverObject, rax
0x140090824  lea     rax, WPP_MAIN_CB.DeviceExtension
0x14009082b  mov     cs:WPP_MAIN_CB.NextDevice, rax
0x140090832  lea     rax, WPP_ThisDir_CTLGUID_RFSMon
0x140090839  mov     qword ptr cs:WPP_MAIN_CB.DeviceType, rax
0x140090840  mov     cs:WPP_MAIN_CB.CurrentIrp, rdi
0x140090847  mov     cs:WPP_MAIN_CB.Timer, rsi
0x14009084e  mov     cs:WPP_MAIN_CB.DeviceExtension, rdi
0x140090855  mov     qword ptr cs:WPP_MAIN_CB.Queue, rdi
0x14009085c  mov     qword ptr cs:WPP_MAIN_CB.Queue+10h, rdi
0x140090863  mov     qword ptr cs:WPP_MAIN_CB.Queue+18h, rsi
0x14009086a  call    WppLoadTracingSupport
0x14009086f  mov     cs:WPP_MAIN_CB.CurrentIrp, rdi
0x140090876  call    WppInitKm
0x14009087b  mov     rax, cs:WPP_GLOBAL_Control
0x140090882  mov     [rsp+130h+var_F0], sil
0x140090887  mov     cl, [rax+29h]
0x14009088a  mov     r12d, [rax+2Ch]
0x14009088e  mov     dword ptr [rax+2Ch], 7FFFFFFFh
0x140090895  mov     rax, cs:WPP_GLOBAL_Control
0x14009089c  mov     [rsp+130h+var_EF], cl
0x1400908a0  mov     byte ptr [rax+29h], 7Fh
0x1400908a4  call    CscInitializeDispatchTable
0x1400908a9  mov     [rsp+130h+DeviceCharacteristics], 10h; DeviceCharacteristics
0x1400908b1  lea     rax, CscMiniRedirectorName
0x1400908b8  mov     [rsp+130h+DeviceType], 14h; DeviceType
0x1400908c0  lea     r8, WPP_MAIN_CB.Queue+30h; MrdrDispatch
0x1400908c7  mov     [rsp+130h+DeviceExtensionSize], 0AA0h; DeviceExtensionSize
0x1400908cf  lea     rcx, CscDeviceObject; DeviceObject
0x1400908d6  mov     r9d, 1F2h; Controls
0x1400908dc  mov     [rsp+130h+DeviceName], rax; DeviceName
0x1400908e1  mov     rdx, r13; DriverObject
0x1400908e4  call    cs:__imp_RxRegisterMinirdr
0x1400908eb  nop     dword ptr [rax+rax+00h]
0x1400908f0  mov     ebx, eax
0x1400908f2  test    eax, eax
0x1400908f4  jz      short loc_140090905
0x1400908f6  mov     r13b, [rsp+130h+var_F0]
0x1400908fb  mov     esi, 157h
0x140090900  jmp     loc_14009117A
0x140090905  mov     rdi, cs:CscDeviceObject
0x14009090c  xor     edx, edx; Val
0x14009090e  add     rdi, 540h
0x140090915  mov     r8d, 0A80h; Size
0x14009091b  mov     rcx, rdi; void *
0x14009091e  mov     cs:CscDevExtn, rdi
0x140090925  call    memset
0x14009092a  lea     rcx, [rdi+10h]; Resource
0x14009092e  call    cs:__imp_ExInitializeResourceLite
0x140090935  nop     dword ptr [rax+rax+00h]
0x14009093a  mov     rcx, cs:CscDevExtn
0x140090941  xor     edi, edi
0x140090943  mov     [rcx+8], rcx
0x140090947  mov     [rcx], rcx
0x14009094a  mov     [rcx+78h], edi
0x14009094d  add     rcx, 180h; Resource
0x140090954  call    cs:__imp_ExInitializeResourceLite
0x14009095b  nop     dword ptr [rax+rax+00h]
0x140090960  mov     rdx, cs:CscDevExtn
0x140090967  mov     r14b, sil
0x14009096a  lea     rax, [rdx+1E8h]
0x140090971  mov     [rax+8], rax
0x140090975  mov     [rax], rax
0x140090978  mov     rax, cs:__imp_SeExports
0x14009097f  mov     qword ptr [rdx+1F8h], 11E1A300h
0x14009098a  add     rdx, 588h
0x140090991  mov     rcx, [rax]
0x140090994  mov     rcx, [rcx+108h]; Sid
0x14009099b  call    CscBuildACL
0x1400909a0  mov     ebx, eax
0x1400909a2  test    eax, eax
0x1400909a4  jns     short loc_1400909B3
0x1400909a6  mov     esi, 16Eh
0x1400909ab  mov     r13b, r14b
0x1400909ae  jmp     loc_14009117F
0x1400909b3  mov     rcx, cs:CscDevExtn
0x1400909ba  xor     r9d, r9d; Flags
0x1400909bd  mov     r8, cs:__imp_ExFreePool; Free
0x1400909c4  sub     rcx, 0FFFFFFFFFFFFFF80h; Lookaside
0x1400909c8  mov     rdx, cs:__imp_ExAllocatePoolWithTag; Allocate
0x1400909cf  mov     r14b, 3
0x1400909d2  mov     word ptr [rsp+130h+DeviceType], di; Depth
0x1400909d7  mov     [rsp+130h+DeviceExtensionSize], 43637343h; Tag
0x1400909df  mov     [rsp+130h+DeviceName], 220h; Size
0x1400909e8  call    cs:__imp_ExInitializePagedLookasideList
0x1400909ef  nop     dword ptr [rax+rax+00h]
0x1400909f4  mov     rcx, cs:CscDevExtn
0x1400909fb  mov     esi, 200h
0x140090a00  mov     r8, cs:__imp_ExFreePool; Free
0x140090a07  add     rcx, 100h; Lookaside
0x140090a0e  mov     rdx, cs:__imp_ExAllocatePoolWithTag; Allocate
0x140090a15  mov     r9d, esi; Flags
0x140090a18  mov     word ptr [rsp+130h+DeviceType], di; Depth
0x140090a1d  mov     [rsp+130h+DeviceExtensionSize], 43504C43h; int
0x140090a25  mov     [rsp+130h+DeviceName], 0C0h; Size
0x140090a2e  call    cs:__imp_ExInitializeNPagedLookasideList
0x140090a35  nop     dword ptr [rax+rax+00h]
0x140090a3a  mov     rcx, cs:CscDevExtn
0x140090a41  mov     r15b, byte ptr [rsp+130h+var_EC+1]
0x140090a46  add     rcx, 300h
0x140090a4d  or      r15b, 1
0x140090a51  call    CscPathPrefixInit
0x140090a56  mov     ebx, eax
0x140090a58  test    eax, eax
0x140090a5a  jns     short loc_140090A6B
0x140090a5c  mov     esi, 18Ah
0x140090a61  mov     r13b, [rsp+130h+var_F0]
0x140090a66  jmp     loc_140091184
0x140090a6b  mov     rcx, cs:CscDevExtn
0x140090a72  or      r15b, 2
0x140090a76  add     rcx, 440h
0x140090a7d  call    CscPathPrefixInit
0x140090a82  mov     ebx, eax
0x140090a84  test    eax, eax
0x140090a86  jns     short loc_140090A8F
0x140090a88  mov     esi, 18Fh
0x140090a8d  jmp     short loc_140090A61
0x140090a8f  mov     rcx, cs:CscDevExtn
0x140090a96  add     rcx, 9E8h; Resource
0x140090a9d  lea     rax, [rcx+68h]
0x140090aa1  mov     [rax+8], rax
0x140090aa5  mov     [rax], rax
0x140090aa8  call    cs:__imp_ExInitializeResourceLite
0x140090aaf  nop     dword ptr [rax+rax+00h]
0x140090ab4  mov     rax, cs:CscDeviceObject
0x140090abb  lea     rcx, WPP_MAIN_CB.Queue+30h
0x140090ac2  xorps   xmm0, xmm0
0x140090ac5  mov     [rsp+130h+var_EC], edi
0x140090ac9  lea     rdx, [rsp+130h+var_EC]
0x140090ace  or      r15b, 0Ch
0x140090ad2  mov     [rax+160h], rcx
0x140090ad9  lea     rcx, aMicrosoftWindo_0; "Microsoft-Windows-OfflineFiles-Core-Bra"...
0x140090ae0  mov     rax, cs:CscDevExtn
0x140090ae7  movdqu  cs:g_CscPolicyData, xmm0
0x140090aef  mov     [rax+9B1h], dil
0x140090af6  call    CscLicensingQueryDWord
0x140090afb  test    eax, eax
0x140090afd  js      short loc_140090B13
0x140090aff  cmp     [rsp+130h+var_EC], edi
0x140090b03  jz      short loc_140090B13
0x140090b05  mov     rax, cs:CscDevExtn
0x140090b0c  mov     byte ptr [rax+9B1h], 1
0x140090b13  call    CscRegistryInitializeParams
0x140090b18  mov     ebx, eax
0x140090b1a  test    eax, eax
0x140090b1c  jns     short loc_140090B28
0x140090b1e  mov     esi, 1A4h
0x140090b23  jmp     loc_140090A61
0x140090b28  lea     rdx, [rbp+57h+StringIn]
0x140090b2c  xor     ecx, ecx
0x140090b2e  mov     r14b, 7
0x140090b31  call    CscRegistryGetValue
0x140090b36  mov     ebx, eax
0x140090b38  test    eax, eax
0x140090b3a  jns     short loc_140090B46
0x140090b3c  mov     esi, 1ABh
0x140090b41  jmp     loc_140090A61
0x140090b46  mov     rcx, cs:WPP_GLOBAL_Control
0x140090b4d  lea     rax, WPP_GLOBAL_Control
0x140090b54  cmp     rcx, rax
0x140090b57  jz      short loc_140090B81
0x140090b59  mov     eax, [rcx+2Ch]
0x140090b5c  test    al, 40h
0x140090b5e  jz      short loc_140090B81
0x140090b60  mov     rcx, [rcx+18h]
0x140090b64  lea     rax, [rbp+57h+StringIn]
0x140090b68  mov     edx, 0Ah
0x140090b6d  mov     [rsp+130h+DeviceName], rax
0x140090b72  mov     r9, r13
0x140090b75  lea     r8, WPP_0148477061aa3f6f7a18a21d9bb78afb_Traceguids
0x140090b7c  call    WPP_SF_qZ
0x140090b81  call    cs:__imp_RxGetRDBSSProcess
0x140090b88  nop     dword ptr [rax+rax+00h]
0x140090b8d  mov     rcx, rax
0x140090b90  call    CscStoreInitialize
0x140090b95  mov     ebx, eax
0x140090b97  test    eax, eax
0x140090b99  jz      short loc_140090BA5
0x140090b9b  mov     esi, 1BBh
0x140090ba0  jmp     loc_140090A61
0x140090ba5  lea     rdx, [rsp+130h+var_DC]
0x140090baa  mov     ecx, 2
0x140090baf  mov     r14b, 0Fh
0x140090bb2  call    CscRegistryGetValueAsULong
0x140090bb7  mov     ebx, eax
0x140090bb9  test    eax, eax
0x140090bbb  jns     short loc_140090BC7
0x140090bbd  mov     esi, 1C8h
0x140090bc2  jmp     loc_140090A61
0x140090bc7  lea     rdx, [rsp+130h+var_DC+4]
0x140090bcc  mov     ecx, 3
0x140090bd1  call    CscRegistryGetValueAsULong
0x140090bd6  mov     ebx, eax
0x140090bd8  test    eax, eax
0x140090bda  jns     short loc_140090BE6
0x140090bdc  mov     esi, 1CDh
0x140090be1  jmp     loc_140090A61
0x140090be6  lea     rdx, [rbp+57h+var_B4]
0x140090bea  mov     ecx, 4
0x140090bef  call    CscRegistryGetValueAsULong
0x140090bf4  mov     ebx, eax
0x140090bf6  test    eax, eax
0x140090bf8  jns     short loc_140090C04
0x140090bfa  mov     esi, 1D3h
0x140090bff  jmp     loc_140090A61
0x140090c04  lea     rdx, [rbp+57h+var_DC+8]
0x140090c08  mov     ecx, 5
0x140090c0d  call    CscRegistryGetValueAsULong
0x140090c12  mov     ebx, eax
0x140090c14  test    eax, eax
0x140090c16  jns     short loc_140090C22
0x140090c18  mov     esi, 1D8h
0x140090c1d  jmp     loc_140090A61
0x140090c22  lea     rdx, [rbp+57h+var_DC+0Ch]
0x140090c26  mov     ecx, 6
0x140090c2b  call    CscRegistryGetValueAsULong
0x140090c30  mov     ebx, eax
0x140090c32  test    eax, eax
0x140090c34  jns     short loc_140090C40
0x140090c36  mov     esi, 1DDh
0x140090c3b  jmp     loc_140090A61
0x140090c40  lea     rdx, [rbp+57h+var_CC]
0x140090c44  mov     ecx, 7
0x140090c49  call    CscRegistryGetValueAsULong
0x140090c4e  mov     ebx, eax
0x140090c50  test    eax, eax
0x140090c52  jns     short loc_140090C5E
0x140090c54  mov     esi, 1E2h
0x140090c59  jmp     loc_140090A61
0x140090c5e  lea     rdx, [rbp+57h+var_CC+4]
0x140090c62  mov     ecx, 8
0x140090c67  call    CscRegistryGetValueAsULong
0x140090c6c  mov     ebx, eax
0x140090c6e  test    eax, eax
0x140090c70  jns     short loc_140090C7C
0x140090c72  mov     esi, 1E7h
0x140090c77  jmp     loc_140090A61
0x140090c7c  lea     rdx, [rbp+57h+var_CC+8]
0x140090c80  mov     ecx, 9
0x140090c85  call    CscRegistryGetValueAsULong
  ... truncated ...
```
