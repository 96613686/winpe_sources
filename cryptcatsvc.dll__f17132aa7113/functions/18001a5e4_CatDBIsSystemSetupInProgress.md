# _CatDBIsSystemSetupInProgress

- ea: `0x18001a5e4`
- end: `0x18001a68d`
- name: `_CatDBIsSystemSetupInProgress`
- size: `169`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, installer_update`

## callers

- `0x180019e84`

## callees

- `0x18000be40`
- `0x18001a5e4`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001a631`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001a631`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001a66c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001a66c`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001a661`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001a661`

## pseudocode

```c
_BOOL8 CatDBIsSystemSetupInProgress()
{
  HKEY hKey; // [rsp+30h] [rbp-28h] BYREF
  BYTE Data[4]; // [rsp+38h] [rbp-20h] BYREF
  DWORD cbData; // [rsp+3Ch] [rbp-1Ch] BYREF

  hKey = 0;
  *(_DWORD *)Data = 0;
  cbData = 4;
  if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"System\\Setup", 0, 1u, &hKey) )
  {
    RegQueryValueExW(hKey, L"SystemSetupInProgress", 0, 0, Data, &cbData);
    RegCloseKey(hKey);
  }
  return *(_DWORD *)Data != 0;
}

```

## disassembly

```asm
0x18001a5e4  sub     rsp, 58h
0x18001a5e8  mov     rax, cs:__security_cookie
0x18001a5ef  xor     rax, rsp
0x18001a5f2  mov     [rsp+58h+var_18], rax
0x18001a5f7  lea     rax, [rsp+58h+hKey]
0x18001a5fc  mov     [rsp+58h+hKey], 0
0x18001a605  mov     r9d, 1; samDesired
0x18001a60b  mov     [rsp+58h+phkResult], rax; phkResult
0x18001a610  xor     r8d, r8d; ulOptions
0x18001a613  mov     dword ptr [rsp+58h+Data], 0
0x18001a61b  lea     rdx, aSystemSetup; "System\\Setup"
0x18001a622  mov     [rsp+58h+cbData], 4
0x18001a62a  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18001a631  call    cs:__imp_RegOpenKeyExW
0x18001a637  test    eax, eax
0x18001a639  jnz     short loc_18001A672
0x18001a63b  mov     rcx, [rsp+58h+hKey]; hKey
0x18001a640  lea     rax, [rsp+58h+cbData]
0x18001a645  mov     [rsp+58h+lpcbData], rax; lpcbData
0x18001a64a  lea     rdx, ValueName; "SystemSetupInProgress"
0x18001a651  lea     rax, [rsp+58h+Data]
0x18001a656  xor     r9d, r9d; lpType
0x18001a659  xor     r8d, r8d; lpReserved
0x18001a65c  mov     [rsp+58h+phkResult], rax; lpData
0x18001a661  call    cs:__imp_RegQueryValueExW
0x18001a667  mov     rcx, [rsp+58h+hKey]; hKey
0x18001a66c  call    cs:__imp_RegCloseKey
0x18001a672  xor     eax, eax
0x18001a674  cmp     dword ptr [rsp+58h+Data], eax
0x18001a678  setnz   al
0x18001a67b  mov     rcx, [rsp+58h+var_18]
0x18001a680  xor     rcx, rsp; StackCookie
0x18001a683  call    __security_check_cookie
0x18001a688  add     rsp, 58h
0x18001a68c  retn
```
