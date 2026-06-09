# CertImportSafeContents(HWND__ *,void *,_SAFE_CONTENTS const *,ulong,_IMPORT_SAFE_CALLBACK_STRUCT const *,ulong,void *)

- ea: `0x1800f94ec`
- end: `0x1800f9ff0`
- name: `?CertImportSafeContents@@YAHPEAUHWND__@@PEAXPEBU_SAFE_CONTENTS@@KPEBU_IMPORT_SAFE_CALLBACK_STRUCT@@K1@Z`
- size: `2820`
- prototype: `_BOOL8 __fastcall(__int64, void *, const struct _SAFE_CONTENTS *, __int64, HCRYPTPROV phProv, DWORD dwFlags, void *)`
- caller_count: `2`
- callee_count: `31`
- tags: `broker_com_uri`

## callers

- `0x1800afff0`
- `0x1800f7410`

## callees

- `0x180014790`
- `0x18002cb30`
- `0x180037fd8`
- `0x180039f5c`
- `0x1800450c0`
- `0x180060a00`
- `0x18006cf20`
- `0x18006d700`
- `0x18006ee50`
- `0x180070880`
- `0x1800a3c1c`
- `0x1800a7554`
- `0x1800b12e0`
- `0x1800bd668`
- `0x1800bf63c`
- `0x1800f61a8`
- `0x1800f9304`
- `0x1800f94ec`
- `0x1800f9ff8`
- `0x1800fa054`
- `0x1800fa264`
- `0x1800fa3c0`
- `0x1800fa7c0`
- `0x1800fabe4`
- `0x1800fac68`
- `0x1800fae1c`
- `0x1800fb008`
- `0x1800fb04c`
- `0x1800fb11c`
- `0x180115094`
- `0x1801150c4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f9bd2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f9bec`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f9c22`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f9bd2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f9bec`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f9c22`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800f9f9f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800f9f9f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800f977a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800f9783`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800f9887`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800f977a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800f9783`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800f9887`
- `ncrypt!NCryptOpenStorageProvider` at `0x1800f9e15`
- `ncrypt!NCryptOpenStorageProvider` at `0x1800f9e15`
- `ncrypt!NCryptOpenKey` at `0x1800f9e45`
- `ncrypt!NCryptOpenKey` at `0x1800f9e45`
- `ncrypt!NCryptFreeObject` at `0x1800f9e5f`
- `ncrypt!NCryptFreeObject` at `0x1800f9ee7`
- `ncrypt!NCryptFreeObject` at `0x1800f9e5f`
- `ncrypt!NCryptFreeObject` at `0x1800f9ee7`
- `ncrypt!NCryptDeleteKey` at `0x1800f9e55`
- `ncrypt!NCryptDeleteKey` at `0x1800f9e55`
- `CRYPTSP!CryptAcquireContextW` at `0x1800f9dfe`
- `CRYPTSP!CryptAcquireContextW` at `0x1800f9dfe`
- `CRYPTSP!CryptReleaseContext` at `0x1800f9ed7`
- `CRYPTSP!CryptReleaseContext` at `0x1800f9ed7`

## pseudocode

```c
_BOOL8 __fastcall CertImportSafeContents(
        __int64 a1,
        void *a2,
        const struct _SAFE_CONTENTS *a3,
        __int64 a4,
        HCRYPTPROV phProv,
        DWORD dwFlags,
        void *a7)
{
  const struct _SAFE_CONTENTS *v7; // rsi
  __int64 v8; // r14
  __int64 v9; // r13
  unsigned int v10; // ebx
  unsigned int v11; // r15d
  __int64 v12; // r8
  int v13; // edi
  __int64 v14; // rax
  char *v15; // rsi
  __int64 v16; // r12
  __int64 v17; // rax
  __int64 v18; // rbx
  __int64 v19; // rsi
  _QWORD *v20; // rdi
  PCCERT_CONTEXT *v21; // r15
  __int64 v22; // rax
  const BYTE *v23; // rbx
  __int64 v24; // rdi
  DWORD v25; // r12d
  DWORD v26; // eax
  const struct _CERT_CONTEXT *v27; // rcx
  int v28; // edx
  int v29; // r8d
  PCCERT_CONTEXT v30; // rcx
  unsigned __int16 *v31; // r15
  HLOCAL v32; // rbx
  __int64 v33; // rax
  int v34; // edi
  __int64 v35; // rbx
  __int64 v36; // rcx
  DWORD v37; // r12d
  int v38; // edx
  __int64 v39; // rcx
  void *v40; // rsi
  _QWORD *v41; // r15
  wchar_t *v42; // rcx
  BOOL v43; // esi
  int v44; // r12d
  signed int v45; // eax
  unsigned __int16 *v46; // r12
  __int64 i; // rbx
  const CERT_CONTEXT *v48; // rcx
  DWORD v49; // edi
  BYTE **v50; // rsi
  signed int v51; // eax
  __int64 v52; // r12
  const void **v53; // r15
  const CERT_CONTEXT *v54; // rcx
  int v55; // eax
  int v56; // eax
  int LastError; // eax
  unsigned int v58; // eax
  unsigned int v59; // esi
  __int64 v60; // rcx
  unsigned int v61; // esi
  __int64 v62; // rcx
  __int64 v63; // r15
  struct _CERT_PUBLIC_KEY_INFO *v64; // rdx
  __int64 v65; // rbx
  unsigned int v66; // r12d
  char v67; // r13
  __int64 v68; // r15
  __int64 v69; // rbx
  int v70; // eax
  DWORD v71; // esi
  DWORD v72; // r9d
  const WCHAR *v73; // r8
  __int64 j; // rbx
  __int64 v75; // rcx
  unsigned int v76; // esi
  __int64 v77; // r15
  __int64 v78; // rbx
  HCRYPTPROV v79; // rcx
  NCRYPT_HANDLE v80; // rcx
  const WCHAR *v81; // rcx
  __int64 v82; // rcx
  __int64 v83; // rcx
  __int64 v84; // rcx
  DWORD dwAddDisposition; // [rsp+28h] [rbp-81h]
  PCCERT_CONTEXT *ppCertContext; // [rsp+30h] [rbp-79h]
  unsigned int v88; // [rsp+48h] [rbp-61h]
  int v89; // [rsp+4Ch] [rbp-5Dh]
  HLOCAL hMem; // [rsp+50h] [rbp-59h] BYREF
  int v91; // [rsp+58h] [rbp-51h]
  unsigned __int16 *v92; // [rsp+60h] [rbp-49h] BYREF
  NCRYPT_KEY_HANDLE phKey; // [rsp+68h] [rbp-41h] BYREF
  __int64 v94; // [rsp+70h] [rbp-39h]
  _QWORD pvData[2]; // [rsp+78h] [rbp-31h] BYREF
  int v96; // [rsp+88h] [rbp-21h]
  __int128 v97; // [rsp+8Ch] [rbp-1Dh]
  __int64 v98; // [rsp+9Ch] [rbp-Dh]
  int v99; // [rsp+A4h] [rbp-5h]
  DWORD cbCertEncoded; // [rsp+110h] [rbp+67h] BYREF

  v7 = a3;
  cbCertEncoded = 0;
  if ( !phProv || (v91 = 0, (dwFlags & 0xC00) != 0) )
    v91 = 1;
  v8 = 0;
  v94 = 0;
  v9 = 0;
  v88 = 0;
  v10 = 0;
  LODWORD(a7) = 0;
  v11 = 0;
  if ( (unsigned int)PfxGetMaxPermissibleLimit(3u, &cbCertEncoded) )
  {
    v13 = -2147024809;
    goto LABEL_129;
  }
  if ( *(_DWORD *)v7 > cbCertEncoded )
  {
    PfxLogCrypt32Error(0x1052u, cbCertEncoded, *(_DWORD *)v7);
    v13 = -2146885630;
LABEL_129:
    cbCertEncoded = v13;
    goto LABEL_130;
  }
  v14 = 0;
  v13 = 0;
  v89 = 0;
  if ( !*(_DWORD *)v7 )
  {
LABEL_87:
    v52 = 0;
    if ( !v11 )
      goto LABEL_143;
    while ( 1 )
    {
      v53 = *(const void ***)(v9 + 24 * v52 + 8);
      if ( !v53 )
        goto LABEL_113;
      if ( !v91 )
        break;
      v54 = *(const CERT_CONTEXT **)(v9 + 24 * v52);
      pvData[1] = L"PfxProvider";
      v98 = 0;
      v99 = 0;
      v96 = 0;
      pvData[0] = L"PfxContainer";
      v97 = 0;
      CertSetCertificateContextProperty(v54, 2u, 0, pvData);
LABEL_124:
      v11 = (unsigned int)a7;
      v52 = (unsigned int)(v52 + 1);
      if ( (unsigned int)v52 >= (unsigned int)a7 )
      {
        v65 = 0;
        do
        {
          CertFreeCertificateContext(*(PCCERT_CONTEXT *)(v9 + 24 * v65));
          v65 = (unsigned int)(v65 + 1);
        }
        while ( (unsigned int)v65 < v11 );
        goto LABEL_143;
      }
    }
    v58 = v88;
    if ( v88 )
    {
      v59 = 0;
      while ( 1 )
      {
        v60 = *(_QWORD *)(v8 + 88LL * v59 + 64);
        if ( v60 )
        {
          if ( *(_DWORD *)v60 == *(_DWORD *)v53 && !memcmp_0(*(const void **)(v60 + 8), v53[1], *(unsigned int *)v53) )
            break;
        }
        v58 = v88;
        if ( ++v59 >= v88 )
        {
          v9 = v94;
          goto LABEL_114;
        }
      }
      v9 = v94;
      cbCertEncoded = LinkCertAndKey(*(struct _CERT_CONTEXT **)(v94 + 24 * v52));
      v13 = cbCertEncoded;
      if ( (cbCertEncoded & 0x80000000) != 0 )
        goto LABEL_62;
      *(_DWORD *)(v9 + 24 * v52 + 16) = 1;
LABEL_113:
      v58 = v88;
    }
LABEL_114:
    if ( !*(_DWORD *)(v9 + 24 * v52 + 16) )
    {
      v61 = 0;
      if ( v58 )
      {
        while ( 1 )
        {
          v62 = 88LL * v61;
          v63 = v62 + v8;
          if ( *(_QWORD *)(v8 + v62 + 72) || (int)GetPublicKeyInfo(v62 + v8, dwFlags) >= 0 )
          {
            v64 = *(struct _CERT_PUBLIC_KEY_INFO **)(v63 + 72);
            if ( v64 )
            {
              if ( CertComparePublicKeyInfo(
                     0x10001u,
                     v64,
                     (PCERT_PUBLIC_KEY_INFO)(*(_QWORD *)(*(_QWORD *)(v9 + 24 * v52) + 24LL) + 96LL)) )
              {
                break;
              }
            }
          }
          if ( ++v61 >= v88 )
            goto LABEL_124;
        }
        cbCertEncoded = LinkCertAndKey(*(struct _CERT_CONTEXT **)(v9 + 24 * v52));
        v13 = cbCertEncoded;
        if ( (cbCertEncoded & 0x80000000) != 0 )
          goto LABEL_62;
        *(_DWORD *)(v9 + 24 * v52 + 16) = 1;
      }
    }
    goto LABEL_124;
  }
  while ( 1 )
  {
    v15 = (char *)*((_QWORD *)v7 + 1);
    v16 = 5 * v14;
    v92 = (unsigned __int16 *)(5 * v14);
    hMem = v15;
    if ( strcmp_0(*(const char **)&v15[40 * v14], "1.2.840.113549.1.12.10.1.1")
      && strcmp_0(*(const char **)&v15[8 * v16], "1.2.840.113549.1.12.10.1.2") )
    {
      if ( v11 > 0xAAAAAAA )
        goto LABEL_103;
      if ( v11 )
      {
        v18 = v11 + 1;
        v17 = PFXHelpRealloc(v9, 24 * v18);
      }
      else
      {
        v17 = PFXHelpAlloc(0x18u);
        LODWORD(v18) = 1;
      }
      v19 = v17;
      if ( !v17 )
        goto LABEL_103;
      v20 = hMem;
      v9 = v17;
      v94 = v17;
      LODWORD(a7) = v18;
      v21 = (PCCERT_CONTEXT *)(v17 + 24LL * v11);
      cbCertEncoded = 0;
      *(_OWORD *)v21 = 0;
      v21[2] = 0;
      if ( !(unsigned int)GetEncodedCertFromEncodedCertBag(v20[v16 + 2], LODWORD(v20[v16 + 1]), 0, &cbCertEncoded) )
      {
        LastError = GetLastError();
        cbCertEncoded = LastError;
        v13 = LastError;
        if ( LastError > 0 )
        {
          v13 = (unsigned __int16)LastError | 0x80070000;
          cbCertEncoded = v13;
        }
        v11 = v18;
        goto LABEL_65;
      }
      v22 = PFXHelpAlloc(cbCertEncoded);
      v23 = (const BYTE *)v22;
      if ( !v22 )
      {
        v13 = -2147024882;
LABEL_98:
        cbCertEncoded = v13;
LABEL_99:
        v11 = (unsigned int)a7;
        goto LABEL_65;
      }
      if ( !(unsigned int)GetEncodedCertFromEncodedCertBag(v20[v16 + 2], LODWORD(v20[v16 + 1]), v22, &cbCertEncoded)
        || !CertAddEncodedCertificateToStore(a2, 1u, v23, cbCertEncoded, 4u, v21) )
      {
        v56 = GetLastError();
        cbCertEncoded = v56;
        v13 = v56;
        if ( v56 > 0 )
        {
          v13 = (unsigned __int16)v56 | 0x80070000;
          cbCertEncoded = v13;
        }
        PFXHelpFree(v23);
        goto LABEL_99;
      }
      PFXHelpFree(v23);
      v24 = (__int64)&v20[v16 + 3];
      if ( !(unsigned int)AddFriendlyNameProperty(*v21, v24)
        || (v25 = dwFlags, (dwFlags & 0x10) != 0) && !(unsigned int)AddExtendedProperties(*v21) )
      {
        v55 = GetLastError();
        cbCertEncoded = v55;
        v13 = v55;
        if ( v55 > 0 )
        {
          v13 = (unsigned __int16)v55 | 0x80070000;
          goto LABEL_98;
        }
        goto LABEL_99;
      }
      v26 = DecodeSafeBagAttributes(v24, 0, v21 + 1, v25);
      v27 = *v21;
      v13 = v26;
      cbCertEncoded = v26;
      hMem = 0;
      PfxGetFriendlyCertName(v27, (unsigned __int16 **)&hMem);
      v30 = v21[1];
      v31 = 0;
      v92 = 0;
      if ( v30 )
      {
        PfxGetFriendlyPbData(v30->dwCertEncodingType, v30->pbCertEncoded, &v92);
        v31 = v92;
      }
      v32 = hMem;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        WPP_SF_dSS(*((_QWORD *)WPP_GLOBAL_Control + 2), v28, v29, v89, (__int64)v31, (__int64)hMem);
      LocalFree(v31);
      LocalFree(v32);
      v11 = (unsigned int)a7;
      if ( v13 < 0 )
        goto LABEL_65;
      goto LABEL_85;
    }
    if ( !v91 )
      break;
LABEL_86:
    v7 = a3;
    v14 = (unsigned int)(v89 + 1);
    v89 = v14;
    if ( (unsigned int)v14 >= *(_DWORD *)a3 )
      goto LABEL_87;
  }
  if ( v10 <= 0x2E8BA2E )
  {
    if ( v10 )
    {
      v34 = v10 + 1;
      v33 = PFXHelpRealloc(v8, 88LL * (v10 + 1));
    }
    else
    {
      v33 = PFXHelpAlloc(0x58u);
      v34 = 1;
    }
    if ( v33 )
    {
      v8 = v33;
      v88 = v34;
      v35 = v33 + 88LL * v10;
      memset_0((void *)v35, 0, 0x58u);
      v36 = v16 + 3;
      v37 = dwFlags;
      cbCertEncoded = DecodeSafeBagAttributes(&v15[8 * v36], v35 + 16, v35 + 64, dwFlags);
      v13 = cbCertEncoded;
      if ( (cbCertEncoded & 0x80000000) != 0 )
        goto LABEL_62;
      v39 = *(_QWORD *)(v35 + 64);
      v40 = 0;
      phKey = 0;
      if ( v39 )
      {
        PfxGetFriendlyPbData(*(_DWORD *)v39, *(const unsigned __int8 **)(v39 + 8), (unsigned __int16 **)&phKey);
        v40 = (void *)phKey;
      }
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        WPP_SF_dSSS(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v38,
          v12,
          v89,
          (__int64)v40,
          *(_QWORD *)(v35 + 24),
          *(_QWORD *)(v35 + 16));
      LocalFree(v40);
      v41 = (_QWORD *)(v35 + 24);
      v42 = *(wchar_t **)(v35 + 24);
      v43 = v42 != 0;
      if ( !v42 )
      {
        if ( (v37 & 0x10300) != 0 )
          goto LABEL_47;
        goto LABEL_46;
      }
      if ( (unsigned int)GetCAPIProviderTypeByName(v42) )
      {
        if ( (v37 & 0x10200) != 0 )
        {
          v43 = 0;
          PFXHelpFree(*v41);
          *v41 = 0;
          *(_DWORD *)(v35 + 32) = 0;
          goto LABEL_47;
        }
LABEL_46:
        *(_DWORD *)(v35 + 80) = 1;
      }
LABEL_47:
      v44 = 0;
      if ( *(_DWORD *)(v35 + 80) )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
          WPP_SF_SS(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, v12, *v41, *(_QWORD *)(v35 + 16));
        v45 = ImportCAPIKey((HCRYPTPROV *)v35, dwFlags);
        cbCertEncoded = v45;
        v13 = v45;
        if ( v45 < 0 )
        {
          if ( v45 == -2147023673 )
            goto LABEL_62;
          v44 = 1;
          *(_DWORD *)(v35 + 80) = 0;
        }
      }
      if ( *(_DWORD *)(v35 + 80) )
      {
        if ( v13 < 0 )
        {
          v46 = v92;
          goto LABEL_72;
        }
      }
      else
      {
        *(_DWORD *)(v35 + 36) &= 0x20u;
        if ( v44 )
        {
          FreeAndNullProvName((unsigned __int16 **)(v35 + 24));
          *(_DWORD *)(v35 + 56) = 0;
          *(_DWORD *)(v35 + 32) = 0;
        }
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
          WPP_SF_SS(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, v12, *v41, *(_QWORD *)(v35 + 16));
        v46 = v92;
        LODWORD(ppCertContext) = dwFlags;
        cbCertEncoded = ImportCNGKey(
                          a1,
                          v35,
                          phProv,
                          *((BYTE **)hMem + (_QWORD)v92 + 2),
                          *((_DWORD *)hMem + 2 * (_QWORD)v92 + 2),
                          ppCertContext);
        v13 = cbCertEncoded;
        if ( (cbCertEncoded & 0x80000000) != 0 )
        {
          if ( (dwFlags & 0x10000) != 0 )
            goto LABEL_62;
LABEL_72:
          if ( v43 )
          {
            FreeAndNullProvName((unsigned __int16 **)(v35 + 24));
            v49 = dwFlags;
            *(_DWORD *)(v35 + 56) = 0;
            *(_DWORD *)(v35 + 32) = 0;
            if ( (v49 & 0x10300) != 0 )
            {
              v50 = (BYTE **)hMem;
LABEL_80:
              if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
              {
                WPP_SF_SS(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, v12, *(_QWORD *)(v35 + 24), *(_QWORD *)(v35 + 16));
              }
              LODWORD(ppCertContext) = v49;
              cbCertEncoded = ImportCNGKey(
                                a1,
                                v35,
                                phProv,
                                v50[(_QWORD)v46 + 2],
                                (DWORD)v50[(_QWORD)v46 + 1],
                                ppCertContext);
              v13 = cbCertEncoded;
              if ( (cbCertEncoded & 0x80000000) != 0 )
              {
LABEL_62:
                v11 = (unsigned int)a7;
                goto LABEL_63;
              }
            }
            else
            {
              if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
              {
                WPP_SF_SS(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, v12, *v41, *(_QWORD *)(v35 + 16));
              }
              v50 = (BYTE **)hMem;
              v51 = ImportCAPIKey((HCRYPTPROV *)v35, v49);
              cbCertEncoded = v51;
              v13 = v51;
              if ( v51 < 0 )
              {
                if ( v51 == -2147023673 )
                  goto LABEL_62;
                v49 = dwFlags;
                goto LABEL_80;
              }
            }
          }
        }
      }
      v11 = (unsigned int)a7;
LABEL_85:
      v10 = v88;
      goto LABEL_86;
    }
  }
