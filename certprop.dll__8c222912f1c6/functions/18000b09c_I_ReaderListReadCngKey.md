# I_ReaderListReadCngKey

- ea: `0x18000b09c`
- end: `0x18000bfd5`
- name: `I_ReaderListReadCngKey`
- size: `3897`
- prototype: `__int64 __fastcall(__int64, _QWORD *, __int64 *, __int64, int, _DWORD *)`
- caller_count: `1`
- callee_count: `17`
- tags: `broker_com_uri`

## callers

- `0x180009c00`

## callees

- `0x180002aa0`
- `0x180004600`
- `0x18000a980`
- `0x18000b010`
- `0x18000b09c`
- `0x18000cce0`
- `0x18000cda0`
- `0x18000d220`
- `0x18000e33c`
- `0x180010b54`
- `0x180016090`
- `0x180018b58`
- `0x180018bb4`
- `0x1800210e0`
- `0x180024380`
- `0x1800243e0`
- `0x180026010`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18000b1ad`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18000b1bf`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18000bf59`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18000b1ad`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18000b1bf`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18000bf59`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b5f1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bb35`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bcb8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b5f1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bb35`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bcb8`
- `CRYPT32!CertSetCertificateContextProperty` at `0x18000b914`
- `CRYPT32!CertSetCertificateContextProperty` at `0x18000bb2b`
- `CRYPT32!CertSetCertificateContextProperty` at `0x18000bcae`
- `CRYPT32!CertSetCertificateContextProperty` at `0x18000b914`
- `CRYPT32!CertSetCertificateContextProperty` at `0x18000bb2b`
- `CRYPT32!CertSetCertificateContextProperty` at `0x18000bcae`
- `CRYPT32!CertAddCertificateContextToStore` at `0x18000bcdb`
- `CRYPT32!CertAddCertificateContextToStore` at `0x18000bcdb`
- `CRYPT32!CertFreeCertificateContext` at `0x18000be18`
- `CRYPT32!CertFreeCertificateContext` at `0x18000be18`
- `CRYPT32!CertCreateCertificateContext` at `0x18000b5dd`
- `CRYPT32!CertCreateCertificateContext` at `0x18000b5dd`
- `ncrypt!NCryptFreeObject` at `0x18000be06`
- `ncrypt!NCryptFreeObject` at `0x18000be06`
- `ncrypt!NCryptGetProperty` at `0x18000b43f`
- `ncrypt!NCryptGetProperty` at `0x18000b586`
- `ncrypt!NCryptGetProperty` at `0x18000b70e`
- `ncrypt!NCryptGetProperty` at `0x18000b852`
- `ncrypt!NCryptGetProperty` at `0x18000b944`
- `ncrypt!NCryptGetProperty` at `0x18000b96e`
- `ncrypt!NCryptGetProperty` at `0x18000baa7`
- `ncrypt!NCryptGetProperty` at `0x18000bc3d`
- `ncrypt!NCryptGetProperty` at `0x18000b43f`
- `ncrypt!NCryptGetProperty` at `0x18000b586`
- `ncrypt!NCryptGetProperty` at `0x18000b70e`
- `ncrypt!NCryptGetProperty` at `0x18000b852`
- `ncrypt!NCryptGetProperty` at `0x18000b944`
- `ncrypt!NCryptGetProperty` at `0x18000b96e`
- `ncrypt!NCryptGetProperty` at `0x18000baa7`
- `ncrypt!NCryptGetProperty` at `0x18000bc3d`
- `ncrypt!NCryptOpenKey` at `0x18000b3c2`
- `ncrypt!NCryptOpenKey` at `0x18000b3c2`

## pseudocode

```c
__int64 __fastcall I_ReaderListReadCngKey(__int64 a1, _QWORD *a2, __int64 *a3, __int64 a4, int a5, _DWORD *a6)
{
  wchar_t *p_lpMem; // rsi
  LPVOID *v9; // r13
  LPVOID *v10; // r14
  LPVOID *v11; // r15
  __int64 v12; // rcx
  __int64 v13; // r8
  __int64 v14; // rax
  __int64 v15; // rcx
  __int64 v16; // rdx
  size_t v17; // rdi
  unsigned __int64 v18; // rbx
  unsigned __int64 v19; // rcx
  __int64 v20; // rcx
  unsigned __int64 v21; // rcx
  void *v22; // rsp
  void *v23; // rsp
  unsigned __int64 v24; // rcx
  wchar_t *v25; // rax
  unsigned int LastError; // edi
  LPVOID *v27; // rbx
  void *v28; // r12
  _QWORD *v29; // rbx
  SECURITY_STATUS v30; // eax
  __int64 v31; // rcx
  char v32; // bl
  STRSAFE_LPSTR v33; // rcx
  int v34; // edx
  SECURITY_STATUS Property; // eax
  __int64 v36; // rdx
  __int64 v37; // rcx
  __int64 v38; // r8
  unsigned __int64 v39; // rbx
  unsigned __int64 v40; // rcx
  __int64 v41; // rcx
  unsigned __int64 v42; // rcx
  void *v43; // rsp
  void *v44; // rsp
  _DWORD *v45; // rax
  STRSAFE_LPSTR v46; // rcx
  __int64 v47; // rdx
  SECURITY_STATUS v48; // eax
  __int64 v49; // rcx
  PCCERT_CONTEXT CertificateContext; // rax
  PCCERT_CONTEXT v51; // rcx
  _DWORD *p_dwVersion; // rcx
  _QWORD *v53; // rbx
  const wchar_t *v54; // rax
  SECURITY_STATUS v55; // eax
  __int64 v56; // rdx
  __int64 v57; // rcx
  __int64 v58; // r8
  unsigned __int64 v59; // rbx
  unsigned __int64 v60; // rcx
  __int64 v61; // rcx
  unsigned __int64 v62; // rcx
  void *v63; // rsp
  void *v64; // rsp
  _DWORD *v65; // rax
  SECURITY_STATUS v66; // eax
  __int64 v67; // rcx
  SECURITY_STATUS v68; // ebx
  SECURITY_STATUS v69; // eax
  __int64 v70; // rdx
  __int64 v71; // r8
  unsigned __int64 v72; // rbx
  LPVOID *v73; // rax
  unsigned __int64 v74; // rcx
  __int64 v75; // rcx
  unsigned __int64 v76; // rcx
  void *v77; // rsp
  void *v78; // rsp
  _DWORD *v79; // rax
  STRSAFE_LPSTR v80; // rcx
  __int64 v81; // rdx
  SECURITY_STATUS v82; // eax
  __int64 v83; // rcx
  char v84; // bl
  STRSAFE_LPSTR v85; // rcx
  int v86; // edx
  __int64 v87; // rdx
  __int64 v88; // r8
  unsigned __int64 v89; // rbx
  unsigned __int64 v90; // rcx
  __int64 v91; // rcx
  unsigned __int64 v92; // rcx
  void *v93; // rsp
  void *v94; // rsp
  _DWORD *v95; // rax
  SECURITY_STATUS v96; // eax
  __int64 v97; // rcx
  _QWORD *v98; // rbx
  _WORD *v99; // r8
  __int64 v100; // rcx
  NCRYPT_KEY_HANDLE v101; // rcx
  __int64 v102; // rcx
  _BYTE v104[32]; // [rsp+0h] [rbp-30h] BYREF
  LPVOID *v105; // [rsp+30h] [rbp+0h] BYREF
  LPVOID lpMem; // [rsp+38h] [rbp+8h] BYREF
  DWORD cbOutput; // [rsp+40h] [rbp+10h] BYREF
  NCRYPT_KEY_HANDLE phKey; // [rsp+48h] [rbp+18h] BYREF
  DWORD pcbResult; // [rsp+50h] [rbp+20h] BYREF
  DWORD v110; // [rsp+54h] [rbp+24h] BYREF
  DWORD v111; // [rsp+58h] [rbp+28h] BYREF
  int v112; // [rsp+60h] [rbp+30h] BYREF
  DWORD cbCertEncoded; // [rsp+68h] [rbp+38h] BYREF
  PCCERT_CONTEXT pCertContext; // [rsp+70h] [rbp+40h]
  DWORD v115; // [rsp+78h] [rbp+48h] BYREF
  DWORD v116; // [rsp+7Ch] [rbp+4Ch]
  void *v117; // [rsp+80h] [rbp+50h] BYREF
  _QWORD *v118; // [rsp+88h] [rbp+58h]
  DWORD v119; // [rsp+90h] [rbp+60h] BYREF
  DWORD v120; // [rsp+94h] [rbp+64h] BYREF
  __int128 pvData; // [rsp+98h] [rbp+68h] BYREF
  __int128 v122; // [rsp+A8h] [rbp+78h]
  __int128 v123; // [rsp+B8h] [rbp+88h]
  __int64 v124; // [rsp+C8h] [rbp+98h]
  __int64 v125; // [rsp+D0h] [rbp+A0h]
  _DWORD *v126; // [rsp+D8h] [rbp+A8h]
  __int128 v127; // [rsp+E0h] [rbp+B0h] BYREF
  __int128 v128; // [rsp+F0h] [rbp+C0h] BYREF
  GUID ActivityId; // [rsp+100h] [rbp+D0h] BYREF
  GUID v130; // [rsp+110h] [rbp+E0h] BYREF
  _BYTE v131[32]; // [rsp+120h] [rbp+F0h] BYREF
  DWORD *p_cbOutput; // [rsp+140h] [rbp+110h]
  __int64 v133; // [rsp+148h] [rbp+118h]
  DWORD *p_cbCertEncoded; // [rsp+150h] [rbp+120h]
  __int64 v135; // [rsp+158h] [rbp+128h]
  _QWORD v136[2]; // [rsp+160h] [rbp+130h] BYREF
  DWORD *v137; // [rsp+170h] [rbp+140h]
  __int64 v138; // [rsp+178h] [rbp+148h]
  LPVOID **v139; // [rsp+180h] [rbp+150h]
  __int64 v140; // [rsp+188h] [rbp+158h]
  _BYTE v141[32]; // [rsp+190h] [rbp+160h] BYREF
  LPVOID **v142; // [rsp+1B0h] [rbp+180h]
  __int64 v143; // [rsp+1B8h] [rbp+188h]

  p_lpMem = 0;
  v118 = a2;
  v125 = a4;
  lpMem = 0;
  v117 = 0;
  v124 = a1;
  v126 = a6;
  phKey = 0;
  v9 = 0;
  v105 = 0;
  v10 = 0;
  pcbResult = 0;
  v11 = 0;
  v110 = 0;
  v111 = 0;
  v115 = 0;
  v119 = 0;
  v120 = 0;
  pCertContext = 0;
  pvData = 0;
  v116 = 0;
  v122 = 0;
  v123 = 0;
  v127 = 0;
  v128 = 0;
  WppTraceIndent(a1, 0);
  if ( WPP_GLOBAL_Control != (STRSAFE_LPSTR)&WPP_GLOBAL_Control
    && (WPP_GLOBAL_Control[28] & 2) != 0
    && (unsigned __int8)WPP_GLOBAL_Control[25] >= 5u )
  {
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 128, &WPP_173052b9a503333cb537dada0074ae31_Traceguids, WPP_pszIndent);
  }
  ActivityId = 0;
  v130 = 0;
  EventActivityIdControl(5u, &ActivityId);
  EventActivityIdControl(1u, &v130);
  if ( (unsigned int)dword_180031008 > 5 )
    tlgWriteTransfer_EventWriteTransfer(v12, byte_18002AA91, &v130, &ActivityId, 2, v141);
  v14 = -1;
  *a6 = 0;
  v15 = -1;
  do
    ++v15;
  while ( *(_WORD *)(*a2 + 2 * v15) );
  v16 = *a3;
  do
    ++v14;
  while ( *(_WORD *)(v16 + 2 * v14) );
  v17 = v14 + v15 + 6;
  pvData = 0;
  v122 = 0;
  v18 = 2 * v17;
  v123 = 0;
  if ( !(2 * v17) )
    goto LABEL_19;
  if ( v18 > g_ulMaxStackAllocSize )
    goto LABEL_19;
  v19 = v18 + g_ulAdditionalProbeSize + 8;
  if ( v19 < v18 || !(unsigned int)VerifyStackAvailable(v19, v16, v13) )
    goto LABEL_19;
  v20 = v18 + 23;
  if ( v18 + 23 <= v18 + 8 )
    v20 = 0xFFFFFFFFFFFFFF0LL;
  v21 = v20 & 0xFFFFFFFFFFFFFFF0uLL;
  v22 = alloca(v21);
  v23 = alloca(v21);
  p_lpMem = (wchar_t *)&v105;
  if ( v104 == (_BYTE *)-48LL || (LODWORD(v105) = 1801679955, (p_lpMem = (wchar_t *)&lpMem) == 0) )
  {
LABEL_19:
    v24 = v18 + 8;
    if ( v18 + 8 >= v18 )
    {
      v25 = (wchar_t *)((__int64 (*)(void))g_pfnAllocate)();
      p_lpMem = v25;
      if ( !v25 )
      {
LABEL_23:
        WppTraceIndent(v24, 2);
        LastError = 8;
        if ( WPP_GLOBAL_Control == (STRSAFE_LPSTR)&WPP_GLOBAL_Control )
        {
          v28 = lpMem;
          goto LABEL_185;
        }
        if ( (WPP_GLOBAL_Control[28] & 1) != 0 && (unsigned __int8)WPP_GLOBAL_Control[25] >= 2u )
          WPP_SF_s(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            129,
            &WPP_173052b9a503333cb537dada0074ae31_Traceguids,
            WPP_pszIndent);
        goto LABEL_27;
      }
      *(_DWORD *)v25 = 1885431112;
      p_lpMem = v25 + 4;
    }
    if ( !p_lpMem )
      goto LABEL_23;
  }
  v29 = v118;
  if ( StringCchPrintfW(p_lpMem, v17, L"\\\\.\\%s\\%s", *v118, *a3) < 0 )
  {
    LastError = 122;
LABEL_27:
    v27 = 0;
LABEL_28:
    v28 = lpMem;
    goto LABEL_29;
  }
  LastError = 0;
  v30 = NCryptOpenKey(v29[17], &phKey, p_lpMem, *((_DWORD *)a3 + 4), *((_DWORD *)a3 + 5) | 0x40);
  v32 = v30;
  if ( v30 )
  {
    WppTraceIndent(v31, 2);
    v33 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (STRSAFE_LPSTR)&WPP_GLOBAL_Control
      || (WPP_GLOBAL_Control[28] & 1) == 0
      || (unsigned __int8)WPP_GLOBAL_Control[25] < 2u )
    {
      goto LABEL_43;
    }
    v34 = 130;
