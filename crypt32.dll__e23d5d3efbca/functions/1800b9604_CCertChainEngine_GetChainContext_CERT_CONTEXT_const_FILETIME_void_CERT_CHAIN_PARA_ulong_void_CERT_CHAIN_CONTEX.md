# CCertChainEngine::GetChainContext(_CERT_CONTEXT const *,_FILETIME *,void *,_CERT_CHAIN_PARA *,ulong,void *,_CERT_CHAIN_CONTEXT const * *)

- ea: `0x1800b9604`
- end: `0x1800ba24c`
- name: `?GetChainContext@CCertChainEngine@@QEAAHPEBU_CERT_CONTEXT@@PEAU_FILETIME@@PEAXPEAU_CERT_CHAIN_PARA@@K2PEAPEBU_CERT_CHAIN_CONTEXT@@@Z`
- size: `3144`
- prototype: `__int64 __fastcall(CCertChainEngine *__hidden this, const struct _CERT_CONTEXT *, struct _FILETIME *, void *, struct _CERT_CHAIN_PARA *, unsigned int, void *, const struct _CERT_CHAIN_CONTEXT **)`
- caller_count: `1`
- callee_count: `35`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x18001aec0`

## callees

- `0x180001008`
- `0x180007c30`
- `0x180010610`
- `0x180014030`
- `0x180014790`
- `0x180018750`
- `0x18001973c`
- `0x18001a0d0`
- `0x18001b57c`
- `0x180028d60`
- `0x1800466a0`
- `0x180047f10`
- `0x18004d0d0`
- `0x18004eff0`
- `0x180054b58`
- `0x180056410`
- `0x18005652c`
- `0x1800592e0`
- `0x180060108`
- `0x180062198`
- `0x18006dc80`
- `0x18008d78c`
- `0x18008dfa0`
- `0x180099740`
- `0x1800b13bc`
- `0x1800b56d0`
- `0x1800b6b38`
- `0x1800b8060`
- `0x1800b8f48`
- `0x1800b92ec`
- `0x1800b9604`
- `0x1800bcec0`
- `0x1800bec20`
- `0x1800bf63c`
- `0x1800f2fc0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b9a60`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ba1de`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b9a60`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ba1de`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800ba1b1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800ba212`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800ba1b1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800ba212`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800b98e2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800ba204`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800b98e2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800ba204`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800b98b6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800ba1f2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800b98b6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800ba1f2`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x1800b9db4`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x1800b9e3b`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x1800ba018`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x1800b9db4`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x1800b9e3b`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x1800ba018`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800b9df2`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800b9e1c`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800b9df2`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800b9e1c`

## string_xrefs

- `0x1800b9e01`: `dllhost.exe`

## pseudocode

```c
__int64 __fastcall CCertChainEngine::GetChainContext(
        CCertChainEngine *this,
        const struct _CERT_CONTEXT *a2,
        struct _FILETIME *a3,
        void *a4,
        struct _CERT_CHAIN_PARA *a5,
        unsigned int a6,
        void *a7,
        const struct _CERT_CHAIN_CONTEXT **a8)
{
  const struct _CERT_CHAIN_CONTEXT **v8; // r13
  int v12; // eax
  _QWORD *v13; // rdi
  struct _CERT_CHAIN_CONTEXT *v14; // rbx
  unsigned int v15; // esi
  PCERT_SIMPLE_CHAIN v16; // r13
  PCERT_CHAIN_ELEMENT *rgpElement; // r14
  unsigned int cElement; // r13d
  int IsOnline; // ebx
  __int64 v20; // rax
  const struct _CERT_CONTEXT *pCertContext; // r9
  unsigned int v22; // r12d
  struct _CERT_CONTEXT *v23; // rax
  const struct _CERT_CONTEXT *pbCertEncoded; // r13
  PCERT_EXTENSION Extension; // rax
  BYTE *pbData; // rcx
  void *NewerIssuerUrlStore; // rax
  void *v28; // r12
  HCERTSTORE v29; // rbx
  HCERTSTORE v30; // rax
  HCERTSTORE v31; // r14
  __int64 v32; // r13
  PCERT_SIMPLE_CHAIN *rgpChain; // rax
  unsigned int v34; // r14d
  struct _CERT_CONTEXT *v35; // rdx
  unsigned int v36; // r12d
  unsigned int v37; // edi
  const CERT_CONTEXT *v38; // rbx
  PCCERT_CHAIN_CONTEXT *v39; // rax
  const struct _CERT_CONTEXT *v40; // rdx
  unsigned int IsThirdPartyChain; // eax
  bool v42; // zf
  int v43; // r12d
  unsigned __int16 *v44; // r14
  int v45; // edx
  __int64 v46; // rax
  PCERT_SIMPLE_CHAIN v47; // rax
  __int64 v48; // rcx
  __int64 v49; // rbx
  const CERT_CONTEXT *v50; // rbx
  unsigned __int16 *v51; // rbx
  const CERT_CONTEXT *v52; // rbx
  unsigned __int16 *v53; // r13
  const wchar_t *v54; // rax
  const WCHAR *v55; // rbx
  DWORD dwErrorStatus; // ebx
  __int64 v57; // r9
  WCHAR *v58; // rbx
  unsigned __int16 *v59; // rax
  __int64 v60; // rcx
  int v61; // r8d
  int v62; // r9d
  unsigned int v63; // edx
  const WCHAR *v64; // rax
  WCHAR *v65; // rax
  const WCHAR *v66; // rax
  WCHAR *v67; // rax
  DWORD v68; // ecx
  DWORD LastError; // r14d
  __int64 result; // rax
  unsigned int v71; // [rsp+A0h] [rbp-80h] BYREF
  unsigned int cbCertEncoded; // [rsp+A4h] [rbp-7Ch] BYREF
  struct _CERT_CHAIN_CONTEXT *v73; // [rsp+A8h] [rbp-78h] BYREF
  int v74; // [rsp+B0h] [rbp-70h] BYREF
  HCERTSTORE hSiblingStore; // [rsp+B8h] [rbp-68h] BYREF
  struct _CERT_CONTEXT *v76; // [rsp+C0h] [rbp-60h] BYREF
  unsigned __int16 *v77; // [rsp+C8h] [rbp-58h] BYREF
  HLOCAL hMem; // [rsp+D0h] [rbp-50h] BYREF
  unsigned int v79; // [rsp+D8h] [rbp-48h] BYREF
  HLOCAL v80; // [rsp+E0h] [rbp-40h] BYREF
  unsigned int v81; // [rsp+E8h] [rbp-38h] BYREF
  DWORD dwErrCode[2]; // [rsp+F0h] [rbp-30h]
  DWORD v83; // [rsp+F8h] [rbp-28h]
  __int64 v84; // [rsp+100h] [rbp-20h] BYREF
  const WCHAR *v85; // [rsp+108h] [rbp-18h] BYREF
  WCHAR *v86; // [rsp+110h] [rbp-10h] BYREF
  unsigned __int16 *v87; // [rsp+118h] [rbp-8h] BYREF
  const WCHAR *v88; // [rsp+120h] [rbp+0h] BYREF
  WCHAR *v89; // [rsp+128h] [rbp+8h] BYREF
  unsigned __int16 *v90; // [rsp+130h] [rbp+10h] BYREF
  unsigned __int16 *v91; // [rsp+138h] [rbp+18h] BYREF
  HLOCAL v92; // [rsp+140h] [rbp+20h] BYREF
  const struct _CERT_CHAIN_CONTEXT **v93; // [rsp+148h] [rbp+28h]
  unsigned __int16 *v94[18]; // [rsp+150h] [rbp+30h] BYREF
  unsigned __int16 v95[8]; // [rsp+1E0h] [rbp+C0h] BYREF
  __int128 v96; // [rsp+1F0h] [rbp+D0h]
  __int64 v97; // [rsp+200h] [rbp+E0h]
  unsigned __int16 v98[8]; // [rsp+208h] [rbp+E8h] BYREF
  __int128 v99; // [rsp+218h] [rbp+F8h]
  __int64 v100; // [rsp+228h] [rbp+108h]
  unsigned __int16 v101[8]; // [rsp+230h] [rbp+110h] BYREF
  __int128 v102; // [rsp+240h] [rbp+120h]
  __int64 v103; // [rsp+250h] [rbp+130h]
  unsigned __int16 v104[48]; // [rsp+260h] [rbp+140h] BYREF
  unsigned __int16 v105[48]; // [rsp+2C0h] [rbp+1A0h] BYREF
  unsigned __int16 v106[48]; // [rsp+320h] [rbp+200h] BYREF
  unsigned __int16 v107[48]; // [rsp+380h] [rbp+260h] BYREF
  WCHAR v108[64]; // [rsp+3E0h] [rbp+2C0h] BYREF
  WCHAR v109[64]; // [rsp+460h] [rbp+340h] BYREF
  WCHAR pszNameString[64]; // [rsp+4E0h] [rbp+3C0h] BYREF
  WCHAR v111[64]; // [rsp+560h] [rbp+440h] BYREF

  v8 = a8;
  *(_QWORD *)dwErrCode = a2;
  hSiblingStore = a4;
  v93 = a8;
  hMem = 0;
  v73 = 0;
  v12 = CallContextCreateCallObject(this, a3, a5, a2, a6, (struct CChainCallContext **)&hMem);
  v13 = hMem;
  if ( !v12
    || (CCertChainEngine::GetTimeValidDisallowedCertAutoUpdateCtl(this, (struct CChainCallContext *)hMem, a2),
        !CCertChainEngine::CreateChainContextFromPathGraph(
           this,
           (struct CChainCallContext *)v13,
           a2,
           a4,
           (const struct _CERT_CHAIN_CONTEXT **)&v73)) )
  {
    LastError = GetLastError();
    v15 = 0;
    goto LABEL_105;
  }
  v14 = v73;
  v15 = 1;
  v83 = 0;
  if ( (v73->TrustStatus.dwErrorStatus & 0x25) != 0 )
  {
    v16 = *v73->rgpChain;
    rgpElement = v16->rgpElement;
    if ( ((*rgpElement)->TrustStatus.dwErrorStatus & 0x25) == 0 )
    {
      cElement = v16->cElement;
      v74 = 0;
      IsOnline = CChainCallContext::IsOnline((CChainCallContext *)v13, &v74);
      if ( v74 )
        CertDiagAIAUrlRetrievalNotConnected(a2);
      if ( !IsOnline )
        goto LABEL_35;
      v14 = v73;
      if ( (v73->TrustStatus.dwErrorStatus & 0x25) == 0x20 )
      {
        if ( cElement < 2 )
          goto LABEL_36;
        if ( !(unsigned int)CCertChainEngine::IsPotentialKeyRolloverRoot(this, rgpElement[cElement - 1]->pCertContext) )
          goto LABEL_35;
        v20 = cElement - 2;
        pCertContext = rgpElement[cElement - 1]->pCertContext;
      }
      else
      {
        v22 = 1;
        if ( cElement <= 1 )
          goto LABEL_36;
        while ( 1 )
        {
          v23 = (struct _CERT_CONTEXT *)rgpElement[v22];
          v76 = v23;
          cbCertEncoded = v23->cbCertEncoded;
          if ( (cbCertEncoded & 0x25) != 0 )
            break;
          if ( ++v22 >= cElement )
            goto LABEL_36;
        }
        pbCertEncoded = (const struct _CERT_CONTEXT *)v23->pbCertEncoded;
        Extension = CertFindExtension(
                      "1.3.6.1.4.1.311.20.2",
                      pbCertEncoded->pCertInfo->cExtension,
                      pbCertEncoded->pCertInfo->rgExtension);
        if ( Extension )
        {
          if ( Extension->Value.cbData == 16 )
          {
            pbData = Extension->Value.pbData;
            if ( *(_QWORD *)pbData == 0x6F00720043000E1ELL && *((_QWORD *)pbData + 1) == 0x4100430073007300LL )
              goto LABEL_36;
          }
        }
        if ( (cbCertEncoded & 4) != 0 && ChainGetElementCrlReasonCode((struct _CERT_CHAIN_ELEMENT *)v76) - 1 <= 1 )
          goto LABEL_35;
        v20 = v22 - 1;
        pCertContext = pbCertEncoded;
      }
      NewerIssuerUrlStore = CCertChainEngine::GetNewerIssuerUrlStore(
                              this,
                              (struct CChainCallContext *)v13,
                              rgpElement[v20]->pCertContext,
                              pCertContext);
      v28 = NewerIssuerUrlStore;
      if ( !NewerIssuerUrlStore )
      {
LABEL_35:
        v14 = v73;
        goto LABEL_36;
      }
      v29 = hSiblingStore;
      if ( hSiblingStore )
      {
        v30 = CertOpenStore((LPCSTR)0xB, 0x10001u, 0, 4u, 0);
        v31 = v30;
        if ( !v30 )
          goto LABEL_34;
        if ( CertAddStoreToCollection(v30, v28, 0, 0) && CertAddStoreToCollection(v31, v29, 0, 0) )
          goto LABEL_31;
        CertCloseStore(v31, 0);
        v31 = 0;
      }
      else
      {
        v31 = CertDuplicateStore(NewerIssuerUrlStore);
      }
      if ( v31 )
      {
LABEL_31:
        hSiblingStore = 0;
        EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
        I_CryptFlushLruCache(*v13, 0, v13);
        *((_DWORD *)v13 + 40) = 0;
        *(_QWORD *)((char *)v13 + 172) = 0;
        LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
        if ( CCertChainEngine::CreateChainContextFromPathGraph(
               this,
               (struct CChainCallContext *)v13,
               *(const struct _CERT_CONTEXT **)dwErrCode,
               v31,
               (const struct _CERT_CHAIN_CONTEXT **)&hSiblingStore) )
        {
          ChainReleaseInternalChainContext((struct _INTERNAL_CERT_CHAIN_CONTEXT *)v73);
          v73 = (struct _CERT_CHAIN_CONTEXT *)hSiblingStore;
          ++*((_DWORD *)v13 + 40);
        }
        CertCloseStore(v31, 0);
      }
LABEL_34:
      CertCloseStore(v28, 0);
      goto LABEL_35;
    }
  }
LABEL_36:
  v32 = 0;
  v71 = 0;
  if ( *((_DWORD *)v13 + 40) )
  {
    if ( (v14->TrustStatus.dwErrorStatus & 0x704AD) == 0 )
    {
      if ( *((_QWORD *)this + 13) )
      {
        rgpChain = v14->rgpChain;
        v34 = 1;
        v35 = (struct _CERT_CONTEXT *)(*rgpChain)->rgpElement;
        v36 = (*rgpChain)->cElement - 1;
        v76 = v35;
        if ( v36 > 1 )
        {
          v37 = 0;
          do
          {
            v38 = *(const CERT_CONTEXT **)(*((_QWORD *)&v35->dwCertEncodingType + v34) + 8LL);
            cbCertEncoded = 0;
            if ( (unsigned int)GetProperty(
                                 (struct _CONTEXT_ELEMENT *)((unsigned __int64)&v38[-2] & -(__int64)(v38 != 0)),
                                 0x43u,
                                 0,
                                 &cbCertEncoded,
                                 0) )
            {
              if ( v34 == 1 )
              {
                v37 |= 1u;
              }
              else
              {
                v37 |= 2u;
                if ( !(_DWORD)v32 )
                  v32 = v34;
              }
              CertSetCertificateContextProperty(v38, 0x43u, 0x80000000, 0);
              CertAddCertificateContextToStore(*((HCERTSTORE *)this + 13), v38, 5u, 0);
            }
            v35 = v76;
            ++v34;
          }
          while ( v34 < v36 );
          v14 = v73;
          v71 = v37;
          v13 = hMem;
        }
      }
    }
  }
  v39 = (PCCERT_CHAIN_CONTEXT *)v13[26];
  v13[26] = 0;
  v14[1].rgpLowerQualityChainContext = v39;
  *(_QWORD *)&v14[1].fHasRevocationFreshnessTime = v13[4];
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AIA_Telemetry>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AIA_Telemetry>::GetImpl'::`2'::impl)
    && *((_DWORD *)v13 + 40) )
  {
    dwErrCode[0] = GetLastError();
    IsThirdPartyChain = IPS_IsThirdPartyChain(v73, 4u);
    v42 = *((_DWORD *)v13 + 14) == 0;
    cbCertEncoded = IsThirdPartyChain;
    if ( v42 )
    {
      v43 = 0;
      v44 = L"None";
    }
    else if ( (unsigned int)ChainIsOIDInUsage("1.3.6.1.5.5.7.3.2", (struct _CTL_USAGE *)(v13 + 7)) )
    {
      v43 = 1;
      v44 = L"ClientAuth";
    }
    else if ( (unsigned int)ChainIsOIDInUsage("1.3.6.1.5.5.7.3.1", (struct _CTL_USAGE *)(v13 + 7)) )
    {
      v43 = 2;
      v44 = L"ServerAuth";
    }
    else if ( (unsigned int)ChainIsOIDInUsage("1.3.6.1.5.5.7.3.3", (struct _CTL_USAGE *)(v13 + 7)) )
    {
      v43 = 3;
      v44 = L"CodeSigning";
    }
    else if ( (unsigned int)ChainIsOIDInUsage("1.3.6.1.5.5.7.3.8", (struct _CTL_USAGE *)(v13 + 7)) )
    {
      v43 = 4;
      v44 = L"TimestampSigning";
    }
    else if ( (unsigned int)ChainIsOIDInUsage("1.3.6.1.5.5.7.3.4", (struct _CTL_USAGE *)(v13 + 7)) )
    {
      v43 = 5;
      v44 = L"EmailProtection";
    }
    else
    {
      v43 = 6;
      v44 = L"Other";
    }
    v45 = v71 | 4;
    v42 = ((*((_BYTE *)v13 + 140) | *(_BYTE *)(v13[1] + 172LL)) & 4) == 0;
    v74 = 0;
    v81 = 4;
    if ( v42 )
      v45 = v71;
    v46 = v13[2];
    v71 = v45;
    GetProperty((struct _CONTEXT_ELEMENT *)((v46 - 80) & -(__int64)(v46 != 0)), 0xEu, &v74, &v81, 0);
    memset_0(v107, 0, 0x52u);
    IPS_GetCertSha1Thumbprint((const struct _CERT_CONTEXT *)v13[2], v107);
    CertGetNameStringW((PCCERT_CONTEXT)v13[2], 5u, 0, 0, pszNameString, 0x40u);
    CertGetNameStringW((PCCERT_CONTEXT)v13[2], 5u, 1u, 0, v111, 0x40u);
    v47 = *v73->rgpChain;
    v48 = v47->cElement - 1;
    v77 = (unsigned __int16 *)v47->rgpElement;
    v49 = (unsigned int)v48;
    v76 = *(struct _CERT_CONTEXT **)(*(_QWORD *)&v77[4 * v48] + 8LL);
    memset_0(v106, 0, 0x52u);
    if ( (*(_BYTE *)(*(_QWORD *)&v77[4 * v49] + 20LL) & 8) != 0 )
      IPS_GetCertSha1Thumbprint(v76, v106);
    memset_0(v105, 0, 0x52u);
    memset_0(v109, 0, sizeof(v109));
    v80 = 0;
    if ( (v71 & 1) != 0 )
    {
      v50 = *(const CERT_CONTEXT **)(*((_QWORD *)v77 + 1) + 8LL);
      IPS_GetCertSha1Thumbprint(v50, v105);
      CertGetNameStringW(v50, 5u, 0, 0, v109, 0x40u);
      v51 = v77;
      v80 = (HLOCAL)LogAIAUrls(*(void **)(*(_QWORD *)v77 + 8LL));
    }
    else
    {
      v51 = v77;
    }
    memset_0(v104, 0, 0x52u);
    memset_0(v108, 0, sizeof(v108));
    hSiblingStore = 0;
    if ( (unsigned int)v32 > 1 && (v71 & 2) != 0 )
    {
      v52 = *(const CERT_CONTEXT **)(*(_QWORD *)&v51[4 * v32] + 8LL);
      IPS_GetCertSha1Thumbprint(v52, v104);
      CertGetNameStringW(v52, 5u, 0, 0, v108, 0x40u);
      v53 = (unsigned __int16 *)LogAIAUrls(*(void **)(*(_QWORD *)&v77[4 * (unsigned int)(v32 - 1)] + 8LL));
    }
    else
    {
      v53 = (unsigned __int16 *)hSiblingStore;
    }
    v54 = L"True";
    if ( !cbCertEncoded )
      v54 = L"False";
    v77 = (unsigned __int16 *)v54;
    InitOnceExecuteOnce(&stru_18015D6E8, ChainProcessNameInitOnceCallback, 0, 0);
    v55 = lpString2;
    v76 = (struct _CERT_CONTEXT *)lpString2;
    hSiblingStore = 0;
    if ( lpString2
      && (CompareStringW(0x409u, 1u, lpString2, -1, L"svchost.exe", -1) == 2
       || CompareStringW(0x409u, 1u, v55, -1, L"dllhost.exe", -1) == 2) )
    {
      InitOnceExecuteOnce(&stru_18015D6F0, ChainServiceNameInitOnceCallback, 0, 0);
      hSiblingStore = qword_18015D198;
    }
    v79 = 0;
    hMem = 0;
    I_GetCallerProcessInfo(&v79, (unsigned __int16 **)&hMem);
    dwErrorStatus = v73->TrustStatus.dwErrorStatus;
    *(_OWORD *)v101 = 0;
    v103 = 0;
    v102 = 0;
    v100 = 0;
    *(_OWORD *)v98 = 0;
    v97 = 0;
    v99 = 0;
    *(_OWORD *)v95 = 0;
    v96 = 0;
    StringCchPrintfW(v101, 0x14u, L"0x%08X", (unsigned int)v74);
    StringCchPrintfW(v98, 0x14u, L"0x%08X", v71);
    StringCchPrintfW(v95, 0x14u, L"0x%08X", dwErrorStatus);
    v57 = 0;
    v58 = (WCHAR *)v80;
    v94[0] = (unsigned __int16 *)v76;
    v94[1] = (unsigned __int16 *)hSiblingStore;
    v94[2] = (unsigned __int16 *)hMem;
    v94[4] = v77;
    v94[5] = v95;
    v94[6] = v98;
    v94[7] = v101;
    v94[8] = v107;
    v94[9] = pszNameString;
    v94[10] = v111;
    v94[11] = v106;
    v94[12] = v105;
    v94[13] = v109;
    v94[15] = v104;
    v94[3] = v44;
    v94[16] = v108;
    v94[14] = (unsigned __int16 *)v80;
    v94[17] = v53;
    do
    {
      v59 = (unsigned __int16 *)&szPassword;
      if ( v94[v57] )
        v59 = v94[v57];
      v94[v57++] = v59;
    }
    while ( v57 != 18 );
    IPR_LogCrypt32Event(2u, 0x1060u, 0x12u, (const unsigned __int16 **)v94);
    InitOnceExecuteOnce(&stru_18015D2C8, Capi2TraceInitOnceCallback, 0, 0);
    if ( (unsigned int)dword_180157050 > 3 && (unsigned __int8)tlgKeywordOn(v60, 0x400000000000LL) )
    {
      v63 = cbCertEncoded;
      v64 = &szPassword;
      v84 = 0x1000000;
      if ( cbCertEncoded )
        v64 = v53;
      v85 = v64;
      v65 = v108;
      if ( !cbCertEncoded )
        v65 = (WCHAR *)&szPassword;
      v86 = v65;
      v87 = v104;
      v66 = &szPassword;
      if ( cbCertEncoded )
        v66 = v58;
      v88 = v66;
      v67 = v109;
      if ( !cbCertEncoded )
        v67 = (WCHAR *)&szPassword;
      v89 = v67;
      v90 = v105;
      v91 = v106;
      v79 = v74;
      cbCertEncoded = v71;
      v68 = v73->TrustStatus.dwErrorStatus;
      v92 = hMem;
      LODWORD(v80) = v63;
      v71 = v68;
      LODWORD(v77) = v43;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<8>>(
        v68,
        (unsigned int)word_180144C4A,
        v61,
        v62,
        (__int64)&v76,
        (__int64)&hSiblingStore,
        (__int64)&v92,
        (__int64)&v77,
        (__int64)&v80,
        (__int64)&v71,
        (__int64)&cbCertEncoded,
        (__int64)&v79,
        (__int64)&v91,
        (__int64)&v90,
        (__int64)&v89,
        (__int64)&v88,
        (__int64)&v87,
        (__int64)&v86,
        (__int64)&v85,
        (__int64)&v84);
    }
    if ( hMem )
      PkiDefaultCryptFree(hMem);
    if ( v58 )
      PkiDefaultCryptFree(v58);
    if ( v53 )
      PkiDefaultCryptFree(v53);
    SetLastError(dwErrCode[0]);
  }
  CCertChainEngine::TriggerPreFetch(this, v40, (struct CChainCallContext *)v13, a6, v73->TrustStatus.dwErrorStatus);
  LastError = v83;
  v8 = v93;
