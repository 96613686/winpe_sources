# CertificateUtil::FindAllCertificatesByOidValue(_CERTFICATE_LOCATION,char const * * const,ushort const * * const,_CERT_OID_VALUE_TYPE * const,ulong,_CERT_CONTEXT const * * const,ulong *)

- ea: `0x18000d4f4`
- end: `0x18000db0a`
- name: `?FindAllCertificatesByOidValue@CertificateUtil@@SAJW4_CERTFICATE_LOCATION@@QEAPEBDQEAPEBGQEAW4_CERT_OID_VALUE_TYPE@@KQEAPEBU_CERT_CONTEXT@@PEAK@Z`
- size: `1558`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180026a24`

## callees

- `0x1800084f4`
- `0x180008530`
- `0x1800086b0`
- `0x18000bac0`
- `0x18000d4f4`
- `0x18000f070`
- `0x180012948`
- `0x18001df5c`
- `0x1800307c4`
- `0x18008bc58`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d5bd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d72d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d5bd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d72d`
- `api-ms-win-core-registry-l1-1-0!RegUnLoadKeyW` at `0x18000d6d5`
- `api-ms-win-core-registry-l1-1-0!RegUnLoadKeyW` at `0x18000dad1`
- `api-ms-win-core-registry-l1-1-0!RegUnLoadKeyW` at `0x18000d6d5`
- `api-ms-win-core-registry-l1-1-0!RegUnLoadKeyW` at `0x18000dad1`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000d69e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000d9ec`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000d69e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000d9ec`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000da97`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000da97`
- `CRYPT32!CertFindExtension` at `0x18000d829`
- `CRYPT32!CertFindExtension` at `0x18000d829`
- `CRYPT32!CertOpenStore` at `0x18000d5a6`
- `CRYPT32!CertOpenStore` at `0x18000d5a6`
- `CRYPT32!CertFindCertificateInStore` at `0x18000d77d`
- `CRYPT32!CertFindCertificateInStore` at `0x18000d77d`
- `CRYPT32!CertCloseStore` at `0x18000d71f`
- `CRYPT32!CertCloseStore` at `0x18000d71f`
- `CRYPT32!CertDuplicateCertificateContext` at `0x18000d900`
- `CRYPT32!CertDuplicateCertificateContext` at `0x18000d900`
- `CRYPT32!CertFreeCertificateContext` at `0x18000da61`
- `CRYPT32!CertFreeCertificateContext` at `0x18000da61`

## string_xrefs

- `0x18000da10`: `CertificateUtil::DoesExtensionWithValueExist`
- `0x18000d5c6`: `%s: CertOpenStore failed with error code: 0x%08x`
- `0x18000d8c0`: `%s: FindExtensionByOid: pcszOid is NULL.`
- `0x18000d8b9`: `CertificateUtil::FindExtensionByOid`
- `0x18000d6bb`: `%s: Cannot open registry key "%s". RegOpenKeyExW error code: 0x%08x. Try loading the registry key...`
- `0x18000d9a5`: `%s: Cannot open registry key "%s". RegOpenKeyExW error code: 0x%08x.`

## pseudocode

