# VerifyCriticalKeysInUserHive(ushort const *)

- ea: `0x18003a7d8`
- end: `0x18003aba5`
- name: `?VerifyCriticalKeysInUserHive@@YAXPEBG@Z`
- size: `973`
- prototype: `void __fastcall(LPCWSTR lpSubKey)`
- caller_count: `2`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180030050`
- `0x18003b26c`

## callees

- `0x1800053c0`
- `0x18000e1a0`
- `0x1800130d0`
- `0x180013770`
- `0x1800146f0`
- `0x180022130`
- `0x18003a7d8`
- `0x180040bcc`
- `0x180041504`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003a816`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003a974`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003aa91`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003a816`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003a974`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003aa91`
- `api-ms-win-core-registry-l1-1-0!RegCopyTreeW` at `0x18003a997`
- `api-ms-win-core-registry-l1-1-0!RegCopyTreeW` at `0x18003ab7b`
- `api-ms-win-core-registry-l1-1-0!RegCopyTreeW` at `0x18003a997`
- `api-ms-win-core-registry-l1-1-0!RegCopyTreeW` at `0x18003ab7b`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18003a87a`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18003a8cb`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18003a923`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18003a9f8`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18003ab5d`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18003a87a`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18003a8cb`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18003a923`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18003a9f8`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18003ab5d`

## string_xrefs

- `0x18003aaed`: `onecore\ds\security\gina\profile\profsvc\util.cpp`
- `0x18003aa1b`: `%USERPROFILE%\AppData\Local\Temp`
- `0x18003aa32`: `%USERPROFILE%\AppData\Local\Temp`

## pseudocode

```c
void __fastcall VerifyCriticalKeysInUserHive(LPCWSTR lpSubKey)
{
  LSTATUS v2; // eax
  bool v3; // sf
  int v4; // eax
  LSTATUS v5; // eax
  bool v6; // sf
  LSTATUS v7; // eax
  const unsigned __int16 *v8; // rdx
  bool v9; // sf
  const unsigned __int16 *v10; // rdx
  const unsigned __int16 *v11; // rdx
  __int64 v12; // r9
  int v13; // eax
  int phkResult; // [rsp+20h] [rbp-50h]
  HKEY hKeyDest; // [rsp+50h] [rbp-20h] BYREF
  unsigned __int16 *v16[3]; // [rsp+58h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+28h]
  HKEY lpdwDisposition; // [rsp+A8h] [rbp+38h] BYREF
  HKEY hKey; // [rsp+B0h] [rbp+40h] BYREF
  HKEY hKeySrc; // [rsp+B8h] [rbp+48h] BYREF

  hKey = 0;
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
    &hKey,
    0);
  v2 = RegOpenKeyExW(HKEY_USERS, lpSubKey, 0, 0x2001Fu, &hKey);
  v3 = v2 < 0;
  if ( v2 > 0 )
    v3 = 1;
  if ( !v3 )
  {
    lpdwDisposition = 0;
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
      &lpdwDisposition,
      0);
    RegCreateKeyExW(hKey, L"System\\CurrentControlSet\\Control", 0, 0, 0, 0xF003Fu, 0, &lpdwDisposition, 0);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&lpdwDisposition);
    lpdwDisposition = 0;
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
      &lpdwDisposition,
      0);
    RegCreateKeyExW(
      hKey,
      L"Software\\Microsoft\\Windows\\CurrentVersion\\Explorer\\Shell Folders",
      0,
      0,
      0,
      0xF003Fu,
      0,
      &lpdwDisposition,
      0);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&lpdwDisposition);
    LODWORD(lpdwDisposition) = 0;
    hKeyDest = 0;
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
      &hKeyDest,
      0);
    v4 = RegCreateKeyExW(
           hKey,
           L"Software\\Microsoft\\Windows\\CurrentVersion\\Explorer\\User Shell Folders",
           0,
           0,
           0,
           0xF003Fu,
           0,
           &hKeyDest,
           (LPDWORD)&lpdwDisposition);
    if ( v4 > 0 )
      v4 = (unsigned __int16)v4 | 0x80070000;
    if ( v4 >= 0 && (_DWORD)lpdwDisposition == 1 )
    {
      hKeySrc = 0;
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
        &hKeySrc,
        0);
      v5 = RegOpenKeyExW(
             HKEY_LOCAL_MACHINE,
             L"Software\\Microsoft\\Windows\\CurrentVersion\\Explorer\\User Shell Folders\\Backup",
             0,
             0x20019u,
             &hKeySrc);
      v6 = v5 < 0;
      if ( v5 > 0 )
        v6 = 1;
      if ( !v6 )
        RegCopyTreeW(hKeySrc, 0, hKeyDest);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKeySrc);
    }
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKeyDest);
    LODWORD(lpdwDisposition) = 0;
    hKeySrc = 0;
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
      &hKeySrc,
      0);
    v7 = RegCreateKeyExW(hKey, L"Environment", 0, 0, 0, 0xF003Fu, 0, &hKeySrc, (LPDWORD)&lpdwDisposition);
    v9 = v7 < 0;
    if ( v7 > 0 )
      v9 = 1;
    if ( !v9 && (_DWORD)lpdwDisposition == 1 )
    {
      SHRegSetExpandString(hKeySrc, v8, L"TEMP", L"%USERPROFILE%\\AppData\\Local\\Temp");
      SHRegSetExpandString(hKeySrc, v10, L"TMP", L"%USERPROFILE%\\AppData\\Local\\Temp");
      SHRegSetExpandString(hKeySrc, v11, L"Path", L"%USERPROFILE%\\AppData\\Local\\Microsoft\\WindowsApps;");
    }
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKeySrc);
    lpdwDisposition = 0;
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
      &lpdwDisposition,
      0);
    if ( RegOpenKeyExW(
           hKey,
           L"Software\\Microsoft\\Windows NT\\CurrentVersion\\Winlogon",
           0,
           0x20019u,
           &lpdwDisposition) )
    {
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
        &lpdwDisposition,
        0);
      if ( !RegCreateKeyExW(
              hKey,
              L"Software\\Microsoft\\Windows NT\\CurrentVersion\\Winlogon",
              0,
              0,
              0,
              0xF003Fu,
              0,
              &lpdwDisposition,
              0) )
        RegCopyTreeW(
          HKEY_LOCAL_MACHINE,
          L"Software\\Microsoft\\Windows NT\\CurrentVersion\\Winlogon\\UserDefaults",
          lpdwDisposition);
    }
    else
    {
      memset(v16, 0, sizeof(v16));
      LOBYTE(v12) = 1;
      if ( (int)Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_InitializeFromRegistry(
                  v16,
                  lpdwDisposition,
                  L"ExcludeProfileDirs",
                  v12) < 0 )
      {
        v13 = Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::Initialize(
                v16,
                -2147483646,
                L"Software\\Microsoft\\Windows NT\\CurrentVersion\\Winlogon\\UserDefaults",
                L"ExcludeProfileDirs");
        if ( v13 >= 0 )
          SHRegSetString(
            hKey,
            L"Software\\Microsoft\\Windows NT\\CurrentVersion\\Winlogon",
            L"ExcludeProfileDirs",
            v16[0]);
        else
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x605,
            (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\util.cpp",
            (const char *)(unsigned int)v13,
            phkResult);
      }
      Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(v16);
    }
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&lpdwDisposition);
  }
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
}

