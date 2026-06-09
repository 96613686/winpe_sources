# WriteValueToRegistry(ushort const *,ushort const *,ushort const *,ulong)

- ea: `0x18000f3d0`
- end: `0x18000f45e`
- name: `?WriteValueToRegistry@@YAKPEBG00K@Z`
- size: `142`
- prototype: `unsigned int __fastcall(LPCWSTR lpSubKey, LPCWSTR lpValueName, BYTE *lpData, DWORD cbData)`
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x18000ba98`
- `0x180024608`

## callees

- `0x18000f3d0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f436`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f44b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f436`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f44b`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000f42c`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000f42c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000f408`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000f408`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000f443`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000f443`

## pseudocode

```c
__int64 __fastcall WriteValueToRegistry(LPCWSTR lpSubKey, LPCWSTR lpValueName, BYTE *lpData, DWORD cbData)
{
  DWORD LastError; // ebx
  HKEY hKey; // [rsp+30h] [rbp-38h] BYREF

  hKey = 0;
  if ( RegOpenKeyExW(HKEY_LOCAL_MACHINE, lpSubKey, 0, 2u, &hKey) )
  {
    return GetLastError();
  }
  else
  {
    LastError = 0;
    if ( RegSetValueExW(hKey, lpValueName, 0, 1u, lpData, cbData) )
      LastError = GetLastError();
    RegCloseKey(hKey);
  }
  return LastError;
}

```

## disassembly

```asm
0x18000f3d0  push    rbx
0x18000f3d2  push    rbp
0x18000f3d3  push    rsi
0x18000f3d4  push    rdi
0x18000f3d5  sub     rsp, 48h
0x18000f3d9  mov     rbp, rdx
0x18000f3dc  mov     [rsp+68h+hKey], 0
0x18000f3e5  mov     rdx, rcx; lpSubKey
0x18000f3e8  lea     rax, [rsp+68h+hKey]
0x18000f3ed  mov     edi, r9d
0x18000f3f0  mov     [rsp+68h+phkResult], rax; phkResult
0x18000f3f5  mov     rsi, r8
0x18000f3f8  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000f3ff  mov     r9d, 2; samDesired
0x18000f405  xor     r8d, r8d; ulOptions
0x18000f408  call    cs:__imp_RegOpenKeyExW
0x18000f40e  test    eax, eax
0x18000f410  jnz     short loc_18000F44B
0x18000f412  mov     rcx, [rsp+68h+hKey]; hKey
0x18000f417  lea     r9d, [rax+1]; dwType
0x18000f41b  mov     [rsp+68h+cbData], edi; cbData
0x18000f41f  xor     r8d, r8d; Reserved
0x18000f422  mov     rdx, rbp; lpValueName
0x18000f425  mov     [rsp+68h+phkResult], rsi; lpData
0x18000f42a  xor     ebx, ebx
0x18000f42c  call    cs:__imp_RegSetValueExW
0x18000f432  test    eax, eax
0x18000f434  jz      short loc_18000F43E
0x18000f436  call    cs:__imp_GetLastError
0x18000f43c  mov     ebx, eax
0x18000f43e  mov     rcx, [rsp+68h+hKey]; hKey
0x18000f443  call    cs:__imp_RegCloseKey
0x18000f449  jmp     short loc_18000F453
0x18000f44b  call    cs:__imp_GetLastError
0x18000f451  mov     ebx, eax
0x18000f453  mov     eax, ebx
0x18000f455  add     rsp, 48h
0x18000f459  pop     rdi
0x18000f45a  pop     rsi
0x18000f45b  pop     rbp
0x18000f45c  pop     rbx
0x18000f45d  retn
```
