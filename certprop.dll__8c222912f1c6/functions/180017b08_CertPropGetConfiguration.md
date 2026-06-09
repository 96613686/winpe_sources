# CertPropGetConfiguration

- ea: `0x180017b08`
- end: `0x180017ce6`
- name: `CertPropGetConfiguration`
- size: `478`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180017d90`

## callees

- `0x180017b08`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180017b57`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180017b57`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180017cd5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180017cd5`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180017b97`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180017bc9`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180017c03`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180017c35`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180017c6f`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180017ca1`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180017b97`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180017bc9`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180017c03`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180017c35`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180017c6f`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180017ca1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017b63`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017b63`

## string_xrefs

- `0x180017b88`: `CertPropEnabled`
- `0x180017bb3`: `CertPropEnabled`

## pseudocode

```c
__int64 CertPropGetConfiguration()
{
  DWORD LastError; // edi
  DWORD v1; // ebx
  int Data; // [rsp+60h] [rbp+28h] BYREF
  DWORD Type; // [rsp+68h] [rbp+30h] BYREF
  DWORD cbData; // [rsp+70h] [rbp+38h] BYREF
  HKEY hKey; // [rsp+78h] [rbp+40h] BYREF

  g_fEnableRootCertProp = 1;
  hKey = 0;
  cbData = 0;
  Data = 0;
  Type = 0;
  g_RootsCleanupOption = 2;
  LastError = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"Software\\Policies\\Microsoft\\Windows\\CertProp", 0, 0x20019u, &hKey);
  if ( LastError )
  {
    LastError = GetLastError();
  }
  else
  {
    cbData = 4;
    Data = 0;
    if ( !RegQueryValueExW(hKey, L"CertPropEnabled", 0, &Type, 0, 0)
      && Type == 4
      && !RegQueryValueExW(hKey, L"CertPropEnabled", 0, 0, (LPBYTE)&Data, &cbData) )
    {
      g_fEnableCertProp = Data != 0;
    }
    Data = 0;
    cbData = 4;
    if ( !RegQueryValueExW(hKey, L"EnableRootCertificatePropagation", 0, &Type, 0, 0)
      && Type == 4
      && !RegQueryValueExW(hKey, L"EnableRootCertificatePropagation", 0, 0, (LPBYTE)&Data, &cbData) )
    {
      g_fEnableRootCertProp = Data != 0;
    }
    Data = 0;
    cbData = 4;
    if ( !RegQueryValueExW(hKey, L"RootCertificateCleanupOption", 0, &Type, 0, 0)
      && Type == 4
      && !RegQueryValueExW(hKey, L"RootCertificateCleanupOption", 0, 0, (LPBYTE)&Data, &cbData)
      && (!Data || (unsigned int)(Data - 1) <= 1) )
    {
      g_RootsCleanupOption = Data;
    }
  }
  v1 = 0;
  if ( LastError != 2 )
    v1 = LastError;
  if ( hKey )
    RegCloseKey(hKey);
  return v1;
}