LABEL_42:
    WPP_SF_sD(
      *((_QWORD *)v33 + 2),
      v34,
      (unsigned int)&WPP_173052b9a503333cb537dada0074ae31_Traceguids,
      WPP_pszIndent,
      v32);
LABEL_43:
    v27 = 0;
    goto LABEL_28;
  }
  Property = NCryptGetProperty(phKey, L"SmartCardKeyCertificate", 0, 0, &pcbResult, 0x40u);
  v32 = Property;
  if ( Property )
  {
    WppTraceIndent(v37, 2);
    v33 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (STRSAFE_LPSTR)&WPP_GLOBAL_Control
      || (WPP_GLOBAL_Control[28] & 1) == 0
      || (unsigned __int8)WPP_GLOBAL_Control[25] < 2u )
    {
      goto LABEL_43;
    }
    v34 = 131;
    goto LABEL_42;
  }
  v39 = pcbResult;
  if ( !pcbResult )
    goto LABEL_57;
  if ( pcbResult > (unsigned __int64)g_ulMaxStackAllocSize )
    goto LABEL_57;
  v40 = pcbResult + g_ulAdditionalProbeSize + 8;
  if ( v40 < pcbResult || !(unsigned int)VerifyStackAvailable(v40, v36, v38) )
    goto LABEL_57;
  v41 = v39 + 23;
  if ( v39 + 23 <= v39 + 8 )
    v41 = 0xFFFFFFFFFFFFFF0LL;
  v42 = v41 & 0xFFFFFFFFFFFFFFF0uLL;
  v43 = alloca(v42);
  v44 = alloca(v42);
  v9 = (LPVOID *)&v105;
  if ( v104 == (_BYTE *)-48LL || (LODWORD(v105) = 1801679955, (v9 = &lpMem) == 0) )
  {
LABEL_57:
    v42 = v39 + 8;
    if ( v39 + 8 >= v39 )
    {
      v45 = (_DWORD *)((__int64 (*)(void))g_pfnAllocate)();
      v9 = (LPVOID *)v45;
      if ( v45 )
      {
        *v45 = 1885431112;
        v9 = (LPVOID *)(v45 + 2);
      }
    }
  }
  if ( !v9 )
  {
    WppTraceIndent(v42, 2);
    LastError = 8;
    v46 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (STRSAFE_LPSTR)&WPP_GLOBAL_Control
      || (WPP_GLOBAL_Control[28] & 1) == 0
      || (unsigned __int8)WPP_GLOBAL_Control[25] < 2u )
    {
      goto LABEL_66;
    }
    v47 = 132;
    goto LABEL_65;
  }
  v48 = NCryptGetProperty(phKey, L"SmartCardKeyCertificate", (PBYTE)v9, pcbResult, &v115, 0x40u);
  v32 = v48;
  if ( v48 )
  {
    WppTraceIndent(v49, 2);
    v33 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (STRSAFE_LPSTR)&WPP_GLOBAL_Control
      || (WPP_GLOBAL_Control[28] & 1) == 0
      || (unsigned __int8)WPP_GLOBAL_Control[25] < 2u )
    {
      goto LABEL_43;
    }
    v34 = 133;
    goto LABEL_42;
  }
  CertificateContext = CertCreateCertificateContext(0x10001u, (const BYTE *)v9, pcbResult);
  pCertContext = CertificateContext;
  v51 = CertificateContext;
  if ( !CertificateContext )
  {
LABEL_73:
    LastError = GetLastError();
    goto LABEL_66;
  }
  if ( (unsigned int)dword_180031008 > 5 )
  {
    cbOutput = CertificateContext->dwCertEncodingType;
    v133 = 4;
    p_cbOutput = &cbOutput;
    p_dwVersion = &CertificateContext->pCertInfo->dwVersion;
    cbCertEncoded = CertificateContext->cbCertEncoded;
    p_cbCertEncoded = &cbCertEncoded;
    v135 = 4;
    v112 = *p_dwVersion;
    v136[0] = &v112;
    v137 = p_dwVersion + 16;
    v139 = (LPVOID **)(p_dwVersion + 18);
    v136[1] = 4;
    v138 = 8;
    v140 = 8;
    tlgWriteTransfer_EventWriteTransfer(p_dwVersion, word_180029F82, &v130, &ActivityId, 7, v131);
  }
  v53 = v118;
  *(_QWORD *)&pvData = *a3;
  if ( *((_DWORD *)v118 + 3) == 1024 )
  {
    if ( a5 )
    {
      v54 = (const wchar_t *)v118[11];
    }
    else
    {
      cbOutput = 0;
      v55 = NCryptGetProperty(phKey, L"SmartCardNgcKeyName", 0, 0, &cbOutput, 0x40u);
      v32 = v55;
      if ( v55 )
      {
        WppTraceIndent(v57, 2);
        v33 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (STRSAFE_LPSTR)&WPP_GLOBAL_Control
          || (WPP_GLOBAL_Control[28] & 1) == 0
          || (unsigned __int8)WPP_GLOBAL_Control[25] < 2u )
        {
          goto LABEL_43;
        }
        v34 = 134;
        goto LABEL_42;
      }
      v59 = cbOutput;
      if ( !cbOutput )
        goto LABEL_92;
      if ( cbOutput > (unsigned __int64)g_ulMaxStackAllocSize )
        goto LABEL_92;
      v60 = cbOutput + g_ulAdditionalProbeSize + 8;
      if ( v60 < cbOutput || !(unsigned int)VerifyStackAvailable(v60, v56, v58) )
        goto LABEL_92;
      v61 = v59 + 23;
      if ( v59 + 23 <= v59 + 8 )
        v61 = 0xFFFFFFFFFFFFFF0LL;
      v62 = v61 & 0xFFFFFFFFFFFFFFF0uLL;
      v63 = alloca(v62);
      v64 = alloca(v62);
      v11 = (LPVOID *)&v105;
      if ( v104 == (_BYTE *)-48LL || (LODWORD(v105) = 1801679955, (v11 = &lpMem) == 0) )
      {
LABEL_92:
        v62 = v59 + 8;
        if ( v59 + 8 >= v59 )
        {
          v65 = (_DWORD *)((__int64 (*)(void))g_pfnAllocate)();
          v11 = (LPVOID *)v65;
          if ( v65 )
          {
            *v65 = 1885431112;
            v11 = (LPVOID *)(v65 + 2);
          }
        }
      }
      if ( !v11 )
      {
        WppTraceIndent(v62, 2);
        LastError = 8;
        v46 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (STRSAFE_LPSTR)&WPP_GLOBAL_Control
          || (WPP_GLOBAL_Control[28] & 1) == 0
          || (unsigned __int8)WPP_GLOBAL_Control[25] < 2u )
        {
          goto LABEL_66;
        }
        v47 = 135;
LABEL_65:
        WPP_SF_s(*((_QWORD *)v46 + 2), v47, &WPP_173052b9a503333cb537dada0074ae31_Traceguids, WPP_pszIndent);
LABEL_66:
        v27 = 0;
        goto LABEL_28;
      }
      v66 = NCryptGetProperty(phKey, L"SmartCardNgcKeyName", (PBYTE)v11, cbOutput, &v115, 0x40u);
      v32 = v66;
      if ( v66 )
      {
        WppTraceIndent(v67, 2);
        v33 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (STRSAFE_LPSTR)&WPP_GLOBAL_Control
          || (WPP_GLOBAL_Control[28] & 1) == 0
          || (unsigned __int8)WPP_GLOBAL_Control[25] < 2u )
        {
          goto LABEL_43;
        }
        v34 = 136;
        goto LABEL_42;
      }
      *(_QWORD *)&pvData = v11;
      v54 = L"Microsoft Passport Key Storage Provider";
    }
    LODWORD(v122) = 0;
    DWORD2(v123) = 0;
  }
  else
  {
    if ( (unsigned int)IsCAPIOverrideForRSAEnabled(v51, 0) && !wcscmp_0((const wchar_t *)a3[1], L"RSA") && v53[10] )
    {
      *((_QWORD *)&pvData + 1) = v53[10];
      DWORD2(v123) = *((_DWORD *)a3 + 4);
      LODWORD(v122) = 1;
      goto LABEL_113;
    }
    v54 = (const wchar_t *)v53[11];
    DWORD2(v123) = 0;
    LODWORD(v122) = 0;
  }
  *((_QWORD *)&pvData + 1) = v54;
