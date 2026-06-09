# I_ReaderListReadContainerDataPerKeyType

- ea: `0x1800205c4`
- end: `0x180020fef`
- name: `I_ReaderListReadContainerDataPerKeyType`
- size: `2603`
- prototype: `__int64 __fastcall(__int64, __int64, HCRYPTPROV, _WORD *, DWORD dwKeySpec)`
- caller_count: `2`
- callee_count: `12`
- tags: ``

## callers

- `0x180020250`
- `0x180020ff8`

## callees

- `0x180002aa0`
- `0x180004600`
- `0x18000a980`
- `0x18000cce0`
- `0x18000cda0`
- `0x18000e33c`
- `0x180016090`
- `0x180018b58`
- `0x180018bb4`
- `0x1800205c4`
- `0x180024380`
- `0x180026010`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18002069a`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x1800206ac`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180020f82`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18002069a`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x1800206ac`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180020f82`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020719`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002079a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800208eb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002094c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020acf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020c38`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020d9f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020719`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002079a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800208eb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002094c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020acf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020c38`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020d9f`
- `CRYPT32!CertSetCertificateContextProperty` at `0x180020ac5`
- `CRYPT32!CertSetCertificateContextProperty` at `0x180020c9b`
- `CRYPT32!CertSetCertificateContextProperty` at `0x180020e02`
- `CRYPT32!CertSetCertificateContextProperty` at `0x180020ac5`
- `CRYPT32!CertSetCertificateContextProperty` at `0x180020c9b`
- `CRYPT32!CertSetCertificateContextProperty` at `0x180020e02`
- `CRYPT32!CertAddCertificateContextToStore` at `0x180020e21`
- `CRYPT32!CertAddCertificateContextToStore` at `0x180020e21`
- `CRYPT32!CertFreeCertificateContext` at `0x180020eaa`
- `CRYPT32!CertFreeCertificateContext` at `0x180020eaa`
- `CRYPT32!CertCreateCertificateContext` at `0x18002093e`
- `CRYPT32!CertCreateCertificateContext` at `0x18002093e`
- `ADVAPI32!CryptGetKeyParam` at `0x18002078f`
- `ADVAPI32!CryptGetKeyParam` at `0x1800208e0`
- `ADVAPI32!CryptGetKeyParam` at `0x180020af3`
- `ADVAPI32!CryptGetKeyParam` at `0x180020b12`
- `ADVAPI32!CryptGetKeyParam` at `0x180020c2d`
- `ADVAPI32!CryptGetKeyParam` at `0x180020d94`
- `ADVAPI32!CryptGetKeyParam` at `0x18002078f`
- `ADVAPI32!CryptGetKeyParam` at `0x1800208e0`
- `ADVAPI32!CryptGetKeyParam` at `0x180020af3`
- `ADVAPI32!CryptGetKeyParam` at `0x180020b12`
- `ADVAPI32!CryptGetKeyParam` at `0x180020c2d`
- `ADVAPI32!CryptGetKeyParam` at `0x180020d94`
- `ADVAPI32!CryptGetUserKey` at `0x18002070e`
- `ADVAPI32!CryptGetUserKey` at `0x18002070e`
- `ADVAPI32!CryptDestroyKey` at `0x180020eb9`
- `ADVAPI32!CryptDestroyKey` at `0x180020eb9`

## pseudocode

```c
__int64 __fastcall I_ReaderListReadContainerDataPerKeyType(
        __int64 a1,
        __int64 a2,
        HCRYPTPROV a3,
        _WORD *a4,
        DWORD dwKeySpec)
{
  DWORD *p_pdwDataLen; // rdi
  DWORD *v7; // r14
  DWORD *v8; // rsi
  __int64 v10; // rcx
  unsigned int LastError; // ebx
  __int64 v12; // rcx
  STRSAFE_LPSTR v13; // rcx
  int v14; // edx
  __int64 v15; // rdx
  __int64 v16; // r8
  __int64 v17; // rcx
  unsigned __int64 v18; // rbx
  unsigned __int64 v19; // rcx
  __int64 v20; // rcx
  unsigned __int64 v21; // rcx
  void *v22; // rsp
  void *v23; // rsp
  DWORD *v24; // rax
  __int64 v25; // rcx
  PCCERT_CONTEXT CertificateContext; // r15
  _DWORD *p_dwVersion; // rcx
  __int64 v28; // rcx
  STRSAFE_LPSTR v29; // rcx
  int v30; // edx
  BOOL KeyParam; // ebx
  BOOL v32; // eax
  __int64 v33; // rdx
  __int64 v34; // r8
  unsigned __int64 v35; // rbx
  unsigned __int64 v36; // rcx
  __int64 v37; // rcx
  unsigned __int64 v38; // rcx
  void *v39; // rsp
  void *v40; // rsp
  DWORD *v41; // rax
  STRSAFE_LPSTR v42; // rcx
  __int64 v43; // rdx
  __int64 v44; // rcx
  __int64 v45; // rdx
  __int64 v46; // r8
  unsigned __int64 v47; // rbx
  unsigned __int64 v48; // rcx
  __int64 v49; // rcx
  unsigned __int64 v50; // rcx
  void *v51; // rsp
  void *v52; // rsp
  DWORD *v53; // rax
  __int64 v54; // rcx
  __int64 v55; // rcx
  LPVOID v56; // rcx
  __int64 v57; // rcx
  _BYTE v59[32]; // [rsp+0h] [rbp-30h] BYREF
  DWORD pdwDataLen; // [rsp+30h] [rbp+0h] BYREF
  DWORD v61; // [rsp+34h] [rbp+4h] BYREF
  DWORD v62; // [rsp+38h] [rbp+8h] BYREF
  HCRYPTKEY phUserKey; // [rsp+40h] [rbp+10h] BYREF
  unsigned int v64; // [rsp+48h] [rbp+18h] BYREF
  LPVOID lpMem; // [rsp+50h] [rbp+20h] BYREF
  DWORD dwCertEncodingType; // [rsp+58h] [rbp+28h] BYREF
  DWORD cbCertEncoded; // [rsp+5Ch] [rbp+2Ch] BYREF
  _WORD *v68; // [rsp+60h] [rbp+30h]
  __int64 v69; // [rsp+68h] [rbp+38h]
  __int128 v70; // [rsp+70h] [rbp+40h] BYREF
  __int128 v71; // [rsp+80h] [rbp+50h] BYREF
  __int128 pvData; // [rsp+90h] [rbp+60h] BYREF
  __int128 v73; // [rsp+A0h] [rbp+70h]
  __int128 v74; // [rsp+B0h] [rbp+80h]
  GUID ActivityId; // [rsp+C0h] [rbp+90h] BYREF
  GUID v76; // [rsp+D0h] [rbp+A0h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v77; // [rsp+E0h] [rbp+B0h] BYREF
  DWORD *p_dwCertEncodingType; // [rsp+100h] [rbp+D0h]
  __int64 v79; // [rsp+108h] [rbp+D8h]
  DWORD *p_cbCertEncoded; // [rsp+110h] [rbp+E0h]
  __int64 v81; // [rsp+118h] [rbp+E8h]
  unsigned int *v82; // [rsp+120h] [rbp+F0h]
  __int64 v83; // [rsp+128h] [rbp+F8h]
  _DWORD *v84; // [rsp+130h] [rbp+100h]
  __int64 v85; // [rsp+138h] [rbp+108h]
  _DWORD *v86; // [rsp+140h] [rbp+110h]
  __int64 v87; // [rsp+148h] [rbp+118h]
  struct _EVENT_DATA_DESCRIPTOR v88[2]; // [rsp+150h] [rbp+120h] BYREF
  unsigned int *v89; // [rsp+170h] [rbp+140h]
  __int64 v90; // [rsp+178h] [rbp+148h]

  v68 = a4;
  phUserKey = 0;
  lpMem = 0;
  pdwDataLen = 0;
  v61 = 0;
  p_pdwDataLen = 0;
  v62 = 0;
  v7 = 0;
  v69 = a1;
  v8 = 0;
  pvData = 0;
  v73 = 0;
  v74 = 0;
  v70 = 0;
  v71 = 0;
  WppTraceIndent(a1, 0);
  if ( WPP_GLOBAL_Control != (STRSAFE_LPSTR)&WPP_GLOBAL_Control
    && (WPP_GLOBAL_Control[28] & 2) != 0
    && (unsigned __int8)WPP_GLOBAL_Control[25] >= 5u )
  {
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 69, &WPP_173052b9a503333cb537dada0074ae31_Traceguids, WPP_pszIndent);
  }
  ActivityId = 0;
  v76 = 0;
  EventActivityIdControl(5u, &ActivityId);
  EventActivityIdControl(1u, &v76);
  if ( (unsigned int)dword_180031008 > 5 )
    tlgWriteTransfer_EventWriteTransfer(v10, (unsigned __int8 *)&dword_180029F5C, &v76, &ActivityId, 2u, v88);
  pvData = 0;
  v73 = 0;
  v74 = 0;
  if ( !CryptGetUserKey(a3, dwKeySpec, &phUserKey) )
  {
    LastError = GetLastError();
    WppTraceIndent(v12, 2);
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (STRSAFE_LPSTR)&WPP_GLOBAL_Control
      && (WPP_GLOBAL_Control[28] & 1) != 0
      && (unsigned __int8)WPP_GLOBAL_Control[25] >= 2u )
    {
      v14 = 70;
LABEL_12:
      WPP_SF_sD(
        *((_QWORD *)v13 + 2),
        v14,
        (unsigned int)&WPP_173052b9a503333cb537dada0074ae31_Traceguids,
        WPP_pszIndent,
        LastError);
      goto LABEL_106;
    }
    goto LABEL_106;
  }
  if ( CryptGetKeyParam(phUserKey, 0x1Au, 0, &pdwDataLen, 0) )
  {
    v18 = pdwDataLen;
    if ( !pdwDataLen )
      goto LABEL_26;
    if ( pdwDataLen > (unsigned __int64)g_ulMaxStackAllocSize )
      goto LABEL_26;
    v19 = pdwDataLen + g_ulAdditionalProbeSize + 8;
    if ( v19 < pdwDataLen || !(unsigned int)VerifyStackAvailable(v19, v15, v16) )
      goto LABEL_26;
    v20 = v18 + 23;
    if ( v18 + 23 <= v18 + 8 )
      v20 = 0xFFFFFFFFFFFFFF0LL;
    v21 = v20 & 0xFFFFFFFFFFFFFFF0uLL;
    v22 = alloca(v21);
    v23 = alloca(v21);
    p_pdwDataLen = &pdwDataLen;
    if ( v59 == (_BYTE *)-48LL || (pdwDataLen = 1801679955, (p_pdwDataLen = &v62) == 0) )
    {
LABEL_26:
      v21 = v18 + 8;
      if ( v18 + 8 >= v18 )
      {
        v24 = (DWORD *)((__int64 (*)(void))g_pfnAllocate)();
        p_pdwDataLen = v24;
        if ( v24 )
        {
          *v24 = 1885431112;
          p_pdwDataLen = v24 + 2;
        }
      }
    }
    if ( !p_pdwDataLen )
    {
      WppTraceIndent(v21, 2);
      LastError = 8;
      if ( WPP_GLOBAL_Control != (STRSAFE_LPSTR)&WPP_GLOBAL_Control
        && (WPP_GLOBAL_Control[28] & 1) != 0
        && (unsigned __int8)WPP_GLOBAL_Control[25] >= 2u )
      {
        WPP_SF_s(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          72,
          &WPP_173052b9a503333cb537dada0074ae31_Traceguids,
          WPP_pszIndent);
      }
      goto LABEL_106;
    }
    if ( !CryptGetKeyParam(phUserKey, 0x1Au, (BYTE *)p_pdwDataLen, &pdwDataLen, 0) )
    {
      LastError = GetLastError();
      WppTraceIndent(v25, 2);
      v13 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (STRSAFE_LPSTR)&WPP_GLOBAL_Control
        && (WPP_GLOBAL_Control[28] & 1) != 0
        && (unsigned __int8)WPP_GLOBAL_Control[25] >= 2u )
      {
        v14 = 73;
        goto LABEL_12;
      }
      goto LABEL_106;
    }
    CertificateContext = CertCreateCertificateContext(0x10001u, (const BYTE *)p_pdwDataLen, pdwDataLen);
    if ( !CertificateContext )
    {
      LastError = GetLastError();
      goto LABEL_106;
    }
    if ( (unsigned int)dword_180031008 > 5 )
    {
      p_dwVersion = &CertificateContext->pCertInfo->dwVersion;
      dwCertEncodingType = CertificateContext->dwCertEncodingType;
      v79 = 4;
      p_dwCertEncodingType = &dwCertEncodingType;
      cbCertEncoded = CertificateContext->cbCertEncoded;
      p_cbCertEncoded = &cbCertEncoded;
      v81 = 4;
      v64 = *p_dwVersion;
      v82 = &v64;
      v84 = p_dwVersion + 16;
      v86 = p_dwVersion + 18;
      v83 = 4;
      v85 = 8;
      v87 = 8;
      tlgWriteTransfer_EventWriteTransfer(
        (__int64)p_dwVersion,
        (unsigned __int8 *)word_180029E6A,
        &v76,
        &ActivityId,
        7u,
        &v77);
    }
    LastError = I_ReaderListBuildCredFromCertContext(v69, CertificateContext, v68, dwKeySpec, &lpMem);
    if ( LastError )
    {
      WppTraceIndent(v28, 2);
      v29 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (STRSAFE_LPSTR)&WPP_GLOBAL_Control
        || (WPP_GLOBAL_Control[28] & 1) == 0
        || (unsigned __int8)WPP_GLOBAL_Control[25] < 2u )
      {
        goto LABEL_105;
      }
      v30 = 74;
      goto LABEL_48;
    }
    *((_QWORD *)&pvData + 1) = *(_QWORD *)(a2 + 80);
    LODWORD(v73) = *(_DWORD *)(a2 + 120);
    *(_QWORD *)&pvData = v68;
    DWORD2(v74) = dwKeySpec;
    if ( !CertSetCertificateContextProperty(CertificateContext, 2u, 0, &pvData) )
    {
LABEL_50:
      LastError = GetLastError();
      goto LABEL_105;
    }
    KeyParam = CryptGetKeyParam(phUserKey, 0x2Bu, 0, &v61, 0x40u);
    v32 = CryptGetKeyParam(phUserKey, 0x2Cu, 0, &v62, 0x40u);
    if ( KeyParam && v32 )
    {
      v35 = v61;
      if ( !v61 )
        goto LABEL_61;
      if ( v61 > (unsigned __int64)g_ulMaxStackAllocSize )
        goto LABEL_61;
      v36 = v61 + g_ulAdditionalProbeSize + 8;
      if ( v36 < v61 || !(unsigned int)VerifyStackAvailable(v36, v33, v34) )
        goto LABEL_61;
      v37 = v35 + 23;
      if ( v35 + 23 <= v35 + 8 )
        v37 = 0xFFFFFFFFFFFFFF0LL;
      v38 = v37 & 0xFFFFFFFFFFFFFFF0uLL;
      v39 = alloca(v38);
      v40 = alloca(v38);
      v7 = &pdwDataLen;
      if ( v59 == (_BYTE *)-48LL || (pdwDataLen = 1801679955, (v7 = &v62) == 0) )
      {
LABEL_61:
        v38 = v35 + 8;
        if ( v35 + 8 >= v35 )
        {
          v41 = (DWORD *)((__int64 (*)(void))g_pfnAllocate)();
          v7 = v41;
          if ( v41 )
          {
            *v41 = 1885431112;
            v7 = v41 + 2;
          }
        }
      }
      if ( !v7 )
      {
        WppTraceIndent(v38, 2);
        LastError = 8;
        v42 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (STRSAFE_LPSTR)&WPP_GLOBAL_Control
          || (WPP_GLOBAL_Control[28] & 1) == 0
          || (unsigned __int8)WPP_GLOBAL_Control[25] < 2u )
        {
          goto LABEL_105;
        }
        v43 = 75;
        goto LABEL_69;
      }
      if ( !CryptGetKeyParam(phUserKey, 0x2Bu, (BYTE *)v7, &v61, 0x40u) )
      {
        LastError = GetLastError();
        WppTraceIndent(v44, 2);
        v29 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (STRSAFE_LPSTR)&WPP_GLOBAL_Control
          || (WPP_GLOBAL_Control[28] & 1) == 0
          || (unsigned __int8)WPP_GLOBAL_Control[25] < 2u )
        {
          goto LABEL_105;
        }
        v30 = 76;
        goto LABEL_48;
      }
      LODWORD(v70) = v61;
      *((_QWORD *)&v70 + 1) = v7;
      if ( !CertSetCertificateContextProperty(CertificateContext, 0x5Au, 0x40000000u, &v70) )
        goto LABEL_50;
      v47 = v62;
      if ( !v62 )
        goto LABEL_84;
      if ( v62 > (unsigned __int64)g_ulMaxStackAllocSize )
        goto LABEL_84;
      v48 = v62 + g_ulAdditionalProbeSize + 8;
      if ( v48 < v62 || !(unsigned int)VerifyStackAvailable(v48, v45, v46) )
        goto LABEL_84;
      v49 = v47 + 23;
      if ( v47 + 23 <= v47 + 8 )
        v49 = 0xFFFFFFFFFFFFFF0LL;
      v50 = v49 & 0xFFFFFFFFFFFFFFF0uLL;
      v51 = alloca(v50);
      v52 = alloca(v50);
      v8 = &pdwDataLen;
      if ( v59 == (_BYTE *)-48LL || (pdwDataLen = 1801679955, (v8 = &v62) == 0) )
      {
LABEL_84:
        v50 = v47 + 8;
        if ( v47 + 8 >= v47 )
        {
          v53 = (DWORD *)((__int64 (*)(void))g_pfnAllocate)();
          v8 = v53;
          if ( v53 )
          {
            *v53 = 1885431112;
            v8 = v53 + 2;
          }
        }
      }
      if ( !v8 )
      {
        WppTraceIndent(v50, 2);
        LastError = 8;
        v42 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (STRSAFE_LPSTR)&WPP_GLOBAL_Control
          || (WPP_GLOBAL_Control[28] & 1) == 0
          || (unsigned __int8)WPP_GLOBAL_Control[25] < 2u )
        {
          goto LABEL_105;
        }
        v43 = 77;
