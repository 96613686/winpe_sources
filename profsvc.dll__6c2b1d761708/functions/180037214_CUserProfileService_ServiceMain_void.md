# CUserProfileService::ServiceMain(void)

- ea: `0x180037214`
- end: `0x1800374b4`
- name: `?ServiceMain@CUserProfileService@@QEAAJXZ`
- size: `672`
- prototype: `__int64 __fastcall(CUserProfileService *__hidden this)`
- caller_count: `1`
- callee_count: `17`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180037190`

## callees

- `0x180005f58`
- `0x18001a9d0`
- `0x180024cb0`
- `0x18002729c`
- `0x180027c64`
- `0x18002894c`
- `0x18002df48`
- `0x180030ad0`
- `0x180032e60`
- `0x180037214`
- `0x1800374bc`
- `0x180038eec`
- `0x18003bc70`
- `0x18003d678`
- `0x18003e44c`
- `0x180040bcc`
- `0x18004f00c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180037486`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180037486`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x1800373d5`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x1800373d5`
- `USERENV!RegisterGPNotification` at `0x180037364`
- `USERENV!RegisterGPNotification` at `0x180037364`
- `USERENV!UnregisterGPNotification` at `0x1800373e8`
- `USERENV!UnregisterGPNotification` at `0x1800373e8`
- `api-ms-win-service-winsvc-l1-1-0!RegisterServiceCtrlHandlerW` at `0x180037251`
- `api-ms-win-service-winsvc-l1-1-0!RegisterServiceCtrlHandlerW` at `0x180037251`
- `ext-ms-win-profile-profsvc-l1-1-0!RefreshSuspendFolderPolicyAndUploadTaskConfig` at `0x1800373b4`
- `ext-ms-win-profile-profsvc-l1-1-0!RefreshSuspendFolderPolicyAndUploadTaskConfig` at `0x1800373b4`

## string_xrefs

- `0x18003726d`: `onecore\ds\security\gina\profile\profsvc\service.cpp`
- `0x1800372bc`: `onecore\ds\security\gina\profile\profsvc\service.cpp`
- `0x18003734b`: `onecore\ds\security\gina\profile\profsvc\service.cpp`
- `0x180037410`: `onecore\ds\security\gina\profile\profsvc\service.cpp`

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
  int v9; // eax
  int LastErrorFailHr; // esi
  HANDLE v11; // rbx
  wil::details *v12; // rcx
  DWORD v13; // eax
  int v14; // eax
  int v15; // ecx
  int v16; // r8d
  DWORD v17; // eax
  unsigned int v18; // r8d
  const char *v19; // r9
  unsigned int bAlertable; // [rsp+20h] [rbp-40h]
  int bAlertablea; // [rsp+20h] [rbp-40h]
  HANDLE hEvent; // [rsp+30h] [rbp-30h] BYREF
  char v23; // [rsp+38h] [rbp-28h]
  HANDLE Handles[3]; // [rsp+40h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+28h]

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
  v23 = 1;
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
    CUserProfileService::_SetStatus((CUserProfileService *)v1, 1u, 0, 0);
    goto LABEL_3;
  }
  CThreadPool::AddWorkItem(
    (CThreadPool *)&v1[1].OwningThread,
    (unsigned int (*)(void *))CleanupProfilesThreadProc,
    0,
    0,
    bAlertable);
  hEvent = 0;
  v9 = _create___event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(
         &hEvent,
         0);
  LastErrorFailHr = v9;
  v11 = hEvent;
  if ( v9 >= 0 )
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
      (const char *)(unsigned int)v9,
      bAlertablea);
  }
  if ( LastErrorFailHr < 0 )
  {
    v17 = WaitForSingleObjectEx(v1[1].DebugInfo, 0xFFFFFFFF, 0);
    if ( v17 != 258 && v17 )
      wil::details::in1diag3::FailFast_Unexpected(retaddr, (void *)0xB0F, v18, v19);
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
      if ( v13 - 1 <= 1 && (unsigned __int8)IsWaitForNetworkForRoamingProfilePresent() )
        RefreshSuspendFolderPolicyAndUploadTaskConfig();
    }
    UnregisterGPNotification(v11);
  }
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&hEvent);
  v14 = CUserProfileService::_StopService((CUserProfileService *)v1);
  if ( v14 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0xF6,
      (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\service.cpp",
      (const char *)(unsigned int)v14,
      bAlertablea);
  wil::EnterCriticalSection(&hEvent, v1);
  if ( (Microsoft_Windows_User_Profiles_ServiceEnableBits & 2) != 0 )
    McGenEventWrite_EtwEventWriteTransfer(v15, (unsigned int)EVENT_SERVICE_STOPPED, v16, 1, (__int64)Handles);
  CUserProfileService::_SetStatus((CUserProfileService *)v1, 1u, 0, 0);
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>(&hEvent);
  return 0;
}

