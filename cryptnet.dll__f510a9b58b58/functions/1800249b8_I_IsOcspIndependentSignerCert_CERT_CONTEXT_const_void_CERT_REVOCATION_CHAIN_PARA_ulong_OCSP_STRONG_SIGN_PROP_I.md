# I_IsOcspIndependentSignerCert(_CERT_CONTEXT const *,void *,_CERT_REVOCATION_CHAIN_PARA *,ulong,_OCSP_STRONG_SIGN_PROP_INFO *)

- ea: `0x1800249b8`
- end: `0x180024bed`
- name: `?I_IsOcspIndependentSignerCert@@YAHPEBU_CERT_CONTEXT@@PEAXPEAU_CERT_REVOCATION_CHAIN_PARA@@KPEAU_OCSP_STRONG_SIGN_PROP_INFO@@@Z`
- size: `565`
- prototype: `__int64 __fastcall(PCCERT_CONTEXT pCertContext, HCERTSTORE hCertStore, struct _CERT_REVOCATION_CHAIN_PARA *, char, struct _OCSP_STRONG_SIGN_PROP_INFO *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000ddb0`

## callees

- `0x1800249b8`
- `0x180024bf4`
- `0x18002656a`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180024a18`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180024a4b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180024a18`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180024a4b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024a1e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024a1e`
- `CRYPT32!CertCloseStore` at `0x180024a42`
- `CRYPT32!CertCloseStore` at `0x180024a42`
- `CRYPT32!CertOpenStore` at `0x180024a80`
- `CRYPT32!CertOpenStore` at `0x180024a80`
- `CRYPT32!CertFreeCertificateChain` at `0x180024a32`
- `CRYPT32!CertFreeCertificateChain` at `0x180024a32`
- `CRYPT32!CertVerifyCertificateChainPolicy` at `0x180024ba8`
- `CRYPT32!CertVerifyCertificateChainPolicy` at `0x180024ba8`
- `CRYPT32!CertGetCertificateChain` at `0x180024b62`
- `CRYPT32!CertGetCertificateChain` at `0x180024b62`
- `CRYPT32!CertDuplicateStore` at `0x180024ac7`
- `CRYPT32!CertDuplicateStore` at `0x180024ac7`
- `CRYPT32!CertAddStoreToCollection` at `0x180024a9a`
- `CRYPT32!CertAddStoreToCollection` at `0x180024ab5`
- `CRYPT32!CertAddStoreToCollection` at `0x180024a9a`
- `CRYPT32!CertAddStoreToCollection` at `0x180024ab5`

## pseudocode

```c
__int64 __fastcall I_IsOcspIndependentSignerCert(
        PCCERT_CONTEXT pCertContext,
        HCERTSTORE hCertStore,
        struct _CERT_REVOCATION_CHAIN_PARA *a3,
        char a4,
        struct _OCSP_STRONG_SIGN_PROP_INFO *a5)
{
  bool v9; // cf
  HCERTSTORE v10; // rdi
  DWORD dwError; // ecx
  DWORD LastError; // r14d
  unsigned int v13; // esi
  HCERTSTORE v15; // rax
  struct _FILETIME *pftCurrentTime; // r8
  DWORD v17; // eax
  unsigned __int16 *ChainStrongCNGAlgidPropertyList; // rax
  struct _OCSP_STRONG_SIGN_PROP_INFO *v19; // rbx
  const struct _CERT_CHAIN_CONTEXT *v20; // rcx
  const char *v21; // [rsp+40h] [rbp-71h] BYREF
  _CERT_CHAIN_POLICY_PARA pPolicyPara; // [rsp+48h] [rbp-69h] BYREF
  _CERT_CHAIN_POLICY_STATUS pPolicyStatus; // [rsp+58h] [rbp-59h] BYREF
  _CERT_CHAIN_PARA pChainPara; // [rsp+70h] [rbp-41h] BYREF
  DWORD dwUrlRetrievalTimeout; // [rsp+A8h] [rbp-9h]
  LPFILETIME pftCacheResync; // [rsp+B8h] [rbp+7h]
  PCCERT_CHAIN_CONTEXT pChainContext; // [rsp+120h] [rbp+6Fh] BYREF

