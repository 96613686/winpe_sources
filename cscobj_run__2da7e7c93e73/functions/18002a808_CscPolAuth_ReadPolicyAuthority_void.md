# CscPolAuth_ReadPolicyAuthority(void)

- ea: `0x18002a808`
- end: `0x18002a8a0`
- name: `?CscPolAuth_ReadPolicyAuthority@@YA?AW4POLICY_AUTHORITY@@XZ`
- size: `152`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180009ac4`
- `0x180012120`

## callees

- `0x18002a808`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002a875`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002a875`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002a83a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002a83a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002a891`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002a891`

## string_xrefs

- `0x18002a828`: `Software\Microsoft\Windows\CurrentVersion\UserState\UserStateTechnologies\ConfigurationControls`

## pseudocode

```c
__int64 CscPolAuth_ReadPolicyAuthority()
{
  unsigned int v0; // ebx
  unsigned int Data; // [rsp+50h] [rbp+18h] BYREF
  DWORD Type; // [rsp+58h] [rbp+20h] BYREF
  DWORD cbData; // [rsp+60h] [rbp+28h] BYREF
  HKEY hKey; // [rsp+68h] [rbp+30h] BYREF

  hKey = 0;
  v0 = 0;
  if ( !RegOpenKeyExW(
          HKEY_LOCAL_MACHINE,
          L"Software\\Microsoft\\Windows\\CurrentVersion\\UserState\\UserStateTechnologies\\ConfigurationControls",
          0,
          1u,
          &hKey) )
  {
    Type = 0;
    Data = 0;
    cbData = 4;
    if ( !RegQueryValueExW(hKey, L"OfflineFiles", 0, &Type, (LPBYTE)&Data, &cbData) && Type == 4 && Data < 2 )
      v0 = Data;
    RegCloseKey(hKey);
  }
  return v0;
}

```

## disassembly

```asm
0x18002a808  push    rbp
0x18002a80a  push    rbx
0x18002a80b  mov     rbp, rsp
0x18002a80e  sub     rsp, 38h
0x18002a812  lea     rax, [rbp+hKey]
0x18002a816  mov     [rbp+hKey], 0
0x18002a81e  xor     ebx, ebx
0x18002a820  mov     [rsp+38h+phkResult], rax; phkResult
0x18002a825  xor     r8d, r8d; ulOptions
0x18002a828  lea     rdx, REGSTR_KEY_WMI_AUTHORITY_POLICY; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18002a82f  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18002a836  lea     r9d, [rbx+1]; samDesired
0x18002a83a  call    cs:__imp_RegOpenKeyExW
0x18002a840  test    eax, eax
0x18002a842  jnz     short loc_18002A897
0x18002a844  mov     rcx, [rbp+hKey]; hKey
0x18002a848  lea     rax, [rbp+cbData]
0x18002a84c  mov     [rsp+38h+lpcbData], rax; lpcbData
0x18002a851  lea     r9, [rbp+Type]; lpType
0x18002a855  lea     rax, [rbp+Data]
0x18002a859  mov     [rbp+Type], ebx
0x18002a85c  xor     r8d, r8d; lpReserved
0x18002a85f  mov     [rsp+38h+phkResult], rax; lpData
0x18002a864  lea     rdx, REGSTR_KEY_POLICY_AUTHORITY; "OfflineFiles"
0x18002a86b  mov     [rbp+Data], ebx
0x18002a86e  mov     [rbp+cbData], 4
0x18002a875  call    cs:__imp_RegQueryValueExW
0x18002a87b  test    eax, eax
0x18002a87d  jnz     short loc_18002A88D
0x18002a87f  cmp     [rbp+Type], 4
0x18002a883  jnz     short loc_18002A88D
0x18002a885  cmp     [rbp+Data], 2
0x18002a889  cmovb   ebx, [rbp+Data]
0x18002a88d  mov     rcx, [rbp+hKey]; hKey
0x18002a891  call    cs:__imp_RegCloseKey
0x18002a897  mov     eax, ebx
0x18002a899  add     rsp, 38h
0x18002a89d  pop     rbx
0x18002a89e  pop     rbp
0x18002a89f  retn
```
