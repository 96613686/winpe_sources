# CertificateUtil::FindAllCertificatesByOidValue(_CERTFICATE_LOCATION,char const * * const,ushort const * * const,_CERT_OID_VALUE_TYPE * const,ulong,_CERT_CONTEXT const * * const,ulong *)

- ea: `0x180013084`
- end: `0x1800135dd`
- name: `?FindAllCertificatesByOidValue@CertificateUtil@@SAJW4_CERTFICATE_LOCATION@@QEAPEBDQEAPEBGQEAW4_CERT_OID_VALUE_TYPE@@KQEAPEBU_CERT_CONTEXT@@PEAK@Z`
- size: `1369`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18002594c`

## callees

- `0x18000f8b8`
- `0x18000febc`
- `0x180010048`
- `0x180010218`
- `0x18001029c`
- `0x180013084`
- `0x1800135e4`
- `0x180024834`
- `0x1800249d4`
- `0x180024e68`
- `0x1800254a4`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegUnLoadKeyW` at `0x1800131e9`
- `api-ms-win-core-registry-l1-1-0!RegUnLoadKeyW` at `0x180013599`
- `api-ms-win-core-registry-l1-1-0!RegUnLoadKeyW` at `0x1800131e9`
- `api-ms-win-core-registry-l1-1-0!RegUnLoadKeyW` at `0x180013599`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800131b2`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180013265`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800131b2`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180013265`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180013561`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180013561`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800132d2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013535`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800132d2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013535`
- `CRYPT32!CertCloseStore` at `0x18001352b`
- `CRYPT32!CertCloseStore` at `0x18001352b`
- `CRYPT32!CertOpenStore` at `0x1800132bf`
- `CRYPT32!CertOpenStore` at `0x1800132bf`
- `CRYPT32!CertFreeCertificateContext` at `0x1800134fc`
- `CRYPT32!CertFreeCertificateContext` at `0x1800134fc`
- `CRYPT32!CertFindCertificateInStore` at `0x180013317`
- `CRYPT32!CertFindCertificateInStore` at `0x180013317`
- `CRYPT32!CertDuplicateCertificateContext` at `0x180013441`
- `CRYPT32!CertDuplicateCertificateContext` at `0x180013441`

## string_xrefs

