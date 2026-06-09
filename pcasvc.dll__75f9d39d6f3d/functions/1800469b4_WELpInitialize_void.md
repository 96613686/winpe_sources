# WELpInitialize(void)

- ea: `0x1800469b4`
- end: `0x180046d52`
- name: `?WELpInitialize@@YAKXZ`
- size: `926`
- prototype: `unsigned int(void)`
- caller_count: `2`
- callee_count: `10`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18009b990`
- `0x18009bc20`

## callees

- `0x180012920`
- `0x18002f7b0`
- `0x18002f860`
- `0x18003859c`
- `0x1800469b4`
- `0x18007a9cf`
- `0x18009bca4`
- `0x18009c2bc`
- `0x18009c2fc`
- `0x1800f1f10`

## import_xrefs

- `ntdll!RtlPublishWnfStateData` at `0x180046a8f`
- `ntdll!RtlPublishWnfStateData` at `0x180046a8f`
- `ntdll!RtlSubscribeWnfStateChangeNotification` at `0x180046b05`
- `ntdll!RtlSubscribeWnfStateChangeNotification` at `0x180046b53`
- `ntdll!RtlSubscribeWnfStateChangeNotification` at `0x180046ba4`
- `ntdll!RtlSubscribeWnfStateChangeNotification` at `0x180046c1e`
- `ntdll!RtlSubscribeWnfStateChangeNotification` at `0x180046c75`
- `ntdll!RtlSubscribeWnfStateChangeNotification` at `0x180046cdf`
- `ntdll!RtlSubscribeWnfStateChangeNotification` at `0x180046b05`
- `ntdll!RtlSubscribeWnfStateChangeNotification` at `0x180046b53`
- `ntdll!RtlSubscribeWnfStateChangeNotification` at `0x180046ba4`
- `ntdll!RtlSubscribeWnfStateChangeNotification` at `0x180046c1e`
- `ntdll!RtlSubscribeWnfStateChangeNotification` at `0x180046c75`
- `ntdll!RtlSubscribeWnfStateChangeNotification` at `0x180046cdf`
- `ntdll!RtlNtStatusToDosError` at `0x180046abc`
- `ntdll!RtlNtStatusToDosError` at `0x180046bd1`
- `ntdll!RtlNtStatusToDosError` at `0x180046abc`
- `ntdll!RtlNtStatusToDosError` at `0x180046bd1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180046d2e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180046d2e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180046a50`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180046a50`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180046a0b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180046cfd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180046a0b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180046cfd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180046a43`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180046a43`

## pseudocode

