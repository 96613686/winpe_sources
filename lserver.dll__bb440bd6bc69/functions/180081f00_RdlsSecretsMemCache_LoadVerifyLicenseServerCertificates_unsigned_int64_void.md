# RdlsSecretsMemCache::LoadVerifyLicenseServerCertificates(unsigned __int64,void * *)

- ea: `0x180081f00`
- end: `0x180082012`
- name: `?LoadVerifyLicenseServerCertificates@RdlsSecretsMemCache@@UEAAK_KPEAPEAX@Z`
- size: `274`
- prototype: `unsigned int(RdlsSecretsMemCache *__hidden this, unsigned __int64, void **)`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x180026a50`
- `0x180081b18`
- `0x180081e50`
- `0x180081f00`
- `0x1800a5010`

## import_xrefs

- `CRYPT32!CertCreateCertificateContext` at `0x180081fcf`
- `CRYPT32!CertCreateCertificateContext` at `0x180081fcf`
- `CRYPT32!CertFreeCertificateContext` at `0x180081fb6`
- `CRYPT32!CertFreeCertificateContext` at `0x180081fb6`
- `CRYPT32!CertCloseStore` at `0x180081f4b`
- `CRYPT32!CertCloseStore` at `0x180081f4b`

## pseudocode

```c
__int64 __fastcall RdlsSecretsMemCache::LoadVerifyLicenseServerCertificates(
        BYTE **this,
        HCRYPTPROV_OR_NCRYPT_KEY_HANDLE a2,
        void **a3)
{
  struct _RdlsCertData *LicensingCertificateStore; // rax
  RdlsSecretsCache *v7; // rcx
  int v8; // ebx
  unsigned int v9; // edi
  void *v10; // rax
  bool v11; // zf
  __int64 result; // rax

  LicensingCertificateStore = (struct _RdlsCertData *)RdlsSecretsMemCache::GetLicensingCertificateStore(this, 1);
  v8 = 0;
  v9 = RdlsSecretsCache::CopyRdlsCertStore(v7, LicensingCertificateStore, (RdlsSecretsCache *)((char *)v7 + 8));
  if ( !v9 )
  {
    if ( *a3 )
      CertCloseStore(*a3, 1u);
    v10 = (void *)(*((__int64 (__fastcall **)(BYTE **, HCRYPTPROV_OR_NCRYPT_KEY_HANDLE))*this + 21))(this, a2);
    *a3 = v10;
    if ( !v10 )
    {
      v9 = -1073676254;
LABEL_11:
      v11 = v9 == 0;
      goto LABEL_12;
    }
    v9 = TLSValidateServerCertficates(a2, v10, this[4], *((_DWORD *)this + 6), this[6], *((_DWORD *)this + 10));
    if ( v9 )
      v9 = -1073676253;
  }
  v11 = v9 == 0;
  if ( !v9 )
  {
    if ( RdlsSecretsCache::g_pLicenseCertContext )
      CertFreeCertificateContext(RdlsSecretsCache::g_pLicenseCertContext);
    RdlsSecretsCache::g_pLicenseCertContext = CertCreateCertificateContext(1u, this[4], *((_DWORD *)this + 6));
    goto LABEL_11;
  }
LABEL_12:
  LOBYTE(v8) = v11;
  result = v9;
  RdlsSecretsCache::g_bHasHydraCert = v8;
  return result;
}