- `0x1800131cf`: `%s: Cannot open registry key "%s". RegOpenKeyExW error code: 0x%08x. Try loading the registry key...`
- `0x1800132db`: `%s: CertOpenStore failed with error code: 0x%08x`
- `0x180013278`: `%s: Cannot open registry key "%s". RegOpenKeyExW error code: 0x%08x.`
- `0x18001345e`: `CertificateUtil::DoesExtensionWithValueExist`

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
  signed int v12; // edi
  const unsigned __int16 *v13; // rdx
  unsigned int v14; // eax
  unsigned int KeyW; // eax
  const unsigned __int16 *v16; // rdx
  HKEY v17; // rcx
  const unsigned __int16 *v18; // r8
  const unsigned __int16 *v19; // r9
  int KeyWinPE; // eax
  const wchar_t *p_hCertStore; // r9
  unsigned int v22; // eax
  const wchar_t *v23; // rax
  DWORD v24; // r9d
  __int64 v25; // rcx
  int v26; // ebp
  __int64 i; // r12
  __int64 v28; // rdx
  const char *v29; // rcx
  int DoesExtensionWithValueExist; // eax
  const wchar_t *v31; // r8
  signed int v32; // eax
  unsigned int v33; // eax
  unsigned int v34; // eax
  PHKEY phkResult; // [rsp+20h] [rbp-88h]
  unsigned int v37; // [rsp+30h] [rbp-78h]
  int v38; // [rsp+34h] [rbp-74h] BYREF
  int v39; // [rsp+38h] [rbp-70h]
  int v40; // [rsp+3Ch] [rbp-6Ch]
  PCCERT_CONTEXT pCertContext; // [rsp+40h] [rbp-68h]
  HCERTSTORE v42; // [rsp+48h] [rbp-60h]
  HKEY hKey[11]; // [rsp+50h] [rbp-58h] BYREF
  unsigned int v44; // [rsp+B0h] [rbp+8h]

  LODWORD(LastError) = 0;
  v8 = 0;
  v40 = 0;
  pPrevCertContext = 0;
  hKey[0] = 0;
  v10 = 0;
  v37 = 0;
  v44 = 0;
  v39 = 0;
  if ( !a2 )
  {
    v12 = -2147024809;
    Logger::TraceError(
      L"%s: \"%s\" should not be null.",
      L"CertificateUtil::FindAllCertificatesByOidValue",
      L"pcszOids");
    v13 = L"pcszOids";
LABEL_3:
    Logger::WriteNullOrEmptyParameterFailureEvent(L"CertificateUtil::FindAllCertificatesByOidValue", v13);
    goto LABEL_44;
  }
  if ( !a3 )
  {
    v12 = -2147024809;
    Logger::TraceError(
      L"%s: \"%s\" should not be null.",
      L"CertificateUtil::FindAllCertificatesByOidValue",
      L"pcszOidValues");
    v13 = L"pcszOidValues";
    goto LABEL_3;
  }
  if ( !a7 )
  {
    v12 = -2147024809;
    Logger::TraceError(
      L"%s: \"%s\" should not be null.",
      L"CertificateUtil::FindAllCertificatesByOidValue",
      L"pdwCount");
    v13 = L"pdwCount";
    goto LABEL_3;
  }
  v12 = 0;
  v37 = *a7;
  *a7 = 0;
  if ( a1 == 1 && (unsigned int)IsWinPEHost() )
  {
    Logger::TraceInformation(L"%s: System is WinPE.", L"CertificateUtil::FindAllCertificatesByOidValue");
    v14 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"TargetSoftware\\Microsoft\\SystemCertificates\\MY", 0, 0x20019u, hKey);
    LODWORD(LastError) = v14;
    if ( v14 )
    {
      Logger::TraceWarning(
        L"%s: Cannot open registry key \"%s\". RegOpenKeyExW error code: 0x%08x. Try loading the registry key...",
        L"CertificateUtil::FindAllCertificatesByOidValue",
        L"HKEY_LOCAL_MACHINE\\TargetSoftware\\Microsoft\\SystemCertificates\\MY",
        v14);
      KeyW = RegUnLoadKeyW(HKEY_LOCAL_MACHINE, L"TargetSoftware");
      if ( KeyW )
        Logger::TraceVerbose(
          L"%s: Always try unloading reg key \"%s\" first before loading it. RegUnLoadKeyW failed with error code: 0x%08x."
           " Failure ignored. Continue to load the key...",
          L"CertificateUtil::FindAllCertificatesByOidValue",
          L"HKEY_LOCAL_MACHINE\\TargetSoftware",
          KeyW);
      KeyWinPE = RegLoadKeyWinPE(v17, v16, v18, v19);
      v12 = KeyWinPE;
      if ( KeyWinPE < 0 )
      {
        Logger::TraceError(
          L"%s: %s failed with error code: 0x%08x.",
          L"CertificateUtil::FindAllCertificatesByOidValue",
          L"RegLoadKeyWinPE",
          (unsigned int)KeyWinPE);
        goto LABEL_15;
      }
      v40 = 1;
      v22 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"TargetSoftware\\Microsoft\\SystemCertificates\\MY", 0, 0x20019u, hKey);
      LODWORD(LastError) = v22;
      if ( v22 )
      {
        Logger::TraceError(
          L"%s: Cannot open registry key \"%s\". RegOpenKeyExW error code: 0x%08x.",
          L"CertificateUtil::FindAllCertificatesByOidValue",
          L"HKEY_LOCAL_MACHINE\\TargetSoftware\\Microsoft\\SystemCertificates\\MY",
          v22);
        goto LABEL_15;
      }
    }
    v23 = (const wchar_t *)hKey[0];
    v24 = 0x8000;
    v25 = 4;
  }
  else
  {
    v25 = 10;
    v23 = L"My";
    v24 = a1 != 0 ? 163840 : 98304;
  }
  v42 = CertOpenStore((LPCSTR)v25, 0, 0, v24, v23);
  v8 = v42;
  if ( v42 )
  {
LABEL_23:
    while ( 1 )
    {
      pCertContext = CertFindCertificateInStore(v8, 0x10001u, 0, 0, 0, pPrevCertContext);
      pPrevCertContext = pCertContext;
      if ( !pCertContext )
        break;
      ++v39;
      v26 = 1;
      v38 = 1;
      for ( i = 0; ; i = (unsigned int)(i + 1) )
      {
        if ( !v26 )
        {
          pPrevCertContext = pCertContext;
          v8 = v42;
          goto LABEL_23;
        }
        if ( (unsigned int)i >= a5 )
          break;
        Logger::TraceVerbose(
          L"%s: Will try to find the OID: '%hs' and value: '%.*s'",
          L"CertificateUtil::FindAllCertificatesByOidValue",
          *(_QWORD *)(a2 + 8 * i),
          1024,
          *(_QWORD *)(a3 + 8 * i));
        v28 = *(_QWORD *)(a3 + 8 * i);
        v29 = *(const char **)(a2 + 8 * i);
        if ( v28 )
        {
          pPrevCertContext = pCertContext;
          DoesExtensionWithValueExist = CertificateUtil::DoesExtensionWithValueExist(
                                          v29,
                                          v28,
                                          *(unsigned int *)(a4 + 4 * i),
                                          pCertContext,
                                          &v38);
          v12 = DoesExtensionWithValueExist;
          if ( DoesExtensionWithValueExist < 0 )
          {
            Logger::TraceError(
              L"%s: %s failed with error code: 0x%08x.",
              L"CertificateUtil::FindAllCertificatesByOidValue",
              L"CertificateUtil::DoesExtensionWithValueExist",
              (unsigned int)DoesExtensionWithValueExist);
            v8 = v42;
            goto LABEL_44;
          }
          v26 = v38;
        }
        else
        {
          if ( CertificateUtil::FindExtensionByOid(v29, pCertContext) )
            v26 = 0;
          v38 = v26;
        }
        v31 = L"TRUE";
        if ( !v26 )
          v31 = L"FALSE";
        Logger::TraceVerbose(L"%s: Cert matching: %s", L"CertificateUtil::FindAllCertificatesByOidValue", v31);
      }
      ++v44;
      pPrevCertContext = pCertContext;
      v8 = v42;
      if ( v37 > (unsigned int)v10 && a6 )
      {
        a6[v10] = (struct _CERT_CONTEXT *)CertDuplicateCertificateContext(pCertContext);
        v10 = (unsigned int)(v10 + 1);
      }
    }
    if ( v37 >= v44 && a6 )
    {
      *a7 = v10;
    }
    else
    {
      *a7 = v44;
      LODWORD(LastError) = 122;
    }
  }
  else
  {
    LastError = GetLastError();
    Logger::TraceError(
      L"%s: CertOpenStore failed with error code: 0x%08x",
      L"CertificateUtil::FindAllCertificatesByOidValue",
      LastError);
  }
