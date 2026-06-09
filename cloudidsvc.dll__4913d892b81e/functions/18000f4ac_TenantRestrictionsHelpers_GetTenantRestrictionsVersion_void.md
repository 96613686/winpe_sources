# TenantRestrictionsHelpers::GetTenantRestrictionsVersion(void)

- ea: `0x18000f4ac`
- end: `0x18000f7c5`
- name: `?GetTenantRestrictionsVersion@TenantRestrictionsHelpers@@YA?AV?$unordered_map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@XZ`
- size: `793`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18000b67c`

## callees

- `0x180001a50`
- `0x180008d64`
- `0x180009da8`
- `0x180009e50`
- `0x18000a864`
- `0x18000c43c`
- `0x18000c498`
- `0x18000c874`
- `0x18000ca74`
- `0x18000da04`
- `0x18000dc08`
- `0x18000dd00`
- `0x18000f4ac`
- `0x18000fd54`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18000f56c`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18000f56c`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18000f5e4`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18000f5e4`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x18000f6a8`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x18000f6a8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000f72d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000f741`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000f72d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000f741`
- `api-ms-win-service-core-l1-1-3!GetServiceRegistryStateKey` at `0x18000f508`
- `api-ms-win-service-core-l1-1-3!GetServiceRegistryStateKey` at `0x18000f508`

## string_xrefs

- `0x18000f519`: `onecoreuap\ds\ext\common\ntservice\lib\utilities.cpp`
- `0x18000f57d`: `onecoreuap\ds\ext\common\ntservice\lib\utilities.cpp`
- `0x18000f5f5`: `onecoreuap\ds\ext\common\ntservice\lib\utilities.cpp`
- `0x18000f78f`: `onecoreuap\ds\ext\common\ntservice\lib\utilities.cpp`
- `0x18000f7a1`: `onecoreuap\ds\ext\common\ntservice\lib\utilities.cpp`
- `0x18000f7b3`: `onecoreuap\ds\ext\common\ntservice\lib\utilities.cpp`

## pseudocode

