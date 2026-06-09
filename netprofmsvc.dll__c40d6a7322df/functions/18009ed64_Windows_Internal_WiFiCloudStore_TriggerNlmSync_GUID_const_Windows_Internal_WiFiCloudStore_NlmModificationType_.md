# Windows::Internal::WiFiCloudStore::TriggerNlmSync(_GUID const &,Windows::Internal::WiFiCloudStore::NlmModificationType,bool)

- ea: `0x18009ed64`
- end: `0x18009f0ea`
- name: `?TriggerNlmSync@WiFiCloudStore@Internal@Windows@@YAXAEBU_GUID@@W4NlmModificationType@123@_N@Z`
- size: `902`
- prototype: ``
- caller_count: `2`
- callee_count: `15`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180128f9c`
- `0x180128fc4`

## callees

- `0x180013748`
- `0x180015608`
- `0x18003b250`
- `0x18004068c`
- `0x180042a7c`
- `0x18009ed64`
- `0x18009f0f0`
- `0x18009f1b8`
- `0x18009f2e0`
- `0x18009f3b0`
- `0x18009f558`
- `0x18009f5e8`
- `0x18009f630`
- `0x1800a88a0`
- `0x1800a9738`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18009efbf`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18009efbf`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18009eeae`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18009eeae`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18009ee3d`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18009ee3d`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18009f00c`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18009f00c`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18009ef57`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18009ef57`

## string_xrefs

- `0x18009edb4`: `onecore\net\wificloudstore\registry\lib\nlmcdsproducerreg.cpp`
- `0x18009ee52`: `onecore\net\wificloudstore\registry\lib\nlmcdsproducerreg.cpp`
- `0x18009eec3`: `onecore\net\wificloudstore\registry\lib\nlmcdsproducerreg.cpp`
- `0x18009ef6c`: `onecore\net\wificloudstore\registry\lib\nlmcdsproducerreg.cpp`
- `0x18009efcf`: `onecore\net\wificloudstore\registry\lib\nlmcdsproducerreg.cpp`
- `0x18009f021`: `onecore\net\wificloudstore\registry\lib\nlmcdsproducerreg.cpp`
- `0x18009f08b`: `onecore\net\wificloudstore\registry\lib\nlmcdsproducerreg.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall Windows::Internal::WiFiCloudStore::TriggerNlmSync(const GUID *a1, bool *a2)
{
  const GUID *v2; // r14
  __int64 result; // rax
  const WCHAR *v4; // rdx
  unsigned int v5; // eax
  unsigned int v6; // eax
  char v7; // si
  DWORD i; // edi
  unsigned int v9; // eax
  unsigned int v10; // eax
  const char *v11; // r9
  int v12; // eax
  int dwOptions; // [rsp+20h] [rbp-138h]
  unsigned int dwOptionsa; // [rsp+20h] [rbp-138h]
  unsigned int dwOptionsb; // [rsp+20h] [rbp-138h]
  unsigned int dwOptionsc; // [rsp+20h] [rbp-138h]
  char v17[4]; // [rsp+60h] [rbp-F8h] BYREF
  DWORD cbMaxSubKeyLen; // [rsp+64h] [rbp-F4h] BYREF
  DWORD cSubKeys; // [rsp+68h] [rbp-F0h] BYREF
  BYTE Data[8]; // [rsp+70h] [rbp-E8h] BYREF
  DWORD v21; // [rsp+78h] [rbp-E0h]
  HKEY hKey; // [rsp+80h] [rbp-D8h] BYREF
  DWORD cchName; // [rsp+88h] [rbp-D0h] BYREF
  HKEY v24; // [rsp+90h] [rbp-C8h] BYREF
  LPWSTR lpName[2]; // [rsp+98h] [rbp-C0h] BYREF
  __int64 v26; // [rsp+A8h] [rbp-B0h]
  const GUID *v27; // [rsp+B0h] [rbp-A8h]
  LPCWSTR lpSubKey[5]; // [rsp+B8h] [rbp-A0h] BYREF
  OLECHAR sz[40]; // [rsp+E0h] [rbp-78h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+158h] [rbp+0h]

  v2 = a1;
  v27 = a1;
  *(_DWORD *)Data = (_DWORD)a2;
  v17[0] = 0;
  result = Windows::Internal::WiFiCloudStore::IsWiFiCloudStoreFeaturePresent(
             (Windows::Internal::WiFiCloudStore *)v17,
             a2);
  if ( (int)result < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xE,
      (unsigned int)"onecore\\net\\wificloudstore\\registry\\lib\\nlmcdsproducerreg.cpp",
      (const char *)(unsigned int)result,
      dwOptions);
  if ( v17[0] )
  {
    Windows::Internal::WiFiCloudStore::GetMutableCDSRegistryKey(lpSubKey);
    hKey = 0;
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
      &hKey,
      0);
    v4 = (const WCHAR *)lpSubKey;
    if ( lpSubKey[3] > (LPCWSTR)7 )
      v4 = lpSubKey[0];
    v5 = RegCreateKeyExW(HKEY_LOCAL_MACHINE, v4, 0, 0, 0, 0xFu, 0, &hKey, 0);
    if ( v5 )
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0x1A,
        (unsigned int)"onecore\\net\\wificloudstore\\registry\\lib\\nlmcdsproducerreg.cpp",
        (const char *)v5,
        dwOptionsa);
    cSubKeys = 0;
    cbMaxSubKeyLen = 0;
    v6 = RegQueryInfoKeyW(hKey, 0, 0, 0, &cSubKeys, &cbMaxSubKeyLen, 0, 0, 0, 0, 0, 0);
    if ( v6 )
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0x1F,
        (unsigned int)"onecore\\net\\wificloudstore\\registry\\lib\\nlmcdsproducerreg.cpp",
        (const char *)v6,
        dwOptionsb);
    v7 = 0;
    v17[0] = 0;
    *(_OWORD *)lpName = 0;
    v26 = 0;
    std::vector<unsigned short>::_Construct_n<>(lpName, cbMaxSubKeyLen + 1);
    for ( i = 0; ; ++i )
    {
      v21 = i;
      if ( i >= cSubKeys )
        break;
      cchName = lpName[1] - lpName[0];
      v9 = RegEnumKeyExW(hKey, i, lpName[0], &cchName, 0, 0, 0, 0);
      try
      {
        if ( v9 )
          wil::details::in1diag3::Throw_Win32(
            retaddr,
            (void *)0x2A,
            (unsigned int)"onecore\\net\\wificloudstore\\registry\\lib\\nlmcdsproducerreg.cpp",
            (const char *)v9,
            dwOptionsc);
        Windows::Internal::WiFiCloudStore::OpenNlmSyncRegistryKeyForUser(&v24);
        memset_0(sz, 0, 0x4Eu);
        if ( !StringFromGUID2(v2, sz, 39) )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x30,
            (unsigned int)"onecore\\net\\wificloudstore\\registry\\lib\\nlmcdsproducerreg.cpp",
            (const char *)0x8007007ALL,
            dwOptionsc);
        v10 = RegSetValueExW(v24, sz, 0, 3u, Data, 4u);
        if ( v10 )
          wil::details::in1diag3::Throw_Win32(
            retaddr,
            (void *)0x33,
            (unsigned int)"onecore\\net\\wificloudstore\\registry\\lib\\nlmcdsproducerreg.cpp",
            (const char *)v10,
            dwOptionsb);
        v7 = 1;
        v17[0] = 1;
        WiFiCloudStoreTelemetry::NlmStoredNeededChange<_GUID const &,enum Windows::Internal::WiFiCloudStore::NlmModificationType const &>(
          v2,
          Data);
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v24);
      }
      catch ( ... )
      {
        wil::details::in1diag3::Log_CaughtException(
          retaddr,
          (void *)0x38,
          (unsigned int)"onecore\\net\\wificloudstore\\registry\\lib\\nlmcdsproducerreg.cpp",
          v11);
        v7 = v17[0];
        i = v21;
        v2 = v27;
        continue;
      }
    }
    if ( v7 )
    {
      v12 = Windows::Internal::WiFiCloudStore::TriggerTaskWithDelay();
      if ( v12 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x3D,
          (unsigned int)"onecore\\net\\wificloudstore\\registry\\lib\\nlmcdsproducerreg.cpp",
          (const char *)(unsigned int)v12,
          dwOptionsb);
    }
    std::vector<unsigned short>::_Tidy(lpName);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
    return std::wstring::~wstring(lpSubKey);
  }
  return result;
}

