# I_RetrieveObjectByOcspUrlValidForSubject(_OCSP_CERT_ID const *,ushort const *,int,_FILETIME *,ulong,ulong,_CERT_CONTEXT const *,_CERT_CONTEXT const *,void * *,_CRYPT_GET_TIME_VALID_OBJECT_EXTRA_INFO *,ushort *)

- ea: `0x18000a9d0`
- end: `0x18000b085`
- name: `?I_RetrieveObjectByOcspUrlValidForSubject@@YAJPEBU_OCSP_CERT_ID@@PEBGHPEAU_FILETIME@@KKPEBU_CERT_CONTEXT@@3PEAPEAXPEAU_CRYPT_GET_TIME_VALID_OBJECT_EXTRA_INFO@@PEAG@Z`
- size: `1717`
- prototype: `__int64 __fastcall(const struct _OCSP_CERT_ID *, const unsigned __int16 *, int, struct _FILETIME *, unsigned int, DWORD dwTimeout, const struct _CERT_CONTEXT *, const struct _CERT_CONTEXT *, void **, struct _CRYPT_GET_TIME_VALID_OBJECT_EXTRA_INFO *, unsigned __int16 *)`
- caller_count: `2`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180009e30`
- `0x18000c300`

## callees

- `0x18000a9d0`
- `0x18000b090`
- `0x18000ba90`
- `0x18000bb78`
- `0x18000ca20`
- `0x18002656a`
- `0x1800265b0`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x18000ab50`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x18000ac19`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x18000ab50`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x18000ac19`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000ab58`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000ab6f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000ac21`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000ac38`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000ad3a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000af4d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000ab58`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000ab6f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000ac21`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000ac38`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000ad3a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000af4d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ab2b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ab34`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000abf4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000abfd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ac70`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000acef`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ae7c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000aee7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ab2b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ab34`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000abf4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000abfd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ac70`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000acef`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ae7c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000aee7`
- `CRYPT32!I_CertDiagControl` at `0x18000ad2a`
- `CRYPT32!I_CertDiagControl` at `0x18000ae66`
- `CRYPT32!I_CertDiagControl` at `0x18000aed8`
- `CRYPT32!I_CertDiagControl` at `0x18000ad2a`
- `CRYPT32!I_CertDiagControl` at `0x18000ae66`
- `CRYPT32!I_CertDiagControl` at `0x18000aed8`
- `CRYPT32!CryptMemFree` at `0x18000adce`
- `CRYPT32!CryptMemFree` at `0x18000addd`
- `CRYPT32!CryptMemFree` at `0x18000afd6`
- `CRYPT32!CryptMemFree` at `0x18000b064`
- `CRYPT32!CryptMemFree` at `0x18000b06f`
- `CRYPT32!CryptMemFree` at `0x18000b07a`
- `CRYPT32!CryptMemFree` at `0x18000adce`
- `CRYPT32!CryptMemFree` at `0x18000addd`
- `CRYPT32!CryptMemFree` at `0x18000afd6`
- `CRYPT32!CryptMemFree` at `0x18000b064`
- `CRYPT32!CryptMemFree` at `0x18000b06f`
- `CRYPT32!CryptMemFree` at `0x18000b07a`
- `CRYPT32!CertNameToStrW` at `0x18000af86`
- `CRYPT32!CertNameToStrW` at `0x18000afae`
- `CRYPT32!CertNameToStrW` at `0x18000b014`
- `CRYPT32!CertNameToStrW` at `0x18000b03c`
- `CRYPT32!CertNameToStrW` at `0x18000af86`
- `CRYPT32!CertNameToStrW` at `0x18000afae`
- `CRYPT32!CertNameToStrW` at `0x18000b014`
- `CRYPT32!CertNameToStrW` at `0x18000b03c`

## string_xrefs

- `0x18000ab19`: `CryptRetrieveObjectByUrl(CRYPT_PROXY_CACHE_RETRIEVAL)`
- `0x18000abe2`: `CryptRetrieveObjectByUrl(CRYPT_PROXY_CACHE_RETRIEVAL)`
- `0x18000b053`: `CRYPTNET.DLL --> OCSP ERROR:: %s for Subject: <%S> Issuer: <%S>\n`
- `0x18000afc5`: `CRYPTNET.DLL --> OCSP TRACE:: %s for Subject: <%S> Issuer: <%S>\n`

