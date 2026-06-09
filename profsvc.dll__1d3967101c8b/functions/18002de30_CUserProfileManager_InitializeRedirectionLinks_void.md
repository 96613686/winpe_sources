# CUserProfileManager::InitializeRedirectionLinks(void)

- ea: `0x18002de30`
- end: `0x18002e0c6`
- name: `?InitializeRedirectionLinks@CUserProfileManager@@AEAAJXZ`
- size: `662`
- prototype: `__int64 __fastcall(CUserProfileManager *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180037c20`

## callees

- `0x1800111a0`
- `0x18001e070`
- `0x18001f060`
- `0x18002de30`
- `0x18002e648`
- `0x18003a730`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002dec1`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002df21`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002dec1`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002df21`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002df52`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002df66`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002e02a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002e069`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002e07e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002e08e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002df52`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002df66`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002e02a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002e069`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002e07e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002e08e`
- `api-ms-win-core-registry-l1-1-0!RegCopyTreeW` at `0x18002e016`
- `api-ms-win-core-registry-l1-1-0!RegCopyTreeW` at `0x18002e016`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18002dffe`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18002dffe`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18002dfa3`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18002dfa3`

## string_xrefs

- `0x18002dedb`: `onecore\ds\security\gina\profile\profsvc\profmgr.cpp`
- `0x18002df32`: `onecore\ds\security\gina\profile\profsvc\profmgr.cpp`
- `0x18002e04a`: `onecore\ds\security\gina\profile\profsvc\profmgr.cpp`

## pseudocode

```c
__int64 __fastcall CUserProfileManager::InitializeRedirectionLinks(CUserProfileManager *this)
{
  unsigned int v1; // eax
  unsigned int v2; // ebx
  unsigned int v3; // eax
  DWORD i; // ebx
  unsigned int v5; // eax
  __int64 v6; // rdx
  unsigned int phkResult; // [rsp+20h] [rbp-E0h]
  unsigned int phkResulta; // [rsp+20h] [rbp-E0h]
  unsigned int phkResultb; // [rsp+20h] [rbp-E0h]
  HKEY hKeySrc; // [rsp+50h] [rbp-B0h] BYREF
  HKEY hKey; // [rsp+58h] [rbp-A8h] BYREF
  HKEY hKeyDest; // [rsp+60h] [rbp-A0h] BYREF
  DWORD cchName; // [rsp+68h] [rbp-98h] BYREF
  DWORD dwDisposition; // [rsp+6Ch] [rbp-94h] BYREF
  LPCWSTR lpSubKey[4]; // [rsp+70h] [rbp-90h] BYREF
  WCHAR Name[264]; // [rsp+90h] [rbp-70h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2B8h] [rbp+1B8h]

  memset(lpSubKey, 0, 24);
  if ( (int)Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::Initialize(
              lpSubKey,
              -2147483646,
              L"System\\CurrentControlSet\\Control\\ProfileList",
              L"RedirectionKey") < 0 )
  {
LABEL_26:
    v2 = 0;
    goto LABEL_27;
  }
  hKeySrc = 0;
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
    &hKeySrc,
    0);
  v1 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, lpSubKey[0], 0, 0x20019u, &hKeySrc);
  if ( v1 == 2 )
  {
LABEL_24:
    if ( hKeySrc )
      RegCloseKey(hKeySrc);
    goto LABEL_26;
  }
  if ( !v1 )
  {
    hKey = 0;
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
      &hKey,
      0);
    v3 = RegOpenKeyExW(
           HKEY_LOCAL_MACHINE,
           L"Software\\Microsoft\\Windows NT\\CurrentVersion\\ProfileList",
           0,
           0xF003Fu,
           &hKey);
    if ( v3 )
    {
      v2 = wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)0xEA,
             (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\profmgr.cpp",
             (const char *)v3,
             phkResulta);
LABEL_7:
      if ( hKey )
        RegCloseKey(hKey);
      goto LABEL_9;
    }
    for ( i = 0; ; ++i )
    {
      Name[0] = 0;
      cchName = 260;
      if ( RegEnumKeyExW(hKeySrc, i, Name, &cchName, 0, 0, 0, 0) )
        break;
      dwDisposition = 0;
      hKeyDest = 0;
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
        &hKeyDest,
        0);
      v5 = RegCreateKeyExW(hKey, Name, 0, 0, 1u, 0xF003Fu, 0, &hKeyDest, &dwDisposition);
      if ( v5 )
      {
        v6 = 250;
LABEL_20:
        v2 = wil::details::in1diag3::Return_Win32(
               retaddr,
               (void *)v6,
               (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\profmgr.cpp",
               (const char *)v5,
               phkResultb);
        if ( hKeyDest )
          RegCloseKey(hKeyDest);
        goto LABEL_7;
      }
      v5 = RegCopyTreeW(hKeySrc, Name, hKeyDest);
      if ( v5 )
      {
        v6 = 253;
        goto LABEL_20;
      }
      if ( hKeyDest )
        RegCloseKey(hKeyDest);
    }
    if ( hKey )
      RegCloseKey(hKey);
    goto LABEL_24;
  }
  v2 = wil::details::in1diag3::Return_Win32(
         retaddr,
         (void *)0xE7,
         (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\profmgr.cpp",
         (const char *)v1,
         phkResult);
LABEL_9:
  if ( hKeySrc )
    RegCloseKey(hKeySrc);
LABEL_27:
  Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free((__int64)lpSubKey);
  return v2;
}

