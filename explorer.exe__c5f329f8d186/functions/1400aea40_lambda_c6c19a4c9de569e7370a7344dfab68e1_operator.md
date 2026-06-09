# _lambda_c6c19a4c9de569e7370a7344dfab68e1_::operator()

- ea: `0x1400aea40`
- end: `0x1400aeba8`
- name: `_lambda_c6c19a4c9de569e7370a7344dfab68e1_::operator()`
- size: `360`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x14007da20`

## callees

- `0x1400272e0`
- `0x140027508`
- `0x140047f0c`
- `0x14007bf4c`
- `0x1400aea40`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1400aeae7`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1400aeae7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400aeab1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400aeab1`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1400aeb4c`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1400aeb4c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400aea9b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400aea9b`

## string_xrefs

- `0x1400aea71`: `Configs`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall lambda_c6c19a4c9de569e7370a7344dfab68e1_::operator()(_BYTE **a1)
{
  unsigned int v2; // ebx
  HKEY *phkResult; // rax
  LSTATUS v5; // eax
  LSTATUS v6; // eax
  LPVOID pv[4]; // [rsp+30h] [rbp-20h] BYREF
  DWORD cbData; // [rsp+70h] [rbp+20h] BYREF
  DWORD Type; // [rsp+78h] [rbp+28h] BYREF
  HKEY hKey; // [rsp+80h] [rbp+30h] BYREF

  hKey = 0;
  memset(pv, 0, 24);
  v2 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::InitializeFormat(
         pv,
         L"%s\\%s",
         *((_QWORD *)*a1 + 1),
         L"Configs");
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
  Type = 0;
  cbData = 0;
  v6 = RegQueryValueExW(hKey, L"GlobalProfileId", 0, &Type, 0, &cbData);
  v2 = v6;
  if ( v6 )
  {
    if ( v6 > 0 )
      v2 = (unsigned __int16)v6 | 0x80070000;
    goto LABEL_10;
  }
  *a1[1] = 1;
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(pv);
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
  return 0;
}

```

## disassembly

```asm
0x1400aea40  push    rbp
0x1400aea42  push    rbx
0x1400aea43  push    rdi
0x1400aea44  mov     rbp, rsp
0x1400aea47  sub     rsp, 50h
0x1400aea4b  mov     rdi, rcx
0x1400aea4e  mov     [rbp+hKey], 0
0x1400aea56  mov     [rbp+pv], 0
0x1400aea5e  mov     [rbp+var_18], 0
0x1400aea66  mov     [rbp+var_10], 0
0x1400aea6e  mov     r8, [rcx]
0x1400aea71  lea     r9, aConfigs; "Configs"
0x1400aea78  mov     r8, [r8+8]
0x1400aea7c  lea     rdx, aSS; "%s\\%s"
0x1400aea83  lea     rcx, [rbp+pv]
0x1400aea87  call    ?InitializeFormat@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEBGZZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::InitializeFormat(ushort const *,...)
0x1400aea8c  mov     ebx, eax
0x1400aea8e  test    eax, eax
0x1400aea90  jns     short loc_1400AEAC5
0x1400aea92  mov     rcx, [rbp+pv]; pv
0x1400aea96  test    rcx, rcx
0x1400aea99  jz      short loc_1400AEAA8
0x1400aea9b  call    cs:__imp_CoTaskMemFree
0x1400aeaa2  nop     dword ptr [rax+rax+00h]
0x1400aeaa7  nop
0x1400aeaa8  mov     rcx, [rbp+hKey]; hKey
0x1400aeaac  test    rcx, rcx
0x1400aeaaf  jz      short loc_1400AEABE
0x1400aeab1  call    cs:__imp_RegCloseKey
0x1400aeab8  nop     dword ptr [rax+rax+00h]
0x1400aeabd  nop
0x1400aeabe  mov     eax, ebx
0x1400aeac0  jmp     loc_1400AEB9F
0x1400aeac5  lea     rcx, [rbp+hKey]
0x1400aeac9  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAUHKEY__@@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(void)
0x1400aeace  mov     [rsp+50h+phkResult], rax; phkResult
0x1400aead3  mov     r9d, 20019h; samDesired
0x1400aead9  xor     r8d, r8d; ulOptions
0x1400aeadc  mov     rdx, [rbp+pv]; lpSubKey
0x1400aeae0  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1400aeae7  call    cs:__imp_RegOpenKeyExW
0x1400aeaee  nop     dword ptr [rax+rax+00h]
0x1400aeaf3  mov     ebx, eax
0x1400aeaf5  test    eax, eax
0x1400aeaf7  jz      short loc_1400AEB1A
0x1400aeaf9  jle     short loc_1400AEB04
0x1400aeafb  movzx   ebx, ax
0x1400aeafe  or      ebx, 80070000h
0x1400aeb04  lea     rcx, [rbp+pv]
0x1400aeb08  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1400aeb0d  nop
0x1400aeb0e  lea     rcx, [rbp+hKey]
0x1400aeb12  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1400aeb17  nop
0x1400aeb18  jmp     short loc_1400AEABE
0x1400aeb1a  mov     [rbp+Type], 0
0x1400aeb21  mov     [rbp+cbData], 0
0x1400aeb28  lea     rax, [rbp+cbData]
0x1400aeb2c  mov     [rsp+50h+lpcbData], rax; lpcbData
0x1400aeb31  mov     [rsp+50h+phkResult], 0; lpData
0x1400aeb3a  lea     r9, [rbp+Type]; lpType
0x1400aeb3e  xor     r8d, r8d; lpReserved
0x1400aeb41  lea     rdx, aGlobalprofilei; "GlobalProfileId"
0x1400aeb48  mov     rcx, [rbp+hKey]; hKey
0x1400aeb4c  call    cs:__imp_RegQueryValueExW
0x1400aeb53  nop     dword ptr [rax+rax+00h]
0x1400aeb58  mov     ebx, eax
0x1400aeb5a  test    eax, eax
0x1400aeb5c  jz      short loc_1400AEB82
0x1400aeb5e  jle     short loc_1400AEB69
0x1400aeb60  movzx   ebx, ax
0x1400aeb63  or      ebx, 80070000h
0x1400aeb69  lea     rcx, [rbp+pv]
0x1400aeb6d  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1400aeb72  nop
0x1400aeb73  lea     rcx, [rbp+hKey]
0x1400aeb77  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1400aeb7c  nop
0x1400aeb7d  jmp     loc_1400AEABE
0x1400aeb82  mov     rax, [rdi+8]
0x1400aeb86  mov     byte ptr [rax], 1
0x1400aeb89  lea     rcx, [rbp+pv]
0x1400aeb8d  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1400aeb92  nop
0x1400aeb93  lea     rcx, [rbp+hKey]
0x1400aeb97  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1400aeb9c  nop
0x1400aeb9d  xor     eax, eax
0x1400aeb9f  add     rsp, 50h
0x1400aeba3  pop     rdi
0x1400aeba4  pop     rbx
0x1400aeba5  pop     rbp
0x1400aeba6  retn
```
