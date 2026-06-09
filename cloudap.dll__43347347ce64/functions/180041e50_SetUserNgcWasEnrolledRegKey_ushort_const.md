# SetUserNgcWasEnrolledRegKey(ushort const *)

- ea: `0x180041e50`
- end: `0x180042019`
- name: `?SetUserNgcWasEnrolledRegKey@@YAJPEBG@Z`
- size: `457`
- prototype: `__int64 __fastcall(const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180041de0`

## callees

- `0x18003bf28`
- `0x18003dd9c`
- `0x180040024`
- `0x180041e50`
- `0x180042410`
- `0x180045b04`
- `0x180045b80`
- `0x18004af14`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180041f5a`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180041f5a`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180041fb5`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180041fb5`

## string_xrefs

- `0x180041eb0`: `onecore\ds\security\base\lsa\pwdless\policy_lib\lib\pwdlesspolicy.cxx`
- `0x180041ef1`: `onecore\ds\security\base\lsa\pwdless\policy_lib\lib\pwdlesspolicy.cxx`
- `0x180041f6e`: `onecore\ds\security\base\lsa\pwdless\policy_lib\lib\pwdlesspolicy.cxx`
- `0x180041fc9`: `onecore\ds\security\base\lsa\pwdless\policy_lib\lib\pwdlesspolicy.cxx`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall SetUserNgcWasEnrolledRegKey(const unsigned __int16 *a1)
{
  int v1; // eax
  unsigned __int64 v2; // rdx
  const unsigned __int16 *v3; // r11
  unsigned int v4; // ebx
  int v6; // eax
  unsigned int v7; // eax
  unsigned int v8; // eax
  int dwOptions; // [rsp+20h] [rbp-E0h]
  unsigned int dwOptionsa; // [rsp+20h] [rbp-E0h]
  unsigned int dwOptionsb; // [rsp+20h] [rbp-E0h]
  HKEY hKey; // [rsp+50h] [rbp-B0h] BYREF
  BYTE Data[8]; // [rsp+58h] [rbp-A8h] BYREF
  WCHAR SubKey[264]; // [rsp+60h] [rbp-A0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+288h] [rbp+188h]

  *(_DWORD *)Data = 1;
  hKey = 0;
  v1 = StringCchCopyW(SubKey, 0x104u, L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\PasswordLess\\NgcStatus\\");
  v4 = v1;
  if ( v1 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x81,
      (unsigned int)"onecore\\ds\\security\\base\\lsa\\pwdless\\policy_lib\\lib\\pwdlesspolicy.cxx",
      (const char *)(unsigned int)v1,
      dwOptions);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
    return v4;
  }
  v6 = StringCchCatW(SubKey, v2, v3);
  v4 = v6;
  if ( v6 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x83,
      (unsigned int)"onecore\\ds\\security\\base\\lsa\\pwdless\\policy_lib\\lib\\pwdlesspolicy.cxx",
      (const char *)(unsigned int)v6,
      dwOptions);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
    return v4;
  }
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
    &hKey,
    0);
  v7 = RegCreateKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 0, 0, 0x20006u, 0, &hKey, 0);
  if ( v7 )
  {
    v4 = wil::details::in1diag3::Return_Win32(
           retaddr,
           (void *)0x85,
           (unsigned int)"onecore\\ds\\security\\base\\lsa\\pwdless\\policy_lib\\lib\\pwdlesspolicy.cxx",
           (const char *)v7,
           dwOptionsa);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
    return v4;
  }
  v8 = RegSetValueExW(hKey, L"NgcSetup", 0, 4u, Data, 4u);
  if ( v8 )
  {
    v4 = wil::details::in1diag3::Return_Win32(
           retaddr,
           (void *)0x87,
           (unsigned int)"onecore\\ds\\security\\base\\lsa\\pwdless\\policy_lib\\lib\\pwdlesspolicy.cxx",
           (const char *)v8,
           dwOptionsb);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
    return v4;
  }
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
  return 0;
}

