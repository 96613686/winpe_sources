# GetExecutionParameters(Windows::ApplicationModel::Activation::IActivatedEventArgs *,DESKTOP_APPX_ACTIVATION_RESULT *,ActivationProperties &)

- ea: `0x1800b6398`
- end: `0x1800b67db`
- name: `?GetExecutionParameters@@YAXPEAUIActivatedEventArgs@Activation@ApplicationModel@Windows@@PEAUDESKTOP_APPX_ACTIVATION_RESULT@@AEAUActivationProperties@@@Z`
- size: `1091`
- prototype: `void(struct Windows::ApplicationModel::Activation::IActivatedEventArgs *, struct DESKTOP_APPX_ACTIVATION_RESULT *, struct ActivationProperties *)`
- caller_count: `1`
- callee_count: `20`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800b45b0`

## callees

- `0x180005fac`
- `0x18000c37c`
- `0x18000e234`
- `0x180010a84`
- `0x18001432c`
- `0x18002ca40`
- `0x18003b850`
- `0x18003d314`
- `0x18007e860`
- `0x1800b49e8`
- `0x1800b6398`
- `0x1800b67e4`
- `0x1800b6a64`
- `0x1800b76c0`
- `0x1800b83a4`
- `0x1800b84ec`
- `0x1800b8e2c`
- `0x1800b97bc`
- `0x1800b9b2c`
- `0x1800bbb94`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800b6458`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800b6458`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800b655e`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800b6598`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800b65d8`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800b6618`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800b6640`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800b6680`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800b66ca`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800b655e`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800b6598`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800b65d8`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800b6618`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800b6640`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800b6680`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800b66ca`
- `ntdll!RtlIsMultiSessionSku` at `0x1800b63dc`
- `ntdll!RtlIsMultiSessionSku` at `0x1800b63dc`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x1800b672a`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x1800b672a`

## string_xrefs

- `0x1800b6489`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-User.hpp`
- `0x1800b64cb`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-User.hpp`
- `0x1800b6772`: `onecore\base\appmodel\execmodel\desktopappx\lib\aamextensions.cpp`
- `0x1800b6787`: `onecore\base\appmodel\execmodel\desktopappx\lib\aamextensions.cpp`
- `0x1800b679c`: `onecore\base\appmodel\execmodel\desktopappx\lib\aamextensions.cpp`
- `0x1800b67b1`: `onecore\base\appmodel\execmodel\desktopappx\lib\aamextensions.cpp`
- `0x1800b67c9`: `onecore\base\appmodel\execmodel\desktopappx\lib\aamextensions.cpp`
- `0x1800b658b`: `Windows.Protocol`
- `0x1800b6633`: `Windows.StartupTask`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall GetExecutionParameters(
        struct Windows::ApplicationModel::Activation::IActivatedEventArgs *a1,
        struct DESKTOP_APPX_ACTIVATION_RESULT *a2,
        struct ActivationProperties *a3)
{
  int v6; // eax
  const unsigned __int16 *v7; // rdx
  int IsEffectiveSupportedUsersMultiple; // eax
  __int64 TargetUserTokenAndUserContext; // rax
  int token_information; // eax
  int v11; // esi
  HANDLE v12; // rcx
  HANDLE v13; // rbx
  int v14; // eax
  const WCHAR *v15; // rbx
  bool ApplicationLaunchParameters; // al
  bool v17; // zf
  unsigned int v18; // eax
  int bIgnoreCase; // [rsp+20h] [rbp-20h]
  const char *v20; // [rsp+28h] [rbp-18h]
  __int64 v21; // [rsp+30h] [rbp-10h] BYREF
  __int64 v22; // [rsp+38h] [rbp-8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+28h]
  HANDLE hObject; // [rsp+88h] [rbp+48h] BYREF

  v21 = 0;
  v6 = StateRepository::Cache::Manager_NoThrow::Open((StateRepository::Cache::Manager_NoThrow *)&v21);
  if ( v6 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1A2,
      (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\aamextensions.cpp",
      (const char *)(unsigned int)v6,
      bIgnoreCase);
  if ( !(unsigned __int8)RtlIsMultiSessionSku(retaddr) && *((_QWORD *)a3 + 40) )
  {
    LOBYTE(hObject) = 0;
    v7 = (const unsigned __int16 *)((char *)a3 + 128);
    if ( *((_QWORD *)a3 + 19) > 7u )
      v7 = *(const unsigned __int16 **)v7;
    IsEffectiveSupportedUsersMultiple = StateRepository::Cache::Entity::Package_NoThrow::GetIsEffectiveSupportedUsersMultiple(
                                          (struct StateRepository::Cache::Manager_NoThrow *)&v21,
                                          v7,
                                          (bool *)&hObject);
    if ( IsEffectiveSupportedUsersMultiple < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x1A7,
        (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\aamextensions.cpp",
        (const char *)(unsigned int)IsEffectiveSupportedUsersMultiple,
        bIgnoreCase);
    if ( (_BYTE)hObject )
    {
      *((_QWORD *)a3 + 40) = 0;
      TargetUserTokenAndUserContext = GetTargetUserTokenAndUserContext(&hObject, (char *)a3 + 320);
      wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>::operator=(
        (char *)a3 + 312,
        TargetUserTokenAndUserContext);
      if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
        CloseHandle(hObject);
    }
  }
  v22 = 0;
  hObject = 0;
  token_information = wil::get_token_information_nothrow<_TOKEN_USER,0>(&hObject, *((_QWORD *)a3 + 39));
  v11 = token_information;
  if ( token_information < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x146,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-User.hpp",
      (const char *)(unsigned int)token_information,
      bIgnoreCase);
    v12 = hObject;
    if ( !hObject )
      goto LABEL_16;
    goto LABEL_12;
  }
  v13 = hObject;
  v14 = StateRepository::Cache::Entity::User_NoThrow::GetByUserSid(
          (struct StateRepository::Cache::Manager_NoThrow *)&v21,
          *(PSID *)hObject,
          &v22);
  v11 = v14;
  if ( v14 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x147,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-User.hpp",
      (const char *)(unsigned int)v14,
      bIgnoreCase);
    v12 = v13;
LABEL_12:
    operator delete(v12);
    goto LABEL_16;
  }
  operator delete(v13);
  v11 = 0;
LABEL_16:
  if ( v11 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1B2,
      (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\aamextensions.cpp",
      (const char *)(unsigned int)v11,
      bIgnoreCase);
  if ( !v22 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1B3,
      (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\aamextensions.cpp",
      (const char *)0x80070490LL,
      bIgnoreCase);
  if ( *((_DWORD *)a3 + 98) != 1 )
  {
    GetApplicationLaunchParameters((struct StateRepository::Cache::Manager_NoThrow *)&v21, v22, a3);
LABEL_41:
    if ( *((_DWORD *)a3 + 72) != 1 )
      goto LABEL_43;
    goto LABEL_42;
  }
  v15 = (const WCHAR *)((char *)a3 + 256);
  if ( *((_QWORD *)a3 + 35) > 7u )
    v15 = *(const WCHAR **)v15;
  if ( !v15 || !*v15 )
  {
    v18 = wil::verify_hresult(2147942487LL);
    wil::details::in1diag3::Throw_HrMsg(
      retaddr,
      (void *)0x1BB,
      (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\aamextensions.cpp",
      (const char *)v18,
      (int)"ContractID required",
      v20);
  }
  if ( CompareStringOrdinal(v15, -1, L"Windows.Launch", 14, 1) == 2 || IsBackgroundExtensionContract(v15) )
  {
    ApplicationLaunchParameters = GetApplicationLaunchParameters(
                                    (struct StateRepository::Cache::Manager_NoThrow *)&v21,
                                    v22,
                                    a3);
  }
  else
  {
    if ( CompareStringOrdinal(v15, -1, L"Windows.Protocol", 16, 1) == 2 )
    {
      ApplicationLaunchParameters = GetProtocolLaunchParameters(
                                      a1,
                                      (struct StateRepository::Cache::Manager_NoThrow *)&v21,
                                      v22,
                                      a3);
      goto LABEL_38;
    }
    if ( CompareStringOrdinal(v15, -1, L"Windows.File", 12, 1) == 2 )
    {
      ApplicationLaunchParameters = GetFileLaunchParameters(
                                      a1,
                                      (struct StateRepository::Cache::Manager_NoThrow *)&v21,
                                      v22,
                                      a3);
      goto LABEL_38;
    }
    if ( CompareStringOrdinal(v15, -1, L"Windows.ShareTarget", 19, 1) == 2 )
      goto LABEL_33;
    if ( CompareStringOrdinal(v15, -1, L"Windows.StartupTask", 19, 1) == 2 )
    {
      ApplicationLaunchParameters = GetStartupTaskLaunchParameters(
                                      a1,
                                      (struct StateRepository::Cache::Manager_NoThrow *)&v21,
                                      v22,
                                      a3);
      goto LABEL_38;
    }
    if ( CompareStringOrdinal(v15, -1, L"Windows.PhoneCallActivation", 27, 1) == 2 )
    {
LABEL_33:
      ApplicationLaunchParameters = GetExtensionLaunchParameters(
                                      (struct StateRepository::Cache::Manager_NoThrow *)&v21,
                                      v22,
                                      a3);
    }
    else
    {
      if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_50902630>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_50902630>::GetImpl'::`2'::impl)
        || CompareStringOrdinal(v15, -1, L"Windows.GamingApp", 17, 1) != 2 )
      {
        goto LABEL_42;
      }
      GetGamingAppLaunchParameters(a1, (struct StateRepository::Cache::Manager_NoThrow *)&v21, v22, a3);
    }
  }
