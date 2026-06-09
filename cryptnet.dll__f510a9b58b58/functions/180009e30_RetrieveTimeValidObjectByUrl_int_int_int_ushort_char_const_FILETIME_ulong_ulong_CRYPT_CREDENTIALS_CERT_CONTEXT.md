# RetrieveTimeValidObjectByUrl(int,int,int,ushort *,char const *,_FILETIME *,ulong,ulong,_CRYPT_CREDENTIALS *,_CERT_CONTEXT const *,void *,uchar * const,void * *,_CRYPT_GET_TIME_VALID_OBJECT_EXTRA_INFO *)

- ea: `0x180009e30`
- end: `0x18000a987`
- name: `?RetrieveTimeValidObjectByUrl@@YAHHHHPEAGPEBDPEAU_FILETIME@@KKPEAU_CRYPT_CREDENTIALS@@PEBU_CERT_CONTEXT@@PEAXQEAEPEAPEAXPEAU_CRYPT_GET_TIME_VALID_OBJECT_EXTRA_INFO@@@Z`
- size: `2903`
- prototype: `__int64 __fastcall(int, int, int, unsigned __int16 *, char *, struct _FILETIME *, unsigned int, unsigned int, struct _CRYPT_CREDENTIALS *, struct _CERT_CONTEXT *, CERT_CONTEXT *pCertContext, unsigned __int8 *const Buf2, void **, struct _CRYPT_GET_TIME_VALID_OBJECT_EXTRA_INFO *)`
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x180008f80`

## callees

- `0x180007a40`
- `0x180009e30`
- `0x18000a990`
- `0x18000a9d0`
- `0x18000c300`
- `0x18000c620`
- `0x18000cef0`
- `0x1800170e0`
- `0x180017ed0`
- `0x18001802c`
- `0x180026552`
- `0x18002656a`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180009f0b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000a053`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000a078`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000a405`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000a47e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000a571`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000a5f3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000a831`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000a927`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000a934`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180009f0b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000a053`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000a078`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000a405`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000a47e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000a571`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000a5f3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000a831`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000a927`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000a934`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a040`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a065`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a3f2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a414`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a435`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a5d3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a81e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a040`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a065`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a3f2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a414`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a435`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a5d3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a81e`
- `CRYPT32!I_CertDiagControl` at `0x18000a5b1`
- `CRYPT32!I_CertDiagControl` at `0x18000a5b1`
- `CRYPT32!CryptEncodeObjectEx` at `0x18000a7b2`
- `CRYPT32!CryptEncodeObjectEx` at `0x18000a802`
- `CRYPT32!CryptEncodeObjectEx` at `0x18000a7b2`
- `CRYPT32!CryptEncodeObjectEx` at `0x18000a802`
- `CRYPT32!CryptBinaryToStringW` at `0x18000a858`
- `CRYPT32!CryptBinaryToStringW` at `0x18000a899`
- `CRYPT32!CryptBinaryToStringW` at `0x18000a858`
- `CRYPT32!CryptBinaryToStringW` at `0x18000a899`
- `CRYPT32!CryptHashCertificate` at `0x18000a69e`
- `CRYPT32!CryptHashCertificate` at `0x18000a6e7`
- `CRYPT32!CryptHashCertificate` at `0x18000a69e`
- `CRYPT32!CryptHashCertificate` at `0x18000a6e7`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18000a0dd`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18000a0dd`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180009ef0`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180009fb4`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000a86e`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180009ef0`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180009fb4`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000a86e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000a04b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000a070`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000a3fd`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000a41f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000a829`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000a04b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000a070`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000a3fd`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000a41f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000a829`
- `ntdll!iswalnum` at `0x180009f6a`
- `ntdll!iswalnum` at `0x18000a00b`
- `ntdll!iswalnum` at `0x180009f6a`
- `ntdll!iswalnum` at `0x18000a00b`

## pseudocode

```c
__int64 __fastcall RetrieveTimeValidObjectByUrl(
        int a1,
        int a2,
        int a3,
        unsigned __int16 *a4,
        char *a5,
        struct _FILETIME *a6,
        unsigned int a7,
        unsigned int a8,
        struct _CRYPT_CREDENTIALS *a9,
        struct _CERT_CONTEXT *a10,
        CERT_CONTEXT *pCertContext,
        unsigned __int8 *const Buf2,
        void **a13,
        struct _CRYPT_GET_TIME_VALID_OBJECT_EXTRA_INFO *a14)
{
  unsigned int v14; // r14d
  int v15; // r11d
  FILETIME *v16; // rdx
  unsigned __int16 *v17; // r15
  int v18; // r10d
  WCHAR *lpString2; // r12
  unsigned int cbData; // eax
  char *v21; // rax
  char *v22; // r14
  DWORD v23; // ecx
  wint_t v25; // di
  wint_t *v26; // rsi
  unsigned int v27; // ebx
  wint_t *v28; // r14
  __int64 v29; // rdi
  size_t v30; // rdi
  unsigned int v31; // r14d
  WCHAR *v32; // rsi
  wint_t *v33; // r15
  wint_t v34; // di
  DWORD v35; // ebx
  DWORD v36; // ecx
  HLOCAL v37; // rdi
  DWORD v38; // ebx
  unsigned __int64 v39; // r9
  const WCHAR *v40; // rcx
  unsigned __int64 cchCount2; // rcx
  WCHAR *v42; // rdx
  unsigned int v43; // esi
  DWORD v44; // eax
  unsigned int v45; // ebx
  const unsigned __int16 *v46; // r14
  unsigned __int16 *v47; // r12
  unsigned __int16 *OcspCacheFileNamePrefix; // rax
  struct _CRYPT_GET_TIME_VALID_OBJECT_EXTRA_INFO *v49; // r15
  unsigned int v50; // edi
  int v51; // r14d
  __int16 v52; // ax
  unsigned int v53; // ecx
  unsigned int v54; // edx
  __int16 v55; // ax
  __int16 v56; // ax
  unsigned int v57; // ecx
  unsigned int v58; // edx
  __int16 v59; // ax
  int OriginUrlStatusW; // ebx
  int v61; // r14d
  unsigned int v62; // r15d
  bool v63; // zf
  FILETIME *v64; // rsi
  int v65; // eax
  unsigned __int16 *v66; // rcx
  unsigned int v67; // eax
  HLOCAL v68; // rdi
  DWORD v69; // ebx
  DWORD v70; // ebx
  DWORD v71; // r14d
  unsigned __int16 *v72; // rax
  DWORD v73; // ebx
  const char *v74; // rdx
  _BYTE *v75; // r8
  __int64 v76; // rcx
  __int64 v77; // r9
  _BYTE *v78; // rax
  DWORD v79; // edx
  __int128 v80; // xmm0
  __int128 v81; // xmm1
  __int128 v82; // xmm0
  __int128 v83; // xmm1
  BOOL v84; // esi
  unsigned __int16 *v85; // rdi
  DWORD LastError; // ebx
  WCHAR *v87; // r13
  WCHAR *v88; // r8
  WCHAR *v89; // rdx
  WCHAR v90; // cx
  char *v91; // r10
  struct _CRYPT_CREDENTIALS *pcbComputedHash; // [rsp+30h] [rbp-D0h]
  void **v93; // [rsp+40h] [rbp-C0h]
  struct _CRYPT_GET_TIME_VALID_OBJECT_EXTRA_INFO *v94; // [rsp+50h] [rbp-B0h]
  struct _CRYPT_GET_TIME_VALID_OBJECT_EXTRA_INFO *v95; // [rsp+68h] [rbp-98h]
  unsigned int v96; // [rsp+70h] [rbp-90h]
  DWORD pcbEncoded; // [rsp+74h] [rbp-8Ch] BYREF
  int v98; // [rsp+78h] [rbp-88h]
  unsigned __int16 *pvEncoded; // [rsp+80h] [rbp-80h] BYREF
  DWORD pcchString; // [rsp+88h] [rbp-78h] BYREF
  DWORD cbBinary; // [rsp+8Ch] [rbp-74h] BYREF
  PCNZWCH v102; // [rsp+90h] [rbp-70h]
  void *v103; // [rsp+98h] [rbp-68h] BYREF
  struct _FILETIME v104; // [rsp+A0h] [rbp-60h] BYREF
  HLOCAL hMem; // [rsp+A8h] [rbp-58h] BYREF
  FILETIME *lpFileTime1; // [rsp+B0h] [rbp-50h]
  HLOCAL v107; // [rsp+B8h] [rbp-48h]
  __int128 v108; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v109; // [rsp+D0h] [rbp-30h]
  struct _FILETIME *v110; // [rsp+D8h] [rbp-28h]
  unsigned __int16 *v111; // [rsp+E0h] [rbp-20h]
  __int64 v112; // [rsp+E8h] [rbp-18h]
  _QWORD pvStructInfo[4]; // [rsp+F0h] [rbp-10h] BYREF
  __int128 v114; // [rsp+110h] [rbp+10h]
  _OWORD v115[4]; // [rsp+120h] [rbp+20h] BYREF
  __int64 v116; // [rsp+160h] [rbp+60h]
  int v117; // [rsp+1D0h] [rbp+D0h]
  unsigned __int16 *Src; // [rsp+1E8h] [rbp+E8h]
  int v121; // [rsp+210h] [rbp+110h]
  unsigned int v122; // [rsp+210h] [rbp+110h]