LABEL_113:
  if ( !CertSetCertificateContextProperty(pCertContext, 2u, 0, &pvData) )
    goto LABEL_73;
  v68 = NCryptGetProperty(phKey, L"SmartCardPinId", 0, 0, &v110, 0x40u);
  v69 = NCryptGetProperty(phKey, L"SmartCardPinInfo", 0, 0, &v111, 0x40u);
  if ( v68 || v69 )
    goto LABEL_167;
  v72 = v110;
  v73 = 0;
  v105 = 0;
  if ( v110 )
  {
    if ( v110 <= (unsigned __int64)g_ulMaxStackAllocSize )
    {
      v74 = v110 + g_ulAdditionalProbeSize + 8;
      if ( v74 >= v110 )
      {
        if ( (unsigned int)VerifyStackAvailable(v74, v70, v71) )
        {
          v75 = v72 + 23;
          if ( v72 + 23 <= v72 + 8 )
            v75 = 0xFFFFFFFFFFFFFF0LL;
          v76 = v75 & 0xFFFFFFFFFFFFFFF0uLL;
          v77 = alloca(v76);
          v78 = alloca(v76);
          v73 = (LPVOID *)&v105;
          v105 = (LPVOID *)&v105;
          if ( v104 != (_BYTE *)-48LL )
          {
            v73 = &lpMem;
            v105 = &lpMem;
            if ( &lpMem )
              goto LABEL_129;
          }
        }
        else
        {
          v73 = 0;
        }
      }
    }
  }
  v76 = v72 + 8;
  if ( v72 + 8 >= v72 )
  {
    v79 = (_DWORD *)((__int64 (*)(void))g_pfnAllocate)();
    v105 = (LPVOID *)v79;
    if ( !v79 )
      goto LABEL_130;
    *v79 = 1885431112;
    v73 = (LPVOID *)(v79 + 2);
    v105 = v73;
  }
