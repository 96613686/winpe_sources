# winrt::Windows::Internal::Eap::Utility::implementation::EapServerSchannelUtil::GetChainContext(_CERT_CONTEXT const *,winrt::Windows::Internal::Eap::Utility::EapTlsCertificateValidationFlags)

- ea: `0x180027ad8`
- end: `0x180027cc0`
- name: `?GetChainContext@EapServerSchannelUtil@implementation@Utility@Eap@Internal@Windows@winrt@@CA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEBU_CERT_CHAIN_CONTEXT@@P6AXPEBU1@@Z$1?CertFreeCertificateChain@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEBU1@PEBU1@$0A@$$T@details@wil@@@details@wil@@@wil@@PEBU_CERT_CONTEXT@@W4EapTlsCertificateValidationFlags@34567@@Z`
- size: `488`
- prototype: `PCCERT_CHAIN_CONTEXT *__fastcall(PCCERT_CHAIN_CONTEXT *ppChainContext, PCCERT_CONTEXT pCertContext, char)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x18002a008`

## callees

- `0x180002b78`
- `0x180023760`
- `0x180027ad8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180027b8e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180027b8e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027b7b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027b7b`
- `CRYPT32!CertCreateCertificateChainEngine` at `0x180027ba4`
- `CRYPT32!CertCreateCertificateChainEngine` at `0x180027ba4`
- `CRYPT32!CertCloseStore` at `0x180027c55`
- `CRYPT32!CertCloseStore` at `0x180027c55`
- `CRYPT32!CertFreeCertificateChainEngine` at `0x180027b86`
- `CRYPT32!CertFreeCertificateChainEngine` at `0x180027c65`
- `CRYPT32!CertFreeCertificateChainEngine` at `0x180027b86`
- `CRYPT32!CertFreeCertificateChainEngine` at `0x180027c65`
- `CRYPT32!CertOpenStore` at `0x180027b3d`
- `CRYPT32!CertOpenStore` at `0x180027b3d`
- `CRYPT32!CertGetCertificateChain` at `0x180027c3d`
- `CRYPT32!CertGetCertificateChain` at `0x180027c3d`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
PCCERT_CHAIN_CONTEXT *__fastcall winrt::Windows::Internal::Eap::Utility::implementation::EapServerSchannelUtil::GetChainContext(
        PCCERT_CHAIN_CONTEXT *ppChainContext,
        PCCERT_CONTEXT pCertContext,
        char a3)
{
  HCERTCHAINENGINE v6; // rcx
  HCERTSTORE v7; // rbx
  const char *v8; // r9
  HCERTCHAINENGINE v9; // r14
  DWORD LastError; // edi
  const char *v11; // r9
  const char *v12; // r9
  const char *v14; // [rsp+58h] [rbp-79h] BYREF
  struct _CERT_CHAIN_PARA pChainPara; // [rsp+60h] [rbp-71h] BYREF
  __int128 v16; // [rsp+80h] [rbp-51h]
  __int128 v17; // [rsp+90h] [rbp-41h]
  _CERT_CHAIN_ENGINE_CONFIG pConfig; // [rsp+A8h] [rbp-29h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+130h] [rbp+5Fh]
  HCERTCHAINENGINE hChainEngine; // [rsp+150h] [rbp+7Fh] BYREF

  v6 = 0;
  hChainEngine = 0;
  v7 = 0;
  if ( (a3 & 0x10) != 0 )
  {
    v7 = CertOpenStore((LPCSTR)0xA, 1u, 0, 0x28000u, L"EAPServerCustomRootStore");
    if ( !v7 )
      wil::details::in1diag3::_Throw_GetLastError(
        retaddr,
        (void *)0x373,
        (unsigned int)"onecoreuap\\net\\eaphost\\eapputil\\lib\\eapserverschannelutil.cpp",
        v8);
    memset_0(&pConfig, 0, 0x58u);
    pConfig.cbSize = 88;
    pConfig.hExclusiveRoot = v7;
    v9 = hChainEngine;
    if ( hChainEngine )
    {
      LastError = GetLastError();
      CertFreeCertificateChainEngine(v9);
      SetLastError(LastError);
    }
    hChainEngine = 0;
    if ( !CertCreateCertificateChainEngine(&pConfig, &hChainEngine) )
      wil::details::in1diag3::_Throw_GetLastError(
        retaddr,
        (void *)0x379,
        (unsigned int)"onecoreuap\\net\\eaphost\\eapputil\\lib\\eapserverschannelutil.cpp",
        v11);
    v6 = hChainEngine;
  }
  v14 = "1.3.6.1.5.5.7.3.2";
  v16 = 0;
  v17 = 0;
  *(_QWORD *)&pChainPara.cbSize = 32;
  pChainPara.RequestedUsage.dwType = 0;
  *(&pChainPara.RequestedUsage.dwType + 1) = 0;
  pChainPara.RequestedUsage.Usage.cUsageIdentifier = 1;
  *(&pChainPara.RequestedUsage.Usage.cUsageIdentifier + 1) = 0;
  pChainPara.RequestedUsage.Usage.rgpszUsageIdentifier = (LPSTR *)&v14;
  *ppChainContext = 0;
  if ( !CertGetCertificateChain(
          v6,
          pCertContext,
          0,
          pCertContext->hCertStore,
          &pChainPara,
          (a3 & 8) != 0 ? 0x80000004 : 0,
          0,
          ppChainContext) )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0x38F,
      (unsigned int)"onecoreuap\\net\\eaphost\\eapputil\\lib\\eapserverschannelutil.cpp",
      v12);
  if ( v7 )
    CertCloseStore(v7, 0);
  if ( hChainEngine )
    CertFreeCertificateChainEngine(hChainEngine);
  return ppChainContext;
}