LABEL_69:
        WPP_SF_s(*((_QWORD *)v42 + 2), v43, &WPP_173052b9a503333cb537dada0074ae31_Traceguids, WPP_pszIndent);
        goto LABEL_105;
      }
      if ( !CryptGetKeyParam(phUserKey, 0x2Cu, (BYTE *)v8, &v62, 0x40u) )
      {
        LastError = GetLastError();
        WppTraceIndent(v54, 2);
        v29 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (STRSAFE_LPSTR)&WPP_GLOBAL_Control
          || (WPP_GLOBAL_Control[28] & 1) == 0
          || (unsigned __int8)WPP_GLOBAL_Control[25] < 2u )
        {
          goto LABEL_105;
        }
        v30 = 78;
LABEL_48:
        WPP_SF_sD(
          *((_QWORD *)v29 + 2),
          v30,
          (unsigned int)&WPP_173052b9a503333cb537dada0074ae31_Traceguids,
          WPP_pszIndent,
          LastError);
LABEL_105:
        CertFreeCertificateContext(CertificateContext);
        goto LABEL_106;
      }
      LODWORD(v71) = v62;
      *((_QWORD *)&v71 + 1) = v8;
      if ( !CertSetCertificateContextProperty(CertificateContext, 0x5Bu, 0x40000000u, &v71) )
        goto LABEL_50;
    }
    if ( CertAddCertificateContextToStore(*(HCERTSTORE *)(a2 + 168), CertificateContext, 4u, 0) )
    {
      LastError = I_ReaderListBuildCredFromCertContext(v69, CertificateContext, v68, dwKeySpec, &lpMem);
      if ( !LastError )
      {
        I_ReaderListAddCredToList(lpMem, *(unsigned __int16 **)(a2 + 96), (__int64 *)(a2 + 232));
        lpMem = 0;
        goto LABEL_105;
      }
      WppTraceIndent(v55, 2);
      v29 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (STRSAFE_LPSTR)&WPP_GLOBAL_Control
        || (WPP_GLOBAL_Control[28] & 1) == 0
        || (unsigned __int8)WPP_GLOBAL_Control[25] < 2u )
      {
        goto LABEL_105;
      }
      v30 = 79;
      goto LABEL_48;
    }
    goto LABEL_50;
  }
  LastError = GetLastError();
  WppTraceIndent(v17, 2);
  v13 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (STRSAFE_LPSTR)&WPP_GLOBAL_Control
    && (WPP_GLOBAL_Control[28] & 1) != 0
    && (unsigned __int8)WPP_GLOBAL_Control[25] >= 2u )
  {
    v14 = 71;
    goto LABEL_12;
  }