LABEL_129:
  if ( !v73 )
  {
LABEL_130:
    WppTraceIndent(v76, 2);
    LastError = 8;
    v80 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (STRSAFE_LPSTR)&WPP_GLOBAL_Control
      || (WPP_GLOBAL_Control[28] & 1) == 0
      || (unsigned __int8)WPP_GLOBAL_Control[25] < 2u )
    {
      goto LABEL_135;
    }
    v81 = 137;
    goto LABEL_134;
  }
  v82 = NCryptGetProperty(phKey, L"SmartCardPinId", (PBYTE)v73, v110, &v119, 0x40u);
  v84 = v82;
  if ( v82 )
  {
    WppTraceIndent(v83, 2);
    v85 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (STRSAFE_LPSTR)&WPP_GLOBAL_Control
      || (WPP_GLOBAL_Control[28] & 1) == 0
      || (unsigned __int8)WPP_GLOBAL_Control[25] < 2u )
    {
      goto LABEL_135;
    }
    v86 = 138;
    goto LABEL_141;
  }
  v27 = v105;
  *((_QWORD *)&v127 + 1) = v105;
  LODWORD(v127) = v110;
  if ( !CertSetCertificateContextProperty(pCertContext, 0x5Au, 0x40000000u, &v127) )
  {
    LastError = GetLastError();
    goto LABEL_28;
  }
  v89 = v111;
  if ( !v111 )
    goto LABEL_152;
  if ( v111 > (unsigned __int64)g_ulMaxStackAllocSize )
    goto LABEL_152;
  v90 = v111 + g_ulAdditionalProbeSize + 8;
  if ( v90 < v111 || !(unsigned int)VerifyStackAvailable(v90, v87, v88) )
    goto LABEL_152;
  v91 = v89 + 23;
  if ( v89 + 23 <= v89 + 8 )
    v91 = 0xFFFFFFFFFFFFFF0LL;
  v92 = v91 & 0xFFFFFFFFFFFFFFF0uLL;
  v93 = alloca(v92);
  v94 = alloca(v92);
  v10 = (LPVOID *)&v105;
  if ( v104 == (_BYTE *)-48LL || (LODWORD(v105) = 1801679955, (v10 = &lpMem) == 0) )
  {
LABEL_152:
    v92 = v89 + 8;
    if ( v89 + 8 >= v89 )
    {
      v95 = (_DWORD *)((__int64 (*)(void))g_pfnAllocate)();
      v10 = (LPVOID *)v95;
      if ( v95 )
      {
        *v95 = 1885431112;
        v10 = (LPVOID *)(v95 + 2);
      }
    }
  }
  if ( !v10 )
  {
    WppTraceIndent(v92, 2);
    LastError = 8;
    v80 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (STRSAFE_LPSTR)&WPP_GLOBAL_Control
      || (WPP_GLOBAL_Control[28] & 1) == 0
      || (unsigned __int8)WPP_GLOBAL_Control[25] < 2u )
    {
      goto LABEL_135;
    }
    v81 = 139;
