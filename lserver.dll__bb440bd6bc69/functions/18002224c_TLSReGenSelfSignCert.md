# TLSReGenSelfSignCert

- ea: `0x18002224c`
- end: `0x180022563`
- name: `TLSReGenSelfSignCert`
- size: `791`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x1800198a0`

## callees

- `0x180002d26`
- `0x180020730`
- `0x18002224c`
- `0x18003a1f8`
- `0x180062f40`
- `0x1800a5010`

## import_xrefs

- `CRYPT32!CertDuplicateCertificateContext` at `0x180022461`
- `CRYPT32!CertDuplicateCertificateContext` at `0x1800224c8`
- `CRYPT32!CertDuplicateCertificateContext` at `0x180022461`
- `CRYPT32!CertDuplicateCertificateContext` at `0x1800224c8`
- `CRYPT32!CertCreateCertificateContext` at `0x1800223f4`
- `CRYPT32!CertCreateCertificateContext` at `0x1800223f4`
- `CRYPT32!CertFreeCertificateContext` at `0x180022452`
- `CRYPT32!CertFreeCertificateContext` at `0x18002248e`
- `CRYPT32!CertFreeCertificateContext` at `0x1800224b9`
- `CRYPT32!CertFreeCertificateContext` at `0x180022452`
- `CRYPT32!CertFreeCertificateContext` at `0x18002248e`
- `CRYPT32!CertFreeCertificateContext` at `0x1800224b9`
- `KERNEL32!GetLastError` at `0x180022353`
- `KERNEL32!GetLastError` at `0x180022479`
- `KERNEL32!GetLastError` at `0x180022353`
- `KERNEL32!GetLastError` at `0x180022479`
- `KERNEL32!LocalAlloc` at `0x1800222bc`
- `KERNEL32!LocalAlloc` at `0x18002233b`
- `KERNEL32!LocalAlloc` at `0x1800222bc`
- `KERNEL32!LocalAlloc` at `0x18002233b`
- `KERNEL32!LocalFree` at `0x18002231a`
- `KERNEL32!LocalFree` at `0x18002250d`
- `KERNEL32!LocalFree` at `0x180022528`
- `KERNEL32!LocalFree` at `0x18002253c`
- `KERNEL32!LocalFree` at `0x18002231a`
- `KERNEL32!LocalFree` at `0x18002250d`
- `KERNEL32!LocalFree` at `0x180022528`
- `KERNEL32!LocalFree` at `0x18002253c`

## pseudocode

```c
__int64 __fastcall TLSReGenSelfSignCert(
        HCRYPTPROV_OR_NCRYPT_KEY_HANDLE a1,
        const void *a2,
        unsigned int a3,
        unsigned int a4,
        __int64 a5)
{
  unsigned __int8 *v5; // rdi
  size_t v6; // r14
  unsigned __int8 *v7; // rsi
  DWORD LastError; // ebx
  unsigned __int16 *v10; // rax
  unsigned __int16 *v11; // r13
  HLOCAL v12; // rax
  DWORD v13; // eax
  const CERT_CONTEXT *CertificateContext; // r15
  RdlsSecretsCache *v15; // rcx
  RdlsSecretsCache *v16; // rcx
  DWORD cbCertEncoded; // [rsp+40h] [rbp-20h] BYREF
  unsigned int v19; // [rsp+44h] [rbp-1Ch] BYREF
  unsigned int v20; // [rsp+48h] [rbp-18h] BYREF
  unsigned __int8 *v21; // [rsp+50h] [rbp-10h] BYREF
  BYTE *pbCertEncoded; // [rsp+58h] [rbp-8h] BYREF

  v5 = 0;
  v6 = a3;
  cbCertEncoded = 0;
  v7 = 0;
  v20 = 0;
  pbCertEncoded = 0;
  v21 = 0;
  if ( !a1 || !a2 || !a3 )
  {
    LastError = 87;
    goto LABEL_32;
  }
  if ( a3 + 2 < a3 )
    return 4117;
  v10 = (unsigned __int16 *)LocalAlloc(0x40u, a3 + 2LL);
  v11 = v10;
  if ( !v10 )
    return 4117;
  memcpy_0(v10, a2, v6);
  v19 = 2;
  LastError = LKPLiteVerifySPK((unsigned __int16 *)String1, v11, &v19);
  if ( LastError || v19 != 2 )
  {
    if ( v19 == 1 )
    {
      LastError = -1071644670;
    }
    else if ( v19 == 3 )
    {
      LastError = -1071644669;
    }
    goto LABEL_30;
  }
  if ( Src )
  {
    LocalFree(Src);
    Src = 0;
    LODWORD(Size) = 0;
  }
  v12 = LocalAlloc(0x40u, v6);
  Src = v12;
  if ( v12 )
  {
    memcpy_0(v12, a2, v6);
    LODWORD(Size) = v6;
    LastError = (*(__int64 (__fastcall **)(RdlsSecretsCache *, size_t *, _QWORD, __int64))(*(_QWORD *)g_RdlsSecrets
                                                                                         + 80LL))(
                  g_RdlsSecrets,
                  &g_ServerIDComponents,
                  a4,
                  a5);
    if ( LastError )
      goto LABEL_30;
    v13 = TLSCreateSelfSignCertificate(a1, 2u, a4, a5, (__int64)&cbCertEncoded, (__int64)&pbCertEncoded);
    v5 = pbCertEncoded;
    LastError = v13;
    if ( v13 )
      goto LABEL_30;
    CertificateContext = CertCreateCertificateContext(1u, pbCertEncoded, cbCertEncoded);
    if ( CertificateContext )
    {
      LastError = TLSCreateSelfSignCertificate(a1, 1u, a4, a5, (__int64)&v20, (__int64)&v21);
      if ( !LastError )
      {
        if ( g_SelfSignCertContext )
          CertFreeCertificateContext(g_SelfSignCertContext);
        g_SelfSignCertContext = CertDuplicateCertificateContext(CertificateContext);
        if ( g_SelfSignCertContext )
        {
          RdlsSecretsCache::SetEndorsedRdlsCertInMemory(v15, 1, cbCertEncoded, v5);
          if ( RdlsSecretsCache::g_pLicenseCertContext )
            CertFreeCertificateContext(RdlsSecretsCache::g_pLicenseCertContext);
          RdlsSecretsCache::g_pLicenseCertContext = CertDuplicateCertificateContext(CertificateContext);
          RdlsSecretsCache::SetEndorsedRdlsCertInMemory(v16, 0, v20, v21);
          v5 = 0;
          RdlsSecretsCache::g_bHasHydraCert = 0;
          goto LABEL_22;
        }
        LastError = GetLastError();
      }
      v7 = v21;
LABEL_22:
      CertFreeCertificateContext(CertificateContext);
      goto LABEL_30;
    }
  }
  LastError = GetLastError();
LABEL_30:
  LocalFree(v11);
LABEL_32:
  if ( v5 )
    LocalFree(v5);
  if ( v7 )
    LocalFree(v7);
  return LastError;
}

