# _RetrieveCrlPreFetchCrl

- ea: `0x18001f61c`
- end: `0x18001f9ea`
- name: `_RetrieveCrlPreFetchCrl`
- size: `974`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `13`
- tags: `file_ops, installer_update, broker_com_uri`

## callers

- `0x18001e834`

## callees

- `0x180007c00`
- `0x18000a990`
- `0x18000b090`
- `0x18000cfa0`
- `0x18001e720`
- `0x18001f26c`
- `0x18001f310`
- `0x18001f3e0`
- `0x18001f61c`
- `0x180026546`
- `0x180026552`
- `0x18002656a`
- `0x1800265b0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f847`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f847`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18001f6a0`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18001f6a0`
- `CRYPT32!CertCloseStore` at `0x18001f9b1`
- `CRYPT32!CertCloseStore` at `0x18001f9b1`
- `CRYPT32!CertFreeCRLContext` at `0x18001f8d4`
- `CRYPT32!CertFreeCRLContext` at `0x18001f99f`
- `CRYPT32!CertFreeCRLContext` at `0x18001f8d4`
- `CRYPT32!CertFreeCRLContext` at `0x18001f99f`
- `CRYPT32!CertFindCertificateInCRL` at `0x18001f8ca`
- `CRYPT32!CertFindCertificateInCRL` at `0x18001f8ca`
- `CRYPT32!CryptMemFree` at `0x18001f782`
- `CRYPT32!CryptMemFree` at `0x18001f9c1`
- `CRYPT32!CryptMemFree` at `0x18001f782`
- `CRYPT32!CryptMemFree` at `0x18001f9c1`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18001f89e`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18001f89e`

## string_xrefs

- `0x18001f7d2`: `CacheRetrieveError`
- `0x18001f8da`: `UPDATED`

## pseudocode

```c
__int64 __fastcall RetrieveCrlPreFetchCrl(__int64 a1)
{
  unsigned int v2; // r12d
  const CRL_CONTEXT *v3; // rsi
  DWORD v4; // r9d
  const unsigned __int16 **v5; // r14
  const WCHAR *v6; // rcx
  int v7; // edi
  const char *v8; // rdi
  HCERTSTORE v9; // rcx
  DWORD LastError; // r15d
  const CRL_CONTEXT *v11; // rax
  __int64 v12; // rdi
  DWORD cbCrlEncoded; // eax
  void *v14; // rcx
  _QWORD *v15; // rax
  __int64 v16; // rcx
  __int64 v17; // rax
  unsigned __int64 v18; // r14
  void *v19; // rax
  LPVOID pv; // [rsp+70h] [rbp-90h] BYREF
  HCERTSTORE hCertStore; // [rsp+78h] [rbp-88h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+80h] [rbp-80h] BYREF
  __int64 v24; // [rsp+88h] [rbp-78h] BYREF
  PCRL_ENTRY ppCrlEntry; // [rsp+90h] [rbp-70h] BYREF
  struct _CRYPT_GET_TIME_VALID_OBJECT_EXTRA_INFO v26; // [rsp+98h] [rbp-68h] BYREF
  struct _CRYPT_RETRIEVE_AUX_INFO pAuxInfo; // [rsp+D0h] [rbp-30h] BYREF
  __int128 v28; // [rsp+130h] [rbp+30h] BYREF
  _OWORD v29[2]; // [rsp+140h] [rbp+40h] BYREF
  __int64 v30; // [rsp+160h] [rbp+60h]

  ppCrlEntry = 0;
  hCertStore = 0;
  *(_QWORD *)&v26.iDeltaCrlIndicator = 0;
  HIDWORD(v26.pftCacheResync) = 0;
  v2 = 0;
  v3 = 0;
  *(_OWORD *)&v26.pChainPara = 0;
  memset_0(&pAuxInfo, 0, sizeof(pAuxInfo));
  pv = 0;
  v24 = 0;
  v30 = 0;
  memset(v29, 0, sizeof(v29));
  SystemTimeAsFileTime = 0;
  v28 = 0;
  GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
  v4 = 1000 * *(_DWORD *)(a1 + 120);
  v26.pLastSyncTime = (LPFILETIME)(a1 + 96);
  pAuxInfo.pLastSyncTime = (FILETIME *)(a1 + 96);
  v5 = (const unsigned __int16 **)(a1 + 88);
  pAuxInfo.cbSize = 88;
  pAuxInfo.pPreFetchInfo = (PCRYPTNET_URL_CACHE_PRE_FETCH_INFO)v29;
  v26.pMaxAgeTime = (LPFILETIME)&v24;
  v6 = *(const WCHAR **)(a1 + 88);
  v7 = 4202501;
  pAuxInfo.pFlushInfo = (PCRYPTNET_URL_CACHE_FLUSH_INFO)&v28;
  v26.cbSize = 48;
  pAuxInfo.ppResponseInfo = (PCRYPTNET_URL_CACHE_RESPONSE_INFO *)&pv;
  LODWORD(v29[0]) = 40;
  LODWORD(v28) = 16;
  if ( !CryptRetrieveObjectByUrlW(v6, (LPCSTR)2, 0x402005u, v4, &hCertStore, 0, 0, 0, &pAuxInfo) )
  {
    v8 = "RetrieveError";
LABEL_13:
    LastError = GetLastError();
    LogCryptnetError(0x1021u, *v5, LastError);
    goto LABEL_30;
  }
  v9 = hCertStore;
  LastError = 0;
  if ( !hCertStore )
  {
    if ( !(unsigned int)IsUpdatedHttpResponse(a1) )
    {
      v8 = "NotModified";
      goto LABEL_30;
    }
    LogCrlPreFetchEvent("OtherProcessGet", a1, 0);
    if ( pv )
    {
      CryptMemFree(pv);
      pv = 0;
    }
    v7 = 11;
    if ( !CryptRetrieveObjectByUrlW(*v5, (LPCSTR)2, 0xBu, 0, &hCertStore, 0, 0, 0, &pAuxInfo) || (v9 = hCertStore) == 0 )
    {
      v8 = "CacheRetrieveError";
      goto LABEL_13;
    }
  }
  v11 = (const CRL_CONTEXT *)I_ValidateObjectForSubject(
                               1,
                               1,
                               (unsigned __int16 *)*v5,
                               (const char *)2,
                               0,
                               &SystemTimeAsFileTime,
                               v7 | 0x20u,
                               *(const struct _CERT_CONTEXT **)(a1 + 72),
                               *(void **)(a1 + 80),
                               (unsigned __int8 *const)(a1 + 32),
                               &v26,
                               v9,
                               &pAuxInfo);
  v3 = v11;
  if ( !v11 )
  {
    v8 = "ValidateError";
    goto LABEL_13;
  }
  v12 = *(_QWORD *)(a1 + 64);
  cbCrlEncoded = v11->cbCrlEncoded;
  if ( cbCrlEncoded == *(_DWORD *)(v12 + 16) && !memcmp_0(v3->pbCrlEncoded, *(const void **)(v12 + 8), cbCrlEncoded) )
  {
    v8 = "SameContents";
  }
  else
  {
    if ( CompareFileTime(&v3->pCrlInfo->ThisUpdate, (const FILETIME *)(*(_QWORD *)(v12 + 24) + 48LL)) < 0 )
    {
      v8 = "OlderCrl";
      goto LABEL_30;
    }
    CertFindCertificateInCRL(*(PCCERT_CONTEXT *)(a1 + 80), v3, 0, 0, &ppCrlEntry);
    CertFreeCRLContext(*(PCCRL_CONTEXT *)(a1 + 64));
    v8 = "UPDATED";
    v2 = 1;
    *(_QWORD *)(a1 + 64) = v3;
    v3 = 0;
    if ( !*(_DWORD *)(a1 + 140) )
      LogCryptnetEvent(4, 4128, 1, a1 + 88);
  }
  *(_QWORD *)(a1 + 104) = 0;
  v14 = *(void **)(a1 + 112);
  if ( v14 )
  {
    operator delete(v14);
    *(_QWORD *)(a1 + 112) = 0;
  }
  v15 = pv;
  if ( pv )
  {
    v16 = *((_QWORD *)pv + 3);
    if ( !v16 )
    {
LABEL_29:
      *(_QWORD *)(a1 + 104) = v15[1];
      goto LABEL_30;
    }
    v17 = -1;
    do
      ++v17;
    while ( *(_WORD *)(v16 + 2 * v17) );
    v18 = (int)v17 + 1;
    v19 = operator new(saturated_mul(v18, 2u));
    *(_QWORD *)(a1 + 112) = v19;
    if ( v19 )
    {
      memcpy_0(v19, *((const void **)pv + 3), 2 * v18);
      v15 = pv;
      goto LABEL_29;
    }
  }
LABEL_30:
  LogCrlPreFetchEvent(v8, a1, LastError);
  if ( v3 )
    CertFreeCRLContext(v3);
  if ( hCertStore )
    CertCloseStore(hCertStore, 0);
  if ( pv )
    CryptMemFree(pv);
  return v2;
}

