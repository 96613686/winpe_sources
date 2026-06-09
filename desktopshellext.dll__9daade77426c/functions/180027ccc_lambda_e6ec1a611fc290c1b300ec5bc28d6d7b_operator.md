# _lambda_e6ec1a611fc290c1b300ec5bc28d6d7b_::operator()

- ea: `0x180027ccc`
- end: `0x180027e4e`
- name: `_lambda_e6ec1a611fc290c1b300ec5bc28d6d7b_::operator()`
- size: `386`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, service_task`

## callers

- `0x1800816e0`

## callees

- `0x1800108cc`
- `0x180027ccc`
- `0x18002812c`
- `0x180081770`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180027d38`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180027d92`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180027de5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180027dff`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180027e1b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180027e35`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180027d38`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180027d92`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180027de5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180027dff`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180027e1b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180027e35`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180027d68`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180027dc5`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180027d68`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180027dc5`

## string_xrefs

- `0x180027d04`: `Configs`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall lambda_e6ec1a611fc290c1b300ec5bc28d6d7b_::operator()(__int64 a1)
{
  unsigned int v2; // ebx
  HKEY *phkResult; // rax
  LSTATUS v5; // eax
  HKEY *v6; // rax
  LSTATUS v7; // eax
  LPCWSTR lpSubKey[4]; // [rsp+30h] [rbp-20h] BYREF
  HKEY hKey; // [rsp+60h] [rbp+10h] BYREF
  HKEY v10; // [rsp+68h] [rbp+18h] BYREF

  hKey = 0;
  memset(lpSubKey, 0, 24);
  v2 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::InitializeFormat(
         lpSubKey,
         L"%s\\%s",
         *(_QWORD *)(*(_QWORD *)a1 + 8LL),
         L"Configs");
  if ( (v2 & 0x80000000) != 0 )
  {
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(lpSubKey);
    if ( hKey )
      RegCloseKey(hKey);
    return v2;
  }
  phkResult = (HKEY *)wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(&hKey);
  v5 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, lpSubKey[0], 0, 0x20019u, phkResult);
  v2 = v5;
  if ( v5 )
  {
    if ( v5 > 0 )
      v2 = (unsigned __int16)v5 | 0x80070000;
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(lpSubKey);
    if ( hKey )
      RegCloseKey(hKey);
    return v2;
  }
  v10 = 0;
  v6 = (HKEY *)wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(&v10);
  v7 = RegOpenKeyExW(hKey, **(LPCWSTR **)(a1 + 8), 0, 0x20019u, v6);
  v2 = v7;
  if ( v7 )
  {
    if ( v7 > 0 )
      v2 = (unsigned __int16)v7 | 0x80070000;
    if ( v10 )
      RegCloseKey(v10);
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(lpSubKey);
    if ( hKey )
      RegCloseKey(hKey);
    return v2;
  }
  **(_BYTE **)(a1 + 16) = 1;
  if ( v10 )
    RegCloseKey(v10);
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(lpSubKey);
  if ( hKey )
    RegCloseKey(hKey);
  return 0;
}

```

## disassembly

