# RdlsSecretsCache::IsCertificateLicenseServerCertificate(unsigned __int64,ulong,ulong,uchar *,ulong *,uchar * *)

- ea: `0x18007cdfc`
- end: `0x18007cf36`
- name: `?IsCertificateLicenseServerCertificate@RdlsSecretsCache@@IEAAK_KKKPEAEPEAKPEAPEAE@Z`
- size: `314`
- prototype: `unsigned int(RdlsSecretsCache *__hidden this, unsigned __int64, unsigned int, unsigned int, unsigned __int8 *, unsigned int *, unsigned __int8 **)`
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x180080fb0`
- `0x180082acc`
- `0x1800831d0`

## callees

- `0x180002d26`
- `0x18007cdfc`
- `0x18007cf3c`

## import_xrefs

- `CRYPT32!CertEnumCertificatesInStore` at `0x18007ce70`
- `CRYPT32!CertEnumCertificatesInStore` at `0x18007ce70`
- `CRYPT32!CertOpenStore` at `0x18007ce45`
- `CRYPT32!CertOpenStore` at `0x18007ce45`
- `CRYPT32!CertFreeCertificateContext` at `0x18007cef8`
- `CRYPT32!CertFreeCertificateContext` at `0x18007cef8`
- `CRYPT32!CertCloseStore` at `0x18007cf0c`
- `CRYPT32!CertCloseStore` at `0x18007cf0c`
- `KERNEL32!GetLastError` at `0x18007ce59`
- `KERNEL32!GetLastError` at `0x18007cee7`
- `KERNEL32!GetLastError` at `0x18007ce59`
- `KERNEL32!GetLastError` at `0x18007cee7`
- `KERNEL32!LocalAlloc` at `0x18007ceb9`
- `KERNEL32!LocalAlloc` at `0x18007ceb9`

## pseudocode

```c
DWORD __fastcall RdlsSecretsCache::IsCertificateLicenseServerCertificate(
        RdlsSecretsCache *this,
        HCRYPTPROV_LEGACY a2,
        unsigned int a3,
        int a4,
        unsigned __int8 *a5,
        unsigned int *a6,
        unsigned __int8 **a7)
{
  const CERT_CONTEXT *v7; // rbx
  HCERTSTORE v10; // rsi
  const struct _CERT_CONTEXT *v12; // rax
  RdlsSecretsCache *v13; // rcx
  unsigned int IsHydraRootOIDInCert; // eax
  DWORD LastError; // edi
  SIZE_T cbCertEncoded; // rdx
  unsigned __int8 *v17; // rax
  _DWORD v18[2]; // [rsp+30h] [rbp-18h] BYREF
  unsigned __int8 *v19; // [rsp+38h] [rbp-10h]

  v7 = 0;
  v18[1] = 0;
  v19 = a5;
  v18[0] = a4;
  v10 = CertOpenStore((LPCSTR)5, 0x10001u, a2, 1u, v18);
  if ( !v10 )
    return GetLastError();
  while ( 1 )
  {
    v12 = CertEnumCertificatesInStore(v10, v7);
    v7 = v12;
    if ( !v12 )
      goto LABEL_6;
    IsHydraRootOIDInCert = RdlsSecretsCache::IsHydraRootOIDInCert(v13, a2, v12, a3);
    LastError = IsHydraRootOIDInCert;
    if ( !IsHydraRootOIDInCert )
      break;
    if ( IsHydraRootOIDInCert == -1071644672 )
      goto LABEL_11;
LABEL_6:
    LastError = 0;
    if ( !v7 )
      goto LABEL_12;
  }
  cbCertEncoded = v7->cbCertEncoded;
  *a6 = cbCertEncoded;
  v17 = (unsigned __int8 *)LocalAlloc(0x40u, cbCertEncoded);
  *a7 = v17;
  if ( v17 )
    memcpy_0(v17, v7->pbCertEncoded, v7->cbCertEncoded);
  else
    LastError = GetLastError();
LABEL_11:
  CertFreeCertificateContext(v7);
LABEL_12:
  CertCloseStore(v10, 1u);
  return LastError;
}