```c
__int64 WELpInitialize(void)
{
  int UserToken; // eax
  NTSTATUS v2; // ebx
  const char *v3; // r9
  int v4; // r8d
  ULONG v5; // ebx
  NTSTATUS v6; // edi
  int v7; // r8d
  const char *v8; // r9
  HANDLE hObject; // [rsp+40h] [rbp-328h] BYREF
  _BYTE v10[736]; // [rsp+50h] [rbp-318h] BYREF

  hObject = 0;
  memset_0(v10, 0, 0x2D4u);
  if ( (unsigned int)UddpIsSystemSetupInProgress() )
    return 0;
  UserToken = GetUserToken(&hObject);
  if ( UserToken < 0 )
  {
    GetCurrentProcessId();
    AslLogCallPrintf(
      3,
      (unsigned int)"WELpInitialize",
      475,
      (unsigned int)"WEL: No interactive user. Skip initializing WNF listener %d");
    return 0;
  }
  if ( UserToken != 1 )
    CloseHandle(hObject);
  EnterCriticalSection(&g_WELpLock);
  if ( g_WELpInitialized )
    goto LABEL_37;
  TraceLoggingRegisterEx_EventRegister_EventSetInformation(&dword_180155A90);
  g_WELpInitialized = 1;
  v2 = RtlPublishWnfStateData(WNF_CMPT_BLOCKED_APP, 0, v10, 724, 0);
  if ( v2 >= 0 )
  {
    if ( !WELpWnfPplBlockSubscription )
    {
      if ( (unsigned int)WELpIsClientSKU() )
      {
        v2 = RtlSubscribeWnfStateChangeNotification(
               &WELpWnfPplBlockSubscription,
               WNF_CI_LSAPPL_DLL_LOAD_FAILURE,
               0,
               WEL_PplBlockWnf,
               0,
               0,
               0,
               0);
        if ( v2 < 0 )
        {
          v3 = "Failed to subscribe to WNF for PPL block %x";
          v4 = 528;
          goto LABEL_10;
        }
      }
    }
    if ( !WELpWnfBlockedAppSubscription )
    {
      v2 = RtlSubscribeWnfStateChangeNotification(
             &WELpWnfBlockedAppSubscription,
             WNF_CMPT_BLOCKED_APP,
             0,
             WEL_BlockedAppWnf,
             0,
             0,
             0,
             0);
      if ( v2 < 0 )
      {
        v3 = "Failed to subscribe to WNF for blocked app %x";
        v4 = 548;
        goto LABEL_10;
      }
    }
    if ( !WELpWnfBlockedDriverSubscription )
    {
      v6 = RtlSubscribeWnfStateChangeNotification(
             &WELpWnfBlockedDriverSubscription,
             WNF_CI_BLOCKED_DRIVER,
             0,
             WEL_BlockedDriverWnf,
             0,
             0,
             0,
             0);
      if ( v6 < 0 )
      {
        v7 = 568;
LABEL_21:
        v8 = "Failed to subscribe to WNF for blocked driver %x";
        goto LABEL_22;
      }
    }
    if ( !WELpWnfCiImageIncompatibleSubscription )
    {
      v6 = RtlSubscribeWnfStateChangeNotification(
             &WELpWnfCiImageIncompatibleSubscription,
             WNF_CI_HVCI_IMAGE_INCOMPATIBLE,
             0,
             WEL_BlockedDriverWnf,
             0,
             0,
             0,
             0);
      if ( v6 < 0 )
      {
        v7 = 591;
        goto LABEL_21;
      }
    }
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_WhqlOnlyAllowBlockToasts>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_WhqlOnlyAllowBlockToasts>::GetImpl'::`2'::impl) )
    {
      if ( !WELpWnfCiBlockedDriverWhqlOnlySubscription )
      {
        v6 = ((__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _DWORD))RtlSubscribeWnfStateChangeNotification)(
               &WELpWnfCiBlockedDriverWhqlOnlySubscription,
               WNF_CI_BLOCKED_DRIVER_WHQLONLY,
               0,
               WEL_BlockedDriverWhqlOnlyWnf,
               0,
               0,
               0,
               0);
        if ( v6 < 0 )
        {
          v8 = "Failed to subscribe to WNF for WhqlOnly blocked driver %x";
          v7 = 615;
LABEL_22:
          AslLogCallPrintf(1, (unsigned int)"WELpInitialize", v7, (_DWORD)v8);
          v5 = RtlNtStatusToDosError(v6);
          if ( v5 == 317 )
            v5 = v6;
          goto LABEL_38;
        }
      }
    }
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_PcaUiArmUpdate>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_PcaUiArmUpdate>::GetImpl'::`2'::impl) )
    {
      if ( !WELpWnfDriverArchSubscription )
      {
        if ( (unsigned int)WELpIsClientSKU() )
        {
          v2 = RtlSubscribeWnfStateChangeNotification(
                 &WELpWnfDriverArchSubscription,
                 WNF_PNPF_DRIVER_NO_NATIVE_ARCHITECTURE_SUPPORT,
                 0,
                 WEL_DriverArchWnf,
                 0,
                 0,
                 0,
                 0);
          if ( v2 < 0 )
          {
            v3 = "Failed to subscribe to WNF for driver arch notification %x";
            v4 = 643;
            goto LABEL_10;
          }
        }
      }
    }
    GetCurrentProcessId();
    AslLogCallPrintf(3, (unsigned int)"WELpInitialize", 649, (unsigned int)"WEL: Initialized WNF listener %d");
LABEL_37:
    v5 = 0;
    goto LABEL_38;
  }
  v3 = "RtlPublishWnfStateData failed, 0x%x";
  v4 = 506;
LABEL_10:
  AslLogCallPrintf(1, (unsigned int)"WELpInitialize", v4, (_DWORD)v3);
  v5 = RtlNtStatusToDosError(v2);
LABEL_38:
  LeaveCriticalSection(&g_WELpLock);
  return v5;
}

