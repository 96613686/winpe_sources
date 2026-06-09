# CscPolAuth_ReadPolicyAuthority(void)

- ea: `0x1800806e8`
- end: `0x180080780`
- name: `?CscPolAuth_ReadPolicyAuthority@@YA?AW4POLICY_AUTHORITY@@XZ`
- size: `152`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18005bb98`

## callees

- `0x1800806e8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18008071a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18008071a`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180080755`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180080755`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180080771`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180080771`

## string_xrefs

- `0x180080708`: `Software\Microsoft\Windows\CurrentVersion\UserState\UserStateTechnologies\ConfigurationControls`

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
0x1800806e8  push    rbp
0x1800806ea  push    rbx
0x1800806eb  mov     rbp, rsp
0x1800806ee  sub     rsp, 38h
0x1800806f2  lea     rax, [rbp+hKey]
0x1800806f6  mov     [rbp+hKey], 0
0x1800806fe  xor     ebx, ebx
0x180080700  mov     [rsp+38h+phkResult], rax; phkResult
0x180080705  xor     r8d, r8d; ulOptions
0x180080708  lea     rdx, REGSTR_KEY_WMI_AUTHORITY_POLICY; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18008070f  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180080716  lea     r9d, [rbx+1]; samDesired
0x18008071a  call    cs:__imp_RegOpenKeyExW
0x180080720  test    eax, eax
0x180080722  jnz     short loc_180080777
0x180080724  mov     rcx, [rbp+hKey]; hKey
0x180080728  lea     rax, [rbp+cbData]
0x18008072c  mov     [rsp+38h+lpcbData], rax; lpcbData
0x180080731  lea     r9, [rbp+Type]; lpType
0x180080735  lea     rax, [rbp+Data]
0x180080739  mov     [rbp+Type], ebx
0x18008073c  xor     r8d, r8d; lpReserved
0x18008073f  mov     [rsp+38h+phkResult], rax; lpData
0x180080744  lea     rdx, REGSTR_KEY_POLICY_AUTHORITY; "OfflineFiles"
0x18008074b  mov     [rbp+Data], ebx
0x18008074e  mov     [rbp+cbData], 4
0x180080755  call    cs:__imp_RegQueryValueExW
0x18008075b  test    eax, eax
0x18008075d  jnz     short loc_18008076D
0x18008075f  cmp     [rbp+Type], 4
0x180080763  jnz     short loc_18008076D
0x180080765  cmp     [rbp+Data], 2
0x180080769  cmovb   ebx, [rbp+Data]
0x18008076d  mov     rcx, [rbp+hKey]; hKey
0x180080771  call    cs:__imp_RegCloseKey
0x180080777  mov     eax, ebx
0x180080779  add     rsp, 38h
0x18008077d  pop     rbx
0x18008077e  pop     rbp
0x18008077f  retn
```
