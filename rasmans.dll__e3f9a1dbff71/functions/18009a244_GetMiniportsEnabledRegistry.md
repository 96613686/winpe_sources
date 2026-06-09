# GetMiniportsEnabledRegistry

- ea: `0x18009a244`
- end: `0x18009a362`
- name: `GetMiniportsEnabledRegistry`
- size: `286`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config, service_task, installer_update`

## callers

- `0x180099f60`
- `0x18009a6f0`

## callees

- `0x18009a244`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18009a2cd`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18009a2cd`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18009a28c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18009a28c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18009a352`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18009a352`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18009a348`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18009a348`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18009a320`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18009a320`

## string_xrefs

- `0x18009a277`: `SYSTEM\CurrentControlSet\Services\RasMan\Parameters`
- `0x18009a2f3`: `SYSTEM\CurrentControlSet\Services\RasMan\Parameters`
- `0x18009a2c6`: `MiniportsInstalled`
- `0x18009a336`: `MiniportsInstalled`

## pseudocode

```c
__int64 GetMiniportsEnabledRegistry()
{
  LSTATUS v0; // eax
  unsigned int Data; // [rsp+70h] [rbp+18h] BYREF
  DWORD cbData; // [rsp+78h] [rbp+20h] BYREF
  DWORD Type; // [rsp+80h] [rbp+28h] BYREF
  HKEY hKey; // [rsp+88h] [rbp+30h] BYREF

  hKey = 0;
  Type = 4;
  Data = 0xFFFF;
  cbData = 0;
  v0 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SYSTEM\\CurrentControlSet\\Services\\RasMan\\Parameters", 0, 0x2001Fu, &hKey);
  if ( v0 == 1169 || v0 == 2 )
  {
    if ( !RegCreateKeyExW(
            HKEY_LOCAL_MACHINE,
            L"SYSTEM\\CurrentControlSet\\Services\\RasMan\\Parameters",
            0,
            0,
            0,
            0xF003Fu,
            0,
            &hKey,
            0) )
      goto LABEL_7;
  }
  else if ( !v0 )
  {
    cbData = 4;
    if ( RegQueryValueExW(hKey, L"MiniportsInstalled", 0, &Type, (LPBYTE)&Data, &cbData) == 2 )
    {
      Data = 0xFFFF;
LABEL_7:
      RegSetValueExW(hKey, L"MiniportsInstalled", 0, 4u, (const BYTE *)&Data, 4u);
    }
  }
  RegCloseKey(hKey);
  return Data;
}

```

## disassembly

```asm
0x18009a244  push    rbp
0x18009a246  push    rbx
0x18009a247  mov     rbp, rsp
0x18009a24a  sub     rsp, 58h
0x18009a24e  lea     rax, [rbp+hKey]
0x18009a252  mov     [rbp+hKey], 0
0x18009a25a  mov     ebx, 4
0x18009a25f  mov     [rsp+58h+phkResult], rax; phkResult
0x18009a264  mov     r9d, 2001Fh; samDesired
0x18009a26a  mov     [rbp+Type], ebx
0x18009a26d  xor     r8d, r8d; ulOptions
0x18009a270  mov     [rbp+Data], 0FFFFh
0x18009a277  lea     rdx, SubKey; "SYSTEM\\CurrentControlSet\\Services\\Ra"...
0x18009a27e  mov     [rbp+cbData], 0
0x18009a285  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18009a28c  call    cs:__imp_RegOpenKeyExW
0x18009a292  cmp     eax, 491h
0x18009a297  jz      short loc_18009A2E1
0x18009a299  cmp     eax, 2
0x18009a29c  jz      short loc_18009A2E1
0x18009a29e  test    eax, eax
0x18009a2a0  jnz     loc_18009A34E
0x18009a2a6  mov     rcx, [rbp+hKey]; hKey
0x18009a2aa  lea     rax, [rbp+cbData]
0x18009a2ae  mov     [rsp+58h+lpcbData], rax; lpcbData
0x18009a2b3  lea     r9, [rbp+Type]; lpType
0x18009a2b7  lea     rax, [rbp+Data]
0x18009a2bb  mov     [rbp+cbData], ebx
0x18009a2be  xor     r8d, r8d; lpReserved
0x18009a2c1  mov     [rsp+58h+phkResult], rax; lpData
0x18009a2c6  lea     rdx, aMiniportsinsta; "MiniportsInstalled"
0x18009a2cd  call    cs:__imp_RegQueryValueExW
0x18009a2d3  cmp     eax, 2
0x18009a2d6  jnz     short loc_18009A34E
0x18009a2d8  mov     [rbp+Data], 0FFFFh
0x18009a2df  jmp     short loc_18009A32A
0x18009a2e1  mov     [rsp+58h+lpdwDisposition], 0; lpdwDisposition
0x18009a2ea  lea     rax, [rbp+hKey]
0x18009a2ee  mov     [rsp+58h+var_20], rax; phkResult
0x18009a2f3  lea     rdx, SubKey; "SYSTEM\\CurrentControlSet\\Services\\Ra"...
0x18009a2fa  mov     [rsp+58h+lpSecurityAttributes], 0; lpSecurityAttributes
0x18009a303  xor     r9d, r9d; lpClass
0x18009a306  mov     dword ptr [rsp+58h+lpcbData], 0F003Fh; samDesired
0x18009a30e  xor     r8d, r8d; Reserved
0x18009a311  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18009a318  mov     dword ptr [rsp+58h+phkResult], 0; dwOptions
0x18009a320  call    cs:__imp_RegCreateKeyExW
0x18009a326  test    eax, eax
0x18009a328  jnz     short loc_18009A34E
0x18009a32a  mov     rcx, [rbp+hKey]; hKey
0x18009a32e  lea     rax, [rbp+Data]
0x18009a332  mov     dword ptr [rsp+58h+lpcbData], ebx; cbData
0x18009a336  lea     rdx, aMiniportsinsta; "MiniportsInstalled"
0x18009a33d  mov     r9d, ebx; dwType
0x18009a340  mov     [rsp+58h+phkResult], rax; lpData
0x18009a345  xor     r8d, r8d; Reserved
0x18009a348  call    cs:__imp_RegSetValueExW
0x18009a34e  mov     rcx, [rbp+hKey]; hKey
0x18009a352  call    cs:__imp_RegCloseKey
0x18009a358  mov     eax, [rbp+Data]
0x18009a35b  add     rsp, 58h
0x18009a35f  pop     rbx
0x18009a360  pop     rbp
0x18009a361  retn
```
