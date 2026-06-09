# helium::VerifyUserClassesSymbolicLinkPresent(void *)

- ea: `0x180073658`
- end: `0x18007396f`
- name: `?VerifyUserClassesSymbolicLinkPresent@helium@@YAXPEAX@Z`
- size: `791`
- prototype: `void __fastcall(helium *__hidden this, void *)`
- caller_count: `1`
- callee_count: `11`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting`

## callers

- `0x18007161c`

## callees

- `0x180004f70`
- `0x18000e074`
- `0x1800125f4`
- `0x180013510`
- `0x180014e74`
- `0x180014efc`
- `0x18007351c`
- `0x180073658`
- `0x180097fb8`
- `0x180098008`
- `0x18009815c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180073709`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180073794`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180073709`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180073794`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800736ea`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180073775`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800736ea`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180073775`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180073751`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180073751`
- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x1800736bd`
- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x1800736bd`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800736fb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180073786`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800737f4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18007380a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800736fb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180073786`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800737f4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18007380a`
- `ntdll!NtQueryKey` at `0x1800737cf`
- `ntdll!NtQueryKey` at `0x1800737cf`

## string_xrefs

- `0x18007388f`: `onecore\base\appmodel\execmodel\desktopappx\lib\registryutils.cpp`
- `0x1800738a4`: `onecore\base\appmodel\execmodel\desktopappx\lib\registryutils.cpp`
- `0x180073905`: `onecore\base\appmodel\execmodel\desktopappx\lib\registryutils.cpp`
- `0x18007395d`: `onecore\base\appmodel\execmodel\desktopappx\lib\registryutils.cpp`

## pseudocode

```c
void __fastcall helium::VerifyUserClassesSymbolicLinkPresent(helium *this, void *a2)
{
  unsigned int v3; // eax
  HKEY v4; // r14
  HKEY *v5; // rdi
  HKEY v6; // rsi
  DWORD LastError; // ebx
  int v8; // edi
  HKEY v9; // r15
  HKEY *v10; // rsi
  HKEY v11; // r14
  DWORD v12; // ebx
  NTSTATUS v13; // ebx
  __int64 v14; // rax
  unsigned int v15; // eax
  __int64 UserSidFromToken; // rax
  unsigned int v17; // eax
  __int64 v18; // rax
  unsigned int v19; // eax
  unsigned int v20; // [rsp+20h] [rbp-49h]
  int v21; // [rsp+20h] [rbp-49h]
  int v22; // [rsp+20h] [rbp-49h]
  int v23; // [rsp+30h] [rbp-39h] BYREF
  __int64 v24; // [rsp+38h] [rbp-31h] BYREF
  ULONG ResultLength; // [rsp+40h] [rbp-29h] BYREF
  HANDLE KeyHandle; // [rsp+48h] [rbp-21h] BYREF
  HKEY hKey; // [rsp+50h] [rbp-19h] BYREF
  _BYTE v28[16]; // [rsp+58h] [rbp-11h] BYREF
  HKEY *p_hKey; // [rsp+68h] [rbp-1h] BYREF
  HKEY phkResult; // [rsp+70h] [rbp+7h] BYREF
  char v31; // [rsp+78h] [rbp+Fh]
  __int64 KeyInformation; // [rsp+88h] [rbp+1Fh] BYREF
  int v33; // [rsp+90h] [rbp+27h]
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+5Fh]

  LoggedonUserImpersonation::Impersonate(v28, this);
  hKey = 0;
  p_hKey = &hKey;
  phkResult = 0;
  v31 = 1;
  v3 = RegOpenCurrentUser(0x20019u, &phkResult);
  if ( v3 )
    wil::details::in1diag3::Throw_Win32(
      retaddr,
      (void *)0x17,
      (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\registryutils.cpp",
      (const char *)v3,
      v20);
  if ( v31 )
  {
    v4 = phkResult;
    v5 = p_hKey;
    v6 = *p_hKey;
    if ( *p_hKey )
    {
      LastError = GetLastError();
      RegCloseKey(v6);
      SetLastError(LastError);
    }
    *v5 = v4;
  }
  KeyHandle = 0;
  p_hKey = (HKEY *)&KeyHandle;
  phkResult = 0;
  v31 = 1;
  v8 = RegOpenKeyExW(hKey, L"Software\\Classes", 8u, 0x20019u, &phkResult);
  if ( v31 )
  {
    v9 = phkResult;
    v10 = p_hKey;
    v11 = *p_hKey;
    if ( *p_hKey )
    {
      v12 = GetLastError();
      RegCloseKey(v11);
      SetLastError(v12);
    }
    *v10 = v9;
  }
  if ( v8 )
  {
    UserSidFromToken = GetUserSidFromToken(&p_hKey, this);
    v24 = std::wstring::c_str(UserSidFromToken);
    if ( v8 > 0 )
      v8 = (unsigned __int16)v8 | 0x80070000;
    v23 = v8;
    DesktopAppXProvider::UserClassesSymbolicLinkNotPresent<long,unsigned short const *>(&v23, &v24);
    std::wstring::~wstring(&p_hKey);
    v17 = wil::verify_hresult(2147943653LL);
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1E,
      (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\registryutils.cpp",
      (const char *)v17,
      v21);
  }
  KeyInformation = 0;
  v33 = 0;
  ResultLength = 0;
  v13 = NtQueryKey(KeyHandle, KeyFlagsInformation, &KeyInformation, 0xCu, &ResultLength);
  if ( v13 )
  {
    v18 = GetUserSidFromToken(&p_hKey, this);
    v24 = std::wstring::c_str(v18);
    v23 = v13 | 0x10000000;
    DesktopAppXProvider::UserClassesSymbolicLinkNotPresent<long,unsigned short const *>(&v23, &v24);
    std::wstring::~wstring(&p_hKey);
    v19 = wil::verify_hresult(2147943653LL);
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x28,
      (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\registryutils.cpp",
      (const char *)v19,
      v22);
  }
  if ( (KeyInformation & 0x200000000LL) == 0 )
  {
    v14 = GetUserSidFromToken(&p_hKey, this);
    v24 = std::wstring::c_str(v14);
    v23 = -2147023643;
    DesktopAppXProvider::UserClassesSymbolicLinkNotPresent<long,unsigned short const *>(&v23, &v24);
    std::wstring::~wstring(&p_hKey);
    v15 = wil::verify_hresult(2147943653LL);
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x2E,
      (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\registryutils.cpp",
      (const char *)v15,
      v22);
  }
  if ( KeyHandle )
    RegCloseKey((HKEY)KeyHandle);
  if ( hKey )
    RegCloseKey(hKey);
  ImpersonationReverter::~ImpersonationReverter((ImpersonationReverter *)v28);
}