```

## disassembly

```asm
0x18001f61c  push    rbp
0x18001f61e  push    rbx
0x18001f61f  push    rsi
0x18001f620  push    rdi
0x18001f621  push    r12
0x18001f623  push    r13
0x18001f625  push    r14
0x18001f627  push    r15
0x18001f629  lea     rbp, [rsp-78h]
0x18001f62e  sub     rsp, 178h
0x18001f635  mov     rax, cs:__security_cookie
0x18001f63c  xor     rax, rsp
0x18001f63f  mov     [rbp+0B0h+var_48], rax
0x18001f643  xor     r13d, r13d
0x18001f646  mov     rbx, rcx
0x18001f649  xorps   xmm0, xmm0
0x18001f64c  mov     [rbp+0B0h+ppCrlEntry], r13
0x18001f650  xor     edx, edx; Val
0x18001f652  mov     [rsp+1B0h+hCertStore], r13
0x18001f657  lea     rcx, [rbp+0B0h+var_E0]; void *
0x18001f65b  mov     qword ptr [rbp+0B0h+var_118.iDeltaCrlIndicator], r13
0x18001f65f  lea     edi, [r13+58h]
0x18001f663  mov     dword ptr [rbp+0B0h+var_118.pftCacheResync+4], r13d
0x18001f667  mov     r8d, edi; Size
0x18001f66a  mov     r12d, r13d
0x18001f66d  mov     esi, r13d
0x18001f670  movdqu  xmmword ptr [rbp+0B0h+var_118.pChainPara], xmm0
0x18001f675  call    memset_0
0x18001f67a  xorps   xmm0, xmm0
0x18001f67d  mov     [rsp+1B0h+pv], r13
0x18001f682  xor     eax, eax
0x18001f684  mov     [rbp+0B0h+var_128], r13
0x18001f688  lea     rcx, [rbp+0B0h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18001f68c  mov     [rbp+0B0h+var_50], rax
0x18001f690  movups  [rbp+0B0h+var_70], xmm0
0x18001f694  mov     qword ptr [rbp+0B0h+SystemTimeAsFileTime.dwLowDateTime], r13
0x18001f698  movups  [rbp+0B0h+var_60], xmm0
0x18001f69c  movups  [rbp+0B0h+var_80], xmm0
0x18001f6a0  call    cs:__imp_GetSystemTimeAsFileTime
0x18001f6a6  imul    r9d, [rbx+78h], 3E8h; dwTimeout
0x18001f6ae  lea     rax, [rbx+60h]
0x18001f6b2  mov     [rbp+0B0h+var_118.pLastSyncTime], rax
0x18001f6b6  lea     rcx, [rbp+0B0h+var_128]
0x18001f6ba  mov     [rbp+0B0h+var_E0.pLastSyncTime], rax
0x18001f6be  lea     r14, [rbx+58h]
0x18001f6c2  lea     rax, [rbp+0B0h+var_70]
0x18001f6c6  mov     [rbp+0B0h+var_E0.cbSize], edi
0x18001f6c9  mov     [rbp+0B0h+var_E0.pPreFetchInfo], rax
0x18001f6cd  lea     edx, [r13+2]; pszObjectOid
0x18001f6d1  lea     rax, [rbp+0B0h+var_80]
0x18001f6d5  mov     [rbp+0B0h+var_118.pMaxAgeTime], rcx
0x18001f6d9  mov     rcx, [r14]; pszUrl
0x18001f6dc  mov     edi, 402005h
0x18001f6e1  mov     [rbp+0B0h+var_E0.pFlushInfo], rax
0x18001f6e5  mov     r8d, edi; dwRetrievalFlags
0x18001f6e8  lea     rax, [rsp+1B0h+pv]
0x18001f6ed  mov     [rbp+0B0h+var_118.cbSize], 30h ; '0'
0x18001f6f4  mov     [rbp+0B0h+var_E0.ppResponseInfo], rax
0x18001f6f8  lea     rax, [rbp+0B0h+var_E0]
0x18001f6fc  mov     [rsp+1B0h+pAuxInfo], rax; pAuxInfo
0x18001f701  lea     rax, [rsp+1B0h+hCertStore]
0x18001f706  mov     [rsp+1B0h+pvVerify], r13; pvVerify
0x18001f70b  mov     [rsp+1B0h+pCredentials], r13; pCredentials
0x18001f710  mov     [rsp+1B0h+hAsyncRetrieve], r13; hAsyncRetrieve
0x18001f715  mov     [rsp+1B0h+ppvObject], rax; ppvObject
0x18001f71a  mov     dword ptr [rbp+0B0h+var_70], 28h ; '('
0x18001f721  mov     dword ptr [rbp+0B0h+var_80], 10h
0x18001f728  call    CryptRetrieveObjectByUrlW
0x18001f72d  test    eax, eax
0x18001f72f  jnz     short loc_18001F73D
0x18001f731  lea     rdi, aRetrieveerror; "RetrieveError"
0x18001f738  jmp     loc_18001F847
0x18001f73d  mov     rcx, [rsp+1B0h+hCertStore]
0x18001f742  mov     r15d, r13d
0x18001f745  test    rcx, rcx
0x18001f748  jnz     loc_18001F7DB
0x18001f74e  mov     rcx, rbx
0x18001f751  call    _IsUpdatedHttpResponse
0x18001f756  test    eax, eax
0x18001f758  jnz     short loc_18001F766
0x18001f75a  lea     rdi, aNotmodified; "NotModified"
0x18001f761  jmp     loc_18001F989
0x18001f766  xor     r8d, r8d
0x18001f769  lea     rcx, aOtherprocessge; "OtherProcessGet"
0x18001f770  mov     rdx, rbx
0x18001f773  call    _LogCrlPreFetchEvent
0x18001f778  mov     rcx, [rsp+1B0h+pv]; pv
0x18001f77d  test    rcx, rcx
0x18001f780  jz      short loc_18001F78D
0x18001f782  call    cs:__imp_CryptMemFree
0x18001f788  mov     [rsp+1B0h+pv], r13
0x18001f78d  mov     rcx, [r14]; pszUrl
0x18001f790  lea     rax, [rbp+0B0h+var_E0]
0x18001f794  mov     [rsp+1B0h+pAuxInfo], rax; pAuxInfo
0x18001f799  xor     r9d, r9d; dwTimeout
0x18001f79c  mov     [rsp+1B0h+pvVerify], r13; pvVerify
0x18001f7a1  lea     rax, [rsp+1B0h+hCertStore]
0x18001f7a6  mov     [rsp+1B0h+pCredentials], r13; pCredentials
0x18001f7ab  mov     [rsp+1B0h+hAsyncRetrieve], r13; hAsyncRetrieve
0x18001f7b0  lea     edi, [r9+0Bh]
0x18001f7b4  mov     [rsp+1B0h+ppvObject], rax; ppvObject
0x18001f7b9  mov     r8d, edi; dwRetrievalFlags
0x18001f7bc  lea     edx, [rdi-9]; pszObjectOid
0x18001f7bf  call    CryptRetrieveObjectByUrlW
0x18001f7c4  test    eax, eax
0x18001f7c6  jz      short loc_18001F7D2
0x18001f7c8  mov     rcx, [rsp+1B0h+hCertStore]
0x18001f7cd  test    rcx, rcx
0x18001f7d0  jnz     short loc_18001F7DB
0x18001f7d2  lea     rdi, aCacheretrievee; "CacheRetrieveError"
0x18001f7d9  jmp     short loc_18001F847
0x18001f7db  mov     r8, [r14]; unsigned __int16 *
0x18001f7de  lea     rdx, [rbp+0B0h+var_E0]
0x18001f7e2  mov     [rsp+1B0h+var_150], rdx; struct _CRYPT_RETRIEVE_AUX_INFO *
0x18001f7e7  lea     rax, [rbx+20h]
0x18001f7eb  mov     [rsp+1B0h+var_158], rcx; void *
0x18001f7f0  mov     r9d, 2; char *
0x18001f7f6  lea     rcx, [rbp+0B0h+var_118]
0x18001f7fa  or      edi, 20h
0x18001f7fd  mov     [rsp+1B0h+var_160], rcx; struct _CRYPT_GET_TIME_VALID_OBJECT_EXTRA_INFO *
0x18001f802  mov     [rsp+1B0h+var_168], rax; unsigned __int8 *
0x18001f807  mov     rax, [rbx+50h]
0x18001f80b  mov     [rsp+1B0h+pAuxInfo], rax; void *
0x18001f810  mov     rax, [rbx+48h]
0x18001f814  mov     [rsp+1B0h+pvVerify], rax; struct _CERT_CONTEXT *
0x18001f819  lea     rax, [rbp+0B0h+SystemTimeAsFileTime]
0x18001f81d  mov     dword ptr [rsp+1B0h+pCredentials], edi; unsigned int
0x18001f821  mov     [rsp+1B0h+hAsyncRetrieve], rax; struct _FILETIME *
0x18001f826  lea     eax, [r9-1]
0x18001f82a  mov     edx, eax; int
0x18001f82c  mov     dword ptr [rsp+1B0h+ppvObject], r13d; int
0x18001f831  mov     ecx, eax; int
0x18001f833  call    ?I_ValidateObjectForSubject@@YAPEAXHHPEAGPEBDHPEAU_FILETIME@@KPEBU_CERT_CONTEXT@@PEAXQEAEPEAU_CRYPT_GET_TIME_VALID_OBJECT_EXTRA_INFO@@4PEAU_CRYPT_RETRIEVE_AUX_INFO@@@Z; I_ValidateObjectForSubject(int,int,ushort *,char const *,int,_FILETIME *,ulong,_CERT_CONTEXT const *,void *,uchar * const,_CRYPT_GET_TIME_VALID_OBJECT_EXTRA_INFO *,void *,_CRYPT_RETRIEVE_AUX_INFO *)
0x18001f838  mov     rsi, rax
0x18001f83b  test    rax, rax
0x18001f83e  jnz     short loc_18001F865
0x18001f840  lea     rdi, aValidateerror; "ValidateError"
0x18001f847  call    cs:__imp_GetLastError
0x18001f84d  mov     rdx, [r14]; unsigned __int16 *
0x18001f850  mov     ecx, 1021h; unsigned int
0x18001f855  mov     r8d, eax; unsigned int
0x18001f858  mov     r15d, eax
0x18001f85b  call    ?LogCryptnetError@@YAXKPEBGK@Z; LogCryptnetError(ulong,ushort const *,ulong)
0x18001f860  jmp     loc_18001F989
0x18001f865  mov     rdi, [rbx+40h]
0x18001f869  mov     eax, [rax+10h]
0x18001f86c  cmp     eax, [rdi+10h]
0x18001f86f  jnz     short loc_18001F88E
0x18001f871  mov     rdx, [rdi+8]; Buf2
0x18001f875  mov     r8d, eax; Size
0x18001f878  mov     rcx, [rsi+8]; Buf1
0x18001f87c  call    memcmp_0
0x18001f881  test    eax, eax
0x18001f883  jnz     short loc_18001F88E
0x18001f885  lea     rdi, aSamecontents; "SameContents"
0x18001f88c  jmp     short loc_18001F90B
0x18001f88e  mov     rdx, [rdi+18h]
0x18001f892  mov     rcx, [rsi+18h]
0x18001f896  add     rdx, 30h ; '0'; lpFileTime2
0x18001f89a  add     rcx, 30h ; '0'; lpFileTime1
0x18001f89e  call    cs:__imp_CompareFileTime
0x18001f8a4  test    eax, eax
0x18001f8a6  jns     short loc_18001F8B4
0x18001f8a8  lea     rdi, aOldercrl; "OlderCrl"
0x18001f8af  jmp     loc_18001F989
0x18001f8b4  mov     rcx, [rbx+50h]; pCert
0x18001f8b8  lea     rax, [rbp+0B0h+ppCrlEntry]
0x18001f8bc  xor     r9d, r9d; pvReserved
0x18001f8bf  mov     [rsp+1B0h+ppvObject], rax; ppCrlEntry
0x18001f8c4  xor     r8d, r8d; dwFlags
0x18001f8c7  mov     rdx, rsi; pCrlContext
0x18001f8ca  call    cs:__imp_CertFindCertificateInCRL
0x18001f8d0  mov     rcx, [rbx+40h]; pCrlContext
0x18001f8d4  call    cs:__imp_CertFreeCRLContext
0x18001f8da  lea     rdi, aUpdated; "UPDATED"
0x18001f8e1  mov     r8d, 1
0x18001f8e7  mov     r12d, r8d
0x18001f8ea  mov     [rbx+40h], rsi
0x18001f8ee  mov     rsi, r13
0x18001f8f1  cmp     [rbx+8Ch], r13d
0x18001f8f8  jnz     short loc_18001F90B
0x18001f8fa  lea     ecx, [r8+3]
0x18001f8fe  mov     r9, r14
0x18001f901  mov     edx, 1020h
0x18001f906  call    _LogCryptnetEvent
0x18001f90b  mov     [rbx+68h], r13
0x18001f90f  mov     rcx, [rbx+70h]; hMem
0x18001f913  test    rcx, rcx
0x18001f916  jz      short loc_18001F921
0x18001f918  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001f91d  mov     [rbx+70h], r13
0x18001f921  mov     rax, [rsp+1B0h+pv]
0x18001f926  test    rax, rax
0x18001f929  jz      short loc_18001F989
0x18001f92b  mov     rcx, [rax+18h]
0x18001f92f  test    rcx, rcx
0x18001f932  jz      short loc_18001F981
0x18001f934  or      r8, 0FFFFFFFFFFFFFFFFh
0x18001f938  mov     rax, r8
0x18001f93b  inc     rax
0x18001f93e  cmp     [rcx+rax*2], r13w
0x18001f943  jnz     short loc_18001F93B
0x18001f945  inc     eax
0x18001f947  movsxd  r14, eax
0x18001f94a  mov     eax, 2
0x18001f94f  mul     r14
0x18001f952  cmovb   rax, r8
0x18001f956  mov     rcx, rax; uBytes
0x18001f959  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001f95e  mov     [rbx+70h], rax
0x18001f962  test    rax, rax
0x18001f965  jz      short loc_18001F989
0x18001f967  mov     rdx, [rsp+1B0h+pv]
0x18001f96c  lea     r8, [r14+r14]; Size
0x18001f970  mov     rcx, rax; void *
0x18001f973  mov     rdx, [rdx+18h]; Src
0x18001f977  call    memcpy_0
0x18001f97c  mov     rax, [rsp+1B0h+pv]
0x18001f981  mov     rax, [rax+8]
0x18001f985  mov     [rbx+68h], rax
0x18001f989  mov     r8d, r15d
0x18001f98c  mov     rdx, rbx
0x18001f98f  mov     rcx, rdi
0x18001f992  call    _LogCrlPreFetchEvent
0x18001f997  test    rsi, rsi
0x18001f99a  jz      short loc_18001F9A5
0x18001f99c  mov     rcx, rsi; pCrlContext
0x18001f99f  call    cs:__imp_CertFreeCRLContext
0x18001f9a5  mov     rcx, [rsp+1B0h+hCertStore]; hCertStore
0x18001f9aa  test    rcx, rcx
0x18001f9ad  jz      short loc_18001F9B7
0x18001f9af  xor     edx, edx; dwFlags
0x18001f9b1  call    cs:__imp_CertCloseStore
0x18001f9b7  mov     rcx, [rsp+1B0h+pv]; pv
0x18001f9bc  test    rcx, rcx
0x18001f9bf  jz      short loc_18001F9C7
0x18001f9c1  call    cs:__imp_CryptMemFree
0x18001f9c7  mov     eax, r12d
0x18001f9ca  mov     rcx, [rbp+0B0h+var_48]
0x18001f9ce  xor     rcx, rsp; StackCookie
0x18001f9d1  call    __security_check_cookie
0x18001f9d6  add     rsp, 178h
0x18001f9dd  pop     r15
0x18001f9df  pop     r14
0x18001f9e1  pop     r13
0x18001f9e3  pop     r12
0x18001f9e5  pop     rdi
0x18001f9e6  pop     rsi
0x18001f9e7  pop     rbx
0x18001f9e8  pop     rbp
0x18001f9e9  retn
```
