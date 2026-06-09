# CertDllVerifyCTLUsage(ulong,ulong,void *,_CTL_USAGE *,ulong,_CTL_VERIFY_USAGE_PARA *,_CTL_VERIFY_USAGE_STATUS *)

- ea: `0x18001c790`
- end: `0x18001cb32`
- name: `?CertDllVerifyCTLUsage@@YAHKKPEAXPEAU_CTL_USAGE@@KPEAU_CTL_VERIFY_USAGE_PARA@@PEAU_CTL_VERIFY_USAGE_STATUS@@@Z`
- size: `930`
- prototype: `__int64 __fastcall(DWORD, DWORD, void *, struct _CTL_USAGE *, unsigned int, struct _CTL_VERIFY_USAGE_PARA *, struct _CTL_VERIFY_USAGE_STATUS *)`
- caller_count: `0`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18001c790`
- `0x18001cb38`
- `0x18001cbf0`
- `0x18001cd44`
- `0x18001cdf4`
- `0x1800265b0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001cb0a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001cb0a`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x18001c83a`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x18001c83a`
- `CRYPT32!CertFindCTLInStore` at `0x18001c8da`
- `CRYPT32!CertFindCTLInStore` at `0x18001c8da`
- `CRYPT32!CertDuplicateCTLContext` at `0x18001ca15`
- `CRYPT32!CertDuplicateCTLContext` at `0x18001ca15`
- `CRYPT32!CertFindSubjectInCTL` at `0x18001ca33`
- `CRYPT32!CertFindSubjectInCTL` at `0x18001ca33`
- `CRYPT32!CertFreeCTLContext` at `0x18001c9d1`
- `CRYPT32!CertFreeCTLContext` at `0x18001ca66`
- `CRYPT32!CertFreeCTLContext` at `0x18001ca98`
- `CRYPT32!CertFreeCTLContext` at `0x18001caaf`
- `CRYPT32!CertFreeCTLContext` at `0x18001cad7`
- `CRYPT32!CertFreeCTLContext` at `0x18001c9d1`
- `CRYPT32!CertFreeCTLContext` at `0x18001ca66`
- `CRYPT32!CertFreeCTLContext` at `0x18001ca98`
- `CRYPT32!CertFreeCTLContext` at `0x18001caaf`
- `CRYPT32!CertFreeCTLContext` at `0x18001cad7`
- `CRYPT32!CertDuplicateCertificateContext` at `0x18001ca83`
- `CRYPT32!CertDuplicateCertificateContext` at `0x18001ca83`
- `CRYPT32!CertFreeCertificateContext` at `0x18001cabe`
- `CRYPT32!CertFreeCertificateContext` at `0x18001cabe`
- `CRYPT32!CertAddCTLContextToStore` at `0x18001c9c4`
- `CRYPT32!CertAddCTLContextToStore` at `0x18001c9c4`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18001c956`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18001c956`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x18001c848`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x18001c848`

## pseudocode

```c
__int64 __fastcall CertDllVerifyCTLUsage(
        DWORD a1,
        DWORD a2,
        void *a3,
        struct _CTL_USAGE *a4,
        unsigned int a5,
        struct _CTL_VERIFY_USAGE_PARA *a6,
        struct _CTL_VERIFY_USAGE_STATUS *a7)
{
  DWORD v8; // edi
  DWORD cCtlStore; // r14d
  HCERTSTORE *rghCtlStore; // rax
  unsigned int v11; // esi
  DWORD v12; // ecx
  void **v13; // rbx
  void *v14; // rax
  CTL_CONTEXT *pPrevCtlContext; // r15
  const FILETIME *pCtlInfo; // rdx
  const CTL_CONTEXT *v17; // rbx
  const CTL_CONTEXT *v18; // rcx
  PCCTL_CONTEXT v19; // rbx
  PCTL_ENTRY SubjectInCTL; // rax
  PCCTL_CONTEXT *ppCtl; // rax
  bool v22; // zf
  PCCERT_CONTEXT *ppSigner; // rbx
  unsigned int v24; // r15d
  unsigned int v25; // ebx
  DWORD v27; // [rsp+40h] [rbp-91h]
  _BYTE v28[12]; // [rsp+44h] [rbp-8Dh] BYREF
  PCCTL_CONTEXT pCtlContext; // [rsp+50h] [rbp-81h] BYREF
  DWORD dwMsgAndCertEncodingType; // [rsp+58h] [rbp-79h]
  PCCERT_CONTEXT pCertContext; // [rsp+60h] [rbp-71h] BYREF
  void **v32; // [rsp+68h] [rbp-69h]
  DWORD dwSubjectType; // [rsp+70h] [rbp-61h]
  struct _FILETIME FileTime; // [rsp+78h] [rbp-59h] BYREF
  void *pvSubject; // [rsp+80h] [rbp-51h]
  _OWORD pvFindPara[3]; // [rsp+88h] [rbp-49h] BYREF
  struct _SYSTEMTIME SystemTime; // [rsp+B8h] [rbp-19h] BYREF

