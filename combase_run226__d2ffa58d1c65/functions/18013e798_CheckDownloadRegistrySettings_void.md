# CheckDownloadRegistrySettings(void)

- ea: `0x18013e798`
- end: `0x18013e894`
- name: `?CheckDownloadRegistrySettings@@YAKXZ`
- size: `252`
- prototype: `unsigned int __fastcall()`
- caller_count: `3`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180133d6c`
- `0x18015cf90`
- `0x1801d57e4`

## callees

- `0x18013e798`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18013e86e`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18024e6b4`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18013e86e`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18024e6b4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18024e6d7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18024e6ee`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18024e6d7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18024e6ee`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18013e7ec`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18013e82a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18013e7ec`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18013e82a`

## string_xrefs

- `0x18013e867`: `COMClassStore`
- `0x18024e6ad`: `COMClassStore`

## pseudocode

```c
__int64 __fastcall CheckDownloadRegistrySettings()
{
  unsigned int dwSize; // [rsp+40h] [rbp+10h] BYREF
  unsigned int dwType; // [rsp+48h] [rbp+18h] BYREF
  unsigned int dwCSEnabledForMachine; // [rsp+50h] [rbp+20h] BYREF
  HKEY__ *hKeyAppMgmt; // [rsp+58h] [rbp+28h] BYREF

  if ( !fInitialized )
  {
    dwType = 0;
    dwSize = 0;
    hKeyAppMgmt = 0;
    if ( !RegOpenKeyExW(
            HKEY_CURRENT_USER,
            L"Software\\Policies\\Microsoft\\Windows\\App Management",
            0,
            1u,
            &hKeyAppMgmt) )
    {
      dwSize = 4;
      if ( RegQueryValueExW(hKeyAppMgmt, L"COMClassStore", 0, &dwType, (LPBYTE)&dwCSEnabled, &dwSize)
        || dwType != 4
        || !dwSize )
      {
        dwCSEnabled = 0;
      }
      RegCloseKey(hKeyAppMgmt);
    }
    if ( !dwCSEnabled )
    {
      dwCSEnabledForMachine = 0;
      if ( !RegOpenKeyExW(
              HKEY_LOCAL_MACHINE,
              L"Software\\Policies\\Microsoft\\Windows\\App Management",
              0,
              1u,
              &hKeyAppMgmt) )
      {
        dwSize = 4;
        if ( RegQueryValueExW(hKeyAppMgmt, L"COMClassStore", 0, &dwType, (LPBYTE)&dwCSEnabledForMachine, &dwSize)
          || dwType != 4
          || !dwSize )
        {
          dwCSEnabledForMachine = 0;
        }
        RegCloseKey(hKeyAppMgmt);
        if ( dwCSEnabledForMachine )
          dwCSEnabled = dwCSEnabledForMachine;
      }
    }
    fInitialized = 1;
  }
  return dwCSEnabled;
}