  Src = a4;
  v117 = a1;
  v14 = a7;
  v96 = 0;
  v15 = a2;
  v103 = 0;
  v16 = 0;
  v107 = 0;
  if ( (a7 & 0x200) == 0 )
    v16 = a6;
  v17 = a4;
  lpFileTime1 = v16;
  v18 = a3;
  v102 = 0;
  lpString2 = 0;
  if ( (a7 & 0x100) != 0 )
  {
    v98 = 0;
    v121 = 8;
  }
  else
  {
    v98 = 32;
    v121 = 0;
  }
  if ( a1 )
  {
    cbData = pCertContext->pCertInfo->SerialNumber.cbData;
    if ( cbData > 0xFFFFFF )
    {
      v23 = 534;
      goto LABEL_9;
    }
    v21 = (char *)LocalAlloc(0x40u, cbData + 126);
    v107 = v21;
    v22 = v21;
    if ( !v21 )
    {
      v23 = -2147024882;
      goto LABEL_9;
    }
    v91 = v21 + 72;
    v76 = 2147483646;
    v75 = v21 + 72;
    v74 = "1.3.14.3.2.26";
    v77 = 14;
    do
    {
      if ( !v76 )
        break;
      if ( !*v74 )
        break;
      *v75++ = *v74++;
      --v76;
      --v77;
    }
    while ( v77 );
    v78 = v75 - 1;
    if ( v77 )
      v78 = v75;
    *v78 = 0;
    *((_QWORD *)v22 + 4) = v91 + 14;
    *(_QWORD *)v22 = v91;
    *((_DWORD *)v22 + 6) = 20;
    *((_QWORD *)v22 + 6) = v91 + 34;
    *((_DWORD *)v22 + 10) = 20;
    *((_QWORD *)v22 + 8) = v91 + 54;
    v79 = pCertContext->pCertInfo->SerialNumber.cbData;
    *((_DWORD *)v22 + 14) = v79;
    memcpy_0(v91 + 54, pCertContext->pCertInfo->SerialNumber.pbData, v79);
    if ( !CryptHashCertificate(
            0,
            0x8004u,
            0,
            pCertContext->pCertInfo->Issuer.pbData,
            pCertContext->pCertInfo->Issuer.cbData,
            *((BYTE **)v22 + 4),
            (DWORD *)v22 + 6)
      || !CryptHashCertificate(
            0,
            0x8004u,
            0,
            a10->pCertInfo->SubjectPublicKeyInfo.PublicKey.pbData,
            a10->pCertInfo->SubjectPublicKeyInfo.PublicKey.cbData,
            *((BYTE **)v22 + 6),
            (DWORD *)v22 + 10) )
    {
      operator delete(v22);
      goto LABEL_10;
    }
    if ( !v22 )
      goto LABEL_80;
    v102 = 0;
    hMem = 0;
    v109 = 0;
    cbBinary = 0;
    pcchString = 0;
    v108 = 0;
    pvEncoded = 0;
    pcbEncoded = 0;
    memset_0(v115, 0, 0x58u);
    v80 = *(_OWORD *)v22;
    v81 = *((_OWORD *)v22 + 1);
    pvStructInfo[3] = v115;
    v115[0] = v80;
    v82 = *((_OWORD *)v22 + 2);
    v115[1] = v81;
    v83 = *((_OWORD *)v22 + 3);
    v115[2] = v82;
    v116 = *((_QWORD *)v22 + 8);
    v114 = 0;
    pvStructInfo[0] = 0;
    v115[3] = v83;
    pvStructInfo[1] = 0;
    pvStructInfo[2] = 1;
    v84 = 0;
    if ( CryptEncodeObjectEx(0x10001u, (LPCSTR)0x42, pvStructInfo, 0x8000u, &PkiEncodePara, &pvEncoded, &pcbEncoded) )
    {
      *((_QWORD *)&v108 + 1) = pvEncoded;
      *(_QWORD *)&v108 = pcbEncoded;
      v109 = 0;
      if ( CryptEncodeObjectEx(0x10001u, (LPCSTR)0x41, &v108, 0x8000u, &PkiEncodePara, &hMem, &cbBinary) )
        v84 = 1;
    }
    v85 = pvEncoded;
    if ( pvEncoded )
    {
      LastError = GetLastError();
      LocalFree(v85);
      SetLastError(LastError);
    }
    if ( !v84 || !CryptBinaryToStringW((const BYTE *)hMem, cbBinary, 0x80000001, 0, &pcchString) )
    {
LABEL_29:
      v37 = hMem;
      if ( hMem )
      {
        v38 = GetLastError();
        LocalFree(v37);
        SetLastError(v38);
      }
      if ( lpString2 )
      {
        v39 = 0;
        v40 = L"post";
        do
        {
          if ( !*v40 )
            break;
          ++v39;
          ++v40;
        }
        while ( v39 < 4 );
        cchCount2 = 0;
        v42 = lpString2;
        do
        {
          if ( !*v42 )
            break;
          ++cchCount2;
          ++v42;
        }
        while ( cchCount2 < 4 );
        if ( CompareStringW(0x409u, 1u, L"post", v39, lpString2, cchCount2) == 2 )
        {
          v98 |= 0x100000u;
          *(_DWORD *)lpString2 = 7602280;
          *((_DWORD *)lpString2 + 1) = 7340148;
        }
        v14 = a7;
        v17 = lpString2;
        a1 = v117;
        v16 = lpFileTime1;
        v18 = a3;
        v15 = a2;
        Src = lpString2;
        goto LABEL_41;
      }
LABEL_80:
      v68 = v107;
      if ( v107 )
      {
        v69 = GetLastError();
        LocalFree(v68);
        SetLastError(v69);
      }
      if ( !lpString2 )
        goto LABEL_10;
      v70 = GetLastError();
      LocalFree(lpString2);
      v23 = v70;
LABEL_9:
      SetLastError(v23);
      goto LABEL_10;
    }
    v87 = (WCHAR *)LocalAlloc(0, 2LL * pcchString);
    if ( !v87 )
    {
      v36 = -2147024882;
      goto LABEL_28;
    }
    if ( CryptBinaryToStringW((const BYTE *)hMem, cbBinary, 0x80000001, v87, &pcchString) )
    {
      v88 = v87;
      v89 = v87;
      do
      {
        v90 = *v88++;
        if ( v90 != 10 )
          *v89++ = v90;
      }
      while ( v90 );
      v28 = 0;
      v26 = v87;
      v27 = 0;
      do
      {
        while ( 1 )
        {
          v25 = *v26++;
          if ( iswalnum(v25) || !v25 )
            break;
          v27 += 3;
          if ( !v27 )
          {
            *v28 = 37;
            v52 = 48;
            v53 = (unsigned __int8)v25 >> 4;
            if ( v53 > 9 )
              v52 = 55;
            v54 = v25 & 0xF;
            v28[1] = v53 + v52;
            v55 = 48;
            if ( v54 > 9 )
              v55 = 55;
            v28[2] = v54 + v55;
            v28 += 3;
          }
        }
        if ( !++v27 )
          *v28++ = v25;
      }
      while ( v25 );
      if ( v17 )
      {
        v29 = -1;
        do
          ++v29;
        while ( v17[v29] );
      }
      else
      {
        LODWORD(v29) = 0;
      }
      v102 = (PCNZWCH)LocalAlloc(0, 2LL * (v27 + (_DWORD)v29 + 2));
      lpString2 = (WCHAR *)v102;
      if ( v102 )
      {
        v30 = (unsigned int)v29;
        memcpy_0((void *)v102, v17, v30 * 2);
        lpString2[v30] = 47;
        v31 = 0;
        v32 = &lpString2[v30 + 1];
        v33 = v87;
        if ( !v32 )
          v27 = 0;
        do
        {
          while ( 1 )
          {
            v34 = *v33++;
            if ( iswalnum(v34) || !v34 )
              break;
            v31 += 3;
            if ( v31 <= v27 )
            {
              *v32 = 37;
              v56 = 48;
              v57 = (unsigned __int8)v34 >> 4;
              if ( v57 > 9 )
                v56 = 55;
              v58 = v34 & 0xF;
              v32[1] = v57 + v56;
              v59 = 48;
              if ( v58 > 9 )
                v59 = 55;
              v32[2] = v58 + v59;
              v32 += 3;
            }
          }
          if ( ++v31 <= v27 )
            *v32++ = v34;
        }
        while ( v34 );
        lpString2 = (WCHAR *)v102;
        if ( !v27 || v27 >= v31 )
          goto LABEL_27;
        SetLastError(0xEAu);
        operator delete(lpString2);
        lpString2 = 0;
      }
      else
      {
        SetLastError(0x8007000E);
      }
      v102 = 0;
    }
LABEL_27:
    v35 = GetLastError();
    LocalFree(v87);
    v36 = v35;
LABEL_28:
    SetLastError(v36);
    goto LABEL_29;
  }
LABEL_41:
  v43 = v14 & 0x400;
  if ( (v14 & 4) != 0 )
  {
    v49 = a14;
    goto LABEL_64;
  }
  v44 = 0;
  v45 = v98 | 2;
  if ( !a1 )
  {
    v49 = a14;
    LOBYTE(v44) = v43 != 0;
    v67 = RetrieveObjectByUrlValidForSubject(
            v15,
            v18,
            Src,
            a5,
            v44,
            v16,
            v98 | 2u,
            0,
            (struct _CRYPT_CREDENTIALS *)v93,
            a10,
            pCertContext,
            Buf2,
            &v103,
            a14);
    v96 = v67;
    goto LABEL_77;
  }
  v46 = v17;
  v104 = (struct _FILETIME)v17;
  LOBYTE(v44) = v43 != 0;
  v47 = 0;
  pcbEncoded = v44;
  v96 = 0;
  OcspCacheFileNamePrefix = CertificateGetOcspCacheFileNamePrefix(pCertContext);
  v49 = a14;
  v50 = 0;
  pvEncoded = OcspCacheFileNamePrefix;
  while ( v50 <= 1 )
  {
    if ( !v50 && (v45 & 0x100000) != 0 )
    {
      v51 = 0;
      SetLastError(2u);
      goto LABEL_84;
    }
    v51 = I_RetrieveObjectByOcspUrlValidForSubject(
            (const struct _OCSP_CERT_ID *)v107,
            v46,
            pcbEncoded,
            lpFileTime1,
            v45,
            0,
            a10,
            pCertContext,
            &v103,
            a14,
            OcspCacheFileNamePrefix);
    if ( v51 > 0 )
    {
      v96 = 1;
LABEL_72:
      OcspCacheFileNamePrefix = pvEncoded;
      break;
    }
    if ( v50 )
    {
      v46 = (const unsigned __int16 *)v104;
      ++v50;
      OcspCacheFileNamePrefix = pvEncoded;
    }
    else
    {
LABEL_84:
      if ( (v45 & 4) != 0 && v51 < 0 )
        goto LABEL_72;
      v71 = GetLastError();
      v72 = OcspFormatPostRequest(Src);
      v47 = v72;
      if ( !v72 )
      {
        SetLastError(v71);
        v66 = pvEncoded;
        goto LABEL_75;
      }
      v45 |= 0x100000u;
      v104 = (struct _FILETIME)v72;
      v46 = v72;
      ++v50;
      OcspCacheFileNamePrefix = pvEncoded;
    }
  }
  operator delete(OcspCacheFileNamePrefix);
  if ( !v47 )
    goto LABEL_76;
  v66 = v47;
LABEL_75:
  operator delete(v66);
LABEL_76:
  v67 = v96;
  v14 = a7;
LABEL_77:
  if ( !v67 )
  {
LABEL_64:
    if ( (v14 & 2) == 0 )
    {
      v122 = v98 | v121 | 4;
      v104 = 0;
      OriginUrlStatusW = GetOriginUrlStatusW(Buf2, Src, a5, v122, &v104);
      if ( OriginUrlStatusW < 0 )
      {
        v111 = Src;
        *(_QWORD *)&v108 = 0;
        *((_QWORD *)&v108 + 1) = L"CanRetrieveFromNetwork";
        v109 = 0;
        v112 = 0;
        v110 = &v104;
        I_CertDiagControl(5, &v108, 0);
      }
      else
      {
        v61 = v14 & 0x1000000;
        if ( v117 )
        {
          if ( v61 )
          {
            v122 |= 0x1000008u;
            v43 = a7 & 0x400;
          }
          v94 = v49;
          v62 = v122;
          v63 = v43 == 0;
          v64 = lpFileTime1;
          v65 = RetrieveObjectByOcspUrlValidForSubject(
                  (const struct _OCSP_CERT_ID *)v107,
                  Src,
                  !v63,
                  lpFileTime1,
                  v122,
                  a8,
                  pcbComputedHash,
                  a10,
                  pCertContext,
                  &v103,
                  v94);
        }
        else
        {
          v95 = v49;
          v62 = v122;
          v63 = v43 == 0;
          v64 = lpFileTime1;
          v65 = RetrieveObjectByUrlValidForSubject(
                  a2,
                  a3,
                  Src,
                  a5,
                  !v63,
                  lpFileTime1,
                  v122,
                  a8,
                  (struct _CRYPT_CREDENTIALS *)v93,
                  a10,
                  pCertContext,
                  Buf2,
                  &v103,
                  v95);
        }
        v96 = v65;
        if ( v65 )
        {
          if ( !OriginUrlStatusW )
            SetOnlineOriginUrlW(Buf2, Src, a5, v62);
        }
        else if ( !v61 )
        {
          v73 = GetLastError();
          SetOfflineOriginUrlW(Buf2, Src, a5, v62, v64);
          SetLastError(v73);
        }
      }
    }
  }
  if ( v117 )
  {
    lpString2 = (WCHAR *)v102;
    goto LABEL_80;
  }
LABEL_10:
  *a13 = v103;
  return v96;
}

