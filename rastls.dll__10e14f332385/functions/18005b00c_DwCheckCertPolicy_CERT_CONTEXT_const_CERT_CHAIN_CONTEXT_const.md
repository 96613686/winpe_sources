# DwCheckCertPolicy(_CERT_CONTEXT const *,_CERT_CHAIN_CONTEXT const * *)

- ea: `0x18005b00c`
- end: `0x18005b4e1`
- name: `?DwCheckCertPolicy@@YAKPEBU_CERT_CONTEXT@@PEAPEBU_CERT_CHAIN_CONTEXT@@@Z`
- size: `1237`
- prototype: `__int64 __fastcall(PCCERT_CONTEXT pCertContext, const struct _CERT_CHAIN_CONTEXT **)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config`

## callers

- `0x18004c178`

## callees

- `0x180004bd0`
- `0x1800075b0`
- `0x180035680`
- `0x180036230`
- `0x180036254`
- `0x180036930`
- `0x18004b3e0`
- `0x180058ddc`
- `0x18005b00c`
- `0x18005b734`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005b19b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005b1bd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005b214`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005b2b0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005b314`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005b36a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005b19b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005b1bd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005b214`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005b2b0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005b314`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005b36a`
- `CRYPT32!CertGetCertificateContextProperty` at `0x18005b404`
- `CRYPT32!CertGetCertificateContextProperty` at `0x18005b404`
- `CRYPT32!CertOpenStore` at `0x18005b151`
- `CRYPT32!CertOpenStore` at `0x18005b151`
- `CRYPT32!CertFreeCertificateChainEngine` at `0x18005b461`
- `CRYPT32!CertFreeCertificateChainEngine` at `0x18005b461`
- `CRYPT32!CertGetCertificateChain` at `0x18005b20a`
- `CRYPT32!CertGetCertificateChain` at `0x18005b20a`
- `CRYPT32!CertCreateCertificateChainEngine` at `0x18005b191`
- `CRYPT32!CertCreateCertificateChainEngine` at `0x18005b191`
- `CRYPT32!CertFreeCertificateChain` at `0x18005b4d6`
- `CRYPT32!CertFreeCertificateChain` at `0x18005b4d6`
- `CRYPT32!CertVerifyCertificateChainPolicy` at `0x18005b2a6`
- `CRYPT32!CertVerifyCertificateChainPolicy` at `0x18005b30a`
- `CRYPT32!CertVerifyCertificateChainPolicy` at `0x18005b360`
- `CRYPT32!CertVerifyCertificateChainPolicy` at `0x18005b2a6`
- `CRYPT32!CertVerifyCertificateChainPolicy` at `0x18005b30a`
- `CRYPT32!CertVerifyCertificateChainPolicy` at `0x18005b360`
- `ext-ms-win-rastlsext-eap-l1-1-0!RasTlsExt_GetConfigCacheOnlyCertValidation` at `0x18005b0f6`
- `ext-ms-win-rastlsext-eap-l1-1-0!RasTlsExt_GetConfigCacheOnlyCertValidation` at `0x18005b0f6`

## pseudocode

```c
__int64 __fastcall DwCheckCertPolicy(PCCERT_CONTEXT pCertContext, const struct _CERT_CHAIN_CONTEXT **a2)
{
  DWORD dwFlags; // edi
  HCERTSTORE v5; // rax
  void *v6; // rbx
  DWORD LastError; // eax
  DWORD dwError; // ebx
  struct _EAPTLS_CONTROL_BLOCK *v9; // rcx
  __int64 v10; // rdx
  DWORD v11; // eax
  DWORD v12; // edi
  PCERT_SIMPLE_CHAIN v13; // r15
  PCERT_CHAIN_ELEMENT *rgpElement; // rax
  char *v15; // r12
  unsigned int i; // esi
  PCCERT_CHAIN_CONTEXT pChainContext; // [rsp+40h] [rbp-C0h] BYREF
  int v19; // [rsp+48h] [rbp-B8h] BYREF
  struct _CERT_CHAIN_POLICY_PARA pPolicyPara; // [rsp+50h] [rbp-B0h] BYREF
  HCERTCHAINENGINE phChainEngine; // [rsp+60h] [rbp-A0h] BYREF
  void *v22; // [rsp+68h] [rbp-98h] BYREF
  struct _CERT_CHAIN_POLICY_STATUS pPolicyStatus; // [rsp+70h] [rbp-90h] BYREF
  _CERT_CHAIN_PARA pChainPara; // [rsp+88h] [rbp-78h] BYREF
  const char *v25; // [rsp+A8h] [rbp-58h] BYREF
  __int128 v26; // [rsp+B0h] [rbp-50h]
  _CERT_CHAIN_ENGINE_CONFIG pConfig; // [rsp+D0h] [rbp-30h] BYREF
  __int128 pvData; // [rsp+130h] [rbp+30h] BYREF
  __int64 v29; // [rsp+140h] [rbp+40h]

  v25 = "1.3.6.1.5.5.7.3.2";
  pChainContext = 0;
  v19 = 0;
  memset(&pChainPara, 0, sizeof(pChainPara));
  pPolicyPara = 0;
  memset(&pPolicyStatus, 0, sizeof(pPolicyStatus));
  memset_0(&pConfig, 0, 0x58u);
  phChainEngine = 0;
  v22 = 0;
  if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 36, &WPP_88923bd842923c348eb3d02ba21152e8_Traceguids);
  *a2 = 0;
  v26 = 0;
  *(&pChainPara.RequestedUsage.dwType + 1) = 0;
  pvData = 0;
  *(&pChainPara.RequestedUsage.Usage.cUsageIdentifier + 1) = 0;
  pChainPara.RequestedUsage.Usage.rgpszUsageIdentifier = (LPSTR *)&v25;
  *(_QWORD *)&pChainPara.cbSize = 32;
  pChainPara.RequestedUsage.dwType = 0;
  pChainPara.RequestedUsage.Usage.cUsageIdentifier = 1;
  if ( (unsigned __int8)IsRasTlsExt_GetPinUserBlobPresent() )
  {
    dwFlags = (unsigned int)RasTlsExt_GetConfigCacheOnlyCertValidation() != 0 ? 0x80000004 : 0;
  }
  else
  {
    dwFlags = 0;
    if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 37, &WPP_88923bd842923c348eb3d02ba21152e8_Traceguids);
  }
  if ( g_useCustomRootStore )
  {
    v5 = CertOpenStore((LPCSTR)0xA, 1u, 0, 0x28000u, L"EAPServerCustomRootStore");
    _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CertCloseStoreNoParam_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
      &v22,
      v5);
    v6 = v22;
    if ( !v22 )
    {
      LastError = GetLastError();
      dwError = LastError;
      v9 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
        goto LABEL_41;
      v10 = 38;
      goto LABEL_40;
    }
    memset_0(&pConfig, 0, 0x58u);
    pConfig.cbSize = 88;
    pConfig.hExclusiveRoot = v6;
    if ( !CertCreateCertificateChainEngine(&pConfig, &phChainEngine) )
    {
      LastError = GetLastError();
      dwError = LastError;
      v9 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
        goto LABEL_41;
      v10 = 39;
LABEL_40:
      WPP_SF_d(*((_QWORD *)v9 + 2), v10, &WPP_88923bd842923c348eb3d02ba21152e8_Traceguids, LastError);
      goto LABEL_41;
    }
  }
  if ( !CertGetCertificateChain(
          phChainEngine,
          pCertContext,
          0,
          pCertContext->hCertStore,
          &pChainPara,
          dwFlags,
          0,
          &pChainContext) )
  {
    v11 = GetLastError();
    dwError = v11;
    if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 40, &WPP_88923bd842923c348eb3d02ba21152e8_Traceguids, v11);
    pChainContext = 0;