```

## disassembly

```asm
0x180027ad8  mov     rax, rsp
0x180027adb  mov     [rax+10h], rbx
0x180027adf  mov     [rax+18h], rsi
0x180027ae3  mov     [rax+8], rcx
0x180027ae7  push    rbp
0x180027ae8  push    rdi
0x180027ae9  push    r13
0x180027aeb  push    r14
0x180027aed  push    r15
0x180027aef  lea     rbp, [rax-5Fh]
0x180027af3  sub     rsp, 100h
0x180027afa  mov     r15d, r8d
0x180027afd  mov     r13, rdx
0x180027b00  mov     rsi, rcx
0x180027b03  mov     dword ptr [rsp+120h+var_E0], 0
0x180027b0b  xor     ecx, ecx
0x180027b0d  mov     [rbp+57h+hChainEngine], rcx
0x180027b11  xor     ebx, ebx
0x180027b13  mov     [rsp+120h+var_D8], rbx
0x180027b18  test    r8b, 10h
0x180027b1c  jz      loc_180027BBA
0x180027b22  lea     rax, aEapservercusto; "EAPServerCustomRootStore"
0x180027b29  mov     [rsp+120h+pvPara], rax; pvPara
0x180027b2e  mov     r9d, 28000h; dwFlags
0x180027b34  xor     r8d, r8d; hCryptProv
0x180027b37  lea     edx, [rcx+1]; dwEncodingType
0x180027b3a  lea     ecx, [rbx+0Ah]; lpszStoreProvider
0x180027b3d  call    cs:__imp_CertOpenStore
0x180027b43  mov     rbx, rax
0x180027b46  mov     [rsp+120h+var_D8], rax
0x180027b4b  mov     rcx, [rbp+5Fh]; this
0x180027b4f  test    rax, rax
0x180027b52  jz      loc_180027C9C
0x180027b58  mov     edi, 58h ; 'X'
0x180027b5d  mov     r8d, edi; Size
0x180027b60  xor     edx, edx; Val
0x180027b62  lea     rcx, [rbp+57h+pConfig]; void *
0x180027b66  call    memset_0
0x180027b6b  mov     [rbp+57h+pConfig.cbSize], edi
0x180027b6e  mov     [rbp+57h+pConfig.hExclusiveRoot], rbx
0x180027b72  mov     r14, [rbp+57h+hChainEngine]
0x180027b76  test    r14, r14
0x180027b79  jz      short loc_180027B94
0x180027b7b  call    cs:__imp_GetLastError
0x180027b81  mov     edi, eax
0x180027b83  mov     rcx, r14; hChainEngine
0x180027b86  call    cs:__imp_CertFreeCertificateChainEngine
0x180027b8c  mov     ecx, edi; dwErrCode
0x180027b8e  call    cs:__imp_SetLastError
0x180027b94  mov     [rbp+57h+hChainEngine], 0
0x180027b9c  lea     rdx, [rbp+57h+hChainEngine]; phChainEngine
0x180027ba0  lea     rcx, [rbp+57h+pConfig]; pConfig
0x180027ba4  call    cs:__imp_CertCreateCertificateChainEngine
0x180027baa  mov     rcx, [rbp+5Fh]; this
0x180027bae  test    eax, eax
0x180027bb0  jz      loc_180027CAE
0x180027bb6  mov     rcx, [rbp+57h+hChainEngine]; hChainEngine
0x180027bba  lea     rax, a136155732; "1.3.6.1.5.5.7.3.2"
0x180027bc1  mov     [rbp+57h+var_D0], rax
0x180027bc5  xorps   xmm0, xmm0
0x180027bc8  movups  [rbp+57h+var_A8], xmm0
0x180027bcc  xorps   xmm1, xmm1
0x180027bcf  xor     eax, eax
0x180027bd1  movups  [rbp+57h+var_98], xmm1
0x180027bd5  mov     qword ptr [rbp+57h+pChainPara.cbSize], 20h ; ' '
0x180027bdd  mov     [rbp+57h+pChainPara.RequestedUsage.dwType], eax
0x180027be0  mov     eax, dword ptr [rbp+57h+var_98+4]
0x180027be3  mov     dword ptr [rbp+57h+pChainPara.RequestedUsage+4], eax
0x180027be6  mov     [rbp+57h+pChainPara.RequestedUsage.Usage.cUsageIdentifier], 1
0x180027bed  mov     eax, dword ptr [rbp+57h+var_A8+4]
0x180027bf0  mov     dword ptr [rbp+57h+pChainPara.RequestedUsage.Usage+4], eax
0x180027bf3  lea     rax, [rbp+57h+var_D0]
0x180027bf7  mov     [rbp+57h+pChainPara.RequestedUsage.Usage.rgpszUsageIdentifier], rax
0x180027bfb  and     r15b, 8
0x180027bff  neg     r15b
0x180027c02  sbb     eax, eax
0x180027c04  and     eax, 80000004h
0x180027c09  mov     dword ptr [rsp+120h+var_E0], 1
0x180027c11  mov     qword ptr [rsi], 0
0x180027c18  mov     [rsp+120h+ppChainContext], rsi; ppChainContext
0x180027c1d  mov     [rsp+120h+pvReserved], 0; pvReserved
0x180027c26  mov     [rsp+120h+dwFlags], eax; dwFlags
0x180027c2a  lea     rax, [rbp+57h+pChainPara]
0x180027c2e  mov     [rsp+120h+pvPara], rax; pChainPara
0x180027c33  mov     r9, [r13+20h]; hAdditionalStore
0x180027c37  xor     r8d, r8d; pTime
0x180027c3a  mov     rdx, r13; pCertContext
0x180027c3d  call    cs:__imp_CertGetCertificateChain
0x180027c43  mov     rcx, [rbp+5Fh]; this
0x180027c47  test    eax, eax
0x180027c49  jz      short loc_180027C8A
0x180027c4b  test    rbx, rbx
0x180027c4e  jz      short loc_180027C5C
0x180027c50  xor     edx, edx; dwFlags
0x180027c52  mov     rcx, rbx; hCertStore
0x180027c55  call    cs:__imp_CertCloseStore
0x180027c5b  nop
0x180027c5c  mov     rcx, [rbp+57h+hChainEngine]; hChainEngine
0x180027c60  test    rcx, rcx
0x180027c63  jz      short loc_180027C6B
0x180027c65  call    cs:__imp_CertFreeCertificateChainEngine
0x180027c6b  mov     rax, rsi
0x180027c6e  lea     r11, [rsp+120h+var_20]
0x180027c76  mov     rbx, [r11+38h]
0x180027c7a  mov     rsi, [r11+40h]
0x180027c7e  mov     rsp, r11
0x180027c81  pop     r15
0x180027c83  pop     r14
0x180027c85  pop     r13
0x180027c87  pop     rdi
0x180027c88  pop     rbp
0x180027c89  retn
0x180027c8a  lea     r8, aOnecoreuapNetE_1; "onecoreuap\\net\\eaphost\\eapputil\\lib"...
0x180027c91  mov     edx, 38Fh; void *
0x180027c96  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x180027c9c  lea     r8, aOnecoreuapNetE_1; "onecoreuap\\net\\eaphost\\eapputil\\lib"...
0x180027ca3  mov     edx, 373h; void *
0x180027ca8  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x180027cae  lea     r8, aOnecoreuapNetE_1; "onecoreuap\\net\\eaphost\\eapputil\\lib"...
0x180027cb5  mov     edx, 379h; void *
0x180027cba  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
```