  v21 = 0;
  memset_0(&pChainPara, 0, 0x60u);
  pChainContext = 0;
  v9 = a3->cbSize < 0x38;
  pPolicyPara = 0;
  memset(&pPolicyStatus, 0, sizeof(pPolicyStatus));
  if ( v9 )
  {
    v10 = 0;
    dwError = -2147024809;
    goto LABEL_3;
  }
  if ( a3->hAdditionalStore )
  {
    v15 = CertOpenStore((LPCSTR)0xB, 0x10001u, 0, 4u, 0);
    v10 = v15;
    if ( !v15
      || !CertAddStoreToCollection(v15, hCertStore, 0, 0)
      || !CertAddStoreToCollection(v10, a3->hAdditionalStore, 0, 0) )
    {
      goto LABEL_4;
    }
  }
  else
  {
    v10 = CertDuplicateStore(hCertStore);
  }
  v21 = "1.3.6.1.5.5.7.3.9";
  memset_0(&pChainPara, 0, 0x60u);
  pftCurrentTime = a3->pftCurrentTime;
  pChainPara.RequestedUsage.Usage.rgpszUsageIdentifier = (LPSTR *)&v21;
  dwUrlRetrievalTimeout = a3->dwUrlRetrievalTimeout;
  v13 = 1;
  pftCacheResync = a3->pftCacheResync;
  v17 = a3->dwChainFlags & 0xFC00053E;
  pChainPara.cbSize = 96;
  pChainPara.RequestedUsage.dwType = 0;
  pChainPara.RequestedUsage.Usage.cUsageIdentifier = 1;
  if ( !CertGetCertificateChain(
          a3->hChainEngine,
          pCertContext,
          pftCurrentTime,
          v10,
          &pChainPara,
          v17 | ((a4 & 2) != 0 ? -2080374780 : 0x4000000),
          0,
          &pChainContext)
    || (pPolicyPara.pvExtraPolicyPara = 0,
        pPolicyPara.cbSize = 16,
        memset(&pPolicyStatus, 0, sizeof(pPolicyStatus)),
        pPolicyStatus.cbSize = 24,
        pPolicyPara.dwFlags = 3840,
        !CertVerifyCertificateChainPolicy((LPCSTR)1, pChainContext, &pPolicyPara, &pPolicyStatus)) )
  {
LABEL_4:
    LastError = GetLastError();
    v13 = 0;
    goto LABEL_5;
  }
  dwError = pPolicyStatus.dwError;
  if ( pPolicyStatus.dwError )
  {
LABEL_3:
    SetLastError(dwError);
    goto LABEL_4;
  }
  LastError = 0;
  ChainStrongCNGAlgidPropertyList = OcspGetChainStrongCNGAlgidPropertyList(pChainContext, 0x59u);
  v19 = a5;
  v20 = pChainContext;
  *((_QWORD *)a5 + 1) = ChainStrongCNGAlgidPropertyList;
  *((_QWORD *)v19 + 2) = OcspGetChainStrongCNGAlgidPropertyList(v20, 0x5Du);
LABEL_5:
  if ( pChainContext )
    CertFreeCertificateChain(pChainContext);
  if ( v10 )
    CertCloseStore(v10, 0);
  SetLastError(LastError);
  return v13;
}

