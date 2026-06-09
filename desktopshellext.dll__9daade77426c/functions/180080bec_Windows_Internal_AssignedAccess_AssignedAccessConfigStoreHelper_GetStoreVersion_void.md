# Windows::Internal::AssignedAccess::AssignedAccessConfigStoreHelper::GetStoreVersion(void)

- ea: `0x180080bec`
- end: `0x180080ca7`
- name: `?GetStoreVersion@AssignedAccessConfigStoreHelper@AssignedAccess@Internal@Windows@@AEAAKXZ`
- size: `187`
- prototype: `unsigned int __fastcall(Windows::Internal::AssignedAccess::AssignedAccessConfigStoreHelper *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180080cbc`

## callees

- `0x1800108cc`
- `0x180080bec`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180080c67`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180080c67`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180080c83`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180080c97`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180080c83`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180080c97`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180080c22`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180080c22`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::Internal::AssignedAccess::AssignedAccessConfigStoreHelper::GetStoreVersion(LPCWSTR *this)
{
  HKEY *phkResult; // rax
  unsigned int v3; // ebx
  DWORD Type; // [rsp+50h] [rbp+18h] BYREF
  unsigned int Data; // [rsp+58h] [rbp+20h] BYREF
  DWORD cbData; // [rsp+60h] [rbp+28h] BYREF
  HKEY hKey; // [rsp+68h] [rbp+30h] BYREF

  hKey = 0;
  phkResult = (HKEY *)wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(&hKey);
  if ( RegOpenKeyExW(HKEY_LOCAL_MACHINE, *this, 0, 0x20019u, phkResult)
    || (Type = 0, Data = 0, cbData = 4, RegQueryValueExW(hKey, L"Version", 0, &Type, (LPBYTE)&Data, &cbData))
    || Type != 4 )
  {
    if ( hKey )
      RegCloseKey(hKey);
    return 0;
  }
  else
  {
    v3 = Data;
    if ( hKey )
      RegCloseKey(hKey);
    return v3;
  }
}

```

## disassembly

```asm
0x180080bec  push    rbp
0x180080bee  push    rbx
0x180080bef  mov     rbp, rsp
0x180080bf2  sub     rsp, 38h
0x180080bf6  mov     rbx, rcx
0x180080bf9  mov     [rbp+hKey], 0
0x180080c01  lea     rcx, [rbp+hKey]
0x180080c05  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAUHKEY__@@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(void)
0x180080c0a  mov     [rsp+38h+phkResult], rax; phkResult
0x180080c0f  mov     r9d, 20019h; samDesired
0x180080c15  xor     r8d, r8d; ulOptions
0x180080c18  mov     rdx, [rbx]; lpSubKey
0x180080c1b  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180080c22  call    cs:__imp_RegOpenKeyExW
0x180080c28  test    eax, eax
0x180080c2a  jz      short loc_180080C2E
0x180080c2c  jmp     short loc_180080C8E
0x180080c2e  mov     [rbp+Type], 0
0x180080c35  mov     [rbp+Data], 0
0x180080c3c  mov     [rbp+cbData], 4
0x180080c43  lea     rax, [rbp+cbData]
0x180080c47  mov     [rsp+38h+lpcbData], rax; lpcbData
0x180080c4c  lea     rax, [rbp+Data]
0x180080c50  mov     [rsp+38h+phkResult], rax; lpData
0x180080c55  lea     r9, [rbp+Type]; lpType
0x180080c59  xor     r8d, r8d; lpReserved
0x180080c5c  lea     rdx, aVersion; "Version"
0x180080c63  mov     rcx, [rbp+hKey]; hKey
0x180080c67  call    cs:__imp_RegQueryValueExW
0x180080c6d  test    eax, eax
0x180080c6f  jnz     short loc_180080C8E
0x180080c71  cmp     [rbp+Type], 4
0x180080c75  jnz     short loc_180080C8E
0x180080c77  mov     ebx, [rbp+Data]
0x180080c7a  mov     rcx, [rbp+hKey]; hKey
0x180080c7e  test    rcx, rcx
0x180080c81  jz      short loc_180080C8A
0x180080c83  call    cs:__imp_RegCloseKey
0x180080c89  nop
0x180080c8a  mov     eax, ebx
0x180080c8c  jmp     short loc_180080CA0
0x180080c8e  mov     rcx, [rbp+hKey]; hKey
0x180080c92  test    rcx, rcx
0x180080c95  jz      short loc_180080C9E
0x180080c97  call    cs:__imp_RegCloseKey
0x180080c9d  nop
0x180080c9e  xor     eax, eax
0x180080ca0  add     rsp, 38h
0x180080ca4  pop     rbx
0x180080ca5  pop     rbp
0x180080ca6  retn
```