LABEL_134:
    WPP_SF_s(*((_QWORD *)v80 + 2), v81, &WPP_173052b9a503333cb537dada0074ae31_Traceguids, WPP_pszIndent);
LABEL_135:
    v27 = v105;
    goto LABEL_28;
  }
  v96 = NCryptGetProperty(phKey, L"SmartCardPinInfo", (PBYTE)v10, v111, &v120, 0x40u);
  v84 = v96;
  if ( v96 )
  {
    WppTraceIndent(v97, 2);
    v85 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (STRSAFE_LPSTR)&WPP_GLOBAL_Control
      || (WPP_GLOBAL_Control[28] & 1) == 0
      || (unsigned __int8)WPP_GLOBAL_Control[25] < 2u )
    {
      goto LABEL_135;
    }
    v86 = 140;
LABEL_141:
    WPP_SF_sD(
      *((_QWORD *)v85 + 2),
      v86,
      (unsigned int)&WPP_173052b9a503333cb537dada0074ae31_Traceguids,
      WPP_pszIndent,
      v84);
    goto LABEL_135;
  }
  LODWORD(v128) = v111;
  *((_QWORD *)&v128 + 1) = v10;
  if ( !CertSetCertificateContextProperty(pCertContext, 0x5Bu, 0x40000000u, &v128) )
  {
LABEL_166:
    LastError = GetLastError();
    goto LABEL_135;
  }
LABEL_167:
  v98 = v118;
  if ( !CertAddCertificateContextToStore((HCERTSTORE)v118[21], pCertContext, 4u, 0) )
    goto LABEL_166;
  v99 = (_WORD *)*a3;
  v116 = 1;
  LastError = I_ReaderListBuildCredFromCertContext(v124, pCertContext, v99, SDWORD2(v123), &v117);
  if ( LastError )
  {
    WppTraceIndent(v100, 2);
    if ( WPP_GLOBAL_Control != (STRSAFE_LPSTR)&WPP_GLOBAL_Control
      && (WPP_GLOBAL_Control[28] & 1) != 0
      && (unsigned __int8)WPP_GLOBAL_Control[25] >= 2u )
    {
      WPP_SF_sD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        141,
        (unsigned int)&WPP_173052b9a503333cb537dada0074ae31_Traceguids,
        WPP_pszIndent,
        LastError);
      lpMem = v117;
      goto LABEL_135;
    }
    v28 = v117;
  }
  else
  {
    I_ReaderListAddCredToList(v117, v125, v98 + 29);
    v28 = 0;
    *v126 = 1;
  }
  v27 = v105;
LABEL_29:
  if ( p_lpMem && *((_DWORD *)p_lpMem - 2) == 1885431112 )
    ((void (*)(void))g_pfnFree)();
  if ( v11 && *((_DWORD *)v11 - 2) == 1885431112 )
    ((void (*)(void))g_pfnFree)();
  if ( v9 && *((_DWORD *)v9 - 2) == 1885431112 )
    ((void (*)(void))g_pfnFree)();
  if ( v27 && *((_DWORD *)v27 - 2) == 1885431112 )
    ((void (*)(void))g_pfnFree)();
  if ( v10 && *((_DWORD *)v10 - 2) == 1885431112 )
    ((void (*)(void))g_pfnFree)();