LABEL_103:
  v13 = -2147024882;
  cbCertEncoded = -2147024882;
LABEL_63:
  if ( !v9 )
    goto LABEL_130;
  v19 = v9;
LABEL_65:
  for ( i = 0; (unsigned int)i < v11; i = (unsigned int)(i + 1) )
  {
    v48 = *(const CERT_CONTEXT **)(v19 + 24 * i);
    if ( v48 )
      CertDeleteCTLFromStore(v48);
  }
LABEL_130:
  if ( (dwFlags & 0x8000) == 0 )
  {
    if ( v8 )
    {
      v66 = 0;
      if ( v88 )
      {
        v67 = dwFlags;
        v68 = 0;
        do
        {
          v69 = 88 * v68;
          if ( *(_DWORD *)(88 * v68 + v8 + 84) )
          {
            phProv = 0;
            v70 = v67 & 0x40;
            if ( *(_DWORD *)(v69 + v8 + 80) )
            {
              CryptAcquireContextW(
                &phProv,
                *(LPCWSTR *)(v69 + v8 + 16),
                *(LPCWSTR *)(v69 + v8 + 24),
                *(_DWORD *)(v69 + v8 + 32),
                *(_DWORD *)(v69 + v8 + 36) | (v70 != 0 ? 80 : 16));
            }
            else
            {
              v71 = v70 != 0 ? 0x40 : 0;
              if ( NCryptOpenStorageProvider(&phProv, *(LPCWSTR *)(v69 + v8 + 24), v71) >= 0 )
              {
                v72 = *(_DWORD *)(v69 + v8 + 56);
                v73 = *(const WCHAR **)(v69 + v8 + 16);
                dwAddDisposition = *(_DWORD *)(v69 + v8 + 36) | 0x40;
                phKey = 0;
                if ( NCryptOpenKey(phProv, &phKey, v73, v72, dwAddDisposition) >= 0 )
                  NCryptDeleteKey(phKey, v71);
                NCryptFreeObject(phProv);
              }
            }
          }
          ++v66;
          ++v68;
        }
        while ( v66 < v88 );
        v13 = cbCertEncoded;
        v9 = v94;
        v11 = (unsigned int)a7;
      }
    }
  }
