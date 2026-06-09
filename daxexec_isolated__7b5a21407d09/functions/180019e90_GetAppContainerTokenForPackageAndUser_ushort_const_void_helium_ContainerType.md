# GetAppContainerTokenForPackageAndUser(ushort const *,void *,helium::ContainerType)

- ea: `0x180019e90`
- end: `0x18001a360`
- name: `?GetAppContainerTokenForPackageAndUser@@YA?AV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@PEBGPEAXW4ContainerType@helium@@@Z`
- size: `1232`
- prototype: `void **__fastcall(void **, const WCHAR *, void *, int)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800234e0`

## callees

- `0x180004f70`
- `0x180010d94`
- `0x1800125f4`
- `0x180014e74`
- `0x180017aa4`
- `0x180019e90`
- `0x18001c65c`
- `0x1800210fc`
- `0x180021118`
- `0x1800cd010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180019fb1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001a064`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001a188`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001a244`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180019fb1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001a064`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001a188`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001a244`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019f92`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a044`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a169`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a225`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019f92`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a044`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a169`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a225`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180019fa3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001a17a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001a1c2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001a236`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180019fa3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001a17a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001a1c2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001a236`
- `ntdll!RtlFreeSid` at `0x18001a055`
- `ntdll!RtlFreeSid` at `0x18001a262`
- `ntdll!NtDuplicateToken` at `0x180019f58`
- `ntdll!NtDuplicateToken` at `0x180019f58`
- `ntdll!NtQueryInformationToken` at `0x180019efb`
- `ntdll!NtQueryInformationToken` at `0x180019efb`
- `api-ms-win-security-base-private-l1-1-1!CreateAppContainerToken` at `0x18001a133`
- `api-ms-win-security-base-private-l1-1-1!CreateAppContainerToken` at `0x18001a1ef`
- `api-ms-win-security-base-private-l1-1-1!CreateAppContainerToken` at `0x18001a133`
- `api-ms-win-security-base-private-l1-1-1!CreateAppContainerToken` at `0x18001a1ef`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18001a0fa`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18001a0fa`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18001a197`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18001a197`
- `api-ms-win-appmodel-runtime-l1-1-0!PackageFamilyNameFromFullName` at `0x180019fd9`
- `api-ms-win-appmodel-runtime-l1-1-0!PackageFamilyNameFromFullName` at `0x180019fd9`
- `api-ms-win-appmodel-identity-l1-2-0!AppContainerDeriveSidFromMoniker` at `0x18001a013`
- `api-ms-win-appmodel-identity-l1-2-0!AppContainerDeriveSidFromMoniker` at `0x18001a013`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserContext` at `0x18001a0b0`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserContext` at `0x18001a0b0`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserToken` at `0x18001a0da`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserToken` at `0x18001a0da`

## string_xrefs

- `0x18001a29a`: `onecore\base\appmodel\execmodel\desktopappx\lib\processcreationextensions.cpp`
- `0x18001a2af`: `onecore\base\appmodel\execmodel\desktopappx\lib\processcreationextensions.cpp`
- `0x18001a2c4`: `onecore\base\appmodel\execmodel\desktopappx\lib\processcreationextensions.cpp`
- `0x18001a2d9`: `onecore\base\appmodel\execmodel\desktopappx\lib\processcreationextensions.cpp`
- `0x18001a2ee`: `onecore\base\appmodel\execmodel\desktopappx\lib\processcreationextensions.cpp`
- `0x18001a303`: `onecore\base\appmodel\execmodel\desktopappx\lib\processcreationextensions.cpp`
- `0x18001a318`: `onecore\base\appmodel\execmodel\desktopappx\lib\processcreationextensions.cpp`
- `0x18001a32a`: `onecore\base\appmodel\execmodel\desktopappx\lib\processcreationextensions.cpp`
- `0x18001a33c`: `onecore\base\appmodel\execmodel\desktopappx\lib\processcreationextensions.cpp`
- `0x18001a34e`: `onecore\base\appmodel\execmodel\desktopappx\lib\processcreationextensions.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=22
void **__fastcall GetAppContainerTokenForPackageAndUser(void **a1, const WCHAR *a2, void *a3, int a4)
{
  HANDLE v5; // rdi
  NTSTATUS v8; // eax
  NTSTATUS v9; // eax
  void *v10; // r15
  void *v11; // r14
  DWORD LastError; // ebx
  unsigned int v13; // eax
  int v14; // eax
  void *v15; // r12
  void *v16; // r15
  DWORD v17; // ebx
  int v18; // eax
  __int64 v19; // rax
  int UserToken; // eax
  const char *v21; // r9
  const char *v22; // r9
  void *v23; // r15
  void *v24; // r14
  DWORD v25; // ebx
  const char *v26; // r9
  const char *v27; // r9
  void *v28; // r15
  void *v29; // r14
  DWORD v30; // ebx
  unsigned int ReturnLength; // [rsp+20h] [rbp-E0h]
  int ReturnLengtha; // [rsp+20h] [rbp-E0h]
  void *NewTokenHandle; // [rsp+38h] [rbp-C8h] BYREF
  char v35; // [rsp+40h] [rbp-C0h]
  int TokenInformation; // [rsp+48h] [rbp-B8h] BYREF
  int v37; // [rsp+4Ch] [rbp-B4h]
  char v38; // [rsp+51h] [rbp-AFh]
  ULONG v39; // [rsp+54h] [rbp-ACh] BYREF
  UINT32 packageFamilyNameLength; // [rsp+58h] [rbp-A8h] BYREF
  HANDLE hObject; // [rsp+60h] [rbp-A0h] BYREF
  void *v42; // [rsp+68h] [rbp-98h]
  __int64 v43; // [rsp+70h] [rbp-90h] BYREF
  void *v44; // [rsp+78h] [rbp-88h] BYREF
  __int128 v45; // [rsp+80h] [rbp-80h]
  void **v46; // [rsp+90h] [rbp-70h]
  WCHAR packageFamilyName[72]; // [rsp+A0h] [rbp-60h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+178h] [rbp+78h]

  v5 = a3;
  v46 = a1;
  v37 = 1;
  TokenInformation = 0;
  v39 = 0;
  v8 = NtQueryInformationToken(a3, TokenIsAppContainer, &TokenInformation, 4u, &v39);
  if ( v8 < 0 )
    wil::details::in1diag3::Throw_NtStatus(
      retaddr,
      (void *)0xE7,
      (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\processcreationextensions.cpp",
      (const char *)(unsigned int)v8,
      ReturnLength);
  *a1 = 0;
  v37 = 1;
  if ( TokenInformation )
  {
    NewTokenHandle = 0;
    v35 = 1;
    v9 = NtDuplicateToken(v5, 0xF01FFu, 0, 0, TokenPrimary, &NewTokenHandle);
    if ( v9 < 0 )
      wil::details::in1diag3::Throw_NtStatus(
        retaddr,
        (void *)0xED,
        (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\processcreationextensions.cpp",
        (const char *)(unsigned int)v9,
        ReturnLengtha);
    if ( v35 )
    {
      v10 = NewTokenHandle;
      v11 = *a1;
      if ( (char *)*a1 - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      {
        LastError = GetLastError();
        CloseHandle(v11);
        SetLastError(LastError);
      }
      *a1 = v10;
    }
  }
  else
  {
    packageFamilyNameLength = 65;
    v13 = PackageFamilyNameFromFullName(a2, &packageFamilyNameLength, packageFamilyName);
    if ( v13 )
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0xF6,
        (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\processcreationextensions.cpp",
        (const char *)v13,
        ReturnLength);
    v42 = 0;
    NewTokenHandle = 0;
    v35 = 1;
    v14 = AppContainerDeriveSidFromMoniker(packageFamilyName, &NewTokenHandle);
    if ( v14 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xFA,
        (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\processcreationextensions.cpp",
        (const char *)(unsigned int)v14,
        ReturnLength);
    if ( v35 )
    {
      v15 = NewTokenHandle;
      v16 = v42;
      if ( v42 )
      {
        v17 = GetLastError();
        ((void (__fastcall *)(void *))RtlFreeSid)(v16);
        SetLastError(v17);
      }
      v42 = v15;
    }
    v45 = 0;
    v44 = v42;
    if ( a4 == 2 )
    {
      NewTokenHandle = 0;
      v35 = 1;
      if ( !(unsigned int)CreateAppContainerToken(v5, &v44, &NewTokenHandle) )
        wil::details::in1diag3::Throw_GetLastError(
          retaddr,
          (void *)0x119,
          (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\processcreationextensions.cpp",
          v27);
      if ( v35 )
      {
        v28 = NewTokenHandle;
        v29 = *a1;
        if ( (char *)*a1 - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
        {
          v30 = GetLastError();
          CloseHandle(v29);
          SetLastError(v30);
        }
        *a1 = v28;
      }
    }
    else
    {
      hObject = 0;
      if ( IsTokenIntegrityLevelLessThanMedium(v5) )
      {
        v43 = 0;
        v18 = UMgrQueryUserContext(v5, &v43);
        if ( v18 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x10B,
            (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\processcreationextensions.cpp",
            (const char *)(unsigned int)v18,
            ReturnLength);
        v19 = wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>::operator&(&hObject);
        UserToken = UMgrQueryUserToken(v43, v19);
        if ( UserToken < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x10C,
            (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\processcreationextensions.cpp",
            (const char *)(unsigned int)UserToken,
            ReturnLength);
        v5 = hObject;
      }
      if ( !ImpersonateLoggedOnUser(v5) )
        wil::details::in1diag3::Throw_GetLastError(
          retaddr,
          (void *)0x10F,
          (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\processcreationextensions.cpp",
          v21);
      v38 = 1;
      NewTokenHandle = 0;
      v35 = 1;
      if ( !(unsigned int)CreateAppContainerToken(v5, &v44, &NewTokenHandle) )
        wil::details::in1diag3::Throw_GetLastError(
          retaddr,
          (void *)0x115,
          (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\processcreationextensions.cpp",
          v22);
      if ( v35 )
      {
        v23 = NewTokenHandle;
        v24 = *a1;
        if ( (char *)*a1 - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
        {
          v25 = GetLastError();
          CloseHandle(v24);
          SetLastError(v25);
        }
        *a1 = v23;
      }
      if ( !RevertToSelf() )
        wil::details::in1diag3::_FailFast_GetLastError(
          retaddr,
          (void *)0x112,
          (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\processcreationextensions.cpp",
          v26);
      if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
        CloseHandle(hObject);
    }
    v37 = 0;
    if ( v42 )
      ((void (*)(void))RtlFreeSid)();
  }
  return a1;
}

```

## disassembly

```asm
0x180019e90  mov     [rsp-8+arg_18], rbx
0x180019e95  push    rbp
0x180019e96  push    rsi
0x180019e97  push    rdi
0x180019e98  push    r12
0x180019e9a  push    r13
0x180019e9c  push    r14
0x180019e9e  push    r15
0x180019ea0  lea     rbp, [rsp-40h]
0x180019ea5  sub     rsp, 140h
0x180019eac  mov     rax, cs:__security_cookie
0x180019eb3  xor     rax, rsp
0x180019eb6  mov     [rbp+70h+var_40], rax
0x180019eba  mov     r13d, r9d
0x180019ebd  mov     rdi, r8
0x180019ec0  mov     rbx, rdx
0x180019ec3  mov     rsi, rcx
0x180019ec6  mov     [rbp+70h+var_E0], rcx
0x180019eca  mov     [rsp+170h+var_124], 1
0x180019ed2  xor     r12d, r12d
0x180019ed5  mov     [rsp+170h+TokenInformation], r12d
0x180019eda  mov     [rsp+170h+var_11C], r12d
0x180019edf  lea     rax, [rsp+170h+var_11C]
0x180019ee4  mov     [rsp+170h+ReturnLength], rax; int
0x180019ee9  lea     r9d, [r12+4]; TokenInformationLength
0x180019eee  lea     r8, [rsp+170h+TokenInformation]; TokenInformation
0x180019ef3  lea     edx, [r12+1Dh]; TokenInformationClass
0x180019ef8  mov     rcx, rdi; TokenHandle
0x180019efb  call    cs:__imp_NtQueryInformationToken
0x180019f02  nop     dword ptr [rax+rax+00h]
0x180019f07  mov     rcx, [rbp+78h]; this
0x180019f0b  test    eax, eax
0x180019f0d  js      loc_18001A2AC
0x180019f13  mov     [rsi], r12
0x180019f16  mov     [rsp+170h+var_124], 1
0x180019f1e  cmp     [rsp+170h+TokenInformation], r12d
0x180019f23  jz      loc_180019FC5
0x180019f29  mov     [rsp+170h+var_140], rsi
0x180019f2e  mov     [rsp+170h+var_138], r12
0x180019f33  mov     [rsp+170h+var_130], 1
0x180019f38  lea     rax, [rsp+170h+var_138]
0x180019f3d  mov     [rsp+170h+NewTokenHandle], rax; NewTokenHandle
0x180019f42  mov     dword ptr [rsp+170h+ReturnLength], 1; int
0x180019f4a  xor     r9d, r9d; EffectiveOnly
0x180019f4d  xor     r8d, r8d; ObjectAttributes
0x180019f50  mov     edx, 0F01FFh; DesiredAccess
0x180019f55  mov     rcx, rdi; ExistingTokenHandle
0x180019f58  call    cs:__imp_NtDuplicateToken
0x180019f5f  nop     dword ptr [rax+rax+00h]
0x180019f64  mov     rcx, [rbp+78h]; this
0x180019f68  test    eax, eax
0x180019f6a  js      loc_18001A2C1
0x180019f70  cmp     [rsp+170h+var_130], r12b
0x180019f75  jz      loc_18001A26F
0x180019f7b  mov     r15, [rsp+170h+var_138]
0x180019f80  mov     rdi, [rsp+170h+var_140]
0x180019f85  mov     r14, [rdi]
0x180019f88  lea     rax, [r14-1]
0x180019f8c  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180019f90  ja      short loc_180019FBD
0x180019f92  call    cs:__imp_GetLastError
0x180019f99  nop     dword ptr [rax+rax+00h]
0x180019f9e  mov     ebx, eax
0x180019fa0  mov     rcx, r14; hObject
0x180019fa3  call    cs:__imp_CloseHandle
0x180019faa  nop     dword ptr [rax+rax+00h]
0x180019faf  mov     ecx, ebx; dwErrCode
0x180019fb1  call    cs:__imp_SetLastError
0x180019fb8  nop     dword ptr [rax+rax+00h]
0x180019fbd  mov     [rdi], r15
0x180019fc0  jmp     loc_18001A26F
0x180019fc5  mov     [rsp+170h+packageFamilyNameLength], 41h ; 'A'
0x180019fcd  lea     r8, [rbp+70h+packageFamilyName]; packageFamilyName
0x180019fd1  lea     rdx, [rsp+170h+packageFamilyNameLength]; packageFamilyNameLength
0x180019fd6  mov     rcx, rbx; packageFullName
0x180019fd9  call    cs:__imp_PackageFamilyNameFromFullName
0x180019fe0  nop     dword ptr [rax+rax+00h]
0x180019fe5  mov     rcx, [rbp+78h]; this
0x180019fe9  test    eax, eax
0x180019feb  jnz     loc_18001A2D6
0x180019ff1  mov     [rsp+170h+var_108], r12
0x180019ff6  lea     rax, [rsp+170h+var_108]
0x180019ffb  mov     [rsp+170h+var_140], rax
0x18001a000  mov     [rsp+170h+var_138], r12
0x18001a005  mov     [rsp+170h+var_130], 1
0x18001a00a  lea     rdx, [rsp+170h+var_138]
0x18001a00f  lea     rcx, [rbp+70h+packageFamilyName]
0x18001a013  call    cs:__imp_AppContainerDeriveSidFromMoniker
0x18001a01a  nop     dword ptr [rax+rax+00h]
0x18001a01f  mov     rcx, [rbp+78h]; this
0x18001a023  test    eax, eax
0x18001a025  js      loc_18001A2EB
0x18001a02b  cmp     [rsp+170h+var_130], r12b
0x18001a030  jz      short loc_18001A076
0x18001a032  mov     r12, [rsp+170h+var_138]
0x18001a037  mov     r14, [rsp+170h+var_140]
0x18001a03c  mov     r15, [r14]
0x18001a03f  test    r15, r15
0x18001a042  jz      short loc_18001A070
0x18001a044  call    cs:__imp_GetLastError
0x18001a04b  nop     dword ptr [rax+rax+00h]
0x18001a050  mov     ebx, eax
0x18001a052  mov     rcx, r15
0x18001a055  mov     rax, cs:__imp_RtlFreeSid
0x18001a05c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a061  nop
0x18001a062  mov     ecx, ebx; dwErrCode
0x18001a064  call    cs:__imp_SetLastError
0x18001a06b  nop     dword ptr [rax+rax+00h]
0x18001a070  mov     [r14], r12
0x18001a073  xor     r12d, r12d
0x18001a076  xorps   xmm0, xmm0
0x18001a079  movdqu  [rbp+70h+var_F0], xmm0
0x18001a07e  mov     rax, [rsp+170h+var_108]
0x18001a083  mov     [rsp+170h+var_F8], rax
0x18001a088  cmp     r13d, 2
0x18001a08c  jz      loc_18001A1D3
0x18001a092  mov     [rsp+170h+hObject], r12
0x18001a097  mov     rcx, rdi; void *
0x18001a09a  call    ?IsTokenIntegrityLevelLessThanMedium@@YA_NPEAX@Z; IsTokenIntegrityLevelLessThanMedium(void *)
0x18001a09f  test    al, al
0x18001a0a1  jz      short loc_18001A0F7
0x18001a0a3  mov     [rsp+170h+var_100], r12
0x18001a0a8  lea     rdx, [rsp+170h+var_100]
0x18001a0ad  mov     rcx, rdi
0x18001a0b0  call    cs:__imp_UMgrQueryUserContext
0x18001a0b7  nop     dword ptr [rax+rax+00h]
0x18001a0bc  mov     rcx, [rbp+78h]; this
0x18001a0c0  test    eax, eax
0x18001a0c2  js      loc_18001A300
0x18001a0c8  lea     rcx, [rsp+170h+hObject]
0x18001a0cd  call    ??I?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@QEAAPEAPEAXXZ; wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>::operator&(void)
0x18001a0d2  mov     rdx, rax
0x18001a0d5  mov     rcx, [rsp+170h+var_100]
0x18001a0da  call    cs:__imp_UMgrQueryUserToken
0x18001a0e1  nop     dword ptr [rax+rax+00h]
0x18001a0e6  mov     rcx, [rbp+78h]; this
0x18001a0ea  test    eax, eax
0x18001a0ec  js      loc_18001A315
0x18001a0f2  mov     rdi, [rsp+170h+hObject]
0x18001a0f7  mov     rcx, rdi; hToken
0x18001a0fa  call    cs:__imp_ImpersonateLoggedOnUser
0x18001a101  nop     dword ptr [rax+rax+00h]
0x18001a106  mov     rcx, [rbp+78h]; this
0x18001a10a  test    eax, eax
0x18001a10c  jz      loc_18001A32A
0x18001a112  mov     [rsp+170h+var_11F], 1
0x18001a117  mov     [rsp+170h+var_140], rsi
0x18001a11c  mov     [rsp+170h+var_138], r12
0x18001a121  mov     [rsp+170h+var_130], 1
0x18001a126  lea     r8, [rsp+170h+var_138]
0x18001a12b  lea     rdx, [rsp+170h+var_F8]
0x18001a130  mov     rcx, rdi
0x18001a133  call    cs:__imp_CreateAppContainerToken
0x18001a13a  nop     dword ptr [rax+rax+00h]
0x18001a13f  mov     rcx, [rbp+78h]; this
0x18001a143  test    eax, eax
0x18001a145  jz      loc_18001A33C
0x18001a14b  cmp     [rsp+170h+var_130], r12b
0x18001a150  jz      short loc_18001A197
0x18001a152  mov     r15, [rsp+170h+var_138]
0x18001a157  mov     rdi, [rsp+170h+var_140]
0x18001a15c  mov     r14, [rdi]
0x18001a15f  lea     rax, [r14-1]
0x18001a163  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18001a167  ja      short loc_18001A194
0x18001a169  call    cs:__imp_GetLastError
0x18001a170  nop     dword ptr [rax+rax+00h]
0x18001a175  mov     ebx, eax
0x18001a177  mov     rcx, r14; hObject
0x18001a17a  call    cs:__imp_CloseHandle
0x18001a181  nop     dword ptr [rax+rax+00h]
0x18001a186  mov     ecx, ebx; dwErrCode
0x18001a188  call    cs:__imp_SetLastError
0x18001a18f  nop     dword ptr [rax+rax+00h]
0x18001a194  mov     [rdi], r15
0x18001a197  call    cs:__imp_RevertToSelf
0x18001a19e  nop     dword ptr [rax+rax+00h]
0x18001a1a3  mov     rcx, [rbp+78h]; this
0x18001a1a7  test    eax, eax
0x18001a1a9  jz      loc_18001A34E
0x18001a1af  mov     rcx, [rsp+170h+hObject]; hObject
0x18001a1b4  lea     rax, [rcx-1]
0x18001a1b8  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18001a1bc  ja      loc_18001A253
0x18001a1c2  call    cs:__imp_CloseHandle
0x18001a1c9  nop     dword ptr [rax+rax+00h]
0x18001a1ce  jmp     loc_18001A253
0x18001a1d3  mov     [rsp+170h+var_140], rsi
0x18001a1d8  mov     [rsp+170h+var_138], r12
0x18001a1dd  mov     [rsp+170h+var_130], 1
0x18001a1e2  lea     r8, [rsp+170h+var_138]
0x18001a1e7  lea     rdx, [rsp+170h+var_F8]
0x18001a1ec  mov     rcx, rdi
0x18001a1ef  call    cs:__imp_CreateAppContainerToken
0x18001a1f6  nop     dword ptr [rax+rax+00h]
0x18001a1fb  mov     rcx, [rbp+78h]; this
0x18001a1ff  test    eax, eax
0x18001a201  jz      loc_18001A29A
0x18001a207  cmp     [rsp+170h+var_130], r12b
0x18001a20c  jz      short loc_18001A253
0x18001a20e  mov     r15, [rsp+170h+var_138]
0x18001a213  mov     rdi, [rsp+170h+var_140]
0x18001a218  mov     r14, [rdi]
0x18001a21b  lea     rax, [r14-1]
0x18001a21f  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18001a223  ja      short loc_18001A250
0x18001a225  call    cs:__imp_GetLastError
0x18001a22c  nop     dword ptr [rax+rax+00h]
0x18001a231  mov     ebx, eax
0x18001a233  mov     rcx, r14; hObject
0x18001a236  call    cs:__imp_CloseHandle
0x18001a23d  nop     dword ptr [rax+rax+00h]
0x18001a242  mov     ecx, ebx; dwErrCode
0x18001a244  call    cs:__imp_SetLastError
0x18001a24b  nop     dword ptr [rax+rax+00h]
0x18001a250  mov     [rdi], r15
0x18001a253  mov     [rsp+170h+var_124], r12d
0x18001a258  mov     rcx, [rsp+170h+var_108]
0x18001a25d  test    rcx, rcx
0x18001a260  jz      short loc_18001A26F
0x18001a262  mov     rax, cs:__imp_RtlFreeSid
0x18001a269  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a26e  nop
0x18001a26f  mov     rax, rsi
0x18001a272  mov     rcx, [rbp+70h+var_40]
0x18001a276  xor     rcx, rsp; StackCookie
0x18001a279  call    __security_check_cookie
0x18001a27e  mov     rbx, [rsp+170h+arg_18]
0x18001a286  add     rsp, 140h
0x18001a28d  pop     r15
0x18001a28f  pop     r14
0x18001a291  pop     r13
0x18001a293  pop     r12
0x18001a295  pop     rdi
0x18001a296  pop     rsi
0x18001a297  pop     rbp
0x18001a298  retn
0x18001a29a  lea     r8, aOnecoreBaseApp_23; "onecore\\base\\appmodel\\execmodel\\des"...
0x18001a2a1  mov     edx, 119h; void *
0x18001a2a6  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x18001a2ac  mov     r9d, eax; char *
0x18001a2af  lea     r8, aOnecoreBaseApp_23; "onecore\\base\\appmodel\\execmodel\\des"...
0x18001a2b6  mov     edx, 0E7h; void *
0x18001a2bb  call    ?Throw_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_NtStatus(void *,uint,char const *,long)
0x18001a2c1  mov     r9d, eax; char *
0x18001a2c4  lea     r8, aOnecoreBaseApp_23; "onecore\\base\\appmodel\\execmodel\\des"...
0x18001a2cb  mov     edx, 0EDh; void *
0x18001a2d0  call    ?Throw_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_NtStatus(void *,uint,char const *,long)
0x18001a2d6  mov     r9d, eax; char *
0x18001a2d9  lea     r8, aOnecoreBaseApp_23; "onecore\\base\\appmodel\\execmodel\\des"...
0x18001a2e0  mov     edx, 0F6h; void *
0x18001a2e5  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x18001a2eb  mov     r9d, eax; char *
0x18001a2ee  lea     r8, aOnecoreBaseApp_23; "onecore\\base\\appmodel\\execmodel\\des"...
0x18001a2f5  mov     edx, 0FAh; void *
0x18001a2fa  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18001a300  mov     r9d, eax; char *
0x18001a303  lea     r8, aOnecoreBaseApp_23; "onecore\\base\\appmodel\\execmodel\\des"...
0x18001a30a  mov     edx, 10Bh; void *
0x18001a30f  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18001a315  mov     r9d, eax; char *
0x18001a318  lea     r8, aOnecoreBaseApp_23; "onecore\\base\\appmodel\\execmodel\\des"...
0x18001a31f  mov     edx, 10Ch; void *
0x18001a324  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18001a32a  lea     r8, aOnecoreBaseApp_23; "onecore\\base\\appmodel\\execmodel\\des"...
0x18001a331  mov     edx, 10Fh; void *
0x18001a336  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x18001a33c  lea     r8, aOnecoreBaseApp_23; "onecore\\base\\appmodel\\execmodel\\des"...
0x18001a343  mov     edx, 115h; void *
0x18001a348  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x18001a34e  lea     r8, aOnecoreBaseApp_23; "onecore\\base\\appmodel\\execmodel\\des"...
0x18001a355  mov     edx, 112h; void *
0x18001a35a  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
