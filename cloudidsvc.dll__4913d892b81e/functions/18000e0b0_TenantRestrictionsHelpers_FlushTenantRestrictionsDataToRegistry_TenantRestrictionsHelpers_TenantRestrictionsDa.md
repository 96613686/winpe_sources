# TenantRestrictionsHelpers::FlushTenantRestrictionsDataToRegistry(TenantRestrictionsHelpers::TenantRestrictionsData &,std::unordered_map<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::hash<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,std::equal_to<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,std::allocator<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>> &)

- ea: `0x18000e0b0`
- end: `0x18000e4aa`
- name: `?FlushTenantRestrictionsDataToRegistry@TenantRestrictionsHelpers@@YAXAEAUTenantRestrictionsData@1@AEAV?$unordered_map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@@Z`
- size: `1018`
- prototype: `__int64 __fastcall(_QWORD *, __int64)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18000b67c`

## callees

- `0x180001a50`
- `0x180009d60`
- `0x18000a864`
- `0x18000c338`
- `0x18000c43c`
- `0x18000c498`
- `0x18000ca74`
- `0x18000dd48`
- `0x18000dfcc`
- `0x18000e0b0`

## import_xrefs

- `ntdll!NtCreateRegistryTransaction` at `0x18000e0f7`
- `ntdll!NtCreateRegistryTransaction` at `0x18000e0f7`
- `ntdll!NtCommitRegistryTransaction` at `0x18000e426`
- `ntdll!NtCommitRegistryTransaction` at `0x18000e426`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000e1bf`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000e220`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000e281`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000e3e1`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000e1bf`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000e220`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000e281`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000e3e1`
- `api-ms-win-service-core-l1-1-3!GetServiceRegistryStateKey` at `0x18000e2d2`
- `api-ms-win-service-core-l1-1-3!GetServiceRegistryStateKey` at `0x18000e2d2`
- `api-ms-win-core-registry-l2-1-0!RegOpenKeyTransactedW` at `0x18000e15a`
- `api-ms-win-core-registry-l2-1-0!RegOpenKeyTransactedW` at `0x18000e15a`
- `api-ms-win-core-registry-l2-1-0!RegCreateKeyTransactedW` at `0x18000e357`
- `api-ms-win-core-registry-l2-1-0!RegCreateKeyTransactedW` at `0x18000e357`

## string_xrefs

- `0x18000e108`: `onecoreuap\ds\ext\common\ntservice\lib\utilities.cpp`
- `0x18000e16b`: `onecoreuap\ds\ext\common\ntservice\lib\utilities.cpp`
- `0x18000e1d0`: `onecoreuap\ds\ext\common\ntservice\lib\utilities.cpp`
- `0x18000e231`: `onecoreuap\ds\ext\common\ntservice\lib\utilities.cpp`
- `0x18000e292`: `onecoreuap\ds\ext\common\ntservice\lib\utilities.cpp`
- `0x18000e2e3`: `onecoreuap\ds\ext\common\ntservice\lib\utilities.cpp`
- `0x18000e368`: `onecoreuap\ds\ext\common\ntservice\lib\utilities.cpp`
- `0x18000e40d`: `onecoreuap\ds\ext\common\ntservice\lib\utilities.cpp`
- `0x18000e437`: `onecoreuap\ds\ext\common\ntservice\lib\utilities.cpp`

## pseudocode