```

## disassembly

```asm
0x180081f00  mov     rax, rsp
0x180081f03  mov     [rax+8], rbx
0x180081f07  mov     [rax+10h], rbp
0x180081f0b  mov     [rax+18h], rsi
0x180081f0f  mov     [rax+20h], rdi
0x180081f13  push    r14
0x180081f15  sub     rsp, 40h
0x180081f19  mov     rbp, rdx
0x180081f1c  mov     r14, r8
0x180081f1f  mov     edx, 1
0x180081f24  mov     rsi, rcx
0x180081f27  call    ?GetLicensingCertificateStore@RdlsSecretsMemCache@@AEAAPEAU_RdlsCertData@@W4_CertDataCategory@@@Z; RdlsSecretsMemCache::GetLicensingCertificateStore(_CertDataCategory)
0x180081f2c  mov     rdx, rax; struct _RdlsCertData *
0x180081f2f  lea     r8, [rcx+8]; struct _RdlsCertData *
0x180081f33  call    ?CopyRdlsCertStore@RdlsSecretsCache@@IEAAKPEAU_RdlsCertData@@0@Z; RdlsSecretsCache::CopyRdlsCertStore(_RdlsCertData *,_RdlsCertData *)
0x180081f38  xor     ebx, ebx
0x180081f3a  mov     edi, eax
0x180081f3c  test    eax, eax
0x180081f3e  jnz     short loc_180081FA6
0x180081f40  cmp     [r14], rbx
0x180081f43  jz      short loc_180081F57
0x180081f45  mov     rcx, [r14]; hCertStore
0x180081f48  lea     edx, [rax+1]; dwFlags
0x180081f4b  call    cs:__imp_CertCloseStore
0x180081f52  nop     dword ptr [rax+rax+00h]
0x180081f57  mov     rax, [rsi]
0x180081f5a  mov     rdx, rbp
0x180081f5d  mov     rcx, rsi
0x180081f60  mov     rax, [rax+0A8h]
0x180081f67  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180081f6c  mov     [r14], rax
0x180081f6f  test    rax, rax
0x180081f72  jz      loc_18008200B
0x180081f78  mov     ecx, [rsi+28h]
0x180081f7b  mov     rdx, [rsi+30h]
0x180081f7f  mov     r9d, [rsi+18h]; cbCertEncoded
0x180081f83  mov     r8, [rsi+20h]; pbCertEncoded
0x180081f87  mov     [rsp+48h+var_20], ecx; DWORD
0x180081f8b  mov     rcx, rbp; hCryptProvOrNCryptKey
0x180081f8e  mov     [rsp+48h+var_28], rdx; BYTE *
0x180081f93  mov     rdx, rax; void *
0x180081f96  call    TLSValidateServerCertficates
0x180081f9b  mov     edi, eax
0x180081f9d  test    eax, eax
0x180081f9f  jz      short loc_180081FA6
0x180081fa1  mov     edi, 0C0010023h
0x180081fa6  test    edi, edi
0x180081fa8  jnz     short loc_180081FE4
0x180081faa  mov     rcx, cs:?g_pLicenseCertContext@RdlsSecretsCache@@2PEBU_CERT_CONTEXT@@EB; pCertContext
0x180081fb1  test    rcx, rcx
0x180081fb4  jz      short loc_180081FC2
0x180081fb6  call    cs:__imp_CertFreeCertificateContext
0x180081fbd  nop     dword ptr [rax+rax+00h]
0x180081fc2  mov     r8d, [rsi+18h]; cbCertEncoded
0x180081fc6  mov     ecx, 1; dwCertEncodingType
0x180081fcb  mov     rdx, [rsi+20h]; pbCertEncoded
0x180081fcf  call    cs:__imp_CertCreateCertificateContext
0x180081fd6  nop     dword ptr [rax+rax+00h]
0x180081fdb  mov     cs:?g_pLicenseCertContext@RdlsSecretsCache@@2PEBU_CERT_CONTEXT@@EB, rax; _CERT_CONTEXT const * const RdlsSecretsCache::g_pLicenseCertContext
0x180081fe2  test    edi, edi
0x180081fe4  mov     rbp, [rsp+48h+arg_8]
0x180081fe9  setz    bl
0x180081fec  mov     rsi, [rsp+48h+arg_10]
0x180081ff1  mov     eax, edi
0x180081ff3  mov     rdi, [rsp+48h+arg_18]
0x180081ff8  mov     cs:?g_bHasHydraCert@RdlsSecretsCache@@2HA, ebx; int RdlsSecretsCache::g_bHasHydraCert
0x180081ffe  mov     rbx, [rsp+48h+arg_0]
0x180082003  add     rsp, 40h
0x180082007  pop     r14
0x180082009  retn
0x18008200b  mov     edi, 0C0010022h
0x180082010  jmp     short loc_180081FE2
```