LABEL_38:
  if ( ApplicationLaunchParameters )
    goto LABEL_41;
LABEL_42:
  *(_QWORD *)a2 = 1;
LABEL_43:
  v17 = v21 == 0;
  v21 = 0;
  if ( !v17 )
    SRCacheManager_Close();
}

```

## disassembly

```asm
0x1800b6398  mov     [rsp-28h+arg_0], rbx
0x1800b639d  mov     [rsp-28h+arg_8], rsi
0x1800b63a2  mov     [rsp-28h+arg_10], rdi
0x1800b63a7  push    rbp
0x1800b63a8  push    r12
0x1800b63aa  push    r13
0x1800b63ac  push    r14
0x1800b63ae  push    r15
0x1800b63b0  mov     rbp, rsp
0x1800b63b3  sub     rsp, 40h
0x1800b63b7  mov     rdi, r8
0x1800b63ba  mov     r14, rdx
0x1800b63bd  mov     r15, rcx
0x1800b63c0  xor     r12d, r12d
0x1800b63c3  mov     [rbp+var_10], r12
0x1800b63c7  lea     rcx, [rbp+var_10]; this
0x1800b63cb  call    ?Open@Manager_NoThrow@Cache@StateRepository@@QEAAJXZ; StateRepository::Cache::Manager_NoThrow::Open(void)
0x1800b63d0  mov     rcx, [rbp+28h]; this
0x1800b63d4  test    eax, eax
0x1800b63d6  js      loc_1800B6784
0x1800b63dc  call    cs:__imp_RtlIsMultiSessionSku
0x1800b63e3  nop     dword ptr [rax+rax+00h]
0x1800b63e8  test    al, al
0x1800b63ea  jnz     short loc_1800B6464
0x1800b63ec  lea     rbx, [rdi+140h]
0x1800b63f3  cmp     [rbx], r12
0x1800b63f6  jz      short loc_1800B6464
0x1800b63f8  mov     byte ptr [rbp+hObject], r12b
0x1800b63fc  lea     rdx, [rdi+80h]
0x1800b6403  cmp     qword ptr [rdx+18h], 7
0x1800b6408  jbe     short loc_1800B640D
0x1800b640a  mov     rdx, [rdx]; unsigned __int16 *
0x1800b640d  lea     r8, [rbp+hObject]; bool *
0x1800b6411  lea     rcx, [rbp+var_10]; struct StateRepository::Cache::Manager_NoThrow *
0x1800b6415  call    ?GetIsEffectiveSupportedUsersMultiple@Package_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@PEBGAEA_N@Z; StateRepository::Cache::Entity::Package_NoThrow::GetIsEffectiveSupportedUsersMultiple(StateRepository::Cache::Manager_NoThrow &,ushort const *,bool &)
0x1800b641a  mov     rcx, [rbp+28h]; this
0x1800b641e  test    eax, eax
0x1800b6420  js      loc_1800B6799
0x1800b6426  cmp     byte ptr [rbp+hObject], r12b
0x1800b642a  jz      short loc_1800B6464
0x1800b642c  mov     [rbx], r12
0x1800b642f  mov     rdx, rbx
0x1800b6432  lea     rcx, [rbp+hObject]
0x1800b6436  call    ?GetTargetUserTokenAndUserContext@@YA?AV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@AEA_K@Z; GetTargetUserTokenAndUserContext(unsigned __int64 &)
0x1800b643b  lea     rcx, [rdi+138h]
0x1800b6442  mov     rdx, rax
0x1800b6445  call    ??4?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>> &&)
0x1800b644a  mov     rcx, [rbp+hObject]; hObject
0x1800b644e  lea     rax, [rcx-1]
0x1800b6452  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800b6456  ja      short loc_1800B6464
0x1800b6458  call    cs:__imp_CloseHandle
0x1800b645f  nop     dword ptr [rax+rax+00h]
0x1800b6464  mov     [rbp+var_8], r12
0x1800b6468  mov     [rbp+hObject], r12
0x1800b646c  mov     rdx, [rdi+138h]
0x1800b6473  lea     rcx, [rbp+hObject]
0x1800b6477  call    ??$get_token_information_nothrow@U_TOKEN_USER@@$0A@@wil@@YAJAEAV?$unique_ptr@U_TOKEN_USER@@Utoken_info_deleter@details@wil@@@wistd@@PEAX@Z; wil::get_token_information_nothrow<_TOKEN_USER,0>(wistd::unique_ptr<_TOKEN_USER,wil::details::token_info_deleter> &,void *)
0x1800b647c  mov     esi, eax
0x1800b647e  test    eax, eax
0x1800b6480  jns     short loc_1800B64AA
0x1800b6482  mov     rcx, [rbp+28h]; this
0x1800b6486  mov     r9d, eax; char *
0x1800b6489  lea     r8, aOnecorePrivate_9; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800b6490  mov     edx, 146h; void *
0x1800b6495  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b649a  mov     rcx, [rbp+hObject]; Block
0x1800b649e  test    rcx, rcx
0x1800b64a1  jz      short loc_1800B64EC
0x1800b64a3  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800b64a8  jmp     short loc_1800B64EC
0x1800b64aa  lea     r8, [rbp+var_8]; __int64 *
0x1800b64ae  mov     rbx, [rbp+hObject]
0x1800b64b2  mov     rdx, [rbx]; Sid
0x1800b64b5  lea     rcx, [rbp+var_10]; struct StateRepository::Cache::Manager_NoThrow *
0x1800b64b9  call    ?GetByUserSid@User_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@PEAXAEA_J@Z; StateRepository::Cache::Entity::User_NoThrow::GetByUserSid(StateRepository::Cache::Manager_NoThrow &,void *,__int64 &)
0x1800b64be  mov     esi, eax
0x1800b64c0  test    eax, eax
0x1800b64c2  jns     short loc_1800B64E1
0x1800b64c4  mov     rcx, [rbp+28h]; this
0x1800b64c8  mov     r9d, eax; char *
0x1800b64cb  lea     r8, aOnecorePrivate_9; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800b64d2  mov     edx, 147h; void *
0x1800b64d7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b64dc  mov     rcx, rbx
0x1800b64df  jmp     short loc_1800B64A3
0x1800b64e1  mov     rcx, rbx; Block
0x1800b64e4  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800b64e9  mov     esi, r12d
0x1800b64ec  mov     rcx, [rbp+28h]; this
0x1800b64f0  test    esi, esi
0x1800b64f2  js      loc_1800B67AE
0x1800b64f8  mov     rdx, [rbp+var_8]; __int64
0x1800b64fc  test    rdx, rdx
0x1800b64ff  setz    al
0x1800b6502  mov     rcx, [rbp+28h]; this
0x1800b6506  test    al, al
0x1800b6508  jnz     loc_1800B67C3
0x1800b650e  mov     esi, 1
0x1800b6513  cmp     [rdi+188h], esi
0x1800b6519  jnz     loc_1800B6706
0x1800b651f  lea     rbx, [rdi+100h]
0x1800b6526  cmp     qword ptr [rbx+18h], 7
0x1800b652b  jbe     short loc_1800B6530
0x1800b652d  mov     rbx, [rbx]
0x1800b6530  test    rbx, rbx
0x1800b6533  jz      loc_1800B6755
0x1800b6539  cmp     [rbx], r12w
0x1800b653d  jz      loc_1800B6755
0x1800b6543  mov     [rsp+40h+bIgnoreCase], esi; bIgnoreCase
0x1800b6547  mov     r9d, 0Eh; cchCount2
0x1800b654d  lea     r8, aWindowsLaunch; "Windows.Launch"
0x1800b6554  or      r13d, 0FFFFFFFFh
0x1800b6558  mov     edx, r13d; cchCount1
0x1800b655b  mov     rcx, rbx; lpString1
0x1800b655e  call    cs:__imp_CompareStringOrdinal
0x1800b6565  nop     dword ptr [rax+rax+00h]
0x1800b656a  cmp     eax, 2
0x1800b656d  jz      loc_1800B66F0
0x1800b6573  mov     rcx, rbx; unsigned __int16 *
0x1800b6576  call    ?IsBackgroundExtensionContract@@YA_NPEBG@Z; IsBackgroundExtensionContract(ushort const *)
0x1800b657b  test    al, al
0x1800b657d  jnz     loc_1800B66F0
0x1800b6583  mov     [rsp+40h+bIgnoreCase], esi; bIgnoreCase
0x1800b6587  lea     r9d, [r13+11h]; cchCount2
0x1800b658b  lea     r8, aWindowsProtoco; "Windows.Protocol"
0x1800b6592  mov     edx, r13d; cchCount1
0x1800b6595  mov     rcx, rbx; lpString1
0x1800b6598  call    cs:__imp_CompareStringOrdinal
0x1800b659f  nop     dword ptr [rax+rax+00h]
0x1800b65a4  cmp     eax, 2
0x1800b65a7  jnz     short loc_1800B65C1
0x1800b65a9  mov     r9, rdi; struct ActivationProperties *
0x1800b65ac  mov     r8, [rbp+var_8]; __int64
0x1800b65b0  lea     rdx, [rbp+var_10]; struct StateRepository::Cache::Manager_NoThrow *
0x1800b65b4  mov     rcx, r15; struct Windows::ApplicationModel::Activation::IActivatedEventArgs *
0x1800b65b7  call    ?GetProtocolLaunchParameters@@YA_NPEAUIActivatedEventArgs@Activation@ApplicationModel@Windows@@AEAVManager_NoThrow@Cache@StateRepository@@_JAEAUActivationProperties@@@Z; GetProtocolLaunchParameters(Windows::ApplicationModel::Activation::IActivatedEventArgs *,StateRepository::Cache::Manager_NoThrow &,__int64,ActivationProperties &)
0x1800b65bc  jmp     loc_1800B6700
0x1800b65c1  mov     [rsp+40h+bIgnoreCase], esi; bIgnoreCase
0x1800b65c5  mov     r9d, 0Ch; cchCount2
0x1800b65cb  lea     r8, aWindowsFile; "Windows.File"
0x1800b65d2  mov     edx, r13d; cchCount1
0x1800b65d5  mov     rcx, rbx; lpString1
0x1800b65d8  call    cs:__imp_CompareStringOrdinal
0x1800b65df  nop     dword ptr [rax+rax+00h]
0x1800b65e4  cmp     eax, 2
0x1800b65e7  jnz     short loc_1800B6601
0x1800b65e9  mov     r9, rdi; struct ActivationProperties *
0x1800b65ec  mov     r8, [rbp+var_8]; __int64
0x1800b65f0  lea     rdx, [rbp+var_10]; struct StateRepository::Cache::Manager_NoThrow *
0x1800b65f4  mov     rcx, r15; struct Windows::ApplicationModel::Activation::IActivatedEventArgs *
0x1800b65f7  call    ?GetFileLaunchParameters@@YA_NPEAUIActivatedEventArgs@Activation@ApplicationModel@Windows@@AEAVManager_NoThrow@Cache@StateRepository@@_JAEAUActivationProperties@@@Z; GetFileLaunchParameters(Windows::ApplicationModel::Activation::IActivatedEventArgs *,StateRepository::Cache::Manager_NoThrow &,__int64,ActivationProperties &)
0x1800b65fc  jmp     loc_1800B6700
0x1800b6601  mov     [rsp+40h+bIgnoreCase], esi; bIgnoreCase
0x1800b6605  mov     r9d, 13h; cchCount2
0x1800b660b  lea     r8, aWindowsShareta; "Windows.ShareTarget"
0x1800b6612  mov     edx, r13d; cchCount1
0x1800b6615  mov     rcx, rbx; lpString1
0x1800b6618  call    cs:__imp_CompareStringOrdinal
0x1800b661f  nop     dword ptr [rax+rax+00h]
0x1800b6624  cmp     eax, 2
0x1800b6627  jz      short loc_1800B6691
0x1800b6629  mov     [rsp+40h+bIgnoreCase], esi; bIgnoreCase
0x1800b662d  mov     r9d, 13h; cchCount2
0x1800b6633  lea     r8, aWindowsStartup; "Windows.StartupTask"
0x1800b663a  mov     edx, r13d; cchCount1
0x1800b663d  mov     rcx, rbx; lpString1
0x1800b6640  call    cs:__imp_CompareStringOrdinal
0x1800b6647  nop     dword ptr [rax+rax+00h]
0x1800b664c  cmp     eax, 2
0x1800b664f  jnz     short loc_1800B6669
0x1800b6651  mov     r9, rdi; struct ActivationProperties *
0x1800b6654  mov     r8, [rbp+var_8]; __int64
0x1800b6658  lea     rdx, [rbp+var_10]; struct StateRepository::Cache::Manager_NoThrow *
0x1800b665c  mov     rcx, r15; struct Windows::ApplicationModel::Activation::IActivatedEventArgs *
0x1800b665f  call    ?GetStartupTaskLaunchParameters@@YA_NPEAUIActivatedEventArgs@Activation@ApplicationModel@Windows@@AEAVManager_NoThrow@Cache@StateRepository@@_JAEAUActivationProperties@@@Z; GetStartupTaskLaunchParameters(Windows::ApplicationModel::Activation::IActivatedEventArgs *,StateRepository::Cache::Manager_NoThrow &,__int64,ActivationProperties &)
0x1800b6664  jmp     loc_1800B6700
0x1800b6669  mov     [rsp+40h+bIgnoreCase], esi; bIgnoreCase
0x1800b666d  mov     r9d, 1Bh; cchCount2
0x1800b6673  lea     r8, aWindowsPhoneca; "Windows.PhoneCallActivation"
0x1800b667a  mov     edx, r13d; cchCount1
0x1800b667d  mov     rcx, rbx; lpString1
0x1800b6680  call    cs:__imp_CompareStringOrdinal
0x1800b6687  nop     dword ptr [rax+rax+00h]
0x1800b668c  cmp     eax, 2
0x1800b668f  jnz     short loc_1800B66A3
0x1800b6691  mov     r8, rdi; struct ActivationProperties *
0x1800b6694  mov     rdx, [rbp+var_8]; __int64
0x1800b6698  lea     rcx, [rbp+var_10]; struct StateRepository::Cache::Manager_NoThrow *
0x1800b669c  call    ?GetExtensionLaunchParameters@@YA_NAEAVManager_NoThrow@Cache@StateRepository@@_JAEAUActivationProperties@@@Z; GetExtensionLaunchParameters(StateRepository::Cache::Manager_NoThrow &,__int64,ActivationProperties &)
0x1800b66a1  jmp     short loc_1800B6700
0x1800b66a3  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_50902630@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_50902630@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_50902630> `wil::Feature<__WilFeatureTraits_Feature_50902630>::GetImpl(void)'::`2'::impl
0x1800b66aa  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_50902630@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_50902630>::__private_IsEnabled(void)
0x1800b66af  test    al, al
0x1800b66b1  jz      short loc_1800B671A
0x1800b66b3  mov     [rsp+40h+bIgnoreCase], esi; bIgnoreCase
0x1800b66b7  mov     r9d, 11h; cchCount2
0x1800b66bd  lea     r8, aWindowsGaminga_0; "Windows.GamingApp"
0x1800b66c4  mov     edx, r13d; cchCount1
0x1800b66c7  mov     rcx, rbx; lpString1
0x1800b66ca  call    cs:__imp_CompareStringOrdinal
0x1800b66d1  nop     dword ptr [rax+rax+00h]
0x1800b66d6  cmp     eax, 2
0x1800b66d9  jnz     short loc_1800B671A
0x1800b66db  mov     r9, rdi; struct ActivationProperties *
0x1800b66de  mov     r8, [rbp+var_8]; __int64
0x1800b66e2  lea     rdx, [rbp+var_10]; struct StateRepository::Cache::Manager_NoThrow *
0x1800b66e6  mov     rcx, r15; struct Windows::ApplicationModel::Activation::IActivatedEventArgs *
0x1800b66e9  call    ?GetGamingAppLaunchParameters@@YA_NPEAUIActivatedEventArgs@Activation@ApplicationModel@Windows@@AEAVManager_NoThrow@Cache@StateRepository@@_JAEAUActivationProperties@@@Z; GetGamingAppLaunchParameters(Windows::ApplicationModel::Activation::IActivatedEventArgs *,StateRepository::Cache::Manager_NoThrow &,__int64,ActivationProperties &)
0x1800b66ee  jmp     short loc_1800B6700
0x1800b66f0  mov     r8, rdi; struct ActivationProperties *
0x1800b66f3  mov     rdx, [rbp+var_8]; __int64
0x1800b66f7  lea     rcx, [rbp+var_10]; struct StateRepository::Cache::Manager_NoThrow *
0x1800b66fb  call    ?GetApplicationLaunchParameters@@YA_NAEAVManager_NoThrow@Cache@StateRepository@@_JAEAUActivationProperties@@@Z; GetApplicationLaunchParameters(StateRepository::Cache::Manager_NoThrow &,__int64,ActivationProperties &)
0x1800b6700  test    al, al
0x1800b6702  jnz     short loc_1800B6712
0x1800b6704  jmp     short loc_1800B671A
0x1800b6706  mov     r8, rdi; struct ActivationProperties *
0x1800b6709  lea     rcx, [rbp+var_10]; struct StateRepository::Cache::Manager_NoThrow *
0x1800b670d  call    ?GetApplicationLaunchParameters@@YA_NAEAVManager_NoThrow@Cache@StateRepository@@_JAEAUActivationProperties@@@Z; GetApplicationLaunchParameters(StateRepository::Cache::Manager_NoThrow &,__int64,ActivationProperties &)
0x1800b6712  cmp     [rdi+120h], esi
0x1800b6718  jnz     short loc_1800B671D
0x1800b671a  mov     [r14], rsi
0x1800b671d  mov     rcx, [rbp+var_10]
0x1800b6721  test    rcx, rcx
0x1800b6724  mov     [rbp+var_10], r12
0x1800b6728  jz      short loc_1800B6736
0x1800b672a  call    cs:__imp_SRCacheManager_Close
0x1800b6731  nop     dword ptr [rax+rax+00h]
0x1800b6736  lea     r11, [rsp+40h+var_s0]
0x1800b673b  mov     rbx, [r11+30h]
0x1800b673f  mov     rsi, [r11+38h]
0x1800b6743  mov     rdi, [r11+40h]
0x1800b6747  mov     rsp, r11
0x1800b674a  pop     r15
0x1800b674c  pop     r14
0x1800b674e  pop     r13
0x1800b6750  pop     r12
0x1800b6752  pop     rbp
0x1800b6753  retn
0x1800b6755  mov     ecx, 80070057h
0x1800b675a  call    ?verify_hresult@wil@@YAJUhresult@winrt@@@Z; wil::verify_hresult(winrt::hresult)
0x1800b675f  mov     r9d, eax; char *
0x1800b6762  mov     rcx, [rbp+28h]; this
0x1800b6766  lea     rax, aContractidRequ; "ContractID required"
0x1800b676d  mov     qword ptr [rsp+40h+bIgnoreCase], rax; int
0x1800b6772  lea     r8, aOnecoreBaseApp_45; "onecore\\base\\appmodel\\execmodel\\des"...
0x1800b6779  mov     edx, 1BBh; void *
0x1800b677e  call    ?Throw_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_HrMsg(void *,uint,char const *,long,char const *,...)
0x1800b6784  mov     r9d, eax; char *
0x1800b6787  lea     r8, aOnecoreBaseApp_45; "onecore\\base\\appmodel\\execmodel\\des"...
0x1800b678e  mov     edx, 1A2h; void *
0x1800b6793  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800b6799  mov     r9d, eax; char *
0x1800b679c  lea     r8, aOnecoreBaseApp_45; "onecore\\base\\appmodel\\execmodel\\des"...
0x1800b67a3  mov     edx, 1A7h; void *
0x1800b67a8  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800b67ae  mov     r9d, esi; char *
0x1800b67b1  lea     r8, aOnecoreBaseApp_45; "onecore\\base\\appmodel\\execmodel\\des"...
0x1800b67b8  mov     edx, 1B2h; void *
0x1800b67bd  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800b67c3  mov     r9d, 80070490h; char *
0x1800b67c9  lea     r8, aOnecoreBaseApp_45; "onecore\\base\\appmodel\\execmodel\\des"...
0x1800b67d0  mov     edx, 1B3h; void *
0x1800b67d5  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