```

## disassembly

```asm
0x18013e798  push    rbp
0x18013e79a  mov     rbp, rsp
0x18013e79d  sub     rsp, 30h
0x18013e7a1  cmp     cs:fInitialized, 0
0x18013e7a8  jz      short loc_18013E7B6
0x18013e7aa  mov     eax, cs:dwCSEnabled
0x18013e7b0  add     rsp, 30h
0x18013e7b4  pop     rbp
0x18013e7b5  retn
0x18013e7b6  lea     rax, [rbp+hKeyAppMgmt]
0x18013e7ba  mov     [rbp+dwType], 0
0x18013e7c1  mov     r9d, 1; samDesired
0x18013e7c7  mov     [rsp+30h+phkResult], rax; phkResult
0x18013e7cc  xor     r8d, r8d; ulOptions
0x18013e7cf  mov     [rbp+dwSize], 0
0x18013e7d6  lea     rdx, aSoftwarePolici; "Software\\Policies\\Microsoft\\Windows"...
0x18013e7dd  mov     [rbp+hKeyAppMgmt], 0
0x18013e7e5  mov     rcx, 0FFFFFFFF80000001h; hKey
0x18013e7ec  call    cs:__imp_RegOpenKeyExW
0x18013e7f2  test    eax, eax
0x18013e7f4  jz      loc_18024E686
0x18013e7fa  cmp     cs:dwCSEnabled, 0
0x18013e801  jnz     short loc_18013E834
0x18013e803  lea     rax, [rbp+hKeyAppMgmt]
0x18013e807  mov     [rbp+dwCSEnabledForMachine], 0
0x18013e80e  mov     r9d, 1; samDesired
0x18013e814  mov     [rsp+30h+phkResult], rax; phkResult
0x18013e819  xor     r8d, r8d; ulOptions
0x18013e81c  lea     rdx, aSoftwarePolici; "Software\\Policies\\Microsoft\\Windows"...
0x18013e823  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18013e82a  call    cs:__imp_RegOpenKeyExW
0x18013e830  test    eax, eax
0x18013e832  jz      short loc_18013E843
0x18013e834  mov     cs:fInitialized, 1
0x18013e83e  jmp     loc_18013E7AA
0x18013e843  mov     rcx, [rbp+hKeyAppMgmt]; hKey
0x18013e847  lea     rax, [rbp+dwSize]
0x18013e84b  mov     [rsp+30h+lpcbData], rax; lpcbData
0x18013e850  lea     r9, [rbp+dwType]; lpType
0x18013e854  lea     rax, [rbp+dwCSEnabledForMachine]
0x18013e858  mov     [rbp+dwSize], 4
0x18013e85f  xor     r8d, r8d; lpReserved
0x18013e862  mov     [rsp+30h+phkResult], rax; lpData
0x18013e867  lea     rdx, aComclassstore; "COMClassStore"
0x18013e86e  call    cs:__imp_RegQueryValueExW
0x18013e874  test    eax, eax
0x18013e876  jnz     loc_18024E6E3
0x18013e87c  cmp     [rbp+dwType], 4
0x18013e880  jnz     loc_18024E6E3
0x18013e886  cmp     [rbp+dwSize], eax
0x18013e889  jz      loc_18024E6E3
0x18013e88f  jmp     loc_18024E6EA
0x18024e686  mov     rcx, [rbp+hKeyAppMgmt]; hKey
0x18024e68a  lea     rax, [rbp+dwSize]
0x18024e68e  mov     [rsp+30h+lpcbData], rax; lpcbData
0x18024e693  lea     r9, [rbp+dwType]; lpType
0x18024e697  lea     rax, dwCSEnabled
0x18024e69e  mov     [rbp+dwSize], 4
0x18024e6a5  xor     r8d, r8d; lpReserved
0x18024e6a8  mov     [rsp+30h+phkResult], rax; lpData
0x18024e6ad  lea     rdx, aComclassstore; "COMClassStore"
0x18024e6b4  call    cs:__imp_RegQueryValueExW
0x18024e6ba  test    eax, eax
0x18024e6bc  jnz     short loc_18024E6C9
0x18024e6be  cmp     [rbp+dwType], 4
0x18024e6c2  jnz     short loc_18024E6C9
0x18024e6c4  cmp     [rbp+dwSize], eax
0x18024e6c7  jnz     short loc_18024E6D3
0x18024e6c9  mov     cs:dwCSEnabled, 0
0x18024e6d3  mov     rcx, [rbp+hKeyAppMgmt]; hKey
0x18024e6d7  call    cs:__imp_RegCloseKey
0x18024e6dd  nop
0x18024e6de  jmp     loc_18013E7FA
0x18024e6e3  mov     [rbp+dwCSEnabledForMachine], 0
0x18024e6ea  mov     rcx, [rbp+hKeyAppMgmt]; hKey
0x18024e6ee  call    cs:__imp_RegCloseKey
0x18024e6f4  mov     eax, [rbp+dwCSEnabledForMachine]
0x18024e6f7  test    eax, eax
0x18024e6f9  jz      loc_18013E834
0x18024e6ff  mov     cs:dwCSEnabled, eax
0x18024e705  jmp     loc_18013E834
```
