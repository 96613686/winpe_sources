# _lambda_e6ec1a611fc290c1b300ec5bc28d6d7b_::operator()

- ea: `0x1400aec2c`
- end: `0x1400aedaf`
- name: `_lambda_e6ec1a611fc290c1b300ec5bc28d6d7b_::operator()`
- size: `387`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x140079b50`

## callees

- `0x1400272e0`
- `0x140027508`
- `0x140047f0c`
- `0x14007bf4c`
- `0x1400aec2c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1400aecda`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1400aed37`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1400aecda`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1400aed37`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400aeca4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400aeca4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400aec8e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400aec8e`

## string_xrefs

- `0x1400aec64`: `Configs`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall lambda_e6ec1a611fc290c1b300ec5bc28d6d7b_::operator()(__int64 a1)
{
  unsigned int v2; // ebx
  HKEY *phkResult; // rax
  LSTATUS v5; // eax
  __int64 v6; // rdx
  HKEY *v7; // rax
  LSTATUS v8; // eax
  __int64 v9; // rdx
  __int64 v10; // rdx
  LPVOID pv[4]; // [rsp+30h] [rbp-20h] BYREF
  HKEY hKey; // [rsp+60h] [rbp+10h] BYREF
  __int64 v13; // [rsp+68h] [rbp+18h] BYREF

  hKey = 0;
  memset(pv, 0, 24);
  v2 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::InitializeFormat(
         pv,
         L"%s\\%s",
         *(_QWORD *)(*(_QWORD *)a1 + 8LL),
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
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(pv, v6);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
    return v2;
  }
  v13 = 0;
  v7 = (HKEY *)wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(&v13);
  v8 = RegOpenKeyExW(hKey, **(LPCWSTR **)(a1 + 8), 0, 0x20019u, v7);
  v2 = v8;
  if ( v8 )
  {
    if ( v8 > 0 )
      v2 = (unsigned __int16)v8 | 0x80070000;
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v13);
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(pv, v9);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
    return v2;
  }
  **(_BYTE **)(a1 + 16) = 1;
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v13);
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(pv, v10);
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
  return 0;
}

```

## disassembly

```asm
0x1400aec2c  mov     [rsp-8+arg_10], rbx
0x1400aec31  mov     [rsp-8+arg_18], rdi
0x1400aec36  push    rbp
0x1400aec37  mov     rbp, rsp
0x1400aec3a  sub     rsp, 50h
0x1400aec3e  mov     rdi, rcx
0x1400aec41  mov     [rbp+hKey], 0
0x1400aec49  mov     [rbp+pv], 0
0x1400aec51  mov     [rbp+var_18], 0
0x1400aec59  mov     [rbp+var_10], 0
0x1400aec61  mov     r8, [rcx]
0x1400aec64  lea     r9, aConfigs; "Configs"
0x1400aec6b  mov     r8, [r8+8]
0x1400aec6f  lea     rdx, aSS; "%s\\%s"
0x1400aec76  lea     rcx, [rbp+pv]
0x1400aec7a  call    ?InitializeFormat@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEBGZZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::InitializeFormat(ushort const *,...)
0x1400aec7f  mov     ebx, eax
0x1400aec81  test    eax, eax
0x1400aec83  jns     short loc_1400AECB8
0x1400aec85  mov     rcx, [rbp+pv]; pv
0x1400aec89  test    rcx, rcx
0x1400aec8c  jz      short loc_1400AEC9B
0x1400aec8e  call    cs:__imp_CoTaskMemFree
0x1400aec95  nop     dword ptr [rax+rax+00h]
0x1400aec9a  nop
0x1400aec9b  mov     rcx, [rbp+hKey]; hKey
0x1400aec9f  test    rcx, rcx
0x1400aeca2  jz      short loc_1400AECB1
0x1400aeca4  call    cs:__imp_RegCloseKey
0x1400aecab  nop     dword ptr [rax+rax+00h]
0x1400aecb0  nop
0x1400aecb1  mov     eax, ebx
0x1400aecb3  jmp     loc_1400AED9E
0x1400aecb8  lea     rcx, [rbp+hKey]
0x1400aecbc  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAUHKEY__@@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(void)
0x1400aecc1  mov     [rsp+50h+phkResult], rax; phkResult
0x1400aecc6  mov     r9d, 20019h; samDesired
0x1400aeccc  xor     r8d, r8d; ulOptions
0x1400aeccf  mov     rdx, [rbp+pv]; lpSubKey
0x1400aecd3  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1400aecda  call    cs:__imp_RegOpenKeyExW
0x1400aece1  nop     dword ptr [rax+rax+00h]
0x1400aece6  mov     ebx, eax
0x1400aece8  test    eax, eax
0x1400aecea  jz      short loc_1400AED0D
0x1400aecec  jle     short loc_1400AECF7
0x1400aecee  movzx   ebx, ax
0x1400aecf1  or      ebx, 80070000h
0x1400aecf7  lea     rcx, [rbp+pv]
0x1400aecfb  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1400aed00  nop
0x1400aed01  lea     rcx, [rbp+hKey]
0x1400aed05  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1400aed0a  nop
0x1400aed0b  jmp     short loc_1400AECB1
0x1400aed0d  mov     [rbp+arg_8], 0
0x1400aed15  lea     rcx, [rbp+arg_8]
0x1400aed19  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAUHKEY__@@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(void)
0x1400aed1e  mov     rdx, [rdi+8]
0x1400aed22  mov     [rsp+50h+phkResult], rax; phkResult
0x1400aed27  mov     r9d, 20019h; samDesired
0x1400aed2d  xor     r8d, r8d; ulOptions
0x1400aed30  mov     rdx, [rdx]; lpSubKey
0x1400aed33  mov     rcx, [rbp+hKey]; hKey
0x1400aed37  call    cs:__imp_RegOpenKeyExW
0x1400aed3e  nop     dword ptr [rax+rax+00h]
0x1400aed43  mov     ebx, eax
0x1400aed45  test    eax, eax
0x1400aed47  jz      short loc_1400AED77
0x1400aed49  jle     short loc_1400AED54
0x1400aed4b  movzx   ebx, ax
0x1400aed4e  or      ebx, 80070000h
0x1400aed54  lea     rcx, [rbp+arg_8]
0x1400aed58  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1400aed5d  nop
0x1400aed5e  lea     rcx, [rbp+pv]
0x1400aed62  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1400aed67  nop
0x1400aed68  lea     rcx, [rbp+hKey]
0x1400aed6c  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1400aed71  nop
0x1400aed72  jmp     loc_1400AECB1
0x1400aed77  mov     rax, [rdi+10h]
0x1400aed7b  mov     byte ptr [rax], 1
0x1400aed7e  lea     rcx, [rbp+arg_8]
0x1400aed82  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1400aed87  nop
0x1400aed88  lea     rcx, [rbp+pv]
0x1400aed8c  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1400aed91  nop
0x1400aed92  lea     rcx, [rbp+hKey]
0x1400aed96  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1400aed9b  nop
0x1400aed9c  xor     eax, eax
0x1400aed9e  mov     rbx, [rsp+50h+arg_10]
0x1400aeda3  mov     rdi, [rsp+50h+arg_18]
0x1400aeda8  add     rsp, 50h
0x1400aedac  pop     rbp
0x1400aedad  retn
```
