# IsRegistryToolDisabled

- ea: `0x1400023e8`
- end: `0x14000249d`
- name: `IsRegistryToolDisabled`
- size: `181`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1400030b8`

## callees

- `0x1400023e8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140002431`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140002431`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x140002466`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x140002466`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14000248e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14000248e`

## string_xrefs

- `0x14000245f`: `DisableRegistryTools`

## pseudocode

```c
_BOOL8 IsRegistryToolDisabled()
{
  BOOL v0; // ebx
  DWORD cbData; // [rsp+50h] [rbp+18h] BYREF
  DWORD Type; // [rsp+58h] [rbp+20h] BYREF
  int Data; // [rsp+60h] [rbp+28h] BYREF
  HKEY hKey; // [rsp+68h] [rbp+30h] BYREF

  hKey = 0;
  Type = 0;
  Data = 0;
  cbData = 0;
  v0 = 0;
  if ( !RegOpenKeyExW(
          HKEY_CURRENT_USER,
          L"Software\\Microsoft\\Windows\\CurrentVersion\\Policies\\System",
          0,
          0x2000000u,
          &hKey) )
  {
    cbData = 4;
    if ( !RegQueryValueExW(hKey, L"DisableRegistryTools", 0, &Type, (LPBYTE)&Data, &cbData) && Type == 4 && cbData == 4 )
      v0 = Data != 0;
    if ( hKey )
      RegCloseKey(hKey);
  }
  return v0;
}

```

## disassembly

```asm
0x1400023e8  push    rbp
0x1400023ea  push    rbx
0x1400023eb  mov     rbp, rsp
0x1400023ee  sub     rsp, 38h
0x1400023f2  lea     rax, [rbp+hKey]
0x1400023f6  mov     [rbp+hKey], 0
0x1400023fe  mov     r9d, 2000000h; samDesired
0x140002404  mov     [rsp+38h+phkResult], rax; phkResult
0x140002409  xor     r8d, r8d; ulOptions
0x14000240c  mov     [rbp+Type], 0
0x140002413  lea     rdx, SubKey; "Software\\Microsoft\\Windows\\CurrentVe"...
0x14000241a  mov     [rbp+Data], 0
0x140002421  mov     rcx, 0FFFFFFFF80000001h; hKey
0x140002428  mov     [rbp+cbData], 0
0x14000242f  xor     ebx, ebx
0x140002431  call    cs:__imp_RegOpenKeyExW
0x140002437  test    eax, eax
0x140002439  jnz     short loc_140002494
0x14000243b  mov     rcx, [rbp+hKey]; hKey
0x14000243f  lea     rax, [rbp+cbData]
0x140002443  mov     [rsp+38h+lpcbData], rax; lpcbData
0x140002448  lea     r9, [rbp+Type]; lpType
0x14000244c  lea     rax, [rbp+Data]
0x140002450  mov     [rbp+cbData], 4
0x140002457  xor     r8d, r8d; lpReserved
0x14000245a  mov     [rsp+38h+phkResult], rax; lpData
0x14000245f  lea     rdx, ValueName; "DisableRegistryTools"
0x140002466  call    cs:__imp_RegQueryValueExW
0x14000246c  test    eax, eax
0x14000246e  jnz     short loc_140002485
0x140002470  cmp     [rbp+Type], 4
0x140002474  jnz     short loc_140002485
0x140002476  cmp     [rbp+cbData], 4
0x14000247a  jnz     short loc_140002485
0x14000247c  cmp     [rbp+Data], ebx
0x14000247f  lea     eax, [rbx+1]
0x140002482  cmovnz  ebx, eax
0x140002485  mov     rcx, [rbp+hKey]; hKey
0x140002489  test    rcx, rcx
0x14000248c  jz      short loc_140002494
0x14000248e  call    cs:__imp_RegCloseKey
0x140002494  mov     eax, ebx
0x140002496  add     rsp, 38h
0x14000249a  pop     rbx
0x14000249b  pop     rbp
0x14000249c  retn
```
