# GetExecutionParameters(Windows::ApplicationModel::Activation::IActivatedEventArgs *,DESKTOP_APPX_ACTIVATION_RESULT *,ActivationProperties &)

- ea: `0x1800b8250`
- end: `0x1800b8685`
- name: `?GetExecutionParameters@@YAXPEAUIActivatedEventArgs@Activation@ApplicationModel@Windows@@PEAUDESKTOP_APPX_ACTIVATION_RESULT@@AEAUActivationProperties@@@Z`
- size: `1077`
- prototype: `void(struct Windows::ApplicationModel::Activation::IActivatedEventArgs *, struct DESKTOP_APPX_ACTIVATION_RESULT *, struct ActivationProperties *)`
- caller_count: `1`
- callee_count: `20`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800b617c`

## callees

- `0x1800057fc`
- `0x18000e074`
- `0x18000ff24`
- `0x1800125f4`
- `0x1800160a0`
- `0x18002d56c`
- `0x18003d45c`
- `0x18003f050`
- `0x180080390`
- `0x1800b671c`
- `0x1800b8250`
- `0x1800b868c`
- `0x1800b8910`
- `0x1800b9520`
- `0x1800ba1ec`
- `0x1800ba360`
- `0x1800bac84`
- `0x1800bb650`
- `0x1800bb920`
- `0x1800bda34`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800b8305`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800b8305`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800b8415`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800b844f`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800b848f`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800b84cf`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800b84f7`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800b8537`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800b8581`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800b8415`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800b844f`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800b848f`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800b84cf`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800b84f7`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800b8537`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800b8581`
- `ntdll!RtlIsMultiSessionSku` at `0x1800b8289`
- `ntdll!RtlIsMultiSessionSku` at `0x1800b8289`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x1800b85e1`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x1800b85e1`

## string_xrefs

- `0x1800b8336`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-User.hpp`
- `0x1800b8378`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-User.hpp`
- `0x1800b861c`: `onecore\base\appmodel\execmodel\desktopappx\lib\aamextensions.cpp`
- `0x1800b8631`: `onecore\base\appmodel\execmodel\desktopappx\lib\aamextensions.cpp`
- `0x1800b8646`: `onecore\base\appmodel\execmodel\desktopappx\lib\aamextensions.cpp`
- `0x1800b865b`: `onecore\base\appmodel\execmodel\desktopappx\lib\aamextensions.cpp`
- `0x1800b8673`: `onecore\base\appmodel\execmodel\desktopappx\lib\aamextensions.cpp`
- `0x1800b8442`: `Windows.Protocol`
- `0x1800b84ea`: `Windows.StartupTask`

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
  int v11; // edi
  HANDLE v12; // rcx
  HANDLE v13; // rsi
  int v14; // eax
  const WCHAR *v15; // rdi
  bool ApplicationLaunchParameters; // al
  bool v17; // zf
  unsigned int v18; // eax
  int bIgnoreCase; // [rsp+20h] [rbp-28h]
  const char *v20; // [rsp+28h] [rbp-20h]
  __int64 v21; // [rsp+30h] [rbp-18h] BYREF
  __int64 v22; // [rsp+38h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+40h]
  HANDLE hObject; // [rsp+A8h] [rbp+60h] BYREF

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
      goto LABEL_19;
    goto LABEL_12;
  }
  v13 = hObject;
  v14 = StateRepository::Cache::Entity::User_NoThrow::GetByUserSid(
          (struct StateRepository::Cache::Manager_NoThrow *)&v21,
          *(PSID *)hObject,
          &v22);
  v11 = v14;
  if ( v14 >= 0 )
  {
    if ( v13 )
      operator delete(v13);
    v11 = 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x147,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-User.hpp",
      (const char *)(unsigned int)v14,
      bIgnoreCase);
    if ( v13 )
    {
      v12 = v13;
LABEL_12:
      operator delete(v12);
    }
  }
LABEL_19:
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
LABEL_44:
    if ( *((_DWORD *)a3 + 72) != 1 )
      goto LABEL_46;
    goto LABEL_45;
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
      goto LABEL_41;
    }
    if ( CompareStringOrdinal(v15, -1, L"Windows.File", 12, 1) == 2 )
    {
      ApplicationLaunchParameters = GetFileLaunchParameters(
                                      a1,
                                      (struct StateRepository::Cache::Manager_NoThrow *)&v21,
                                      v22,
                                      a3);
      goto LABEL_41;
    }
    if ( CompareStringOrdinal(v15, -1, L"Windows.ShareTarget", 19, 1) == 2 )
      goto LABEL_36;
    if ( CompareStringOrdinal(v15, -1, L"Windows.StartupTask", 19, 1) == 2 )
    {
      ApplicationLaunchParameters = GetStartupTaskLaunchParameters(
                                      a1,
                                      (struct StateRepository::Cache::Manager_NoThrow *)&v21,
                                      v22,
                                      a3);
      goto LABEL_41;
    }
    if ( CompareStringOrdinal(v15, -1, L"Windows.PhoneCallActivation", 27, 1) == 2 )
    {
LABEL_36:
      ApplicationLaunchParameters = GetExtensionLaunchParameters(
                                      (struct StateRepository::Cache::Manager_NoThrow *)&v21,
                                      v22,
                                      a3);
    }
    else
    {
      if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_50902630>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_50902630>::GetImpl'::`2'::impl)
        || CompareStringOrdinal(v15, -1, L"Windows.GamingApp", 17, 1) != 2 )
      {
        goto LABEL_45;
      }
      GetGamingAppLaunchParameters(a1, (struct StateRepository::Cache::Manager_NoThrow *)&v21, v22, a3);
    }
  }
