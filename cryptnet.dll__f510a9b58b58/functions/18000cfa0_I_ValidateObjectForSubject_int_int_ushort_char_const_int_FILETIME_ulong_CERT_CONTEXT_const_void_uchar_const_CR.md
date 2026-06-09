# I_ValidateObjectForSubject(int,int,ushort *,char const *,int,_FILETIME *,ulong,_CERT_CONTEXT const *,void *,uchar * const,_CRYPT_GET_TIME_VALID_OBJECT_EXTRA_INFO *,void *,_CRYPT_RETRIEVE_AUX_INFO *)

- ea: `0x18000cfa0`
- end: `0x18000d5c5`
- name: `?I_ValidateObjectForSubject@@YAPEAXHHPEAGPEBDHPEAU_FILETIME@@KPEBU_CERT_CONTEXT@@PEAXQEAEPEAU_CRYPT_GET_TIME_VALID_OBJECT_EXTRA_INFO@@4PEAU_CRYPT_RETRIEVE_AUX_INFO@@@Z`
- size: `1573`
- prototype: `struct _CERT_CONTEXT *__fastcall(DWORD, int, unsigned __int16 *, const char *, int, struct _FILETIME *lpFileTime1, unsigned int, struct _CERT_CONTEXT *, void *, unsigned __int8 *const Buf1, struct _CRYPT_GET_TIME_VALID_OBJECT_EXTRA_INFO *, HCERTSTORE hCertStore, struct _CRYPT_RETRIEVE_AUX_INFO *)`
- caller_count: `2`
- callee_count: `13`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000c620`
- `0x18001f61c`

## callees

- `0x180001460`
- `0x180002460`
- `0x18000cfa0`
- `0x18000e5a8`
- `0x18000eb80`
- `0x18000ee20`
- `0x180010e80`
- `0x1800189b0`
- `0x180018b30`
- `0x18001a9c8`
- `0x180025338`
- `0x180026546`
- `0x1800265b0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000d4e8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000d4e8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d368`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d452`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d527`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d368`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d452`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d527`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18000d225`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18000d225`
- `CRYPT32!CertEnumCRLsInStore` at `0x18000d037`
- `CRYPT32!CertEnumCRLsInStore` at `0x18000d037`
- `CRYPT32!I_CertDiagControl` at `0x18000d087`
- `CRYPT32!I_CertDiagControl` at `0x18000d0a6`
- `CRYPT32!I_CertDiagControl` at `0x18000d478`
- `CRYPT32!I_CertDiagControl` at `0x18000d087`
- `CRYPT32!I_CertDiagControl` at `0x18000d0a6`
- `CRYPT32!I_CertDiagControl` at `0x18000d478`
- `CRYPT32!CertEnumCTLsInStore` at `0x18000d40d`
- `CRYPT32!CertEnumCTLsInStore` at `0x18000d40d`
- `CRYPT32!CertFindExtension` at `0x18000d3d4`
- `CRYPT32!CertFindExtension` at `0x18000d3d4`
- `CRYPT32!CryptDecodeObject` at `0x18000d5ac`
- `CRYPT32!CryptDecodeObject` at `0x18000d5ac`
- `CRYPT32!CertEnumCertificatesInStore` at `0x18000d26f`
- `CRYPT32!CertEnumCertificatesInStore` at `0x18000d26f`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18000d155`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18000d55c`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18000d155`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18000d55c`

## string_xrefs

- `0x18000d06b`: `UrlCache`

## pseudocode

