# CleanupProfiles(void)

- ea: `0x18003797c`
- end: `0x180037bb3`
- name: `?CleanupProfiles@@YAJXZ`
- size: `567`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x1800403e0`

## callees

- `0x18000e1a0`
- `0x1800130d0`
- `0x180013770`
- `0x180019ab0`
- `0x180024d10`
- `0x180030ad0`
- `0x180031060`
- `0x18003533c`
- `0x18003797c`
- `0x180037bbc`
- `0x18003bc70`
- `0x180040510`
- `0x180040bcc`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180037a47`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180037a47`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180037ac1`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180037ac1`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180037b11`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180037b11`

## string_xrefs

- `0x180037a01`: `onecore\ds\security\gina\profile\profsvc\cleanup.cpp`
- `0x180037a5c`: `onecore\ds\security\gina\profile\profsvc\cleanup.cpp`
- `0x180037b5c`: `onecore\ds\security\gina\profile\profsvc\cleanup.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
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
              && !IsServiceSid(Name)
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
          wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
          v2 = 0;
          goto LABEL_17;
        }
        v4 = 202;
      }
      v2 = wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)v4,
             (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\cleanup.cpp",
             (const char *)v3,
             phkResulta);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
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
LABEL_17:
    Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(&lpSubKey);
    return v2;
  }
  return result;
}

