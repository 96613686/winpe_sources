# GetAppContainerTokenForPackageAndUser(ushort const *,void *,helium::ContainerType)

- ea: `0x1800182f4`
- end: `0x1800186a0`
- name: `?GetAppContainerTokenForPackageAndUser@@YA?AV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@PEBGPEAXW4ContainerType@helium@@@Z`
- size: `940`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180022b30`

## callees

- `0x1800053a0`
- `0x18000f1c8`
- `0x180010a84`
- `0x180013100`
- `0x180015314`
- `0x18001538c`
- `0x180015ec8`
- `0x1800182f4`
- `0x18001bbd8`
- `0x18002031c`
- `0x180020338`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001854f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001854f`
- `ntdll!RtlFreeSid` at `0x1800185a6`
- `ntdll!RtlFreeSid` at `0x1800185a6`
- `ntdll!NtDuplicateToken` at `0x1800183b2`
- `ntdll!NtDuplicateToken` at `0x1800183b2`
- `ntdll!NtQueryInformationToken` at `0x180018359`
- `ntdll!NtQueryInformationToken` at `0x180018359`
- `api-ms-win-security-base-private-l1-1-1!CreateAppContainerToken` at `0x180018505`
- `api-ms-win-security-base-private-l1-1-1!CreateAppContainerToken` at `0x180018579`
- `api-ms-win-security-base-private-l1-1-1!CreateAppContainerToken` at `0x180018505`
- `api-ms-win-security-base-private-l1-1-1!CreateAppContainerToken` at `0x180018579`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x1800184cc`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x1800184cc`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180018528`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180018528`
- `api-ms-win-appmodel-runtime-l1-1-0!PackageFamilyNameFromFullName` at `0x1800183ed`
- `api-ms-win-appmodel-runtime-l1-1-0!PackageFamilyNameFromFullName` at `0x1800183ed`
- `api-ms-win-appmodel-identity-l1-2-0!AppContainerDeriveSidFromMoniker` at `0x180018427`
- `api-ms-win-appmodel-identity-l1-2-0!AppContainerDeriveSidFromMoniker` at `0x180018427`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserContext` at `0x180018482`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserContext` at `0x180018482`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserToken` at `0x1800184ac`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserToken` at `0x1800184ac`

## string_xrefs

