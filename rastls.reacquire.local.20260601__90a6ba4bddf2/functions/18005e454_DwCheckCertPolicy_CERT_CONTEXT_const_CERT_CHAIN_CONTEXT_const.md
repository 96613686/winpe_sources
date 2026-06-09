# DwCheckCertPolicy(_CERT_CONTEXT const *,_CERT_CHAIN_CONTEXT const * *)

- ea: `0x18005e454`
- end: `0x18005e991`
- name: `?DwCheckCertPolicy@@YAKPEBU_CERT_CONTEXT@@PEAPEBU_CERT_CHAIN_CONTEXT@@@Z`
- size: `1341`
- prototype: `unsigned int __fastcall(PCCERT_CONTEXT pCertContext, const struct _CERT_CHAIN_CONTEXT **)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config`

## callers

- `0x18004eaf8`

## callees

- `0x180005010`
- `0x180007d00`
- `0x180038270`
- `0x180038e40`
- `0x180038e64`
- `0x180039540`
- `0x18004dcd0`
- `0x18005c064`
- `0x18005e454`
- `0x18005ec10`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005e5f5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005e61d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005e680`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005e728`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005e798`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005e7fa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005e5f5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005e61d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005e680`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005e728`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005e798`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005e7fa`
- `CRYPT32!CertGetCertificateContextProperty` at `0x18005e89a`
- `CRYPT32!CertGetCertificateContextProperty` at `0x18005e89a`
- `CRYPT32!CertOpenStore` at `0x18005e59f`
- `CRYPT32!CertOpenStore` at `0x18005e59f`
- `CRYPT32!CertFreeCertificateChainEngine` at `0x18005e900`
- `CRYPT32!CertFreeCertificateChainEngine` at `0x18005e900`
- `CRYPT32!CertGetCertificateChain` at `0x18005e670`
- `CRYPT32!CertGetCertificateChain` at `0x18005e670`
- `CRYPT32!CertCreateCertificateChainEngine` at `0x18005e5e5`
- `CRYPT32!CertCreateCertificateChainEngine` at `0x18005e5e5`
- `CRYPT32!CertFreeCertificateChain` at `0x18005e980`
- `CRYPT32!CertFreeCertificateChain` at `0x18005e980`
- `CRYPT32!CertVerifyCertificateChainPolicy` at `0x18005e718`
- `CRYPT32!CertVerifyCertificateChainPolicy` at `0x18005e788`
- `CRYPT32!CertVerifyCertificateChainPolicy` at `0x18005e7ea`
- `CRYPT32!CertVerifyCertificateChainPolicy` at `0x18005e718`
- `CRYPT32!CertVerifyCertificateChainPolicy` at `0x18005e788`
- `CRYPT32!CertVerifyCertificateChainPolicy` at `0x18005e7ea`
- `ext-ms-win-rastlsext-eap-l1-1-0!RasTlsExt_GetConfigCacheOnlyCertValidation` at `0x18005e53e`
- `ext-ms-win-rastlsext-eap-l1-1-0!RasTlsExt_GetConfigCacheOnlyCertValidation` at `0x18005e53e`

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
0x18005e454  mov     [rsp-8+arg_10], rbx
0x18005e459  push    rbp
0x18005e45a  push    rsi
0x18005e45b  push    rdi
0x18005e45c  push    r12
0x18005e45e  push    r13
0x18005e460  push    r14
0x18005e462  push    r15
0x18005e464  lea     rbp, [rsp-50h]
0x18005e469  sub     rsp, 150h
0x18005e470  mov     rax, cs:__security_cookie
0x18005e477  xor     rax, rsp
0x18005e47a  mov     [rbp+80h+var_38], rax
0x18005e47e  xor     r13d, r13d
0x18005e481  lea     rax, Buf1; "1.3.6.1.5.5.7.3.2"
0x18005e488  xorps   xmm0, xmm0
0x18005e48b  mov     [rbp+80h+var_D8], rax
0x18005e48f  mov     r14, rdx
0x18005e492  mov     [rsp+180h+pChainContext], r13
0x18005e497  mov     rsi, rcx
0x18005e49a  mov     [rsp+180h+var_138], r13d
0x18005e49f  xorps   xmm1, xmm1
0x18005e4a2  lea     r8d, [r13+58h]; Size
0x18005e4a6  xor     eax, eax
0x18005e4a8  lea     rcx, [rbp+80h+pConfig]; void *
0x18005e4ac  xor     edx, edx; Val
0x18005e4ae  mov     [rbp+80h+pPolicyStatus.pvExtraPolicyStatus], rax
0x18005e4b2  movups  xmmword ptr [rbp+80h+pChainPara.cbSize], xmm0
0x18005e4b6  movups  xmmword ptr [rbp+80h+pChainPara.RequestedUsage.Usage.cUsageIdentifier], xmm0
0x18005e4ba  movups  xmmword ptr [rsp+180h+pPolicyPara.cbSize], xmm0
0x18005e4bf  movups  xmmword ptr [rsp+180h+pPolicyStatus.cbSize], xmm1
0x18005e4c4  call    memset_0
0x18005e4c9  mov     [rsp+180h+phChainEngine], r13
0x18005e4ce  mov     [rsp+180h+var_118], r13
0x18005e4d3  mov     rcx, cs:WPP_GLOBAL_Control
0x18005e4da  lea     r12, WPP_GLOBAL_Control
0x18005e4e1  lea     r15, WPP_88923bd842923c348eb3d02ba21152e8_Traceguids
0x18005e4e8  cmp     rcx, r12
0x18005e4eb  jz      short loc_18005E4FD
0x18005e4ed  mov     rcx, [rcx+10h]
0x18005e4f1  lea     edx, [r13+24h]
0x18005e4f5  mov     r8, r15
0x18005e4f8  call    WPP_SF_
0x18005e4fd  xorps   xmm1, xmm1
0x18005e500  mov     [r14], r13
0x18005e503  movups  [rbp+80h+var_D0], xmm1
0x18005e507  mov     eax, dword ptr [rbp+80h+var_D0+4]
0x18005e50a  mov     dword ptr [rbp+80h+pChainPara.RequestedUsage+4], eax
0x18005e50d  xorps   xmm0, xmm0
0x18005e510  movups  [rbp+80h+pvData], xmm0
0x18005e514  mov     eax, dword ptr [rbp+80h+pvData+4]
0x18005e517  mov     dword ptr [rbp+80h+pChainPara.RequestedUsage.Usage+4], eax
0x18005e51a  lea     rax, [rbp+80h+var_D8]
0x18005e51e  mov     [rbp+80h+pChainPara.RequestedUsage.Usage.rgpszUsageIdentifier], rax
0x18005e522  mov     qword ptr [rbp+80h+pChainPara.cbSize], 20h ; ' '
0x18005e52a  mov     [rbp+80h+pChainPara.RequestedUsage.dwType], r13d
0x18005e52e  mov     [rbp+80h+pChainPara.RequestedUsage.Usage.cUsageIdentifier], 1
0x18005e535  call    IsRasTlsExt_GetPinUserBlobPresent
0x18005e53a  test    al, al
0x18005e53c  jz      short loc_18005E556
0x18005e53e  call    cs:__imp_RasTlsExt_GetConfigCacheOnlyCertValidation
0x18005e545  nop     dword ptr [rax+rax+00h]
0x18005e54a  neg     eax
0x18005e54c  sbb     edi, edi
0x18005e54e  and     edi, 80000004h
0x18005e554  jmp     short loc_18005E576
0x18005e556  mov     rcx, cs:WPP_GLOBAL_Control
0x18005e55d  mov     edi, r13d
0x18005e560  cmp     rcx, r12
0x18005e563  jz      short loc_18005E576
0x18005e565  mov     rcx, [rcx+10h]
0x18005e569  mov     edx, 25h ; '%'
0x18005e56e  mov     r8, r15
0x18005e571  call    WPP_SF_
0x18005e576  cmp     cs:?g_useCustomRootStore@@3_NA, r13b; bool g_useCustomRootStore
0x18005e57d  jz      loc_18005E645
0x18005e583  xor     r8d, r8d; hCryptProv
0x18005e586  lea     rax, aEapservercusto; "EAPServerCustomRootStore"
0x18005e58d  mov     r9d, 28000h; dwFlags
0x18005e593  mov     [rsp+180h+pvPara], rax; pvPara
0x18005e598  lea     edx, [r8+1]; dwEncodingType
0x18005e59c  lea     ecx, [rdx+9]; lpszStoreProvider
0x18005e59f  call    cs:__imp_CertOpenStore
0x18005e5a6  nop     dword ptr [rax+rax+00h]
0x18005e5ab  mov     rdx, rax
0x18005e5ae  lea     rcx, [rsp+180h+var_118]
0x18005e5b3  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CertCloseStoreNoParam@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x18005e5b8  mov     rbx, [rsp+180h+var_118]
0x18005e5bd  test    rbx, rbx
0x18005e5c0  jz      short loc_18005E61D
0x18005e5c2  xor     edx, edx; Val
0x18005e5c4  lea     rcx, [rbp+80h+pConfig]; void *
0x18005e5c8  lea     r8d, [rdx+58h]; Size
0x18005e5cc  call    memset_0
0x18005e5d1  lea     rdx, [rsp+180h+phChainEngine]; phChainEngine
0x18005e5d6  mov     [rbp+80h+pConfig.cbSize], 58h ; 'X'
0x18005e5dd  lea     rcx, [rbp+80h+pConfig]; pConfig
0x18005e5e1  mov     [rbp+80h+pConfig.hExclusiveRoot], rbx
0x18005e5e5  call    cs:__imp_CertCreateCertificateChainEngine
0x18005e5ec  nop     dword ptr [rax+rax+00h]
0x18005e5f1  test    eax, eax
0x18005e5f3  jnz     short loc_18005E645
0x18005e5f5  call    cs:__imp_GetLastError
0x18005e5fc  nop     dword ptr [rax+rax+00h]
0x18005e601  mov     ebx, eax
0x18005e603  mov     rcx, cs:WPP_GLOBAL_Control
0x18005e60a  cmp     rcx, r12
0x18005e60d  jz      loc_18005E845
0x18005e613  mov     edx, 27h ; '''
0x18005e618  jmp     loc_18005E836
0x18005e61d  call    cs:__imp_GetLastError
0x18005e624  nop     dword ptr [rax+rax+00h]
0x18005e629  mov     ebx, eax
0x18005e62b  mov     rcx, cs:WPP_GLOBAL_Control
0x18005e632  cmp     rcx, r12
0x18005e635  jz      loc_18005E845
0x18005e63b  mov     edx, 26h ; '&'
0x18005e640  jmp     loc_18005E836
0x18005e645  mov     r9, [rsi+20h]; hAdditionalStore
0x18005e649  lea     rax, [rsp+180h+pChainContext]
0x18005e64e  mov     rcx, [rsp+180h+phChainEngine]; hChainEngine
0x18005e653  xor     r8d, r8d; pTime
0x18005e656  mov     [rsp+180h+ppChainContext], rax; ppChainContext
0x18005e65b  mov     rdx, rsi; pCertContext
0x18005e65e  mov     [rsp+180h+pvReserved], r13; pvReserved
0x18005e663  lea     rax, [rbp+80h+pChainPara]
0x18005e667  mov     [rsp+180h+dwFlags], edi; dwFlags
0x18005e66b  mov     [rsp+180h+pvPara], rax; pChainPara
0x18005e670  call    cs:__imp_CertGetCertificateChain
0x18005e677  nop     dword ptr [rax+rax+00h]
0x18005e67c  test    eax, eax
0x18005e67e  jnz     short loc_18005E6B8
0x18005e680  call    cs:__imp_GetLastError
0x18005e687  nop     dword ptr [rax+rax+00h]
0x18005e68c  mov     ebx, eax
0x18005e68e  mov     rcx, cs:WPP_GLOBAL_Control
0x18005e695  cmp     rcx, r12
0x18005e698  jz      short loc_18005E6AE
0x18005e69a  mov     rcx, [rcx+10h]
0x18005e69e  mov     edx, 28h ; '('
0x18005e6a3  mov     r9d, eax
0x18005e6a6  mov     r8, r15
0x18005e6a9  call    WPP_SF_d
0x18005e6ae  mov     [rsp+180h+pChainContext], r13
0x18005e6b3  jmp     loc_18005E845
0x18005e6b8  lea     rcx, [rsp+180h+var_138]; int *
0x18005e6bd  mov     [rsp+180h+pPolicyPara.pvExtraPolicyPara], r13
0x18005e6c2  mov     ebx, r13d
0x18005e6c5  mov     [rsp+180h+pPolicyPara.cbSize], 10h
0x18005e6cd  mov     [rsp+180h+pPolicyPara.dwFlags], 40000000h
0x18005e6d5  call    ?GetDisableEndEntityClientCheck@@YAXPEAH@Z; GetDisableEndEntityClientCheck(int *)
0x18005e6da  cmp     [rsp+180h+var_138], r13d
0x18005e6df  jz      short loc_18005E6E7
0x18005e6e1  bts     [rsp+180h+pPolicyPara.dwFlags], 1Fh
0x18005e6e7  mov     rdx, [rsp+180h+pChainContext]; pChainContext
0x18005e6ec  lea     r9, [rsp+180h+pPolicyStatus]; pPolicyStatus
0x18005e6f1  xor     eax, eax
0x18005e6f3  lea     r8, [rsp+180h+pPolicyPara]; pPolicyPara
0x18005e6f8  cmp     cs:?g_eapTlsDisableADChecks@@3HA, r13d; int g_eapTlsDisableADChecks
0x18005e6ff  xorps   xmm0, xmm0
0x18005e702  movups  xmmword ptr [rsp+180h+pPolicyStatus.cbSize], xmm0
0x18005e707  mov     [rsp+180h+pPolicyStatus.cbSize], 18h
0x18005e70f  mov     [rbp+80h+pPolicyStatus.pvExtraPolicyStatus], rax
0x18005e713  jnz     short loc_18005E781
0x18005e715  lea     ecx, [rax+6]; pszPolicyOID
0x18005e718  call    cs:__imp_CertVerifyCertificateChainPolicy
0x18005e71f  nop     dword ptr [rax+rax+00h]
0x18005e724  test    eax, eax
0x18005e726  jnz     short loc_18005E750
0x18005e728  call    cs:__imp_GetLastError
0x18005e72f  nop     dword ptr [rax+rax+00h]
0x18005e734  mov     ebx, eax
0x18005e736  mov     rcx, cs:WPP_GLOBAL_Control
0x18005e73d  cmp     rcx, r12
0x18005e740  jz      loc_18005E845
0x18005e746  mov     edx, 29h ; ')'
0x18005e74b  jmp     loc_18005E836
0x18005e750  mov     eax, [rsp+180h+pPolicyStatus.dwError]
0x18005e754  test    eax, eax
0x18005e756  jz      short loc_18005E774
0x18005e758  mov     ebx, eax
0x18005e75a  mov     rcx, cs:WPP_GLOBAL_Control
0x18005e761  cmp     rcx, r12
0x18005e764  jz      loc_18005E845
0x18005e76a  mov     edx, 2Ah ; '*'
0x18005e76f  jmp     loc_18005E836
0x18005e774  mov     rax, [rsp+180h+pChainContext]
0x18005e779  mov     [r14], rax
0x18005e77c  jmp     loc_18005E845
0x18005e781  mov     edi, 1
0x18005e786  mov     ecx, edi; pszPolicyOID
0x18005e788  call    cs:__imp_CertVerifyCertificateChainPolicy
0x18005e78f  nop     dword ptr [rax+rax+00h]
0x18005e794  test    eax, eax
0x18005e796  jnz     short loc_18005E7BB
0x18005e798  call    cs:__imp_GetLastError
0x18005e79f  nop     dword ptr [rax+rax+00h]
0x18005e7a4  mov     ebx, eax
0x18005e7a6  mov     rcx, cs:WPP_GLOBAL_Control
0x18005e7ad  cmp     rcx, r12
0x18005e7b0  jz      loc_18005E845
0x18005e7b6  lea     edx, [rdi+2Ah]
0x18005e7b9  jmp     short loc_18005E836
0x18005e7bb  mov     eax, [rsp+180h+pPolicyStatus.dwError]
0x18005e7bf  test    eax, eax
0x18005e7c1  jz      short loc_18005E7D8
0x18005e7c3  mov     ebx, eax
0x18005e7c5  mov     rcx, cs:WPP_GLOBAL_Control
0x18005e7cc  cmp     rcx, r12
0x18005e7cf  jz      short loc_18005E845
0x18005e7d1  mov     edx, 2Ch ; ','
0x18005e7d6  jmp     short loc_18005E836
0x18005e7d8  mov     rdx, [rsp+180h+pChainContext]; pChainContext
0x18005e7dd  lea     r9, [rsp+180h+pPolicyStatus]; pPolicyStatus
0x18005e7e2  lea     r8, [rsp+180h+pPolicyPara]; pPolicyPara
0x18005e7e7  mov     rcx, rdi; pszPolicyOID
0x18005e7ea  call    cs:__imp_CertVerifyCertificateChainPolicy
0x18005e7f1  nop     dword ptr [rax+rax+00h]
0x18005e7f6  test    eax, eax
0x18005e7f8  jnz     short loc_18005E81B
0x18005e7fa  call    cs:__imp_GetLastError
0x18005e801  nop     dword ptr [rax+rax+00h]
0x18005e806  mov     ebx, eax
0x18005e808  mov     rcx, cs:WPP_GLOBAL_Control
0x18005e80f  cmp     rcx, r12
0x18005e812  jz      short loc_18005E845
0x18005e814  mov     edx, 2Dh ; '-'
0x18005e819  jmp     short loc_18005E836
0x18005e81b  mov     eax, [rsp+180h+pPolicyStatus.dwError]
0x18005e81f  test    eax, eax
0x18005e821  jz      short loc_18005E852
0x18005e823  mov     ebx, eax
0x18005e825  mov     rcx, cs:WPP_GLOBAL_Control
0x18005e82c  cmp     rcx, r12
0x18005e82f  jz      short loc_18005E845
0x18005e831  mov     edx, 2Eh ; '.'
0x18005e836  mov     rcx, [rcx+10h]
0x18005e83a  mov     r9d, eax
0x18005e83d  mov     r8, r15
0x18005e840  call    WPP_SF_d
0x18005e845  test    ebx, ebx
0x18005e847  jz      loc_18005E8F6
0x18005e84d  jmp     loc_18005E972
0x18005e852  mov     rax, [rsp+180h+pChainContext]
0x18005e857  mov     edi, r13d
0x18005e85a  mov     rcx, [rax+10h]
0x18005e85e  mov     r15, [rcx]
0x18005e861  cmp     edi, [r15+0Ch]
0x18005e865  jnb     loc_18005E961
0x18005e86b  xor     eax, eax
0x18005e86d  mov     ecx, edi
0x18005e86f  mov     [rbp+80h+var_40], rax
0x18005e873  lea     r9, [rbp+80h+pvData]; pcbData
0x18005e877  mov     rax, [r15+10h]
0x18005e87b  lea     r8, [rbp+80h+pvData+4]; pvData
0x18005e87f  xorps   xmm0, xmm0
0x18005e882  mov     edx, 3; dwPropId
0x18005e887  movups  [rbp+80h+pvData], xmm0
0x18005e88b  mov     dword ptr [rbp+80h+pvData], 14h
0x18005e892  mov     rcx, [rax+rcx*8]
0x18005e896  mov     rcx, [rcx+8]; pCertContext
0x18005e89a  call    cs:__imp_CertGetCertificateContextProperty
0x18005e8a1  nop     dword ptr [rax+rax+00h]
0x18005e8a6  test    eax, eax
0x18005e8a8  jz      short loc_18005E8E0
0x18005e8aa  mov     r12, cs:?g_eapTlsCACertList@@3PEAU_EAPTLS_HASH@@EA; _EAPTLS_HASH * g_eapTlsCACertList
0x18005e8b1  mov     esi, r13d
0x18005e8b4  cmp     esi, cs:?g_eapTlsNumCACerts@@3KA; ulong g_eapTlsNumCACerts
0x18005e8ba  jnb     short loc_18005E8E0
0x18005e8bc  mov     r8d, dword ptr [rbp+80h+pvData]; Size
0x18005e8c0  lea     rdx, [r12+4]
0x18005e8c5  mov     eax, esi
0x18005e8c7  lea     rcx, [rax+rax*2]
0x18005e8cb  lea     rdx, [rdx+rcx*8]; Buf2
0x18005e8cf  lea     rcx, [rbp+80h+pvData+4]; Buf1
0x18005e8d3  call    memcmp_0
0x18005e8d8  test    eax, eax
0x18005e8da  jz      short loc_18005E8E7
0x18005e8dc  inc     esi
0x18005e8de  jmp     short loc_18005E8B4
0x18005e8e0  inc     edi
0x18005e8e2  jmp     loc_18005E861
0x18005e8e7  mov     rax, [rsp+180h+pChainContext]
0x18005e8ec  mov     [r14], rax
0x18005e8ef  lea     r12, WPP_GLOBAL_Control
0x18005e8f6  mov     rcx, [rsp+180h+phChainEngine]; hChainEngine
0x18005e8fb  test    rcx, rcx
0x18005e8fe  jz      short loc_18005E90C
0x18005e900  call    cs:__imp_CertFreeCertificateChainEngine
0x18005e907  nop     dword ptr [rax+rax+00h]
0x18005e90c  mov     rcx, cs:WPP_GLOBAL_Control
0x18005e913  cmp     rcx, r12
0x18005e916  jz      short loc_18005E92D
0x18005e918  mov     rcx, [rcx+10h]
0x18005e91c  lea     r8, WPP_88923bd842923c348eb3d02ba21152e8_Traceguids
0x18005e923  mov     edx, 2Fh ; '/'
0x18005e928  call    WPP_SF_
0x18005e92d  lea     rcx, [rsp+180h+var_118]
0x18005e932  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CertCloseStoreNoParam@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18005e937  mov     eax, ebx
  ... truncated ...
```