```

## disassembly

```asm
0x180017b08  push    rbp
0x180017b0a  push    rbx
0x180017b0b  push    rsi
0x180017b0c  push    rdi
0x180017b0d  mov     rbp, rsp
0x180017b10  sub     rsp, 38h
0x180017b14  xor     esi, esi
0x180017b16  mov     cs:g_fEnableRootCertProp, 1
0x180017b20  lea     rax, [rbp+hKey]
0x180017b24  mov     [rbp+hKey], rsi
0x180017b28  mov     r9d, 20019h; samDesired
0x180017b2e  mov     [rbp+cbData], esi
0x180017b31  xor     r8d, r8d; ulOptions
0x180017b34  mov     [rbp+Data], esi
0x180017b37  lea     rdx, aSoftwarePolici_0; "Software\\Policies\\Microsoft\\Windows"...
0x180017b3e  mov     [rbp+Type], esi
0x180017b41  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180017b48  mov     [rsp+38h+phkResult], rax; phkResult
0x180017b4d  mov     cs:g_RootsCleanupOption, 2
0x180017b57  call    cs:__imp_RegOpenKeyExW
0x180017b5d  mov     edi, eax
0x180017b5f  test    eax, eax
0x180017b61  jz      short loc_180017B70
0x180017b63  call    cs:__imp_GetLastError
0x180017b69  mov     edi, eax
0x180017b6b  jmp     loc_180017CC4
0x180017b70  mov     rcx, [rbp+hKey]; hKey
0x180017b74  lea     r9, [rbp+Type]; lpType
0x180017b78  mov     ebx, 4
0x180017b7d  mov     [rsp+38h+lpcbData], rsi; lpcbData
0x180017b82  xor     r8d, r8d; lpReserved
0x180017b85  mov     [rbp+cbData], ebx
0x180017b88  lea     rdx, aCertpropenable; "CertPropEnabled"
0x180017b8f  mov     [rbp+Data], esi
0x180017b92  mov     [rsp+38h+phkResult], rsi; lpData
0x180017b97  call    cs:__imp_RegQueryValueExW
0x180017b9d  test    eax, eax
0x180017b9f  jnz     short loc_180017BE1
0x180017ba1  cmp     [rbp+Type], ebx
0x180017ba4  jnz     short loc_180017BE1
0x180017ba6  mov     rcx, [rbp+hKey]; hKey
0x180017baa  lea     rax, [rbp+cbData]
0x180017bae  mov     [rsp+38h+lpcbData], rax; lpcbData
0x180017bb3  lea     rdx, aCertpropenable; "CertPropEnabled"
0x180017bba  lea     rax, [rbp+Data]
0x180017bbe  xor     r9d, r9d; lpType
0x180017bc1  xor     r8d, r8d; lpReserved
0x180017bc4  mov     [rsp+38h+phkResult], rax; lpData
0x180017bc9  call    cs:__imp_RegQueryValueExW
0x180017bcf  test    eax, eax
0x180017bd1  jnz     short loc_180017BE1
0x180017bd3  cmp     [rbp+Data], esi
0x180017bd6  mov     eax, esi
0x180017bd8  setnz   al
0x180017bdb  mov     cs:g_fEnableCertProp, eax
0x180017be1  mov     rcx, [rbp+hKey]; hKey
0x180017be5  lea     r9, [rbp+Type]; lpType
0x180017be9  mov     [rsp+38h+lpcbData], rsi; lpcbData
0x180017bee  lea     rdx, aEnablerootcert; "EnableRootCertificatePropagation"
0x180017bf5  xor     r8d, r8d; lpReserved
0x180017bf8  mov     [rsp+38h+phkResult], rsi; lpData
0x180017bfd  mov     [rbp+Data], esi
0x180017c00  mov     [rbp+cbData], ebx
0x180017c03  call    cs:__imp_RegQueryValueExW
0x180017c09  test    eax, eax
0x180017c0b  jnz     short loc_180017C4D
0x180017c0d  cmp     [rbp+Type], ebx
0x180017c10  jnz     short loc_180017C4D
0x180017c12  mov     rcx, [rbp+hKey]; hKey
0x180017c16  lea     rax, [rbp+cbData]
0x180017c1a  mov     [rsp+38h+lpcbData], rax; lpcbData
0x180017c1f  lea     rdx, aEnablerootcert; "EnableRootCertificatePropagation"
0x180017c26  lea     rax, [rbp+Data]
0x180017c2a  xor     r9d, r9d; lpType
0x180017c2d  xor     r8d, r8d; lpReserved
0x180017c30  mov     [rsp+38h+phkResult], rax; lpData
0x180017c35  call    cs:__imp_RegQueryValueExW
0x180017c3b  test    eax, eax
0x180017c3d  jnz     short loc_180017C4D
0x180017c3f  cmp     [rbp+Data], esi
0x180017c42  mov     eax, esi
0x180017c44  setnz   al
0x180017c47  mov     cs:g_fEnableRootCertProp, eax
0x180017c4d  mov     rcx, [rbp+hKey]; hKey
0x180017c51  lea     r9, [rbp+Type]; lpType
0x180017c55  mov     [rsp+38h+lpcbData], rsi; lpcbData
0x180017c5a  lea     rdx, aRootcertificat; "RootCertificateCleanupOption"
0x180017c61  xor     r8d, r8d; lpReserved
0x180017c64  mov     [rsp+38h+phkResult], rsi; lpData
0x180017c69  mov     [rbp+Data], esi
0x180017c6c  mov     [rbp+cbData], ebx
0x180017c6f  call    cs:__imp_RegQueryValueExW
0x180017c75  test    eax, eax
0x180017c77  jnz     short loc_180017CC4
0x180017c79  cmp     [rbp+Type], ebx
0x180017c7c  jnz     short loc_180017CC4
0x180017c7e  mov     rcx, [rbp+hKey]; hKey
0x180017c82  lea     rax, [rbp+cbData]
0x180017c86  mov     [rsp+38h+lpcbData], rax; lpcbData
0x180017c8b  lea     rdx, aRootcertificat; "RootCertificateCleanupOption"
0x180017c92  lea     rax, [rbp+Data]
0x180017c96  xor     r9d, r9d; lpType
0x180017c99  xor     r8d, r8d; lpReserved
0x180017c9c  mov     [rsp+38h+phkResult], rax; lpData
0x180017ca1  call    cs:__imp_RegQueryValueExW
0x180017ca7  test    eax, eax
0x180017ca9  jnz     short loc_180017CC4
0x180017cab  mov     edx, [rbp+Data]
0x180017cae  mov     ecx, edx
0x180017cb0  test    edx, edx
0x180017cb2  jz      short loc_180017CBE
0x180017cb4  sub     ecx, 1
0x180017cb7  jz      short loc_180017CBE
0x180017cb9  cmp     ecx, 1
0x180017cbc  jnz     short loc_180017CC4
0x180017cbe  mov     cs:g_RootsCleanupOption, edx
0x180017cc4  mov     rcx, [rbp+hKey]; hKey
0x180017cc8  cmp     edi, 2
0x180017ccb  mov     ebx, esi
0x180017ccd  cmovnz  ebx, edi
0x180017cd0  test    rcx, rcx
0x180017cd3  jz      short loc_180017CDB
0x180017cd5  call    cs:__imp_RegCloseKey
0x180017cdb  mov     eax, ebx
0x180017cdd  add     rsp, 38h
0x180017ce1  pop     rdi
0x180017ce2  pop     rsi
0x180017ce3  pop     rbx
0x180017ce4  pop     rbp
0x180017ce5  retn
```
