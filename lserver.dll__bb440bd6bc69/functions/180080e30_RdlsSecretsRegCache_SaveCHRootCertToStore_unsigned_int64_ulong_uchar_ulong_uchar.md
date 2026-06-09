# RdlsSecretsRegCache::SaveCHRootCertToStore(unsigned __int64,ulong,uchar *,ulong,uchar *)

- ea: `0x180080e30`
- end: `0x180080f9e`
- name: `?SaveCHRootCertToStore@RdlsSecretsRegCache@@UEAAK_KKPEAEK1@Z`
- size: `366`
- prototype: `unsigned int(RdlsSecretsRegCache *__hidden this, unsigned __int64, unsigned int, unsigned __int8 *, unsigned int, unsigned __int8 *)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180080e30`
- `0x180081368`

## import_xrefs

- `ADVAPI32!RegCreateKeyExW` at `0x180080eb2`
- `ADVAPI32!RegCreateKeyExW` at `0x180080f4b`
- `ADVAPI32!RegCreateKeyExW` at `0x180080eb2`
- `ADVAPI32!RegCreateKeyExW` at `0x180080f4b`
- `ADVAPI32!RegCloseKey` at `0x180080ee2`
- `ADVAPI32!RegCloseKey` at `0x180080f7f`
- `ADVAPI32!RegCloseKey` at `0x180080ee2`
- `ADVAPI32!RegCloseKey` at `0x180080f7f`

## pseudocode

```c
LSTATUS __fastcall RdlsSecretsRegCache::SaveCHRootCertToStore(
        RdlsSecretsRegCache *this,
        unsigned __int64 a2,
        unsigned int a3,
        unsigned __int8 *a4,
        unsigned int a5,
        unsigned __int8 *a6)
{
  unsigned int v9; // ebx
  LSTATUS result; // eax
  RdlsSecretsRegCache *v11; // rcx
  unsigned int v12; // edi
  RdlsSecretsRegCache *v13; // rcx
  HKEY hKey[3]; // [rsp+50h] [rbp-18h] BYREF
  DWORD dwDisposition; // [rsp+80h] [rbp+18h] BYREF

  hKey[0] = 0;
  if ( a3 )
  {
    dwDisposition = 0;
    result = RegCreateKeyExW(
               HKEY_LOCAL_MACHINE,
               L"SOFTWARE\\Microsoft\\TermServLicensing\\Certificates\\Signature\\ROOT",
               0,
               0,
               0,
               0xF003Fu,
               0,
               hKey,
               &dwDisposition);
    if ( result )
      return result;
    v12 = RdlsSecretsRegCache::SaveRootCertificateToReg(v11, a2, hKey[0], a3, a4);
    RegCloseKey(hKey[0]);
    if ( v12 )
      return v12;
    v9 = a5;
    if ( !a5 )
      return v12;
  }
  else
  {
    v9 = a5;
    if ( !a5 )
      return -1073676256;
  }
  dwDisposition = 0;
  result = RegCreateKeyExW(
             HKEY_LOCAL_MACHINE,
             L"SOFTWARE\\Microsoft\\TermServLicensing\\Certificates\\Exchange\\ROOT",
             0,
             0,
             0,
             0xF003Fu,
             0,
             hKey,
             &dwDisposition);
  if ( result )
    return result;
  v12 = RdlsSecretsRegCache::SaveRootCertificateToReg(v13, a2, hKey[0], v9, a6);
  RegCloseKey(hKey[0]);
  return v12;
}

```

## disassembly