- `0x1800185da`: `onecore\base\appmodel\execmodel\desktopappx\lib\processcreationextensions.cpp`
- `0x1800185ef`: `onecore\base\appmodel\execmodel\desktopappx\lib\processcreationextensions.cpp`
- `0x180018604`: `onecore\base\appmodel\execmodel\desktopappx\lib\processcreationextensions.cpp`
- `0x180018619`: `onecore\base\appmodel\execmodel\desktopappx\lib\processcreationextensions.cpp`
- `0x18001862e`: `onecore\base\appmodel\execmodel\desktopappx\lib\processcreationextensions.cpp`
- `0x180018643`: `onecore\base\appmodel\execmodel\desktopappx\lib\processcreationextensions.cpp`
- `0x180018658`: `onecore\base\appmodel\execmodel\desktopappx\lib\processcreationextensions.cpp`
- `0x18001866a`: `onecore\base\appmodel\execmodel\desktopappx\lib\processcreationextensions.cpp`
- `0x18001867c`: `onecore\base\appmodel\execmodel\desktopappx\lib\processcreationextensions.cpp`
- `0x18001868e`: `onecore\base\appmodel\execmodel\desktopappx\lib\processcreationextensions.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
PSID *__fastcall GetAppContainerTokenForPackageAndUser(PSID *a1, const WCHAR *a2, void *a3, int a4)
{
  HANDLE v5; // rbx
  NTSTATUS v8; // eax
  NTSTATUS v9; // eax
  unsigned int v10; // eax
  int v11; // eax
  int v12; // eax
  __int64 v13; // rax
  int UserToken; // eax
  const char *v15; // r9
  const char *v16; // r9
  const char *v17; // r9
  const char *v18; // r9
  unsigned int ReturnLength; // [rsp+20h] [rbp-E0h]
  int ReturnLengtha; // [rsp+20h] [rbp-E0h]
  PSID *p_Sid; // [rsp+30h] [rbp-D0h] BYREF
  void *NewTokenHandle; // [rsp+38h] [rbp-C8h] BYREF
  char v24; // [rsp+40h] [rbp-C0h]
  int TokenInformation; // [rsp+48h] [rbp-B8h] BYREF
  int v26; // [rsp+4Ch] [rbp-B4h]
  char v27; // [rsp+51h] [rbp-AFh]
  ULONG v28; // [rsp+54h] [rbp-ACh] BYREF
  UINT32 packageFamilyNameLength; // [rsp+58h] [rbp-A8h] BYREF
  HANDLE hObject; // [rsp+60h] [rbp-A0h] BYREF
  PSID Sid; // [rsp+68h] [rbp-98h] BYREF
  __int64 v32; // [rsp+70h] [rbp-90h] BYREF
  PSID v33; // [rsp+78h] [rbp-88h] BYREF
  __int128 v34; // [rsp+80h] [rbp-80h]
  PSID *v35; // [rsp+90h] [rbp-70h]
  WCHAR packageFamilyName[72]; // [rsp+A0h] [rbp-60h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+168h] [rbp+68h]

  v5 = a3;
  v35 = a1;
  v26 = 1;
  TokenInformation = 0;
  v28 = 0;
  v8 = NtQueryInformationToken(a3, TokenIsAppContainer, &TokenInformation, 4u, &v28);
  if ( v8 < 0 )
    wil::details::in1diag3::Throw_NtStatus(
      retaddr,
      (void *)0xEB,
      (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\processcreationextensions.cpp",
      (const char *)(unsigned int)v8,
      ReturnLength);
  *a1 = 0;
  v26 = 1;
  if ( TokenInformation )
  {
    p_Sid = a1;
    NewTokenHandle = 0;
    v24 = 1;
    v9 = NtDuplicateToken(v5, 0xF01FFu, 0, 0, TokenPrimary, &NewTokenHandle);
    if ( v9 < 0 )
      wil::details::in1diag3::Throw_NtStatus(
        retaddr,
        (void *)0xF1,
        (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\processcreationextensions.cpp",
        (const char *)(unsigned int)v9,
        ReturnLengtha);
    wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>(&p_Sid);
  }
  else
  {
    packageFamilyNameLength = 65;
    v10 = PackageFamilyNameFromFullName(a2, &packageFamilyNameLength, packageFamilyName);
    if ( v10 )
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0xFA,
        (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\processcreationextensions.cpp",
        (const char *)v10,
        ReturnLength);
    Sid = 0;
    p_Sid = &Sid;
    NewTokenHandle = 0;
    v24 = 1;
    v11 = AppContainerDeriveSidFromMoniker(packageFamilyName, &NewTokenHandle);
    if ( v11 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xFE,
        (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\processcreationextensions.cpp",
        (const char *)(unsigned int)v11,
        ReturnLength);
    wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (void *),&void * RtlFreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (void *),&void * RtlFreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>(&p_Sid);
    v34 = 0;
    v33 = Sid;
    if ( a4 == 2 )
    {
      p_Sid = a1;
      NewTokenHandle = 0;
      v24 = 1;
      if ( !(unsigned int)CreateAppContainerToken(v5, &v33, &NewTokenHandle) )
        wil::details::in1diag3::Throw_GetLastError(
          retaddr,
          (void *)0x11D,
          (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\processcreationextensions.cpp",
          v18);
      wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>(&p_Sid);
    }
    else
    {
      hObject = 0;
      if ( IsTokenIntegrityLevelLessThanMedium(v5) )
      {
        v32 = 0;
        v12 = UMgrQueryUserContext(v5, &v32);
        if ( v12 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x10F,
            (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\processcreationextensions.cpp",
            (const char *)(unsigned int)v12,
            ReturnLength);
        v13 = wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>::operator&(&hObject);
        UserToken = UMgrQueryUserToken(v32, v13);
        if ( UserToken < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x110,
            (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\processcreationextensions.cpp",
            (const char *)(unsigned int)UserToken,
            ReturnLength);
        v5 = hObject;
      }
      if ( !ImpersonateLoggedOnUser(v5) )
        wil::details::in1diag3::Throw_GetLastError(
          retaddr,
          (void *)0x113,
          (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\processcreationextensions.cpp",
          v15);
      v27 = 1;
      p_Sid = a1;
      NewTokenHandle = 0;
      v24 = 1;
      if ( !(unsigned int)CreateAppContainerToken(v5, &v33, &NewTokenHandle) )
        wil::details::in1diag3::Throw_GetLastError(
          retaddr,
          (void *)0x119,
          (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\processcreationextensions.cpp",
          v16);
      wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>(&p_Sid);
      if ( !RevertToSelf() )
        wil::details::in1diag3::_FailFast_GetLastError(
          retaddr,
          (void *)0x116,
          (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\processcreationextensions.cpp",
          v17);
      if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
        CloseHandle(hObject);
    }
    v26 = 0;
    if ( Sid )
      RtlFreeSid(Sid);
  }
  return a1;
}

```

