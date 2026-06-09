# CertDiagPrvXmlFormatChainElementElement(void *,_CERT_CHAIN_ELEMENT *,_CERT_TRUST_LIST_INFO *,_CERT_CONTEXT const *)

- ea: `0x18000ac20`
- end: `0x18000bad0`
- name: `?CertDiagPrvXmlFormatChainElementElement@@YAXPEAXPEAU_CERT_CHAIN_ELEMENT@@PEAU_CERT_TRUST_LIST_INFO@@PEBU_CERT_CONTEXT@@@Z`
- size: `3760`
- prototype: `void __fastcall(_DWORD *, struct _CERT_CHAIN_ELEMENT *, struct _CERT_TRUST_LIST_INFO *, struct _CERT_CONTEXT *)`
- caller_count: `1`
- callee_count: `15`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800051f0`

## callees

- `0x18000666c`
- `0x180009da0`
- `0x18000ac20`
- `0x18000bae0`
- `0x18000f970`
- `0x180015440`
- `0x180015500`
- `0x180026d50`
- `0x180028d60`
- `0x18002f0e0`
- `0x18002f250`
- `0x180030e60`
- `0x1800600e0`
- `0x1800616d0`
- `0x1800c3c74`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ae7a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ae7a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000ae42`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000ae8d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000ae42`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000ae8d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000ae85`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000b663`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000ae85`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000b663`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18000b614`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18000b614`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18000aefc`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18000aefc`

## pseudocode

```c
void __fastcall CertDiagPrvXmlFormatChainElementElement(
        _DWORD *a1,
        struct _CERT_CHAIN_ELEMENT *a2,
        struct _CERT_TRUST_LIST_INFO *a3,
        struct _CERT_CONTEXT *a4)
{
  __int64 v5; // rcx
  const wchar_t *v6; // r12
  int v7; // r13d
  int v9; // ebx
  const wchar_t *v10; // rsi
  DWORD v11; // edx
  wchar_t *i; // r8
  wchar_t v13; // r14
  __int64 v14; // rcx
  const wchar_t *v15; // rsi
  int v16; // ebx
  DWORD v17; // edx
  wchar_t *j; // r8
  wchar_t v19; // r14
  __int64 v20; // rcx
  const wchar_t *v21; // rsi
  int v22; // ebx
  DWORD v23; // edx
  wchar_t *k; // r8
  wchar_t v25; // r14
  struct _CERT_CHAIN_ELEMENT *v26; // r14
  const CERT_CONTEXT *pCertContext; // rsi
  CRYPT_ALGORITHM_IDENTIFIER *p_SignatureAlgorithm; // rax
  __int16 *v29; // rbx
  __int16 *v30; // rax
  __int16 v31; // cx
  __int16 *v32; // rdx
  HLOCAL v33; // rsi
  DWORD LastError; // ebx
  PCCERT_CONTEXT v35; // rax
  struct _CERT_PUBLIC_KEY_INFO *p_SubjectPublicKeyInfo; // rsi
  DWORD PublicKeyLength; // eax
  LPSTR pszObjId; // rdx
  PCCRYPT_OID_INFO OIDInfo; // rax
  PCCRYPT_OID_INFO v40; // rbx
  const WCHAR *v41; // r8
  __int64 v42; // rcx
  int v43; // ebx
  DWORD v44; // edx
  wchar_t *m; // r8
  wchar_t v46; // si
  __int64 v47; // rcx
  const wchar_t *v48; // r15
  int v49; // ebx
  const wchar_t *v50; // rsi
  DWORD v51; // edx
  wchar_t *n; // r8
  wchar_t v53; // r14
  __int64 v54; // rcx
  const wchar_t *v55; // rsi
  int v56; // ebx
  DWORD v57; // edx
  wchar_t *ii; // r8
  wchar_t v59; // r14
  struct _CERT_CHAIN_ELEMENT *v60; // r12
  __int64 v61; // rcx
  const wchar_t *v62; // r14
  int v63; // ebx
  DWORD v64; // r8d
  wchar_t *jj; // rdx
  wchar_t v66; // si
  __int64 v67; // rcx
  int v68; // ebx
  DWORD v69; // edx
  wchar_t *kk; // r8
  wchar_t v71; // si
  __int64 v72; // rcx
  int v73; // ebx
  const wchar_t *v74; // rsi
  DWORD v75; // edx
  wchar_t *mm; // r8
  wchar_t v77; // r14
  PCERT_ENHKEY_USAGE pApplicationUsage; // rsi
  const wchar_t *v79; // r12
  __int64 v80; // rcx
  int v81; // ebx
  DWORD v82; // edx
  wchar_t *v83; // r8
  DWORD v84; // ecx
  const wchar_t *nn; // r14
  wchar_t v86; // r15
  DWORD i1; // ebx
  LPSTR *rgpszUsageIdentifier; // rax
  PCCRYPT_OID_INFO v89; // rax
  struct _CERT_CHAIN_ELEMENT *v90; // r14
  PCERT_ENHKEY_USAGE pIssuanceUsage; // rsi
  __int64 v92; // rcx
  int v93; // ebx
  DWORD v94; // edx
  wchar_t *v95; // r8
  DWORD v96; // ecx
  const wchar_t *v97; // r12
  const wchar_t *i3; // r14
  wchar_t v99; // r15
  DWORD i4; // ebx
  LPSTR *v101; // rax
  PCCRYPT_OID_INFO v102; // rax
  const unsigned __int16 *pwszExtendedErrorInfo; // rcx
  __int64 v104; // rcx
  const wchar_t *v105; // r14
  int v106; // ebx
  DWORD v107; // edx
  wchar_t *i6; // r8
  wchar_t v109; // si
  __int64 v110; // rcx
  const wchar_t *v111; // r14
  int v112; // ebx
  DWORD v113; // edx
  wchar_t *i7; // r8
  wchar_t v115; // si
  __int64 v116; // rcx
  DWORD v117; // edx
  wchar_t *i8; // r8
  wchar_t v119; // bx
  __int64 v120; // rsi
  void *v121; // rbx
  DWORD v122; // r8d
  struct _CERT_REVOCATION_CRL_INFO *v123; // rbx
  const CERT_CONTEXT *pBaseCrlContext; // rdx
  const CERT_CONTEXT *pDeltaCrlContext; // rdx
  int v126; // eax
  int v127; // eax
  int v128; // eax
  int v129; // eax
  int v130; // eax
  int v131; // eax
  int v132; // eax
  int v133; // eax
  int v134; // eax
  int v135; // eax
  int v136; // eax
  int v137; // eax
  const wchar_t *i2; // rsi
  wchar_t v139; // r14
  wchar_t v140; // si
  int v141; // eax
  int v142; // eax
  int v143; // eax
  int v144; // eax
  struct _CERT_CONTEXT *v145; // rbx
  unsigned int i5; // edx
  __int64 v147; // rax
  DWORD pcbData; // [rsp+40h] [rbp-99h] BYREF
  const WCHAR *pwszName; // [rsp+48h] [rbp-91h] BYREF
  WCHAR Buffer[4]; // [rsp+50h] [rbp-89h] BYREF
  HLOCAL hMem; // [rsp+58h] [rbp-81h] BYREF
  struct _CERT_CHAIN_ELEMENT *v152; // [rsp+60h] [rbp-79h] BYREF
  _QWORD *p_pszObjId; // [rsp+68h] [rbp-71h] BYREF
  HLOCAL *p_pwszName; // [rsp+70h] [rbp-69h]
  void *p_hMem; // [rsp+78h] [rbp-61h]
  struct _CERT_CONTEXT *v156; // [rsp+80h] [rbp-59h] BYREF
  const wchar_t *v157; // [rsp+90h] [rbp-49h]
  int v158; // [rsp+98h] [rbp-41h]
  __int64 v159; // [rsp+9Ch] [rbp-3Dh]
  int v160; // [rsp+A4h] [rbp-35h]
  __int64 v161; // [rsp+A8h] [rbp-31h]
  __int64 v162; // [rsp+B0h] [rbp-29h]
  int v163; // [rsp+B8h] [rbp-21h]
  __int64 v164; // [rsp+BCh] [rbp-1Dh]
  int v165; // [rsp+C4h] [rbp-15h]
  __int64 *v166; // [rsp+C8h] [rbp-11h]
  DWORD *p_pcbData; // [rsp+D0h] [rbp-9h]
  void **p_p_pszObjId; // [rsp+D8h] [rbp-1h]
  WCHAR *v169; // [rsp+E0h] [rbp+7h]

