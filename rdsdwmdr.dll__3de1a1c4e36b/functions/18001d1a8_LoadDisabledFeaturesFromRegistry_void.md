# LoadDisabledFeaturesFromRegistry(void)

- ea: `0x18001d1a8`
- end: `0x18001d250`
- name: `?LoadDisabledFeaturesFromRegistry@@YAIXZ`
- size: `168`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x18001d258`

## callees

- `0x18001d1a8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001d221`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001d221`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001d241`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001d241`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001d1ee`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001d1ee`

## pseudocode

```c
__int64 LoadDisabledFeaturesFromRegistry(void)
{
  unsigned int Data; // [rsp+40h] [rbp+10h] BYREF
  DWORD Type; // [rsp+48h] [rbp+18h] BYREF
  DWORD cbData; // [rsp+50h] [rbp+20h] BYREF
  HKEY hKey; // [rsp+58h] [rbp+28h] BYREF

  hKey = 0;
  Data = 0;
  cbData = 4;
  Type = 0;
  if ( !RegOpenKeyExW(
          HKEY_LOCAL_MACHINE,
          L"SYSTEM\\CurrentControlSet\\Control\\Terminal Server\\WinStations",
          0,
          0x20019u,
          &hKey) )
  {
    if ( !hKey )
      return Data;
    if ( RegQueryValueExW(hKey, L"ProcFeatDisabled", 0, &Type, (LPBYTE)&Data, &cbData) || Type != 4 )
      Data = 0;
  }
  if ( hKey )
    RegCloseKey(hKey);
  return Data;
}

```

## disassembly

```asm
0x18001d1a8  push    rbp
0x18001d1aa  mov     rbp, rsp
0x18001d1ad  sub     rsp, 30h
0x18001d1b1  lea     rax, [rbp+hKey]
0x18001d1b5  mov     [rbp+hKey], 0
0x18001d1bd  mov     r9d, 20019h; samDesired
0x18001d1c3  mov     [rsp+30h+phkResult], rax; phkResult
0x18001d1c8  xor     r8d, r8d; ulOptions
0x18001d1cb  mov     [rbp+Data], 0
0x18001d1d2  lea     rdx, SubKey; "SYSTEM\\CurrentControlSet\\Control\\Ter"...
0x18001d1d9  mov     [rbp+cbData], 4
0x18001d1e0  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18001d1e7  mov     [rbp+Type], 0
0x18001d1ee  call    cs:__imp_RegOpenKeyExW
0x18001d1f4  test    eax, eax
0x18001d1f6  jnz     short loc_18001D238
0x18001d1f8  mov     rcx, [rbp+hKey]; hKey
0x18001d1fc  test    rcx, rcx
0x18001d1ff  jz      short loc_18001D247
0x18001d201  lea     rax, [rbp+cbData]
0x18001d205  xor     r8d, r8d; lpReserved
0x18001d208  mov     [rsp+30h+lpcbData], rax; lpcbData
0x18001d20d  lea     r9, [rbp+Type]; lpType
0x18001d211  lea     rax, [rbp+Data]
0x18001d215  lea     rdx, aProcfeatdisabl; "ProcFeatDisabled"
0x18001d21c  mov     [rsp+30h+phkResult], rax; lpData
0x18001d221  call    cs:__imp_RegQueryValueExW
0x18001d227  test    eax, eax
0x18001d229  jnz     short loc_18001D231
0x18001d22b  cmp     [rbp+Type], 4
0x18001d22f  jz      short loc_18001D238
0x18001d231  mov     [rbp+Data], 0
0x18001d238  mov     rcx, [rbp+hKey]; hKey
0x18001d23c  test    rcx, rcx
0x18001d23f  jz      short loc_18001D247
0x18001d241  call    cs:__imp_RegCloseKey
0x18001d247  mov     eax, [rbp+Data]
0x18001d24a  add     rsp, 30h
0x18001d24e  pop     rbp
0x18001d24f  retn
```