```

## disassembly

```asm
0x180041e50  mov     [rsp-8+arg_8], rbx
0x180041e55  push    rbp
0x180041e56  lea     rbp, [rsp-180h]
0x180041e5e  sub     rsp, 280h
0x180041e65  mov     rax, cs:__security_cookie
0x180041e6c  xor     rax, rsp
0x180041e6f  mov     [rbp+180h+var_10], rax
0x180041e76  mov     r11, rcx
0x180041e79  mov     dword ptr [rsp+280h+Data], 1
0x180041e81  mov     [rsp+280h+hKey], 0
0x180041e8a  lea     r8, aSoftwareMicros_0; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x180041e91  mov     edx, 104h; unsigned __int64
0x180041e96  lea     rcx, [rsp+280h+SubKey]; unsigned __int16 *
0x180041e9b  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180041ea0  mov     ebx, eax
0x180041ea2  test    eax, eax
0x180041ea4  jns     short loc_180041ED4
0x180041ea6  mov     rcx, [rbp+188h]; this
0x180041ead  mov     r9d, eax; char *
0x180041eb0  lea     r8, aOnecoreDsSecur; "onecore\\ds\\security\\base\\lsa\\pwdle"...
0x180041eb7  mov     edx, 81h; void *
0x180041ebc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180041ec1  nop
0x180041ec2  lea     rcx, [rsp+280h+hKey]
0x180041ec7  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180041ecc  nop
0x180041ecd  mov     eax, ebx
0x180041ecf  jmp     loc_180041FF9
0x180041ed4  mov     r8, r11; unsigned __int16 *
0x180041ed7  lea     rcx, [rsp+280h+SubKey]; unsigned __int16 *
0x180041edc  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180041ee1  mov     ebx, eax
0x180041ee3  test    eax, eax
0x180041ee5  jns     short loc_180041F10
0x180041ee7  mov     rcx, [rbp+188h]; this
0x180041eee  mov     r9d, eax; char *
0x180041ef1  lea     r8, aOnecoreDsSecur; "onecore\\ds\\security\\base\\lsa\\pwdle"...
0x180041ef8  mov     edx, 83h; void *
0x180041efd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180041f02  nop
0x180041f03  lea     rcx, [rsp+280h+hKey]
0x180041f08  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180041f0d  nop
0x180041f0e  jmp     short loc_180041ECD
0x180041f10  xor     edx, edx
0x180041f12  lea     rcx, [rsp+280h+hKey]
0x180041f17  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x180041f1c  mov     [rsp+280h+lpdwDisposition], 0; lpdwDisposition
0x180041f25  lea     rax, [rsp+280h+hKey]
0x180041f2a  mov     [rsp+280h+phkResult], rax; phkResult
0x180041f2f  mov     [rsp+280h+lpSecurityAttributes], 0; lpSecurityAttributes
0x180041f38  mov     [rsp+280h+samDesired], 20006h; samDesired
0x180041f40  mov     [rsp+280h+dwOptions], 0; unsigned int
0x180041f48  xor     r9d, r9d; lpClass
0x180041f4b  xor     r8d, r8d; Reserved
0x180041f4e  lea     rdx, [rsp+280h+SubKey]; lpSubKey
0x180041f53  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180041f5a  call    cs:__imp_RegCreateKeyExW
0x180041f60  test    eax, eax
0x180041f62  jz      short loc_180041F91
0x180041f64  mov     rcx, [rbp+188h]; this
0x180041f6b  mov     r9d, eax; char *
0x180041f6e  lea     r8, aOnecoreDsSecur; "onecore\\ds\\security\\base\\lsa\\pwdle"...
0x180041f75  mov     edx, 85h; void *
0x180041f7a  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180041f7f  mov     ebx, eax
0x180041f81  lea     rcx, [rsp+280h+hKey]
0x180041f86  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180041f8b  nop
0x180041f8c  jmp     loc_180041ECD
0x180041f91  mov     r9d, 4; dwType
0x180041f97  mov     [rsp+280h+samDesired], r9d; cbData
0x180041f9c  lea     rax, [rsp+280h+Data]
0x180041fa1  mov     qword ptr [rsp+280h+dwOptions], rax; unsigned int
0x180041fa6  xor     r8d, r8d; Reserved
0x180041fa9  lea     rdx, aNgcsetup; "NgcSetup"
0x180041fb0  mov     rcx, [rsp+280h+hKey]; hKey
0x180041fb5  call    cs:__imp_RegSetValueExW
0x180041fbb  test    eax, eax
0x180041fbd  jz      short loc_180041FEC
0x180041fbf  mov     rcx, [rbp+188h]; this
0x180041fc6  mov     r9d, eax; char *
0x180041fc9  lea     r8, aOnecoreDsSecur; "onecore\\ds\\security\\base\\lsa\\pwdle"...
0x180041fd0  mov     edx, 87h; void *
0x180041fd5  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180041fda  mov     ebx, eax
0x180041fdc  lea     rcx, [rsp+280h+hKey]
0x180041fe1  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180041fe6  nop
0x180041fe7  jmp     loc_180041ECD
0x180041fec  lea     rcx, [rsp+280h+hKey]
0x180041ff1  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180041ff6  nop
0x180041ff7  xor     eax, eax
0x180041ff9  mov     rcx, [rbp+180h+var_10]
0x180042000  xor     rcx, rsp; StackCookie
0x180042003  call    __security_check_cookie
0x180042008  mov     rbx, [rsp+280h+arg_8]
0x180042010  add     rsp, 280h
0x180042017  pop     rbp
0x180042018  retn
```
