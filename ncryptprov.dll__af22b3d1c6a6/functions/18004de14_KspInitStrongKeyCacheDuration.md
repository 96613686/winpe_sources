# KspInitStrongKeyCacheDuration

- ea: `0x18004de14`
- end: `0x18004df08`
- name: `KspInitStrongKeyCacheDuration`
- size: `244`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800096e0`

## callees

- `0x18004de14`

## import_xrefs

- `ntdll!NtClose` at `0x18004def2`
- `ntdll!NtClose` at `0x18004def2`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x18004de5e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x18004de5e`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x18004de91`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x18004dec9`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x18004de91`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x18004dec9`

## string_xrefs

- `0x18004de7b`: `CachePrivateKeys`

## pseudocode

```c
__int64 KspInitStrongKeyCacheDuration()
{
  HKEY hKey; // [rsp+30h] [rbp-10h] BYREF
  unsigned int v2; // [rsp+50h] [rbp+10h] BYREF
  int Data; // [rsp+58h] [rbp+18h] BYREF
  DWORD cbData; // [rsp+60h] [rbp+20h] BYREF
  DWORD lpcbData; // [rsp+68h] [rbp+28h] BYREF

  hKey = 0;
  lpcbData = 4;
  cbData = 4;
  v2 = -1;
  Data = 0;
  if ( !RegOpenKeyExA(HKEY_LOCAL_MACHINE, "Software\\Policies\\Microsoft\\Cryptography", 0, 0x20119u, &hKey)
    && !RegQueryValueExA(hKey, "CachePrivateKeys", 0, 0, (LPBYTE)&Data, &cbData) )
  {
    if ( Data )
    {
      if ( RegQueryValueExA(hKey, "PrivateKeyLifetimeSeconds", 0, 0, (LPBYTE)&v2, &lpcbData) )
        v2 = -1;
    }
    else
    {
      v2 = 0;
    }
  }
  if ( hKey )
    NtClose(hKey);
  return v2;
}

```

## disassembly

```asm
0x18004de14  push    rbp
0x18004de16  mov     rbp, rsp
0x18004de19  sub     rsp, 40h
0x18004de1d  mov     eax, 4
0x18004de22  mov     [rbp+hKey], 0
0x18004de2a  mov     [rbp+arg_18], eax
0x18004de2d  lea     rdx, aSoftwarePolici; "Software\\Policies\\Microsoft\\Cryptogr"...
0x18004de34  mov     [rbp+cbData], eax
0x18004de37  mov     r9d, 20119h; samDesired
0x18004de3d  lea     rax, [rbp+hKey]
0x18004de41  mov     [rbp+arg_0], 0FFFFFFFFh
0x18004de48  xor     r8d, r8d; ulOptions
0x18004de4b  mov     [rsp+40h+phkResult], rax; phkResult
0x18004de50  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18004de57  mov     [rbp+Data], 0
0x18004de5e  call    cs:__imp_RegOpenKeyExA
0x18004de65  nop     dword ptr [rax+rax+00h]
0x18004de6a  test    eax, eax
0x18004de6c  jnz     short loc_18004DEE9
0x18004de6e  mov     rcx, [rbp+hKey]; hKey
0x18004de72  lea     rax, [rbp+cbData]
0x18004de76  mov     [rsp+40h+lpcbData], rax; lpcbData
0x18004de7b  lea     rdx, aCacheprivateke; "CachePrivateKeys"
0x18004de82  lea     rax, [rbp+Data]
0x18004de86  xor     r9d, r9d; lpType
0x18004de89  xor     r8d, r8d; lpReserved
0x18004de8c  mov     [rsp+40h+phkResult], rax; lpData
0x18004de91  call    cs:__imp_RegQueryValueExA
0x18004de98  nop     dword ptr [rax+rax+00h]
0x18004de9d  test    eax, eax
0x18004de9f  jnz     short loc_18004DEE9
0x18004dea1  cmp     [rbp+Data], eax
0x18004dea4  jz      short loc_18004DEE2
0x18004dea6  mov     rcx, [rbp+hKey]; hKey
0x18004deaa  lea     rax, [rbp+arg_18]
0x18004deae  mov     [rsp+40h+lpcbData], rax; lpcbData
0x18004deb3  lea     rdx, aPrivatekeylife; "PrivateKeyLifetimeSeconds"
0x18004deba  lea     rax, [rbp+arg_0]
0x18004debe  xor     r9d, r9d; lpType
0x18004dec1  xor     r8d, r8d; lpReserved
0x18004dec4  mov     [rsp+40h+phkResult], rax; lpData
0x18004dec9  call    cs:__imp_RegQueryValueExA
0x18004ded0  nop     dword ptr [rax+rax+00h]
0x18004ded5  test    eax, eax
0x18004ded7  jz      short loc_18004DEE9
0x18004ded9  mov     [rbp+arg_0], 0FFFFFFFFh
0x18004dee0  jmp     short loc_18004DEE9
0x18004dee2  mov     [rbp+arg_0], 0
0x18004dee9  mov     rcx, [rbp+hKey]; Handle
0x18004deed  test    rcx, rcx
0x18004def0  jz      short loc_18004DEFE
0x18004def2  call    cs:__imp_NtClose
0x18004def9  nop     dword ptr [rax+rax+00h]
0x18004defe  mov     eax, [rbp+arg_0]
0x18004df01  add     rsp, 40h
0x18004df05  pop     rbp
0x18004df06  retn
```