```

## disassembly

```asm
0x1800469b4  push    rbx
0x1800469b6  push    rbp
0x1800469b7  push    rsi
0x1800469b8  push    rdi
0x1800469b9  sub     rsp, 348h
0x1800469c0  mov     rax, cs:__security_cookie
0x1800469c7  xor     rax, rsp
0x1800469ca  mov     [rsp+368h+var_38], rax
0x1800469d2  mov     ebx, 2D4h
0x1800469d7  lea     rcx, [rsp+368h+var_318]; void *
0x1800469dc  xor     esi, esi
0x1800469de  mov     r8d, ebx; Size
0x1800469e1  xor     edx, edx; Val
0x1800469e3  mov     [rsp+368h+hObject], rsi
0x1800469e8  call    memset_0
0x1800469ed  call    UddpIsSystemSetupInProgress
0x1800469f2  test    eax, eax
0x1800469f4  jz      short loc_1800469FD
0x1800469f6  xor     eax, eax
0x1800469f8  jmp     loc_180046D36
0x1800469fd  lea     rcx, [rsp+368h+hObject]; phToken
0x180046a02  call    ?GetUserToken@@YAJAEAPEAX@Z; GetUserToken(void * &)
0x180046a07  test    eax, eax
0x180046a09  jns     short loc_180046A35
0x180046a0b  call    cs:__imp_GetCurrentProcessId
0x180046a11  lea     r9, aWelNoInteracti; "WEL: No interactive user. Skip initiali"...
0x180046a18  mov     r8d, 1DBh
0x180046a1e  lea     rdx, aWelpinitialize; "WELpInitialize"
0x180046a25  mov     dword ptr [rsp+368h+var_348], eax
0x180046a29  mov     ecx, 3
0x180046a2e  call    AslLogCallPrintf
0x180046a33  jmp     short loc_1800469F6
0x180046a35  mov     ebp, 1
0x180046a3a  cmp     eax, ebp
0x180046a3c  jz      short loc_180046A49
0x180046a3e  mov     rcx, [rsp+368h+hObject]; hObject
0x180046a43  call    cs:__imp_CloseHandle
0x180046a49  lea     rcx, ?g_WELpLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180046a50  call    cs:__imp_EnterCriticalSection
0x180046a56  cmp     cs:?g_WELpInitialized@@3HA, esi; int g_WELpInitialized
0x180046a5c  jnz     loc_180046D25
0x180046a62  xor     r8d, r8d
0x180046a65  lea     rcx, dword_180155A90; CallbackContext
0x180046a6c  xor     edx, edx
0x180046a6e  call    TraceLoggingRegisterEx_EventRegister_EventSetInformation
0x180046a73  mov     rcx, cs:WNF_CMPT_BLOCKED_APP
0x180046a7a  lea     r8, [rsp+368h+var_318]
0x180046a7f  mov     r9d, ebx
0x180046a82  mov     cs:?g_WELpInitialized@@3HA, ebp; int g_WELpInitialized
0x180046a88  xor     edx, edx
0x180046a8a  mov     [rsp+368h+var_348], rsi
0x180046a8f  call    cs:__imp_RtlPublishWnfStateData
0x180046a95  mov     ebx, eax
0x180046a97  test    eax, eax
0x180046a99  jns     short loc_180046AC9
0x180046a9b  lea     r9, aRtlpublishwnfs; "RtlPublishWnfStateData failed, 0x%x"
0x180046aa2  mov     r8d, 1FAh
0x180046aa8  lea     rdx, aWelpinitialize; "WELpInitialize"
0x180046aaf  mov     dword ptr [rsp+368h+var_348], ebx
0x180046ab3  mov     ecx, ebp
0x180046ab5  call    AslLogCallPrintf
0x180046aba  mov     ecx, ebx; Status
0x180046abc  call    cs:__imp_RtlNtStatusToDosError
0x180046ac2  mov     ebx, eax
0x180046ac4  jmp     loc_180046D27
0x180046ac9  cmp     cs:?WELpWnfPplBlockSubscription@@3PEAU_WNF_USER_SUBSCRIPTION@@EA, rsi; _WNF_USER_SUBSCRIPTION * WELpWnfPplBlockSubscription
0x180046ad0  jnz     short loc_180046B20
0x180046ad2  call    ?WELpIsClientSKU@@YAHXZ; WELpIsClientSKU(void)
0x180046ad7  test    eax, eax
0x180046ad9  jz      short loc_180046B20
0x180046adb  mov     rdx, cs:WNF_CI_LSAPPL_DLL_LOAD_FAILURE
0x180046ae2  lea     r9, ?WEL_PplBlockWnf@@YAJU_WNF_STATE_NAME@@KPEAU_WNF_TYPE_ID@@PEAXPEBXK@Z; WEL_PplBlockWnf(_WNF_STATE_NAME,ulong,_WNF_TYPE_ID *,void *,void const *,ulong)
0x180046ae9  mov     [rsp+368h+var_330], esi
0x180046aed  lea     rcx, ?WELpWnfPplBlockSubscription@@3PEAU_WNF_USER_SUBSCRIPTION@@EA; _WNF_USER_SUBSCRIPTION * WELpWnfPplBlockSubscription
0x180046af4  mov     [rsp+368h+var_338], esi
0x180046af8  xor     r8d, r8d
0x180046afb  mov     [rsp+368h+var_340], rsi
0x180046b00  mov     [rsp+368h+var_348], rsi
0x180046b05  call    cs:__imp_RtlSubscribeWnfStateChangeNotification
0x180046b0b  mov     ebx, eax
0x180046b0d  test    eax, eax
0x180046b0f  jns     short loc_180046B20
0x180046b11  lea     r9, aFailedToSubscr_3; "Failed to subscribe to WNF for PPL bloc"...
0x180046b18  mov     r8d, 210h
0x180046b1e  jmp     short loc_180046AA8
0x180046b20  cmp     cs:?WELpWnfBlockedAppSubscription@@3PEAU_WNF_USER_SUBSCRIPTION@@EA, rsi; _WNF_USER_SUBSCRIPTION * WELpWnfBlockedAppSubscription
0x180046b27  jnz     short loc_180046B71
0x180046b29  mov     rdx, cs:WNF_CMPT_BLOCKED_APP
0x180046b30  lea     r9, ?WEL_BlockedAppWnf@@YAJU_WNF_STATE_NAME@@KPEAU_WNF_TYPE_ID@@PEAXPEBXK@Z; WEL_BlockedAppWnf(_WNF_STATE_NAME,ulong,_WNF_TYPE_ID *,void *,void const *,ulong)
0x180046b37  mov     [rsp+368h+var_330], esi
0x180046b3b  lea     rcx, ?WELpWnfBlockedAppSubscription@@3PEAU_WNF_USER_SUBSCRIPTION@@EA; _WNF_USER_SUBSCRIPTION * WELpWnfBlockedAppSubscription
0x180046b42  mov     [rsp+368h+var_338], esi
0x180046b46  xor     r8d, r8d
0x180046b49  mov     [rsp+368h+var_340], rsi
0x180046b4e  mov     [rsp+368h+var_348], rsi
0x180046b53  call    cs:__imp_RtlSubscribeWnfStateChangeNotification
0x180046b59  mov     ebx, eax
0x180046b5b  test    eax, eax
0x180046b5d  jns     short loc_180046B71
0x180046b5f  lea     r9, aFailedToSubscr_4; "Failed to subscribe to WNF for blocked "...
0x180046b66  mov     r8d, 224h
0x180046b6c  jmp     loc_180046AA8
0x180046b71  cmp     cs:?WELpWnfBlockedDriverSubscription@@3PEAU_WNF_USER_SUBSCRIPTION@@EA, rsi; _WNF_USER_SUBSCRIPTION * WELpWnfBlockedDriverSubscription
0x180046b78  jnz     short loc_180046BEB
0x180046b7a  mov     rdx, cs:WNF_CI_BLOCKED_DRIVER
0x180046b81  lea     r9, ?WEL_BlockedDriverWnf@@YAJU_WNF_STATE_NAME@@KPEAU_WNF_TYPE_ID@@PEAXPEBXK@Z; WEL_BlockedDriverWnf(_WNF_STATE_NAME,ulong,_WNF_TYPE_ID *,void *,void const *,ulong)
0x180046b88  mov     [rsp+368h+var_330], esi
0x180046b8c  lea     rcx, ?WELpWnfBlockedDriverSubscription@@3PEAU_WNF_USER_SUBSCRIPTION@@EA; _WNF_USER_SUBSCRIPTION * WELpWnfBlockedDriverSubscription
0x180046b93  mov     [rsp+368h+var_338], esi
0x180046b97  xor     r8d, r8d
0x180046b9a  mov     [rsp+368h+var_340], rsi
0x180046b9f  mov     [rsp+368h+var_348], rsi
0x180046ba4  call    cs:__imp_RtlSubscribeWnfStateChangeNotification
0x180046baa  mov     edi, eax
0x180046bac  test    eax, eax
0x180046bae  jns     short loc_180046BEB
0x180046bb0  mov     r8d, 238h
0x180046bb6  lea     r9, aFailedToSubscr_6; "Failed to subscribe to WNF for blocked "...
0x180046bbd  lea     rdx, aWelpinitialize; "WELpInitialize"
0x180046bc4  mov     dword ptr [rsp+368h+var_348], edi
0x180046bc8  mov     ecx, ebp
0x180046bca  call    AslLogCallPrintf
0x180046bcf  mov     ecx, edi; Status
0x180046bd1  call    cs:__imp_RtlNtStatusToDosError
0x180046bd7  mov     ebx, eax
0x180046bd9  cmp     eax, 13Dh
0x180046bde  jnz     loc_180046D27
0x180046be4  mov     ebx, edi
0x180046be6  jmp     loc_180046D27
0x180046beb  cmp     cs:?WELpWnfCiImageIncompatibleSubscription@@3PEAU_WNF_USER_SUBSCRIPTION@@EA, rsi; _WNF_USER_SUBSCRIPTION * WELpWnfCiImageIncompatibleSubscription
0x180046bf2  jnz     short loc_180046C32
0x180046bf4  mov     rdx, cs:WNF_CI_HVCI_IMAGE_INCOMPATIBLE
0x180046bfb  lea     r9, ?WEL_BlockedDriverWnf@@YAJU_WNF_STATE_NAME@@KPEAU_WNF_TYPE_ID@@PEAXPEBXK@Z; WEL_BlockedDriverWnf(_WNF_STATE_NAME,ulong,_WNF_TYPE_ID *,void *,void const *,ulong)
0x180046c02  mov     [rsp+368h+var_330], esi
0x180046c06  lea     rcx, ?WELpWnfCiImageIncompatibleSubscription@@3PEAU_WNF_USER_SUBSCRIPTION@@EA; _WNF_USER_SUBSCRIPTION * WELpWnfCiImageIncompatibleSubscription
0x180046c0d  mov     [rsp+368h+var_338], esi
0x180046c11  xor     r8d, r8d
0x180046c14  mov     [rsp+368h+var_340], rsi
0x180046c19  mov     [rsp+368h+var_348], rsi
0x180046c1e  call    cs:__imp_RtlSubscribeWnfStateChangeNotification
0x180046c24  mov     edi, eax
0x180046c26  test    eax, eax
0x180046c28  jns     short loc_180046C32
0x180046c2a  mov     r8d, 24Fh
0x180046c30  jmp     short loc_180046BB6
0x180046c32  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_WhqlOnlyAllowBlockToasts@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_WhqlOnlyAllowBlockToasts@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_WhqlOnlyAllowBlockToasts> `wil::Feature<__WilFeatureTraits_Feature_Servicing_WhqlOnlyAllowBlockToasts>::GetImpl(void)'::`2'::impl
0x180046c39  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_WhqlOnlyAllowBlockToasts@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_WhqlOnlyAllowBlockToasts>::__private_IsEnabled(void)
0x180046c3e  test    al, al
0x180046c40  jz      short loc_180046C93
0x180046c42  cmp     cs:?WELpWnfCiBlockedDriverWhqlOnlySubscription@@3PEAU_WNF_USER_SUBSCRIPTION@@EA, rsi; _WNF_USER_SUBSCRIPTION * WELpWnfCiBlockedDriverWhqlOnlySubscription
0x180046c49  jnz     short loc_180046C93
0x180046c4b  mov     rdx, qword ptr cs:WNF_CI_BLOCKED_DRIVER_WHQLONLY.Data
0x180046c52  lea     r9, ?WEL_BlockedDriverWhqlOnlyWnf@@YAJU_WNF_STATE_NAME@@KPEAU_WNF_TYPE_ID@@PEAXPEBXK@Z; WEL_BlockedDriverWhqlOnlyWnf(_WNF_STATE_NAME,ulong,_WNF_TYPE_ID *,void *,void const *,ulong)
0x180046c59  mov     [rsp+368h+var_330], esi
0x180046c5d  lea     rcx, ?WELpWnfCiBlockedDriverWhqlOnlySubscription@@3PEAU_WNF_USER_SUBSCRIPTION@@EA; _WNF_USER_SUBSCRIPTION * WELpWnfCiBlockedDriverWhqlOnlySubscription
0x180046c64  mov     [rsp+368h+var_338], esi
0x180046c68  xor     r8d, r8d
0x180046c6b  mov     [rsp+368h+var_340], rsi
0x180046c70  mov     [rsp+368h+var_348], rsi
0x180046c75  call    cs:__imp_RtlSubscribeWnfStateChangeNotification
0x180046c7b  mov     edi, eax
0x180046c7d  test    eax, eax
0x180046c7f  jns     short loc_180046C93
0x180046c81  lea     r9, aFailedToSubscr_1; "Failed to subscribe to WNF for WhqlOnly"...
0x180046c88  mov     r8d, 267h
0x180046c8e  jmp     loc_180046BBD
0x180046c93  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_PcaUiArmUpdate@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_PcaUiArmUpdate@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PcaUiArmUpdate> `wil::Feature<__WilFeatureTraits_Feature_PcaUiArmUpdate>::GetImpl(void)'::`2'::impl
0x180046c9a  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_PcaUiArmUpdate@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PcaUiArmUpdate>::__private_IsEnabled(void)
0x180046c9f  test    al, al
0x180046ca1  jz      short loc_180046CFD
0x180046ca3  cmp     cs:?WELpWnfDriverArchSubscription@@3PEAU_WNF_USER_SUBSCRIPTION@@EA, rsi; _WNF_USER_SUBSCRIPTION * WELpWnfDriverArchSubscription
0x180046caa  jnz     short loc_180046CFD
0x180046cac  call    ?WELpIsClientSKU@@YAHXZ; WELpIsClientSKU(void)
0x180046cb1  test    eax, eax
0x180046cb3  jz      short loc_180046CFD
0x180046cb5  mov     rdx, cs:WNF_PNPF_DRIVER_NO_NATIVE_ARCHITECTURE_SUPPORT
0x180046cbc  lea     r9, ?WEL_DriverArchWnf@@YAJU_WNF_STATE_NAME@@KPEAU_WNF_TYPE_ID@@PEAXPEBXK@Z; WEL_DriverArchWnf(_WNF_STATE_NAME,ulong,_WNF_TYPE_ID *,void *,void const *,ulong)
0x180046cc3  mov     [rsp+368h+var_330], esi
0x180046cc7  lea     rcx, ?WELpWnfDriverArchSubscription@@3PEAU_WNF_USER_SUBSCRIPTION@@EA; _WNF_USER_SUBSCRIPTION * WELpWnfDriverArchSubscription
0x180046cce  mov     [rsp+368h+var_338], esi
0x180046cd2  xor     r8d, r8d
0x180046cd5  mov     [rsp+368h+var_340], rsi
0x180046cda  mov     [rsp+368h+var_348], rsi
0x180046cdf  call    cs:__imp_RtlSubscribeWnfStateChangeNotification
0x180046ce5  mov     ebx, eax
0x180046ce7  test    eax, eax
0x180046ce9  jns     short loc_180046CFD
0x180046ceb  lea     r9, aFailedToSubscr_2; "Failed to subscribe to WNF for driver a"...
0x180046cf2  mov     r8d, 283h
0x180046cf8  jmp     loc_180046AA8
0x180046cfd  call    cs:__imp_GetCurrentProcessId
0x180046d03  lea     r9, aWelInitialized; "WEL: Initialized WNF listener %d"
0x180046d0a  mov     r8d, 289h
0x180046d10  lea     rdx, aWelpinitialize; "WELpInitialize"
0x180046d17  mov     dword ptr [rsp+368h+var_348], eax
0x180046d1b  mov     ecx, 3
0x180046d20  call    AslLogCallPrintf
0x180046d25  mov     ebx, esi
0x180046d27  lea     rcx, ?g_WELpLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180046d2e  call    cs:__imp_LeaveCriticalSection
0x180046d34  mov     eax, ebx
0x180046d36  mov     rcx, [rsp+368h+var_38]
0x180046d3e  xor     rcx, rsp; StackCookie
0x180046d41  call    __security_check_cookie
0x180046d46  add     rsp, 348h
0x180046d4d  pop     rdi
0x180046d4e  pop     rsi
0x180046d4f  pop     rbp
0x180046d50  pop     rbx
0x180046d51  retn
```
