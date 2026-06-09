# ConvertAuthDataToAuthDataInt(bool,_ApPluginPkg *,ushort const *,_DECRYPTED_AUTH_DATA *,_DECRYPTED_AUTH_DATA *,ushort * *,_SCARD_PIN * *)

- ea: `0x180029650`
- end: `0x18002ae02`
- name: `?ConvertAuthDataToAuthDataInt@@YAJ_NPEAU_ApPluginPkg@@PEBGPEAU_DECRYPTED_AUTH_DATA@@3PEAPEAGPEAPEAU_SCARD_PIN@@@Z`
- size: `6066`
- prototype: `__int64 __fastcall(unsigned __int8, struct _ApPluginPkg *, unsigned __int16 *, struct _DECRYPTED_AUTH_DATA *, unsigned __int16 **, unsigned __int16 **, struct _SCARD_PIN **)`
- caller_count: `5`
- callee_count: `25`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800035b4`
- `0x180011960`
- `0x180017780`
- `0x180047c70`
- `0x180058090`

## callees

- `0x180007690`
- `0x180007fc0`
- `0x18000a600`
- `0x18000b0c0`
- `0x18000b9b0`
- `0x180029650`
- `0x18002f080`
- `0x180032884`
- `0x18003530c`
- `0x18003f6a0`
- `0x18003faf4`
- `0x1800403d4`
- `0x1800407a4`
- `0x180040a7c`
- `0x180040b30`
- `0x180042410`
- `0x1800427e0`
- `0x180052978`
- `0x180054ff4`
- `0x180061f84`
- `0x18007c610`
- `0x18007c93c`
- `0x18007eb90`
- `0x18007f9fc`
- `0x180081010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x18002a5d3`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x18002aa01`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x18002a5d3`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x18002aa01`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029ce8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029e83`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a0d7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a15d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a1e1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a2b6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a35c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002acaf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029ce8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029e83`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a0d7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a15d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a1e1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a2b6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a35c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002acaf`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180029aba`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180029aba`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180029cde`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18002aca5`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180029cde`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18002aca5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180029879`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180029879`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002986b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002986b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002a90e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002a90e`
- `CRYPT32!CertCloseStore` at `0x18002adbe`
- `CRYPT32!CertCloseStore` at `0x18002adbe`
- `CRYPT32!CertFreeCertificateContext` at `0x18002999c`
- `CRYPT32!CertFreeCertificateContext` at `0x18002999c`
- `CRYPT32!CertGetCertificateContextProperty` at `0x18002a2ac`
- `CRYPT32!CertGetCertificateContextProperty` at `0x18002a352`
- `CRYPT32!CertGetCertificateContextProperty` at `0x18002a2ac`
- `CRYPT32!CertGetCertificateContextProperty` at `0x18002a352`
- `CRYPT32!CertSetCertificateContextProperty` at `0x18002a1d7`
- `CRYPT32!CertSetCertificateContextProperty` at `0x18002a1d7`
- `CRYPT32!CertFindCertificateInStore` at `0x18002a14b`
- `CRYPT32!CertFindCertificateInStore` at `0x18002a14b`
- `CRYPT32!CertOpenStore` at `0x18002a0c5`
- `CRYPT32!CertOpenStore` at `0x18002a0c5`
- `ncrypt!NCryptFreeObject` at `0x18002ad5b`
- `ncrypt!NCryptFreeObject` at `0x18002ad6a`
- `ncrypt!NCryptFreeObject` at `0x18002ad5b`
- `ncrypt!NCryptFreeObject` at `0x18002ad6a`
- `ncrypt!NCryptOpenStorageProvider` at `0x18002a231`
- `ncrypt!NCryptOpenStorageProvider` at `0x18002a3b1`
- `ncrypt!NCryptOpenStorageProvider` at `0x18002a231`
- `ncrypt!NCryptOpenStorageProvider` at `0x18002a3b1`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptReleaseContext` at `0x1800299bf`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptReleaseContext` at `0x1800299bf`
- `ntdll!RtlReleaseResource` at `0x18002a9b8`
- `ntdll!RtlReleaseResource` at `0x18002ab0e`
- `ntdll!RtlReleaseResource` at `0x18002abfe`
- `ntdll!RtlReleaseResource` at `0x18002a9b8`
- `ntdll!RtlReleaseResource` at `0x18002ab0e`
- `ntdll!RtlReleaseResource` at `0x18002abfe`
- `ntdll!RtlAcquireResourceShared` at `0x18002a766`
- `ntdll!RtlAcquireResourceShared` at `0x18002a766`

## string_xrefs

- `0x18002a7b2`: `onecore\ds\ext\cloudap\dll\utils.cpp`
- `0x18002a8d2`: `onecore\ds\ext\cloudap\dll\utils.cpp`
- `0x18002a91e`: `onecore\ds\ext\cloudap\dll\utils.cpp`
- `0x18002abbb`: `onecore\ds\ext\cloudap\dll\utils.cpp`
- `0x180029768`: `onecore\ds\ext\cloudap\dll\logonapi.cpp`
- `0x180029f32`: `onecore\ds\ext\cloudap\dll\logonapi.cpp`
- `0x18002ad19`: `onecore\ds\ext\cloudap\dll\logonapi.cpp`
- `0x18002a8ad`: `Name2Sid`
- `0x18002ac2b`: `FindUserInCacheByName`
- `0x18002a930`: `RegOpenKeyExW`
- `0x180029ae5`: `ImpersonateClient`
- `0x180029d0d`: `SetThreadToken`
- `0x18002acd7`: `SetThreadToken`
- `0x18002a0fc`: `CertOpenStore`
- `0x18002a251`: `NCryptOpenStorageProvider`
- `0x18002a3cd`: `NCryptOpenStorageProvider`

## pseudocode

```c
__int64 __fastcall ConvertAuthDataToAuthDataInt(
        unsigned __int8 a1,
        struct _ApPluginPkg *a2,
        unsigned __int16 *a3,
        struct _DECRYPTED_AUTH_DATA *a4,
        unsigned __int16 **a5,
        unsigned __int16 **a6,
        struct _SCARD_PIN **a7)
{
  struct _ApPluginPkg *v7; // rbx
  char v8; // r12
  struct _DECRYPTED_AUTH_DATA *v9; // r15
  unsigned __int16 *v10; // r14
  int v11; // r13d
  __int64 v12; // rcx
  unsigned int v13; // r9d
  __int64 v14; // rax
  unsigned int v15; // edx
  __int64 v16; // r15
  unsigned int v17; // eax
  unsigned int v18; // ecx
  size_t v19; // r14
  unsigned int CertContextFromCSPEx; // ebx
  const char *v21; // r9
  struct _SCARD_PIN *v22; // r13
  HANDLE v23; // r15
  unsigned __int8 *v24; // rsi
  unsigned int v25; // r14d
  CSCLogonInit *v26; // rdi
  __int64 v27; // rdx
  unsigned __int8 *v28; // rax
  int v29; // r8d
  const char *v30; // r9
  const char *v31; // r9
  __int64 v32; // rcx
  unsigned __int8 *v33; // rax
  unsigned __int8 *v34; // r12
  const char *v35; // r9
  const char *v36; // r9
  const char *v37; // rax
  unsigned __int8 *v38; // rbx
  CSCLogonInit *v39; // rcx
  __int64 v40; // rcx
  NCRYPT_PROV_HANDLE v41; // rcx
  unsigned int KeySpecFromCSPInfo; // eax
  unsigned int v43; // r9d
  unsigned __int8 *v44; // r8
  NCRYPT_HANDLE v45; // r10
  const char *v46; // r9
  unsigned __int16 *CSPName; // rax
  const char *v48; // rax
  const char *v49; // r9
  signed int v50; // eax
  const char *v51; // rax
  struct _SCARD_PIN **v52; // r14
  const char *v53; // rax
  struct _SCARD_PIN *v54; // r15
  __int64 v55; // rax
  const char *v56; // r9
  signed int v57; // eax
  const char *v58; // r9
  const char *v59; // r9
  const char *v60; // r9
  const char *v61; // r9
  char v62; // al
  const char *v63; // rcx
  bool v64; // zf
  const char *v65; // r9
  const char *v66; // r9
  const char *v67; // r9
  __int64 v68; // rcx
  unsigned int v69; // edx
  unsigned int v70; // eax
  const char *v71; // r9
  unsigned int v72; // r8d
  signed int LastError; // eax
  const char *v74; // r9
  __int64 v75; // rcx
  const CERT_CONTEXT *CertificateInStore; // rax
  __int64 v77; // rdx
  const struct _CERT_CONTEXT *v78; // r13
  signed int v79; // eax
  const char *v80; // r9
  signed int v81; // eax
  const char *v82; // r9
  const char *v83; // r9
  const char *v84; // rax
  __int64 v85; // r8
  signed int v86; // eax
  const char *v87; // r9
  _BYTE *v88; // rax
  LPCWSTR *v89; // rbx
  const char *v90; // r9
  signed int v91; // eax
  const char *v92; // r9
  const char *v93; // r9
  const char *v94; // r9
  __int64 v95; // rax
  const char *v96; // r9
  const char *v97; // r9
  const char *v98; // r9
  const char *v99; // r9
  struct _SEC_WINNT_AUTH_PACKED_CREDENTIALS *v100; // rax
  const char *v101; // r9
  const wchar_t *v102; // rcx
  bool v103; // r13
  unsigned __int16 *v104; // r9
  const char *v105; // rax
  const char *v106; // r9
  const char *v107; // r9
  unsigned __int16 *v108; // rbx
  struct _ApPluginPkg *v109; // r12
  HKEY v110; // r14
  const UCHAR *v111; // rax
  char v112; // cl
  const UCHAR *v113; // rdx
  __int64 v114; // r10
  const char *v115; // r15
  __int64 v116; // r8
  int v117; // ecx
  WCHAR *v118; // rdx
  _WORD *v119; // rcx
  const char *v120; // r9
  const char *v121; // r9
  const char *v122; // rax
  unsigned __int16 *v123; // r12
  const char *v124; // rax
  const char *v125; // rax
  unsigned int v126; // r15d
  unsigned __int16 **v127; // r14
  unsigned __int16 *v128; // rcx
  const char *v129; // r9
  __int64 v130; // r8
  unsigned __int16 *v131; // rax
  unsigned __int16 **v132; // rcx
  const char *v133; // rax
  char v134; // al
  const char *v135; // rcx
  bool v136; // zf
  const char *v137; // r9
  signed int v138; // eax
  unsigned int v139; // r14d
  const char *v140; // rax
  char v141; // al
  _BYTE *v142; // rdx
  __int64 v143; // rcx
  _BYTE *v144; // rax
  void *pvPara; // [rsp+28h] [rbp-E0h]
  void *pvParaa; // [rsp+28h] [rbp-E0h]
  int pvParab; // [rsp+28h] [rbp-E0h]
  void *pvParac; // [rsp+28h] [rbp-E0h]
  const char *pPrevCertContext; // [rsp+30h] [rbp-D8h]
  const char *pPrevCertContexta; // [rsp+30h] [rbp-D8h]
  char v152; // [rsp+48h] [rbp-C0h]
  wchar_t *Str; // [rsp+50h] [rbp-B8h]
  struct _SCARD_PIN *v154; // [rsp+58h] [rbp-B0h]
  char v155; // [rsp+60h] [rbp-A8h]
  HANDLE hObject; // [rsp+68h] [rbp-A0h] BYREF
  DWORD pcbData[2]; // [rsp+70h] [rbp-98h] BYREF
  unsigned __int16 *v158; // [rsp+78h] [rbp-90h] BYREF
  unsigned __int16 *v159; // [rsp+80h] [rbp-88h] BYREF
  HCRYPTPROV hProv; // [rsp+88h] [rbp-80h] BYREF
  PCCERT_CONTEXT pCertContext; // [rsp+90h] [rbp-78h]
  NCRYPT_PROV_HANDLE phProvider; // [rsp+98h] [rbp-70h] BYREF
  unsigned int v163; // [rsp+A0h] [rbp-68h]
  unsigned int v164; // [rsp+A4h] [rbp-64h]
  struct _SEC_WINNT_AUTH_PACKED_CREDENTIALS *v165; // [rsp+A8h] [rbp-60h]
  struct _DECRYPTED_AUTH_DATA *v166; // [rsp+B0h] [rbp-58h]
  unsigned __int16 *v167; // [rsp+B8h] [rbp-50h] BYREF
  unsigned __int16 *v168; // [rsp+C0h] [rbp-48h] BYREF
  unsigned __int16 *v169; // [rsp+C8h] [rbp-40h]
  unsigned __int16 *v170; // [rsp+D0h] [rbp-38h]
  unsigned __int8 *v171; // [rsp+D8h] [rbp-30h]
  struct _CERT_CONTEXT *v172; // [rsp+E0h] [rbp-28h] BYREF
  struct _SCARD_PIN *v173; // [rsp+E8h] [rbp-20h] BYREF
  struct _ApPluginPkg *v174; // [rsp+F0h] [rbp-18h]
  HKEY hKey; // [rsp+F8h] [rbp-10h] BYREF
  unsigned __int16 *v176; // [rsp+100h] [rbp-8h]
  unsigned __int16 **v177; // [rsp+108h] [rbp+0h]
  _BYTE *v178; // [rsp+110h] [rbp+8h]
  HCERTSTORE hCertStore; // [rsp+118h] [rbp+10h]
  struct _SCARD_PIN **v180; // [rsp+120h] [rbp+18h]
  unsigned __int16 **v181; // [rsp+128h] [rbp+20h]
  __int128 pvFindPara; // [rsp+130h] [rbp+28h] BYREF
  __int128 pvData; // [rsp+140h] [rbp+38h] BYREF
  __int64 v184; // [rsp+150h] [rbp+48h]
  WCHAR SubKey[80]; // [rsp+158h] [rbp+50h] BYREF
  unsigned __int16 v186[72]; // [rsp+1F8h] [rbp+F0h] BYREF

