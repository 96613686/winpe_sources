# CMessageBody::InternalSetOption(ulong,tagPROPVARIANT const *,int,int)

- ea: `0x18003e818`
- end: `0x18003f7a3`
- name: `?InternalSetOption@CMessageBody@@QEAAJKPEBUtagPROPVARIANT@@HH@Z`
- size: `3979`
- prototype: `__int64 __usercall@<rax>(CMessageBody *__hidden this@<rcx>, unsigned int@<edx>, const struct tagPROPVARIANT *@<r8>, int@<r9d>, int)`
- caller_count: `2`
- callee_count: `14`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18003b5a8`
- `0x18003feb0`

## callees

- `0x180014f00`
- `0x1800247c8`
- `0x18002c524`
- `0x18002c544`
- `0x18003e818`
- `0x180040760`
- `0x1800407f8`
- `0x180040968`
- `0x180040a90`
- `0x18004168c`
- `0x180041b18`
- `0x1800cc9ba`
- `0x1800cca00`
- `0x1800cd010`

## import_xrefs

- `MSOERT2!PszDupW` at `0x18003f754`
- `MSOERT2!PszDupW` at `0x18003f754`
- `ADVAPI32!CryptReleaseContext` at `0x18003ec26`
- `ADVAPI32!CryptReleaseContext` at `0x18003ec26`
- `KERNEL32!lstrcmpW` at `0x18003f71b`
- `KERNEL32!lstrcmpW` at `0x18003f71b`
- `KERNEL32!LeaveCriticalSection` at `0x18003f771`
- `KERNEL32!LeaveCriticalSection` at `0x18003f771`
- `KERNEL32!EnterCriticalSection` at `0x18003e86e`
- `KERNEL32!EnterCriticalSection` at `0x18003e86e`
- `CRYPT32!CertAddEncodedCRLToStore` at `0x18003f294`
- `CRYPT32!CertAddEncodedCRLToStore` at `0x18003f294`
- `CRYPT32!CertOpenStore` at `0x18003f25b`
- `CRYPT32!CertOpenStore` at `0x18003f668`
- `CRYPT32!CertOpenStore` at `0x18003f25b`
- `CRYPT32!CertOpenStore` at `0x18003f668`
- `CRYPT32!CertAddCertificateContextToStore` at `0x18003f6a3`
- `CRYPT32!CertAddCertificateContextToStore` at `0x18003f6a3`
- `CRYPT32!CertFreeCertificateContext` at `0x18003ea2d`
- `CRYPT32!CertFreeCertificateContext` at `0x18003ea94`
- `CRYPT32!CertFreeCertificateContext` at `0x18003eb88`
- `CRYPT32!CertFreeCertificateContext` at `0x18003f45a`
- `CRYPT32!CertFreeCertificateContext` at `0x18003ea2d`
- `CRYPT32!CertFreeCertificateContext` at `0x18003ea94`
- `CRYPT32!CertFreeCertificateContext` at `0x18003eb88`
- `CRYPT32!CertFreeCertificateContext` at `0x18003f45a`
- `CRYPT32!CertCloseStore` at `0x18003ec6f`
- `CRYPT32!CertCloseStore` at `0x18003f42f`
- `CRYPT32!CertCloseStore` at `0x18003f6e3`
- `CRYPT32!CertCloseStore` at `0x18003ec6f`
- `CRYPT32!CertCloseStore` at `0x18003f42f`
- `CRYPT32!CertCloseStore` at `0x18003f6e3`
- `CRYPT32!CertDuplicateCertificateContext` at `0x18003ea36`
- `CRYPT32!CertDuplicateCertificateContext` at `0x18003ea9e`
- `CRYPT32!CertDuplicateCertificateContext` at `0x18003eb92`
- `CRYPT32!CertDuplicateCertificateContext` at `0x18003ea36`
- `CRYPT32!CertDuplicateCertificateContext` at `0x18003ea9e`
- `CRYPT32!CertDuplicateCertificateContext` at `0x18003eb92`
- `CRYPT32!CryptEncodeObjectEx` at `0x18003f061`
- `CRYPT32!CryptEncodeObjectEx` at `0x18003f11a`
- `CRYPT32!CryptEncodeObjectEx` at `0x18003f061`
- `CRYPT32!CryptEncodeObjectEx` at `0x18003f11a`
- `CRYPT32!CertDuplicateStore` at `0x18003ec7e`
- `CRYPT32!CertDuplicateStore` at `0x18003f6f2`
- `CRYPT32!CertDuplicateStore` at `0x18003ec7e`
- `CRYPT32!CertDuplicateStore` at `0x18003f6f2`

## pseudocode

```c
__int64 __fastcall CMessageBody::InternalSetOption(
        CMessageBody *this,
        unsigned int a2,
        const struct tagPROPVARIANT *a3,
        int a4,
        int a5)
{
  signed int v9; // edi
  int v10; // eax
  int v11; // eax
  int v12; // ecx
  unsigned int v13; // eax
  int v14; // eax
  LONG v15; // eax
  unsigned int v16; // r14d
  int v17; // eax
  BYTE *v18; // r13
  unsigned int v19; // r15d
  __int64 v20; // rsi
  const CERT_CONTEXT *v21; // r12
  const CERT_CONTEXT *v22; // rcx
  const CERT_CONTEXT **v23; // rax
  const CERT_CONTEXT *v24; // rcx
  struct tagBLOB *v25; // rdx
  struct tagBLOB **v26; // r8
  int LastError; // eax
  const struct tagBLOB *v28; // r14
  const CERT_CONTEXT *v29; // rcx
  int v30; // eax
  HCRYPTPROV v31; // rcx
  CLSID *v32; // rcx
  HCERTSTORE v33; // rax
  int v34; // r14d
  __int64 v35; // rax
  unsigned int n; // r14d
  const char *v37; // r8
  unsigned int m; // r14d
  unsigned __int8 *v39; // rax
  unsigned int v40; // r9d
  struct _CRYPT_ATTRIBUTES **v41; // rdx
  unsigned int v42; // ecx
  int v43; // eax
  unsigned int v44; // edx
  BYTE *v45; // r10
  __int64 v46; // rax
  __int64 v47; // r8
  int v48; // r9d
  __int64 v49; // rax
  __int64 v50; // r8
  int v51; // r9d
  LONG *v52; // rcx
  LONG v53; // eax
  unsigned int j; // r15d
  BYTE *v55; // r8
  int v56; // eax
  unsigned int i; // r14d
  int iVal; // eax
  LONG v59; // eax
  HCERTSTORE v60; // rax
  unsigned int ulVal; // ecx
  int v62; // eax
  unsigned int v63; // edx
  BYTE *pData; // r10
  __int64 v65; // rax
  __int64 v66; // r8
  int v67; // r9d
  __int64 v68; // rax
  __int64 v69; // r8
  int v70; // r9d
  LONG lVal; // eax
  unsigned int v72; // edx
  unsigned int v73; // eax
  unsigned int v74; // r14d
  int v75; // eax
  int v76; // eax
  HCERTSTORE v77; // rax
  unsigned int k; // r14d
  CLSID *puuid; // rcx
  HCERTSTORE v80; // rax
  const WCHAR *v81; // rcx
  const WCHAR *bstrVal; // rdx
  LARGE_INTEGER hVal; // rcx
  __int64 v84; // rax
  DWORD pcbEncoded; // [rsp+40h] [rbp-C0h] BYREF
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+48h] [rbp-B8h]
  struct tagCAUH v88; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v89[8]; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v90; // [rsp+68h] [rbp-98h]
  unsigned __int8 pvEncoded[56]; // [rsp+160h] [rbp+60h] BYREF

  lpCriticalSection = (LPCRITICAL_SECTION)((char *)this + 392);
  pcbEncoded = 0;
  v9 = 0;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 392));
  if ( a2 > 0x2B0041 )
  {
    if ( a2 <= 0x330003 )
    {
      if ( a2 == 3342339 )
      {
        lVal = a3->lVal;
        if ( *((_DWORD *)this + 62) == lVal )
          goto LABEL_262;
        *((_DWORD *)this + 62) = lVal;
        goto LABEL_227;
      }
      if ( a2 > 0x2E0013 )
      {
        switch ( a2 )
        {
          case 0x2E1013u:
            v9 = CMessageBody::_HrEnsureBodyOptionLayers(this, a3->ulVal);
            if ( v9 < 0 )
              goto LABEL_262;
            ulVal = a3->ulVal;
            v62 = *((_DWORD *)this + 72);
            if ( v62 != ulVal && v62 )
              goto LABEL_35;
            v63 = 0;
            pData = a3->bstrblobVal.pData;
            if ( a5 )
            {
              if ( ulVal )
              {
                v65 = 0;
                do
                {
                  v66 = *((_QWORD *)this + 27);
                  v67 = *(_DWORD *)&pData[4 * v65];
                  if ( *(_DWORD *)(v66 + 4 * v65) != v67 )
                    *(_DWORD *)(v66 + 4 * v65) = v67;
                  ++v63;
                  ++v65;
                }
                while ( v63 < ulVal );
              }
            }
            else if ( ulVal )
            {
              v68 = 0;
              do
              {
                v69 = *((_QWORD *)this + 27);
                v70 = *(_DWORD *)&pData[4 * v68];
                if ( *(_DWORD *)(v69 + 4 * v68) != v70 )
                {
                  *(_DWORD *)(v69 + 4 * v68) = v70;
                  *((_DWORD *)this + 16) |= 1u;
                }
                ++v63;
                ++v68;
              }
              while ( v63 < ulVal );
            }
            goto LABEL_262;
          case 0x2F0041u:
            v60 = (HCERTSTORE)*((_QWORD *)this + 19);
            if ( v60 || (v60 = CertOpenStore((LPCSTR)2, 1u, 0, 0, 0), (*((_QWORD *)this + 19) = v60) != 0) )
            {
              if ( CertAddEncodedCRLToStore(v60, 1u, a3->bstrblobVal.pData, a3->ulVal, 4u, 0) )
                goto LABEL_227;
            }
            goto LABEL_174;
          case 0x300013u:
            v59 = a3->lVal;
            if ( *((_DWORD *)this + 58) == v59 )
              goto LABEL_262;
            *((_DWORD *)this + 58) = v59;
            goto LABEL_227;
        }
        if ( a2 != 3211275 )
          goto LABEL_238;
        if ( a4 )
        {
          iVal = a3->iVal;
          if ( *((_DWORD *)this + 59) == iVal )
            goto LABEL_262;
          *((_DWORD *)this + 59) = iVal;
          goto LABEL_227;
        }
      }
      else
      {
        if ( a2 != 3014675 )
        {
          if ( a2 == 2822156 )
          {
            v9 = CMessageBody::_HrEnsureBodyOptionLayers(this, a3->ulVal);
            if ( v9 >= 0 )
            {
              for ( i = 0; i < a3->lVal; ++i )
              {
                v9 = CMessageBody::_HrSetAttribute(
                       0,
                       (struct _CRYPT_ATTRIBUTES **)(*((_QWORD *)this + 24) + 8LL * i),
                       0,
                       *(_DWORD *)&a3->bstrblobVal.pData[24 * i + 8],
                       *(const unsigned __int8 **)&a3->bstrblobVal.pData[24 * i + 16]);
                if ( v9 < 0 )
                  break;
              }
            }
            goto LABEL_262;
          }
          if ( a2 != 2883648 )
          {
            if ( a2 == 2887744 )
            {
              v9 = CMessageBody::_HrEnsureBodyOptionLayers(this, a3->ulVal);
              if ( v9 >= 0 )
              {
                for ( j = 0; j < a3->lVal; ++j )
                {
                  v55 = &a3->bstrblobVal.pData[8 * j];
                  if ( *(_DWORD *)v55 || *((_DWORD *)v55 + 1) )
                  {
                    pcbEncoded = 50;
                    if ( !CryptEncodeObjectEx(1u, (LPCSTR)0x1E, v55, 0, 0, pvEncoded, &pcbEncoded) )
                      goto LABEL_174;
                    v56 = CMessageBody::_HrSetAttribute(
                            0,
                            (struct _CRYPT_ATTRIBUTES **)(*((_QWORD *)this + 23) + 8LL * j),
                            "1.2.840.113549.1.9.5",
                            pcbEncoded,
                            pvEncoded);
                  }
                  else
                  {
                    v56 = (*(__int64 (__fastcall **)(char *, _QWORD, _QWORD, _QWORD, _DWORD, const CHAR *))(*((_QWORD *)this + 4) + 88LL))(
                            (char *)this + 32,
                            0,
                            0,
                            0,
                            0,
                            "1.2.840.113549.1.9.5");
                  }
                  v9 = v56;
                }
              }
              goto LABEL_262;
            }
            if ( a2 != 2949139 )
            {
              if ( a2 == 2953235 )
              {
                v9 = CMessageBody::_HrEnsureBodyOptionLayers(this, a3->ulVal);
                if ( v9 < 0 )
                  goto LABEL_262;
                v42 = a3->ulVal;
                v43 = *((_DWORD *)this + 72);
                if ( v43 != v42 && v43 )
                  goto LABEL_35;
                v44 = 0;
                v45 = a3->bstrblobVal.pData;
                if ( a5 )
                {
                  if ( v42 )
                  {
                    v46 = 0;
                    do
                    {
                      v47 = *((_QWORD *)this + 26);
                      v48 = *(_DWORD *)&v45[4 * v46];
                      if ( *(_DWORD *)(v47 + 4 * v46) != v48 )
                        *(_DWORD *)(v47 + 4 * v46) = v48;
                      ++v44;
                      ++v46;
                    }
                    while ( v44 < v42 );
                  }
                }
                else if ( v42 )
                {
                  v49 = 0;
                  do
                  {
                    v50 = *((_QWORD *)this + 26);
                    v51 = *(_DWORD *)&v45[4 * v49];
                    if ( *(_DWORD *)(v50 + 4 * v49) != v51 )
                    {
                      *(_DWORD *)(v50 + 4 * v49) = v51;
                      *((_DWORD *)this + 16) |= 1u;
                    }
                    ++v44;
                    ++v49;
                  }
                  while ( v44 < v42 );
                }
                goto LABEL_262;
              }
              goto LABEL_238;
            }
            v9 = CMessageBody::_HrEnsureBodyOptionLayers(this, 1u);
            if ( v9 < 0 )
              goto LABEL_262;
            v52 = (LONG *)*((_QWORD *)this + 26);
LABEL_137:
            v53 = a3->lVal;
            if ( *v52 == v53 )
              goto LABEL_262;
            *v52 = v53;
            goto LABEL_227;
          }
          v9 = CMessageBody::_HrEnsureBodyOptionLayers(this, 1u);
          if ( v9 < 0 )
            goto LABEL_262;
          if ( !a3->lVal && !a3->hVal.HighPart )
          {
            LastError = (*(__int64 (__fastcall **)(char *, _QWORD, _QWORD, _QWORD, _DWORD, const CHAR *))(*((_QWORD *)this + 4) + 88LL))(
                          (char *)this + 32,
                          0,
                          0,
                          0,
                          0,
                          "1.2.840.113549.1.9.5");
            goto LABEL_239;
          }
          pcbEncoded = 50;
          if ( CryptEncodeObjectEx(1u, (LPCSTR)0x1E, &a3->decVal.8, 0, 0, pvEncoded, &pcbEncoded) )
          {
            v40 = pcbEncoded;
            v39 = pvEncoded;
            v37 = "1.2.840.113549.1.9.5";
LABEL_106:
            v41 = (struct _CRYPT_ATTRIBUTES **)*((_QWORD *)this + 23);
LABEL_107:
            LastError = CMessageBody::_HrSetAttribute(0, v41, v37, v40, v39);
            goto LABEL_239;
          }
LABEL_174:
          LastError = HrGetLastError();
          goto LABEL_239;
        }
        v9 = CMessageBody::_HrEnsureBodyOptionLayers(this, 1u);
        if ( v9 < 0 )
          goto LABEL_262;
        if ( a4 )
        {
          v52 = (LONG *)*((_QWORD *)this + 27);
          goto LABEL_137;
        }
      }
LABEL_162:
      v9 = -2146644423;
      goto LABEL_262;
    }
    if ( a2 > 0x4A100C )
    {
      switch ( a2 )
      {
        case 0x4B001Fu:
          v81 = (const WCHAR *)*((_QWORD *)this + 34);
          if ( !v81 || (bstrVal = a3->bstrVal) == 0 || lstrcmpW(v81, bstrVal) )
          {
            if ( *((_QWORD *)this + 34) )
            {
              ((void (__fastcall *)(LPMALLOC))g_pMalloc->lpVtbl->Free)(g_pMalloc);
              *((_QWORD *)this + 34) = 0;
            }
            hVal = a3->hVal;
            if ( hVal.QuadPart )
            {
              v84 = ((__int64 (__fastcall *)(_QWORD))PszDupW)((LARGE_INTEGER)hVal.QuadPart);
              *((_QWORD *)this + 34) = v84;
              if ( !v84 )
                v9 = -2147024882;
            }
          }
          goto LABEL_262;
        case 0x4C0015u:
          CertCloseStore(*((HCERTSTORE *)this + 39), 0);
          puuid = a3->puuid;
          if ( puuid )
            v80 = CertDuplicateStore(puuid);
          else
            v80 = 0;
          *((_QWORD *)this + 39) = v80;
          goto LABEL_262;
        case 0x570015u:
          *((_QWORD *)this + 30) = a3->hVal.QuadPart;
          goto LABEL_262;
        case 0x591015u:
          if ( !*((_QWORD *)this + 19) )
          {
            v77 = CertOpenStore((LPCSTR)2, 1u, 0, 0, 0);
            *((_QWORD *)this + 19) = v77;
            if ( !v77 )
              v9 = HrGetLastError();
          }
          for ( k = 0; k < a3->lVal; ++k )
          {
            if ( !CertAddCertificateContextToStore(
                    *((HCERTSTORE *)this + 19),
                    *(PCCERT_CONTEXT *)&a3->bstrblobVal.pData[8 * k],
                    4u,
                    0) )
              v9 = HrGetLastError();
          }
          if ( !v9 )
            goto LABEL_227;
          goto LABEL_262;
      }
      goto LABEL_238;
    }
    switch ( a2 )
    {
      case 0x4A100Cu:
        if ( !a4 )
          goto LABEL_162;
        v9 = CMessageBody::_HrEnsureBodyOptionLayers(this, a3->ulVal);
        if ( v9 < 0 )
          goto LABEL_262;
        v26 = (struct tagBLOB **)((char *)this + 264);
        break;
      case 0x39000Bu:
        v76 = a3->iVal != 0;
        if ( *((_DWORD *)this + 70) == v76 )
          goto LABEL_262;
        *((_DWORD *)this + 70) = v76;
        goto LABEL_227;
      case 0x41000Bu:
        v75 = a3->iVal != 0;
        if ( *((_DWORD *)this + 71) == v75 )
          goto LABEL_262;
        *((_DWORD *)this + 71) = v75;
        goto LABEL_227;
      case 0x430013u:
        v72 = a3->ulVal;
        v73 = *((_DWORD *)this + 72);
        if ( !v72 )
        {
          if ( v73 )
          {
            if ( *(_QWORD *)(*((_QWORD *)this + 14) + 8LL) )
            {
              ((void (__fastcall *)(LPMALLOC))g_pMalloc->lpVtbl->Free)(g_pMalloc);
              *(_QWORD *)(*((_QWORD *)this + 14) + 8LL) = 0;
            }
            CertCloseStore(*((HCERTSTORE *)this + 19), 0);
            v74 = 0;
            for ( *((_QWORD *)this + 19) = 0; v74 < *((_DWORD *)this + 72); ++v74 )
            {
              CertFreeCertificateContext(*(PCCERT_CONTEXT *)(*((_QWORD *)this + 17) + 8LL * v74));
              if ( *(_QWORD *)(*((_QWORD *)this + 23) + 8LL * v74) )
              {
                ((void (__fastcall *)(LPMALLOC))g_pMalloc->lpVtbl->Free)(g_pMalloc);
                *(_QWORD *)(*((_QWORD *)this + 23) + 8LL * v74) = 0;
              }
              if ( *(_QWORD *)(*((_QWORD *)this + 24) + 8LL * v74) )
              {
                ((void (__fastcall *)(LPMALLOC))g_pMalloc->lpVtbl->Free)(g_pMalloc);
                *(_QWORD *)(*((_QWORD *)this + 24) + 8LL * v74) = 0;
              }
              if ( *(_QWORD *)(*((_QWORD *)this + 32) + 16LL * v74 + 8) )
              {
                ((void (__fastcall *)(LPMALLOC))g_pMalloc->lpVtbl->Free)(g_pMalloc);
                *(_QWORD *)(*((_QWORD *)this + 32) + 16LL * v74 + 8) = 0;
              }
              if ( *(_QWORD *)(*((_QWORD *)this + 33) + 16LL * v74 + 8) )
              {
                ((void (__fastcall *)(LPMALLOC))g_pMalloc->lpVtbl->Free)(g_pMalloc);
                *(_QWORD *)(*((_QWORD *)this + 33) + 16LL * v74 + 8) = 0;
              }
              if ( *((_QWORD *)this + 34) )
              {
                ((void (__fastcall *)(LPMALLOC))g_pMalloc->lpVtbl->Free)(g_pMalloc);
                *((_QWORD *)this + 34) = 0;
              }
            }
            CMessageBody::_FreeLayerArrays(this);
            *((_DWORD *)this + 72) = 0;
          }
          goto LABEL_262;
        }
        if ( v73 > v72 )
          goto LABEL_262;
        LastError = CMessageBody::_HrEnsureBodyOptionLayers(this, v72);
LABEL_239:
        v9 = LastError;
        goto LABEL_262;
      case 0x45100Cu:
        if ( !a4 )
          goto LABEL_162;
        v9 = CMessageBody::_HrEnsureBodyOptionLayers(this, a3->ulVal);
        if ( v9 < 0 )
          goto LABEL_262;
        v26 = (struct tagBLOB **)((char *)this + 256);
        break;
      case 0x46000Bu:
        *((_DWORD *)this + 73) = a3->iVal != 0;
        goto LABEL_262;
      default:
        goto LABEL_238;
    }
LABEL_54:
    LastError = CMessageBody::_CompareCopyBlobArray(this, a3, v26, a5);
    goto LABEL_239;
  }
  if ( a2 == 2818113 )
  {
    v9 = CMessageBody::_HrEnsureBodyOptionLayers(this, 1u);
    if ( v9 < 0 )
      goto LABEL_262;
    v39 = a3->bstrblobVal.pData;
    v37 = 0;
    v40 = a3->ulVal;
    v41 = (struct _CRYPT_ATTRIBUTES **)*((_QWORD *)this + 24);
    goto LABEL_107;
  }
  if ( a2 > 0x220015 )
  {
    if ( a2 <= 0x281013 )
    {
      switch ( a2 )
      {
        case 0x281013u:
          v9 = a4 == 0 ? 0x800CCE39 : 0;
          goto LABEL_262;
        case 0x231015u:
          v34 = 0;
          if ( !a3->lVal )
            goto LABEL_227;
          while ( 1 )
          {
            memset_0(v89, 0, 0xF8u);
            v35 = *((_QWORD *)this + 4);
            v90 = *(_QWORD *)&a3->bstrblobVal.pData[8 * v34];
            v9 = (*(__int64 (__fastcall **)(char *, bool, __int64, _BYTE *))(v35 + 48))(
                   (char *)this + 32,
                   v34 == 0,
                   1,
                   v89);
            if ( v9 < 0 )
              goto LABEL_262;
            if ( (unsigned int)++v34 >= a3->lVal )
              goto LABEL_227;
          }
        case 0x240015u:
          CertCloseStore(*((HCERTSTORE *)this + 19), 0);
          v32 = a3->puuid;
          if ( v32 )
            v33 = CertDuplicateStore(v32);
          else
            v33 = 0;
          *((_QWORD *)this + 19) = v33;
          goto LABEL_262;
        case 0x251015u:
          v88 = *(struct tagCAUH *)&a3->decVal.Lo32;
          v30 = CMessageBody::_CAUHToCertStore(&v88, (void **)this + 19);
LABEL_76:
          v9 = v30;
          if ( v30 < 0 )
            goto LABEL_262;
          goto LABEL_227;
        case 0x260015u:
          v31 = *((_QWORD *)this + 28);
          if ( v31 == a3->hVal.QuadPart )
            goto LABEL_262;
          if ( v31 )
            CryptReleaseContext(v31, 0);
          *((_QWORD *)this + 28) = a3->hVal.QuadPart;
          goto LABEL_227;
        case 0x271013u:
          v88 = *(struct tagCAUH *)&a3->decVal.Lo32;
          v30 = CMessageBody::_CAUHToSTOREARRAY(&v88, (struct STOREARRAY **)this + 20);
          goto LABEL_76;
      }
LABEL_238:
      LastError = (*(__int64 (__fastcall **)(_QWORD, _QWORD, const struct tagPROPVARIANT *))(**((_QWORD **)this + 47)
                                                                                           + 200LL))(
                    *((_QWORD *)this + 47),
                    a2,
                    a3);
      goto LABEL_239;
    }
    switch ( a2 )
    {
      case 0x290041u:
        v9 = CMessageBody::_HrEnsureBodyOptionLayers(this, 1u);
        if ( v9 < 0 )
          goto LABEL_262;
        v37 = "1.2.840.113549.1.9.15";
        break;
      case 0x29100Cu:
        v9 = CMessageBody::_HrEnsureBodyOptionLayers(this, a3->ulVal);
        if ( v9 >= 0 )
        {
          for ( m = 0; m < a3->lVal; ++m )
          {
            v9 = CMessageBody::_HrSetAttribute(
                   0,
                   (struct _CRYPT_ATTRIBUTES **)(*((_QWORD *)this + 23) + 8LL * m),
                   "1.2.840.113549.1.9.15",
                   *(_DWORD *)&a3->bstrblobVal.pData[24 * m + 8],
                   *(const unsigned __int8 **)&a3->bstrblobVal.pData[24 * m + 16]);
            if ( v9 < 0 )
              break;
          }
        }
        goto LABEL_262;
      case 0x2A0041u:
        v9 = CMessageBody::_HrEnsureBodyOptionLayers(this, 1u);
        if ( v9 < 0 )
          goto LABEL_262;
        v37 = 0;
        break;
      case 0x2A100Cu:
        v9 = CMessageBody::_HrEnsureBodyOptionLayers(this, a3->ulVal);
        if ( v9 >= 0 )
        {
          for ( n = 0; n < a3->lVal; ++n )
          {
            v9 = CMessageBody::_HrSetAttribute(
                   0,
                   (struct _CRYPT_ATTRIBUTES **)(*((_QWORD *)this + 23) + 8LL * n),
                   0,
                   *(_DWORD *)&a3->bstrblobVal.pData[24 * n + 8],
                   *(const unsigned __int8 **)&a3->bstrblobVal.pData[24 * n + 16]);
            if ( v9 < 0 )
              break;
          }
        }
        goto LABEL_262;
      default:
        goto LABEL_238;
    }
    v39 = a3->bstrblobVal.pData;
    v40 = a3->ulVal;
    goto LABEL_106;
  }
  if ( a2 == 2228245 )
  {
    v29 = (const CERT_CONTEXT *)*((_QWORD *)this + 18);
    if ( v29 == (const CERT_CONTEXT *)a3->hVal.QuadPart )
      goto LABEL_262;
    if ( v29 )
      CertFreeCertificateContext(v29);
    *((_QWORD *)this + 18) = CertDuplicateCertificateContext((PCCERT_CONTEXT)a3->hVal.QuadPart);
    goto LABEL_227;
  }
  if ( a2 <= 0x180013 )
  {
    switch ( a2 )
    {
      case 0x180013u:
        v15 = a3->lVal;
        if ( *((_DWORD *)this + 26) == v15 )
          goto LABEL_262;
        *((_DWORD *)this + 26) = v15;
        goto LABEL_227;
      case 0x4000Bu:
        v14 = a3->iVal != 0;
        if ( *((_DWORD *)this + 22) == v14 )
          goto LABEL_262;
        *((_DWORD *)this + 22) = v14;
        goto LABEL_227;
      case 0x50013u:
        v13 = a3->ulVal;
        if ( v13 >= 0x1E )
        {
          if ( *((_DWORD *)this + 21) == v13 )
            goto LABEL_262;
          *((_DWORD *)this + 21) = v13;
          goto LABEL_227;
        }
        break;
      case 0x60013u:
        if ( (unsigned int)FIsValidBodyEncoding(a3->ulVal) )
        {
          if ( *((_DWORD *)this + 20) == v12 )
            goto LABEL_262;
          *((_DWORD *)this + 20) = v12;
          goto LABEL_227;
        }
        break;
      case 0xE000Bu:
        v11 = a3->iVal != 0;
        if ( *((_DWORD *)this + 25) == v11 )
          goto LABEL_262;
        *((_DWORD *)this + 25) = v11;
LABEL_227:
        if ( !a5 )
          *((_DWORD *)this + 16) |= 1u;
        goto LABEL_262;
      case 0x17000Bu:
        v10 = a3->iVal != 0;
        if ( *((_DWORD *)this + 24) == v10 )
          goto LABEL_262;
        *((_DWORD *)this + 24) = v10;
        goto LABEL_227;
      default:
        goto LABEL_238;
    }
    v9 = -2146644449;
    goto LABEL_262;
  }
  switch ( a2 )
  {
    case 0x190041u:
      v9 = CMessageBody::_HrEnsureBodyOptionLayers(this, 1u);
      if ( v9 < 0 )
        goto LABEL_262;
      v28 = (const struct tagBLOB *)*((_QWORD *)this + 14);
      if ( !(unsigned int)CompareBlob(v28, &a3->blob) )
        goto LABEL_262;
      ((void (__fastcall *)(LPMALLOC, BYTE *))g_pMalloc->lpVtbl->Free)(g_pMalloc, v28->pBlobData);
      v25 = (struct tagBLOB *)*((_QWORD *)this + 14);
      goto LABEL_58;
    case 0x19100Cu:
      v9 = CMessageBody::_HrEnsureBodyOptionLayers(this, a3->ulVal);
      if ( v9 < 0 )
        goto LABEL_262;
      v26 = (struct tagBLOB **)((char *)this + 112);
      goto LABEL_54;
    case 0x200041u:
      if ( !(unsigned int)CompareBlob((const struct tagBLOB *)((char *)this + 120), &a3->blob) )
        goto LABEL_262;
      ((void (__fastcall *)(LPMALLOC, _QWORD))g_pMalloc->lpVtbl->Free)(g_pMalloc, *((_QWORD *)this + 16));
      v25 = (struct tagBLOB *)((char *)this + 120);
LABEL_58:
      v9 = HrCopyBlob(&a3->blob, v25);
      goto LABEL_227;
    case 0x210015u:
      v9 = CMessageBody::_HrEnsureBodyOptionLayers(this, 1u);
      if ( v9 < 0 )
        goto LABEL_262;
      v23 = (const CERT_CONTEXT **)*((_QWORD *)this + 17);
      v24 = *v23;
      if ( *v23 == (const CERT_CONTEXT *)a3->hVal.QuadPart )
        goto LABEL_262;
      if ( v24 )
        CertFreeCertificateContext(v24);
      **((_QWORD **)this + 17) = CertDuplicateCertificateContext((PCCERT_CONTEXT)a3->hVal.QuadPart);
      goto LABEL_227;
  }
  if ( a2 != 2166805 )
    goto LABEL_238;
  v9 = CMessageBody::_HrEnsureBodyOptionLayers(this, a3->ulVal);
  if ( v9 < 0 )
    goto LABEL_262;
  v16 = a3->ulVal;
  v17 = *((_DWORD *)this + 72);
  if ( v17 != v16 && v17 )
  {
LABEL_35:
    v9 = -2147024809;
    goto LABEL_262;
  }
  v18 = a3->bstrblobVal.pData;
  v19 = 0;
  if ( v16 )
  {
    v20 = 0;
    do
    {
      v21 = *(const CERT_CONTEXT **)&v18[8 * v20];
      v22 = *(const CERT_CONTEXT **)(*((_QWORD *)this + 17) + 8 * v20);
      if ( v22 != v21 )
      {
        if ( v22 )
          CertFreeCertificateContext(v22);
        *(_QWORD *)(*((_QWORD *)this + 17) + 8 * v20) = CertDuplicateCertificateContext(v21);
        if ( !a5 )
          *((_DWORD *)this + 16) |= 1u;
      }
      ++v19;
      ++v20;
    }
    while ( v19 < v16 );
  }
