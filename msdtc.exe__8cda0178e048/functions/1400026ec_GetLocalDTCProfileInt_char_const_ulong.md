# GetLocalDTCProfileInt(char const *,ulong)

- ea: `0x1400026ec`
- end: `0x14000279b`
- name: `?GetLocalDTCProfileInt@@YAKPEBDK@Z`
- size: `175`
- prototype: `__int64 __fastcall(LPCSTR lpValueName)`
- caller_count: `3`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140002494`
- `0x1400025c0`
- `0x1400029f0`

## callees

- `0x1400026ec`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140002787`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140002787`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x14000273d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x14000273d`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x140002767`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x140002767`

## pseudocode

```c
__int64 __fastcall GetLocalDTCProfileInt(LPCSTR lpValueName)
{
  HKEY hKey; // [rsp+30h] [rbp-10h] BYREF
  unsigned int Data; // [rsp+58h] [rbp+18h] BYREF
  DWORD Type; // [rsp+60h] [rbp+20h] BYREF
  DWORD cbData; // [rsp+68h] [rbp+28h] BYREF

  hKey = 0;
  Type = 0;
  Data = 0;
  cbData = 4;
  if ( RegOpenKeyExA(HKEY_LOCAL_MACHINE, "Software\\Microsoft\\MSDTC", 0, 0x20119u, &hKey)
    || RegQueryValueExA(hKey, lpValueName, 0, &Type, (LPBYTE)&Data, &cbData)
    || Type != 4 )
  {
    Data = 0;
  }
  if ( hKey )
    RegCloseKey(hKey);
  return Data;
}

```

## disassembly

```asm
0x1400026ec  mov     [rsp-8+arg_0], rbx
0x1400026f1  mov     [rsp-8+Data], edx
0x1400026f5  push    rbp
0x1400026f6  mov     rbp, rsp
0x1400026f9  sub     rsp, 40h
0x1400026fd  mov     rbx, rcx
0x140002700  mov     [rbp+hKey], 0
0x140002708  lea     rax, [rbp+hKey]
0x14000270c  mov     [rbp+Type], 0
0x140002713  mov     rcx, 0FFFFFFFF80000002h; hKey
0x14000271a  mov     [rsp+40h+phkResult], rax; phkResult
0x14000271f  mov     r9d, 20119h; samDesired
0x140002725  mov     [rbp+Data], 0
0x14000272c  xor     r8d, r8d; ulOptions
0x14000272f  mov     [rbp+cbData], 4
0x140002736  lea     rdx, SubKey; "Software\\Microsoft\\MSDTC"
0x14000273d  call    cs:__imp_RegOpenKeyExA
0x140002743  test    eax, eax
0x140002745  jnz     short loc_140002777
0x140002747  mov     rcx, [rbp+hKey]; hKey
0x14000274b  lea     rax, [rbp+cbData]
0x14000274f  mov     [rsp+40h+lpcbData], rax; lpcbData
0x140002754  lea     r9, [rbp+Type]; lpType
0x140002758  lea     rax, [rbp+Data]
0x14000275c  xor     r8d, r8d; lpReserved
0x14000275f  mov     rdx, rbx; lpValueName
0x140002762  mov     [rsp+40h+phkResult], rax; lpData
0x140002767  call    cs:__imp_RegQueryValueExA
0x14000276d  test    eax, eax
0x14000276f  jnz     short loc_140002777
0x140002771  cmp     [rbp+Type], 4
0x140002775  jz      short loc_14000277E
0x140002777  mov     [rbp+Data], 0
0x14000277e  mov     rcx, [rbp+hKey]; hKey
0x140002782  test    rcx, rcx
0x140002785  jz      short loc_14000278D
0x140002787  call    cs:__imp_RegCloseKey
0x14000278d  mov     eax, [rbp+Data]
0x140002790  mov     rbx, [rsp+40h+arg_0]
0x140002795  add     rsp, 40h
0x140002799  pop     rbp
0x14000279a  retn
```
