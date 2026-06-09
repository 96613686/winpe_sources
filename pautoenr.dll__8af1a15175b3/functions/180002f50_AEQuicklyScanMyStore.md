# AEQuicklyScanMyStore

- ea: `0x180002f50`
- end: `0x18000372f`
- name: `AEQuicklyScanMyStore`
- size: `2015`
- prototype: `_BOOL8 __fastcall(int, int, unsigned int, PCCERT_CONTEXT **, unsigned __int64 *, _DWORD *, char)`
- caller_count: `2`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180001d90`
- `0x180006974`

## callees

- `0x180002f50`
- `0x180003740`
- `0x180003a30`
- `0x180004bb0`
- `0x180004bf0`
- `0x180004cd0`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x180003260`
- `msvcrt!_wcsicmp` at `0x180003466`
- `msvcrt!_wcsicmp` at `0x1800034b7`
- `msvcrt!_wcsicmp` at `0x180003260`
- `msvcrt!_wcsicmp` at `0x180003466`
- `msvcrt!_wcsicmp` at `0x1800034b7`
- `msvcrt!free` at `0x180003106`
- `msvcrt!free` at `0x180003106`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000371a`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000371a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800031e8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000365a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800031e8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000365a`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x1800031b7`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x1800031b7`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180002fa7`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180002fa7`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000320a`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180003647`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000320a`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180003647`
- `api-ms-win-core-heap-l2-1-0!LocalReAlloc` at `0x18000329b`
- `api-ms-win-core-heap-l2-1-0!LocalReAlloc` at `0x1800032e5`
- `api-ms-win-core-heap-l2-1-0!LocalReAlloc` at `0x18000329b`
- `api-ms-win-core-heap-l2-1-0!LocalReAlloc` at `0x1800032e5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800030ba`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800030ce`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000313c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800036af`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800036ed`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180003724`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800030ba`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800030ce`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000313c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800036af`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800036ed`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180003724`
- `CRYPT32!CertGetCertificateContextProperty` at `0x1800031de`
- `CRYPT32!CertGetCertificateContextProperty` at `0x1800031de`
- `CRYPT32!CertOpenStore` at `0x180002fec`
- `CRYPT32!CertOpenStore` at `0x18000350d`
- `CRYPT32!CertOpenStore` at `0x180002fec`
- `CRYPT32!CertOpenStore` at `0x18000350d`
- `CRYPT32!CertEnumCertificatesInStore` at `0x180003023`
- `CRYPT32!CertEnumCertificatesInStore` at `0x180003023`
- `CRYPT32!CertFreeCertificateContext` at `0x180003452`
- `CRYPT32!CertFreeCertificateContext` at `0x1800036cf`
- `CRYPT32!CertFreeCertificateContext` at `0x180003452`
- `CRYPT32!CertFreeCertificateContext` at `0x1800036cf`
- `CRYPT32!CertDuplicateCertificateContext` at `0x180003220`
- `CRYPT32!CertDuplicateCertificateContext` at `0x180003220`
- `CRYPT32!CertCloseStore` at `0x1800030de`
- `CRYPT32!CertCloseStore` at `0x1800030de`
- `CRYPT32!CertVerifySubjectCertificateContext` at `0x18000343e`
- `CRYPT32!CertVerifySubjectCertificateContext` at `0x18000343e`
- `certca!__imp_CAEnumCertTypesEx` at `0x18000300d`
- `certca!__imp_CAEnumCertTypesEx` at `0x18000300d`
- `certca!__imp_CAEnumNextCertType` at `0x18000354a`
- `certca!__imp_CAEnumNextCertType` at `0x18000354a`
- `certca!__imp_CACloseCertType` at `0x1800033de`
- `certca!__imp_CACloseCertType` at `0x180003556`
- `certca!__imp_CACloseCertType` at `0x1800033de`
- `certca!__imp_CACloseCertType` at `0x180003556`
- `certca!__imp_CAGetCertTypePropertyEx` at `0x18000333e`
- `certca!__imp_CAGetCertTypePropertyEx` at `0x180003395`
- `certca!__imp_CAGetCertTypePropertyEx` at `0x18000333e`
- `certca!__imp_CAGetCertTypePropertyEx` at `0x180003395`
- `certca!__imp_CAFreeCertTypeProperty` at `0x1800033c1`
- `certca!__imp_CAFreeCertTypeProperty` at `0x18000348a`
- `certca!__imp_CAFreeCertTypeProperty` at `0x1800033c1`
- `certca!__imp_CAFreeCertTypeProperty` at `0x18000348a`
- `certca!__imp_CAGetCertTypeExpiration` at `0x18000359c`
- `certca!__imp_CAGetCertTypeExpiration` at `0x18000359c`
- `certca!__imp_CAIsCertTypeValid` at `0x18000336f`
- `certca!__imp_CAIsCertTypeValid` at `0x18000336f`

## string_xrefs

- `0x18000338e`: `msPKI-Cert-Template-OID`

## pseudocode

```c
_BOOL8 __fastcall AEQuicklyScanMyStore(
        int a1,
        int a2,
        unsigned int a3,
        PCCERT_CONTEXT **a4,
        unsigned __int64 *a5,
        _DWORD *a6,
        char a7)
{
  unsigned __int64 v8; // rsi
  PCCERT_CONTEXT *v9; // r14
  _QWORD *v10; // r12
  int v12; // ebx
  int v13; // eax
  DWORD v14; // ebx
  HCERTSTORE v15; // r15
  unsigned __int64 v16; // rdi
  PCCERT_CONTEXT v17; // rax
  unsigned __int64 v18; // rax
  unsigned __int64 v19; // rcx
  const CERT_CONTEXT *v20; // rdx
  BOOL v21; // ebx
  unsigned int v22; // esi
  unsigned int v23; // edi
  HLOCAL *v24; // r12
  int v25; // esi
  int v26; // edi
  int v28; // edx
  FILETIME NotAfter; // r9
  __int64 v30; // rcx
  HLOCAL v31; // rax
  PCCERT_CONTEXT v32; // rax
  const wchar_t *v33; // rcx
  int v34; // eax
  __int64 v35; // rdx
  bool v36; // zf
  HLOCAL v37; // rcx
  __int64 v38; // rax
  __int64 v39; // rcx
  int v40; // eax
  int i; // ecx
  void *v42; // rax
  int v43; // eax
  const wchar_t **v44; // rdx
  DWORD v45; // ecx
  unsigned __int64 v46; // rdi
  const CERT_CONTEXT *v47; // rcx
  int v48; // eax
  char v49; // cl
  _QWORD *v50; // rax
  int v51; // eax
  unsigned __int64 v52; // rcx
  unsigned int v53; // r8d
  HLOCAL v54; // rdx
  unsigned int v55; // [rsp+30h] [rbp-71h]
  unsigned int v56; // [rsp+30h] [rbp-71h]
  const wchar_t **v57; // [rsp+38h] [rbp-69h] BYREF
  HLOCAL v58; // [rsp+40h] [rbp-61h]
  int v59; // [rsp+48h] [rbp-59h]
  int v60; // [rsp+4Ch] [rbp-55h] BYREF
  HLOCAL hMem[2]; // [rsp+50h] [rbp-51h] BYREF
  _QWORD *v62; // [rsp+60h] [rbp-41h] BYREF
  __int64 v63; // [rsp+68h] [rbp-39h]
  HLOCAL v64; // [rsp+70h] [rbp-31h]
  DWORD pcbData; // [rsp+78h] [rbp-29h] BYREF
  __int64 v66; // [rsp+80h] [rbp-21h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+88h] [rbp-19h] BYREF
  __int64 v68; // [rsp+90h] [rbp-11h] BYREF
  PCERT_INFO pCertInfo; // [rsp+98h] [rbp-9h]
  FILETIME FileTime2; // [rsp+A0h] [rbp-1h] BYREF
  DWORD pdwFlags; // [rsp+F0h] [rbp+4Fh] BYREF
  int v72; // [rsp+F8h] [rbp+57h]
  unsigned int v73; // [rsp+100h] [rbp+5Fh]

  v73 = a3;
  v72 = a2;
  SystemTimeAsFileTime = 0;
  v68 = 0;
  v66 = 0;
  v8 = 0;
  v9 = 0;
  v64 = 0;
  *(_OWORD *)hMem = 0;
  v10 = 0;
  v62 = 0;
  v63 = 0;
  GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
  v12 = 0x20000;
  if ( !a1 )
    v12 = 0x10000;
  if ( !a6 || (v13 = 4, !*a6) )
    v13 = 0x8000;
  v14 = v13 | v12;
  v15 = CertOpenStore((LPCSTR)0xA, 0x10001u, 0, v14, L"MY");
  if ( v15 )
    goto LABEL_6;
  if ( (v14 & 0x8000) != 0 )
  {
    v21 = 0;
    goto LABEL_25;
  }
  v14 = v14 & 0xFFFF7FFB | 0x8000;
  v15 = CertOpenStore((LPCSTR)0xA, 0x10001u, 0, v14, L"MY");
  if ( v15 )
  {
LABEL_6:
    v57 = 0;
    if ( !(unsigned int)CAEnumCertTypesEx(0, 192, &v57) )
    {
      while ( v57 )
      {
        if ( !(unsigned int)ATL::CSimpleArray<void *>::Add(&v62, &v57) )
        {
          CACloseCertType(v57);
          break;
        }
        if ( (unsigned int)CAEnumNextCertType(v57, &v57) )
          break;
      }
      v10 = v62;
    }
    v16 = 0;
    while ( 1 )
    {
      while ( 1 )
      {
        v17 = CertEnumCertificatesInStore(v15, (PCCERT_CONTEXT)v16);
        v16 = (unsigned __int64)v17;
        if ( !v17 )
        {
          if ( !v9 )
          {
LABEL_18:
            if ( a4 )
              *a4 = v9;
            if ( a5 )
              *a5 = v8;
            if ( a6 )
              *a6 = (v14 & 0x8000) == 0;
            v21 = v8 != 0;
            goto LABEL_25;
          }
          if ( v8 )
          {
            do
            {
              if ( (unsigned int)AEIsTemplateTimeValid((__int64)hMem, (__int64)v9[v16]) )
              {
                CertFreeCertificateContext(v9[v16]);
                v9[v16] = 0;
              }
              ++v16;
            }
            while ( v16 < v8 );
          }
          if ( (v72 & 0x40) != 0 || (v46 = 0, !v8) )
          {
            v18 = 0;
            v19 = 0;
            if ( !v8 )
            {
LABEL_16:
              v8 = v18;
              if ( !v18 )
              {
                LocalFree(v9);
                v9 = 0;
              }
              goto LABEL_18;
            }
          }
          else
          {
            do
            {
              v47 = v9[v46];
              if ( v47 )
              {
                pdwFlags = 1;
                if ( CertVerifySubjectCertificateContext(v47, v47, &pdwFlags) )
                {
                  if ( (pdwFlags & 1) == 0 )
                  {
                    CertFreeCertificateContext(v9[v46]);
                    v9[v46] = 0;
                  }
                }
              }
              ++v46;
            }
            while ( v46 < v8 );
            v10 = v62;
            v18 = 0;
            v19 = 0;
          }
          do
          {
            v20 = v9[v19];
            if ( v20 )
              v9[v18++] = v20;
            ++v19;
          }
          while ( v19 < v8 );
          goto LABEL_16;
        }
        pCertInfo = v17->pCertInfo;
        v59 = 0;
        LocalFree(v64);
        v64 = AEGetTemplateName(v16);
        if ( v64 )
        {
          v40 = v63;
          if ( (int)v63 > 0 )
          {
            for ( i = 0; ; ++i )
            {
              v56 = i;
              if ( i >= v40 )
                goto LABEL_38;
              if ( i < 0 )
                goto LABEL_137;
              v57 = 0;
              v42 = (void *)v10[i];
              v58 = v42;
              if ( v42 )
                break;
LABEL_81:
              v40 = v63;
            }
            LOBYTE(pdwFlags) = 0;
            v43 = CAGetCertTypePropertyEx(v42, L"cn", &v57);
            v44 = v57;
            if ( v43 )
            {
LABEL_69:
              LOBYTE(v45) = pdwFlags;
              goto LABEL_70;
            }
            if ( !v57 )
              goto LABEL_73;
            if ( !*v57 )
              goto LABEL_69;
            v36 = _wcsicmp(*v57, (const wchar_t *)v64) == 0;
            v44 = v57;
            v45 = (unsigned __int8)pdwFlags;
            if ( v36 )
              v45 = 1;
            pdwFlags = v45;
LABEL_70:
            if ( v44 )
            {
              CAFreeCertTypeProperty(v58);
              LOBYTE(v45) = pdwFlags;
              v44 = 0;
              v57 = 0;
            }
            if ( (_BYTE)v45 )
            {
LABEL_78:
              if ( v44 )
                CAFreeCertTypeProperty(v58);
            }
            else
            {
LABEL_73:
              v60 = 0;
              if ( (unsigned int)CAIsCertTypeValid(v58, &v60)
                || !v60
                || (unsigned int)CAGetCertTypePropertyEx(v58, L"msPKI-Cert-Template-OID", &v57) )
              {
                goto LABEL_94;
              }
              v44 = v57;
              if ( v57 )
              {
                if ( !*v57 )
                  goto LABEL_78;
                v48 = _wcsicmp(*v57, (const wchar_t *)v64);
                v49 = pdwFlags;
                if ( !v48 )
                  v49 = 1;
                LOBYTE(pdwFlags) = v49;
LABEL_94:
                v44 = v57;
                goto LABEL_78;
              }
            }
            i = v56;
            if ( (_BYTE)pdwFlags )
            {
              if ( (int)v56 >= (int)v63 || !*(_QWORD *)ATL::CSimpleArray<void *>::operator[](&v62, v56) )
                goto LABEL_38;
              v50 = (_QWORD *)ATL::CSimpleArray<void *>::operator[](&v62, v56);
              v51 = CAGetCertTypeExpiration(*v50, &v68, &v66);
              v28 = v59;
              if ( !v51 )
                v28 = 1;
              goto LABEL_39;
            }
            goto LABEL_81;
          }
        }
LABEL_38:
        v28 = v59;
LABEL_39:
        if ( pCertInfo )
        {
          NotAfter = pCertInfo->NotAfter;
          v60 = 0;
          v30 = *(_QWORD *)&NotAfter - *(_QWORD *)&pCertInfo->NotBefore;
          if ( !a7 && v28 && v66 )
          {
            if ( v66 < 0 )
            {
              if ( v30 / 5 <= -v66 )
              {
                v52 = (__int64)((unsigned __int128)(v30 * (__int128)0x6666666666666667LL) >> 64) >> 2;
                v30 = (v52 >> 63) + v52;
              }
              else
              {
                v30 = v66 / -2;
              }
            }
          }
          else
          {
            v30 = v73 * (v30 / 100);
          }
          FileTime2 = (FILETIME)(*(_QWORD *)&NotAfter - v30);
          if ( CompareFileTime(&SystemTimeAsFileTime, &FileTime2) > 0 )
          {
            pcbData = 0;
            v60 = 1;
            if ( !CertGetCertificateContextProperty((PCCERT_CONTEXT)v16, 0x4Du, 0, &pcbData)
              && GetLastError() == -2146885628 )
            {
              if ( a4 )
              {
                if ( v9 )
                  v31 = LocalReAlloc(v9, 8 * v8 + 8, 2u);
                else
                  v31 = LocalAlloc(0, 8u);
                v58 = v31;
                if ( !v31 )
                  goto LABEL_82;
                v32 = CertDuplicateCertificateContext((PCCERT_CONTEXT)v16);
                v9 = (PCCERT_CONTEXT *)v58;
                *((_QWORD *)v58 + v8) = v32;
              }
              ++v8;
            }
          }
          v58 = AEGetTemplateName(v16);
          v33 = (const wchar_t *)v58;
          if ( v58 )
            break;
        }
      }
      v34 = (int)hMem[1];
      v35 = 0;
      v55 = 0;
      if ( !LODWORD(hMem[1]) )
        goto LABEL_55;
      while ( 1 )
      {
        v36 = _wcsicmp(v33, *((const wchar_t **)hMem[0] + 2 * v35)) == 0;
        v34 = (int)hMem[1];
        if ( v36 )
          break;
        v33 = (const wchar_t *)v58;
        v35 = v55 + 1;
        v55 = v35;
        if ( (unsigned int)v35 >= LODWORD(hMem[1]) )
          goto LABEL_55;
      }
      v53 = v55;
      if ( v55 < LODWORD(hMem[1]) )
      {
        v37 = hMem[0];
        v54 = v58;
      }
      else
      {
LABEL_55:
        if ( hMem[0] )
        {
          v37 = LocalReAlloc(hMem[0], 16LL * (unsigned int)(v34 + 1), 2u);
          v38 = LODWORD(hMem[1]);
        }
        else
        {
          v37 = LocalAlloc(0, 0x10u);
          v38 = 0;
          LODWORD(hMem[1]) = 0;
        }
        if ( !v37 )
        {
          GetLastError();
          v54 = v58;
          goto LABEL_132;
        }
        v53 = v38;
        hMem[0] = v37;
        *((_QWORD *)v37 + 2 * v38) = v58;
        v54 = 0;
        *((_DWORD *)v37 + 4 * (unsigned int)v38 + 2) = 0;
        LODWORD(hMem[1]) = v38 + 1;
      }
      if ( !v60 )
        *((_DWORD *)v37 + 4 * v53 + 2) = 1;
      if ( v54 )
LABEL_132:
        LocalFree(v54);
    }
  }
LABEL_82:
  v21 = 0;
  if ( v9 )
    AEFreeCertArray(v9, v8);
LABEL_25:
  v22 = (unsigned int)hMem[1];
  v23 = 0;
  if ( LODWORD(hMem[1]) )
  {
    v24 = (HLOCAL *)hMem[0];
    do
      LocalFree(v24[2 * v23++]);
    while ( v23 < v22 );
    v10 = v62;
  }
  LocalFree(hMem[0]);
  if ( v15 )
    CertCloseStore(v15, 0);
  v25 = v63;
  v26 = 0;
  if ( (int)v63 > 0 )
  {
    while ( v26 >= 0 )
    {
      v39 = v10[v26];
      if ( v39 )
        CACloseCertType(v39);
      if ( ++v26 >= v25 )
        goto LABEL_32;
    }
LABEL_137:
    RaiseException(0xC000008C, 1u, 0, 0);
    __debugbreak();
  }
LABEL_32:
  if ( v64 )
    LocalFree(v64);
  if ( v10 )
    free(v10);
  return v21;
}