## pseudocode

```c
__int64 __fastcall I_RetrieveObjectByOcspUrlValidForSubject(
        const struct _OCSP_CERT_ID *a1,
        const unsigned __int16 *a2,
        int a3,
        struct _FILETIME *a4,
        unsigned int a5,
        DWORD dwTimeout,
        const struct _CERT_CONTEXT *a7,
        struct _CERT_CONTEXT *a8,
        void **a9,
        struct _CRYPT_GET_TIME_VALID_OBJECT_EXTRA_INFO *a10,
        unsigned __int16 *a11)
{
  struct _FILETIME *v11; // r12
  unsigned int v12; // ebx
  __int64 v13; // rsi
  PCERT_REVOCATION_CHAIN_PARA pChainPara; // rax
  const char *v15; // r15
  int v16; // r12d
  DWORD LastError; // r14d
  DWORD v18; // edi
  LPCWSTR v19; // r15
  unsigned int v20; // r13d
  bool v21; // zf
  const char *v22; // r12
  DWORD v23; // r14d
  DWORD v24; // edi
  __int64 result; // rax
  DWORD v26; // eax
  __int64 v27; // rdx
  int v28; // eax
  DWORD v29; // eax
  LPVOID v30; // rdx
  __int64 *v31; // r8
  __int64 v32; // rax
  int v33; // edx
  struct _CERT_CONTEXT *v34; // rdi
  struct _CERT_CONTEXT *v35; // rdi
  LPVOID v36; // [rsp+60h] [rbp-A0h] BYREF
  int v37[2]; // [rsp+68h] [rbp-98h]
  LPVOID pv; // [rsp+70h] [rbp-90h] BYREF
  int v39; // [rsp+78h] [rbp-88h]
  struct _CERT_CONTEXT *v40; // [rsp+80h] [rbp-80h]
  LPVOID v41; // [rsp+88h] [rbp-78h] BYREF
  void **v42; // [rsp+90h] [rbp-70h]
  int v43; // [rsp+98h] [rbp-68h] BYREF
  __int64 v44; // [rsp+9Ch] [rbp-64h]
  DWORD v45; // [rsp+A4h] [rbp-5Ch]
  LPCWSTR v46; // [rsp+A8h] [rbp-58h]
  _BYTE v47[24]; // [rsp+B0h] [rbp-50h]
  __int64 *v48; // [rsp+C8h] [rbp-38h]
  __int64 v49; // [rsp+D0h] [rbp-30h] BYREF
  WCHAR *v50; // [rsp+D8h] [rbp-28h]
  LPCWSTR pszUrl; // [rsp+E0h] [rbp-20h]
  __int64 v52; // [rsp+E8h] [rbp-18h]
  int v53[4]; // [rsp+F0h] [rbp-10h]
  struct _CRYPT_RETRIEVE_AUX_INFO pAuxInfo; // [rsp+100h] [rbp+0h] BYREF
  _OWORD v55[2]; // [rsp+160h] [rbp+60h] BYREF
  __int64 v56; // [rsp+180h] [rbp+80h]
  WCHAR v57[200]; // [rsp+190h] [rbp+90h] BYREF
  WCHAR psz[200]; // [rsp+320h] [rbp+220h] BYREF

  v11 = a4;
  v12 = a5;
  v52 = (__int64)a7;
  v40 = a8;
  v42 = a9;
  v50 = a11;
  *(_QWORD *)v37 = a4;
  v13 = 0;
  v39 = a3;
  pszUrl = a2;
  *(_QWORD *)v53 = a1;
  if ( (a5 & 0x1000000) != 0 )
  {
    v12 = a5 & 0xFEFFFFFF;
  }
  else if ( (a5 & 4) != 0 )
  {
    v12 = a5 | 0x200000;
  }
  while ( 1 )
  {
    if ( v13 )
    {
      result = 1;
      goto LABEL_32;
    }
    pv = 0;
    v41 = 0;
    v36 = 0;
    v49 = 0;
    memset(v55, 0, sizeof(v55));
    v56 = 0;
    LODWORD(v55[0]) = 40;
    memset_0(&pAuxInfo, 0, sizeof(pAuxInfo));
    pAuxInfo.pLastSyncTime = a10->pLastSyncTime;
    pAuxInfo.cbSize = 88;
    *pAuxInfo.pLastSyncTime = 0;
    pAuxInfo.pPreFetchInfo = (PCRYPTNET_URL_CACHE_PRE_FETCH_INFO)v55;
    pAuxInfo.ppResponseInfo = (PCRYPTNET_URL_CACHE_RESPONSE_INFO *)&v41;
    pAuxInfo.ppwszErrorResponseHeaders = (LPWSTR *)&v36;
    pAuxInfo.pwszCacheFileNamePrefix = v50;
    pChainPara = a10->pChainPara;
    if ( pChainPara && pChainPara->cbSize >= 0x38 )
      pAuxInfo.dwMaxUrlRetrievalByteCount = pChainPara->cbMaxUrlRetrievalByteCount;
    if ( (v12 & 2) == 0 || v11 )
      pAuxInfo.pftCacheResync = a10->pftCacheResync;
    v15 = "CryptRetrieveObjectByUrl(CRYPT_PROXY_CACHE_RETRIEVAL)";
    v16 = v12 & 0x200000;
    if ( (v12 & 0x200000) == 0 )
      v15 = "CryptRetrieveObjectByUrl";
    LastError = GetLastError();
    v18 = GetLastError();
    InitOnceExecuteOnce(&InitOnce, CryptNetDebugFlagsInitOnceCallback, 0, 0);
    SetLastError(v18);
    if ( (dword_180032904 & 2) != 0 )
    {
      v34 = v40;
      CertNameToStrW(1u, &v40->pCertInfo->Subject, 0x2000003u, psz, 0xC8u);
      CertNameToStrW(1u, &v34->pCertInfo->Issuer, 0x2000003u, v57, 0xC8u);
      I_CryptNetDebugTracePrintfA("CRYPTNET.DLL --> OCSP TRACE:: %s for Subject: <%S> Issuer: <%S>\n", v15, psz, v57);
    }
    SetLastError(LastError);
    v19 = pszUrl;
    if ( !CryptRetrieveObjectByUrlW(pszUrl, (LPCSTR)6, v12 & 0xFFFFDFDE | 0x2000, dwTimeout, &pv, 0, 0, 0, &pAuxInfo) )
      break;
    if ( pv && *(_DWORD *)pv && (v12 & 0x100000) == 0 )
    {
      v27 = *((_QWORD *)pv + 1);
      if ( !*(_DWORD *)v27 )
        goto LABEL_68;
      if ( *(_DWORD *)v27 == 5 )
      {
        v32 = *(_QWORD *)(v27 + 8);
        v33 = *(_DWORD *)v32 - 17433392;
        if ( *(_DWORD *)v32 == 17433392 )
          v33 = *(unsigned __int8 *)(v32 + 4) - 1;
        if ( !v33 )
        {
LABEL_68:
          pAuxInfo.dwHttpStatusCode = 404;
          SetLastError(0x80190194);
          break;
        }
      }
    }
    v13 = I_ValidateOcspResponse(
            v53[0],
            (int)v19,
            v39,
            v37[0],
            v12,
            v52,
            v40,
            (__int64)pv,
            (__int64)a10,
            (__int64)&pAuxInfo,
            (__int64)&v49);
    if ( !v13 && (v12 & 4) != 0 )
    {
      v29 = GetLastError();
      v30 = pv;
      v31 = &v49;
      v43 = 2;
      v45 = 0;
      if ( v29 == -2146762495 )
        v30 = 0;
      HIDWORD(v44) = v29;
      if ( v29 != -2146762495 )
        v31 = 0;
      *(_QWORD *)&v47[16] = v30;
      v48 = v31;
      v46 = v19;
      LODWORD(v44) = (v12 & 0x100000 | 0x200000) >> 20;
      *(_OWORD *)v47 = 0;
      I_CertDiagControl(24, &v43, 0);
    }
    if ( pv )
      CryptMemFree(pv);
    if ( v41 )
      CryptMemFree(v41);
    if ( v36 )
    {
      CryptMemFree(v36);
      v36 = 0;
    }
    v28 = v12 & 0x100000;
    if ( v13 )
    {
      v11 = *(struct _FILETIME **)v37;
      if ( v28 && (v12 & 4) != 0 )
      {
        v43 = 1;
        *(_QWORD *)v47 = &v36;
        v44 = 3;
        v45 = dwTimeout;
        v46 = v19;
        *(_OWORD *)&v47[8] = 0;
        v48 = 0;
        I_CertDiagControl(24, &v43, 0);
      }
    }
    else
    {
      if ( !v28 && GetLastError() + 2146881280 <= 0x200 )
      {
        v20 = 0;
        goto LABEL_29;
      }
      if ( !v16 || !pAuxInfo.fProxyCacheRetrieval )
      {
        v20 = -1;
        goto LABEL_29;
      }
      v11 = *(struct _FILETIME **)v37;
      v12 &= ~0x200000u;
    }
  }
  if ( pAuxInfo.dwHttpStatusCode - 404 <= 1 )
    v20 = 0;
  else
    v20 = -1;
  v21 = v16 == 0;
  v22 = "CryptRetrieveObjectByUrl";
  if ( !v21 )
    v22 = "CryptRetrieveObjectByUrl(CRYPT_PROXY_CACHE_RETRIEVAL)";
  v23 = GetLastError();
  v24 = GetLastError();
  InitOnceExecuteOnce(&InitOnce, CryptNetDebugFlagsInitOnceCallback, 0, 0);
  SetLastError(v24);
  if ( (dword_180032904 & 1) != 0 )
  {
    v35 = v40;
    CertNameToStrW(1u, &v40->pCertInfo->Subject, 0x2000003u, v57, 0xC8u);
    CertNameToStrW(1u, &v35->pCertInfo->Issuer, 0x2000003u, psz, 0xC8u);
    I_CryptNetDebugErrorPrintfA("CRYPTNET.DLL --> OCSP ERROR:: %s for Subject: <%S> Issuer: <%S>\n", v22, v57, psz);
  }
  SetLastError(v23);
  if ( (v12 & 4) != 0 )
  {
    v43 = 1;
    LODWORD(v44) = (v12 & 0x100000 | 0x200000) >> 20;
    v26 = GetLastError();
    v46 = v19;
    HIDWORD(v44) = v26;
    v45 = dwTimeout;
    v48 = 0;
    *(_QWORD *)v47 = &v36;
    *(_OWORD *)&v47[8] = 0;
    I_CertDiagControl(24, &v43, 0);
  }
  if ( pv )
    CryptMemFree(pv);
  if ( v41 )
    CryptMemFree(v41);
  if ( v36 )
    CryptMemFree(v36);
LABEL_29:
  if ( GetLastError() == -2146885628 )
    SetLastError(2u);
  result = v20;
LABEL_32:
  *v42 = (void *)v13;
  return result;
}

```

