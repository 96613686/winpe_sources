# CleanupProfiles(void)

- ea: `0x18002f4fc`
- end: `0x18002f730`
- name: `?CleanupProfiles@@YAJXZ`
- size: `564`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x18003ecb0`

## callees

- `0x1800111a0`
- `0x180015d00`
- `0x18001f060`
- `0x180021d00`
- `0x18002c630`
- `0x18002d2d8`
- `0x18002e648`
- `0x18002f4fc`
- `0x180034bfc`
- `0x18003a730`
- `0x18003edbc`
- `0x18003f42c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002f5c7`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002f5c7`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18002f645`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18002f645`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002f5fc`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002f6f8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002f5fc`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002f6f8`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18002f68f`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18002f68f`

## string_xrefs

- `0x18002f581`: `onecore\ds\security\gina\profile\profsvc\cleanup.cpp`
- `0x18002f5d6`: `onecore\ds\security\gina\profile\profsvc\cleanup.cpp`
- `0x18002f6d4`: `onecore\ds\security\gina\profile\profsvc\cleanup.cpp`

## pseudocode

```c
__int64 CleanupProfiles(void)
{
  __int64 result; // rax
  int UserProfileListRootKeyName; // eax
  unsigned int v2; // ebx
  unsigned int v3; // eax
  __int64 v4; // rdx
  DWORD v5; // ebx
  int v6; // eax
  int phkResult; // [rsp+20h] [rbp-E0h]
  unsigned int phkResulta; // [rsp+20h] [rbp-E0h]
  int phkResultb; // [rsp+20h] [rbp-E0h]
  HKEY hKey; // [rsp+60h] [rbp-A0h] BYREF
  DWORD cSubKeys; // [rsp+68h] [rbp-98h] BYREF
  DWORD cchName; // [rsp+6Ch] [rbp-94h] BYREF
  unsigned int v13; // [rsp+70h] [rbp-90h] BYREF
  LPCWSTR lpSubKey; // [rsp+78h] [rbp-88h] BYREF
  __int64 v15; // [rsp+80h] [rbp-80h]
  __int64 v16; // [rsp+88h] [rbp-78h]
  WCHAR Name[264]; // [rsp+90h] [rbp-70h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2B8h] [rbp+1B8h]

  v13 = 0;
  result = Profile::GetLocalSetting(9, &v13);
  if ( (int)result >= 0 )
  {
    lpSubKey = 0;
    v15 = 0;
    v16 = 0;
    Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(&lpSubKey);
    v15 = -1;
    v16 = -1;
    UserProfileListRootKeyName = GetUserProfileListRootKeyName((unsigned __int16 **)&lpSubKey, 0);
    v2 = UserProfileListRootKeyName;
    if ( UserProfileListRootKeyName >= 0 )
    {
      hKey = 0;
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
        &hKey,
        0);
      v3 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, lpSubKey, 0, 0x20019u, &hKey);
      if ( v3 )
      {
        v4 = 198;
      }
      else
      {
        cSubKeys = 0;
        v3 = RegQueryInfoKeyW(hKey, 0, 0, 0, &cSubKeys, 0, 0, 0, 0, 0, 0, 0);
        if ( !v3 )
        {
          cchName = 0;
          v5 = cSubKeys;
          while ( (--v5 & 0x80000000) == 0 )
          {
            cchName = 260;
            if ( !RegEnumKeyExW(hKey, v5, Name, &cchName, 0, 0, 0, 0)
              && !(unsigned int)IsServiceSid(Name)
              && !(unsigned int)IsVirtualServiceAccount(Name) )
            {
              v6 = _CleanupProfile(Name, hKey, v13);
              if ( v6 < 0 )
                wil::details::in1diag3::_Log_Hr(
                  retaddr,
                  (void *)0xD5,
                  (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\cleanup.cpp",
                  (const char *)(unsigned int)v6,
                  phkResultb);
            }
          }
          if ( hKey )
            RegCloseKey(hKey);
          v2 = 0;
          goto LABEL_20;
        }
        v4 = 202;
      }
      v2 = wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)v4,
             (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\cleanup.cpp",
             (const char *)v3,
             phkResulta);
      if ( hKey )
        RegCloseKey(hKey);
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xC3,
        (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\cleanup.cpp",
        (const char *)(unsigned int)UserProfileListRootKeyName,
        phkResult);
    }
LABEL_20:
    Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(&lpSubKey);
    return v2;
  }
  return result;
}

