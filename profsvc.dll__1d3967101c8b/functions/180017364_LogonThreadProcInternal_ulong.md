# LogonThreadProcInternal(ulong)

- ea: `0x180017364`
- end: `0x1800177e7`
- name: `?LogonThreadProcInternal@@YAJK@Z`
- size: `1155`
- prototype: `__int64 __fastcall(unsigned int)`
- caller_count: `1`
- callee_count: `30`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180017320`

## callees

- `0x1800036e0`
- `0x180006e70`
- `0x180008200`
- `0x18000a320`
- `0x18000a9b8`
- `0x1800168ec`
- `0x180016bc4`
- `0x180016e00`
- `0x180016eac`
- `0x180016f5c`
- `0x1800170c8`
- `0x180017364`
- `0x1800190f4`
- `0x180019460`
- `0x180019630`
- `0x1800199b4`
- `0x180021b6c`
- `0x18002c324`
- `0x18002d2d8`
- `0x180030e58`
- `0x180030ebc`
- `0x18003483c`
- `0x180036988`
- `0x18003c118`
- `0x18003c264`
- `0x18003f42c`
- `0x180042658`
- `0x180047cbc`
- `0x18004e25c`
- `0x18004e2e8`

## import_xrefs

- `ntdll!RtlGetActiveConsoleId` at `0x180017587`
- `ntdll!RtlGetActiveConsoleId` at `0x180017587`
- `ext-ms-win-profile-profsvc-l1-1-0!InitializeSuspendFolderPolicyAndUploadTaskConfig` at `0x18001778f`
- `ext-ms-win-profile-profsvc-l1-1-0!InitializeSuspendFolderPolicyAndUploadTaskConfig` at `0x18001778f`
- `ext-ms-win-session-winsta-l1-1-0!WinStationFreeMemory` at `0x1800175bb`
- `ext-ms-win-session-winsta-l1-1-0!WinStationFreeMemory` at `0x1800175eb`
- `ext-ms-win-session-winsta-l1-1-0!WinStationFreeMemory` at `0x18001761b`
- `ext-ms-win-session-winsta-l1-1-0!WinStationFreeMemory` at `0x1800175bb`
- `ext-ms-win-session-winsta-l1-1-0!WinStationFreeMemory` at `0x1800175eb`
- `ext-ms-win-session-winsta-l1-1-0!WinStationFreeMemory` at `0x18001761b`
- `ext-ms-win-session-winsta-l1-1-0!WinStationGetUserProfile` at `0x18001764a`
- `ext-ms-win-session-winsta-l1-1-0!WinStationGetUserProfile` at `0x18001764a`

## string_xrefs

- `0x1800173d1`: `onecore\ds\security\gina\profile\profsvc\winlogon.cpp`
- `0x180017412`: `onecore\ds\security\gina\profile\profsvc\winlogon.cpp`
- `0x180017466`: `onecore\ds\security\gina\profile\profsvc\winlogon.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall LogonThreadProcInternal(unsigned int a1)
{
  __int64 v2; // rcx
  void *ReadyEvent; // rax
  int v4; // eax
  unsigned int v5; // edi
  int MyOwnToken; // eax
  CUserProfileManager *v7; // rcx
  void **Params; // r15
  int v9; // eax
  int v10; // eax
  int v11; // eax
  CUserProfileManager *v12; // rcx
  void *UserToken; // r14
  int UserNameAndDomain; // eax
  __int64 v15; // rdx
  __int64 v16; // rcx
  unsigned __int16 *v17; // rdi
  unsigned __int16 *v18; // rdi
  unsigned __int16 *v19; // rdi
  int UserProfile; // eax
  int v21; // ecx
  int v22; // eax
  int v23; // eax
  wil::details::in1diag3 *v24; // rcx
  int v26; // [rsp+20h] [rbp-E0h]
  int v27; // [rsp+20h] [rbp-E0h]
  _BYTE v28[8]; // [rsp+30h] [rbp-D0h] BYREF
  void *TokenHandle; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v30; // [rsp+40h] [rbp-C0h] BYREF
  char v31; // [rsp+48h] [rbp-B8h]
  _PROFILEINFOW v32; // [rsp+50h] [rbp-B0h] BYREF
  void *v33[44]; // [rsp+90h] [rbp-70h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1F8h] [rbp+F8h]
  unsigned __int16 *v35; // [rsp+208h] [rbp+108h] BYREF
  unsigned __int16 *v36; // [rsp+210h] [rbp+110h] BYREF
  unsigned __int16 *v37; // [rsp+218h] [rbp+118h] BYREF

  if ( wil::details::FeatureImpl<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::GetImpl'::`2'::impl)
    && Microsoft_Windows_User_Profiles_ServiceEnableBits < 0 )
  {
    McTemplateU0q_EtwEventWriteTransfer(v2, EVENT_LOGON_THREAD_PROC_START, a1);
  }
  ReadyEvent = CUserProfileManager::GetReadyEvent(g_pProfMgr, a1);
  v4 = WaitForEventInternal(ReadyEvent);
  v5 = v4;
  if ( v4 >= 0 )
  {
    TokenHandle = 0;
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
      &TokenHandle,
      0);
    MyOwnToken = GetMyOwnToken(&TokenHandle);
    v5 = MyOwnToken;
    if ( MyOwnToken >= 0 )
    {
      memset(&v32, 0, sizeof(v32));
      v32.dwSize = 56;
      Params = (void **)CUserProfileManager::GetParams(v7, a1);
      v9 = _SetupServerName(&v32, Params);
      if ( v9 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x2E1,
          (int)"onecore\\ds\\security\\gina\\profile\\profsvc\\winlogon.cpp",
          (const char *)(unsigned int)v9);
      v10 = _SetupProfilePath(&v32, Params);
      if ( v10 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x2E2,
          (int)"onecore\\ds\\security\\gina\\profile\\profsvc\\winlogon.cpp",
          (const char *)(unsigned int)v10);
      v11 = _SetupNetworkDefaultProfilePath(&v32, (const struct _SN_ONLOGON_PARAMS *)Params);
      v12 = retaddr;
      if ( v11 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x2E3,
          (int)"onecore\\ds\\security\\gina\\profile\\profsvc\\winlogon.cpp",
          (const char *)(unsigned int)v11);
      UserToken = CUserProfileManager::GetUserToken(v12, a1);
      v30 = 0;
      v31 = 0;
      UserNameAndDomain = CAutoImpersonate::ImpersonateUser((CAutoImpersonate *)&v30, UserToken);
      v5 = UserNameAndDomain;
      if ( UserNameAndDomain >= 0 )
      {
        UserNameAndDomain = GetUserNameAndDomain(NameSamCompatible, &v32.lpUserName, 0);
        v5 = UserNameAndDomain;
        if ( UserNameAndDomain >= 0 )
        {
          if ( wil::details::FeatureImpl<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::GetImpl'::`2'::impl)
            && Microsoft_Windows_User_Profiles_ServiceEnableBits < 0 )
          {
            McTemplateU0z_EtwEventWriteTransfer(v16, EVENT_IMPERSONATE_USER, v32.lpUserName);
          }
          CAutoImpersonate::ResetImpersonation((CAutoImpersonate *)&v30);
          v36 = 0;
          v35 = 0;
          v37 = 0;
          if ( (unsigned int)RtlGetActiveConsoleId() != a1 && (unsigned __int8)IsWinStationGetUserProfilePresent() )
          {
            v17 = v37;
            if ( v37 )
            {
              wil::last_error_context::last_error_context((wil::last_error_context *)v28);
              WinStationFreeMemory(v17);
              wil::last_error_context::~last_error_context((wil::last_error_context *)v28);
            }
            v37 = 0;
            v18 = v35;
            if ( v35 )
            {
              wil::last_error_context::last_error_context((wil::last_error_context *)v28);
              WinStationFreeMemory(v18);
              wil::last_error_context::~last_error_context((wil::last_error_context *)v28);
            }
            v35 = 0;
            v19 = v36;
            if ( v36 )
            {
              wil::last_error_context::last_error_context((wil::last_error_context *)v28);
              WinStationFreeMemory(v19);
              wil::last_error_context::~last_error_context((wil::last_error_context *)v28);
            }
            v36 = 0;
            UserProfile = WinStationGetUserProfile(UserToken, &v36, &v35, &v37);
            if ( UserProfile < 0 )
              wil::details::in1diag3::_Log_Hr(
                retaddr,
                (void *)0x2FD,
                (int)"onecore\\ds\\security\\gina\\profile\\profsvc\\winlogon.cpp",
                (const char *)(unsigned int)UserProfile);
          }
          if ( wil::details::FeatureImpl<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::GetImpl'::`2'::impl)
            && Microsoft_Windows_User_Profiles_ServiceEnableBits < 0 )
          {
            McTemplateU0zzz_EtwEventWriteTransfer(
              v21,
              (unsigned int)EVENT_LOGON_THREAD_PROC_TSDATA,
              (_DWORD)v36,
              (_DWORD)v35,
              (__int64)v37);
          }
          _WaitForNetworkIfNecessary(UserToken, &v32, v36, v35, Params);
          CUserProfile::CUserProfile((CUserProfile *)v33);
          v22 = CUserProfile::Load(v33, TokenHandle, UserToken, &v32, a1, v36);
          v5 = v22;
          if ( v22 >= 0 )
          {
            v23 = PrepareEnvBlock(UserToken, v35, v37, (struct _SN_ONLOGON_PARAMS *)Params);
            v24 = retaddr;
            if ( v23 < 0 )
              wil::details::in1diag3::_Log_Hr(
                retaddr,
                (void *)0x30E,
                (int)"onecore\\ds\\security\\gina\\profile\\profsvc\\winlogon.cpp",
                (const char *)(unsigned int)v23);
            if ( (unsigned __int8)IsWaitForNetworkForRoamingProfilePresent(v24) )
              InitializeSuspendFolderPolicyAndUploadTaskConfig(UserToken, 1);
            CUserProfile::~CUserProfile((CUserProfile *)v33);
            wil::details::unique_storage<wil::details::resource_policy<unsigned short *,unsigned char (*)(void *),&unsigned char WinStationFreeMemory(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,unsigned char (*)(void *),&unsigned char WinStationFreeMemory(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v37);
            wil::details::unique_storage<wil::details::resource_policy<unsigned short *,unsigned char (*)(void *),&unsigned char WinStationFreeMemory(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,unsigned char (*)(void *),&unsigned char WinStationFreeMemory(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v35);
            wil::details::unique_storage<wil::details::resource_policy<unsigned short *,unsigned char (*)(void *),&unsigned char WinStationFreeMemory(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,unsigned char (*)(void *),&unsigned char WinStationFreeMemory(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v36);
            v5 = 0;
          }
          else
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x30A,
              (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\winlogon.cpp",
              (const char *)(unsigned int)v22,
              v27);
            CUserProfile::~CUserProfile((CUserProfile *)v33);
            wil::details::unique_storage<wil::details::resource_policy<unsigned short *,unsigned char (*)(void *),&unsigned char WinStationFreeMemory(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,unsigned char (*)(void *),&unsigned char WinStationFreeMemory(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v37);
            wil::details::unique_storage<wil::details::resource_policy<unsigned short *,unsigned char (*)(void *),&unsigned char WinStationFreeMemory(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,unsigned char (*)(void *),&unsigned char WinStationFreeMemory(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v35);
            wil::details::unique_storage<wil::details::resource_policy<unsigned short *,unsigned char (*)(void *),&unsigned char WinStationFreeMemory(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,unsigned char (*)(void *),&unsigned char WinStationFreeMemory(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v36);
          }
          goto LABEL_42;
        }
        v15 = 748;
      }
      else
      {
        v15 = 747;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v15,
        (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\winlogon.cpp",
        (const char *)(unsigned int)UserNameAndDomain,
        v26);
      CAutoImpersonate::ResetImpersonation((CAutoImpersonate *)&v30);
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x2D5,
        (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\winlogon.cpp",
        (const char *)(unsigned int)MyOwnToken,
        v26);
    }
LABEL_42:
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
    return v5;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x2D1,
    (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\winlogon.cpp",
    (const char *)(unsigned int)v4,
    v26);
  return v5;
}

```

## disassembly

```asm
0x180017364  push    rbp
0x180017366  push    rbx
0x180017367  push    rsi
0x180017368  push    rdi
0x180017369  push    r12
0x18001736b  push    r14
0x18001736d  push    r15
0x18001736f  lea     rbp, [rsp-0C0h]
0x180017377  sub     rsp, 1C0h
0x18001737e  mov     esi, ecx
0x180017380  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Profile_Service_ETW_Logging@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Profile_Service_ETW_Logging@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging> `wil::Feature<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::GetImpl(void)'::`2'::impl
0x180017387  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Profile_Service_ETW_Logging@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::__private_IsEnabled(void)
0x18001738c  xor     r12d, r12d
0x18001738f  test    al, al
0x180017391  jz      short loc_1800173AB
0x180017393  cmp     cs:Microsoft_Windows_User_Profiles_ServiceEnableBits, r12b
0x18001739a  jge     short loc_1800173AB
0x18001739c  mov     r8d, esi
0x18001739f  lea     rdx, EVENT_LOGON_THREAD_PROC_START
0x1800173a6  call    McTemplateU0q_EtwEventWriteTransfer
0x1800173ab  mov     edx, esi; unsigned int
0x1800173ad  mov     rcx, cs:?g_pProfMgr@@3PEAVCUserProfileManager@@EA; SRWLock
0x1800173b4  call    ?GetReadyEvent@CUserProfileManager@@QEAAPEAXK@Z; CUserProfileManager::GetReadyEvent(ulong)
0x1800173b9  mov     rcx, rax; void *
0x1800173bc  call    ?WaitForEventInternal@@YAJPEAX@Z; WaitForEventInternal(void *)
0x1800173c1  mov     edi, eax
0x1800173c3  test    eax, eax
0x1800173c5  jns     short loc_1800173E7
0x1800173c7  mov     rcx, [rbp+0F8h]; this
0x1800173ce  mov     r9d, eax; char *
0x1800173d1  lea     r8, aOnecoreDsSecur_12; "onecore\\ds\\security\\gina\\profile\\p"...
0x1800173d8  mov     edx, 2D1h; void *
0x1800173dd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800173e2  jmp     loc_1800177D3
0x1800173e7  mov     [rsp+1F0h+TokenHandle], r12
0x1800173ec  xor     edx, edx
0x1800173ee  lea     rcx, [rsp+1F0h+TokenHandle]
0x1800173f3  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x1800173f8  lea     rcx, [rsp+1F0h+TokenHandle]; TokenHandle
0x1800173fd  call    ?GetMyOwnToken@@YAJPEAPEAX@Z; GetMyOwnToken(void * *)
0x180017402  mov     edi, eax
0x180017404  test    eax, eax
0x180017406  jns     short loc_180017428
0x180017408  mov     rcx, [rbp+0F8h]; this
0x18001740f  mov     r9d, eax; char *
0x180017412  lea     r8, aOnecoreDsSecur_12; "onecore\\ds\\security\\gina\\profile\\p"...
0x180017419  mov     edx, 2D5h; void *
0x18001741e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180017423  jmp     loc_1800177C9
0x180017428  xorps   xmm0, xmm0
0x18001742b  xor     eax, eax
0x18001742d  movups  xmmword ptr [rsp+1F0h+var_1A0.dwSize], xmm0
0x180017432  movups  xmmword ptr [rsp+1F0h+var_1A0.lpProfilePath], xmm0
0x180017437  movups  xmmword ptr [rsp+1F0h+var_1A0.lpServerName], xmm0
0x18001743c  mov     [rbp+0F0h+var_1A0.hProfile], rax
0x180017440  mov     [rsp+1F0h+var_1A0.dwSize], 38h ; '8'
0x180017448  mov     edx, esi; unsigned int
0x18001744a  call    ?GetParams@CUserProfileManager@@QEAAPEAXK@Z; CUserProfileManager::GetParams(ulong)
0x18001744f  mov     r15, rax
0x180017452  mov     rdx, rax; struct _SN_ONLOGON_PARAMS *
0x180017455  lea     rcx, [rsp+1F0h+var_1A0]; struct _PROFILEINFOW *
0x18001745a  call    ?_SetupServerName@@YAJPEAU_PROFILEINFOW@@PEBU_SN_ONLOGON_PARAMS@@@Z; _SetupServerName(_PROFILEINFOW *,_SN_ONLOGON_PARAMS const *)
0x18001745f  mov     rcx, [rbp+0F8h]; this
0x180017466  lea     rbx, aOnecoreDsSecur_12; "onecore\\ds\\security\\gina\\profile\\p"...
0x18001746d  test    eax, eax
0x18001746f  jns     short loc_180017481
0x180017471  mov     r9d, eax; char *
0x180017474  mov     r8, rbx; unsigned int
0x180017477  mov     edx, 2E1h; void *
0x18001747c  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180017481  mov     rdx, r15; struct _SN_ONLOGON_PARAMS *
0x180017484  lea     rcx, [rsp+1F0h+var_1A0]; struct _PROFILEINFOW *
0x180017489  call    ?_SetupProfilePath@@YAJPEAU_PROFILEINFOW@@PEBU_SN_ONLOGON_PARAMS@@@Z; _SetupProfilePath(_PROFILEINFOW *,_SN_ONLOGON_PARAMS const *)
0x18001748e  mov     rcx, [rbp+0F8h]; this
0x180017495  test    eax, eax
0x180017497  jns     short loc_1800174A9
0x180017499  mov     r9d, eax; char *
0x18001749c  mov     r8, rbx; unsigned int
0x18001749f  mov     edx, 2E2h; void *
0x1800174a4  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800174a9  mov     rdx, r15; struct _SN_ONLOGON_PARAMS *
0x1800174ac  lea     rcx, [rsp+1F0h+var_1A0]; struct _PROFILEINFOW *
0x1800174b1  call    ?_SetupNetworkDefaultProfilePath@@YAJPEAU_PROFILEINFOW@@PEBU_SN_ONLOGON_PARAMS@@@Z; _SetupNetworkDefaultProfilePath(_PROFILEINFOW *,_SN_ONLOGON_PARAMS const *)
0x1800174b6  mov     rcx, [rbp+0F8h]; this
0x1800174bd  test    eax, eax
0x1800174bf  jns     short loc_1800174D1
0x1800174c1  mov     r9d, eax; char *
0x1800174c4  mov     r8, rbx; unsigned int
0x1800174c7  mov     edx, 2E3h; void *
0x1800174cc  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800174d1  mov     edx, esi; unsigned int
0x1800174d3  call    ?GetUserToken@CUserProfileManager@@QEAAPEAXK@Z; CUserProfileManager::GetUserToken(ulong)
0x1800174d8  mov     r14, rax
0x1800174db  mov     [rsp+1F0h+var_1B0], r12
0x1800174e0  mov     [rsp+1F0h+var_1A8], r12b
0x1800174e5  mov     rdx, rax; void *
0x1800174e8  lea     rcx, [rsp+1F0h+var_1B0]; this
0x1800174ed  call    ?ImpersonateUser@CAutoImpersonate@@QEAAJPEAX@Z; CAutoImpersonate::ImpersonateUser(void *)
0x1800174f2  mov     edi, eax
0x1800174f4  test    eax, eax
0x1800174f6  jns     short loc_18001751F
0x1800174f8  mov     edx, 2EBh; void *
0x1800174fd  mov     r8, rbx; unsigned int
0x180017500  mov     r9d, eax; char *
0x180017503  mov     rcx, [rbp+0F8h]; this
0x18001750a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001750f  nop
0x180017510  lea     rcx, [rsp+1F0h+var_1B0]; this
0x180017515  call    ?ResetImpersonation@CAutoImpersonate@@QEAAXXZ; CAutoImpersonate::ResetImpersonation(void)
0x18001751a  jmp     loc_1800177C9
0x18001751f  xor     r8d, r8d; unsigned __int16 **
0x180017522  lea     rdx, [rsp+1F0h+var_1A0.lpUserName]; unsigned __int16 **
0x180017527  lea     ecx, [r8+2]; NameFormat
0x18001752b  call    ?GetUserNameAndDomain@@YAJW4EXTENDED_NAME_FORMAT@@PEAPEAG1@Z; GetUserNameAndDomain(EXTENDED_NAME_FORMAT,ushort * *,ushort * *)
0x180017530  mov     edi, eax
0x180017532  test    eax, eax
0x180017534  jns     short loc_18001753D
0x180017536  mov     edx, 2ECh
0x18001753b  jmp     short loc_1800174FD
0x18001753d  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Profile_Service_ETW_Logging@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Profile_Service_ETW_Logging@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging> `wil::Feature<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::GetImpl(void)'::`2'::impl
0x180017544  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Profile_Service_ETW_Logging@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::__private_IsEnabled(void)
0x180017549  test    al, al
0x18001754b  jz      short loc_180017568
0x18001754d  cmp     cs:Microsoft_Windows_User_Profiles_ServiceEnableBits, r12b
0x180017554  jge     short loc_180017568
0x180017556  mov     r8, [rsp+1F0h+var_1A0.lpUserName]
0x18001755b  lea     rdx, EVENT_IMPERSONATE_USER
0x180017562  call    McTemplateU0z_EtwEventWriteTransfer
0x180017567  nop
0x180017568  lea     rcx, [rsp+1F0h+var_1B0]; this
0x18001756d  call    ?ResetImpersonation@CAutoImpersonate@@QEAAXXZ; CAutoImpersonate::ResetImpersonation(void)
0x180017572  mov     [rbp+0F0h+arg_10], r12
0x180017579  mov     [rbp+0F0h+arg_8], r12
0x180017580  mov     [rbp+0F0h+arg_18], r12
0x180017587  call    cs:__imp_RtlGetActiveConsoleId
0x18001758d  cmp     eax, esi
0x18001758f  jz      loc_18001766B
0x180017595  call    IsWinStationGetUserProfilePresent
0x18001759a  test    al, al
0x18001759c  jz      loc_18001766B
0x1800175a2  mov     rdi, [rbp+0F0h+arg_18]
0x1800175a9  test    rdi, rdi
0x1800175ac  jz      short loc_1800175CB
0x1800175ae  lea     rcx, [rsp+1F0h+var_1C0]; this
0x1800175b3  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x1800175b8  mov     rcx, rdi
0x1800175bb  call    cs:__imp_WinStationFreeMemory
0x1800175c1  lea     rcx, [rsp+1F0h+var_1C0]; this
0x1800175c6  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x1800175cb  mov     [rbp+0F0h+arg_18], r12
0x1800175d2  mov     rdi, [rbp+0F0h+arg_8]
0x1800175d9  test    rdi, rdi
0x1800175dc  jz      short loc_1800175FB
0x1800175de  lea     rcx, [rsp+1F0h+var_1C0]; this
0x1800175e3  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x1800175e8  mov     rcx, rdi
0x1800175eb  call    cs:__imp_WinStationFreeMemory
0x1800175f1  lea     rcx, [rsp+1F0h+var_1C0]; this
0x1800175f6  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x1800175fb  mov     [rbp+0F0h+arg_8], r12
0x180017602  mov     rdi, [rbp+0F0h+arg_10]
0x180017609  test    rdi, rdi
0x18001760c  jz      short loc_18001762B
0x18001760e  lea     rcx, [rsp+1F0h+var_1C0]; this
0x180017613  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180017618  mov     rcx, rdi
0x18001761b  call    cs:__imp_WinStationFreeMemory
0x180017621  lea     rcx, [rsp+1F0h+var_1C0]; this
0x180017626  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18001762b  mov     [rbp+0F0h+arg_10], r12
0x180017632  lea     r9, [rbp+0F0h+arg_18]
0x180017639  lea     r8, [rbp+0F0h+arg_8]
0x180017640  lea     rdx, [rbp+0F0h+arg_10]
0x180017647  mov     rcx, r14
0x18001764a  call    cs:__imp_WinStationGetUserProfile
0x180017650  mov     rcx, [rbp+0F8h]; this
0x180017657  test    eax, eax
0x180017659  jns     short loc_18001766B
0x18001765b  mov     r9d, eax; char *
0x18001765e  mov     r8, rbx; unsigned int
0x180017661  mov     edx, 2FDh; void *
0x180017666  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18001766b  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Profile_Service_ETW_Logging@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Profile_Service_ETW_Logging@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging> `wil::Feature<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::GetImpl(void)'::`2'::impl
0x180017672  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Profile_Service_ETW_Logging@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::__private_IsEnabled(void)
0x180017677  test    al, al
0x180017679  jz      short loc_1800176AA
0x18001767b  cmp     cs:Microsoft_Windows_User_Profiles_ServiceEnableBits, r12b
0x180017682  jge     short loc_1800176AA
0x180017684  mov     rax, [rbp+0F0h+arg_18]
0x18001768b  mov     [rsp+1F0h+var_1D0], rax
0x180017690  mov     r9, [rbp+0F0h+arg_8]
0x180017697  mov     r8, [rbp+0F0h+arg_10]
0x18001769e  lea     rdx, EVENT_LOGON_THREAD_PROC_TSDATA
0x1800176a5  call    McTemplateU0zzz_EtwEventWriteTransfer
0x1800176aa  mov     [rsp+1F0h+var_1D0], r15; struct _SN_ONLOGON_PARAMS *
0x1800176af  mov     r9, [rbp+0F0h+arg_8]; unsigned __int16 *
0x1800176b6  mov     r8, [rbp+0F0h+arg_10]; unsigned __int16 *
0x1800176bd  lea     rdx, [rsp+1F0h+var_1A0]; struct _PROFILEINFOW *
0x1800176c2  mov     rcx, r14; void *
0x1800176c5  call    ?_WaitForNetworkIfNecessary@@YAXPEAXQEAU_PROFILEINFOW@@PEBG2PEBU_SN_ONLOGON_PARAMS@@@Z; _WaitForNetworkIfNecessary(void *,_PROFILEINFOW * const,ushort const *,ushort const *,_SN_ONLOGON_PARAMS const *)
0x1800176ca  lea     rcx, [rbp+0F0h+var_160]; this
0x1800176ce  call    ??0CUserProfile@@QEAA@XZ; CUserProfile::CUserProfile(void)
0x1800176d3  nop
0x1800176d4  mov     rax, [rbp+0F0h+arg_10]
0x1800176db  mov     [rsp+1F0h+var_1C8], rax; unsigned __int16 *
0x1800176e0  mov     dword ptr [rsp+1F0h+var_1D0], esi; int
0x1800176e4  lea     r9, [rsp+1F0h+var_1A0]; struct _PROFILEINFOW *
0x1800176e9  mov     r8, r14; void *
0x1800176ec  mov     rdx, [rsp+1F0h+TokenHandle]; void *
0x1800176f1  lea     rcx, [rbp+0F0h+var_160]; this
0x1800176f5  call    ?Load@CUserProfile@@QEAAJPEAX0PEAU_PROFILEINFOW@@KPEBG@Z; CUserProfile::Load(void *,void *,_PROFILEINFOW *,ulong,ushort const *)
0x1800176fa  mov     edi, eax
0x1800176fc  test    eax, eax
0x1800176fe  jns     short loc_18001774A
0x180017700  mov     rcx, [rbp+0F8h]; this
0x180017707  mov     r9d, eax; char *
0x18001770a  mov     r8, rbx; unsigned int
0x18001770d  mov     edx, 30Ah; void *
0x180017712  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180017717  nop
0x180017718  lea     rcx, [rbp+0F0h+var_160]; this
0x18001771c  call    ??1CUserProfile@@QEAA@XZ; CUserProfile::~CUserProfile(void)
0x180017721  nop
0x180017722  lea     rcx, [rbp+0F0h+arg_18]
0x180017729  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AEPEAX@Z$1?WinStationFreeMemory@@YAE0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,uchar (*)(void *),&WinStationFreeMemory(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,uchar (*)(void *),&WinStationFreeMemory(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18001772e  nop
0x18001772f  lea     rcx, [rbp+0F0h+arg_8]
0x180017736  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AEPEAX@Z$1?WinStationFreeMemory@@YAE0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,uchar (*)(void *),&WinStationFreeMemory(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,uchar (*)(void *),&WinStationFreeMemory(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18001773b  nop
0x18001773c  lea     rcx, [rbp+0F0h+arg_10]
0x180017743  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AEPEAX@Z$1?WinStationFreeMemory@@YAE0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,uchar (*)(void *),&WinStationFreeMemory(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,uchar (*)(void *),&WinStationFreeMemory(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180017748  jmp     short loc_1800177C9
0x18001774a  mov     r9, r15; struct _SN_ONLOGON_PARAMS *
0x18001774d  mov     r8, [rbp+0F0h+arg_18]; unsigned __int16 *
0x180017754  mov     rdx, [rbp+0F0h+arg_8]; unsigned __int16 *
0x18001775b  mov     rcx, r14; TokenHandle
0x18001775e  call    ?PrepareEnvBlock@@YAJPEAXPEBG1PEAU_SN_ONLOGON_PARAMS@@@Z; PrepareEnvBlock(void *,ushort const *,ushort const *,_SN_ONLOGON_PARAMS *)
0x180017763  mov     rcx, [rbp+0F8h]; this
0x18001776a  test    eax, eax
0x18001776c  jns     short loc_18001777E
0x18001776e  mov     r9d, eax; char *
0x180017771  mov     r8, rbx; unsigned int
0x180017774  mov     edx, 30Eh; void *
0x180017779  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18001777e  call    IsWaitForNetworkForRoamingProfilePresent
0x180017783  test    al, al
0x180017785  jz      short loc_180017796
0x180017787  mov     edx, 1
0x18001778c  mov     rcx, r14
0x18001778f  call    cs:__imp_InitializeSuspendFolderPolicyAndUploadTaskConfig
0x180017795  nop
0x180017796  lea     rcx, [rbp+0F0h+var_160]; this
0x18001779a  call    ??1CUserProfile@@QEAA@XZ; CUserProfile::~CUserProfile(void)
0x18001779f  nop
0x1800177a0  lea     rcx, [rbp+0F0h+arg_18]
0x1800177a7  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AEPEAX@Z$1?WinStationFreeMemory@@YAE0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,uchar (*)(void *),&WinStationFreeMemory(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,uchar (*)(void *),&WinStationFreeMemory(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800177ac  nop
0x1800177ad  lea     rcx, [rbp+0F0h+arg_8]
0x1800177b4  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AEPEAX@Z$1?WinStationFreeMemory@@YAE0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,uchar (*)(void *),&WinStationFreeMemory(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,uchar (*)(void *),&WinStationFreeMemory(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800177b9  nop
0x1800177ba  lea     rcx, [rbp+0F0h+arg_10]
0x1800177c1  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AEPEAX@Z$1?WinStationFreeMemory@@YAE0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,uchar (*)(void *),&WinStationFreeMemory(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,uchar (*)(void *),&WinStationFreeMemory(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800177c6  mov     edi, r12d
0x1800177c9  lea     rcx, [rsp+1F0h+TokenHandle]
0x1800177ce  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800177d3  mov     eax, edi
0x1800177d5  add     rsp, 1C0h
0x1800177dc  pop     r15
0x1800177de  pop     r14
0x1800177e0  pop     r12
0x1800177e2  pop     rdi
0x1800177e3  pop     rsi
0x1800177e4  pop     rbx
0x1800177e5  pop     rbp
0x1800177e6  retn
```
