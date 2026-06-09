# GetMiniportsEnabledRegistry

- ea: `0x18009f4dc`
- end: `0x18009f61d`
- name: `GetMiniportsEnabledRegistry`
- size: `321`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config, service_task, installer_update`

## callers

- `0x18009f1e8`
- `0x18009fa1c`

## callees

- `0x18009f4dc`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18009f524`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18009f524`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18009f5f6`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18009f5f6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18009f606`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18009f606`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18009f5c8`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18009f5c8`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18009f56b`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18009f56b`

## string_xrefs

- `0x18009f50f`: `SYSTEM\CurrentControlSet\Services\RasMan\Parameters`
- `0x18009f59b`: `SYSTEM\CurrentControlSet\Services\RasMan\Parameters`
- `0x18009f564`: `MiniportsInstalled`
- `0x18009f5e4`: `MiniportsInstalled`

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
0x18009f4dc  push    rbp
0x18009f4de  push    rbx
0x18009f4df  mov     rbp, rsp
0x18009f4e2  sub     rsp, 58h
0x18009f4e6  lea     rax, [rbp+hKey]
0x18009f4ea  mov     [rbp+hKey], 0
0x18009f4f2  mov     ebx, 4
0x18009f4f7  mov     [rsp+58h+phkResult], rax; phkResult
0x18009f4fc  mov     r9d, 2001Fh; samDesired
0x18009f502  mov     [rbp+Type], ebx
0x18009f505  xor     r8d, r8d; ulOptions
0x18009f508  mov     [rbp+Data], 0FFFFh
0x18009f50f  lea     rdx, SubKey; "SYSTEM\\CurrentControlSet\\Services\\Ra"...
0x18009f516  mov     [rbp+cbData], 0
0x18009f51d  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18009f524  call    cs:__imp_RegOpenKeyExW
0x18009f52b  nop     dword ptr [rax+rax+00h]
0x18009f530  cmp     eax, 491h
0x18009f535  jz      short loc_18009F589
0x18009f537  cmp     eax, 2
0x18009f53a  jz      short loc_18009F589
0x18009f53c  test    eax, eax
0x18009f53e  jnz     loc_18009F602
0x18009f544  mov     rcx, [rbp+hKey]; hKey
0x18009f548  lea     rax, [rbp+cbData]
0x18009f54c  mov     [rsp+58h+lpcbData], rax; lpcbData
0x18009f551  lea     r9, [rbp+Type]; lpType
0x18009f555  lea     rax, [rbp+Data]
0x18009f559  mov     [rbp+cbData], ebx
0x18009f55c  xor     r8d, r8d; lpReserved
0x18009f55f  mov     [rsp+58h+phkResult], rax; lpData
0x18009f564  lea     rdx, aMiniportsinsta; "MiniportsInstalled"
0x18009f56b  call    cs:__imp_RegQueryValueExW
0x18009f572  nop     dword ptr [rax+rax+00h]
0x18009f577  cmp     eax, 2
0x18009f57a  jnz     loc_18009F602
0x18009f580  mov     [rbp+Data], 0FFFFh
0x18009f587  jmp     short loc_18009F5D8
0x18009f589  mov     [rsp+58h+lpdwDisposition], 0; lpdwDisposition
0x18009f592  lea     rax, [rbp+hKey]
0x18009f596  mov     [rsp+58h+var_20], rax; phkResult
0x18009f59b  lea     rdx, SubKey; "SYSTEM\\CurrentControlSet\\Services\\Ra"...
0x18009f5a2  mov     [rsp+58h+lpSecurityAttributes], 0; lpSecurityAttributes
0x18009f5ab  xor     r9d, r9d; lpClass
0x18009f5ae  mov     dword ptr [rsp+58h+lpcbData], 0F003Fh; samDesired
0x18009f5b6  xor     r8d, r8d; Reserved
0x18009f5b9  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18009f5c0  mov     dword ptr [rsp+58h+phkResult], 0; dwOptions
0x18009f5c8  call    cs:__imp_RegCreateKeyExW
0x18009f5cf  nop     dword ptr [rax+rax+00h]
0x18009f5d4  test    eax, eax
0x18009f5d6  jnz     short loc_18009F602
0x18009f5d8  mov     rcx, [rbp+hKey]; hKey
0x18009f5dc  lea     rax, [rbp+Data]
0x18009f5e0  mov     dword ptr [rsp+58h+lpcbData], ebx; cbData
0x18009f5e4  lea     rdx, aMiniportsinsta; "MiniportsInstalled"
0x18009f5eb  mov     r9d, ebx; dwType
0x18009f5ee  mov     [rsp+58h+phkResult], rax; lpData
0x18009f5f3  xor     r8d, r8d; Reserved
0x18009f5f6  call    cs:__imp_RegSetValueExW
0x18009f5fd  nop     dword ptr [rax+rax+00h]
0x18009f602  mov     rcx, [rbp+hKey]; hKey
0x18009f606  call    cs:__imp_RegCloseKey
0x18009f60d  nop     dword ptr [rax+rax+00h]
0x18009f612  mov     eax, [rbp+Data]
0x18009f615  add     rsp, 58h
0x18009f619  pop     rbx
0x18009f61a  pop     rbp
0x18009f61b  retn
```