```

## disassembly

```asm
0x18007cdfc  mov     r11, rsp
0x18007cdff  mov     [r11+8], rbx
0x18007ce03  mov     [r11+10h], rbp
0x18007ce07  mov     [r11+18h], rsi
0x18007ce0b  mov     [r11+20h], rdi
0x18007ce0f  push    r14
0x18007ce11  sub     rsp, 40h
0x18007ce15  mov     rax, [rsp+48h+arg_20]
0x18007ce1a  xor     ebx, ebx
0x18007ce1c  and     [rsp+48h+var_14], ebx
0x18007ce20  mov     r14d, r8d
0x18007ce23  mov     [r11-10h], rax
0x18007ce27  mov     rbp, rdx
0x18007ce2a  lea     rax, [r11-18h]
0x18007ce2e  mov     [r11-18h], r9d
0x18007ce32  mov     r8, rdx; hCryptProv
0x18007ce35  mov     [r11-28h], rax
0x18007ce39  lea     r9d, [rbx+1]; dwFlags
0x18007ce3d  mov     edx, 10001h; dwEncodingType
0x18007ce42  lea     ecx, [rbx+5]; lpszStoreProvider
0x18007ce45  call    cs:__imp_CertOpenStore
0x18007ce4c  nop     dword ptr [rax+rax+00h]
0x18007ce51  mov     rsi, rax
0x18007ce54  test    rax, rax
0x18007ce57  jnz     short loc_18007CE6A
0x18007ce59  call    cs:__imp_GetLastError
0x18007ce60  nop     dword ptr [rax+rax+00h]
0x18007ce65  jmp     loc_18007CF1A
0x18007ce6a  mov     rdx, rbx; pPrevCertContext
0x18007ce6d  mov     rcx, rsi; hCertStore
0x18007ce70  call    cs:__imp_CertEnumCertificatesInStore
0x18007ce77  nop     dword ptr [rax+rax+00h]
0x18007ce7c  mov     rbx, rax
0x18007ce7f  test    rax, rax
0x18007ce82  jz      short loc_18007CE9F
0x18007ce84  mov     r9d, r14d; unsigned int
0x18007ce87  mov     r8, rax; struct _CERT_CONTEXT *
0x18007ce8a  mov     rdx, rbp; unsigned __int64
0x18007ce8d  call    ?IsHydraRootOIDInCert@RdlsSecretsCache@@IEAAK_KPEBU_CERT_CONTEXT@@K@Z; RdlsSecretsCache::IsHydraRootOIDInCert(unsigned __int64,_CERT_CONTEXT const *,ulong)
0x18007ce92  mov     edi, eax
0x18007ce94  test    eax, eax
0x18007ce96  jz      short loc_18007CEA8
0x18007ce98  cmp     eax, 0C0200000h
0x18007ce9d  jz      short loc_18007CEF5
0x18007ce9f  xor     edi, edi
0x18007cea1  test    rbx, rbx
0x18007cea4  jnz     short loc_18007CE6A
0x18007cea6  jmp     short loc_18007CF04
0x18007cea8  mov     ecx, [rbx+10h]
0x18007ceab  mov     rax, [rsp+48h+arg_28]
0x18007ceb0  mov     edx, ecx; uBytes
0x18007ceb2  mov     [rax], ecx
0x18007ceb4  mov     ecx, 40h ; '@'; uFlags
0x18007ceb9  call    cs:__imp_LocalAlloc
0x18007cec0  nop     dword ptr [rax+rax+00h]
0x18007cec5  mov     rcx, [rsp+48h+arg_30]
0x18007cecd  mov     [rcx], rax
0x18007ced0  test    rax, rax
0x18007ced3  jz      short loc_18007CEE7
0x18007ced5  mov     r8d, [rbx+10h]; Size
0x18007ced9  mov     rcx, rax; void *
0x18007cedc  mov     rdx, [rbx+8]; Src
0x18007cee0  call    memcpy_0
0x18007cee5  jmp     short loc_18007CEF5
0x18007cee7  call    cs:__imp_GetLastError
0x18007ceee  nop     dword ptr [rax+rax+00h]
0x18007cef3  mov     edi, eax
0x18007cef5  mov     rcx, rbx; pCertContext
0x18007cef8  call    cs:__imp_CertFreeCertificateContext
0x18007ceff  nop     dword ptr [rax+rax+00h]
0x18007cf04  mov     edx, 1; dwFlags
0x18007cf09  mov     rcx, rsi; hCertStore
0x18007cf0c  call    cs:__imp_CertCloseStore
0x18007cf13  nop     dword ptr [rax+rax+00h]
0x18007cf18  mov     eax, edi
0x18007cf1a  mov     rbx, [rsp+48h+arg_0]
0x18007cf1f  mov     rbp, [rsp+48h+arg_8]
0x18007cf24  mov     rsi, [rsp+48h+arg_10]
0x18007cf29  mov     rdi, [rsp+48h+arg_18]
0x18007cf2e  add     rsp, 40h
0x18007cf32  pop     r14
0x18007cf34  retn
```