```

## disassembly

```asm
0x18009ed64  mov     [rsp+arg_10], rbx
0x18009ed69  push    rsi
0x18009ed6a  push    rdi
0x18009ed6b  push    r14
0x18009ed6d  sub     rsp, 140h
0x18009ed74  mov     rax, cs:__security_cookie
0x18009ed7b  xor     rax, rsp
0x18009ed7e  mov     [rsp+158h+var_28], rax
0x18009ed86  mov     r14, rcx
0x18009ed89  mov     [rsp+158h+var_A8], rcx
0x18009ed91  mov     dword ptr [rsp+158h+Data], edx
0x18009ed95  xor     ebx, ebx
0x18009ed97  mov     [rsp+158h+var_F8], bl
0x18009ed9b  lea     rcx, [rsp+158h+var_F8]; this
0x18009eda0  call    ?IsWiFiCloudStoreFeaturePresent@WiFiCloudStore@Internal@Windows@@YAJPEA_N@Z; Windows::Internal::WiFiCloudStore::IsWiFiCloudStoreFeaturePresent(bool *)
0x18009eda5  mov     rcx, [rsp+158h]; this
0x18009edad  test    eax, eax
0x18009edaf  jns     short loc_18009EDC4
0x18009edb1  mov     r9d, eax; char *
0x18009edb4  lea     r8, aOnecoreNetWifi_1; "onecore\\net\\wificloudstore\\registry"...
0x18009edbb  lea     edx, [rbx+0Eh]; void *
0x18009edbe  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18009edc4  cmp     [rsp+158h+var_F8], bl
0x18009edc8  jz      loc_18009F0C6
0x18009edce  lea     rcx, [rsp+158h+lpSubKey]
0x18009edd6  call    ?GetMutableCDSRegistryKey@WiFiCloudStore@Internal@Windows@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; Windows::Internal::WiFiCloudStore::GetMutableCDSRegistryKey(void)
0x18009eddb  nop
0x18009eddc  mov     [rsp+158h+hKey], rbx
0x18009ede4  xor     edx, edx
0x18009ede6  lea     rcx, [rsp+158h+hKey]
0x18009edee  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x18009edf3  lea     rdx, [rsp+158h+lpSubKey]
0x18009edfb  cmp     [rsp+158h+var_88], 7
0x18009ee04  cmova   rdx, [rsp+158h+lpSubKey]; lpSubKey
0x18009ee0d  mov     [rsp+158h+lpdwDisposition], rbx; lpdwDisposition
0x18009ee12  lea     rax, [rsp+158h+hKey]
0x18009ee1a  mov     [rsp+158h+phkResult], rax; phkResult
0x18009ee1f  mov     [rsp+158h+lpSecurityAttributes], rbx; lpSecurityAttributes
0x18009ee24  mov     [rsp+158h+samDesired], 0Fh; samDesired
0x18009ee2c  mov     [rsp+158h+dwOptions], ebx; unsigned int
0x18009ee30  xor     r9d, r9d; lpClass
0x18009ee33  xor     r8d, r8d; Reserved
0x18009ee36  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18009ee3d  call    cs:__imp_RegCreateKeyExW
0x18009ee43  mov     rcx, [rsp+158h]; this
0x18009ee4b  test    eax, eax
0x18009ee4d  jz      short loc_18009EE64
0x18009ee4f  mov     r9d, eax; char *
0x18009ee52  lea     r8, aOnecoreNetWifi_1; "onecore\\net\\wificloudstore\\registry"...
0x18009ee59  mov     edx, 1Ah; void *
0x18009ee5e  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x18009ee64  mov     [rsp+158h+cSubKeys], ebx
0x18009ee68  mov     [rsp+158h+cbMaxSubKeyLen], ebx
0x18009ee6c  mov     [rsp+158h+lpftLastWriteTime], rbx; lpftLastWriteTime
0x18009ee71  mov     [rsp+158h+lpcbSecurityDescriptor], rbx; lpcbSecurityDescriptor
0x18009ee76  mov     [rsp+158h+lpcbMaxValueLen], rbx; lpcbMaxValueLen
0x18009ee7b  mov     [rsp+158h+lpdwDisposition], rbx; lpcbMaxValueNameLen
0x18009ee80  mov     [rsp+158h+phkResult], rbx; lpcValues
0x18009ee85  mov     [rsp+158h+lpSecurityAttributes], rbx; lpcbMaxClassLen
0x18009ee8a  lea     rax, [rsp+158h+cbMaxSubKeyLen]
0x18009ee8f  mov     qword ptr [rsp+158h+samDesired], rax; lpcbMaxSubKeyLen
0x18009ee94  lea     rax, [rsp+158h+cSubKeys]
0x18009ee99  mov     qword ptr [rsp+158h+dwOptions], rax; int
0x18009ee9e  xor     r9d, r9d; lpReserved
0x18009eea1  xor     r8d, r8d; lpcchClass
0x18009eea4  xor     edx, edx; lpClass
0x18009eea6  mov     rcx, [rsp+158h+hKey]; hKey
0x18009eeae  call    cs:__imp_RegQueryInfoKeyW
0x18009eeb4  mov     rcx, [rsp+158h]; this
0x18009eebc  test    eax, eax
0x18009eebe  jz      short loc_18009EED5
0x18009eec0  mov     r9d, eax; char *
0x18009eec3  lea     r8, aOnecoreNetWifi_1; "onecore\\net\\wificloudstore\\registry"...
0x18009eeca  mov     edx, 1Fh; void *
0x18009eecf  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x18009eed5  mov     sil, bl
0x18009eed8  mov     [rsp+158h+var_F8], bl
0x18009eedc  xorps   xmm0, xmm0
0x18009eedf  movdqu  xmmword ptr [rsp+158h+lpName], xmm0
0x18009eee8  mov     [rsp+158h+var_B0], rbx
0x18009eef0  mov     edx, [rsp+158h+cbMaxSubKeyLen]
0x18009eef4  inc     edx
0x18009eef6  lea     rcx, [rsp+158h+lpName]
0x18009eefe  call    ??$_Construct_n@$$V@?$vector@GV?$allocator@G@std@@@std@@AEAAX_K@Z; std::vector<ushort>::_Construct_n<>(unsigned __int64)
0x18009ef03  nop
0x18009ef04  mov     edi, ebx
0x18009ef06  mov     [rsp+158h+var_E0], edi
0x18009ef0a  cmp     edi, [rsp+158h+cSubKeys]
0x18009ef0e  jnb     loc_18009F072
0x18009ef14  mov     r8, [rsp+158h+lpName]; lpName
0x18009ef1c  mov     rax, [rsp+158h+lpName+8]
0x18009ef24  sub     rax, r8
0x18009ef27  sar     rax, 1
0x18009ef2a  mov     [rsp+158h+cchName], eax
0x18009ef31  mov     [rsp+158h+phkResult], rbx; lpftLastWriteTime
0x18009ef36  mov     [rsp+158h+lpSecurityAttributes], rbx; lpcchClass
0x18009ef3b  mov     qword ptr [rsp+158h+samDesired], rbx; lpClass
0x18009ef40  mov     qword ptr [rsp+158h+dwOptions], rbx; int
0x18009ef45  lea     r9, [rsp+158h+cchName]; lpcchName
0x18009ef4d  mov     edx, edi; dwIndex
0x18009ef4f  mov     rcx, [rsp+158h+hKey]; hKey
0x18009ef57  call    cs:__imp_RegEnumKeyExW
0x18009ef5d  mov     rcx, [rsp+158h]; this
0x18009ef65  test    eax, eax
0x18009ef67  jz      short loc_18009EF7D
0x18009ef69  mov     r9d, eax; char *
0x18009ef6c  lea     r8, aOnecoreNetWifi_1; "onecore\\net\\wificloudstore\\registry"...
0x18009ef73  mov     edx, 2Ah ; '*'; void *
0x18009ef78  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x18009ef7d  mov     r8, [rsp+158h+lpName]
0x18009ef85  lea     rcx, [rsp+158h+var_C8]; phkResult
0x18009ef8d  call    ?OpenNlmSyncRegistryKeyForUser@WiFiCloudStore@Internal@Windows@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@W4ProfileGeneration@123@PEBG@Z; Windows::Internal::WiFiCloudStore::OpenNlmSyncRegistryKeyForUser(Windows::Internal::WiFiCloudStore::ProfileGeneration,ushort const *)
0x18009ef92  nop
0x18009ef93  xor     edx, edx; Val
0x18009ef95  lea     r8d, [rdx+4Eh]; Size
0x18009ef99  lea     rcx, [rsp+158h+sz]; void *
0x18009efa1  call    memset_0
0x18009efa6  mov     rsi, [rsp+158h]
0x18009efae  mov     r8d, 27h ; '''; cchMax
0x18009efb4  lea     rdx, [rsp+158h+sz]; lpsz
0x18009efbc  mov     rcx, r14; rguid
0x18009efbf  call    cs:__imp_StringFromGUID2
0x18009efc5  test    eax, eax
0x18009efc7  jnz     short loc_18009EFE1
0x18009efc9  mov     r9d, 8007007Ah; char *
0x18009efcf  lea     r8, aOnecoreNetWifi_1; "onecore\\net\\wificloudstore\\registry"...
0x18009efd6  lea     edx, [rax+30h]; void *
0x18009efd9  mov     rcx, rsi; this
0x18009efdc  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18009efe1  mov     [rsp+158h+samDesired], 4; cbData
0x18009efe9  lea     rax, [rsp+158h+Data]
0x18009efee  mov     qword ptr [rsp+158h+dwOptions], rax; unsigned int
0x18009eff3  mov     r9d, 3; dwType
0x18009eff9  xor     r8d, r8d; Reserved
0x18009effc  lea     rdx, [rsp+158h+sz]; lpValueName
0x18009f004  mov     rcx, [rsp+158h+var_C8]; hKey
0x18009f00c  call    cs:__imp_RegSetValueExW
0x18009f012  mov     rcx, [rsp+158h]; this
0x18009f01a  test    eax, eax
0x18009f01c  jz      short loc_18009F032
0x18009f01e  mov     r9d, eax; char *
0x18009f021  lea     r8, aOnecoreNetWifi_1; "onecore\\net\\wificloudstore\\registry"...
0x18009f028  mov     edx, 33h ; '3'; void *
0x18009f02d  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x18009f032  mov     sil, 1
0x18009f035  mov     [rsp+158h+var_F8], sil
0x18009f03a  lea     rdx, [rsp+158h+Data]
0x18009f03f  mov     rcx, r14
0x18009f042  call    ??$NlmStoredNeededChange@AEBU_GUID@@AEBW4NlmModificationType@WiFiCloudStore@Internal@Windows@@@WiFiCloudStoreTelemetry@@SAXAEBU_GUID@@AEBW4NlmModificationType@WiFiCloudStore@Internal@Windows@@@Z; WiFiCloudStoreTelemetry::NlmStoredNeededChange<_GUID const &,Windows::Internal::WiFiCloudStore::NlmModificationType const &>(_GUID const &,Windows::Internal::WiFiCloudStore::NlmModificationType const &)
0x18009f047  nop
0x18009f048  lea     rcx, [rsp+158h+var_C8]
0x18009f050  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18009f055  nop
0x18009f056  jmp     short loc_18009F06B
0x18009f058  xor     ebx, ebx
0x18009f05a  mov     sil, [rsp+158h+var_F8]
0x18009f05f  mov     edi, [rsp+158h+var_E0]
0x18009f063  mov     r14, [rsp+158h+var_A8]
0x18009f06b  inc     edi
0x18009f06d  jmp     loc_18009EF06
0x18009f072  test    sil, sil
0x18009f075  jz      short loc_18009F09D
0x18009f077  call    ?TriggerTaskWithDelay@WiFiCloudStore@Internal@Windows@@YAJW4TaskTrigger@123@@Z; Windows::Internal::WiFiCloudStore::TriggerTaskWithDelay(Windows::Internal::WiFiCloudStore::TaskTrigger)
0x18009f07c  mov     rcx, [rsp+158h]; this
0x18009f084  test    eax, eax
0x18009f086  jns     short loc_18009F09D
0x18009f088  mov     r9d, eax; char *
0x18009f08b  lea     r8, aOnecoreNetWifi_1; "onecore\\net\\wificloudstore\\registry"...
0x18009f092  mov     edx, 3Dh ; '='; void *
0x18009f097  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18009f09d  lea     rcx, [rsp+158h+lpName]
0x18009f0a5  call    ?_Tidy@?$vector@GV?$allocator@G@std@@@std@@AEAAXXZ; std::vector<ushort>::_Tidy(void)
0x18009f0aa  nop
0x18009f0ab  lea     rcx, [rsp+158h+hKey]
0x18009f0b3  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18009f0b8  nop
0x18009f0b9  lea     rcx, [rsp+158h+lpSubKey]
0x18009f0c1  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18009f0c6  mov     rcx, [rsp+158h+var_28]
0x18009f0ce  xor     rcx, rsp; StackCookie
0x18009f0d1  call    __security_check_cookie
0x18009f0d6  mov     rbx, [rsp+158h+arg_10]
0x18009f0de  add     rsp, 140h
0x18009f0e5  pop     r14
0x18009f0e7  pop     rdi
0x18009f0e8  pop     rsi
0x18009f0e9  retn
```