LABEL_143:
  if ( v9 )
  {
    for ( j = 0; (unsigned int)j < v11; j = (unsigned int)(j + 1) )
    {
      v75 = *(_QWORD *)(v9 + 24 * j + 8);
      if ( v75 )
        PFXHelpFree(v75);
    }
    PFXHelpFree(v9);
  }
  if ( v8 )
  {
    v76 = 0;
    if ( v88 )
    {
      v77 = 0;
      do
      {
        v78 = 88 * v77;
        v79 = *(_QWORD *)(88 * v77 + v8);
        if ( v79 )
          CryptReleaseContext(v79, 0);
        v80 = *(_QWORD *)(v78 + v8 + 8);
        if ( v80 )
          NCryptFreeObject(v80);
        v81 = *(const WCHAR **)(v78 + v8 + 24);
        if ( v81
          && v81 != L"Microsoft Software Key Storage Provider"
          && v81 != L"Microsoft Base Cryptographic Provider v1.0"
          && v81 != L"Microsoft Enhanced Cryptographic Provider v1.0"
          && v81 != L"Microsoft Base DSS and Diffie-Hellman Cryptographic Provider" )
        {
          PFXHelpFree(v81);
        }
        v82 = *(_QWORD *)(v78 + v8 + 16);
        if ( v82 )
          PFXHelpFree(v82);
        v83 = *(_QWORD *)(v78 + v8 + 64);
        if ( v83 )
          PFXHelpFree(v83);
        v84 = *(_QWORD *)(v78 + v8 + 72);
        if ( v84 )
          PFXHelpFree(v84);
        ++v76;
        ++v77;
      }
      while ( v76 < v88 );
    }
    PFXHelpFree(v8);
  }
  if ( v13 >= 0 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 24, WPP_dc3d9b1f72b2343e6ef12ad6b8d70f74_Traceguids);
  }
  else
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, v12, (unsigned int)v13);
    SetLastError(v13);
  }
  return v13 >= 0;
}