```

## disassembly

```asm
0x180009e30  mov     [rsp-8+Src], r9
0x180009e35  mov     [rsp-8+arg_10], r8d
0x180009e3a  mov     [rsp-8+arg_8], edx
0x180009e3e  mov     [rsp-8+arg_0], ecx
0x180009e42  push    rbp
0x180009e43  push    r12
0x180009e45  push    r13
0x180009e47  push    r14
0x180009e49  push    r15
0x180009e4b  lea     rbp, [rsp-0A0h]
0x180009e53  sub     rsp, 1A0h
0x180009e5a  mov     r14d, [rbp+0C0h+arg_30]
0x180009e61  xor     r13d, r13d
0x180009e64  bt      r14d, 9
0x180009e69  mov     [rsp+1C0h+var_150], r13d
0x180009e6e  mov     r11d, edx
0x180009e71  mov     [rbp+0C0h+var_128], r13
0x180009e75  mov     edx, r13d
0x180009e78  mov     [rbp+0C0h+var_108], r13
0x180009e7c  cmovnb  rdx, [rbp+0C0h+arg_28]
0x180009e84  mov     r15, r9
0x180009e87  mov     [rbp+0C0h+lpFileTime1], rdx
0x180009e8b  mov     r10d, r8d
0x180009e8e  mov     [rbp+0C0h+var_130], r13
0x180009e92  mov     r12d, r13d
0x180009e95  bt      r14d, 8
0x180009e9a  jb      loc_18000A4F4
0x180009ea0  mov     [rsp+1C0h+var_148], 20h ; ' '
0x180009ea8  mov     dword ptr [rbp+0C0h+arg_40], r13d
0x180009eaf  mov     [rsp+1C0h+var_28], rbx
0x180009eb7  mov     [rsp+1C0h+var_30], rsi
0x180009ebf  mov     [rsp+1C0h+var_38], rdi
0x180009ec7  test    ecx, ecx
0x180009ec9  jz      loc_18000A115
0x180009ecf  mov     rsi, [rbp+0C0h+pCertContext]
0x180009ed6  mov     rax, [rsi+18h]
0x180009eda  mov     eax, [rax+8]
0x180009edd  cmp     eax, 0FFFFFFh
0x180009ee2  ja      loc_18000A8E1
0x180009ee8  lea     edx, [rax+7Eh]; uBytes
0x180009eeb  mov     ecx, 40h ; '@'; uFlags
0x180009ef0  call    cs:__imp_LocalAlloc
0x180009ef6  mov     [rbp+0C0h+var_108], rax
0x180009efa  mov     r14, rax
0x180009efd  test    rax, rax
0x180009f00  jnz     loc_18000A8EB
0x180009f06  mov     ecx, 8007000Eh; dwErrCode
0x180009f0b  call    cs:__imp_SetLastError
0x180009f11  mov     rax, [rbp+0C0h+var_128]
0x180009f15  mov     rcx, [rbp+0C0h+arg_60]
0x180009f1c  mov     rdi, [rsp+1C0h+var_38]
0x180009f24  mov     rsi, [rsp+1C0h+var_30]
0x180009f2c  mov     rbx, [rsp+1C0h+var_28]
0x180009f34  mov     [rcx], rax
0x180009f37  mov     eax, [rsp+1C0h+var_150]
0x180009f3b  add     rsp, 1A0h
0x180009f42  pop     r15
0x180009f44  pop     r14
0x180009f46  pop     r13
0x180009f48  pop     r12
0x180009f4a  pop     rbp
0x180009f4b  retn
0x180009f4c  xor     r14d, r14d
0x180009f4f  mov     rsi, r13
0x180009f52  xor     ebx, ebx
0x180009f54  mov     r12d, 37h ; '7'
0x180009f5a  nop     word ptr [rax+rax+00h]
0x180009f60  movzx   edi, word ptr [rsi]
0x180009f63  lea     rsi, [rsi+2]
0x180009f67  movzx   ecx, di; C
0x180009f6a  call    cs:__imp_iswalnum
0x180009f70  test    eax, eax
0x180009f72  jz      loc_18000A1EE
0x180009f78  add     ebx, 1
0x180009f7b  jnz     short loc_180009F85
0x180009f7d  mov     [r14], di
0x180009f81  add     r14, 2
0x180009f85  xor     eax, eax
0x180009f87  cmp     ax, di
0x180009f8a  jnz     short loc_180009F60
0x180009f8c  test    r15, r15
0x180009f8f  jz      loc_18000A91B
0x180009f95  mov     rdi, 0FFFFFFFFFFFFFFFFh
0x180009f9c  nop     dword ptr [rax+00h]
0x180009fa0  inc     rdi
0x180009fa3  cmp     [r15+rdi*2], ax
0x180009fa8  jnz     short loc_180009FA0
0x180009faa  lea     edx, [rdi+2]
0x180009fad  xor     ecx, ecx; uFlags
0x180009faf  add     edx, ebx
0x180009fb1  add     rdx, rdx; uBytes
0x180009fb4  call    cs:__imp_LocalAlloc
0x180009fba  mov     [rbp+0C0h+var_130], rax
0x180009fbe  mov     r12, rax
0x180009fc1  test    rax, rax
0x180009fc4  jz      loc_18000A922
0x180009fca  mov     eax, edi
0x180009fcc  mov     rdx, r15; Src
0x180009fcf  mov     rcx, r12; void *
0x180009fd2  lea     rdi, [rax+rax]
0x180009fd6  mov     r8, rdi; Size
0x180009fd9  call    memcpy_0
0x180009fde  xor     eax, eax
0x180009fe0  mov     word ptr [rdi+r12], 2Fh ; '/'
0x180009fe7  lea     rsi, [rdi+2]
0x180009feb  xor     r14d, r14d
0x180009fee  add     rsi, r12
0x180009ff1  mov     r15, r13
0x180009ff4  mov     r12d, 37h ; '7'
0x180009ffa  cmovz   ebx, eax
0x180009ffd  nop     dword ptr [rax]
0x18000a000  movzx   edi, word ptr [r15]
0x18000a004  lea     r15, [r15+2]
0x18000a008  movzx   ecx, di; C
0x18000a00b  call    cs:__imp_iswalnum
0x18000a011  test    eax, eax
0x18000a013  jz      loc_18000A248
0x18000a019  inc     r14d
0x18000a01c  cmp     r14d, ebx
0x18000a01f  ja      short loc_18000A028
0x18000a021  mov     [rsi], di
0x18000a024  add     rsi, 2
0x18000a028  xor     eax, eax
0x18000a02a  cmp     ax, di
0x18000a02d  jnz     short loc_18000A000
0x18000a02f  mov     r12, [rbp+0C0h+var_130]
0x18000a033  test    ebx, ebx
0x18000a035  jz      short loc_18000A040
0x18000a037  cmp     ebx, r14d
0x18000a03a  jb      loc_18000A92F
0x18000a040  call    cs:__imp_GetLastError
0x18000a046  mov     rcx, r13; hMem
0x18000a049  mov     ebx, eax
0x18000a04b  call    cs:__imp_LocalFree
0x18000a051  mov     ecx, ebx; dwErrCode
0x18000a053  call    cs:__imp_SetLastError
0x18000a059  xor     r13d, r13d
0x18000a05c  mov     rdi, [rbp+0C0h+hMem]
0x18000a060  test    rdi, rdi
0x18000a063  jz      short loc_18000A07E
0x18000a065  call    cs:__imp_GetLastError
0x18000a06b  mov     rcx, rdi; hMem
0x18000a06e  mov     ebx, eax
0x18000a070  call    cs:__imp_LocalFree
0x18000a076  mov     ecx, ebx; dwErrCode
0x18000a078  call    cs:__imp_SetLastError
0x18000a07e  test    r12, r12
0x18000a081  jz      loc_18000A3E9
0x18000a087  mov     r9, r13
0x18000a08a  lea     rcx, String1; "post"
0x18000a091  cmp     r13w, [rcx]
0x18000a095  jz      short loc_18000A0A4
0x18000a097  inc     r9; cchCount1
0x18000a09a  add     rcx, 2
0x18000a09e  cmp     r9, 4
0x18000a0a2  jb      short loc_18000A091
0x18000a0a4  mov     rcx, r13
0x18000a0a7  mov     rdx, r12
0x18000a0aa  nop     word ptr [rax+rax+00h]
0x18000a0b0  cmp     r13w, [rdx]
0x18000a0b4  jz      short loc_18000A0C3
0x18000a0b6  inc     rcx
0x18000a0b9  add     rdx, 2
0x18000a0bd  cmp     rcx, 4
0x18000a0c1  jb      short loc_18000A0B0
0x18000a0c3  mov     [rsp+1C0h+cchCount2], ecx; cchCount2
0x18000a0c7  lea     r8, String1; "post"
0x18000a0ce  mov     ecx, 409h; Locale
0x18000a0d3  mov     [rsp+1C0h+lpString2], r12; lpString2
0x18000a0d8  mov     edx, 1; dwCmpFlags
0x18000a0dd  call    cs:__imp_CompareStringW
0x18000a0e3  cmp     eax, 2
0x18000a0e6  jz      loc_18000A94E
0x18000a0ec  mov     r14d, [rbp+0C0h+arg_30]
0x18000a0f3  mov     r15, r12
0x18000a0f6  mov     ecx, [rbp+0C0h+arg_0]
0x18000a0fc  mov     rdx, [rbp+0C0h+lpFileTime1]
0x18000a100  mov     r10d, [rbp+0C0h+arg_10]
0x18000a107  mov     r11d, [rbp+0C0h+arg_8]
0x18000a10e  mov     [rbp+0C0h+Src], r12
0x18000a115  mov     r13, [rbp+0C0h+Buf2]
0x18000a11c  mov     esi, r14d
0x18000a11f  and     esi, 400h
0x18000a125  test    r14b, 4
0x18000a129  jnz     loc_18000A2A3
0x18000a12f  mov     ebx, [rsp+1C0h+var_148]
0x18000a133  xor     eax, eax
0x18000a135  or      ebx, 2
0x18000a138  test    ecx, ecx
0x18000a13a  jz      loc_18000A486
0x18000a140  mov     rcx, [rbp+0C0h+pCertContext]; pCertContext
0x18000a147  test    esi, esi
0x18000a149  mov     r14, r15
0x18000a14c  mov     qword ptr [rbp+0C0h+var_120.dwLowDateTime], r15
0x18000a150  setnz   al
0x18000a153  xor     r12d, r12d
0x18000a156  mov     [rsp+1C0h+pcbEncoded], eax
0x18000a15a  xor     eax, eax
0x18000a15c  mov     [rsp+1C0h+var_150], eax
0x18000a160  call    ?CertificateGetOcspCacheFileNamePrefix@@YAPEAGPEBU_CERT_CONTEXT@@@Z; CertificateGetOcspCacheFileNamePrefix(_CERT_CONTEXT const *)
0x18000a165  mov     r15, [rbp+0C0h+arg_68]
0x18000a16c  xor     edi, edi
0x18000a16e  mov     [rbp+0C0h+pvEncoded], rax
0x18000a172  cmp     edi, 1
0x18000a175  ja      loc_18000A3B0
0x18000a17b  test    edi, edi
0x18000a17d  jz      loc_18000A46C
0x18000a183  mov     r9, [rbp+0C0h+lpFileTime1]; struct _FILETIME *
0x18000a187  mov     rdx, r14; unsigned __int16 *
0x18000a18a  mov     r8d, [rsp+1C0h+pcbEncoded]; int
0x18000a18f  mov     rcx, [rbp+0C0h+var_108]; struct _OCSP_CERT_ID *
0x18000a193  mov     [rsp+1C0h+var_170], rax; unsigned __int16 *
0x18000a198  lea     rax, [rbp+0C0h+var_128]
0x18000a19c  mov     [rsp+1C0h+var_178], r15; struct _CRYPT_GET_TIME_VALID_OBJECT_EXTRA_INFO *
0x18000a1a1  mov     [rsp+1C0h+var_180], rax; void **
0x18000a1a6  mov     rax, [rbp+0C0h+pCertContext]
0x18000a1ad  mov     [rsp+1C0h+var_188], rax; struct _CERT_CONTEXT *
0x18000a1b2  mov     rax, [rbp+0C0h+arg_48]
0x18000a1b9  mov     [rsp+1C0h+pcbComputedHash], rax; struct _CERT_CONTEXT *
0x18000a1be  mov     [rsp+1C0h+cchCount2], 0; dwTimeout
0x18000a1c6  mov     dword ptr [rsp+1C0h+lpString2], ebx; unsigned int
0x18000a1ca  call    ?I_RetrieveObjectByOcspUrlValidForSubject@@YAJPEBU_OCSP_CERT_ID@@PEBGHPEAU_FILETIME@@KKPEBU_CERT_CONTEXT@@3PEAPEAXPEAU_CRYPT_GET_TIME_VALID_OBJECT_EXTRA_INFO@@PEAG@Z; I_RetrieveObjectByOcspUrlValidForSubject(_OCSP_CERT_ID const *,ushort const *,int,_FILETIME *,ulong,ulong,_CERT_CONTEXT const *,_CERT_CONTEXT const *,void * *,_CRYPT_GET_TIME_VALID_OBJECT_EXTRA_INFO *,ushort *)
0x18000a1cf  mov     r14d, eax
0x18000a1d2  test    eax, eax
0x18000a1d4  jg      loc_18000A3A4
0x18000a1da  test    edi, edi
0x18000a1dc  jz      loc_18000A42C
0x18000a1e2  mov     r14, qword ptr [rbp+0C0h+var_120.dwLowDateTime]
0x18000a1e6  inc     edi
0x18000a1e8  mov     rax, [rbp+0C0h+pvEncoded]
0x18000a1ec  jmp     short loc_18000A172
0x18000a1ee  xor     eax, eax
0x18000a1f0  cmp     ax, di
0x18000a1f3  jz      loc_180009F78
0x18000a1f9  add     ebx, 3
0x18000a1fc  jnz     loc_180009F60
0x18000a202  mov     word ptr [r14], 25h ; '%'
0x18000a208  mov     eax, 30h ; '0'
0x18000a20d  mov     ecx, edi
0x18000a20f  mov     edx, edi
0x18000a211  shr     ecx, 4
0x18000a214  and     ecx, 0Fh
0x18000a217  cmp     ecx, 9
0x18000a21a  cmova   ax, r12w
0x18000a21f  and     edx, 0Fh
0x18000a222  add     ax, cx
0x18000a225  mov     [r14+2], ax
0x18000a22a  cmp     edx, 9
0x18000a22d  mov     eax, 30h ; '0'
0x18000a232  cmova   ax, r12w
0x18000a237  add     ax, dx
0x18000a23a  mov     [r14+4], ax
0x18000a23f  add     r14, 6
0x18000a243  jmp     loc_180009F60
0x18000a248  xor     eax, eax
0x18000a24a  cmp     ax, di
0x18000a24d  jz      loc_18000A019
0x18000a253  add     r14d, 3
0x18000a257  cmp     r14d, ebx
0x18000a25a  ja      loc_18000A000
0x18000a260  mov     word ptr [rsi], 25h ; '%'
0x18000a265  mov     eax, 30h ; '0'
0x18000a26a  mov     ecx, edi
0x18000a26c  mov     edx, edi
0x18000a26e  shr     ecx, 4
0x18000a271  and     ecx, 0Fh
0x18000a274  cmp     ecx, 9
0x18000a277  cmova   ax, r12w
0x18000a27c  and     edx, 0Fh
0x18000a27f  add     ax, cx
0x18000a282  mov     [rsi+2], ax
0x18000a286  cmp     edx, 9
0x18000a289  mov     eax, 30h ; '0'
0x18000a28e  cmova   ax, r12w
0x18000a293  add     ax, dx
0x18000a296  mov     [rsi+4], ax
0x18000a29a  add     rsi, 6
0x18000a29e  jmp     loc_18000A000
0x18000a2a3  mov     r15, [rbp+0C0h+arg_68]
0x18000a2aa  test    r14b, 2
0x18000a2ae  jnz     loc_18000A3D8
0x18000a2b4  mov     eax, dword ptr [rbp+0C0h+arg_40]
0x18000a2ba  lea     rcx, [rbp+0C0h+var_120]
0x18000a2be  or      eax, [rsp+1C0h+var_148]
0x18000a2c2  mov     rdi, [rbp+0C0h+arg_20]
0x18000a2c9  or      eax, 4
0x18000a2cc  mov     r12, [rbp+0C0h+Src]
0x18000a2d3  mov     r9d, eax; unsigned int
0x18000a2d6  mov     [rsp+1C0h+lpString2], rcx; struct _FILETIME *
0x18000a2db  mov     r8, rdi; char *
0x18000a2de  mov     rdx, r12; unsigned __int16 *
0x18000a2e1  mov     dword ptr [rbp+0C0h+arg_40], eax
0x18000a2e7  mov     rcx, r13; Buf2
0x18000a2ea  mov     qword ptr [rbp+0C0h+var_120.dwLowDateTime], 0
0x18000a2f2  call    ?GetOriginUrlStatusW@@YAJQEAEPEBGPEBDKPEAU_FILETIME@@@Z; GetOriginUrlStatusW(uchar * const,ushort const *,char const *,ulong,_FILETIME *)
0x18000a2f7  mov     ebx, eax
0x18000a2f9  test    eax, eax
0x18000a2fb  js      loc_18000A580
0x18000a301  and     r14d, 1000000h
0x18000a308  cmp     [rbp+0C0h+arg_0], 0
  ... truncated ...
```
