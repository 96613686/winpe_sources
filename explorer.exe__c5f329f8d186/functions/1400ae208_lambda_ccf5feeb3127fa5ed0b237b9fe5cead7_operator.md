# _lambda_ccf5feeb3127fa5ed0b237b9fe5cead7_::operator()

- ea: `0x1400ae208`
- end: `0x1400ae382`
- name: `_lambda_ccf5feeb3127fa5ed0b237b9fe5cead7_::operator()`
- size: `378`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x14007ccc0`

## callees

- `0x1400272e0`
- `0x140027508`
- `0x140047f0c`
- `0x14007bf4c`
- `0x1400ae208`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x1400ae316`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x1400ae316`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1400ae2a8`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1400ae2a8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400ae272`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400ae272`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400ae25c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400ae25c`

## string_xrefs

- `0x1400ae232`: `GroupConfigs`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall lambda_ccf5feeb3127fa5ed0b237b9fe5cead7_::operator()(_BYTE **a1)
{
  unsigned int v2; // ebx
  HKEY *phkResult; // rax
  LSTATUS v5; // eax
  LSTATUS v6; // eax
  LPVOID pv[4]; // [rsp+60h] [rbp-20h] BYREF
  DWORD cSubKeys; // [rsp+A0h] [rbp+20h] BYREF
  HKEY hKey; // [rsp+A8h] [rbp+28h] BYREF

  hKey = 0;
  memset(pv, 0, 24);
  v2 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::InitializeFormat(
         pv,
         L"%s\\%s",
         *((_QWORD *)*a1 + 1),
         L"GroupConfigs");
  if ( (v2 & 0x80000000) != 0 )
  {
    if ( pv[0] )
      CoTaskMemFree(pv[0]);
    if ( hKey )
      RegCloseKey(hKey);
    return v2;
  }
  phkResult = (HKEY *)wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(&hKey);
  v5 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, (LPCWSTR)pv[0], 0, 0x20019u, phkResult);
  v2 = v5;
  if ( v5 )
  {
    if ( v5 > 0 )
      v2 = (unsigned __int16)v5 | 0x80070000;
LABEL_10:
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(pv);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
    return v2;
  }
  cSubKeys = 0;
  v6 = RegQueryInfoKeyW(hKey, 0, 0, 0, &cSubKeys, 0, 0, 0, 0, 0, 0, 0);
  v2 = v6;
  if ( v6 )
  {
    if ( v6 > 0 )
      v2 = (unsigned __int16)v6 | 0x80070000;
    goto LABEL_10;
  }
  *a1[1] = cSubKeys != 0;
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(pv);
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
  return 0;
}

```

## disassembly