LABEL_41:
    if ( !dwError )
      goto LABEL_52;
    goto LABEL_59;
  }
  pPolicyPara.pvExtraPolicyPara = 0;
  dwError = 0;
  pPolicyPara.cbSize = 16;
  pPolicyPara.dwFlags = 0x40000000;
  GetDisableEndEntityClientCheck(&v19);
  if ( v19 )
    pPolicyPara.dwFlags |= 0x80000000;
  memset(&pPolicyStatus, 0, sizeof(pPolicyStatus));
  pPolicyStatus.cbSize = 24;
  if ( !g_eapTlsDisableADChecks )
  {
    if ( CertVerifyCertificateChainPolicy((LPCSTR)6, pChainContext, &pPolicyPara, &pPolicyStatus) )
    {
      LastError = pPolicyStatus.dwError;
      if ( !pPolicyStatus.dwError )
      {
        *a2 = pChainContext;
        goto LABEL_41;
      }
      dwError = pPolicyStatus.dwError;
      v9 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
        goto LABEL_41;
      v10 = 42;
    }
    else
    {
      LastError = GetLastError();
      dwError = LastError;
      v9 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
        goto LABEL_41;
      v10 = 41;
    }
    goto LABEL_40;
  }
  if ( !CertVerifyCertificateChainPolicy((LPCSTR)1, pChainContext, &pPolicyPara, &pPolicyStatus) )
  {
    LastError = GetLastError();
    dwError = LastError;
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
      goto LABEL_41;
    v10 = 43;
    goto LABEL_40;
  }
  LastError = pPolicyStatus.dwError;
  if ( pPolicyStatus.dwError )
  {
    dwError = pPolicyStatus.dwError;
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
      goto LABEL_41;
    v10 = 44;
    goto LABEL_40;
  }
  if ( !CertVerifyCertificateChainPolicy((LPCSTR)1, pChainContext, &pPolicyPara, &pPolicyStatus) )
  {
    LastError = GetLastError();
    dwError = LastError;
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
      goto LABEL_41;
    v10 = 45;
    goto LABEL_40;
  }
  LastError = pPolicyStatus.dwError;
  if ( pPolicyStatus.dwError )
  {
    dwError = pPolicyStatus.dwError;
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
      goto LABEL_41;
    v10 = 46;
    goto LABEL_40;
  }
  v12 = 0;
  v13 = *pChainContext->rgpChain;
  while ( v12 < v13->cElement )
  {
    v29 = 0;
    rgpElement = v13->rgpElement;
    pvData = 0;
    LODWORD(pvData) = 20;
    if ( CertGetCertificateContextProperty(rgpElement[v12]->pCertContext, 3u, (char *)&pvData + 4, (DWORD *)&pvData) )
    {
      v15 = (char *)g_eapTlsCACertList;
      for ( i = 0; i < g_eapTlsNumCACerts; ++i )
      {
        if ( !memcmp_0((char *)&pvData + 4, &v15[24 * i + 4], (unsigned int)pvData) )
        {
          *a2 = pChainContext;
          goto LABEL_52;
        }
      }
    }
    ++v12;
  }
  if ( !*a2 )
  {
    dwError = -2146762478;
LABEL_59:
    if ( pChainContext )
      CertFreeCertificateChain(pChainContext);
  }