```c
__int64 __fastcall TenantRestrictionsHelpers::FlushTenantRestrictionsDataToRegistry(_QWORD *a1, __int64 a2)
{
  unsigned int v4; // eax
  HANDLE hTransaction; // rbx
  unsigned int v6; // eax
  const BYTE *v7; // rax
  DWORD v8; // edx
  unsigned int v9; // eax
  const BYTE *v10; // rax
  DWORD v11; // edx
  unsigned int v12; // eax
  const BYTE *v13; // rax
  DWORD v14; // edx
  unsigned int v15; // eax
  unsigned int ServiceRegistryStateKey; // eax
  HANDLE v17; // rbx
  unsigned int v18; // eax
  _QWORD **v19; // rdi
  _QWORD *i; // rbx
  const WCHAR *v21; // rax
  const BYTE *v22; // r8
  DWORD v23; // r9d
  unsigned int v24; // eax
  unsigned int v25; // eax
  unsigned int phkResult; // [rsp+20h] [rbp-E0h]
  unsigned int phkResulta; // [rsp+20h] [rbp-E0h]
  unsigned int phkResultb; // [rsp+20h] [rbp-E0h]
  unsigned int phkResultc; // [rsp+20h] [rbp-E0h]
  unsigned int phkResultd; // [rsp+20h] [rbp-E0h]
  unsigned int phkResulte; // [rsp+20h] [rbp-E0h]
  HKEY hKey; // [rsp+60h] [rbp-A0h] BYREF
  HANDLE v34; // [rsp+68h] [rbp-98h] BYREF
  HKEY v35; // [rsp+70h] [rbp-90h] BYREF
  HKEY v36; // [rsp+78h] [rbp-88h] BYREF
  _BYTE v37[16]; // [rsp+80h] [rbp-80h] BYREF
  _BYTE v38[16]; // [rsp+A0h] [rbp-60h] BYREF
  _BYTE v39[16]; // [rsp+C0h] [rbp-40h] BYREF
  _BYTE v40[16]; // [rsp+E0h] [rbp-20h] BYREF
  _BYTE v41[32]; // [rsp+100h] [rbp+0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+158h] [rbp+58h]

  hKey = 0;
  v34 = 0;
  v4 = NtCreateRegistryTransaction(&v34, 2031679, 0, 0);
  if ( v4 )
    wil::details::in1diag3::_Throw_Win32(
      retaddr,
      (void *)0x177,
      (unsigned int)"onecoreuap\\ds\\ext\\common\\ntservice\\lib\\utilities.cpp",
      (const char *)v4,
      phkResult);
  hTransaction = v34;
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
    &hKey,
    0);
  v6 = RegOpenKeyTransactedW(
         HKEY_LOCAL_MACHINE,
         L"SOFTWARE\\Microsoft\\Windows\\TenantRestrictions\\TenantRestrictionsList",
         0,
         0xF003Fu,
         &hKey,
         hTransaction,
         0);
  if ( v6 )
    wil::details::in1diag3::_Throw_Win32(
      retaddr,
      (void *)0x180,
      (unsigned int)"onecoreuap\\ds\\ext\\common\\ntservice\\lib\\utilities.cpp",
      (const char *)v6,
      phkResulta);
  TenantRestrictionsHelpers::ConvertToRegMultiSz(v40, *(_QWORD *)*a1, *a1);
  v7 = (const BYTE *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v40);
  v9 = RegSetValueExW(hKey, L"Hostnames", 0, 7u, v7, v8);
  if ( v9 )
    wil::details::in1diag3::_Throw_Win32(
      retaddr,
      (void *)0x18A,
      (unsigned int)"onecoreuap\\ds\\ext\\common\\ntservice\\lib\\utilities.cpp",
      (const char *)v9,
      phkResultb);
  TenantRestrictionsHelpers::ConvertToRegMultiSz(v39, *(_QWORD *)a1[2], a1[2]);
  v10 = (const BYTE *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v39);
  v12 = RegSetValueExW(hKey, L"SubdomainSupportedHostnames", 0, 7u, v10, v11);
  if ( v12 )
    wil::details::in1diag3::_Throw_Win32(
      retaddr,
      (void *)0x193,
      (unsigned int)"onecoreuap\\ds\\ext\\common\\ntservice\\lib\\utilities.cpp",
      (const char *)v12,
      phkResultc);
  TenantRestrictionsHelpers::ConvertToRegMultiSz(v38, *(_QWORD *)a1[4], a1[4]);
  v13 = (const BYTE *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v38);
  v15 = RegSetValueExW(hKey, L"IPRanges", 0, 7u, v13, v14);
  if ( v15 )
    wil::details::in1diag3::_Throw_Win32(
      retaddr,
      (void *)0x19C,
      (unsigned int)"onecoreuap\\ds\\ext\\common\\ntservice\\lib\\utilities.cpp",
      (const char *)v15,
      phkResultd);
  v36 = 0;
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
    &v36,
    0);
  ServiceRegistryStateKey = GetServiceRegistryStateKey(g_SvcStatusHandle, 1, 131103, &v36);
  if ( ServiceRegistryStateKey )
    wil::details::in1diag3::_Throw_Win32(
      retaddr,
      (void *)0x1A5,
      (unsigned int)"onecoreuap\\ds\\ext\\common\\ntservice\\lib\\utilities.cpp",
      (const char *)ServiceRegistryStateKey,
      phkResultd);
  v35 = 0;
  v17 = v34;
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
    &v35,
    0);
  v18 = RegCreateKeyTransactedW(v36, L"TenantRestrictionsVersion", 0, 0, 0, 0x2001Fu, 0, &v35, 0, v17, 0);
  if ( v18 )
    wil::details::in1diag3::_Throw_Win32(
      retaddr,
      (void *)0x1B4,
      (unsigned int)"onecoreuap\\ds\\ext\\common\\ntservice\\lib\\utilities.cpp",
      (const char *)v18,
      phkResulte);
  v19 = *(_QWORD ***)(a2 + 8);
  for ( i = *v19; i != v19; i = (_QWORD *)*i )
  {
    std::wstring::wstring(v41, i + 2);
    std::wstring::wstring(v37, i + 6);
    std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v37);
    v21 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v41);
    v24 = RegSetValueExW(v35, v21, 0, 1u, v22, v23);
    if ( v24 )
      wil::details::in1diag3::_Throw_Win32(
        retaddr,
        (void *)0x1C1,
        (unsigned int)"onecoreuap\\ds\\ext\\common\\ntservice\\lib\\utilities.cpp",
        (const char *)v24,
        phkResulte);
    std::wstring::_Tidy_deallocate(v37);
    std::wstring::_Tidy_deallocate(v41);
  }
  v25 = NtCommitRegistryTransaction(v34, 0);
  if ( v25 )
    wil::details::in1diag3::_Throw_Win32(
      retaddr,
      (void *)0x1C4,
      (unsigned int)"onecoreuap\\ds\\ext\\common\\ntservice\\lib\\utilities.cpp",
      (const char *)v25,
      phkResulte);
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v35);
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v36);
  std::wstring::_Tidy_deallocate(v38);
  std::wstring::_Tidy_deallocate(v39);
  std::wstring::_Tidy_deallocate(v40);
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v34);
  return wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
}

```

