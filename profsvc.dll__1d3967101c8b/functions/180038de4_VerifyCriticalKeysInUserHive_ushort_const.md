# VerifyCriticalKeysInUserHive(ushort const *)

- ea: `0x180038de4`
- end: `0x1800391a0`
- name: `?VerifyCriticalKeysInUserHive@@YAXPEBG@Z`
- size: `956`
- prototype: `void __fastcall(LPCWSTR lpSubKey)`
- caller_count: `2`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18002ed00`
- `0x180039d6c`

## callees

- `0x180006b10`
- `0x1800079b0`
- `0x1800111a0`
- `0x18001e070`
- `0x18001f060`
- `0x180038de4`
- `0x18003f42c`
- `0x18003fd14`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180038e23`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180038f75`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180039092`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180038e23`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180038f75`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180039092`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180038e90`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180038ee1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180038fa1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180038fb0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180039060`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003917f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003918e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180038e90`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180038ee1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180038fa1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180038fb0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180039060`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003917f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003918e`
- `api-ms-win-core-registry-l1-1-0!RegCopyTreeW` at `0x180038f92`
- `api-ms-win-core-registry-l1-1-0!RegCopyTreeW` at `0x180039170`
- `api-ms-win-core-registry-l1-1-0!RegCopyTreeW` at `0x180038f92`
- `api-ms-win-core-registry-l1-1-0!RegCopyTreeW` at `0x180039170`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180038e81`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180038ed2`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180038f2a`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180038ff9`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180039158`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180038e81`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180038ed2`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180038f2a`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180038ff9`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180039158`

## string_xrefs

- `0x1800390e8`: `onecore\ds\security\gina\profile\profsvc\util.cpp`
- `0x180039016`: `%USERPROFILE%\AppData\Local\Temp`
- `0x18003902d`: `%USERPROFILE%\AppData\Local\Temp`

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
  int v12; // eax
  HKEY hKeyDest; // [rsp+50h] [rbp-20h] BYREF
  unsigned __int16 *v14[3]; // [rsp+58h] [rbp-18h] BYREF
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
    if ( lpdwDisposition )
      RegCloseKey(lpdwDisposition);
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
    if ( lpdwDisposition )
      RegCloseKey(lpdwDisposition);
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
      if ( hKeySrc )
        RegCloseKey(hKeySrc);
    }
    if ( hKeyDest )
      RegCloseKey(hKeyDest);
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
    if ( hKeySrc )
      RegCloseKey(hKeySrc);
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
      memset(v14, 0, sizeof(v14));
      if ( (int)Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_InitializeFromRegistry(
                  (__int64)v14,
                  lpdwDisposition,
                  L"ExcludeProfileDirs",
                  1) < 0 )
      {
        v12 = Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::Initialize(
                v14,
                -2147483646,
                L"Software\\Microsoft\\Windows NT\\CurrentVersion\\Winlogon\\UserDefaults",
                L"ExcludeProfileDirs");
        if ( v12 >= 0 )
          SHRegSetString(
            hKey,
            L"Software\\Microsoft\\Windows NT\\CurrentVersion\\Winlogon",
            L"ExcludeProfileDirs",
            v14[0]);
        else
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x605,
            (int)"onecore\\ds\\security\\gina\\profile\\profsvc\\util.cpp",
            (const char *)(unsigned int)v12);
      }
      Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free((__int64)v14);
    }
    if ( lpdwDisposition )
      RegCloseKey(lpdwDisposition);
  }
  if ( hKey )
    RegCloseKey(hKey);
}

