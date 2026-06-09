# GetMiniportsEnabledRegistry

- ea: `0x180046534`
- end: `0x180046652`
- name: `GetMiniportsEnabledRegistry`
- size: `286`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config, service_task, installer_update`

## callers

- `0x180046254`
- `0x1800469b0`

## callees

- `0x180046534`

## import_xrefs

- `ADVAPI32!RegOpenKeyExW` at `0x18004657c`
- `ADVAPI32!RegOpenKeyExW` at `0x18004657c`
- `ADVAPI32!RegSetValueExW` at `0x180046638`
- `ADVAPI32!RegSetValueExW` at `0x180046638`
- `ADVAPI32!RegCloseKey` at `0x180046642`
- `ADVAPI32!RegCloseKey` at `0x180046642`
- `ADVAPI32!RegQueryValueExW` at `0x1800465bd`
- `ADVAPI32!RegQueryValueExW` at `0x1800465bd`
- `ADVAPI32!RegCreateKeyExW` at `0x180046610`
- `ADVAPI32!RegCreateKeyExW` at `0x180046610`

## string_xrefs

- `0x180046567`: `SYSTEM\CurrentControlSet\Services\RasMan\Parameters`
- `0x1800465e3`: `SYSTEM\CurrentControlSet\Services\RasMan\Parameters`
- `0x1800465b6`: `MiniportsInstalled`
- `0x180046626`: `MiniportsInstalled`

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
0x180046534  push    rbp
0x180046536  push    rbx
0x180046537  mov     rbp, rsp
0x18004653a  sub     rsp, 58h
0x18004653e  lea     rax, [rbp+hKey]
0x180046542  mov     [rbp+hKey], 0
0x18004654a  mov     ebx, 4
0x18004654f  mov     [rsp+58h+phkResult], rax; phkResult
0x180046554  mov     r9d, 2001Fh; samDesired
0x18004655a  mov     [rbp+Type], ebx
0x18004655d  xor     r8d, r8d; ulOptions
0x180046560  mov     [rbp+Data], 0FFFFh
0x180046567  lea     rdx, aSystemCurrentc; "SYSTEM\\CurrentControlSet\\Services\\Ra"...
0x18004656e  mov     [rbp+cbData], 0
0x180046575  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18004657c  call    cs:__imp_RegOpenKeyExW
0x180046582  cmp     eax, 491h
0x180046587  jz      short loc_1800465D1
0x180046589  cmp     eax, 2
0x18004658c  jz      short loc_1800465D1
0x18004658e  test    eax, eax
0x180046590  jnz     loc_18004663E
0x180046596  mov     rcx, [rbp+hKey]; hKey
0x18004659a  lea     rax, [rbp+cbData]
0x18004659e  mov     [rsp+58h+lpcbData], rax; lpcbData
0x1800465a3  lea     r9, [rbp+Type]; lpType
0x1800465a7  lea     rax, [rbp+Data]
0x1800465ab  mov     [rbp+cbData], ebx
0x1800465ae  xor     r8d, r8d; lpReserved
0x1800465b1  mov     [rsp+58h+phkResult], rax; lpData
0x1800465b6  lea     rdx, aMiniportsinsta; "MiniportsInstalled"
0x1800465bd  call    cs:__imp_RegQueryValueExW
0x1800465c3  cmp     eax, 2
0x1800465c6  jnz     short loc_18004663E
0x1800465c8  mov     [rbp+Data], 0FFFFh
0x1800465cf  jmp     short loc_18004661A
0x1800465d1  mov     [rsp+58h+lpdwDisposition], 0; lpdwDisposition
0x1800465da  lea     rax, [rbp+hKey]
0x1800465de  mov     [rsp+58h+var_20], rax; phkResult
0x1800465e3  lea     rdx, aSystemCurrentc; "SYSTEM\\CurrentControlSet\\Services\\Ra"...
0x1800465ea  mov     [rsp+58h+lpSecurityAttributes], 0; lpSecurityAttributes
0x1800465f3  xor     r9d, r9d; lpClass
0x1800465f6  mov     dword ptr [rsp+58h+lpcbData], 0F003Fh; samDesired
0x1800465fe  xor     r8d, r8d; Reserved
0x180046601  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180046608  mov     dword ptr [rsp+58h+phkResult], 0; dwOptions
0x180046610  call    cs:__imp_RegCreateKeyExW
0x180046616  test    eax, eax
0x180046618  jnz     short loc_18004663E
0x18004661a  mov     rcx, [rbp+hKey]; hKey
0x18004661e  lea     rax, [rbp+Data]
0x180046622  mov     dword ptr [rsp+58h+lpcbData], ebx; cbData
0x180046626  lea     rdx, aMiniportsinsta; "MiniportsInstalled"
0x18004662d  mov     r9d, ebx; dwType
0x180046630  mov     [rsp+58h+phkResult], rax; lpData
0x180046635  xor     r8d, r8d; Reserved
0x180046638  call    cs:__imp_RegSetValueExW
0x18004663e  mov     rcx, [rbp+hKey]; hKey
0x180046642  call    cs:__imp_RegCloseKey
0x180046648  mov     eax, [rbp+Data]
0x18004664b  add     rsp, 58h
0x18004664f  pop     rbx
0x180046650  pop     rbp
0x180046651  retn
```
