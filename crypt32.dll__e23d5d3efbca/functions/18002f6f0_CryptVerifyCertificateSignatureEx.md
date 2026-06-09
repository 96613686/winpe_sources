# CryptVerifyCertificateSignatureEx

- ea: `0x18002f6f0`
- end: `0x18002fe5d`
- name: `CryptVerifyCertificateSignatureEx`
- size: `1901`
- prototype: `BOOL __stdcall(HCRYPTPROV_LEGACY hCryptProv, DWORD dwCertEncodingType, DWORD dwSubjectType, void *pvSubject, DWORD dwIssuerType, void *pvIssuer, DWORD dwFlags, void *pvExtra)`
- caller_count: `6`
- callee_count: `16`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18006433c`
- `0x180066184`
- `0x180067fac`
- `0x1800686b0`
- `0x1800ac0e0`
- `0x1800e3414`

## callees

- `0x180008720`
- `0x180009da0`
- `0x180014ae0`
- `0x180028d60`
- `0x18002f6f0`
- `0x18002fe64`
- `0x180030218`
- `0x180030e60`
- `0x180046e10`
- `0x18004d730`
- `0x1800600e0`
- `0x1800959d4`
- `0x1800a9f44`
- `0x1800b90f4`
- `0x1800bf63c`
- `0x1801150d0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002f9e2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002fa04`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002fb65`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002fe3c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002f9e2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002fa04`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002fb65`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002fe3c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002f9f5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002fa17`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002fa90`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002fcf3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002fe24`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002fe52`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002f9f5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002fa17`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002fa90`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002fcf3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002fe24`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002fe52`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002f9ed`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002fa0f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002f9ed`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002fa0f`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18002f941`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18002fbbc`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18002f941`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18002fbbc`

## pseudocode

```c
BOOL __stdcall CryptVerifyCertificateSignatureEx(
        HCRYPTPROV_LEGACY hCryptProv,
        DWORD dwCertEncodingType,
        DWORD dwSubjectType,
        void *pvSubject,
        DWORD dwIssuerType,
        void *pvIssuer,
        DWORD dwFlags,
        void *pvExtra)
{
  char v8; // r10
  BOOL v10; // r12d
  int v11; // r15d
  DWORD v12; // r9d
  void *v13; // rsi
  PCCRYPT_OID_INFO OIDInfo; // rax
  PCCRYPT_OID_INFO v15; // rdi
  ALG_ID dwValue; // r14d
  unsigned int v17; // eax
  DWORD *pbData; // rcx
  DWORD v19; // edx
  unsigned int v20; // esi
  const CERT_CONTEXT *v21; // rcx
  __int128 *p_SubjectPublicKeyInfo; // rbx
  __int64 v23; // rsi
  int v24; // ebx
  unsigned __int64 v25; // r14
  unsigned int v26; // ebx
  size_t v27; // r14
  unsigned __int16 *v28; // rax
  unsigned __int16 *v29; // r15
  DWORD v30; // eax
  HLOCAL v31; // rdi
  DWORD LastError; // ebx
  HLOCAL v33; // rdi
  DWORD v34; // ebx
  _DWORD *v36; // rcx
  DWORD v37; // ecx
  _QWORD *v38; // r13
  _DWORD *v39; // rax
  _DWORD *v40; // rsi
  __int64 v41; // rdx
  PCCRYPT_OID_INFO v42; // rax
  PCCRYPT_OID_INFO v43; // rax
  unsigned int v44; // eax
  _OWORD *v45; // rax
  _QWORD *v46; // rax
  _QWORD *v47; // rax
  char *v48; // rcx
  void *v49; // rax
  BOOL CertificateContextProperty; // eax
  __int128 v51; // xmm0
  PCCRYPT_OID_INFO v52; // rax
  unsigned int v53; // [rsp+28h] [rbp-A9h]
  PCRYPT_DECODE_PARA pDecodePara; // [rsp+30h] [rbp-A1h]
  unsigned int v55; // [rsp+48h] [rbp-89h]
  void *v56; // [rsp+50h] [rbp-81h]
  HLOCAL hMem; // [rsp+58h] [rbp-79h] BYREF
  PCCERT_CONTEXT pCertContext; // [rsp+60h] [rbp-71h]
  DWORD pcbData; // [rsp+68h] [rbp-69h] BYREF
  DWORD v60[2]; // [rsp+70h] [rbp-61h] BYREF
  void *pvKey; // [rsp+78h] [rbp-59h] BYREF
  DWORD pcbStructInfo; // [rsp+80h] [rbp-51h] BYREF
  unsigned __int64 v63; // [rsp+88h] [rbp-49h] BYREF
  DWORD *p_dwFlags; // [rsp+90h] [rbp-41h]
  HLOCAL v65; // [rsp+98h] [rbp-39h]
  __int128 v66; // [rsp+A0h] [rbp-31h] BYREF
  __int128 v67; // [rsp+B0h] [rbp-21h]
  __int128 v68; // [rsp+C0h] [rbp-11h]

  v8 = dwFlags;
  hMem = 0;
  pcbStructInfo = 0;
  v65 = 0;
  v10 = 1;
  LODWORD(pvKey) = dwFlags & 1;
  v66 = 0;
  v67 = 0;
  v68 = 0;
  if ( (dwFlags & 4) != 0 )
  {
    if ( (dwFlags & 8) != 0 )
      goto LABEL_60;
    if ( !pvExtra )
      goto LABEL_60;
    *(_QWORD *)pvExtra = 0;
    if ( dwSubjectType != 4 )
      goto LABEL_60;
    v11 = 1;
    v63 = 0;
  }
  else
  {
    v63 = 0;
    v11 = 0;
    if ( (dwFlags & 8) != 0 )
    {
      v36 = pvExtra;
      if ( !pvExtra )
        goto LABEL_60;
      *((_DWORD *)pvExtra + 4) = *(_DWORD *)pvExtra;
      v63 = (unsigned __int64)v36;
    }
  }
  if ( (v8 & 2) != 0 )
  {
    if ( dwSubjectType == 3 )
    {
      v11 = 1;
      goto LABEL_6;
    }
LABEL_60:
    v37 = -2147024809;
LABEL_61:
    SetLastError(v37);
    goto LABEL_62;
  }
  if ( dwSubjectType == 1 )
  {
    v12 = *(_DWORD *)pvSubject;
LABEL_7:
    if ( !CryptDecodeObjectEx(
            dwCertEncodingType,
            (LPCSTR)1,
            *((const BYTE **)pvSubject + 1),
            v12,
            0x800Du,
            &PkiDecodePara,
            &hMem,
            &pcbStructInfo) )
      goto LABEL_62;
    goto LABEL_8;
  }
  if ( dwSubjectType == 2 || dwSubjectType == 3 )
  {
LABEL_6:
    v12 = *((_DWORD *)pvSubject + 4);
    goto LABEL_7;
  }
  if ( dwSubjectType != 4 )
    goto LABEL_60;
  v44 = *((_DWORD *)pvSubject + 10);
  if ( v44 > 0xFFFF )
  {
    v37 = 534;
    goto LABEL_61;
  }
  pcbStructInfo = v44 + 64;
  v45 = (_OWORD *)PkiZeroAlloc(v44 + 64);
  hMem = v45;
  if ( !v45 )
    goto LABEL_62;
  *v45 = *(_OWORD *)pvSubject;
  v46 = hMem;
  *((_OWORD *)hMem + 1) = *((_OWORD *)pvSubject + 1);
  v46[4] = *((_QWORD *)pvSubject + 4);
  v47 = hMem;
  *(_OWORD *)((char *)hMem + 40) = *(_OWORD *)((char *)pvSubject + 40);
  v47[7] = *((_QWORD *)pvSubject + 7);
  v48 = (char *)hMem + 64;
  *((_QWORD *)hMem + 6) = (char *)hMem + 64;
  memcpy_0(v48, *((const void **)pvSubject + 6), *((unsigned int *)pvSubject + 10));
LABEL_8:
  v60[0] = 0;
  v13 = (void *)*((_QWORD *)hMem + 2);
  OIDInfo = CryptFindOIDInfo(1u, v13, 0x40000004u);
  v15 = OIDInfo;
  if ( !OIDInfo )
  {
    v43 = CryptFindOIDInfo(1u, v13, 0x40000001u);
    v15 = v43;
    if ( !v43 )
    {
      SetLastError(0x80090008);
      v37 = 50;
      goto LABEL_61;
    }
    dwValue = v43->dwValue;
    v20 = 0;
    v19 = 0x2000;
    dwFlags = 0x2000;
    goto LABEL_95;
  }
  dwValue = OIDInfo->dwValue;
  v17 = OIDInfo->ExtraInfo.cbData >> 2;
  if ( !v17 )
  {
    v19 = 0;
    dwFlags = 0;
LABEL_11:
    v20 = 0;
    goto LABEL_12;
  }
  pbData = (DWORD *)v15->ExtraInfo.pbData;
  v19 = *pbData;
  dwFlags = *pbData;
  if ( v17 < 2 )
    goto LABEL_11;
  v60[0] = pbData[1];
  if ( v17 < 3 )
    goto LABEL_11;
  v20 = pbData[2];
LABEL_12:
  if ( v19 != 0x2000 )
    goto LABEL_13;
LABEL_95:
  if ( dwIssuerType != 4 )
    goto LABEL_60;
LABEL_13:
  v21 = 0;
  pCertContext = 0;
  if ( dwIssuerType == 1 )
  {
    p_SubjectPublicKeyInfo = (__int128 *)pvIssuer;
  }
  else
  {
    if ( dwIssuerType == 2 )
    {
      v21 = (const CERT_CONTEXT *)pvIssuer;
    }
    else
    {
      if ( dwIssuerType != 3 )
      {
        if ( dwIssuerType != 4 || v19 != 0x2000 )
          goto LABEL_60;
        p_SubjectPublicKeyInfo = 0;
        goto LABEL_20;
      }
      v21 = *(const CERT_CONTEXT **)(**(_QWORD **)(**((_QWORD **)pvIssuer + 2) + 16LL) + 8LL);
    }
    p_SubjectPublicKeyInfo = (__int128 *)&v21->pCertInfo->SubjectPublicKeyInfo;
    pCertContext = v21;
    if ( !*((_DWORD *)p_SubjectPublicKeyInfo + 2) || **((_BYTE **)p_SubjectPublicKeyInfo + 2) == 5 )
    {
      pcbData = 0;
      if ( CertGetCertificateContextProperty(v21, 0x16u, 0, &pcbData) && pcbData )
      {
        v49 = (void *)PkiNonzeroAlloc(pcbData);
        v21 = pCertContext;
        v65 = v49;
        if ( v49 )
        {
          CertificateContextProperty = CertGetCertificateContextProperty(pCertContext, 0x16u, v49, &pcbData);
          v21 = pCertContext;
          if ( CertificateContextProperty )
          {
            v66 = *p_SubjectPublicKeyInfo;
            v67 = p_SubjectPublicKeyInfo[1];
            v51 = p_SubjectPublicKeyInfo[2];
            *(_QWORD *)&v67 = v65;
            p_SubjectPublicKeyInfo = &v66;
            v68 = v51;
            DWORD2(v66) = pcbData;
          }
        }
      }
      else
      {
        v21 = pCertContext;
      }
    }
  }
LABEL_20:
  if ( v11 && !v21 )
    goto LABEL_60;
  if ( dwValue < 0xFFFFFFFD )
  {
    if ( (unsigned int)I_CryptCAPI1VerifyCertificateSignedContent(
                         dwValue,
                         dwFlags,
                         v60[0],
                         v20,
                         hCryptProv,
                         dwCertEncodingType,
                         (struct _CERT_PUBLIC_KEY_INFO *)p_SubjectPublicKeyInfo,
                         (struct _CERT_SIGNED_CONTENT_INFO *)hMem,
                         v55,
                         v56) )
      goto LABEL_23;
    if ( GetLastError() != -2146881276 )
    {
LABEL_62:
      if ( (_DWORD)pvKey && GetLastError() == -2146893816 )
        SetLastError(0x80090006);
      v10 = 0;
      goto LABEL_47;
    }
  }
  if ( !I_CryptCNGVerifyCertificateSignedContent(
          v15,
          dwCertEncodingType,
          (struct _CERT_PUBLIC_KEY_INFO *)p_SubjectPublicKeyInfo,
          (struct _CERT_SIGNED_CONTENT_INFO *)hMem,
          v53,
          pDecodePara) )
    goto LABEL_62;
LABEL_23:
  v23 = -1;
  if ( p_SubjectPublicKeyInfo )
  {
    if ( dwSubjectType == 2 )
    {
      if ( *((_DWORD *)p_SubjectPublicKeyInfo + 2) )
      {
        if ( **((_BYTE **)p_SubjectPublicKeyInfo + 2) != 5 )
        {
          v41 = *((_QWORD *)pvSubject + 3);
          if ( !*(_DWORD *)(v41 + 104) || **(_BYTE **)(v41 + 112) == 5 )
          {
            v42 = CryptFindOIDInfo(1u, *(void **)(v41 + 96), 0x40000003u);
            if ( v42 )
            {
              if ( CompareStringW(0x409u, 1u, (PCNZWCH)v15[1].pszOID, -1, *(PCNZWCH *)&v42[1].cbSize, -1) == 2
                && !(unsigned int)I_CertUpdatePubKeyAlgPara((PCCERT_CONTEXT)pvSubject) )
              {
                goto LABEL_62;
              }
            }
          }
        }
      }
    }
  }
  v24 = (int)pvKey;
  if ( (_DWORD)pvKey || v63 )
  {
    if ( dwValue == -2 )
    {
      *(_QWORD *)v60 = 0;
      pvKey = 0;
      if ( (unsigned int)I_CryptCNGExtractEncodedSignatureParameters(
                           dwCertEncodingType,
                           (struct _CRYPT_ALGORITHM_IDENTIFIER *)((char *)hMem + 16),
                           (void **)v60,
                           (unsigned __int16 **)&pvKey) )
      {
        v52 = CryptFindOIDInfo(5u, pvKey, 0x40000001u);
        v15 = v52;
        dwValue = 32769;
        if ( v52 )
          dwValue = v52->dwValue;
      }
      else
      {
        v15 = 0;
        dwValue = 32769;
      }
      if ( *(_QWORD *)v60 )
        PkiDefaultCryptFree(*(HLOCAL *)v60);
      if ( pvKey )
        PkiDefaultCryptFree(pvKey);
    }
    if ( v24 && dwValue - 32769 <= 1 )
    {
      SetLastError(0x80090008);
      v10 = 0;
      goto LABEL_47;
    }
    v25 = v63;
    v26 = 0;
    if ( v63 && v15 )
    {
      if ( *(_DWORD *)v63 )
      {
        do
        {
          if ( CompareStringW(
                 0x409u,
                 1u,
                 *(PCNZWCH *)&v15[1].cbSize,
                 -1,
                 *(PCNZWCH *)(*(_QWORD *)(v25 + 8) + 8LL * v26),
                 -1) == 2 )
            break;
          ++v26;
        }
        while ( v26 < *(_DWORD *)v25 );
      }
      *(_DWORD *)(v25 + 16) = v26;
    }
  }
  if ( v11 )
  {
    v27 = 0;
    dwFlags = 0;
    v60[0] = 4;
    v28 = I_CryptCNGGetSignHashAlgidFromSignatureAlgorithm(
            dwCertEncodingType,
            (struct _CRYPT_ALGORITHM_IDENTIFIER *)((char *)hMem + 16));
    v29 = v28;
    if ( v28 )
    {
      do
        ++v23;
      while ( v28[v23] );
      if ( (unsigned __int64)((int)v23 + 1) <= 0x42 )
        v27 = 2LL * ((int)v23 + 1);
    }
    if ( CertGetCertificateContextProperty(pCertContext, 0x5Cu, &dwFlags, v60) && v60[0] == 4 )
    {
      v30 = dwFlags;
    }
    else
    {
      v30 = 0;
      dwFlags = 0;
    }
    if ( v27 && v30 )
    {
      if ( dwSubjectType == 3 )
      {
        p_dwFlags = (DWORD *)v29;
        v63 = (unsigned int)v27;
        SetProperty(
          (struct _CONTEXT_ELEMENT *)(((__int64)pvSubject - 80) & -(__int64)(pvSubject != 0)),
          0x59u,
          0x40000000u,
          &v63,
          0);
        LODWORD(v63) = 4;
        p_dwFlags = &dwFlags;
        SetProperty(
          (struct _CONTEXT_ELEMENT *)(((__int64)pvSubject - 80) & -(__int64)(pvSubject != 0)),
          0x5Eu,
          0x40000000u,
          &v63,
          0);
      }
      else if ( dwSubjectType == 4 )
      {
        v38 = pvExtra;
        if ( pvExtra )
        {
          v39 = (_DWORD *)PkiAlloc((unsigned int)(v27 + 36));
          v40 = v39;
          if ( v39 )
          {
            memset_0(v39, 0, v27 + 36);
            v40[8] = dwFlags;
            memcpy_0(v40 + 9, v29, v27);
            *((_QWORD *)v40 + 1) = v40 + 9;
            *v40 = v27;
            *((_QWORD *)v40 + 3) = v40 + 8;
            v40[4] = 4;
            *v38 = v40;
          }
        }
      }
    }
    PkiDefaultCryptFree(v29);
  }
LABEL_47:
  v31 = hMem;
  if ( hMem )
  {
    LastError = GetLastError();
    LocalFree(v31);
    SetLastError(LastError);
  }
  v33 = v65;
  if ( v65 )
  {
    v34 = GetLastError();
    LocalFree(v33);
    SetLastError(v34);
  }
  return v10;
}