```

## disassembly

```asm
0x18002224c  mov     [rsp-38h+arg_8], rbx
0x180022251  mov     [rsp-38h+arg_18], r9d
0x180022256  mov     [rsp-38h+hCryptProvOrNCryptKey], rcx
0x18002225b  push    rbp
0x18002225c  push    rsi
0x18002225d  push    rdi
0x18002225e  push    r12
0x180022260  push    r13
0x180022262  push    r14
0x180022264  push    r15
0x180022266  mov     rbp, rsp
0x180022269  sub     rsp, 60h
0x18002226d  xor     edi, edi
0x18002226f  mov     r14d, r8d
0x180022272  and     [rbp+cbCertEncoded], edi
0x180022275  xor     esi, esi
0x180022277  and     [rbp+var_18], esi
0x18002227a  mov     r12, rdx
0x18002227d  mov     [rbp+pbCertEncoded], rdi
0x180022281  mov     [rbp+var_10], rsi
0x180022285  test    rcx, rcx
0x180022288  jz      loc_18002251B
0x18002228e  test    rdx, rdx
0x180022291  jz      loc_18002251B
0x180022297  test    r8d, r8d
0x18002229a  jz      loc_18002251B
0x1800222a0  lea     eax, [r14+2]
0x1800222a4  cmp     eax, r14d
0x1800222a7  jnb     short loc_1800222B3
0x1800222a9  mov     ebx, 1015h
0x1800222ae  jmp     loc_180022548
0x1800222b3  lea     rdx, [r14+2]; uBytes
0x1800222b7  mov     ecx, 40h ; '@'; uFlags
0x1800222bc  call    cs:__imp_LocalAlloc
0x1800222c3  nop     dword ptr [rax+rax+00h]
0x1800222c8  mov     r13, rax
0x1800222cb  test    rax, rax
0x1800222ce  jz      short loc_1800222A9
0x1800222d0  mov     r8, r14; Size
0x1800222d3  mov     rdx, r12; Src
0x1800222d6  mov     rcx, rax; void *
0x1800222d9  call    memcpy_0
0x1800222de  mov     rcx, cs:String1; unsigned __int16 *
0x1800222e5  lea     r8, [rbp+var_1C]; unsigned int *
0x1800222e9  mov     rdx, r13; unsigned __int16 *
0x1800222ec  mov     [rbp+var_1C], 2
0x1800222f3  call    ?LKPLiteVerifySPK@@YAKPEAG0PEAK@Z; LKPLiteVerifySPK(ushort *,ushort *,ulong *)
0x1800222f8  mov     edx, [rbp+var_1C]
0x1800222fb  mov     ebx, eax
0x1800222fd  test    eax, eax
0x1800222ff  jnz     loc_1800224F4
0x180022305  cmp     edx, 2
0x180022308  jnz     loc_1800224F4
0x18002230e  mov     rcx, cs:Src; hMem
0x180022315  test    rcx, rcx
0x180022318  jz      short loc_180022333
0x18002231a  call    cs:__imp_LocalFree
0x180022321  nop     dword ptr [rax+rax+00h]
0x180022326  and     cs:Src, rsi
0x18002232d  and     cs:Size, esi
0x180022333  mov     rdx, r14; uBytes
0x180022336  mov     ecx, 40h ; '@'; uFlags
0x18002233b  call    cs:__imp_LocalAlloc
0x180022342  nop     dword ptr [rax+rax+00h]
0x180022347  mov     cs:Src, rax
0x18002234e  test    rax, rax
0x180022351  jnz     short loc_180022366
0x180022353  call    cs:__imp_GetLastError
0x18002235a  nop     dword ptr [rax+rax+00h]
0x18002235f  mov     ebx, eax
0x180022361  jmp     loc_18002250A
0x180022366  mov     r8, r14; Size
0x180022369  mov     rdx, r12; Src
0x18002236c  mov     rcx, rax; void *
0x18002236f  call    memcpy_0
0x180022374  mov     rcx, cs:?g_RdlsSecrets@@3PEAVRdlsSecretsCache@@EA; RdlsSecretsCache * g_RdlsSecrets
0x18002237b  lea     rdx, ?g_ServerIDComponents@@3U_ServerIDComponents@@A; _ServerIDComponents g_ServerIDComponents
0x180022382  mov     r15d, [rbp+arg_18]
0x180022386  mov     r8d, r15d
0x180022389  mov     r9, [rbp+arg_20]
0x18002238d  mov     cs:Size, r14d
0x180022394  mov     rax, [rcx]
0x180022397  mov     rax, [rax+50h]
0x18002239b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800223a0  mov     ebx, eax
0x1800223a2  test    eax, eax
0x1800223a4  jnz     loc_18002250A
0x1800223aa  mov     rcx, [rbp+hCryptProvOrNCryptKey]; hCryptProvOrNCryptKey
0x1800223ae  lea     rax, [rbp+pbCertEncoded]
0x1800223b2  mov     [rsp+60h+var_28], rax; __int64
0x1800223b7  lea     edx, [rbx+2]; dwKeySpec
0x1800223ba  lea     rax, [rbp+cbCertEncoded]
0x1800223be  mov     r9d, r14d
0x1800223c1  mov     [rsp+60h+var_30], rax; __int64
0x1800223c6  mov     r8, r12
0x1800223c9  mov     rax, [rbp+arg_20]
0x1800223cd  mov     [rsp+60h+var_38], rax; __int64
0x1800223d2  mov     [rsp+60h+var_40], r15d; int
0x1800223d7  call    TLSCreateSelfSignCertificate
0x1800223dc  mov     rdi, [rbp+pbCertEncoded]
0x1800223e0  mov     ebx, eax
0x1800223e2  test    eax, eax
0x1800223e4  jnz     loc_18002250A
0x1800223ea  mov     r8d, [rbp+cbCertEncoded]; cbCertEncoded
0x1800223ee  lea     ecx, [rax+1]; dwCertEncodingType
0x1800223f1  mov     rdx, rdi; pbCertEncoded
0x1800223f4  call    cs:__imp_CertCreateCertificateContext
0x1800223fb  nop     dword ptr [rax+rax+00h]
0x180022400  mov     r15, rax
0x180022403  test    rax, rax
0x180022406  jz      loc_180022353
0x18002240c  mov     rcx, [rbp+hCryptProvOrNCryptKey]; hCryptProvOrNCryptKey
0x180022410  lea     rax, [rbp+var_10]
0x180022414  mov     [rsp+60h+var_28], rax; __int64
0x180022419  lea     edx, [rbx+1]; dwKeySpec
0x18002241c  lea     rax, [rbp+var_18]
0x180022420  mov     r9d, r14d
0x180022423  mov     [rsp+60h+var_30], rax; __int64
0x180022428  mov     r8, r12
0x18002242b  mov     rax, [rbp+arg_20]
0x18002242f  mov     [rsp+60h+var_38], rax; __int64
0x180022434  mov     eax, [rbp+arg_18]
0x180022437  mov     [rsp+60h+var_40], eax; int
0x18002243b  call    TLSCreateSelfSignCertificate
0x180022440  mov     ebx, eax
0x180022442  test    eax, eax
0x180022444  jnz     short loc_180022487
0x180022446  mov     rcx, cs:?g_SelfSignCertContext@@3PEBU_CERT_CONTEXT@@EB; pCertContext
0x18002244d  test    rcx, rcx
0x180022450  jz      short loc_18002245E
0x180022452  call    cs:__imp_CertFreeCertificateContext
0x180022459  nop     dword ptr [rax+rax+00h]
0x18002245e  mov     rcx, r15; pCertContext
0x180022461  call    cs:__imp_CertDuplicateCertificateContext
0x180022468  nop     dword ptr [rax+rax+00h]
0x18002246d  mov     cs:?g_SelfSignCertContext@@3PEBU_CERT_CONTEXT@@EB, rax; _CERT_CONTEXT const * const g_SelfSignCertContext
0x180022474  test    rax, rax
0x180022477  jnz     short loc_18002249C
0x180022479  call    cs:__imp_GetLastError
0x180022480  nop     dword ptr [rax+rax+00h]
0x180022485  mov     ebx, eax
0x180022487  mov     rsi, [rbp+var_10]
0x18002248b  mov     rcx, r15; pCertContext
0x18002248e  call    cs:__imp_CertFreeCertificateContext
0x180022495  nop     dword ptr [rax+rax+00h]
0x18002249a  jmp     short loc_18002250A
0x18002249c  mov     r8d, [rbp+cbCertEncoded]; unsigned int
0x1800224a0  mov     r9, rdi; unsigned __int8 *
0x1800224a3  mov     edx, 1; int
0x1800224a8  call    ?SetEndorsedRdlsCertInMemory@RdlsSecretsCache@@QEAAXHKPEAE@Z; RdlsSecretsCache::SetEndorsedRdlsCertInMemory(int,ulong,uchar *)
0x1800224ad  mov     rcx, cs:?g_pLicenseCertContext@RdlsSecretsCache@@2PEBU_CERT_CONTEXT@@EB; pCertContext
0x1800224b4  test    rcx, rcx
0x1800224b7  jz      short loc_1800224C5
0x1800224b9  call    cs:__imp_CertFreeCertificateContext
0x1800224c0  nop     dword ptr [rax+rax+00h]
0x1800224c5  mov     rcx, r15; pCertContext
0x1800224c8  call    cs:__imp_CertDuplicateCertificateContext
0x1800224cf  nop     dword ptr [rax+rax+00h]
0x1800224d4  mov     r9, [rbp+var_10]; unsigned __int8 *
0x1800224d8  xor     edx, edx; int
0x1800224da  mov     r8d, [rbp+var_18]; unsigned int
0x1800224de  mov     cs:?g_pLicenseCertContext@RdlsSecretsCache@@2PEBU_CERT_CONTEXT@@EB, rax; _CERT_CONTEXT const * const RdlsSecretsCache::g_pLicenseCertContext
0x1800224e5  call    ?SetEndorsedRdlsCertInMemory@RdlsSecretsCache@@QEAAXHKPEAE@Z; RdlsSecretsCache::SetEndorsedRdlsCertInMemory(int,ulong,uchar *)
0x1800224ea  xor     edi, edi
0x1800224ec  and     cs:?g_bHasHydraCert@RdlsSecretsCache@@2HA, esi; int RdlsSecretsCache::g_bHasHydraCert
0x1800224f2  jmp     short loc_18002248B
0x1800224f4  cmp     edx, 1
0x1800224f7  jnz     short loc_180022500
0x1800224f9  mov     ebx, 0C0200002h
0x1800224fe  jmp     short loc_18002250A
0x180022500  cmp     edx, 3
0x180022503  jnz     short loc_18002250A
0x180022505  mov     ebx, 0C0200003h
0x18002250a  mov     rcx, r13; hMem
0x18002250d  call    cs:__imp_LocalFree
0x180022514  nop     dword ptr [rax+rax+00h]
0x180022519  jmp     short loc_180022520
0x18002251b  mov     ebx, 57h ; 'W'
0x180022520  test    rdi, rdi
0x180022523  jz      short loc_180022534
0x180022525  mov     rcx, rdi; hMem
0x180022528  call    cs:__imp_LocalFree
0x18002252f  nop     dword ptr [rax+rax+00h]
0x180022534  test    rsi, rsi
0x180022537  jz      short loc_180022548
0x180022539  mov     rcx, rsi; hMem
0x18002253c  call    cs:__imp_LocalFree
0x180022543  nop     dword ptr [rax+rax+00h]
0x180022548  mov     eax, ebx
0x18002254a  mov     rbx, [rsp+60h+arg_8]
0x180022552  add     rsp, 60h
0x180022556  pop     r15
0x180022558  pop     r14
0x18002255a  pop     r13
0x18002255c  pop     r12
0x18002255e  pop     rdi
0x18002255f  pop     rsi
0x180022560  pop     rbp
0x180022561  retn
```