```asm
0x1400ae208  mov     [rsp-18h+arg_10], rbx
0x1400ae20d  push    rbp
0x1400ae20e  push    rsi
0x1400ae20f  push    rdi
0x1400ae210  mov     rbp, rsp
0x1400ae213  sub     rsp, 80h
0x1400ae21a  mov     rdi, rcx
0x1400ae21d  xor     esi, esi
0x1400ae21f  mov     [rbp+hKey], rsi
0x1400ae223  mov     [rbp+pv], rsi
0x1400ae227  mov     [rbp+var_18], rsi
0x1400ae22b  mov     [rbp+var_10], rsi
0x1400ae22f  mov     r8, [rcx]
0x1400ae232  lea     r9, aGroupconfigs; "GroupConfigs"
0x1400ae239  mov     r8, [r8+8]
0x1400ae23d  lea     rdx, aSS; "%s\\%s"
0x1400ae244  lea     rcx, [rbp+pv]
0x1400ae248  call    ?InitializeFormat@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEBGZZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::InitializeFormat(ushort const *,...)
0x1400ae24d  mov     ebx, eax
0x1400ae24f  test    eax, eax
0x1400ae251  jns     short loc_1400AE286
0x1400ae253  mov     rcx, [rbp+pv]; pv
0x1400ae257  test    rcx, rcx
0x1400ae25a  jz      short loc_1400AE269
0x1400ae25c  call    cs:__imp_CoTaskMemFree
0x1400ae263  nop     dword ptr [rax+rax+00h]
0x1400ae268  nop
0x1400ae269  mov     rcx, [rbp+hKey]; hKey
0x1400ae26d  test    rcx, rcx
0x1400ae270  jz      short loc_1400AE27F
0x1400ae272  call    cs:__imp_RegCloseKey
0x1400ae279  nop     dword ptr [rax+rax+00h]
0x1400ae27e  nop
0x1400ae27f  mov     eax, ebx
0x1400ae281  jmp     loc_1400AE36E
0x1400ae286  lea     rcx, [rbp+hKey]
0x1400ae28a  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAUHKEY__@@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(void)
0x1400ae28f  mov     [rsp+80h+phkResult], rax; phkResult
0x1400ae294  mov     r9d, 20019h; samDesired
0x1400ae29a  xor     r8d, r8d; ulOptions
0x1400ae29d  mov     rdx, [rbp+pv]; lpSubKey
0x1400ae2a1  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1400ae2a8  call    cs:__imp_RegOpenKeyExW
0x1400ae2af  nop     dword ptr [rax+rax+00h]
0x1400ae2b4  mov     ebx, eax
0x1400ae2b6  test    eax, eax
0x1400ae2b8  jz      short loc_1400AE2DB
0x1400ae2ba  jle     short loc_1400AE2C5
0x1400ae2bc  movzx   ebx, ax
0x1400ae2bf  or      ebx, 80070000h
0x1400ae2c5  lea     rcx, [rbp+pv]
0x1400ae2c9  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1400ae2ce  nop
0x1400ae2cf  lea     rcx, [rbp+hKey]
0x1400ae2d3  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1400ae2d8  nop
0x1400ae2d9  jmp     short loc_1400AE27F
0x1400ae2db  mov     [rbp+cSubKeys], esi
0x1400ae2de  mov     [rsp+80h+lpftLastWriteTime], rsi; lpftLastWriteTime
0x1400ae2e3  mov     [rsp+80h+lpcbSecurityDescriptor], rsi; lpcbSecurityDescriptor
0x1400ae2e8  mov     [rsp+80h+lpcbMaxValueLen], rsi; lpcbMaxValueLen
0x1400ae2ed  mov     [rsp+80h+lpcbMaxValueNameLen], rsi; lpcbMaxValueNameLen
0x1400ae2f2  mov     [rsp+80h+lpcValues], rsi; lpcValues
0x1400ae2f7  mov     [rsp+80h+lpcbMaxClassLen], rsi; lpcbMaxClassLen
0x1400ae2fc  mov     [rsp+80h+lpcbMaxSubKeyLen], rsi; lpcbMaxSubKeyLen
0x1400ae301  lea     rax, [rbp+cSubKeys]
0x1400ae305  mov     [rsp+80h+phkResult], rax; lpcSubKeys
0x1400ae30a  xor     r9d, r9d; lpReserved
0x1400ae30d  xor     r8d, r8d; lpcchClass
0x1400ae310  xor     edx, edx; lpClass
0x1400ae312  mov     rcx, [rbp+hKey]; hKey
0x1400ae316  call    cs:__imp_RegQueryInfoKeyW
0x1400ae31d  nop     dword ptr [rax+rax+00h]
0x1400ae322  mov     ebx, eax
0x1400ae324  test    eax, eax
0x1400ae326  jz      short loc_1400AE34C
0x1400ae328  jle     short loc_1400AE333
0x1400ae32a  movzx   ebx, ax
0x1400ae32d  or      ebx, 80070000h
0x1400ae333  lea     rcx, [rbp+pv]
0x1400ae337  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1400ae33c  nop
0x1400ae33d  lea     rcx, [rbp+hKey]
0x1400ae341  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1400ae346  nop
0x1400ae347  jmp     loc_1400AE27F
0x1400ae34c  cmp     [rbp+cSubKeys], esi
0x1400ae34f  setnz   cl
0x1400ae352  mov     rax, [rdi+8]
0x1400ae356  mov     [rax], cl
0x1400ae358  lea     rcx, [rbp+pv]
0x1400ae35c  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1400ae361  nop
0x1400ae362  lea     rcx, [rbp+hKey]
0x1400ae366  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1400ae36b  nop
0x1400ae36c  xor     eax, eax
0x1400ae36e  mov     rbx, [rsp+80h+arg_10]
0x1400ae376  add     rsp, 80h
0x1400ae37d  pop     rdi
0x1400ae37e  pop     rsi
0x1400ae37f  pop     rbp
0x1400ae380  retn
```
