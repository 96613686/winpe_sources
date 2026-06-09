# GetCustomCofigurationKey

- ea: `0x180087204`
- end: `0x1800872a8`
- name: `GetCustomCofigurationKey`
- size: `164`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config, service_task`

## callers

- `0x1800864c4`
- `0x1800872b0`

## callees

- `0x180087204`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x180087294`
- `ADVAPI32!RegCloseKey` at `0x180087294`
- `ADVAPI32!RegOpenKeyExA` at `0x180087234`
- `ADVAPI32!RegOpenKeyExA` at `0x180087234`
- `ADVAPI32!RegQueryValueExA` at `0x180087272`
- `ADVAPI32!RegQueryValueExA` at `0x180087272`

## string_xrefs

- `0x180087218`: `System\CurrentControlSet\Services\rasman\IKEv2`

## pseudocode

```c
HKEY GetCustomCofigurationKey()
{
  int Data; // [rsp+40h] [rbp+8h] BYREF
  DWORD cbData; // [rsp+48h] [rbp+10h] BYREF
  HKEY hKey; // [rsp+50h] [rbp+18h] BYREF

  hKey = 0;
  Data = 0;
  if ( !RegOpenKeyExA(HKEY_LOCAL_MACHINE, "System\\CurrentControlSet\\Services\\rasman\\IKEv2", 0, 1u, &hKey) )
  {
    cbData = 4;
    if ( !RegQueryValueExA(hKey, "CustomParams", 0, 0, (LPBYTE)&Data, &cbData) && Data )
      return hKey;
    RegCloseKey(hKey);
  }
  return 0;
}

```

## disassembly

```asm
0x180087204  sub     rsp, 38h
0x180087208  and     [rsp+38h+hKey], 0
0x18008720e  lea     rax, [rsp+38h+hKey]
0x180087213  and     [rsp+38h+Data], 0
0x180087218  lea     rdx, aSystemCurrentc_28; "System\\CurrentControlSet\\Services\\ra"...
0x18008721f  mov     r9d, 1; samDesired
0x180087225  mov     [rsp+38h+phkResult], rax; phkResult
0x18008722a  xor     r8d, r8d; ulOptions
0x18008722d  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180087234  call    cs:__imp_RegOpenKeyExA
0x18008723b  nop     dword ptr [rax+rax+00h]
0x180087240  test    eax, eax
0x180087242  jnz     short loc_1800872A0
0x180087244  mov     rcx, [rsp+38h+hKey]; hKey
0x180087249  lea     rax, [rsp+38h+cbData]
0x18008724e  mov     [rsp+38h+lpcbData], rax; lpcbData
0x180087253  lea     rdx, aCustomparams; "CustomParams"
0x18008725a  lea     rax, [rsp+38h+Data]
0x18008725f  mov     [rsp+38h+cbData], 4
0x180087267  xor     r9d, r9d; lpType
0x18008726a  mov     [rsp+38h+phkResult], rax; lpData
0x18008726f  xor     r8d, r8d; lpReserved
0x180087272  call    cs:__imp_RegQueryValueExA
0x180087279  nop     dword ptr [rax+rax+00h]
0x18008727e  test    eax, eax
0x180087280  jnz     short loc_18008728F
0x180087282  cmp     [rsp+38h+Data], eax
0x180087286  jz      short loc_18008728F
0x180087288  mov     rax, [rsp+38h+hKey]
0x18008728d  jmp     short loc_1800872A2
0x18008728f  mov     rcx, [rsp+38h+hKey]; hKey
0x180087294  call    cs:__imp_RegCloseKey
0x18008729b  nop     dword ptr [rax+rax+00h]
0x1800872a0  xor     eax, eax
0x1800872a2  add     rsp, 38h
0x1800872a6  retn
```