LABEL_185:
  v101 = phKey;
  if ( phKey )
    NCryptFreeObject(phKey);
  if ( pCertContext )
    CertFreeCertificateContext(pCertContext);
  if ( v28 )
    I_FreeCredListItem(v28);
  if ( (unsigned int)dword_180031008 > 5 && (unsigned __int8)tlgKeywordOn(v101, 0x400000000000LL) )
  {
    v112 = a5;
    p_cbOutput = (DWORD *)&v112;
    v133 = 4;
    v135 = 4;
    cbCertEncoded = *((_DWORD *)v118 + 3);
    p_cbCertEncoded = &cbCertEncoded;
    tlgCreate1Sz_wchar_t(v136, *((_QWORD *)&pvData + 1));
    v137 = &cbOutput;
    cbOutput = v116;
    v139 = &v105;
    v138 = 4;
    LODWORD(v105) = LastError;
    v140 = 4;
    tlgWriteTransfer_EventWriteTransfer(v116, &unk_18002A100, 0, 0, 7, v131);
  }
  if ( (unsigned int)dword_180031008 > 5 )
  {
    LODWORD(v105) = LastError;
    v142 = &v105;
    v143 = 4;
    tlgWriteTransfer_EventWriteTransfer(v101, &byte_180029F2F, &v130, &ActivityId, 3, v141);
  }
  EventActivityIdControl(2u, &ActivityId);
  WppTraceIndent(v102, 1);
  if ( WPP_GLOBAL_Control != (STRSAFE_LPSTR)&WPP_GLOBAL_Control
    && (WPP_GLOBAL_Control[28] & 2) != 0
    && (unsigned __int8)WPP_GLOBAL_Control[25] >= 5u )
  {
    WPP_SF_sD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      142,
      (unsigned int)&WPP_173052b9a503333cb537dada0074ae31_Traceguids,
      WPP_pszIndent,
      LastError);
  }
  return LastError;
}