  v152 = a2;
  v5 = (unsigned int)a1[3];
  v6 = L"<";
  v7 = -1;
  v156 = a4;
  v9 = -1;
  v10 = L"<";
  v11 = a1[2] - v5;
  for ( i = (wchar_t *)(*(_QWORD *)a1 + 2 * v5); v9; ++i )
  {
    v13 = *v10;
    if ( !*v10 )
      break;
    if ( !v11 )
    {
      v126 = a1[2];
      pcbData = 128;
      a1[3] = v126;
      i = (wchar_t *)CertDiagStrMemAlloc(a1, &pcbData);
      if ( !i )
        goto LABEL_7;
      v11 = pcbData;
    }
    --v11;
    *i = v13;
    --v9;
    ++v10;
  }
  a1[3] = a1[2] - v11;
LABEL_7:
  v14 = (unsigned int)a1[3];
  v15 = L"ChainElement";
  v16 = -1;
  v17 = a1[2] - v14;
  for ( j = (wchar_t *)(*(_QWORD *)a1 + 2 * v14); v16; ++j )
  {
    v19 = *v15;
    if ( !*v15 )
      break;
    if ( !v17 )
    {
      v127 = a1[2];
      pcbData = 128;
      a1[3] = v127;
      j = (wchar_t *)CertDiagStrMemAlloc(a1, &pcbData);
      if ( !j )
        goto LABEL_13;
      v17 = pcbData;
    }
    --v17;
    *j = v19;
    --v16;
    ++v15;
  }
  a1[3] = a1[2] - v17;
LABEL_13:
  v20 = (unsigned int)a1[3];
  v21 = L">";
  v22 = -1;
  v23 = a1[2] - v20;
  for ( k = (wchar_t *)(*(_QWORD *)a1 + 2 * v20); v22; ++k )
  {
    v25 = *v21;
    if ( !*v21 )
      break;
    if ( !v23 )
    {
      v128 = a1[2];
      pcbData = 128;
      a1[3] = v128;
      k = (wchar_t *)CertDiagStrMemAlloc(a1, &pcbData);
      if ( !k )
        goto LABEL_19;
      v23 = pcbData;
    }
    --v23;
    *k = v25;
    --v22;
    ++v21;
  }
  a1[3] = a1[2] - v23;
LABEL_19:
  v26 = v152;
  CertDiagXmlFormatCertificateRefElement(a1);
  if ( a3 && a3->pCtlContext )
    CertDiagXmlFormatCtlRefElement(a1);
  pCertContext = v26->pCertContext;
  if ( pCertContext )
  {
    p_SignatureAlgorithm = &pCertContext->pCertInfo->SignatureAlgorithm;
    hMem = 0;
    p_pszObjId = &p_SignatureAlgorithm->pszObjId;
    v29 = 0;
    pwszName = 0;
    p_pwszName = (HLOCAL *)&pwszName;
    pcbData = 0;
    p_hMem = &hMem;
    if ( CertGetCertificateContextProperty(pCertContext, 0x59u, 0, &pcbData) && pcbData && pcbData + 4 >= pcbData )
    {
      v30 = (__int16 *)PkiNonzeroAlloc(pcbData + 4LL);
      v29 = v30;
      if ( !v30 )
        goto LABEL_33;
      if ( CertGetCertificateContextProperty(pCertContext, 0x59u, v30, &pcbData) && pcbData )
      {
        *(_DWORD *)((char *)v29 + pcbData) = 0;
        hMem = v29;
        pwszName = (const WCHAR *)v29;
        v31 = *v29;
        if ( *v29 )
        {
          v32 = v29;
          while ( v31 != 47 )
          {
            v29 = v32 + 1;
            pwszName = (const WCHAR *)v29;
            ++v32;
            v31 = *v29;
            if ( !*v29 )
              goto LABEL_31;
          }
          *v29 = 0;
          ++pwszName;
        }
        else
        {
LABEL_31:
          pwszName = 0;
        }
        goto LABEL_34;
      }
    }
    SetLastError(0x80092004);
    if ( v29 )
    {
      PkiDefaultCryptFree(v29);
      hMem = 0;
      goto LABEL_34;
    }
LABEL_33:
    hMem = v29;
LABEL_34:
    CertDiagXmlFormatElement(a1);
    v33 = hMem;
    if ( hMem )
    {
      LastError = GetLastError();
      LocalFree(v33);
      SetLastError(LastError);
    }
    v35 = v26->pCertContext;
    pwszName = 0;
    p_SubjectPublicKeyInfo = &v35->pCertInfo->SubjectPublicKeyInfo;
    PublicKeyLength = CertGetPublicKeyLength(0x10001u, p_SubjectPublicKeyInfo);
    pszObjId = p_SubjectPublicKeyInfo->Algorithm.pszObjId;
    pcbData = PublicKeyLength;
    OIDInfo = CryptFindOIDInfo(1u, pszObjId, 0xC0000003);
    v40 = OIDInfo;
    if ( OIDInfo )
    {
      v41 = *(const WCHAR **)&OIDInfo[1].cbSize;
      pwszName = v41;
      if ( v41 )
      {
        if ( CompareStringW(0x409u, 1u, v41, -1, L"CryptOIDInfoECCParameters", -1) == 2 )
          pwszName = v40->pwszName;
      }
    }
    p_pszObjId = &p_SubjectPublicKeyInfo->Algorithm.pszObjId;
    p_pwszName = (HLOCAL *)&pwszName;
    p_hMem = &pcbData;
    CertDiagXmlFormatElement(a1);
  }
  v42 = (unsigned int)a1[3];
  v43 = -1;
  v44 = a1[2] - v42;
  for ( m = (wchar_t *)(*(_QWORD *)a1 + 2 * v42); v43; ++m )
  {
    v46 = *v6;
    if ( !*v6 )
      break;
    if ( !v44 )
    {
      v129 = a1[2];
      pcbData = 128;
      a1[3] = v129;
      m = (wchar_t *)CertDiagStrMemAlloc(a1, &pcbData);
      if ( !m )
        goto LABEL_47;
      v44 = pcbData;
    }
    --v44;
    *m = v46;
    --v43;
    ++v6;
  }
  a1[3] = a1[2] - v44;
LABEL_47:
  v47 = (unsigned int)a1[3];
  v48 = L"TrustStatus";
  v49 = -1;
  v50 = L"TrustStatus";
  v51 = a1[2] - v47;
  for ( n = (wchar_t *)(*(_QWORD *)a1 + 2 * v47); v49; ++n )
  {
    v53 = *v50;
    if ( !*v50 )
      break;
    if ( !v51 )
    {
      v130 = a1[2];
      pcbData = 128;
      a1[3] = v130;
      n = (wchar_t *)CertDiagStrMemAlloc(a1, &pcbData);
      if ( !n )
        goto LABEL_53;
      v51 = pcbData;
    }
    --v51;
    *n = v53;
    --v49;
    ++v50;
  }
  a1[3] = a1[2] - v51;
LABEL_53:
  v54 = (unsigned int)a1[3];
  v55 = L">";
  v56 = -1;
  v57 = a1[2] - v54;
  for ( ii = (wchar_t *)(*(_QWORD *)a1 + 2 * v54); v56; ++ii )
  {
    v59 = *v55;
    if ( !*v55 )
      break;
    if ( !v57 )
    {
      v131 = a1[2];
      pcbData = 128;
      a1[3] = v131;
      ii = (wchar_t *)CertDiagStrMemAlloc(a1, &pcbData);
      if ( !ii )
        goto LABEL_59;
      v57 = pcbData;
    }
    --v57;
    *ii = v59;
    --v56;
    ++v55;
  }
  a1[3] = a1[2] - v57;
LABEL_59:
  v60 = v152;
  v158 = 0;
  v159 = 5;
  v160 = 0;
  pcbData = v152->TrustStatus.dwErrorStatus;
  *(_QWORD *)Buffer = &pcbData;
  v157 = L"value";
  v166 = &qword_1801207A0;
  v161 = 0;
  v162 = 0;
  v163 = 3;
  v164 = 15;
  v165 = 0;
  CertDiagXmlFormatElement(a1);
  pcbData = v60->TrustStatus.dwInfoStatus;
  v159 = 5;
  *(_QWORD *)Buffer = &pcbData;
  v163 = 3;
  v157 = L"value";
  v164 = 15;
  v158 = 0;
  v160 = 0;
  v161 = 0;
  v162 = 0;
  v165 = 0;
  v166 = &qword_180120610;
  CertDiagXmlFormatElement(a1);
  v61 = (unsigned int)a1[3];
  v62 = L"</";
  v63 = -1;
  v64 = a1[2] - v61;
  for ( jj = (wchar_t *)(*(_QWORD *)a1 + 2 * v61); v63; ++jj )
  {
    v66 = *v62;
    if ( !*v62 )
      break;
    if ( !v64 )
    {
      v132 = a1[2];
      pcbData = 128;
      a1[3] = v132;
      jj = (wchar_t *)CertDiagStrMemAlloc(a1, &pcbData);
      if ( !jj )
        goto LABEL_65;
      v64 = pcbData;
    }
    *jj = v66;
    --v64;
    --v63;
    ++v62;
  }
  a1[3] = a1[2] - v64;
LABEL_65:
  v67 = (unsigned int)a1[3];
  v68 = -1;
  v69 = a1[2] - v67;
  for ( kk = (wchar_t *)(*(_QWORD *)a1 + 2 * v67); v68; ++kk )
  {
    v71 = *v48;
    if ( !*v48 )
      break;
    if ( !v69 )
    {
      v133 = a1[2];
      pcbData = 128;
      a1[3] = v133;
      kk = (wchar_t *)CertDiagStrMemAlloc(a1, &pcbData);
      if ( !kk )
        goto LABEL_71;
      v69 = pcbData;
    }
    *kk = v71;
    --v69;
    --v68;
    ++v48;
  }
  a1[3] = a1[2] - v69;
LABEL_71:
  v72 = (unsigned int)a1[3];
  v73 = -1;
  v74 = L">";
  v75 = a1[2] - v72;
  for ( mm = (wchar_t *)(*(_QWORD *)a1 + 2 * v72); v73; ++mm )
  {
    v77 = *v74;
    if ( !*v74 )
      break;
    if ( !v75 )
    {
      v134 = a1[2];
      pcbData = 128;
      a1[3] = v134;
      mm = (wchar_t *)CertDiagStrMemAlloc(a1, &pcbData);
      if ( !mm )
        goto LABEL_77;
      v75 = pcbData;
    }
    *mm = v77;
    --v75;
    --v73;
    ++v74;
  }
  a1[3] = a1[2] - v75;
LABEL_77:
  pApplicationUsage = v60->pApplicationUsage;
  p_pszObjId = &hMem;
  LODWORD(pwszName) = 0;
  p_pwszName = (HLOCAL *)&pwszName;
  LODWORD(hMem) = 0;
  CertDiagXmlFormatElement(a1);
  v79 = L"/>";
  if ( pApplicationUsage )
  {
    v80 = (unsigned int)a1[3];
    v81 = -1;
    v82 = a1[2] - v80;
    v83 = (wchar_t *)(*(_QWORD *)a1 + 2 * v80);
    v84 = v82;
    if ( pApplicationUsage->cUsageIdentifier )
    {
      for ( nn = L">"; v81; ++nn )
      {
        v86 = *nn;
        if ( !*nn )
          break;
        if ( !v84 )
        {
          v141 = a1[2];
          pcbData = 128;
          a1[3] = v141;
          v83 = (wchar_t *)CertDiagStrMemAlloc(a1, &pcbData);
          if ( !v83 )
            goto LABEL_85;
          v82 = pcbData;
        }
        --v82;
        *v83++ = v86;
        --v81;
        v84 = v82;
      }
      a1[3] = a1[2] - v84;
LABEL_85:
      for ( i1 = 0; i1 < pApplicationUsage->cUsageIdentifier; ++i1 )
      {
        rgpszUsageIdentifier = pApplicationUsage->rgpszUsageIdentifier;
        pcbData = 0;
        *(_QWORD *)Buffer = 0;
        p_pszObjId = rgpszUsageIdentifier[i1];
        v89 = CryptFindOIDInfo(1u, p_pszObjId, 0x80000000);
        if ( v89 )
          *(_QWORD *)Buffer = v89->pwszName;
        p_pcbData = &pcbData;
        p_p_pszObjId = (void **)&p_pszObjId;
        v169 = Buffer;
        CertDiagXmlFormatElement(a1);
      }
      CertDiagXmlAppendEndElementName(a1, L"ApplicationUsage");
    }
    else
    {
      for ( i2 = L"/>"; v81; ++i2 )
      {
        v139 = *i2;
        if ( !*i2 )
          break;
        if ( !v84 )
        {
          v143 = a1[2];
          pcbData = 128;
          a1[3] = v143;
          v83 = (wchar_t *)CertDiagStrMemAlloc(a1, &pcbData);
          if ( !v83 )
            goto LABEL_90;
          v82 = pcbData;
        }
        --v82;
        *v83++ = v139;
        --v81;
        v84 = v82;
      }
      a1[3] = a1[2] - v84;
    }
  }
  else
  {
    CertDiagXmlFormatElement(a1);
  }
LABEL_90:
  v90 = v152;
  p_pszObjId = &pwszName;
  LODWORD(hMem) = 0;
  p_pwszName = &hMem;
  pIssuanceUsage = v152->pIssuanceUsage;
  LODWORD(pwszName) = 0;
  CertDiagXmlFormatElement(a1);
  if ( !pIssuanceUsage )
  {
    CertDiagXmlFormatElement(a1);
LABEL_125:
    v97 = L">";
    goto LABEL_103;
  }
  v92 = (unsigned int)a1[3];
  v93 = -1;
  v94 = a1[2] - v92;
  v95 = (wchar_t *)(*(_QWORD *)a1 + 2 * v92);
  v96 = v94;
  if ( !pIssuanceUsage->cUsageIdentifier )
  {
    while ( v93 )
    {
      v140 = *v79;
      if ( !*v79 )
        break;
      if ( !v96 )
      {
        v144 = a1[2];
        pcbData = 128;
        a1[3] = v144;
        v95 = (wchar_t *)CertDiagStrMemAlloc(a1, &pcbData);
        if ( !v95 )
          goto LABEL_125;
        v94 = pcbData;
      }
      --v94;
      *v95++ = v140;
      --v93;
      ++v79;
      v96 = v94;
    }
    a1[3] = a1[2] - v96;
    goto LABEL_125;
  }
  v97 = L">";
  for ( i3 = L">"; v93; ++i3 )
  {
    v99 = *i3;
    if ( !*i3 )
      break;
    if ( !v96 )
    {
      v142 = a1[2];
      pcbData = 128;
      a1[3] = v142;
      v95 = (wchar_t *)CertDiagStrMemAlloc(a1, &pcbData);
      if ( !v95 )
        goto LABEL_98;
      v94 = pcbData;
    }
    *v95 = v99;
    --v94;
    ++v95;
    --v93;
    v96 = v94;
  }
  a1[3] = a1[2] - v96;
LABEL_98:
  for ( i4 = 0; i4 < pIssuanceUsage->cUsageIdentifier; ++i4 )
  {
    v101 = pIssuanceUsage->rgpszUsageIdentifier;
    pcbData = 0;
    *(_QWORD *)Buffer = 0;
    p_pszObjId = v101[i4];
    v102 = CryptFindOIDInfo(1u, p_pszObjId, 0x80000000);
    if ( v102 )
      *(_QWORD *)Buffer = v102->pwszName;
    p_pcbData = &pcbData;
    p_p_pszObjId = (void **)&p_pszObjId;
    v169 = Buffer;
    CertDiagXmlFormatElement(a1);
  }
  CertDiagXmlAppendEndElementName(a1, L"IssuanceUsage");
  v90 = v152;
LABEL_103:
  if ( v90->pRevocationInfo )
  {
    *(_QWORD *)Buffer = v90->pRevocationInfo;
    CertDiagXmlFormatElement(a1);
    v120 = *(_QWORD *)Buffer;
    v121 = 0;
    v152 = 0;
    v122 = *(_DWORD *)(*(_QWORD *)Buffer + 4LL);
    LODWORD(pwszName) = v122;
    if ( v122 )
    {
      *(_QWORD *)Buffer = 0;
      FormatMessageW(0x1100u, 0, v122, 0x400u, Buffer, 0, 0);
      v121 = *(void **)Buffer;
      v152 = *(struct _CERT_CHAIN_ELEMENT **)Buffer;
      if ( *(_QWORD *)Buffer )
        CertDiagPrvRemoveControlCharacters(*(unsigned __int16 **)Buffer);
    }
    p_pszObjId = &pwszName;
    p_pwszName = (HLOCAL *)&v152;
    CertDiagXmlFormatElement(a1);
    if ( v121 )
      LocalFree(v121);
    v123 = *(struct _CERT_REVOCATION_CRL_INFO **)(v120 + 32);
    if ( v123 )
    {
      pBaseCrlContext = (const CERT_CONTEXT *)v123->pBaseCrlContext;
      if ( pBaseCrlContext )
        CertDiagPrvXmlFormatCrlStrongSignPropertiesElement(a1, pBaseCrlContext, 0);
      pDeltaCrlContext = (const CERT_CONTEXT *)v123->pDeltaCrlContext;
      if ( pDeltaCrlContext )
        CertDiagPrvXmlFormatCrlStrongSignPropertiesElement(a1, pDeltaCrlContext, 1);
      CertDiagPrvXmlFormatRevocationCrlInfoElements(a1, v123, v156);
    }
    CertDiagXmlAppendEndElementName(a1, L"RevocationInfo");
  }
  pwszExtendedErrorInfo = v90->pwszExtendedErrorInfo;
  if ( pwszExtendedErrorInfo )
  {
    v145 = (struct _CERT_CONTEXT *)ILS_AllocAndCopyString(pwszExtendedErrorInfo, -1);
    if ( v145 )
    {
      for ( i5 = 0; *((_WORD *)&v145->dwCertEncodingType + i5); ++i5 )
      {
        if ( *((_WORD *)&v145->dwCertEncodingType + i5) == 13 )
        {
          *((_WORD *)&v145->dwCertEncodingType + i5) = 44;
        }
        else if ( *((_WORD *)&v145->dwCertEncodingType + i5) == 10 )
        {
          if ( !*((_WORD *)&v145->dwCertEncodingType + i5 + 1) )
          {
            if ( i5 && (v147 = i5 - 1, *((_WORD *)&v145->dwCertEncodingType + v147) == 44) )
              *((_WORD *)&v145->dwCertEncodingType + v147) = 0;
            else
              *((_WORD *)&v145->dwCertEncodingType + i5) = 0;
            break;
          }
          *((_WORD *)&v145->dwCertEncodingType + i5) = 32;
        }
      }
      v156 = v145;
      p_pszObjId = &v156;
      CertDiagXmlFormatElement(a1);
      PkiDefaultCryptFree(v145);
    }
  }
  v104 = (unsigned int)a1[3];
  v105 = L"</";
  v106 = -1;
  v107 = a1[2] - v104;
  for ( i6 = (wchar_t *)(*(_QWORD *)a1 + 2 * v104); v106; ++i6 )
  {
    v109 = *v105;
    if ( !*v105 )
      break;
    if ( !v107 )
    {
      v135 = a1[2];
      pcbData = 128;
      a1[3] = v135;
      i6 = (wchar_t *)CertDiagStrMemAlloc(a1, &pcbData);
      if ( !i6 )
        goto LABEL_111;
      v107 = pcbData;
    }
    *i6 = v109;
    --v107;
    --v106;
    ++v105;
  }
  a1[3] = a1[2] - v107;
LABEL_111:
  v110 = (unsigned int)a1[3];
  v111 = L"ChainElement";
  v112 = -1;
  v113 = a1[2] - v110;
  for ( i7 = (wchar_t *)(*(_QWORD *)a1 + 2 * v110); v112; ++i7 )
  {
    v115 = *v111;
    if ( !*v111 )
      break;
    if ( !v113 )
    {
      v136 = a1[2];
      pcbData = 128;
      a1[3] = v136;
      i7 = (wchar_t *)CertDiagStrMemAlloc(a1, &pcbData);
      if ( !i7 )
        goto LABEL_117;
      v113 = pcbData;
    }
    *i7 = v115;
    --v113;
    --v112;
    ++v111;
  }
  a1[3] = a1[2] - v113;
LABEL_117:
  v116 = (unsigned int)a1[3];
  v117 = a1[2] - v116;
  for ( i8 = (wchar_t *)(*(_QWORD *)a1 + 2 * v116); v7; ++i8 )
  {
    v119 = *v97;
    if ( !*v97 )
      break;
    if ( !v117 )
    {
      v137 = a1[2];
      pcbData = 128;
      a1[3] = v137;
      i8 = (wchar_t *)CertDiagStrMemAlloc(a1, &pcbData);
      if ( !i8 )
        return;
      v117 = pcbData;
    }
    *i8 = v119;
    --v117;
    --v7;
    ++v97;
  }
  a1[3] = a1[2] - v117;
}

