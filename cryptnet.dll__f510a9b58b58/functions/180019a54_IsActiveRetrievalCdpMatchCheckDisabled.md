# _IsActiveRetrievalCdpMatchCheckDisabled

- ea: `0x180019a54`
- end: `0x180019af9`
- name: `_IsActiveRetrievalCdpMatchCheckDisabled`
- size: `165`
- prototype: `_BOOL8()`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180008a30`

## callees

- `0x180019a54`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180019ad1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180019ad1`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180019a88`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180019a88`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180019ac3`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180019ac3`

## string_xrefs

- `0x180019a78`: `Software\Microsoft\Cryptography\OID\EncodingType 0\CertDllCreateCertificateChainEngine\Config`

## pseudocode

```c
_BOOL8 IsActiveRetrievalCdpMatchCheckDisabled()
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
    if ( !RegQueryValueExW(hKey, L"CryptnetDisableActiveRetrievalCdpMatchCheck", 0, &Type, (LPBYTE)&Data, &cbData)
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
0x180019a54  push    rbp
0x180019a56  push    rbx
0x180019a57  mov     rbp, rsp
0x180019a5a  sub     rsp, 38h
0x180019a5e  lea     rax, [rbp+hKey]
0x180019a62  mov     [rbp+hKey], 0
0x180019a6a  mov     r9d, 20119h; samDesired
0x180019a70  mov     [rsp+38h+phkResult], rax; phkResult
0x180019a75  xor     r8d, r8d; ulOptions
0x180019a78  lea     rdx, SubKey; "Software\\Microsoft\\Cryptography\\OID"...
0x180019a7f  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180019a86  xor     ebx, ebx
0x180019a88  call    cs:__imp_RegOpenKeyExW
0x180019a8e  test    eax, eax
0x180019a90  jnz     short loc_180019AD7
0x180019a92  mov     rcx, [rbp+hKey]; hKey
0x180019a96  lea     rax, [rbp+cbData]
0x180019a9a  mov     [rsp+38h+lpcbData], rax; lpcbData
0x180019a9f  lea     r9, [rbp+Type]; lpType
0x180019aa3  lea     rax, [rbp+Data]
0x180019aa7  mov     [rbp+Type], ebx
0x180019aaa  xor     r8d, r8d; lpReserved
0x180019aad  mov     [rsp+38h+phkResult], rax; lpData
0x180019ab2  lea     rdx, aCryptnetdisabl; "CryptnetDisableActiveRetrievalCdpMatchC"...
0x180019ab9  mov     [rbp+Data], ebx
0x180019abc  mov     [rbp+cbData], 4
0x180019ac3  call    cs:__imp_RegQueryValueExW
0x180019ac9  test    eax, eax
0x180019acb  jz      short loc_180019AE0
0x180019acd  mov     rcx, [rbp+hKey]; hKey
0x180019ad1  call    cs:__imp_RegCloseKey
0x180019ad7  mov     eax, ebx
0x180019ad9  add     rsp, 38h
0x180019add  pop     rbx
0x180019ade  pop     rbp
0x180019adf  retn
0x180019ae0  cmp     [rbp+Type], 4
0x180019ae4  jnz     short loc_180019ACD
0x180019ae6  cmp     [rbp+cbData], 4
0x180019aea  jnz     short loc_180019ACD
0x180019aec  cmp     [rbp+Data], ebx
0x180019aef  mov     eax, 1
0x180019af4  cmovnz  ebx, eax
0x180019af7  jmp     short loc_180019ACD
```
