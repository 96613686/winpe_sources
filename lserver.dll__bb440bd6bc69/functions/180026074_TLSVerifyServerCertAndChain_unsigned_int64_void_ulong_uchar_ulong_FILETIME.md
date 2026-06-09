# TLSVerifyServerCertAndChain(unsigned __int64,void *,ulong,uchar *,ulong,_FILETIME *)

- ea: `0x180026074`
- end: `0x180026111`
- name: `?TLSVerifyServerCertAndChain@@YAK_KPEAXKPEAEKPEAU_FILETIME@@@Z`
- size: `157`
- prototype: `unsigned int __fastcall(HCRYPTPROV_OR_NCRYPT_KEY_HANDLE hCryptProvOrNCryptKey, void *, unsigned int, BYTE *pbCertEncoded, DWORD cbCertEncoded, struct _FILETIME *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180026a50`

## callees

- `0x180025f9c`
- `0x180026074`
- `0x1800261b8`

## import_xrefs

- `CRYPT32!CertCreateCertificateContext` at `0x18002609e`
- `CRYPT32!CertCreateCertificateContext` at `0x18002609e`
- `CRYPT32!CertFreeCertificateContext` at `0x1800260ed`
- `CRYPT32!CertFreeCertificateContext` at `0x1800260ed`
- `KERNEL32!GetLastError` at `0x1800260b2`
- `KERNEL32!GetLastError` at `0x1800260b2`

## pseudocode

```c
__int64 __fastcall TLSVerifyServerCertAndChain(
        HCRYPTPROV_OR_NCRYPT_KEY_HANDLE hCryptProvOrNCryptKey,
        void *a2,
        unsigned int a3,
        BYTE *pbCertEncoded,
        DWORD cbCertEncoded)
{
  const struct _CERT_CONTEXT *CertificateContext; // rax
  const CERT_CONTEXT *v9; // rdi
  unsigned int v10; // ebx
  __int64 v11; // rcx

  CertificateContext = CertCreateCertificateContext(1u, pbCertEncoded, cbCertEncoded);
  v9 = CertificateContext;
  if ( CertificateContext )
  {
    v10 = VerifyLicenseServerCertificate(hCryptProvOrNCryptKey, CertificateContext, a3);
    if ( !v10 )
      v10 = TLSVerifyCertChain(v11, a2, v9, &RdlsSecretsCache::g_ftCertExpiredTime);
    CertFreeCertificateContext(v9);
  }
  else
  {
    return GetLastError();
  }
  return v10;
}

```

## disassembly

```asm
0x180026074  mov     [rsp+arg_0], rbx
0x180026079  mov     [rsp+arg_8], rbp
0x18002607e  mov     [rsp+arg_10], rsi
0x180026083  push    rdi
0x180026084  sub     rsp, 20h
0x180026088  mov     ebx, r8d
0x18002608b  mov     rsi, rdx
0x18002608e  mov     r8d, [rsp+28h+cbCertEncoded]; cbCertEncoded
0x180026093  mov     rbp, rcx
0x180026096  mov     rdx, r9; pbCertEncoded
0x180026099  mov     ecx, 1; dwCertEncodingType
0x18002609e  call    cs:__imp_CertCreateCertificateContext
0x1800260a5  nop     dword ptr [rax+rax+00h]
0x1800260aa  mov     rdi, rax
0x1800260ad  test    rax, rax
0x1800260b0  jnz     short loc_1800260C2
0x1800260b2  call    cs:__imp_GetLastError
0x1800260b9  nop     dword ptr [rax+rax+00h]
0x1800260be  mov     ebx, eax
0x1800260c0  jmp     short loc_1800260F9
0x1800260c2  mov     r8d, ebx; unsigned int
0x1800260c5  mov     rdx, rdi; struct _CERT_CONTEXT *
0x1800260c8  mov     rcx, rbp; hCryptProvOrNCryptKey
0x1800260cb  call    ?VerifyLicenseServerCertificate@@YAK_KPEBU_CERT_CONTEXT@@K@Z; VerifyLicenseServerCertificate(unsigned __int64,_CERT_CONTEXT const *,ulong)
0x1800260d0  mov     ebx, eax
0x1800260d2  test    eax, eax
0x1800260d4  jnz     short loc_1800260EA
0x1800260d6  lea     r9, ?g_ftCertExpiredTime@RdlsSecretsCache@@2U_FILETIME@@A; struct _FILETIME *
0x1800260dd  mov     r8, rdi; struct _CERT_CONTEXT *
0x1800260e0  mov     rdx, rsi; void *
0x1800260e3  call    ?TLSVerifyCertChain@@YAK_KPEAXPEBU_CERT_CONTEXT@@PEAU_FILETIME@@@Z; TLSVerifyCertChain(unsigned __int64,void *,_CERT_CONTEXT const *,_FILETIME *)
0x1800260e8  mov     ebx, eax
0x1800260ea  mov     rcx, rdi; pCertContext
0x1800260ed  call    cs:__imp_CertFreeCertificateContext
0x1800260f4  nop     dword ptr [rax+rax+00h]
0x1800260f9  mov     rbp, [rsp+28h+arg_8]
0x1800260fe  mov     eax, ebx
0x180026100  mov     rbx, [rsp+28h+arg_0]
0x180026105  mov     rsi, [rsp+28h+arg_10]
0x18002610a  add     rsp, 20h
0x18002610e  pop     rdi
0x18002610f  retn
```