```

## disassembly

```asm
0x180038de4  push    rbp
0x180038de6  push    rbx
0x180038de7  push    rdi
0x180038de8  push    r14
0x180038dea  push    r15
0x180038dec  mov     rbp, rsp
0x180038def  sub     rsp, 70h
0x180038df3  mov     rbx, rcx
0x180038df6  xor     edi, edi
0x180038df8  lea     rcx, [rbp+hKey]
0x180038dfc  mov     [rbp+hKey], rdi
0x180038e00  xor     edx, edx
0x180038e02  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x180038e07  lea     rax, [rbp+hKey]
0x180038e0b  mov     r9d, 2001Fh; samDesired
0x180038e11  xor     r8d, r8d; ulOptions
0x180038e14  mov     [rsp+70h+phkResult], rax; phkResult
0x180038e19  mov     rdx, rbx; lpSubKey
0x180038e1c  mov     rcx, 0FFFFFFFF80000003h; hKey
0x180038e23  call    cs:__imp_RegOpenKeyExW
0x180038e29  mov     ebx, 80070000h
0x180038e2e  test    eax, eax
0x180038e30  jle     short loc_180038E39
0x180038e32  movzx   eax, ax
0x180038e35  or      eax, ebx
0x180038e37  test    eax, eax
0x180038e39  js      loc_180039185
0x180038e3f  xor     edx, edx
0x180038e41  mov     [rbp+arg_8], rdi
0x180038e45  lea     rcx, [rbp+arg_8]
0x180038e49  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x180038e4e  mov     rcx, [rbp+hKey]; hKey
0x180038e52  lea     rax, [rbp+arg_8]
0x180038e56  mov     [rsp+70h+lpdwDisposition], rdi; lpdwDisposition
0x180038e5b  lea     rdx, aSystemCurrentc_1; "System\\CurrentControlSet\\Control"
0x180038e62  mov     [rsp+70h+var_38], rax; phkResult
0x180038e67  mov     r14d, 0F003Fh
0x180038e6d  mov     [rsp+70h+lpSecurityAttributes], rdi; lpSecurityAttributes
0x180038e72  xor     r9d, r9d; lpClass
0x180038e75  mov     [rsp+70h+samDesired], r14d; samDesired
0x180038e7a  xor     r8d, r8d; Reserved
0x180038e7d  mov     dword ptr [rsp+70h+phkResult], edi; dwOptions
0x180038e81  call    cs:__imp_RegCreateKeyExW
0x180038e87  mov     rcx, [rbp+arg_8]; hKey
0x180038e8b  test    rcx, rcx
0x180038e8e  jz      short loc_180038E96
0x180038e90  call    cs:__imp_RegCloseKey
0x180038e96  xor     edx, edx
0x180038e98  mov     [rbp+arg_8], rdi
0x180038e9c  lea     rcx, [rbp+arg_8]
0x180038ea0  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x180038ea5  mov     rcx, [rbp+hKey]; hKey
0x180038ea9  lea     rax, [rbp+arg_8]
0x180038ead  mov     [rsp+70h+lpdwDisposition], rdi; lpdwDisposition
0x180038eb2  lea     rdx, aSoftwareMicros_22; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180038eb9  mov     [rsp+70h+var_38], rax; phkResult
0x180038ebe  xor     r9d, r9d; lpClass
0x180038ec1  mov     [rsp+70h+lpSecurityAttributes], rdi; lpSecurityAttributes
0x180038ec6  xor     r8d, r8d; Reserved
0x180038ec9  mov     [rsp+70h+samDesired], r14d; samDesired
0x180038ece  mov     dword ptr [rsp+70h+phkResult], edi; dwOptions
0x180038ed2  call    cs:__imp_RegCreateKeyExW
0x180038ed8  mov     rcx, [rbp+arg_8]; hKey
0x180038edc  test    rcx, rcx
0x180038edf  jz      short loc_180038EE7
0x180038ee1  call    cs:__imp_RegCloseKey
0x180038ee7  xor     edx, edx
0x180038ee9  mov     dword ptr [rbp+arg_8], edi
0x180038eec  lea     rcx, [rbp+hKeyDest]
0x180038ef0  mov     [rbp+hKeyDest], rdi
0x180038ef4  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x180038ef9  mov     rcx, [rbp+hKey]; hKey
0x180038efd  lea     rax, [rbp+arg_8]
0x180038f01  mov     [rsp+70h+lpdwDisposition], rax; lpdwDisposition
0x180038f06  lea     rdx, aSoftwareMicros_17; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180038f0d  lea     rax, [rbp+hKeyDest]
0x180038f11  xor     r9d, r9d; lpClass
0x180038f14  mov     [rsp+70h+var_38], rax; phkResult
0x180038f19  xor     r8d, r8d; Reserved
0x180038f1c  mov     [rsp+70h+lpSecurityAttributes], rdi; lpSecurityAttributes
0x180038f21  mov     [rsp+70h+samDesired], r14d; samDesired
0x180038f26  mov     dword ptr [rsp+70h+phkResult], edi; dwOptions
0x180038f2a  call    cs:__imp_RegCreateKeyExW
0x180038f30  test    eax, eax
0x180038f32  jle     short loc_180038F39
0x180038f34  movzx   eax, ax
0x180038f37  or      eax, ebx
0x180038f39  mov     r15, 0FFFFFFFF80000002h
0x180038f40  test    eax, eax
0x180038f42  js      short loc_180038FA7
0x180038f44  cmp     dword ptr [rbp+arg_8], 1
0x180038f48  jnz     short loc_180038FA7
0x180038f4a  xor     edx, edx
0x180038f4c  mov     [rbp+hKeySrc], rdi
0x180038f50  lea     rcx, [rbp+hKeySrc]
0x180038f54  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x180038f59  lea     rax, [rbp+hKeySrc]
0x180038f5d  mov     r9d, 20019h; samDesired
0x180038f63  xor     r8d, r8d; ulOptions
0x180038f66  mov     [rsp+70h+phkResult], rax; phkResult
0x180038f6b  lea     rdx, aSoftwareMicros_6; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180038f72  mov     rcx, r15; hKey
0x180038f75  call    cs:__imp_RegOpenKeyExW
0x180038f7b  test    eax, eax
0x180038f7d  jle     short loc_180038F86
0x180038f7f  movzx   eax, ax
0x180038f82  or      eax, ebx
0x180038f84  test    eax, eax
0x180038f86  js      short loc_180038F98
0x180038f88  mov     r8, [rbp+hKeyDest]; hKeyDest
0x180038f8c  xor     edx, edx; lpSubKey
0x180038f8e  mov     rcx, [rbp+hKeySrc]; hKeySrc
0x180038f92  call    cs:__imp_RegCopyTreeW
0x180038f98  mov     rcx, [rbp+hKeySrc]; hKey
0x180038f9c  test    rcx, rcx
0x180038f9f  jz      short loc_180038FA7
0x180038fa1  call    cs:__imp_RegCloseKey
0x180038fa7  mov     rcx, [rbp+hKeyDest]; hKey
0x180038fab  test    rcx, rcx
0x180038fae  jz      short loc_180038FB6
0x180038fb0  call    cs:__imp_RegCloseKey
0x180038fb6  xor     edx, edx
0x180038fb8  mov     dword ptr [rbp+arg_8], edi
0x180038fbb  lea     rcx, [rbp+hKeySrc]
0x180038fbf  mov     [rbp+hKeySrc], rdi
0x180038fc3  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x180038fc8  mov     rcx, [rbp+hKey]; hKey
0x180038fcc  lea     rax, [rbp+arg_8]
0x180038fd0  mov     [rsp+70h+lpdwDisposition], rax; lpdwDisposition
0x180038fd5  lea     rdx, aEnvironment; "Environment"
0x180038fdc  lea     rax, [rbp+hKeySrc]
0x180038fe0  xor     r9d, r9d; lpClass
0x180038fe3  mov     [rsp+70h+var_38], rax; phkResult
0x180038fe8  xor     r8d, r8d; Reserved
0x180038feb  mov     [rsp+70h+lpSecurityAttributes], rdi; lpSecurityAttributes
0x180038ff0  mov     [rsp+70h+samDesired], r14d; samDesired
0x180038ff5  mov     dword ptr [rsp+70h+phkResult], edi; dwOptions
0x180038ff9  call    cs:__imp_RegCreateKeyExW
0x180038fff  test    eax, eax
0x180039001  jle     short loc_18003900A
0x180039003  movzx   eax, ax
0x180039006  or      eax, ebx
0x180039008  test    eax, eax
0x18003900a  js      short loc_180039057
0x18003900c  cmp     dword ptr [rbp+arg_8], 1
0x180039010  jnz     short loc_180039057
0x180039012  mov     rcx, [rbp+hKeySrc]; HKEY
0x180039016  lea     r9, aUserprofileApp; "%USERPROFILE%\\AppData\\Local\\Temp"
0x18003901d  lea     r8, aTemp; "TEMP"
0x180039024  call    ?SHRegSetExpandString@@YAJPEAUHKEY__@@PEBG11@Z; SHRegSetExpandString(HKEY__ *,ushort const *,ushort const *,ushort const *)
0x180039029  mov     rcx, [rbp+hKeySrc]; HKEY
0x18003902d  lea     r9, aUserprofileApp; "%USERPROFILE%\\AppData\\Local\\Temp"
0x180039034  lea     r8, aTmp; "TMP"
0x18003903b  call    ?SHRegSetExpandString@@YAJPEAUHKEY__@@PEBG11@Z; SHRegSetExpandString(HKEY__ *,ushort const *,ushort const *,ushort const *)
0x180039040  mov     rcx, [rbp+hKeySrc]; HKEY
0x180039044  lea     r9, aUserprofileApp_0; "%USERPROFILE%\\AppData\\Local\\Microsof"...
0x18003904b  lea     r8, aPath; "Path"
0x180039052  call    ?SHRegSetExpandString@@YAJPEAUHKEY__@@PEBG11@Z; SHRegSetExpandString(HKEY__ *,ushort const *,ushort const *,ushort const *)
0x180039057  mov     rcx, [rbp+hKeySrc]; hKey
0x18003905b  test    rcx, rcx
0x18003905e  jz      short loc_180039066
0x180039060  call    cs:__imp_RegCloseKey
0x180039066  xor     edx, edx
0x180039068  mov     [rbp+arg_8], rdi
0x18003906c  lea     rcx, [rbp+arg_8]
0x180039070  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x180039075  mov     rcx, [rbp+hKey]; hKey
0x180039079  lea     rax, [rbp+arg_8]
0x18003907d  mov     r9d, 20019h; samDesired
0x180039083  mov     [rsp+70h+phkResult], rax; int
0x180039088  xor     r8d, r8d; ulOptions
0x18003908b  lea     rdx, aSoftwareMicros_39; "Software\\Microsoft\\Windows NT\\Curren"...
0x180039092  call    cs:__imp_RegOpenKeyExW
0x180039098  test    eax, eax
0x18003909a  jnz     loc_180039120
0x1800390a0  mov     rdx, [rbp+arg_8]
0x1800390a4  lea     rbx, aExcludeprofile; "ExcludeProfileDirs"
0x1800390ab  mov     r8, rbx
0x1800390ae  mov     [rbp+var_18], rdi
0x1800390b2  mov     r9b, 1
0x1800390b5  mov     [rbp+var_10], rdi
0x1800390b9  lea     rcx, [rbp+var_18]
0x1800390bd  mov     [rbp+var_8], rdi
0x1800390c1  call    ?_InitializeFromRegistry@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJPEAUHKEY__@@PEBG_N@Z; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_InitializeFromRegistry(HKEY__ *,ushort const *,bool)
0x1800390c6  test    eax, eax
0x1800390c8  jns     short loc_180039115
0x1800390ca  mov     r9, rbx
0x1800390cd  lea     r8, aSoftwareMicros; "Software\\Microsoft\\Windows NT\\Curren"...
0x1800390d4  mov     rdx, r15
0x1800390d7  lea     rcx, [rbp+var_18]
0x1800390db  call    ?Initialize@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEAUHKEY__@@PEBG1@Z; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::Initialize(HKEY__ *,ushort const *,ushort const *)
0x1800390e0  test    eax, eax
0x1800390e2  jns     short loc_1800390FE
0x1800390e4  mov     rcx, [rbp+28h]; this
0x1800390e8  lea     r8, aOnecoreDsSecur_14; "onecore\\ds\\security\\gina\\profile\\p"...
0x1800390ef  mov     r9d, eax; char *
0x1800390f2  mov     edx, 605h; void *
0x1800390f7  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800390fc  jmp     short loc_180039115
0x1800390fe  mov     r9, [rbp+var_18]; unsigned __int16 *
0x180039102  lea     rdx, aSoftwareMicros_39; "Software\\Microsoft\\Windows NT\\Curren"...
0x180039109  mov     rcx, [rbp+hKey]; hKey
0x18003910d  mov     r8, rbx; unsigned __int16 *
0x180039110  call    ?SHRegSetString@@YAJPEAUHKEY__@@PEBG11@Z; SHRegSetString(HKEY__ *,ushort const *,ushort const *,ushort const *)
0x180039115  lea     rcx, [rbp+var_18]
0x180039119  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x18003911e  jmp     short loc_180039176
0x180039120  xor     edx, edx
0x180039122  lea     rcx, [rbp+arg_8]
0x180039126  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x18003912b  mov     rcx, [rbp+hKey]; hKey
0x18003912f  lea     rax, [rbp+arg_8]
0x180039133  mov     [rsp+70h+lpdwDisposition], rdi; lpdwDisposition
0x180039138  lea     rdx, aSoftwareMicros_39; "Software\\Microsoft\\Windows NT\\Curren"...
0x18003913f  mov     [rsp+70h+var_38], rax; phkResult
0x180039144  xor     r9d, r9d; lpClass
0x180039147  mov     [rsp+70h+lpSecurityAttributes], rdi; lpSecurityAttributes
0x18003914c  xor     r8d, r8d; Reserved
0x18003914f  mov     [rsp+70h+samDesired], r14d; samDesired
0x180039154  mov     dword ptr [rsp+70h+phkResult], edi; dwOptions
0x180039158  call    cs:__imp_RegCreateKeyExW
0x18003915e  test    eax, eax
0x180039160  jnz     short loc_180039176
0x180039162  mov     r8, [rbp+arg_8]; hKeyDest
0x180039166  lea     rdx, aSoftwareMicros; "Software\\Microsoft\\Windows NT\\Curren"...
0x18003916d  mov     rcx, r15; hKeySrc
0x180039170  call    cs:__imp_RegCopyTreeW
0x180039176  mov     rcx, [rbp+arg_8]; hKey
0x18003917a  test    rcx, rcx
0x18003917d  jz      short loc_180039185
0x18003917f  call    cs:__imp_RegCloseKey
0x180039185  mov     rcx, [rbp+hKey]; hKey
0x180039189  test    rcx, rcx
0x18003918c  jz      short loc_180039194
0x18003918e  call    cs:__imp_RegCloseKey
0x180039194  add     rsp, 70h
0x180039198  pop     r15
0x18003919a  pop     r14
0x18003919c  pop     rdi
0x18003919d  pop     rbx
0x18003919e  pop     rbp
0x18003919f  retn
```
