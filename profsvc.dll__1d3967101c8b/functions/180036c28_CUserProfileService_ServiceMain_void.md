# CUserProfileService::ServiceMain(void)

- ea: `0x180036c28`
- end: `0x180036ee4`
- name: `?ServiceMain@CUserProfileService@@QEAAJXZ`
- size: `700`
- prototype: `__int64 __fastcall(CUserProfileService *__hidden this)`
- caller_count: `1`
- callee_count: `17`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180036ac0`

## callees

- `0x180019afc`
- `0x180021ca0`
- `0x180023d74`
- `0x180024bf0`
- `0x1800253dc`
- `0x1800265ac`
- `0x18002d2d8`
- `0x18002db38`
- `0x1800321f4`
- `0x180036c28`
- `0x180037a80`
- `0x18003a730`
- `0x18003c118`
- `0x18003cea8`
- `0x180048d0c`
- `0x18004c0a0`
- `0x18004c0cc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180036ebc`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180036ebc`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x180036dd9`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x180036dd9`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroupMembers` at `0x180036e47`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroupMembers` at `0x180036e47`
- `USERENV!RegisterGPNotification` at `0x180036d74`
- `USERENV!RegisterGPNotification` at `0x180036d74`
- `USERENV!UnregisterGPNotification` at `0x180036de6`
- `USERENV!UnregisterGPNotification` at `0x180036de6`
- `api-ms-win-service-winsvc-l1-1-0!RegisterServiceCtrlHandlerW` at `0x180036c67`
- `api-ms-win-service-winsvc-l1-1-0!RegisterServiceCtrlHandlerW` at `0x180036c67`
- `ext-ms-win-profile-profsvc-l1-1-0!RefreshSuspendFolderPolicyAndUploadTaskConfig` at `0x180036dbe`
- `ext-ms-win-profile-profsvc-l1-1-0!RefreshSuspendFolderPolicyAndUploadTaskConfig` at `0x180036dbe`
- `ext-ms-win-profile-profsvc-l1-1-0!StopRoamingClassFactories` at `0x180036e0a`
- `ext-ms-win-profile-profsvc-l1-1-0!StopRoamingClassFactories` at `0x180036e0a`

## string_xrefs