  pvSubject = a3;
  dwSubjectType = a2;
  dwMsgAndCertEncodingType = a1;
  v8 = -2146885592;
  FileTime = 0;
  pCtlContext = 0;
  pCertContext = 0;
  *(_QWORD *)v28 = 0;
  memset(pvFindPara, 0, sizeof(pvFindPara));
  if ( a6 && (cCtlStore = a6->cCtlStore) != 0 )
  {
    rghCtlStore = a6->rghCtlStore;
    v11 = a5;
  }
  else
  {
    MSCtlOpenDefaultStores();
    rghCtlStore = (HCERTSTORE *)&xmmword_1800328E0;
    v11 = a5 & 0xFFFFFFFE;
    cCtlStore = 1;
  }
  v32 = rghCtlStore;
  SystemTime = 0;
  GetSystemTime(&SystemTime);
  SystemTimeToFileTime(&SystemTime, &FileTime);
  v12 = 0;
  v27 = 0;
  memset(pvFindPara, 0, sizeof(pvFindPara));
  LODWORD(pvFindPara[0]) = 48;
  if ( a4 )
  {
    v12 = (v11 & 8) == 0;
    v27 = v12;
    *(struct _CTL_USAGE *)((char *)pvFindPara + 8) = *a4;
  }
  if ( a6 )
    *(CRYPT_DATA_BLOB *)((char *)&pvFindPara[1] + 8) = a6->ListIdentifier;
  v13 = v32;
  do
  {
    if ( !v8 )
      break;
    v14 = *v13;
    *(_QWORD *)&SystemTime.wYear = v14;
    if ( !v14 )
      goto LABEL_44;
    pPrevCtlContext = 0;
    while ( 1 )
    {
      pPrevCtlContext = (CTL_CONTEXT *)CertFindCTLInStore(
                                         v14,
                                         dwMsgAndCertEncodingType,
                                         v12,
                                         3u,
                                         pvFindPara,
                                         pPrevCtlContext);
      if ( !pPrevCtlContext )
        break;
      pCtlContext = 0;
      pCertContext = 0;
      *(_DWORD *)v28 = 0;
      *(_DWORD *)&v28[4] = VerifyCtl(pPrevCtlContext, v11, a6, &pCertContext, v28);
      if ( *(_DWORD *)&v28[4] == 1 )
      {
        if ( (v11 & 4) != 0 )
          goto LABEL_25;
        pCtlInfo = (const FILETIME *)pPrevCtlContext->pCtlInfo;
        if ( !pCtlInfo[8].dwLowDateTime && !pCtlInfo[8].dwHighDateTime )
          goto LABEL_25;
        if ( CompareFileTime(pCtlInfo + 8, &FileTime) >= 0 )
          goto LABEL_25;
        *(_DWORD *)&v28[4] = GetTimeValidCtl(
                               &FileTime,
                               pPrevCtlContext,
                               (LPVOID *)&pCtlContext,
                               (__int64)&pCertContext,
                               (__int64)v28);
        if ( *(_DWORD *)&v28[4] == 1 )
        {
          if ( (v11 & 1) == 0 )
          {
            v17 = pCtlContext;
            *(_QWORD *)&v28[4] = 0;
            if ( CertAddCTLContextToStore(*(HCERTSTORE *)&SystemTime.wYear, pCtlContext, 5u, (PCCTL_CONTEXT *)&v28[4]) )
            {
              CertFreeCTLContext(v17);
              v17 = *(const CTL_CONTEXT **)&v28[4];
            }
            pCtlContext = v17;
            a7->dwFlags |= 1u;
          }
          *(_DWORD *)&v28[4] = CompareCtlUsage(v27, pvFindPara, pCtlContext);
          if ( *(_DWORD *)&v28[4] != 1 )
            goto LABEL_37;
LABEL_25:
          v18 = pCtlContext;
          if ( !pCtlContext )
            v18 = pPrevCtlContext;
          v19 = CertDuplicateCTLContext(v18);
          SubjectInCTL = CertFindSubjectInCTL(dwMsgAndCertEncodingType, dwSubjectType, pvSubject, v19, 0);
          if ( SubjectInCTL )
          {
            a7->dwCtlEntryIndex = SubjectInCTL - v19->pCtlInfo->rgCTLEntry;
            ppCtl = a7->ppCtl;
            if ( ppCtl )
              *ppCtl = v19;
            else
              CertFreeCTLContext(v19);
            v22 = a7->ppSigner == 0;
            a7->dwSignerIndex = *(_DWORD *)v28;
            if ( !v22 )
            {
              ppSigner = a7->ppSigner;
              *ppSigner = CertDuplicateCertificateContext(pCertContext);
            }
            v8 = 0;
          }
          else
          {
            v8 = -2146885590;
            CertFreeCTLContext(v19);
          }
          goto LABEL_37;
        }
        v8 = -2146885591;
      }
      else
      {
        v8 = -2146885589;
      }
LABEL_37:
      if ( pCtlContext )
        CertFreeCTLContext(pCtlContext);
      if ( pCertContext )
        CertFreeCertificateContext(pCertContext);
      v14 = *(void **)&SystemTime.wYear;
      v12 = v27;
      if ( !v8 )
      {
        CertFreeCTLContext(pPrevCtlContext);
        break;
      }
    }
    v12 = v27;
    v13 = v32;
LABEL_44:
    v32 = ++v13;
    --cCtlStore;
  }
  while ( cCtlStore );
  v24 = *(_DWORD *)&v28[4];
  v25 = 0;
  a7->dwError = v8;
  if ( !v8 )
    v25 = v24;
  SetLastError(v8);
  return v25;
}