## disassembly

```asm
0x18000e0b0  push    rbp
0x18000e0b2  push    rbx
0x18000e0b3  push    rsi
0x18000e0b4  push    rdi
0x18000e0b5  lea     rbp, [rsp-38h]
0x18000e0ba  sub     rsp, 138h
0x18000e0c1  mov     rax, cs:__security_cookie
0x18000e0c8  xor     rax, rsp
0x18000e0cb  mov     [rbp+50h+var_30], rax
0x18000e0cf  mov     rsi, rdx
0x18000e0d2  mov     rdi, rcx
0x18000e0d5  mov     [rsp+150h+hKey], 0
0x18000e0de  mov     [rsp+150h+var_E8], 0
0x18000e0e7  xor     r9d, r9d
0x18000e0ea  xor     r8d, r8d
0x18000e0ed  mov     edx, 1F003Fh
0x18000e0f2  lea     rcx, [rsp+150h+var_E8]
0x18000e0f7  call    cs:__imp_NtCreateRegistryTransaction
0x18000e0fd  mov     rcx, [rbp+58h]; this
0x18000e101  test    eax, eax
0x18000e103  jz      short loc_18000E11A
0x18000e105  mov     r9d, eax; char *
0x18000e108  lea     r8, aOnecoreuapDsEx; "onecoreuap\\ds\\ext\\common\\ntservice"...
0x18000e10f  mov     edx, 177h; void *
0x18000e114  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x18000e11a  mov     rbx, [rsp+150h+var_E8]
0x18000e11f  xor     edx, edx
0x18000e121  lea     rcx, [rsp+150h+hKey]
0x18000e126  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x18000e12b  mov     [rsp+150h+pExtendedParemeter], 0; pExtendedParemeter
0x18000e134  mov     [rsp+150h+hTransaction], rbx; hTransaction
0x18000e139  lea     rax, [rsp+150h+hKey]
0x18000e13e  mov     [rsp+150h+phkResult], rax; unsigned int
0x18000e143  mov     r9d, 0F003Fh; samDesired
0x18000e149  xor     r8d, r8d; ulOptions
0x18000e14c  lea     rdx, aSoftwareMicros; "SOFTWARE\\Microsoft\\Windows\\TenantRes"...
0x18000e153  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000e15a  call    cs:__imp_RegOpenKeyTransactedW
0x18000e160  mov     rcx, [rbp+58h]; this
0x18000e164  test    eax, eax
0x18000e166  jz      short loc_18000E17D
0x18000e168  mov     r9d, eax; char *
0x18000e16b  lea     r8, aOnecoreuapDsEx; "onecoreuap\\ds\\ext\\common\\ntservice"...
0x18000e172  mov     edx, 180h; void *
0x18000e177  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x18000e17d  mov     rdx, [rdi]
0x18000e180  mov     r8, rdx
0x18000e183  mov     rdx, [rdx]
0x18000e186  lea     rcx, [rbp+50h+var_70]
0x18000e18a  call    ?ConvertToRegMultiSz@TenantRestrictionsHelpers@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@@3@0@Z; TenantRestrictionsHelpers::ConvertToRegMultiSz(std::_Tree_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::wstring>>>,std::_Tree_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::wstring>>>)
0x18000e18f  nop
0x18000e190  mov     eax, [rbp+50h+var_60]
0x18000e193  lea     edx, [rax+rax]
0x18000e196  lea     rcx, [rbp+50h+var_70]
0x18000e19a  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18000e19f  mov     dword ptr [rsp+150h+hTransaction], edx; cbData
0x18000e1a3  mov     [rsp+150h+phkResult], rax; unsigned int
0x18000e1a8  mov     ebx, 7
0x18000e1ad  mov     r9d, ebx; dwType
0x18000e1b0  xor     r8d, r8d; Reserved
0x18000e1b3  lea     rdx, ValueName; "Hostnames"
0x18000e1ba  mov     rcx, [rsp+150h+hKey]; hKey
0x18000e1bf  call    cs:__imp_RegSetValueExW
0x18000e1c5  mov     rcx, [rbp+58h]; this
0x18000e1c9  test    eax, eax
0x18000e1cb  jz      short loc_18000E1E2
0x18000e1cd  mov     r9d, eax; char *
0x18000e1d0  lea     r8, aOnecoreuapDsEx; "onecoreuap\\ds\\ext\\common\\ntservice"...
0x18000e1d7  mov     edx, 18Ah; void *
0x18000e1dc  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x18000e1e2  mov     rdx, [rdi+10h]
0x18000e1e6  mov     r8, rdx
0x18000e1e9  mov     rdx, [rdx]
0x18000e1ec  lea     rcx, [rbp+50h+var_90]
0x18000e1f0  call    ?ConvertToRegMultiSz@TenantRestrictionsHelpers@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@@3@0@Z; TenantRestrictionsHelpers::ConvertToRegMultiSz(std::_Tree_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::wstring>>>,std::_Tree_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::wstring>>>)
0x18000e1f5  nop
0x18000e1f6  mov     eax, [rbp+50h+var_80]
0x18000e1f9  lea     edx, [rax+rax]
0x18000e1fc  lea     rcx, [rbp+50h+var_90]
0x18000e200  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18000e205  mov     dword ptr [rsp+150h+hTransaction], edx; cbData
0x18000e209  mov     [rsp+150h+phkResult], rax; unsigned int
0x18000e20e  mov     r9d, ebx; dwType
0x18000e211  xor     r8d, r8d; Reserved
0x18000e214  lea     rdx, aSubdomainsuppo; "SubdomainSupportedHostnames"
0x18000e21b  mov     rcx, [rsp+150h+hKey]; hKey
0x18000e220  call    cs:__imp_RegSetValueExW
0x18000e226  mov     rcx, [rbp+58h]; this
0x18000e22a  test    eax, eax
0x18000e22c  jz      short loc_18000E243
0x18000e22e  mov     r9d, eax; char *
0x18000e231  lea     r8, aOnecoreuapDsEx; "onecoreuap\\ds\\ext\\common\\ntservice"...
0x18000e238  mov     edx, 193h; void *
0x18000e23d  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x18000e243  mov     rdx, [rdi+20h]
0x18000e247  mov     r8, rdx
0x18000e24a  mov     rdx, [rdx]
0x18000e24d  lea     rcx, [rbp+50h+var_B0]
0x18000e251  call    ?ConvertToRegMultiSz@TenantRestrictionsHelpers@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@@3@0@Z; TenantRestrictionsHelpers::ConvertToRegMultiSz(std::_Tree_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::wstring>>>,std::_Tree_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::wstring>>>)
0x18000e256  nop
0x18000e257  mov     eax, [rbp+50h+var_A0]
0x18000e25a  lea     edx, [rax+rax]
0x18000e25d  lea     rcx, [rbp+50h+var_B0]
0x18000e261  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18000e266  mov     dword ptr [rsp+150h+hTransaction], edx; cbData
0x18000e26a  mov     [rsp+150h+phkResult], rax; unsigned int
0x18000e26f  mov     r9d, ebx; dwType
0x18000e272  xor     r8d, r8d; Reserved
0x18000e275  lea     rdx, aIpranges; "IPRanges"
0x18000e27c  mov     rcx, [rsp+150h+hKey]; hKey
0x18000e281  call    cs:__imp_RegSetValueExW
0x18000e287  mov     rcx, [rbp+58h]; this
0x18000e28b  test    eax, eax
0x18000e28d  jz      short loc_18000E2A4
0x18000e28f  mov     r9d, eax; char *
0x18000e292  lea     r8, aOnecoreuapDsEx; "onecoreuap\\ds\\ext\\common\\ntservice"...
0x18000e299  mov     edx, 19Ch; void *
0x18000e29e  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x18000e2a4  mov     [rsp+150h+var_D8], 0
0x18000e2ad  xor     edx, edx
0x18000e2af  lea     rcx, [rsp+150h+var_D8]
0x18000e2b4  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x18000e2b9  lea     r9, [rsp+150h+var_D8]
0x18000e2be  mov     edi, 2001Fh
0x18000e2c3  mov     r8d, edi
0x18000e2c6  mov     edx, 1
0x18000e2cb  mov     rcx, cs:?g_SvcStatusHandle@@3PEAUSERVICE_STATUS_HANDLE__@@EA; SERVICE_STATUS_HANDLE__ * g_SvcStatusHandle
0x18000e2d2  call    cs:__imp_GetServiceRegistryStateKey
0x18000e2d8  mov     rcx, [rbp+58h]; this
0x18000e2dc  test    eax, eax
0x18000e2de  jz      short loc_18000E2F5
0x18000e2e0  mov     r9d, eax; char *
0x18000e2e3  lea     r8, aOnecoreuapDsEx; "onecoreuap\\ds\\ext\\common\\ntservice"...
0x18000e2ea  mov     edx, 1A5h; void *
0x18000e2ef  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x18000e2f5  mov     [rsp+150h+var_E0], 0
0x18000e2fe  mov     rbx, [rsp+150h+var_E8]
0x18000e303  xor     edx, edx
0x18000e305  lea     rcx, [rsp+150h+var_E0]
0x18000e30a  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x18000e30f  mov     [rsp+150h+var_100], 0; pExtendedParemeter
0x18000e318  mov     [rsp+150h+var_108], rbx; hTransaction
0x18000e31d  mov     [rsp+150h+lpdwDisposition], 0; lpdwDisposition
0x18000e326  lea     rax, [rsp+150h+var_E0]
0x18000e32b  mov     [rsp+150h+var_118], rax; phkResult
0x18000e330  mov     [rsp+150h+pExtendedParemeter], 0; lpSecurityAttributes
0x18000e339  mov     dword ptr [rsp+150h+hTransaction], edi; samDesired
0x18000e33d  mov     dword ptr [rsp+150h+phkResult], 0; unsigned int
0x18000e345  xor     r9d, r9d; lpClass
0x18000e348  xor     r8d, r8d; Reserved
0x18000e34b  lea     rdx, aTenantrestrict; "TenantRestrictionsVersion"
0x18000e352  mov     rcx, [rsp+150h+var_D8]; hKey
0x18000e357  call    cs:__imp_RegCreateKeyTransactedW
0x18000e35d  mov     rcx, [rbp+58h]; this
0x18000e361  test    eax, eax
0x18000e363  jz      short loc_18000E37A
0x18000e365  mov     r9d, eax; char *
0x18000e368  lea     r8, aOnecoreuapDsEx; "onecoreuap\\ds\\ext\\common\\ntservice"...
0x18000e36f  mov     edx, 1B4h; void *
0x18000e374  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x18000e37a  mov     rdi, [rsi+8]
0x18000e37e  mov     rbx, [rdi]
0x18000e381  cmp     rbx, rdi
0x18000e384  jz      loc_18000E41F
0x18000e38a  lea     rdx, [rbx+10h]
0x18000e38e  lea     rcx, [rbp+50h+var_50]
0x18000e392  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18000e397  nop
0x18000e398  lea     rdx, [rbx+30h]
0x18000e39c  lea     rcx, [rbp+50h+var_D0]
0x18000e3a0  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18000e3a5  nop
0x18000e3a6  mov     eax, [rbp+50h+var_C0]
0x18000e3a9  lea     r9d, ds:2[rax*2]
0x18000e3b1  lea     rcx, [rbp+50h+var_D0]
0x18000e3b5  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18000e3ba  mov     r8, rax
0x18000e3bd  lea     rcx, [rbp+50h+var_50]
0x18000e3c1  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18000e3c6  mov     rdx, rax; lpValueName
0x18000e3c9  mov     dword ptr [rsp+150h+hTransaction], r9d; cbData
0x18000e3ce  mov     [rsp+150h+phkResult], r8; unsigned int
0x18000e3d3  mov     r9d, 1; dwType
0x18000e3d9  xor     r8d, r8d; Reserved
0x18000e3dc  mov     rcx, [rsp+150h+var_E0]; hKey
0x18000e3e1  call    cs:__imp_RegSetValueExW
0x18000e3e7  mov     rcx, [rbp+58h]; this
0x18000e3eb  test    eax, eax
0x18000e3ed  jnz     short loc_18000E40A
0x18000e3ef  lea     rcx, [rbp+50h+var_D0]
0x18000e3f3  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18000e3f8  nop
0x18000e3f9  lea     rcx, [rbp+50h+var_50]
0x18000e3fd  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18000e402  mov     rbx, [rbx]
0x18000e405  jmp     loc_18000E381
0x18000e40a  mov     r9d, eax; char *
0x18000e40d  lea     r8, aOnecoreuapDsEx; "onecoreuap\\ds\\ext\\common\\ntservice"...
0x18000e414  mov     edx, 1C1h; void *
0x18000e419  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x18000e41f  xor     edx, edx
0x18000e421  mov     rcx, [rsp+150h+var_E8]
0x18000e426  call    cs:__imp_NtCommitRegistryTransaction
0x18000e42c  mov     rcx, [rbp+58h]; this
0x18000e430  test    eax, eax
0x18000e432  jz      short loc_18000E449
0x18000e434  mov     r9d, eax; char *
0x18000e437  lea     r8, aOnecoreuapDsEx; "onecoreuap\\ds\\ext\\common\\ntservice"...
0x18000e43e  mov     edx, 1C4h; void *
0x18000e443  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x18000e449  lea     rcx, [rsp+150h+var_E0]
0x18000e44e  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18000e453  nop
0x18000e454  lea     rcx, [rsp+150h+var_D8]
0x18000e459  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18000e45e  nop
0x18000e45f  lea     rcx, [rbp+50h+var_B0]
0x18000e463  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18000e468  nop
0x18000e469  lea     rcx, [rbp+50h+var_90]
0x18000e46d  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18000e472  nop
0x18000e473  lea     rcx, [rbp+50h+var_70]
0x18000e477  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18000e47c  nop
0x18000e47d  lea     rcx, [rsp+150h+var_E8]
0x18000e482  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18000e487  nop
0x18000e488  lea     rcx, [rsp+150h+hKey]
0x18000e48d  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18000e492  mov     rcx, [rbp+50h+var_30]
0x18000e496  xor     rcx, rsp; StackCookie
0x18000e499  call    __security_check_cookie
0x18000e49e  add     rsp, 138h
0x18000e4a5  pop     rdi
0x18000e4a6  pop     rsi
0x18000e4a7  pop     rbx
0x18000e4a8  pop     rbp
0x18000e4a9  retn
```
