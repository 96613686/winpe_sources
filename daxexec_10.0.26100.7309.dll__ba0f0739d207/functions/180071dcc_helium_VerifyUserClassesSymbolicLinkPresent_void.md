# helium::VerifyUserClassesSymbolicLinkPresent(void *)

- ea: `0x180071dcc`
- end: `0x180072052`
- name: `?VerifyUserClassesSymbolicLinkPresent@helium@@YAXPEAX@Z`
- size: `646`
- prototype: `void __fastcall(helium *__hidden this, void *)`
- caller_count: `1`
- callee_count: `12`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting`

## callers

- `0x18006fabc`

## callees

- `0x1800053a0`
- `0x18000c37c`
- `0x180010a84`
- `0x180011820`
- `0x1800118c0`
- `0x180013100`
- `0x180013200`
- `0x180071c98`
- `0x180071dcc`
- `0x180096668`
- `0x1800966b8`
- `0x1800967b0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180071ede`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180071ef4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180071ede`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180071ef4`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180071e76`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180071e76`
- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x180071e22`
- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x180071e22`
- `ntdll!NtQueryKey` at `0x180071eb9`
- `ntdll!NtQueryKey` at `0x180071eb9`

## string_xrefs

- `0x180071f72`: `onecore\base\appmodel\execmodel\desktopappx\lib\registryutils.cpp`
- `0x180071f87`: `onecore\base\appmodel\execmodel\desktopappx\lib\registryutils.cpp`
- `0x180071fe8`: `onecore\base\appmodel\execmodel\desktopappx\lib\registryutils.cpp`
- `0x180072040`: `onecore\base\appmodel\execmodel\desktopappx\lib\registryutils.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall helium::VerifyUserClassesSymbolicLinkPresent(helium *this, void *a2)
{
  unsigned int v3; // eax
  int v4; // ebx
  NTSTATUS v5; // ebx
  __int64 v6; // rax
  unsigned int v7; // eax
  __int64 UserSidFromToken; // rax
  unsigned int v9; // eax
  __int64 v10; // rax
  unsigned int v11; // eax
  unsigned int v12; // [rsp+20h] [rbp-29h]
  int v13; // [rsp+20h] [rbp-29h]
  int v14; // [rsp+20h] [rbp-29h]
  int v15; // [rsp+30h] [rbp-19h] BYREF
  __int64 v16; // [rsp+38h] [rbp-11h] BYREF
  ULONG ResultLength; // [rsp+40h] [rbp-9h] BYREF
  HANDLE KeyHandle; // [rsp+48h] [rbp-1h] BYREF
  HKEY hKey; // [rsp+50h] [rbp+7h] BYREF
  _BYTE v20[16]; // [rsp+58h] [rbp+Fh] BYREF
  void *p_hKey; // [rsp+68h] [rbp+1Fh] BYREF
  HKEY phkResult; // [rsp+70h] [rbp+27h] BYREF
  char v23; // [rsp+78h] [rbp+2Fh]
  __int64 KeyInformation; // [rsp+88h] [rbp+3Fh] BYREF
  int v25; // [rsp+90h] [rbp+47h]
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+5Fh]

  LoggedonUserImpersonation::Impersonate(v20, this);
  hKey = 0;
  p_hKey = &hKey;
  phkResult = 0;
  v23 = 1;
  v3 = RegOpenCurrentUser(0x20019u, &phkResult);
  if ( v3 )
    wil::details::in1diag3::Throw_Win32(
      retaddr,
      (void *)0x17,
      (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\registryutils.cpp",
      (const char *)v3,
      v12);
  wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(&p_hKey);
  KeyHandle = 0;
  p_hKey = &KeyHandle;
  phkResult = 0;
  v23 = 1;
  v4 = RegOpenKeyExW(hKey, L"Software\\Classes", 8u, 0x20019u, &phkResult);
  wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(&p_hKey);
  if ( v4 )
  {
    UserSidFromToken = GetUserSidFromToken(&p_hKey, this);
    v16 = std::wstring::c_str(UserSidFromToken);
    if ( v4 > 0 )
      v4 = (unsigned __int16)v4 | 0x80070000;
    v15 = v4;
    DesktopAppXProvider::UserClassesSymbolicLinkNotPresent<long,unsigned short const *>(&v15, &v16);
    std::wstring::~wstring(&p_hKey);
    v9 = wil::verify_hresult(2147943653LL);
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1E,
      (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\registryutils.cpp",
      (const char *)v9,
      v13);
  }
  KeyInformation = 0;
  v25 = 0;
  ResultLength = 0;
  v5 = NtQueryKey(KeyHandle, KeyFlagsInformation, &KeyInformation, 0xCu, &ResultLength);
  if ( v5 )
  {
    v10 = GetUserSidFromToken(&p_hKey, this);
    v16 = std::wstring::c_str(v10);
    v15 = v5 | 0x10000000;
    DesktopAppXProvider::UserClassesSymbolicLinkNotPresent<long,unsigned short const *>(&v15, &v16);
    std::wstring::~wstring(&p_hKey);
    v11 = wil::verify_hresult(2147943653LL);
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x28,
      (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\registryutils.cpp",
      (const char *)v11,
      v14);
  }
  if ( (KeyInformation & 0x200000000LL) == 0 )
  {
    v6 = GetUserSidFromToken(&p_hKey, this);
    v16 = std::wstring::c_str(v6);
    v15 = -2147023643;
    DesktopAppXProvider::UserClassesSymbolicLinkNotPresent<long,unsigned short const *>(&v15, &v16);
    std::wstring::~wstring(&p_hKey);
    v7 = wil::verify_hresult(2147943653LL);
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x2E,
      (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\registryutils.cpp",
      (const char *)v7,
      v14);
  }
  if ( KeyHandle )
    RegCloseKey((HKEY)KeyHandle);
  if ( hKey )
    RegCloseKey(hKey);
  ImpersonationReverter::~ImpersonationReverter((ImpersonationReverter *)v20);
}