```

## disassembly

```asm
0x1800249b8  push    rbp
0x1800249ba  push    rbx
0x1800249bb  push    rsi
0x1800249bc  push    rdi
0x1800249bd  push    r14
0x1800249bf  push    r15
0x1800249c1  lea     rbp, [rsp-27h]
0x1800249c6  sub     rsp, 0D8h
0x1800249cd  mov     rsi, rdx
0x1800249d0  mov     [rbp+4Fh+var_C0], 0
0x1800249d8  xor     edx, edx; Val
0x1800249da  mov     rbx, r8
0x1800249dd  mov     r15, rcx
0x1800249e0  mov     r14d, r9d
0x1800249e3  lea     rcx, [rbp+4Fh+pChainPara]; void *
0x1800249e7  lea     r8d, [rdx+60h]; Size
0x1800249eb  call    memset_0
0x1800249f0  xor     eax, eax
0x1800249f2  mov     [rbp+4Fh+pChainContext], 0
0x1800249fa  cmp     dword ptr [rbx], 38h ; '8'
0x1800249fd  xorps   xmm0, xmm0
0x180024a00  xorps   xmm1, xmm1
0x180024a03  mov     [rbp+4Fh+pPolicyStatus.pvExtraPolicyStatus], rax
0x180024a07  movups  xmmword ptr [rbp+4Fh+pPolicyPara.cbSize], xmm0
0x180024a0b  movups  xmmword ptr [rbp+4Fh+pPolicyStatus.cbSize], xmm1
0x180024a0f  jnb     short loc_180024A63
0x180024a11  xor     edi, edi
0x180024a13  mov     ecx, 80070057h; dwErrCode
0x180024a18  call    cs:__imp_SetLastError
0x180024a1e  call    cs:__imp_GetLastError
0x180024a24  mov     r14d, eax
0x180024a27  xor     esi, esi
0x180024a29  mov     rcx, [rbp+4Fh+pChainContext]; pChainContext
0x180024a2d  test    rcx, rcx
0x180024a30  jz      short loc_180024A38
0x180024a32  call    cs:__imp_CertFreeCertificateChain
0x180024a38  test    rdi, rdi
0x180024a3b  jz      short loc_180024A48
0x180024a3d  xor     edx, edx; dwFlags
0x180024a3f  mov     rcx, rdi; hCertStore
0x180024a42  call    cs:__imp_CertCloseStore
0x180024a48  mov     ecx, r14d; dwErrCode
0x180024a4b  call    cs:__imp_SetLastError
0x180024a51  mov     eax, esi
0x180024a53  add     rsp, 0D8h
0x180024a5a  pop     r15
0x180024a5c  pop     r14
0x180024a5e  pop     rdi
0x180024a5f  pop     rsi
0x180024a60  pop     rbx
0x180024a61  pop     rbp
0x180024a62  retn
0x180024a63  cmp     [rbx+10h], rax
0x180024a67  jz      short loc_180024AC4
0x180024a69  mov     r9d, 4; dwFlags
0x180024a6f  mov     [rsp+100h+pvPara], rax; pvPara
0x180024a74  xor     r8d, r8d; hCryptProv
0x180024a77  mov     edx, 10001h; dwEncodingType
0x180024a7c  lea     ecx, [r9+7]; lpszStoreProvider
0x180024a80  call    cs:__imp_CertOpenStore
0x180024a86  mov     rdi, rax
0x180024a89  test    rax, rax
0x180024a8c  jz      short loc_180024A1E
0x180024a8e  xor     r9d, r9d; dwPriority
0x180024a91  xor     r8d, r8d; dwUpdateFlags
0x180024a94  mov     rdx, rsi; hSiblingStore
0x180024a97  mov     rcx, rax; hCollectionStore
0x180024a9a  call    cs:__imp_CertAddStoreToCollection
0x180024aa0  test    eax, eax
0x180024aa2  jz      loc_180024A1E
0x180024aa8  mov     rdx, [rbx+10h]; hSiblingStore
0x180024aac  xor     r9d, r9d; dwPriority
0x180024aaf  xor     r8d, r8d; dwUpdateFlags
0x180024ab2  mov     rcx, rdi; hCollectionStore
0x180024ab5  call    cs:__imp_CertAddStoreToCollection
0x180024abb  test    eax, eax
0x180024abd  jnz     short loc_180024AD0
0x180024abf  jmp     loc_180024A1E
0x180024ac4  mov     rcx, rsi; hCertStore
0x180024ac7  call    cs:__imp_CertDuplicateStore
0x180024acd  mov     rdi, rax
0x180024ad0  xor     edx, edx; Val
0x180024ad2  lea     rax, a136155739; "1.3.6.1.5.5.7.3.9"
0x180024ad9  lea     rcx, [rbp+4Fh+pChainPara]; void *
0x180024add  mov     [rbp+4Fh+var_C0], rax
0x180024ae1  lea     r8d, [rdx+60h]; Size
0x180024ae5  call    memset_0
0x180024aea  mov     r8, [rbx+20h]; pTime
0x180024aee  lea     rax, [rbp+4Fh+var_C0]
0x180024af2  mov     [rbp+4Fh+pChainPara.RequestedUsage.Usage.rgpszUsageIdentifier], rax
0x180024af6  and     r14b, 2
0x180024afa  mov     eax, [rbx+1Ch]
0x180024afd  neg     r14b
0x180024b00  mov     [rbp+4Fh+var_58], eax
0x180024b03  mov     esi, 1
0x180024b08  mov     rax, [rbx+28h]
0x180024b0c  sbb     ecx, ecx
0x180024b0e  mov     [rbp+4Fh+var_48], rax
0x180024b12  and     ecx, 80000004h
0x180024b18  mov     eax, [rbx+18h]
0x180024b1b  add     ecx, 4000000h
0x180024b21  and     eax, 0FC00053Eh
0x180024b26  mov     [rbp+4Fh+pChainPara.cbSize], 60h ; '`'
0x180024b2d  or      ecx, eax
0x180024b2f  mov     [rbp+4Fh+pChainPara.RequestedUsage.dwType], 0
0x180024b36  lea     rax, [rbp+4Fh+pChainContext]
0x180024b3a  mov     [rbp+4Fh+pChainPara.RequestedUsage.Usage.cUsageIdentifier], esi
0x180024b3d  mov     [rsp+100h+ppChainContext], rax; ppChainContext
0x180024b42  mov     r9, rdi; hAdditionalStore
0x180024b45  mov     [rsp+100h+pvReserved], 0; pvReserved
0x180024b4e  lea     rax, [rbp+4Fh+pChainPara]
0x180024b52  mov     [rsp+100h+dwFlags], ecx; dwFlags
0x180024b56  mov     rdx, r15; pCertContext
0x180024b59  mov     rcx, [rbx+8]; hChainEngine
0x180024b5d  mov     [rsp+100h+pvPara], rax; pChainPara
0x180024b62  call    cs:__imp_CertGetCertificateChain
0x180024b68  test    eax, eax
0x180024b6a  jz      loc_180024A1E
0x180024b70  mov     rdx, [rbp+4Fh+pChainContext]; pChainContext
0x180024b74  lea     r9, [rbp+4Fh+pPolicyStatus]; pPolicyStatus
0x180024b78  xorps   xmm0, xmm0
0x180024b7b  mov     [rbp+4Fh+pPolicyPara.pvExtraPolicyPara], 0
0x180024b83  xor     eax, eax
0x180024b85  mov     [rbp+4Fh+pPolicyPara.cbSize], 10h
0x180024b8c  movups  xmmword ptr [rbp+4Fh+pPolicyStatus.cbSize], xmm0
0x180024b90  lea     r8, [rbp+4Fh+pPolicyPara]; pPolicyPara
0x180024b94  mov     [rbp+4Fh+pPolicyStatus.cbSize], 18h
0x180024b9b  mov     ecx, esi; pszPolicyOID
0x180024b9d  mov     [rbp+4Fh+pPolicyPara.dwFlags], 0F00h
0x180024ba4  mov     [rbp+4Fh+pPolicyStatus.pvExtraPolicyStatus], rax
0x180024ba8  call    cs:__imp_CertVerifyCertificateChainPolicy
0x180024bae  test    eax, eax
0x180024bb0  jz      loc_180024A1E
0x180024bb6  mov     ecx, [rbp+4Fh+pPolicyStatus.dwError]
0x180024bb9  test    ecx, ecx
0x180024bbb  jnz     loc_180024A18
0x180024bc1  mov     rcx, [rbp+4Fh+pChainContext]; struct _CERT_CHAIN_CONTEXT *
0x180024bc5  lea     edx, [rsi+58h]; unsigned int
0x180024bc8  xor     r14d, r14d
0x180024bcb  call    ?OcspGetChainStrongCNGAlgidPropertyList@@YAPEAGPEBU_CERT_CHAIN_CONTEXT@@K@Z; OcspGetChainStrongCNGAlgidPropertyList(_CERT_CHAIN_CONTEXT const *,ulong)
0x180024bd0  mov     rbx, [rbp+4Fh+arg_20]
0x180024bd4  lea     edx, [rsi+5Ch]; unsigned int
0x180024bd7  mov     rcx, [rbp+4Fh+pChainContext]; struct _CERT_CHAIN_CONTEXT *
0x180024bdb  mov     [rbx+8], rax
0x180024bdf  call    ?OcspGetChainStrongCNGAlgidPropertyList@@YAPEAGPEBU_CERT_CHAIN_CONTEXT@@K@Z; OcspGetChainStrongCNGAlgidPropertyList(_CERT_CHAIN_CONTEXT const *,ulong)
0x180024be4  mov     [rbx+10h], rax
0x180024be8  jmp     loc_180024A29
```