```

## disassembly

```asm
0x18002de30  mov     [rsp-8+arg_0], rbx
0x18002de35  mov     [rsp-8+arg_8], rdi
0x18002de3a  push    rbp
0x18002de3b  lea     rbp, [rsp-1B0h]
0x18002de43  sub     rsp, 2B0h
0x18002de4a  mov     rax, cs:__security_cookie
0x18002de51  xor     rax, rsp
0x18002de54  mov     [rbp+1B0h+var_10], rax
0x18002de5b  xor     edi, edi
0x18002de5d  lea     r9, aRedirectionkey; "RedirectionKey"
0x18002de64  mov     rbx, 0FFFFFFFF80000002h
0x18002de6b  mov     [rsp+2B0h+lpSubKey], rdi
0x18002de70  mov     rdx, rbx
0x18002de73  mov     [rsp+2B0h+var_238], rdi
0x18002de78  lea     r8, aSystemCurrentc_0; "System\\CurrentControlSet\\Control\\Pro"...
0x18002de7f  mov     [rbp+1B0h+var_230], rdi
0x18002de83  lea     rcx, [rsp+2B0h+lpSubKey]
0x18002de88  call    ?Initialize@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEAUHKEY__@@PEBG1@Z; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::Initialize(HKEY__ *,ushort const *,ushort const *)
0x18002de8d  test    eax, eax
0x18002de8f  js      loc_18002E094
0x18002de95  xor     edx, edx
0x18002de97  mov     [rsp+2B0h+hKeySrc], rdi
0x18002de9c  lea     rcx, [rsp+2B0h+hKeySrc]
0x18002dea1  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x18002dea6  mov     rdx, [rsp+2B0h+lpSubKey]; lpSubKey
0x18002deab  lea     rax, [rsp+2B0h+hKeySrc]
0x18002deb0  mov     r9d, 20019h; samDesired
0x18002deb6  mov     [rsp+2B0h+phkResult], rax; unsigned int
0x18002debb  xor     r8d, r8d; ulOptions
0x18002debe  mov     rcx, rbx; hKey
0x18002dec1  call    cs:__imp_RegOpenKeyExW
0x18002dec7  cmp     eax, 2
0x18002deca  jz      loc_18002E084
0x18002ded0  test    eax, eax
0x18002ded2  jz      short loc_18002DEF3
0x18002ded4  mov     rcx, [rbp+1B8h]; this
0x18002dedb  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\gina\\profile\\p"...
0x18002dee2  mov     r9d, eax; char *
0x18002dee5  mov     edx, 0E7h; void *
0x18002deea  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18002deef  mov     ebx, eax
0x18002def1  jmp     short loc_18002DF58
0x18002def3  xor     edx, edx
0x18002def5  mov     [rsp+2B0h+hKey], rdi
0x18002defa  lea     rcx, [rsp+2B0h+hKey]
0x18002deff  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x18002df04  lea     rax, [rsp+2B0h+hKey]
0x18002df09  mov     r9d, 0F003Fh; samDesired
0x18002df0f  xor     r8d, r8d; ulOptions
0x18002df12  mov     [rsp+2B0h+phkResult], rax; unsigned int
0x18002df17  lea     rdx, aSoftwareMicros_34; "Software\\Microsoft\\Windows NT\\Curren"...
0x18002df1e  mov     rcx, rbx; hKey
0x18002df21  call    cs:__imp_RegOpenKeyExW
0x18002df27  test    eax, eax
0x18002df29  jz      short loc_18002DF71
0x18002df2b  mov     rcx, [rbp+1B8h]; this
0x18002df32  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\gina\\profile\\p"...
0x18002df39  mov     r9d, eax; char *
0x18002df3c  mov     edx, 0EAh; void *
0x18002df41  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18002df46  mov     ebx, eax
0x18002df48  mov     rcx, [rsp+2B0h+hKey]; hKey
0x18002df4d  test    rcx, rcx
0x18002df50  jz      short loc_18002DF58
0x18002df52  call    cs:__imp_RegCloseKey
0x18002df58  mov     rcx, [rsp+2B0h+hKeySrc]; hKey
0x18002df5d  test    rcx, rcx
0x18002df60  jz      loc_18002E096
0x18002df66  call    cs:__imp_RegCloseKey
0x18002df6c  jmp     loc_18002E096
0x18002df71  mov     ebx, edi
0x18002df73  mov     rcx, [rsp+2B0h+hKeySrc]; hKey
0x18002df78  lea     r9, [rsp+2B0h+cchName]; lpcchName
0x18002df7d  mov     [rsp+2B0h+lpftLastWriteTime], rdi; lpftLastWriteTime
0x18002df82  lea     r8, [rbp+1B0h+Name]; lpName
0x18002df86  mov     [rsp+2B0h+lpcchClass], rdi; lpcchClass
0x18002df8b  mov     edx, ebx; dwIndex
0x18002df8d  mov     [rsp+2B0h+lpClass], rdi; lpClass
0x18002df92  mov     [rsp+2B0h+phkResult], rdi; lpReserved
0x18002df97  mov     [rbp+1B0h+Name], di
0x18002df9b  mov     [rsp+2B0h+cchName], 104h
0x18002dfa3  call    cs:__imp_RegEnumKeyExW
0x18002dfa9  test    eax, eax
0x18002dfab  jnz     loc_18002E074
0x18002dfb1  xor     edx, edx
0x18002dfb3  mov     [rsp+2B0h+dwDisposition], edi
0x18002dfb7  lea     rcx, [rsp+2B0h+hKeyDest]
0x18002dfbc  mov     [rsp+2B0h+hKeyDest], rdi
0x18002dfc1  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x18002dfc6  mov     rcx, [rsp+2B0h+hKey]; hKey
0x18002dfcb  lea     rax, [rsp+2B0h+dwDisposition]
0x18002dfd0  mov     [rsp+2B0h+lpdwDisposition], rax; lpdwDisposition
0x18002dfd5  lea     rdx, [rbp+1B0h+Name]; lpSubKey
0x18002dfd9  lea     rax, [rsp+2B0h+hKeyDest]
0x18002dfde  xor     r9d, r9d; lpClass
0x18002dfe1  mov     [rsp+2B0h+lpftLastWriteTime], rax; phkResult
0x18002dfe6  xor     r8d, r8d; Reserved
0x18002dfe9  mov     [rsp+2B0h+lpcchClass], rdi; lpSecurityAttributes
0x18002dfee  mov     dword ptr [rsp+2B0h+lpClass], 0F003Fh; samDesired
0x18002dff6  mov     dword ptr [rsp+2B0h+phkResult], 1; unsigned int
0x18002dffe  call    cs:__imp_RegCreateKeyExW
0x18002e004  test    eax, eax
0x18002e006  jnz     short loc_18002E03E
0x18002e008  mov     r8, [rsp+2B0h+hKeyDest]; hKeyDest
0x18002e00d  lea     rdx, [rbp+1B0h+Name]; lpSubKey
0x18002e011  mov     rcx, [rsp+2B0h+hKeySrc]; hKeySrc
0x18002e016  call    cs:__imp_RegCopyTreeW
0x18002e01c  test    eax, eax
0x18002e01e  jnz     short loc_18002E037
0x18002e020  mov     rcx, [rsp+2B0h+hKeyDest]; hKey
0x18002e025  test    rcx, rcx
0x18002e028  jz      short loc_18002E030
0x18002e02a  call    cs:__imp_RegCloseKey
0x18002e030  inc     ebx
0x18002e032  jmp     loc_18002DF73
0x18002e037  mov     edx, 0FDh
0x18002e03c  jmp     short loc_18002E043
0x18002e03e  mov     edx, 0FAh; void *
0x18002e043  mov     rcx, [rbp+1B8h]; this
0x18002e04a  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\gina\\profile\\p"...
0x18002e051  mov     r9d, eax; char *
0x18002e054  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18002e059  mov     rcx, [rsp+2B0h+hKeyDest]; hKey
0x18002e05e  mov     ebx, eax
0x18002e060  test    rcx, rcx
0x18002e063  jz      loc_18002DF48
0x18002e069  call    cs:__imp_RegCloseKey
0x18002e06f  jmp     loc_18002DF48
0x18002e074  mov     rcx, [rsp+2B0h+hKey]; hKey
0x18002e079  test    rcx, rcx
0x18002e07c  jz      short loc_18002E084
0x18002e07e  call    cs:__imp_RegCloseKey
0x18002e084  mov     rcx, [rsp+2B0h+hKeySrc]; hKey
0x18002e089  test    rcx, rcx
0x18002e08c  jz      short loc_18002E094
0x18002e08e  call    cs:__imp_RegCloseKey
0x18002e094  mov     ebx, edi
0x18002e096  lea     rcx, [rsp+2B0h+lpSubKey]
0x18002e09b  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x18002e0a0  mov     eax, ebx
0x18002e0a2  mov     rcx, [rbp+1B0h+var_10]
0x18002e0a9  xor     rcx, rsp; StackCookie
0x18002e0ac  call    __security_check_cookie
0x18002e0b1  lea     r11, [rsp+2B0h+var_s0]
0x18002e0b9  mov     rbx, [r11+10h]
0x18002e0bd  mov     rdi, [r11+18h]
0x18002e0c1  mov     rsp, r11
0x18002e0c4  pop     rbp
0x18002e0c5  retn
```
