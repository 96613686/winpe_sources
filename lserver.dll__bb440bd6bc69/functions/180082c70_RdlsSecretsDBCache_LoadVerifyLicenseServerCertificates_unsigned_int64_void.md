# RdlsSecretsDBCache::LoadVerifyLicenseServerCertificates(unsigned __int64,void * *)

- ea: `0x180082c70`
- end: `0x180082d97`
- name: `?LoadVerifyLicenseServerCertificates@RdlsSecretsDBCache@@UEAAK_KPEAPEAX@Z`
- size: `295`
- prototype: `unsigned int(RdlsSecretsDBCache *__hidden this, unsigned __int64, void **)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x180026a50`
- `0x180081b18`
- `0x180081cc0`
- `0x180082acc`
- `0x180082c70`
- `0x1800a5010`

## import_xrefs

- `CRYPT32!CertCreateCertificateContext` at `0x180082d54`
- `CRYPT32!CertCreateCertificateContext` at `0x180082d54`
- `CRYPT32!CertFreeCertificateContext` at `0x180082d3b`
- `CRYPT32!CertFreeCertificateContext` at `0x180082d3b`
- `CRYPT32!CertCloseStore` at `0x180082cd0`
- `CRYPT32!CertCloseStore` at `0x180082cd0`

## pseudocode

```c
__int64 __fastcall RdlsSecretsDBCache::LoadVerifyLicenseServerCertificates(
        BYTE **this,
        HCRYPTPROV_OR_NCRYPT_KEY_HANDLE a2,
        void **a3)
{
  struct _RdlsCertData *LicensingCertificateStore; // rbx
  RdlsSecretsCache *v7; // rcx
  unsigned int v8; // edi
  RdlsSecretsCache *v9; // rcx
  int v10; // ebx
  bool v11; // zf
  void *v12; // rax
  __int64 result; // rax

  LicensingCertificateStore = (struct _RdlsCertData *)RdlsSecretsDBCache::GetLicensingCertificateStore(this, 1);
  v8 = RdlsSecretsCache::CopyRdlsCertStore(v7, LicensingCertificateStore, (struct _RdlsCertData *)(this + 1));
  RdlsSecretsCache::DeAllocateRdlsCertStore(v9, LicensingCertificateStore, 1);
  v10 = 0;
  v11 = v8 == 0;
  if ( !v8 )
  {
    if ( *a3 )
      CertCloseStore(*a3, 1u);
    v12 = (void *)(*((__int64 (__fastcall **)(BYTE **, HCRYPTPROV_OR_NCRYPT_KEY_HANDLE))*this + 21))(this, a2);
    *a3 = v12;
    if ( !v12 )
    {
      v8 = -1073676254;
LABEL_11:
      v11 = v8 == 0;
      goto LABEL_12;
    }
    v8 = TLSValidateServerCertficates(a2, v12, this[4], *((_DWORD *)this + 6), this[6], *((_DWORD *)this + 10));
    if ( v8 )
      v8 = -1073676253;
    v11 = v8 == 0;
    if ( !v8 )
    {
      if ( RdlsSecretsCache::g_pLicenseCertContext )
        CertFreeCertificateContext(RdlsSecretsCache::g_pLicenseCertContext);
      RdlsSecretsCache::g_pLicenseCertContext = CertCreateCertificateContext(1u, this[4], *((_DWORD *)this + 6));
      goto LABEL_11;
    }
  }
LABEL_12:
  LOBYTE(v10) = v11;
  result = v8;
  RdlsSecretsCache::g_bHasHydraCert = v10;
  return result;
}

```

## disassembly

