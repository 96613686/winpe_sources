# CertificateUtil::FindAllCertificatesByOidValue(_CERTFICATE_LOCATION,char const * * const,ushort const * * const,_CERT_OID_VALUE_TYPE * const,ulong,_CERT_CONTEXT const * * const,ulong *)

- ea: `0x18006f884`
- end: `0x18006fddd`
- name: `?FindAllCertificatesByOidValue@CertificateUtil@@SAJW4_CERTFICATE_LOCATION@@QEAPEBDQEAPEBGQEAW4_CERT_OID_VALUE_TYPE@@KQEAPEBU_CERT_CONTEXT@@PEAK@Z`
- size: `1369`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800efce0`

## callees

- `0x18006f478`
- `0x18006f680`
- `0x18006f6dc`
- `0x18006f848`
- `0x18006f884`
- `0x18006fde4`
- `0x1800ee300`
- `0x1800eea9c`
- `0x1800eec3c`
- `0x1800ef0d0`
- `0x1800ef7e4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006fad2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006fd35`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006fad2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006fd35`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006fd61`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006fd61`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18006f9b2`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18006fa65`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18006f9b2`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18006fa65`
- `api-ms-win-core-registry-l1-1-0!RegUnLoadKeyW` at `0x18006f9e9`
- `api-ms-win-core-registry-l1-1-0!RegUnLoadKeyW` at `0x18006fd99`
- `api-ms-win-core-registry-l1-1-0!RegUnLoadKeyW` at `0x18006f9e9`
- `api-ms-win-core-registry-l1-1-0!RegUnLoadKeyW` at `0x18006fd99`
- `CRYPT32!CertFindCertificateInStore` at `0x18006fb17`
- `CRYPT32!CertFindCertificateInStore` at `0x18006fb17`
- `CRYPT32!CertCloseStore` at `0x18006fd2b`
- `CRYPT32!CertCloseStore` at `0x18006fd2b`
- `CRYPT32!CertOpenStore` at `0x18006fabf`
- `CRYPT32!CertOpenStore` at `0x18006fabf`
- `CRYPT32!CertDuplicateCertificateContext` at `0x18006fc41`
- `CRYPT32!CertDuplicateCertificateContext` at `0x18006fc41`
- `CRYPT32!CertFreeCertificateContext` at `0x18006fcfc`
- `CRYPT32!CertFreeCertificateContext` at `0x18006fcfc`

## string_xrefs

