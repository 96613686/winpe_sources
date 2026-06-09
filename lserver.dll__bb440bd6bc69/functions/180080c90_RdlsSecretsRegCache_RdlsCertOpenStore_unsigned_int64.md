# RdlsSecretsRegCache::RdlsCertOpenStore(unsigned __int64)

- ea: `0x180080c90`
- end: `0x180080d25`
- name: `?RdlsCertOpenStore@RdlsSecretsRegCache@@UEAAPEAX_K@Z`
- size: `149`
- prototype: `void *(RdlsSecretsRegCache *__hidden this, unsigned __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180080c90`

## import_xrefs

- `CRYPT32!CertOpenStore` at `0x180080d0d`
- `CRYPT32!CertOpenStore` at `0x180080d0d`
- `ADVAPI32!RegOpenKeyExW` at `0x180080cd1`
- `ADVAPI32!RegOpenKeyExW` at `0x180080cd1`
- `ADVAPI32!RegCloseKey` at `0x180080ca9`
- `ADVAPI32!RegCloseKey` at `0x180080ca9`
- `KERNEL32!SetLastError` at `0x180080ce3`
- `KERNEL32!SetLastError` at `0x180080ce3`

## pseudocode

```c
HCERTSTORE __fastcall RdlsSecretsRegCache::RdlsCertOpenStore(RdlsSecretsRegCache *this, HCRYPTPROV_LEGACY a2)
{
  HKEY *phkResult; // rbx
  HKEY v4; // rcx
  LSTATUS v5; // eax

  phkResult = (HKEY *)((char *)this + 88);
  v4 = (HKEY)*((_QWORD *)this + 11);
  if ( v4 )
    RegCloseKey(v4);
  v5 = RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"SOFTWARE\\Microsoft\\TermServLicensing\\Certificates\\Signature\\CA",
         0,
         0xF003Fu,
         phkResult);
  if ( !v5 )
    return CertOpenStore((LPCSTR)4, 0x10001u, a2, 1u, *phkResult);
  SetLastError(v5);
  return 0;
}

```

## disassembly

```asm
0x180080c90  mov     [rsp+arg_0], rbx
0x180080c95  push    rdi
0x180080c96  sub     rsp, 30h
0x180080c9a  lea     rbx, [rcx+58h]
0x180080c9e  mov     rdi, rdx
0x180080ca1  mov     rcx, [rbx]; hKey
0x180080ca4  test    rcx, rcx
0x180080ca7  jz      short loc_180080CB5
0x180080ca9  call    cs:__imp_RegCloseKey
0x180080cb0  nop     dword ptr [rax+rax+00h]
0x180080cb5  mov     r9d, 0F003Fh; samDesired
0x180080cbb  mov     [rsp+38h+phkResult], rbx; phkResult
0x180080cc0  xor     r8d, r8d; ulOptions
0x180080cc3  lea     rdx, aSoftwareMicros_3; "SOFTWARE\\Microsoft\\TermServLicensing"...
0x180080cca  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180080cd1  call    cs:__imp_RegOpenKeyExW
0x180080cd8  nop     dword ptr [rax+rax+00h]
0x180080cdd  test    eax, eax
0x180080cdf  jz      short loc_180080CF3
0x180080ce1  mov     ecx, eax; dwErrCode
0x180080ce3  call    cs:__imp_SetLastError
0x180080cea  nop     dword ptr [rax+rax+00h]
0x180080cef  xor     eax, eax
0x180080cf1  jmp     short loc_180080D19
0x180080cf3  mov     rax, [rbx]
0x180080cf6  mov     r9d, 1; dwFlags
0x180080cfc  mov     r8, rdi; hCryptProv
0x180080cff  mov     [rsp+38h+phkResult], rax; pvPara
0x180080d04  mov     edx, 10001h; dwEncodingType
0x180080d09  lea     ecx, [r9+3]; lpszStoreProvider
0x180080d0d  call    cs:__imp_CertOpenStore
0x180080d14  nop     dword ptr [rax+rax+00h]
0x180080d19  mov     rbx, [rsp+38h+arg_0]
0x180080d1e  add     rsp, 30h
0x180080d22  pop     rdi
0x180080d23  retn
```
