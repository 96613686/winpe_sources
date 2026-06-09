# RdlsSecretsRegCache::LoadVerifyLicenseServerCertificates(unsigned __int64,void * *)

- ea: `0x180080b70`
- end: `0x180080c86`
- name: `?LoadVerifyLicenseServerCertificates@RdlsSecretsRegCache@@UEAAK_KPEAPEAX@Z`
- size: `278`
- prototype: `unsigned int(RdlsSecretsRegCache *__hidden this, unsigned __int64, void **)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x180026a50`
- `0x180080984`
- `0x180080b70`
- `0x1800a5010`

## import_xrefs

- `CRYPT32!CertCreateCertificateContext` at `0x180080c43`
- `CRYPT32!CertCreateCertificateContext` at `0x180080c43`
- `CRYPT32!CertFreeCertificateContext` at `0x180080c2a`
- `CRYPT32!CertFreeCertificateContext` at `0x180080c2a`
- `CRYPT32!CertCloseStore` at `0x180080baa`
- `CRYPT32!CertCloseStore` at `0x180080baa`
- `ADVAPI32!RegCloseKey` at `0x180080bbf`
- `ADVAPI32!RegCloseKey` at `0x180080bbf`

## pseudocode

```c
__int64 __fastcall RdlsSecretsRegCache::LoadVerifyLicenseServerCertificates(
        RdlsSecretsRegCache *this,
        HCRYPTPROV_OR_NCRYPT_KEY_HANDLE a2,
        void **a3)
{
  int v6; // ebx
  unsigned int CHEndorsedCertificates; // edi
  HKEY v8; // rcx
  void *v9; // rax
  bool v10; // zf
  __int64 result; // rax

  v6 = 0;
  CHEndorsedCertificates = RdlsSecretsRegCache::LoadCHEndorsedCertificates(this);
  if ( !CHEndorsedCertificates )
  {
    if ( *a3 )
      CertCloseStore(*a3, 1u);
    v8 = (HKEY)*((_QWORD *)this + 11);
    if ( v8 )
      RegCloseKey(v8);
    v9 = (void *)(*(__int64 (__fastcall **)(RdlsSecretsRegCache *, HCRYPTPROV_OR_NCRYPT_KEY_HANDLE))(*(_QWORD *)this + 168LL))(
                   this,
                   a2);
    *a3 = v9;
    if ( !v9 )
    {
      CHEndorsedCertificates = -1073676254;
LABEL_13:
      v10 = CHEndorsedCertificates == 0;
      goto LABEL_14;
    }
    CHEndorsedCertificates = TLSValidateServerCertficates(
                               a2,
                               v9,
                               *((BYTE **)this + 4),
                               *((_DWORD *)this + 6),
                               *((BYTE **)this + 6),
                               *((_DWORD *)this + 10));
    if ( CHEndorsedCertificates )
      CHEndorsedCertificates = -1073676253;
  }
  v10 = CHEndorsedCertificates == 0;
  if ( !CHEndorsedCertificates )
  {
    if ( RdlsSecretsCache::g_pLicenseCertContext )
      CertFreeCertificateContext(RdlsSecretsCache::g_pLicenseCertContext);
    RdlsSecretsCache::g_pLicenseCertContext = CertCreateCertificateContext(
                                                1u,
                                                *((const BYTE **)this + 4),
                                                *((_DWORD *)this + 6));
    goto LABEL_13;
  }
LABEL_14:
  LOBYTE(v6) = v10;
  result = CHEndorsedCertificates;
  RdlsSecretsCache::g_bHasHydraCert = v6;
  return result;
}

```

## disassembly