```

## disassembly

```asm
0x18002f6f0  mov     rax, rsp
0x18002f6f3  mov     [rax+20h], rbx
0x18002f6f7  mov     [rax+18h], r8d
0x18002f6fb  mov     [rax+10h], edx
0x18002f6fe  mov     [rax+8], rcx
0x18002f702  push    rbp
0x18002f703  push    rsi
0x18002f704  push    rdi
0x18002f705  push    r12
0x18002f707  push    r13
0x18002f709  push    r14
0x18002f70b  push    r15
0x18002f70d  lea     rbp, [rax-3Fh]
0x18002f711  sub     rsp, 0D0h
0x18002f718  mov     r10d, [rbp+37h+dwFlags]
0x18002f71c  xor     r14d, r14d
0x18002f71f  xorps   xmm0, xmm0
0x18002f722  mov     [rbp+37h+hMem], r14
0x18002f726  mov     r13, r9
0x18002f729  mov     [rbp+37h+pcbStructInfo], r14d
0x18002f72d  mov     r9d, r8d
0x18002f730  mov     [rbp+37h+var_70], r14
0x18002f734  lea     r12d, [r14+1]
0x18002f738  mov     eax, r10d
0x18002f73b  and     eax, r12d
0x18002f73e  lea     r8d, [r14+8]
0x18002f742  mov     ecx, r10d
0x18002f745  mov     dword ptr [rbp+37h+pvKey], eax
0x18002f748  and     ecx, r8d
0x18002f74b  mov     r11d, edx
0x18002f74e  movups  [rbp+37h+var_68], xmm0
0x18002f752  movups  [rbp+37h+var_58], xmm0
0x18002f756  movups  [rbp+37h+var_48], xmm0
0x18002f75a  test    r10b, 4
0x18002f75e  jnz     loc_18002FC05
0x18002f764  mov     [rbp+37h+var_80], r14
0x18002f768  mov     r15d, r14d
0x18002f76b  test    ecx, ecx
0x18002f76d  jnz     loc_18002FA3B
0x18002f773  test    r10b, 2
0x18002f777  jnz     loc_18002FC9E
0x18002f77d  mov     eax, r9d
0x18002f780  sub     eax, r12d
0x18002f783  jz      loc_18002FCCC
0x18002f789  sub     eax, r12d
0x18002f78c  jnz     loc_18002FD23
0x18002f792  mov     r9d, [r13+10h]; cbEncoded
0x18002f796  lea     rcx, [rbp+37h+pcbStructInfo]
0x18002f79a  mov     rax, r13
0x18002f79d  mov     [rsp+38h], rcx; pcbStructInfo
0x18002f7a2  mov     rdx, r12; lpszStructType
0x18002f7a5  lea     rcx, [rbp+37h+hMem]
0x18002f7a9  mov     [rsp+100h+pvStructInfo], rcx; pvStructInfo
0x18002f7ae  lea     rcx, PkiDecodePara
0x18002f7b5  mov     r8, [r8+rax]; pbEncoded
0x18002f7b9  mov     [rsp+100h+pDecodePara], rcx; void *
0x18002f7be  mov     ecx, r11d; dwCertEncodingType
0x18002f7c1  mov     [rsp+100h+var_E0], 800Dh; unsigned int
0x18002f7c9  call    CryptDecodeObjectEx
0x18002f7ce  test    eax, eax
0x18002f7d0  jz      loc_18002FA96
0x18002f7d6  mov     rax, [rbp+37h+hMem]
0x18002f7da  mov     r8d, 40000004h; dwGroupId
0x18002f7e0  mov     ecx, r12d; dwKeyType
0x18002f7e3  mov     [rbp+37h+var_98], r14d
0x18002f7e7  mov     rsi, [rax+10h]
0x18002f7eb  mov     rdx, rsi; pvKey
0x18002f7ee  call    CryptFindOIDInfo
0x18002f7f3  mov     ebx, [rbp+37h+dwIssuerType]
0x18002f7f6  mov     rdi, rax
0x18002f7f9  test    rax, rax
0x18002f7fc  jz      loc_18002FCD5
0x18002f802  mov     eax, [rax+20h]
0x18002f805  mov     r14d, [rdi+1Ch]
0x18002f809  shr     eax, 2
0x18002f80c  cmp     eax, r12d
0x18002f80f  jb      loc_18002FA52
0x18002f815  mov     rcx, [rdi+28h]
0x18002f819  mov     edx, [rcx]
0x18002f81b  mov     [rbp+37h+dwFlags], edx
0x18002f81e  cmp     eax, 2
0x18002f821  jnb     loc_18002FCB0
0x18002f827  xor     r8d, r8d
0x18002f82a  mov     esi, r8d
0x18002f82d  mov     eax, 2000h
0x18002f832  cmp     edx, eax
0x18002f834  jz      loc_18002FD15
0x18002f83a  mov     rcx, r8
0x18002f83d  mov     [rbp+37h+pCertContext], rcx
0x18002f841  sub     ebx, r12d
0x18002f844  jz      loc_18002FA70
0x18002f84a  sub     ebx, r12d
0x18002f84d  jnz     loc_18002FA79
0x18002f853  mov     rcx, [rbp+37h+pvIssuer]; pCertContext
0x18002f857  mov     rbx, [rcx+18h]
0x18002f85b  add     rbx, 60h ; '`'
0x18002f85f  mov     [rbp+37h+pCertContext], rcx
0x18002f863  cmp     [rbx+8], r8d
0x18002f867  jz      short loc_18002F872
0x18002f869  mov     rax, [rbx+10h]
0x18002f86d  cmp     byte ptr [rax], 5
0x18002f870  jnz     short loc_18002F892
0x18002f872  mov     [rbp+37h+pcbData], r8d
0x18002f876  lea     r9, [rbp+37h+pcbData]; pcbData
0x18002f87a  xor     r8d, r8d; pvData
0x18002f87d  lea     edx, [r8+16h]; dwPropId
0x18002f881  call    CertGetCertificateContextProperty
0x18002f886  test    eax, eax
0x18002f888  jnz     loc_180116F0E
0x18002f88e  mov     rcx, [rbp+37h+pCertContext]
0x18002f892  test    r15d, r15d
0x18002f895  jnz     loc_18002FBE8
0x18002f89b  cmp     r14d, 0FFFFFFFDh
0x18002f89f  jb      loc_18002FB2D
0x18002f8a5  mov     r9, [rbp+37h+hMem]; struct _CERT_SIGNED_CONTENT_INFO *
0x18002f8a9  mov     r8, rbx; struct _CERT_PUBLIC_KEY_INFO *
0x18002f8ac  mov     edx, [rbp+37h+dwCertEncodingType]; unsigned int
0x18002f8af  mov     rcx, rdi; struct _CRYPT_OID_INFO *
0x18002f8b2  call    ?I_CryptCNGVerifyCertificateSignedContent@@YAHPEBU_CRYPT_OID_INFO@@KPEAU_CERT_PUBLIC_KEY_INFO@@PEAU_CERT_SIGNED_CONTENT_INFO@@KPEAX@Z; I_CryptCNGVerifyCertificateSignedContent(_CRYPT_OID_INFO const *,ulong,_CERT_PUBLIC_KEY_INFO *,_CERT_SIGNED_CONTENT_INFO *,ulong,void *)
0x18002f8b7  test    eax, eax
0x18002f8b9  jz      loc_18002FA96
0x18002f8bf  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18002f8c3  test    rbx, rbx
0x18002f8c6  jz      short loc_18002F8E1
0x18002f8c8  cmp     [rbp+37h+arg_10], 2
0x18002f8cc  jnz     short loc_18002F8E1
0x18002f8ce  cmp     dword ptr [rbx+8], 0
0x18002f8d2  jz      short loc_18002F8E1
0x18002f8d4  mov     rax, [rbx+10h]
0x18002f8d8  cmp     byte ptr [rax], 5
0x18002f8db  jnz     loc_18002FB7B
0x18002f8e1  mov     ebx, dword ptr [rbp+37h+pvKey]
0x18002f8e4  test    ebx, ebx
0x18002f8e6  jz      loc_18002FA60
0x18002f8ec  cmp     r14d, 0FFFFFFFEh
0x18002f8f0  jz      loc_18002FDE6
0x18002f8f6  test    ebx, ebx
0x18002f8f8  jz      short loc_18002F90A
0x18002f8fa  lea     eax, [r14-8001h]
0x18002f901  cmp     eax, r12d
0x18002f904  jbe     loc_18002FE1F
0x18002f90a  mov     r14, [rbp+37h+var_80]
0x18002f90e  xor     ebx, ebx
0x18002f910  test    r14, r14
0x18002f913  jz      short loc_18002F958
0x18002f915  test    rdi, rdi
0x18002f918  jz      short loc_18002F958
0x18002f91a  cmp     [r14], ebx
0x18002f91d  jbe     short loc_18002F954
0x18002f91f  mov     rax, [r14+8]
0x18002f923  mov     r9d, esi; cchCount1
0x18002f926  mov     r8, [rdi+30h]; lpString1
0x18002f92a  mov     edx, r12d; dwCmpFlags
0x18002f92d  mov     ecx, ebx
0x18002f92f  mov     dword ptr [rsp+100h+pDecodePara], esi; cchCount2
0x18002f933  mov     rax, [rax+rcx*8]
0x18002f937  mov     ecx, 409h; Locale
0x18002f93c  mov     qword ptr [rsp+100h+var_E0], rax; lpString2
0x18002f941  call    cs:__imp_CompareStringW
0x18002f947  cmp     eax, 2
0x18002f94a  jz      short loc_18002F954
0x18002f94c  add     ebx, r12d
0x18002f94f  cmp     ebx, [r14]
0x18002f952  jb      short loc_18002F91F
0x18002f954  mov     [r14+10h], ebx
0x18002f958  xor     edi, edi
0x18002f95a  test    r15d, r15d
0x18002f95d  jz      short loc_18002F9D9
0x18002f95f  mov     rdx, [rbp+37h+hMem]
0x18002f963  mov     r14d, edi
0x18002f966  mov     ecx, [rbp+37h+dwCertEncodingType]; dwCertEncodingType
0x18002f969  add     rdx, 10h; struct _CRYPT_ALGORITHM_IDENTIFIER *
0x18002f96d  mov     [rbp+37h+dwFlags], edi
0x18002f970  mov     [rbp+37h+var_98], 4
0x18002f977  call    ?I_CryptCNGGetSignHashAlgidFromSignatureAlgorithm@@YAPEAGKPEAU_CRYPT_ALGORITHM_IDENTIFIER@@@Z; I_CryptCNGGetSignHashAlgidFromSignatureAlgorithm(ulong,_CRYPT_ALGORITHM_IDENTIFIER *)
0x18002f97c  mov     r15, rax
0x18002f97f  test    rax, rax
0x18002f982  jz      short loc_18002F99D
0x18002f984  inc     rsi
0x18002f987  cmp     [rax+rsi*2], di
0x18002f98b  jnz     short loc_18002F984
0x18002f98d  lea     eax, [rsi+1]
0x18002f990  movsxd  rdx, eax
0x18002f993  cmp     rdx, 42h ; 'B'
0x18002f997  ja      short loc_18002F99D
0x18002f999  lea     r14, [rdx+rdx]
0x18002f99d  mov     rcx, [rbp+37h+pCertContext]; pCertContext
0x18002f9a1  lea     r9, [rbp+37h+var_98]; pcbData
0x18002f9a5  lea     r8, [rbp+37h+dwFlags]; pvData
0x18002f9a9  mov     edx, 5Ch ; '\'; dwPropId
0x18002f9ae  call    CertGetCertificateContextProperty
0x18002f9b3  test    eax, eax
0x18002f9b5  jz      loc_18002FE32
0x18002f9bb  cmp     [rbp+37h+var_98], 4
0x18002f9bf  jnz     loc_18002FE32
0x18002f9c5  mov     eax, [rbp+37h+dwFlags]
0x18002f9c8  test    r14, r14
0x18002f9cb  jnz     loc_18002FAA9
0x18002f9d1  mov     rcx, r15; hMem
0x18002f9d4  call    PkiDefaultCryptFree
0x18002f9d9  mov     rdi, [rbp+37h+hMem]
0x18002f9dd  test    rdi, rdi
0x18002f9e0  jz      short loc_18002F9FB
0x18002f9e2  call    cs:__imp_GetLastError
0x18002f9e8  mov     rcx, rdi; hMem
0x18002f9eb  mov     ebx, eax
0x18002f9ed  call    cs:__imp_LocalFree
0x18002f9f3  mov     ecx, ebx; dwErrCode
0x18002f9f5  call    cs:__imp_SetLastError
0x18002f9fb  mov     rdi, [rbp+37h+var_70]
0x18002f9ff  test    rdi, rdi
0x18002fa02  jz      short loc_18002FA1D
0x18002fa04  call    cs:__imp_GetLastError
0x18002fa0a  mov     rcx, rdi; hMem
0x18002fa0d  mov     ebx, eax
0x18002fa0f  call    cs:__imp_LocalFree
0x18002fa15  mov     ecx, ebx; dwErrCode
0x18002fa17  call    cs:__imp_SetLastError
0x18002fa1d  mov     rbx, [rsp+100h+arg_18]
0x18002fa25  mov     eax, r12d
0x18002fa28  add     rsp, 0D0h
0x18002fa2f  pop     r15
0x18002fa31  pop     r14
0x18002fa33  pop     r13
0x18002fa35  pop     r12
0x18002fa37  pop     rdi
0x18002fa38  pop     rsi
0x18002fa39  pop     rbp
0x18002fa3a  retn
0x18002fa3b  mov     rcx, [rbp+37h+pvExtra]
0x18002fa3f  test    rcx, rcx
0x18002fa42  jz      short loc_18002FA8B
0x18002fa44  mov     eax, [rcx]
0x18002fa46  mov     [rcx+10h], eax
0x18002fa49  mov     [rbp+37h+var_80], rcx
0x18002fa4d  jmp     loc_18002F773
0x18002fa52  xor     r8d, r8d
0x18002fa55  mov     edx, r8d
0x18002fa58  mov     [rbp+37h+dwFlags], edx
0x18002fa5b  jmp     loc_18002F82A
0x18002fa60  cmp     [rbp+37h+var_80], 0
0x18002fa65  jz      loc_18002F958
0x18002fa6b  jmp     loc_18002F8EC
0x18002fa70  mov     rbx, [rbp+37h+pvIssuer]
0x18002fa74  jmp     loc_18002F892
0x18002fa79  sub     ebx, r12d
0x18002fa7c  jz      loc_18002FDCB
0x18002fa82  cmp     ebx, r12d
0x18002fa85  jz      loc_18002FDBB
0x18002fa8b  mov     ecx, 80070057h; dwErrCode
0x18002fa90  call    cs:__imp_SetLastError
0x18002fa96  xor     edi, edi
0x18002fa98  cmp     dword ptr [rbp+37h+pvKey], edi
0x18002fa9b  jnz     loc_18002FE3C
0x18002faa1  mov     r12d, edi
0x18002faa4  jmp     loc_18002F9D9
0x18002faa9  test    eax, eax
0x18002faab  jz      loc_18002F9D1
0x18002fab1  mov     eax, [rbp+37h+arg_10]
0x18002fab4  cmp     eax, 3
0x18002fab7  jz      loc_18002FC33
0x18002fabd  cmp     eax, 4
0x18002fac0  jnz     loc_18002F9D1
0x18002fac6  mov     r13, [rbp+37h+pvExtra]
0x18002faca  test    r13, r13
0x18002facd  jz      loc_18002F9D1
0x18002fad3  lea     rbx, [r14+24h]
0x18002fad7  mov     ecx, ebx; uBytes
0x18002fad9  call    PkiAlloc
0x18002fade  mov     rsi, rax
0x18002fae1  test    rax, rax
0x18002fae4  jz      loc_18002F9D1
0x18002faea  mov     r8, rbx; Size
0x18002faed  xor     edx, edx; Val
0x18002faef  mov     rcx, rax; void *
0x18002faf2  call    memset_0
0x18002faf7  mov     ecx, [rbp+37h+dwFlags]
0x18002fafa  lea     rdi, [rsi+20h]
0x18002fafe  mov     [rdi], ecx
0x18002fb00  lea     rbx, [rdi+4]
0x18002fb04  mov     rcx, rbx; void *
0x18002fb07  mov     r8, r14; Size
0x18002fb0a  mov     rdx, r15; Src
0x18002fb0d  call    memcpy_0
0x18002fb12  mov     [rsi+8], rbx
0x18002fb16  mov     [rsi], r14d
0x18002fb19  mov     [rsi+18h], rdi
0x18002fb1d  mov     dword ptr [rsi+10h], 4
0x18002fb24  mov     [r13+0], rsi
0x18002fb28  jmp     loc_18002F9D1
0x18002fb2d  mov     rax, [rbp+37h+hMem]
0x18002fb31  mov     r9d, esi; unsigned int
0x18002fb34  mov     r8d, [rbp+37h+var_98]; unsigned int
0x18002fb38  mov     ecx, r14d; Algid
0x18002fb3b  mov     edx, [rbp+37h+dwFlags]; unsigned int
0x18002fb3e  mov     [rsp+38h], rax; struct _CERT_SIGNED_CONTENT_INFO *
0x18002fb43  mov     eax, [rbp+37h+dwCertEncodingType]
0x18002fb46  mov     [rsp+100h+pvStructInfo], rbx; struct _CERT_PUBLIC_KEY_INFO *
0x18002fb4b  mov     dword ptr [rsp+100h+pDecodePara], eax; unsigned int
0x18002fb4f  mov     rax, [rbp+37h+hCryptProv]
  ... truncated ...
```