```

## disassembly

```asm
0x18001c790  push    rbp
0x18001c792  push    rbx
0x18001c793  push    rsi
0x18001c794  push    rdi
0x18001c795  push    r12
0x18001c797  push    r13
0x18001c799  push    r14
0x18001c79b  push    r15
0x18001c79d  lea     rbp, [rsp-7]
0x18001c7a2  sub     rsp, 0D8h
0x18001c7a9  mov     rax, cs:__security_cookie
0x18001c7b0  xor     rax, rsp
0x18001c7b3  mov     [rbp+3Fh+var_48], rax
0x18001c7b7  mov     r12, [rbp+3Fh+arg_28]
0x18001c7bb  xor     eax, eax
0x18001c7bd  mov     r13, [rbp+3Fh+arg_30]
0x18001c7c1  xorps   xmm0, xmm0
0x18001c7c4  mov     [rbp+3Fh+pvSubject], r8
0x18001c7c8  mov     rbx, r9
0x18001c7cb  mov     [rbp+3Fh+dwSubjectType], edx
0x18001c7ce  mov     r15d, eax
0x18001c7d1  mov     [rbp+3Fh+dwMsgAndCertEncodingType], ecx
0x18001c7d4  mov     edi, 80092028h
0x18001c7d9  mov     dword ptr [rsp+110h+var_CC+4], eax
0x18001c7dd  mov     qword ptr [rbp+3Fh+FileTime.dwLowDateTime], rax
0x18001c7e1  mov     [rsp+110h+pCtlContext], rax
0x18001c7e6  mov     [rbp+3Fh+pCertContext], rax
0x18001c7ea  mov     dword ptr [rsp+110h+var_CC], eax
0x18001c7ee  movups  [rbp+3Fh+var_88], xmm0
0x18001c7f2  movups  [rbp+3Fh+var_78], xmm0
0x18001c7f6  movups  [rbp+3Fh+var_68], xmm0
0x18001c7fa  test    r12, r12
0x18001c7fd  jz      short loc_18001C813
0x18001c7ff  mov     r14d, [r12+18h]
0x18001c804  test    r14d, r14d
0x18001c807  jz      short loc_18001C813
0x18001c809  mov     rax, [r12+20h]
0x18001c80e  mov     esi, [rbp+3Fh+arg_20]
0x18001c811  jmp     short loc_18001C82B
0x18001c813  call    MSCtlOpenDefaultStores
0x18001c818  mov     esi, [rbp+3Fh+arg_20]
0x18001c81b  lea     rax, xmmword_1800328E0
0x18001c822  and     esi, 0FFFFFFFEh
0x18001c825  mov     r14d, 1
0x18001c82b  xorps   xmm0, xmm0
0x18001c82e  mov     [rbp+3Fh+var_A8], rax
0x18001c832  lea     rcx, [rbp+3Fh+SystemTime]; lpSystemTime
0x18001c836  movups  xmmword ptr [rbp+3Fh+SystemTime.wYear], xmm0
0x18001c83a  call    cs:__imp_GetSystemTime
0x18001c840  lea     rdx, [rbp+3Fh+FileTime]; lpFileTime
0x18001c844  lea     rcx, [rbp+3Fh+SystemTime]; lpSystemTime
0x18001c848  call    cs:__imp_SystemTimeToFileTime
0x18001c84e  xorps   xmm0, xmm0
0x18001c851  xor     ecx, ecx
0x18001c853  mov     [rsp+110h+var_D0], ecx
0x18001c857  movups  [rbp+3Fh+var_88], xmm0
0x18001c85b  mov     dword ptr [rbp+3Fh+var_88], 30h ; '0'
0x18001c862  movups  [rbp+3Fh+var_78], xmm0
0x18001c866  movups  [rbp+3Fh+var_68], xmm0
0x18001c86a  test    rbx, rbx
0x18001c86d  jz      short loc_18001C885
0x18001c86f  movups  xmm0, xmmword ptr [rbx]
0x18001c872  test    sil, 8
0x18001c876  lea     eax, [rcx+1]
0x18001c879  cmovz   ecx, eax
0x18001c87c  mov     [rsp+110h+var_D0], ecx
0x18001c880  movdqu  [rbp+3Fh+var_88+8], xmm0
0x18001c885  test    r12, r12
0x18001c888  jz      short loc_18001C895
0x18001c88a  movups  xmm0, xmmword ptr [r12+8]
0x18001c890  movdqu  [rbp+3Fh+var_78+8], xmm0
0x18001c895  test    r14d, r14d
0x18001c898  jz      loc_18001CAFC
0x18001c89e  mov     rbx, [rbp+3Fh+var_A8]
0x18001c8a2  test    edi, edi
0x18001c8a4  jz      loc_18001CAF7
0x18001c8aa  mov     rax, [rbx]
0x18001c8ad  mov     qword ptr [rbp+3Fh+SystemTime.wYear], rax
0x18001c8b1  test    rax, rax
0x18001c8b4  jz      loc_18001CAE5
0x18001c8ba  xor     r15d, r15d
0x18001c8bd  lea     rdx, [rbp+3Fh+var_88]
0x18001c8c1  mov     [rsp+110h+pPrevCtlContext], r15; pPrevCtlContext
0x18001c8c6  mov     [rsp+110h+pvFindPara], rdx; pvFindPara
0x18001c8cb  mov     r8d, ecx; dwFindFlags
0x18001c8ce  mov     edx, [rbp+3Fh+dwMsgAndCertEncodingType]; dwMsgAndCertEncodingType
0x18001c8d1  mov     r9d, 3; dwFindType
0x18001c8d7  mov     rcx, rax; hCertStore
0x18001c8da  call    cs:__imp_CertFindCTLInStore
0x18001c8e0  mov     r15, rax
0x18001c8e3  test    rax, rax
0x18001c8e6  jz      loc_18001CADD
0x18001c8ec  lea     rax, [rsp+110h+var_CC]
0x18001c8f1  mov     [rsp+110h+pCtlContext], 0
0x18001c8fa  lea     r9, [rbp+3Fh+pCertContext]
0x18001c8fe  mov     [rsp+110h+pvFindPara], rax
0x18001c903  mov     r8, r12
0x18001c906  mov     [rbp+3Fh+pCertContext], 0
0x18001c90e  mov     edx, esi
0x18001c910  mov     dword ptr [rsp+110h+var_CC], 0
0x18001c918  mov     rcx, r15
0x18001c91b  call    VerifyCtl
0x18001c920  mov     ebx, 1
0x18001c925  mov     dword ptr [rsp+110h+var_CC+4], eax
0x18001c929  cmp     eax, ebx
0x18001c92b  jnz     loc_18001CAA0
0x18001c931  test    sil, 4
0x18001c935  jnz     loc_18001CA08
0x18001c93b  mov     rdx, [r15+18h]
0x18001c93f  lea     rcx, [rdx+40h]; lpFileTime1
0x18001c943  cmp     dword ptr [rcx], 0
0x18001c946  jnz     short loc_18001C952
0x18001c948  cmp     dword ptr [rdx+44h], 0
0x18001c94c  jz      loc_18001CA08
0x18001c952  lea     rdx, [rbp+3Fh+FileTime]; lpFileTime2
0x18001c956  call    cs:__imp_CompareFileTime
0x18001c95c  test    eax, eax
0x18001c95e  jns     loc_18001CA08
0x18001c964  lea     rax, [rsp+110h+var_CC]
0x18001c969  mov     r9, r12
0x18001c96c  mov     [rsp+110h+var_E0], rax; __int64
0x18001c971  lea     rcx, [rbp+3Fh+FileTime]; pftValidFor
0x18001c975  lea     rax, [rbp+3Fh+pCertContext]
0x18001c979  mov     r8d, esi
0x18001c97c  mov     [rsp+110h+pPrevCtlContext], rax; __int64
0x18001c981  mov     rdx, r15; pvPara
0x18001c984  lea     rax, [rsp+110h+pCtlContext]
0x18001c989  mov     [rsp+110h+pvFindPara], rax; LPVOID *
0x18001c98e  call    GetTimeValidCtl
0x18001c993  mov     dword ptr [rsp+110h+var_CC+4], eax
0x18001c997  cmp     eax, ebx
0x18001c999  jnz     loc_18001CA5C
0x18001c99f  test    bl, sil
0x18001c9a2  jnz     short loc_18001C9EA
0x18001c9a4  mov     rbx, [rsp+110h+pCtlContext]
0x18001c9a9  lea     r9, [rsp+110h+var_CC+4]; ppStoreContext
0x18001c9ae  mov     rcx, qword ptr [rbp+3Fh+SystemTime.wYear]; hCertStore
0x18001c9b2  mov     rdx, rbx; pCtlContext
0x18001c9b5  mov     r8d, 5; dwAddDisposition
0x18001c9bb  mov     qword ptr [rsp+110h+var_CC+4], 0
0x18001c9c4  call    cs:__imp_CertAddCTLContextToStore
0x18001c9ca  test    eax, eax
0x18001c9cc  jz      short loc_18001C9DC
0x18001c9ce  mov     rcx, rbx; pCtlContext
0x18001c9d1  call    cs:__imp_CertFreeCTLContext
0x18001c9d7  mov     rbx, qword ptr [rsp+110h+var_CC+4]
0x18001c9dc  mov     [rsp+110h+pCtlContext], rbx
0x18001c9e1  mov     ebx, 1
0x18001c9e6  or      [r13+8], ebx
0x18001c9ea  mov     r8, [rsp+110h+pCtlContext]
0x18001c9ef  lea     rdx, [rbp+3Fh+var_88]
0x18001c9f3  mov     ecx, [rsp+110h+var_D0]
0x18001c9f7  call    CompareCtlUsage
0x18001c9fc  mov     dword ptr [rsp+110h+var_CC+4], eax
0x18001ca00  cmp     eax, ebx
0x18001ca02  jnz     loc_18001CAA5
0x18001ca08  mov     rcx, [rsp+110h+pCtlContext]
0x18001ca0d  test    rcx, rcx
0x18001ca10  jnz     short loc_18001CA15
0x18001ca12  mov     rcx, r15; pCtlContext
0x18001ca15  call    cs:__imp_CertDuplicateCTLContext
0x18001ca1b  mov     r8, [rbp+3Fh+pvSubject]; pvSubject
0x18001ca1f  mov     r9, rax; pCtlContext
0x18001ca22  mov     edx, [rbp+3Fh+dwSubjectType]; dwSubjectType
0x18001ca25  mov     rbx, rax
0x18001ca28  mov     ecx, [rbp+3Fh+dwMsgAndCertEncodingType]; dwEncodingType
0x18001ca2b  mov     dword ptr [rsp+110h+pvFindPara], 0; dwFlags
0x18001ca33  call    cs:__imp_CertFindSubjectInCTL
0x18001ca39  test    rax, rax
0x18001ca3c  jz      short loc_18001CA90
0x18001ca3e  mov     rcx, [rbx+18h]
0x18001ca42  sub     rax, [rcx+68h]
0x18001ca46  sar     rax, 5
0x18001ca4a  mov     [r13+18h], eax
0x18001ca4e  mov     rax, [r13+10h]
0x18001ca52  test    rax, rax
0x18001ca55  jz      short loc_18001CA63
0x18001ca57  mov     [rax], rbx
0x18001ca5a  jmp     short loc_18001CA6C
0x18001ca5c  mov     edi, 80092029h
0x18001ca61  jmp     short loc_18001CAA5
0x18001ca63  mov     rcx, rbx; pCtlContext
0x18001ca66  call    cs:__imp_CertFreeCTLContext
0x18001ca6c  cmp     qword ptr [r13+20h], 0
0x18001ca71  mov     eax, dword ptr [rsp+110h+var_CC]
0x18001ca75  mov     [r13+28h], eax
0x18001ca79  jz      short loc_18001CA8C
0x18001ca7b  mov     rcx, [rbp+3Fh+pCertContext]; pCertContext
0x18001ca7f  mov     rbx, [r13+20h]
0x18001ca83  call    cs:__imp_CertDuplicateCertificateContext
0x18001ca89  mov     [rbx], rax
0x18001ca8c  xor     edi, edi
0x18001ca8e  jmp     short loc_18001CAA5
0x18001ca90  mov     rcx, rbx; pCtlContext
0x18001ca93  mov     edi, 8009202Ah
0x18001ca98  call    cs:__imp_CertFreeCTLContext
0x18001ca9e  jmp     short loc_18001CAA5
0x18001caa0  mov     edi, 8009202Bh
0x18001caa5  mov     rcx, [rsp+110h+pCtlContext]; pCtlContext
0x18001caaa  test    rcx, rcx
0x18001caad  jz      short loc_18001CAB5
0x18001caaf  call    cs:__imp_CertFreeCTLContext
0x18001cab5  mov     rcx, [rbp+3Fh+pCertContext]; pCertContext
0x18001cab9  test    rcx, rcx
0x18001cabc  jz      short loc_18001CAC4
0x18001cabe  call    cs:__imp_CertFreeCertificateContext
0x18001cac4  mov     rax, qword ptr [rbp+3Fh+SystemTime.wYear]
0x18001cac8  mov     ecx, [rsp+110h+var_D0]
0x18001cacc  test    edi, edi
0x18001cace  jnz     loc_18001C8BD
0x18001cad4  mov     rcx, r15; pCtlContext
0x18001cad7  call    cs:__imp_CertFreeCTLContext
0x18001cadd  mov     ecx, [rsp+110h+var_D0]
0x18001cae1  mov     rbx, [rbp+3Fh+var_A8]
0x18001cae5  add     rbx, 8
0x18001cae9  mov     [rbp+3Fh+var_A8], rbx
0x18001caed  add     r14d, 0FFFFFFFFh
0x18001caf1  jnz     loc_18001C8A2
0x18001caf7  mov     r15d, dword ptr [rsp+110h+var_CC+4]
0x18001cafc  xor     ebx, ebx
0x18001cafe  mov     [r13+4], edi
0x18001cb02  test    edi, edi
0x18001cb04  mov     ecx, edi; dwErrCode
0x18001cb06  cmovz   ebx, r15d
0x18001cb0a  call    cs:__imp_SetLastError
0x18001cb10  mov     eax, ebx
0x18001cb12  mov     rcx, [rbp+3Fh+var_48]
0x18001cb16  xor     rcx, rsp; StackCookie
0x18001cb19  call    __security_check_cookie
0x18001cb1e  add     rsp, 0D8h
0x18001cb25  pop     r15
0x18001cb27  pop     r14
0x18001cb29  pop     r13
0x18001cb2b  pop     r12
0x18001cb2d  pop     rdi
0x18001cb2e  pop     rsi
0x18001cb2f  pop     rbx
0x18001cb30  pop     rbp
0x18001cb31  retn
```