## disassembly

```asm
0x1800182f4  mov     [rsp-8+arg_18], rbx
0x1800182f9  push    rbp
0x1800182fa  push    rsi
0x1800182fb  push    rdi
0x1800182fc  push    r14
0x1800182fe  push    r15
0x180018300  lea     rbp, [rsp-40h]
0x180018305  sub     rsp, 140h
0x18001830c  mov     rax, cs:__security_cookie
0x180018313  xor     rax, rsp
0x180018316  mov     [rbp+60h+var_30], rax
0x18001831a  mov     esi, r9d
0x18001831d  mov     rbx, r8
0x180018320  mov     r14, rdx
0x180018323  mov     rdi, rcx
0x180018326  mov     [rbp+60h+var_D0], rcx
0x18001832a  mov     [rsp+160h+var_114], 1
0x180018332  xor     r15d, r15d
0x180018335  mov     [rsp+160h+TokenInformation], r15d
0x18001833a  mov     [rsp+160h+var_10C], r15d
0x18001833f  lea     rax, [rsp+160h+var_10C]
0x180018344  mov     [rsp+160h+ReturnLength], rax; int
0x180018349  lea     r9d, [r15+4]; TokenInformationLength
0x18001834d  lea     r8, [rsp+160h+TokenInformation]; TokenInformation
0x180018352  lea     edx, [r15+1Dh]; TokenInformationClass
0x180018356  mov     rcx, rbx; TokenHandle
0x180018359  call    cs:__imp_NtQueryInformationToken
0x180018360  nop     dword ptr [rax+rax+00h]
0x180018365  mov     rcx, [rbp+68h]; this
0x180018369  test    eax, eax
0x18001836b  js      loc_1800185EC
0x180018371  mov     [rdi], r15
0x180018374  mov     [rsp+160h+var_114], 1
0x18001837c  cmp     [rsp+160h+TokenInformation], r15d
0x180018381  jz      short loc_1800183D9
0x180018383  mov     [rsp+160h+var_130], rdi
0x180018388  mov     [rsp+160h+var_128], r15
0x18001838d  mov     [rsp+160h+var_120], 1
0x180018392  lea     rax, [rsp+160h+var_128]
0x180018397  mov     [rsp+160h+NewTokenHandle], rax; NewTokenHandle
0x18001839c  mov     dword ptr [rsp+160h+ReturnLength], 1; int
0x1800183a4  xor     r9d, r9d; EffectiveOnly
0x1800183a7  xor     r8d, r8d; ObjectAttributes
0x1800183aa  mov     edx, 0F01FFh; DesiredAccess
0x1800183af  mov     rcx, rbx; ExistingTokenHandle
0x1800183b2  call    cs:__imp_NtDuplicateToken
0x1800183b9  nop     dword ptr [rax+rax+00h]
0x1800183be  mov     rcx, [rbp+68h]; this
0x1800183c2  test    eax, eax
0x1800183c4  js      loc_180018601
0x1800183ca  lea     rcx, [rsp+160h+var_130]
0x1800183cf  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>(void)
0x1800183d4  jmp     loc_1800185B3
0x1800183d9  mov     [rsp+160h+packageFamilyNameLength], 41h ; 'A'
0x1800183e1  lea     r8, [rbp+60h+packageFamilyName]; packageFamilyName
0x1800183e5  lea     rdx, [rsp+160h+packageFamilyNameLength]; packageFamilyNameLength
0x1800183ea  mov     rcx, r14; packageFullName
0x1800183ed  call    cs:__imp_PackageFamilyNameFromFullName
0x1800183f4  nop     dword ptr [rax+rax+00h]
0x1800183f9  mov     rcx, [rbp+68h]; this
0x1800183fd  test    eax, eax
0x1800183ff  jnz     loc_180018616
0x180018405  mov     [rsp+160h+Sid], r15
0x18001840a  lea     rax, [rsp+160h+Sid]
0x18001840f  mov     [rsp+160h+var_130], rax
0x180018414  mov     [rsp+160h+var_128], r15
0x180018419  mov     [rsp+160h+var_120], 1
0x18001841e  lea     rdx, [rsp+160h+var_128]
0x180018423  lea     rcx, [rbp+60h+packageFamilyName]
0x180018427  call    cs:__imp_AppContainerDeriveSidFromMoniker
0x18001842e  nop     dword ptr [rax+rax+00h]
0x180018433  mov     rcx, [rbp+68h]; this
0x180018437  test    eax, eax
0x180018439  js      loc_18001862B
0x18001843f  lea     rcx, [rsp+160h+var_130]
0x180018444  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAX$$A6APEAXPEAX@Z$1?RtlFreeSid@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (void *),&RtlFreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (void *),&RtlFreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>(void)
0x180018449  xorps   xmm0, xmm0
0x18001844c  movdqu  [rbp+60h+var_E0], xmm0
0x180018451  mov     rax, [rsp+160h+Sid]
0x180018456  mov     [rsp+160h+var_E8], rax
0x18001845b  cmp     esi, 2
0x18001845e  jz      loc_18001855D
0x180018464  mov     [rsp+160h+hObject], r15
0x180018469  mov     rcx, rbx; void *
0x18001846c  call    ?IsTokenIntegrityLevelLessThanMedium@@YA_NPEAX@Z; IsTokenIntegrityLevelLessThanMedium(void *)
0x180018471  test    al, al
0x180018473  jz      short loc_1800184C9
0x180018475  mov     [rsp+160h+var_F0], r15
0x18001847a  lea     rdx, [rsp+160h+var_F0]
0x18001847f  mov     rcx, rbx
0x180018482  call    cs:__imp_UMgrQueryUserContext
0x180018489  nop     dword ptr [rax+rax+00h]
0x18001848e  mov     rcx, [rbp+68h]; this
0x180018492  test    eax, eax
0x180018494  js      loc_180018640
0x18001849a  lea     rcx, [rsp+160h+hObject]
0x18001849f  call    ??I?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@QEAAPEAPEAXXZ; wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>::operator&(void)
0x1800184a4  mov     rdx, rax
0x1800184a7  mov     rcx, [rsp+160h+var_F0]
0x1800184ac  call    cs:__imp_UMgrQueryUserToken
0x1800184b3  nop     dword ptr [rax+rax+00h]
0x1800184b8  mov     rcx, [rbp+68h]; this
0x1800184bc  test    eax, eax
0x1800184be  js      loc_180018655
0x1800184c4  mov     rbx, [rsp+160h+hObject]
0x1800184c9  mov     rcx, rbx; hToken
0x1800184cc  call    cs:__imp_ImpersonateLoggedOnUser
0x1800184d3  nop     dword ptr [rax+rax+00h]
0x1800184d8  mov     rcx, [rbp+68h]; this
0x1800184dc  test    eax, eax
0x1800184de  jz      loc_18001866A
0x1800184e4  mov     [rsp+160h+var_10F], 1
0x1800184e9  mov     [rsp+160h+var_130], rdi
0x1800184ee  mov     [rsp+160h+var_128], r15
0x1800184f3  mov     [rsp+160h+var_120], 1
0x1800184f8  lea     r8, [rsp+160h+var_128]
0x1800184fd  lea     rdx, [rsp+160h+var_E8]
0x180018502  mov     rcx, rbx
0x180018505  call    cs:__imp_CreateAppContainerToken
0x18001850c  nop     dword ptr [rax+rax+00h]
0x180018511  mov     rcx, [rbp+68h]; this
0x180018515  test    eax, eax
0x180018517  jz      loc_18001867C
0x18001851d  lea     rcx, [rsp+160h+var_130]
0x180018522  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>(void)
0x180018527  nop
0x180018528  call    cs:__imp_RevertToSelf
0x18001852f  nop     dword ptr [rax+rax+00h]
0x180018534  mov     rcx, [rbp+68h]; this
0x180018538  test    eax, eax
0x18001853a  jz      loc_18001868E
0x180018540  mov     rcx, [rsp+160h+hObject]; hObject
0x180018545  lea     rax, [rcx-1]
0x180018549  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18001854d  ja      short loc_180018597
0x18001854f  call    cs:__imp_CloseHandle
0x180018556  nop     dword ptr [rax+rax+00h]
0x18001855b  jmp     short loc_180018597
0x18001855d  mov     [rsp+160h+var_130], rdi
0x180018562  mov     [rsp+160h+var_128], r15
0x180018567  mov     [rsp+160h+var_120], 1
0x18001856c  lea     r8, [rsp+160h+var_128]
0x180018571  lea     rdx, [rsp+160h+var_E8]
0x180018576  mov     rcx, rbx
0x180018579  call    cs:__imp_CreateAppContainerToken
0x180018580  nop     dword ptr [rax+rax+00h]
0x180018585  mov     rcx, [rbp+68h]; this
0x180018589  test    eax, eax
0x18001858b  jz      short loc_1800185DA
0x18001858d  lea     rcx, [rsp+160h+var_130]
0x180018592  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>(void)
0x180018597  mov     [rsp+160h+var_114], r15d
0x18001859c  mov     rcx, [rsp+160h+Sid]; Sid
0x1800185a1  test    rcx, rcx
0x1800185a4  jz      short loc_1800185B3
0x1800185a6  call    cs:__imp_RtlFreeSid
0x1800185ad  nop     dword ptr [rax+rax+00h]
0x1800185b2  nop
0x1800185b3  mov     rax, rdi
0x1800185b6  mov     rcx, [rbp+60h+var_30]
0x1800185ba  xor     rcx, rsp; StackCookie
0x1800185bd  call    __security_check_cookie
0x1800185c2  mov     rbx, [rsp+160h+arg_18]
0x1800185ca  add     rsp, 140h
0x1800185d1  pop     r15
0x1800185d3  pop     r14
0x1800185d5  pop     rdi
0x1800185d6  pop     rsi
0x1800185d7  pop     rbp
0x1800185d8  retn
0x1800185da  lea     r8, aOnecoreBaseApp_22; "onecore\\base\\appmodel\\execmodel\\des"...
0x1800185e1  mov     edx, 11Dh; void *
0x1800185e6  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1800185ec  mov     r9d, eax; char *
0x1800185ef  lea     r8, aOnecoreBaseApp_22; "onecore\\base\\appmodel\\execmodel\\des"...
0x1800185f6  mov     edx, 0EBh; void *
0x1800185fb  call    ?Throw_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_NtStatus(void *,uint,char const *,long)
0x180018601  mov     r9d, eax; char *
0x180018604  lea     r8, aOnecoreBaseApp_22; "onecore\\base\\appmodel\\execmodel\\des"...
0x18001860b  mov     edx, 0F1h; void *
0x180018610  call    ?Throw_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_NtStatus(void *,uint,char const *,long)
0x180018616  mov     r9d, eax; char *
0x180018619  lea     r8, aOnecoreBaseApp_22; "onecore\\base\\appmodel\\execmodel\\des"...
0x180018620  mov     edx, 0FAh; void *
0x180018625  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x18001862b  mov     r9d, eax; char *
0x18001862e  lea     r8, aOnecoreBaseApp_22; "onecore\\base\\appmodel\\execmodel\\des"...
0x180018635  mov     edx, 0FEh; void *
0x18001863a  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180018640  mov     r9d, eax; char *
0x180018643  lea     r8, aOnecoreBaseApp_22; "onecore\\base\\appmodel\\execmodel\\des"...
0x18001864a  mov     edx, 10Fh; void *
0x18001864f  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180018655  mov     r9d, eax; char *
0x180018658  lea     r8, aOnecoreBaseApp_22; "onecore\\base\\appmodel\\execmodel\\des"...
0x18001865f  mov     edx, 110h; void *
0x180018664  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18001866a  lea     r8, aOnecoreBaseApp_22; "onecore\\base\\appmodel\\execmodel\\des"...
0x180018671  mov     edx, 113h; void *
0x180018676  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x18001867c  lea     r8, aOnecoreBaseApp_22; "onecore\\base\\appmodel\\execmodel\\des"...
0x180018683  mov     edx, 119h; void *
0x180018688  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x18001868e  lea     r8, aOnecoreBaseApp_22; "onecore\\base\\appmodel\\execmodel\\des"...
0x180018695  mov     edx, 116h; void *
0x18001869a  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