```c
__int64 __fastcall TenantRestrictionsHelpers::GetTenantRestrictionsVersion(__int64 a1)
{
  unsigned int ServiceRegistryStateKey; // eax
  unsigned int v3; // eax
  unsigned int v4; // eax
  DWORD i; // edi
  const char *v6; // r9
  const char *v7; // r9
  unsigned int v8; // eax
  __int64 v9; // rbx
  __int64 v10; // rax
  _QWORD *v11; // r8
  __int64 v12; // rdx
  LPBYTE v13; // rcx
  LPWSTR v14; // rcx
  unsigned int dwOptions; // [rsp+20h] [rbp-89h]
  unsigned int dwOptionsa; // [rsp+20h] [rbp-89h]
  unsigned int dwOptionsb; // [rsp+20h] [rbp-89h]
  unsigned int dwOptionsc; // [rsp+20h] [rbp-89h]
  DWORD cbMaxValueNameLen; // [rsp+60h] [rbp-49h] BYREF
  DWORD cbMaxValueLen; // [rsp+64h] [rbp-45h] BYREF
  DWORD cValues; // [rsp+68h] [rbp-41h] BYREF
  LPBYTE lpData; // [rsp+70h] [rbp-39h] BYREF
  LPWSTR lpValueName; // [rsp+78h] [rbp-31h] BYREF
  HKEY v25; // [rsp+80h] [rbp-29h] BYREF
  HKEY hKey; // [rsp+88h] [rbp-21h] BYREF
  int v27; // [rsp+90h] [rbp-19h]
  DWORD cbData; // [rsp+94h] [rbp-15h] BYREF
  DWORD Type; // [rsp+98h] [rbp-11h] BYREF
  DWORD cchValueName; // [rsp+9Ch] [rbp-Dh] BYREF
  HKEY *v31; // [rsp+A0h] [rbp-9h] BYREF
  HKEY phkResult; // [rsp+A8h] [rbp-1h] BYREF
  char v33; // [rsp+B0h] [rbp+7h]
  __int64 v34; // [rsp+B8h] [rbp+Fh]
  _BYTE v35[32]; // [rsp+C0h] [rbp+17h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+108h] [rbp+5Fh]

  v34 = a1;
  v27 = 0;
  hKey = 0;
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
    &hKey,
    0);
  ServiceRegistryStateKey = GetServiceRegistryStateKey(g_SvcStatusHandle, 1, 131103, &hKey);
  if ( ServiceRegistryStateKey )
    wil::details::in1diag3::_Throw_Win32(
      retaddr,
      (void *)0xDA,
      (unsigned int)"onecoreuap\\ds\\ext\\common\\ntservice\\lib\\utilities.cpp",
      (const char *)ServiceRegistryStateKey,
      dwOptions);
  v25 = 0;
  v31 = &v25;
  phkResult = 0;
  v33 = 1;
  v3 = RegCreateKeyExW(hKey, L"TenantRestrictionsVersion", 0, 0, 0, 0x2001Fu, 0, &phkResult, 0);
  if ( v3 )
    wil::details::in1diag3::_Throw_Win32(
      retaddr,
      (void *)0xE7,
      (unsigned int)"onecoreuap\\ds\\ext\\common\\ntservice\\lib\\utilities.cpp",
      (const char *)v3,
      dwOptionsa);
  wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(&v31);
  cValues = 0;
  cbMaxValueNameLen = 0;
  cbMaxValueLen = 0;
  v4 = RegQueryInfoKeyW(v25, 0, 0, 0, 0, 0, 0, &cValues, &cbMaxValueNameLen, &cbMaxValueLen, 0, 0);
  if ( v4 )
    wil::details::in1diag3::_Throw_Win32(
      retaddr,
      (void *)0xF9,
      (unsigned int)"onecoreuap\\ds\\ext\\common\\ntservice\\lib\\utilities.cpp",
      (const char *)v4,
      dwOptionsb);
  std::unordered_map<std::wstring,std::wstring>::unordered_map<std::wstring,std::wstring>(a1);
  v27 = 1;
  for ( i = 0; i < cValues; ++i )
  {
    wil::make_unique_hlocal<unsigned short [0]>(&lpValueName, cbMaxValueNameLen + 1);
    if ( !lpValueName )
      wil::details::in1diag3::_Throw_NullAlloc(
        retaddr,
        (void *)0xFF,
        (unsigned int)"onecoreuap\\ds\\ext\\common\\ntservice\\lib\\utilities.cpp",
        v6);
    wil::make_unique_hlocal<unsigned short [0]>(&lpData, cbMaxValueLen + 1);
    if ( !lpData )
      wil::details::in1diag3::_Throw_NullAlloc(
        retaddr,
        (void *)0x101,
        (unsigned int)"onecoreuap\\ds\\ext\\common\\ntservice\\lib\\utilities.cpp",
        v7);
    Type = 0;
    cchValueName = 2 * cbMaxValueNameLen + 2;
    cbData = 2 * cbMaxValueLen + 2;
    v8 = RegEnumValueW(v25, i, lpValueName, &cchValueName, 0, &Type, lpData, &cbData);
    if ( v8 )
      wil::details::in1diag3::_Throw_Win32(
        retaddr,
        (void *)0x10D,
        (unsigned int)"onecoreuap\\ds\\ext\\common\\ntservice\\lib\\utilities.cpp",
        (const char *)v8,
        dwOptionsc);
    v9 = *(_QWORD *)(std::wstring::wstring(v35, lpData) + 16);
    std::wstring::_Tidy_deallocate(v35);
    if ( v9 )
    {
      std::wstring::wstring(v35, lpValueName);
      std::_Hash<std::_Umap_traits<std::wstring,std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::_Try_emplace<std::wstring,>(
        a1,
        &v31,
        v35);
      v10 = std::_WChar_traits<unsigned short>::length(lpData);
      std::wstring::_Assign<unsigned short>(*v11 + 48LL, v12, v10);
      std::wstring::_Tidy_deallocate(v35);
    }
    v13 = lpData;
    lpData = 0;
    if ( v13 )
      LocalFree(v13);
    v14 = lpValueName;
    lpValueName = 0;
    if ( v14 )
      LocalFree(v14);
  }
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v25);
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
  return a1;
}

```

## disassembly

