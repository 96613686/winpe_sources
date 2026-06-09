# _CreatePinRulesDiagCert

- ea: `0x1800e3414`
- end: `0x1800e3de8`
- name: `_CreatePinRulesDiagCert`
- size: `2516`
- prototype: ``
- caller_count: `1`
- callee_count: `19`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x1800211ec`

## callees

- `0x18001e590`
- `0x180023000`
- `0x180024d40`
- `0x180025120`
- `0x180028d60`
- `0x18002cb30`
- `0x18002f6f0`
- `0x180030e60`
- `0x18003523c`
- `0x180036dfc`
- `0x180037114`
- `0x1800450c0`
- `0x18005936c`
- `0x1800600e0`
- `0x1800a071c`
- `0x1800bec20`
- `0x1800bf63c`
- `0x1800e3414`
- `0x1801150c4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800e3d84`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800e3d84`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800e3a3b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800e3a3b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800e3950`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800e3950`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800e35ae`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800e3899`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800e35ae`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800e3899`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x1800e3bb2`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x1800e3bcc`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x1800e3bb2`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x1800e3bcc`

## string_xrefs

- `0x1800e3942`: `Software\Microsoft\SystemCertificates\AuthRoot\AutoUpdate`

## pseudocode

```c
PCCERT_CONTEXT __fastcall CreatePinRulesDiagCert(__int64 a1, __int64 a2, int a3, FILETIME a4, __int64 a5)
{
  _QWORD *v5; // r12
  PCCERT_CONTEXT v7; // r14
  CERT_CONTEXT *v8; // rsi
  unsigned int v9; // ebx
  BYTE *v10; // r15
  int v11; // edi
  _OWORD *p_dwVersion; // rax
  PCERT_INFO pCertInfo; // r9
  unsigned __int64 v14; // rax
  __int64 v15; // rcx
  unsigned __int64 v16; // rax
  __int64 *v17; // rdx
  __int64 v18; // rdx
  unsigned __int64 v19; // rax
  unsigned int v20; // r8d
  unsigned __int64 v21; // rcx
  unsigned __int64 v22; // rax
  unsigned int v23; // ebx
  unsigned __int64 v24; // rax
  unsigned __int16 *SZValueFromRegistry; // rax
  unsigned __int16 *v26; // r14
  __int64 v27; // rcx
  __int64 v28; // rax
  int v29; // edx
  unsigned __int64 v30; // rcx
  __int64 v31; // rsi
  __int64 v32; // rsi
  const CTL_CONTEXT *v33; // r14
  int v34; // r15d
  HKEY PinRulesContext; // rdx
  __int64 v36; // rax
  __int64 v37; // rcx
  DWORD v38; // r8d
  __int64 v39; // r13
  __int64 v40; // r12
  DWORD v41; // esi
  __int64 v42; // rax
  int v43; // eax
  const CERT_CONTEXT *AutoUpdateCtl; // rsi
  DWORD cbCtlEncoded; // eax
  unsigned int v46; // edx
  unsigned __int64 v47; // rcx
  unsigned int v48; // ebx
  DWORD v49; // r9d
  _DWORD *v50; // rbx
  char v52; // [rsp+54h] [rbp-364h] BYREF
  int v53; // [rsp+58h] [rbp-360h]
  DWORD v54; // [rsp+5Ch] [rbp-35Ch] BYREF
  DWORD pcbEncoded; // [rsp+60h] [rbp-358h] BYREF
  unsigned int v56; // [rsp+64h] [rbp-354h]
  DWORD cbCertEncoded; // [rsp+68h] [rbp-350h] BYREF
  FILETIME FileTime1; // [rsp+70h] [rbp-348h] BYREF
  DWORD pcbData; // [rsp+78h] [rbp-340h] BYREF
  DWORD pcbComputedHash; // [rsp+7Ch] [rbp-33Ch] BYREF
  int v61; // [rsp+80h] [rbp-338h]
  int v62; // [rsp+84h] [rbp-334h]
  __int64 v63; // [rsp+88h] [rbp-330h]
  PCCERT_CONTEXT ppCertContext; // [rsp+90h] [rbp-328h] BYREF
  BYTE *v65; // [rsp+98h] [rbp-320h]
  DWORD i; // [rsp+A0h] [rbp-318h]
  unsigned int v67; // [rsp+A4h] [rbp-314h]
  HLOCAL v68; // [rsp+A8h] [rbp-310h]
  struct _FILETIME v69; // [rsp+B0h] [rbp-308h] BYREF
  __int64 v70; // [rsp+B8h] [rbp-300h] BYREF
  HLOCAL hMem; // [rsp+C0h] [rbp-2F8h]
  PCCERT_CONTEXT v72; // [rsp+C8h] [rbp-2F0h]
  __int64 v73; // [rsp+D0h] [rbp-2E8h]
  _DWORD pvStructInfo[4]; // [rsp+E0h] [rbp-2D8h] BYREF
  char *v75; // [rsp+F0h] [rbp-2C8h]
  struct _CRYPT_ALGORITHM_IDENTIFIER pSignatureAlgorithm; // [rsp+F8h] [rbp-2C0h] BYREF
  DWORD v77; // [rsp+110h] [rbp-2A8h]
  int v78; // [rsp+114h] [rbp-2A4h]
  BYTE *v79; // [rsp+118h] [rbp-2A0h]
  struct _FILETIME SystemTimeAsFileTime; // [rsp+120h] [rbp-298h] BYREF
  struct _FILETIME v81; // [rsp+128h] [rbp-290h]
  DWORD v82; // [rsp+130h] [rbp-288h]
  int v83; // [rsp+134h] [rbp-284h]
  BYTE *v84; // [rsp+138h] [rbp-280h]
  __int128 v85; // [rsp+140h] [rbp-278h]
  __int128 v86; // [rsp+150h] [rbp-268h]
  __int128 v87; // [rsp+160h] [rbp-258h]
  unsigned int v88; // [rsp+1A0h] [rbp-218h]
  const char **v89; // [rsp+1A8h] [rbp-210h]
  const char *v90; // [rsp+1B0h] [rbp-208h] BYREF
  char v91[8]; // [rsp+1B8h] [rbp-200h] BYREF
  _DWORD v92[2]; // [rsp+1C0h] [rbp-1F8h]
  _QWORD v93[37]; // [rsp+1C8h] [rbp-1F0h]
  BYTE pbComputedHash[8]; // [rsp+2F0h] [rbp-C8h] BYREF
  _BYTE pvData[16]; // [rsp+300h] [rbp-B8h] BYREF
  BYTE v96[32]; // [rsp+310h] [rbp-A8h] BYREF
  BYTE pbEncoded[64]; // [rsp+330h] [rbp-88h] BYREF

  v5 = (_QWORD *)a4;
  FileTime1 = a4;
  v62 = a3;
  v63 = a5;
  v73 = a5;
  v7 = 0;
  ppCertContext = 0;
  v8 = *(CERT_CONTEXT **)(*(_QWORD *)(*(_QWORD *)(**(_QWORD **)(a1 + 16) + 16LL)
                                    + 8LL * (unsigned int)(*(_DWORD *)(**(_QWORD **)(a1 + 16) + 12LL) - 1))
                        + 8LL);
  memset_0(pvStructInfo, 0, 0xD0u);
  v52 = 1;
  memset_0(pbEncoded, 0, sizeof(pbEncoded));
  pcbEncoded = 64;
  v90 = 0;
  memset_0(v91, 0, 0x138u);
  v9 = 0;
  cbCertEncoded = 0;
  v10 = 0;
  v65 = 0;
  v11 = 0;
  v53 = 0;
  v69 = 0;
  v70 = 0;
  hMem = 0;
  v68 = 0;
  if ( v62 )
  {
    *v5 = L"ctlsign.err";
    v11 = 1;
    v53 = 1;
  }
  if ( !CertStrToNameW(1u, L"CN=Pin Rules", 0x2000003u, 0, pbEncoded, &pcbEncoded, 0) || pcbEncoded > 0x40 )
  {
LABEL_90:
    v50 = (_DWORD *)v63;
    goto LABEL_91;
  }
  pvStructInfo[0] = 2;
  v75 = &v52;
  pvStructInfo[2] = 1;
  pSignatureAlgorithm.pszObjId = (LPSTR)"1.3.14.3.2.26";
  GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
  v81 = SystemTimeAsFileTime;
  v82 = pcbEncoded;
  v84 = pbEncoded;
  v77 = pcbEncoded;
  v78 = v83;
  v79 = pbEncoded;
  p_dwVersion = &v8->pCertInfo->dwVersion;
  v85 = p_dwVersion[6];
  v86 = p_dwVersion[7];
  v87 = p_dwVersion[8];
  pcbData = 16;
  if ( !CertGetCertificateContextProperty(v8, 0x19u, pvData, &pcbData) || pcbData != 16 )
  {
    v11 = 1;
    goto LABEL_12;
  }
  v90 = "1.3.6.1.4.1.311.10.3.33.1";
  v93[0] = pvData;
  v92[0] = 16;
  v9 = 1;
  pCertInfo = v8->pCertInfo;
  pcbComputedHash = 16;
  if ( CryptHashCertificate(
         0,
         0x8003u,
         0,
         pCertInfo->SubjectPublicKeyInfo.PublicKey.pbData,
         pCertInfo->SubjectPublicKeyInfo.PublicKey.cbData,
         pbComputedHash,
         &pcbComputedHash)
    && pcbComputedHash == 16
    && memcmp_0(pvData, pbComputedHash, 0x10u) )
  {
    v11 = 1;
LABEL_12:
    *v5 = L"keyprop.err";
    v53 = 1;
  }
  v54 = 32;
  if ( CertGetCertificateContextProperty(v8, 0xA000u, v96, &v54) && v54 == 32 )
  {
    v14 = 8LL * v9;
    *(_QWORD *)&v91[v14 * 4 - 8] = "1.3.6.1.4.1.311.10.3.33.2";
    v93[v14 / 2] = v96;
    v92[v14] = 32;
    ++v9;
  }
  if ( !CryptVerifyCertificateSignatureEx(0, v8->dwCertEncodingType, 2u, v8, 2u, v8, 0, 0) )
  {
    *v5 = L"rootsign.err";
    v11 = 1;
    v53 = 1;
  }
  v15 = *(_QWORD *)(a2 + 32);
  if ( v15 )
  {
    v16 = 8LL * v9;
    *(_QWORD *)&v91[v16 * 4 - 8] = "1.3.6.1.4.1.311.10.3.33.3";
    v93[v16 / 2] = v15;
    v92[v16] = 24;
    ++v9;
    if ( *(_DWORD *)v15 )
    {
      v17 = *(__int64 **)(v15 + 8);
      if ( v17 )
      {
        v18 = *v17;
        if ( v18 )
        {
          v19 = 8LL * v9;
          *(_QWORD *)&v91[v19 * 4 - 8] = "1.3.6.1.4.1.311.10.3.33.4";
          v93[v19 / 2] = v18;
          v92[v19] = 24;
          ++v9;
          v20 = *(_DWORD *)(v18 + 8);
          if ( v20 )
          {
            if ( *(_QWORD *)(v18 + 16) )
            {
              if ( v20 > 0x20 )
                v20 = 32;
              v21 = 8LL * v9;
              *(_QWORD *)&v91[v21 * 4 - 8] = "1.3.6.1.4.1.311.10.3.33.5";
              v93[v21 / 2] = *(_QWORD *)(v18 + 16);
              v92[v21] = 56 * v20;
              ++v9;
            }
          }
        }
      }
    }
  }
  GetSystemTimeAsFileTime(&v69);
  v22 = 8LL * v9;
  *(_QWORD *)&v91[v22 * 4 - 8] = "1.3.6.1.4.1.311.10.3.33.6";
  v93[v22 / 2] = &v69;
  v92[v22] = 8;
  v23 = v9 + 1;
  if ( (unsigned int)I_CertGetAutoUpdateLastSyncTime(7, &v70) )
  {
    v24 = 8LL * v23;
    *(_QWORD *)&v91[v24 * 4 - 8] = "1.3.6.1.4.1.311.10.3.33.7";
    v93[v24 / 2] = &v70;
    v92[v24] = 8;
    ++v23;
  }
  *(_QWORD *)pbComputedHash = 0;
  if ( !RegOpenKeyExW(
          HKEY_LOCAL_MACHINE,
          L"Software\\Microsoft\\SystemCertificates\\AuthRoot\\AutoUpdate",
          0,
          0x20119u,
          (PHKEY)pbComputedHash) )
  {
    SZValueFromRegistry = ILS_ReadSZValueFromRegistry(*(HKEY *)pbComputedHash, L"RootDirUrl");
    v26 = SZValueFromRegistry;
    hMem = SZValueFromRegistry;
    if ( SZValueFromRegistry && *SZValueFromRegistry )
    {
      v27 = 4LL * v23;
      *(_QWORD *)&v91[v27 * 8 - 8] = "1.3.6.1.4.1.311.10.3.33.8";
      v93[v27] = SZValueFromRegistry;
      v28 = -1;
      do
        ++v28;
      while ( v26[v28] );
      v92[8 * v23++] = 2 * v28;
    }
    v56 = 0;
    if ( (unsigned int)I_CertReadBINARYValueFromRegistry(*(HKEY *)pbComputedHash, L"PinRulesLastError") && v56 )
    {
      v29 = 2064;
      if ( v56 < 0x810 )
        v29 = v56;
      v56 = v29;
      v30 = 8LL * v23;
      *(_QWORD *)&v91[v30 * 4 - 8] = "1.3.6.1.4.1.311.10.3.33.9";
      v93[v30 / 2] = v68;
      v92[v30] = v29;
      ++v23;
    }
    RegCloseKey(*(HKEY *)pbComputedHash);
  }
  if ( !*(_DWORD *)(a2 + 40) )
    goto LABEL_79;
  v31 = *(_QWORD *)(a2 + 16);
  if ( !v31 )
    goto LABEL_79;
  v32 = *(_QWORD *)(v31 + 8);
  if ( !v32 )
    goto LABEL_79;
  v33 = *(const CTL_CONTEXT **)v32;
  if ( !*(_QWORD *)v32 )
    goto LABEL_79;
  v34 = 0;
  v61 = 0;
  PinRulesContext = (HKEY)CreatePinRulesContext(v33);
  *(_QWORD *)pbComputedHash = PinRulesContext;
  if ( PinRulesContext )
  {
    v36 = *(_QWORD *)(v32 + 8);
    if ( v36 && (v37 = *((_QWORD *)PinRulesContext + 1)) != 0 )
    {
      v38 = *(_DWORD *)v36;
      v54 = v38;
      if ( v38 == *(_DWORD *)v37 )
      {
        v39 = *(_QWORD *)(v36 + 8);
        if ( v39 )
        {
          v40 = *(_QWORD *)(v37 + 8);
          if ( v40 )
          {
            v41 = 0;
            for ( i = 0; ; i = v41 )
            {
              if ( v41 >= v38 )
              {
                v43 = 1;
                PinRulesContext = *(HKEY *)pbComputedHash;
                v5 = (_QWORD *)FileTime1;
                goto LABEL_60;
              }
              v42 = *(unsigned int *)(v39 + 24LL * v41 + 8);
              if ( (_DWORD)v42 != *(_DWORD *)(v40 + 24LL * v41 + 8) )
                break;
              if ( (_DWORD)v42 )
              {
                if ( memcmp_0(
                       *(const void **)(v39 + 24LL * v41 + 16),
                       *(const void **)(v40 + 24LL * v41 + 16),
                       56 * v42) )
                {
                  break;
                }
                v38 = v54;
              }
              ++v41;
            }
            PinRulesContext = *(HKEY *)pbComputedHash;
          }
          v5 = (_QWORD *)FileTime1;
        }
      }
    }
    else
    {
      v43 = 0;
LABEL_60:
      if ( v43 )
        goto LABEL_65;
    }
    v34 = 1;
    v61 = 1;
    *v5 = L"keymem.err";
    v11 = 1;
    v53 = 1;
LABEL_65:
    ReleasePinRulesContext(PinRulesContext);
  }
  FileTime1 = 0;
  AutoUpdateCtl = (const CERT_CONTEXT *)I_CertGetAutoUpdateCtl(7, &FileTime1);
  if ( AutoUpdateCtl )
  {
    if ( !CompareFileTime(&FileTime1, &FileTime2)
      || !CompareFileTime(&v33->pCtlInfo->ThisUpdate, (const FILETIME *)&AutoUpdateCtl->pCertInfo->Issuer.pbData) )
    {
      cbCtlEncoded = v33->cbCtlEncoded;
      if ( cbCtlEncoded != AutoUpdateCtl->cbCertEncoded
        || memcmp_0(v33->pbCtlEncoded, AutoUpdateCtl->pbCertEncoded, cbCtlEncoded) )
      {
        v34 = 1;
        v61 = 1;
        *v5 = L"ctlmem.err";
        v11 = 1;
        v53 = 1;
      }
    }
    CertFreeCertificateContext(AutoUpdateCtl);
  }
  if ( v62 || v34 )
  {
    v46 = v33->cbCtlEncoded;
    if ( v46 > 0x10000 )
      v46 = 0x10000;
    v47 = 8LL * v23;
    *(_QWORD *)&v91[v47 * 4 - 8] = "1.3.6.1.4.1.311.10.3.32";
    v93[v47 / 2] = v33->pbCtlEncoded;
    v92[v47] = v46;
    ++v23;
  }
  v10 = v65;
LABEL_79:
  v88 = v23;
  v89 = &v90;
  v48 = 0;
  v49 = cbCertEncoded;
  while ( 1 )
  {
    v67 = v48;
    if ( v48 >= 2 )
      break;
    if ( v48 == 1 && (v10 = (BYTE *)PkiNonzeroAlloc(v49), (v65 = v10) == 0)
      || !CryptSignAndEncodeCertificate(0, 0, 1u, (LPCSTR)2, pvStructInfo, &pSignatureAlgorithm, 0, v10, &cbCertEncoded)
      || (v49 = cbCertEncoded) == 0 )
    {
      v7 = ppCertContext;
      goto LABEL_90;
    }
    ++v48;
  }
  ppCertContext = 0;
  CertAddEncodedCertificateToStore(0, 1u, v10, v49, 4u, &ppCertContext);
  v7 = ppCertContext;
  v72 = ppCertContext;
  if ( !ppCertContext )
    goto LABEL_90;
  v50 = (_DWORD *)v63;
LABEL_91:
  PkiDefaultCryptFree(hMem);
  PkiDefaultCryptFree(v68);
  PkiDefaultCryptFree(v10);
  *v50 = v11;
  return v7;
}

```