```asm
0x180082c70  mov     rax, rsp
0x180082c73  mov     [rax+8], rbx
0x180082c77  mov     [rax+10h], rbp
0x180082c7b  mov     [rax+18h], rsi
0x180082c7f  mov     [rax+20h], rdi
0x180082c83  push    r14
0x180082c85  sub     rsp, 40h
0x180082c89  mov     rbp, rdx
0x180082c8c  mov     r14, r8
0x180082c8f  mov     edx, 1
0x180082c94  mov     rsi, rcx
0x180082c97  call    ?GetLicensingCertificateStore@RdlsSecretsDBCache@@AEAAPEAU_RdlsCertData@@W4_CertDataCategory@@@Z; RdlsSecretsDBCache::GetLicensingCertificateStore(_CertDataCategory)
0x180082c9c  lea     r8, [rsi+8]; struct _RdlsCertData *
0x180082ca0  mov     rdx, rax; struct _RdlsCertData *
0x180082ca3  mov     rbx, rax
0x180082ca6  call    ?CopyRdlsCertStore@RdlsSecretsCache@@IEAAKPEAU_RdlsCertData@@0@Z; RdlsSecretsCache::CopyRdlsCertStore(_RdlsCertData *,_RdlsCertData *)
0x180082cab  mov     r8d, 1; int
0x180082cb1  mov     rdx, rbx; struct _RdlsCertData *
0x180082cb4  mov     edi, eax
0x180082cb6  call    ?DeAllocateRdlsCertStore@RdlsSecretsCache@@IEAAXPEAU_RdlsCertData@@H@Z; RdlsSecretsCache::DeAllocateRdlsCertStore(_RdlsCertData *,int)
0x180082cbb  xor     ebx, ebx
0x180082cbd  test    edi, edi
0x180082cbf  jnz     loc_180082D69
0x180082cc5  cmp     [r14], rbx
0x180082cc8  jz      short loc_180082CDC
0x180082cca  mov     rcx, [r14]; hCertStore
0x180082ccd  lea     edx, [rbx+1]; dwFlags
0x180082cd0  call    cs:__imp_CertCloseStore
0x180082cd7  nop     dword ptr [rax+rax+00h]
0x180082cdc  mov     rax, [rsi]
0x180082cdf  mov     rdx, rbp
0x180082ce2  mov     rcx, rsi
0x180082ce5  mov     rax, [rax+0A8h]
0x180082cec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180082cf1  mov     [r14], rax
0x180082cf4  test    rax, rax
0x180082cf7  jz      loc_180082D90
0x180082cfd  mov     ecx, [rsi+28h]
0x180082d00  mov     rdx, [rsi+30h]
0x180082d04  mov     r9d, [rsi+18h]; cbCertEncoded
0x180082d08  mov     r8, [rsi+20h]; pbCertEncoded
0x180082d0c  mov     [rsp+48h+var_20], ecx; DWORD
0x180082d10  mov     rcx, rbp; hCryptProvOrNCryptKey
0x180082d13  mov     [rsp+48h+var_28], rdx; BYTE *
0x180082d18  mov     rdx, rax; void *
0x180082d1b  call    TLSValidateServerCertficates
0x180082d20  mov     edi, eax
0x180082d22  test    eax, eax
0x180082d24  jz      short loc_180082D2B
0x180082d26  mov     edi, 0C0010023h
0x180082d2b  test    edi, edi
0x180082d2d  jnz     short loc_180082D69
0x180082d2f  mov     rcx, cs:?g_pLicenseCertContext@RdlsSecretsCache@@2PEBU_CERT_CONTEXT@@EB; pCertContext
0x180082d36  test    rcx, rcx
0x180082d39  jz      short loc_180082D47
0x180082d3b  call    cs:__imp_CertFreeCertificateContext
0x180082d42  nop     dword ptr [rax+rax+00h]
0x180082d47  mov     r8d, [rsi+18h]; cbCertEncoded
0x180082d4b  mov     ecx, 1; dwCertEncodingType
0x180082d50  mov     rdx, [rsi+20h]; pbCertEncoded
0x180082d54  call    cs:__imp_CertCreateCertificateContext
0x180082d5b  nop     dword ptr [rax+rax+00h]
0x180082d60  mov     cs:?g_pLicenseCertContext@RdlsSecretsCache@@2PEBU_CERT_CONTEXT@@EB, rax; _CERT_CONTEXT const * const RdlsSecretsCache::g_pLicenseCertContext
0x180082d67  test    edi, edi
0x180082d69  mov     rbp, [rsp+48h+arg_8]
0x180082d6e  setz    bl
0x180082d71  mov     rsi, [rsp+48h+arg_10]
0x180082d76  mov     eax, edi
0x180082d78  mov     rdi, [rsp+48h+arg_18]
0x180082d7d  mov     cs:?g_bHasHydraCert@RdlsSecretsCache@@2HA, ebx; int RdlsSecretsCache::g_bHasHydraCert
0x180082d83  mov     rbx, [rsp+48h+arg_0]
0x180082d88  add     rsp, 40h
0x180082d8c  pop     r14
0x180082d8e  retn
0x180082d90  mov     edi, 0C0010022h
0x180082d95  jmp     short loc_180082D67
```