```asm
0x180080b70  mov     rax, rsp
0x180080b73  mov     [rax+8], rbx
0x180080b77  mov     [rax+10h], rbp
0x180080b7b  mov     [rax+18h], rsi
0x180080b7f  mov     [rax+20h], rdi
0x180080b83  push    r14
0x180080b85  sub     rsp, 40h
0x180080b89  mov     r14, r8
0x180080b8c  mov     rbp, rdx
0x180080b8f  mov     rsi, rcx
0x180080b92  call    ?LoadCHEndorsedCertificates@RdlsSecretsRegCache@@AEAAKXZ; RdlsSecretsRegCache::LoadCHEndorsedCertificates(void)
0x180080b97  xor     ebx, ebx
0x180080b99  mov     edi, eax
0x180080b9b  test    eax, eax
0x180080b9d  jnz     short loc_180080C1A
0x180080b9f  cmp     [r14], rbx
0x180080ba2  jz      short loc_180080BB6
0x180080ba4  mov     rcx, [r14]; hCertStore
0x180080ba7  lea     edx, [rax+1]; dwFlags
0x180080baa  call    cs:__imp_CertCloseStore
0x180080bb1  nop     dword ptr [rax+rax+00h]
0x180080bb6  mov     rcx, [rsi+58h]; hKey
0x180080bba  test    rcx, rcx
0x180080bbd  jz      short loc_180080BCB
0x180080bbf  call    cs:__imp_RegCloseKey
0x180080bc6  nop     dword ptr [rax+rax+00h]
0x180080bcb  mov     rax, [rsi]
0x180080bce  mov     rdx, rbp
0x180080bd1  mov     rcx, rsi
0x180080bd4  mov     rax, [rax+0A8h]
0x180080bdb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180080be0  mov     [r14], rax
0x180080be3  test    rax, rax
0x180080be6  jz      loc_180080C7F
0x180080bec  mov     ecx, [rsi+28h]
0x180080bef  mov     rdx, [rsi+30h]
0x180080bf3  mov     r9d, [rsi+18h]; cbCertEncoded
0x180080bf7  mov     r8, [rsi+20h]; pbCertEncoded
0x180080bfb  mov     [rsp+48h+var_20], ecx; DWORD
0x180080bff  mov     rcx, rbp; hCryptProvOrNCryptKey
0x180080c02  mov     [rsp+48h+var_28], rdx; BYTE *
0x180080c07  mov     rdx, rax; void *
0x180080c0a  call    TLSValidateServerCertficates
0x180080c0f  mov     edi, eax
0x180080c11  test    eax, eax
0x180080c13  jz      short loc_180080C1A
0x180080c15  mov     edi, 0C0010023h
0x180080c1a  test    edi, edi
0x180080c1c  jnz     short loc_180080C58
0x180080c1e  mov     rcx, cs:?g_pLicenseCertContext@RdlsSecretsCache@@2PEBU_CERT_CONTEXT@@EB; pCertContext
0x180080c25  test    rcx, rcx
0x180080c28  jz      short loc_180080C36
0x180080c2a  call    cs:__imp_CertFreeCertificateContext
0x180080c31  nop     dword ptr [rax+rax+00h]
0x180080c36  mov     r8d, [rsi+18h]; cbCertEncoded
0x180080c3a  mov     ecx, 1; dwCertEncodingType
0x180080c3f  mov     rdx, [rsi+20h]; pbCertEncoded
0x180080c43  call    cs:__imp_CertCreateCertificateContext
0x180080c4a  nop     dword ptr [rax+rax+00h]
0x180080c4f  mov     cs:?g_pLicenseCertContext@RdlsSecretsCache@@2PEBU_CERT_CONTEXT@@EB, rax; _CERT_CONTEXT const * const RdlsSecretsCache::g_pLicenseCertContext
0x180080c56  test    edi, edi
0x180080c58  mov     rbp, [rsp+48h+arg_8]
0x180080c5d  setz    bl
0x180080c60  mov     rsi, [rsp+48h+arg_10]
0x180080c65  mov     eax, edi
0x180080c67  mov     rdi, [rsp+48h+arg_18]
0x180080c6c  mov     cs:?g_bHasHydraCert@RdlsSecretsCache@@2HA, ebx; int RdlsSecretsCache::g_bHasHydraCert
0x180080c72  mov     rbx, [rsp+48h+arg_0]
0x180080c77  add     rsp, 40h
0x180080c7b  pop     r14
0x180080c7d  retn
0x180080c7f  mov     edi, 0C0010022h
0x180080c84  jmp     short loc_180080C56
```
