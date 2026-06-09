# I_ValidateOcspResponse

- ea: `0x18000ca20`
- end: `0x18000cee4`
- name: `I_ValidateOcspResponse`
- size: `1220`
- prototype: `__int64 __fastcall(int, int, int, int, unsigned int, __int64, struct _CERT_CONTEXT *, __int64, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18000a9d0`

## callees

- `0x180002460`
- `0x18000a990`
- `0x18000bb78`
- `0x18000ca20`
- `0x18000dab0`
- `0x18000e610`
- `0x18000ee20`
- `0x1800265b0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000ccbc`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000cd26`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000cdd4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000ccbc`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000cd26`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000cdd4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ccc2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ccee`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ccc2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ccee`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18000cc97`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18000cc97`
- `CRYPT32!I_CertDiagControl` at `0x18000cadb`
- `CRYPT32!I_CertDiagControl` at `0x18000cbb1`
- `CRYPT32!I_CertDiagControl` at `0x18000cbd2`
- `CRYPT32!I_CertDiagControl` at `0x18000cdc9`
- `CRYPT32!I_CertDiagControl` at `0x18000cadb`
- `CRYPT32!I_CertDiagControl` at `0x18000cbb1`
- `CRYPT32!I_CertDiagControl` at `0x18000cbd2`
- `CRYPT32!I_CertDiagControl` at `0x18000cdc9`
- `CRYPT32!CertFreeCertificateContext` at `0x18000cd3c`
- `CRYPT32!CertFreeCertificateContext` at `0x18000cd3c`
- `CRYPT32!CertFindExtension` at `0x18000ce3b`
- `CRYPT32!CertFindExtension` at `0x18000ce3b`
- `CRYPT32!CertFreeCRLContext` at `0x18000cce6`
- `CRYPT32!CertFreeCRLContext` at `0x18000cce6`
- `CRYPT32!CryptDecodeObject` at `0x18000cecb`
- `CRYPT32!CryptDecodeObject` at `0x18000cecb`
- `CRYPT32!CryptMemFree` at `0x18000ccff`
- `CRYPT32!CryptMemFree` at `0x18000ccff`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18000cbf8`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18000ce83`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18000cbf8`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18000ce83`

## string_xrefs

- `0x18000ca93`: `UrlCache`
- `0x18000cccc`: `CRYPTNET.DLL --> OCSP URL: %S, failed: %d (0x%x)\n`

## pseudocode

```c
const CRL_CONTEXT *__fastcall I_ValidateOcspResponse(
        struct _OCSP_CERT_ID *a1,
        const wchar_t *a2,
        unsigned int a3,
        FILETIME *a4,
        unsigned int a5,
        struct _CERT_CONTEXT *a6,
        struct _CERT_CONTEXT *a7,
        __int64 a8,
        __int64 a9,
        const FILETIME *a10,
        FILETIME *a11)
{
  struct _OCSP_BASIC_RESPONSE_INFO *v11; // r14
  const CERT_CONTEXT *v12; // rdi
  const CRL_CONTEXT *v13; // rbx
  const wchar_t *v14; // rax
  int v15; // eax
  const struct _CRL_CONTEXT *v16; // rax
  const wchar_t *v17; // r12
  const FILETIME *pCrlInfo; // r15
  const FILETIME *v19; // rsi
  __int64 v20; // rcx
  unsigned int v21; // r15d
  _QWORD *v22; // r12
  unsigned int v23; // esi
  DWORD LastError; // eax
  DWORD v25; // esi
  const wchar_t *v27; // rax
  PCRL_INFO v28; // rdx
  const FILETIME *v29; // rax
  void *v30; // r15
  PCERT_EXTENSION Extension; // rax
  DWORD cbData; // r9d
  const BYTE *pbData; // r8
  unsigned int v34; // [rsp+50h] [rbp-A9h] BYREF
  DWORD pcbStructInfo[2]; // [rsp+58h] [rbp-A1h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+60h] [rbp-99h] BYREF
  void *v37; // [rsp+68h] [rbp-91h] BYREF
  const wchar_t *v38; // [rsp+70h] [rbp-89h]
  const FILETIME *v39; // [rsp+78h] [rbp-81h]
  LPVOID pv[2]; // [rsp+80h] [rbp-79h] BYREF
  HLOCAL hMem; // [rsp+90h] [rbp-69h]
  const wchar_t *v42; // [rsp+98h] [rbp-61h]
  struct _CERT_CONTEXT *pvIssuer; // [rsp+A0h] [rbp-59h]
  struct _OCSP_CERT_ID *v44; // [rsp+A8h] [rbp-51h]
  const wchar_t *v45; // [rsp+B0h] [rbp-49h]
  FILETIME *lpFileTime1; // [rsp+B8h] [rbp-41h]
  FILETIME *v47; // [rsp+C0h] [rbp-39h]
  _BYTE pvStructInfo[40]; // [rsp+C8h] [rbp-31h] BYREF
  unsigned int v49; // [rsp+F0h] [rbp-9h]
  int v50; // [rsp+F4h] [rbp-5h]

  v11 = 0;
  v12 = 0;
  v13 = 0;
  pvIssuer = a6;
  v39 = a10;
  v47 = a11;
  hMem = 0;
  v44 = a1;
  v14 = L"UrlCache";
  v34 = a3;
  if ( (a5 & 2) == 0 )
    v14 = L"Wire";
  v42 = a2;
  v38 = a2;
  v45 = v14;
  v37 = (void *)v14;
  lpFileTime1 = a4;
  *(_QWORD *)pcbStructInfo = 0;
  SystemTimeAsFileTime = 0;
  *(_OWORD *)pv = 0;
  I_CertDiagControl(4, &v37, 0);
  hMem = 0;
  *(_OWORD *)pv = 0;
  if ( !a8 || !*(_DWORD *)a8 )
  {
    SetLastError(0xDu);
    goto LABEL_20;
  }
  v15 = OcspVerifyResponse(
          *(BYTE **)(*(_QWORD *)(a8 + 8) + 8LL),
          **(_DWORD **)(a8 + 8),
          a7,
          pvIssuer,
          *(struct _CERT_REVOCATION_CHAIN_PARA **)(a9 + 32),
          a5,
          (struct _OCSP_BASIC_RESPONSE_INFO **)pcbStructInfo,
          (const struct _CERT_CONTEXT **)&SystemTimeAsFileTime,
          (struct _OCSP_STRONG_SIGN_PROP_INFO *)pv,
          (a5 >> 2) & 1);
  v12 = (const CERT_CONTEXT *)SystemTimeAsFileTime;
  v11 = *(struct _OCSP_BASIC_RESPONSE_INFO **)pcbStructInfo;
  if ( !v15
    || (v16 = OcspConvertResponseToCrl(
                *(struct _OCSP_STRONG_SIGN_PROP_INFO **)(*(_QWORD *)(a8 + 8) + 8LL),
                **(_DWORD **)(a8 + 8),
                v44,
                *(struct _OCSP_BASIC_RESPONSE_INFO **)pcbStructInfo,
                a7,
                *(const struct _CERT_CONTEXT **)&SystemTimeAsFileTime,
                (struct _OCSP_STRONG_SIGN_PROP_INFO *)pv,
                0),
        (v13 = v16) == 0) )
  {
LABEL_20:
    LastError = GetLastError();
    I_CryptNetDebugErrorPrintfA("CRYPTNET.DLL --> OCSP URL: %S, failed: %d (0x%x)\n", v42, LastError, LastError);
    if ( !v13 )
      goto LABEL_22;
    goto LABEL_21;
  }
  v37 = (void *)v16;
  v38 = v45;
  I_CertDiagControl(2, &v37, 0);
  v17 = v42;
  v38 = v42;
  v37 = (void *)v13;
  I_CertDiagControl(3, &v37, 0);
  if ( !lpFileTime1 )
    goto LABEL_22;
  pCrlInfo = (const FILETIME *)v13->pCrlInfo;
  if ( v34 )
  {
    if ( CompareFileTime(lpFileTime1, pCrlInfo + 6) > 0 )
      goto LABEL_29;
  }
  else if ( CompareFileTime(lpFileTime1, pCrlInfo + 7) > 0 && (pCrlInfo[7].dwLowDateTime || pCrlInfo[7].dwHighDateTime) )
  {
    *v47 = v13->pCrlInfo->NextUpdate;
LABEL_29:
    *(_QWORD *)pvStructInfo = v13;
    v27 = L"CheckFreshnessTime";
    *(_QWORD *)&pvStructInfo[16] = 1931;
    if ( !v34 )
      v27 = L"CheckTimeValidity";
    v49 = a5;
    *(_QWORD *)&pvStructInfo[8] = v27;
    v50 = 0;
    *(_OWORD *)&pvStructInfo[24] = 0;
    I_CertDiagControl(5, pvStructInfo, 0);
    SetLastError(0x800B0101);
LABEL_21:
    CertFreeCRLContext(v13);
    v13 = 0;
    goto LABEL_22;
  }
  if ( (a5 & 8) == 0 )
  {
    v19 = v39;
    memset(pvStructInfo, 0, sizeof(pvStructInfo));
    if ( !*(_DWORD *)(*(_QWORD *)&v39[3] + 4LL) )
    {
      v28 = v13->pCrlInfo;
      if ( v28->NextUpdate.dwLowDateTime || v28->NextUpdate.dwHighDateTime )
      {
        v29 = (const FILETIME *)v39[1];
        v30 = (void *)v39[6];
        *(_DWORD *)pvStructInfo = 40;
        *(_QWORD *)&pvStructInfo[4] = 3;
        v39 = v29;
        *(_OWORD *)&pvStructInfo[16] = *(_OWORD *)&v28->ThisUpdate.dwLowDateTime;
        Extension = CertFindExtension("1.3.6.1.4.1.311.21.4", v28->cExtension, v28->rgExtension);
        if ( Extension )
        {
          cbData = Extension->Value.cbData;
          pbData = Extension->Value.pbData;
          pcbStructInfo[0] = 8;
          if ( !CryptDecodeObject(0x10001u, (LPCSTR)0x1E, pbData, cbData, 0, &pvStructInfo[32], pcbStructInfo) )
            *(_QWORD *)&pvStructInfo[32] = 0;
        }
        I_CryptNetSetUrlCachePreFetchInfo((__int64)v17, v39, 0, pvStructInfo, v30);
      }
    }
    v20 = **(_QWORD **)&v19[5];
    v34 = 0;
    pcbStructInfo[0] = 0;
    SystemTimeAsFileTime = 0;
    if ( v20 )
    {
      v21 = *(_DWORD *)(v20 + 16);
      if ( v21 )
      {
        if ( *(_DWORD *)(v20 + 8) || *(_DWORD *)(v20 + 12) || *(_QWORD *)(v20 + 24) )
        {
          v22 = *(_QWORD **)(a9 + 24);
          I_GetMaxAgeParameters(&v34, pcbStructInfo);
          v23 = v34;
          if ( v21 >= v34 )
          {
            v23 = v21;
            if ( v21 > pcbStructInfo[0] )
              v23 = pcbStructInfo[0];
          }
          GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
          *v22 = *(_QWORD *)&SystemTimeAsFileTime + 10000000LL * ((v23 >> 1) + 300);
        }
      }
    }
  }
LABEL_22:
  v25 = GetLastError();
  if ( pv[0] )
    CryptMemFree(pv[0]);
  operator delete(pv[1]);
  operator delete(hMem);
  hMem = 0;
  *(_OWORD *)pv = 0;
  SetLastError(v25);
  operator delete(v11);
  if ( v12 )
    CertFreeCertificateContext(v12);
  return v13;
}