```

## disassembly

```asm
0x18002f4fc  mov     [rsp-8+arg_0], rbx
0x18002f501  mov     [rsp-8+arg_8], rdi
0x18002f506  push    rbp
0x18002f507  lea     rbp, [rsp-1B0h]
0x18002f50f  sub     rsp, 2B0h
0x18002f516  mov     rax, cs:__security_cookie
0x18002f51d  xor     rax, rsp
0x18002f520  mov     [rbp+1B0h+var_10], rax
0x18002f527  xor     edi, edi
0x18002f529  mov     [rsp+2B0h+var_240], edi
0x18002f52d  lea     rdx, [rsp+2B0h+var_240]
0x18002f532  lea     ecx, [rdi+9]
0x18002f535  call    ?GetLocalSetting@Profile@@YAJW4PROFILE_SETTING_ID@1@AEAKPEBGW4USERSTATE_SETTING_SOURCES@@@Z; Profile::GetLocalSetting(Profile::PROFILE_SETTING_ID,ulong &,ushort const *,USERSTATE_SETTING_SOURCES)
0x18002f53a  test    eax, eax
0x18002f53c  js      loc_18002F70C
0x18002f542  mov     [rsp+2B0h+lpSubKey], rdi
0x18002f547  mov     [rbp+1B0h+var_230], rdi
0x18002f54b  mov     [rbp+1B0h+var_228], rdi
0x18002f54f  lea     rcx, [rsp+2B0h+lpSubKey]
0x18002f554  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x18002f559  or      rax, 0FFFFFFFFFFFFFFFFh
0x18002f55d  mov     [rbp+1B0h+var_230], rax
0x18002f561  mov     [rbp+1B0h+var_228], rax
0x18002f565  xor     edx, edx; int *
0x18002f567  lea     rcx, [rsp+2B0h+lpSubKey]; unsigned __int16 **
0x18002f56c  call    ?GetUserProfileListRootKeyName@@YAJPEAPEAGPEAH@Z; GetUserProfileListRootKeyName(ushort * *,int *)
0x18002f571  mov     ebx, eax
0x18002f573  test    eax, eax
0x18002f575  jns     short loc_18002F597
0x18002f577  mov     rcx, [rbp+1B8h]; this
0x18002f57e  mov     r9d, eax; char *
0x18002f581  lea     r8, aOnecoreDsSecur_5; "onecore\\ds\\security\\gina\\profile\\p"...
0x18002f588  mov     edx, 0C3h; void *
0x18002f58d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002f592  jmp     loc_18002F700
0x18002f597  mov     [rsp+2B0h+hKey], rdi
0x18002f59c  xor     edx, edx
0x18002f59e  lea     rcx, [rsp+2B0h+hKey]
0x18002f5a3  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x18002f5a8  lea     rax, [rsp+2B0h+hKey]
0x18002f5ad  mov     [rsp+2B0h+phkResult], rax; unsigned int
0x18002f5b2  mov     r9d, 20019h; samDesired
0x18002f5b8  xor     r8d, r8d; ulOptions
0x18002f5bb  mov     rdx, [rsp+2B0h+lpSubKey]; lpSubKey
0x18002f5c0  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18002f5c7  call    cs:__imp_RegOpenKeyExW
0x18002f5cd  test    eax, eax
0x18002f5cf  jz      short loc_18002F607
0x18002f5d1  mov     edx, 0C6h; void *
0x18002f5d6  lea     r8, aOnecoreDsSecur_5; "onecore\\ds\\security\\gina\\profile\\p"...
0x18002f5dd  mov     r9d, eax; char *
0x18002f5e0  mov     rcx, [rbp+1B8h]; this
0x18002f5e7  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18002f5ec  mov     ebx, eax
0x18002f5ee  mov     rcx, [rsp+2B0h+hKey]; hKey
0x18002f5f3  test    rcx, rcx
0x18002f5f6  jz      loc_18002F700
0x18002f5fc  call    cs:__imp_RegCloseKey
0x18002f602  jmp     loc_18002F700
0x18002f607  mov     [rsp+2B0h+cSubKeys], edi
0x18002f60b  mov     [rsp+2B0h+lpftLastWriteTime], rdi; lpftLastWriteTime
0x18002f610  mov     [rsp+2B0h+lpcbSecurityDescriptor], rdi; lpcbSecurityDescriptor
0x18002f615  mov     [rsp+2B0h+lpcbMaxValueLen], rdi; lpcbMaxValueLen
0x18002f61a  mov     [rsp+2B0h+lpcbMaxValueNameLen], rdi; lpcbMaxValueNameLen
0x18002f61f  mov     [rsp+2B0h+lpcValues], rdi; lpcValues
0x18002f624  mov     [rsp+2B0h+lpcbMaxClassLen], rdi; lpcbMaxClassLen
0x18002f629  mov     [rsp+2B0h+lpcbMaxSubKeyLen], rdi; lpcbMaxSubKeyLen
0x18002f62e  lea     rax, [rsp+2B0h+cSubKeys]
0x18002f633  mov     [rsp+2B0h+phkResult], rax; lpcSubKeys
0x18002f638  xor     r9d, r9d; lpReserved
0x18002f63b  xor     r8d, r8d; lpcchClass
0x18002f63e  xor     edx, edx; lpClass
0x18002f640  mov     rcx, [rsp+2B0h+hKey]; hKey
0x18002f645  call    cs:__imp_RegQueryInfoKeyW
0x18002f64b  test    eax, eax
0x18002f64d  jz      short loc_18002F656
0x18002f64f  mov     edx, 0CAh
0x18002f654  jmp     short loc_18002F5D6
0x18002f656  mov     [rsp+2B0h+cchName], edi
0x18002f65a  mov     ebx, [rsp+2B0h+cSubKeys]
0x18002f65e  jmp     loc_18002F6E5
0x18002f663  mov     [rsp+2B0h+cchName], 104h
0x18002f66b  mov     [rsp+2B0h+lpcValues], rdi; lpftLastWriteTime
0x18002f670  mov     [rsp+2B0h+lpcbMaxClassLen], rdi; lpcchClass
0x18002f675  mov     [rsp+2B0h+lpcbMaxSubKeyLen], rdi; lpClass
0x18002f67a  mov     [rsp+2B0h+phkResult], rdi; int
0x18002f67f  lea     r9, [rsp+2B0h+cchName]; lpcchName
0x18002f684  lea     r8, [rbp+1B0h+Name]; lpName
0x18002f688  mov     edx, ebx; dwIndex
0x18002f68a  mov     rcx, [rsp+2B0h+hKey]; hKey
0x18002f68f  call    cs:__imp_RegEnumKeyExW
0x18002f695  test    eax, eax
0x18002f697  jnz     short loc_18002F6E5
0x18002f699  lea     rcx, [rbp+1B0h+Name]; lpString1
0x18002f69d  call    ?IsServiceSid@@YAHPEBG@Z; IsServiceSid(ushort const *)
0x18002f6a2  test    eax, eax
0x18002f6a4  jnz     short loc_18002F6E5
0x18002f6a6  lea     rcx, [rbp+1B0h+Name]; unsigned __int16 *
0x18002f6aa  call    ?IsVirtualServiceAccount@@YAHPEBG@Z; IsVirtualServiceAccount(ushort const *)
0x18002f6af  test    eax, eax
0x18002f6b1  jnz     short loc_18002F6E5
0x18002f6b3  mov     r8d, [rsp+2B0h+var_240]; unsigned int
0x18002f6b8  mov     rdx, [rsp+2B0h+hKey]; HKEY
0x18002f6bd  lea     rcx, [rbp+1B0h+Name]; unsigned __int16 *
0x18002f6c1  call    ?_CleanupProfile@@YAJPEBGPEAUHKEY__@@K@Z; _CleanupProfile(ushort const *,HKEY__ *,ulong)
0x18002f6c6  mov     rcx, [rbp+1B8h]; this
0x18002f6cd  test    eax, eax
0x18002f6cf  jns     short loc_18002F6E5
0x18002f6d1  mov     r9d, eax; char *
0x18002f6d4  lea     r8, aOnecoreDsSecur_5; "onecore\\ds\\security\\gina\\profile\\p"...
0x18002f6db  mov     edx, 0D5h; void *
0x18002f6e0  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18002f6e5  sub     ebx, 1
0x18002f6e8  jns     loc_18002F663
0x18002f6ee  mov     rcx, [rsp+2B0h+hKey]; hKey
0x18002f6f3  test    rcx, rcx
0x18002f6f6  jz      short loc_18002F6FE
0x18002f6f8  call    cs:__imp_RegCloseKey
0x18002f6fe  mov     ebx, edi
0x18002f700  lea     rcx, [rsp+2B0h+lpSubKey]
0x18002f705  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x18002f70a  mov     eax, ebx
0x18002f70c  mov     rcx, [rbp+1B0h+var_10]
0x18002f713  xor     rcx, rsp; StackCookie
0x18002f716  call    __security_check_cookie
0x18002f71b  lea     r11, [rsp+2B0h+var_s0]
0x18002f723  mov     rbx, [r11+10h]
0x18002f727  mov     rdi, [r11+18h]
0x18002f72b  mov     rsp, r11
0x18002f72e  pop     rbp
0x18002f72f  retn
```