  v7 = a2;
  v8 = 0;
  v174 = a2;
  v9 = a4;
  v166 = a4;
  v180 = a7;
  v10 = 0;
  v11 = a1;
  v176 = a3;
  v177 = a5;
  v181 = a6;
  v163 = 0;
  v164 = 0;
  pcbData[0] = 0;
  v184 = 0;
  v159 = 0;
  v169 = 0;
  v167 = 0;
  Str = 0;
  v158 = 0;
  v170 = 0;
  v168 = 0;
  v165 = 0;
  v171 = 0;
  phProvider = 0;
  hProv = 0;
  pCertContext = 0;
  v172 = 0;
  v178 = 0;
  hObject = 0;
  hCertStore = 0;
  v154 = 0;
  v173 = 0;
  hKey = 0;
  pvFindPara = 0;
  pvData = 0;
  if ( !a4 || !a5 || !*((_QWORD *)a4 + 2) || !a6 )
  {
    CertContextFromCSPEx = -1073741811;
    v61 = "";
    while ( 1 )
    {
      v141 = *(v61 - 1);
      v63 = v61--;
      v64 = v141 == 92;
      if ( v141 == 92 )
        break;
      if ( v61 <= "onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp" )
      {
        v64 = v141 == 92;
        break;
      }
    }
    pPrevCertContext = "Null Arg(s)";
    pvParab = 10112;
    goto LABEL_100;
  }
  *(_OWORD *)a5 = 0;
  a5[2] = 0;
  *a6 = 0;
  v12 = *((_QWORD *)a4 + 2);
  v155 = 0;
  if ( SEC_WINNT_AUTH_DATA_TYPE_NGC != *(_OWORD *)(v12 + 4) )
  {
LABEL_107:
    v68 = *((_QWORD *)v9 + 2);
    v152 = 0;
    if ( SEC_WINNT_AUTH_DATA_TYPE_CREDMAN_CERT == *(_QWORD *)(v68 + 4) && *(_QWORD *)(v68 + 12) == 0x3ADDB7A12A4D878CLL )
    {
      v69 = *(unsigned __int16 *)(v68 + 2);
      v70 = *(_DWORD *)(v68 + 20);
      if ( v70 > v69 )
      {
        CertContextFromCSPEx = -1073739509;
        v71 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
        WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", 3221227787LL, v71, 10328, "Bad NGC Data length 6", &Class);
        goto LABEL_230;
      }
      v72 = *(unsigned __int16 *)(v68 + 24);
      if ( v72 + v70 < v70 )
      {
        CertContextFromCSPEx = -1073741675;
        v98 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
        WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", 3221225621LL, v98, 10335, "RtlULongAdd", &Class);
        goto LABEL_230;
      }
      if ( v72 + v70 > v69 || v72 < 0x14 )
      {
        CertContextFromCSPEx = -1073739509;
        v97 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
        WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", 3221227787LL, v97, 10343, "Bad NGC Data length 7", &Class);
        goto LABEL_230;
      }
      hCertStore = CertOpenStore((LPCSTR)0xA, 0, 0, 0x10000u, L"MY");
      if ( !hCertStore )
      {
        LastError = GetLastError();
        CertContextFromCSPEx = LastError;
        if ( LastError > 0 )
          CertContextFromCSPEx = (unsigned __int16)LastError | 0xC0070000;
        v74 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
        LODWORD(pvParac) = 10358;
        WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", CertContextFromCSPEx, v74, pvParac, "CertOpenStore", &Class);
        goto LABEL_230;
      }
      v75 = *((_QWORD *)v9 + 2);
      LODWORD(pvFindPara) = *(unsigned __int16 *)(v75 + 24);
      *((_QWORD *)&pvFindPara + 1) = v75 + *(unsigned int *)(v75 + 20);
      CertificateInStore = CertFindCertificateInStore(hCertStore, 0x10001u, 0, 0x10000u, &pvFindPara, 0);
      pCertContext = CertificateInStore;
      v78 = CertificateInStore;
      if ( !CertificateInStore )
      {
        v79 = GetLastError();
        CertContextFromCSPEx = v79;
        if ( v79 > 0 )
          CertContextFromCSPEx = (unsigned __int16)v79 | 0xC0070000;
        v80 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
        LODWORD(pvPara) = 10377;
        WPPTraceLogA(
          0,
          "0x%08x %s:%u : %s:%ws",
          CertContextFromCSPEx,
          v80,
          pvPara,
          "CertFindCertificateInStore",
          &Class);
        goto LABEL_230;
      }
      if ( (unsigned int)SCardCertToNgc(CertificateInStore, v77, &hProv) )
      {
        v84 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
        LODWORD(pvPara) = 10417;
        WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", v85, v84, pvPara, "SCardCertToNgc", &Class);
        if ( !CertGetCertificateContextProperty(v78, 2u, 0, pcbData) )
        {
          v86 = GetLastError();
          CertContextFromCSPEx = v86;
          if ( v86 > 0 )
            CertContextFromCSPEx = (unsigned __int16)v86 | 0xC0070000;
          v87 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
          LODWORD(pvPara) = 10432;
          WPPTraceLogA(
            0,
            "0x%08x %s:%u : %s:%ws",
            CertContextFromCSPEx,
            v87,
            pvPara,
            "CertGetCertificateContextProperty",
            &Class);
          goto LABEL_69;
        }
        v88 = (_BYTE *)((__int64 (__fastcall *)(_QWORD))g_pLsaFunctionTable->AllocateLsaHeap)(pcbData[0]);
        v178 = v88;
        v89 = (LPCWSTR *)v88;
        if ( !v88 )
        {
          CertContextFromCSPEx = -1073741801;
          v90 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
          LODWORD(pvPara) = 10439;
          WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", 3221225495LL, v90, pvPara, "AllocateLsaHeap", &Class);
          goto LABEL_69;
        }
        if ( !CertGetCertificateContextProperty(v78, 2u, v88, pcbData) )
        {
          v91 = GetLastError();
          CertContextFromCSPEx = v91;
          if ( v91 > 0 )
            CertContextFromCSPEx = (unsigned __int16)v91 | 0xC0070000;
          v92 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
          LODWORD(pvPara) = 10450;
          WPPTraceLogA(
            0,
            "0x%08x %s:%u : %s:%ws",
            CertContextFromCSPEx,
            v92,
            pvPara,
            "CertGetCertificateContextProperty",
            &Class);
          goto LABEL_69;
        }
        if ( ((*((_DWORD *)v89 + 10) + 1) & 0xFFFFFFFE) == 0 )
        {
          CertContextFromCSPEx = NCryptOpenStorageProvider(&phProvider, v89[1], 0);
          if ( CertContextFromCSPEx )
          {
            v93 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
            LODWORD(pvPara) = 10460;
            WPPTraceLogA(
              0,
              "0x%08x %s:%u : %s:%ws",
              CertContextFromCSPEx,
              v93,
              pvPara,
              "NCryptOpenStorageProvider",
              &Class);
            goto LABEL_69;
          }
        }
      }
      else
      {
        *((_QWORD *)&pvData + 1) = hProv;
        LODWORD(pvData) = 24;
        LODWORD(v184) = -1;
        if ( !CertSetCertificateContextProperty(v78, 5u, 0, &pvData) )
        {
          v81 = GetLastError();
          CertContextFromCSPEx = v81;
          if ( v81 > 0 )
            CertContextFromCSPEx = (unsigned __int16)v81 | 0xC0070000;
          v82 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
          LODWORD(pvPara) = 10402;
          WPPTraceLogA(
            0,
            "0x%08x %s:%u : %s:%ws",
            CertContextFromCSPEx,
            v82,
            pvPara,
            "CertSetCertificateContextProperty",
            &Class);
          goto LABEL_69;
        }
        hProv = 0;
        CertContextFromCSPEx = NCryptOpenStorageProvider(&phProvider, L"Microsoft Passport Key Storage Provider", 0);
        if ( CertContextFromCSPEx )
        {
          v83 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
          LODWORD(pvPara) = 10413;
          WPPTraceLogA(
            0,
            "0x%08x %s:%u : %s:%ws",
            CertContextFromCSPEx,
            v83,
            pvPara,
            "NCryptOpenStorageProvider",
            &Class);
          goto LABEL_69;
        }
      }
      CertContextFromCSPEx = TestAcquirePrivateKey(v78);
      if ( CertContextFromCSPEx )
      {
        v94 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
        LODWORD(pvPara) = 10466;
        WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", CertContextFromCSPEx, v94, pvPara, "TestAcquirePrivateKey", &Class);
        goto LABEL_69;
      }
      v95 = ((__int64 (__fastcall *)(__int64))g_pLsaFunctionTable->AllocateLsaHeap)(52);
      v165 = (struct _SEC_WINNT_AUTH_PACKED_CREDENTIALS *)v95;
      if ( !v95 )
      {
        CertContextFromCSPEx = -1073741801;
        v96 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
        LODWORD(pvPara) = 10473;
        WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", 3221225495LL, v96, pvPara, "AllocateLsaHeap", &Class);
        goto LABEL_69;
      }
      v7 = v174;
      *(_DWORD *)v95 = 3407900;
      *(_WORD *)(v95 + 24) = 24;
      v8 = 1;
      *(_DWORD *)(v95 + 20) = 28;
      v10 = (unsigned __int16 *)(v95 + 28);
      *(_OWORD *)(v95 + 4) = SEC_WINNT_AUTH_DATA_TYPE_SMARTCARD_CONTEXTS;
      *(_QWORD *)(v95 + 36) = phProvider;
      phProvider = 0;
      *(_QWORD *)(v95 + 28) = pCertContext;
      pCertContext = 0;
      *(_QWORD *)(v95 + 44) = 0;
    }
    else
    {
      if ( SEC_WINNT_AUTH_DATA_TYPE_SMARTCARD_CONTEXTS == *(_OWORD *)(v68 + 4) )
      {
        CertContextFromCSPEx = -1073739509;
        v99 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
        WPPTraceLogA(
          0,
          "0x%08x %s:%u : %s:%ws",
          3221227787LL,
          v99,
          10491,
          "AuthData.CredType SEC_WINNT_AUTH_DATA_TYPE_SMARTCARD_CONTEXTS only allowed to be generated internally",
          &Class);
        goto LABEL_230;
      }
      v100 = (struct _SEC_WINNT_AUTH_PACKED_CREDENTIALS *)((__int64 (__fastcall *)(_QWORD))g_pLsaFunctionTable->AllocateLsaHeap)(*(unsigned __int16 *)(v68 + 2));
      v165 = v100;
      if ( !v100 )
      {
        CertContextFromCSPEx = -1073741801;
        v101 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
        WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", 3221225495LL, v101, 10499, "AllocateLsaHeap", &Class);
        goto LABEL_230;
      }
      memcpy_0(v100, *((const void **)v9 + 2), *(unsigned __int16 *)(*((_QWORD *)v9 + 2) + 2LL));
    }
    goto LABEL_154;
  }
  v13 = *(unsigned __int16 *)(v12 + 2);
  v14 = *(unsigned int *)(v12 + 20);
  if ( (unsigned int)v14 > v13 || (v15 = *(unsigned __int16 *)(v12 + 24), v15 < 0x2C) )
  {
    CertContextFromCSPEx = -1073739509;
    v67 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
    WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", 3221227787LL, v67, 10127, "Bad NGC Data length 1", &Class);
    goto LABEL_17;
  }
  if ( v15 + (unsigned int)v14 < (unsigned int)v14 )
  {
    CertContextFromCSPEx = -1073741675;
    v66 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
    WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", 3221225621LL, v66, 10134, "RtlDWordAdd", &Class);
    goto LABEL_17;
  }
  if ( v15 + (unsigned int)v14 > v13 )
  {
    CertContextFromCSPEx = -1073739509;
    v65 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
    WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", 3221227787LL, v65, 10142, "Bad NGC Data length 2", &Class);
    goto LABEL_17;
  }
  v16 = v12 + v14;
  if ( (*(_BYTE *)(v12 + v14 + 8) & 4) == 0 )
  {
    v9 = v166;
    goto LABEL_107;
  }
  v17 = *(_DWORD *)(v16 + 12);
  if ( v17 > v15 || (v18 = *(_DWORD *)(v16 + 20), v18 > v15) )
  {
    CertContextFromCSPEx = -1073739509;
    v61 = "";
    while ( 1 )
    {
      v62 = *(v61 - 1);
      v63 = v61--;
      v64 = v62 == 92;
      if ( v62 == 92 )
        break;
      if ( v61 <= "onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp" )
      {
        v64 = v62 == 92;
        break;
      }
    }
    pPrevCertContext = "Bad NGC Data length 3";
    pvParab = 10156;
LABEL_100:
    if ( v64 )
      v61 = v63;
    WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", CertContextFromCSPEx, v61, pvParab, pPrevCertContext, &Class);
    goto LABEL_17;
  }
  v19 = *(unsigned __int16 *)(v16 + 16);
  if ( (unsigned int)v19 + v17 < v17 )
  {
    CertContextFromCSPEx = -1073741675;
    v60 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
    WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", 3221225621LL, v60, 10163, "RtlDWordAdd", &Class);
    goto LABEL_16;
  }
  if ( (unsigned int)v19 + v17 > v15 )
  {
    CertContextFromCSPEx = -1073739509;
    v21 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
    WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", 3221227787LL, v21, 10168, "Bad NGC Data length 4", &Class);
LABEL_16:
    v10 = 0;
LABEL_17:
    v22 = 0;
LABEL_18:
    v23 = hObject;
    goto LABEL_19;
  }
  v29 = *(unsigned __int16 *)(v16 + 24);
  if ( v29 + v18 < v18 )
  {
    CertContextFromCSPEx = -1073741675;
    v59 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
    WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", 3221225621LL, v59, 10175, "RtlDWordAdd", &Class);
    goto LABEL_16;
  }
  if ( v29 + v18 > v15 )
  {
    CertContextFromCSPEx = -1073739509;
    v30 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
    WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", 3221227787LL, v30, 10180, "Bad NGC Data length 4", &Class);
    goto LABEL_16;
  }
  if ( (v29 & 1) != 0 )
  {
    CertContextFromCSPEx = -1073739509;
    v31 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
    WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", 3221227787LL, v31, 10186, "Bad NGC Data length 5", &Class);
    goto LABEL_16;
  }
  v32 = *(unsigned __int16 *)(v16 + 16);
  v163 = *(unsigned __int16 *)(v16 + 16);
  v33 = (unsigned __int8 *)((__int64 (__fastcall *)(__int64))g_pLsaFunctionTable->AllocateLsaHeap)(v32);
  v171 = v33;
  v34 = v33;
  if ( !v33 )
  {
    CertContextFromCSPEx = -1073741801;
    v35 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
    WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", 3221225495LL, v35, 10195, "AllocateLsaHeap", &Class);
LABEL_52:
    v8 = 0;
    goto LABEL_16;
  }
  memcpy_0(v33, (const void *)(v16 + *(unsigned int *)(v16 + 12)), v19);
  SetLastError(0);
  if ( (_BYTE)v11 )
  {
    CertContextFromCSPEx = ImpersonateClient(&hObject);
    if ( CertContextFromCSPEx )
    {
      v36 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
      WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", CertContextFromCSPEx, v36, 10206, "ImpersonateClient", &Class);
      goto LABEL_52;
    }
    v155 = 1;
  }
  CertContextFromCSPEx = ScHelperInitializeContextEx(v34, (unsigned int)v19);
  if ( !CertContextFromCSPEx )
  {
    v8 = 1;
    if ( (unsigned int)v19 >= 0x28
      && (v38 = v171, *(_DWORD *)v171 == (_DWORD)v19)
      && (v39 = (CSCLogonInit *)*((_QWORD *)v171 + 1)) != 0 )
    {
      hProv = CSCLogonInit::CryptCtx(v39, v171, v19);
      if ( hProv )
      {
        if ( *(_DWORD *)v38 == (_DWORD)v19 && (v40 = *((_QWORD *)v38 + 1)) != 0 )
          v41 = *(_QWORD *)(v40 + 16);
        else
          v41 = 0;
        phProvider = v41;
        KeySpecFromCSPInfo = ScHelperGetKeySpecFromCSPInfo(v38, (unsigned int)v19);
        v43 = *(unsigned __int16 *)(v16 + 24);
        v44 = (unsigned __int8 *)(v16 + *(unsigned int *)(v16 + 20));
        v164 = KeySpecFromCSPInfo;
        CertContextFromCSPEx = SetScardPin(v45, KeySpecFromCSPInfo, v44, v43);
        if ( CertContextFromCSPEx )
        {
          v46 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
          WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", CertContextFromCSPEx, v46, 10241, "SetScardPin", &Class);
LABEL_69:
          v10 = 0;
          goto LABEL_230;
        }
        CSPName = (unsigned __int16 *)GetCSPName(v171, v19);
        CertContextFromCSPEx = ScHelperGetCertContextFromCSPEx(hProv, v164, CSPName, (__int64)&v172);
        if ( CertContextFromCSPEx )
        {
          v48 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
          LODWORD(pvPara) = 10249;
          WPPTraceLogA(
            0,
            "0x%08x %s:%u : %s:%ws",
            CertContextFromCSPEx,
            v48,
            pvPara,
            "ScHelperGetCertContextFromCSPEx",
            &Class);
          v10 = 0;
          pCertContext = v172;
          goto LABEL_230;
        }
        hProv = 0;
        pCertContext = v172;
        CertContextFromCSPEx = TestAcquirePrivateKey(v172);
        if ( CertContextFromCSPEx )
        {
          v49 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
          LODWORD(pvPara) = 10256;
          WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", CertContextFromCSPEx, v49, pvPara, "TestAcquirePrivateKey", &Class);
          goto LABEL_69;
        }
        if ( v155 )
        {
          if ( !SetThreadToken(0, hObject) )
          {
            v50 = GetLastError();
            CertContextFromCSPEx = v50;
            if ( v50 > 0 )
              CertContextFromCSPEx = (unsigned __int16)v50 | 0xC0070000;
            v51 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
            LODWORD(pvPara) = 10264;
            WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", CertContextFromCSPEx, v51, pvPara, "SetThreadToken", &Class);
            v22 = 0;
            goto LABEL_232;
          }
          v155 = 0;
        }
        v52 = v180;
        if ( v180 )
        {
          CertContextFromCSPEx = AllocScardPin(
                                   (unsigned __int8 *)(v16 + *(unsigned int *)(v16 + 20)),
                                   *(unsigned __int16 *)(v16 + 24),
                                   v11,
                                   &v173);
          if ( CertContextFromCSPEx )
          {
            v53 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
            LODWORD(pvPara) = 10280;
            WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", CertContextFromCSPEx, v53, pvPara, "AllocScardPin", &Class);
            v22 = v173;
            v10 = 0;
            goto LABEL_231;
          }
          v54 = v173;
          v154 = v173;
          ((void (__fastcall *)(_QWORD, _QWORD))g_pLsaFunctionTable->LsaProtectMemory)(
            *(_QWORD *)v173,
            *((unsigned int *)v173 + 2));
          *v52 = v54;
        }
        v55 = ((__int64 (__fastcall *)(__int64))g_pLsaFunctionTable->AllocateLsaHeap)(52);
        v165 = (struct _SEC_WINNT_AUTH_PACKED_CREDENTIALS *)v55;
        if ( !v55 )
        {
          CertContextFromCSPEx = -1073741801;
          v56 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
          LODWORD(pvPara) = 10296;
          WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", 3221225495LL, v56, pvPara, "AllocateLsaHeap", &Class);
          goto LABEL_69;
        }
        v9 = v166;
        v10 = (unsigned __int16 *)(v55 + 28);
        v7 = v174;
        *(_DWORD *)v55 = 3407900;
        *(_DWORD *)(v55 + 20) = 28;
        *(_WORD *)(v55 + 24) = 24;
        *(_OWORD *)(v55 + 4) = SEC_WINNT_AUTH_DATA_TYPE_SMARTCARD_CONTEXTS;
        *(_QWORD *)(v55 + 36) = phProvider;
        phProvider = 0;
        *(_QWORD *)(v55 + 28) = pCertContext;
        pCertContext = 0;
        *(_QWORD *)(v55 + 44) = 0;
        v152 = 1;
LABEL_154:
        v102 = (const wchar_t *)*((_QWORD *)v9 + 1);
        v103 = 0;
        if ( v102 && *v102 && wcschr(v102, 0x40u) || (*((_BYTE *)v7 + 160) & 1) != 0 )
        {
          v10 = 0;
        }
        else
        {
          if ( !v176 )
            goto LABEL_171;
          v104 = (unsigned __int16 *)*((_QWORD *)v9 + 1);
          if ( !v104 || !*v104 )
            goto LABEL_171;
          CertContextFromCSPEx = ConvertNameToUPN(v7, v176, 1, v104, &v159, &v158);
          if ( (CertContextFromCSPEx & 0x80000000) != 0 )
          {
            if ( CertContextFromCSPEx == -1073741801 || CertContextFromCSPEx == -1073741670 )
            {
              v106 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
              LODWORD(pvPara) = 10532;
              WPPTraceLogA(
                0,
                "0x%08x %s:%u : %s:%ws",
                CertContextFromCSPEx,
                v106,
                pvPara,
                "ConvertSAMNameToUPN error. Aborting.",
                &Class);
              goto LABEL_170;
            }
            v105 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
            LODWORD(pvPara) = 10536;
            WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", CertContextFromCSPEx, v105, pvPara, "ConvertSAMNameToUPN", &Class);
          }
          else
          {
            v103 = 1;
          }
          Str = v158;
          if ( v158 && *v158 )
          {
            v10 = v158;
          }
          else
          {
LABEL_171:
            if ( v8 )
            {
              CertContextFromCSPEx = GetUpnFromScardCert(
                                       (struct _SEC_WINNT_AUTH_DATA_TYPE_SMARTCARD_CONTEXTS_DATA *const)v10,
                                       &v159,
                                       &v158);
              if ( CertContextFromCSPEx )
              {
                v107 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
                LODWORD(pvPara) = 10547;
                WPPTraceLogA(
                  0,
                  "0x%08x %s:%u : %s:%ws",
                  CertContextFromCSPEx,
                  v107,
                  pvPara,
                  "GetUpnFromScardCert",
                  &Class);
                goto LABEL_170;
              }
              v10 = v158;
              v103 = 1;
              Str = v158;
            }
            else
            {
              v10 = Str;
            }
          }
          if ( v10 && *v10 )
          {
            v108 = Str;
LABEL_179:
            RtlAcquireResourceShared(&g_LookupsCacheLock, 1u);
            v109 = v174;
            hKey = 0;
            v110 = (HKEY)*((_QWORD *)v174 + 44);
            if ( v110 && v108 )
            {
              CertContextFromCSPEx = GetHashString(v108, v186);
              if ( CertContextFromCSPEx )
              {
                v111 = "";
                do
                {
                  v112 = *(v111 - 1);
                  v113 = v111--;
                }
                while ( v112 != 92 && v111 > "onecore\\ds\\ext\\cloudap\\dll\\utils.cpp" );
                v114 = 0;
                v115 = "GetHashString";
                v64 = v112 == 92;
                v116 = CertContextFromCSPEx;
                v117 = 1279;
                if ( v64 )
                  v111 = v113;
                v118 = (WCHAR *)&Class;
              }
              else
              {
                CertContextFromCSPEx = RtlStringCchPrintfW(SubKey, 0x4Au, L"%ws\\%ws", L"Name2Sid", v186);
                if ( CertContextFromCSPEx )
                {
                  v111 = (const UCHAR *)_DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\utils.cpp");
                  v118 = (WCHAR *)&Class;
                  v115 = "RtlStringCchPrintfW";
                  v117 = 1287;
                }
                else
                {
                  CertContextFromCSPEx = RegOpenKeyExW(v110, SubKey, 0, 0x20019u, &hKey);
                  if ( !CertContextFromCSPEx )
                  {
                    RtlReleaseResource(&g_LookupsCacheLock);
                    v123 = Str;
LABEL_214:
                    v127 = v177;
                    v128 = v159;
                    if ( !v103 )
                      v128 = *(unsigned __int16 **)v9;
                    CertContextFromCSPEx = DuplicateString(v128, 0, v177);
                    if ( !CertContextFromCSPEx )
                    {
                      v131 = v159;
                      CertContextFromCSPEx = 0;
                      v127[2] = (unsigned __int16 *)v165;
                      v132 = v181;
                      v127[1] = v123;
                      v10 = 0;
                      Str = 0;
                      v165 = 0;
                      *v132 = v131;
                      v159 = 0;
                      goto LABEL_229;
                    }
                    v129 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
                    v130 = CertContextFromCSPEx;
                    pPrevCertContexta = "DuplicateString";
                    LODWORD(pvParaa) = 10659;
                    goto LABEL_218;
                  }
                  v122 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\utils.cpp");
                  v115 = "RegOpenKeyExW";
                  LODWORD(pvParaa) = 1298;
                  WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", CertContextFromCSPEx, v122, pvParaa, "RegOpenKeyExW", SubKey);
                  if ( CertContextFromCSPEx - 2 <= 1 )
                  {
                    CertContextFromCSPEx = -1073741275;
                  }
                  else if ( (int)CertContextFromCSPEx > 0 )
                  {
                    CertContextFromCSPEx = (unsigned __int16)CertContextFromCSPEx | 0xC0070000;
                  }
                  v111 = (const UCHAR *)_DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\utils.cpp");
                  v118 = SubKey;
                  v117 = 1308;
                }
              }
              LODWORD(pvPara) = v117;
              WPPTraceLogA(v114, "0x%08x %s:%u : %s:%ws", v116, v111, pvPara, v115, v118);
              RtlReleaseResource(&g_LookupsCacheLock);
              if ( CertContextFromCSPEx == -1073741275 )
              {
                v10 = Str;
                CertContextFromCSPEx = ConvertNameToUPN(v109, v176, 0, Str, &v167, &v168);
                if ( (CertContextFromCSPEx & 0x80000000) == 0 )
                {
                  v103 = wcschr(Str, 0x5Cu) != 0;
                  ((void (__fastcall *)(unsigned __int16 *))g_pLsaFunctionTable->FreeLsaHeap)(v159);
                  ((void (__fastcall *)(wchar_t *))g_pLsaFunctionTable->FreeLsaHeap)(Str);
                  v123 = v168;
                  v159 = v167;
                  v169 = 0;
                  v170 = 0;
                  Str = v168;
LABEL_213:
                  v9 = v166;
                  goto LABEL_214;
                }
                if ( CertContextFromCSPEx != -1073741801 && CertContextFromCSPEx != -1073741670 )
                {
                  v124 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
                  LODWORD(pvParaa) = 10640;
                  WPPTraceLogA(
                    0,
                    "0x%08x %s:%u : %s:%ws",
                    CertContextFromCSPEx,
                    v124,
                    pvParaa,
                    "ConvertAliasToUPN",
                    &Class);
                  v123 = Str;
                  v169 = v167;
                  v170 = v168;
                  goto LABEL_213;
                }
                v125 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
                LODWORD(pvParaa) = 10636;
                WPPTraceLogA(
                  0,
                  "0x%08x %s:%u : %s:%ws",
                  CertContextFromCSPEx,
                  v125,
                  pvParaa,
                  "ConvertAliasToUPN",
                  &Class);
                v169 = v167;
                v170 = v168;
LABEL_229:
                v8 = v152;
                goto LABEL_230;
              }
              v126 = CertContextFromCSPEx;
            }
            else
            {
              CertContextFromCSPEx = -1073741811;
              v126 = -1073741811;
              v133 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\utils.cpp");
              LODWORD(pvPara) = 1273;
              WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", 3221225485LL, v133, pvPara, "Invalid Arg(s)", &Class);
              RtlReleaseResource(&g_LookupsCacheLock);
            }
            v129 = "";
            while ( 1 )
            {
              v134 = *(v129 - 1);
              v135 = v129--;
              v136 = v134 == 92;
              if ( v134 == 92 )
                break;
              if ( v129 <= "onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp" )
              {
                v136 = v134 == 92;
                break;
              }
            }
            pPrevCertContexta = "FindUserInCacheByName";
            if ( v136 )
              v129 = v135;
            LODWORD(pvParaa) = 10646;
            v130 = v126;
LABEL_218:
            WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", v130, v129, pvParaa, pPrevCertContexta, &Class);
            v10 = Str;
            goto LABEL_229;
          }
        }
        v119 = (_WORD *)*((_QWORD *)v9 + 1);
        if ( !v119 || !*v119 )
        {
          CertContextFromCSPEx = -1073741715;
          v137 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
          LODWORD(pvPara) = 10586;
          WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", 3221225581LL, v137, pvPara, "no username", &Class);
          goto LABEL_229;
        }
        CertContextFromCSPEx = DuplicateString(*(const unsigned __int16 **)v9, 0, &v159);
        if ( CertContextFromCSPEx )
        {
          v120 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
          LODWORD(pvPara) = 10575;
          WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", CertContextFromCSPEx, v120, pvPara, "DuplicateString", &Class);
          goto LABEL_229;
        }
        CertContextFromCSPEx = DuplicateString(*((const unsigned __int16 **)v9 + 1), 1, &v158);
        if ( !CertContextFromCSPEx )
        {
          v108 = v158;
          Str = v158;
          goto LABEL_179;
        }
        v121 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
        LODWORD(pvPara) = 10581;
        WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", CertContextFromCSPEx, v121, pvPara, "DuplicateString", &Class);
LABEL_170:
        v10 = v158;
        Str = v158;
        goto LABEL_229;
      }
    }
    else
    {
      hProv = 0;
    }
    v57 = GetLastError();
    CertContextFromCSPEx = v57;
    if ( v57 )
    {
      if ( v57 <= 0 )
      {
LABEL_92:
        v58 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
        WPPTraceLogA(
          0,
          "0x%08x %s:%u : %s:%ws",
          CertContextFromCSPEx,
          v58,
          10229,
          "ScHelperGetHPROVOrKeyHandleFromCSPInfo",
          &Class);
        goto LABEL_69;
      }
    }
    else
    {
      LOWORD(CertContextFromCSPEx) = 1264;
    }
    CertContextFromCSPEx = (unsigned __int16)CertContextFromCSPEx | 0xC0070000;
    goto LABEL_92;
  }
  v37 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
  WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", CertContextFromCSPEx, v37, 10217, "ScHelperInitializeContextEx", &Class);
  v10 = 0;
  v8 = 0;
LABEL_230:
  v22 = v154;
LABEL_231:
  if ( !v155 )
    goto LABEL_18;
LABEL_232:
  v23 = hObject;
  if ( !SetThreadToken(0, hObject) )
  {
    v138 = GetLastError();
    v139 = v138;
    if ( v138 > 0 )
      v139 = (unsigned __int16)v138 | 0xC0070000;
    v140 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
    LODWORD(pvParaa) = 10676;
    WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", v139, v140, pvParaa, "SetThreadToken", &Class);
    if ( (CertContextFromCSPEx & 0x80000000) == 0 )
      CertContextFromCSPEx = v139;
  }
  v10 = Str;
LABEL_19:
  if ( hKey )
    RegCloseKey(hKey);
  if ( v23 )
    CloseHandle(v23);
  if ( v159 )
    ((void (*)(void))g_pLsaFunctionTable->FreeLsaHeap)();
  if ( v10 )
    ((void (__fastcall *)(unsigned __int16 *))g_pLsaFunctionTable->FreeLsaHeap)(v10);
  if ( v169 )
    ((void (*)(void))g_pLsaFunctionTable->FreeLsaHeap)();
  if ( v170 )
    ((void (*)(void))g_pLsaFunctionTable->FreeLsaHeap)();
  FreePackedCreds(v165);
  v24 = v171;
  if ( v171 )
  {
    v25 = v163;
    if ( v8 )
    {
      if ( v163 >= 0x28 && *(_DWORD *)v171 == v163 )
      {
        v26 = (CSCLogonInit *)*((_QWORD *)v171 + 1);
        *((_QWORD *)v171 + 1) = 0;
        if ( v26 )
        {
          CSCLogonInit::Release(v26);
          CSCLogonInit::Release(v26);
          operator delete(v26, (const struct std::nothrow_t *)0x20);
        }
      }
    }
    v27 = v25;
    v28 = v24;
    if ( v25 )
    {
      do
      {
        *v28++ = 0;
        --v27;
      }
      while ( v27 );
    }
    ((void (__fastcall *)(unsigned __int8 *, __int64))g_pLsaFunctionTable->FreeLsaHeap)(v24, v27);
  }
  if ( pCertContext )
    CertFreeCertificateContext(pCertContext);
  if ( hProv )
  {
    if ( v164 - 1 > 0xFFFFFFFD )
      NCryptFreeObject(hProv);
    else
      CryptReleaseContext(hProv, 0);
  }
  if ( phProvider )
    NCryptFreeObject(phProvider);
  v142 = v178;
  if ( v178 )
  {
    v143 = pcbData[0];
    v144 = v178;
    if ( pcbData[0] )
    {
      do
      {
        *v144++ = 0;
        --v143;
      }
      while ( v143 );
    }
    ((void (__fastcall *)(_BYTE *))g_pLsaFunctionTable->FreeLsaHeap)(v142);
  }
  if ( hCertStore )
    CertCloseStore(hCertStore, 0);
  if ( (CertContextFromCSPEx & 0x80000000) != 0 )
  {
    if ( v22 )
    {
      FreeScardPin(v22);
      if ( v180 )
        *v180 = 0;
    }
  }
  return CertContextFromCSPEx;
}

