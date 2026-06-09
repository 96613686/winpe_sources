# IsRegistryToolDisabled

- ea: `0x1400024a8`
- end: `0x140002570`
- name: `IsRegistryToolDisabled`
- size: `200`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1400031f4`

## callees

- `0x1400024a8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1400024f1`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1400024f1`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x14000252c`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x14000252c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14000255a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14000255a`

## string_xrefs

- `0x140002525`: `DisableRegistryTools`

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
0x1400024a8  push    rbp
0x1400024aa  push    rbx
0x1400024ab  mov     rbp, rsp
0x1400024ae  sub     rsp, 38h
0x1400024b2  lea     rax, [rbp+hKey]
0x1400024b6  mov     [rbp+hKey], 0
0x1400024be  mov     r9d, 2000000h; samDesired
0x1400024c4  mov     [rsp+38h+phkResult], rax; phkResult
0x1400024c9  xor     r8d, r8d; ulOptions
0x1400024cc  mov     [rbp+Type], 0
0x1400024d3  lea     rdx, SubKey; "Software\\Microsoft\\Windows\\CurrentVe"...
0x1400024da  mov     [rbp+Data], 0
0x1400024e1  mov     rcx, 0FFFFFFFF80000001h; hKey
0x1400024e8  mov     [rbp+cbData], 0
0x1400024ef  xor     ebx, ebx
0x1400024f1  call    cs:__imp_RegOpenKeyExW
0x1400024f8  nop     dword ptr [rax+rax+00h]
0x1400024fd  test    eax, eax
0x1400024ff  jnz     short loc_140002566
0x140002501  mov     rcx, [rbp+hKey]; hKey
0x140002505  lea     rax, [rbp+cbData]
0x140002509  mov     [rsp+38h+lpcbData], rax; lpcbData
0x14000250e  lea     r9, [rbp+Type]; lpType
0x140002512  lea     rax, [rbp+Data]
0x140002516  mov     [rbp+cbData], 4
0x14000251d  xor     r8d, r8d; lpReserved
0x140002520  mov     [rsp+38h+phkResult], rax; lpData
0x140002525  lea     rdx, ValueName; "DisableRegistryTools"
0x14000252c  call    cs:__imp_RegQueryValueExW
0x140002533  nop     dword ptr [rax+rax+00h]
0x140002538  test    eax, eax
0x14000253a  jnz     short loc_140002551
0x14000253c  cmp     [rbp+Type], 4
0x140002540  jnz     short loc_140002551
0x140002542  cmp     [rbp+cbData], 4
0x140002546  jnz     short loc_140002551
0x140002548  cmp     [rbp+Data], ebx
0x14000254b  lea     eax, [rbx+1]
0x14000254e  cmovnz  ebx, eax
0x140002551  mov     rcx, [rbp+hKey]; hKey
0x140002555  test    rcx, rcx
0x140002558  jz      short loc_140002566
0x14000255a  call    cs:__imp_RegCloseKey
0x140002561  nop     dword ptr [rax+rax+00h]
0x140002566  mov     eax, ebx
0x140002568  add     rsp, 38h
0x14000256c  pop     rbx
0x14000256d  pop     rbp
0x14000256e  retn
```