LABEL_52:
  if ( phChainEngine )
    CertFreeCertificateChainEngine(phChainEngine);
  if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 47, &WPP_88923bd842923c348eb3d02ba21152e8_Traceguids);
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CertCloseStoreNoParam_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v22);
  return dwError;
}

```

## disassembly

```asm
0x18005b00c  mov     [rsp-8+arg_10], rbx
0x18005b011  push    rbp
0x18005b012  push    rsi
0x18005b013  push    rdi
0x18005b014  push    r12
0x18005b016  push    r13
0x18005b018  push    r14
0x18005b01a  push    r15
0x18005b01c  lea     rbp, [rsp-50h]
0x18005b021  sub     rsp, 150h
0x18005b028  mov     rax, cs:__security_cookie
0x18005b02f  xor     rax, rsp
0x18005b032  mov     [rbp+80h+var_38], rax
0x18005b036  xor     r13d, r13d
0x18005b039  lea     rax, Buf1; "1.3.6.1.5.5.7.3.2"
0x18005b040  xorps   xmm0, xmm0
0x18005b043  mov     [rbp+80h+var_D8], rax
0x18005b047  mov     r14, rdx
0x18005b04a  mov     [rsp+180h+pChainContext], r13
0x18005b04f  mov     rsi, rcx
0x18005b052  mov     [rsp+180h+var_138], r13d
0x18005b057  xorps   xmm1, xmm1
0x18005b05a  lea     r8d, [r13+58h]; Size
0x18005b05e  xor     eax, eax
0x18005b060  lea     rcx, [rbp+80h+pConfig]; void *
0x18005b064  xor     edx, edx; Val
0x18005b066  mov     [rbp+80h+pPolicyStatus.pvExtraPolicyStatus], rax
0x18005b06a  movups  xmmword ptr [rbp+80h+pChainPara.cbSize], xmm0
0x18005b06e  movups  xmmword ptr [rbp+80h+pChainPara.RequestedUsage.Usage.cUsageIdentifier], xmm0
0x18005b072  movups  xmmword ptr [rsp+180h+pPolicyPara.cbSize], xmm0
0x18005b077  movups  xmmword ptr [rsp+180h+pPolicyStatus.cbSize], xmm1
0x18005b07c  call    memset_0
0x18005b081  mov     [rsp+180h+phChainEngine], r13
0x18005b086  mov     [rsp+180h+var_118], r13
0x18005b08b  mov     rcx, cs:WPP_GLOBAL_Control
0x18005b092  lea     r12, WPP_GLOBAL_Control
0x18005b099  lea     r15, WPP_88923bd842923c348eb3d02ba21152e8_Traceguids
0x18005b0a0  cmp     rcx, r12
0x18005b0a3  jz      short loc_18005B0B5
0x18005b0a5  mov     rcx, [rcx+10h]
0x18005b0a9  lea     edx, [r13+24h]
0x18005b0ad  mov     r8, r15
0x18005b0b0  call    WPP_SF_
0x18005b0b5  xorps   xmm1, xmm1
0x18005b0b8  mov     [r14], r13
0x18005b0bb  movups  [rbp+80h+var_D0], xmm1
0x18005b0bf  mov     eax, dword ptr [rbp+80h+var_D0+4]
0x18005b0c2  mov     dword ptr [rbp+80h+pChainPara.RequestedUsage+4], eax
0x18005b0c5  xorps   xmm0, xmm0
0x18005b0c8  movups  [rbp+80h+pvData], xmm0
0x18005b0cc  mov     eax, dword ptr [rbp+80h+pvData+4]
0x18005b0cf  mov     dword ptr [rbp+80h+pChainPara.RequestedUsage.Usage+4], eax
0x18005b0d2  lea     rax, [rbp+80h+var_D8]
0x18005b0d6  mov     [rbp+80h+pChainPara.RequestedUsage.Usage.rgpszUsageIdentifier], rax
0x18005b0da  mov     qword ptr [rbp+80h+pChainPara.cbSize], 20h ; ' '
0x18005b0e2  mov     [rbp+80h+pChainPara.RequestedUsage.dwType], r13d
0x18005b0e6  mov     [rbp+80h+pChainPara.RequestedUsage.Usage.cUsageIdentifier], 1
0x18005b0ed  call    IsRasTlsExt_GetPinUserBlobPresent
0x18005b0f2  test    al, al
0x18005b0f4  jz      short loc_18005B108
0x18005b0f6  call    cs:__imp_RasTlsExt_GetConfigCacheOnlyCertValidation
0x18005b0fc  neg     eax
0x18005b0fe  sbb     edi, edi
0x18005b100  and     edi, 80000004h
0x18005b106  jmp     short loc_18005B128
0x18005b108  mov     rcx, cs:WPP_GLOBAL_Control
0x18005b10f  mov     edi, r13d
0x18005b112  cmp     rcx, r12
0x18005b115  jz      short loc_18005B128
0x18005b117  mov     rcx, [rcx+10h]
0x18005b11b  mov     edx, 25h ; '%'
0x18005b120  mov     r8, r15
0x18005b123  call    WPP_SF_
0x18005b128  cmp     cs:?g_useCustomRootStore@@3_NA, r13b; bool g_useCustomRootStore
0x18005b12f  jz      loc_18005B1DF
0x18005b135  xor     r8d, r8d; hCryptProv
0x18005b138  lea     rax, aEapservercusto; "EAPServerCustomRootStore"
0x18005b13f  mov     r9d, 28000h; dwFlags
0x18005b145  mov     [rsp+180h+pvPara], rax; pvPara
0x18005b14a  lea     edx, [r8+1]; dwEncodingType
0x18005b14e  lea     ecx, [rdx+9]; lpszStoreProvider
0x18005b151  call    cs:__imp_CertOpenStore
0x18005b157  mov     rdx, rax
0x18005b15a  lea     rcx, [rsp+180h+var_118]
0x18005b15f  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CertCloseStoreNoParam@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x18005b164  mov     rbx, [rsp+180h+var_118]
0x18005b169  test    rbx, rbx
0x18005b16c  jz      short loc_18005B1BD
0x18005b16e  xor     edx, edx; Val
0x18005b170  lea     rcx, [rbp+80h+pConfig]; void *
0x18005b174  lea     r8d, [rdx+58h]; Size
0x18005b178  call    memset_0
0x18005b17d  lea     rdx, [rsp+180h+phChainEngine]; phChainEngine
0x18005b182  mov     [rbp+80h+pConfig.cbSize], 58h ; 'X'
0x18005b189  lea     rcx, [rbp+80h+pConfig]; pConfig
0x18005b18d  mov     [rbp+80h+pConfig.hExclusiveRoot], rbx
0x18005b191  call    cs:__imp_CertCreateCertificateChainEngine
0x18005b197  test    eax, eax
0x18005b199  jnz     short loc_18005B1DF
0x18005b19b  call    cs:__imp_GetLastError
0x18005b1a1  mov     ebx, eax
0x18005b1a3  mov     rcx, cs:WPP_GLOBAL_Control
0x18005b1aa  cmp     rcx, r12
0x18005b1ad  jz      loc_18005B3AF
0x18005b1b3  mov     edx, 27h ; '''
0x18005b1b8  jmp     loc_18005B3A0
0x18005b1bd  call    cs:__imp_GetLastError
0x18005b1c3  mov     ebx, eax
0x18005b1c5  mov     rcx, cs:WPP_GLOBAL_Control
0x18005b1cc  cmp     rcx, r12
0x18005b1cf  jz      loc_18005B3AF
0x18005b1d5  mov     edx, 26h ; '&'
0x18005b1da  jmp     loc_18005B3A0
0x18005b1df  mov     r9, [rsi+20h]; hAdditionalStore
0x18005b1e3  lea     rax, [rsp+180h+pChainContext]
0x18005b1e8  mov     rcx, [rsp+180h+phChainEngine]; hChainEngine
0x18005b1ed  xor     r8d, r8d; pTime
0x18005b1f0  mov     [rsp+180h+ppChainContext], rax; ppChainContext
0x18005b1f5  mov     rdx, rsi; pCertContext
0x18005b1f8  mov     [rsp+180h+pvReserved], r13; pvReserved
0x18005b1fd  lea     rax, [rbp+80h+pChainPara]
0x18005b201  mov     [rsp+180h+dwFlags], edi; dwFlags
0x18005b205  mov     [rsp+180h+pvPara], rax; pChainPara
0x18005b20a  call    cs:__imp_CertGetCertificateChain
0x18005b210  test    eax, eax
0x18005b212  jnz     short loc_18005B246
0x18005b214  call    cs:__imp_GetLastError
0x18005b21a  mov     ebx, eax
0x18005b21c  mov     rcx, cs:WPP_GLOBAL_Control
0x18005b223  cmp     rcx, r12
0x18005b226  jz      short loc_18005B23C
0x18005b228  mov     rcx, [rcx+10h]
0x18005b22c  mov     edx, 28h ; '('
0x18005b231  mov     r9d, eax
0x18005b234  mov     r8, r15
0x18005b237  call    WPP_SF_d
0x18005b23c  mov     [rsp+180h+pChainContext], r13
0x18005b241  jmp     loc_18005B3AF
0x18005b246  lea     rcx, [rsp+180h+var_138]; int *
0x18005b24b  mov     [rsp+180h+pPolicyPara.pvExtraPolicyPara], r13
0x18005b250  mov     ebx, r13d
0x18005b253  mov     [rsp+180h+pPolicyPara.cbSize], 10h
0x18005b25b  mov     [rsp+180h+pPolicyPara.dwFlags], 40000000h
0x18005b263  call    ?GetDisableEndEntityClientCheck@@YAXPEAH@Z; GetDisableEndEntityClientCheck(int *)
0x18005b268  cmp     [rsp+180h+var_138], r13d
0x18005b26d  jz      short loc_18005B275
0x18005b26f  bts     [rsp+180h+pPolicyPara.dwFlags], 1Fh
0x18005b275  mov     rdx, [rsp+180h+pChainContext]; pChainContext
0x18005b27a  lea     r9, [rsp+180h+pPolicyStatus]; pPolicyStatus
0x18005b27f  xor     eax, eax
0x18005b281  lea     r8, [rsp+180h+pPolicyPara]; pPolicyPara
0x18005b286  cmp     cs:?g_eapTlsDisableADChecks@@3HA, r13d; int g_eapTlsDisableADChecks
0x18005b28d  xorps   xmm0, xmm0
0x18005b290  movups  xmmword ptr [rsp+180h+pPolicyStatus.cbSize], xmm0
0x18005b295  mov     [rsp+180h+pPolicyStatus.cbSize], 18h
0x18005b29d  mov     [rbp+80h+pPolicyStatus.pvExtraPolicyStatus], rax
0x18005b2a1  jnz     short loc_18005B303
0x18005b2a3  lea     ecx, [rax+6]; pszPolicyOID
0x18005b2a6  call    cs:__imp_CertVerifyCertificateChainPolicy
0x18005b2ac  test    eax, eax
0x18005b2ae  jnz     short loc_18005B2D2
0x18005b2b0  call    cs:__imp_GetLastError
0x18005b2b6  mov     ebx, eax
0x18005b2b8  mov     rcx, cs:WPP_GLOBAL_Control
0x18005b2bf  cmp     rcx, r12
0x18005b2c2  jz      loc_18005B3AF
0x18005b2c8  mov     edx, 29h ; ')'
0x18005b2cd  jmp     loc_18005B3A0
0x18005b2d2  mov     eax, [rsp+180h+pPolicyStatus.dwError]
0x18005b2d6  test    eax, eax
0x18005b2d8  jz      short loc_18005B2F6
0x18005b2da  mov     ebx, eax
0x18005b2dc  mov     rcx, cs:WPP_GLOBAL_Control
0x18005b2e3  cmp     rcx, r12
0x18005b2e6  jz      loc_18005B3AF
0x18005b2ec  mov     edx, 2Ah ; '*'
0x18005b2f1  jmp     loc_18005B3A0
0x18005b2f6  mov     rax, [rsp+180h+pChainContext]
0x18005b2fb  mov     [r14], rax
0x18005b2fe  jmp     loc_18005B3AF
0x18005b303  mov     edi, 1
0x18005b308  mov     ecx, edi; pszPolicyOID
0x18005b30a  call    cs:__imp_CertVerifyCertificateChainPolicy
0x18005b310  test    eax, eax
0x18005b312  jnz     short loc_18005B331
0x18005b314  call    cs:__imp_GetLastError
0x18005b31a  mov     ebx, eax
0x18005b31c  mov     rcx, cs:WPP_GLOBAL_Control
0x18005b323  cmp     rcx, r12
0x18005b326  jz      loc_18005B3AF
0x18005b32c  lea     edx, [rdi+2Ah]
0x18005b32f  jmp     short loc_18005B3A0
0x18005b331  mov     eax, [rsp+180h+pPolicyStatus.dwError]
0x18005b335  test    eax, eax
0x18005b337  jz      short loc_18005B34E
0x18005b339  mov     ebx, eax
0x18005b33b  mov     rcx, cs:WPP_GLOBAL_Control
0x18005b342  cmp     rcx, r12
0x18005b345  jz      short loc_18005B3AF
0x18005b347  mov     edx, 2Ch ; ','
0x18005b34c  jmp     short loc_18005B3A0
0x18005b34e  mov     rdx, [rsp+180h+pChainContext]; pChainContext
0x18005b353  lea     r9, [rsp+180h+pPolicyStatus]; pPolicyStatus
0x18005b358  lea     r8, [rsp+180h+pPolicyPara]; pPolicyPara
0x18005b35d  mov     rcx, rdi; pszPolicyOID
0x18005b360  call    cs:__imp_CertVerifyCertificateChainPolicy
0x18005b366  test    eax, eax
0x18005b368  jnz     short loc_18005B385
0x18005b36a  call    cs:__imp_GetLastError
0x18005b370  mov     ebx, eax
0x18005b372  mov     rcx, cs:WPP_GLOBAL_Control
0x18005b379  cmp     rcx, r12
0x18005b37c  jz      short loc_18005B3AF
0x18005b37e  mov     edx, 2Dh ; '-'
0x18005b383  jmp     short loc_18005B3A0
0x18005b385  mov     eax, [rsp+180h+pPolicyStatus.dwError]
0x18005b389  test    eax, eax
0x18005b38b  jz      short loc_18005B3BC
0x18005b38d  mov     ebx, eax
0x18005b38f  mov     rcx, cs:WPP_GLOBAL_Control
0x18005b396  cmp     rcx, r12
0x18005b399  jz      short loc_18005B3AF
0x18005b39b  mov     edx, 2Eh ; '.'
0x18005b3a0  mov     rcx, [rcx+10h]
0x18005b3a4  mov     r9d, eax
0x18005b3a7  mov     r8, r15
0x18005b3aa  call    WPP_SF_d
0x18005b3af  test    ebx, ebx
0x18005b3b1  jz      loc_18005B457
0x18005b3b7  jmp     loc_18005B4CC
0x18005b3bc  mov     rax, [rsp+180h+pChainContext]
0x18005b3c1  mov     edi, r13d
0x18005b3c4  mov     rcx, [rax+10h]
0x18005b3c8  mov     r15, [rcx]
0x18005b3cb  cmp     edi, [r15+0Ch]
0x18005b3cf  jnb     loc_18005B4BB
0x18005b3d5  xor     eax, eax
0x18005b3d7  mov     ecx, edi
0x18005b3d9  mov     [rbp+80h+var_40], rax
0x18005b3dd  lea     r9, [rbp+80h+pvData]; pcbData
0x18005b3e1  mov     rax, [r15+10h]
0x18005b3e5  lea     r8, [rbp+80h+pvData+4]; pvData
0x18005b3e9  xorps   xmm0, xmm0
0x18005b3ec  mov     edx, 3; dwPropId
0x18005b3f1  movups  [rbp+80h+pvData], xmm0
0x18005b3f5  mov     dword ptr [rbp+80h+pvData], 14h
0x18005b3fc  mov     rcx, [rax+rcx*8]
0x18005b400  mov     rcx, [rcx+8]; pCertContext
0x18005b404  call    cs:__imp_CertGetCertificateContextProperty
0x18005b40a  test    eax, eax
0x18005b40c  jz      short loc_18005B444
0x18005b40e  mov     r12, cs:?g_eapTlsCACertList@@3PEAU_EAPTLS_HASH@@EA; _EAPTLS_HASH * g_eapTlsCACertList
0x18005b415  mov     esi, r13d
0x18005b418  cmp     esi, cs:?g_eapTlsNumCACerts@@3KA; ulong g_eapTlsNumCACerts
0x18005b41e  jnb     short loc_18005B444
0x18005b420  mov     r8d, dword ptr [rbp+80h+pvData]; Size
0x18005b424  lea     rdx, [r12+4]
0x18005b429  mov     eax, esi
0x18005b42b  lea     rcx, [rax+rax*2]
0x18005b42f  lea     rdx, [rdx+rcx*8]; Buf2
0x18005b433  lea     rcx, [rbp+80h+pvData+4]; Buf1
0x18005b437  call    memcmp_0
0x18005b43c  test    eax, eax
0x18005b43e  jz      short loc_18005B448
0x18005b440  inc     esi
0x18005b442  jmp     short loc_18005B418
0x18005b444  inc     edi
0x18005b446  jmp     short loc_18005B3CB
0x18005b448  mov     rax, [rsp+180h+pChainContext]
0x18005b44d  mov     [r14], rax
0x18005b450  lea     r12, WPP_GLOBAL_Control
0x18005b457  mov     rcx, [rsp+180h+phChainEngine]; hChainEngine
0x18005b45c  test    rcx, rcx
0x18005b45f  jz      short loc_18005B467
0x18005b461  call    cs:__imp_CertFreeCertificateChainEngine
0x18005b467  mov     rcx, cs:WPP_GLOBAL_Control
0x18005b46e  cmp     rcx, r12
0x18005b471  jz      short loc_18005B488
0x18005b473  mov     rcx, [rcx+10h]
0x18005b477  lea     r8, WPP_88923bd842923c348eb3d02ba21152e8_Traceguids
0x18005b47e  mov     edx, 2Fh ; '/'
0x18005b483  call    WPP_SF_
0x18005b488  lea     rcx, [rsp+180h+var_118]
0x18005b48d  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CertCloseStoreNoParam@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18005b492  mov     eax, ebx
0x18005b494  mov     rcx, [rbp+80h+var_38]
0x18005b498  xor     rcx, rsp; StackCookie
0x18005b49b  call    __security_check_cookie
0x18005b4a0  mov     rbx, [rsp+180h+arg_10]
0x18005b4a8  add     rsp, 150h
0x18005b4af  pop     r15
0x18005b4b1  pop     r14
0x18005b4b3  pop     r13
0x18005b4b5  pop     r12
0x18005b4b7  pop     rdi
0x18005b4b8  pop     rsi
0x18005b4b9  pop     rbp
0x18005b4ba  retn
0x18005b4bb  cmp     [r14], r13
0x18005b4be  jnz     short loc_18005B450
  ... truncated ...
```
