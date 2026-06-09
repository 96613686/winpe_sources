# VerifyCriticalKeysInUserHive(ushort const *)

- ea: `0x18000ebe0`
- end: `0x18000ee54`
- name: `?VerifyCriticalKeysInUserHive@@YAXPEBG@Z`
- size: `628`
- prototype: `void __fastcall(LPCWSTR lpSubKey)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000a250`

## callees

- `0x180009cb0`
- `0x18000a1f4`
- `0x18000ebe0`
- `0x180016acc`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18000ec76`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18000ecc4`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18000ed19`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18000eddc`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18000ec76`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18000ecc4`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18000ed19`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18000eddc`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000ec1b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000ed61`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000ec1b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000ed61`
- `api-ms-win-core-registry-l1-1-0!RegCopyTreeW` at `0x18000ed7e`
- `api-ms-win-core-registry-l1-1-0!RegCopyTreeW` at `0x18000ed7e`

## string_xrefs

- `0x18000edf9`: `%USERPROFILE%\AppData\Local\Temp`
- `0x18000ee10`: `%USERPROFILE%\AppData\Local\Temp`

## pseudocode

```c
void __fastcall VerifyCriticalKeysInUserHive(LPCWSTR lpSubKey)
{
  LSTATUS v2; // eax
  bool v3; // sf
  LSTATUS Key; // eax
  bool v5; // sf
  LSTATUS v6; // eax
  bool v7; // sf
  LSTATUS v8; // eax
  const unsigned __int16 *v9; // rdx
  bool v10; // sf
  const unsigned __int16 *v11; // rdx
  const unsigned __int16 *v12; // rdx
  HKEY hKeyDest[2]; // [rsp+50h] [rbp-10h] BYREF
  HKEY lpdwDisposition; // [rsp+88h] [rbp+28h] BYREF
  HKEY hKey; // [rsp+90h] [rbp+30h] BYREF
  HKEY hKeySrc; // [rsp+98h] [rbp+38h] BYREF

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
    hKeyDest[0] = 0;
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
      hKeyDest,
      0);
    Key = RegCreateKeyExW(
            hKey,
            L"Software\\Microsoft\\Windows\\CurrentVersion\\Explorer\\User Shell Folders",
            0,
            0,
            0,
            0xF003Fu,
            0,
            hKeyDest,
            (LPDWORD)&lpdwDisposition);
    v5 = Key < 0;
    if ( Key > 0 )
      v5 = 1;
    if ( !v5 && (_DWORD)lpdwDisposition == 1 )
    {
      hKeySrc = 0;
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
        &hKeySrc,
        0);
      v6 = RegOpenKeyExW(
             HKEY_LOCAL_MACHINE,
             L"Software\\Microsoft\\Windows\\CurrentVersion\\Explorer\\User Shell Folders\\Backup",
             0,
             0x20019u,
             &hKeySrc);
      v7 = v6 < 0;
      if ( v6 > 0 )
        v7 = 1;
      if ( !v7 )
        RegCopyTreeW(hKeySrc, 0, hKeyDest[0]);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKeySrc);
    }
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(hKeyDest);
    LODWORD(lpdwDisposition) = 0;
    hKeySrc = 0;
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
      &hKeySrc,
      0);
    v8 = RegCreateKeyExW(hKey, L"Environment", 0, 0, 0, 0xF003Fu, 0, &hKeySrc, (LPDWORD)&lpdwDisposition);
    v10 = v8 < 0;
    if ( v8 > 0 )
      v10 = 1;
    if ( !v10 && (_DWORD)lpdwDisposition == 1 )
    {
      SHRegSetExpandString(hKeySrc, v9, L"TEMP", (const BYTE *)L"%USERPROFILE%\\AppData\\Local\\Temp");
      SHRegSetExpandString(hKeySrc, v11, L"TMP", (const BYTE *)L"%USERPROFILE%\\AppData\\Local\\Temp");
      SHRegSetExpandString(
        hKeySrc,
        v12,
        L"Path",
        (const BYTE *)L"%USERPROFILE%\\AppData\\Local\\Microsoft\\WindowsApps;");
    }
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKeySrc);
  }
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
}

```

## disassembly