- `0x18006f9cf`: `%s: Cannot open registry key "%s". RegOpenKeyExW error code: 0x%08x. Try loading the registry key...`
- `0x18006fc5e`: `CertificateUtil::DoesExtensionWithValueExist`
- `0x18006fa78`: `%s: Cannot open registry key "%s". RegOpenKeyExW error code: 0x%08x.`
- `0x18006fadb`: `%s: CertOpenStore failed with error code: 0x%08x`

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
    p_hCertStore = (const wchar_t *)&stru_1801282C8.hCertStore;
    goto LABEL_48;
  }
  p_hCertStore = L"CurrentUser";
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
0x18006f884  mov     r11, rsp
0x18006f887  mov     [r11+20h], r9
0x18006f88b  mov     [r11+18h], r8
0x18006f88f  mov     [r11+10h], rdx
0x18006f893  push    rbx
0x18006f894  push    rbp
0x18006f895  push    rsi
0x18006f896  push    rdi
0x18006f897  push    r12
0x18006f899  push    r13
0x18006f89b  push    r14
0x18006f89d  push    r15
0x18006f89f  sub     rsp, 68h
0x18006f8a3  xor     esi, esi
0x18006f8a5  lea     rbx, aCertificateuti; "CertificateUtil::FindAllCertificatesByO"...
0x18006f8ac  xor     r12d, r12d
0x18006f8af  mov     [rsp+0A8h+var_6C], esi
0x18006f8b3  xor     ebp, ebp
0x18006f8b5  mov     [r11-58h], rsi
0x18006f8b9  xor     r14d, r14d
0x18006f8bc  mov     [rsp+0A8h+var_78], esi
0x18006f8c0  mov     [rsp+0A8h+arg_0], esi
0x18006f8c7  mov     rax, r8
0x18006f8ca  mov     [rsp+0A8h+var_70], esi
0x18006f8ce  mov     r13d, ecx
0x18006f8d1  test    rdx, rdx
0x18006f8d4  jnz     short loc_18006F905
0x18006f8d6  lea     r8, aPcszoids; "pcszOids"
0x18006f8dd  mov     rdx, rbx
0x18006f8e0  lea     rcx, aSSShouldNotBeN; "%s: \"%s\" should not be null."
0x18006f8e7  mov     edi, 80070057h
0x18006f8ec  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18006f8f1  lea     rdx, aPcszoids; "pcszOids"
0x18006f8f8  mov     rcx, rbx; unsigned __int16 *
0x18006f8fb  call    ?WriteNullOrEmptyParameterFailureEvent@Logger@@SAJPEBG0@Z; Logger::WriteNullOrEmptyParameterFailureEvent(ushort const *,ushort const *)
0x18006f900  jmp     loc_18006FCA0
0x18006f905  test    rax, rax
0x18006f908  jnz     short loc_18006F92E
0x18006f90a  lea     r8, aPcszoidvalues; "pcszOidValues"
0x18006f911  mov     rdx, rbx
0x18006f914  lea     rcx, aSSShouldNotBeN; "%s: \"%s\" should not be null."
0x18006f91b  mov     edi, 80070057h
0x18006f920  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18006f925  lea     rdx, aPcszoidvalues; "pcszOidValues"
0x18006f92c  jmp     short loc_18006F8F8
0x18006f92e  mov     r15, [rsp+0A8h+arg_30]
0x18006f936  test    r15, r15
0x18006f939  jnz     short loc_18006F95F
0x18006f93b  lea     r8, aPdwcount; "pdwCount"
0x18006f942  mov     rdx, rbx
0x18006f945  lea     rcx, aSSShouldNotBeN; "%s: \"%s\" should not be null."
0x18006f94c  mov     edi, 80070057h
0x18006f951  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18006f956  lea     rdx, aPdwcount; "pdwCount"
0x18006f95d  jmp     short loc_18006F8F8
0x18006f95f  mov     eax, [r15]
0x18006f962  xor     edi, edi
0x18006f964  mov     [rsp+0A8h+var_78], eax
0x18006f968  mov     [r15], esi
0x18006f96b  cmp     r13d, 1
0x18006f96f  jnz     loc_18006FA93
0x18006f975  call    ?IsWinPEHost@@YAHXZ; IsWinPEHost(void)
0x18006f97a  test    eax, eax
0x18006f97c  jz      loc_18006FA93
0x18006f982  mov     rdx, rbx
0x18006f985  lea     rcx, aSSystemIsWinpe; "%s: System is WinPE."
0x18006f98c  call    ?TraceInformation@Logger@@SAJPEBGZZ; Logger::TraceInformation(ushort const *,...)
0x18006f991  lea     rax, [rsp+0A8h+hKey]
0x18006f996  mov     r9d, 20019h; samDesired
0x18006f99c  xor     r8d, r8d; ulOptions
0x18006f99f  mov     [rsp+0A8h+phkResult], rax; phkResult
0x18006f9a4  lea     rdx, aTargetsoftware; "TargetSoftware\\Microsoft\\SystemCertif"...
0x18006f9ab  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18006f9b2  call    cs:__imp_RegOpenKeyExW
0x18006f9b8  mov     esi, eax
0x18006f9ba  test    eax, eax
0x18006f9bc  jz      loc_18006FA81
0x18006f9c2  mov     r9d, eax
0x18006f9c5  lea     r8, aHkeyLocalMachi; "HKEY_LOCAL_MACHINE\\TargetSoftware\\Mic"...
0x18006f9cc  mov     rdx, rbx
0x18006f9cf  lea     rcx, aSCannotOpenReg; "%s: Cannot open registry key \"%s\". Re"...
0x18006f9d6  call    ?TraceWarning@Logger@@SAJPEBGZZ; Logger::TraceWarning(ushort const *,...)
0x18006f9db  lea     rdx, aTargetsoftware_0; "TargetSoftware"
0x18006f9e2  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18006f9e9  call    cs:__imp_RegUnLoadKeyW
0x18006f9ef  test    eax, eax
0x18006f9f1  jz      short loc_18006FA0C
0x18006f9f3  mov     r9d, eax
0x18006f9f6  lea     r8, aHkeyLocalMachi_2; "HKEY_LOCAL_MACHINE\\TargetSoftware"
0x18006f9fd  mov     rdx, rbx
0x18006fa00  lea     rcx, aSAlwaysTryUnlo; "%s: Always try unloading reg key \"%s\""...
0x18006fa07  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x18006fa0c  call    ?RegLoadKeyWinPE@@YAJPEAUHKEY__@@PEBG11@Z; RegLoadKeyWinPE(HKEY__ *,ushort const *,ushort const *,ushort const *)
0x18006fa11  mov     edi, eax
0x18006fa13  test    eax, eax
0x18006fa15  jns     short loc_18006FA3C
0x18006fa17  lea     r8, aRegloadkeywinp; "RegLoadKeyWinPE"
0x18006fa1e  lea     rcx, aSSFailedWithEr_0; "%s: %s failed with error code: 0x%08x."
0x18006fa25  mov     rdx, rbx
0x18006fa28  mov     r9d, eax
0x18006fa2b  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18006fa30  lea     r9, stru_1801282C8.hCertStore
0x18006fa37  jmp     loc_18006FCBF
0x18006fa3c  lea     rax, [rsp+0A8h+hKey]
0x18006fa41  mov     [rsp+0A8h+var_6C], 1
0x18006fa49  mov     r9d, 20019h; samDesired
0x18006fa4f  mov     [rsp+0A8h+phkResult], rax; phkResult
0x18006fa54  xor     r8d, r8d; ulOptions
0x18006fa57  lea     rdx, aTargetsoftware; "TargetSoftware\\Microsoft\\SystemCertif"...
0x18006fa5e  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18006fa65  call    cs:__imp_RegOpenKeyExW
0x18006fa6b  mov     esi, eax
0x18006fa6d  test    eax, eax
0x18006fa6f  jz      short loc_18006FA81
0x18006fa71  lea     r8, aHkeyLocalMachi; "HKEY_LOCAL_MACHINE\\TargetSoftware\\Mic"...
0x18006fa78  lea     rcx, aSCannotOpenReg_0; "%s: Cannot open registry key \"%s\". Re"...
0x18006fa7f  jmp     short loc_18006FA25
0x18006fa81  mov     rax, [rsp+0A8h+hKey]
0x18006fa86  mov     r9d, 8000h
0x18006fa8c  mov     ecx, 4
0x18006fa91  jmp     short loc_18006FAB5
0x18006fa93  mov     eax, r13d
0x18006fa96  mov     ecx, 0Ah; lpszStoreProvider
0x18006fa9b  neg     eax
0x18006fa9d  lea     rax, aMy; "My"
0x18006faa4  sbb     r9d, r9d
0x18006faa7  and     r9d, 10000h
0x18006faae  add     r9d, 18000h; dwFlags
0x18006fab5  xor     r8d, r8d; hCryptProv
0x18006fab8  mov     [rsp+0A8h+phkResult], rax; pvPara
0x18006fabd  xor     edx, edx; dwEncodingType
0x18006fabf  call    cs:__imp_CertOpenStore
0x18006fac5  mov     [rsp+0A8h+var_60], rax
0x18006faca  mov     r12, rax
0x18006facd  test    rax, rax
0x18006fad0  jnz     short loc_18006FAFB
0x18006fad2  call    cs:__imp_GetLastError
0x18006fad8  mov     rdx, rbx
0x18006fadb  lea     rcx, aSCertopenstore; "%s: CertOpenStore failed with error cod"...
0x18006fae2  mov     r8d, eax
0x18006fae5  mov     esi, eax
0x18006fae7  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18006faec  jmp     loc_18006FCA0
0x18006faf1  mov     rbp, [rsp+0A8h+pCertContext]
0x18006faf6  mov     r12, [rsp+0A8h+var_60]
0x18006fafb  mov     [rsp+0A8h+pPrevCertContext], rbp; pPrevCertContext
0x18006fb00  xor     r9d, r9d; dwFindType
0x18006fb03  xor     r8d, r8d; dwFindFlags
0x18006fb06  mov     [rsp+0A8h+phkResult], 0; pvFindPara
0x18006fb0f  mov     edx, 10001h; dwCertEncodingType
0x18006fb14  mov     rcx, r12; hCertStore
0x18006fb17  call    cs:__imp_CertFindCertificateInStore
0x18006fb1d  mov     [rsp+0A8h+pCertContext], rax
0x18006fb22  mov     rbp, rax
0x18006fb25  test    rax, rax
0x18006fb28  jz      loc_18006FC7B
0x18006fb2e  inc     [rsp+0A8h+var_70]
0x18006fb32  mov     ebp, 1
0x18006fb37  mov     [rsp+0A8h+var_74], ebp
0x18006fb3b  xor     r12d, r12d
0x18006fb3e  test    ebp, ebp
0x18006fb40  jz      short loc_18006FAF1
0x18006fb42  cmp     r12d, [rsp+0A8h+arg_20]
0x18006fb4a  jnb     loc_18006FC13
0x18006fb50  mov     rax, [rsp+0A8h+arg_10]
0x18006fb58  lea     rcx, aSWillTryToFind; "%s: Will try to find the OID: '%hs' and"...
0x18006fb5f  mov     r8, [rsp+0A8h+arg_8]
0x18006fb67  mov     r9d, 400h
0x18006fb6d  mov     rdx, rbx
0x18006fb70  mov     rax, [rax+r12*8]
0x18006fb74  mov     r8, [r8+r12*8]
0x18006fb78  mov     [rsp+0A8h+phkResult], rax
0x18006fb7d  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x18006fb82  mov     rax, [rsp+0A8h+arg_10]
0x18006fb8a  mov     rdx, [rax+r12*8]
0x18006fb8e  mov     rax, [rsp+0A8h+arg_8]
0x18006fb96  mov     rcx, [rax+r12*8]; char *
0x18006fb9a  test    rdx, rdx
0x18006fb9d  jz      short loc_18006FBD2
0x18006fb9f  mov     rbp, [rsp+0A8h+pCertContext]
0x18006fba4  lea     rax, [rsp+0A8h+var_74]
0x18006fba9  mov     [rsp+0A8h+phkResult], rax
0x18006fbae  mov     r9, rbp
0x18006fbb1  mov     rax, [rsp+0A8h+arg_18]
0x18006fbb9  mov     r8d, [rax+r12*4]
0x18006fbbd  call    ?DoesExtensionWithValueExist@CertificateUtil@@SAJPEBDPEBGW4_CERT_OID_VALUE_TYPE@@PEBU_CERT_CONTEXT@@PEAH@Z; CertificateUtil::DoesExtensionWithValueExist(char const *,ushort const *,_CERT_OID_VALUE_TYPE,_CERT_CONTEXT const *,int *)
0x18006fbc2  mov     edi, eax
0x18006fbc4  test    eax, eax
0x18006fbc6  js      loc_18006FC5B
0x18006fbcc  mov     ebp, [rsp+0A8h+var_74]
0x18006fbd0  jmp     short loc_18006FBE8
0x18006fbd2  mov     rdx, [rsp+0A8h+pCertContext]; struct _CERT_CONTEXT *
0x18006fbd7  call    ?FindExtensionByOid@CertificateUtil@@SAPEAU_CERT_EXTENSION@@PEBDPEBU_CERT_CONTEXT@@@Z; CertificateUtil::FindExtensionByOid(char const *,_CERT_CONTEXT const *)
0x18006fbdc  xor     ecx, ecx
0x18006fbde  test    rax, rax
0x18006fbe1  cmovnz  ebp, ecx
0x18006fbe4  mov     [rsp+0A8h+var_74], ebp
0x18006fbe8  lea     rax, aFalse_1; "FALSE"
0x18006fbef  test    ebp, ebp
0x18006fbf1  lea     r8, aTrue_1; "TRUE"
0x18006fbf8  mov     rdx, rbx
0x18006fbfb  cmovz   r8, rax
0x18006fbff  lea     rcx, aSCertMatchingS; "%s: Cert matching: %s"
0x18006fc06  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x18006fc0b  inc     r12d
0x18006fc0e  jmp     loc_18006FB3E
0x18006fc13  inc     [rsp+0A8h+arg_0]
0x18006fc1a  mov     rbp, [rsp+0A8h+pCertContext]
0x18006fc1f  mov     r12, [rsp+0A8h+var_60]
0x18006fc24  cmp     [rsp+0A8h+var_78], r14d
0x18006fc29  jbe     loc_18006FAFB
0x18006fc2f  cmp     [rsp+0A8h+arg_28], 0
0x18006fc38  jz      loc_18006FAFB
0x18006fc3e  mov     rcx, rbp; pCertContext
0x18006fc41  call    cs:__imp_CertDuplicateCertificateContext
0x18006fc47  mov     rdx, [rsp+0A8h+arg_28]
0x18006fc4f  mov     [rdx+r14*8], rax
0x18006fc53  inc     r14d
0x18006fc56  jmp     loc_18006FAFB
0x18006fc5b  mov     r9d, eax
0x18006fc5e  lea     r8, aCertificateuti_6; "CertificateUtil::DoesExtensionWithValue"...
0x18006fc65  mov     rdx, rbx
0x18006fc68  lea     rcx, aSSFailedWithEr_0; "%s: %s failed with error code: 0x%08x."
0x18006fc6f  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18006fc74  mov     r12, [rsp+0A8h+var_60]
0x18006fc79  jmp     short loc_18006FCA0
0x18006fc7b  mov     eax, [rsp+0A8h+arg_0]
0x18006fc82  cmp     [rsp+0A8h+var_78], eax
0x18006fc86  jb      short loc_18006FC98
0x18006fc88  cmp     [rsp+0A8h+arg_28], 0
0x18006fc91  jz      short loc_18006FC98
0x18006fc93  mov     [r15], r14d
0x18006fc96  jmp     short loc_18006FCA0
0x18006fc98  mov     [r15], eax
0x18006fc9b  mov     esi, 7Ah ; 'z'
0x18006fca0  test    r13d, r13d
0x18006fca3  jz      short loc_18006FCB8
0x18006fca5  cmp     r13d, 1
0x18006fca9  jz      loc_18006FA30
0x18006fcaf  lea     r9, aUnknown; "Unknown"
0x18006fcb6  jmp     short loc_18006FCBF
0x18006fcb8  lea     r9, aCurrentuser; "CurrentUser"
0x18006fcbf  mov     eax, [rsp+0A8h+var_70]
0x18006fcc3  lea     rcx, aSUTotalSCertif; "%s: %u total %s certificate(s) found. %"...
0x18006fcca  mov     r8d, [rsp+0A8h+arg_0]
0x18006fcd2  mov     rdx, rbx
0x18006fcd5  mov     dword ptr [rsp+0A8h+phkResult], eax
0x18006fcd9  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x18006fcde  mov     r15d, 80070000h
0x18006fce4  test    esi, esi
0x18006fce6  jz      short loc_18006FCF4
0x18006fce8  jg      short loc_18006FCEE
0x18006fcea  mov     edi, esi
0x18006fcec  jmp     short loc_18006FCF4
0x18006fcee  movzx   edi, si
0x18006fcf1  or      edi, r15d
0x18006fcf4  test    rbp, rbp
0x18006fcf7  jz      short loc_18006FD02
0x18006fcf9  mov     rcx, rbp; pCertContext
0x18006fcfc  call    cs:__imp_CertFreeCertificateContext
0x18006fd02  test    edi, edi
0x18006fd04  jns     short loc_18006FD21
0x18006fd06  cmp     [rsp+0A8h+var_78], r14d
0x18006fd0b  mov     rcx, [rsp+0A8h+arg_28]; struct _CERT_CONTEXT **
0x18006fd13  cmovb   r14d, [rsp+0A8h+var_78]
0x18006fd19  mov     edx, r14d; unsigned int
0x18006fd1c  call    ?FreeCertificates@CertificateUtil@@SAXQEAPEBU_CERT_CONTEXT@@K@Z; CertificateUtil::FreeCertificates(_CERT_CONTEXT const * * const,ulong)
0x18006fd21  test    r12, r12
0x18006fd24  jz      short loc_18006FD57
0x18006fd26  xor     edx, edx; dwFlags
0x18006fd28  mov     rcx, r12; hCertStore
0x18006fd2b  call    cs:__imp_CertCloseStore
0x18006fd31  test    eax, eax
0x18006fd33  jnz     short loc_18006FD57
0x18006fd35  call    cs:__imp_GetLastError
0x18006fd3b  test    eax, eax
0x18006fd3d  jle     short loc_18006FD45
0x18006fd3f  movzx   eax, ax
0x18006fd42  or      eax, r15d
0x18006fd45  mov     r8d, eax
0x18006fd48  lea     rcx, aSCertclosestor; "%s: CertCloseStore failed with error co"...
0x18006fd4f  mov     rdx, rbx
0x18006fd52  call    ?TraceWarning@Logger@@SAJPEBGZZ; Logger::TraceWarning(ushort const *,...)
0x18006fd57  mov     rcx, [rsp+0A8h+hKey]; hKey
0x18006fd5c  test    rcx, rcx
0x18006fd5f  jz      short loc_18006FD84
0x18006fd61  call    cs:__imp_RegCloseKey
0x18006fd67  test    eax, eax
0x18006fd69  jz      short loc_18006FD84
0x18006fd6b  mov     r9d, eax
0x18006fd6e  lea     r8, aHkeyLocalMachi; "HKEY_LOCAL_MACHINE\\TargetSoftware\\Mic"...
0x18006fd75  mov     rdx, rbx
0x18006fd78  lea     rcx, aSCannotCloseRe; "%s: Cannot close reg key %s. RegCloseKe"...
0x18006fd7f  call    ?TraceWarning@Logger@@SAJPEBGZZ; Logger::TraceWarning(ushort const *,...)
0x18006fd84  cmp     [rsp+0A8h+var_6C], 0
0x18006fd89  jz      short loc_18006FDCA
0x18006fd8b  lea     rdx, aTargetsoftware_0; "TargetSoftware"
0x18006fd92  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18006fd99  call    cs:__imp_RegUnLoadKeyW
0x18006fd9f  lea     r8, aHkeyLocalMachi_2; "HKEY_LOCAL_MACHINE\\TargetSoftware"
  ... truncated ...
```