```

## disassembly

```asm
0x180029650  mov     r11, rsp
0x180029653  push    rbp
0x180029654  push    rbx
0x180029655  push    r13
0x180029657  lea     rbp, [r11-1D8h]
0x18002965e  sub     rsp, 2C0h
0x180029665  mov     rax, cs:__security_cookie
0x18002966c  xor     rax, rsp
0x18002966f  mov     [rbp+1D0h+var_50], rax
0x180029676  mov     rax, [rbp+1D0h+arg_20]
0x18002967d  mov     rbx, rdx
0x180029680  mov     [r11-20h], rsi
0x180029684  xorps   xmm0, xmm0
0x180029687  mov     [r11-28h], rdi
0x18002968b  xorps   xmm1, xmm1
0x18002968e  mov     [r11-30h], r12
0x180029692  xor     r12b, r12b
0x180029695  mov     [rbp+1D0h+var_1E8], rdx
0x180029699  mov     rdx, [rbp+1D0h+arg_30]
0x1800296a0  mov     [r11-38h], r14
0x1800296a4  mov     [r11-40h], r15
0x1800296a8  mov     r15, r9
0x1800296ab  mov     [rbp+1D0h+var_228], r9
0x1800296af  xor     r9d, r9d
0x1800296b2  mov     [rbp+1D0h+var_1B8], rdx
0x1800296b6  mov     r14d, r9d
0x1800296b9  xor     edx, edx
0x1800296bb  movzx   r13d, cl
0x1800296bf  mov     rcx, [rbp+1D0h+arg_28]
0x1800296c6  mov     [rbp+1D0h+var_1D8], r8
0x1800296ca  mov     [rbp+1D0h+var_1D0], rax
0x1800296ce  mov     [rbp+1D0h+var_1B0], rcx
0x1800296d2  mov     [rbp+1D0h+var_238], r9d
0x1800296d6  mov     [rbp+1D0h+var_234], r9d
0x1800296da  mov     [rsp+2D0h+pcbData], r9d
0x1800296df  mov     [rbp+1D0h+var_188], rdx
0x1800296e3  mov     [rsp+2D0h+var_258], r9
0x1800296e8  mov     [rbp+1D0h+var_210], rdx
0x1800296ec  mov     [rbp+1D0h+var_220], rdx
0x1800296f0  mov     [rsp+2D0h+Str], r9
0x1800296f5  mov     [rsp+2D0h+var_260], r9
0x1800296fa  mov     [rbp+1D0h+var_208], rdx
0x1800296fe  mov     [rbp+1D0h+var_218], rdx
0x180029702  mov     [rbp+1D0h+var_230], r9
0x180029706  mov     [rbp+1D0h+var_200], r9
0x18002970a  mov     [rbp+1D0h+phProvider], r9
0x18002970e  mov     [rbp+1D0h+hProv], r9
0x180029712  mov     [rbp+1D0h+pCertContext], rdx
0x180029716  mov     [rbp+1D0h+var_1F8], rdx
0x18002971a  mov     [rbp+1D0h+var_1C8], r9
0x18002971e  mov     [rsp+2D0h+hObject], r9
0x180029723  mov     [rbp+1D0h+hCertStore], r9
0x180029727  mov     [rsp+2D0h+var_280], rdx
0x18002972c  mov     [rbp+1D0h+var_1F0], rdx
0x180029730  mov     [rbp+1D0h+hKey], r9
0x180029734  movups  [rbp+1D0h+pvFindPara], xmm0
0x180029738  movups  [rbp+1D0h+pvData], xmm1
0x18002973c  test    r15, r15
0x18002973f  jz      loc_18002AD0D
0x180029745  test    rax, rax
0x180029748  jz      loc_18002AD0D
0x18002974e  cmp     [r15+10h], rdx
0x180029752  jz      loc_18002AD0D
0x180029758  test    rcx, rcx
0x18002975b  jz      loc_18002AD0D
0x180029761  movups  xmmword ptr [rax], xmm0
0x180029764  mov     [rax+10h], rdx
0x180029768  lea     rdi, aOnecoreDsExtCl_6; "onecore\\ds\\ext\\cloudap\\dll\\logonap"...
0x18002976f  mov     [rcx], r9
0x180029772  lea     rsi, Class
0x180029779  mov     rcx, [r15+10h]
0x18002977d  mov     rax, qword ptr cs:SEC_WINNT_AUTH_DATA_TYPE_NGC
0x180029784  mov     byte ptr [rsp+2D0h+var_278], dl
0x180029788  cmp     rax, [rcx+4]
0x18002978c  jnz     loc_18002A011
0x180029792  mov     rax, qword ptr cs:SEC_WINNT_AUTH_DATA_TYPE_NGC+8
0x180029799  cmp     rax, [rcx+0Ch]
0x18002979d  jnz     loc_18002A011
0x1800297a3  movzx   r9d, word ptr [rcx+2]
0x1800297a8  mov     eax, [rcx+14h]
0x1800297ab  cmp     eax, r9d
0x1800297ae  ja      loc_180029FDF
0x1800297b4  movzx   edx, word ptr [rcx+18h]
0x1800297b8  cmp     edx, 2Ch ; ','
0x1800297bb  jb      loc_180029FDF
0x1800297c1  lea     r8d, [rdx+rax]
0x1800297c5  cmp     r8d, eax
0x1800297c8  jb      loc_180029FB4
0x1800297ce  cmp     r8d, r9d
0x1800297d1  ja      loc_180029F89
0x1800297d7  test    byte ptr [rcx+rax+8], 4
0x1800297dc  lea     r15, [rcx+rax]
0x1800297e0  jz      loc_18002A00D
0x1800297e6  mov     eax, [r15+0Ch]
0x1800297ea  cmp     eax, edx
0x1800297ec  ja      loc_180029F26
0x1800297f2  mov     ecx, [r15+14h]
0x1800297f6  cmp     ecx, edx
0x1800297f8  ja      loc_180029F26
0x1800297fe  movzx   r14d, word ptr [r15+10h]
0x180029803  lea     r8d, [r14+rax]
0x180029807  cmp     r8d, eax
0x18002980a  jb      loc_180029EF8
0x180029810  cmp     r8d, edx
0x180029813  jbe     loc_1800299CA
0x180029819  mov     rcx, rdi; char *
0x18002981c  mov     ebx, 0C000090Bh
0x180029821  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180029826  mov     [rsp+30h], rsi
0x18002982b  mov     r9, rax
0x18002982e  lea     rax, aBadNgcDataLeng; "Bad NGC Data length 4"
0x180029835  mov     [rsp+2D0h+pPrevCertContext], rax
0x18002983a  mov     dword ptr [rsp+2D0h+pvPara], 27B8h
0x180029842  mov     r8d, ebx
0x180029845  lea     rdx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x18002984c  xor     ecx, ecx
0x18002984e  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x180029853  mov     r14, [rsp+2D0h+Str]
0x180029858  mov     r13, [rsp+2D0h+var_280]
0x18002985d  mov     r15, [rsp+2D0h+hObject]
0x180029862  mov     rcx, [rbp+1D0h+hKey]; hKey
0x180029866  test    rcx, rcx
0x180029869  jz      short loc_180029871
0x18002986b  call    cs:__imp_RegCloseKey
0x180029871  test    r15, r15
0x180029874  jz      short loc_18002987F
0x180029876  mov     rcx, r15; hObject
0x180029879  call    cs:__imp_CloseHandle
0x18002987f  mov     rcx, [rsp+2D0h+var_258]
0x180029884  mov     r15, [rsp+2D0h+var_38]
0x18002988c  test    rcx, rcx
0x18002988f  jz      short loc_1800298A1
0x180029891  mov     rax, cs:?g_pLsaFunctionTable@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * g_pLsaFunctionTable
0x180029898  mov     rax, [rax+30h]
0x18002989c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800298a1  test    r14, r14
0x1800298a4  jz      short loc_1800298B9
0x1800298a6  mov     rax, cs:?g_pLsaFunctionTable@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * g_pLsaFunctionTable
0x1800298ad  mov     rcx, r14
0x1800298b0  mov     rax, [rax+30h]
0x1800298b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800298b9  mov     rcx, [rbp+1D0h+var_210]
0x1800298bd  test    rcx, rcx
0x1800298c0  jz      short loc_1800298D2
0x1800298c2  mov     rax, cs:?g_pLsaFunctionTable@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * g_pLsaFunctionTable
0x1800298c9  mov     rax, [rax+30h]
0x1800298cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800298d2  mov     rcx, [rbp+1D0h+var_208]
0x1800298d6  test    rcx, rcx
0x1800298d9  jz      short loc_1800298EB
0x1800298db  mov     rax, cs:?g_pLsaFunctionTable@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * g_pLsaFunctionTable
0x1800298e2  mov     rax, [rax+30h]
0x1800298e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800298eb  mov     rcx, [rbp+1D0h+var_230]; struct _SEC_WINNT_AUTH_PACKED_CREDENTIALS *
0x1800298ef  call    ?FreePackedCreds@@YAXPEAU_SEC_WINNT_AUTH_PACKED_CREDENTIALS@@@Z; FreePackedCreds(_SEC_WINNT_AUTH_PACKED_CREDENTIALS *)
0x1800298f4  mov     rsi, [rbp+1D0h+var_200]
0x1800298f8  test    rsi, rsi
0x1800298fb  jz      short loc_180029970
0x1800298fd  mov     r14d, [rbp+1D0h+var_238]
0x180029901  test    r12b, r12b
0x180029904  jz      short loc_18002993F
0x180029906  cmp     r14d, 28h ; '('
0x18002990a  jb      short loc_18002993F
0x18002990c  cmp     [rsi], r14d
0x18002990f  jnz     short loc_18002993F
0x180029911  mov     rdi, [rsi+8]
0x180029915  mov     qword ptr [rsi+8], 0
0x18002991d  test    rdi, rdi
0x180029920  jz      short loc_18002993F
0x180029922  mov     rcx, rdi; this
0x180029925  call    ?Release@CSCLogonInit@@QEAAXXZ; CSCLogonInit::Release(void)
0x18002992a  mov     rcx, rdi; this
0x18002992d  call    ?Release@CSCLogonInit@@QEAAXXZ; CSCLogonInit::Release(void)
0x180029932  mov     edx, 20h ; ' '; struct std::nothrow_t *
0x180029937  mov     rcx, rdi; void *
0x18002993a  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18002993f  mov     edx, r14d
0x180029942  mov     rax, rsi
0x180029945  test    r14d, r14d
0x180029948  jz      short loc_18002995D
0x18002994a  nop     word ptr [rax+rax+00h]
0x180029950  mov     byte ptr [rax], 0
0x180029953  lea     rax, [rax+1]
0x180029957  sub     rdx, 1
0x18002995b  jnz     short loc_180029950
0x18002995d  mov     rax, cs:?g_pLsaFunctionTable@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * g_pLsaFunctionTable
0x180029964  mov     rcx, rsi
0x180029967  mov     rax, [rax+30h]
0x18002996b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029970  mov     rax, [rbp+1D0h+pCertContext]
0x180029974  mov     r14, [rsp+2D0h+var_30]
0x18002997c  mov     r12, [rsp+2D0h+var_28]
0x180029984  mov     rdi, [rsp+2D0h+var_20]
0x18002998c  mov     rsi, [rsp+2B8h]
0x180029994  test    rax, rax
0x180029997  jz      short loc_1800299A2
0x180029999  mov     rcx, rax; pCertContext
0x18002999c  call    cs:__imp_CertFreeCertificateContext
0x1800299a2  mov     rcx, [rbp+1D0h+hProv]; hObject
0x1800299a6  test    rcx, rcx
0x1800299a9  jz      loc_18002AD61
0x1800299af  mov     eax, [rbp+1D0h+var_234]
0x1800299b2  dec     eax
0x1800299b4  cmp     eax, 0FFFFFFFDh
0x1800299b7  ja      loc_18002AD5B
0x1800299bd  xor     edx, edx; dwFlags
0x1800299bf  call    cs:__imp_CryptReleaseContext
0x1800299c5  jmp     loc_18002AD61
0x1800299ca  movzx   r8d, word ptr [r15+18h]
0x1800299cf  lea     eax, [r8+rcx]
0x1800299d3  cmp     eax, ecx
0x1800299d5  jb      loc_180029ECA
0x1800299db  cmp     eax, edx
0x1800299dd  jbe     short loc_180029A0D
0x1800299df  mov     rcx, rdi; char *
0x1800299e2  mov     ebx, 0C000090Bh
0x1800299e7  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x1800299ec  mov     [rsp+30h], rsi
0x1800299f1  mov     r9, rax
0x1800299f4  lea     rax, aBadNgcDataLeng; "Bad NGC Data length 4"
0x1800299fb  mov     [rsp+2D0h+pPrevCertContext], rax
0x180029a00  mov     dword ptr [rsp+2D0h+pvPara], 27C4h
0x180029a08  jmp     loc_180029842
0x180029a0d  test    r8b, 1
0x180029a11  jz      short loc_180029A41
0x180029a13  mov     rcx, rdi; char *
0x180029a16  mov     ebx, 0C000090Bh
0x180029a1b  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180029a20  mov     [rsp+30h], rsi
0x180029a25  mov     r9, rax
0x180029a28  lea     rax, aBadNgcDataLeng_0; "Bad NGC Data length 5"
0x180029a2f  mov     [rsp+2D0h+pPrevCertContext], rax
0x180029a34  mov     dword ptr [rsp+2D0h+pvPara], 27CAh
0x180029a3c  jmp     loc_180029842
0x180029a41  mov     rax, cs:?g_pLsaFunctionTable@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * g_pLsaFunctionTable
0x180029a48  mov     ecx, r14d
0x180029a4b  mov     [rbp+1D0h+var_238], r14d
0x180029a4f  mov     rax, [rax+28h]
0x180029a53  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029a58  mov     [rbp+1D0h+var_200], rax
0x180029a5c  mov     r12, rax
0x180029a5f  test    rax, rax
0x180029a62  jnz     short loc_180029AA6
0x180029a64  mov     rcx, rdi; char *
0x180029a67  mov     ebx, 0C0000017h
0x180029a6c  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180029a71  mov     [rsp+30h], rsi
0x180029a76  mov     r9, rax
0x180029a79  lea     rax, aAllocatelsahea_3; "AllocateLsaHeap"
0x180029a80  mov     [rsp+2D0h+pPrevCertContext], rax
0x180029a85  mov     dword ptr [rsp+2D0h+pvPara], 27D3h
0x180029a8d  mov     r8d, ebx
0x180029a90  lea     rdx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x180029a97  xor     ecx, ecx
0x180029a99  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x180029a9e  xor     r12b, r12b
0x180029aa1  jmp     loc_180029853
0x180029aa6  mov     edx, [r15+0Ch]
0x180029aaa  mov     r8, r14; Size
0x180029aad  add     rdx, r15; Src
0x180029ab0  mov     rcx, r12; void *
0x180029ab3  call    memcpy_0
0x180029ab8  xor     ecx, ecx; dwErrCode
0x180029aba  call    cs:__imp_SetLastError
0x180029ac0  test    r13b, r13b
0x180029ac3  jz      short loc_180029B00
0x180029ac5  lea     rcx, [rsp+2D0h+hObject]; void **
0x180029aca  call    ?ImpersonateClient@@YAJPEAPEAX@Z; ImpersonateClient(void * *)
0x180029acf  mov     ebx, eax
0x180029ad1  test    eax, eax
0x180029ad3  jz      short loc_180029AFB
0x180029ad5  mov     rcx, rdi; char *
0x180029ad8  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180029add  mov     [rsp+30h], rsi
0x180029ae2  mov     r9, rax
0x180029ae5  lea     rax, aImpersonatecli; "ImpersonateClient"
0x180029aec  mov     [rsp+2D0h+pPrevCertContext], rax
0x180029af1  mov     dword ptr [rsp+2D0h+pvPara], 27DEh
0x180029af9  jmp     short loc_180029A8D
0x180029afb  mov     byte ptr [rsp+2D0h+var_278], 1
0x180029b00  mov     edx, r14d
0x180029b03  mov     rcx, r12
0x180029b06  call    ScHelperInitializeContextEx
0x180029b0b  mov     ebx, eax
0x180029b0d  test    eax, eax
0x180029b0f  jz      short loc_180029B53
0x180029b11  mov     rcx, rdi; char *
0x180029b14  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180029b19  mov     r9, rax
0x180029b1c  mov     [rsp+30h], rsi
0x180029b21  lea     rax, aSchelperinitia; "ScHelperInitializeContextEx"
0x180029b28  mov     r8d, ebx
0x180029b2b  mov     [rsp+2D0h+pPrevCertContext], rax
0x180029b30  lea     rdx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x180029b37  xor     ecx, ecx
0x180029b39  mov     dword ptr [rsp+2D0h+pvPara], 27E9h
0x180029b41  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x180029b46  mov     r14, [rsp+2D0h+Str]
0x180029b4b  xor     r12b, r12b
0x180029b4e  jmp     loc_18002AC8B
  ... truncated ...
```