```

## disassembly

```asm
0x180071dcc  mov     [rsp-8+arg_8], rbx
0x180071dd1  mov     [rsp-8+arg_10], rdi
0x180071dd6  push    rbp
0x180071dd7  lea     rbp, [rsp-57h]
0x180071ddc  sub     rsp, 0A0h
0x180071de3  mov     rax, cs:__security_cookie
0x180071dea  xor     rax, rsp
0x180071ded  mov     [rbp+57h+var_8], rax
0x180071df1  mov     rdi, rcx
0x180071df4  mov     rdx, rcx
0x180071df7  lea     rcx, [rbp+57h+var_48]
0x180071dfb  call    ?Impersonate@LoggedonUserImpersonation@@SA?AU1@PEAX@Z; LoggedonUserImpersonation::Impersonate(void *)
0x180071e00  nop
0x180071e01  and     [rbp+57h+hKey], 0
0x180071e06  lea     rax, [rbp+57h+hKey]
0x180071e0a  mov     [rbp+57h+var_38], rax
0x180071e0e  and     [rbp+57h+phkResult], 0
0x180071e13  mov     [rbp+57h+var_28], 1
0x180071e17  lea     rdx, [rbp+57h+phkResult]; phkResult
0x180071e1b  mov     ebx, 20019h
0x180071e20  mov     ecx, ebx; samDesired
0x180071e22  call    cs:__imp_RegOpenCurrentUser
0x180071e29  nop     dword ptr [rax+rax+00h]
0x180071e2e  mov     rcx, [rbp+5Fh]; this
0x180071e32  test    eax, eax
0x180071e34  jnz     loc_180071F84
0x180071e3a  lea     rcx, [rbp+57h+var_38]
0x180071e3e  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(void)
0x180071e43  and     [rbp+57h+KeyHandle], 0
0x180071e48  lea     rax, [rbp+57h+KeyHandle]
0x180071e4c  mov     [rbp+57h+var_38], rax
0x180071e50  and     [rbp+57h+phkResult], 0
0x180071e55  mov     [rbp+57h+var_28], 1
0x180071e59  lea     rax, [rbp+57h+phkResult]
0x180071e5d  mov     qword ptr [rsp+0A0h+var_80], rax; int
0x180071e62  mov     r9d, ebx; samDesired
0x180071e65  mov     r8d, 8; ulOptions
0x180071e6b  lea     rdx, aSoftwareClasse_1; "Software\\Classes"
0x180071e72  mov     rcx, [rbp+57h+hKey]; hKey
0x180071e76  call    cs:__imp_RegOpenKeyExW
0x180071e7d  nop     dword ptr [rax+rax+00h]
0x180071e82  mov     ebx, eax
0x180071e84  lea     rcx, [rbp+57h+var_38]
0x180071e88  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(void)
0x180071e8d  test    ebx, ebx
0x180071e8f  jnz     loc_180071F99
0x180071e95  xor     eax, eax
0x180071e97  mov     [rbp+57h+KeyInformation], rax
0x180071e9b  mov     [rbp+57h+var_10], eax
0x180071e9e  and     [rbp+57h+ResultLength], eax
0x180071ea1  lea     rax, [rbp+57h+ResultLength]
0x180071ea5  mov     qword ptr [rsp+0A0h+var_80], rax; int
0x180071eaa  lea     r9d, [rbx+0Ch]; Length
0x180071eae  lea     r8, [rbp+57h+KeyInformation]; KeyInformation
0x180071eb2  lea     edx, [rbx+5]; KeyInformationClass
0x180071eb5  mov     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x180071eb9  call    cs:__imp_NtQueryKey
0x180071ec0  nop     dword ptr [rax+rax+00h]
0x180071ec5  mov     ebx, eax
0x180071ec7  test    eax, eax
0x180071ec9  jnz     loc_180071FFA
0x180071ecf  test    byte ptr [rbp+57h+KeyInformation+4], 2
0x180071ed3  jz      short loc_180071F2C
0x180071ed5  mov     rcx, [rbp+57h+KeyHandle]; hKey
0x180071ed9  test    rcx, rcx
0x180071edc  jz      short loc_180071EEB
0x180071ede  call    cs:__imp_RegCloseKey
0x180071ee5  nop     dword ptr [rax+rax+00h]
0x180071eea  nop
0x180071eeb  mov     rcx, [rbp+57h+hKey]; hKey
0x180071eef  test    rcx, rcx
0x180071ef2  jz      short loc_180071F01
0x180071ef4  call    cs:__imp_RegCloseKey
0x180071efb  nop     dword ptr [rax+rax+00h]
0x180071f00  nop
0x180071f01  lea     rcx, [rbp+57h+var_48]; this
0x180071f05  call    ??1ImpersonationReverter@@QEAA@XZ; ImpersonationReverter::~ImpersonationReverter(void)
0x180071f0a  mov     rcx, [rbp+57h+var_8]
0x180071f0e  xor     rcx, rsp; StackCookie
0x180071f11  call    __security_check_cookie
0x180071f16  lea     r11, [rsp+0A0h+var_s0]
0x180071f1e  mov     rbx, [r11+18h]
0x180071f22  mov     rdi, [r11+20h]
0x180071f26  mov     rsp, r11
0x180071f29  pop     rbp
0x180071f2a  retn
0x180071f2c  mov     rdx, rdi
0x180071f2f  lea     rcx, [rbp+57h+var_38]
0x180071f33  call    ?GetUserSidFromToken@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@Z; GetUserSidFromToken(void *)
0x180071f38  mov     rcx, rax
0x180071f3b  call    ?c_str@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAPEBGXZ; std::wstring::c_str(void)
0x180071f40  mov     [rbp+57h+var_68], rax
0x180071f44  mov     [rbp+57h+var_70], 800704E5h
0x180071f4b  lea     rdx, [rbp+57h+var_68]
0x180071f4f  lea     rcx, [rbp+57h+var_70]
0x180071f53  call    ??$UserClassesSymbolicLinkNotPresent@JPEBG@DesktopAppXProvider@@SAX$$QEAJ$$QEAPEBG@Z; DesktopAppXProvider::UserClassesSymbolicLinkNotPresent<long,ushort const *>(long &&,ushort const * &&)
0x180071f58  lea     rcx, [rbp+57h+var_38]; void *
0x180071f5c  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180071f61  mov     ecx, 800704E5h
0x180071f66  call    ?verify_hresult@wil@@YAJUhresult@winrt@@@Z; wil::verify_hresult(winrt::hresult)
0x180071f6b  mov     r9d, eax; char *
0x180071f6e  mov     rcx, [rbp+5Fh]; this
0x180071f72  lea     r8, aOnecoreBaseApp_13; "onecore\\base\\appmodel\\execmodel\\des"...
0x180071f79  mov     edx, 2Eh ; '.'; void *
0x180071f7e  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180071f84  mov     r9d, eax; char *
0x180071f87  lea     r8, aOnecoreBaseApp_13; "onecore\\base\\appmodel\\execmodel\\des"...
0x180071f8e  mov     edx, 17h; void *
0x180071f93  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x180071f99  mov     rdx, rdi
0x180071f9c  lea     rcx, [rbp+57h+var_38]
0x180071fa0  call    ?GetUserSidFromToken@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@Z; GetUserSidFromToken(void *)
0x180071fa5  mov     rcx, rax
0x180071fa8  call    ?c_str@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAPEBGXZ; std::wstring::c_str(void)
0x180071fad  mov     [rbp+57h+var_68], rax
0x180071fb1  test    ebx, ebx
0x180071fb3  jle     short loc_180071FBE
0x180071fb5  movzx   ebx, bx
0x180071fb8  or      ebx, 80070000h
0x180071fbe  mov     [rbp+57h+var_70], ebx
0x180071fc1  lea     rdx, [rbp+57h+var_68]
0x180071fc5  lea     rcx, [rbp+57h+var_70]
0x180071fc9  call    ??$UserClassesSymbolicLinkNotPresent@JPEBG@DesktopAppXProvider@@SAX$$QEAJ$$QEAPEBG@Z; DesktopAppXProvider::UserClassesSymbolicLinkNotPresent<long,ushort const *>(long &&,ushort const * &&)
0x180071fce  lea     rcx, [rbp+57h+var_38]; void *
0x180071fd2  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180071fd7  mov     ecx, 800704E5h
0x180071fdc  call    ?verify_hresult@wil@@YAJUhresult@winrt@@@Z; wil::verify_hresult(winrt::hresult)
0x180071fe1  mov     r9d, eax; char *
0x180071fe4  mov     rcx, [rbp+5Fh]; this
0x180071fe8  lea     r8, aOnecoreBaseApp_13; "onecore\\base\\appmodel\\execmodel\\des"...
0x180071fef  mov     edx, 1Eh; void *
0x180071ff4  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180071ffa  mov     rdx, rdi
0x180071ffd  lea     rcx, [rbp+57h+var_38]
0x180072001  call    ?GetUserSidFromToken@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@Z; GetUserSidFromToken(void *)
0x180072006  mov     rcx, rax
0x180072009  call    ?c_str@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAPEBGXZ; std::wstring::c_str(void)
0x18007200e  mov     [rbp+57h+var_68], rax
0x180072012  bts     ebx, 1Ch
0x180072016  mov     [rbp+57h+var_70], ebx
0x180072019  lea     rdx, [rbp+57h+var_68]
0x18007201d  lea     rcx, [rbp+57h+var_70]
0x180072021  call    ??$UserClassesSymbolicLinkNotPresent@JPEBG@DesktopAppXProvider@@SAX$$QEAJ$$QEAPEBG@Z; DesktopAppXProvider::UserClassesSymbolicLinkNotPresent<long,ushort const *>(long &&,ushort const * &&)
0x180072026  lea     rcx, [rbp+57h+var_38]; void *
0x18007202a  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18007202f  mov     ecx, 800704E5h
0x180072034  call    ?verify_hresult@wil@@YAJUhresult@winrt@@@Z; wil::verify_hresult(winrt::hresult)
0x180072039  mov     r9d, eax; char *
0x18007203c  mov     rcx, [rbp+5Fh]; this
0x180072040  lea     r8, aOnecoreBaseApp_13; "onecore\\base\\appmodel\\execmodel\\des"...
0x180072047  mov     edx, 28h ; '('; void *
0x18007204c  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