```

## disassembly

```asm
0x180002f50  mov     [rsp-8+arg_18], rbx
0x180002f55  mov     [rsp-8+arg_10], r8d
0x180002f5a  mov     [rsp-8+arg_8], edx
0x180002f5e  push    rbp
0x180002f5f  push    rsi
0x180002f60  push    rdi
0x180002f61  push    r12
0x180002f63  push    r13
0x180002f65  push    r14
0x180002f67  push    r15
0x180002f69  lea     rbp, [rsp-0Fh]
0x180002f6e  sub     rsp, 0B0h
0x180002f75  xor     eax, eax
0x180002f77  mov     edi, ecx
0x180002f79  xorps   xmm0, xmm0
0x180002f7c  mov     qword ptr [rbp+3Fh+SystemTimeAsFileTime.dwLowDateTime], rax
0x180002f80  lea     rcx, [rbp+3Fh+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180002f84  mov     [rbp+3Fh+var_50], rax
0x180002f88  mov     [rbp+3Fh+var_60], rax
0x180002f8c  mov     esi, eax
0x180002f8e  mov     r14d, eax
0x180002f91  mov     [rbp+3Fh+var_70], rax
0x180002f95  movups  xmmword ptr [rbp+3Fh+hMem], xmm0
0x180002f99  mov     r12d, eax
0x180002f9c  mov     [rbp+3Fh+var_80], rax
0x180002fa0  mov     [rbp+3Fh+var_78], rax
0x180002fa4  mov     r13, r9
0x180002fa7  call    cs:__imp_GetSystemTimeAsFileTime
0x180002fad  test    edi, edi
0x180002faf  mov     eax, 10000h
0x180002fb4  mov     ebx, 20000h
0x180002fb9  cmovz   ebx, eax
0x180002fbc  mov     rax, [rbp+3Fh+arg_28]
0x180002fc0  test    rax, rax
0x180002fc3  jnz     loc_1800034D9
0x180002fc9  mov     eax, 8000h
0x180002fce  or      ebx, eax
0x180002fd0  lea     rdi, aMy_0; "MY"
0x180002fd7  mov     r9d, ebx; dwFlags
0x180002fda  mov     [rsp+0E0h+pvPara], rdi; pvPara
0x180002fdf  xor     r8d, r8d; hCryptProv
0x180002fe2  mov     edx, 10001h; dwEncodingType
0x180002fe7  mov     ecx, 0Ah; lpszStoreProvider
0x180002fec  call    cs:__imp_CertOpenStore
0x180002ff2  mov     r15, rax
0x180002ff5  test    rax, rax
0x180002ff8  jz      loc_1800034EB
0x180002ffe  lea     r8, [rbp+3Fh+var_A8]
0x180003002  mov     [rbp+3Fh+var_A8], rsi
0x180003006  mov     edx, 0C0h
0x18000300b  xor     ecx, ecx
0x18000300d  call    cs:__imp_CAEnumCertTypesEx
0x180003013  test    eax, eax
0x180003015  jz      loc_18000352B
0x18000301b  xor     edi, edi
0x18000301d  mov     rdx, rdi; pPrevCertContext
0x180003020  mov     rcx, r15; hCertStore
0x180003023  call    cs:__imp_CertEnumCertificatesInStore
0x180003029  mov     rdi, rax
0x18000302c  test    rax, rax
0x18000302f  jnz     loc_180003129
0x180003035  test    r14, r14
0x180003038  jz      short loc_18000307A
0x18000303a  test    rsi, rsi
0x18000303d  jnz     loc_1800036BA
0x180003043  test    byte ptr [rbp+3Fh+arg_8], 40h
0x180003047  jz      loc_180003404
0x18000304d  xor     eax, eax
0x18000304f  xor     ecx, ecx
0x180003051  test    rsi, rsi
0x180003054  jz      short loc_18000306E
0x180003056  mov     rdx, [r14+rcx*8]
0x18000305a  test    rdx, rdx
0x18000305d  jz      short loc_180003066
0x18000305f  mov     [r14+rax*8], rdx
0x180003063  inc     rax
0x180003066  inc     rcx
0x180003069  cmp     rcx, rsi
0x18000306c  jb      short loc_180003056
0x18000306e  mov     rsi, rax
0x180003071  test    rax, rax
0x180003074  jz      loc_1800036EA
0x18000307a  test    r13, r13
0x18000307d  jz      short loc_180003083
0x18000307f  mov     [r13+0], r14
0x180003083  mov     rax, [rbp+3Fh+arg_20]
0x180003087  test    rax, rax
0x18000308a  jz      short loc_18000308F
0x18000308c  mov     [rax], rsi
0x18000308f  mov     rax, [rbp+3Fh+arg_28]
0x180003093  test    rax, rax
0x180003096  jnz     loc_1800036FB
0x18000309c  xor     ebx, ebx
0x18000309e  test    rsi, rsi
0x1800030a1  setnz   bl
0x1800030a4  mov     esi, dword ptr [rbp+3Fh+hMem+8]
0x1800030a7  xor     edi, edi
0x1800030a9  test    esi, esi
0x1800030ab  jz      short loc_1800030CA
0x1800030ad  mov     r12, [rbp+3Fh+hMem]
0x1800030b1  mov     ecx, edi
0x1800030b3  add     rcx, rcx
0x1800030b6  mov     rcx, [r12+rcx*8]; hMem
0x1800030ba  call    cs:__imp_LocalFree
0x1800030c0  inc     edi
0x1800030c2  cmp     edi, esi
0x1800030c4  jb      short loc_1800030B1
0x1800030c6  mov     r12, [rbp+3Fh+var_80]
0x1800030ca  mov     rcx, [rbp+3Fh+hMem]; hMem
0x1800030ce  call    cs:__imp_LocalFree
0x1800030d4  test    r15, r15
0x1800030d7  jz      short loc_1800030E4
0x1800030d9  xor     edx, edx; dwFlags
0x1800030db  mov     rcx, r15; hCertStore
0x1800030de  call    cs:__imp_CertCloseStore
0x1800030e4  mov     esi, dword ptr [rbp+3Fh+var_78]
0x1800030e7  xor     edi, edi
0x1800030e9  test    esi, esi
0x1800030eb  jg      loc_1800032B0
0x1800030f1  mov     rax, [rbp+3Fh+var_70]
0x1800030f5  test    rax, rax
0x1800030f8  jnz     loc_180003721
0x1800030fe  test    r12, r12
0x180003101  jz      short loc_18000310C
0x180003103  mov     rcx, r12; Block
0x180003106  call    cs:__imp_free
0x18000310c  mov     eax, ebx
0x18000310e  mov     rbx, [rsp+0E0h+arg_18]
0x180003116  add     rsp, 0B0h
0x18000311d  pop     r15
0x18000311f  pop     r14
0x180003121  pop     r13
0x180003123  pop     r12
0x180003125  pop     rdi
0x180003126  pop     rsi
0x180003127  pop     rbp
0x180003128  retn
0x180003129  mov     rax, [rax+18h]
0x18000312d  mov     rcx, [rbp+3Fh+var_70]; hMem
0x180003131  mov     [rbp+3Fh+var_48], rax
0x180003135  mov     [rbp+3Fh+var_98], 0
0x18000313c  call    cs:__imp_LocalFree
0x180003142  mov     rcx, rdi
0x180003145  call    AEGetTemplateName
0x18000314a  mov     [rbp+3Fh+var_70], rax
0x18000314e  test    rax, rax
0x180003151  jnz     loc_1800032F0
0x180003157  mov     edx, [rbp+3Fh+var_98]
0x18000315a  mov     rax, [rbp+3Fh+var_48]
0x18000315e  test    rax, rax
0x180003161  jz      loc_18000301D
0x180003167  mov     r9, [rax+48h]
0x18000316b  mov     rcx, r9
0x18000316e  mov     [rbp+3Fh+var_94], 0
0x180003175  sub     rcx, [rax+40h]
0x180003179  cmp     [rbp+3Fh+arg_30], 0
0x18000317d  jz      loc_1800035B4
0x180003183  mov     rax, 0A3D70A3D70A3D70Bh
0x18000318d  imul    rcx
0x180003190  add     rcx, rdx
0x180003193  sar     rcx, 6
0x180003197  mov     rax, rcx
0x18000319a  shr     rax, 3Fh
0x18000319e  add     rcx, rax
0x1800031a1  mov     eax, [rbp+3Fh+arg_10]
0x1800031a4  imul    rcx, rax
0x1800031a8  sub     r9, rcx
0x1800031ab  lea     rdx, [rbp+3Fh+FileTime2]; lpFileTime2
0x1800031af  lea     rcx, [rbp+3Fh+SystemTimeAsFileTime]; lpFileTime1
0x1800031b3  mov     qword ptr [rbp+3Fh+FileTime2.dwLowDateTime], r9
0x1800031b7  call    cs:__imp_CompareFileTime
0x1800031bd  test    eax, eax
0x1800031bf  jle     short loc_180003231
0x1800031c1  lea     r9, [rbp+3Fh+pcbData]; pcbData
0x1800031c5  mov     [rbp+3Fh+pcbData], 0
0x1800031cc  xor     r8d, r8d; pvData
0x1800031cf  mov     [rbp+3Fh+var_94], 1
0x1800031d6  mov     edx, 4Dh ; 'M'; dwPropId
0x1800031db  mov     rcx, rdi; pCertContext
0x1800031de  call    cs:__imp_CertGetCertificateContextProperty
0x1800031e4  test    eax, eax
0x1800031e6  jnz     short loc_180003231
0x1800031e8  call    cs:__imp_GetLastError
0x1800031ee  cmp     eax, 80092004h
0x1800031f3  jnz     short loc_180003231
0x1800031f5  test    r13, r13
0x1800031f8  jz      short loc_18000322E
0x1800031fa  test    r14, r14
0x1800031fd  jnz     loc_1800032D4
0x180003203  mov     edx, 8; uBytes
0x180003208  xor     ecx, ecx; uFlags
0x18000320a  call    cs:__imp_LocalAlloc
0x180003210  mov     [rbp+3Fh+var_A0], rax
0x180003214  test    rax, rax
0x180003217  jz      loc_1800033E9
0x18000321d  mov     rcx, rdi; pCertContext
0x180003220  call    cs:__imp_CertDuplicateCertificateContext
0x180003226  mov     r14, [rbp+3Fh+var_A0]
0x18000322a  mov     [r14+rsi*8], rax
0x18000322e  inc     rsi
0x180003231  mov     rcx, rdi
0x180003234  call    AEGetTemplateName
0x180003239  mov     [rbp+3Fh+var_A0], rax
0x18000323d  mov     rcx, rax; String1
0x180003240  test    rax, rax
0x180003243  jz      loc_18000301D
0x180003249  mov     eax, dword ptr [rbp+3Fh+hMem+8]
0x18000324c  xor     edx, edx
0x18000324e  mov     [rbp+3Fh+var_B0], edx
0x180003251  test    eax, eax
0x180003253  jz      short loc_180003281
0x180003255  mov     rax, [rbp+3Fh+hMem]
0x180003259  add     rdx, rdx
0x18000325c  mov     rdx, [rax+rdx*8]; String2
0x180003260  call    cs:__imp__wcsicmp
0x180003266  test    eax, eax
0x180003268  mov     eax, dword ptr [rbp+3Fh+hMem+8]
0x18000326b  jz      loc_180003629
0x180003271  mov     edx, [rbp+3Fh+var_B0]
0x180003274  mov     rcx, [rbp+3Fh+var_A0]
0x180003278  inc     edx
0x18000327a  mov     [rbp+3Fh+var_B0], edx
0x18000327d  cmp     edx, eax
0x18000327f  jb      short loc_180003255
0x180003281  mov     rcx, [rbp+3Fh+hMem]; hMem
0x180003285  test    rcx, rcx
0x180003288  jz      loc_180003640
0x18000328e  lea     edx, [rax+1]
0x180003291  mov     r8d, 2; uFlags
0x180003297  shl     rdx, 4; uBytes
0x18000329b  call    cs:__imp_LocalReAlloc
0x1800032a1  mov     rcx, rax
0x1800032a4  mov     eax, dword ptr [rbp+3Fh+hMem+8]
0x1800032a7  jmp     loc_180003655
0x1800032b0  test    edi, edi
0x1800032b2  js      loc_18000370A
0x1800032b8  movsxd  rax, edi
0x1800032bb  mov     rcx, [r12+rax*8]
0x1800032bf  test    rcx, rcx
0x1800032c2  jnz     loc_1800033DE
0x1800032c8  inc     edi
0x1800032ca  cmp     edi, esi
0x1800032cc  jge     loc_1800030F1
0x1800032d2  jmp     short loc_1800032B0
0x1800032d4  lea     rdx, ds:8[rsi*8]; uBytes
0x1800032dc  mov     r8d, 2; uFlags
0x1800032e2  mov     rcx, r14; hMem
0x1800032e5  call    cs:__imp_LocalReAlloc
0x1800032eb  jmp     loc_180003210
0x1800032f0  mov     eax, dword ptr [rbp+3Fh+var_78]
0x1800032f3  test    eax, eax
0x1800032f5  jle     loc_180003157
0x1800032fb  xor     ecx, ecx
0x1800032fd  mov     [rbp+3Fh+var_B0], ecx
0x180003300  cmp     ecx, eax
0x180003302  jge     loc_180003157
0x180003308  test    ecx, ecx
0x18000330a  js      loc_18000370A
0x180003310  movsxd  rax, ecx
0x180003313  mov     [rbp+3Fh+var_A8], 0
0x18000331b  mov     rax, [r12+rax*8]
0x18000331f  mov     [rbp+3Fh+var_A0], rax
0x180003323  test    rax, rax
0x180003326  jz      loc_1800033D4
0x18000332c  lea     r8, [rbp+3Fh+var_A8]
0x180003330  mov     byte ptr [rbp+3Fh+pdwFlags], 0
0x180003334  lea     rdx, aCn; "cn"
0x18000333b  mov     rcx, rax
0x18000333e  call    cs:__imp_CAGetCertTypePropertyEx
0x180003344  mov     rdx, [rbp+3Fh+var_A8]
0x180003348  test    eax, eax
0x18000334a  jz      loc_18000349E
0x180003350  mov     ecx, [rbp+3Fh+pdwFlags]
0x180003353  test    rdx, rdx
0x180003356  jnz     loc_180003486
0x18000335c  test    cl, cl
0x18000335e  jnz     short loc_1800033B8
0x180003360  mov     rcx, [rbp+3Fh+var_A0]
0x180003364  lea     rdx, [rbp+3Fh+var_94]
0x180003368  mov     [rbp+3Fh+var_94], 0
0x18000336f  call    cs:__imp_CAIsCertTypeValid
0x180003375  test    eax, eax
0x180003377  jnz     loc_18000347D
0x18000337d  cmp     [rbp+3Fh+var_94], eax
0x180003380  jz      loc_18000347D
0x180003386  mov     rcx, [rbp+3Fh+var_A0]
0x18000338a  lea     r8, [rbp+3Fh+var_A8]
0x18000338e  lea     rdx, aMspkiCertTempl; "msPKI-Cert-Template-OID"
0x180003395  call    cs:__imp_CAGetCertTypePropertyEx
0x18000339b  test    eax, eax
0x18000339d  jnz     loc_18000347D
0x1800033a3  mov     rdx, [rbp+3Fh+var_A8]
0x1800033a7  test    rdx, rdx
0x1800033aa  jz      short loc_1800033C7
0x1800033ac  mov     rcx, [rdx]; String1
0x1800033af  test    rcx, rcx
0x1800033b2  jnz     loc_180003462
0x1800033b8  test    rdx, rdx
0x1800033bb  jz      short loc_1800033C7
0x1800033bd  mov     rcx, [rbp+3Fh+var_A0]
  ... truncated ...
```