```

## disassembly

```asm
0x18003a7d8  push    rbp
0x18003a7da  push    rbx
0x18003a7db  push    rsi
0x18003a7dc  push    rdi
0x18003a7dd  push    r15
0x18003a7df  mov     rbp, rsp
0x18003a7e2  sub     rsp, 70h
0x18003a7e6  mov     rbx, rcx
0x18003a7e9  xor     edi, edi
0x18003a7eb  lea     rcx, [rbp+hKey]
0x18003a7ef  mov     [rbp+hKey], rdi
0x18003a7f3  xor     edx, edx
0x18003a7f5  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x18003a7fa  lea     rax, [rbp+hKey]
0x18003a7fe  mov     r9d, 2001Fh; samDesired
0x18003a804  xor     r8d, r8d; ulOptions
0x18003a807  mov     [rsp+70h+phkResult], rax; phkResult
0x18003a80c  mov     rdx, rbx; lpSubKey
0x18003a80f  mov     rcx, 0FFFFFFFF80000003h; hKey
0x18003a816  call    cs:__imp_RegOpenKeyExW
0x18003a81d  nop     dword ptr [rax+rax+00h]
0x18003a822  mov     ebx, 80070000h
0x18003a827  test    eax, eax
0x18003a829  jle     short loc_18003A832
0x18003a82b  movzx   eax, ax
0x18003a82e  or      eax, ebx
0x18003a830  test    eax, eax
0x18003a832  js      loc_18003AB90
0x18003a838  xor     edx, edx
0x18003a83a  mov     [rbp+arg_8], rdi
0x18003a83e  lea     rcx, [rbp+arg_8]
0x18003a842  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x18003a847  mov     rcx, [rbp+hKey]; hKey
0x18003a84b  lea     rax, [rbp+arg_8]
0x18003a84f  mov     [rsp+70h+lpdwDisposition], rdi; lpdwDisposition
0x18003a854  lea     rdx, aSystemCurrentc_1; "System\\CurrentControlSet\\Control"
0x18003a85b  mov     [rsp+70h+var_38], rax; phkResult
0x18003a860  mov     r15d, 0F003Fh
0x18003a866  mov     [rsp+70h+lpSecurityAttributes], rdi; lpSecurityAttributes
0x18003a86b  xor     r9d, r9d; lpClass
0x18003a86e  mov     [rsp+70h+samDesired], r15d; samDesired
0x18003a873  xor     r8d, r8d; Reserved
0x18003a876  mov     dword ptr [rsp+70h+phkResult], edi; dwOptions
0x18003a87a  call    cs:__imp_RegCreateKeyExW
0x18003a881  nop     dword ptr [rax+rax+00h]
0x18003a886  lea     rcx, [rbp+arg_8]
0x18003a88a  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18003a88f  xor     edx, edx
0x18003a891  mov     [rbp+arg_8], rdi
0x18003a895  lea     rcx, [rbp+arg_8]
0x18003a899  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x18003a89e  mov     rcx, [rbp+hKey]; hKey
0x18003a8a2  lea     rax, [rbp+arg_8]
0x18003a8a6  mov     [rsp+70h+lpdwDisposition], rdi; lpdwDisposition
0x18003a8ab  lea     rdx, aSoftwareMicros_22; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18003a8b2  mov     [rsp+70h+var_38], rax; phkResult
0x18003a8b7  xor     r9d, r9d; lpClass
0x18003a8ba  mov     [rsp+70h+lpSecurityAttributes], rdi; lpSecurityAttributes
0x18003a8bf  xor     r8d, r8d; Reserved
0x18003a8c2  mov     [rsp+70h+samDesired], r15d; samDesired
0x18003a8c7  mov     dword ptr [rsp+70h+phkResult], edi; dwOptions
0x18003a8cb  call    cs:__imp_RegCreateKeyExW
0x18003a8d2  nop     dword ptr [rax+rax+00h]
0x18003a8d7  lea     rcx, [rbp+arg_8]
0x18003a8db  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18003a8e0  xor     edx, edx
0x18003a8e2  mov     dword ptr [rbp+arg_8], edi
0x18003a8e5  lea     rcx, [rbp+hKeyDest]
0x18003a8e9  mov     [rbp+hKeyDest], rdi
0x18003a8ed  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x18003a8f2  mov     rcx, [rbp+hKey]; hKey
0x18003a8f6  lea     rax, [rbp+arg_8]
0x18003a8fa  mov     [rsp+70h+lpdwDisposition], rax; lpdwDisposition
0x18003a8ff  lea     rdx, aSoftwareMicros_17; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18003a906  lea     rax, [rbp+hKeyDest]
0x18003a90a  xor     r9d, r9d; lpClass
0x18003a90d  mov     [rsp+70h+var_38], rax; phkResult
0x18003a912  xor     r8d, r8d; Reserved
0x18003a915  mov     [rsp+70h+lpSecurityAttributes], rdi; lpSecurityAttributes
0x18003a91a  mov     [rsp+70h+samDesired], r15d; samDesired
0x18003a91f  mov     dword ptr [rsp+70h+phkResult], edi; dwOptions
0x18003a923  call    cs:__imp_RegCreateKeyExW
0x18003a92a  nop     dword ptr [rax+rax+00h]
0x18003a92f  test    eax, eax
0x18003a931  jle     short loc_18003A938
0x18003a933  movzx   eax, ax
0x18003a936  or      eax, ebx
0x18003a938  mov     rsi, 0FFFFFFFF80000002h
0x18003a93f  test    eax, eax
0x18003a941  js      short loc_18003A9AC
0x18003a943  cmp     dword ptr [rbp+arg_8], 1
0x18003a947  jnz     short loc_18003A9AC
0x18003a949  xor     edx, edx
0x18003a94b  mov     [rbp+hKeySrc], rdi
0x18003a94f  lea     rcx, [rbp+hKeySrc]
0x18003a953  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x18003a958  lea     rax, [rbp+hKeySrc]
0x18003a95c  mov     r9d, 20019h; samDesired
0x18003a962  xor     r8d, r8d; ulOptions
0x18003a965  mov     [rsp+70h+phkResult], rax; phkResult
0x18003a96a  lea     rdx, aSoftwareMicros_6; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18003a971  mov     rcx, rsi; hKey
0x18003a974  call    cs:__imp_RegOpenKeyExW
0x18003a97b  nop     dword ptr [rax+rax+00h]
0x18003a980  test    eax, eax
0x18003a982  jle     short loc_18003A98B
0x18003a984  movzx   eax, ax
0x18003a987  or      eax, ebx
0x18003a989  test    eax, eax
0x18003a98b  js      short loc_18003A9A3
0x18003a98d  mov     r8, [rbp+hKeyDest]; hKeyDest
0x18003a991  xor     edx, edx; lpSubKey
0x18003a993  mov     rcx, [rbp+hKeySrc]; hKeySrc
0x18003a997  call    cs:__imp_RegCopyTreeW
0x18003a99e  nop     dword ptr [rax+rax+00h]
0x18003a9a3  lea     rcx, [rbp+hKeySrc]
0x18003a9a7  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18003a9ac  lea     rcx, [rbp+hKeyDest]
0x18003a9b0  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18003a9b5  xor     edx, edx
0x18003a9b7  mov     dword ptr [rbp+arg_8], edi
0x18003a9ba  lea     rcx, [rbp+hKeySrc]
0x18003a9be  mov     [rbp+hKeySrc], rdi
0x18003a9c2  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x18003a9c7  mov     rcx, [rbp+hKey]; hKey
0x18003a9cb  lea     rax, [rbp+arg_8]
0x18003a9cf  mov     [rsp+70h+lpdwDisposition], rax; lpdwDisposition
0x18003a9d4  lea     rdx, aEnvironment; "Environment"
0x18003a9db  lea     rax, [rbp+hKeySrc]
0x18003a9df  xor     r9d, r9d; lpClass
0x18003a9e2  mov     [rsp+70h+var_38], rax; phkResult
0x18003a9e7  xor     r8d, r8d; Reserved
0x18003a9ea  mov     [rsp+70h+lpSecurityAttributes], rdi; lpSecurityAttributes
0x18003a9ef  mov     [rsp+70h+samDesired], r15d; samDesired
0x18003a9f4  mov     dword ptr [rsp+70h+phkResult], edi; dwOptions
0x18003a9f8  call    cs:__imp_RegCreateKeyExW
0x18003a9ff  nop     dword ptr [rax+rax+00h]
0x18003aa04  test    eax, eax
0x18003aa06  jle     short loc_18003AA0F
0x18003aa08  movzx   eax, ax
0x18003aa0b  or      eax, ebx
0x18003aa0d  test    eax, eax
0x18003aa0f  js      short loc_18003AA5C
0x18003aa11  cmp     dword ptr [rbp+arg_8], 1
0x18003aa15  jnz     short loc_18003AA5C
0x18003aa17  mov     rcx, [rbp+hKeySrc]; HKEY
0x18003aa1b  lea     r9, aUserprofileApp; "%USERPROFILE%\\AppData\\Local\\Temp"
0x18003aa22  lea     r8, aTemp; "TEMP"
0x18003aa29  call    ?SHRegSetExpandString@@YAJPEAUHKEY__@@PEBG11@Z; SHRegSetExpandString(HKEY__ *,ushort const *,ushort const *,ushort const *)
0x18003aa2e  mov     rcx, [rbp+hKeySrc]; HKEY
0x18003aa32  lea     r9, aUserprofileApp; "%USERPROFILE%\\AppData\\Local\\Temp"
0x18003aa39  lea     r8, aTmp; "TMP"
0x18003aa40  call    ?SHRegSetExpandString@@YAJPEAUHKEY__@@PEBG11@Z; SHRegSetExpandString(HKEY__ *,ushort const *,ushort const *,ushort const *)
0x18003aa45  mov     rcx, [rbp+hKeySrc]; HKEY
0x18003aa49  lea     r9, aUserprofileApp_0; "%USERPROFILE%\\AppData\\Local\\Microsof"...
0x18003aa50  lea     r8, aPath; "Path"
0x18003aa57  call    ?SHRegSetExpandString@@YAJPEAUHKEY__@@PEBG11@Z; SHRegSetExpandString(HKEY__ *,ushort const *,ushort const *,ushort const *)
0x18003aa5c  lea     rcx, [rbp+hKeySrc]
0x18003aa60  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18003aa65  xor     edx, edx
0x18003aa67  mov     [rbp+arg_8], rdi
0x18003aa6b  lea     rcx, [rbp+arg_8]
0x18003aa6f  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x18003aa74  mov     rcx, [rbp+hKey]; hKey
0x18003aa78  lea     rax, [rbp+arg_8]
0x18003aa7c  mov     r9d, 20019h; samDesired
0x18003aa82  mov     [rsp+70h+phkResult], rax; int
0x18003aa87  xor     r8d, r8d; ulOptions
0x18003aa8a  lea     rdx, aSoftwareMicros_39; "Software\\Microsoft\\Windows NT\\Curren"...
0x18003aa91  call    cs:__imp_RegOpenKeyExW
0x18003aa98  nop     dword ptr [rax+rax+00h]
0x18003aa9d  test    eax, eax
0x18003aa9f  jnz     loc_18003AB25
0x18003aaa5  mov     rdx, [rbp+arg_8]
0x18003aaa9  lea     rbx, aExcludeprofile; "ExcludeProfileDirs"
0x18003aab0  mov     r8, rbx
0x18003aab3  mov     [rbp+var_18], rdi
0x18003aab7  mov     r9b, 1
0x18003aaba  mov     [rbp+var_10], rdi
0x18003aabe  lea     rcx, [rbp+var_18]
0x18003aac2  mov     [rbp+var_8], rdi
0x18003aac6  call    ?_InitializeFromRegistry@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJPEAUHKEY__@@PEBG_N@Z; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_InitializeFromRegistry(HKEY__ *,ushort const *,bool)
0x18003aacb  test    eax, eax
0x18003aacd  jns     short loc_18003AB1A
0x18003aacf  mov     r9, rbx
0x18003aad2  lea     r8, aSoftwareMicros; "Software\\Microsoft\\Windows NT\\Curren"...
0x18003aad9  mov     rdx, rsi
0x18003aadc  lea     rcx, [rbp+var_18]
0x18003aae0  call    ?Initialize@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEAUHKEY__@@PEBG1@Z; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::Initialize(HKEY__ *,ushort const *,ushort const *)
0x18003aae5  test    eax, eax
0x18003aae7  jns     short loc_18003AB03
0x18003aae9  mov     rcx, [rbp+28h]; this
0x18003aaed  lea     r8, aOnecoreDsSecur_14; "onecore\\ds\\security\\gina\\profile\\p"...
0x18003aaf4  mov     r9d, eax; char *
0x18003aaf7  mov     edx, 605h; void *
0x18003aafc  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18003ab01  jmp     short loc_18003AB1A
0x18003ab03  mov     r9, [rbp+var_18]; unsigned __int16 *
0x18003ab07  lea     rdx, aSoftwareMicros_39; "Software\\Microsoft\\Windows NT\\Curren"...
0x18003ab0e  mov     rcx, [rbp+hKey]; hKey
0x18003ab12  mov     r8, rbx; unsigned __int16 *
0x18003ab15  call    ?SHRegSetString@@YAJPEAUHKEY__@@PEBG11@Z; SHRegSetString(HKEY__ *,ushort const *,ushort const *,ushort const *)
0x18003ab1a  lea     rcx, [rbp+var_18]
0x18003ab1e  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x18003ab23  jmp     short loc_18003AB87
0x18003ab25  xor     edx, edx
0x18003ab27  lea     rcx, [rbp+arg_8]
0x18003ab2b  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x18003ab30  mov     rcx, [rbp+hKey]; hKey
0x18003ab34  lea     rax, [rbp+arg_8]
0x18003ab38  mov     [rsp+70h+lpdwDisposition], rdi; lpdwDisposition
0x18003ab3d  lea     rdx, aSoftwareMicros_39; "Software\\Microsoft\\Windows NT\\Curren"...
0x18003ab44  mov     [rsp+70h+var_38], rax; phkResult
0x18003ab49  xor     r9d, r9d; lpClass
0x18003ab4c  mov     [rsp+70h+lpSecurityAttributes], rdi; lpSecurityAttributes
0x18003ab51  xor     r8d, r8d; Reserved
0x18003ab54  mov     [rsp+70h+samDesired], r15d; samDesired
0x18003ab59  mov     dword ptr [rsp+70h+phkResult], edi; dwOptions
0x18003ab5d  call    cs:__imp_RegCreateKeyExW
0x18003ab64  nop     dword ptr [rax+rax+00h]
0x18003ab69  test    eax, eax
0x18003ab6b  jnz     short loc_18003AB87
0x18003ab6d  mov     r8, [rbp+arg_8]; hKeyDest
0x18003ab71  lea     rdx, aSoftwareMicros; "Software\\Microsoft\\Windows NT\\Curren"...
0x18003ab78  mov     rcx, rsi; hKeySrc
0x18003ab7b  call    cs:__imp_RegCopyTreeW
0x18003ab82  nop     dword ptr [rax+rax+00h]
0x18003ab87  lea     rcx, [rbp+arg_8]
0x18003ab8b  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18003ab90  lea     rcx, [rbp+hKey]
0x18003ab94  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18003ab99  add     rsp, 70h
0x18003ab9d  pop     r15
0x18003ab9f  pop     rdi
0x18003aba0  pop     rsi
0x18003aba1  pop     rbx
0x18003aba2  pop     rbp
0x18003aba3  retn
```