LABEL_262:
  LeaveCriticalSection(lpCriticalSection);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18003e818  mov     [rsp-8+arg_18], rbx
0x18003e81d  push    rbp
0x18003e81e  push    rsi
0x18003e81f  push    rdi
0x18003e820  push    r12
0x18003e822  push    r13
0x18003e824  push    r14
0x18003e826  push    r15
0x18003e828  lea     rbp, [rsp-0A0h]
0x18003e830  sub     rsp, 1A0h
0x18003e837  mov     rax, cs:__security_cookie
0x18003e83e  xor     rax, rsp
0x18003e841  mov     [rbp+0D0h+var_38], rax
0x18003e848  lea     rax, [rcx+188h]
0x18003e84f  mov     rbx, rcx
0x18003e852  xor     r12d, r12d
0x18003e855  mov     [rsp+1D0h+lpCriticalSection], rax
0x18003e85a  mov     rcx, rax; lpCriticalSection
0x18003e85d  mov     [rsp+1D0h+var_190], r12d
0x18003e862  mov     r15d, r9d
0x18003e865  mov     rsi, r8
0x18003e868  mov     r14d, edx
0x18003e86b  mov     edi, r12d
0x18003e86e  call    cs:__imp_EnterCriticalSection
0x18003e874  mov     eax, 2B0041h
0x18003e879  cmp     r14d, eax
0x18003e87c  ja      loc_18003EEA1
0x18003e882  jz      loc_18003EE76
0x18003e888  mov     eax, 220015h
0x18003e88d  cmp     r14d, eax
0x18003e890  ja      loc_18003EBA4
0x18003e896  jz      loc_18003EB72
0x18003e89c  mov     eax, 180013h
0x18003e8a1  cmp     r14d, eax
0x18003e8a4  ja      loc_18003E98D
0x18003e8aa  jz      loc_18003E979
0x18003e8b0  cmp     r14d, 4000Bh
0x18003e8b7  jz      loc_18003E95D
0x18003e8bd  cmp     r14d, 50013h
0x18003e8c4  jz      short loc_18003E93A
0x18003e8c6  cmp     r14d, 60013h
0x18003e8cd  jz      short loc_18003E91D
0x18003e8cf  cmp     r14d, 0E000Bh
0x18003e8d6  jz      short loc_18003E901
0x18003e8d8  cmp     r14d, 17000Bh
0x18003e8df  jnz     loc_18003F62A
0x18003e8e5  cmp     [rsi+8], r12w
0x18003e8ea  mov     eax, r12d
0x18003e8ed  setnz   al
0x18003e8f0  cmp     [rbx+60h], eax
0x18003e8f3  jz      loc_18003F76C
0x18003e8f9  mov     [rbx+60h], eax
0x18003e8fc  jmp     loc_18003F59B
0x18003e901  cmp     [rsi+8], r12w
0x18003e906  mov     eax, r12d
0x18003e909  setnz   al
0x18003e90c  cmp     [rbx+64h], eax
0x18003e90f  jz      loc_18003F76C
0x18003e915  mov     [rbx+64h], eax
0x18003e918  jmp     loc_18003F59B
0x18003e91d  mov     ecx, [rsi+8]
0x18003e920  call    ?FIsValidBodyEncoding@@YAHW4tagENCODINGTYPE@@@Z; FIsValidBodyEncoding(tagENCODINGTYPE)
0x18003e925  test    eax, eax
0x18003e927  jz      short loc_18003E953
0x18003e929  cmp     [rbx+50h], ecx
0x18003e92c  jz      loc_18003F76C
0x18003e932  mov     [rbx+50h], ecx
0x18003e935  jmp     loc_18003F59B
0x18003e93a  mov     eax, [rsi+8]
0x18003e93d  cmp     eax, 1Eh
0x18003e940  jb      short loc_18003E953
0x18003e942  cmp     [rbx+54h], eax
0x18003e945  jz      loc_18003F76C
0x18003e94b  mov     [rbx+54h], eax
0x18003e94e  jmp     loc_18003F59B
0x18003e953  mov     edi, 800CCE1Fh
0x18003e958  jmp     loc_18003F76C
0x18003e95d  cmp     [rsi+8], r12w
0x18003e962  mov     eax, r12d
0x18003e965  setnz   al
0x18003e968  cmp     [rbx+58h], eax
0x18003e96b  jz      loc_18003F76C
0x18003e971  mov     [rbx+58h], eax
0x18003e974  jmp     loc_18003F59B
0x18003e979  mov     eax, [rsi+8]
0x18003e97c  cmp     [rbx+68h], eax
0x18003e97f  jz      loc_18003F76C
0x18003e985  mov     [rbx+68h], eax
0x18003e988  jmp     loc_18003F59B
0x18003e98d  cmp     r14d, 190041h
0x18003e994  jz      loc_18003EB18
0x18003e99a  cmp     r14d, 19100Ch
0x18003e9a1  jz      loc_18003EAE8
0x18003e9a7  cmp     r14d, 200041h
0x18003e9ae  jz      loc_18003EAB3
0x18003e9b4  cmp     r14d, 210015h
0x18003e9bb  jz      loc_18003EA64
0x18003e9c1  cmp     r14d, 211015h
0x18003e9c8  jnz     loc_18003F62A
0x18003e9ce  mov     edx, [rsi+8]; unsigned int
0x18003e9d1  mov     rcx, rbx; this
0x18003e9d4  call    ?_HrEnsureBodyOptionLayers@CMessageBody@@AEAAJK@Z; CMessageBody::_HrEnsureBodyOptionLayers(ulong)
0x18003e9d9  mov     edi, eax
0x18003e9db  test    eax, eax
0x18003e9dd  js      loc_18003F76C
0x18003e9e3  mov     r14d, [rsi+8]
0x18003e9e7  mov     eax, [rbx+120h]
0x18003e9ed  cmp     eax, r14d
0x18003e9f0  jz      short loc_18003EA00
0x18003e9f2  test    eax, eax
0x18003e9f4  jz      short loc_18003EA00
0x18003e9f6  mov     edi, 80070057h
0x18003e9fb  jmp     loc_18003F76C
0x18003ea00  mov     r13, [rsi+10h]
0x18003ea04  mov     r15d, r12d
0x18003ea07  test    r14d, r14d
0x18003ea0a  jz      loc_18003F76C
0x18003ea10  mov     rsi, r12
0x18003ea13  mov     rax, [rbx+88h]
0x18003ea1a  mov     r12, [r13+rsi*8+0]
0x18003ea1f  mov     rcx, [rax+rsi*8]; pCertContext
0x18003ea23  cmp     rcx, r12
0x18003ea26  jz      short loc_18003EA54
0x18003ea28  test    rcx, rcx
0x18003ea2b  jz      short loc_18003EA33
0x18003ea2d  call    cs:__imp_CertFreeCertificateContext
0x18003ea33  mov     rcx, r12; pCertContext
0x18003ea36  call    cs:__imp_CertDuplicateCertificateContext
0x18003ea3c  cmp     [rbp+0D0h+arg_20], 0
0x18003ea43  mov     rcx, [rbx+88h]
0x18003ea4a  mov     [rcx+rsi*8], rax
0x18003ea4e  jnz     short loc_18003EA54
0x18003ea50  or      dword ptr [rbx+40h], 1
0x18003ea54  inc     r15d
0x18003ea57  inc     rsi
0x18003ea5a  cmp     r15d, r14d
0x18003ea5d  jb      short loc_18003EA13
0x18003ea5f  jmp     loc_18003F76C
0x18003ea64  mov     edx, 1; unsigned int
0x18003ea69  mov     rcx, rbx; this
0x18003ea6c  call    ?_HrEnsureBodyOptionLayers@CMessageBody@@AEAAJK@Z; CMessageBody::_HrEnsureBodyOptionLayers(ulong)
0x18003ea71  mov     edi, eax
0x18003ea73  test    eax, eax
0x18003ea75  js      loc_18003F76C
0x18003ea7b  mov     rax, [rbx+88h]
0x18003ea82  mov     rcx, [rax]; pCertContext
0x18003ea85  cmp     rcx, [rsi+8]
0x18003ea89  jz      loc_18003F76C
0x18003ea8f  test    rcx, rcx
0x18003ea92  jz      short loc_18003EA9A
0x18003ea94  call    cs:__imp_CertFreeCertificateContext
0x18003ea9a  mov     rcx, [rsi+8]; pCertContext
0x18003ea9e  call    cs:__imp_CertDuplicateCertificateContext
0x18003eaa4  mov     rcx, [rbx+88h]
0x18003eaab  mov     [rcx], rax
0x18003eaae  jmp     loc_18003F59B
0x18003eab3  lea     rdx, [rsi+8]; struct tagBLOB *
0x18003eab7  lea     rcx, [rbx+78h]; struct tagBLOB *
0x18003eabb  call    ?CompareBlob@@YAHPEBUtagBLOB@@0@Z; CompareBlob(tagBLOB const *,tagBLOB const *)
0x18003eac0  test    eax, eax
0x18003eac2  jz      loc_18003F76C
0x18003eac8  mov     rcx, cs:?g_pMalloc@@3PEAUIMalloc@@EA; IMalloc * g_pMalloc
0x18003eacf  mov     rdx, [rbx+80h]
0x18003ead6  mov     rax, [rcx]
0x18003ead9  mov     rax, [rax+28h]
0x18003eadd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003eae2  lea     rdx, [rbx+78h]
0x18003eae6  jmp     short loc_18003EB62
0x18003eae8  mov     edx, [rsi+8]; unsigned int
0x18003eaeb  mov     rcx, rbx; this
0x18003eaee  call    ?_HrEnsureBodyOptionLayers@CMessageBody@@AEAAJK@Z; CMessageBody::_HrEnsureBodyOptionLayers(ulong)
0x18003eaf3  mov     edi, eax
0x18003eaf5  test    eax, eax
0x18003eaf7  js      loc_18003F76C
0x18003eafd  lea     r8, [rbx+70h]; struct tagBLOB **
0x18003eb01  mov     r9d, [rbp+0D0h+arg_20]; int
0x18003eb08  mov     rdx, rsi; struct tagPROPVARIANT *
0x18003eb0b  mov     rcx, rbx; this
0x18003eb0e  call    ?_CompareCopyBlobArray@CMessageBody@@AEAAJPEBUtagPROPVARIANT@@PEAPEAUtagBLOB@@H@Z; CMessageBody::_CompareCopyBlobArray(tagPROPVARIANT const *,tagBLOB * *,int)
0x18003eb13  jmp     loc_18003F646
0x18003eb18  mov     edx, 1; unsigned int
0x18003eb1d  mov     rcx, rbx; this
0x18003eb20  call    ?_HrEnsureBodyOptionLayers@CMessageBody@@AEAAJK@Z; CMessageBody::_HrEnsureBodyOptionLayers(ulong)
0x18003eb25  mov     edi, eax
0x18003eb27  test    eax, eax
0x18003eb29  js      loc_18003F76C
0x18003eb2f  mov     r14, [rbx+70h]
0x18003eb33  lea     rdx, [rsi+8]; struct tagBLOB *
0x18003eb37  mov     rcx, r14; struct tagBLOB *
0x18003eb3a  call    ?CompareBlob@@YAHPEBUtagBLOB@@0@Z; CompareBlob(tagBLOB const *,tagBLOB const *)
0x18003eb3f  test    eax, eax
0x18003eb41  jz      loc_18003F76C
0x18003eb47  mov     rcx, cs:?g_pMalloc@@3PEAUIMalloc@@EA; IMalloc * g_pMalloc
0x18003eb4e  mov     rdx, [r14+8]
0x18003eb52  mov     rax, [rcx]
0x18003eb55  mov     rax, [rax+28h]
0x18003eb59  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003eb5e  mov     rdx, [rbx+70h]; struct tagBLOB *
0x18003eb62  lea     rcx, [rsi+8]; struct tagBLOB *
0x18003eb66  call    ?HrCopyBlob@@YAJPEBUtagBLOB@@PEAU1@@Z; HrCopyBlob(tagBLOB const *,tagBLOB *)
0x18003eb6b  mov     edi, eax
0x18003eb6d  jmp     loc_18003F59B
0x18003eb72  mov     rcx, [rbx+90h]; pCertContext
0x18003eb79  cmp     rcx, [rsi+8]
0x18003eb7d  jz      loc_18003F76C
0x18003eb83  test    rcx, rcx
0x18003eb86  jz      short loc_18003EB8E
0x18003eb88  call    cs:__imp_CertFreeCertificateContext
0x18003eb8e  mov     rcx, [rsi+8]; pCertContext
0x18003eb92  call    cs:__imp_CertDuplicateCertificateContext
0x18003eb98  mov     [rbx+90h], rax
0x18003eb9f  jmp     loc_18003F59B
0x18003eba4  mov     eax, 281013h
0x18003eba9  cmp     r14d, eax
0x18003ebac  ja      loc_18003ED13
0x18003ebb2  jz      loc_18003ED01
0x18003ebb8  cmp     r14d, 231015h
0x18003ebbf  jz      loc_18003EC95
0x18003ebc5  cmp     r14d, 240015h
0x18003ebcc  jz      loc_18003EC66
0x18003ebd2  cmp     r14d, 251015h
0x18003ebd9  jz      short loc_18003EC3C
0x18003ebdb  cmp     r14d, 260015h
0x18003ebe2  jz      short loc_18003EC0E
0x18003ebe4  cmp     r14d, 271013h
0x18003ebeb  jnz     loc_18003F62A
0x18003ebf1  movups  xmm0, xmmword ptr [rsi+8]
0x18003ebf5  lea     rdx, [rbx+0A0h]; struct STOREARRAY **
0x18003ebfc  lea     rcx, [rsp+1D0h+var_180]; struct tagCAUH
0x18003ec01  movdqu  xmmword ptr [rsp+1D0h+var_180.cElems], xmm0
0x18003ec07  call    ?_CAUHToSTOREARRAY@CMessageBody@@CAJUtagCAUH@@PEAPEAVSTOREARRAY@@@Z; CMessageBody::_CAUHToSTOREARRAY(tagCAUH,STOREARRAY * *)
0x18003ec0c  jmp     short loc_18003EC57
0x18003ec0e  mov     rcx, [rbx+0E0h]; hProv
0x18003ec15  cmp     rcx, [rsi+8]
0x18003ec19  jz      loc_18003F76C
0x18003ec1f  test    rcx, rcx
0x18003ec22  jz      short loc_18003EC2C
0x18003ec24  xor     edx, edx; dwFlags
0x18003ec26  call    cs:__imp_CryptReleaseContext
0x18003ec2c  mov     rax, [rsi+8]
0x18003ec30  mov     [rbx+0E0h], rax
0x18003ec37  jmp     loc_18003F59B
0x18003ec3c  movups  xmm0, xmmword ptr [rsi+8]
0x18003ec40  lea     rdx, [rbx+98h]; void **
0x18003ec47  lea     rcx, [rsp+1D0h+var_180]; struct tagCAUH
0x18003ec4c  movdqu  xmmword ptr [rsp+1D0h+var_180.cElems], xmm0
0x18003ec52  call    ?_CAUHToCertStore@CMessageBody@@CAJUtagCAUH@@PEAPEAX@Z; CMessageBody::_CAUHToCertStore(tagCAUH,void * *)
0x18003ec57  mov     edi, eax
0x18003ec59  test    eax, eax
0x18003ec5b  js      loc_18003F76C
0x18003ec61  jmp     loc_18003F59B
0x18003ec66  mov     rcx, [rbx+98h]; hCertStore
0x18003ec6d  xor     edx, edx; dwFlags
0x18003ec6f  call    cs:__imp_CertCloseStore
0x18003ec75  mov     rcx, [rsi+8]; hCertStore
0x18003ec79  test    rcx, rcx
0x18003ec7c  jz      short loc_18003EC86
0x18003ec7e  call    cs:__imp_CertDuplicateStore
0x18003ec84  jmp     short loc_18003EC89
0x18003ec86  mov     rax, r12
0x18003ec89  mov     [rbx+98h], rax
0x18003ec90  jmp     loc_18003F76C
0x18003ec95  mov     r14d, r12d
0x18003ec98  cmp     [rsi+8], r12d
0x18003ec9c  jbe     loc_18003F59B
0x18003eca2  xor     edx, edx; Val
0x18003eca4  lea     rcx, [rsp+1D0h+var_170]; void *
0x18003eca9  mov     r8d, 0F8h; Size
0x18003ecaf  call    memset_0
0x18003ecb4  mov     rax, [rsi+10h]
0x18003ecb8  lea     r9, [rsp+1D0h+var_170]
0x18003ecbd  mov     edx, r12d
0x18003ecc0  mov     ecx, r14d
0x18003ecc3  test    r14d, r14d
0x18003ecc6  mov     r8d, 1
0x18003eccc  setz    dl
0x18003eccf  mov     rcx, [rax+rcx*8]
0x18003ecd3  mov     rax, [rbx+20h]
0x18003ecd7  mov     [rsp+1D0h+var_168], rcx
0x18003ecdc  lea     rcx, [rbx+20h]
0x18003ece0  mov     rax, [rax+30h]
0x18003ece4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ece9  mov     edi, eax
0x18003eceb  test    eax, eax
0x18003eced  js      loc_18003F76C
0x18003ecf3  inc     r14d
0x18003ecf6  cmp     r14d, [rsi+8]
0x18003ecfa  jb      short loc_18003ECA2
0x18003ecfc  jmp     loc_18003F59B
0x18003ed01  neg     r15d
0x18003ed04  sbb     edi, edi
0x18003ed06  not     edi
0x18003ed08  and     edi, 800CCE39h
0x18003ed0e  jmp     loc_18003F76C
0x18003ed13  cmp     r14d, 290041h
0x18003ed1a  jz      loc_18003EE38
0x18003ed20  cmp     r14d, 29100Ch
0x18003ed27  jz      loc_18003EDCB
0x18003ed2d  cmp     r14d, 2A0041h
0x18003ed34  jz      short loc_18003EDAC
  ... truncated ...
```