```

## disassembly

```asm
0x18003797c  mov     [rsp-8+arg_0], rbx
0x180037981  mov     [rsp-8+arg_8], rdi
0x180037986  push    rbp
0x180037987  lea     rbp, [rsp-1B0h]
0x18003798f  sub     rsp, 2B0h
0x180037996  mov     rax, cs:__security_cookie
0x18003799d  xor     rax, rsp
0x1800379a0  mov     [rbp+1B0h+var_10], rax
0x1800379a7  xor     edi, edi
0x1800379a9  mov     [rsp+2B0h+var_240], edi
0x1800379ad  lea     rdx, [rsp+2B0h+var_240]
0x1800379b2  lea     ecx, [rdi+9]
0x1800379b5  call    ?GetLocalSetting@Profile@@YAJW4PROFILE_SETTING_ID@1@AEAKPEBGW4USERSTATE_SETTING_SOURCES@@@Z; Profile::GetLocalSetting(Profile::PROFILE_SETTING_ID,ulong &,ushort const *,USERSTATE_SETTING_SOURCES)
0x1800379ba  test    eax, eax
0x1800379bc  js      loc_180037B8E
0x1800379c2  mov     [rsp+2B0h+lpSubKey], rdi
0x1800379c7  mov     [rbp+1B0h+var_230], rdi
0x1800379cb  mov     [rbp+1B0h+var_228], rdi
0x1800379cf  lea     rcx, [rsp+2B0h+lpSubKey]
0x1800379d4  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x1800379d9  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800379dd  mov     [rbp+1B0h+var_230], rax
0x1800379e1  mov     [rbp+1B0h+var_228], rax
0x1800379e5  xor     edx, edx; int *
0x1800379e7  lea     rcx, [rsp+2B0h+lpSubKey]; unsigned __int16 **
0x1800379ec  call    ?GetUserProfileListRootKeyName@@YAJPEAPEAGPEAH@Z; GetUserProfileListRootKeyName(ushort * *,int *)
0x1800379f1  mov     ebx, eax
0x1800379f3  test    eax, eax
0x1800379f5  jns     short loc_180037A17
0x1800379f7  mov     rcx, [rbp+1B8h]; this
0x1800379fe  mov     r9d, eax; char *
0x180037a01  lea     r8, aOnecoreDsSecur_5; "onecore\\ds\\security\\gina\\profile\\p"...
0x180037a08  mov     edx, 0C3h; void *
0x180037a0d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180037a12  jmp     loc_180037B82
0x180037a17  mov     [rsp+2B0h+hKey], rdi
0x180037a1c  xor     edx, edx
0x180037a1e  lea     rcx, [rsp+2B0h+hKey]
0x180037a23  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x180037a28  lea     rax, [rsp+2B0h+hKey]
0x180037a2d  mov     [rsp+2B0h+phkResult], rax; unsigned int
0x180037a32  mov     r9d, 20019h; samDesired
0x180037a38  xor     r8d, r8d; ulOptions
0x180037a3b  mov     rdx, [rsp+2B0h+lpSubKey]; lpSubKey
0x180037a40  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180037a47  call    cs:__imp_RegOpenKeyExW
0x180037a4e  nop     dword ptr [rax+rax+00h]
0x180037a53  test    eax, eax
0x180037a55  jz      short loc_180037A83
0x180037a57  mov     edx, 0C6h; void *
0x180037a5c  lea     r8, aOnecoreDsSecur_5; "onecore\\ds\\security\\gina\\profile\\p"...
0x180037a63  mov     r9d, eax; char *
0x180037a66  mov     rcx, [rbp+1B8h]; this
0x180037a6d  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180037a72  mov     ebx, eax
0x180037a74  lea     rcx, [rsp+2B0h+hKey]
0x180037a79  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180037a7e  jmp     loc_180037B82
0x180037a83  mov     [rsp+2B0h+cSubKeys], edi
0x180037a87  mov     [rsp+2B0h+lpftLastWriteTime], rdi; lpftLastWriteTime
0x180037a8c  mov     [rsp+2B0h+lpcbSecurityDescriptor], rdi; lpcbSecurityDescriptor
0x180037a91  mov     [rsp+2B0h+lpcbMaxValueLen], rdi; lpcbMaxValueLen
0x180037a96  mov     [rsp+2B0h+lpcbMaxValueNameLen], rdi; lpcbMaxValueNameLen
0x180037a9b  mov     [rsp+2B0h+lpcValues], rdi; lpcValues
0x180037aa0  mov     [rsp+2B0h+lpcbMaxClassLen], rdi; lpcbMaxClassLen
0x180037aa5  mov     [rsp+2B0h+lpcbMaxSubKeyLen], rdi; lpcbMaxSubKeyLen
0x180037aaa  lea     rax, [rsp+2B0h+cSubKeys]
0x180037aaf  mov     [rsp+2B0h+phkResult], rax; lpcSubKeys
0x180037ab4  xor     r9d, r9d; lpReserved
0x180037ab7  xor     r8d, r8d; lpcchClass
0x180037aba  xor     edx, edx; lpClass
0x180037abc  mov     rcx, [rsp+2B0h+hKey]; hKey
0x180037ac1  call    cs:__imp_RegQueryInfoKeyW
0x180037ac8  nop     dword ptr [rax+rax+00h]
0x180037acd  test    eax, eax
0x180037acf  jz      short loc_180037AD8
0x180037ad1  mov     edx, 0CAh
0x180037ad6  jmp     short loc_180037A5C
0x180037ad8  mov     [rsp+2B0h+cchName], edi
0x180037adc  mov     ebx, [rsp+2B0h+cSubKeys]
0x180037ae0  jmp     loc_180037B6D
0x180037ae5  mov     [rsp+2B0h+cchName], 104h
0x180037aed  mov     [rsp+2B0h+lpcValues], rdi; lpftLastWriteTime
0x180037af2  mov     [rsp+2B0h+lpcbMaxClassLen], rdi; lpcchClass
0x180037af7  mov     [rsp+2B0h+lpcbMaxSubKeyLen], rdi; lpClass
0x180037afc  mov     [rsp+2B0h+phkResult], rdi; int
0x180037b01  lea     r9, [rsp+2B0h+cchName]; lpcchName
0x180037b06  lea     r8, [rbp+1B0h+Name]; lpName
0x180037b0a  mov     edx, ebx; dwIndex
0x180037b0c  mov     rcx, [rsp+2B0h+hKey]; hKey
0x180037b11  call    cs:__imp_RegEnumKeyExW
0x180037b18  nop     dword ptr [rax+rax+00h]
0x180037b1d  test    eax, eax
0x180037b1f  jnz     short loc_180037B6D
0x180037b21  lea     rcx, [rbp+1B0h+Name]; lpString1
0x180037b25  call    ?IsServiceSid@@YAHPEBG@Z; IsServiceSid(ushort const *)
0x180037b2a  test    eax, eax
0x180037b2c  jnz     short loc_180037B6D
0x180037b2e  lea     rcx, [rbp+1B0h+Name]; unsigned __int16 *
0x180037b32  call    ?IsVirtualServiceAccount@@YAHPEBG@Z; IsVirtualServiceAccount(ushort const *)
0x180037b37  test    eax, eax
0x180037b39  jnz     short loc_180037B6D
0x180037b3b  mov     r8d, [rsp+2B0h+var_240]; unsigned int
0x180037b40  mov     rdx, [rsp+2B0h+hKey]; HKEY
0x180037b45  lea     rcx, [rbp+1B0h+Name]; unsigned __int16 *
0x180037b49  call    ?_CleanupProfile@@YAJPEBGPEAUHKEY__@@K@Z; _CleanupProfile(ushort const *,HKEY__ *,ulong)
0x180037b4e  mov     rcx, [rbp+1B8h]; this
0x180037b55  test    eax, eax
0x180037b57  jns     short loc_180037B6D
0x180037b59  mov     r9d, eax; char *
0x180037b5c  lea     r8, aOnecoreDsSecur_5; "onecore\\ds\\security\\gina\\profile\\p"...
0x180037b63  mov     edx, 0D5h; void *
0x180037b68  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180037b6d  sub     ebx, 1
0x180037b70  jns     loc_180037AE5
0x180037b76  lea     rcx, [rsp+2B0h+hKey]
0x180037b7b  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180037b80  mov     ebx, edi
0x180037b82  lea     rcx, [rsp+2B0h+lpSubKey]
0x180037b87  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x180037b8c  mov     eax, ebx
0x180037b8e  mov     rcx, [rbp+1B0h+var_10]
0x180037b95  xor     rcx, rsp; StackCookie
0x180037b98  call    __security_check_cookie
0x180037b9d  lea     r11, [rsp+2B0h+var_s0]
0x180037ba5  mov     rbx, [r11+10h]
0x180037ba9  mov     rdi, [r11+18h]
0x180037bad  mov     rsp, r11
0x180037bb0  pop     rbp
0x180037bb1  retn
```