```

## disassembly

```asm
0x18000ca20  mov     [rsp-8+arg_10], rbx
0x18000ca25  push    rbp
0x18000ca26  push    rsi
0x18000ca27  push    rdi
0x18000ca28  push    r12
0x18000ca2a  push    r13
0x18000ca2c  push    r14
0x18000ca2e  push    r15
0x18000ca30  lea     rbp, [rsp-7]
0x18000ca35  sub     rsp, 100h
0x18000ca3c  mov     rax, cs:__security_cookie
0x18000ca43  xor     rax, rsp
0x18000ca46  mov     [rbp+37h+var_38], rax
0x18000ca4a  mov     rax, [rbp+37h+arg_28]
0x18000ca4e  xor     r14d, r14d
0x18000ca51  mov     esi, [rbp+37h+arg_20]
0x18000ca54  xor     edi, edi
0x18000ca56  mov     r15, [rbp+37h+arg_38]
0x18000ca5a  xorps   xmm0, xmm0
0x18000ca5d  mov     r12, [rbp+37h+arg_30]
0x18000ca61  xor     ebx, ebx
0x18000ca63  mov     r13, [rbp+37h+arg_40]
0x18000ca6a  mov     [rbp+37h+pvIssuer], rax
0x18000ca6e  mov     rax, [rbp+37h+arg_48]
0x18000ca75  mov     [rsp+130h+var_B8], rax
0x18000ca7a  mov     rax, [rbp+37h+arg_50]
0x18000ca81  mov     [rbp+37h+var_70], rax
0x18000ca85  xor     eax, eax
0x18000ca87  mov     [rbp+37h+hMem], rax
0x18000ca8b  test    sil, 2
0x18000ca8f  mov     [rbp+37h+var_88], rcx
0x18000ca93  lea     rax, aUrlcache; "UrlCache"
0x18000ca9a  lea     rcx, aWire_0; "Wire"
0x18000caa1  mov     [rsp+130h+var_E0], r8d
0x18000caa6  cmovz   rax, rcx
0x18000caaa  mov     [rbp+37h+var_98], rdx
0x18000caae  mov     [rsp+130h+var_C0], rdx
0x18000cab3  xor     r8d, r8d
0x18000cab6  mov     ecx, 4
0x18000cabb  mov     [rbp+37h+var_80], rax
0x18000cabf  lea     rdx, [rsp+130h+var_C8]
0x18000cac4  mov     [rsp+130h+var_C8], rax
0x18000cac9  mov     [rbp+37h+lpFileTime1], r9
0x18000cacd  mov     qword ptr [rsp+130h+var_D8], r14
0x18000cad2  mov     qword ptr [rsp+130h+SystemTimeAsFileTime.dwLowDateTime], rdi
0x18000cad7  movups  xmmword ptr [rbp+37h+pv], xmm0
0x18000cadb  call    cs:__imp_I_CertDiagControl
0x18000cae1  mov     [rbp+37h+hMem], rbx
0x18000cae5  xorps   xmm0, xmm0
0x18000cae8  movdqu  xmmword ptr [rbp+37h+pv], xmm0
0x18000caed  test    r15, r15
0x18000caf0  jz      loc_18000CCB7
0x18000caf6  cmp     [r15], ebx
0x18000caf9  jz      loc_18000CCB7
0x18000caff  mov     rcx, [r15+8]
0x18000cb03  mov     eax, esi
0x18000cb05  mov     r9, [rbp+37h+pvIssuer]; pvIssuer
0x18000cb09  mov     r8, r12; struct _CERT_CONTEXT *
0x18000cb0c  shr     eax, 2
0x18000cb0f  and     eax, 1
0x18000cb12  mov     edx, [rcx]; cbEncoded
0x18000cb14  mov     rcx, [rcx+8]; pbEncoded
0x18000cb18  mov     [rsp+130h+var_E8], eax; unsigned int
0x18000cb1c  lea     rax, [rbp+37h+pv]
0x18000cb20  mov     [rsp+130h+var_F0], rax; struct _OCSP_STRONG_SIGN_PROP_INFO *
0x18000cb25  lea     rax, [rsp+130h+SystemTimeAsFileTime]
0x18000cb2a  mov     [rsp+130h+var_F8], rax; struct _CERT_CONTEXT **
0x18000cb2f  lea     rax, [rsp+130h+var_D8]
0x18000cb34  mov     [rsp+130h+pcbStructInfo], rax; struct _OCSP_BASIC_RESPONSE_INFO **
0x18000cb39  mov     rax, [r13+20h]
0x18000cb3d  mov     dword ptr [rsp+130h+pvStructInfo], esi; unsigned int
0x18000cb41  mov     qword ptr [rsp+130h+dwFlags], rax; struct _CERT_REVOCATION_CHAIN_PARA *
0x18000cb46  call    ?OcspVerifyResponse@@YAHPEBEKPEBU_CERT_CONTEXT@@1PEAU_CERT_REVOCATION_CHAIN_PARA@@KPEAPEAU_OCSP_BASIC_RESPONSE_INFO@@PEAPEBU1@PEAU_OCSP_STRONG_SIGN_PROP_INFO@@K@Z; OcspVerifyResponse(uchar const *,ulong,_CERT_CONTEXT const *,_CERT_CONTEXT const *,_CERT_REVOCATION_CHAIN_PARA *,ulong,_OCSP_BASIC_RESPONSE_INFO * *,_CERT_CONTEXT const * *,_OCSP_STRONG_SIGN_PROP_INFO *,ulong)
0x18000cb4b  mov     rdi, qword ptr [rsp+130h+SystemTimeAsFileTime.dwLowDateTime]
0x18000cb50  mov     r14, qword ptr [rsp+130h+var_D8]
0x18000cb55  test    eax, eax
0x18000cb57  jz      loc_18000CCC2
0x18000cb5d  mov     rcx, [r15+8]
0x18000cb61  lea     rax, [rbp+37h+pv]
0x18000cb65  mov     r8, [rbp+37h+var_88]; struct _OCSP_CERT_ID *
0x18000cb69  mov     r9, r14; struct _OCSP_BASIC_RESPONSE_INFO *
0x18000cb6c  mov     dword ptr [rsp+130h+var_F8], ebx; unsigned int
0x18000cb70  mov     [rsp+130h+pcbStructInfo], rax; struct _OCSP_STRONG_SIGN_PROP_INFO *
0x18000cb75  mov     edx, [rcx]; unsigned int
0x18000cb77  mov     rcx, [rcx+8]; unsigned __int8 *
0x18000cb7b  mov     [rsp+130h+pvStructInfo], rdi; struct _CERT_CONTEXT *
0x18000cb80  mov     qword ptr [rsp+130h+dwFlags], r12; struct _CERT_CONTEXT *
0x18000cb85  call    ?OcspConvertResponseToCrl@@YAPEBU_CRL_CONTEXT@@PEBEKPEBU_OCSP_CERT_ID@@PEAU_OCSP_BASIC_RESPONSE_INFO@@PEBU_CERT_CONTEXT@@3PEAU_OCSP_STRONG_SIGN_PROP_INFO@@K@Z; OcspConvertResponseToCrl(uchar const *,ulong,_OCSP_CERT_ID const *,_OCSP_BASIC_RESPONSE_INFO *,_CERT_CONTEXT const *,_CERT_CONTEXT const *,_OCSP_STRONG_SIGN_PROP_INFO *,ulong)
0x18000cb8a  mov     rbx, rax
0x18000cb8d  test    rax, rax
0x18000cb90  jz      loc_18000CCC2
0x18000cb96  mov     [rsp+130h+var_C8], rax
0x18000cb9b  lea     rdx, [rsp+130h+var_C8]
0x18000cba0  mov     rax, [rbp+37h+var_80]
0x18000cba4  xor     r8d, r8d
0x18000cba7  mov     ecx, 2
0x18000cbac  mov     [rsp+130h+var_C0], rax
0x18000cbb1  call    cs:__imp_I_CertDiagControl
0x18000cbb7  mov     r12, [rbp+37h+var_98]
0x18000cbbb  lea     rdx, [rsp+130h+var_C8]
0x18000cbc0  xor     r8d, r8d
0x18000cbc3  mov     [rsp+130h+var_C0], r12
0x18000cbc8  mov     ecx, 3
0x18000cbcd  mov     [rsp+130h+var_C8], rbx
0x18000cbd2  call    cs:__imp_I_CertDiagControl
0x18000cbd8  mov     rcx, [rbp+37h+lpFileTime1]; lpFileTime1
0x18000cbdc  test    rcx, rcx
0x18000cbdf  jz      loc_18000CCEE
0x18000cbe5  cmp     [rsp+130h+var_E0], 0
0x18000cbea  mov     r15, [rbx+18h]
0x18000cbee  jnz     loc_18000CE7F
0x18000cbf4  lea     rdx, [r15+38h]; lpFileTime2
0x18000cbf8  call    cs:__imp_CompareFileTime
0x18000cbfe  test    eax, eax
0x18000cc00  jg      loc_18000CD6C
0x18000cc06  test    sil, 8
0x18000cc0a  jnz     loc_18000CCEE
0x18000cc10  mov     rsi, [rsp+130h+var_B8]
0x18000cc15  xor     eax, eax
0x18000cc17  xorps   xmm0, xmm0
0x18000cc1a  mov     [rbp+37h+var_48], rax
0x18000cc1e  movups  [rbp+37h+var_68], xmm0
0x18000cc22  mov     rax, [rsi+18h]
0x18000cc26  movups  [rbp+37h+var_58], xmm0
0x18000cc2a  cmp     dword ptr [rax+4], 0
0x18000cc2e  jz      loc_18000CDF7
0x18000cc34  mov     rax, [rsi+28h]
0x18000cc38  mov     rcx, [rax]
0x18000cc3b  xor     eax, eax
0x18000cc3d  mov     [rsp+130h+var_E0], eax
0x18000cc41  mov     [rsp+130h+var_D8], eax
0x18000cc45  mov     qword ptr [rsp+130h+SystemTimeAsFileTime.dwLowDateTime], rax
0x18000cc4a  test    rcx, rcx
0x18000cc4d  jz      loc_18000CCEE
0x18000cc53  mov     r15d, [rcx+10h]
0x18000cc57  test    r15d, r15d
0x18000cc5a  jz      loc_18000CCEE
0x18000cc60  cmp     [rcx+8], eax
0x18000cc63  jz      loc_18000CDDF
0x18000cc69  mov     r12, [r13+18h]
0x18000cc6d  lea     rdx, [rsp+130h+var_D8]; unsigned int *
0x18000cc72  lea     rcx, [rsp+130h+var_E0]; unsigned int *
0x18000cc77  call    ?I_GetMaxAgeParameters@@YAXPEAK0@Z; I_GetMaxAgeParameters(ulong *,ulong *)
0x18000cc7c  mov     esi, [rsp+130h+var_E0]
0x18000cc80  cmp     r15d, esi
0x18000cc83  jb      short loc_18000CC92
0x18000cc85  cmp     r15d, [rsp+130h+var_D8]
0x18000cc8a  mov     esi, r15d
0x18000cc8d  cmova   esi, [rsp+130h+var_D8]
0x18000cc92  lea     rcx, [rsp+130h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18000cc97  call    cs:__imp_GetSystemTimeAsFileTime
0x18000cc9d  shr     esi, 1
0x18000cc9f  lea     eax, [rsi+12Ch]
0x18000cca5  imul    rcx, rax, 989680h
0x18000ccac  add     rcx, qword ptr [rsp+130h+SystemTimeAsFileTime.dwLowDateTime]
0x18000ccb1  mov     [r12], rcx
0x18000ccb5  jmp     short loc_18000CCEE
0x18000ccb7  mov     ecx, 0Dh; dwErrCode
0x18000ccbc  call    cs:__imp_SetLastError
0x18000ccc2  call    cs:__imp_GetLastError
0x18000ccc8  mov     rdx, [rbp+37h+var_98]
0x18000cccc  lea     rcx, aCryptnetDllOcs; "CRYPTNET.DLL --> OCSP URL: %S, failed: "...
0x18000ccd3  mov     r9d, eax
0x18000ccd6  mov     r8d, eax
0x18000ccd9  call    ?I_CryptNetDebugErrorPrintfA@@YAXPEBDZZ; I_CryptNetDebugErrorPrintfA(char const *,...)
0x18000ccde  test    rbx, rbx
0x18000cce1  jz      short loc_18000CCEE
0x18000cce3  mov     rcx, rbx; pCrlContext
0x18000cce6  call    cs:__imp_CertFreeCRLContext
0x18000ccec  xor     ebx, ebx
0x18000ccee  call    cs:__imp_GetLastError
0x18000ccf4  mov     rcx, [rbp+37h+pv]; pv
0x18000ccf8  mov     esi, eax
0x18000ccfa  test    rcx, rcx
0x18000ccfd  jz      short loc_18000CD05
0x18000ccff  call    cs:__imp_CryptMemFree
0x18000cd05  mov     rcx, [rbp+37h+pv+8]; hMem
0x18000cd09  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000cd0e  mov     rcx, [rbp+37h+hMem]; hMem
0x18000cd12  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000cd17  xorps   xmm0, xmm0
0x18000cd1a  xor     eax, eax
0x18000cd1c  mov     ecx, esi; dwErrCode
0x18000cd1e  mov     [rbp+37h+hMem], rax
0x18000cd22  movups  xmmword ptr [rbp+37h+pv], xmm0
0x18000cd26  call    cs:__imp_SetLastError
0x18000cd2c  mov     rcx, r14; hMem
0x18000cd2f  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000cd34  test    rdi, rdi
0x18000cd37  jz      short loc_18000CD42
0x18000cd39  mov     rcx, rdi; pCertContext
0x18000cd3c  call    cs:__imp_CertFreeCertificateContext
0x18000cd42  mov     rax, rbx
0x18000cd45  mov     rcx, [rbp+37h+var_38]
0x18000cd49  xor     rcx, rsp; StackCookie
0x18000cd4c  call    __security_check_cookie
0x18000cd51  mov     rbx, [rsp+130h+arg_10]
0x18000cd59  add     rsp, 100h
0x18000cd60  pop     r15
0x18000cd62  pop     r14
0x18000cd64  pop     r13
0x18000cd66  pop     r12
0x18000cd68  pop     rdi
0x18000cd69  pop     rsi
0x18000cd6a  pop     rbp
0x18000cd6b  retn
0x18000cd6c  cmp     dword ptr [r15+38h], 0
0x18000cd71  jz      loc_18000CE64
0x18000cd77  mov     rax, [rbx+18h]
0x18000cd7b  mov     rcx, [rax+38h]
0x18000cd7f  mov     rax, [rbp+37h+var_70]
0x18000cd83  mov     [rax], rcx
0x18000cd86  cmp     [rsp+130h+var_E0], 0
0x18000cd8b  lea     rcx, aChecktimevalid; "CheckTimeValidity"
0x18000cd92  xorps   xmm0, xmm0
0x18000cd95  mov     qword ptr [rbp+37h+var_68], rbx
0x18000cd99  lea     rax, aCheckfreshness; "CheckFreshnessTime"
0x18000cda0  mov     qword ptr [rbp+37h+var_58], 78Bh
0x18000cda8  cmovz   rax, rcx
0x18000cdac  mov     [rbp+37h+var_40], esi
0x18000cdaf  mov     qword ptr [rbp+37h+var_68+8], rax
0x18000cdb3  lea     rdx, [rbp+37h+var_68]
0x18000cdb7  xor     eax, eax
0x18000cdb9  xor     r8d, r8d
0x18000cdbc  mov     ecx, 5
0x18000cdc1  mov     [rbp+37h+var_3C], eax
0x18000cdc4  movdqu  [rbp+37h+var_58+8], xmm0
0x18000cdc9  call    cs:__imp_I_CertDiagControl
0x18000cdcf  mov     ecx, 800B0101h; dwErrCode
0x18000cdd4  call    cs:__imp_SetLastError
0x18000cdda  jmp     loc_18000CCE3
0x18000cddf  cmp     [rcx+0Ch], eax
0x18000cde2  jnz     loc_18000CC69
0x18000cde8  cmp     [rcx+18h], rax
0x18000cdec  jnz     loc_18000CC69
0x18000cdf2  jmp     loc_18000CCEE
0x18000cdf7  mov     rdx, [rbx+18h]
0x18000cdfb  cmp     dword ptr [rdx+38h], 0
0x18000cdff  jz      short loc_18000CE74
0x18000ce01  mov     rax, [rsi+8]
0x18000ce05  lea     rcx, a136141311214; "1.3.6.1.4.1.311.21.4"
0x18000ce0c  mov     r15, [rsi+30h]
0x18000ce10  mov     dword ptr [rbp+37h+var_68], 28h ; '('
0x18000ce17  mov     qword ptr [rbp+37h+var_68+4], 3
0x18000ce1f  mov     [rsp+130h+var_B8], rax
0x18000ce24  mov     rax, [rdx+30h]
0x18000ce28  mov     qword ptr [rbp+37h+var_58], rax
0x18000ce2c  mov     rax, [rdx+38h]
0x18000ce30  mov     qword ptr [rbp+37h+var_58+8], rax
0x18000ce34  mov     r8, [rdx+58h]; rgExtensions
0x18000ce38  mov     edx, [rdx+50h]; cExtensions
0x18000ce3b  call    cs:__imp_CertFindExtension
0x18000ce41  test    rax, rax
0x18000ce44  jnz     short loc_18000CE96
0x18000ce46  mov     rdx, [rsp+130h+var_B8]
0x18000ce4b  lea     r9, [rbp+37h+var_68]
0x18000ce4f  xor     r8d, r8d
0x18000ce52  mov     qword ptr [rsp+130h+dwFlags], r15
0x18000ce57  mov     rcx, r12
0x18000ce5a  call    I_CryptNetSetUrlCachePreFetchInfo
0x18000ce5f  jmp     loc_18000CC34
0x18000ce64  cmp     dword ptr [r15+3Ch], 0
0x18000ce69  jz      loc_18000CC06
0x18000ce6f  jmp     loc_18000CD77
0x18000ce74  cmp     dword ptr [rdx+3Ch], 0
0x18000ce78  jnz     short loc_18000CE01
0x18000ce7a  jmp     loc_18000CC34
0x18000ce7f  lea     rdx, [r15+30h]; lpFileTime2
0x18000ce83  call    cs:__imp_CompareFileTime
0x18000ce89  test    eax, eax
0x18000ce8b  jg      loc_18000CD86
0x18000ce91  jmp     loc_18000CC06
0x18000ce96  mov     r9d, [rax+10h]; cbEncoded
0x18000ce9a  lea     rcx, [rsp+130h+var_D8]
0x18000ce9f  mov     r8, [rax+18h]; pbEncoded
0x18000cea3  mov     edx, 1Eh; lpszStructType
0x18000cea8  mov     [rsp+130h+pcbStructInfo], rcx; pcbStructInfo
0x18000cead  lea     rcx, [rbp+37h+var_48]
0x18000ceb1  mov     [rsp+130h+pvStructInfo], rcx; pvStructInfo
0x18000ceb6  mov     ecx, 10001h; dwCertEncodingType
0x18000cebb  mov     [rsp+130h+var_D8], 8
0x18000cec3  mov     [rsp+130h+dwFlags], 0; dwFlags
0x18000cecb  call    cs:__imp_CryptDecodeObject
0x18000ced1  test    eax, eax
0x18000ced3  jnz     loc_18000CE46
0x18000ced9  xor     eax, eax
0x18000cedb  mov     [rbp+37h+var_48], rax
0x18000cedf  jmp     loc_18000CE46
```