```

## disassembly

```asm
0x18000b09c  push    rbp
0x18000b09e  push    rsi
0x18000b09f  push    rdi
0x18000b0a0  push    r12
0x18000b0a2  push    r13
0x18000b0a4  push    r14
0x18000b0a6  push    r15
0x18000b0a8  sub     rsp, 1D0h
0x18000b0af  lea     rbp, [rsp+30h]
0x18000b0b4  mov     [rbp+1D0h+arg_18], rbx
0x18000b0bb  mov     rax, cs:__security_cookie
0x18000b0c2  xor     rax, rbp
0x18000b0c5  mov     [rbp+1D0h+var_40], rax
0x18000b0cc  mov     rbx, [rbp+1D0h+arg_28]
0x18000b0d3  xor     esi, esi
0x18000b0d5  xorps   xmm0, xmm0
0x18000b0d8  mov     [rbp+1D0h+var_178], rdx
0x18000b0dc  mov     eax, esi
0x18000b0de  mov     [rbp+1D0h+var_130], r9
0x18000b0e5  mov     rdi, rdx
0x18000b0e8  mov     [rbp+1D0h+lpMem], rax
0x18000b0ec  xorps   xmm1, xmm1
0x18000b0ef  mov     [rbp+1D0h+var_180], rax
0x18000b0f3  xor     edx, edx
0x18000b0f5  mov     [rbp+1D0h+var_138], rcx
0x18000b0fc  mov     r12, r8
0x18000b0ff  mov     [rbp+1D0h+var_128], rbx
0x18000b106  mov     [rbp+1D0h+phKey], rsi
0x18000b10a  mov     r13d, esi
0x18000b10d  mov     [rbp+1D0h+var_1D0], rsi
0x18000b111  mov     r14d, esi
0x18000b114  mov     [rbp+1D0h+pcbResult], esi
0x18000b117  mov     r15d, esi
0x18000b11a  mov     [rbp+1D0h+var_1AC], esi
0x18000b11d  mov     [rbp+1D0h+var_1A8], esi
0x18000b120  mov     [rbp+1D0h+var_188], esi
0x18000b123  mov     [rbp+1D0h+var_170], esi
0x18000b126  mov     [rbp+1D0h+var_16C], esi
0x18000b129  mov     [rbp+1D0h+pCertContext], rsi
0x18000b12d  movups  [rbp+1D0h+pvData], xmm0
0x18000b131  mov     [rbp+1D0h+var_184], esi
0x18000b134  movups  [rbp+1D0h+var_158], xmm0
0x18000b138  movups  [rbp+1D0h+var_148], xmm0
0x18000b13f  movups  [rbp+1D0h+var_120], xmm0
0x18000b146  movups  [rbp+1D0h+var_110], xmm1
0x18000b14d  call    WppTraceIndent
0x18000b152  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b159  lea     rax, WPP_GLOBAL_Control
0x18000b160  cmp     rcx, rax
0x18000b163  jz      short loc_18000B18D
0x18000b165  test    byte ptr [rcx+1Ch], 2
0x18000b169  jz      short loc_18000B18D
0x18000b16b  cmp     byte ptr [rcx+19h], 5
0x18000b16f  jb      short loc_18000B18D
0x18000b171  mov     r9, cs:WPP_pszIndent
0x18000b178  lea     r8, WPP_173052b9a503333cb537dada0074ae31_Traceguids
0x18000b17f  mov     rcx, [rcx+10h]
0x18000b183  mov     edx, 80h
0x18000b188  call    WPP_SF_s
0x18000b18d  xorps   xmm0, xmm0
0x18000b190  lea     rdx, [rbp+1D0h+ActivityId]; ActivityId
0x18000b197  xorps   xmm1, xmm1
0x18000b19a  mov     ecx, 5; ControlCode
0x18000b19f  movups  xmmword ptr [rbp+1D0h+ActivityId.Data1], xmm0
0x18000b1a6  movups  xmmword ptr [rbp+1D0h+var_F0.Data1], xmm1
0x18000b1ad  call    cs:__imp_EventActivityIdControl
0x18000b1b3  lea     rdx, [rbp+1D0h+var_F0]; ActivityId
0x18000b1ba  mov     ecx, 1; ControlCode
0x18000b1bf  call    cs:__imp_EventActivityIdControl
0x18000b1c5  mov     eax, cs:dword_180031008
0x18000b1cb  cmp     eax, 5
0x18000b1ce  jbe     short loc_18000B1FE
0x18000b1d0  lea     rax, [rbp+1D0h+var_70]
0x18000b1d7  mov     qword ptr [rsp+200h+var_1D8], rax
0x18000b1dc  lea     r9, [rbp+1D0h+ActivityId]
0x18000b1e3  lea     r8, [rbp+1D0h+var_F0]
0x18000b1ea  mov     [rsp+200h+dwFlags], 2
0x18000b1f2  lea     rdx, byte_18002AA91
0x18000b1f9  call    _tlgWriteTransfer_EventWriteTransfer
0x18000b1fe  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000b202  mov     [rbx], esi
0x18000b204  mov     rdx, [rdi]
0x18000b207  mov     rcx, rax
0x18000b20a  inc     rcx
0x18000b20d  cmp     [rdx+rcx*2], si
0x18000b211  jnz     short loc_18000B20A
0x18000b213  mov     rdx, [r12]
0x18000b217  inc     rax
0x18000b21a  cmp     [rdx+rax*2], si
0x18000b21e  jnz     short loc_18000B217
0x18000b220  xorps   xmm0, xmm0
0x18000b223  lea     rdi, [rcx+6]
0x18000b227  add     rdi, rax
0x18000b22a  movups  [rbp+1D0h+pvData], xmm0
0x18000b22e  movups  [rbp+1D0h+var_158], xmm0
0x18000b232  lea     rbx, [rdi+rdi]
0x18000b236  movups  [rbp+1D0h+var_148], xmm0
0x18000b23d  test    rbx, rbx
0x18000b240  jz      short loc_18000B2A7
0x18000b242  cmp     rbx, cs:g_ulMaxStackAllocSize
0x18000b249  ja      short loc_18000B2A7
0x18000b24b  mov     rcx, cs:g_ulAdditionalProbeSize
0x18000b252  add     rcx, 8
0x18000b256  add     rcx, rbx
0x18000b259  cmp     rcx, rbx
0x18000b25c  jb      short loc_18000B2A7
0x18000b25e  call    VerifyStackAvailable
0x18000b263  test    eax, eax
0x18000b265  jz      short loc_18000B2A7
0x18000b267  lea     rax, [rbx+8]
0x18000b26b  lea     rcx, [rax+0Fh]
0x18000b26f  cmp     rcx, rax
0x18000b272  ja      short loc_18000B27E
0x18000b274  mov     rcx, 0FFFFFFFFFFFFFF0h
0x18000b27e  and     rcx, 0FFFFFFFFFFFFFFF0h
0x18000b282  mov     rax, rcx
0x18000b285  call    _alloca_probe
0x18000b28a  sub     rsp, rcx
0x18000b28d  lea     rsi, [rsp+200h+var_1D0]
0x18000b292  test    rsi, rsi
0x18000b295  jz      short loc_18000B2A7
0x18000b297  mov     dword ptr [rsi], 6B637453h
0x18000b29d  add     rsi, 8
0x18000b2a1  jnz     loc_18000B374
0x18000b2a7  lea     rcx, [rbx+8]
0x18000b2ab  cmp     rcx, rbx
0x18000b2ae  jb      short loc_18000B2CE
0x18000b2b0  mov     rax, cs:g_pfnAllocate
0x18000b2b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b2bc  mov     rsi, rax
0x18000b2bf  test    rax, rax
0x18000b2c2  jz      short loc_18000B2D7
0x18000b2c4  mov     dword ptr [rax], 70616548h
0x18000b2ca  add     rsi, 8
0x18000b2ce  test    rsi, rsi
0x18000b2d1  jnz     loc_18000B374
0x18000b2d7  mov     edx, 2
0x18000b2dc  call    WppTraceIndent
0x18000b2e1  mov     edi, 8
0x18000b2e6  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b2ed  lea     rbx, WPP_GLOBAL_Control
0x18000b2f4  cmp     rcx, rbx
0x18000b2f7  jz      loc_18000BFCC
0x18000b2fd  test    byte ptr [rcx+1Ch], 1
0x18000b301  jz      short loc_18000B323
0x18000b303  cmp     byte ptr [rcx+19h], 2
0x18000b307  jb      short loc_18000B323
0x18000b309  mov     r9, cs:WPP_pszIndent
0x18000b310  lea     edx, [rdi+79h]
0x18000b313  mov     rcx, [rcx+10h]
0x18000b317  lea     r8, WPP_173052b9a503333cb537dada0074ae31_Traceguids
0x18000b31e  call    WPP_SF_s
0x18000b323  mov     rbx, r13
0x18000b326  mov     r12, [rbp+1D0h+lpMem]
0x18000b32a  test    rsi, rsi
0x18000b32d  jz      short loc_18000B347
0x18000b32f  lea     rcx, [rsi-8]
0x18000b333  cmp     dword ptr [rcx], 70616548h
0x18000b339  jnz     short loc_18000B347
0x18000b33b  mov     rax, cs:g_pfnFree
0x18000b342  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b347  test    r15, r15
0x18000b34a  jz      loc_18000BDA2
0x18000b350  lea     rcx, [r15-8]
0x18000b354  mov     r15d, 70616548h
0x18000b35a  cmp     [rcx], r15d
0x18000b35d  jnz     loc_18000BDA8
0x18000b363  mov     rax, cs:g_pfnFree
0x18000b36a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b36f  jmp     loc_18000BDA8
0x18000b374  mov     rax, [r12]
0x18000b378  lea     r8, aSS_0; "\\\\.\\%s\\%s"
0x18000b37f  mov     rbx, [rbp+1D0h+var_178]
0x18000b383  mov     rdx, rdi; cchDest
0x18000b386  mov     rcx, rsi; pszDest
0x18000b389  mov     qword ptr [rsp+200h+dwFlags], rax
0x18000b38e  mov     r9, [rbx]
0x18000b391  call    StringCchPrintfW
0x18000b396  test    eax, eax
0x18000b398  jns     short loc_18000B3A1
0x18000b39a  mov     edi, 7Ah ; 'z'
0x18000b39f  jmp     short loc_18000B323
0x18000b3a1  mov     eax, [r12+14h]
0x18000b3a6  lea     rdx, [rbp+1D0h+phKey]; phKey
0x18000b3aa  mov     r9d, [r12+10h]; dwLegacyKeySpec
0x18000b3af  or      eax, 40h
0x18000b3b2  mov     rcx, [rbx+88h]; hProvider
0x18000b3b9  mov     r8, rsi; pszKeyName
0x18000b3bc  mov     [rsp+200h+dwFlags], eax; dwFlags
0x18000b3c0  xor     edi, edi
0x18000b3c2  call    cs:__imp_NCryptOpenKey
0x18000b3c8  mov     ebx, eax
0x18000b3ca  test    eax, eax
0x18000b3cc  jz      short loc_18000B41D
0x18000b3ce  lea     edx, [rdi+2]
0x18000b3d1  call    WppTraceIndent
0x18000b3d6  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b3dd  lea     rax, WPP_GLOBAL_Control
0x18000b3e4  cmp     rcx, rax
0x18000b3e7  jz      short loc_18000B415
0x18000b3e9  test    byte ptr [rcx+1Ch], 1
0x18000b3ed  jz      short loc_18000B415
0x18000b3ef  cmp     byte ptr [rcx+19h], 2
0x18000b3f3  jb      short loc_18000B415
0x18000b3f5  mov     edx, 82h
0x18000b3fa  mov     r9, cs:WPP_pszIndent
0x18000b401  lea     r8, WPP_173052b9a503333cb537dada0074ae31_Traceguids
0x18000b408  mov     rcx, [rcx+10h]
0x18000b40c  mov     [rsp+200h+dwFlags], ebx
0x18000b410  call    WPP_SF_sD
0x18000b415  mov     rbx, rdi
0x18000b418  jmp     loc_18000B326
0x18000b41d  mov     rcx, [rbp+1D0h+phKey]; hObject
0x18000b421  lea     rax, [rbp+1D0h+pcbResult]
0x18000b425  mov     [rsp+200h+var_1D8], 40h ; '@'; dwFlags
0x18000b42d  lea     rdx, aSmartcardkeyce; "SmartCardKeyCertificate"
0x18000b434  xor     r9d, r9d; cbOutput
0x18000b437  mov     qword ptr [rsp+200h+dwFlags], rax; pcbResult
0x18000b43c  xor     r8d, r8d; pbOutput
0x18000b43f  call    cs:__imp_NCryptGetProperty
0x18000b445  mov     ebx, eax
0x18000b447  test    eax, eax
0x18000b449  jz      short loc_18000B47E
0x18000b44b  mov     edx, 2
0x18000b450  call    WppTraceIndent
0x18000b455  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b45c  lea     rax, WPP_GLOBAL_Control
0x18000b463  cmp     rcx, rax
0x18000b466  jz      short loc_18000B415
0x18000b468  test    byte ptr [rcx+1Ch], 1
0x18000b46c  jz      short loc_18000B415
0x18000b46e  cmp     byte ptr [rcx+19h], 2
0x18000b472  jb      short loc_18000B415
0x18000b474  mov     edx, 83h
0x18000b479  jmp     loc_18000B3FA
0x18000b47e  mov     ebx, [rbp+1D0h+pcbResult]
0x18000b481  test    rbx, rbx
0x18000b484  jz      short loc_18000B4E9
0x18000b486  cmp     rbx, cs:g_ulMaxStackAllocSize
0x18000b48d  ja      short loc_18000B4E9
0x18000b48f  mov     rcx, cs:g_ulAdditionalProbeSize
0x18000b496  add     rcx, 8
0x18000b49a  add     rcx, rbx
0x18000b49d  cmp     rcx, rbx
0x18000b4a0  jb      short loc_18000B4E9
0x18000b4a2  call    VerifyStackAvailable
0x18000b4a7  test    eax, eax
0x18000b4a9  jz      short loc_18000B4E9
0x18000b4ab  lea     rax, [rbx+8]
0x18000b4af  lea     rcx, [rax+0Fh]
0x18000b4b3  cmp     rcx, rax
0x18000b4b6  ja      short loc_18000B4C2
0x18000b4b8  mov     rcx, 0FFFFFFFFFFFFFF0h
0x18000b4c2  and     rcx, 0FFFFFFFFFFFFFFF0h
0x18000b4c6  mov     rax, rcx
0x18000b4c9  call    _alloca_probe
0x18000b4ce  sub     rsp, rcx
0x18000b4d1  lea     r13, [rsp+200h+var_1D0]
0x18000b4d6  test    r13, r13
0x18000b4d9  jz      short loc_18000B4E9
0x18000b4db  mov     dword ptr [r13+0], 6B637453h
0x18000b4e3  add     r13, 8
0x18000b4e7  jnz     short loc_18000B510
0x18000b4e9  lea     rcx, [rbx+8]
0x18000b4ed  cmp     rcx, rbx
0x18000b4f0  jb      short loc_18000B510
0x18000b4f2  mov     rax, cs:g_pfnAllocate
0x18000b4f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b4fe  mov     r13, rax
0x18000b501  test    rax, rax
0x18000b504  jz      short loc_18000B510
0x18000b506  mov     dword ptr [rax], 70616548h
0x18000b50c  add     r13, 8
0x18000b510  test    r13, r13
0x18000b513  jnz     short loc_18000B563
0x18000b515  lea     edx, [r13+2]
0x18000b519  call    WppTraceIndent
0x18000b51e  lea     edi, [r13+8]
0x18000b522  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b529  lea     rax, WPP_GLOBAL_Control
0x18000b530  cmp     rcx, rax
0x18000b533  jz      short loc_18000B55B
0x18000b535  test    byte ptr [rcx+1Ch], 1
0x18000b539  jz      short loc_18000B55B
0x18000b53b  cmp     byte ptr [rcx+19h], 2
0x18000b53f  jb      short loc_18000B55B
0x18000b541  lea     edx, [rdi+7Ch]
0x18000b544  mov     r9, cs:WPP_pszIndent
0x18000b54b  lea     r8, WPP_173052b9a503333cb537dada0074ae31_Traceguids
0x18000b552  mov     rcx, [rcx+10h]
0x18000b556  call    WPP_SF_s
0x18000b55b  mov     rbx, r14
0x18000b55e  jmp     loc_18000B326
0x18000b563  mov     r9d, [rbp+1D0h+pcbResult]; cbOutput
0x18000b567  lea     rax, [rbp+1D0h+var_188]
0x18000b56b  mov     rcx, [rbp+1D0h+phKey]; hObject
0x18000b56f  lea     rdx, aSmartcardkeyce; "SmartCardKeyCertificate"
0x18000b576  mov     [rsp+200h+var_1D8], 40h ; '@'; dwFlags
0x18000b57e  mov     r8, r13; pbOutput
0x18000b581  mov     qword ptr [rsp+200h+dwFlags], rax; pcbResult
  ... truncated ...
```