```

## disassembly

```asm
0x18000ac20  push    rbp
0x18000ac22  push    rbx
0x18000ac23  push    rsi
0x18000ac24  push    rdi
0x18000ac25  push    r12
0x18000ac27  push    r13
0x18000ac29  push    r14
0x18000ac2b  push    r15
0x18000ac2d  lea     rbp, [rsp-1Fh]
0x18000ac32  sub     rsp, 0F8h
0x18000ac39  mov     rdi, rcx
0x18000ac3c  mov     [rbp+57h+var_D0], rdx
0x18000ac40  mov     ecx, [rcx+0Ch]
0x18000ac43  lea     r12, asc_1801302B0; "<"
0x18000ac4a  or      r13d, 0FFFFFFFFh
0x18000ac4e  mov     [rbp+57h+var_B0], r9
0x18000ac52  mov     r15, r8
0x18000ac55  mov     ebx, r13d
0x18000ac58  mov     rax, [rdi]
0x18000ac5b  mov     rsi, r12
0x18000ac5e  mov     edx, [rdi+8]
0x18000ac61  sub     edx, ecx
0x18000ac63  lea     r8, [rax+rcx*2]
0x18000ac67  mov     ecx, edx
0x18000ac69  test    ebx, ebx
0x18000ac6b  jz      short loc_18000AC94
0x18000ac6d  movzx   r14d, word ptr [rsi]
0x18000ac71  xor     eax, eax
0x18000ac73  cmp     ax, r14w
0x18000ac77  jz      short loc_18000AC94
0x18000ac79  cmp     edx, 1
0x18000ac7c  jb      loc_18000B6C4
0x18000ac82  dec     edx
0x18000ac84  mov     [r8], r14w
0x18000ac88  dec     ebx
0x18000ac8a  add     rsi, 2
0x18000ac8e  add     r8, 2
0x18000ac92  jmp     short loc_18000AC67
0x18000ac94  mov     eax, [rdi+8]
0x18000ac97  sub     eax, ecx
0x18000ac99  mov     [rdi+0Ch], eax
0x18000ac9c  mov     ecx, [rdi+0Ch]
0x18000ac9f  lea     rsi, aChainelement; "ChainElement"
0x18000aca6  mov     rax, [rdi]
0x18000aca9  mov     ebx, r13d
0x18000acac  mov     edx, [rdi+8]
0x18000acaf  sub     edx, ecx
0x18000acb1  lea     r8, [rax+rcx*2]
0x18000acb5  mov     ecx, edx
0x18000acb7  test    ebx, ebx
0x18000acb9  jz      short loc_18000ACE2
0x18000acbb  movzx   r14d, word ptr [rsi]
0x18000acbf  xor     eax, eax
0x18000acc1  cmp     ax, r14w
0x18000acc5  jz      short loc_18000ACE2
0x18000acc7  cmp     edx, 1
0x18000acca  jb      loc_18000B6F6
0x18000acd0  dec     edx
0x18000acd2  mov     [r8], r14w
0x18000acd6  dec     ebx
0x18000acd8  add     rsi, 2
0x18000acdc  add     r8, 2
0x18000ace0  jmp     short loc_18000ACB5
0x18000ace2  mov     eax, [rdi+8]
0x18000ace5  sub     eax, ecx
0x18000ace7  mov     [rdi+0Ch], eax
0x18000acea  mov     ecx, [rdi+0Ch]
0x18000aced  lea     rsi, asc_180130284; ">"
0x18000acf4  mov     rax, [rdi]
0x18000acf7  mov     ebx, r13d
0x18000acfa  mov     edx, [rdi+8]
0x18000acfd  sub     edx, ecx
0x18000acff  lea     r8, [rax+rcx*2]
0x18000ad03  mov     ecx, edx
0x18000ad05  test    ebx, ebx
0x18000ad07  jz      short loc_18000AD30
0x18000ad09  movzx   r14d, word ptr [rsi]
0x18000ad0d  xor     eax, eax
0x18000ad0f  cmp     ax, r14w
0x18000ad13  jz      short loc_18000AD30
0x18000ad15  cmp     edx, 1
0x18000ad18  jb      loc_18000B728
0x18000ad1e  dec     edx
0x18000ad20  mov     [r8], r14w
0x18000ad24  dec     ebx
0x18000ad26  add     rsi, 2
0x18000ad2a  add     r8, 2
0x18000ad2e  jmp     short loc_18000AD03
0x18000ad30  mov     eax, [rdi+8]
0x18000ad33  sub     eax, ecx
0x18000ad35  mov     [rdi+0Ch], eax
0x18000ad38  mov     r14, [rbp+57h+var_D0]
0x18000ad3c  xor     edx, edx
0x18000ad3e  mov     rcx, rdi; void *
0x18000ad41  mov     r8, [r14+8]
0x18000ad45  call    CertDiagXmlFormatCertificateRefElement
0x18000ad4a  test    r15, r15
0x18000ad4d  jnz     loc_18000BA6F
0x18000ad53  mov     rsi, [r14+8]
0x18000ad57  test    rsi, rsi
0x18000ad5a  jz      loc_18000AF3B
0x18000ad60  mov     rax, [rsi+18h]
0x18000ad64  lea     r9, [rsp+130h+pcbData]; pcbData
0x18000ad69  add     rax, 18h
0x18000ad6d  mov     [rsp+130h+hMem], 0
0x18000ad76  mov     [rbp+57h+var_C8], rax
0x18000ad7a  xor     ebx, ebx
0x18000ad7c  lea     rax, [rsp+130h+var_E8]
0x18000ad81  mov     [rsp+130h+var_E8], 0
0x18000ad8a  mov     [rbp+57h+var_C0], rax
0x18000ad8e  xor     r8d, r8d; pvData
0x18000ad91  lea     rax, [rsp+130h+hMem]
0x18000ad96  mov     [rsp+130h+pcbData], ebx
0x18000ad9a  lea     edx, [rbx+59h]; dwPropId
0x18000ad9d  mov     [rbp+57h+var_B8], rax
0x18000ada1  mov     rcx, rsi; pCertContext
0x18000ada4  call    CertGetCertificateContextProperty
0x18000ada9  xor     r15d, r15d
0x18000adac  test    eax, eax
0x18000adae  jz      loc_18000AE3D
0x18000adb4  mov     r8d, [rsp+130h+pcbData]
0x18000adb9  test    r8d, r8d
0x18000adbc  jz      short loc_18000AE3D
0x18000adbe  lea     eax, [r8+4]
0x18000adc2  cmp     eax, r8d
0x18000adc5  jb      short loc_18000AE3D
0x18000adc7  lea     rcx, [r8+4]; uBytes
0x18000adcb  call    PkiNonzeroAlloc
0x18000add0  mov     rbx, rax
0x18000add3  test    rax, rax
0x18000add6  jz      short loc_18000AE51
0x18000add8  lea     r9, [rsp+130h+pcbData]; pcbData
0x18000addd  mov     r8, rax; pvData
0x18000ade0  lea     edx, [r15+59h]; dwPropId
0x18000ade4  mov     rcx, rsi; pCertContext
0x18000ade7  call    CertGetCertificateContextProperty
0x18000adec  test    eax, eax
0x18000adee  jz      short loc_18000AE3D
0x18000adf0  mov     eax, [rsp+130h+pcbData]
0x18000adf4  test    eax, eax
0x18000adf6  jz      short loc_18000AE3D
0x18000adf8  xor     ecx, ecx
0x18000adfa  mov     [rax+rbx], ecx
0x18000adfd  mov     [rsp+130h+hMem], rbx
0x18000ae02  mov     [rsp+130h+var_E8], rbx
0x18000ae07  movzx   ecx, word ptr [rbx]
0x18000ae0a  cmp     r15w, cx
0x18000ae0e  jz      short loc_18000AE36
0x18000ae10  mov     rdx, rbx
0x18000ae13  mov     eax, 2Fh ; '/'
0x18000ae18  cmp     ax, cx
0x18000ae1b  jz      loc_18000BA58
0x18000ae21  lea     rbx, [rdx+2]
0x18000ae25  mov     [rsp+130h+var_E8], rbx
0x18000ae2a  mov     rdx, rbx
0x18000ae2d  movzx   ecx, word ptr [rbx]
0x18000ae30  cmp     r15w, cx
0x18000ae34  jnz     short loc_18000AE13
0x18000ae36  mov     [rsp+130h+var_E8], r15
0x18000ae3b  jmp     short loc_18000AE56
0x18000ae3d  mov     ecx, 80092004h; dwErrCode
0x18000ae42  call    cs:__imp_SetLastError
0x18000ae48  test    rbx, rbx
0x18000ae4b  jnz     loc_18000BA89
0x18000ae51  mov     [rsp+130h+hMem], rbx
0x18000ae56  lea     r9, [rbp+57h+var_C8]
0x18000ae5a  mov     rcx, rdi; void *
0x18000ae5d  lea     r8, off_180123510; "oid"
0x18000ae64  lea     rdx, aSignaturealgor; "SignatureAlgorithm"
0x18000ae6b  call    CertDiagXmlFormatElement
0x18000ae70  mov     rsi, [rsp+130h+hMem]
0x18000ae75  test    rsi, rsi
0x18000ae78  jz      short loc_18000AE93
0x18000ae7a  call    cs:__imp_GetLastError
0x18000ae80  mov     rcx, rsi; hMem
0x18000ae83  mov     ebx, eax
0x18000ae85  call    cs:__imp_LocalFree
0x18000ae8b  mov     ecx, ebx; dwErrCode
0x18000ae8d  call    cs:__imp_SetLastError
0x18000ae93  mov     rax, [r14+8]
0x18000ae97  mov     ecx, 10001h; dwCertEncodingType
0x18000ae9c  mov     [rsp+130h+var_E8], r15
0x18000aea1  mov     rsi, [rax+18h]
0x18000aea5  add     rsi, 60h ; '`'
0x18000aea9  mov     rdx, rsi; pPublicKey
0x18000aeac  call    CertGetPublicKeyLength
0x18000aeb1  mov     rdx, [rsi]; pvKey
0x18000aeb4  mov     r8d, 0C0000003h; dwGroupId
0x18000aeba  mov     ecx, 1; dwKeyType
0x18000aebf  mov     [rsp+130h+pcbData], eax
0x18000aec3  call    CryptFindOIDInfo
0x18000aec8  mov     rbx, rax
0x18000aecb  test    rax, rax
0x18000aece  jz      short loc_18000AF0B
0x18000aed0  mov     r8, [rax+30h]; lpString1
0x18000aed4  mov     [rsp+130h+var_E8], r8
0x18000aed9  test    r8, r8
0x18000aedc  jz      short loc_18000AF0B
0x18000aede  lea     rax, String2; "CryptOIDInfoECCParameters"
0x18000aee5  mov     [rsp+130h+cchCount2], r13d; cchCount2
0x18000aeea  mov     r9d, r13d; cchCount1
0x18000aeed  mov     [rsp+130h+lpString2], rax; lpString2
0x18000aef2  mov     edx, 1; dwCmpFlags
0x18000aef7  mov     ecx, 409h; Locale
0x18000aefc  call    cs:__imp_CompareStringW
0x18000af02  cmp     eax, 2
0x18000af05  jz      loc_18000B6B6
0x18000af0b  lea     rax, [rsp+130h+var_E8]
0x18000af10  mov     [rbp+57h+var_C8], rsi
0x18000af14  mov     [rbp+57h+var_C0], rax
0x18000af18  lea     r9, [rbp+57h+var_C8]
0x18000af1c  lea     rax, [rsp+130h+pcbData]
0x18000af21  mov     rcx, rdi; void *
0x18000af24  lea     r8, off_180121E70; "oid"
0x18000af2b  mov     [rbp+57h+var_B8], rax
0x18000af2f  lea     rdx, aPublickeyalgor; "PublicKeyAlgorithm"
0x18000af36  call    CertDiagXmlFormatElement
0x18000af3b  mov     ecx, [rdi+0Ch]
0x18000af3e  mov     ebx, r13d
0x18000af41  mov     rax, [rdi]
0x18000af44  mov     edx, [rdi+8]
0x18000af47  sub     edx, ecx
0x18000af49  lea     r8, [rax+rcx*2]
0x18000af4d  mov     ecx, edx
0x18000af4f  test    ebx, ebx
0x18000af51  jz      short loc_18000AF7A
0x18000af53  movzx   esi, word ptr [r12]
0x18000af58  xor     eax, eax
0x18000af5a  cmp     ax, si
0x18000af5d  jz      short loc_18000AF7A
0x18000af5f  cmp     edx, 1
0x18000af62  jb      loc_18000B75A
0x18000af68  dec     edx
0x18000af6a  mov     [r8], si
0x18000af6e  dec     ebx
0x18000af70  add     r12, 2
0x18000af74  add     r8, 2
0x18000af78  jmp     short loc_18000AF4D
0x18000af7a  mov     eax, [rdi+8]
0x18000af7d  sub     eax, ecx
0x18000af7f  mov     [rdi+0Ch], eax
0x18000af82  mov     ecx, [rdi+0Ch]
0x18000af85  lea     r15, aTruststatus; "TrustStatus"
0x18000af8c  mov     rax, [rdi]
0x18000af8f  mov     ebx, r13d
0x18000af92  mov     edx, [rdi+8]
0x18000af95  mov     rsi, r15
0x18000af98  sub     edx, ecx
0x18000af9a  or      r12d, 0FFFFFFFFh
0x18000af9e  lea     r8, [rax+rcx*2]
0x18000afa2  mov     ecx, edx
0x18000afa4  test    ebx, ebx
0x18000afa6  jz      short loc_18000AFD0
0x18000afa8  movzx   r14d, word ptr [rsi]
0x18000afac  xor     eax, eax
0x18000afae  cmp     ax, r14w
0x18000afb2  jz      short loc_18000AFD0
0x18000afb4  cmp     edx, 1
0x18000afb7  jb      loc_18000B78C
0x18000afbd  add     edx, r12d
0x18000afc0  mov     [r8], r14w
0x18000afc4  dec     ebx
0x18000afc6  add     rsi, 2
0x18000afca  add     r8, 2
0x18000afce  jmp     short loc_18000AFA2
0x18000afd0  mov     eax, [rdi+8]
0x18000afd3  sub     eax, ecx
0x18000afd5  mov     [rdi+0Ch], eax
0x18000afd8  mov     ecx, [rdi+0Ch]
0x18000afdb  lea     rsi, asc_180130284; ">"
0x18000afe2  mov     rax, [rdi]
0x18000afe5  mov     ebx, r13d
0x18000afe8  mov     edx, [rdi+8]
0x18000afeb  sub     edx, ecx
0x18000afed  lea     r8, [rax+rcx*2]
0x18000aff1  mov     ecx, edx
0x18000aff3  test    ebx, ebx
0x18000aff5  jz      short loc_18000B01F
0x18000aff7  movzx   r14d, word ptr [rsi]
0x18000affb  xor     eax, eax
0x18000affd  cmp     ax, r14w
0x18000b001  jz      short loc_18000B01F
0x18000b003  cmp     edx, 1
0x18000b006  jb      loc_18000B7BE
0x18000b00c  add     edx, r12d
0x18000b00f  mov     [r8], r14w
0x18000b013  dec     ebx
0x18000b015  add     rsi, 2
0x18000b019  add     r8, 2
0x18000b01d  jmp     short loc_18000AFF1
0x18000b01f  mov     eax, [rdi+8]
0x18000b022  sub     eax, ecx
0x18000b024  mov     [rdi+0Ch], eax
0x18000b027  mov     r12, [rbp+57h+var_D0]
0x18000b02b  lea     r9, [rsp+130h+Buffer]
0x18000b030  mov     esi, 3
0x18000b035  mov     [rbp+57h+var_98], 0
0x18000b03c  lea     r8, [rbp+57h+var_A0]
0x18000b040  mov     [rbp+57h+var_94], 5
0x18000b048  lea     rdx, aErrorstatus; "ErrorStatus"
  ... truncated ...
```
