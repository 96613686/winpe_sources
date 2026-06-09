# I_CertSelectCertificateChains2

- ea: `0x180067020`
- end: `0x180067b0f`
- name: `I_CertSelectCertificateChains2`
- size: `2799`
- prototype: `__int64 __fastcall(int, int, int, int, __int64, HCERTSTORE hCertStore, __int64, __int64, __int64)`
- caller_count: `2`
- callee_count: `24`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180068280`
- `0x180068b04`

## callees

- `0x180015a30`
- `0x18001aec0`
- `0x18001b57c`
- `0x180044e60`
- `0x1800450c0`
- `0x180066a48`
- `0x180066ba4`
- `0x180067020`
- `0x180067b20`
- `0x180067c14`
- `0x180068224`
- `0x180068330`
- `0x18006859c`
- `0x18006890c`
- `0x180068940`
- `0x1800b6774`
- `0x1800bec20`
- `0x1800bf5e8`
- `0x1800bf63c`
- `0x180113dc8`
- `0x18011416c`
- `0x180114264`
- `0x180115094`
- `0x18011f010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800671ba`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800671ba`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800674c7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800674c7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006746f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180067479`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180067840`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180067ad0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180067ade`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180067af6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006746f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180067479`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180067840`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180067ad0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180067ade`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180067af6`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18006722b`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180067452`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18011a2cd`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18006722b`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180067452`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18011a2cd`
- `api-ms-win-core-heap-l2-1-0!LocalReAlloc` at `0x18011a2de`
- `api-ms-win-core-heap-l2-1-0!LocalReAlloc` at `0x18011a2de`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180067b04`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180067b04`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180067197`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180067197`
- `RPCRT4!UuidCreate` at `0x180067691`
- `RPCRT4!UuidCreate` at `0x180067691`

## string_xrefs

- `0x18006717f`: `ncrypt.dll`

## pseudocode

```c
__int64 __fastcall I_CertSelectCertificateChains2(
        __int64 a1,
        unsigned int a2,
        __int64 a3,
        unsigned int a4,
        _DWORD *a5,
        struct _FILETIME *hCertStore,
        _DWORD *a7,
        _QWORD *a8,
        __int128 *a9)
{
  _DWORD *v9; // r14
  LPFILETIME v10; // r13
  unsigned int v11; // edi
  BOOL v13; // r12d
  int v14; // r8d
  __int64 v15; // rdx
  __int64 v16; // rcx
  HCERTSTORE v17; // r15
  HCERTCHAINENGINE v18; // rbx
  unsigned int v19; // r14d
  struct _CERT_CONTEXT *v20; // rdi
  PCCERT_CONTEXT v21; // rax
  DWORD LastError; // eax
  DWORD updated; // ebx
  unsigned int v24; // r15d
  int v25; // r13d
  int v26; // edi
  unsigned int v27; // eax
  unsigned int v28; // ecx
  unsigned int v29; // eax
  unsigned int v30; // edx
  unsigned int v31; // ecx
  __int64 v32; // rax
  SIZE_T v33; // rbx
  char *v34; // rax
  unsigned int *v35; // r11
  _DWORD *v36; // rsi
  __int64 *v37; // rdx
  char *v38; // rcx
  unsigned int j; // r10d
  struct _CERT_CHAIN_PARA *pChainPara; // r15
  DWORD dwFlags; // r14d
  unsigned int v42; // r12d
  void *v43; // rsi
  PCCERT_CONTEXT *v44; // rdi
  HCERTCHAINENGINE v45; // r13
  int v46; // eax
  unsigned int v47; // esi
  unsigned int *v48; // rbx
  unsigned int (__fastcall *v49)(PCCERT_CONTEXT *, _QWORD, _QWORD, char *); // rax
  int v50; // ecx
  unsigned int v51; // esi
  unsigned int *v52; // rbx
  int v53; // ecx
  unsigned int (__fastcall *v54)(PCCERT_CONTEXT *, _QWORD, _QWORD, char *); // rax
  unsigned int v55; // r15d
  _QWORD *v56; // r12
  HLOCAL v57; // r13
  void *v58; // r14
  const CERT_CONTEXT *v60; // rsi
  BOOL v61; // r13d
  __int128 v62; // xmm0
  __int128 v63; // xmm6
  __m128i v64; // xmm7
  __int64 v65; // rdx
  void *v66; // rsi
  __int64 v67; // rdx
  HCERTSTORE v68; // r13
  int v69; // eax
  const unsigned __int16 *v70; // rsi
  const unsigned __int16 *v71; // r14
  __int64 v72; // rdi
  char v73; // al
  struct SelectionContext *v74; // rbx
  unsigned int v75; // r15d
  unsigned int v76; // eax
  char v77; // r14
  unsigned int KeyPriority; // eax
  __int64 k; // rdx
  PCCERT_CONTEXT *v80; // rbx
  unsigned int i; // r15d
  const struct _CERT_CONTEXT *v82; // r13
  unsigned int v83; // r9d
  _DWORD *v84; // r8
  unsigned int v85; // esi
  char *m; // rdi
  struct _INTERNAL_CERT_CHAIN_CONTEXT *v87; // rcx
  void *v88; // rcx
  int v89; // esi
  unsigned int v90; // edi
  unsigned int v91; // eax
  __int64 v92; // rbx
  unsigned int v93; // r14d
  __int64 v94; // rax
  SIZE_T v95; // rdx
  _QWORD *v96; // rax
  _QWORD *v97; // r9
  __int64 v98; // rcx
  rsize_t NumOfElements; // [rsp+48h] [rbp-C0h] BYREF
  __int64 v100; // [rsp+50h] [rbp-B8h]
  HLOCAL hMem; // [rsp+58h] [rbp-B0h] BYREF
  unsigned int v102; // [rsp+60h] [rbp-A8h]
  __int64 v103; // [rsp+68h] [rbp-A0h] BYREF
  __int64 v104; // [rsp+70h] [rbp-98h]
  __int64 v105; // [rsp+78h] [rbp-90h] BYREF
  void *Base; // [rsp+80h] [rbp-88h]
  LPFILETIME pTime; // [rsp+88h] [rbp-80h]
  HCERTSTORE hAdditionalStore; // [rsp+90h] [rbp-78h]
  int v109; // [rsp+98h] [rbp-70h]
  int v110; // [rsp+9Ch] [rbp-6Ch]
  HCERTCHAINENGINE hChainEngine; // [rsp+A0h] [rbp-68h]
  HCERTSTORE v112; // [rsp+A8h] [rbp-60h]
  PCCERT_CHAIN_CONTEXT ppChainContext; // [rsp+B0h] [rbp-58h] BYREF
  unsigned int v114; // [rsp+B8h] [rbp-50h]
  int v115; // [rsp+BCh] [rbp-4Ch]
  HLOCAL v116; // [rsp+C0h] [rbp-48h]
  HLOCAL v117; // [rsp+C8h] [rbp-40h] BYREF
  HLOCAL v118; // [rsp+D0h] [rbp-38h] BYREF
  __int64 v119; // [rsp+D8h] [rbp-30h]
  HCERTSTORE v120[2]; // [rsp+E0h] [rbp-28h] BYREF
  HCERTSTORE v121[2]; // [rsp+F0h] [rbp-18h]
  __int64 v122; // [rsp+100h] [rbp-8h]
  HMODULE hLibModule; // [rsp+108h] [rbp+0h]
  _DWORD *v124; // [rsp+110h] [rbp+8h]
  _QWORD *v125; // [rsp+118h] [rbp+10h]
  _DWORD v126[6]; // [rsp+128h] [rbp+20h] BYREF
  __int64 v127; // [rsp+140h] [rbp+38h]
  UUID Uuid; // [rsp+188h] [rbp+80h] BYREF
  _BYTE Context[40]; // [rsp+198h] [rbp+90h] BYREF
  _OWORD v130[2]; // [rsp+1C0h] [rbp+B8h] BYREF
  int v131; // [rsp+1E0h] [rbp+D8h]

  v9 = a5;
  v10 = hCertStore;
  v11 = a2;
  v124 = a7;
  v119 = a3;
  v102 = a2;
  v114 = a4;
  LODWORD(v103) = a4;
  hAdditionalStore = a5;
  pTime = hCertStore;
  v125 = a8;
  NumOfElements = 0;
  Base = 0;
  memset_0(v126, 0, 0x60u);
  ppChainContext = 0;
  v116 = 0;
  LODWORD(v105) = 0;
  v122 = 0;
  v13 = (v11 & 2) == 0;
  v118 = 0;
  hLibModule = 0;
  v117 = 0;
  hMem = 0;
  *(_OWORD *)v120 = 0;
  *(_OWORD *)v121 = 0;
  memset(Context, 0, sizeof(Context));
  if ( !hCertStore || a4 > 0x21 || (v11 & 0xFFFFFE00) != 0 )
  {
    updated = 87;
    v55 = 0;
    goto LABEL_62;
  }
  v14 = 0;
  v15 = 0;
  v115 = 0;
  if ( a4 )
  {
    do
    {
      v16 = 2LL * (unsigned int)v15;
      v15 = (unsigned int)(v15 + 1);
      v14 |= 1 << a5[2 * v16];
    }
    while ( (unsigned int)v15 < a4 );
    v115 = v14;
  }
  if ( a9 )
  {
    v62 = *a9;
    v63 = a9[1];
    v64 = (__m128i)*((unsigned __int64 *)a9 + 4);
    v18 = (HCERTCHAINENGINE)*((_QWORD *)a9 + 1);
    v122 = *((_QWORD *)a9 + 4);
    *(_OWORD *)v120 = v62;
    *(_OWORD *)v121 = v63;
    v66 = (void *)v63;
    if ( (unsigned int)IsEmptyCertificateStore(v18, v15) )
      v18 = 0;
    hChainEngine = v18;
    v120[1] = v18;
    v68 = v121[1];
    if ( (unsigned int)IsEmptyCertificateStore(v63, v65) )
      v66 = 0;
    v112 = v66;
    v121[0] = v66;
    if ( (unsigned int)IsEmptyCertificateStore(v121[1], v67) )
      v68 = 0;
    v69 = _mm_cvtsi128_si32(v64);
    v121[1] = v68;
    if ( (v69 & 1) != 0 )
    {
      v11 |= 0x40u;
      v102 = v11;
    }
    if ( (v11 & 0x100) != 0 )
      LODWORD(v122) = v69 & 0xFFFFFFFD;
    if ( LODWORD(v120[0]) )
      v102 = v11 & 0xFFFFFF7F;
    if ( v68 )
    {
      v89 = 0;
      v90 = 0;
      if ( a4 )
      {
        do
        {
          if ( v9[4 * v90] == 1 )
          {
            v92 = 0;
            v93 = v9[4 * v90 + 1];
            v94 = *((_QWORD *)hAdditionalStore + 2 * v90 + 1);
            v104 = v94;
            while ( (unsigned int)v92 < v93 )
            {
              if ( !strcmp_0("1.3.6.1.5.5.7.3.2", *(const char **)(v94 + 8 * v92)) )
              {
                v89 = 1;
                break;
              }
              v94 = v104;
              v92 = (unsigned int)(v92 + 1);
            }
            v9 = hAdditionalStore;
          }
          ++v90;
        }
        while ( v90 < a4 );
        if ( v89 )
        {
          updated = UpdateCriteriaIssuerName(a4, v9, v68, &v103, &v118);
          if ( updated )
            goto LABEL_82;
          hAdditionalStore = v118;
          v114 = v103;
        }
        v18 = hChainEngine;
      }
    }
    v10 = pTime;
    v17 = v112;
  }
  else
  {
    v17 = v121[0];
    v18 = v120[1];
    v112 = v121[0];
    hChainEngine = v120[1];
  }
  LODWORD(v103) = 0;
  v110 = 0;
  v19 = 0;
  hLibModule = LoadLibraryExW(L"ncrypt.dll", 0, 0);
  v20 = 0;
  while ( 1 )
  {
    v21 = CertEnumCertificatesInStore(v10, v20);
    v20 = (struct _CERT_CONTEXT *)v21;
    if ( !v21 )
      break;
    LODWORD(v104) = v21->cbCertEncoded;
    v60 = CertDuplicateCRLContext(v21);
    if ( (unsigned int)IsCertificateInStore(v20, v18) )
      v61 = 0;
    else
      v61 = IsCertificateInStore(v20, v17) != 0;
    v109 = v61;
    if ( (v102 & 0x80u) != 0 )
      goto LABEL_78;
    v80 = (PCCERT_CONTEXT *)Base;
    for ( i = 0; ; ++i )
    {
      if ( i >= (unsigned int)NumOfElements )
      {
        v61 = v109;
LABEL_78:
        if ( !v60 )
          goto LABEL_79;
        v55 = NumOfElements;
        if ( (int)NumOfElements + 1 < v19 )
        {
          v97 = Base;
          goto LABEL_196;
        }
        if ( v19 )
          v19 *= 2;
        else
          v19 = 4;
        v95 = 40LL * v19;
        if ( Base )
          v96 = LocalReAlloc(Base, v95, 2u);
        else
          v96 = LocalAlloc(0, v95);
        if ( v96 )
        {
          v97 = v96;
          Base = v96;
LABEL_196:
          v98 = 5LL * (unsigned int)NumOfElements;
          LODWORD(NumOfElements) = NumOfElements + 1;
          v97[v98] = v60;
          v97[v98 + 1] = 0;
          v97[v98 + 2] = 0;
          LODWORD(v97[v98 + 3]) = 0;
          HIDWORD(v97[v98 + 3]) = v61;
          LODWORD(v97[v98 + 4]) = -1;
          goto LABEL_79;
        }
        updated = 8;
        CertFreeCertificateContext(v20);
        CertFreeCertificateContext(v60);
LABEL_62:
        v57 = hMem;
        goto LABEL_63;
      }
      v82 = *v80;
      if ( CertCompareCertificate(v20->dwCertEncodingType, v20->pCertInfo, (*v80)->pCertInfo) )
        goto LABEL_140;
      if ( v109 == *((_DWORD *)v80 + 7) && (unsigned int)EqualCerts(v20, v82, 0) )
        break;
      v80 += 5;
    }
    if ( (int)CompareCertTimeValidity(v20, v82) <= 0 )
    {
LABEL_140:
      CertFreeCertificateContext(v60);
    }
    else
    {
      CertFreeCertificateContext(*v80);
      *v80 = v60;
    }
LABEL_79:
    LODWORD(v103) = v103 + 1;
    v18 = hChainEngine;
    v17 = v112;
    v10 = pTime;
    v110 += v104;
  }
  LastError = GetLastError();
  updated = LastError;
  if ( LastError != -2146885628 && LastError != 18 )
  {
LABEL_82:
    v55 = NumOfElements;
    goto LABEL_62;
  }
  v24 = v114;
  v25 = 8;
  v26 = v102 ^ 1;
  v27 = v114 + 1;
  if ( (((unsigned __int8)v102 ^ 1) & 1) == 0 )
    v27 = v114;
  v28 = v27 + 1;
  if ( (v26 & 4) == 0 )
    v28 = v27;
  v29 = v28 + 1;
  if ( (v26 & 8) == 0 )
    v29 = v28;
  v30 = v29 + 1;
  if ( (v26 & 0x10) == 0 )
    v30 = v29;
  v31 = v30 + 1;
  if ( (v26 & 0x20) == 0 )
    v31 = v30;
  v32 = v31 + 1;
  if ( (v26 & 0x40) == 0 )
    v32 = v31;
  v104 = v32;
  v33 = 8LL * (unsigned int)v32;
  v34 = (char *)LocalAlloc(0, v33 * 4);
  v116 = v34;
  v35 = (unsigned int *)v34;
  if ( !v34 )
  {
    updated = 8;
    goto LABEL_82;
  }
  v36 = hAdditionalStore;
  v37 = &qword_180123710;
  v38 = v34;
  for ( j = 0; j < 0x14; ++j )
  {
    if ( *(_DWORD *)v37 )
    {
      if ( (v26 & *(_DWORD *)v37) != 0 )
      {
        if ( v38 >= (char *)&v35[v33] )
        {
LABEL_142:
          updated = 111;
          goto LABEL_82;
        }
        *(_DWORD *)v38 = 0;
        *((_QWORD *)v38 + 1) = 0;
        *((_QWORD *)v38 + 2) = v37[1];
        *((_QWORD *)v38 + 3) = v37[2];
        if ( v37[2] )
          v13 = 0;
        v38 += 32;
      }
    }
    else
    {
      v83 = 0;
      v84 = v36;
      while ( v83 < v24 )
      {
        if ( *v84 == *((_DWORD *)v37 + 1) )
        {
          if ( v38 >= (char *)&v35[v33] )
            goto LABEL_142;
          v91 = v84[1];
          if ( v91 > 0x1F4 )
            goto LABEL_162;
          *(_DWORD *)v38 = v91;
          *((_QWORD *)v38 + 1) = *((_QWORD *)v84 + 1);
          *((_QWORD *)v38 + 2) = v37[1];
          *((_QWORD *)v38 + 3) = v37[2];
          if ( v37[2] )
            v13 = 0;
          v38 += 32;
        }
        ++v83;
        v84 += 4;
      }
    }
    v37 += 3;
  }
  if ( v119 )
  {
    pChainPara = *(struct _CERT_CHAIN_PARA **)(v119 + 24);
    dwFlags = *(_DWORD *)(v119 + 32);
    hChainEngine = *(HCERTCHAINENGINE *)v119;
    pTime = *(LPFILETIME *)(v119 + 8);
    hAdditionalStore = *(HCERTSTORE *)(v119 + 16);
  }
  else
  {
    v126[0] = 96;
    v126[2] = 0;
    pChainPara = (struct _CERT_CHAIN_PARA *)v126;
    v126[4] = 0;
    v127 = 0;
    dwFlags = v13 ? -1073741820 : -1073741824;
    hChainEngine = 0;
    pTime = 0;
    hAdditionalStore = 0;
  }
  if ( v38 != (char *)&v35[v33] )
  {
LABEL_162:
    updated = 87;
    goto LABEL_82;
  }
  v42 = 0;
  v43 = Base;
  v44 = (PCCERT_CONTEXT *)Base;
  if ( !(_DWORD)NumOfElements )
    goto LABEL_57;
  v45 = hChainEngine;
  v46 = v104;
  while ( 1 )
  {
    v47 = 0;
    HIDWORD(NumOfElements) = 1;
    v48 = v35;
    if ( !v46 )
    {
LABEL_42:
      if ( !CertGetCertificateChain(v45, *v44, pTime, hAdditionalStore, pChainPara, dwFlags, 0, &ppChainContext) )
        goto LABEL_55;
      v51 = 0;
      v52 = (unsigned int *)v116;
      v44[1] = (PCCERT_CONTEXT)ppChainContext;
      v53 = HIDWORD(NumOfElements);
      if ( (_DWORD)v104 )
      {
        while ( 1 )
        {
          v54 = (unsigned int (__fastcall *)(PCCERT_CONTEXT *, _QWORD, _QWORD, char *))*((_QWORD *)v52 + 3);
          if ( v54 )
          {
            if ( v54(v44, *v52, *((_QWORD *)v52 + 1), (char *)&NumOfElements + 4) )
            {
              v53 = 0;
              HIDWORD(NumOfElements) = 0;
            }
            else
            {
              v53 = HIDWORD(NumOfElements);
            }
            if ( !v53 )
              break;
          }
          ++v51;
          v52 += 8;
          if ( v51 >= (unsigned int)v104 )
            goto LABEL_46;
        }
      }
      else
      {
LABEL_46:
        if ( v53 )
        {
          if ( (ppChainContext->TrustStatus.dwErrorStatus & 0x4000084) != 0 )
          {
            v53 = 0;
            HIDWORD(NumOfElements) = 0;
          }
          if ( v53 )
          {
            if ( pChainPara->cbSize >= 0x58
              && *(_QWORD *)&pChainPara[2].RequestedUsage.Usage.cUsageIdentifier
              && (ppChainContext->TrustStatus.dwErrorStatus & 0x100008) != 0 )
            {
              v53 = 0;
              HIDWORD(NumOfElements) = 0;
            }
            if ( v53 )
            {
              if ( (v102 & 2) != 0 && (ppChainContext->TrustStatus.dwErrorStatus & 0x10E21) != 0 )
              {
                v53 = 0;
                HIDWORD(NumOfElements) = 0;
              }
              if ( v53 )
              {
                LODWORD(v105) = v105 + 1;
                goto LABEL_54;
              }
            }
          }
        }
      }
      v44[1] = 0;
      ChainReleaseInternalChainContext((struct _INTERNAL_CERT_CHAIN_CONTEXT *)ppChainContext);
LABEL_54:
      ppChainContext = 0;
      goto LABEL_55;
    }
    while ( 1 )
    {
      v49 = (unsigned int (__fastcall *)(PCCERT_CONTEXT *, _QWORD, _QWORD, char *))*((_QWORD *)v48 + 2);
      if ( v49 )
      {
        if ( v49(v44, *v48, *((_QWORD *)v48 + 1), (char *)&NumOfElements + 4) )
        {
          v50 = 0;
          HIDWORD(NumOfElements) = 0;
        }
        else
        {
          v50 = HIDWORD(NumOfElements);
        }
        if ( !v50 )
          break;
      }
      ++v47;
      v48 += 8;
      if ( v47 >= (unsigned int)v104 )
        goto LABEL_42;
    }
LABEL_55:
    v46 = v104;
    ++v42;
    v44 += 5;
    if ( v42 >= (unsigned int)NumOfElements )
      break;
    v35 = (unsigned int *)v116;
  }
  v43 = Base;
  v25 = 8;
LABEL_57:
  updated = LoadCertSelectionPolicy((struct _CERT_KEYTYPES *)Context);
  if ( updated )
    goto LABEL_82;
  v55 = NumOfElements;
  o_qsort_s_0(v43, (unsigned int)NumOfElements, 0x28u, (_CoreCrtSecureSearchSortCompareFunction)CompareChains, Context);
  if ( LODWORD(v120[0]) )
    RemoveAppContainerDuplicateChains(v120, (unsigned int)NumOfElements, v43, &v105);
  v56 = LocalAlloc(0, 8LL * (unsigned int)v105);
  if ( !v56 )
  {
    updated = 8;
    goto LABEL_62;
  }
  v70 = &byte_180136197;
  v71 = &byte_180136197;
  Uuid = 0;
  v72 = 0;
  UuidCreate(&Uuid);
  memset(v130, 0, sizeof(v130));
  v131 = 0;
  v73 = TraceLoggingThrottleCheck();
  v74 = (struct SelectionContext *)Base;
  v75 = 0;
  LOBYTE(v100) = v73;
  v76 = NumOfElements;
  if ( (_DWORD)NumOfElements )
  {
    v77 = v100;
    do
    {
      if ( *((_QWORD *)v74 + 1) )
      {
        KeyPriority = *((_DWORD *)v74 + 8);
        if ( KeyPriority < 9
          || (KeyPriority = GetKeyPriority(v74, (const struct _CERT_KEYTYPES *)Context),
              *((_DWORD *)v74 + 8) = KeyPriority,
              KeyPriority < 9) )
        {
          ++*((_DWORD *)v130 + KeyPriority);
        }
        if ( (unsigned int)v72 < 2 && v77 )
          TraceLoggingWriteCertProp(&Uuid, v74, (unsigned int)v72);
        v56[v72] = *((_QWORD *)v74 + 1);
        v72 = (unsigned int)(v72 + 1);
        v76 = NumOfElements;
        *((_QWORD *)v74 + 1) = 0;
      }
      ++v75;
      v74 = (struct SelectionContext *)((char *)v74 + 40);
    }
    while ( v75 < v76 );
    v71 = &byte_180136197;
  }
  for ( k = 0; ; k = (unsigned int)(k + 1) )
  {
    if ( (unsigned int)k >= 9 )
      goto LABEL_114;
    if ( LODWORD(qword_180157668[2 * (unsigned int)k]) != *(_DWORD *)&Context[4 * k + 4] )
      break;
  }
  LODWORD(v122) = *(_DWORD *)&Context[36];
  *(_OWORD *)v120 = *(_OWORD *)&Context[4];
  *(_OWORD *)v121 = *(_OWORD *)&Context[20];
  ConvertArrayToString(v120, 9, &v117);
  if ( v117 )
    v70 = (const unsigned __int16 *)v117;
  while ( 1 )
  {
LABEL_114:
    if ( v25 < 0 )
    {
      v57 = hMem;
      goto LABEL_116;
    }
    if ( *((_DWORD *)v130 + v25) )
      break;
    --v25;
  }
  ConvertArrayToString(v130, (unsigned int)(v25 + 1), &hMem);
  v57 = hMem;
  if ( hMem )
    v71 = (const unsigned __int16 *)hMem;
LABEL_116:
  if ( (_BYTE)v100 )
    TraceLoggingWriteCertSelection((unsigned int)&Uuid, v102, v103, v110, v115, v72, (__int64)v70, (__int64)v71);
  updated = 0;
  v55 = NumOfElements;
  *v124 = v72;
  *v125 = v56;
LABEL_63:
  LocalFree(v57);
  LocalFree(v117);
  v58 = Base;
  if ( Base )
  {
    v85 = 0;
    for ( m = (char *)Base; v85 < v55; m += 40 )
    {
      if ( *(_QWORD *)m )
        CertFreeCertificateContext(*(PCCERT_CONTEXT *)m);
      v87 = (struct _INTERNAL_CERT_CHAIN_CONTEXT *)*((_QWORD *)m + 1);
      if ( v87 )
        ChainReleaseInternalChainContext(v87);
      v88 = (void *)*((_QWORD *)m + 2);
      if ( v88 )
        LocalFree(v88);
      ++v85;
    }
    LocalFree(v58);
  }
  if ( v116 )
    LocalFree(v116);
  if ( ppChainContext )
    ChainReleaseInternalChainContext((struct _INTERNAL_CERT_CHAIN_CONTEXT *)ppChainContext);
  if ( v118 )
    LocalFree(v118);
  if ( hLibModule )
    FreeLibrary(hLibModule);
  if ( !updated )
    return 1;
  SetLastError(updated);
  return 0;
}