```asm
0x180080e30  mov     [rsp+arg_0], rbx
0x180080e35  mov     [rsp+arg_8], rsi
0x180080e3a  push    rdi
0x180080e3b  sub     rsp, 60h
0x180080e3f  and     [rsp+68h+hKey], 0
0x180080e45  mov     rdi, r9
0x180080e48  mov     ebx, r8d
0x180080e4b  mov     rsi, rdx
0x180080e4e  test    r8d, r8d
0x180080e51  jnz     short loc_180080E6C
0x180080e53  mov     ebx, [rsp+68h+arg_20]
0x180080e5a  test    ebx, ebx
0x180080e5c  jnz     loc_180080F05
0x180080e62  mov     eax, 0C0010020h
0x180080e67  jmp     loc_180080F8D
0x180080e6c  and     [rsp+68h+dwDisposition], 0
0x180080e74  lea     rax, [rsp+68h+dwDisposition]
0x180080e7c  mov     [rsp+68h+lpdwDisposition], rax; lpdwDisposition
0x180080e81  lea     rdx, aSoftwareMicros_1; "SOFTWARE\\Microsoft\\TermServLicensing"...
0x180080e88  lea     rax, [rsp+68h+hKey]
0x180080e8d  xor     r9d, r9d; lpClass
0x180080e90  mov     [rsp+68h+phkResult], rax; phkResult
0x180080e95  xor     r8d, r8d; Reserved
0x180080e98  and     [rsp+68h+var_38], 0
0x180080e9e  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180080ea5  mov     [rsp+68h+samDesired], 0F003Fh; samDesired
0x180080ead  and     [rsp+68h+dwOptions], 0
0x180080eb2  call    cs:__imp_RegCreateKeyExW
0x180080eb9  nop     dword ptr [rax+rax+00h]
0x180080ebe  test    eax, eax
0x180080ec0  jnz     loc_180080F8D
0x180080ec6  mov     r8, [rsp+68h+hKey]; HKEY
0x180080ecb  mov     r9d, ebx; unsigned int
0x180080ece  mov     rdx, rsi; unsigned __int64
0x180080ed1  mov     qword ptr [rsp+68h+dwOptions], rdi; unsigned __int8 *
0x180080ed6  call    ?SaveRootCertificateToReg@RdlsSecretsRegCache@@AEAAK_KPEAUHKEY__@@KPEAE@Z; RdlsSecretsRegCache::SaveRootCertificateToReg(unsigned __int64,HKEY__ *,ulong,uchar *)
0x180080edb  mov     rcx, [rsp+68h+hKey]; hKey
0x180080ee0  mov     edi, eax
0x180080ee2  call    cs:__imp_RegCloseKey
0x180080ee9  nop     dword ptr [rax+rax+00h]
0x180080eee  test    edi, edi
0x180080ef0  jnz     loc_180080F8B
0x180080ef6  mov     ebx, [rsp+68h+arg_20]
0x180080efd  test    ebx, ebx
0x180080eff  jz      loc_180080F8B
0x180080f05  and     [rsp+68h+dwDisposition], 0
0x180080f0d  lea     rax, [rsp+68h+dwDisposition]
0x180080f15  mov     [rsp+68h+lpdwDisposition], rax; lpdwDisposition
0x180080f1a  lea     rdx, aSoftwareMicros_9; "SOFTWARE\\Microsoft\\TermServLicensing"...
0x180080f21  lea     rax, [rsp+68h+hKey]
0x180080f26  xor     r9d, r9d; lpClass
0x180080f29  mov     [rsp+68h+phkResult], rax; phkResult
0x180080f2e  xor     r8d, r8d; Reserved
0x180080f31  and     [rsp+68h+var_38], 0
0x180080f37  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180080f3e  mov     [rsp+68h+samDesired], 0F003Fh; samDesired
0x180080f46  and     [rsp+68h+dwOptions], 0
0x180080f4b  call    cs:__imp_RegCreateKeyExW
0x180080f52  nop     dword ptr [rax+rax+00h]
0x180080f57  test    eax, eax
0x180080f59  jnz     short loc_180080F8D
0x180080f5b  mov     rax, [rsp+68h+arg_28]
0x180080f63  mov     r9d, ebx; unsigned int
0x180080f66  mov     r8, [rsp+68h+hKey]; HKEY
0x180080f6b  mov     rdx, rsi; unsigned __int64
0x180080f6e  mov     qword ptr [rsp+68h+dwOptions], rax; unsigned __int8 *
0x180080f73  call    ?SaveRootCertificateToReg@RdlsSecretsRegCache@@AEAAK_KPEAUHKEY__@@KPEAE@Z; RdlsSecretsRegCache::SaveRootCertificateToReg(unsigned __int64,HKEY__ *,ulong,uchar *)
0x180080f78  mov     rcx, [rsp+68h+hKey]; hKey
0x180080f7d  mov     edi, eax
0x180080f7f  call    cs:__imp_RegCloseKey
0x180080f86  nop     dword ptr [rax+rax+00h]
0x180080f8b  mov     eax, edi
0x180080f8d  mov     rbx, [rsp+68h+arg_0]
0x180080f92  mov     rsi, [rsp+68h+arg_8]
0x180080f97  add     rsp, 60h
0x180080f9b  pop     rdi
0x180080f9c  retn
```