```c
__int64 __fastcall CertificateUtil::FindAllCertificatesByOidValue(
        int a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        unsigned int a5,
        struct _CERT_CONTEXT **a6,
        unsigned int *a7)
{
  __int64 LastError; // rsi
  void *v8; // r12
  const CERT_CONTEXT *pPrevCertContext; // rbp
  __int64 v10; // r14
  int v11; // r13d
  signed int v12; // edi
  __int64 v13; // rcx
  const wchar_t *v14; // rax
  DWORD v15; // r9d
  const wchar_t *v16; // r9
  unsigned int v18; // eax
  unsigned int KeyW; // eax
  const unsigned __int16 *v20; // rdx
  HKEY v21; // rcx
  const unsigned __int16 *v22; // r8
  const unsigned __int16 *v23; // r9
  int KeyWinPE; // eax
  signed int v25; // eax
  unsigned int v26; // r13d
  int v27; // ebp
  __int64 i; // r12
  __int64 v29; // rdx
  const CHAR *v30; // rcx
  const wchar_t *v31; // r8
  int DoesExtensionWithValueExist; // eax
  const unsigned __int16 *v33; // rdx
  unsigned int v34; // eax
  unsigned int v35; // eax
  unsigned int v36; // eax
  void *pvPara; // [rsp+20h] [rbp-88h]
  unsigned int v38; // [rsp+30h] [rbp-78h]
  unsigned int v39; // [rsp+34h] [rbp-74h]
  int v40; // [rsp+38h] [rbp-70h] BYREF
  int v41; // [rsp+3Ch] [rbp-6Ch]
  int v42; // [rsp+40h] [rbp-68h]
  PCCERT_CONTEXT pCertContext; // [rsp+48h] [rbp-60h]
  HCERTSTORE v44; // [rsp+50h] [rbp-58h]
  HKEY phkResult[10]; // [rsp+58h] [rbp-50h] BYREF

  LODWORD(LastError) = 0;
  v8 = 0;
  v42 = 0;
  pPrevCertContext = 0;
  phkResult[0] = 0;
  v10 = 0;
  v39 = 0;
  v38 = 0;
  v41 = 0;
  v11 = a1;
  if ( !a2 )
  {
    v12 = -2147024809;
    Logger::TraceError(
      L"%s: \"%s\" should not be null.",
      L"CertificateUtil::FindAllCertificatesByOidValue",
      L"pcszOids");
    v33 = L"pcszOids";
LABEL_56:
    Logger::WriteNullOrEmptyParameterFailureEvent(L"CertificateUtil::FindAllCertificatesByOidValue", v33);
    goto LABEL_8;
  }
  if ( !a3 )
  {
    v12 = -2147024809;
    Logger::TraceError(
      L"%s: \"%s\" should not be null.",
      L"CertificateUtil::FindAllCertificatesByOidValue",
      L"pcszOidValues");
    v33 = L"pcszOidValues";
    goto LABEL_56;
  }
  if ( !a7 )
  {
    v12 = -2147024809;
    Logger::TraceError(
      L"%s: \"%s\" should not be null.",
      L"CertificateUtil::FindAllCertificatesByOidValue",
      L"pdwCount");
    v33 = L"pdwCount";
    goto LABEL_56;
  }
  v12 = 0;
  v39 = *a7;
  *a7 = 0;
  if ( a1 == 1 && (unsigned int)IsWinPEHost() )
  {
    Logger::TraceInformation(L"%s: System is WinPE.", L"CertificateUtil::FindAllCertificatesByOidValue");
    v18 = RegOpenKeyExW(
            HKEY_LOCAL_MACHINE,
            L"TargetSoftware\\Microsoft\\SystemCertificates\\MY",
            0,
            0x20019u,
            phkResult);
    LODWORD(LastError) = v18;
    if ( v18 )
    {
      Logger::TraceWarning(
        (wchar_t *)L"%s: Cannot open registry key \"%s\". RegOpenKeyExW error code: 0x%08x. Try loading the registry key...",
        L"CertificateUtil::FindAllCertificatesByOidValue",
        L"HKEY_LOCAL_MACHINE\\TargetSoftware\\Microsoft\\SystemCertificates\\MY",
        v18);
      KeyW = RegUnLoadKeyW(HKEY_LOCAL_MACHINE, L"TargetSoftware");
      if ( KeyW )
        Logger::TraceVerbose(
          (wchar_t *)L"%s: Always try unloading reg key \"%s\" first before loading it. RegUnLoadKeyW failed with error co"
                      "de: 0x%08x. Failure ignored. Continue to load the key...",
          L"CertificateUtil::FindAllCertificatesByOidValue",
          L"HKEY_LOCAL_MACHINE\\TargetSoftware",
          KeyW);
      KeyWinPE = RegLoadKeyWinPE(v21, v20, v22, v23);
      v12 = KeyWinPE;
      if ( KeyWinPE < 0 )
      {
        Logger::TraceError(
          L"%s: %s failed with error code: 0x%08x.",
          L"CertificateUtil::FindAllCertificatesByOidValue",
          L"RegLoadKeyWinPE",
          (unsigned int)KeyWinPE);
LABEL_59:
        v16 = L"LocalMachine";
        goto LABEL_11;
      }
      v42 = 1;
      v34 = RegOpenKeyExW(
              HKEY_LOCAL_MACHINE,
              L"TargetSoftware\\Microsoft\\SystemCertificates\\MY",
              0,
              0x20019u,
              phkResult);
      LODWORD(LastError) = v34;
      if ( v34 )
      {
        Logger::TraceError(
          L"%s: Cannot open registry key \"%s\". RegOpenKeyExW error code: 0x%08x.",
          L"CertificateUtil::FindAllCertificatesByOidValue",
          L"HKEY_LOCAL_MACHINE\\TargetSoftware\\Microsoft\\SystemCertificates\\MY",
          v34);
        goto LABEL_59;
      }
    }
    v14 = (const wchar_t *)phkResult[0];
    v15 = 0x8000;
    v13 = 4;
  }
  else
  {
    v13 = 10;
    v14 = L"My";
    v15 = v11 != 0 ? 163840 : 98304;
  }
  v44 = CertOpenStore((LPCSTR)v13, 0, 0, v15, v14);
  v8 = v44;
  if ( v44 )
  {
    v26 = 0;
LABEL_31:
    while ( 1 )
    {
      pCertContext = CertFindCertificateInStore(v8, 0x10001u, 0, 0, 0, pPrevCertContext);
      pPrevCertContext = pCertContext;
      if ( !pCertContext )
        break;
      ++v41;
      v27 = 1;
      v40 = 1;
      for ( i = 0; ; i = (unsigned int)(i + 1) )
      {
        v26 = v38;
        if ( !v27 )
        {
          pPrevCertContext = pCertContext;
          v8 = v44;
          goto LABEL_31;
        }
        if ( (unsigned int)i >= a5 )
          break;
        Logger::TraceVerbose(
          (wchar_t *)L"%s: Will try to find the OID: '%hs' and value: '%.*s'",
          L"CertificateUtil::FindAllCertificatesByOidValue",
          *(_QWORD *)(a2 + 8 * i),
          1024,
          *(_QWORD *)(a3 + 8 * i));
        v29 = *(_QWORD *)(a3 + 8 * i);
        v30 = *(const CHAR **)(a2 + 8 * i);
        if ( v29 )
        {
          pPrevCertContext = pCertContext;
          DoesExtensionWithValueExist = CertificateUtil::DoesExtensionWithValueExist(
                                          v30,
                                          v29,
                                          *(unsigned int *)(a4 + 4 * i),
                                          pCertContext,
                                          &v40);
          v12 = DoesExtensionWithValueExist;
          if ( DoesExtensionWithValueExist < 0 )
          {
            Logger::TraceError(
              L"%s: %s failed with error code: 0x%08x.",
              L"CertificateUtil::FindAllCertificatesByOidValue",
              L"CertificateUtil::DoesExtensionWithValueExist",
              (unsigned int)DoesExtensionWithValueExist);
            v8 = v44;
            goto LABEL_47;
          }
          v27 = v40;
        }
        else if ( v30 )
        {
          if ( CertFindExtension(v30, pCertContext->pCertInfo->cExtension, pCertContext->pCertInfo->rgExtension) )
            v27 = 0;
          v40 = v27;
        }
        else
        {
          Logger::TraceError(L"%s: FindExtensionByOid: pcszOid is NULL.", L"CertificateUtil::FindExtensionByOid");
        }
        v31 = L"TRUE";
        if ( !v27 )
          v31 = L"FALSE";
        Logger::TraceVerbose(
          (wchar_t *)L"%s: Cert matching: %s",
          L"CertificateUtil::FindAllCertificatesByOidValue",
          v31);
      }
      pPrevCertContext = pCertContext;
      v8 = v44;
      v26 = ++v38;
      if ( v39 > (unsigned int)v10 && a6 )
      {
        a6[v10] = (struct _CERT_CONTEXT *)CertDuplicateCertificateContext(pCertContext);
        v10 = (unsigned int)(v10 + 1);
      }
    }
    if ( v39 >= v26 && a6 )
    {
      *a7 = v10;
    }
    else
    {
      *a7 = v26;
      LODWORD(LastError) = 122;
    }
LABEL_47:
    v11 = a1;
  }
  else
  {
    LastError = GetLastError();
    Logger::TraceError(
      L"%s: CertOpenStore failed with error code: 0x%08x",
      L"CertificateUtil::FindAllCertificatesByOidValue",
      LastError);
  }
LABEL_8:
  if ( v11 )
  {
    if ( v11 != 1 )
    {
      v16 = L"Unknown";
      goto LABEL_11;
    }
    goto LABEL_59;
  }
  v16 = L"CurrentUser";
LABEL_11:
  LODWORD(pvPara) = v41;
  Logger::TraceVerbose(
    (wchar_t *)L"%s: %u total %s certificate(s) found. %u certificate(s) checked.",
    L"CertificateUtil::FindAllCertificatesByOidValue",
    v38,
    v16,
    pvPara);
  if ( (_DWORD)LastError )
  {
    if ( (int)LastError > 0 )
      v12 = (unsigned __int16)LastError | 0x80070000;
    else
      v12 = LastError;
  }
  if ( pPrevCertContext )
    CertFreeCertificateContext(pPrevCertContext);
  if ( v12 < 0 )
  {
    if ( v39 < (unsigned int)v10 )
      LODWORD(v10) = v39;
    CertificateUtil::FreeCertificates((const struct _CERT_CONTEXT **const)a6, v10);
  }
  if ( v8 && !CertCloseStore(v8, 0) )
  {
    v25 = GetLastError();
    if ( v25 > 0 )
      v25 = (unsigned __int16)v25 | 0x80070000;
    Logger::TraceWarning(
      (wchar_t *)L"%s: CertCloseStore failed with error code: 0x%08x",
      L"CertificateUtil::FindAllCertificatesByOidValue",
      (unsigned int)v25);
  }
  if ( phkResult[0] )
  {
    v35 = RegCloseKey(phkResult[0]);
    if ( v35 )
      Logger::TraceWarning(
        (wchar_t *)L"%s: Cannot close reg key %s. RegCloseKey failed with error code: 0x%08x.",
        L"CertificateUtil::FindAllCertificatesByOidValue",
        L"HKEY_LOCAL_MACHINE\\TargetSoftware\\Microsoft\\SystemCertificates\\MY",
        v35);
  }
  if ( v42 )
  {
    v36 = RegUnLoadKeyW(HKEY_LOCAL_MACHINE, L"TargetSoftware");
    if ( v36 )
      Logger::TraceWarning(
        (wchar_t *)L"%s: Cannot unload reg key %s. RegUnLoadKeyW failed with error code: 0x%08x.",
        L"CertificateUtil::FindAllCertificatesByOidValue",
        L"HKEY_LOCAL_MACHINE\\TargetSoftware",
        v36);
    else
      Logger::TraceVerbose(
        (wchar_t *)L"%s: reg key \"%s\" unloaded.",
        L"CertificateUtil::FindAllCertificatesByOidValue",
        L"HKEY_LOCAL_MACHINE\\TargetSoftware");
  }
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x18000d4f4  mov     rax, rsp
0x18000d4f7  mov     [rax+20h], r9
0x18000d4fb  mov     [rax+18h], r8
0x18000d4ff  mov     [rax+10h], rdx
0x18000d503  mov     [rax+8], ecx
0x18000d506  push    rbx
0x18000d507  push    rbp
0x18000d508  push    rsi
0x18000d509  push    rdi
0x18000d50a  push    r12
0x18000d50c  push    r13
0x18000d50e  push    r14
0x18000d510  push    r15
0x18000d512  sub     rsp, 68h
0x18000d516  xor     esi, esi
0x18000d518  lea     rbx, aCertificateuti; "CertificateUtil::FindAllCertificatesByO"...
0x18000d51f  xor     r12d, r12d
0x18000d522  mov     [rsp+0A8h+var_68], esi
0x18000d526  xor     ebp, ebp
0x18000d528  mov     [rsp+0A8h+phkResult], rsi
0x18000d52d  xor     r14d, r14d
0x18000d530  mov     [rsp+0A8h+var_74], esi
0x18000d534  mov     [rsp+0A8h+var_78], esi
0x18000d538  mov     rax, r8
0x18000d53b  mov     [rsp+0A8h+var_6C], esi
0x18000d53f  mov     r13d, ecx
0x18000d542  test    rdx, rdx
0x18000d545  jz      loc_18000D927
0x18000d54b  test    rax, rax
0x18000d54e  jz      loc_18000D97A
0x18000d554  mov     r15, [rsp+0A8h+arg_30]
0x18000d55c  test    r15, r15
0x18000d55f  jz      loc_18000D94B
0x18000d565  mov     eax, [r15]
0x18000d568  xor     edi, edi
0x18000d56a  mov     [rsp+0A8h+var_74], eax
0x18000d56e  mov     [r15], esi
0x18000d571  cmp     ecx, 1
0x18000d574  jz      loc_18000D661
0x18000d57a  mov     eax, r13d
0x18000d57d  mov     ecx, 0Ah; lpszStoreProvider
0x18000d582  neg     eax
0x18000d584  lea     rax, aMy; "My"
0x18000d58b  sbb     r9d, r9d
0x18000d58e  and     r9d, 10000h
0x18000d595  add     r9d, 18000h; dwFlags
0x18000d59c  xor     r8d, r8d; hCryptProv
0x18000d59f  mov     [rsp+0A8h+pvPara], rax; pvPara
0x18000d5a4  xor     edx, edx; dwEncodingType
0x18000d5a6  call    cs:__imp_CertOpenStore
0x18000d5ac  mov     [rsp+0A8h+var_58], rax
0x18000d5b1  mov     r12, rax
0x18000d5b4  test    rax, rax
0x18000d5b7  jnz     loc_18000D752
0x18000d5bd  call    cs:__imp_GetLastError
0x18000d5c3  mov     rdx, rbx
0x18000d5c6  lea     rcx, aSCertopenstore; "%s: CertOpenStore failed with error cod"...
0x18000d5cd  mov     r8d, eax
0x18000d5d0  mov     esi, eax
0x18000d5d2  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18000d5d7  test    r13d, r13d
0x18000d5da  jz      loc_18000DA47
0x18000d5e0  cmp     r13d, 1
0x18000d5e4  jz      loc_18000D9B7
0x18000d5ea  lea     r9, aUnknown_2; "Unknown"
0x18000d5f1  mov     eax, [rsp+0A8h+var_6C]
0x18000d5f5  lea     rcx, aSUTotalSCertif; "%s: %u total %s certificate(s) found. %"...
0x18000d5fc  mov     r8d, [rsp+0A8h+var_78]
0x18000d601  mov     rdx, rbx
0x18000d604  mov     dword ptr [rsp+0A8h+pvPara], eax
0x18000d608  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x18000d60d  mov     r15d, 80070000h
0x18000d613  test    esi, esi
0x18000d615  jnz     loc_18000D91A
0x18000d61b  test    rbp, rbp
0x18000d61e  jnz     loc_18000DA5E
0x18000d624  test    edi, edi
0x18000d626  js      loc_18000DA6C
0x18000d62c  test    r12, r12
0x18000d62f  jnz     loc_18000D71A
0x18000d635  mov     rcx, [rsp+0A8h+phkResult]; hKey
0x18000d63a  test    rcx, rcx
0x18000d63d  jnz     loc_18000DA97
0x18000d643  cmp     [rsp+0A8h+var_68], 0
0x18000d648  jnz     loc_18000DAC3
0x18000d64e  mov     eax, edi
0x18000d650  add     rsp, 68h
0x18000d654  pop     r15
0x18000d656  pop     r14
0x18000d658  pop     r13
0x18000d65a  pop     r12
0x18000d65c  pop     rdi
0x18000d65d  pop     rsi
0x18000d65e  pop     rbp
0x18000d65f  pop     rbx
0x18000d660  retn
0x18000d661  call    ?IsWinPEHost@@YAHXZ; IsWinPEHost(void)
0x18000d666  test    eax, eax
0x18000d668  jz      loc_18000D57A
0x18000d66e  mov     rdx, rbx
0x18000d671  lea     rcx, aSSystemIsWinpe; "%s: System is WinPE."
0x18000d678  call    ?TraceInformation@Logger@@SAJPEBGZZ; Logger::TraceInformation(ushort const *,...)
0x18000d67d  lea     rax, [rsp+0A8h+phkResult]
0x18000d682  mov     r9d, 20019h; samDesired
0x18000d688  xor     r8d, r8d; ulOptions
0x18000d68b  mov     [rsp+0A8h+pvPara], rax; phkResult
0x18000d690  lea     rdx, SubKey; "TargetSoftware\\Microsoft\\SystemCertif"...
0x18000d697  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000d69e  call    cs:__imp_RegOpenKeyExW
0x18000d6a4  mov     esi, eax
0x18000d6a6  test    eax, eax
0x18000d6a8  jz      loc_18000D9F8
0x18000d6ae  mov     r9d, eax
0x18000d6b1  lea     r8, aHkeyLocalMachi; "HKEY_LOCAL_MACHINE\\TargetSoftware\\Mic"...
0x18000d6b8  mov     rdx, rbx
0x18000d6bb  lea     rcx, aSCannotOpenReg; "%s: Cannot open registry key \"%s\". Re"...
0x18000d6c2  call    ?TraceWarning@Logger@@SAJPEBGZZ; Logger::TraceWarning(ushort const *,...)
0x18000d6c7  lea     rdx, aTargetsoftware_0; "TargetSoftware"
0x18000d6ce  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000d6d5  call    cs:__imp_RegUnLoadKeyW
0x18000d6db  test    eax, eax
0x18000d6dd  jz      short loc_18000D6F8
0x18000d6df  mov     r9d, eax
0x18000d6e2  lea     r8, aHkeyLocalMachi_5; "HKEY_LOCAL_MACHINE\\TargetSoftware"
0x18000d6e9  mov     rdx, rbx
0x18000d6ec  lea     rcx, aSAlwaysTryUnlo; "%s: Always try unloading reg key \"%s\""...
0x18000d6f3  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x18000d6f8  call    ?RegLoadKeyWinPE@@YAJPEAUHKEY__@@PEBG11@Z; RegLoadKeyWinPE(HKEY__ *,ushort const *,ushort const *,ushort const *)
0x18000d6fd  mov     edi, eax
0x18000d6ff  test    eax, eax
0x18000d701  jns     loc_18000D9C3
0x18000d707  lea     r8, aRegloadkeywinp; "RegLoadKeyWinPE"
0x18000d70e  lea     rcx, aSSFailedWithEr_2; "%s: %s failed with error code: 0x%08x."
0x18000d715  jmp     loc_18000D9AC
0x18000d71a  xor     edx, edx; dwFlags
0x18000d71c  mov     rcx, r12; hCertStore
0x18000d71f  call    cs:__imp_CertCloseStore
0x18000d725  test    eax, eax
0x18000d727  jnz     loc_18000D635
0x18000d72d  call    cs:__imp_GetLastError
0x18000d733  test    eax, eax
0x18000d735  jg      loc_18000DA8C
0x18000d73b  mov     r8d, eax
0x18000d73e  lea     rcx, aSCertclosestor_0; "%s: CertCloseStore failed with error co"...
0x18000d745  mov     rdx, rbx
0x18000d748  call    ?TraceWarning@Logger@@SAJPEBGZZ; Logger::TraceWarning(ushort const *,...)
0x18000d74d  jmp     loc_18000D635
0x18000d752  mov     r13d, ebp
0x18000d755  jmp     short loc_18000D761
0x18000d757  mov     rbp, [rsp+0A8h+pCertContext]
0x18000d75c  mov     r12, [rsp+0A8h+var_58]
0x18000d761  mov     [rsp+0A8h+pPrevCertContext], rbp; pPrevCertContext
0x18000d766  xor     r9d, r9d; dwFindType
0x18000d769  xor     r8d, r8d; dwFindFlags
0x18000d76c  mov     [rsp+0A8h+pvPara], 0; pvFindPara
0x18000d775  mov     edx, 10001h; dwCertEncodingType
0x18000d77a  mov     rcx, r12; hCertStore
0x18000d77d  call    cs:__imp_CertFindCertificateInStore
0x18000d783  mov     [rsp+0A8h+pCertContext], rax
0x18000d788  mov     rbp, rax
0x18000d78b  test    rax, rax
0x18000d78e  jz      loc_18000D899
0x18000d794  inc     [rsp+0A8h+var_6C]
0x18000d798  mov     ebp, 1
0x18000d79d  mov     [rsp+0A8h+var_70], ebp
0x18000d7a1  xor     r12d, r12d
0x18000d7a4  mov     r13d, [rsp+0A8h+var_78]
0x18000d7a9  test    ebp, ebp
0x18000d7ab  jz      short loc_18000D757
0x18000d7ad  cmp     r12d, [rsp+0A8h+arg_20]
0x18000d7b5  jnb     loc_18000D8D1
0x18000d7bb  mov     rax, [rsp+0A8h+arg_10]
0x18000d7c3  lea     rcx, aSWillTryToFind; "%s: Will try to find the OID: '%hs' and"...
0x18000d7ca  mov     r8, [rsp+0A8h+arg_8]
0x18000d7d2  mov     r9d, 400h
0x18000d7d8  mov     rdx, rbx
0x18000d7db  mov     rax, [rax+r12*8]
0x18000d7df  mov     r8, [r8+r12*8]
0x18000d7e3  mov     [rsp+0A8h+pvPara], rax
0x18000d7e8  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x18000d7ed  mov     rax, [rsp+0A8h+arg_10]
0x18000d7f5  mov     rdx, [rax+r12*8]
0x18000d7f9  mov     rax, [rsp+0A8h+arg_8]
0x18000d801  mov     rcx, [rax+r12*8]; pszObjId
0x18000d805  test    rdx, rdx
0x18000d808  jnz     short loc_18000D866
0x18000d80a  test    rcx, rcx
0x18000d80d  jz      loc_18000D8B9
0x18000d813  mov     rax, [rsp+0A8h+pCertContext]
0x18000d818  mov     rdx, [rax+18h]
0x18000d81c  mov     r8, [rdx+0C8h]; rgExtensions
0x18000d823  mov     edx, [rdx+0C0h]; cExtensions
0x18000d829  call    cs:__imp_CertFindExtension
0x18000d82f  xor     ecx, ecx
0x18000d831  test    rax, rax
0x18000d834  cmovnz  ebp, ecx
0x18000d837  mov     [rsp+0A8h+var_70], ebp
0x18000d83b  lea     rax, aFalse_0; "FALSE"
0x18000d842  test    ebp, ebp
0x18000d844  lea     r8, aTrue_0; "TRUE"
0x18000d84b  mov     rdx, rbx
0x18000d84e  cmovz   r8, rax
0x18000d852  lea     rcx, aSCertMatchingS; "%s: Cert matching: %s"
0x18000d859  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x18000d85e  inc     r12d
0x18000d861  jmp     loc_18000D7A4
0x18000d866  mov     rbp, [rsp+0A8h+pCertContext]
0x18000d86b  lea     rax, [rsp+0A8h+var_70]
0x18000d870  mov     [rsp+0A8h+pvPara], rax
0x18000d875  mov     r9, rbp
0x18000d878  mov     rax, [rsp+0A8h+arg_18]
0x18000d880  mov     r8d, [rax+r12*4]
0x18000d884  call    ?DoesExtensionWithValueExist@CertificateUtil@@SAJPEBDPEBGW4_CERT_OID_VALUE_TYPE@@PEBU_CERT_CONTEXT@@PEAH@Z; CertificateUtil::DoesExtensionWithValueExist(char const *,ushort const *,_CERT_OID_VALUE_TYPE,_CERT_CONTEXT const *,int *)
0x18000d889  mov     edi, eax
0x18000d88b  test    eax, eax
0x18000d88d  js      loc_18000DA0D
0x18000d893  mov     ebp, [rsp+0A8h+var_70]
0x18000d897  jmp     short loc_18000D83B
0x18000d899  cmp     [rsp+0A8h+var_74], r13d
0x18000d89e  jnb     loc_18000DA30
0x18000d8a4  mov     [r15], r13d
0x18000d8a7  mov     esi, 7Ah ; 'z'
0x18000d8ac  mov     r13d, [rsp+0A8h+arg_0]
0x18000d8b4  jmp     loc_18000D5D7
0x18000d8b9  lea     rdx, aCertificateuti_2; "CertificateUtil::FindExtensionByOid"
0x18000d8c0  lea     rcx, aSFindextension; "%s: FindExtensionByOid: pcszOid is NULL"...
0x18000d8c7  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18000d8cc  jmp     loc_18000D83B
0x18000d8d1  mov     rbp, [rsp+0A8h+pCertContext]
0x18000d8d6  mov     r12, [rsp+0A8h+var_58]
0x18000d8db  inc     r13d
0x18000d8de  mov     [rsp+0A8h+var_78], r13d
0x18000d8e3  cmp     [rsp+0A8h+var_74], r14d
0x18000d8e8  jbe     loc_18000D761
0x18000d8ee  cmp     [rsp+0A8h+arg_28], 0
0x18000d8f7  jz      loc_18000D761
0x18000d8fd  mov     rcx, rbp; pCertContext
0x18000d900  call    cs:__imp_CertDuplicateCertificateContext
0x18000d906  mov     rdx, [rsp+0A8h+arg_28]
0x18000d90e  mov     [rdx+r14*8], rax
0x18000d912  inc     r14d
0x18000d915  jmp     loc_18000D761
0x18000d91a  jg      loc_18000DA53
0x18000d920  mov     edi, esi
0x18000d922  jmp     loc_18000D61B
0x18000d927  lea     r8, aPcszoids; "pcszOids"
0x18000d92e  mov     rdx, rbx
0x18000d931  lea     rcx, aSSShouldNotBeN_0; "%s: \"%s\" should not be null."
0x18000d938  mov     edi, 80070057h
0x18000d93d  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18000d942  lea     rdx, aPcszoids; "pcszOids"
0x18000d949  jmp     short loc_18000D96D
0x18000d94b  lea     r8, aPdwcount; "pdwCount"
0x18000d952  mov     rdx, rbx
0x18000d955  lea     rcx, aSSShouldNotBeN_0; "%s: \"%s\" should not be null."
0x18000d95c  mov     edi, 80070057h
0x18000d961  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18000d966  lea     rdx, aPdwcount; "pdwCount"
0x18000d96d  mov     rcx, rbx; unsigned __int16 *
0x18000d970  call    ?WriteNullOrEmptyParameterFailureEvent@Logger@@SAJPEBG0@Z; Logger::WriteNullOrEmptyParameterFailureEvent(ushort const *,ushort const *)
0x18000d975  jmp     loc_18000D5D7
0x18000d97a  lea     r8, aPcszoidvalues; "pcszOidValues"
0x18000d981  mov     rdx, rbx
0x18000d984  lea     rcx, aSSShouldNotBeN_0; "%s: \"%s\" should not be null."
0x18000d98b  mov     edi, 80070057h
0x18000d990  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18000d995  lea     rdx, aPcszoidvalues; "pcszOidValues"
0x18000d99c  jmp     short loc_18000D96D
0x18000d99e  lea     r8, aHkeyLocalMachi; "HKEY_LOCAL_MACHINE\\TargetSoftware\\Mic"...
0x18000d9a5  lea     rcx, aSCannotOpenReg_0; "%s: Cannot open registry key \"%s\". Re"...
0x18000d9ac  mov     rdx, rbx
0x18000d9af  mov     r9d, eax
0x18000d9b2  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18000d9b7  lea     r9, aLocalmachine; "LocalMachine"
0x18000d9be  jmp     loc_18000D5F1
0x18000d9c3  lea     rax, [rsp+0A8h+phkResult]
0x18000d9c8  mov     [rsp+0A8h+var_68], 1
0x18000d9d0  mov     r9d, 20019h; samDesired
0x18000d9d6  mov     [rsp+0A8h+pvPara], rax; phkResult
0x18000d9db  xor     r8d, r8d; ulOptions
0x18000d9de  lea     rdx, SubKey; "TargetSoftware\\Microsoft\\SystemCertif"...
0x18000d9e5  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000d9ec  call    cs:__imp_RegOpenKeyExW
0x18000d9f2  mov     esi, eax
0x18000d9f4  test    eax, eax
0x18000d9f6  jnz     short loc_18000D99E
0x18000d9f8  mov     rax, [rsp+0A8h+phkResult]
0x18000d9fd  mov     r9d, 8000h
0x18000da03  mov     ecx, 4
0x18000da08  jmp     loc_18000D59C
0x18000da0d  mov     r9d, eax
0x18000da10  lea     r8, aCertificateuti_8; "CertificateUtil::DoesExtensionWithValue"...
0x18000da17  mov     rdx, rbx
0x18000da1a  lea     rcx, aSSFailedWithEr_2; "%s: %s failed with error code: 0x%08x."
0x18000da21  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18000da26  mov     r12, [rsp+0A8h+var_58]
0x18000da2b  jmp     loc_18000D8AC
0x18000da30  cmp     [rsp+0A8h+arg_28], 0
0x18000da39  jz      loc_18000D8A4
0x18000da3f  mov     [r15], r14d
  ... truncated ...
```