LABEL_106:
  if ( phUserKey )
    CryptDestroyKey(phUserKey);
  if ( p_pdwDataLen && *(p_pdwDataLen - 2) == 1885431112 )
    ((void (*)(void))g_pfnFree)();
  if ( v7 && *(v7 - 2) == 1885431112 )
    ((void (*)(void))g_pfnFree)();
  if ( v8 && *(v8 - 2) == 1885431112 )
    ((void (*)(void))g_pfnFree)();
  v56 = lpMem;
  if ( lpMem )
    I_FreeCredListItem((LPVOID *)lpMem);
  if ( (unsigned int)dword_180031008 > 5 )
  {
    v64 = LastError;
    v89 = &v64;
    v90 = 4;
    tlgWriteTransfer_EventWriteTransfer((__int64)v56, (unsigned __int8 *)&unk_18002A480, &v76, &ActivityId, 3u, v88);
  }
  EventActivityIdControl(2u, &ActivityId);
  WppTraceIndent(v57, 1);
  if ( WPP_GLOBAL_Control != (STRSAFE_LPSTR)&WPP_GLOBAL_Control
    && (WPP_GLOBAL_Control[28] & 2) != 0
    && (unsigned __int8)WPP_GLOBAL_Control[25] >= 5u )
  {
    WPP_SF_sD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      80,
      (unsigned int)&WPP_173052b9a503333cb537dada0074ae31_Traceguids,
      WPP_pszIndent,
      LastError);
  }
  return LastError;
}

