# I_GetOcspValiditySeconds(void)

- ea: `0x18001abbc`
- end: `0x18001ac5c`
- name: `?I_GetOcspValiditySeconds@@YAKXZ`
- size: `160`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18000e610`

## callees

- `0x18001abbc`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001ac4d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001ac4d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001abf4`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001abf4`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001ac2c`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001ac2c`

## string_xrefs

- `0x18001abe6`: `Software\Microsoft\Cryptography\OID\EncodingType 0\CertDllCreateCertificateChainEngine\Config`

## pseudocode

```c
__int64 I_GetOcspValiditySeconds(void)
{
  unsigned int Data; // [rsp+40h] [rbp+10h] BYREF
  DWORD Type; // [rsp+48h] [rbp+18h] BYREF
  DWORD cbData; // [rsp+50h] [rbp+20h] BYREF
  HKEY hKey; // [rsp+58h] [rbp+28h] BYREF

  hKey = 0;
  Data = 43200;
  if ( !RegOpenKeyExW(
          HKEY_LOCAL_MACHINE,
          L"Software\\Microsoft\\Cryptography\\OID\\EncodingType 0\\CertDllCreateCertificateChainEngine\\Config",
          0,
          0x20119u,
          &hKey) )
  {
    Type = 0;
    cbData = 4;
    if ( RegQueryValueExW(hKey, L"OcspValiditySeconds", 0, &Type, (LPBYTE)&Data, &cbData) || Type != 4 || cbData != 4 )
      Data = 43200;
    RegCloseKey(hKey);
  }
  return Data;
}

```

## disassembly

```asm
0x18001abbc  push    rbp
0x18001abbe  mov     rbp, rsp
0x18001abc1  sub     rsp, 30h
0x18001abc5  lea     rax, [rbp+hKey]
0x18001abc9  mov     [rbp+hKey], 0
0x18001abd1  mov     r9d, 20119h; samDesired
0x18001abd7  mov     [rsp+30h+phkResult], rax; phkResult
0x18001abdc  xor     r8d, r8d; ulOptions
0x18001abdf  mov     [rbp+Data], 0A8C0h
0x18001abe6  lea     rdx, SubKey; "Software\\Microsoft\\Cryptography\\OID"...
0x18001abed  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18001abf4  call    cs:__imp_RegOpenKeyExW
0x18001abfa  test    eax, eax
0x18001abfc  jnz     short loc_18001AC53
0x18001abfe  mov     rcx, [rbp+hKey]; hKey
0x18001ac02  lea     r9, [rbp+Type]; lpType
0x18001ac06  mov     [rbp+Type], eax
0x18001ac09  lea     rdx, aOcspvalidityse; "OcspValiditySeconds"
0x18001ac10  lea     rax, [rbp+cbData]
0x18001ac14  mov     [rbp+cbData], 4
0x18001ac1b  mov     [rsp+30h+lpcbData], rax; lpcbData
0x18001ac20  xor     r8d, r8d; lpReserved
0x18001ac23  lea     rax, [rbp+Data]
0x18001ac27  mov     [rsp+30h+phkResult], rax; lpData
0x18001ac2c  call    cs:__imp_RegQueryValueExW
0x18001ac32  test    eax, eax
0x18001ac34  jnz     short loc_18001AC42
0x18001ac36  cmp     [rbp+Type], 4
0x18001ac3a  jnz     short loc_18001AC42
0x18001ac3c  cmp     [rbp+cbData], 4
0x18001ac40  jz      short loc_18001AC49
0x18001ac42  mov     [rbp+Data], 0A8C0h
0x18001ac49  mov     rcx, [rbp+hKey]; hKey
0x18001ac4d  call    cs:__imp_RegCloseKey
0x18001ac53  mov     eax, [rbp+Data]
0x18001ac56  add     rsp, 30h
0x18001ac5a  pop     rbp
0x18001ac5b  retn
```
