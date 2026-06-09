# LogonThreadProcInternal(ulong)

- ea: `0x18001ce78`
- end: `0x18001d323`
- name: `?LogonThreadProcInternal@@YAJK@Z`
- size: `1195`
- prototype: `__int64 __fastcall(unsigned int)`
- caller_count: `1`
- callee_count: `30`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x18001ce30`

## callees

- `0x180004330`
- `0x180004730`
- `0x180005dd0`
- `0x180007b58`
- `0x1800084bc`
- `0x18001a680`
- `0x18001a858`
- `0x18001bdd8`
- `0x18001c130`
- `0x18001c4a0`
- `0x18001c85c`
- `0x18001ce78`
- `0x18001e010`
- `0x18001e200`
- `0x18001e2bc`
- `0x18001e380`
- `0x180024b84`
- `0x180030ad0`
- `0x180030af8`
- `0x180032894`
- `0x180032900`
- `0x180034f78`
- `0x180037054`
- `0x18003d678`
- `0x18003d7c4`
- `0x180040bcc`
- `0x1800440d0`
- `0x180049e10`
- `0x18005136c`
- `0x1800513f8`

## import_xrefs

- `ntdll!RtlGetActiveConsoleId` at `0x18001d09b`
- `ntdll!RtlGetActiveConsoleId` at `0x18001d09b`
- `ext-ms-win-profile-profsvc-l1-1-0!InitializeSuspendFolderPolicyAndUploadTaskConfig` at `0x18001d2c4`
- `ext-ms-win-profile-profsvc-l1-1-0!InitializeSuspendFolderPolicyAndUploadTaskConfig` at `0x18001d2c4`
- `ext-ms-win-session-winsta-l1-1-0!WinStationFreeMemory` at `0x18001d0d5`
- `ext-ms-win-session-winsta-l1-1-0!WinStationFreeMemory` at `0x18001d10b`
- `ext-ms-win-session-winsta-l1-1-0!WinStationFreeMemory` at `0x18001d141`
- `ext-ms-win-session-winsta-l1-1-0!WinStationFreeMemory` at `0x18001d0d5`
- `ext-ms-win-session-winsta-l1-1-0!WinStationFreeMemory` at `0x18001d10b`
- `ext-ms-win-session-winsta-l1-1-0!WinStationFreeMemory` at `0x18001d141`
- `ext-ms-win-session-winsta-l1-1-0!WinStationGetUserProfile` at `0x18001d176`
- `ext-ms-win-session-winsta-l1-1-0!WinStationGetUserProfile` at `0x18001d176`

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
  const struct _SN_ONLOGON_PARAMS *Params; // r15
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
  HANDLE v30; // [rsp+40h] [rbp-C0h] BYREF
  char v31; // [rsp+48h] [rbp-B8h]
  _PROFILEINFOW v32; // [rsp+50h] [rbp-B0h] BYREF
  void *v33[44]; // [rsp+90h] [rbp-70h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1F8h] [rbp+F8h]
  unsigned __int16 *v35; // [rsp+208h] [rbp+108h] BYREF
  unsigned __int16 *v36; // [rsp+210h] [rbp+110h] BYREF
  unsigned __int16 *v37; // [rsp+218h] [rbp+118h] BYREF

  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::GetImpl'::`2'::impl)
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
      Params = (const struct _SN_ONLOGON_PARAMS *)CUserProfileManager::GetParams(v7, a1);
      v9 = _SetupServerName(&v32, Params);
      if ( v9 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x2E1,
          (unsigned int)`DaclContainsPackageAndLpacCapabilitySid_'::`2'::AppPackageAuthority.SubAuthority,
          (const char *)(unsigned int)v9,
          v26);
      v10 = _SetupProfilePath(&v32, Params);
      if ( v10 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x2E2,
          (unsigned int)`DaclContainsPackageAndLpacCapabilitySid_'::`2'::AppPackageAuthority.SubAuthority,
          (const char *)(unsigned int)v10,
          v26);
      v11 = _SetupNetworkDefaultProfilePath(&v32, Params);
      v12 = retaddr;
      if ( v11 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x2E3,
          (unsigned int)`DaclContainsPackageAndLpacCapabilitySid_'::`2'::AppPackageAuthority.SubAuthority,
          (const char *)(unsigned int)v11,
          v26);
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
          if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::GetImpl'::`2'::impl)
            && Microsoft_Windows_User_Profiles_ServiceEnableBits < 0 )
          {
            McTemplateU0z_EtwEventWriteTransfer(v16, EVENT_IMPERSONATE_USER, v32.lpUserName);
          }
          CAutoImpersonate::ResetImpersonation(&v30);
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
                (unsigned int)`DaclContainsPackageAndLpacCapabilitySid_'::`2'::AppPackageAuthority.SubAuthority,
                (const char *)(unsigned int)UserProfile,
                v26);
          }
          if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::GetImpl'::`2'::impl)
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
            v23 = PrepareEnvBlock(UserToken, v35, v37, Params);
            v24 = retaddr;
            if ( v23 < 0 )
              wil::details::in1diag3::_Log_Hr(
                retaddr,
                (void *)0x30E,
                (unsigned int)`DaclContainsPackageAndLpacCapabilitySid_'::`2'::AppPackageAuthority.SubAuthority,
                (const char *)(unsigned int)v23,
                v27);
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
              (unsigned int)`DaclContainsPackageAndLpacCapabilitySid_'::`2'::AppPackageAuthority.SubAuthority,
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
        (unsigned int)`DaclContainsPackageAndLpacCapabilitySid_'::`2'::AppPackageAuthority.SubAuthority,
        (const char *)(unsigned int)UserNameAndDomain,
        v26);
      CAutoImpersonate::ResetImpersonation(&v30);
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x2D5,
        (unsigned int)`DaclContainsPackageAndLpacCapabilitySid_'::`2'::AppPackageAuthority.SubAuthority,
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
    (unsigned int)`DaclContainsPackageAndLpacCapabilitySid_'::`2'::AppPackageAuthority.SubAuthority,
    (const char *)(unsigned int)v4,
    v26);
  return v5;
}