```

## disassembly

```asm
0x180067020  mov     rax, rsp
0x180067023  mov     [rax+8], rbx
0x180067027  push    rbp
0x180067028  push    rsi
0x180067029  push    rdi
0x18006702a  push    r12
0x18006702c  push    r13
0x18006702e  push    r14
0x180067030  push    r15
0x180067032  lea     rbp, [rax-148h]
0x180067039  sub     rsp, 210h
0x180067040  movaps  xmmword ptr [rax-48h], xmm6
0x180067044  movaps  xmmword ptr [rax-58h], xmm7
0x180067048  mov     rax, cs:__security_cookie
0x18006704f  xor     rax, rsp
0x180067052  mov     [rbp+140h+var_60], rax
0x180067059  mov     rax, [rbp+140h+arg_30]
0x180067060  lea     rcx, [rbp+140h+var_120]; void *
0x180067064  mov     r14, [rbp+140h+arg_20]
0x18006706b  xor     esi, esi
0x18006706d  mov     r13, [rbp+140h+hCertStore]
0x180067074  mov     edi, edx
0x180067076  mov     rbx, [rbp+140h+arg_40]
0x18006707d  mov     r15d, r9d
0x180067080  mov     [rbp+140h+var_138], rax
0x180067084  mov     rax, [rbp+140h+arg_38]
0x18006708b  mov     [rbp+140h+var_170], r8
0x18006708f  lea     r8d, [rsi+60h]; Size
0x180067093  mov     [rsp+240h+var_1E8], edx
0x180067097  xor     edx, edx; Val
0x180067099  mov     [rbp+140h+var_190], r9d
0x18006709d  mov     dword ptr [rsp+240h+var_1E0], r9d
0x1800670a2  mov     [rbp+140h+hAdditionalStore], r14
0x1800670a6  mov     [rbp+140h+pTime], r13
0x1800670aa  mov     [rbp+140h+var_130], rax
0x1800670ae  mov     dword ptr [rsp+240h+NumOfElements+4], 0
0x1800670b6  mov     dword ptr [rsp+240h+NumOfElements], 0
0x1800670be  mov     [rsp+240h+Base], rsi
0x1800670c3  call    memset_0
0x1800670c8  xor     eax, eax
0x1800670ca  mov     [rbp+140h+var_198], rsi
0x1800670ce  xorps   xmm0, xmm0
0x1800670d1  mov     [rbp+140h+var_188], rax
0x1800670d5  mov     r12d, edi
0x1800670d8  mov     dword ptr [rsp+240h+var_1D0], eax
0x1800670dc  shr     r12d, 1
0x1800670df  not     r12d
0x1800670e2  mov     [rbp+140h+var_148], rax
0x1800670e6  and     r12d, 1
0x1800670ea  mov     [rbp+140h+var_178], rax
0x1800670ee  mov     [rbp+140h+hLibModule], rax
0x1800670f2  mov     [rbp+140h+var_90], rax
0x1800670f9  mov     [rbp+140h+var_180], rax
0x1800670fd  mov     [rsp+240h+hMem], rax
0x180067102  movups  xmmword ptr [rbp+140h+var_168], xmm0
0x180067106  movups  xmmword ptr [rbp+140h+var_158], xmm0
0x18006710a  movups  [rbp+140h+Context], xmm0
0x180067111  movups  [rbp+140h+var_A0], xmm0
0x180067118  test    r13, r13
0x18006711b  jz      loc_18006786A
0x180067121  cmp     r15d, 21h ; '!'
0x180067125  ja      loc_18006786A
0x18006712b  test    edi, 0FFFFFE00h
0x180067131  jnz     loc_18006786A
0x180067137  xor     r8d, r8d
0x18006713a  xor     edx, edx
0x18006713c  mov     [rbp+140h+var_18C], r8d
0x180067140  test    r15d, r15d
0x180067143  jz      short loc_180067163
0x180067145  mov     ecx, edx
0x180067147  mov     eax, 1
0x18006714c  add     rcx, rcx
0x18006714f  inc     edx
0x180067151  mov     ecx, [r14+rcx*8]
0x180067155  shl     eax, cl
0x180067157  or      r8d, eax
0x18006715a  cmp     edx, r15d
0x18006715d  jb      short loc_180067145
0x18006715f  mov     [rbp+140h+var_18C], r8d
0x180067163  test    rbx, rbx
0x180067166  jnz     loc_180067596
0x18006716c  mov     r15, [rbp+140h+var_158]
0x180067170  mov     rbx, [rbp+140h+var_168+8]
0x180067174  mov     [rbp+140h+var_1A0], r15
0x180067178  mov     [rbp+140h+hChainEngine], rbx
0x18006717c  xor     r8d, r8d; dwFlags
0x18006717f  lea     rcx, aNcryptDll_0; "ncrypt.dll"
0x180067186  xor     r9d, r9d
0x180067189  mov     dword ptr [rsp+240h+var_1E0], r8d
0x18006718e  xor     edx, edx; hFile
0x180067190  mov     [rbp+140h+var_1AC], r9d
0x180067194  xor     r14d, r14d
0x180067197  call    cs:__imp_LoadLibraryExW
0x18006719d  mov     [rbp+140h+hLibModule], rax
0x1800671a1  xor     edi, edi
0x1800671a3  mov     rdx, rdi; pPrevCertContext
0x1800671a6  mov     rcx, r13; hCertStore
0x1800671a9  call    CertEnumCertificatesInStore
0x1800671ae  mov     rdi, rax
0x1800671b1  test    rax, rax
0x1800671b4  jnz     loc_18006750A
0x1800671ba  call    cs:__imp_GetLastError
0x1800671c0  mov     ebx, eax
0x1800671c2  cmp     eax, 80092004h
0x1800671c7  jnz     loc_180067583
0x1800671cd  mov     r15d, [rbp+140h+var_190]
0x1800671d1  mov     r13d, 8
0x1800671d7  mov     edi, [rsp+240h+var_1E8]
0x1800671db  xor     edi, 1
0x1800671de  test    dil, 1
0x1800671e2  lea     eax, [r15+1]
0x1800671e6  cmovz   eax, r15d
0x1800671ea  test    dil, 4
0x1800671ee  lea     ecx, [rax+1]
0x1800671f1  cmovz   ecx, eax
0x1800671f4  test    r13b, dil
0x1800671f7  lea     eax, [rcx+1]
0x1800671fa  cmovz   eax, ecx
0x1800671fd  test    dil, 10h
0x180067201  lea     edx, [rax+1]
0x180067204  cmovz   edx, eax
0x180067207  test    dil, 20h
0x18006720b  lea     ecx, [rdx+1]
0x18006720e  cmovz   ecx, edx
0x180067211  test    dil, 40h
0x180067215  lea     eax, [rcx+1]
0x180067218  cmovz   eax, ecx
0x18006721b  xor     ecx, ecx; uFlags
0x18006721d  mov     ebx, eax
0x18006721f  mov     [rsp+240h+var_1D8], rax
0x180067224  shl     rbx, 5
0x180067228  mov     rdx, rbx; uBytes
0x18006722b  call    cs:__imp_LocalAlloc
0x180067231  xor     r8d, r8d
0x180067234  mov     [rbp+140h+var_188], rax
0x180067238  mov     r11, rax
0x18006723b  test    rax, rax
0x18006723e  jz      loc_180067914
0x180067244  mov     rsi, [rbp+140h+hAdditionalStore]
0x180067248  lea     rdx, qword_180123710
0x18006724f  mov     rcx, rax
0x180067252  mov     r10d, r8d
0x180067255  cmp     r10d, 14h
0x180067259  jnb     short loc_180067275
0x18006725b  cmp     [rdx], r8d
0x18006725e  jz      loc_1800677E1
0x180067264  test    [rdx], edi
0x180067266  jnz     loc_18006763F
0x18006726c  inc     r10d
0x18006726f  add     rdx, 18h
0x180067273  jmp     short loc_180067255
0x180067275  mov     rax, [rbp+140h+var_170]
0x180067279  test    rax, rax
0x18006727c  jz      loc_18006796B
0x180067282  mov     rdx, [rax]
0x180067285  mov     r15, [rax+18h]
0x180067289  mov     r14d, [rax+20h]
0x18006728d  mov     [rbp+140h+hChainEngine], rdx
0x180067291  mov     rdx, [rax+8]
0x180067295  mov     [rbp+140h+pTime], rdx
0x180067299  mov     rdx, [rax+10h]
0x18006729d  mov     [rbp+140h+hAdditionalStore], rdx
0x1800672a1  lea     rax, [rbx+r11]
0x1800672a5  cmp     rcx, rax
0x1800672a8  jnz     loc_180067961
0x1800672ae  mov     r12d, r8d
0x1800672b1  mov     rsi, [rsp+240h+Base]
0x1800672b6  mov     rdi, rsi
0x1800672b9  cmp     dword ptr [rsp+240h+NumOfElements], r8d
0x1800672be  jbe     loc_180067402
0x1800672c4  mov     r13, [rbp+140h+hChainEngine]
0x1800672c8  mov     rax, [rsp+240h+var_1D8]
0x1800672cd  jmp     short loc_1800672D3
0x1800672cf  mov     r11, [rbp+140h+var_188]
0x1800672d3  mov     ecx, 1
0x1800672d8  mov     esi, r8d
0x1800672db  mov     dword ptr [rsp+240h+NumOfElements+4], ecx
0x1800672df  mov     rbx, r11
0x1800672e2  test    eax, eax
0x1800672e4  jz      short loc_180067333
0x1800672e6  mov     rax, [rbx+10h]
0x1800672ea  test    rax, rax
0x1800672ed  jz      short loc_18006731C
0x1800672ef  mov     r8, [rbx+8]
0x1800672f3  lea     r9, [rsp+240h+NumOfElements+4]
0x1800672f8  mov     edx, [rbx]
0x1800672fa  mov     rcx, rdi
0x1800672fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180067302  xor     r8d, r8d
0x180067305  test    eax, eax
0x180067307  jz      loc_18006757A
0x18006730d  mov     ecx, r8d
0x180067310  mov     dword ptr [rsp+240h+NumOfElements+4], ecx
0x180067314  test    ecx, ecx
0x180067316  jz      loc_1800673E0
0x18006731c  mov     rax, [rsp+240h+var_1D8]
0x180067321  inc     esi
0x180067323  add     rbx, 20h ; ' '
0x180067327  cmp     esi, eax
0x180067329  jb      short loc_1800672E6
0x18006732b  test    ecx, ecx
0x18006732d  jz      loc_1800673E5
0x180067333  mov     r9, [rbp+140h+hAdditionalStore]; hAdditionalStore
0x180067337  lea     rax, [rbp+140h+var_198]
0x18006733b  mov     rdx, [rdi]; pCertContext
0x18006733e  mov     rcx, r13; hChainEngine
0x180067341  mov     [rsp+240h+ppChainContext], rax; ppChainContext
0x180067346  mov     [rsp+240h+pvReserved], r8; pvReserved
0x18006734b  mov     r8, [rbp+140h+pTime]; pTime
0x18006734f  mov     [rsp+240h+dwFlags], r14d; dwFlags
0x180067354  mov     [rsp+240h+pChainPara], r15; pChainPara
0x180067359  call    CertGetCertificateChain
0x18006735e  xor     r8d, r8d
0x180067361  test    eax, eax
0x180067363  jz      short loc_1800673E0
0x180067365  mov     esi, r8d
0x180067368  mov     rax, [rbp+140h+var_198]
0x18006736c  mov     rbx, [rbp+140h+var_188]
0x180067370  mov     [rdi+8], rax
0x180067374  mov     ecx, dword ptr [rsp+240h+NumOfElements+4]
0x180067378  cmp     dword ptr [rsp+240h+var_1D8], r8d
0x18006737d  jbe     short loc_180067398
0x18006737f  mov     rax, [rbx+18h]
0x180067383  test    rax, rax
0x180067386  jnz     loc_1800679A4
0x18006738c  inc     esi
0x18006738e  add     rbx, 20h ; ' '
0x180067392  cmp     esi, dword ptr [rsp+240h+var_1D8]
0x180067396  jb      short loc_18006737F
0x180067398  test    ecx, ecx
0x18006739a  jz      short loc_1800673CC
0x18006739c  mov     rax, [rbp+140h+var_198]
0x1800673a0  test    dword ptr [rax+4], 4000084h
0x1800673a7  jz      short loc_1800673B0
0x1800673a9  mov     ecx, r8d
0x1800673ac  mov     dword ptr [rsp+240h+NumOfElements+4], ecx
0x1800673b0  test    ecx, ecx
0x1800673b2  jz      short loc_1800673CC
0x1800673b4  cmp     dword ptr [r15], 58h ; 'X'
0x1800673b8  jb      short loc_1800673C4
0x1800673ba  cmp     [r15+50h], r8
0x1800673be  jnz     loc_1800679CE
0x1800673c4  test    ecx, ecx
0x1800673c6  jnz     loc_180067877
0x1800673cc  mov     [rdi+8], r8
0x1800673d0  mov     rcx, [rbp+140h+var_198]; struct _INTERNAL_CERT_CHAIN_CONTEXT *
0x1800673d4  call    ?ChainReleaseInternalChainContext@@YAXPEAU_INTERNAL_CERT_CHAIN_CONTEXT@@@Z; ChainReleaseInternalChainContext(_INTERNAL_CERT_CHAIN_CONTEXT *)
0x1800673d9  xor     r8d, r8d
0x1800673dc  mov     [rbp+140h+var_198], r8
0x1800673e0  mov     rax, [rsp+240h+var_1D8]
0x1800673e5  inc     r12d
0x1800673e8  add     rdi, 28h ; '('
0x1800673ec  cmp     r12d, dword ptr [rsp+240h+NumOfElements]
0x1800673f1  jb      loc_1800672CF
0x1800673f7  mov     rsi, [rsp+240h+Base]
0x1800673fc  mov     r13d, 8
0x180067402  lea     rcx, [rbp+140h+Context]; struct _CERT_KEYTYPES *
0x180067409  call    ?LoadCertSelectionPolicy@@YAKPEAU_CERT_KEYTYPES@@@Z; LoadCertSelectionPolicy(_CERT_KEYTYPES *)
0x18006740e  mov     ebx, eax
0x180067410  test    eax, eax
0x180067412  jnz     loc_18006758C
0x180067418  mov     r15d, dword ptr [rsp+240h+NumOfElements]
0x18006741d  lea     rax, [rbp+140h+Context]
0x180067424  mov     edx, r15d; NumOfElements
0x180067427  mov     [rsp+240h+pChainPara], rax; Context
0x18006742c  lea     r9, ?CompareChains@@YAHPEAXPEBX1@Z; CompareFunction
0x180067433  mov     rcx, rsi; Base
0x180067436  lea     r8d, [rbx+28h]; SizeOfElements
0x18006743a  call    _o_qsort_s_0
0x18006743f  cmp     dword ptr [rbp+140h+var_168], ebx
0x180067442  jnz     loc_180067A00
0x180067448  mov     edx, dword ptr [rsp+240h+var_1D0]
0x18006744c  xor     ecx, ecx; uFlags
0x18006744e  shl     rdx, 3; uBytes
0x180067452  call    cs:__imp_LocalAlloc
0x180067458  mov     r12, rax
0x18006745b  test    rax, rax
0x18006745e  jnz     loc_180067674
0x180067464  mov     ebx, r13d
0x180067467  mov     r13, [rsp+240h+hMem]
0x18006746c  mov     rcx, r13; hMem
0x18006746f  call    cs:__imp_LocalFree
0x180067475  mov     rcx, [rbp+140h+var_180]; hMem
0x180067479  call    cs:__imp_LocalFree
0x18006747f  mov     r14, [rsp+240h+Base]
0x180067484  test    r14, r14
0x180067487  jnz     loc_180067801
0x18006748d  mov     rax, [rbp+140h+var_188]
0x180067491  test    rax, rax
0x180067494  jnz     loc_180067ADB
0x18006749a  mov     rcx, [rbp+140h+var_198]; struct _INTERNAL_CERT_CHAIN_CONTEXT *
0x18006749e  test    rcx, rcx
0x1800674a1  jnz     loc_180067AE9
0x1800674a7  mov     rax, [rbp+140h+var_178]
0x1800674ab  test    rax, rax
0x1800674ae  jnz     loc_180067AF3
0x1800674b4  mov     rax, [rbp+140h+hLibModule]
0x1800674b8  test    rax, rax
0x1800674bb  jnz     loc_180067B01
0x1800674c1  test    ebx, ebx
  ... truncated ...
```