```

## disassembly

```asm
0x180037214  push    rbp
0x180037216  push    rbx
0x180037217  push    rsi
0x180037218  push    rdi
0x180037219  push    r15
0x18003721b  mov     rbp, rsp
0x18003721e  sub     rsp, 60h
0x180037222  mov     rax, cs:__security_cookie
0x180037229  xor     rax, rsp
0x18003722c  mov     [rbp+var_8], rax
0x180037230  mov     rdi, cs:?g_pUPSvc@@3PEAVCUserProfileService@@EA; CUserProfileService * g_pUPSvc
0x180037237  mov     rdx, rdi
0x18003723a  lea     rcx, [rbp+hEvent]
0x18003723e  call    ?EnterCriticalSection@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_CRITICAL_SECTION@@@Z; wil::EnterCriticalSection(_RTL_CRITICAL_SECTION *)
0x180037243  lea     rdx, ?UserProfileServiceHandler@@YAXK@Z; lpHandlerProc
0x18003724a  lea     rcx, ServiceName; "ProfSvc"
0x180037251  call    cs:__imp_RegisterServiceCtrlHandlerW
0x180037258  nop     dword ptr [rax+rax+00h]
0x18003725d  mov     [rdi+88h], rax
0x180037264  test    rax, rax
0x180037267  jnz     short loc_180037290
0x180037269  mov     rcx, [rbp+28h]; this
0x18003726d  lea     r8, aOnecoreDsSecur_13; "onecore\\ds\\security\\gina\\profile\\p"...
0x180037274  mov     edx, 0E9h; void *
0x180037279  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18003727e  mov     ebx, eax
0x180037280  lea     rcx, [rbp+hEvent]
0x180037284  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>(void)
0x180037289  mov     eax, ebx
0x18003728b  jmp     loc_18003746B
0x180037290  lea     rcx, [rbp+hEvent]
0x180037294  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>(void)
0x180037299  mov     [rbp+hEvent], rdi
0x18003729d  mov     r15d, 1
0x1800372a3  mov     [rbp+var_28], r15b
0x1800372a7  mov     rcx, rdi; this
0x1800372aa  call    ?_StartService@CUserProfileService@@AEAAJXZ; CUserProfileService::_StartService(void)
0x1800372af  mov     ebx, eax
0x1800372b1  test    eax, eax
0x1800372b3  jns     short loc_180037311
0x1800372b5  mov     rcx, [rbp+28h]; this
0x1800372b9  mov     r9d, eax; char *
0x1800372bc  lea     r8, aOnecoreDsSecur_13; "onecore\\ds\\security\\gina\\profile\\p"...
0x1800372c3  mov     edx, 0F2h; void *
0x1800372c8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800372cd  nop
0x1800372ce  mov     rdx, rdi
0x1800372d1  lea     rcx, [rbp+hEvent]
0x1800372d5  call    ?EnterCriticalSection@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_CRITICAL_SECTION@@@Z; wil::EnterCriticalSection(_RTL_CRITICAL_SECTION *)
0x1800372da  test    cs:Microsoft_Windows_User_Profiles_ServiceEnableBits, 2
0x1800372e1  jz      short loc_1800372FB
0x1800372e3  lea     rax, [rbp+Handles]
0x1800372e7  mov     qword ptr [rsp+60h+bAlertable], rax
0x1800372ec  mov     r9d, r15d
0x1800372ef  lea     rdx, EVENT_SERVICE_STOPPED
0x1800372f6  call    McGenEventWrite_EtwEventWriteTransfer
0x1800372fb  xor     r9d, r9d; unsigned int
0x1800372fe  xor     r8d, r8d; unsigned int
0x180037301  mov     edx, r15d; unsigned int
0x180037304  mov     rcx, rdi; this
0x180037307  call    ?_SetStatus@CUserProfileService@@AEAAJKKK@Z; CUserProfileService::_SetStatus(ulong,ulong,ulong)
0x18003730c  jmp     loc_180037280
0x180037311  lea     rcx, [rdi+38h]; this
0x180037315  xor     r9d, r9d; void *
0x180037318  xor     r8d, r8d; void *
0x18003731b  lea     rdx, ?CleanupProfilesThreadProc@@YAKPEAX@Z; unsigned int (*)(void *)
0x180037322  call    ?AddWorkItem@CThreadPool@@QEAAJP6AKPEAX@Z00K@Z; CThreadPool::AddWorkItem(ulong (*)(void *),void *,void *,ulong)
0x180037327  mov     [rbp+hEvent], 0
0x18003732f  xor     edx, edx
0x180037331  lea     rcx, [rbp+hEvent]
0x180037335  call    ?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x18003733a  mov     esi, eax
0x18003733c  mov     rbx, [rbp+hEvent]
0x180037340  test    eax, eax
0x180037342  jns     short loc_18003735E
0x180037344  mov     rcx, [rbp+28h]; this
0x180037348  mov     r9d, eax; char *
0x18003734b  lea     r8, aOnecoreDsSecur_13; "onecore\\ds\\security\\gina\\profile\\p"...
0x180037352  mov     edx, 13Eh; void *
0x180037357  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003735c  jmp     short loc_18003737F
0x18003735e  mov     edx, r15d; bMachine
0x180037361  mov     rcx, rbx; hEvent
0x180037364  call    cs:__imp_RegisterGPNotification
0x18003736b  nop     dword ptr [rax+rax+00h]
0x180037370  test    eax, eax
0x180037372  jnz     short loc_18003737D
0x180037374  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180037379  mov     esi, eax
0x18003737b  jmp     short loc_18003737F
0x18003737d  xor     esi, esi
0x18003737f  mov     rcx, [rdi+28h]; hHandle
0x180037383  xor     r8d, r8d; bAlertable
0x180037386  test    esi, esi
0x180037388  js      loc_180037483
0x18003738e  mov     [rbp+Handles], rcx
0x180037392  mov     [rbp+var_18], rbx
0x180037396  mov     rax, [rdi+30h]
0x18003739a  mov     [rbp+var_10], rax
0x18003739e  lea     esi, [r8+3]
0x1800373a2  jmp     short loc_1800373C3
0x1800373a4  dec     eax
0x1800373a6  cmp     eax, r15d
0x1800373a9  ja      short loc_1800373C0
0x1800373ab  call    IsWaitForNetworkForRoamingProfilePresent
0x1800373b0  test    al, al
0x1800373b2  jz      short loc_1800373C0
0x1800373b4  call    cs:__imp_RefreshSuspendFolderPolicyAndUploadTaskConfig
0x1800373bb  nop     dword ptr [rax+rax+00h]
0x1800373c0  xor     r8d, r8d; bWaitAll
0x1800373c3  mov     [rsp+60h+bAlertable], 0; int
0x1800373cb  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x1800373cf  lea     rdx, [rbp+Handles]; lpHandles
0x1800373d3  mov     ecx, esi; nCount
0x1800373d5  call    cs:__imp_WaitForMultipleObjectsEx
0x1800373dc  nop     dword ptr [rax+rax+00h]
0x1800373e1  test    eax, eax
0x1800373e3  jnz     short loc_1800373A4
0x1800373e5  mov     rcx, rbx; hEvent
0x1800373e8  call    cs:__imp_UnregisterGPNotification
0x1800373ef  nop     dword ptr [rax+rax+00h]
0x1800373f4  lea     rcx, [rbp+hEvent]
0x1800373f8  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800373fd  mov     rcx, rdi; this
0x180037400  call    ?_StopService@CUserProfileService@@AEAAJXZ; CUserProfileService::_StopService(void)
0x180037405  mov     rcx, [rbp+28h]; this
0x180037409  test    eax, eax
0x18003740b  jns     short loc_180037422
0x18003740d  mov     r9d, eax; char *
0x180037410  lea     r8, aOnecoreDsSecur_13; "onecore\\ds\\security\\gina\\profile\\p"...
0x180037417  mov     edx, 0F6h; void *
0x18003741c  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180037421  nop
0x180037422  mov     rdx, rdi
0x180037425  lea     rcx, [rbp+hEvent]
0x180037429  call    ?EnterCriticalSection@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_CRITICAL_SECTION@@@Z; wil::EnterCriticalSection(_RTL_CRITICAL_SECTION *)
0x18003742e  test    cs:Microsoft_Windows_User_Profiles_ServiceEnableBits, 2
0x180037435  jz      short loc_18003744F
0x180037437  lea     rax, [rbp+Handles]
0x18003743b  mov     qword ptr [rsp+60h+bAlertable], rax
0x180037440  mov     r9d, r15d
0x180037443  lea     rdx, EVENT_SERVICE_STOPPED
0x18003744a  call    McGenEventWrite_EtwEventWriteTransfer
0x18003744f  xor     r9d, r9d; unsigned int
0x180037452  xor     r8d, r8d; unsigned int
0x180037455  mov     edx, r15d; unsigned int
0x180037458  mov     rcx, rdi; this
0x18003745b  call    ?_SetStatus@CUserProfileService@@AEAAJKKK@Z; CUserProfileService::_SetStatus(ulong,ulong,ulong)
0x180037460  lea     rcx, [rbp+hEvent]
0x180037464  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>(void)
0x180037469  xor     eax, eax
0x18003746b  mov     rcx, [rbp+var_8]
0x18003746f  xor     rcx, rsp; StackCookie
0x180037472  call    __security_check_cookie
0x180037477  add     rsp, 60h
0x18003747b  pop     r15
0x18003747d  pop     rdi
0x18003747e  pop     rsi
0x18003747f  pop     rbx
0x180037480  pop     rbp
0x180037481  retn
0x180037483  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180037486  call    cs:__imp_WaitForSingleObjectEx
0x18003748d  nop     dword ptr [rax+rax+00h]
0x180037492  cmp     eax, 102h
0x180037497  jz      loc_1800373F4
0x18003749d  test    eax, eax
0x18003749f  jz      loc_1800373F4
0x1800374a5  mov     rcx, [rbp+28h]; this
0x1800374a9  mov     edx, 0B0Fh; void *
0x1800374ae  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
```