- `0x180036c7d`: `onecore\ds\security\gina\profile\profsvc\service.cpp`
- `0x180036ccc`: `onecore\ds\security\gina\profile\profsvc\service.cpp`
- `0x180036d5b`: `onecore\ds\security\gina\profile\profsvc\service.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CUserProfileService::ServiceMain(CUserProfileService *this)
{
  LPCRITICAL_SECTION v1; // rdi
  SERVICE_STATUS_HANDLE v2; // rax
  const char *v3; // r9
  unsigned int LastError; // ebx
  int started; // eax
  int v7; // ecx
  int v8; // r8d
  int event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z; // eax
  int LastErrorFailHr; // esi
  HANDLE v11; // rbx
  wil::details *v12; // rcx
  DWORD v13; // eax
  __int64 v14; // rcx
  __int64 v15; // rcx
  unsigned int v16; // edx
  struct _TP_CLEANUP_GROUP *OwningThread; // rcx
  int v18; // ecx
  int v19; // r8d
  DWORD v20; // eax
  unsigned int v21; // r8d
  const char *v22; // r9
  int bAlertable; // [rsp+20h] [rbp-48h]
  HANDLE hEvent; // [rsp+30h] [rbp-38h] BYREF
  char v25; // [rsp+38h] [rbp-30h]
  HANDLE Handles[3]; // [rsp+40h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+30h]

  v1 = g_pUPSvc;
  wil::EnterCriticalSection(&hEvent, g_pUPSvc);
  v2 = RegisterServiceCtrlHandlerW(L"ProfSvc", UserProfileServiceHandler);
  v1[3].OwningThread = v2;
  if ( !v2 )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0xE9,
                  (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\service.cpp",
                  v3);
LABEL_3:
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>(&hEvent);
    return LastError;
  }
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>(&hEvent);
  hEvent = v1;
  v25 = 1;
  started = CUserProfileService::_StartService((CUserProfileService *)v1);
  LastError = started;
  if ( started < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xF2,
      (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\service.cpp",
      (const char *)(unsigned int)started,
      bAlertable);
    wil::EnterCriticalSection(&hEvent, v1);
    if ( (Microsoft_Windows_User_Profiles_ServiceEnableBits & 2) != 0 )
      McGenEventWrite_EtwEventWriteTransfer(v7, (unsigned int)EVENT_SERVICE_STOPPED, v8, 1, (__int64)Handles);
    CUserProfileService::_SetStatus((CUserProfileService *)v1, 1, 0, 0);
    goto LABEL_3;
  }
  CThreadPool::AddWorkItem(
    (CThreadPool *)&v1[1].OwningThread,
    (unsigned int (*)(void *))CleanupProfilesThreadProc,
    0,
    0);
  hEvent = 0;
  event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z = _create___event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z((__int64)&hEvent, 0);
  LastErrorFailHr = event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z;
  v11 = hEvent;
  if ( event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z >= 0 )
  {
    if ( RegisterGPNotification(hEvent, 1) )
      LastErrorFailHr = 0;
    else
      LastErrorFailHr = wil::details::GetLastErrorFailHr(v12);
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x13E,
      (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\service.cpp",
      (const char *)(unsigned int)event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z,
      bAlertable);
  }
  if ( LastErrorFailHr < 0 )
  {
    v20 = WaitForSingleObjectEx(v1[1].DebugInfo, 0xFFFFFFFF, 0);
    if ( v20 != 258 && v20 )
      wil::details::in1diag3::FailFast_Unexpected(retaddr, (void *)0xB0F, v21, v22);
  }
  else
  {
    Handles[0] = v1[1].DebugInfo;
    Handles[1] = v11;
    Handles[2] = *(HANDLE *)&v1[1].LockCount;
    while ( 1 )
    {
      v13 = WaitForMultipleObjectsEx(3u, Handles, 0, 0xFFFFFFFF, 0);
      if ( !v13 )
        break;
      if ( v13 - 1 <= 1 && (unsigned __int8)IsWaitForNetworkForRoamingProfilePresent(v14) )
        RefreshSuspendFolderPolicyAndUploadTaskConfig();
    }
    UnregisterGPNotification(v11);
  }
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&hEvent);
  wil::EnterCriticalSection(&hEvent, v1);
  if ( (unsigned __int8)IsWaitForNetworkForRoamingProfilePresent(v15) )
    StopRoamingClassFactories();
  CUserProfileManager::Uninitialize((CUserProfileManager *)g_pProfMgr);
  if ( g_pProfMgr )
    CUserProfileManager::`scalar deleting destructor'((CUserProfileManager *)g_pProfMgr, v16);
  g_pProfMgr = 0;
  OwningThread = (struct _TP_CLEANUP_GROUP *)v1[1].OwningThread;
  if ( OwningThread )
    CloseThreadpoolCleanupGroupMembers(OwningThread, 1, 0);
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>(&hEvent);
  wil::EnterCriticalSection(&hEvent, v1);
  if ( (Microsoft_Windows_User_Profiles_ServiceEnableBits & 2) != 0 )
    McGenEventWrite_EtwEventWriteTransfer(v18, (unsigned int)EVENT_SERVICE_STOPPED, v19, 1, (__int64)Handles);
  CUserProfileService::_SetStatus((CUserProfileService *)v1, 1, 0, 0);
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>(&hEvent);
  return 0;
}