## disassembly

```asm
0x18000a9d0  push    rbp
0x18000a9d2  push    rbx
0x18000a9d3  push    rsi
0x18000a9d4  push    rdi
0x18000a9d5  push    r12
0x18000a9d7  push    r13
0x18000a9d9  lea     rbp, [rsp-3D8h]
0x18000a9e1  sub     rsp, 4D8h
0x18000a9e8  mov     rax, cs:__security_cookie
0x18000a9ef  xor     rax, rsp
0x18000a9f2  mov     [rbp+400h+var_50], rax
0x18000a9f9  mov     rax, [rbp+400h+arg_30]
0x18000aa00  mov     r12, r9
0x18000aa03  mov     ebx, [rbp+400h+arg_20]
0x18000aa09  mov     r13, [rbp+400h+arg_48]
0x18000aa10  mov     [rbp+400h+var_418], rax
0x18000aa14  mov     rax, [rbp+400h+arg_38]
0x18000aa1b  mov     [rbp+400h+var_480], rax
0x18000aa1f  mov     rax, [rbp+400h+arg_40]
0x18000aa26  mov     [rbp+400h+var_470], rax
0x18000aa2a  mov     rax, [rbp+400h+arg_50]
0x18000aa31  mov     [rbp+400h+var_428], rax
0x18000aa35  xor     eax, eax
0x18000aa37  mov     qword ptr [rsp+500h+var_498], r9
0x18000aa3c  mov     esi, eax
0x18000aa3e  mov     [rsp+500h+var_488], r8d
0x18000aa43  mov     [rbp+400h+pszUrl], rdx
0x18000aa47  mov     qword ptr [rbp+400h+var_410], rcx
0x18000aa4b  bt      ebx, 18h
0x18000aa4f  jb      loc_18000ACCF
0x18000aa55  test    bl, 4
0x18000aa58  jz      short loc_18000AA5E
0x18000aa5a  bts     ebx, 15h
0x18000aa5e  mov     [rsp+500h+var_30], r14
0x18000aa66  mov     [rsp+500h+var_38], r15
0x18000aa6e  lea     rdi, aCryptretrieveo_1; "CryptRetrieveObjectByUrl"
0x18000aa75  test    rsi, rsi
0x18000aa78  jnz     loc_18000ACC8
0x18000aa7e  xorps   xmm0, xmm0
0x18000aa81  mov     [rsp+500h+pv], rax
0x18000aa86  mov     [rbp+400h+var_478], rax
0x18000aa8a  lea     rcx, [rbp+400h+var_400]; void *
0x18000aa8e  mov     [rsp+500h+var_4A0], rax
0x18000aa93  xor     edx, edx; Val
0x18000aa95  mov     [rbp+400h+var_430], rax
0x18000aa99  mov     r8d, 58h ; 'X'; Size
0x18000aa9f  xor     eax, eax
0x18000aaa1  movups  [rbp+400h+var_3A0], xmm0
0x18000aaa5  mov     [rbp+400h+var_380], rax
0x18000aaac  mov     dword ptr [rbp+400h+var_3A0], 28h ; '('
0x18000aab3  movups  [rbp+400h+var_390], xmm0
0x18000aab7  call    memset_0
0x18000aabc  mov     rax, [r13+10h]
0x18000aac0  xor     ecx, ecx
0x18000aac2  mov     [rbp+400h+var_400.pLastSyncTime], rax
0x18000aac6  mov     [rbp+400h+var_400.cbSize], 58h ; 'X'
0x18000aacd  mov     [rax], rcx
0x18000aad0  lea     rax, [rbp+400h+var_3A0]
0x18000aad4  mov     [rbp+400h+var_400.pPreFetchInfo], rax
0x18000aad8  lea     rax, [rbp+400h+var_478]
0x18000aadc  mov     [rbp+400h+var_400.ppResponseInfo], rax
0x18000aae0  lea     rax, [rsp+500h+var_4A0]
0x18000aae5  mov     [rbp+400h+var_400.ppwszErrorResponseHeaders], rax
0x18000aae9  mov     rax, [rbp+400h+var_428]
0x18000aaed  mov     [rbp+400h+var_400.pwszCacheFileNamePrefix], rax
0x18000aaf1  mov     rax, [r13+20h]
0x18000aaf5  test    rax, rax
0x18000aaf8  jz      short loc_18000AB05
0x18000aafa  cmp     dword ptr [rax], 38h ; '8'
0x18000aafd  jb      short loc_18000AB05
0x18000aaff  mov     eax, [rax+30h]
0x18000ab02  mov     [rbp+400h+var_400.dwMaxUrlRetrievalByteCount], eax
0x18000ab05  test    bl, 2
0x18000ab08  jnz     loc_18000ACBA
0x18000ab0e  mov     rax, [r13+8]
0x18000ab12  mov     [rbp+400h+var_400.pftCacheResync], rax
0x18000ab16  mov     r12d, ebx
0x18000ab19  lea     r15, aCryptretrieveo_2; "CryptRetrieveObjectByUrl(CRYPT_PROXY_CA"...
0x18000ab20  and     r12d, 200000h
0x18000ab27  cmovz   r15, rdi
0x18000ab2b  call    cs:__imp_GetLastError
0x18000ab31  mov     r14d, eax
0x18000ab34  call    cs:__imp_GetLastError
0x18000ab3a  xor     r9d, r9d; Context
0x18000ab3d  lea     rdx, CryptNetDebugFlagsInitOnceCallback; InitFn
0x18000ab44  xor     r8d, r8d; Parameter
0x18000ab47  lea     rcx, InitOnce; InitOnce
0x18000ab4e  mov     edi, eax
0x18000ab50  call    cs:__imp_InitOnceExecuteOnce
0x18000ab56  mov     ecx, edi; dwErrCode
0x18000ab58  call    cs:__imp_SetLastError
0x18000ab5e  mov     eax, cs:dword_180032904
0x18000ab64  test    al, 2
0x18000ab66  jnz     loc_18000AF60
0x18000ab6c  mov     ecx, r14d; dwErrCode
0x18000ab6f  call    cs:__imp_SetLastError
0x18000ab75  mov     r15, [rbp+400h+pszUrl]
0x18000ab79  lea     rax, [rbp+400h+var_400]
0x18000ab7d  mov     r14d, [rbp+400h+dwTimeout]
0x18000ab84  xor     edi, edi
0x18000ab86  mov     [rsp+500h+pAuxInfo], rax; pAuxInfo
0x18000ab8b  mov     r8d, ebx
0x18000ab8e  mov     [rsp+500h+pvVerify], rdi; pvVerify
0x18000ab93  lea     rax, [rsp+500h+pv]
0x18000ab98  and     r8d, 0FFFFFFDEh
0x18000ab9c  mov     [rsp+500h+pCredentials], rdi; pCredentials
0x18000aba1  mov     [rsp+500h+hAsyncRetrieve], rdi; hAsyncRetrieve
0x18000aba6  bts     r8d, 0Dh; dwRetrievalFlags
0x18000abab  mov     r9d, r14d; dwTimeout
0x18000abae  mov     [rsp+500h+ppvObject], rax; ppvObject
0x18000abb3  mov     edx, 6; pszObjectOid
0x18000abb8  mov     rcx, r15; pszUrl
0x18000abbb  call    CryptRetrieveObjectByUrlW
0x18000abc0  test    eax, eax
0x18000abc2  jnz     loc_18000AD45
0x18000abc8  mov     eax, [rbp+400h+var_400.dwHttpStatusCode]
0x18000abcb  add     eax, 0FFFFFE6Ch
0x18000abd0  cmp     eax, 1
0x18000abd3  jbe     loc_18000AFE6
0x18000abd9  mov     r13d, 0FFFFFFFFh
0x18000abdf  test    r12d, r12d
0x18000abe2  lea     rax, aCryptretrieveo_2; "CryptRetrieveObjectByUrl(CRYPT_PROXY_CA"...
0x18000abe9  lea     r12, aCryptretrieveo_1; "CryptRetrieveObjectByUrl"
0x18000abf0  cmovnz  r12, rax
0x18000abf4  call    cs:__imp_GetLastError
0x18000abfa  mov     r14d, eax
0x18000abfd  call    cs:__imp_GetLastError
0x18000ac03  xor     r9d, r9d; Context
0x18000ac06  lea     rdx, CryptNetDebugFlagsInitOnceCallback; InitFn
0x18000ac0d  xor     r8d, r8d; Parameter
0x18000ac10  lea     rcx, InitOnce; InitOnce
0x18000ac17  mov     edi, eax
0x18000ac19  call    cs:__imp_InitOnceExecuteOnce
0x18000ac1f  mov     ecx, edi; dwErrCode
0x18000ac21  call    cs:__imp_SetLastError
0x18000ac27  mov     eax, cs:dword_180032904
0x18000ac2d  test    al, 1
0x18000ac2f  jnz     loc_18000AFEE
0x18000ac35  mov     ecx, r14d; dwErrCode
0x18000ac38  call    cs:__imp_SetLastError
0x18000ac3e  test    bl, 4
0x18000ac41  jnz     loc_18000ACD8
0x18000ac47  mov     rcx, [rsp+500h+pv]; pv
0x18000ac4c  test    rcx, rcx
0x18000ac4f  jnz     loc_18000B064
0x18000ac55  mov     rcx, [rbp+400h+var_478]; pv
0x18000ac59  test    rcx, rcx
0x18000ac5c  jnz     loc_18000B06F
0x18000ac62  mov     rcx, [rsp+500h+var_4A0]; pv
0x18000ac67  test    rcx, rcx
0x18000ac6a  jnz     loc_18000B07A
0x18000ac70  call    cs:__imp_GetLastError
0x18000ac76  cmp     eax, 80092004h
0x18000ac7b  jz      loc_18000AD35
0x18000ac81  mov     eax, r13d
0x18000ac84  mov     rcx, [rbp+400h+var_470]
0x18000ac88  mov     [rcx], rsi
0x18000ac8b  mov     r15, [rsp+500h+var_38]
0x18000ac93  mov     r14, [rsp+500h+var_30]
0x18000ac9b  mov     rcx, [rbp+400h+var_50]
0x18000aca2  xor     rcx, rsp; StackCookie
0x18000aca5  call    __security_check_cookie
0x18000acaa  add     rsp, 4D8h
0x18000acb1  pop     r13
0x18000acb3  pop     r12
0x18000acb5  pop     rdi
0x18000acb6  pop     rsi
0x18000acb7  pop     rbx
0x18000acb8  pop     rbp
0x18000acb9  retn
0x18000acba  test    r12, r12
0x18000acbd  jz      loc_18000AB16
0x18000acc3  jmp     loc_18000AB0E
0x18000acc8  mov     eax, 1
0x18000accd  jmp     short loc_18000AC84
0x18000accf  btr     ebx, 18h
0x18000acd3  jmp     loc_18000AA5E
0x18000acd8  and     ebx, 100000h
0x18000acde  mov     [rbp+400h+var_468], 1
0x18000ace5  bts     ebx, 15h
0x18000ace9  shr     ebx, 14h
0x18000acec  mov     dword ptr [rbp+400h+var_464], ebx
0x18000acef  call    cs:__imp_GetLastError
0x18000acf5  xorps   xmm0, xmm0
0x18000acf8  mov     [rbp+400h+var_458], r15
0x18000acfc  mov     dword ptr [rbp+400h+var_464+4], eax
0x18000acff  lea     rdx, [rbp+400h+var_468]
0x18000ad03  mov     eax, [rbp+400h+dwTimeout]
0x18000ad09  xor     r8d, r8d
0x18000ad0c  mov     [rbp+400h+var_45C], eax
0x18000ad0f  mov     ecx, 18h
0x18000ad14  lea     rax, [rsp+500h+var_4A0]
0x18000ad19  mov     [rbp+400h+var_438], 0
0x18000ad21  mov     qword ptr [rbp+400h+var_450], rax
0x18000ad25  movdqu  xmmword ptr [rbp+400h+var_450+8], xmm0
0x18000ad2a  call    cs:__imp_I_CertDiagControl
0x18000ad30  jmp     loc_18000AC47
0x18000ad35  mov     ecx, 2; dwErrCode
0x18000ad3a  call    cs:__imp_SetLastError
0x18000ad40  jmp     loc_18000AC81
0x18000ad45  mov     rcx, [rsp+500h+pv]
0x18000ad4a  test    rcx, rcx
0x18000ad4d  jz      short loc_18000AD70
0x18000ad4f  cmp     [rcx], edi
0x18000ad51  jz      short loc_18000AD70
0x18000ad53  bt      ebx, 14h
0x18000ad57  jb      short loc_18000AD70
0x18000ad59  mov     rdx, [rcx+8]
0x18000ad5d  mov     eax, [rdx]
0x18000ad5f  test    eax, eax
0x18000ad61  jz      loc_18000AF41
0x18000ad67  cmp     eax, 5
0x18000ad6a  jz      loc_18000AF1E
0x18000ad70  mov     r9, qword ptr [rsp+500h+var_498]; int
0x18000ad75  lea     rax, [rbp+400h+var_430]
0x18000ad79  mov     r8d, [rsp+500h+var_488]; int
0x18000ad7e  mov     rdx, r15; int
0x18000ad81  mov     [rsp+500h+var_4B0], rax; __int64
0x18000ad86  lea     rax, [rbp+400h+var_400]
0x18000ad8a  mov     [rsp+500h+var_4B8], rax; __int64
0x18000ad8f  mov     rax, [rbp+400h+var_480]
0x18000ad93  mov     [rsp+500h+pAuxInfo], r13; __int64
0x18000ad98  mov     [rsp+500h+pvVerify], rcx; __int64
0x18000ad9d  mov     rcx, qword ptr [rbp+400h+var_410]; int
0x18000ada1  mov     [rsp+500h+pCredentials], rax; struct _CERT_CONTEXT *
0x18000ada6  mov     rax, [rbp+400h+var_418]
0x18000adaa  mov     [rsp+500h+hAsyncRetrieve], rax; __int64
0x18000adaf  mov     dword ptr [rsp+500h+ppvObject], ebx; unsigned int
0x18000adb3  call    I_ValidateOcspResponse
0x18000adb8  mov     rsi, rax
0x18000adbb  test    rax, rax
0x18000adbe  jz      loc_18000AE73
0x18000adc4  mov     rcx, [rsp+500h+pv]; pv
0x18000adc9  test    rcx, rcx
0x18000adcc  jz      short loc_18000ADD4
0x18000adce  call    cs:__imp_CryptMemFree
0x18000add4  mov     rcx, [rbp+400h+var_478]; pv
0x18000add8  test    rcx, rcx
0x18000addb  jz      short loc_18000ADE3
0x18000addd  call    cs:__imp_CryptMemFree
0x18000ade3  mov     rcx, [rsp+500h+var_4A0]; pv
0x18000ade8  test    rcx, rcx
0x18000adeb  jnz     loc_18000AFD6
0x18000adf1  mov     eax, ebx
0x18000adf3  and     eax, 100000h
0x18000adf8  test    rsi, rsi
0x18000adfb  jz      loc_18000AEE3
0x18000ae01  mov     r12, qword ptr [rsp+500h+var_498]
0x18000ae06  lea     rdi, aCryptretrieveo_1; "CryptRetrieveObjectByUrl"
0x18000ae0d  test    eax, eax
0x18000ae0f  mov     eax, 0
0x18000ae14  jz      loc_18000AA75
0x18000ae1a  lea     rdi, aCryptretrieveo_1; "CryptRetrieveObjectByUrl"
0x18000ae21  test    bl, 4
0x18000ae24  jz      loc_18000AA75
0x18000ae2a  lea     rax, [rsp+500h+var_4A0]
0x18000ae2f  mov     [rbp+400h+var_468], 1
0x18000ae36  xorps   xmm0, xmm0
0x18000ae39  mov     qword ptr [rbp+400h+var_450], rax
0x18000ae3d  xor     r8d, r8d
0x18000ae40  mov     [rbp+400h+var_464], 3
0x18000ae48  lea     rdx, [rbp+400h+var_468]
0x18000ae4c  mov     [rbp+400h+var_45C], r14d
0x18000ae50  mov     ecx, 18h
0x18000ae55  mov     [rbp+400h+var_458], r15
0x18000ae59  movdqu  xmmword ptr [rbp+400h+var_450+8], xmm0
0x18000ae5e  mov     [rbp+400h+var_438], 0
0x18000ae66  call    cs:__imp_I_CertDiagControl
0x18000ae6c  xor     eax, eax
0x18000ae6e  jmp     loc_18000AA6E
0x18000ae73  test    bl, 4
0x18000ae76  jz      loc_18000ADC4
0x18000ae7c  call    cs:__imp_GetLastError
0x18000ae82  mov     rdx, [rsp+500h+pv]
0x18000ae87  lea     r8, [rbp+400h+var_430]
0x18000ae8b  cmp     eax, 800B0101h
0x18000ae90  mov     [rbp+400h+var_468], 2
0x18000ae97  mov     ecx, eax
0x18000ae99  mov     [rbp+400h+var_45C], edi
0x18000ae9c  cmovz   rdx, rdi
0x18000aea0  mov     dword ptr [rbp+400h+var_464+4], ecx
0x18000aea3  cmovnz  r8, rdi
0x18000aea7  mov     qword ptr [rbp+400h+var_450+10h], rdx
0x18000aeab  mov     eax, ebx
0x18000aead  mov     [rbp+400h+var_438], r8
0x18000aeb1  and     eax, 100000h
0x18000aeb6  mov     [rbp+400h+var_458], r15
0x18000aeba  bts     eax, 15h
0x18000aebe  lea     rdx, [rbp+400h+var_468]
0x18000aec2  shr     eax, 14h
0x18000aec5  xorps   xmm0, xmm0
0x18000aec8  xor     r8d, r8d
0x18000aecb  mov     dword ptr [rbp+400h+var_464], eax
0x18000aece  mov     ecx, 18h
0x18000aed3  movdqu  xmmword ptr [rbp+400h+var_450], xmm0
0x18000aed8  call    cs:__imp_I_CertDiagControl
0x18000aede  jmp     loc_18000ADC4
0x18000aee3  test    eax, eax
0x18000aee5  jnz     short loc_18000AEF9
0x18000aee7  call    cs:__imp_GetLastError
  ... truncated ...
```
