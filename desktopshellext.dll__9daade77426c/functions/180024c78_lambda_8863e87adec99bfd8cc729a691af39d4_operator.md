# _lambda_8863e87adec99bfd8cc729a691af39d4_::operator()

- ea: `0x180024c78`
- end: `0x180024d8a`
- name: `_lambda_8863e87adec99bfd8cc729a691af39d4_::operator()`
- size: `274`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180081690`

## callees

- `0x1800108cc`
- `0x180024c78`
- `0x180024d90`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180024cd5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180024d31`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180024d42`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180024d65`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180024d76`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180024cd5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180024d31`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180024d42`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180024d65`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180024d76`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180024cb4`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180024d10`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180024cb4`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180024d10`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall lambda_8863e87adec99bfd8cc729a691af39d4_::operator()(__int64 a1)
{
  HKEY *phkResult; // rax
  LSTATUS v3; // eax
  unsigned int v4; // ebx
  HKEY *v6; // rax
  LSTATUS v7; // eax
  Windows::Internal::AssignedAccess::AssignedAccessConfigStoreV0 *v8; // rcx
  _BYTE *v9; // rbx
  HKEY hKey; // [rsp+40h] [rbp+8h] BYREF
  HKEY v11; // [rsp+48h] [rbp+10h] BYREF

  hKey = 0;
  phkResult = (HKEY *)wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(&hKey);
  v3 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, *(LPCWSTR *)(*(_QWORD *)a1 + 8LL), 0, 0x20019u, phkResult);
  v4 = v3;
  if ( v3 )
  {
    if ( v3 > 0 )
      v4 = (unsigned __int16)v3 | 0x80070000;
    if ( hKey )
      RegCloseKey(hKey);
    return v4;
  }
  v11 = 0;
  v6 = (HKEY *)wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(&v11);
  v7 = RegOpenKeyExW(hKey, **(LPCWSTR **)(a1 + 8), 0, 0x20019u, v6);
  v4 = v7;
  if ( v7 )
  {
    if ( v7 > 0 )
      v4 = (unsigned __int16)v7 | 0x80070000;
    if ( v11 )
      RegCloseKey(v11);
    if ( hKey )
      RegCloseKey(hKey);
    return v4;
  }
  v9 = *(_BYTE **)(a1 + 16);
  *v9 = Windows::Internal::AssignedAccess::AssignedAccessConfigStoreV0::IsValidProfile(v8, v11);
  if ( v11 )
    RegCloseKey(v11);
  if ( hKey )
    RegCloseKey(hKey);
  return 0;
}

```

## disassembly

```asm
0x180024c78  mov     [rsp+arg_10], rbx
0x180024c7d  push    rdi
0x180024c7e  sub     rsp, 30h
0x180024c82  mov     rdi, rcx
0x180024c85  mov     [rsp+38h+hKey], 0
0x180024c8e  lea     rcx, [rsp+38h+hKey]
0x180024c93  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAUHKEY__@@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(void)
0x180024c98  mov     rdx, [rdi]
0x180024c9b  mov     [rsp+38h+phkResult], rax; phkResult
0x180024ca0  mov     r9d, 20019h; samDesired
0x180024ca6  xor     r8d, r8d; ulOptions
0x180024ca9  mov     rdx, [rdx+8]; lpSubKey
0x180024cad  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180024cb4  call    cs:__imp_RegOpenKeyExW
0x180024cba  mov     ebx, eax
0x180024cbc  test    eax, eax
0x180024cbe  jz      short loc_180024CE3
0x180024cc0  jle     short loc_180024CCB
0x180024cc2  movzx   ebx, ax
0x180024cc5  or      ebx, 80070000h
0x180024ccb  mov     rcx, [rsp+38h+hKey]; hKey
0x180024cd0  test    rcx, rcx
0x180024cd3  jz      short loc_180024CDC
0x180024cd5  call    cs:__imp_RegCloseKey
0x180024cdb  nop
0x180024cdc  mov     eax, ebx
0x180024cde  jmp     loc_180024D7F
0x180024ce3  mov     [rsp+38h+arg_8], 0
0x180024cec  lea     rcx, [rsp+38h+arg_8]
0x180024cf1  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAUHKEY__@@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(void)
0x180024cf6  mov     rdx, [rdi+8]
0x180024cfa  mov     [rsp+38h+phkResult], rax; phkResult
0x180024cff  mov     r9d, 20019h; samDesired
0x180024d05  xor     r8d, r8d; ulOptions
0x180024d08  mov     rdx, [rdx]; lpSubKey
0x180024d0b  mov     rcx, [rsp+38h+hKey]; hKey
0x180024d10  call    cs:__imp_RegOpenKeyExW
0x180024d16  mov     ebx, eax
0x180024d18  test    eax, eax
0x180024d1a  jz      short loc_180024D4B
0x180024d1c  jle     short loc_180024D27
0x180024d1e  movzx   ebx, ax
0x180024d21  or      ebx, 80070000h
0x180024d27  mov     rcx, [rsp+38h+arg_8]; hKey
0x180024d2c  test    rcx, rcx
0x180024d2f  jz      short loc_180024D38
0x180024d31  call    cs:__imp_RegCloseKey
0x180024d37  nop
0x180024d38  mov     rcx, [rsp+38h+hKey]; hKey
0x180024d3d  test    rcx, rcx
0x180024d40  jz      short loc_180024D49
0x180024d42  call    cs:__imp_RegCloseKey
0x180024d48  nop
0x180024d49  jmp     short loc_180024CDC
0x180024d4b  mov     rbx, [rdi+10h]
0x180024d4f  mov     rdx, [rsp+38h+arg_8]; HKEY
0x180024d54  call    ?IsValidProfile@AssignedAccessConfigStoreV0@AssignedAccess@Internal@Windows@@AEAA_NPEAUHKEY__@@@Z; Windows::Internal::AssignedAccess::AssignedAccessConfigStoreV0::IsValidProfile(HKEY__ *)
0x180024d59  mov     [rbx], al
0x180024d5b  mov     rcx, [rsp+38h+arg_8]; hKey
0x180024d60  test    rcx, rcx
0x180024d63  jz      short loc_180024D6C
0x180024d65  call    cs:__imp_RegCloseKey
0x180024d6b  nop
0x180024d6c  mov     rcx, [rsp+38h+hKey]; hKey
0x180024d71  test    rcx, rcx
0x180024d74  jz      short loc_180024D7D
0x180024d76  call    cs:__imp_RegCloseKey
0x180024d7c  nop
0x180024d7d  xor     eax, eax
0x180024d7f  mov     rbx, [rsp+38h+arg_10]
0x180024d84  add     rsp, 30h
0x180024d88  pop     rdi
0x180024d89  retn
```