```

## disassembly

```asm
0x1800205c4  push    rbp
0x1800205c6  push    rbx
0x1800205c7  push    rsi
0x1800205c8  push    rdi
0x1800205c9  push    r12
0x1800205cb  push    r13
0x1800205cd  push    r14
0x1800205cf  push    r15
0x1800205d1  sub     rsp, 198h
0x1800205d8  lea     rbp, [rsp+30h]
0x1800205dd  mov     rax, cs:__security_cookie
0x1800205e4  xor     rax, rbp
0x1800205e7  mov     [rbp+1A0h+var_50], rax
0x1800205ee  xor     r15d, r15d
0x1800205f1  mov     [rbp+1A0h+var_170], r9
0x1800205f5  xorps   xmm0, xmm0
0x1800205f8  mov     [rbp+1A0h+phUserKey], r15
0x1800205fc  mov     r13, rdx
0x1800205ff  mov     [rbp+1A0h+lpMem], r15
0x180020603  xorps   xmm1, xmm1
0x180020606  mov     [rbp+1A0h+pdwDataLen], r15d
0x18002060a  xor     edx, edx
0x18002060c  mov     [rbp+1A0h+var_19C], r15d
0x180020610  mov     edi, r15d
0x180020613  mov     [rbp+1A0h+var_198], r15d
0x180020617  mov     r14d, r15d
0x18002061a  mov     [rbp+1A0h+var_168], rcx
0x18002061e  mov     esi, r15d
0x180020621  mov     rbx, r8
0x180020624  movups  [rbp+1A0h+pvData], xmm0
0x180020628  movups  [rbp+1A0h+var_130], xmm0
0x18002062c  movups  [rbp+1A0h+var_120], xmm0
0x180020633  movups  [rbp+1A0h+var_160], xmm0
0x180020637  movups  [rbp+1A0h+var_150], xmm1
0x18002063b  call    WppTraceIndent
0x180020640  mov     rcx, cs:WPP_GLOBAL_Control
0x180020647  lea     rax, WPP_GLOBAL_Control
0x18002064e  cmp     rcx, rax
0x180020651  jz      short loc_18002067A
0x180020653  test    byte ptr [rcx+1Ch], 2
0x180020657  jz      short loc_18002067A
0x180020659  cmp     byte ptr [rcx+19h], 5
0x18002065d  jb      short loc_18002067A
0x18002065f  mov     r9, cs:WPP_pszIndent
0x180020666  lea     edx, [r15+45h]
0x18002066a  mov     rcx, [rcx+10h]
0x18002066e  lea     r8, WPP_173052b9a503333cb537dada0074ae31_Traceguids
0x180020675  call    WPP_SF_s
0x18002067a  xorps   xmm0, xmm0
0x18002067d  lea     rdx, [rbp+1A0h+ActivityId]; ActivityId
0x180020684  xorps   xmm1, xmm1
0x180020687  mov     ecx, 5; ControlCode
0x18002068c  movups  xmmword ptr [rbp+1A0h+ActivityId.Data1], xmm0
0x180020693  movups  xmmword ptr [rbp+1A0h+var_100.Data1], xmm1
0x18002069a  call    cs:__imp_EventActivityIdControl
0x1800206a0  lea     rdx, [rbp+1A0h+var_100]; ActivityId
0x1800206a7  mov     ecx, 1; ControlCode
0x1800206ac  call    cs:__imp_EventActivityIdControl
0x1800206b2  mov     eax, cs:dword_180031008
0x1800206b8  cmp     eax, 5
0x1800206bb  jbe     short loc_1800206EB
0x1800206bd  lea     rax, [rbp+1A0h+var_80]
0x1800206c4  mov     [rsp+1D0h+var_1A8], rax
0x1800206c9  lea     r9, [rbp+1A0h+ActivityId]
0x1800206d0  lea     r8, [rbp+1A0h+var_100]
0x1800206d7  mov     [rsp+1D0h+dwFlags], 2
0x1800206df  lea     rdx, dword_180029F5C
0x1800206e6  call    _tlgWriteTransfer_EventWriteTransfer
0x1800206eb  mov     r12d, [rbp+1A0h+dwKeySpec]
0x1800206f2  lea     r8, [rbp+1A0h+phUserKey]; phUserKey
0x1800206f6  xorps   xmm0, xmm0
0x1800206f9  mov     edx, r12d; dwKeySpec
0x1800206fc  mov     rcx, rbx; hProv
0x1800206ff  movups  [rbp+1A0h+pvData], xmm0
0x180020703  movups  [rbp+1A0h+var_130], xmm0
0x180020707  movups  [rbp+1A0h+var_120], xmm0
0x18002070e  call    cs:__imp_CryptGetUserKey
0x180020714  cmp     eax, 1
0x180020717  jz      short loc_18002077B
0x180020719  call    cs:__imp_GetLastError
0x18002071f  mov     edx, 2
0x180020724  mov     ebx, eax
0x180020726  call    WppTraceIndent
0x18002072b  mov     rcx, cs:WPP_GLOBAL_Control
0x180020732  lea     r12, WPP_GLOBAL_Control
0x180020739  cmp     rcx, r12
0x18002073c  jz      loc_180020EB0
0x180020742  test    byte ptr [rcx+1Ch], 1
0x180020746  jz      loc_180020EB0
0x18002074c  cmp     byte ptr [rcx+19h], 2
0x180020750  jb      loc_180020EB0
0x180020756  mov     edx, 46h ; 'F'
0x18002075b  mov     r9, cs:WPP_pszIndent
0x180020762  lea     r8, WPP_173052b9a503333cb537dada0074ae31_Traceguids
0x180020769  mov     rcx, [rcx+10h]
0x18002076d  mov     [rsp+1D0h+dwFlags], ebx
0x180020771  call    WPP_SF_sD
0x180020776  jmp     loc_180020EB0
0x18002077b  mov     rcx, [rbp+1A0h+phUserKey]; hKey
0x18002077f  lea     r9, [rbp+1A0h+pdwDataLen]; pdwDataLen
0x180020783  xor     r8d, r8d; pbData
0x180020786  mov     [rsp+1D0h+dwFlags], r15d; dwFlags
0x18002078b  lea     edx, [r8+1Ah]; dwParam
0x18002078f  call    cs:__imp_CryptGetKeyParam
0x180020795  cmp     eax, 1
0x180020798  jz      short loc_1800207E1
0x18002079a  call    cs:__imp_GetLastError
0x1800207a0  mov     edx, 2
0x1800207a5  mov     ebx, eax
0x1800207a7  call    WppTraceIndent
0x1800207ac  mov     rcx, cs:WPP_GLOBAL_Control
0x1800207b3  lea     r12, WPP_GLOBAL_Control
0x1800207ba  cmp     rcx, r12
0x1800207bd  jz      loc_180020EB0
0x1800207c3  test    byte ptr [rcx+1Ch], 1
0x1800207c7  jz      loc_180020EB0
0x1800207cd  cmp     byte ptr [rcx+19h], 2
0x1800207d1  jb      loc_180020EB0
0x1800207d7  mov     edx, 47h ; 'G'
0x1800207dc  jmp     loc_18002075B
0x1800207e1  mov     ebx, [rbp+1A0h+pdwDataLen]
0x1800207e4  test    rbx, rbx
0x1800207e7  jz      short loc_18002084A
0x1800207e9  cmp     rbx, cs:g_ulMaxStackAllocSize
0x1800207f0  ja      short loc_18002084A
0x1800207f2  mov     rcx, cs:g_ulAdditionalProbeSize
0x1800207f9  add     rcx, 8
0x1800207fd  add     rcx, rbx
0x180020800  cmp     rcx, rbx
0x180020803  jb      short loc_18002084A
0x180020805  call    VerifyStackAvailable
0x18002080a  test    eax, eax
0x18002080c  jz      short loc_18002084A
0x18002080e  lea     rax, [rbx+8]
0x180020812  lea     rcx, [rax+0Fh]
0x180020816  cmp     rcx, rax
0x180020819  ja      short loc_180020825
0x18002081b  mov     rcx, 0FFFFFFFFFFFFFF0h
0x180020825  and     rcx, 0FFFFFFFFFFFFFFF0h
0x180020829  mov     rax, rcx
0x18002082c  call    _alloca_probe
0x180020831  sub     rsp, rcx
0x180020834  lea     rdi, [rsp+1D0h+pdwDataLen]
0x180020839  test    rdi, rdi
0x18002083c  jz      short loc_18002084A
0x18002083e  mov     dword ptr [rdi], 6B637453h
0x180020844  add     rdi, 8
0x180020848  jnz     short loc_180020871
0x18002084a  lea     rcx, [rbx+8]
0x18002084e  cmp     rcx, rbx
0x180020851  jb      short loc_180020871
0x180020853  mov     rax, cs:g_pfnAllocate
0x18002085a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002085f  mov     rdi, rax
0x180020862  test    rax, rax
0x180020865  jz      short loc_180020871
0x180020867  mov     dword ptr [rax], 70616548h
0x18002086d  add     rdi, 8
0x180020871  test    rdi, rdi
0x180020874  jnz     short loc_1800208CB
0x180020876  lea     edx, [rdi+2]
0x180020879  call    WppTraceIndent
0x18002087e  lea     ebx, [rdi+8]
0x180020881  mov     rcx, cs:WPP_GLOBAL_Control
0x180020888  lea     r12, WPP_GLOBAL_Control
0x18002088f  cmp     rcx, r12
0x180020892  jz      loc_180020EB0
0x180020898  test    byte ptr [rcx+1Ch], 1
0x18002089c  jz      loc_180020EB0
0x1800208a2  cmp     byte ptr [rcx+19h], 2
0x1800208a6  jb      loc_180020EB0
0x1800208ac  mov     r9, cs:WPP_pszIndent
0x1800208b3  lea     edx, [rdi+48h]
0x1800208b6  mov     rcx, [rcx+10h]
0x1800208ba  lea     r8, WPP_173052b9a503333cb537dada0074ae31_Traceguids
0x1800208c1  call    WPP_SF_s
0x1800208c6  jmp     loc_180020EB0
0x1800208cb  mov     rcx, [rbp+1A0h+phUserKey]; hKey
0x1800208cf  lea     r9, [rbp+1A0h+pdwDataLen]; pdwDataLen
0x1800208d3  mov     r8, rdi; pbData
0x1800208d6  mov     [rsp+1D0h+dwFlags], r15d; dwFlags
0x1800208db  mov     edx, 1Ah; dwParam
0x1800208e0  call    cs:__imp_CryptGetKeyParam
0x1800208e6  cmp     eax, 1
0x1800208e9  jz      short loc_180020932
0x1800208eb  call    cs:__imp_GetLastError
0x1800208f1  mov     edx, 2
0x1800208f6  mov     ebx, eax
0x1800208f8  call    WppTraceIndent
0x1800208fd  mov     rcx, cs:WPP_GLOBAL_Control
0x180020904  lea     r12, WPP_GLOBAL_Control
0x18002090b  cmp     rcx, r12
0x18002090e  jz      loc_180020EB0
0x180020914  test    byte ptr [rcx+1Ch], 1
0x180020918  jz      loc_180020EB0
0x18002091e  cmp     byte ptr [rcx+19h], 2
0x180020922  jb      loc_180020EB0
0x180020928  mov     edx, 49h ; 'I'
0x18002092d  jmp     loc_18002075B
0x180020932  mov     r8d, [rbp+1A0h+pdwDataLen]; cbCertEncoded
0x180020936  mov     rdx, rdi; pbCertEncoded
0x180020939  mov     ecx, 10001h; dwCertEncodingType
0x18002093e  call    cs:__imp_CertCreateCertificateContext
0x180020944  mov     r15, rax
0x180020947  test    rax, rax
0x18002094a  jnz     short loc_180020960
0x18002094c  call    cs:__imp_GetLastError
0x180020952  mov     ebx, eax
0x180020954  lea     r12, WPP_GLOBAL_Control
0x18002095b  jmp     loc_180020EB0
0x180020960  mov     eax, cs:dword_180031008
0x180020966  cmp     eax, 5
0x180020969  jbe     loc_180020A21
0x18002096f  mov     rcx, [r15+18h]
0x180020973  lea     r9, [rbp+1A0h+ActivityId]
0x18002097a  mov     eax, [r15]
0x18002097d  lea     r8, [rbp+1A0h+var_100]
0x180020984  mov     [rbp+1A0h+var_178], eax
0x180020987  lea     rdx, word_180029E6A
0x18002098e  lea     rax, [rbp+1A0h+var_178]
0x180020992  mov     [rbp+1A0h+var_C8], 4
0x18002099d  mov     [rbp+1A0h+var_D0], rax
0x1800209a4  mov     eax, [r15+10h]
0x1800209a8  mov     [rbp+1A0h+var_174], eax
0x1800209ab  lea     rax, [rbp+1A0h+var_174]
0x1800209af  mov     [rbp+1A0h+var_C0], rax
0x1800209b6  mov     [rbp+1A0h+var_B8], 4
0x1800209c1  mov     eax, [rcx]
0x1800209c3  mov     [rbp+1A0h+var_188], eax
0x1800209c6  lea     rax, [rbp+1A0h+var_188]
0x1800209ca  mov     [rbp+1A0h+var_B0], rax
0x1800209d1  lea     rax, [rcx+40h]
0x1800209d5  mov     [rbp+1A0h+var_A0], rax
0x1800209dc  lea     rax, [rcx+48h]
0x1800209e0  mov     [rbp+1A0h+var_90], rax
0x1800209e7  lea     rax, [rbp+1A0h+var_F0]
0x1800209ee  mov     [rsp+1D0h+var_1A8], rax
0x1800209f3  mov     [rsp+1D0h+dwFlags], 7
0x1800209fb  mov     [rbp+1A0h+var_A8], 4
0x180020a06  mov     [rbp+1A0h+var_98], 8
0x180020a11  mov     [rbp+1A0h+var_88], 8
0x180020a1c  call    _tlgWriteTransfer_EventWriteTransfer
0x180020a21  mov     r8, [rbp+1A0h+var_170]
0x180020a25  lea     rax, [rbp+1A0h+lpMem]
0x180020a29  mov     rcx, [rbp+1A0h+var_168]
0x180020a2d  mov     r9d, r12d
0x180020a30  mov     rdx, r15
0x180020a33  mov     qword ptr [rsp+1D0h+dwFlags], rax
0x180020a38  call    I_ReaderListBuildCredFromCertContext
0x180020a3d  mov     ebx, eax
0x180020a3f  mov     edx, 2; dwPropId
0x180020a44  test    eax, eax
0x180020a46  jz      short loc_180020A9D
0x180020a48  call    WppTraceIndent
0x180020a4d  mov     rcx, cs:WPP_GLOBAL_Control
0x180020a54  lea     r12, WPP_GLOBAL_Control
0x180020a5b  cmp     rcx, r12
0x180020a5e  jz      loc_180020EA7
0x180020a64  test    byte ptr [rcx+1Ch], 1
0x180020a68  jz      loc_180020EA7
0x180020a6e  cmp     byte ptr [rcx+19h], 2
0x180020a72  jb      loc_180020EA7
0x180020a78  mov     edx, 4Ah ; 'J'
0x180020a7d  mov     r9, cs:WPP_pszIndent
0x180020a84  lea     r8, WPP_173052b9a503333cb537dada0074ae31_Traceguids
0x180020a8b  mov     rcx, [rcx+10h]
0x180020a8f  mov     [rsp+1D0h+dwFlags], ebx
0x180020a93  call    WPP_SF_sD
0x180020a98  jmp     loc_180020EA7
0x180020a9d  mov     rax, [r13+50h]
0x180020aa1  lea     r9, [rbp+1A0h+pvData]; pvData
0x180020aa5  mov     qword ptr [rbp+1A0h+pvData+8], rax
0x180020aa9  xor     r8d, r8d; dwFlags
0x180020aac  mov     eax, [r13+78h]
0x180020ab0  mov     rcx, r15; pCertContext
0x180020ab3  mov     dword ptr [rbp+1A0h+var_130], eax
0x180020ab6  mov     rax, [rbp+1A0h+var_170]
0x180020aba  mov     qword ptr [rbp+1A0h+pvData], rax
0x180020abe  mov     dword ptr [rbp+1A0h+var_120+8], r12d
0x180020ac5  call    cs:__imp_CertSetCertificateContextProperty
0x180020acb  test    eax, eax
0x180020acd  jnz     short loc_180020ADC
0x180020acf  call    cs:__imp_GetLastError
0x180020ad5  mov     ebx, eax
0x180020ad7  jmp     loc_180020EA0
0x180020adc  mov     rcx, [rbp+1A0h+phUserKey]; hKey
0x180020ae0  lea     r9, [rbp+1A0h+var_19C]; pdwDataLen
0x180020ae4  xor     r8d, r8d; pbData
0x180020ae7  mov     [rsp+1D0h+dwFlags], 40h ; '@'; dwFlags
0x180020aef  lea     edx, [r8+2Bh]; dwParam
0x180020af3  call    cs:__imp_CryptGetKeyParam
0x180020af9  mov     rcx, [rbp+1A0h+phUserKey]; hKey
0x180020afd  lea     r9, [rbp+1A0h+var_198]; pdwDataLen
0x180020b01  xor     r8d, r8d; pbData
0x180020b04  mov     [rsp+1D0h+dwFlags], 40h ; '@'; dwFlags
0x180020b0c  mov     ebx, eax
0x180020b0e  lea     edx, [r8+2Ch]; dwParam
0x180020b12  call    cs:__imp_CryptGetKeyParam
0x180020b18  test    ebx, ebx
0x180020b1a  jz      loc_180020E10
  ... truncated ...
```