```c
struct _CERT_CONTEXT *__fastcall I_ValidateObjectForSubject(
        DWORD a1,
        int a2,
        unsigned __int16 *a3,
        const char *a4,
        int a5,
        struct _FILETIME *lpFileTime1,
        unsigned int a7,
        struct _CERT_CONTEXT *a8,
        void *a9,
        unsigned __int8 *const Buf1,
        struct _CRYPT_GET_TIME_VALID_OBJECT_EXTRA_INFO *a11,
        HCERTSTORE hCertStore,
        struct _CRYPT_RETRIEVE_AUX_INFO *a13)
{
  struct _CERT_CONTEXT *v15; // rsi
  void *v16; // rcx
  const wchar_t *v17; // rax
  struct _CERT_CONTEXT *v18; // rdi
  __int64 v19; // r8
  int OriginIdentifier; // eax
  FILETIME *pCertInfo; // rcx
  FILETIME v22; // rax
  PCERT_INFO v23; // rdx
  int pbData; // r8d
  int v25; // ecx
  PCRYPTNET_URL_CACHE_PRE_FETCH_INFO pPreFetchInfo; // rax
  PCRYPTNET_URL_CACHE_RESPONSE_INFO *ppResponseInfo; // rax
  PCRYPTNET_URL_CACHE_RESPONSE_INFO v28; // rax
  DWORD dwMaxAge; // ebx
  LPFILETIME pMaxAgeTime; // r14
  DWORD v31; // edi
  const wchar_t *v33; // rdx
  FILETIME *v34; // rdx
  DWORD LastError; // eax
  FILETIME *pLastSyncTime; // rbx
  PCERT_EXTENSION Extension; // rax
  FILETIME *v38; // rcx
  DWORD v39; // eax
  DWORD cbData; // r9d
  const BYTE *v41; // r8
  DWORD pcbStructInfo; // [rsp+40h] [rbp-B9h] BYREF
  unsigned int v43[2]; // [rsp+48h] [rbp-B1h] BYREF
  FILETIME FileTime2; // [rsp+50h] [rbp-A9h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+58h] [rbp-A1h] BYREF
  struct _CERT_CONTEXT *v46; // [rsp+60h] [rbp-99h]
  FILETIME v47; // [rsp+68h] [rbp-91h] BYREF
  struct _CRYPT_GET_TIME_VALID_OBJECT_EXTRA_INFO *v48; // [rsp+70h] [rbp-89h]
  _QWORD v49[2]; // [rsp+78h] [rbp-81h] BYREF
  _QWORD v50[2]; // [rsp+88h] [rbp-71h] BYREF
  _BYTE pvStructInfo[40]; // [rsp+98h] [rbp-61h] BYREF
  __int64 v52; // [rsp+C0h] [rbp-39h]
  void *v53[2]; // [rsp+C8h] [rbp-31h] BYREF
  unsigned __int8 Buf2[32]; // [rsp+D8h] [rbp-21h] BYREF

  v15 = 0;
  v46 = a8;
  v53[0] = a9;
  pcbStructInfo = a1;
  v16 = hCertStore;
  v48 = a11;
  SystemTimeAsFileTime = (struct _FILETIME)a3;
  *(_QWORD *)v43 = hCertStore;
  while ( 1 )
  {
    if ( a4 == (const char *)1 )
    {
      v15 = (struct _CERT_CONTEXT *)CertEnumCertificatesInStore(v16, v15);
      if ( !v15 )
        goto LABEL_71;
      goto LABEL_6;
    }
    if ( a4 == (const char *)3 )
    {
      v15 = (struct _CERT_CONTEXT *)CertEnumCTLsInStore(v16, (PCCTL_CONTEXT)v15);
      if ( !v15 )
        goto LABEL_71;
      goto LABEL_6;
    }
    if ( a4 != (const char *)2 || (v15 = (struct _CERT_CONTEXT *)CertEnumCRLsInStore(v16, (PCCRL_CONTEXT)v15)) == 0 )
LABEL_71:
      v15 = 0;
LABEL_6:
    if ( !v15 )
      return v15;
    if ( a4 == (const char *)2 )
    {
      v49[0] = v15;
      v17 = L"UrlCache";
      v18 = v15;
      if ( (a7 & 2) == 0 )
        v17 = L"Wire";
      v49[1] = v17;
      I_CertDiagControl(2, v49, 0);
      v50[1] = SystemTimeAsFileTime;
      v50[0] = v15;
      I_CertDiagControl(3, v50, 0);
      OriginIdentifier = CrlGetOriginIdentifier((const struct _CRL_CONTEXT *)v15, v46, v19, Buf2);
      goto LABEL_11;
    }
    v18 = 0;
    if ( a4 != (const char *)1 )
    {
      if ( a4 == (const char *)3 )
      {
        OriginIdentifier = CtlGetOriginIdentifier((const struct _CTL_CONTEXT *)v15, v46, (__int64)a3, Buf2);
        goto LABEL_11;
      }
      SetLastError(0x80070057);
      goto LABEL_71;
    }
    OriginIdentifier = CertGetOriginIdentifier(v15, v46, (__int64)a3, Buf2);
LABEL_11:
    v16 = *(void **)v43;
    if ( OriginIdentifier )
    {
      if ( !memcmp_0(Buf1, Buf2, 0x20u) )
      {
        if ( (a7 & 0x20) == 0 )
          goto LABEL_14;
        if ( ObjectContextVerifySignature(a4, v15, v46) )
        {
          if ( !v18 || (unsigned int)IsValidCrlIssuerKeyUsage(v46) )
          {
LABEL_14:
            if ( !ObjectContextIsValidForSubject(a4, v15, v53[0], v48) )
            {
              *(_QWORD *)pvStructInfo = v18;
              *(_QWORD *)&pvStructInfo[8] = L"Call_CertIsValidCRLForCertificate";
              *(_QWORD *)&pvStructInfo[16] = GetLastError();
              v52 = 0;
              goto LABEL_63;
            }
            if ( !lpFileTime1 )
              return v15;
            v47 = 0;
            FileTime2 = 0;
            if ( a4 == (const char *)2 )
            {
              pCertInfo = (FILETIME *)v15->pCertInfo;
              v47 = pCertInfo[6];
              v22 = pCertInfo[7];
            }
            else
            {
              v38 = (FILETIME *)v15->pCertInfo;
              if ( a4 == (const char *)1 )
              {
                v47 = v38[8];
                v22 = v38[9];
              }
              else
              {
                v47 = v38[7];
                v22 = v38[8];
              }
            }
            FileTime2 = v22;
            if ( a5 )
            {
              if ( CompareFileTime(lpFileTime1, &v47) <= 0 )
                goto LABEL_20;
            }
            else if ( CompareFileTime(lpFileTime1, &FileTime2) <= 0
                   || !FileTime2.dwLowDateTime && !FileTime2.dwHighDateTime )
            {
LABEL_20:
              if ( v18 && (a7 & 8) == 0 )
              {
                v23 = v18->pCertInfo;
                pbData = (int)v23->Issuer.pbData;
                if ( pbData || HIDWORD(v23->Issuer.pbData) )
                {
                  if ( a2 )
                  {
                    v25 = 4304;
                  }
                  else if ( pcbStructInfo && (a7 & 4) != 0 )
                  {
                    v25 = 4304;
                  }
                  else
                  {
                    v25 = 0;
                  }
                  pPreFetchInfo = a13->pPreFetchInfo;
                  memset(pvStructInfo, 0, sizeof(pvStructInfo));
                  if ( !pPreFetchInfo->dwObjectType && (pbData || HIDWORD(v23->Issuer.pbData)) )
                  {
                    pLastSyncTime = a13->pLastSyncTime;
                    *(_DWORD *)&pvStructInfo[8] = v25;
                    *(_QWORD *)pvStructInfo = 0x200000028LL;
                    *(CERT_NAME_BLOB *)&pvStructInfo[16] = v23->Issuer;
                    Extension = CertFindExtension(
                                  "1.3.6.1.4.1.311.21.4",
                                  v23->Subject.cbData,
                                  (CERT_EXTENSION *)v23->Subject.pbData);
                    if ( Extension )
                    {
                      cbData = Extension->Value.cbData;
                      v41 = Extension->Value.pbData;
                      pcbStructInfo = 8;
                      if ( !CryptDecodeObject(0x10001u, (LPCSTR)0x1E, v41, cbData, 0, &pvStructInfo[32], &pcbStructInfo) )
                        *(_QWORD *)&pvStructInfo[32] = 0;
                    }
                    ((void (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD))I_CryptNetSetUrlCachePreFetchInfo)(
                      SystemTimeAsFileTime,
                      pLastSyncTime,
                      0,
                      pvStructInfo,
                      0);
                  }
                  ppResponseInfo = a13->ppResponseInfo;
                  v43[0] = 0;
                  pcbStructInfo = 0;
                  SystemTimeAsFileTime = 0;
                  v28 = *ppResponseInfo;
                  if ( v28 )
                  {
                    dwMaxAge = v28->dwMaxAge;
                    if ( dwMaxAge )
                    {
                      if ( v28->LastModifiedTime.dwLowDateTime || v28->LastModifiedTime.dwHighDateTime || v28->pwszETag )
                      {
                        pMaxAgeTime = v48->pMaxAgeTime;
                        I_GetMaxAgeParameters(v43, &pcbStructInfo);
                        v31 = v43[0];
                        if ( dwMaxAge >= v43[0] )
                        {
                          v31 = dwMaxAge;
                          if ( dwMaxAge > pcbStructInfo )
                            v31 = pcbStructInfo;
                        }
                        GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
                        *pMaxAgeTime = (struct _FILETIME)(*(_QWORD *)&SystemTimeAsFileTime
                                                        + 10000000LL * ((v31 >> 1) + 300));
                      }
                    }
                  }
                }
                else if ( !a13->pFlushInfo->dwExemptSeconds )
                {
                  v34 = a13->pLastSyncTime;
                  v53[1] = 0;
                  v53[0] = (void *)0xFFFFFFFF00000010LL;
                  ((void (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD))I_CryptNetSetUrlCacheFlushInfo)(
                    SystemTimeAsFileTime,
                    v34,
                    0,
                    v53,
                    0);
                }
              }
              return v15;
            }
            v33 = L"CheckFreshnessTime";
            if ( !a5 )
              v33 = L"CheckTimeValidity";
            CertDiagRejectCrl((_DWORD)v18, (_DWORD)v33, 1931, 0, 0, a7);
            v16 = *(void **)v43;
          }
          else
          {
            LastError = GetLastError();
            CertDiagRejectCrl((_DWORD)v18, (unsigned int)L"IsCrlSignKeyUsagePresent", LastError, 0, 0, 0);
            v16 = *(void **)v43;
          }
        }
        else
        {
          v39 = GetLastError();
          CertDiagRejectCrl((_DWORD)v18, (unsigned int)L"IsCrlSignatureValid", v39, 0, 0, 0);
          v16 = *(void **)v43;
        }
      }
      else
      {
        *(_QWORD *)pvStructInfo = v18;
        *(_QWORD *)&pvStructInfo[16] = 0;
        *(_QWORD *)&pvStructInfo[8] = L"IsCrlSignedByCertIssuer";
        v52 = 0;
LABEL_63:
        *(_OWORD *)&pvStructInfo[24] = 0;
        I_CertDiagControl(5, pvStructInfo, 0);
        v16 = *(void **)v43;
      }
    }
  }
}

```