```

## disassembly

```asm
0x1800f94ec  mov     rax, rsp
0x1800f94ef  mov     [rax+20h], r9d
0x1800f94f3  mov     [rax+18h], r8
0x1800f94f7  mov     [rax+10h], rdx
0x1800f94fb  mov     [rax+8], rcx
0x1800f94ff  push    rbp
0x1800f9500  push    rbx
0x1800f9501  push    rsi
0x1800f9502  push    rdi
0x1800f9503  push    r12
0x1800f9505  push    r13
0x1800f9507  push    r14
0x1800f9509  push    r15
0x1800f950b  lea     rbp, [rax-47h]
0x1800f950f  sub     rsp, 0A8h
0x1800f9516  xor     ecx, ecx
0x1800f9518  mov     rsi, r8
0x1800f951b  mov     [rbp+3Fh+cbCertEncoded], ecx
0x1800f951e  cmp     [rbp+3Fh+phProv], rcx
0x1800f9522  jz      short loc_1800F9530
0x1800f9524  test    [rbp+3Fh+dwFlags], 0C00h
0x1800f952b  mov     [rbp+3Fh+var_90], ecx
0x1800f952e  jz      short loc_1800F9537
0x1800f9530  mov     [rbp+3Fh+var_90], 1
0x1800f9537  mov     r14, rcx
0x1800f953a  mov     [rbp+3Fh+var_78], rcx
0x1800f953e  mov     r13, rcx
0x1800f9541  mov     [rbp+3Fh+var_A0], ecx
0x1800f9544  mov     ebx, ecx
0x1800f9546  mov     dword ptr [rbp+3Fh+arg_30], ecx
0x1800f9549  mov     r15d, ecx
0x1800f954c  lea     rdx, [rbp+3Fh+cbCertEncoded]; unsigned int *
0x1800f9550  mov     ecx, 3; unsigned int
0x1800f9555  call    ?PfxGetMaxPermissibleLimit@@YAJKPEAK@Z; PfxGetMaxPermissibleLimit(ulong,ulong *)
0x1800f955a  test    eax, eax
0x1800f955c  jnz     loc_1800F9D7D
0x1800f9562  mov     edx, [rbp+3Fh+cbCertEncoded]; unsigned int
0x1800f9565  cmp     [rsi], edx
0x1800f9567  jbe     short loc_1800F9580
0x1800f9569  mov     r8d, [rsi]; unsigned int
0x1800f956c  mov     ecx, 1052h; unsigned int
0x1800f9571  call    ?PfxLogCrypt32Error@@YAXKKK@Z; PfxLogCrypt32Error(ulong,ulong,ulong)
0x1800f9576  mov     edi, 80092002h
0x1800f957b  jmp     loc_1800F9D82
0x1800f9580  xor     eax, eax
0x1800f9582  xor     edi, edi
0x1800f9584  mov     [rbp+3Fh+var_9C], eax
0x1800f9587  cmp     [rsi], eax
0x1800f9589  jbe     loc_1800F9B53
0x1800f958f  mov     rsi, [rsi+8]
0x1800f9593  lea     r12, [rax+rax*4]
0x1800f9597  lea     rdx, a12840113549112_7; "1.2.840.113549.1.12.10.1.1"
0x1800f959e  mov     [rbp+3Fh+var_88], r12
0x1800f95a2  mov     [rbp+3Fh+hMem], rsi
0x1800f95a6  mov     rcx, [rsi+r12*8]; Str1
0x1800f95aa  call    strcmp_0
0x1800f95af  test    eax, eax
0x1800f95b1  jz      loc_1800F979A
0x1800f95b7  mov     rcx, [rsi+r12*8]; Str1
0x1800f95bb  lea     rdx, a12840113549112_4; "1.2.840.113549.1.12.10.1.2"
0x1800f95c2  call    strcmp_0
0x1800f95c7  test    eax, eax
0x1800f95c9  jz      loc_1800F979A
0x1800f95cf  cmp     r15d, 0AAAAAAAh
0x1800f95d6  ja      loc_1800F9C45
0x1800f95dc  test    r15d, r15d
0x1800f95df  jnz     short loc_1800F95F0
0x1800f95e1  lea     ecx, [r15+18h]; uBytes
0x1800f95e5  call    PFXHelpAlloc
0x1800f95ea  lea     ebx, [r15+1]
0x1800f95ee  jmp     short loc_1800F9604
0x1800f95f0  lea     ebx, [r15+1]
0x1800f95f4  mov     rcx, r13
0x1800f95f7  lea     rdx, [rbx+rbx*2]
0x1800f95fb  shl     rdx, 3
0x1800f95ff  call    PFXHelpRealloc
0x1800f9604  mov     rsi, rax
0x1800f9607  test    rax, rax
0x1800f960a  jz      loc_1800F9C45
0x1800f9610  mov     rdi, [rbp+3Fh+hMem]
0x1800f9614  lea     r9, [rbp+3Fh+cbCertEncoded]
0x1800f9618  mov     r13, rax
0x1800f961b  mov     [rbp+3Fh+var_78], rax
0x1800f961f  mov     eax, r15d
0x1800f9622  xorps   xmm0, xmm0
0x1800f9625  xor     r8d, r8d
0x1800f9628  mov     dword ptr [rbp+3Fh+arg_30], ebx
0x1800f962b  lea     rcx, [rax+rax*2]
0x1800f962f  xor     eax, eax
0x1800f9631  lea     r15, [r13+rcx*8+0]
0x1800f9636  mov     [rbp+3Fh+cbCertEncoded], eax
0x1800f9639  movups  xmmword ptr [r15], xmm0
0x1800f963d  mov     [r15+10h], rax
0x1800f9641  mov     edx, [rdi+r12*8+8]
0x1800f9646  mov     rcx, [rdi+r12*8+10h]
0x1800f964b  call    GetEncodedCertFromEncodedCertBag
0x1800f9650  test    eax, eax
0x1800f9652  jz      loc_1800F9C22
0x1800f9658  mov     ecx, [rbp+3Fh+cbCertEncoded]; uBytes
0x1800f965b  call    PFXHelpAlloc
0x1800f9660  mov     rbx, rax
0x1800f9663  test    rax, rax
0x1800f9666  jz      loc_1800F9C11
0x1800f966c  mov     edx, [rdi+r12*8+8]
0x1800f9671  lea     r9, [rbp+3Fh+cbCertEncoded]
0x1800f9675  mov     rcx, [rdi+r12*8+10h]
0x1800f967a  mov     r8, rax
0x1800f967d  call    GetEncodedCertFromEncodedCertBag
0x1800f9682  test    eax, eax
0x1800f9684  jz      loc_1800F9BEC
0x1800f968a  mov     r9d, [rbp+3Fh+cbCertEncoded]; cbCertEncoded
0x1800f968e  mov     r8, rbx; pbCertEncoded
0x1800f9691  mov     rcx, [rbp+3Fh+hCertStore]; hCertStore
0x1800f9695  mov     edx, 1; dwCertEncodingType
0x1800f969a  mov     [rsp+0E0h+ppCertContext], r15; ppCertContext
0x1800f969f  mov     [rsp+0E0h+dwAddDisposition], 4; dwAddDisposition
0x1800f96a7  call    CertAddEncodedCertificateToStore
0x1800f96ac  test    eax, eax
0x1800f96ae  jz      loc_1800F9BEC
0x1800f96b4  mov     rcx, rbx
0x1800f96b7  call    PFXHelpFree
0x1800f96bc  mov     rcx, [r15]
0x1800f96bf  lea     rdi, [rdi+r12*8]
0x1800f96c3  add     rdi, 18h
0x1800f96c7  mov     rdx, rdi
0x1800f96ca  call    AddFriendlyNameProperty
0x1800f96cf  test    eax, eax
0x1800f96d1  jz      loc_1800F9BD2
0x1800f96d7  mov     r12d, [rbp+3Fh+dwFlags]
0x1800f96db  test    r12b, 10h
0x1800f96df  jz      short loc_1800F96F4
0x1800f96e1  mov     rcx, [r15]; pCertContext
0x1800f96e4  mov     rdx, rdi
0x1800f96e7  call    AddExtendedProperties
0x1800f96ec  test    eax, eax
0x1800f96ee  jz      loc_1800F9BD2
0x1800f96f4  lea     rbx, [r15+8]
0x1800f96f8  mov     r9d, r12d
0x1800f96fb  mov     r8, rbx
0x1800f96fe  xor     edx, edx
0x1800f9700  mov     rcx, rdi
0x1800f9703  call    DecodeSafeBagAttributes
0x1800f9708  mov     rcx, [r15]; struct _CERT_CONTEXT *
0x1800f970b  lea     rdx, [rbp+3Fh+hMem]; unsigned __int16 **
0x1800f970f  mov     edi, eax
0x1800f9711  mov     [rbp+3Fh+cbCertEncoded], eax
0x1800f9714  mov     [rbp+3Fh+hMem], 0
0x1800f971c  call    ?PfxGetFriendlyCertName@@YAXPEBU_CERT_CONTEXT@@PEAPEAG@Z; PfxGetFriendlyCertName(_CERT_CONTEXT const *,ushort * *)
0x1800f9721  mov     rcx, [rbx]
0x1800f9724  xor     r15d, r15d
0x1800f9727  mov     [rbp+3Fh+var_88], r15
0x1800f972b  test    rcx, rcx
0x1800f972e  jz      short loc_1800F9743
0x1800f9730  mov     rdx, [rcx+8]; unsigned __int8 *
0x1800f9734  lea     r8, [rbp+3Fh+var_88]; unsigned __int16 **
0x1800f9738  mov     ecx, [rcx]; unsigned int
0x1800f973a  call    ?PfxGetFriendlyPbData@@YAXKPEBEPEAPEAG@Z; PfxGetFriendlyPbData(ulong,uchar const *,ushort * *)
0x1800f973f  mov     r15, [rbp+3Fh+var_88]
0x1800f9743  mov     rcx, cs:WPP_GLOBAL_Control
0x1800f974a  lea     rax, WPP_GLOBAL_Control
0x1800f9751  mov     rbx, [rbp+3Fh+hMem]
0x1800f9755  cmp     rcx, rax
0x1800f9758  jz      short loc_1800F9777
0x1800f975a  test    byte ptr [rcx+1Ch], 2
0x1800f975e  jz      short loc_1800F9777
0x1800f9760  mov     r9d, [rbp+3Fh+var_9C]
0x1800f9764  mov     rcx, [rcx+10h]
0x1800f9768  mov     [rsp+0E0h+ppCertContext], rbx
0x1800f976d  mov     qword ptr [rsp+0E0h+dwAddDisposition], r15
0x1800f9772  call    WPP_SF_dSS
0x1800f9777  mov     rcx, r15; hMem
0x1800f977a  call    cs:__imp_LocalFree
0x1800f9780  mov     rcx, rbx; hMem
0x1800f9783  call    cs:__imp_LocalFree
0x1800f9789  mov     r15d, dword ptr [rbp+3Fh+arg_30]
0x1800f978d  test    edi, edi
0x1800f978f  js      loc_1800F9A0B
0x1800f9795  jmp     loc_1800F9B3C
0x1800f979a  cmp     [rbp+3Fh+var_90], 0
0x1800f979e  jnz     loc_1800F9B3F
0x1800f97a4  cmp     ebx, 2E8BA2Eh
0x1800f97aa  ja      loc_1800F9C45
0x1800f97b0  test    ebx, ebx
0x1800f97b2  jnz     short loc_1800F97C1
0x1800f97b4  lea     ecx, [rbx+58h]; uBytes
0x1800f97b7  call    PFXHelpAlloc
0x1800f97bc  lea     edi, [rbx+1]
0x1800f97bf  jmp     short loc_1800F97D2
0x1800f97c1  lea     edi, [rbx+1]
0x1800f97c4  mov     rcx, r14
0x1800f97c7  mov     eax, edi
0x1800f97c9  imul    rdx, rax, 58h ; 'X'
0x1800f97cd  call    PFXHelpRealloc
0x1800f97d2  mov     rdx, rax
0x1800f97d5  test    rax, rax
0x1800f97d8  jz      loc_1800F9C45
0x1800f97de  mov     r14, rax
0x1800f97e1  mov     [rbp+3Fh+var_A0], edi
0x1800f97e4  mov     eax, ebx
0x1800f97e6  imul    rbx, rax, 58h ; 'X'
0x1800f97ea  add     rbx, rdx
0x1800f97ed  xor     edx, edx; Val
0x1800f97ef  mov     rcx, rbx; void *
0x1800f97f2  lea     r8d, [rdx+58h]; Size
0x1800f97f6  call    memset_0
0x1800f97fb  lea     rcx, [r12+3]
0x1800f9800  mov     r12d, [rbp+3Fh+dwFlags]
0x1800f9804  lea     rcx, [rsi+rcx*8]
0x1800f9808  mov     r9d, r12d
0x1800f980b  lea     rdx, [rbx+10h]
0x1800f980f  lea     r8, [rbx+40h]
0x1800f9813  call    DecodeSafeBagAttributes
0x1800f9818  mov     [rbp+3Fh+cbCertEncoded], eax
0x1800f981b  mov     edi, eax
0x1800f981d  test    eax, eax
0x1800f981f  js      loc_1800F99FB
0x1800f9825  mov     rcx, [rbx+40h]
0x1800f9829  xor     esi, esi
0x1800f982b  mov     [rbp+3Fh+phKey], rsi
0x1800f982f  test    rcx, rcx
0x1800f9832  jz      short loc_1800F9847
0x1800f9834  mov     rdx, [rcx+8]; unsigned __int8 *
0x1800f9838  lea     r8, [rbp+3Fh+phKey]; unsigned __int16 **
0x1800f983c  mov     ecx, [rcx]; unsigned int
0x1800f983e  call    ?PfxGetFriendlyPbData@@YAXKPEBEPEAPEAG@Z; PfxGetFriendlyPbData(ulong,uchar const *,ushort * *)
0x1800f9843  mov     rsi, [rbp+3Fh+phKey]
0x1800f9847  mov     rcx, cs:WPP_GLOBAL_Control
0x1800f984e  lea     rax, WPP_GLOBAL_Control
0x1800f9855  cmp     rcx, rax
0x1800f9858  jz      short loc_1800F9884
0x1800f985a  test    byte ptr [rcx+1Ch], 2
0x1800f985e  jz      short loc_1800F9884
0x1800f9860  mov     rax, [rbx+10h]
0x1800f9864  mov     r9d, [rbp+3Fh+var_9C]
0x1800f9868  mov     rcx, [rcx+10h]
0x1800f986c  mov     [rsp+30h], rax
0x1800f9871  mov     rax, [rbx+18h]
0x1800f9875  mov     [rsp+0E0h+ppCertContext], rax
0x1800f987a  mov     qword ptr [rsp+0E0h+dwAddDisposition], rsi
0x1800f987f  call    WPP_SF_dSSS
0x1800f9884  mov     rcx, rsi; hMem
0x1800f9887  call    cs:__imp_LocalFree
0x1800f988d  xor     esi, esi
0x1800f988f  lea     r15, [rbx+18h]
0x1800f9893  mov     rcx, [r15]; String2
0x1800f9896  test    rcx, rcx
0x1800f9899  setnz   sil
0x1800f989d  test    rcx, rcx
0x1800f98a0  jz      short loc_1800F98CA
0x1800f98a2  lea     rdx, [rbx+20h]
0x1800f98a6  call    GetCAPIProviderTypeByName
0x1800f98ab  test    eax, eax
0x1800f98ad  jz      short loc_1800F98DA
0x1800f98af  test    r12d, 10200h
0x1800f98b6  jz      short loc_1800F98D3
0x1800f98b8  mov     rcx, [r15]
0x1800f98bb  xor     esi, esi
0x1800f98bd  call    PFXHelpFree
0x1800f98c2  mov     [r15], rsi
0x1800f98c5  mov     [rbx+20h], esi
0x1800f98c8  jmp     short loc_1800F98DA
0x1800f98ca  test    r12d, 10300h
0x1800f98d1  jnz     short loc_1800F98DA
0x1800f98d3  mov     dword ptr [rbx+50h], 1
0x1800f98da  xor     r12d, r12d
0x1800f98dd  cmp     [rbx+50h], r12d
0x1800f98e1  jz      short loc_1800F995C
0x1800f98e3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800f98ea  lea     rax, WPP_GLOBAL_Control
0x1800f98f1  cmp     rcx, rax
0x1800f98f4  jz      short loc_1800F9916
0x1800f98f6  test    byte ptr [rcx+1Ch], 2
0x1800f98fa  jz      short loc_1800F9916
0x1800f98fc  mov     rax, [rbx+10h]
0x1800f9900  lea     edx, [r12+12h]
0x1800f9905  mov     r9, [r15]
0x1800f9908  mov     rcx, [rcx+10h]
0x1800f990c  mov     qword ptr [rsp+0E0h+dwAddDisposition], rax
0x1800f9911  call    WPP_SF_SS
0x1800f9916  mov     eax, [rbp+3Fh+dwFlags]
0x1800f9919  mov     rcx, rbx; phCryptProv
0x1800f991c  mov     r8, [rbp+3Fh+var_88]
0x1800f9920  mov     rdx, [rbp+3Fh+phProv]
0x1800f9924  mov     [rsp+0E0h+dwAddDisposition], eax; dwFlags
0x1800f9928  mov     rax, [rbp+3Fh+hMem]
0x1800f992c  mov     r9d, [rax+r8*8+8]
0x1800f9931  mov     r8, [rax+r8*8+10h]
0x1800f9936  call    ImportCAPIKey
0x1800f993b  mov     [rbp+3Fh+cbCertEncoded], eax
0x1800f993e  mov     edi, eax
0x1800f9940  test    eax, eax
0x1800f9942  jns     short loc_1800F995C
0x1800f9944  cmp     eax, 800704C7h
0x1800f9949  jz      loc_1800F99FB
0x1800f994f  mov     r12d, 1
0x1800f9955  mov     dword ptr [rbx+50h], 0
0x1800f995c  cmp     dword ptr [rbx+50h], 0
0x1800f9960  jnz     loc_1800F9A34
0x1800f9966  and     dword ptr [rbx+24h], 20h
0x1800f996a  test    r12d, r12d
  ... truncated ...
```