LABEL_105:
  if ( v13 )
  {
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
    CallContextFreeCallObject((struct CChainCallContext *)v13);
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
  }
  if ( LastError )
    SetLastError(LastError);
  result = v15;
  *v8 = v73;
  return result;
}

```

## disassembly

```asm
0x1800b9604  mov     [rsp-8+arg_10], rbx
0x1800b9609  push    rbp
0x1800b960a  push    rsi
0x1800b960b  push    rdi
0x1800b960c  push    r12
0x1800b960e  push    r13
0x1800b9610  push    r14
0x1800b9612  push    r15
0x1800b9614  lea     rbp, [rsp-4D0h]
0x1800b961c  sub     rsp, 5F0h
0x1800b9623  mov     rax, cs:__security_cookie
0x1800b962a  xor     rax, rsp
0x1800b962d  mov     [rbp+500h+var_40], rax
0x1800b9634  mov     r13, [rbp+500h+arg_38]
0x1800b963b  mov     r15, rcx
0x1800b963e  lea     rcx, [rbp+500h+hMem]
0x1800b9642  mov     qword ptr [rbp+500h+dwErrCode], rdx
0x1800b9646  mov     qword ptr [rsp+620h+cchNameString], rcx; struct CChainCallContext **
0x1800b964b  mov     rbx, r9
0x1800b964e  mov     ecx, [rbp+500h+arg_28]
0x1800b9654  mov     rax, r8
0x1800b9657  mov     r8, [rbp+500h+arg_20]; struct _CERT_CHAIN_PARA *
0x1800b965e  mov     r12, rdx
0x1800b9661  mov     dword ptr [rsp+620h+pvPara], ecx; unsigned int
0x1800b9665  mov     r9, rdx; struct _CERT_CONTEXT *
0x1800b9668  mov     rcx, r15; struct CCertChainEngine *
0x1800b966b  mov     [rbp+500h+hSiblingStore], rbx
0x1800b966f  mov     rdx, rax; struct _FILETIME *
0x1800b9672  mov     [rbp+500h+var_4D8], r13
0x1800b9676  mov     [rbp+500h+hMem], 0
0x1800b967e  mov     [rbp+500h+var_578], 0
0x1800b9686  call    ?CallContextCreateCallObject@@YAHPEAVCCertChainEngine@@PEAU_FILETIME@@PEAU_CERT_CHAIN_PARA@@PEBU_CERT_CONTEXT@@KPEAPEAVCChainCallContext@@@Z; CallContextCreateCallObject(CCertChainEngine *,_FILETIME *,_CERT_CHAIN_PARA *,_CERT_CONTEXT const *,ulong,CChainCallContext * *)
0x1800b968b  mov     rdi, [rbp+500h+hMem]
0x1800b968f  test    eax, eax
0x1800b9691  jz      loc_1800BA1DE
0x1800b9697  mov     r8, r12; struct _CERT_CONTEXT *
0x1800b969a  mov     rdx, rdi; struct CChainCallContext *
0x1800b969d  mov     rcx, r15; this
0x1800b96a0  call    ?GetTimeValidDisallowedCertAutoUpdateCtl@CCertChainEngine@@QEAAXPEAVCChainCallContext@@PEBU_CERT_CONTEXT@@@Z; CCertChainEngine::GetTimeValidDisallowedCertAutoUpdateCtl(CChainCallContext *,_CERT_CONTEXT const *)
0x1800b96a5  lea     rax, [rbp+500h+var_578]
0x1800b96a9  mov     r9, rbx; void *
0x1800b96ac  mov     r8, r12; struct _CERT_CONTEXT *
0x1800b96af  mov     [rsp+620h+pvPara], rax; struct _CERT_CHAIN_CONTEXT **
0x1800b96b4  mov     rdx, rdi; struct CChainCallContext *
0x1800b96b7  mov     rcx, r15; this
0x1800b96ba  call    ?CreateChainContextFromPathGraph@CCertChainEngine@@QEAAHPEAVCChainCallContext@@PEBU_CERT_CONTEXT@@PEAXPEAPEBU_CERT_CHAIN_CONTEXT@@@Z; CCertChainEngine::CreateChainContextFromPathGraph(CChainCallContext *,_CERT_CONTEXT const *,void *,_CERT_CHAIN_CONTEXT const * *)
0x1800b96bf  test    eax, eax
0x1800b96c1  jz      loc_1800BA1DE
0x1800b96c7  mov     rbx, [rbp+500h+var_578]
0x1800b96cb  mov     esi, 1
0x1800b96d0  mov     [rbp+500h+var_528], 0
0x1800b96d7  mov     eax, [rbx+4]
0x1800b96da  test    al, 25h
0x1800b96dc  jz      loc_1800B9936
0x1800b96e2  mov     rax, [rbx+10h]
0x1800b96e6  mov     r13, [rax]
0x1800b96e9  mov     r14, [r13+10h]
0x1800b96ed  mov     rax, [r14]
0x1800b96f0  test    byte ptr [rax+10h], 25h
0x1800b96f4  jnz     loc_1800B9936
0x1800b96fa  mov     r13d, [r13+0Ch]
0x1800b96fe  lea     rdx, [rbp+500h+var_570]; int *
0x1800b9702  mov     rcx, rdi; this
0x1800b9705  mov     [rbp+500h+var_570], 0
0x1800b970c  call    ?IsOnline@CChainCallContext@@QEAAHPEAH@Z; CChainCallContext::IsOnline(int *)
0x1800b9711  cmp     [rbp+500h+var_570], 0
0x1800b9715  mov     ebx, eax
0x1800b9717  jz      short loc_1800B9721
0x1800b9719  mov     rcx, r12
0x1800b971c  call    CertDiagAIAUrlRetrievalNotConnected
0x1800b9721  test    ebx, ebx
0x1800b9723  jz      loc_1800B9932
0x1800b9729  mov     rbx, [rbp+500h+var_578]
0x1800b972d  mov     eax, [rbx+4]
0x1800b9730  and     eax, 25h
0x1800b9733  cmp     al, 20h ; ' '
0x1800b9735  jnz     short loc_1800B9770
0x1800b9737  cmp     r13d, 2
0x1800b973b  jb      loc_1800B9936
0x1800b9741  lea     eax, [r13-1]
0x1800b9745  mov     rcx, r15; this
0x1800b9748  mov     rdx, [r14+rax*8]
0x1800b974c  mov     ebx, eax
0x1800b974e  mov     rdx, [rdx+8]; struct _CERT_CONTEXT *
0x1800b9752  call    ?IsPotentialKeyRolloverRoot@CCertChainEngine@@QEAAHPEBU_CERT_CONTEXT@@@Z; CCertChainEngine::IsPotentialKeyRolloverRoot(_CERT_CONTEXT const *)
0x1800b9757  test    eax, eax
0x1800b9759  jz      loc_1800B9932
0x1800b975f  mov     r9, [r14+rbx*8]
0x1800b9763  lea     eax, [r13-2]
0x1800b9767  mov     r9, [r9+8]
0x1800b976b  jmp     loc_1800B980D
0x1800b9770  mov     r12d, esi
0x1800b9773  cmp     r13d, esi
0x1800b9776  jbe     loc_1800B9936
0x1800b977c  mov     eax, r12d
0x1800b977f  mov     rax, [r14+rax*8]
0x1800b9783  mov     [rbp+500h+var_560], rax
0x1800b9787  mov     ecx, [rax+10h]
0x1800b978a  mov     [rbp+500h+var_57C], ecx
0x1800b978d  test    cl, 25h
0x1800b9790  jnz     short loc_1800B979F
0x1800b9792  add     r12d, esi
0x1800b9795  cmp     r12d, r13d
0x1800b9798  jb      short loc_1800B977C
0x1800b979a  jmp     loc_1800B9936
0x1800b979f  mov     r13, [rax+8]
0x1800b97a3  lea     rcx, a136141311202; "1.3.6.1.4.1.311.20.2"
0x1800b97aa  mov     rdx, [r13+18h]
0x1800b97ae  mov     r8, [rdx+0C8h]; rgExtensions
0x1800b97b5  mov     edx, [rdx+0C0h]; cExtensions
0x1800b97bb  call    CertFindExtension
0x1800b97c0  test    rax, rax
0x1800b97c3  jz      short loc_1800B97EC
0x1800b97c5  cmp     dword ptr [rax+10h], 10h
0x1800b97c9  jnz     short loc_1800B97EC
0x1800b97cb  mov     rcx, [rax+18h]
0x1800b97cf  mov     rax, [rcx]
0x1800b97d2  cmp     rax, cs:qword_180142048
0x1800b97d9  jnz     short loc_1800B97EC
0x1800b97db  mov     rax, [rcx+8]
0x1800b97df  cmp     rax, cs:qword_180142050
0x1800b97e6  jz      loc_1800B9936
0x1800b97ec  test    byte ptr [rbp+500h+var_57C], 4
0x1800b97f0  jz      short loc_1800B9805
0x1800b97f2  mov     rcx, [rbp+500h+var_560]; struct _CERT_CHAIN_ELEMENT *
0x1800b97f6  call    ?ChainGetElementCrlReasonCode@@YAKPEAU_CERT_CHAIN_ELEMENT@@@Z; ChainGetElementCrlReasonCode(_CERT_CHAIN_ELEMENT *)
0x1800b97fb  dec     eax
0x1800b97fd  cmp     eax, esi
0x1800b97ff  jbe     loc_1800B9932
0x1800b9805  lea     eax, [r12-1]
0x1800b980a  mov     r9, r13; struct _CERT_CONTEXT *
0x1800b980d  mov     r8, [r14+rax*8]
0x1800b9811  mov     rdx, rdi; struct CChainCallContext *
0x1800b9814  mov     rcx, r15; this
0x1800b9817  mov     r8, [r8+8]; struct _CERT_CONTEXT *
0x1800b981b  call    ?GetNewerIssuerUrlStore@CCertChainEngine@@QEAAPEAXPEAVCChainCallContext@@PEBU_CERT_CONTEXT@@1@Z; CCertChainEngine::GetNewerIssuerUrlStore(CChainCallContext *,_CERT_CONTEXT const *,_CERT_CONTEXT const *)
0x1800b9820  mov     r12, rax
0x1800b9823  test    rax, rax
0x1800b9826  jz      loc_1800B9932
0x1800b982c  mov     rbx, [rbp+500h+hSiblingStore]
0x1800b9830  test    rbx, rbx
0x1800b9833  jz      short loc_1800B989A
0x1800b9835  mov     r9d, 4; dwFlags
0x1800b983b  mov     [rsp+620h+pvPara], 0; pvPara
0x1800b9844  xor     r8d, r8d; hCryptProv
0x1800b9847  mov     edx, 10001h; dwEncodingType
0x1800b984c  lea     ecx, [r9+7]; lpszStoreProvider
0x1800b9850  call    CertOpenStore
0x1800b9855  mov     r14, rax
0x1800b9858  test    rax, rax
0x1800b985b  jz      loc_1800B9928
0x1800b9861  xor     r9d, r9d; dwPriority
0x1800b9864  xor     r8d, r8d; dwUpdateFlags
0x1800b9867  mov     rdx, r12; hSiblingStore
0x1800b986a  mov     rcx, rax; hCollectionStore
0x1800b986d  call    CertAddStoreToCollection
0x1800b9872  test    eax, eax
0x1800b9874  jz      short loc_1800B988B
0x1800b9876  xor     r9d, r9d; dwPriority
0x1800b9879  xor     r8d, r8d; dwUpdateFlags
0x1800b987c  mov     rdx, rbx; hSiblingStore
0x1800b987f  mov     rcx, r14; hCollectionStore
0x1800b9882  call    CertAddStoreToCollection
0x1800b9887  test    eax, eax
0x1800b9889  jnz     short loc_1800B98AA
0x1800b988b  xor     edx, edx; dwFlags
0x1800b988d  mov     rcx, r14; hCertStore
0x1800b9890  call    CertCloseStore
0x1800b9895  xor     r14d, r14d
0x1800b9898  jmp     short loc_1800B98A5
0x1800b989a  mov     rcx, r12; hCertStore
0x1800b989d  call    CertDuplicateStore
0x1800b98a2  mov     r14, rax
0x1800b98a5  test    r14, r14
0x1800b98a8  jz      short loc_1800B9928
0x1800b98aa  lea     rcx, [r15+8]; lpCriticalSection
0x1800b98ae  mov     [rbp+500h+hSiblingStore], 0
0x1800b98b6  call    cs:__imp_EnterCriticalSection
0x1800b98bc  mov     rcx, [rdi]
0x1800b98bf  mov     r8, rdi
0x1800b98c2  xor     edx, edx
0x1800b98c4  call    I_CryptFlushLruCache
0x1800b98c9  lea     rcx, [r15+8]; lpCriticalSection
0x1800b98cd  mov     dword ptr [rdi+0A0h], 0
0x1800b98d7  mov     qword ptr [rdi+0ACh], 0
0x1800b98e2  call    cs:__imp_LeaveCriticalSection
0x1800b98e8  mov     r8, qword ptr [rbp+500h+dwErrCode]; struct _CERT_CONTEXT *
0x1800b98ec  lea     rax, [rbp+500h+hSiblingStore]
0x1800b98f0  mov     r9, r14; void *
0x1800b98f3  mov     [rsp+620h+pvPara], rax; struct _CERT_CHAIN_CONTEXT **
0x1800b98f8  mov     rdx, rdi; struct CChainCallContext *
0x1800b98fb  mov     rcx, r15; this
0x1800b98fe  call    ?CreateChainContextFromPathGraph@CCertChainEngine@@QEAAHPEAVCChainCallContext@@PEBU_CERT_CONTEXT@@PEAXPEAPEBU_CERT_CHAIN_CONTEXT@@@Z; CCertChainEngine::CreateChainContextFromPathGraph(CChainCallContext *,_CERT_CONTEXT const *,void *,_CERT_CHAIN_CONTEXT const * *)
0x1800b9903  test    eax, eax
0x1800b9905  jz      short loc_1800B991E
0x1800b9907  mov     rcx, [rbp+500h+var_578]; struct _INTERNAL_CERT_CHAIN_CONTEXT *
0x1800b990b  call    ?ChainReleaseInternalChainContext@@YAXPEAU_INTERNAL_CERT_CHAIN_CONTEXT@@@Z; ChainReleaseInternalChainContext(_INTERNAL_CERT_CHAIN_CONTEXT *)
0x1800b9910  mov     rax, [rbp+500h+hSiblingStore]
0x1800b9914  mov     [rbp+500h+var_578], rax
0x1800b9918  add     [rdi+0A0h], esi
0x1800b991e  xor     edx, edx; dwFlags
0x1800b9920  mov     rcx, r14; hCertStore
0x1800b9923  call    CertCloseStore
0x1800b9928  xor     edx, edx; dwFlags
0x1800b992a  mov     rcx, r12; hCertStore
0x1800b992d  call    CertCloseStore
0x1800b9932  mov     rbx, [rbp+500h+var_578]
0x1800b9936  xor     r13d, r13d
0x1800b9939  mov     [rbp+500h+var_580], 0
0x1800b9940  cmp     [rdi+0A0h], r13d
0x1800b9947  jbe     loc_1800B9A1D
0x1800b994d  test    dword ptr [rbx+4], 704ADh
0x1800b9954  jnz     loc_1800B9A1D
0x1800b995a  cmp     [r15+68h], r13
0x1800b995e  jz      loc_1800B9A1D
0x1800b9964  mov     rax, [rbx+10h]
0x1800b9968  mov     r14d, esi
0x1800b996b  mov     rcx, [rax]
0x1800b996e  mov     r12d, [rcx+0Ch]
0x1800b9972  mov     rdx, [rcx+10h]
0x1800b9976  sub     r12d, esi
0x1800b9979  mov     [rbp+500h+var_560], rdx
0x1800b997d  cmp     r12d, esi
0x1800b9980  jbe     loc_1800B9A1D
0x1800b9986  mov     edi, r13d
0x1800b9989  mov     eax, r14d
0x1800b998c  lea     r9, [rbp+500h+var_57C]; unsigned int *
0x1800b9990  mov     dword ptr [rsp+620h+pvPara], 0; int
0x1800b9998  mov     rcx, [rdx+rax*8]
0x1800b999c  mov     rbx, [rcx+8]
0x1800b99a0  mov     rax, rbx
0x1800b99a3  mov     [rbp+500h+var_57C], 0
0x1800b99aa  neg     rax
0x1800b99ad  sbb     rcx, rcx
0x1800b99b0  lea     rdx, [rbx-50h]
0x1800b99b4  xor     r8d, r8d; void *
0x1800b99b7  and     rcx, rdx; struct _CONTEXT_ELEMENT *
0x1800b99ba  lea     edx, [r8+43h]; unsigned int
0x1800b99be  call    ?GetProperty@@YAHPEAU_CONTEXT_ELEMENT@@KPEAXPEAKH@Z; GetProperty(_CONTEXT_ELEMENT *,ulong,void *,ulong *,int)
0x1800b99c3  test    eax, eax
0x1800b99c5  jz      short loc_1800B9A02
0x1800b99c7  cmp     r14d, esi
0x1800b99ca  jnz     short loc_1800B99D0
0x1800b99cc  or      edi, esi
0x1800b99ce  jmp     short loc_1800B99DA
0x1800b99d0  or      edi, 2
0x1800b99d3  test    r13d, r13d
0x1800b99d6  cmovz   r13d, r14d
0x1800b99da  xor     r9d, r9d; pvData
0x1800b99dd  mov     r8d, 80000000h; dwFlags
0x1800b99e3  mov     rcx, rbx; pCertContext
0x1800b99e6  lea     edx, [r9+43h]; dwPropId
0x1800b99ea  call    CertSetCertificateContextProperty
0x1800b99ef  mov     rcx, [r15+68h]; hCertStore
0x1800b99f3  xor     r9d, r9d; ppStoreContext
0x1800b99f6  mov     rdx, rbx; pCertContext
0x1800b99f9  lea     r8d, [r9+5]; dwAddDisposition
0x1800b99fd  call    CertAddCertificateContextToStore
0x1800b9a02  mov     rdx, [rbp+500h+var_560]
0x1800b9a06  add     r14d, esi
0x1800b9a09  cmp     r14d, r12d
0x1800b9a0c  jb      loc_1800B9989
0x1800b9a12  mov     rbx, [rbp+500h+var_578]
0x1800b9a16  mov     [rbp+500h+var_580], edi
0x1800b9a19  mov     rdi, [rbp+500h+hMem]
0x1800b9a1d  mov     rax, [rdi+0D0h]
0x1800b9a24  mov     qword ptr [rdi+0D0h], 0
0x1800b9a2f  mov     [rbx+68h], rax
0x1800b9a33  mov     rax, [rdi+20h]
0x1800b9a37  mov     [rbx+70h], rax
0x1800b9a3b  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AIA_Telemetry@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AIA_Telemetry@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AIA_Telemetry> `wil::Feature<__WilFeatureTraits_Feature_AIA_Telemetry>::GetImpl(void)'::`2'::impl
0x1800b9a42  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_AIA_Telemetry@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AIA_Telemetry>::__private_IsEnabled(void)
0x1800b9a47  test    al, al
0x1800b9a49  jz      loc_1800BA1B7
0x1800b9a4f  cmp     dword ptr [rdi+0A0h], 0
0x1800b9a56  jbe     loc_1800BA1B7
0x1800b9a5c  lea     rbx, [rdi+38h]
0x1800b9a60  call    cs:__imp_GetLastError
0x1800b9a66  mov     rcx, [rbp+500h+var_578]; struct _CERT_CHAIN_CONTEXT *
0x1800b9a6a  mov     r14d, 4
0x1800b9a70  mov     edx, r14d; unsigned int
0x1800b9a73  mov     [rbp+500h+dwErrCode], eax
0x1800b9a76  call    ?IPS_IsThirdPartyChain@@YAHPEBU_CERT_CHAIN_CONTEXT@@K@Z; IPS_IsThirdPartyChain(_CERT_CHAIN_CONTEXT const *,ulong)
0x1800b9a7b  cmp     dword ptr [rbx], 0
0x1800b9a7e  mov     [rbp+500h+var_57C], eax
0x1800b9a81  jnz     short loc_1800B9A92
0x1800b9a83  xor     r12d, r12d
0x1800b9a86  lea     r14, aNone_0; "None"
0x1800b9a8d  jmp     loc_1800B9B46
0x1800b9a92  mov     rdx, rbx; struct _CTL_USAGE *
0x1800b9a95  lea     rcx, a136155732; "1.3.6.1.5.5.7.3.2"
0x1800b9a9c  call    ?ChainIsOIDInUsage@@YAHPEADPEAU_CTL_USAGE@@@Z; ChainIsOIDInUsage(char *,_CTL_USAGE *)
0x1800b9aa1  test    eax, eax
0x1800b9aa3  jz      short loc_1800B9AB4
0x1800b9aa5  mov     r12d, esi
0x1800b9aa8  lea     r14, aClientauth; "ClientAuth"
0x1800b9aaf  jmp     loc_1800B9B46
0x1800b9ab4  mov     rdx, rbx; struct _CTL_USAGE *
0x1800b9ab7  lea     rcx, a136155731; "1.3.6.1.5.5.7.3.1"
0x1800b9abe  call    ?ChainIsOIDInUsage@@YAHPEADPEAU_CTL_USAGE@@@Z; ChainIsOIDInUsage(char *,_CTL_USAGE *)
  ... truncated ...
```