## disassembly

```asm
0x18000cfa0  mov     [rsp-8+arg_0], rbx
0x18000cfa5  push    rbp
0x18000cfa6  push    rsi
0x18000cfa7  push    rdi
0x18000cfa8  push    r12
0x18000cfaa  push    r13
0x18000cfac  push    r14
0x18000cfae  push    r15
0x18000cfb0  lea     rbp, [rsp-7]
0x18000cfb5  sub     rsp, 100h
0x18000cfbc  mov     rax, cs:__security_cookie
0x18000cfc3  xor     rax, rsp
0x18000cfc6  mov     [rbp+37h+var_38], rax
0x18000cfca  mov     rax, [rbp+37h+arg_38]
0x18000cfce  mov     rbx, r9
0x18000cfd1  mov     r12, [rbp+37h+lpFileTime1]
0x18000cfd5  mov     r13d, edx
0x18000cfd8  mov     r15, [rbp+37h+arg_60]
0x18000cfdf  xor     esi, esi
0x18000cfe1  mov     r14d, [rbp+37h+arg_30]
0x18000cfe5  mov     [rsp+130h+var_D0], rax
0x18000cfea  mov     rax, [rbp+37h+arg_40]
0x18000cff1  mov     [rbp+37h+var_68], rax
0x18000cff5  mov     rax, [rbp+37h+arg_50]
0x18000cffc  mov     [rsp+130h+var_F0], ecx
0x18000d000  mov     rcx, [rbp+37h+hCertStore]; hCertStore
0x18000d007  mov     [rsp+130h+var_C0], rax
0x18000d00c  mov     qword ptr [rsp+130h+SystemTimeAsFileTime.dwLowDateTime], r8
0x18000d011  mov     qword ptr [rsp+130h+var_E8], rcx
0x18000d016  cmp     rbx, 1
0x18000d01a  jz      loc_18000D26C
0x18000d020  cmp     rbx, 3
0x18000d024  jz      loc_18000D40A
0x18000d02a  cmp     rbx, 2
0x18000d02e  jnz     loc_18000D4EE
0x18000d034  mov     rdx, rsi; pPrevCrlContext
0x18000d037  call    cs:__imp_CertEnumCRLsInStore
0x18000d03d  mov     rsi, rax
0x18000d040  test    rax, rax
0x18000d043  jz      loc_18000D4EE
0x18000d049  test    rsi, rsi
0x18000d04c  jz      loc_18000D242
0x18000d052  cmp     rbx, 2
0x18000d056  jnz     loc_18000D4BF
0x18000d05c  lea     rcx, aWire_0; "Wire"
0x18000d063  mov     [rsp+130h+var_B8], rsi
0x18000d068  test    bl, r14b
0x18000d06b  lea     rax, aUrlcache; "UrlCache"
0x18000d072  lea     rdx, [rsp+130h+var_B8]
0x18000d077  mov     rdi, rsi
0x18000d07a  cmovz   rax, rcx
0x18000d07e  xor     r8d, r8d
0x18000d081  mov     ecx, ebx
0x18000d083  mov     [rbp+37h+var_B0], rax
0x18000d087  call    cs:__imp_I_CertDiagControl
0x18000d08d  mov     rax, qword ptr [rsp+130h+SystemTimeAsFileTime.dwLowDateTime]
0x18000d092  lea     rdx, [rbp+37h+var_A8]
0x18000d096  xor     r8d, r8d
0x18000d099  mov     [rbp+37h+var_A0], rax
0x18000d09d  mov     ecx, 3
0x18000d0a2  mov     [rbp+37h+var_A8], rsi
0x18000d0a6  call    cs:__imp_I_CertDiagControl
0x18000d0ac  mov     rdx, [rsp+130h+var_D0]; struct _CERT_CONTEXT *
0x18000d0b1  lea     r9, [rbp+37h+Buf2]; unsigned __int8 *
0x18000d0b5  mov     rcx, rsi; struct _CRL_CONTEXT *
0x18000d0b8  call    ?CrlGetOriginIdentifier@@YAHPEBU_CRL_CONTEXT@@PEBU_CERT_CONTEXT@@KQEAE@Z; CrlGetOriginIdentifier(_CRL_CONTEXT const *,_CERT_CONTEXT const *,ulong,uchar * const)
0x18000d0bd  mov     rcx, qword ptr [rsp+130h+var_E8]
0x18000d0c2  test    eax, eax
0x18000d0c4  jz      loc_18000D016
0x18000d0ca  mov     rcx, [rbp+37h+Buf1]; Buf1
0x18000d0d1  lea     rdx, [rbp+37h+Buf2]; Buf2
0x18000d0d5  mov     r8d, 20h ; ' '; Size
0x18000d0db  call    memcmp_0
0x18000d0e0  test    eax, eax
0x18000d0e2  jnz     loc_18000D488
0x18000d0e8  test    r14b, 20h
0x18000d0ec  jnz     loc_18000D335
0x18000d0f2  mov     r9, [rsp+130h+var_C0]; struct _CRYPT_GET_TIME_VALID_OBJECT_EXTRA_INFO *
0x18000d0f7  mov     rdx, rsi; void *
0x18000d0fa  mov     r8, [rbp+37h+var_68]; void *
0x18000d0fe  mov     rcx, rbx; char *
0x18000d101  call    ?ObjectContextIsValidForSubject@@YAHPEBDPEAX1PEAU_CRYPT_GET_TIME_VALID_OBJECT_EXTRA_INFO@@@Z; ObjectContextIsValidForSubject(char const *,void *,void *,_CRYPT_GET_TIME_VALID_OBJECT_EXTRA_INFO *)
0x18000d106  test    eax, eax
0x18000d108  jz      loc_18000D443
0x18000d10e  test    r12, r12
0x18000d111  jz      loc_18000D242
0x18000d117  xor     eax, eax
0x18000d119  mov     qword ptr [rsp+130h+var_C8.dwLowDateTime], rax
0x18000d11e  mov     qword ptr [rsp+130h+FileTime2.dwLowDateTime], rax
0x18000d123  cmp     rbx, 2
0x18000d127  jnz     loc_18000D4A3
0x18000d12d  mov     rcx, [rsi+18h]
0x18000d131  mov     rax, [rcx+30h]
0x18000d135  mov     qword ptr [rsp+130h+var_C8.dwLowDateTime], rax
0x18000d13a  mov     rax, [rcx+38h]
0x18000d13e  cmp     [rbp+37h+arg_20], 0
0x18000d142  mov     rcx, r12; lpFileTime1
0x18000d145  mov     qword ptr [rsp+130h+FileTime2.dwLowDateTime], rax
0x18000d14a  jnz     loc_18000D557
0x18000d150  lea     rdx, [rsp+130h+FileTime2]; lpFileTime2
0x18000d155  call    cs:__imp_CompareFileTime
0x18000d15b  test    eax, eax
0x18000d15d  jg      loc_18000D286
0x18000d163  test    rdi, rdi
0x18000d166  jz      loc_18000D242
0x18000d16c  test    r14b, 8
0x18000d170  jnz     loc_18000D242
0x18000d176  mov     rdx, [rdi+18h]
0x18000d17a  mov     r8d, [rdx+38h]
0x18000d17e  test    r8d, r8d
0x18000d181  jz      loc_18000D2D0
0x18000d187  test    r13d, r13d
0x18000d18a  jnz     loc_18000D56F
0x18000d190  cmp     [rsp+130h+var_F0], r13d
0x18000d195  jz      loc_18000D401
0x18000d19b  test    r14b, 4
0x18000d19f  jz      loc_18000D401
0x18000d1a5  mov     ecx, 10D0h
0x18000d1aa  xor     edi, edi
0x18000d1ac  xor     eax, eax
0x18000d1ae  xorps   xmm0, xmm0
0x18000d1b1  mov     [rbp+37h+var_78], rax
0x18000d1b5  mov     rax, [r15+18h]
0x18000d1b9  movups  [rbp+37h+var_98], xmm0
0x18000d1bd  movups  [rbp+37h+var_88], xmm0
0x18000d1c1  cmp     dword ptr [rax+4], 0
0x18000d1c5  jz      loc_18000D398
0x18000d1cb  mov     rax, [r15+28h]
0x18000d1cf  mov     [rsp+130h+var_E8], edi
0x18000d1d3  mov     [rsp+130h+var_F0], edi
0x18000d1d7  mov     qword ptr [rsp+130h+SystemTimeAsFileTime.dwLowDateTime], rdi
0x18000d1dc  mov     rax, [rax]
0x18000d1df  test    rax, rax
0x18000d1e2  jz      short loc_18000D242
0x18000d1e4  mov     ebx, [rax+10h]
0x18000d1e7  test    ebx, ebx
0x18000d1e9  jz      short loc_18000D242
0x18000d1eb  cmp     dword ptr [rax+8], 0
0x18000d1ef  jz      loc_18000D31B
0x18000d1f5  mov     rax, [rsp+130h+var_C0]
0x18000d1fa  lea     rdx, [rsp+130h+var_F0]; unsigned int *
0x18000d1ff  lea     rcx, [rsp+130h+var_E8]; unsigned int *
0x18000d204  mov     r14, [rax+18h]
0x18000d208  call    ?I_GetMaxAgeParameters@@YAXPEAK0@Z; I_GetMaxAgeParameters(ulong *,ulong *)
0x18000d20d  mov     edi, [rsp+130h+var_E8]
0x18000d211  cmp     ebx, edi
0x18000d213  jb      short loc_18000D220
0x18000d215  cmp     ebx, [rsp+130h+var_F0]
0x18000d219  mov     edi, ebx
0x18000d21b  cmova   edi, [rsp+130h+var_F0]
0x18000d220  lea     rcx, [rsp+130h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18000d225  call    cs:__imp_GetSystemTimeAsFileTime
0x18000d22b  shr     edi, 1
0x18000d22d  lea     eax, [rdi+12Ch]
0x18000d233  imul    rcx, rax, 989680h
0x18000d23a  add     rcx, qword ptr [rsp+130h+SystemTimeAsFileTime.dwLowDateTime]
0x18000d23f  mov     [r14], rcx
0x18000d242  mov     rax, rsi
0x18000d245  mov     rcx, [rbp+37h+var_38]
0x18000d249  xor     rcx, rsp; StackCookie
0x18000d24c  call    __security_check_cookie
0x18000d251  mov     rbx, [rsp+130h+arg_0]
0x18000d259  add     rsp, 100h
0x18000d260  pop     r15
0x18000d262  pop     r14
0x18000d264  pop     r13
0x18000d266  pop     r12
0x18000d268  pop     rdi
0x18000d269  pop     rsi
0x18000d26a  pop     rbp
0x18000d26b  retn
0x18000d26c  mov     rdx, rsi; pPrevCertContext
0x18000d26f  call    cs:__imp_CertEnumCertificatesInStore
0x18000d275  mov     rsi, rax
0x18000d278  test    rax, rax
0x18000d27b  jnz     loc_18000D049
0x18000d281  jmp     loc_18000D4EE
0x18000d286  cmp     [rsp+130h+FileTime2.dwLowDateTime], 0
0x18000d28b  jz      loc_18000D424
0x18000d291  cmp     [rbp+37h+arg_20], 0
0x18000d295  lea     rax, aChecktimevalid; "CheckTimeValidity"
0x18000d29c  lea     rdx, aCheckfreshness; "CheckFreshnessTime"
0x18000d2a3  mov     dword ptr [rsp+130h+pvStructInfo], r14d
0x18000d2a8  cmovz   rdx, rax
0x18000d2ac  mov     qword ptr [rsp+130h+dwFlags], 0
0x18000d2b5  xor     r9d, r9d
0x18000d2b8  mov     r8d, 78Bh
0x18000d2be  mov     rcx, rdi
0x18000d2c1  call    CertDiagRejectCrl
0x18000d2c6  mov     rcx, qword ptr [rsp+130h+var_E8]
0x18000d2cb  jmp     loc_18000D016
0x18000d2d0  cmp     dword ptr [rdx+3Ch], 0
0x18000d2d4  jnz     loc_18000D187
0x18000d2da  mov     rax, [r15+20h]
0x18000d2de  cmp     dword ptr [rax+4], 0
0x18000d2e2  jnz     loc_18000D242
0x18000d2e8  mov     rdx, [r15+8]
0x18000d2ec  lea     r9, [rbp+37h+var_68]
0x18000d2f0  mov     rcx, qword ptr [rsp+130h+SystemTimeAsFileTime.dwLowDateTime]
0x18000d2f5  xor     eax, eax
0x18000d2f7  xor     r8d, r8d
0x18000d2fa  mov     [rbp+37h+var_60], rax
0x18000d2fe  mov     qword ptr [rsp+130h+dwFlags], rax
0x18000d303  mov     dword ptr [rbp+37h+var_68], 10h
0x18000d30a  mov     dword ptr [rbp+37h+var_68+4], 0FFFFFFFFh
0x18000d311  call    I_CryptNetSetUrlCacheFlushInfo
0x18000d316  jmp     loc_18000D242
0x18000d31b  cmp     dword ptr [rax+0Ch], 0
0x18000d31f  jnz     loc_18000D1F5
0x18000d325  cmp     qword ptr [rax+18h], 0
0x18000d32a  jnz     loc_18000D1F5
0x18000d330  jmp     loc_18000D242
0x18000d335  mov     r8, [rsp+130h+var_D0]; struct _CERT_CONTEXT *
0x18000d33a  mov     rdx, rsi; void *
0x18000d33d  mov     rcx, rbx; char *
0x18000d340  call    ?ObjectContextVerifySignature@@YAHPEBDPEAXPEBU_CERT_CONTEXT@@@Z; ObjectContextVerifySignature(char const *,void *,_CERT_CONTEXT const *)
0x18000d345  test    eax, eax
0x18000d347  jz      loc_18000D527
0x18000d34d  test    rdi, rdi
0x18000d350  jz      loc_18000D0F2
0x18000d356  mov     rcx, [rsp+130h+var_D0]; struct _CERT_CONTEXT *
0x18000d35b  call    ?IsValidCrlIssuerKeyUsage@@YAHPEBU_CERT_CONTEXT@@@Z; IsValidCrlIssuerKeyUsage(_CERT_CONTEXT const *)
0x18000d360  test    eax, eax
0x18000d362  jnz     loc_18000D0F2
0x18000d368  call    cs:__imp_GetLastError
0x18000d36e  xor     r9d, r9d
0x18000d371  lea     rdx, aIscrlsignkeyus; "IsCrlSignKeyUsagePresent"
0x18000d378  mov     r8d, eax
0x18000d37b  mov     rcx, rdi
0x18000d37e  xor     eax, eax
0x18000d380  mov     dword ptr [rsp+130h+pvStructInfo], eax
0x18000d384  mov     qword ptr [rsp+130h+dwFlags], rax
0x18000d389  call    CertDiagRejectCrl
0x18000d38e  mov     rcx, qword ptr [rsp+130h+var_E8]
0x18000d393  jmp     loc_18000D016
0x18000d398  test    r8d, r8d
0x18000d39b  jz      loc_18000D434
0x18000d3a1  mov     rbx, [r15+8]
0x18000d3a5  mov     dword ptr [rbp+37h+var_98+8], ecx
0x18000d3a8  lea     rcx, a136141311214; "1.3.6.1.4.1.311.21.4"
0x18000d3af  mov     dword ptr [rbp+37h+var_98], 28h ; '('
0x18000d3b6  mov     dword ptr [rbp+37h+var_98+4], 2
0x18000d3bd  mov     rax, [rdx+30h]
0x18000d3c1  mov     qword ptr [rbp+37h+var_88], rax
0x18000d3c5  mov     rax, [rdx+38h]
0x18000d3c9  mov     qword ptr [rbp+37h+var_88+8], rax
0x18000d3cd  mov     r8, [rdx+58h]; rgExtensions
0x18000d3d1  mov     edx, [rdx+50h]; cExtensions
0x18000d3d4  call    cs:__imp_CertFindExtension
0x18000d3da  test    rax, rax
0x18000d3dd  jnz     loc_18000D57B
0x18000d3e3  mov     rcx, qword ptr [rsp+130h+SystemTimeAsFileTime.dwLowDateTime]
0x18000d3e8  lea     r9, [rbp+37h+var_98]
0x18000d3ec  xor     r8d, r8d
0x18000d3ef  mov     qword ptr [rsp+130h+dwFlags], rdi
0x18000d3f4  mov     rdx, rbx
0x18000d3f7  call    I_CryptNetSetUrlCachePreFetchInfo
0x18000d3fc  jmp     loc_18000D1CB
0x18000d401  xor     edi, edi
0x18000d403  mov     ecx, edi
0x18000d405  jmp     loc_18000D1AC
0x18000d40a  mov     rdx, rsi; pPrevCtlContext
0x18000d40d  call    cs:__imp_CertEnumCTLsInStore
0x18000d413  mov     rsi, rax
0x18000d416  test    rax, rax
0x18000d419  jnz     loc_18000D049
0x18000d41f  jmp     loc_18000D4EE
0x18000d424  cmp     [rsp+130h+FileTime2.dwHighDateTime], 0
0x18000d429  jz      loc_18000D163
0x18000d42f  jmp     loc_18000D291
0x18000d434  cmp     dword ptr [rdx+3Ch], 0
0x18000d438  jnz     loc_18000D3A1
0x18000d43e  jmp     loc_18000D1CB
0x18000d443  lea     rax, aCallCertisvali; "Call_CertIsValidCRLForCertificate"
0x18000d44a  mov     qword ptr [rbp+37h+var_98], rdi
0x18000d44e  mov     qword ptr [rbp+37h+var_98+8], rax
0x18000d452  call    cs:__imp_GetLastError
0x18000d458  mov     dword ptr [rbp+37h+var_88], eax
0x18000d45b  xor     eax, eax
0x18000d45d  mov     dword ptr [rbp+37h+var_88+4], eax
0x18000d460  mov     [rbp+37h+var_70], rax
0x18000d464  xorps   xmm0, xmm0
0x18000d467  lea     rdx, [rbp+37h+var_98]
0x18000d46b  xor     r8d, r8d
0x18000d46e  mov     ecx, 5
0x18000d473  movdqu  [rbp+37h+var_88+8], xmm0
0x18000d478  call    cs:__imp_I_CertDiagControl
0x18000d47e  mov     rcx, qword ptr [rsp+130h+var_E8]
0x18000d483  jmp     loc_18000D016
0x18000d488  xor     ecx, ecx
0x18000d48a  mov     qword ptr [rbp+37h+var_98], rdi
0x18000d48e  lea     rax, aIscrlsignedbyc; "IsCrlSignedByCertIssuer"
0x18000d495  mov     qword ptr [rbp+37h+var_88], rcx
0x18000d499  mov     qword ptr [rbp+37h+var_98+8], rax
0x18000d49d  mov     [rbp+37h+var_70], rcx
0x18000d4a1  jmp     short loc_18000D464
0x18000d4a3  cmp     rbx, 1
0x18000d4a7  jnz     short loc_18000D50B
0x18000d4a9  mov     rcx, [rsi+18h]
0x18000d4ad  mov     rax, [rcx+40h]
  ... truncated ...
```