```asm
0x180027ccc  mov     [rsp-8+arg_10], rbx
0x180027cd1  mov     [rsp-8+arg_18], rdi
0x180027cd6  push    rbp
0x180027cd7  mov     rbp, rsp
0x180027cda  sub     rsp, 50h
0x180027cde  mov     rdi, rcx
0x180027ce1  mov     [rbp+hKey], 0
0x180027ce9  mov     [rbp+lpSubKey], 0
0x180027cf1  mov     [rbp+var_18], 0
0x180027cf9  mov     [rbp+var_10], 0
0x180027d01  mov     r8, [rcx]
0x180027d04  lea     r9, aConfigs; "Configs"
0x180027d0b  mov     r8, [r8+8]
0x180027d0f  lea     rdx, aSS; "%s\\%s"
0x180027d16  lea     rcx, [rbp+lpSubKey]
0x180027d1a  call    ?InitializeFormat@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEBGZZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::InitializeFormat(ushort const *,...)
0x180027d1f  mov     ebx, eax
0x180027d21  test    eax, eax
0x180027d23  jns     short loc_180027D46
0x180027d25  lea     rcx, [rbp+lpSubKey]
0x180027d29  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180027d2e  nop
0x180027d2f  mov     rcx, [rbp+hKey]; hKey
0x180027d33  test    rcx, rcx
0x180027d36  jz      short loc_180027D3F
0x180027d38  call    cs:__imp_RegCloseKey
0x180027d3e  nop
0x180027d3f  mov     eax, ebx
0x180027d41  jmp     loc_180027E3E
0x180027d46  lea     rcx, [rbp+hKey]
0x180027d4a  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAUHKEY__@@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(void)
0x180027d4f  mov     [rsp+50h+phkResult], rax; phkResult
0x180027d54  mov     r9d, 20019h; samDesired
0x180027d5a  xor     r8d, r8d; ulOptions
0x180027d5d  mov     rdx, [rbp+lpSubKey]; lpSubKey
0x180027d61  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180027d68  call    cs:__imp_RegOpenKeyExW
0x180027d6e  mov     ebx, eax
0x180027d70  test    eax, eax
0x180027d72  jz      short loc_180027D9B
0x180027d74  jle     short loc_180027D7F
0x180027d76  movzx   ebx, ax
0x180027d79  or      ebx, 80070000h
0x180027d7f  lea     rcx, [rbp+lpSubKey]
0x180027d83  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180027d88  nop
0x180027d89  mov     rcx, [rbp+hKey]; hKey
0x180027d8d  test    rcx, rcx
0x180027d90  jz      short loc_180027D99
0x180027d92  call    cs:__imp_RegCloseKey
0x180027d98  nop
0x180027d99  jmp     short loc_180027D3F
0x180027d9b  mov     [rbp+arg_8], 0
0x180027da3  lea     rcx, [rbp+arg_8]
0x180027da7  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAUHKEY__@@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(void)
0x180027dac  mov     rdx, [rdi+8]
0x180027db0  mov     [rsp+50h+phkResult], rax; phkResult
0x180027db5  mov     r9d, 20019h; samDesired
0x180027dbb  xor     r8d, r8d; ulOptions
0x180027dbe  mov     rdx, [rdx]; lpSubKey
0x180027dc1  mov     rcx, [rbp+hKey]; hKey
0x180027dc5  call    cs:__imp_RegOpenKeyExW
0x180027dcb  mov     ebx, eax
0x180027dcd  test    eax, eax
0x180027dcf  jz      short loc_180027E0B
0x180027dd1  jle     short loc_180027DDC
0x180027dd3  movzx   ebx, ax
0x180027dd6  or      ebx, 80070000h
0x180027ddc  mov     rcx, [rbp+arg_8]; hKey
0x180027de0  test    rcx, rcx
0x180027de3  jz      short loc_180027DEC
0x180027de5  call    cs:__imp_RegCloseKey
0x180027deb  nop
0x180027dec  lea     rcx, [rbp+lpSubKey]
0x180027df0  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180027df5  nop
0x180027df6  mov     rcx, [rbp+hKey]; hKey
0x180027dfa  test    rcx, rcx
0x180027dfd  jz      short loc_180027E06
0x180027dff  call    cs:__imp_RegCloseKey
0x180027e05  nop
0x180027e06  jmp     loc_180027D3F
0x180027e0b  mov     rax, [rdi+10h]
0x180027e0f  mov     byte ptr [rax], 1
0x180027e12  mov     rcx, [rbp+arg_8]; hKey
0x180027e16  test    rcx, rcx
0x180027e19  jz      short loc_180027E22
0x180027e1b  call    cs:__imp_RegCloseKey
0x180027e21  nop
0x180027e22  lea     rcx, [rbp+lpSubKey]
0x180027e26  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180027e2b  nop
0x180027e2c  mov     rcx, [rbp+hKey]; hKey
0x180027e30  test    rcx, rcx
0x180027e33  jz      short loc_180027E3C
0x180027e35  call    cs:__imp_RegCloseKey
0x180027e3b  nop
0x180027e3c  xor     eax, eax
0x180027e3e  mov     rbx, [rsp+50h+arg_10]
0x180027e43  mov     rdi, [rsp+50h+arg_18]
0x180027e48  add     rsp, 50h
0x180027e4c  pop     rbp
0x180027e4d  retn
```