```

## disassembly

```asm
0x18001ce78  push    rbp
0x18001ce7a  push    rbx
0x18001ce7b  push    rsi
0x18001ce7c  push    rdi
0x18001ce7d  push    r12
0x18001ce7f  push    r14
0x18001ce81  push    r15
0x18001ce83  lea     rbp, [rsp-0C0h]
0x18001ce8b  sub     rsp, 1C0h
0x18001ce92  mov     esi, ecx
0x18001ce94  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Profile_Service_ETW_Logging@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Profile_Service_ETW_Logging@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging> `wil::Feature<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::GetImpl(void)'::`2'::impl
0x18001ce9b  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Profile_Service_ETW_Logging@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::__private_IsEnabled(void)
0x18001cea0  xor     r12d, r12d
0x18001cea3  test    al, al
0x18001cea5  jz      short loc_18001CEBF
0x18001cea7  cmp     cs:Microsoft_Windows_User_Profiles_ServiceEnableBits, r12b
0x18001ceae  jge     short loc_18001CEBF
0x18001ceb0  mov     r8d, esi
0x18001ceb3  lea     rdx, EVENT_LOGON_THREAD_PROC_START
0x18001ceba  call    McTemplateU0q_EtwEventWriteTransfer
0x18001cebf  mov     edx, esi; unsigned int
0x18001cec1  mov     rcx, cs:?g_pProfMgr@@3PEAVCUserProfileManager@@EA; SRWLock
0x18001cec8  call    ?GetReadyEvent@CUserProfileManager@@QEAAPEAXK@Z; CUserProfileManager::GetReadyEvent(ulong)
0x18001cecd  mov     rcx, rax; void *
0x18001ced0  call    ?WaitForEventInternal@@YAJPEAX@Z; WaitForEventInternal(void *)
0x18001ced5  mov     edi, eax
0x18001ced7  test    eax, eax
0x18001ced9  jns     short loc_18001CEFB
0x18001cedb  mov     rcx, [rbp+0F8h]; this
0x18001cee2  mov     r9d, eax; char *
0x18001cee5  lea     r8, ?AppPackageAuthority@?1??DaclContainsPackageAndLpacCapabilitySid_@@YAHPEAX@Z@4U_SID_IDENTIFIER_AUTHORITY@@B.SubAuthority; unsigned int
0x18001ceec  mov     edx, 2D1h; void *
0x18001cef1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001cef6  jmp     loc_18001D30E
0x18001cefb  mov     [rsp+1F0h+TokenHandle], r12
0x18001cf00  xor     edx, edx
0x18001cf02  lea     rcx, [rsp+1F0h+TokenHandle]
0x18001cf07  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x18001cf0c  lea     rcx, [rsp+1F0h+TokenHandle]; TokenHandle
0x18001cf11  call    ?GetMyOwnToken@@YAJPEAPEAX@Z; GetMyOwnToken(void * *)
0x18001cf16  mov     edi, eax
0x18001cf18  test    eax, eax
0x18001cf1a  jns     short loc_18001CF3C
0x18001cf1c  mov     rcx, [rbp+0F8h]; this
0x18001cf23  mov     r9d, eax; char *
0x18001cf26  lea     r8, ?AppPackageAuthority@?1??DaclContainsPackageAndLpacCapabilitySid_@@YAHPEAX@Z@4U_SID_IDENTIFIER_AUTHORITY@@B.SubAuthority; unsigned int
0x18001cf2d  mov     edx, 2D5h; void *
0x18001cf32  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001cf37  jmp     loc_18001D304
0x18001cf3c  xorps   xmm0, xmm0
0x18001cf3f  xor     eax, eax
0x18001cf41  movups  xmmword ptr [rsp+1F0h+var_1A0.dwSize], xmm0
0x18001cf46  movups  xmmword ptr [rsp+1F0h+var_1A0.lpProfilePath], xmm0
0x18001cf4b  movups  xmmword ptr [rsp+1F0h+var_1A0.lpServerName], xmm0
0x18001cf50  mov     [rbp+0F0h+var_1A0.hProfile], rax
0x18001cf54  mov     [rsp+1F0h+var_1A0.dwSize], 38h ; '8'
0x18001cf5c  mov     edx, esi; unsigned int
0x18001cf5e  call    ?GetParams@CUserProfileManager@@QEAAPEAXK@Z; CUserProfileManager::GetParams(ulong)
0x18001cf63  mov     r15, rax
0x18001cf66  mov     rdx, rax; struct _SN_ONLOGON_PARAMS *
0x18001cf69  lea     rcx, [rsp+1F0h+var_1A0]; struct _PROFILEINFOW *
0x18001cf6e  call    ?_SetupServerName@@YAJPEAU_PROFILEINFOW@@PEBU_SN_ONLOGON_PARAMS@@@Z; _SetupServerName(_PROFILEINFOW *,_SN_ONLOGON_PARAMS const *)
0x18001cf73  mov     rcx, [rbp+0F8h]; this
0x18001cf7a  lea     rbx, ?AppPackageAuthority@?1??DaclContainsPackageAndLpacCapabilitySid_@@YAHPEAX@Z@4U_SID_IDENTIFIER_AUTHORITY@@B.SubAuthority; _SID_IDENTIFIER_AUTHORITY const `DaclContainsPackageAndLpacCapabilitySid_(void *)'::`2'::AppPackageAuthority ...
0x18001cf81  test    eax, eax
0x18001cf83  jns     short loc_18001CF95
0x18001cf85  mov     r9d, eax; char *
0x18001cf88  mov     r8, rbx; unsigned int
0x18001cf8b  mov     edx, 2E1h; void *
0x18001cf90  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18001cf95  mov     rdx, r15; struct _SN_ONLOGON_PARAMS *
0x18001cf98  lea     rcx, [rsp+1F0h+var_1A0]; struct _PROFILEINFOW *
0x18001cf9d  call    ?_SetupProfilePath@@YAJPEAU_PROFILEINFOW@@PEBU_SN_ONLOGON_PARAMS@@@Z; _SetupProfilePath(_PROFILEINFOW *,_SN_ONLOGON_PARAMS const *)
0x18001cfa2  mov     rcx, [rbp+0F8h]; this
0x18001cfa9  test    eax, eax
0x18001cfab  jns     short loc_18001CFBD
0x18001cfad  mov     r9d, eax; char *
0x18001cfb0  mov     r8, rbx; unsigned int
0x18001cfb3  mov     edx, 2E2h; void *
0x18001cfb8  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18001cfbd  mov     rdx, r15; struct _SN_ONLOGON_PARAMS *
0x18001cfc0  lea     rcx, [rsp+1F0h+var_1A0]; struct _PROFILEINFOW *
0x18001cfc5  call    ?_SetupNetworkDefaultProfilePath@@YAJPEAU_PROFILEINFOW@@PEBU_SN_ONLOGON_PARAMS@@@Z; _SetupNetworkDefaultProfilePath(_PROFILEINFOW *,_SN_ONLOGON_PARAMS const *)
0x18001cfca  mov     rcx, [rbp+0F8h]; this
0x18001cfd1  test    eax, eax
0x18001cfd3  jns     short loc_18001CFE5
0x18001cfd5  mov     r9d, eax; char *
0x18001cfd8  mov     r8, rbx; unsigned int
0x18001cfdb  mov     edx, 2E3h; void *
0x18001cfe0  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18001cfe5  mov     edx, esi; unsigned int
0x18001cfe7  call    ?GetUserToken@CUserProfileManager@@QEAAPEAXK@Z; CUserProfileManager::GetUserToken(ulong)
0x18001cfec  mov     r14, rax
0x18001cfef  mov     [rsp+1F0h+var_1B0], r12
0x18001cff4  mov     [rsp+1F0h+var_1A8], r12b
0x18001cff9  mov     rdx, rax; void *
0x18001cffc  lea     rcx, [rsp+1F0h+var_1B0]; this
0x18001d001  call    ?ImpersonateUser@CAutoImpersonate@@QEAAJPEAX@Z; CAutoImpersonate::ImpersonateUser(void *)
0x18001d006  mov     edi, eax
0x18001d008  test    eax, eax
0x18001d00a  jns     short loc_18001D033
0x18001d00c  mov     edx, 2EBh; void *
0x18001d011  mov     r8, rbx; unsigned int
0x18001d014  mov     r9d, eax; char *
0x18001d017  mov     rcx, [rbp+0F8h]; this
0x18001d01e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001d023  nop
0x18001d024  lea     rcx, [rsp+1F0h+var_1B0]; this
0x18001d029  call    ?ResetImpersonation@CAutoImpersonate@@QEAAXXZ; CAutoImpersonate::ResetImpersonation(void)
0x18001d02e  jmp     loc_18001D304
0x18001d033  xor     r8d, r8d; unsigned __int16 **
0x18001d036  lea     rdx, [rsp+1F0h+var_1A0.lpUserName]; unsigned __int16 **
0x18001d03b  lea     ecx, [r8+2]; NameFormat
0x18001d03f  call    ?GetUserNameAndDomain@@YAJW4EXTENDED_NAME_FORMAT@@PEAPEAG1@Z; GetUserNameAndDomain(EXTENDED_NAME_FORMAT,ushort * *,ushort * *)
0x18001d044  mov     edi, eax
0x18001d046  test    eax, eax
0x18001d048  jns     short loc_18001D051
0x18001d04a  mov     edx, 2ECh
0x18001d04f  jmp     short loc_18001D011
0x18001d051  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Profile_Service_ETW_Logging@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Profile_Service_ETW_Logging@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging> `wil::Feature<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::GetImpl(void)'::`2'::impl
0x18001d058  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Profile_Service_ETW_Logging@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::__private_IsEnabled(void)
0x18001d05d  test    al, al
0x18001d05f  jz      short loc_18001D07C
0x18001d061  cmp     cs:Microsoft_Windows_User_Profiles_ServiceEnableBits, r12b
0x18001d068  jge     short loc_18001D07C
0x18001d06a  mov     r8, [rsp+1F0h+var_1A0.lpUserName]
0x18001d06f  lea     rdx, EVENT_IMPERSONATE_USER
0x18001d076  call    McTemplateU0z_EtwEventWriteTransfer
0x18001d07b  nop
0x18001d07c  lea     rcx, [rsp+1F0h+var_1B0]; this
0x18001d081  call    ?ResetImpersonation@CAutoImpersonate@@QEAAXXZ; CAutoImpersonate::ResetImpersonation(void)
0x18001d086  mov     [rbp+0F0h+arg_10], r12
0x18001d08d  mov     [rbp+0F0h+arg_8], r12
0x18001d094  mov     [rbp+0F0h+arg_18], r12
0x18001d09b  call    cs:__imp_RtlGetActiveConsoleId
0x18001d0a2  nop     dword ptr [rax+rax+00h]
0x18001d0a7  cmp     eax, esi
0x18001d0a9  jz      loc_18001D19D
0x18001d0af  call    IsWinStationGetUserProfilePresent
0x18001d0b4  test    al, al
0x18001d0b6  jz      loc_18001D19D
0x18001d0bc  mov     rdi, [rbp+0F0h+arg_18]
0x18001d0c3  test    rdi, rdi
0x18001d0c6  jz      short loc_18001D0EB
0x18001d0c8  lea     rcx, [rsp+1F0h+var_1C0]; this
0x18001d0cd  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18001d0d2  mov     rcx, rdi
0x18001d0d5  call    cs:__imp_WinStationFreeMemory
0x18001d0dc  nop     dword ptr [rax+rax+00h]
0x18001d0e1  lea     rcx, [rsp+1F0h+var_1C0]; this
0x18001d0e6  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18001d0eb  mov     [rbp+0F0h+arg_18], r12
0x18001d0f2  mov     rdi, [rbp+0F0h+arg_8]
0x18001d0f9  test    rdi, rdi
0x18001d0fc  jz      short loc_18001D121
0x18001d0fe  lea     rcx, [rsp+1F0h+var_1C0]; this
0x18001d103  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18001d108  mov     rcx, rdi
0x18001d10b  call    cs:__imp_WinStationFreeMemory
0x18001d112  nop     dword ptr [rax+rax+00h]
0x18001d117  lea     rcx, [rsp+1F0h+var_1C0]; this
0x18001d11c  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18001d121  mov     [rbp+0F0h+arg_8], r12
0x18001d128  mov     rdi, [rbp+0F0h+arg_10]
0x18001d12f  test    rdi, rdi
0x18001d132  jz      short loc_18001D157
0x18001d134  lea     rcx, [rsp+1F0h+var_1C0]; this
0x18001d139  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18001d13e  mov     rcx, rdi
0x18001d141  call    cs:__imp_WinStationFreeMemory
0x18001d148  nop     dword ptr [rax+rax+00h]
0x18001d14d  lea     rcx, [rsp+1F0h+var_1C0]; this
0x18001d152  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18001d157  mov     [rbp+0F0h+arg_10], r12
0x18001d15e  lea     r9, [rbp+0F0h+arg_18]
0x18001d165  lea     r8, [rbp+0F0h+arg_8]
0x18001d16c  lea     rdx, [rbp+0F0h+arg_10]
0x18001d173  mov     rcx, r14
0x18001d176  call    cs:__imp_WinStationGetUserProfile
0x18001d17d  nop     dword ptr [rax+rax+00h]
0x18001d182  mov     rcx, [rbp+0F8h]; this
0x18001d189  test    eax, eax
0x18001d18b  jns     short loc_18001D19D
0x18001d18d  mov     r9d, eax; char *
0x18001d190  mov     r8, rbx; unsigned int
0x18001d193  mov     edx, 2FDh; void *
0x18001d198  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18001d19d  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Profile_Service_ETW_Logging@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Profile_Service_ETW_Logging@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging> `wil::Feature<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::GetImpl(void)'::`2'::impl
0x18001d1a4  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Profile_Service_ETW_Logging@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::__private_IsEnabled(void)
0x18001d1a9  test    al, al
0x18001d1ab  jz      short loc_18001D1DC
0x18001d1ad  cmp     cs:Microsoft_Windows_User_Profiles_ServiceEnableBits, r12b
0x18001d1b4  jge     short loc_18001D1DC
0x18001d1b6  mov     rax, [rbp+0F0h+arg_18]
0x18001d1bd  mov     [rsp+1F0h+var_1D0], rax
0x18001d1c2  mov     r9, [rbp+0F0h+arg_8]
0x18001d1c9  mov     r8, [rbp+0F0h+arg_10]
0x18001d1d0  lea     rdx, EVENT_LOGON_THREAD_PROC_TSDATA
0x18001d1d7  call    McTemplateU0zzz_EtwEventWriteTransfer
0x18001d1dc  mov     [rsp+1F0h+var_1D0], r15; struct _SN_ONLOGON_PARAMS *
0x18001d1e1  mov     r9, [rbp+0F0h+arg_8]; unsigned __int16 *
0x18001d1e8  mov     r8, [rbp+0F0h+arg_10]; unsigned __int16 *
0x18001d1ef  lea     rdx, [rsp+1F0h+var_1A0]; struct _PROFILEINFOW *
0x18001d1f4  mov     rcx, r14; void *
0x18001d1f7  call    ?_WaitForNetworkIfNecessary@@YAXPEAXQEAU_PROFILEINFOW@@PEBG2PEBU_SN_ONLOGON_PARAMS@@@Z; _WaitForNetworkIfNecessary(void *,_PROFILEINFOW * const,ushort const *,ushort const *,_SN_ONLOGON_PARAMS const *)
0x18001d1fc  lea     rcx, [rbp+0F0h+var_160]; this
0x18001d200  call    ??0CUserProfile@@QEAA@XZ; CUserProfile::CUserProfile(void)
0x18001d205  nop
0x18001d206  mov     rax, [rbp+0F0h+arg_10]
0x18001d20d  mov     [rsp+1F0h+var_1C8], rax; unsigned __int16 *
0x18001d212  mov     dword ptr [rsp+1F0h+var_1D0], esi; int
0x18001d216  lea     r9, [rsp+1F0h+var_1A0]; struct _PROFILEINFOW *
0x18001d21b  mov     r8, r14; void *
0x18001d21e  mov     rdx, [rsp+1F0h+TokenHandle]; void *
0x18001d223  lea     rcx, [rbp+0F0h+var_160]; this
0x18001d227  call    ?Load@CUserProfile@@QEAAJPEAX0PEAU_PROFILEINFOW@@KPEBG@Z; CUserProfile::Load(void *,void *,_PROFILEINFOW *,ulong,ushort const *)
0x18001d22c  mov     edi, eax
0x18001d22e  test    eax, eax
0x18001d230  jns     short loc_18001D27F
0x18001d232  mov     rcx, [rbp+0F8h]; this
0x18001d239  mov     r9d, eax; char *
0x18001d23c  mov     r8, rbx; unsigned int
0x18001d23f  mov     edx, 30Ah; void *
0x18001d244  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001d249  nop
0x18001d24a  lea     rcx, [rbp+0F0h+var_160]; this
0x18001d24e  call    ??1CUserProfile@@QEAA@XZ; CUserProfile::~CUserProfile(void)
0x18001d253  nop
0x18001d254  lea     rcx, [rbp+0F0h+arg_18]
0x18001d25b  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AEPEAX@Z$1?WinStationFreeMemory@@YAE0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,uchar (*)(void *),&WinStationFreeMemory(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,uchar (*)(void *),&WinStationFreeMemory(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18001d260  nop
0x18001d261  lea     rcx, [rbp+0F0h+arg_8]
0x18001d268  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AEPEAX@Z$1?WinStationFreeMemory@@YAE0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,uchar (*)(void *),&WinStationFreeMemory(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,uchar (*)(void *),&WinStationFreeMemory(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18001d26d  nop
0x18001d26e  lea     rcx, [rbp+0F0h+arg_10]
0x18001d275  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AEPEAX@Z$1?WinStationFreeMemory@@YAE0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,uchar (*)(void *),&WinStationFreeMemory(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,uchar (*)(void *),&WinStationFreeMemory(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18001d27a  jmp     loc_18001D304
0x18001d27f  mov     r9, r15; struct _SN_ONLOGON_PARAMS *
0x18001d282  mov     r8, [rbp+0F0h+arg_18]; unsigned __int16 *
0x18001d289  mov     rdx, [rbp+0F0h+arg_8]; unsigned __int16 *
0x18001d290  mov     rcx, r14; TokenHandle
0x18001d293  call    ?PrepareEnvBlock@@YAJPEAXPEBG1PEAU_SN_ONLOGON_PARAMS@@@Z; PrepareEnvBlock(void *,ushort const *,ushort const *,_SN_ONLOGON_PARAMS *)
0x18001d298  mov     rcx, [rbp+0F8h]; this
0x18001d29f  test    eax, eax
0x18001d2a1  jns     short loc_18001D2B3
0x18001d2a3  mov     r9d, eax; char *
0x18001d2a6  mov     r8, rbx; unsigned int
0x18001d2a9  mov     edx, 30Eh; void *
0x18001d2ae  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18001d2b3  call    IsWaitForNetworkForRoamingProfilePresent
0x18001d2b8  test    al, al
0x18001d2ba  jz      short loc_18001D2D1
0x18001d2bc  mov     edx, 1
0x18001d2c1  mov     rcx, r14
0x18001d2c4  call    cs:__imp_InitializeSuspendFolderPolicyAndUploadTaskConfig
0x18001d2cb  nop     dword ptr [rax+rax+00h]
0x18001d2d0  nop
0x18001d2d1  lea     rcx, [rbp+0F0h+var_160]; this
0x18001d2d5  call    ??1CUserProfile@@QEAA@XZ; CUserProfile::~CUserProfile(void)
0x18001d2da  nop
0x18001d2db  lea     rcx, [rbp+0F0h+arg_18]
0x18001d2e2  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AEPEAX@Z$1?WinStationFreeMemory@@YAE0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,uchar (*)(void *),&WinStationFreeMemory(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,uchar (*)(void *),&WinStationFreeMemory(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18001d2e7  nop
0x18001d2e8  lea     rcx, [rbp+0F0h+arg_8]
0x18001d2ef  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AEPEAX@Z$1?WinStationFreeMemory@@YAE0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,uchar (*)(void *),&WinStationFreeMemory(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,uchar (*)(void *),&WinStationFreeMemory(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18001d2f4  nop
0x18001d2f5  lea     rcx, [rbp+0F0h+arg_10]
0x18001d2fc  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AEPEAX@Z$1?WinStationFreeMemory@@YAE0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,uchar (*)(void *),&WinStationFreeMemory(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,uchar (*)(void *),&WinStationFreeMemory(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18001d301  mov     edi, r12d
0x18001d304  lea     rcx, [rsp+1F0h+TokenHandle]
0x18001d309  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18001d30e  mov     eax, edi
0x18001d310  add     rsp, 1C0h
0x18001d317  pop     r15
0x18001d319  pop     r14
0x18001d31b  pop     r12
0x18001d31d  pop     rdi
0x18001d31e  pop     rsi
0x18001d31f  pop     rbx
0x18001d320  pop     rbp
0x18001d321  retn
```