```

## disassembly

```asm
0x180073658  mov     [rsp-8+arg_8], rbx
0x18007365d  mov     [rsp-8+arg_10], rsi
0x180073662  push    rbp
0x180073663  push    rdi
0x180073664  push    r12
0x180073666  push    r14
0x180073668  push    r15
0x18007366a  lea     rbp, [rsp-37h]
0x18007366f  sub     rsp, 0A0h
0x180073676  mov     rax, cs:__security_cookie
0x18007367d  xor     rax, rsp
0x180073680  mov     [rbp+57h+var_28], rax
0x180073684  mov     r12, rcx
0x180073687  mov     rdx, rcx
0x18007368a  lea     rcx, [rbp+57h+var_68]
0x18007368e  call    ?Impersonate@LoggedonUserImpersonation@@SA?AU1@PEAX@Z; LoggedonUserImpersonation::Impersonate(void *)
0x180073693  nop
0x180073694  mov     [rbp+57h+hKey], 0
0x18007369c  lea     rax, [rbp+57h+hKey]
0x1800736a0  mov     [rbp+57h+var_58], rax
0x1800736a4  mov     [rbp+57h+phkResult], 0
0x1800736ac  mov     [rbp+57h+var_48], 1
0x1800736b0  lea     rdx, [rbp+57h+phkResult]; phkResult
0x1800736b4  mov     r15d, 20019h
0x1800736ba  mov     ecx, r15d; samDesired
0x1800736bd  call    cs:__imp_RegOpenCurrentUser
0x1800736c4  nop     dword ptr [rax+rax+00h]
0x1800736c9  mov     rcx, [rbp+5Fh]; this
0x1800736cd  test    eax, eax
0x1800736cf  jnz     loc_1800738A1
0x1800736d5  cmp     [rbp+57h+var_48], al
0x1800736d8  jz      short loc_180073718
0x1800736da  mov     r14, [rbp+57h+phkResult]
0x1800736de  mov     rdi, [rbp+57h+var_58]
0x1800736e2  mov     rsi, [rdi]
0x1800736e5  test    rsi, rsi
0x1800736e8  jz      short loc_180073715
0x1800736ea  call    cs:__imp_GetLastError
0x1800736f1  nop     dword ptr [rax+rax+00h]
0x1800736f6  mov     ebx, eax
0x1800736f8  mov     rcx, rsi; hKey
0x1800736fb  call    cs:__imp_RegCloseKey
0x180073702  nop     dword ptr [rax+rax+00h]
0x180073707  mov     ecx, ebx; dwErrCode
0x180073709  call    cs:__imp_SetLastError
0x180073710  nop     dword ptr [rax+rax+00h]
0x180073715  mov     [rdi], r14
0x180073718  mov     [rbp+57h+KeyHandle], 0
0x180073720  lea     rax, [rbp+57h+KeyHandle]
0x180073724  mov     [rbp+57h+var_58], rax
0x180073728  mov     [rbp+57h+phkResult], 0
0x180073730  mov     [rbp+57h+var_48], 1
0x180073734  lea     rax, [rbp+57h+phkResult]
0x180073738  mov     qword ptr [rsp+0C0h+var_A0], rax; int
0x18007373d  mov     r9d, r15d; samDesired
0x180073740  mov     r8d, 8; ulOptions
0x180073746  lea     rdx, aSoftwareClasse_1; "Software\\Classes"
0x18007374d  mov     rcx, [rbp+57h+hKey]; hKey
0x180073751  call    cs:__imp_RegOpenKeyExW
0x180073758  nop     dword ptr [rax+rax+00h]
0x18007375d  mov     edi, eax
0x18007375f  cmp     [rbp+57h+var_48], 0
0x180073763  jz      short loc_1800737A3
0x180073765  mov     r15, [rbp+57h+phkResult]
0x180073769  mov     rsi, [rbp+57h+var_58]
0x18007376d  mov     r14, [rsi]
0x180073770  test    r14, r14
0x180073773  jz      short loc_1800737A0
0x180073775  call    cs:__imp_GetLastError
0x18007377c  nop     dword ptr [rax+rax+00h]
0x180073781  mov     ebx, eax
0x180073783  mov     rcx, r14; hKey
0x180073786  call    cs:__imp_RegCloseKey
0x18007378d  nop     dword ptr [rax+rax+00h]
0x180073792  mov     ecx, ebx; dwErrCode
0x180073794  call    cs:__imp_SetLastError
0x18007379b  nop     dword ptr [rax+rax+00h]
0x1800737a0  mov     [rsi], r15
0x1800737a3  test    edi, edi
0x1800737a5  jnz     loc_1800738B6
0x1800737ab  xor     eax, eax
0x1800737ad  mov     [rbp+57h+KeyInformation], rax
0x1800737b1  mov     [rbp+57h+var_30], eax
0x1800737b4  mov     [rbp+57h+ResultLength], eax
0x1800737b7  lea     rax, [rbp+57h+ResultLength]
0x1800737bb  mov     qword ptr [rsp+0C0h+var_A0], rax; int
0x1800737c0  lea     r9d, [rdi+0Ch]; Length
0x1800737c4  lea     r8, [rbp+57h+KeyInformation]; KeyInformation
0x1800737c8  lea     edx, [rdi+5]; KeyInformationClass
0x1800737cb  mov     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x1800737cf  call    cs:__imp_NtQueryKey
0x1800737d6  nop     dword ptr [rax+rax+00h]
0x1800737db  mov     ebx, eax
0x1800737dd  test    eax, eax
0x1800737df  jnz     loc_180073917
0x1800737e5  test    byte ptr [rbp+57h+KeyInformation+4], 2
0x1800737e9  jz      short loc_180073849
0x1800737eb  mov     rcx, [rbp+57h+KeyHandle]; hKey
0x1800737ef  test    rcx, rcx
0x1800737f2  jz      short loc_180073801
0x1800737f4  call    cs:__imp_RegCloseKey
0x1800737fb  nop     dword ptr [rax+rax+00h]
0x180073800  nop
0x180073801  mov     rcx, [rbp+57h+hKey]; hKey
0x180073805  test    rcx, rcx
0x180073808  jz      short loc_180073817
0x18007380a  call    cs:__imp_RegCloseKey
0x180073811  nop     dword ptr [rax+rax+00h]
0x180073816  nop
0x180073817  lea     rcx, [rbp+57h+var_68]; this
0x18007381b  call    ??1ImpersonationReverter@@QEAA@XZ; ImpersonationReverter::~ImpersonationReverter(void)
0x180073820  mov     rcx, [rbp+57h+var_28]
0x180073824  xor     rcx, rsp; StackCookie
0x180073827  call    __security_check_cookie
0x18007382c  lea     r11, [rsp+0C0h+var_20]
0x180073834  mov     rbx, [r11+38h]
0x180073838  mov     rsi, [r11+40h]
0x18007383c  mov     rsp, r11
0x18007383f  pop     r15
0x180073841  pop     r14
0x180073843  pop     r12
0x180073845  pop     rdi
0x180073846  pop     rbp
0x180073847  retn
0x180073849  mov     rdx, r12
0x18007384c  lea     rcx, [rbp+57h+var_58]
0x180073850  call    ?GetUserSidFromToken@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@Z; GetUserSidFromToken(void *)
0x180073855  mov     rcx, rax
0x180073858  call    ?c_str@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAPEBGXZ; std::wstring::c_str(void)
0x18007385d  mov     [rbp+57h+var_88], rax
0x180073861  mov     [rbp+57h+var_90], 800704E5h
0x180073868  lea     rdx, [rbp+57h+var_88]
0x18007386c  lea     rcx, [rbp+57h+var_90]
0x180073870  call    ??$UserClassesSymbolicLinkNotPresent@JPEBG@DesktopAppXProvider@@SAX$$QEAJ$$QEAPEBG@Z; DesktopAppXProvider::UserClassesSymbolicLinkNotPresent<long,ushort const *>(long &&,ushort const * &&)
0x180073875  lea     rcx, [rbp+57h+var_58]; void *
0x180073879  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18007387e  mov     ecx, 800704E5h
0x180073883  call    ?verify_hresult@wil@@YAJUhresult@winrt@@@Z; wil::verify_hresult(winrt::hresult)
0x180073888  mov     r9d, eax; char *
0x18007388b  mov     rcx, [rbp+5Fh]; this
0x18007388f  lea     r8, aOnecoreBaseApp_13; "onecore\\base\\appmodel\\execmodel\\des"...
0x180073896  mov     edx, 2Eh ; '.'; void *
0x18007389b  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800738a1  mov     r9d, eax; char *
0x1800738a4  lea     r8, aOnecoreBaseApp_13; "onecore\\base\\appmodel\\execmodel\\des"...
0x1800738ab  mov     edx, 17h; void *
0x1800738b0  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x1800738b6  mov     rdx, r12
0x1800738b9  lea     rcx, [rbp+57h+var_58]
0x1800738bd  call    ?GetUserSidFromToken@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@Z; GetUserSidFromToken(void *)
0x1800738c2  mov     rcx, rax
0x1800738c5  call    ?c_str@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAPEBGXZ; std::wstring::c_str(void)
0x1800738ca  mov     [rbp+57h+var_88], rax
0x1800738ce  test    edi, edi
0x1800738d0  jle     short loc_1800738DB
0x1800738d2  movzx   edi, di
0x1800738d5  or      edi, 80070000h
0x1800738db  mov     [rbp+57h+var_90], edi
0x1800738de  lea     rdx, [rbp+57h+var_88]
0x1800738e2  lea     rcx, [rbp+57h+var_90]
0x1800738e6  call    ??$UserClassesSymbolicLinkNotPresent@JPEBG@DesktopAppXProvider@@SAX$$QEAJ$$QEAPEBG@Z; DesktopAppXProvider::UserClassesSymbolicLinkNotPresent<long,ushort const *>(long &&,ushort const * &&)
0x1800738eb  lea     rcx, [rbp+57h+var_58]; void *
0x1800738ef  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800738f4  mov     ecx, 800704E5h
0x1800738f9  call    ?verify_hresult@wil@@YAJUhresult@winrt@@@Z; wil::verify_hresult(winrt::hresult)
0x1800738fe  mov     r9d, eax; char *
0x180073901  mov     rcx, [rbp+5Fh]; this
0x180073905  lea     r8, aOnecoreBaseApp_13; "onecore\\base\\appmodel\\execmodel\\des"...
0x18007390c  mov     edx, 1Eh; void *
0x180073911  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180073917  mov     rdx, r12
0x18007391a  lea     rcx, [rbp+57h+var_58]
0x18007391e  call    ?GetUserSidFromToken@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@Z; GetUserSidFromToken(void *)
0x180073923  mov     rcx, rax
0x180073926  call    ?c_str@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAPEBGXZ; std::wstring::c_str(void)
0x18007392b  mov     [rbp+57h+var_88], rax
0x18007392f  bts     ebx, 1Ch
0x180073933  mov     [rbp+57h+var_90], ebx
0x180073936  lea     rdx, [rbp+57h+var_88]
0x18007393a  lea     rcx, [rbp+57h+var_90]
0x18007393e  call    ??$UserClassesSymbolicLinkNotPresent@JPEBG@DesktopAppXProvider@@SAX$$QEAJ$$QEAPEBG@Z; DesktopAppXProvider::UserClassesSymbolicLinkNotPresent<long,ushort const *>(long &&,ushort const * &&)
0x180073943  lea     rcx, [rbp+57h+var_58]; void *
0x180073947  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18007394c  mov     ecx, 800704E5h
0x180073951  call    ?verify_hresult@wil@@YAJUhresult@winrt@@@Z; wil::verify_hresult(winrt::hresult)
0x180073956  mov     r9d, eax; char *
0x180073959  mov     rcx, [rbp+5Fh]; this
0x18007395d  lea     r8, aOnecoreBaseApp_13; "onecore\\base\\appmodel\\execmodel\\des"...
0x180073964  mov     edx, 28h ; '('; void *
0x180073969  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