## disassembly

```asm
0x1800e3414  push    rbx
0x1800e3416  push    rsi
0x1800e3417  push    rdi
0x1800e3418  push    r12
0x1800e341a  push    r13
0x1800e341c  push    r14
0x1800e341e  push    r15
0x1800e3420  sub     rsp, 380h
0x1800e3427  mov     rax, cs:__security_cookie
0x1800e342e  xor     rax, rsp
0x1800e3431  mov     [rsp+3B8h+var_48], rax
0x1800e3439  mov     r12, r9
0x1800e343c  mov     qword ptr [rsp+3B8h+FileTime1.dwLowDateTime], r9
0x1800e3441  mov     [rsp+3B8h+var_334], r8d
0x1800e3449  mov     r13, rdx
0x1800e344c  mov     rax, [rsp+3B8h+arg_20]
0x1800e3454  mov     [rsp+3B8h+var_330], rax
0x1800e345c  mov     [rsp+3B8h+var_2E8], rax
0x1800e3464  xor     r14d, r14d
0x1800e3467  mov     [rsp+3B8h+ppCertContext], r14
0x1800e346f  mov     rax, [rcx+10h]
0x1800e3473  mov     rdx, [rax]
0x1800e3476  mov     ecx, [rdx+0Ch]
0x1800e3479  dec     ecx
0x1800e347b  mov     rax, [rdx+10h]
0x1800e347f  mov     rcx, [rax+rcx*8]
0x1800e3483  mov     rsi, [rcx+8]
0x1800e3487  xor     edx, edx; Val
0x1800e3489  mov     r8d, 0D0h; Size
0x1800e348f  lea     rcx, [rsp+3B8h+pvStructInfo]; void *
0x1800e3497  call    memset_0
0x1800e349c  mov     [rsp+3B8h+var_364], 1
0x1800e34a1  lea     ebx, [r14+40h]
0x1800e34a5  mov     r8d, ebx; Size
0x1800e34a8  xor     edx, edx; Val
0x1800e34aa  lea     rcx, [rsp+3B8h+var_88]; void *
0x1800e34b2  call    memset_0
0x1800e34b7  mov     [rsp+3B8h+var_358], ebx
0x1800e34bb  mov     [rsp+3B8h+var_208], r14
0x1800e34c3  xor     edx, edx; Val
0x1800e34c5  mov     r8d, 138h; Size
0x1800e34cb  lea     rcx, [rsp+3B8h+var_200]; void *
0x1800e34d3  call    memset_0
0x1800e34d8  xor     ecx, ecx
0x1800e34da  mov     ebx, ecx
0x1800e34dc  mov     [rsp+3B8h+cbCertEncoded], ecx
0x1800e34e0  mov     r15d, ecx
0x1800e34e3  mov     [rsp+3B8h+var_320], rcx
0x1800e34eb  mov     edi, ecx
0x1800e34ed  mov     [rsp+3B8h+var_360], ecx
0x1800e34f1  mov     qword ptr [rsp+3B8h+var_308.dwLowDateTime], rcx
0x1800e34f9  mov     [rsp+3B8h+var_300], rcx
0x1800e3501  mov     [rsp+3B8h+hMem], rcx
0x1800e3509  mov     [rsp+3B8h+var_310], rcx
0x1800e3511  cmp     [rsp+3B8h+var_334], ecx
0x1800e3518  jz      short loc_1800E352C
0x1800e351a  lea     rax, aCtlsignErr; "ctlsign.err"
0x1800e3521  mov     [r12], rax
0x1800e3525  lea     edi, [rcx+1]
0x1800e3528  mov     [rsp+3B8h+var_360], edi
0x1800e352c  mov     [rsp+3B8h+ppszError], rcx; ppszError
0x1800e3531  lea     rax, [rsp+3B8h+var_358]
0x1800e3536  mov     [rsp+3B8h+pcbEncoded], rax; pcbEncoded
0x1800e353b  lea     rax, [rsp+3B8h+var_88]
0x1800e3543  mov     [rsp+3B8h+pbEncoded], rax; pbEncoded
0x1800e3548  xor     r9d, r9d; pvReserved
0x1800e354b  mov     r8d, 2000003h; dwStrType
0x1800e3551  lea     rdx, pszX500; "CN=Pin Rules"
0x1800e3558  lea     ecx, [r9+1]; dwCertEncodingType
0x1800e355c  call    CertStrToNameW
0x1800e3561  test    eax, eax
0x1800e3563  jz      loc_1800E3D6D
0x1800e3569  cmp     [rsp+3B8h+var_358], 40h ; '@'
0x1800e356e  ja      loc_1800E3D6D
0x1800e3574  mov     [rsp+3B8h+pvStructInfo], 2
0x1800e357f  lea     rax, [rsp+3B8h+var_364]
0x1800e3584  mov     [rsp+3B8h+var_2C8], rax
0x1800e358c  mov     [rsp+3B8h+var_2D0], 1
0x1800e3597  lea     rax, a13143226; "1.3.14.3.2.26"
0x1800e359e  mov     [rsp+3B8h+pSignatureAlgorithm.pszObjId], rax
0x1800e35a6  lea     rcx, [rsp+3B8h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1800e35ae  call    cs:__imp_GetSystemTimeAsFileTime
0x1800e35b4  mov     rax, qword ptr [rsp+3B8h+SystemTimeAsFileTime.dwLowDateTime]
0x1800e35bc  mov     [rsp+3B8h+var_290], rax
0x1800e35c4  mov     eax, [rsp+3B8h+var_358]
0x1800e35c8  mov     [rsp+3B8h+var_288], eax
0x1800e35cf  lea     rcx, [rsp+3B8h+var_88]
0x1800e35d7  mov     [rsp+3B8h+var_280], rcx
0x1800e35df  mov     [rsp+3B8h+var_2A8], eax
0x1800e35e6  mov     eax, [rsp+3B8h+var_284]
0x1800e35ed  mov     [rsp+3B8h+var_2A4], eax
0x1800e35f4  lea     rax, [rsp+3B8h+var_88]
0x1800e35fc  mov     [rsp+3B8h+var_2A0], rax
0x1800e3604  mov     rax, [rsi+18h]
0x1800e3608  movups  xmm0, xmmword ptr [rax+60h]
0x1800e360c  movaps  [rsp+3B8h+var_278], xmm0
0x1800e3614  movups  xmm1, xmmword ptr [rax+70h]
0x1800e3618  movaps  [rsp+3B8h+var_268], xmm1
0x1800e3620  movups  xmm0, xmmword ptr [rax+80h]
0x1800e3627  movaps  [rsp+3B8h+var_258], xmm0
0x1800e362f  mov     [rsp+3B8h+pcbData], 10h
0x1800e3637  lea     r9, [rsp+3B8h+pcbData]; pcbData
0x1800e363c  lea     r8, [rsp+3B8h+pvData]; pvData
0x1800e3644  mov     edx, 19h; dwPropId
0x1800e3649  mov     rcx, rsi; pCertContext
0x1800e364c  call    CertGetCertificateContextProperty
0x1800e3651  xor     r14d, r14d
0x1800e3654  test    eax, eax
0x1800e3656  jz      loc_1800E3706
0x1800e365c  cmp     [rsp+3B8h+pcbData], 10h
0x1800e3661  jnz     loc_1800E3706
0x1800e3667  lea     rax, a13614131110333_4; "1.3.6.1.4.1.311.10.3.33.1"
0x1800e366e  mov     [rsp+3B8h+var_208], rax
0x1800e3676  lea     rax, [rsp+3B8h+pvData]
0x1800e367e  mov     [rsp+3B8h+var_1F0], rax
0x1800e3686  mov     [rsp+3B8h+var_1F8], 10h
0x1800e3691  lea     ebx, [r14+1]
0x1800e3695  mov     [rsp+3B8h+var_368], ebx
0x1800e3699  mov     r9, [rsi+18h]
0x1800e369d  mov     [rsp+3B8h+pcbComputedHash], 10h
0x1800e36a5  lea     rax, [rsp+3B8h+pcbComputedHash]
0x1800e36aa  mov     [rsp+3B8h+ppszError], rax; pcbComputedHash
0x1800e36af  lea     rax, [rsp+3B8h+pbComputedHash]
0x1800e36b7  mov     [rsp+3B8h+pcbEncoded], rax; pbComputedHash
0x1800e36bc  mov     eax, [r9+78h]
0x1800e36c0  mov     dword ptr [rsp+3B8h+pbEncoded], eax; cbEncoded
0x1800e36c4  mov     r9, [r9+80h]; pbEncoded
0x1800e36cb  xor     r8d, r8d; dwFlags
0x1800e36ce  mov     edx, 8003h; Algid
0x1800e36d3  xor     ecx, ecx; hCryptProv
0x1800e36d5  call    CryptHashCertificate
0x1800e36da  test    eax, eax
0x1800e36dc  jz      short loc_1800E371A
0x1800e36de  cmp     [rsp+3B8h+pcbComputedHash], 10h
0x1800e36e3  jnz     short loc_1800E371A
0x1800e36e5  lea     r8d, [r14+10h]; Size
0x1800e36e9  lea     rdx, [rsp+3B8h+pbComputedHash]; Buf2
0x1800e36f1  lea     rcx, [rsp+3B8h+pvData]; Buf1
0x1800e36f9  call    memcmp_0
0x1800e36fe  test    eax, eax
0x1800e3700  jz      short loc_1800E371A
0x1800e3702  mov     edi, ebx
0x1800e3704  jmp     short loc_1800E370B
0x1800e3706  mov     edi, 1
0x1800e370b  lea     rax, aKeypropErr; "keyprop.err"
0x1800e3712  mov     [r12], rax
0x1800e3716  mov     [rsp+3B8h+var_360], edi
0x1800e371a  mov     [rsp+3B8h+var_35C], 20h ; ' '
0x1800e3722  lea     r9, [rsp+3B8h+var_35C]; pcbData
0x1800e3727  lea     r8, [rsp+3B8h+var_A8]; pvData
0x1800e372f  mov     edx, 0A000h; dwPropId
0x1800e3734  mov     rcx, rsi; pCertContext
0x1800e3737  call    CertGetCertificateContextProperty
0x1800e373c  test    eax, eax
0x1800e373e  jz      short loc_1800E377D
0x1800e3740  cmp     [rsp+3B8h+var_35C], 20h ; ' '
0x1800e3745  jnz     short loc_1800E377D
0x1800e3747  mov     eax, ebx
0x1800e3749  shl     rax, 5
0x1800e374d  lea     rcx, a13614131110333_1; "1.3.6.1.4.1.311.10.3.33.2"
0x1800e3754  mov     [rsp+rax+3B8h+var_208], rcx
0x1800e375c  lea     rcx, [rsp+3B8h+var_A8]
0x1800e3764  mov     [rsp+rax+3B8h+var_1F0], rcx
0x1800e376c  mov     [rsp+rax+3B8h+var_1F8], 20h ; ' '
0x1800e3777  inc     ebx
0x1800e3779  mov     [rsp+3B8h+var_368], ebx
0x1800e377d  mov     [rsp+3B8h+pvExtra], r14; pvExtra
0x1800e3782  mov     dword ptr [rsp+3B8h+ppszError], r14d; dwFlags
0x1800e3787  mov     [rsp+3B8h+pcbEncoded], rsi; pvIssuer
0x1800e378c  mov     dword ptr [rsp+3B8h+pbEncoded], 2; dwIssuerType
0x1800e3794  mov     r9, rsi; pvSubject
0x1800e3797  mov     r8d, 2; dwSubjectType
0x1800e379d  mov     edx, [rsi]; dwCertEncodingType
0x1800e379f  xor     ecx, ecx; hCryptProv
0x1800e37a1  call    CryptVerifyCertificateSignatureEx
0x1800e37a6  xor     esi, esi
0x1800e37a8  test    eax, eax
0x1800e37aa  jnz     short loc_1800E37BE
0x1800e37ac  lea     rax, aRootsignErr; "rootsign.err"
0x1800e37b3  mov     [r12], rax
0x1800e37b7  lea     edi, [rsi+1]
0x1800e37ba  mov     [rsp+3B8h+var_360], edi
0x1800e37be  mov     rcx, [r13+20h]
0x1800e37c2  test    rcx, rcx
0x1800e37c5  jz      loc_1800E3891
0x1800e37cb  mov     eax, ebx
0x1800e37cd  shl     rax, 5
0x1800e37d1  lea     rdx, a13614131110333_0; "1.3.6.1.4.1.311.10.3.33.3"
0x1800e37d8  mov     [rsp+rax+3B8h+var_208], rdx
0x1800e37e0  mov     [rsp+rax+3B8h+var_1F0], rcx
0x1800e37e8  mov     r8d, 18h
0x1800e37ee  mov     [rsp+rax+3B8h+var_1F8], r8d
0x1800e37f6  inc     ebx
0x1800e37f8  mov     [rsp+3B8h+var_368], ebx
0x1800e37fc  cmp     [rcx], esi
0x1800e37fe  jz      loc_1800E3891
0x1800e3804  mov     rdx, [rcx+8]
0x1800e3808  test    rdx, rdx
0x1800e380b  jz      loc_1800E3891
0x1800e3811  mov     rdx, [rdx]
0x1800e3814  test    rdx, rdx
0x1800e3817  jz      short loc_1800E3891
0x1800e3819  mov     eax, ebx
0x1800e381b  shl     rax, 5
0x1800e381f  lea     rcx, a13614131110333_2; "1.3.6.1.4.1.311.10.3.33.4"
0x1800e3826  mov     [rsp+rax+3B8h+var_208], rcx
0x1800e382e  mov     [rsp+rax+3B8h+var_1F0], rdx
0x1800e3836  mov     [rsp+rax+3B8h+var_1F8], r8d
0x1800e383e  inc     ebx
0x1800e3840  mov     [rsp+3B8h+var_368], ebx
0x1800e3844  mov     r8d, [rdx+8]
0x1800e3848  test    r8d, r8d
0x1800e384b  jz      short loc_1800E3891
0x1800e384d  cmp     [rdx+10h], rsi
0x1800e3851  jz      short loc_1800E3891
0x1800e3853  mov     eax, 20h ; ' '
0x1800e3858  cmp     r8d, eax
0x1800e385b  cmova   r8d, eax
0x1800e385f  mov     ecx, ebx
0x1800e3861  shl     rcx, 5
0x1800e3865  lea     rax, a13614131110333; "1.3.6.1.4.1.311.10.3.33.5"
0x1800e386c  mov     [rsp+rcx+3B8h+var_208], rax
0x1800e3874  mov     rax, [rdx+10h]
0x1800e3878  mov     [rsp+rcx+3B8h+var_1F0], rax
0x1800e3880  imul    eax, r8d, 38h ; '8'
0x1800e3884  mov     [rsp+rcx+3B8h+var_1F8], eax
0x1800e388b  inc     ebx
0x1800e388d  mov     [rsp+3B8h+var_368], ebx
0x1800e3891  lea     rcx, [rsp+3B8h+var_308]; lpSystemTimeAsFileTime
0x1800e3899  call    cs:__imp_GetSystemTimeAsFileTime
0x1800e389f  mov     eax, ebx
0x1800e38a1  shl     rax, 5
0x1800e38a5  lea     rcx, a13614131110333_3; "1.3.6.1.4.1.311.10.3.33.6"
0x1800e38ac  mov     [rsp+rax+3B8h+var_208], rcx
0x1800e38b4  lea     rcx, [rsp+3B8h+var_308]
0x1800e38bc  mov     [rsp+rax+3B8h+var_1F0], rcx
0x1800e38c4  mov     r14d, 8
0x1800e38ca  mov     [rsp+rax+3B8h+var_1F8], r14d
0x1800e38d2  inc     ebx
0x1800e38d4  mov     [rsp+3B8h+var_368], ebx
0x1800e38d8  lea     r8d, [r14-7]
0x1800e38dc  lea     rdx, [rsp+3B8h+var_300]
0x1800e38e4  lea     ecx, [r14-1]
0x1800e38e8  call    I_CertGetAutoUpdateLastSyncTime
0x1800e38ed  test    eax, eax
0x1800e38ef  jz      short loc_1800E3924
0x1800e38f1  mov     eax, ebx
0x1800e38f3  shl     rax, 5
0x1800e38f7  lea     rcx, a13614131110333_7; "1.3.6.1.4.1.311.10.3.33.7"
0x1800e38fe  mov     [rsp+rax+3B8h+var_208], rcx
0x1800e3906  lea     rcx, [rsp+3B8h+var_300]
0x1800e390e  mov     [rsp+rax+3B8h+var_1F0], rcx
0x1800e3916  mov     [rsp+rax+3B8h+var_1F8], r14d
0x1800e391e  inc     ebx
0x1800e3920  mov     [rsp+3B8h+var_368], ebx
0x1800e3924  mov     qword ptr [rsp+3B8h+pbComputedHash], rsi
0x1800e392c  lea     rax, [rsp+3B8h+pbComputedHash]
0x1800e3934  mov     [rsp+3B8h+pbEncoded], rax; phkResult
0x1800e3939  mov     r9d, 20119h; samDesired
0x1800e393f  xor     r8d, r8d; ulOptions
0x1800e3942  lea     rdx, aSoftwareMicros_0; "Software\\Microsoft\\SystemCertificates"...
0x1800e3949  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800e3950  call    cs:__imp_RegOpenKeyExW
0x1800e3956  test    eax, eax
0x1800e3958  jnz     loc_1800E3A41
0x1800e395e  lea     rdx, aRootdirurl; "RootDirUrl"
0x1800e3965  mov     rcx, qword ptr [rsp+3B8h+pbComputedHash]; hKey
0x1800e396d  call    ?ILS_ReadSZValueFromRegistry@@YAPEAGPEAUHKEY__@@PEBG@Z; ILS_ReadSZValueFromRegistry(HKEY__ *,ushort const *)
0x1800e3972  mov     r14, rax
0x1800e3975  mov     [rsp+3B8h+hMem], rax
0x1800e397d  test    rax, rax
0x1800e3980  jz      short loc_1800E39C1
0x1800e3982  cmp     si, [rax]
0x1800e3985  jz      short loc_1800E39C1
0x1800e3987  mov     ecx, ebx
0x1800e3989  shl     rcx, 5
0x1800e398d  lea     rax, a13614131110333_5; "1.3.6.1.4.1.311.10.3.33.8"
0x1800e3994  mov     [rsp+rcx+3B8h+var_208], rax
0x1800e399c  mov     [rsp+rcx+3B8h+var_1F0], r14
0x1800e39a4  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800e39a8  inc     rax
0x1800e39ab  cmp     [r14+rax*2], si
0x1800e39b0  jnz     short loc_1800E39A8
0x1800e39b2  add     eax, eax
0x1800e39b4  mov     [rsp+rcx+3B8h+var_1F8], eax
0x1800e39bb  inc     ebx
0x1800e39bd  mov     [rsp+3B8h+var_368], ebx
0x1800e39c1  mov     [rsp+3B8h+var_354], esi
0x1800e39c5  lea     r9, [rsp+3B8h+var_354]
0x1800e39ca  lea     r8, [rsp+3B8h+var_310]
0x1800e39d2  lea     rdx, aPinruleslaster; "PinRulesLastError"
0x1800e39d9  mov     rcx, qword ptr [rsp+3B8h+pbComputedHash]; hKey
0x1800e39e1  call    I_CertReadBINARYValueFromRegistry
0x1800e39e6  test    eax, eax
0x1800e39e8  jz      short loc_1800E3A33
0x1800e39ea  mov     eax, [rsp+3B8h+var_354]
0x1800e39ee  test    eax, eax
0x1800e39f0  jz      short loc_1800E3A33
0x1800e39f2  mov     edx, 810h
0x1800e39f7  cmp     eax, edx
  ... truncated ...
```