LABEL_41:
  if ( ApplicationLaunchParameters )
    goto LABEL_44;
LABEL_45:
  *(_QWORD *)a2 = 1;
LABEL_46:
  v17 = v21 == 0;
  v21 = 0;
  if ( !v17 )
    SRCacheManager_Close();
}

```

## disassembly

```asm
0x1800b8250  push    rbp
0x1800b8252  push    rbx
0x1800b8253  push    rsi
0x1800b8254  push    rdi
0x1800b8255  push    r12
0x1800b8257  push    r13
0x1800b8259  push    r14
0x1800b825b  push    r15
0x1800b825d  mov     rbp, rsp
0x1800b8260  sub     rsp, 48h
0x1800b8264  mov     rbx, r8
0x1800b8267  mov     r14, rdx
0x1800b826a  mov     r15, rcx
0x1800b826d  xor     r12d, r12d
0x1800b8270  mov     [rbp+var_18], r12
0x1800b8274  lea     rcx, [rbp+var_18]; this
0x1800b8278  call    ?Open@Manager_NoThrow@Cache@StateRepository@@QEAAJXZ; StateRepository::Cache::Manager_NoThrow::Open(void)
0x1800b827d  mov     rcx, [rbp+40h]; this
0x1800b8281  test    eax, eax
0x1800b8283  js      loc_1800B862E
0x1800b8289  call    cs:__imp_RtlIsMultiSessionSku
0x1800b8290  nop     dword ptr [rax+rax+00h]
0x1800b8295  test    al, al
0x1800b8297  jnz     short loc_1800B8311
0x1800b8299  lea     rdi, [rbx+140h]
0x1800b82a0  cmp     [rdi], r12
0x1800b82a3  jz      short loc_1800B8311
0x1800b82a5  mov     byte ptr [rbp+hObject], r12b
0x1800b82a9  lea     rdx, [rbx+80h]
0x1800b82b0  cmp     qword ptr [rdx+18h], 7
0x1800b82b5  jbe     short loc_1800B82BA
0x1800b82b7  mov     rdx, [rdx]; unsigned __int16 *
0x1800b82ba  lea     r8, [rbp+hObject]; bool *
0x1800b82be  lea     rcx, [rbp+var_18]; struct StateRepository::Cache::Manager_NoThrow *
0x1800b82c2  call    ?GetIsEffectiveSupportedUsersMultiple@Package_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@PEBGAEA_N@Z; StateRepository::Cache::Entity::Package_NoThrow::GetIsEffectiveSupportedUsersMultiple(StateRepository::Cache::Manager_NoThrow &,ushort const *,bool &)
0x1800b82c7  mov     rcx, [rbp+40h]; this
0x1800b82cb  test    eax, eax
0x1800b82cd  js      loc_1800B8643
0x1800b82d3  cmp     byte ptr [rbp+hObject], r12b
0x1800b82d7  jz      short loc_1800B8311
0x1800b82d9  mov     [rdi], r12
0x1800b82dc  mov     rdx, rdi
0x1800b82df  lea     rcx, [rbp+hObject]
0x1800b82e3  call    ?GetTargetUserTokenAndUserContext@@YA?AV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@AEA_K@Z; GetTargetUserTokenAndUserContext(unsigned __int64 &)
0x1800b82e8  lea     rcx, [rbx+138h]
0x1800b82ef  mov     rdx, rax
0x1800b82f2  call    ??4?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>> &&)
0x1800b82f7  mov     rcx, [rbp+hObject]; hObject
0x1800b82fb  lea     rax, [rcx-1]
0x1800b82ff  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800b8303  ja      short loc_1800B8311
0x1800b8305  call    cs:__imp_CloseHandle
0x1800b830c  nop     dword ptr [rax+rax+00h]
0x1800b8311  mov     [rbp+var_10], r12
0x1800b8315  mov     [rbp+hObject], r12
0x1800b8319  mov     rdx, [rbx+138h]
0x1800b8320  lea     rcx, [rbp+hObject]
0x1800b8324  call    ??$get_token_information_nothrow@U_TOKEN_USER@@$0A@@wil@@YAJAEAV?$unique_ptr@U_TOKEN_USER@@Utoken_info_deleter@details@wil@@@wistd@@PEAX@Z; wil::get_token_information_nothrow<_TOKEN_USER,0>(wistd::unique_ptr<_TOKEN_USER,wil::details::token_info_deleter> &,void *)
0x1800b8329  mov     edi, eax
0x1800b832b  test    eax, eax
0x1800b832d  jns     short loc_1800B8357
0x1800b832f  mov     rcx, [rbp+40h]; this
0x1800b8333  mov     r9d, eax; char *
0x1800b8336  lea     r8, aOnecorePrivate_9; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800b833d  mov     edx, 146h; void *
0x1800b8342  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b8347  mov     rcx, [rbp+hObject]; Block
0x1800b834b  test    rcx, rcx
0x1800b834e  jz      short loc_1800B83A3
0x1800b8350  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800b8355  jmp     short loc_1800B83A3
0x1800b8357  lea     r8, [rbp+var_10]; __int64 *
0x1800b835b  mov     rsi, [rbp+hObject]
0x1800b835f  mov     rdx, [rsi]; Sid
0x1800b8362  lea     rcx, [rbp+var_18]; struct StateRepository::Cache::Manager_NoThrow *
0x1800b8366  call    ?GetByUserSid@User_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@PEAXAEA_J@Z; StateRepository::Cache::Entity::User_NoThrow::GetByUserSid(StateRepository::Cache::Manager_NoThrow &,void *,__int64 &)
0x1800b836b  mov     edi, eax
0x1800b836d  test    eax, eax
0x1800b836f  jns     short loc_1800B8393
0x1800b8371  mov     rcx, [rbp+40h]; this
0x1800b8375  mov     r9d, eax; char *
0x1800b8378  lea     r8, aOnecorePrivate_9; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800b837f  mov     edx, 147h; void *
0x1800b8384  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b8389  test    rsi, rsi
0x1800b838c  jz      short loc_1800B83A3
0x1800b838e  mov     rcx, rsi
0x1800b8391  jmp     short loc_1800B8350
0x1800b8393  test    rsi, rsi
0x1800b8396  jz      short loc_1800B83A0
0x1800b8398  mov     rcx, rsi; Block
0x1800b839b  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800b83a0  mov     edi, r12d
0x1800b83a3  mov     rcx, [rbp+40h]; this
0x1800b83a7  test    edi, edi
0x1800b83a9  js      loc_1800B8658
0x1800b83af  mov     rdx, [rbp+var_10]; __int64
0x1800b83b3  test    rdx, rdx
0x1800b83b6  setz    al
0x1800b83b9  mov     rcx, [rbp+40h]; this
0x1800b83bd  test    al, al
0x1800b83bf  jnz     loc_1800B866D
0x1800b83c5  mov     esi, 1
0x1800b83ca  cmp     [rbx+188h], esi
0x1800b83d0  jnz     loc_1800B85BD
0x1800b83d6  lea     rdi, [rbx+100h]
0x1800b83dd  cmp     qword ptr [rdi+18h], 7
0x1800b83e2  jbe     short loc_1800B83E7
0x1800b83e4  mov     rdi, [rdi]
0x1800b83e7  test    rdi, rdi
0x1800b83ea  jz      loc_1800B85FF
0x1800b83f0  cmp     [rdi], r12w
0x1800b83f4  jz      loc_1800B85FF
0x1800b83fa  mov     [rsp+48h+bIgnoreCase], esi; bIgnoreCase
0x1800b83fe  mov     r9d, 0Eh; cchCount2
0x1800b8404  lea     r8, aWindowsLaunch; "Windows.Launch"
0x1800b840b  or      r13d, 0FFFFFFFFh
0x1800b840f  mov     edx, r13d; cchCount1
0x1800b8412  mov     rcx, rdi; lpString1
0x1800b8415  call    cs:__imp_CompareStringOrdinal
0x1800b841c  nop     dword ptr [rax+rax+00h]
0x1800b8421  cmp     eax, 2
0x1800b8424  jz      loc_1800B85A7
0x1800b842a  mov     rcx, rdi; unsigned __int16 *
0x1800b842d  call    ?IsBackgroundExtensionContract@@YA_NPEBG@Z; IsBackgroundExtensionContract(ushort const *)
0x1800b8432  test    al, al
0x1800b8434  jnz     loc_1800B85A7
0x1800b843a  mov     [rsp+48h+bIgnoreCase], esi; bIgnoreCase
0x1800b843e  lea     r9d, [r13+11h]; cchCount2
0x1800b8442  lea     r8, aWindowsProtoco; "Windows.Protocol"
0x1800b8449  mov     edx, r13d; cchCount1
0x1800b844c  mov     rcx, rdi; lpString1
0x1800b844f  call    cs:__imp_CompareStringOrdinal
0x1800b8456  nop     dword ptr [rax+rax+00h]
0x1800b845b  cmp     eax, 2
0x1800b845e  jnz     short loc_1800B8478
0x1800b8460  mov     r9, rbx; struct ActivationProperties *
0x1800b8463  mov     r8, [rbp+var_10]; __int64
0x1800b8467  lea     rdx, [rbp+var_18]; struct StateRepository::Cache::Manager_NoThrow *
0x1800b846b  mov     rcx, r15; struct Windows::ApplicationModel::Activation::IActivatedEventArgs *
0x1800b846e  call    ?GetProtocolLaunchParameters@@YA_NPEAUIActivatedEventArgs@Activation@ApplicationModel@Windows@@AEAVManager_NoThrow@Cache@StateRepository@@_JAEAUActivationProperties@@@Z; GetProtocolLaunchParameters(Windows::ApplicationModel::Activation::IActivatedEventArgs *,StateRepository::Cache::Manager_NoThrow &,__int64,ActivationProperties &)
0x1800b8473  jmp     loc_1800B85B7
0x1800b8478  mov     [rsp+48h+bIgnoreCase], esi; bIgnoreCase
0x1800b847c  mov     r9d, 0Ch; cchCount2
0x1800b8482  lea     r8, aWindowsFile; "Windows.File"
0x1800b8489  mov     edx, r13d; cchCount1
0x1800b848c  mov     rcx, rdi; lpString1
0x1800b848f  call    cs:__imp_CompareStringOrdinal
0x1800b8496  nop     dword ptr [rax+rax+00h]
0x1800b849b  cmp     eax, 2
0x1800b849e  jnz     short loc_1800B84B8
0x1800b84a0  mov     r9, rbx; struct ActivationProperties *
0x1800b84a3  mov     r8, [rbp+var_10]; __int64
0x1800b84a7  lea     rdx, [rbp+var_18]; struct StateRepository::Cache::Manager_NoThrow *
0x1800b84ab  mov     rcx, r15; struct Windows::ApplicationModel::Activation::IActivatedEventArgs *
0x1800b84ae  call    ?GetFileLaunchParameters@@YA_NPEAUIActivatedEventArgs@Activation@ApplicationModel@Windows@@AEAVManager_NoThrow@Cache@StateRepository@@_JAEAUActivationProperties@@@Z; GetFileLaunchParameters(Windows::ApplicationModel::Activation::IActivatedEventArgs *,StateRepository::Cache::Manager_NoThrow &,__int64,ActivationProperties &)
0x1800b84b3  jmp     loc_1800B85B7
0x1800b84b8  mov     [rsp+48h+bIgnoreCase], esi; bIgnoreCase
0x1800b84bc  mov     r9d, 13h; cchCount2
0x1800b84c2  lea     r8, aWindowsShareta; "Windows.ShareTarget"
0x1800b84c9  mov     edx, r13d; cchCount1
0x1800b84cc  mov     rcx, rdi; lpString1
0x1800b84cf  call    cs:__imp_CompareStringOrdinal
0x1800b84d6  nop     dword ptr [rax+rax+00h]
0x1800b84db  cmp     eax, 2
0x1800b84de  jz      short loc_1800B8548
0x1800b84e0  mov     [rsp+48h+bIgnoreCase], esi; bIgnoreCase
0x1800b84e4  mov     r9d, 13h; cchCount2
0x1800b84ea  lea     r8, aWindowsStartup; "Windows.StartupTask"
0x1800b84f1  mov     edx, r13d; cchCount1
0x1800b84f4  mov     rcx, rdi; lpString1
0x1800b84f7  call    cs:__imp_CompareStringOrdinal
0x1800b84fe  nop     dword ptr [rax+rax+00h]
0x1800b8503  cmp     eax, 2
0x1800b8506  jnz     short loc_1800B8520
0x1800b8508  mov     r9, rbx; struct ActivationProperties *
0x1800b850b  mov     r8, [rbp+var_10]; __int64
0x1800b850f  lea     rdx, [rbp+var_18]; struct StateRepository::Cache::Manager_NoThrow *
0x1800b8513  mov     rcx, r15; struct Windows::ApplicationModel::Activation::IActivatedEventArgs *
0x1800b8516  call    ?GetStartupTaskLaunchParameters@@YA_NPEAUIActivatedEventArgs@Activation@ApplicationModel@Windows@@AEAVManager_NoThrow@Cache@StateRepository@@_JAEAUActivationProperties@@@Z; GetStartupTaskLaunchParameters(Windows::ApplicationModel::Activation::IActivatedEventArgs *,StateRepository::Cache::Manager_NoThrow &,__int64,ActivationProperties &)
0x1800b851b  jmp     loc_1800B85B7
0x1800b8520  mov     [rsp+48h+bIgnoreCase], esi; bIgnoreCase
0x1800b8524  mov     r9d, 1Bh; cchCount2
0x1800b852a  lea     r8, aWindowsPhoneca; "Windows.PhoneCallActivation"
0x1800b8531  mov     edx, r13d; cchCount1
0x1800b8534  mov     rcx, rdi; lpString1
0x1800b8537  call    cs:__imp_CompareStringOrdinal
0x1800b853e  nop     dword ptr [rax+rax+00h]
0x1800b8543  cmp     eax, 2
0x1800b8546  jnz     short loc_1800B855A
0x1800b8548  mov     r8, rbx; struct ActivationProperties *
0x1800b854b  mov     rdx, [rbp+var_10]; __int64
0x1800b854f  lea     rcx, [rbp+var_18]; struct StateRepository::Cache::Manager_NoThrow *
0x1800b8553  call    ?GetExtensionLaunchParameters@@YA_NAEAVManager_NoThrow@Cache@StateRepository@@_JAEAUActivationProperties@@@Z; GetExtensionLaunchParameters(StateRepository::Cache::Manager_NoThrow &,__int64,ActivationProperties &)
0x1800b8558  jmp     short loc_1800B85B7
0x1800b855a  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_50902630@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_50902630@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_50902630> `wil::Feature<__WilFeatureTraits_Feature_50902630>::GetImpl(void)'::`2'::impl
0x1800b8561  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_50902630@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_50902630>::__private_IsEnabled(void)
0x1800b8566  test    al, al
0x1800b8568  jz      short loc_1800B85D1
0x1800b856a  mov     [rsp+48h+bIgnoreCase], esi; bIgnoreCase
0x1800b856e  mov     r9d, 11h; cchCount2
0x1800b8574  lea     r8, aWindowsGaminga_0; "Windows.GamingApp"
0x1800b857b  mov     edx, r13d; cchCount1
0x1800b857e  mov     rcx, rdi; lpString1
0x1800b8581  call    cs:__imp_CompareStringOrdinal
0x1800b8588  nop     dword ptr [rax+rax+00h]
0x1800b858d  cmp     eax, 2
0x1800b8590  jnz     short loc_1800B85D1
0x1800b8592  mov     r9, rbx; struct ActivationProperties *
0x1800b8595  mov     r8, [rbp+var_10]; __int64
0x1800b8599  lea     rdx, [rbp+var_18]; struct StateRepository::Cache::Manager_NoThrow *
0x1800b859d  mov     rcx, r15; struct Windows::ApplicationModel::Activation::IActivatedEventArgs *
0x1800b85a0  call    ?GetGamingAppLaunchParameters@@YA_NPEAUIActivatedEventArgs@Activation@ApplicationModel@Windows@@AEAVManager_NoThrow@Cache@StateRepository@@_JAEAUActivationProperties@@@Z; GetGamingAppLaunchParameters(Windows::ApplicationModel::Activation::IActivatedEventArgs *,StateRepository::Cache::Manager_NoThrow &,__int64,ActivationProperties &)
0x1800b85a5  jmp     short loc_1800B85B7
0x1800b85a7  mov     r8, rbx; struct ActivationProperties *
0x1800b85aa  mov     rdx, [rbp+var_10]; __int64
0x1800b85ae  lea     rcx, [rbp+var_18]; struct StateRepository::Cache::Manager_NoThrow *
0x1800b85b2  call    ?GetApplicationLaunchParameters@@YA_NAEAVManager_NoThrow@Cache@StateRepository@@_JAEAUActivationProperties@@@Z; GetApplicationLaunchParameters(StateRepository::Cache::Manager_NoThrow &,__int64,ActivationProperties &)
0x1800b85b7  test    al, al
0x1800b85b9  jnz     short loc_1800B85C9
0x1800b85bb  jmp     short loc_1800B85D1
0x1800b85bd  mov     r8, rbx; struct ActivationProperties *
0x1800b85c0  lea     rcx, [rbp+var_18]; struct StateRepository::Cache::Manager_NoThrow *
0x1800b85c4  call    ?GetApplicationLaunchParameters@@YA_NAEAVManager_NoThrow@Cache@StateRepository@@_JAEAUActivationProperties@@@Z; GetApplicationLaunchParameters(StateRepository::Cache::Manager_NoThrow &,__int64,ActivationProperties &)
0x1800b85c9  cmp     [rbx+120h], esi
0x1800b85cf  jnz     short loc_1800B85D4
0x1800b85d1  mov     [r14], rsi
0x1800b85d4  mov     rcx, [rbp+var_18]
0x1800b85d8  test    rcx, rcx
0x1800b85db  mov     [rbp+var_18], r12
0x1800b85df  jz      short loc_1800B85ED
0x1800b85e1  call    cs:__imp_SRCacheManager_Close
0x1800b85e8  nop     dword ptr [rax+rax+00h]
0x1800b85ed  add     rsp, 48h
0x1800b85f1  pop     r15
0x1800b85f3  pop     r14
0x1800b85f5  pop     r13
0x1800b85f7  pop     r12
0x1800b85f9  pop     rdi
0x1800b85fa  pop     rsi
0x1800b85fb  pop     rbx
0x1800b85fc  pop     rbp
0x1800b85fd  retn
0x1800b85ff  mov     ecx, 80070057h
0x1800b8604  call    ?verify_hresult@wil@@YAJUhresult@winrt@@@Z; wil::verify_hresult(winrt::hresult)
0x1800b8609  mov     r9d, eax; char *
0x1800b860c  mov     rcx, [rbp+40h]; this
0x1800b8610  lea     rax, aContractidRequ; "ContractID required"
0x1800b8617  mov     qword ptr [rsp+48h+bIgnoreCase], rax; int
0x1800b861c  lea     r8, aOnecoreBaseApp_46; "onecore\\base\\appmodel\\execmodel\\des"...
0x1800b8623  mov     edx, 1BBh; void *
0x1800b8628  call    ?Throw_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_HrMsg(void *,uint,char const *,long,char const *,...)
0x1800b862e  mov     r9d, eax; char *
0x1800b8631  lea     r8, aOnecoreBaseApp_46; "onecore\\base\\appmodel\\execmodel\\des"...
0x1800b8638  mov     edx, 1A2h; void *
0x1800b863d  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800b8643  mov     r9d, eax; char *
0x1800b8646  lea     r8, aOnecoreBaseApp_46; "onecore\\base\\appmodel\\execmodel\\des"...
0x1800b864d  mov     edx, 1A7h; void *
0x1800b8652  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800b8658  mov     r9d, edi; char *
0x1800b865b  lea     r8, aOnecoreBaseApp_46; "onecore\\base\\appmodel\\execmodel\\des"...
0x1800b8662  mov     edx, 1B2h; void *
0x1800b8667  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800b866d  mov     r9d, 80070490h; char *
0x1800b8673  lea     r8, aOnecoreBaseApp_46; "onecore\\base\\appmodel\\execmodel\\des"...
0x1800b867a  mov     edx, 1B3h; void *
0x1800b867f  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
