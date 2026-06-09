# GetMaxNodeCount

- ea: `0x18009ff40`
- end: `0x1800a0013`
- name: `GetMaxNodeCount`
- size: `211`
- prototype: `__int64 __fastcall(LPCWSTR lpMachineName, LPBYTE lpData)`
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18003f114`
- `0x18009ff08`

## callees

- `0x18009ff40`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18009ffbf`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18009fff5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18009ffbf`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18009fff5`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18009ffb3`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18009ffb3`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18009ffe9`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18009ffe9`
- `api-ms-win-core-registry-private-l1-1-0!RegConnectRegistryExW` at `0x18009ff8a`
- `api-ms-win-core-registry-private-l1-1-0!RegConnectRegistryExW` at `0x18009ff8a`

## pseudocode

```c
__int64 __fastcall GetMaxNodeCount(LPCWSTR lpMachineName, LPBYTE lpData)
{
  HKEY v3; // rcx
  unsigned int v5; // ebx
  DWORD Type; // [rsp+50h] [rbp+20h] BYREF
  DWORD cbData; // [rsp+58h] [rbp+28h] BYREF
  HKEY phkResult; // [rsp+60h] [rbp+30h] BYREF
  HKEY hKey; // [rsp+68h] [rbp+38h] BYREF

  cbData = 4;
  Type = 0;
  v3 = HKEY_LOCAL_MACHINE;
  phkResult = HKEY_LOCAL_MACHINE;
  hKey = 0;
  *(_DWORD *)lpData = 0;
  if ( lpMachineName )
  {
    v5 = RegConnectRegistryExW(lpMachineName, HKEY_LOCAL_MACHINE, 0, &phkResult);
    if ( v5 )
      return v5;
    v3 = phkResult;
  }
  v5 = RegOpenKeyExW(v3, L"Software\\Microsoft\\Windows NT\\CurrentVersion\\Failover Clusters", 0, 1u, &hKey);
  RegCloseKey(phkResult);
  if ( !v5 )
  {
    v5 = RegQueryValueExW(hKey, L"MaxLicensedNodes", 0, &Type, lpData, &cbData);
    RegCloseKey(hKey);
    if ( !v5 && Type != 4 )
      return 13;
  }
  return v5;
}

```

## disassembly

```asm
0x18009ff40  push    rbp
0x18009ff42  push    rbx
0x18009ff43  push    rdi
0x18009ff44  mov     rbp, rsp
0x18009ff47  sub     rsp, 30h
0x18009ff4b  mov     rax, rcx
0x18009ff4e  mov     [rbp+cbData], 4
0x18009ff55  mov     [rbp+Type], 0
0x18009ff5c  mov     rcx, 0FFFFFFFF80000002h
0x18009ff63  mov     [rbp+phkResult], rcx
0x18009ff67  mov     rdi, rdx
0x18009ff6a  mov     [rbp+hKey], 0
0x18009ff72  mov     dword ptr [rdx], 0
0x18009ff78  test    rax, rax
0x18009ff7b  jz      short loc_18009FF9A
0x18009ff7d  mov     rdx, rcx; hKey
0x18009ff80  lea     r9, [rbp+phkResult]; phkResult
0x18009ff84  mov     rcx, rax; lpMachineName
0x18009ff87  xor     r8d, r8d; Flags
0x18009ff8a  call    cs:__imp_RegConnectRegistryExW
0x18009ff90  mov     ebx, eax
0x18009ff92  test    eax, eax
0x18009ff94  jnz     short loc_1800A0009
0x18009ff96  mov     rcx, [rbp+phkResult]; hKey
0x18009ff9a  lea     rax, [rbp+hKey]
0x18009ff9e  mov     r9d, 1; samDesired
0x18009ffa4  xor     r8d, r8d; ulOptions
0x18009ffa7  mov     [rsp+30h+var_10], rax; phkResult
0x18009ffac  lea     rdx, aSoftwareMicros; "Software\\Microsoft\\Windows NT\\Curren"...
0x18009ffb3  call    cs:__imp_RegOpenKeyExW
0x18009ffb9  mov     rcx, [rbp+phkResult]; hKey
0x18009ffbd  mov     ebx, eax
0x18009ffbf  call    cs:__imp_RegCloseKey
0x18009ffc5  test    ebx, ebx
0x18009ffc7  jnz     short loc_1800A0009
0x18009ffc9  mov     rcx, [rbp+hKey]; hKey
0x18009ffcd  lea     rax, [rbp+cbData]
0x18009ffd1  mov     [rsp+30h+lpcbData], rax; lpcbData
0x18009ffd6  lea     r9, [rbp+Type]; lpType
0x18009ffda  xor     r8d, r8d; lpReserved
0x18009ffdd  mov     [rsp+30h+var_10], rdi; lpData
0x18009ffe2  lea     rdx, aMaxlicensednod; "MaxLicensedNodes"
0x18009ffe9  call    cs:__imp_RegQueryValueExW
0x18009ffef  mov     rcx, [rbp+hKey]; hKey
0x18009fff3  mov     ebx, eax
0x18009fff5  call    cs:__imp_RegCloseKey
0x18009fffb  test    ebx, ebx
0x18009fffd  jnz     short loc_1800A0009
0x18009ffff  cmp     [rbp+Type], 4
0x1800a0003  lea     eax, [rbx+0Dh]
0x1800a0006  cmovnz  ebx, eax
0x1800a0009  mov     eax, ebx
0x1800a000b  add     rsp, 30h
0x1800a000f  pop     rdi
0x1800a0010  pop     rbx
0x1800a0011  pop     rbp
0x1800a0012  retn
```