LABEL_44:
  if ( a1 )
  {
    if ( a1 != 1 )
    {
      p_hCertStore = L"Unknown";
      goto LABEL_48;
    }
LABEL_15:
    p_hCertStore = L"LocalMachine";
    goto LABEL_48;
  }
  p_hCertStore = (const wchar_t *)&stru_18002C008.hCertStore;
LABEL_48:
  LODWORD(phkResult) = v39;
  Logger::TraceVerbose(
    L"%s: %u total %s certificate(s) found. %u certificate(s) checked.",
    L"CertificateUtil::FindAllCertificatesByOidValue",
    v44,
    p_hCertStore,
    phkResult);
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
    if ( v37 < (unsigned int)v10 )
      LODWORD(v10) = v37;
    CertificateUtil::FreeCertificates((const struct _CERT_CONTEXT **const)a6, v10);
  }
  if ( v8 && !CertCloseStore(v8, 0) )
  {
    v32 = GetLastError();
    if ( v32 > 0 )
      v32 = (unsigned __int16)v32 | 0x80070000;
    Logger::TraceWarning(
      L"%s: CertCloseStore failed with error code: 0x%08x",
      L"CertificateUtil::FindAllCertificatesByOidValue",
      (unsigned int)v32);
  }
  if ( hKey[0] )
  {
    v33 = RegCloseKey(hKey[0]);
    if ( v33 )
      Logger::TraceWarning(
        L"%s: Cannot close reg key %s. RegCloseKey failed with error code: 0x%08x.",
        L"CertificateUtil::FindAllCertificatesByOidValue",
        L"HKEY_LOCAL_MACHINE\\TargetSoftware\\Microsoft\\SystemCertificates\\MY",
        v33);
  }
  if ( v40 )
  {
    v34 = RegUnLoadKeyW(HKEY_LOCAL_MACHINE, L"TargetSoftware");
    if ( v34 )
      Logger::TraceWarning(
        L"%s: Cannot unload reg key %s. RegUnLoadKeyW failed with error code: 0x%08x.",
        L"CertificateUtil::FindAllCertificatesByOidValue",
        L"HKEY_LOCAL_MACHINE\\TargetSoftware",
        v34);
    else
      Logger::TraceVerbose(
        L"%s: reg key \"%s\" unloaded.",
        L"CertificateUtil::FindAllCertificatesByOidValue",
        L"HKEY_LOCAL_MACHINE\\TargetSoftware");
  }
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x180013084  mov     r11, rsp
0x180013087  mov     [r11+20h], r9
0x18001308b  mov     [r11+18h], r8
0x18001308f  mov     [r11+10h], rdx
0x180013093  push    rbx
0x180013094  push    rbp
0x180013095  push    rsi
0x180013096  push    rdi
0x180013097  push    r12
0x180013099  push    r13
0x18001309b  push    r14
0x18001309d  push    r15
0x18001309f  sub     rsp, 68h
0x1800130a3  xor     esi, esi
0x1800130a5  lea     rbx, aCertificateuti; "CertificateUtil::FindAllCertificatesByO"...
0x1800130ac  xor     r12d, r12d
0x1800130af  mov     [rsp+0A8h+var_6C], esi
0x1800130b3  xor     ebp, ebp
0x1800130b5  mov     [r11-58h], rsi
0x1800130b9  xor     r14d, r14d
0x1800130bc  mov     [rsp+0A8h+var_78], esi
0x1800130c0  mov     [rsp+0A8h+arg_0], esi
0x1800130c7  mov     rax, r8
0x1800130ca  mov     [rsp+0A8h+var_70], esi
0x1800130ce  mov     r13d, ecx
0x1800130d1  test    rdx, rdx
0x1800130d4  jnz     short loc_180013105
0x1800130d6  lea     r8, aPcszoids; "pcszOids"
0x1800130dd  mov     rdx, rbx
0x1800130e0  lea     rcx, aSSShouldNotBeN; "%s: \"%s\" should not be null."
0x1800130e7  mov     edi, 80070057h
0x1800130ec  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x1800130f1  lea     rdx, aPcszoids; "pcszOids"
0x1800130f8  mov     rcx, rbx; unsigned __int16 *
0x1800130fb  call    ?WriteNullOrEmptyParameterFailureEvent@Logger@@SAJPEBG0@Z; Logger::WriteNullOrEmptyParameterFailureEvent(ushort const *,ushort const *)
0x180013100  jmp     loc_1800134A0
0x180013105  test    rax, rax
0x180013108  jnz     short loc_18001312E
0x18001310a  lea     r8, aPcszoidvalues; "pcszOidValues"
0x180013111  mov     rdx, rbx
0x180013114  lea     rcx, aSSShouldNotBeN; "%s: \"%s\" should not be null."
0x18001311b  mov     edi, 80070057h
0x180013120  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180013125  lea     rdx, aPcszoidvalues; "pcszOidValues"
0x18001312c  jmp     short loc_1800130F8
0x18001312e  mov     r15, [rsp+0A8h+arg_30]
0x180013136  test    r15, r15
0x180013139  jnz     short loc_18001315F
0x18001313b  lea     r8, aPdwcount; "pdwCount"
0x180013142  mov     rdx, rbx
0x180013145  lea     rcx, aSSShouldNotBeN; "%s: \"%s\" should not be null."
0x18001314c  mov     edi, 80070057h
0x180013151  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180013156  lea     rdx, aPdwcount; "pdwCount"
0x18001315d  jmp     short loc_1800130F8
0x18001315f  mov     eax, [r15]
0x180013162  xor     edi, edi
0x180013164  mov     [rsp+0A8h+var_78], eax
0x180013168  mov     [r15], esi
0x18001316b  cmp     r13d, 1
0x18001316f  jnz     loc_180013293
0x180013175  call    ?IsWinPEHost@@YAHXZ; IsWinPEHost(void)
0x18001317a  test    eax, eax
0x18001317c  jz      loc_180013293
0x180013182  mov     rdx, rbx
0x180013185  lea     rcx, aSSystemIsWinpe; "%s: System is WinPE."
0x18001318c  call    ?TraceInformation@Logger@@SAJPEBGZZ; Logger::TraceInformation(ushort const *,...)
0x180013191  lea     rax, [rsp+0A8h+hKey]
0x180013196  mov     r9d, 20019h; samDesired
0x18001319c  xor     r8d, r8d; ulOptions
0x18001319f  mov     [rsp+0A8h+phkResult], rax; phkResult
0x1800131a4  lea     rdx, aTargetsoftware; "TargetSoftware\\Microsoft\\SystemCertif"...
0x1800131ab  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800131b2  call    cs:__imp_RegOpenKeyExW
0x1800131b8  mov     esi, eax
0x1800131ba  test    eax, eax
0x1800131bc  jz      loc_180013281
0x1800131c2  mov     r9d, eax
0x1800131c5  lea     r8, aHkeyLocalMachi; "HKEY_LOCAL_MACHINE\\TargetSoftware\\Mic"...
0x1800131cc  mov     rdx, rbx
0x1800131cf  lea     rcx, aSCannotOpenReg; "%s: Cannot open registry key \"%s\". Re"...
0x1800131d6  call    ?TraceWarning@Logger@@SAJPEBGZZ; Logger::TraceWarning(ushort const *,...)
0x1800131db  lea     rdx, aTargetsoftware_0; "TargetSoftware"
0x1800131e2  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800131e9  call    cs:__imp_RegUnLoadKeyW
0x1800131ef  test    eax, eax
0x1800131f1  jz      short loc_18001320C
0x1800131f3  mov     r9d, eax
0x1800131f6  lea     r8, aHkeyLocalMachi_2; "HKEY_LOCAL_MACHINE\\TargetSoftware"
0x1800131fd  mov     rdx, rbx
0x180013200  lea     rcx, aSAlwaysTryUnlo; "%s: Always try unloading reg key \"%s\""...
0x180013207  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x18001320c  call    ?RegLoadKeyWinPE@@YAJPEAUHKEY__@@PEBG11@Z; RegLoadKeyWinPE(HKEY__ *,ushort const *,ushort const *,ushort const *)
0x180013211  mov     edi, eax
0x180013213  test    eax, eax
0x180013215  jns     short loc_18001323C
0x180013217  lea     r8, aRegloadkeywinp; "RegLoadKeyWinPE"
0x18001321e  lea     rcx, aSSFailedWithEr_0; "%s: %s failed with error code: 0x%08x."
0x180013225  mov     rdx, rbx
0x180013228  mov     r9d, eax
0x18001322b  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180013230  lea     r9, aLocalmachine; "LocalMachine"
0x180013237  jmp     loc_1800134BF
0x18001323c  lea     rax, [rsp+0A8h+hKey]
0x180013241  mov     [rsp+0A8h+var_6C], 1
0x180013249  mov     r9d, 20019h; samDesired
0x18001324f  mov     [rsp+0A8h+phkResult], rax; phkResult
0x180013254  xor     r8d, r8d; ulOptions
0x180013257  lea     rdx, aTargetsoftware; "TargetSoftware\\Microsoft\\SystemCertif"...
0x18001325e  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180013265  call    cs:__imp_RegOpenKeyExW
0x18001326b  mov     esi, eax
0x18001326d  test    eax, eax
0x18001326f  jz      short loc_180013281
0x180013271  lea     r8, aHkeyLocalMachi; "HKEY_LOCAL_MACHINE\\TargetSoftware\\Mic"...
0x180013278  lea     rcx, aSCannotOpenReg_0; "%s: Cannot open registry key \"%s\". Re"...
0x18001327f  jmp     short loc_180013225
0x180013281  mov     rax, [rsp+0A8h+hKey]
0x180013286  mov     r9d, 8000h
0x18001328c  mov     ecx, 4
0x180013291  jmp     short loc_1800132B5
0x180013293  mov     eax, r13d
0x180013296  mov     ecx, 0Ah; lpszStoreProvider
0x18001329b  neg     eax
0x18001329d  lea     rax, aMy; "My"
0x1800132a4  sbb     r9d, r9d
0x1800132a7  and     r9d, 10000h
0x1800132ae  add     r9d, 18000h; dwFlags
0x1800132b5  xor     r8d, r8d; hCryptProv
0x1800132b8  mov     [rsp+0A8h+phkResult], rax; pvPara
0x1800132bd  xor     edx, edx; dwEncodingType
0x1800132bf  call    cs:__imp_CertOpenStore
0x1800132c5  mov     [rsp+0A8h+var_60], rax
0x1800132ca  mov     r12, rax
0x1800132cd  test    rax, rax
0x1800132d0  jnz     short loc_1800132FB
0x1800132d2  call    cs:__imp_GetLastError
0x1800132d8  mov     rdx, rbx
0x1800132db  lea     rcx, aSCertopenstore; "%s: CertOpenStore failed with error cod"...
0x1800132e2  mov     r8d, eax
0x1800132e5  mov     esi, eax
0x1800132e7  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x1800132ec  jmp     loc_1800134A0
0x1800132f1  mov     rbp, [rsp+0A8h+pCertContext]
0x1800132f6  mov     r12, [rsp+0A8h+var_60]
0x1800132fb  mov     [rsp+0A8h+pPrevCertContext], rbp; pPrevCertContext
0x180013300  xor     r9d, r9d; dwFindType
0x180013303  xor     r8d, r8d; dwFindFlags
0x180013306  mov     [rsp+0A8h+phkResult], 0; pvFindPara
0x18001330f  mov     edx, 10001h; dwCertEncodingType
0x180013314  mov     rcx, r12; hCertStore
0x180013317  call    cs:__imp_CertFindCertificateInStore
0x18001331d  mov     [rsp+0A8h+pCertContext], rax
0x180013322  mov     rbp, rax
0x180013325  test    rax, rax
0x180013328  jz      loc_18001347B
0x18001332e  inc     [rsp+0A8h+var_70]
0x180013332  mov     ebp, 1
0x180013337  mov     [rsp+0A8h+var_74], ebp
0x18001333b  xor     r12d, r12d
0x18001333e  test    ebp, ebp
0x180013340  jz      short loc_1800132F1
0x180013342  cmp     r12d, [rsp+0A8h+arg_20]
0x18001334a  jnb     loc_180013413
0x180013350  mov     rax, [rsp+0A8h+arg_10]
0x180013358  lea     rcx, aSWillTryToFind; "%s: Will try to find the OID: '%hs' and"...
0x18001335f  mov     r8, [rsp+0A8h+arg_8]
0x180013367  mov     r9d, 400h
0x18001336d  mov     rdx, rbx
0x180013370  mov     rax, [rax+r12*8]
0x180013374  mov     r8, [r8+r12*8]
0x180013378  mov     [rsp+0A8h+phkResult], rax
0x18001337d  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x180013382  mov     rax, [rsp+0A8h+arg_10]
0x18001338a  mov     rdx, [rax+r12*8]
0x18001338e  mov     rax, [rsp+0A8h+arg_8]
0x180013396  mov     rcx, [rax+r12*8]; char *
0x18001339a  test    rdx, rdx
0x18001339d  jz      short loc_1800133D2
0x18001339f  mov     rbp, [rsp+0A8h+pCertContext]
0x1800133a4  lea     rax, [rsp+0A8h+var_74]
0x1800133a9  mov     [rsp+0A8h+phkResult], rax
0x1800133ae  mov     r9, rbp
0x1800133b1  mov     rax, [rsp+0A8h+arg_18]
0x1800133b9  mov     r8d, [rax+r12*4]
0x1800133bd  call    ?DoesExtensionWithValueExist@CertificateUtil@@SAJPEBDPEBGW4_CERT_OID_VALUE_TYPE@@PEBU_CERT_CONTEXT@@PEAH@Z; CertificateUtil::DoesExtensionWithValueExist(char const *,ushort const *,_CERT_OID_VALUE_TYPE,_CERT_CONTEXT const *,int *)
0x1800133c2  mov     edi, eax
0x1800133c4  test    eax, eax
0x1800133c6  js      loc_18001345B
0x1800133cc  mov     ebp, [rsp+0A8h+var_74]
0x1800133d0  jmp     short loc_1800133E8
0x1800133d2  mov     rdx, [rsp+0A8h+pCertContext]; struct _CERT_CONTEXT *
0x1800133d7  call    ?FindExtensionByOid@CertificateUtil@@SAPEAU_CERT_EXTENSION@@PEBDPEBU_CERT_CONTEXT@@@Z; CertificateUtil::FindExtensionByOid(char const *,_CERT_CONTEXT const *)
0x1800133dc  xor     ecx, ecx
0x1800133de  test    rax, rax
0x1800133e1  cmovnz  ebp, ecx
0x1800133e4  mov     [rsp+0A8h+var_74], ebp
0x1800133e8  lea     rax, aFalse_0; "FALSE"
0x1800133ef  test    ebp, ebp
0x1800133f1  lea     r8, aTrue_0; "TRUE"
0x1800133f8  mov     rdx, rbx
0x1800133fb  cmovz   r8, rax
0x1800133ff  lea     rcx, aSCertMatchingS; "%s: Cert matching: %s"
0x180013406  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x18001340b  inc     r12d
0x18001340e  jmp     loc_18001333E
0x180013413  inc     [rsp+0A8h+arg_0]
0x18001341a  mov     rbp, [rsp+0A8h+pCertContext]
0x18001341f  mov     r12, [rsp+0A8h+var_60]
0x180013424  cmp     [rsp+0A8h+var_78], r14d
0x180013429  jbe     loc_1800132FB
0x18001342f  cmp     [rsp+0A8h+arg_28], 0
0x180013438  jz      loc_1800132FB
0x18001343e  mov     rcx, rbp; pCertContext
0x180013441  call    cs:__imp_CertDuplicateCertificateContext
0x180013447  mov     rdx, [rsp+0A8h+arg_28]
0x18001344f  mov     [rdx+r14*8], rax
0x180013453  inc     r14d
0x180013456  jmp     loc_1800132FB
0x18001345b  mov     r9d, eax
0x18001345e  lea     r8, aCertificateuti_6; "CertificateUtil::DoesExtensionWithValue"...
0x180013465  mov     rdx, rbx
0x180013468  lea     rcx, aSSFailedWithEr_0; "%s: %s failed with error code: 0x%08x."
0x18001346f  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180013474  mov     r12, [rsp+0A8h+var_60]
0x180013479  jmp     short loc_1800134A0
0x18001347b  mov     eax, [rsp+0A8h+arg_0]
0x180013482  cmp     [rsp+0A8h+var_78], eax
0x180013486  jb      short loc_180013498
0x180013488  cmp     [rsp+0A8h+arg_28], 0
0x180013491  jz      short loc_180013498
0x180013493  mov     [r15], r14d
0x180013496  jmp     short loc_1800134A0
0x180013498  mov     [r15], eax
0x18001349b  mov     esi, 7Ah ; 'z'
0x1800134a0  test    r13d, r13d
0x1800134a3  jz      short loc_1800134B8
0x1800134a5  cmp     r13d, 1
0x1800134a9  jz      loc_180013230
0x1800134af  lea     r9, aUnknown; "Unknown"
0x1800134b6  jmp     short loc_1800134BF
0x1800134b8  lea     r9, stru_18002C008.hCertStore
0x1800134bf  mov     eax, [rsp+0A8h+var_70]
0x1800134c3  lea     rcx, aSUTotalSCertif; "%s: %u total %s certificate(s) found. %"...
0x1800134ca  mov     r8d, [rsp+0A8h+arg_0]
0x1800134d2  mov     rdx, rbx
0x1800134d5  mov     dword ptr [rsp+0A8h+phkResult], eax
0x1800134d9  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x1800134de  mov     r15d, 80070000h
0x1800134e4  test    esi, esi
0x1800134e6  jz      short loc_1800134F4
0x1800134e8  jg      short loc_1800134EE
0x1800134ea  mov     edi, esi
0x1800134ec  jmp     short loc_1800134F4
0x1800134ee  movzx   edi, si
0x1800134f1  or      edi, r15d
0x1800134f4  test    rbp, rbp
0x1800134f7  jz      short loc_180013502
0x1800134f9  mov     rcx, rbp; pCertContext
0x1800134fc  call    cs:__imp_CertFreeCertificateContext
0x180013502  test    edi, edi
0x180013504  jns     short loc_180013521
0x180013506  cmp     [rsp+0A8h+var_78], r14d
0x18001350b  mov     rcx, [rsp+0A8h+arg_28]; struct _CERT_CONTEXT **
0x180013513  cmovb   r14d, [rsp+0A8h+var_78]
0x180013519  mov     edx, r14d; unsigned int
0x18001351c  call    ?FreeCertificates@CertificateUtil@@SAXQEAPEBU_CERT_CONTEXT@@K@Z; CertificateUtil::FreeCertificates(_CERT_CONTEXT const * * const,ulong)
0x180013521  test    r12, r12
0x180013524  jz      short loc_180013557
0x180013526  xor     edx, edx; dwFlags
0x180013528  mov     rcx, r12; hCertStore
0x18001352b  call    cs:__imp_CertCloseStore
0x180013531  test    eax, eax
0x180013533  jnz     short loc_180013557
0x180013535  call    cs:__imp_GetLastError
0x18001353b  test    eax, eax
0x18001353d  jle     short loc_180013545
0x18001353f  movzx   eax, ax
0x180013542  or      eax, r15d
0x180013545  mov     r8d, eax
0x180013548  lea     rcx, aSCertclosestor; "%s: CertCloseStore failed with error co"...
0x18001354f  mov     rdx, rbx
0x180013552  call    ?TraceWarning@Logger@@SAJPEBGZZ; Logger::TraceWarning(ushort const *,...)
0x180013557  mov     rcx, [rsp+0A8h+hKey]; hKey
0x18001355c  test    rcx, rcx
0x18001355f  jz      short loc_180013584
0x180013561  call    cs:__imp_RegCloseKey
0x180013567  test    eax, eax
0x180013569  jz      short loc_180013584
0x18001356b  mov     r9d, eax
0x18001356e  lea     r8, aHkeyLocalMachi; "HKEY_LOCAL_MACHINE\\TargetSoftware\\Mic"...
0x180013575  mov     rdx, rbx
0x180013578  lea     rcx, aSCannotCloseRe; "%s: Cannot close reg key %s. RegCloseKe"...
0x18001357f  call    ?TraceWarning@Logger@@SAJPEBGZZ; Logger::TraceWarning(ushort const *,...)
0x180013584  cmp     [rsp+0A8h+var_6C], 0
0x180013589  jz      short loc_1800135CA
0x18001358b  lea     rdx, aTargetsoftware_0; "TargetSoftware"
0x180013592  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180013599  call    cs:__imp_RegUnLoadKeyW
0x18001359f  lea     r8, aHkeyLocalMachi_2; "HKEY_LOCAL_MACHINE\\TargetSoftware"
  ... truncated ...
```