```

## disassembly

```asm
0x180036c28  push    rbp
0x180036c2a  push    rbx
0x180036c2b  push    rsi
0x180036c2c  push    rdi
0x180036c2d  push    r12
0x180036c2f  push    r14
0x180036c31  mov     rbp, rsp
0x180036c34  sub     rsp, 68h
0x180036c38  mov     rax, cs:__security_cookie
0x180036c3f  xor     rax, rsp
0x180036c42  mov     [rbp+var_10], rax
0x180036c46  mov     rdi, cs:?g_pUPSvc@@3PEAVCUserProfileService@@EA; CUserProfileService * g_pUPSvc
0x180036c4d  mov     rdx, rdi
0x180036c50  lea     rcx, [rbp+hEvent]
0x180036c54  call    ?EnterCriticalSection@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_CRITICAL_SECTION@@@Z; wil::EnterCriticalSection(_RTL_CRITICAL_SECTION *)
0x180036c59  lea     rdx, ?UserProfileServiceHandler@@YAXK@Z; lpHandlerProc
0x180036c60  lea     rcx, ServiceName; "ProfSvc"
0x180036c67  call    cs:__imp_RegisterServiceCtrlHandlerW
0x180036c6d  mov     [rdi+88h], rax
0x180036c74  test    rax, rax
0x180036c77  jnz     short loc_180036CA0
0x180036c79  mov     rcx, [rbp+30h]; this
0x180036c7d  lea     r8, aOnecoreDsSecur_13; "onecore\\ds\\security\\gina\\profile\\p"...
0x180036c84  mov     edx, 0E9h; void *
0x180036c89  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180036c8e  mov     ebx, eax
0x180036c90  lea     rcx, [rbp+hEvent]
0x180036c94  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>(void)
0x180036c99  mov     eax, ebx
0x180036c9b  jmp     loc_180036EA0
0x180036ca0  lea     rcx, [rbp+hEvent]
0x180036ca4  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>(void)
0x180036ca9  mov     [rbp+hEvent], rdi
0x180036cad  mov     r12d, 1
0x180036cb3  mov     [rbp+var_30], r12b
0x180036cb7  mov     rcx, rdi; this
0x180036cba  call    ?_StartService@CUserProfileService@@AEAAJXZ; CUserProfileService::_StartService(void)
0x180036cbf  mov     ebx, eax
0x180036cc1  test    eax, eax
0x180036cc3  jns     short loc_180036D21
0x180036cc5  mov     rcx, [rbp+30h]; this
0x180036cc9  mov     r9d, eax; char *
0x180036ccc  lea     r8, aOnecoreDsSecur_13; "onecore\\ds\\security\\gina\\profile\\p"...
0x180036cd3  mov     edx, 0F2h; void *
0x180036cd8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180036cdd  nop
0x180036cde  mov     rdx, rdi
0x180036ce1  lea     rcx, [rbp+hEvent]
0x180036ce5  call    ?EnterCriticalSection@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_CRITICAL_SECTION@@@Z; wil::EnterCriticalSection(_RTL_CRITICAL_SECTION *)
0x180036cea  test    cs:Microsoft_Windows_User_Profiles_ServiceEnableBits, 2
0x180036cf1  jz      short loc_180036D0B
0x180036cf3  lea     rax, [rbp+Handles]
0x180036cf7  mov     qword ptr [rsp+68h+bAlertable], rax
0x180036cfc  mov     r9d, r12d
0x180036cff  lea     rdx, EVENT_SERVICE_STOPPED
0x180036d06  call    McGenEventWrite_EtwEventWriteTransfer
0x180036d0b  xor     r9d, r9d; unsigned int
0x180036d0e  xor     r8d, r8d; unsigned int
0x180036d11  mov     edx, r12d; unsigned int
0x180036d14  mov     rcx, rdi; this
0x180036d17  call    ?_SetStatus@CUserProfileService@@AEAAJKKK@Z; CUserProfileService::_SetStatus(ulong,ulong,ulong)
0x180036d1c  jmp     loc_180036C90
0x180036d21  xor     r9d, r9d; void *
0x180036d24  xor     r8d, r8d; void *
0x180036d27  lea     rdx, ?CleanupProfilesThreadProc@@YAKPEAX@Z; unsigned int (*)(void *)
0x180036d2e  lea     rcx, [rdi+38h]; this
0x180036d32  call    ?AddWorkItem@CThreadPool@@QEAAJP6AKPEAX@Z00K@Z; CThreadPool::AddWorkItem(ulong (*)(void *),void *,void *,ulong)
0x180036d37  mov     [rbp+hEvent], 0
0x180036d3f  xor     edx, edx
0x180036d41  lea     rcx, [rbp+hEvent]
0x180036d45  call    ?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x180036d4a  mov     esi, eax
0x180036d4c  mov     rbx, [rbp+hEvent]
0x180036d50  test    eax, eax
0x180036d52  jns     short loc_180036D6E
0x180036d54  mov     rcx, [rbp+30h]; this
0x180036d58  mov     r9d, eax; char *
0x180036d5b  lea     r8, aOnecoreDsSecur_13; "onecore\\ds\\security\\gina\\profile\\p"...
0x180036d62  mov     edx, 13Eh; void *
0x180036d67  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180036d6c  jmp     short loc_180036D89
0x180036d6e  mov     edx, r12d; bMachine
0x180036d71  mov     rcx, rbx; hEvent
0x180036d74  call    cs:__imp_RegisterGPNotification
0x180036d7a  test    eax, eax
0x180036d7c  jnz     short loc_180036D87
0x180036d7e  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180036d83  mov     esi, eax
0x180036d85  jmp     short loc_180036D89
0x180036d87  xor     esi, esi
0x180036d89  mov     rcx, [rdi+28h]; hHandle
0x180036d8d  xor     r8d, r8d; bAlertable
0x180036d90  test    esi, esi
0x180036d92  js      loc_180036EB9
0x180036d98  mov     [rbp+Handles], rcx
0x180036d9c  mov     [rbp+var_20], rbx
0x180036da0  mov     rax, [rdi+30h]
0x180036da4  mov     [rbp+var_18], rax
0x180036da8  lea     esi, [r8+3]
0x180036dac  jmp     short loc_180036DC7
0x180036dae  dec     eax
0x180036db0  cmp     eax, r12d
0x180036db3  ja      short loc_180036DC4
0x180036db5  call    IsWaitForNetworkForRoamingProfilePresent
0x180036dba  test    al, al
0x180036dbc  jz      short loc_180036DC4
0x180036dbe  call    cs:__imp_RefreshSuspendFolderPolicyAndUploadTaskConfig
0x180036dc4  xor     r8d, r8d; bWaitAll
0x180036dc7  mov     [rsp+68h+bAlertable], 0; bAlertable
0x180036dcf  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x180036dd3  lea     rdx, [rbp+Handles]; lpHandles
0x180036dd7  mov     ecx, esi; nCount
0x180036dd9  call    cs:__imp_WaitForMultipleObjectsEx
0x180036ddf  test    eax, eax
0x180036de1  jnz     short loc_180036DAE
0x180036de3  mov     rcx, rbx; hEvent
0x180036de6  call    cs:__imp_UnregisterGPNotification
0x180036dec  lea     rcx, [rbp+hEvent]
0x180036df0  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180036df5  mov     rdx, rdi
0x180036df8  lea     rcx, [rbp+hEvent]
0x180036dfc  call    ?EnterCriticalSection@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_CRITICAL_SECTION@@@Z; wil::EnterCriticalSection(_RTL_CRITICAL_SECTION *)
0x180036e01  call    IsWaitForNetworkForRoamingProfilePresent
0x180036e06  test    al, al
0x180036e08  jz      short loc_180036E10
0x180036e0a  call    cs:__imp_StopRoamingClassFactories
0x180036e10  mov     rcx, cs:?g_pProfMgr@@3PEAVCUserProfileManager@@EA; this
0x180036e17  call    ?Uninitialize@CUserProfileManager@@QEAAXXZ; CUserProfileManager::Uninitialize(void)
0x180036e1c  mov     rcx, cs:?g_pProfMgr@@3PEAVCUserProfileManager@@EA; this
0x180036e23  test    rcx, rcx
0x180036e26  jz      short loc_180036E2D
0x180036e28  call    ??_GCUserProfileManager@@QEAAPEAXI@Z; CUserProfileManager::`scalar deleting destructor'(uint)
0x180036e2d  mov     cs:?g_pProfMgr@@3PEAVCUserProfileManager@@EA, 0; CUserProfileManager * g_pProfMgr
0x180036e38  mov     rcx, [rdi+38h]; ptpcg
0x180036e3c  test    rcx, rcx
0x180036e3f  jz      short loc_180036E4D
0x180036e41  xor     r8d, r8d; pvCleanupContext
0x180036e44  mov     edx, r12d; fCancelPendingCallbacks
0x180036e47  call    cs:__imp_CloseThreadpoolCleanupGroupMembers
0x180036e4d  lea     rcx, [rbp+hEvent]
0x180036e51  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>(void)
0x180036e56  nop
0x180036e57  mov     rdx, rdi
0x180036e5a  lea     rcx, [rbp+hEvent]
0x180036e5e  call    ?EnterCriticalSection@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_CRITICAL_SECTION@@@Z; wil::EnterCriticalSection(_RTL_CRITICAL_SECTION *)
0x180036e63  test    cs:Microsoft_Windows_User_Profiles_ServiceEnableBits, 2
0x180036e6a  jz      short loc_180036E84
0x180036e6c  lea     rax, [rbp+Handles]
0x180036e70  mov     qword ptr [rsp+68h+bAlertable], rax
0x180036e75  mov     r9d, r12d
0x180036e78  lea     rdx, EVENT_SERVICE_STOPPED
0x180036e7f  call    McGenEventWrite_EtwEventWriteTransfer
0x180036e84  xor     r9d, r9d; unsigned int
0x180036e87  xor     r8d, r8d; unsigned int
0x180036e8a  mov     edx, r12d; unsigned int
0x180036e8d  mov     rcx, rdi; this
0x180036e90  call    ?_SetStatus@CUserProfileService@@AEAAJKKK@Z; CUserProfileService::_SetStatus(ulong,ulong,ulong)
0x180036e95  lea     rcx, [rbp+hEvent]
0x180036e99  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>(void)
0x180036e9e  xor     eax, eax
0x180036ea0  mov     rcx, [rbp+var_10]
0x180036ea4  xor     rcx, rsp; StackCookie
0x180036ea7  call    __security_check_cookie
0x180036eac  add     rsp, 68h
0x180036eb0  pop     r14
0x180036eb2  pop     r12
0x180036eb4  pop     rdi
0x180036eb5  pop     rsi
0x180036eb6  pop     rbx
0x180036eb7  pop     rbp
0x180036eb8  retn
0x180036eb9  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180036ebc  call    cs:__imp_WaitForSingleObjectEx
0x180036ec2  cmp     eax, 102h
0x180036ec7  jz      loc_180036DEC
0x180036ecd  test    eax, eax
0x180036ecf  jz      loc_180036DEC
0x180036ed5  mov     rcx, [rbp+30h]; this
0x180036ed9  mov     edx, 0B0Fh; void *
0x180036ede  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
```
