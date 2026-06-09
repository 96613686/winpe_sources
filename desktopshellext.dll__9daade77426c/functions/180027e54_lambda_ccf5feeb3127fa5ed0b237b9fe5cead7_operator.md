# _lambda_ccf5feeb3127fa5ed0b237b9fe5cead7_::operator()

- ea: `0x180027e54`
- end: `0x180027fc1`
- name: `_lambda_ccf5feeb3127fa5ed0b237b9fe5cead7_::operator()`
- size: `365`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, service_task`

## callers

- `0x180081650`

## callees

- `0x1800108cc`
- `0x180027e54`
- `0x18002812c`
- `0x180081770`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180027f50`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180027f50`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180027eb2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180027f0c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180027f7a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180027fa5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180027eb2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180027f0c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180027f7a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180027fa5`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180027ee2`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180027ee2`

## string_xrefs

- `0x180027e7e`: `GroupConfigs`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall lambda_ccf5feeb3127fa5ed0b237b9fe5cead7_::operator()(_BYTE **a1)
{
  unsigned int v2; // ebx
  HKEY *phkResult; // rax
  LSTATUS v5; // eax
  LSTATUS v6; // eax
  LPCWSTR lpSubKey[4]; // [rsp+60h] [rbp-20h] BYREF
  DWORD cSubKeys; // [rsp+A0h] [rbp+20h] BYREF
  HKEY hKey; // [rsp+A8h] [rbp+28h] BYREF

  hKey = 0;
  memset(lpSubKey, 0, 24);
  v2 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::InitializeFormat(
         lpSubKey,
         L"%s\\%s",
         *((_QWORD *)*a1 + 1),
         L"GroupConfigs");
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
  cSubKeys = 0;
  v6 = RegQueryInfoKeyW(hKey, 0, 0, 0, &cSubKeys, 0, 0, 0, 0, 0, 0, 0);
  v2 = v6;
  if ( v6 )
  {
    if ( v6 > 0 )
      v2 = (unsigned __int16)v6 | 0x80070000;
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(lpSubKey);
    if ( hKey )
      RegCloseKey(hKey);
    return v2;
  }
  *a1[1] = cSubKeys != 0;
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(lpSubKey);
  if ( hKey )
    RegCloseKey(hKey);
  return 0;
}