```asm
0x18000ebe0  push    rbp
0x18000ebe2  push    rbx
0x18000ebe3  push    rdi
0x18000ebe4  mov     rbp, rsp
0x18000ebe7  sub     rsp, 60h
0x18000ebeb  mov     rbx, rcx
0x18000ebee  xor     edi, edi
0x18000ebf0  lea     rcx, [rbp+hKey]
0x18000ebf4  mov     [rbp+hKey], rdi
0x18000ebf8  xor     edx, edx
0x18000ebfa  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x18000ebff  lea     rax, [rbp+hKey]
0x18000ec03  mov     r9d, 2001Fh; samDesired
0x18000ec09  xor     r8d, r8d; ulOptions
0x18000ec0c  mov     [rsp+60h+phkResult], rax; phkResult
0x18000ec11  mov     rdx, rbx; lpSubKey
0x18000ec14  mov     rcx, 0FFFFFFFF80000003h; hKey
0x18000ec1b  call    cs:__imp_RegOpenKeyExW
0x18000ec21  mov     ebx, 80070000h
0x18000ec26  test    eax, eax
0x18000ec28  jle     short loc_18000EC31
0x18000ec2a  movzx   eax, ax
0x18000ec2d  or      eax, ebx
0x18000ec2f  test    eax, eax
0x18000ec31  js      loc_18000EE43
0x18000ec37  xor     edx, edx
0x18000ec39  mov     [rbp+arg_8], rdi
0x18000ec3d  lea     rcx, [rbp+arg_8]
0x18000ec41  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x18000ec46  mov     rcx, [rbp+hKey]; hKey
0x18000ec4a  lea     rax, [rbp+arg_8]
0x18000ec4e  mov     [rsp+60h+lpdwDisposition], rdi; lpdwDisposition
0x18000ec53  lea     rdx, aSystemCurrentc; "System\\CurrentControlSet\\Control"
0x18000ec5a  mov     [rsp+60h+var_28], rax; phkResult
0x18000ec5f  xor     r9d, r9d; lpClass
0x18000ec62  mov     [rsp+60h+lpSecurityAttributes], rdi; lpSecurityAttributes
0x18000ec67  xor     r8d, r8d; Reserved
0x18000ec6a  mov     [rsp+60h+samDesired], 0F003Fh; samDesired
0x18000ec72  mov     dword ptr [rsp+60h+phkResult], edi; dwOptions
0x18000ec76  call    cs:__imp_RegCreateKeyExW
0x18000ec7c  lea     rcx, [rbp+arg_8]
0x18000ec80  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18000ec85  xor     edx, edx
0x18000ec87  mov     [rbp+arg_8], rdi
0x18000ec8b  lea     rcx, [rbp+arg_8]
0x18000ec8f  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x18000ec94  mov     rcx, [rbp+hKey]; hKey
0x18000ec98  lea     rax, [rbp+arg_8]
0x18000ec9c  mov     [rsp+60h+lpdwDisposition], rdi; lpdwDisposition
0x18000eca1  lea     rdx, aSoftwareMicros_17; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18000eca8  mov     [rsp+60h+var_28], rax; phkResult
0x18000ecad  xor     r9d, r9d; lpClass
0x18000ecb0  mov     [rsp+60h+lpSecurityAttributes], rdi; lpSecurityAttributes
0x18000ecb5  xor     r8d, r8d; Reserved
0x18000ecb8  mov     [rsp+60h+samDesired], 0F003Fh; samDesired
0x18000ecc0  mov     dword ptr [rsp+60h+phkResult], edi; dwOptions
0x18000ecc4  call    cs:__imp_RegCreateKeyExW
0x18000ecca  lea     rcx, [rbp+arg_8]
0x18000ecce  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18000ecd3  xor     edx, edx
0x18000ecd5  mov     dword ptr [rbp+arg_8], edi
0x18000ecd8  lea     rcx, [rbp+hKeyDest]
0x18000ecdc  mov     [rbp+hKeyDest], rdi
0x18000ece0  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x18000ece5  mov     rcx, [rbp+hKey]; hKey
0x18000ece9  lea     rax, [rbp+arg_8]
0x18000eced  mov     [rsp+60h+lpdwDisposition], rax; lpdwDisposition
0x18000ecf2  lea     rdx, aSoftwareMicros_12; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18000ecf9  lea     rax, [rbp+hKeyDest]
0x18000ecfd  xor     r9d, r9d; lpClass
0x18000ed00  mov     [rsp+60h+var_28], rax; phkResult
0x18000ed05  xor     r8d, r8d; Reserved
0x18000ed08  mov     [rsp+60h+lpSecurityAttributes], rdi; lpSecurityAttributes
0x18000ed0d  mov     [rsp+60h+samDesired], 0F003Fh; samDesired
0x18000ed15  mov     dword ptr [rsp+60h+phkResult], edi; dwOptions
0x18000ed19  call    cs:__imp_RegCreateKeyExW
0x18000ed1f  test    eax, eax
0x18000ed21  jle     short loc_18000ED2A
0x18000ed23  movzx   eax, ax
0x18000ed26  or      eax, ebx
0x18000ed28  test    eax, eax
0x18000ed2a  js      short loc_18000ED8D
0x18000ed2c  cmp     dword ptr [rbp+arg_8], 1
0x18000ed30  jnz     short loc_18000ED8D
0x18000ed32  xor     edx, edx
0x18000ed34  mov     [rbp+hKeySrc], rdi
0x18000ed38  lea     rcx, [rbp+hKeySrc]
0x18000ed3c  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x18000ed41  lea     rax, [rbp+hKeySrc]
0x18000ed45  mov     r9d, 20019h; samDesired
0x18000ed4b  xor     r8d, r8d; ulOptions
0x18000ed4e  mov     [rsp+60h+phkResult], rax; phkResult
0x18000ed53  lea     rdx, aSoftwareMicros_3; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18000ed5a  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000ed61  call    cs:__imp_RegOpenKeyExW
0x18000ed67  test    eax, eax
0x18000ed69  jle     short loc_18000ED72
0x18000ed6b  movzx   eax, ax
0x18000ed6e  or      eax, ebx
0x18000ed70  test    eax, eax
0x18000ed72  js      short loc_18000ED84
0x18000ed74  mov     r8, [rbp+hKeyDest]; hKeyDest
0x18000ed78  xor     edx, edx; lpSubKey
0x18000ed7a  mov     rcx, [rbp+hKeySrc]; hKeySrc
0x18000ed7e  call    cs:__imp_RegCopyTreeW
0x18000ed84  lea     rcx, [rbp+hKeySrc]
0x18000ed88  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18000ed8d  lea     rcx, [rbp+hKeyDest]
0x18000ed91  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18000ed96  xor     edx, edx
0x18000ed98  mov     dword ptr [rbp+arg_8], edi
0x18000ed9b  lea     rcx, [rbp+hKeySrc]
0x18000ed9f  mov     [rbp+hKeySrc], rdi
0x18000eda3  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x18000eda8  mov     rcx, [rbp+hKey]; hKey
0x18000edac  lea     rax, [rbp+arg_8]
0x18000edb0  mov     [rsp+60h+lpdwDisposition], rax; lpdwDisposition
0x18000edb5  lea     rdx, aEnvironment; "Environment"
0x18000edbc  lea     rax, [rbp+hKeySrc]
0x18000edc0  xor     r9d, r9d; lpClass
0x18000edc3  mov     [rsp+60h+var_28], rax; phkResult
0x18000edc8  xor     r8d, r8d; Reserved
0x18000edcb  mov     [rsp+60h+lpSecurityAttributes], rdi; lpSecurityAttributes
0x18000edd0  mov     [rsp+60h+samDesired], 0F003Fh; samDesired
0x18000edd8  mov     dword ptr [rsp+60h+phkResult], edi; dwOptions
0x18000eddc  call    cs:__imp_RegCreateKeyExW
0x18000ede2  test    eax, eax
0x18000ede4  jle     short loc_18000EDED
0x18000ede6  movzx   eax, ax
0x18000ede9  or      eax, ebx
0x18000edeb  test    eax, eax
0x18000eded  js      short loc_18000EE3A
0x18000edef  cmp     dword ptr [rbp+arg_8], 1
0x18000edf3  jnz     short loc_18000EE3A
0x18000edf5  mov     rcx, [rbp+hKeySrc]; HKEY
0x18000edf9  lea     r9, aUserprofileApp; "%USERPROFILE%\\AppData\\Local\\Temp"
0x18000ee00  lea     r8, String2; "TEMP"
0x18000ee07  call    ?SHRegSetExpandString@@YAJPEAUHKEY__@@PEBG11@Z; SHRegSetExpandString(HKEY__ *,ushort const *,ushort const *,ushort const *)
0x18000ee0c  mov     rcx, [rbp+hKeySrc]; HKEY
0x18000ee10  lea     r9, aUserprofileApp; "%USERPROFILE%\\AppData\\Local\\Temp"
0x18000ee17  lea     r8, aTmp; "TMP"
0x18000ee1e  call    ?SHRegSetExpandString@@YAJPEAUHKEY__@@PEBG11@Z; SHRegSetExpandString(HKEY__ *,ushort const *,ushort const *,ushort const *)
0x18000ee23  mov     rcx, [rbp+hKeySrc]; HKEY
0x18000ee27  lea     r9, aUserprofileApp_0; "%USERPROFILE%\\AppData\\Local\\Microsof"...
0x18000ee2e  lea     r8, aPath; "Path"
0x18000ee35  call    ?SHRegSetExpandString@@YAJPEAUHKEY__@@PEBG11@Z; SHRegSetExpandString(HKEY__ *,ushort const *,ushort const *,ushort const *)
0x18000ee3a  lea     rcx, [rbp+hKeySrc]
0x18000ee3e  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18000ee43  lea     rcx, [rbp+hKey]
0x18000ee47  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18000ee4c  add     rsp, 60h
0x18000ee50  pop     rdi
0x18000ee51  pop     rbx
0x18000ee52  pop     rbp
0x18000ee53  retn
```
