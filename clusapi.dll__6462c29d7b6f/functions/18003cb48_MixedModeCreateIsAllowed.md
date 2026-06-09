# MixedModeCreateIsAllowed

- ea: `0x18003cb48`
- end: `0x18003cbd4`
- name: `MixedModeCreateIsAllowed`
- size: `140`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config, service_task`

## callers

- `0x18003b410`
- `0x18003b5c8`

## callees

- `0x18003cb48`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003cbc6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003cbc6`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003cb7a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003cb7a`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18003cbb6`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18003cbb6`

## string_xrefs

- `0x18003cb6a`: `SYSTEM\CurrentControlSet\Services\ClusSvc\Parameters`
- `0x18003cb89`: `CreateInMixedMode`

## pseudocode

```c
bool MixedModeCreateIsAllowed()
{
  bool v0; // bl
  DWORD cbData; // [rsp+40h] [rbp+8h] BYREF
  int Data; // [rsp+48h] [rbp+10h] BYREF
  HKEY hKey; // [rsp+50h] [rbp+18h] BYREF

  hKey = 0;
  v0 = 0;
  if ( !RegOpenKeyExW(
          HKEY_LOCAL_MACHINE,
          L"SYSTEM\\CurrentControlSet\\Services\\ClusSvc\\Parameters",
          0,
          0x20019u,
          &hKey) )
  {
    Data = 0;
    cbData = 4;
    v0 = RegQueryValueExW(hKey, L"CreateInMixedMode", 0, 0, (LPBYTE)&Data, &cbData) == 0;
    RegCloseKey(hKey);
  }
  return v0;
}

```

## disassembly

```asm
0x18003cb48  push    rbx
0x18003cb4a  sub     rsp, 30h
0x18003cb4e  lea     rax, [rsp+38h+hKey]
0x18003cb53  mov     [rsp+38h+hKey], 0
0x18003cb5c  mov     r9d, 20019h; samDesired
0x18003cb62  mov     [rsp+38h+phkResult], rax; phkResult
0x18003cb67  xor     r8d, r8d; ulOptions
0x18003cb6a  lea     rdx, SubKey; "SYSTEM\\CurrentControlSet\\Services\\Cl"...
0x18003cb71  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18003cb78  xor     bl, bl
0x18003cb7a  call    cs:__imp_RegOpenKeyExW
0x18003cb80  test    eax, eax
0x18003cb82  jnz     short loc_18003CBCC
0x18003cb84  mov     rcx, [rsp+38h+hKey]; hKey
0x18003cb89  lea     rdx, aCreateinmixedm; "CreateInMixedMode"
0x18003cb90  mov     [rsp+38h+Data], eax
0x18003cb94  xor     r9d, r9d; lpType
0x18003cb97  lea     rax, [rsp+38h+cbData]
0x18003cb9c  mov     [rsp+38h+cbData], 4
0x18003cba4  mov     [rsp+38h+lpcbData], rax; lpcbData
0x18003cba9  xor     r8d, r8d; lpReserved
0x18003cbac  lea     rax, [rsp+38h+Data]
0x18003cbb1  mov     [rsp+38h+phkResult], rax; lpData
0x18003cbb6  call    cs:__imp_RegQueryValueExW
0x18003cbbc  mov     rcx, [rsp+38h+hKey]; hKey
0x18003cbc1  test    eax, eax
0x18003cbc3  setz    bl
0x18003cbc6  call    cs:__imp_RegCloseKey
0x18003cbcc  mov     al, bl
0x18003cbce  add     rsp, 30h
0x18003cbd2  pop     rbx
0x18003cbd3  retn
```