```

## disassembly

```asm
0x180027e54  mov     [rsp-18h+arg_10], rbx
0x180027e59  push    rbp
0x180027e5a  push    rsi
0x180027e5b  push    rdi
0x180027e5c  mov     rbp, rsp
0x180027e5f  sub     rsp, 80h
0x180027e66  mov     rdi, rcx
0x180027e69  xor     esi, esi
0x180027e6b  mov     [rbp+hKey], rsi
0x180027e6f  mov     [rbp+lpSubKey], rsi
0x180027e73  mov     [rbp+var_18], rsi
0x180027e77  mov     [rbp+var_10], rsi
0x180027e7b  mov     r8, [rcx]
0x180027e7e  lea     r9, aGroupconfigs; "GroupConfigs"
0x180027e85  mov     r8, [r8+8]
0x180027e89  lea     rdx, aSS; "%s\\%s"
0x180027e90  lea     rcx, [rbp+lpSubKey]
0x180027e94  call    ?InitializeFormat@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEBGZZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::InitializeFormat(ushort const *,...)
0x180027e99  mov     ebx, eax
0x180027e9b  test    eax, eax
0x180027e9d  jns     short loc_180027EC0
0x180027e9f  lea     rcx, [rbp+lpSubKey]
0x180027ea3  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180027ea8  nop
0x180027ea9  mov     rcx, [rbp+hKey]; hKey
0x180027ead  test    rcx, rcx
0x180027eb0  jz      short loc_180027EB9
0x180027eb2  call    cs:__imp_RegCloseKey
0x180027eb8  nop
0x180027eb9  mov     eax, ebx
0x180027ebb  jmp     loc_180027FAE
0x180027ec0  lea     rcx, [rbp+hKey]
0x180027ec4  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAUHKEY__@@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(void)
0x180027ec9  mov     [rsp+80h+phkResult], rax; phkResult
0x180027ece  mov     r9d, 20019h; samDesired
0x180027ed4  xor     r8d, r8d; ulOptions
0x180027ed7  mov     rdx, [rbp+lpSubKey]; lpSubKey
0x180027edb  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180027ee2  call    cs:__imp_RegOpenKeyExW
0x180027ee8  mov     ebx, eax
0x180027eea  test    eax, eax
0x180027eec  jz      short loc_180027F15
0x180027eee  jle     short loc_180027EF9
0x180027ef0  movzx   ebx, ax
0x180027ef3  or      ebx, 80070000h
0x180027ef9  lea     rcx, [rbp+lpSubKey]
0x180027efd  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180027f02  nop
0x180027f03  mov     rcx, [rbp+hKey]; hKey
0x180027f07  test    rcx, rcx
0x180027f0a  jz      short loc_180027F13
0x180027f0c  call    cs:__imp_RegCloseKey
0x180027f12  nop
0x180027f13  jmp     short loc_180027EB9
0x180027f15  mov     [rbp+cSubKeys], esi
0x180027f18  mov     [rsp+80h+lpftLastWriteTime], rsi; lpftLastWriteTime
0x180027f1d  mov     [rsp+80h+lpcbSecurityDescriptor], rsi; lpcbSecurityDescriptor
0x180027f22  mov     [rsp+80h+lpcbMaxValueLen], rsi; lpcbMaxValueLen
0x180027f27  mov     [rsp+80h+lpcbMaxValueNameLen], rsi; lpcbMaxValueNameLen
0x180027f2c  mov     [rsp+80h+lpcValues], rsi; lpcValues
0x180027f31  mov     [rsp+80h+lpcbMaxClassLen], rsi; lpcbMaxClassLen
0x180027f36  mov     [rsp+80h+lpcbMaxSubKeyLen], rsi; lpcbMaxSubKeyLen
0x180027f3b  lea     rax, [rbp+cSubKeys]
0x180027f3f  mov     [rsp+80h+phkResult], rax; lpcSubKeys
0x180027f44  xor     r9d, r9d; lpReserved
0x180027f47  xor     r8d, r8d; lpcchClass
0x180027f4a  xor     edx, edx; lpClass
0x180027f4c  mov     rcx, [rbp+hKey]; hKey
0x180027f50  call    cs:__imp_RegQueryInfoKeyW
0x180027f56  mov     ebx, eax
0x180027f58  test    eax, eax
0x180027f5a  jz      short loc_180027F86
0x180027f5c  jle     short loc_180027F67
0x180027f5e  movzx   ebx, ax
0x180027f61  or      ebx, 80070000h
0x180027f67  lea     rcx, [rbp+lpSubKey]
0x180027f6b  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180027f70  nop
0x180027f71  mov     rcx, [rbp+hKey]; hKey
0x180027f75  test    rcx, rcx
0x180027f78  jz      short loc_180027F81
0x180027f7a  call    cs:__imp_RegCloseKey
0x180027f80  nop
0x180027f81  jmp     loc_180027EB9
0x180027f86  cmp     [rbp+cSubKeys], esi
0x180027f89  setnz   cl
0x180027f8c  mov     rax, [rdi+8]
0x180027f90  mov     [rax], cl
0x180027f92  lea     rcx, [rbp+lpSubKey]
0x180027f96  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180027f9b  nop
0x180027f9c  mov     rcx, [rbp+hKey]; hKey
0x180027fa0  test    rcx, rcx
0x180027fa3  jz      short loc_180027FAC
0x180027fa5  call    cs:__imp_RegCloseKey
0x180027fab  nop
0x180027fac  xor     eax, eax
0x180027fae  mov     rbx, [rsp+80h+arg_10]
0x180027fb6  add     rsp, 80h
0x180027fbd  pop     rdi
0x180027fbe  pop     rsi
0x180027fbf  pop     rbp
0x180027fc0  retn
```