```asm
0x18000f4ac  mov     [rsp-8+arg_8], rbx
0x18000f4b1  mov     [rsp-8+arg_10], rsi
0x18000f4b6  push    rbp
0x18000f4b7  push    rdi
0x18000f4b8  push    r14
0x18000f4ba  lea     rbp, [rsp-47h]
0x18000f4bf  sub     rsp, 0F0h
0x18000f4c6  mov     rax, cs:__security_cookie
0x18000f4cd  xor     rax, rsp
0x18000f4d0  mov     [rbp+57h+var_20], rax
0x18000f4d4  mov     rsi, rcx
0x18000f4d7  mov     [rbp+57h+var_48], rcx
0x18000f4db  xor     r14d, r14d
0x18000f4de  mov     [rbp+57h+var_70], r14d
0x18000f4e2  mov     [rbp+57h+hKey], r14
0x18000f4e6  xor     edx, edx
0x18000f4e8  lea     rcx, [rbp+57h+hKey]
0x18000f4ec  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x18000f4f1  lea     r9, [rbp+57h+hKey]
0x18000f4f5  mov     ebx, 2001Fh
0x18000f4fa  mov     r8d, ebx
0x18000f4fd  lea     edx, [r14+1]
0x18000f501  mov     rcx, cs:?g_SvcStatusHandle@@3PEAUSERVICE_STATUS_HANDLE__@@EA; SERVICE_STATUS_HANDLE__ * g_SvcStatusHandle
0x18000f508  call    cs:__imp_GetServiceRegistryStateKey
0x18000f50e  mov     rcx, [rbp+5Fh]; this
0x18000f512  test    eax, eax
0x18000f514  jz      short loc_18000F52B
0x18000f516  mov     r9d, eax; char *
0x18000f519  lea     r8, aOnecoreuapDsEx; "onecoreuap\\ds\\ext\\common\\ntservice"...
0x18000f520  mov     edx, 0DAh; void *
0x18000f525  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x18000f52b  mov     [rbp+57h+var_80], r14
0x18000f52f  lea     rax, [rbp+57h+var_80]
0x18000f533  mov     [rbp+57h+var_60], rax
0x18000f537  mov     [rbp+57h+var_58], r14
0x18000f53b  mov     [rbp+57h+var_50], 1
0x18000f53f  mov     [rsp+100h+lpdwDisposition], r14; lpdwDisposition
0x18000f544  lea     rax, [rbp+57h+var_58]
0x18000f548  mov     [rsp+100h+phkResult], rax; phkResult
0x18000f54d  mov     [rsp+100h+lpSecurityAttributes], r14; lpSecurityAttributes
0x18000f552  mov     [rsp+100h+samDesired], ebx; samDesired
0x18000f556  mov     [rsp+100h+dwOptions], r14d; unsigned int
0x18000f55b  xor     r9d, r9d; lpClass
0x18000f55e  xor     r8d, r8d; Reserved
0x18000f561  lea     rdx, aTenantrestrict; "TenantRestrictionsVersion"
0x18000f568  mov     rcx, [rbp+57h+hKey]; hKey
0x18000f56c  call    cs:__imp_RegCreateKeyExW
0x18000f572  mov     rcx, [rbp+5Fh]; this
0x18000f576  test    eax, eax
0x18000f578  jz      short loc_18000F58F
0x18000f57a  mov     r9d, eax; char *
0x18000f57d  lea     r8, aOnecoreuapDsEx; "onecoreuap\\ds\\ext\\common\\ntservice"...
0x18000f584  mov     edx, 0E7h; void *
0x18000f589  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x18000f58f  lea     rcx, [rbp+57h+var_60]
0x18000f593  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(void)
0x18000f598  mov     [rbp+57h+cValues], r14d
0x18000f59c  mov     [rbp+57h+cbMaxValueNameLen], r14d
0x18000f5a0  mov     [rbp+57h+cbMaxValueLen], r14d
0x18000f5a4  mov     [rsp+100h+lpftLastWriteTime], r14; lpftLastWriteTime
0x18000f5a9  mov     [rsp+100h+lpcbSecurityDescriptor], r14; lpcbSecurityDescriptor
0x18000f5ae  lea     rax, [rbp+57h+cbMaxValueLen]
0x18000f5b2  mov     [rsp+100h+lpcbMaxValueLen], rax; lpcbMaxValueLen
0x18000f5b7  lea     rax, [rbp+57h+cbMaxValueNameLen]
0x18000f5bb  mov     [rsp+100h+lpdwDisposition], rax; lpcbMaxValueNameLen
0x18000f5c0  lea     rax, [rbp+57h+cValues]
0x18000f5c4  mov     [rsp+100h+phkResult], rax; lpcValues
0x18000f5c9  mov     [rsp+100h+lpSecurityAttributes], r14; lpcbMaxClassLen
0x18000f5ce  mov     qword ptr [rsp+100h+samDesired], r14; lpcbMaxSubKeyLen
0x18000f5d3  mov     qword ptr [rsp+100h+dwOptions], r14; unsigned int
0x18000f5d8  xor     r9d, r9d; lpReserved
0x18000f5db  xor     r8d, r8d; lpcchClass
0x18000f5de  xor     edx, edx; lpClass
0x18000f5e0  mov     rcx, [rbp+57h+var_80]; hKey
0x18000f5e4  call    cs:__imp_RegQueryInfoKeyW
0x18000f5ea  mov     rcx, [rbp+5Fh]; this
0x18000f5ee  test    eax, eax
0x18000f5f0  jz      short loc_18000F607
0x18000f5f2  mov     r9d, eax; char *
0x18000f5f5  lea     r8, aOnecoreuapDsEx; "onecoreuap\\ds\\ext\\common\\ntservice"...
0x18000f5fc  mov     edx, 0F9h; void *
0x18000f601  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x18000f607  mov     rcx, rsi
0x18000f60a  call    ??0?$unordered_map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@QEAA@XZ; std::unordered_map<std::wstring,std::wstring>::unordered_map<std::wstring,std::wstring>(void)
0x18000f60f  mov     [rbp+57h+var_70], 1
0x18000f616  mov     edi, r14d
0x18000f619  cmp     [rbp+57h+cValues], r14d
0x18000f61d  jbe     loc_18000F752
0x18000f623  mov     edx, [rbp+57h+cbMaxValueNameLen]
0x18000f626  inc     edx
0x18000f628  lea     rcx, [rbp+57h+lpValueName]
0x18000f62c  call    ??$make_unique_hlocal@$$BY0A@G@wil@@YA?AV?$unique_ptr@$$BY0A@GU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@_K@Z; wil::make_unique_hlocal<ushort [0]>(unsigned __int64)
0x18000f631  nop
0x18000f632  mov     rcx, [rbp+5Fh]; this
0x18000f636  cmp     [rbp+57h+lpValueName], r14
0x18000f63a  jz      loc_18000F7B3
0x18000f640  mov     edx, [rbp+57h+cbMaxValueLen]
0x18000f643  inc     edx
0x18000f645  lea     rcx, [rbp+57h+lpData]
0x18000f649  call    ??$make_unique_hlocal@$$BY0A@G@wil@@YA?AV?$unique_ptr@$$BY0A@GU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@_K@Z; wil::make_unique_hlocal<ushort [0]>(unsigned __int64)
0x18000f64e  nop
0x18000f64f  mov     rcx, [rbp+5Fh]; this
0x18000f653  mov     rax, [rbp+57h+lpData]
0x18000f657  test    rax, rax
0x18000f65a  jz      loc_18000F7A1
0x18000f660  mov     [rbp+57h+Type], r14d
0x18000f664  mov     ecx, [rbp+57h+cbMaxValueNameLen]
0x18000f667  lea     ecx, ds:2[rcx*2]
0x18000f66e  mov     [rbp+57h+cchValueName], ecx
0x18000f671  mov     ecx, [rbp+57h+cbMaxValueLen]
0x18000f674  lea     ecx, ds:2[rcx*2]
0x18000f67b  mov     [rbp+57h+cbData], ecx
0x18000f67e  lea     rcx, [rbp+57h+cbData]
0x18000f682  mov     [rsp+100h+phkResult], rcx; lpcbData
0x18000f687  mov     [rsp+100h+lpSecurityAttributes], rax; lpData
0x18000f68c  lea     rax, [rbp+57h+Type]
0x18000f690  mov     qword ptr [rsp+100h+samDesired], rax; lpType
0x18000f695  mov     qword ptr [rsp+100h+dwOptions], r14; unsigned int
0x18000f69a  lea     r9, [rbp+57h+cchValueName]; lpcchValueName
0x18000f69e  mov     r8, [rbp+57h+lpValueName]; lpValueName
0x18000f6a2  mov     edx, edi; dwIndex
0x18000f6a4  mov     rcx, [rbp+57h+var_80]; hKey
0x18000f6a8  call    cs:__imp_RegEnumValueW
0x18000f6ae  mov     rcx, [rbp+5Fh]; this
0x18000f6b2  test    eax, eax
0x18000f6b4  jnz     loc_18000F78C
0x18000f6ba  mov     rdx, [rbp+57h+lpData]
0x18000f6be  lea     rcx, [rbp+57h+var_40]
0x18000f6c2  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18000f6c7  mov     rbx, [rax+10h]
0x18000f6cb  lea     rcx, [rbp+57h+var_40]
0x18000f6cf  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18000f6d4  test    rbx, rbx
0x18000f6d7  jz      short loc_18000F720
0x18000f6d9  mov     rdx, [rbp+57h+lpValueName]
0x18000f6dd  lea     rcx, [rbp+57h+var_40]
0x18000f6e1  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18000f6e6  nop
0x18000f6e7  lea     r8, [rbp+57h+var_40]
0x18000f6eb  lea     rdx, [rbp+57h+var_60]
0x18000f6ef  mov     rcx, rsi
0x18000f6f2  call    ??$_Try_emplace@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@$$V@?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@$0A@@std@@@std@@IEAA?AU?$pair@PEAU?$_List_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@PEAX@std@@_N@1@$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::_Hash<std::_Umap_traits<std::wstring,std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::_Try_emplace<std::wstring,>(std::wstring &&)
0x18000f6f7  mov     r8, rax
0x18000f6fa  mov     rdx, [rbp+57h+lpData]
0x18000f6fe  mov     rcx, rdx
0x18000f701  call    ?length@?$_WChar_traits@G@std@@SA_KPEBG@Z; std::_WChar_traits<ushort>::length(ushort const *)
0x18000f706  mov     rcx, [r8]
0x18000f709  add     rcx, 30h ; '0'
0x18000f70d  mov     r8, rax
0x18000f710  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x18000f715  nop
0x18000f716  lea     rcx, [rbp+57h+var_40]
0x18000f71a  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18000f71f  nop
0x18000f720  mov     rcx, [rbp+57h+lpData]; hMem
0x18000f724  mov     [rbp+57h+lpData], r14
0x18000f728  test    rcx, rcx
0x18000f72b  jz      short loc_18000F734
0x18000f72d  call    cs:__imp_LocalFree
0x18000f733  nop
0x18000f734  mov     rcx, [rbp+57h+lpValueName]; hMem
0x18000f738  mov     [rbp+57h+lpValueName], r14
0x18000f73c  test    rcx, rcx
0x18000f73f  jz      short loc_18000F747
0x18000f741  call    cs:__imp_LocalFree
0x18000f747  inc     edi
0x18000f749  cmp     edi, [rbp+57h+cValues]
0x18000f74c  jb      loc_18000F623
0x18000f752  lea     rcx, [rbp+57h+var_80]
0x18000f756  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18000f75b  nop
0x18000f75c  lea     rcx, [rbp+57h+hKey]
0x18000f760  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18000f765  mov     rax, rsi
0x18000f768  mov     rcx, [rbp+57h+var_20]
0x18000f76c  xor     rcx, rsp; StackCookie
0x18000f76f  call    __security_check_cookie
0x18000f774  lea     r11, [rsp+100h+var_10]
0x18000f77c  mov     rbx, [r11+28h]
0x18000f780  mov     rsi, [r11+30h]
0x18000f784  mov     rsp, r11
0x18000f787  pop     r14
0x18000f789  pop     rdi
0x18000f78a  pop     rbp
0x18000f78b  retn
0x18000f78c  mov     r9d, eax; char *
0x18000f78f  lea     r8, aOnecoreuapDsEx; "onecoreuap\\ds\\ext\\common\\ntservice"...
0x18000f796  mov     edx, 10Dh; void *
0x18000f79b  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x18000f7a1  lea     r8, aOnecoreuapDsEx; "onecoreuap\\ds\\ext\\common\\ntservice"...
0x18000f7a8  mov     edx, 101h; void *
0x18000f7ad  call    ?_Throw_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_NullAlloc(void *,uint,char const *)
0x18000f7b3  lea     r8, aOnecoreuapDsEx; "onecoreuap\\ds\\ext\\common\\ntservice"...
0x18000f7ba  mov     edx, 0FFh; void *
0x18000f7bf  call    ?_Throw_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_NullAlloc(void *,uint,char const *)
```
