# LdapIsControlCharacterEnabled

- ea: `0x180024ed8`
- end: `0x180024f79`
- name: `LdapIsControlCharacterEnabled`
- size: `161`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800196e0`

## callees

- `0x180024ed8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180024f6a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180024f6a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180024f0c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180024f0c`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180024f47`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180024f47`

## string_xrefs

- `0x180024efc`: `Software\Microsoft\Cryptography\OID\EncodingType 0\CertDllCreateCertificateChainEngine\Config`

## pseudocode

```c
_BOOL8 LdapIsControlCharacterEnabled()
{
  BOOL v0; // ebx
  DWORD Type; // [rsp+50h] [rbp+18h] BYREF
  DWORD cbData; // [rsp+58h] [rbp+20h] BYREF
  int Data; // [rsp+60h] [rbp+28h] BYREF
  HKEY hKey; // [rsp+68h] [rbp+30h] BYREF

  hKey = 0;
  v0 = 0;
  if ( !RegOpenKeyExW(
          HKEY_LOCAL_MACHINE,
          L"Software\\Microsoft\\Cryptography\\OID\\EncodingType 0\\CertDllCreateCertificateChainEngine\\Config",
          0,
          0x20119u,
          &hKey) )
  {
    Type = 0;
    Data = 0;
    cbData = 4;
    if ( !RegQueryValueExW(hKey, L"CryptnetEnableLdapControlCharacter", 0, &Type, (LPBYTE)&Data, &cbData)
      && Type == 4
      && cbData == 4 )
    {
      v0 = Data != 0;
    }
    RegCloseKey(hKey);
  }
  return v0;
}

```

## disassembly

```asm
0x180024ed8  push    rbp
0x180024eda  push    rbx
0x180024edb  mov     rbp, rsp
0x180024ede  sub     rsp, 38h
0x180024ee2  lea     rax, [rbp+hKey]
0x180024ee6  mov     [rbp+hKey], 0
0x180024eee  mov     r9d, 20119h; samDesired
0x180024ef4  mov     [rsp+38h+phkResult], rax; phkResult
0x180024ef9  xor     r8d, r8d; ulOptions
0x180024efc  lea     rdx, SubKey; "Software\\Microsoft\\Cryptography\\OID"...
0x180024f03  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180024f0a  xor     ebx, ebx
0x180024f0c  call    cs:__imp_RegOpenKeyExW
0x180024f12  test    eax, eax
0x180024f14  jnz     short loc_180024F70
0x180024f16  mov     rcx, [rbp+hKey]; hKey
0x180024f1a  lea     rax, [rbp+cbData]
0x180024f1e  mov     [rsp+38h+lpcbData], rax; lpcbData
0x180024f23  lea     r9, [rbp+Type]; lpType
0x180024f27  lea     rax, [rbp+Data]
0x180024f2b  mov     [rbp+Type], ebx
0x180024f2e  xor     r8d, r8d; lpReserved
0x180024f31  mov     [rsp+38h+phkResult], rax; lpData
0x180024f36  lea     rdx, aCryptnetenable; "CryptnetEnableLdapControlCharacter"
0x180024f3d  mov     [rbp+Data], ebx
0x180024f40  mov     [rbp+cbData], 4
0x180024f47  call    cs:__imp_RegQueryValueExW
0x180024f4d  test    eax, eax
0x180024f4f  jnz     short loc_180024F66
0x180024f51  cmp     [rbp+Type], 4
0x180024f55  jnz     short loc_180024F66
0x180024f57  cmp     [rbp+cbData], 4
0x180024f5b  jnz     short loc_180024F66
0x180024f5d  cmp     [rbp+Data], ebx
0x180024f60  lea     eax, [rbx+1]
0x180024f63  cmovnz  ebx, eax
0x180024f66  mov     rcx, [rbp+hKey]; hKey
0x180024f6a  call    cs:__imp_RegCloseKey
0x180024f70  mov     eax, ebx
0x180024f72  add     rsp, 38h
0x180024f76  pop     rbx
0x180024f77  pop     rbp
0x180024f78  retn
```
